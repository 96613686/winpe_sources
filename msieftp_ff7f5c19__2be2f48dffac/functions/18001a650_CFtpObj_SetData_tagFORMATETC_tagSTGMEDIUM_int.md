# CFtpObj::SetData(tagFORMATETC *,tagSTGMEDIUM *,int)

- ea: `0x18001a650`
- end: `0x18001a756`
- name: `?SetData@CFtpObj@@UEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@H@Z`
- size: `262`
- prototype: `__int64 __fastcall(CFtpObj *__hidden this, struct tagFORMATETC *, struct tagSTGMEDIUM *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000d85c`
- `0x18001a650`
- `0x18001abf8`
- `0x18001ae3c`
- `0x18001b2e0`

## import_xrefs

- `ole32!ReleaseStgMedium` at `0x18001a6dc`
- `ole32!ReleaseStgMedium` at `0x18001a6dc`
- `urlmon!CopyStgMedium` at `0x18001a6b3`
- `urlmon!CopyStgMedium` at `0x18001a6b3`

## pseudocode

```c
__int64 __fastcall CFtpObj::SetData(CFtpObj *this, struct tagFORMATETC *a2, struct tagSTGMEDIUM *a3)
{
  int Data; // eax
  const struct tagFORMATETC *v6; // rdx
  unsigned int v7; // edi
  HRESULT v8; // eax
  char *v9; // rbx
  bool v10; // zf
  int v12; // [rsp+20h] [rbp-28h] BYREF
  STGMEDIUM pstgmedDest; // [rsp+28h] [rbp-20h] BYREF

  v12 = 0;
  Data = CFtpObj::_FindData(this, a2, &v12);
  v7 = Data;
  if ( Data < 0 )
  {
    if ( Data == -2147024875 )
      return v7;
    if ( a3->tymed == 1 )
      return (unsigned int)CFtpObj::_SetExtraData((HDSA *)this, v6, a3);
    return (unsigned int)-2147221402;
  }
  if ( !v12 )
    return (unsigned int)-2147221404;
  if ( !a3->hBitmap )
    return (unsigned int)-2147221402;
  memset(&pstgmedDest, 0, sizeof(pstgmedDest));
  v8 = CopyStgMedium(a3, &pstgmedDest);
  pstgmedDest.pUnkForRelease = 0;
  v7 = v8;
  if ( v8 >= 0 )
  {
    v9 = (char *)this + 24 * v12;
    ReleaseStgMedium((LPSTGMEDIUM)(v9 + 152));
    v10 = v12 == 9;
    *(STGMEDIUM *)(v9 + 152) = pstgmedDest;
    if ( v10 && DataObj_GetDWORD((struct IDataObject *)this, (unsigned __int16)word_180032460, 0) == 2 )
      CFtpObj::_DeleteContents(this);
  }
  return v7;
}

```

## disassembly

```asm
0x18001a650  mov     rax, rsp
0x18001a653  mov     [rax+8], rbx
0x18001a657  mov     [rax+10h], rsi
0x18001a65b  push    rdi
0x18001a65c  sub     rsp, 40h
0x18001a660  mov     rbx, r8
0x18001a663  mov     dword ptr [rax-28h], 0
0x18001a66a  lea     r8, [rax-28h]; int *
0x18001a66e  mov     rsi, rcx
0x18001a671  call    ?_FindData@CFtpObj@@IEAAJPEBUtagFORMATETC@@PEAH@Z; CFtpObj::_FindData(tagFORMATETC const *,int *)
0x18001a676  mov     edi, eax
0x18001a678  test    eax, eax
0x18001a67a  js      loc_18001A724
0x18001a680  cmp     [rsp+48h+var_28], 0
0x18001a685  jnz     short loc_18001A691
0x18001a687  mov     edi, 80040064h
0x18001a68c  jmp     loc_18001A744
0x18001a691  cmp     qword ptr [rbx+8], 0
0x18001a696  jz      loc_18001A73F
0x18001a69c  xorps   xmm0, xmm0
0x18001a69f  lea     rdx, [rsp+48h+pstgmedDest]; pstgmedDest
0x18001a6a4  xor     eax, eax
0x18001a6a6  mov     rcx, rbx; pcstgmedSrc
0x18001a6a9  movups  xmmword ptr [rsp+48h+pstgmedDest.tymed], xmm0
0x18001a6ae  mov     [rsp+48h+pstgmedDest.pUnkForRelease], rax
0x18001a6b3  call    cs:__imp_CopyStgMedium
0x18001a6b9  mov     [rsp+48h+pstgmedDest.pUnkForRelease], 0
0x18001a6c2  mov     edi, eax
0x18001a6c4  test    eax, eax
0x18001a6c6  js      short loc_18001A744
0x18001a6c8  movsxd  rax, [rsp+48h+var_28]
0x18001a6cd  lea     rcx, [rax+rax*2]
0x18001a6d1  lea     rbx, [rsi+rcx*8]
0x18001a6d5  lea     rcx, [rbx+98h]; LPSTGMEDIUM
0x18001a6dc  call    cs:__imp_ReleaseStgMedium
0x18001a6e2  cmp     [rsp+48h+var_28], 9
0x18001a6e7  movups  xmm0, xmmword ptr [rsp+48h+pstgmedDest.tymed]
0x18001a6ec  movups  xmmword ptr [rbx+98h], xmm0
0x18001a6f3  movsd   xmm1, [rsp+48h+pstgmedDest.pUnkForRelease]
0x18001a6f9  movsd   qword ptr [rbx+0A8h], xmm1
0x18001a701  jnz     short loc_18001A744
0x18001a703  movzx   edx, cs:word_180032460; unsigned int
0x18001a70a  xor     r8d, r8d; unsigned int
0x18001a70d  mov     rcx, rsi; struct IDataObject *
0x18001a710  call    ?DataObj_GetDWORD@@YAKPEAUIDataObject@@IK@Z; DataObj_GetDWORD(IDataObject *,uint,ulong)
0x18001a715  cmp     eax, 2
0x18001a718  jnz     short loc_18001A744
0x18001a71a  mov     rcx, rsi; this
0x18001a71d  call    ?_DeleteContents@CFtpObj@@IEAAXXZ; CFtpObj::_DeleteContents(void)
0x18001a722  jmp     short loc_18001A744
0x18001a724  cmp     eax, 80070015h
0x18001a729  jz      short loc_18001A744
0x18001a72b  cmp     dword ptr [rbx], 1
0x18001a72e  jnz     short loc_18001A73F
0x18001a730  mov     r8, rbx; struct tagSTGMEDIUM *
0x18001a733  mov     rcx, rsi; this
0x18001a736  call    ?_SetExtraData@CFtpObj@@IEAAJPEBUtagFORMATETC@@PEBUtagSTGMEDIUM@@H@Z; CFtpObj::_SetExtraData(tagFORMATETC const *,tagSTGMEDIUM const *,int)
0x18001a73b  mov     edi, eax
0x18001a73d  jmp     short loc_18001A744
0x18001a73f  mov     edi, 80040066h
0x18001a744  mov     rbx, [rsp+48h+arg_0]
0x18001a749  mov     eax, edi
0x18001a74b  mov     rsi, [rsp+48h+arg_8]
0x18001a750  add     rsp, 40h
0x18001a754  pop     rdi
0x18001a755  retn
```
