# CWMReadSample::GetBufferAndLength(uchar * *,ulong *)

- ea: `0x180009770`
- end: `0x1800097bf`
- name: `?GetBufferAndLength@CWMReadSample@@UEAAJPEAPEAEPEAK@Z`
- size: `79`
- prototype: `__int64 __fastcall(CWMReadSample *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009770`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWMReadSample::GetBufferAndLength(CWMReadSample *this, unsigned __int8 **a2, unsigned int *a3)
{
  int v5; // ebx

  v5 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 **))(**((_QWORD **)this + 9) + 24LL))(
         *((_QWORD *)this + 9),
         a2);
  if ( v5 >= 0 )
    *a3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 88LL))(*((_QWORD *)this + 9));
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180009770  mov     [rsp+arg_0], rbx
0x180009775  mov     [rsp+arg_8], rsi
0x18000977a  push    rdi
0x18000977b  sub     rsp, 20h
0x18000977f  mov     rdi, rcx
0x180009782  mov     rsi, r8
0x180009785  mov     rcx, [rcx+48h]
0x180009789  mov     rax, [rcx]
0x18000978c  mov     rax, [rax+18h]
0x180009790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009795  mov     ebx, eax
0x180009797  test    eax, eax
0x180009799  js      short loc_1800097AD
0x18000979b  mov     rcx, [rdi+48h]
0x18000979f  mov     rdx, [rcx]
0x1800097a2  mov     rax, [rdx+58h]
0x1800097a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097ab  mov     [rsi], eax
0x1800097ad  mov     rsi, [rsp+28h+arg_8]
0x1800097b2  mov     eax, ebx
0x1800097b4  mov     rbx, [rsp+28h+arg_0]
0x1800097b9  add     rsp, 20h
0x1800097bd  pop     rdi
0x1800097be  retn
```
