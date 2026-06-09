# CASFOutput::SetUncompSurfacesInfo(ulong)

- ea: `0x18000d150`
- end: `0x18000d1d8`
- name: `?SetUncompSurfacesInfo@CASFOutput@@UEAAJK@Z`
- size: `136`
- prototype: `__int64 __fastcall(CASFOutput *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180009838`
- `0x18000d150`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFOutput::SetUncompSurfacesInfo(CASFOutput *this, unsigned int a2)
{
  unsigned int CodecInterface; // ebx
  void *v5; // [rsp+20h] [rbp-18h] BYREF

  v5 = 0;
  CodecInterface = CASFOutput::GetCodecInterface(
                     (CASFOutput *)((char *)this - 232),
                     &IID_IAMVideoAcceleratorNotify,
                     &v5);
  if ( v5 )
  {
    CodecInterface = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v5 + 32LL))(v5, a2);
    if ( v5 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return CodecInterface;
}

```

## disassembly

```asm
0x18000d150  mov     [rsp+arg_10], rbx
0x18000d155  push    rdi
0x18000d156  sub     rsp, 30h
0x18000d15a  mov     rax, cs:__security_cookie
0x18000d161  xor     rax, rsp
0x18000d164  mov     [rsp+38h+var_10], rax
0x18000d169  mov     edi, edx
0x18000d16b  mov     [rsp+38h+var_18], 0
0x18000d174  lea     rdx, IID_IAMVideoAcceleratorNotify; struct _GUID *
0x18000d17b  add     rcx, 0FFFFFFFFFFFFFF18h; this
0x18000d182  lea     r8, [rsp+38h+var_18]; void **
0x18000d187  call    ?GetCodecInterface@CASFOutput@@QEAAJAEBU_GUID@@PEAPEAX@Z; CASFOutput::GetCodecInterface(_GUID const &,void * *)
0x18000d18c  mov     rcx, [rsp+38h+var_18]
0x18000d191  mov     ebx, eax
0x18000d193  test    rcx, rcx
0x18000d196  jz      short loc_18000D1BE
0x18000d198  mov     rax, [rcx]
0x18000d19b  mov     edx, edi
0x18000d19d  mov     rax, [rax+20h]
0x18000d1a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1a6  mov     rcx, [rsp+38h+var_18]
0x18000d1ab  mov     ebx, eax
0x18000d1ad  test    rcx, rcx
0x18000d1b0  jz      short loc_18000D1BE
0x18000d1b2  mov     rax, [rcx]
0x18000d1b5  mov     rax, [rax+10h]
0x18000d1b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1be  mov     eax, ebx
0x18000d1c0  mov     rcx, [rsp+38h+var_10]
0x18000d1c5  xor     rcx, rsp; StackCookie
0x18000d1c8  call    __security_check_cookie
0x18000d1cd  mov     rbx, [rsp+38h+arg_10]
0x18000d1d2  add     rsp, 30h
0x18000d1d6  pop     rdi
0x18000d1d7  retn
```
