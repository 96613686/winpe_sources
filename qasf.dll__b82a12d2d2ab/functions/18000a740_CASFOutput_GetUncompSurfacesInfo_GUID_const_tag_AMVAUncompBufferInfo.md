# CASFOutput::GetUncompSurfacesInfo(_GUID const *,_tag_AMVAUncompBufferInfo *)

- ea: `0x18000a740`
- end: `0x18000a7cb`
- name: `?GetUncompSurfacesInfo@CASFOutput@@UEAAJPEBU_GUID@@PEAU_tag_AMVAUncompBufferInfo@@@Z`
- size: `139`
- prototype: `__int64 __fastcall(CASFOutput *__hidden this, const struct _GUID *, struct _tag_AMVAUncompBufferInfo *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180009838`
- `0x18000a740`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFOutput::GetUncompSurfacesInfo(
        CASFOutput *this,
        const struct _GUID *a2,
        struct _tag_AMVAUncompBufferInfo *a3)
{
  unsigned int CodecInterface; // ebx
  void *v7; // [rsp+20h] [rbp-28h] BYREF

  v7 = 0;
  CodecInterface = CASFOutput::GetCodecInterface(
                     (CASFOutput *)((char *)this - 232),
                     &IID_IAMVideoAcceleratorNotify,
                     &v7);
  if ( v7 )
  {
    CodecInterface = (*(__int64 (__fastcall **)(void *, const struct _GUID *, struct _tag_AMVAUncompBufferInfo *))(*(_QWORD *)v7 + 24LL))(
                       v7,
                       a2,
                       a3);
    if ( v7 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 16LL))(v7);
  }
  return CodecInterface;
}

```

## disassembly

```asm
0x18000a740  push    rbx
0x18000a742  push    rsi
0x18000a743  push    rdi
0x18000a744  sub     rsp, 30h
0x18000a748  mov     rax, cs:__security_cookie
0x18000a74f  xor     rax, rsp
0x18000a752  mov     [rsp+48h+var_20], rax
0x18000a757  mov     rsi, r8
0x18000a75a  mov     [rsp+48h+var_28], 0
0x18000a763  mov     rdi, rdx
0x18000a766  lea     r8, [rsp+48h+var_28]; void **
0x18000a76b  lea     rdx, IID_IAMVideoAcceleratorNotify; struct _GUID *
0x18000a772  add     rcx, 0FFFFFFFFFFFFFF18h; this
0x18000a779  call    ?GetCodecInterface@CASFOutput@@QEAAJAEBU_GUID@@PEAPEAX@Z; CASFOutput::GetCodecInterface(_GUID const &,void * *)
0x18000a77e  mov     rcx, [rsp+48h+var_28]
0x18000a783  mov     ebx, eax
0x18000a785  test    rcx, rcx
0x18000a788  jz      short loc_18000A7B4
0x18000a78a  mov     rax, [rcx]
0x18000a78d  mov     r8, rsi
0x18000a790  mov     rdx, rdi
0x18000a793  mov     rax, [rax+18h]
0x18000a797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a79c  mov     rcx, [rsp+48h+var_28]
0x18000a7a1  mov     ebx, eax
0x18000a7a3  test    rcx, rcx
0x18000a7a6  jz      short loc_18000A7B4
0x18000a7a8  mov     rax, [rcx]
0x18000a7ab  mov     rax, [rax+10h]
0x18000a7af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7b4  mov     eax, ebx
0x18000a7b6  mov     rcx, [rsp+48h+var_20]
0x18000a7bb  xor     rcx, rsp; StackCookie
0x18000a7be  call    __security_check_cookie
0x18000a7c3  add     rsp, 30h
0x18000a7c7  pop     rdi
0x18000a7c8  pop     rsi
0x18000a7c9  pop     rbx
0x18000a7ca  retn
```
