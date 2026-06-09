# _attribute_t::SetValue(ushort const *)

- ea: `0x180007dc0`
- end: `0x180007e51`
- name: `?SetValue@_attribute_t@@QEAAJPEBG@Z`
- size: `145`
- prototype: `__int64 __fastcall(LPVOID *this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006274`
- `0x180006ac0`
- `0x1800086b0`
- `0x18000d100`

## callees

- `0x180007dc0`
- `0x180008084`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007de3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007e03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007de3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007e03`

## pseudocode

```c
__int64 __fastcall _attribute_t::SetValue(LPVOID *this, const unsigned __int16 *a2)
{
  __int64 result; // rax
  int v5; // ecx

  if ( *((_DWORD *)this + 2) == 10 )
  {
    CoTaskMemFree(this[2]);
    this[2] = 0;
  }
  else if ( *((_DWORD *)this + 2) == 14 )
  {
    CoTaskMemFree(this[3]);
    this[3] = 0;
    *((_DWORD *)this + 4) = 0;
  }
  result = 0;
  if ( a2 )
  {
    result = StringCchCopyWithAlloc((unsigned __int16 **)this + 2, 0xFFFFu, a2);
    v5 = 0;
    if ( (int)result >= 0 )
      v5 = 10;
    *((_DWORD *)this + 2) = v5;
  }
  return result;
}

```

## disassembly

```asm
0x180007dc0  mov     [rsp+arg_0], rbx
0x180007dc5  mov     [rsp+arg_8], rbp
0x180007dca  push    rdi
0x180007dcb  sub     rsp, 20h
0x180007dcf  mov     ebp, 0Ah
0x180007dd4  mov     rdi, rdx
0x180007dd7  mov     rbx, rcx
0x180007dda  cmp     [rcx+8], ebp
0x180007ddd  jnz     short loc_180007DF9
0x180007ddf  mov     rcx, [rcx+10h]; pv
0x180007de3  call    cs:__imp_CoTaskMemFree
0x180007dea  nop     dword ptr [rax+rax+00h]
0x180007def  mov     qword ptr [rbx+10h], 0
0x180007df7  jmp     short loc_180007E1E
0x180007df9  cmp     dword ptr [rcx+8], 0Eh
0x180007dfd  jnz     short loc_180007E1E
0x180007dff  mov     rcx, [rcx+18h]; pv
0x180007e03  call    cs:__imp_CoTaskMemFree
0x180007e0a  nop     dword ptr [rax+rax+00h]
0x180007e0f  mov     qword ptr [rbx+18h], 0
0x180007e17  mov     dword ptr [rbx+10h], 0
0x180007e1e  xor     eax, eax
0x180007e20  test    rdi, rdi
0x180007e23  jz      short loc_180007E40
0x180007e25  lea     rcx, [rbx+10h]; unsigned __int16 **
0x180007e29  mov     r8, rdi; unsigned __int16 *
0x180007e2c  mov     edx, 0FFFFh; unsigned __int64
0x180007e31  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x180007e36  xor     ecx, ecx
0x180007e38  test    eax, eax
0x180007e3a  cmovns  ecx, ebp
0x180007e3d  mov     [rbx+8], ecx
0x180007e40  mov     rbx, [rsp+28h+arg_0]
0x180007e45  mov     rbp, [rsp+28h+arg_8]
0x180007e4a  add     rsp, 20h
0x180007e4e  pop     rdi
0x180007e4f  retn
```
