# SslGetContextToken

- ea: `0x140028eb0`
- end: `0x140028f94`
- name: `SslGetContextToken`
- size: `228`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140003e30`
- `0x140028eb0`
- `0x14002fd60`
- `0x14002fdf0`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x140028f1e`
- `ntoskrnl!ExGetPreviousMode` at `0x140028f1e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140028f57`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140028f57`

## pseudocode

```c
__int64 __fastcall SslGetContextToken(PVOID Entry, _QWORD *a2, _QWORD *a3)
{
  NTSTATUS v6; // edi
  __int64 v7; // rax
  KPROCESSOR_MODE PreviousMode; // al
  PVOID Object; // [rsp+78h] [rbp+20h] BYREF

  GetExternalSchannelAlgorithmsDeferred();
  v6 = SslReferenceContext(Entry, 0);
  if ( v6 >= 0 )
  {
    v7 = *((_QWORD *)Entry + 35);
    if ( v7 )
    {
      if ( a2 )
        *a2 = v7;
      if ( a3 )
      {
        if ( !*((_QWORD *)Entry + 35)
          || *((_QWORD *)Entry + 37)
          || (PreviousMode = ExGetPreviousMode(),
              Object = 0,
              v6 = ObReferenceObjectByHandle(*((HANDLE *)Entry + 35), 0xCu, 0, PreviousMode, &Object, 0),
              *((_QWORD *)Entry + 37) = Object,
              v6 >= 0) )
        {
          *a3 = *((_QWORD *)Entry + 37);
        }
      }
    }
    else
    {
      v6 = -2146893045;
      if ( *((_DWORD *)Entry + 72) )
        v6 = *((_DWORD *)Entry + 72);
    }
    SslDerefContext(Entry);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140028eb0  push    rbx
0x140028eb2  push    rsi
0x140028eb3  push    rdi
0x140028eb4  push    r14
0x140028eb6  sub     rsp, 38h
0x140028eba  mov     r14, r8
0x140028ebd  mov     rsi, rdx
0x140028ec0  mov     rbx, rcx
0x140028ec3  call    GetExternalSchannelAlgorithmsDeferred
0x140028ec8  xor     edx, edx
0x140028eca  mov     rcx, rbx
0x140028ecd  call    SslReferenceContext
0x140028ed2  mov     edi, eax
0x140028ed4  test    eax, eax
0x140028ed6  js      loc_140028F87
0x140028edc  mov     rax, [rbx+118h]
0x140028ee3  test    rax, rax
0x140028ee6  jnz     short loc_140028EFD
0x140028ee8  mov     eax, [rbx+120h]
0x140028eee  mov     edi, 8009030Bh
0x140028ef3  test    eax, eax
0x140028ef5  cmovnz  edi, eax
0x140028ef8  jmp     loc_140028F7F
0x140028efd  test    rsi, rsi
0x140028f00  jz      short loc_140028F05
0x140028f02  mov     [rsi], rax
0x140028f05  test    r14, r14
0x140028f08  jz      short loc_140028F7F
0x140028f0a  cmp     qword ptr [rbx+118h], 0
0x140028f12  jz      short loc_140028F75
0x140028f14  cmp     qword ptr [rbx+128h], 0
0x140028f1c  jnz     short loc_140028F75
0x140028f1e  call    cs:__imp_ExGetPreviousMode
0x140028f25  nop     dword ptr [rax+rax+00h]
0x140028f2a  xor     r8d, r8d; ObjectType
0x140028f2d  mov     [rsp+58h+HandleInformation], 0; HandleInformation
0x140028f36  lea     rcx, [rsp+58h+arg_18]
0x140028f3b  mov     [rsp+58h+arg_18], 0
0x140028f44  mov     [rsp+58h+Object], rcx; Object
0x140028f49  mov     r9b, al; AccessMode
0x140028f4c  mov     rcx, [rbx+118h]; Handle
0x140028f53  lea     edx, [r8+0Ch]; DesiredAccess
0x140028f57  call    cs:__imp_ObReferenceObjectByHandle
0x140028f5e  nop     dword ptr [rax+rax+00h]
0x140028f63  mov     edi, eax
0x140028f65  mov     rax, [rsp+58h+arg_18]
0x140028f6a  mov     [rbx+128h], rax
0x140028f71  test    edi, edi
0x140028f73  js      short loc_140028F7F
0x140028f75  mov     rax, [rbx+128h]
0x140028f7c  mov     [r14], rax
0x140028f7f  mov     rcx, rbx; Entry
0x140028f82  call    SslDerefContext
0x140028f87  mov     eax, edi
0x140028f89  add     rsp, 38h
0x140028f8d  pop     r14
0x140028f8f  pop     rdi
0x140028f90  pop     rsi
0x140028f91  pop     rbx
0x140028f92  retn
```
