# CWrapperOutputPin::CompleteConnect(IPin *)

- ea: `0x180019180`
- end: `0x180019240`
- name: `?CompleteConnect@CWrapperOutputPin@@UEAAJPEAUIPin@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(CWrapperOutputPin *__hidden this, struct IPin *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180019180`
- `0x18001aab8`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWrapperOutputPin::CompleteConnect(CWrapperOutputPin *this, struct IPin *a2)
{
  int v3; // edi
  __int64 v4; // rax
  __int64 v6; // [rsp+20h] [rbp-18h] BYREF

  v3 = (*(__int64 (__fastcall **)(CWrapperOutputPin *, _QWORD, char *))(*(_QWORD *)this + 112LL))(
         this,
         *((_QWORD *)this + 28),
         (char *)this + 216);
  if ( v3 >= 0 && CWrapperOutputPin::UsingDXVATransport(this) )
  {
    v4 = *((_QWORD *)this + 10);
    v6 = 0;
    v3 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v4 + 160))(
           *(_QWORD *)(v4 + 160),
           &IID_IWMCodecAMVideoAccelerator,
           &v6);
    if ( v3 >= 0 )
      v3 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v6 + 32LL))(v6, (char *)this + 104);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180019180  mov     [rsp+arg_8], rbx
0x180019185  push    rdi
0x180019186  sub     rsp, 30h
0x18001918a  mov     rax, cs:__security_cookie
0x180019191  xor     rax, rsp
0x180019194  mov     [rsp+38h+var_10], rax
0x180019199  mov     rax, [rcx]
0x18001919c  lea     r8, [rcx+0D8h]
0x1800191a3  mov     rdx, [rcx+0E0h]
0x1800191aa  mov     rbx, rcx
0x1800191ad  mov     rax, [rax+70h]
0x1800191b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191b6  mov     edi, eax
0x1800191b8  test    eax, eax
0x1800191ba  js      short loc_180019226
0x1800191bc  mov     rcx, rbx; this
0x1800191bf  call    ?UsingDXVATransport@CWrapperOutputPin@@IEAA_NXZ; CWrapperOutputPin::UsingDXVATransport(void)
0x1800191c4  test    al, al
0x1800191c6  jz      short loc_180019226
0x1800191c8  mov     rax, [rbx+50h]
0x1800191cc  lea     r8, [rsp+38h+var_18]
0x1800191d1  mov     [rsp+38h+var_18], 0
0x1800191da  lea     rdx, IID_IWMCodecAMVideoAccelerator
0x1800191e1  mov     rcx, [rax+0A0h]
0x1800191e8  mov     rax, [rcx]
0x1800191eb  mov     rax, [rax]
0x1800191ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191f3  mov     edi, eax
0x1800191f5  test    eax, eax
0x1800191f7  js      short loc_180019210
0x1800191f9  mov     rcx, [rsp+38h+var_18]
0x1800191fe  lea     rdx, [rbx+68h]
0x180019202  mov     rax, [rcx]
0x180019205  mov     rax, [rax+20h]
0x180019209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001920e  mov     edi, eax
0x180019210  mov     rcx, [rsp+38h+var_18]
0x180019215  test    rcx, rcx
0x180019218  jz      short loc_180019226
0x18001921a  mov     rax, [rcx]
0x18001921d  mov     rax, [rax+10h]
0x180019221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019226  mov     eax, edi
0x180019228  mov     rcx, [rsp+38h+var_10]
0x18001922d  xor     rcx, rsp; StackCookie
0x180019230  call    __security_check_cookie
0x180019235  mov     rbx, [rsp+38h+arg_8]
0x18001923a  add     rsp, 30h
0x18001923e  pop     rdi
0x18001923f  retn
```
