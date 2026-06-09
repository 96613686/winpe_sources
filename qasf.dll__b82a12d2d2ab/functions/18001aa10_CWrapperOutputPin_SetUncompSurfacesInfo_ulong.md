# CWrapperOutputPin::SetUncompSurfacesInfo(ulong)

- ea: `0x18001aa10`
- end: `0x18001aab2`
- name: `?SetUncompSurfacesInfo@CWrapperOutputPin@@UEAAJK@Z`
- size: `162`
- prototype: `__int64 __fastcall(CWrapperOutputPin *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x18001aa10`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWrapperOutputPin::SetUncompSurfacesInfo(CWrapperOutputPin *this, unsigned int a2)
{
  __int64 v2; // rax
  int v4; // ebx
  void (*v5)(void); // rax
  __int64 v7; // [rsp+20h] [rbp-18h] BYREF

  v2 = *((_QWORD *)this - 20);
  v7 = 0;
  v4 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v2 + 160))(
         *(_QWORD *)(v2 + 160),
         &IID_IAMVideoAcceleratorNotify,
         &v7);
  if ( v4 < 0 )
  {
    if ( v7 )
    {
      v5 = *(void (**)(void))(*(_QWORD *)v7 + 16LL);
      goto LABEL_6;
    }
  }
  else
  {
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 32LL))(v7, a2);
    if ( v7 )
    {
      v5 = *(void (**)(void))(*(_QWORD *)v7 + 16LL);
LABEL_6:
      v5();
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001aa10  mov     [rsp+arg_10], rbx
0x18001aa15  push    rdi
0x18001aa16  sub     rsp, 30h
0x18001aa1a  mov     rax, cs:__security_cookie
0x18001aa21  xor     rax, rsp
0x18001aa24  mov     [rsp+38h+var_10], rax
0x18001aa29  mov     rax, [rcx-0A0h]
0x18001aa30  lea     r8, [rsp+38h+var_18]
0x18001aa35  mov     [rsp+38h+var_18], 0
0x18001aa3e  mov     edi, edx
0x18001aa40  lea     rdx, IID_IAMVideoAcceleratorNotify
0x18001aa47  mov     rcx, [rax+0A0h]
0x18001aa4e  mov     rax, [rcx]
0x18001aa51  mov     rax, [rax]
0x18001aa54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa59  mov     rcx, [rsp+38h+var_18]
0x18001aa5e  mov     ebx, eax
0x18001aa60  test    eax, eax
0x18001aa62  js      short loc_18001AA87
0x18001aa64  mov     rax, [rcx]
0x18001aa67  mov     edx, edi
0x18001aa69  mov     rax, [rax+20h]
0x18001aa6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa72  mov     rcx, [rsp+38h+var_18]
0x18001aa77  mov     ebx, eax
0x18001aa79  test    rcx, rcx
0x18001aa7c  jz      short loc_18001AA98
0x18001aa7e  mov     rdx, [rcx]
0x18001aa81  mov     rax, [rdx+10h]
0x18001aa85  jmp     short loc_18001AA93
0x18001aa87  test    rcx, rcx
0x18001aa8a  jz      short loc_18001AA98
0x18001aa8c  mov     rax, [rcx]
0x18001aa8f  mov     rax, [rax+10h]
0x18001aa93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa98  mov     eax, ebx
0x18001aa9a  mov     rcx, [rsp+38h+var_10]
0x18001aa9f  xor     rcx, rsp; StackCookie
0x18001aaa2  call    __security_check_cookie
0x18001aaa7  mov     rbx, [rsp+38h+arg_10]
0x18001aaac  add     rsp, 30h
0x18001aab0  pop     rdi
0x18001aab1  retn
```
