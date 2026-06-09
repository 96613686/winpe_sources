# update_thread_multibyte_data_internal

- ea: `0x180016cb4`
- end: `0x180016d5b`
- name: `update_thread_multibyte_data_internal`
- size: `167`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180016a3c`
- `0x180016dcc`

## callees

- `0x1800150f8`
- `0x180015c20`
- `0x1800160b4`
- `0x1800160d4`
- `0x180016cb4`

## pseudocode

```c
__int64 *__fastcall update_thread_multibyte_data_internal(__int64 a1, void **a2)
{
  __int64 *v4; // rbx

  if ( (_globallocalestatus & *(_DWORD *)(a1 + 936)) != 0 && *(_QWORD *)(a1 + 144) )
  {
    v4 = *(__int64 **)(a1 + 136);
  }
  else
  {
    _acrt_lock(5);
    v4 = *(__int64 **)(a1 + 136);
    if ( v4 != *a2 )
    {
      if ( v4 && !_InterlockedDecrement((volatile signed __int32 *)v4) && v4 != _acrt_initial_multibyte_data )
        free_base(v4);
      v4 = (__int64 *)*a2;
      *(_QWORD *)(a1 + 136) = *a2;
      _InterlockedIncrement((volatile signed __int32 *)v4);
    }
    _acrt_unlock(5);
  }
  if ( !v4 )
    abort();
  return v4;
}

```

## disassembly

```asm
0x180016cb4  mov     [rsp+arg_0], rbx
0x180016cb9  mov     [rsp+arg_8], rsi
0x180016cbe  push    rdi
0x180016cbf  sub     rsp, 20h
0x180016cc3  mov     rsi, rdx
0x180016cc6  mov     rdi, rcx
0x180016cc9  mov     eax, cs:__globallocalestatus
0x180016ccf  test    [rcx+3A8h], eax
0x180016cd5  jz      short loc_180016CEA
0x180016cd7  cmp     qword ptr [rcx+90h], 0
0x180016cdf  jz      short loc_180016CEA
0x180016ce1  mov     rbx, [rcx+88h]
0x180016ce8  jmp     short loc_180016D3D
0x180016cea  mov     ecx, 5
0x180016cef  call    __acrt_lock
0x180016cf4  nop
0x180016cf5  mov     rbx, [rdi+88h]
0x180016cfc  cmp     rbx, [rsi]
0x180016cff  jz      short loc_180016D33
0x180016d01  test    rbx, rbx
0x180016d04  jz      short loc_180016D26
0x180016d06  or      eax, 0FFFFFFFFh
0x180016d09  lock xadd [rbx], eax
0x180016d0d  sub     eax, 1
0x180016d10  jnz     short loc_180016D26
0x180016d12  lea     rax, __acrt_initial_multibyte_data
0x180016d19  cmp     rbx, rax
0x180016d1c  jz      short loc_180016D26
0x180016d1e  mov     rcx, rbx; Block
0x180016d21  call    _free_base
0x180016d26  mov     rbx, [rsi]
0x180016d29  mov     [rdi+88h], rbx
0x180016d30  lock inc dword ptr [rbx]
0x180016d33  mov     ecx, 5
0x180016d38  call    __acrt_unlock
0x180016d3d  test    rbx, rbx
0x180016d40  jz      short loc_180016D55
0x180016d42  mov     rax, rbx
0x180016d45  mov     rbx, [rsp+28h+arg_0]
0x180016d4a  mov     rsi, [rsp+28h+arg_8]
0x180016d4f  add     rsp, 20h
0x180016d53  pop     rdi
0x180016d54  retn
0x180016d55  call    abort
```
