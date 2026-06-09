# __acrt_update_thread_multibyte_data

- ea: `0x18001a328`
- end: `0x18001a3e7`
- name: `__acrt_update_thread_multibyte_data`
- size: `191`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001a140`
- `0x18001b278`

## callees

- `0x1800183f4`
- `0x1800189e4`
- `0x180018bd8`
- `0x180018c38`
- `0x180019608`
- `0x18001a328`

## pseudocode

```c
__int64 *_acrt_update_thread_multibyte_data()
{
  __int64 v0; // rax
  __int64 v1; // rdi
  __int64 *v2; // rbx
  __int64 *Block; // [rsp+30h] [rbp+8h]

  v0 = _acrt_getptd();
  v1 = v0;
  if ( (_globallocalestatus & *(_DWORD *)(v0 + 936)) != 0 && *(_QWORD *)(v0 + 144) )
  {
    v2 = *(__int64 **)(v0 + 136);
  }
  else
  {
    _acrt_lock(5);
    v2 = *(__int64 **)(v1 + 136);
    if ( v2 != _acrt_current_multibyte_data )
    {
      if ( v2
        && _InterlockedExchangeAdd((volatile signed __int32 *)v2, 0xFFFFFFFF) == 1
        && v2 != _acrt_initial_multibyte_data )
      {
        free_base(v2);
      }
      *(_QWORD *)(v1 + 136) = _acrt_current_multibyte_data;
      Block = (__int64 *)_acrt_current_multibyte_data;
      _InterlockedIncrement((volatile signed __int32 *)_acrt_current_multibyte_data);
      v2 = Block;
    }
    _acrt_unlock(5);
  }
  if ( !v2 )
    abort();
  return v2;
}

```

## disassembly

```asm
0x18001a328  mov     [rsp+arg_8], rbx
0x18001a32d  push    rdi
0x18001a32e  sub     rsp, 20h
0x18001a332  call    __acrt_getptd
0x18001a337  mov     rdi, rax
0x18001a33a  mov     ecx, cs:__globallocalestatus
0x18001a340  test    [rax+3A8h], ecx
0x18001a346  jz      short loc_18001A35B
0x18001a348  cmp     qword ptr [rax+90h], 0
0x18001a350  jz      short loc_18001A35B
0x18001a352  mov     rbx, [rax+88h]
0x18001a359  jmp     short loc_18001A3CE
0x18001a35b  mov     ecx, 5
0x18001a360  call    __acrt_lock
0x18001a365  nop
0x18001a366  mov     rbx, [rdi+88h]
0x18001a36d  mov     [rsp+28h+Block], rbx
0x18001a372  cmp     rbx, cs:__acrt_current_multibyte_data
0x18001a379  jz      short loc_18001A3C4
0x18001a37b  test    rbx, rbx
0x18001a37e  jz      short loc_18001A3A2
0x18001a380  or      eax, 0FFFFFFFFh
0x18001a383  lock xadd [rbx], eax
0x18001a387  cmp     eax, 1
0x18001a38a  jnz     short loc_18001A3A2
0x18001a38c  lea     rax, __acrt_initial_multibyte_data
0x18001a393  mov     rcx, [rsp+28h+Block]; Block
0x18001a398  cmp     rcx, rax
0x18001a39b  jz      short loc_18001A3A2
0x18001a39d  call    _free_base
0x18001a3a2  mov     rax, cs:__acrt_current_multibyte_data
0x18001a3a9  mov     [rdi+88h], rax
0x18001a3b0  mov     rax, cs:__acrt_current_multibyte_data
0x18001a3b7  mov     [rsp+28h+Block], rax
0x18001a3bc  lock inc dword ptr [rax]
0x18001a3bf  mov     rbx, [rsp+28h+Block]
0x18001a3c4  mov     ecx, 5
0x18001a3c9  call    __acrt_unlock
0x18001a3ce  test    rbx, rbx
0x18001a3d1  jnz     short loc_18001A3D9
0x18001a3d3  call    abort
0x18001a3d9  mov     rax, rbx
0x18001a3dc  mov     rbx, [rsp+28h+arg_8]
0x18001a3e1  add     rsp, 20h
0x18001a3e5  pop     rdi
0x18001a3e6  retn
0x18001f775  push    rbp
0x18001f777  sub     rsp, 20h
0x18001f77b  mov     rbp, rdx
0x18001f77e  mov     ecx, 5
0x18001f783  add     rsp, 20h
0x18001f787  pop     rbp
0x18001f788  jmp     __acrt_unlock
```
