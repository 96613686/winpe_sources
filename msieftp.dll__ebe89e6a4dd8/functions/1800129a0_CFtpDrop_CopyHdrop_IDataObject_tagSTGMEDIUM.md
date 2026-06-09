# CFtpDrop::CopyHdrop(IDataObject *,tagSTGMEDIUM *)

- ea: `0x1800129a0`
- end: `0x180012bc4`
- name: `?CopyHdrop@CFtpDrop@@IEAAJPEAUIDataObject@@PEAUtagSTGMEDIUM@@@Z`
- size: `548`
- prototype: `__int64 __fastcall(CFtpDrop *__hidden this, struct IDataObject *, struct tagSTGMEDIUM *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180014100`

## callees

- `0x180002240`
- `0x180012060`
- `0x1800129a0`
- `0x180012f28`
- `0x1800147a4`
- `0x180025324`
- `0x1800253d4`
- `0x180028010`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x1800129d1`
- `KERNEL32!GlobalLock` at `0x180012a56`
- `KERNEL32!GlobalLock` at `0x1800129d1`
- `KERNEL32!GlobalLock` at `0x180012a56`
- `KERNEL32!GlobalUnlock` at `0x180012a02`
- `KERNEL32!GlobalUnlock` at `0x180012a99`
- `KERNEL32!GlobalUnlock` at `0x180012a02`
- `KERNEL32!GlobalUnlock` at `0x180012a99`
- `ole32!ReleaseStgMedium` at `0x180012b98`
- `ole32!ReleaseStgMedium` at `0x180012b98`

## pseudocode

```c
__int64 __fastcall CFtpDrop::CopyHdrop(CFtpDrop *this, struct IDataObject *a2, struct tagSTGMEDIUM *a3)
{
  const unsigned __int16 *v5; // rax
  int v6; // r8d
  unsigned __int16 *v7; // rdi
  LPWSTR *v8; // rcx
  int v9; // esi
  const unsigned __int16 *v10; // rdx
  struct IDataObjectVtbl *lpVtbl; // rax
  __int16 *v12; // rdx
  HRESULT (__stdcall *GetData)(IDataObject *, FORMATETC *, STGMEDIUM *); // rax
  int v14; // eax
  int v15; // r8d
  unsigned int v16; // r9d
  HBITMAP hBitmap; // rcx
  const CHAR *v18; // rax
  CHAR *v19; // rdi
  LPWSTR *v20; // rcx
  __int64 v21; // r9
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // rcx
  int v25; // edi
  CDropOperation *v26; // rbx
  unsigned int v28; // [rsp+28h] [rbp-D8h]
  CDropOperation *v29; // [rsp+40h] [rbp-C0h] BYREF
  STGMEDIUM v30; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v31; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v32[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v33[264]; // [rsp+280h] [rbp+180h] BYREF

  v5 = (const unsigned __int16 *)GlobalLock(a3->hBitmap);
  v7 = (unsigned __int16 *)v5;
  if ( !v5 )
    return (unsigned int)-2147024809;
  v8 = (LPWSTR *)((char *)this + 72);
  v9 = 1;
  if ( *v5 == 8 )
  {
    v10 = v5 + 4;
  }
  else
  {
    v10 = (const unsigned __int16 *)((char *)v5 + *(unsigned int *)v5);
    if ( *((_DWORD *)v5 + 4) )
    {
      Str_StrAndThunkW(v8, v10, v6);
      v9 = 0;
      goto LABEL_5;
    }
  }
  Str_StrAndThunkA(v8, (LPCSTR)v10, v6);
LABEL_5:
  GlobalUnlock(v7);
  lpVtbl = a2->lpVtbl;
  v12 = &word_1800324A0;
  memset(&v30, 0, sizeof(v30));
  GetData = lpVtbl->GetData;
  if ( !v9 )
    v12 = &word_1800324C0;
  v14 = ((__int64 (__fastcall *)(struct IDataObject *, __int16 *, STGMEDIUM *))GetData)(a2, v12, &v30);
  hBitmap = v30.hBitmap;
  if ( v14 < 0 )
    hBitmap = 0;
  v30.hBitmap = hBitmap;
  if ( hBitmap )
  {
    v18 = (const CHAR *)GlobalLock(hBitmap);
    v19 = (CHAR *)v18;
    if ( v18 )
    {
      v20 = (LPWSTR *)((char *)this + 80);
      if ( v9 )
        Str_StrAndThunkA(v20, v18, v15);
      else
        Str_StrAndThunkW(v20, (const unsigned __int16 *)v18, v15);
      GlobalUnlock(v19);
    }
  }
  if ( *((_QWORD *)this + 10)
    || (Str_StrAndThunkW((LPWSTR *)this + 10, *((const unsigned __int16 **)this + 9), v15), *((_QWORD *)this + 10)) )
  {
    **((_DWORD **)this + 7) = 1;
    v31 = (unsigned __int16 *)*((_QWORD *)this + 9);
    v29 = (CDropOperation *)*((_QWORD *)this + 10);
    *((_DWORD *)this + 17) = 0;
    while ( !_EnumOneHdrop((const unsigned __int16 **)&v31, (const unsigned __int16 **)&v29, v33, v16, v32, v28) )
      ++*((_DWORD *)this + 17);
    v21 = *((_QWORD *)this + 10);
    v22 = *((_QWORD *)this + 9);
    v23 = *((_QWORD *)this + 4);
    v24 = *((_QWORD *)this + 2);
    v29 = 0;
    v25 = CDropOperation_Create(v24, v23, v22, v21, &v29);
    if ( v25 >= 0 )
    {
      *((_QWORD *)this + 9) = 0;
      *((_QWORD *)this + 10) = 0;
      v26 = v29;
      v25 = CDropOperation::DoOperation(v29, 1);
      (*(void (__fastcall **)(CDropOperation *))(*(_QWORD *)v26 + 16LL))(v26);
    }
  }
  else
  {
    v25 = -2147024809;
  }
  if ( v30.hBitmap )
    ReleaseStgMedium(&v30);
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x1800129a0  push    rbp
0x1800129a2  push    rbx
0x1800129a3  push    rsi
0x1800129a4  push    rdi
0x1800129a5  push    r14
0x1800129a7  lea     rbp, [rsp-3A0h]
0x1800129af  sub     rsp, 4A0h
0x1800129b6  mov     rax, cs:__security_cookie
0x1800129bd  xor     rax, rsp
0x1800129c0  mov     [rbp+3C0h+var_30], rax
0x1800129c7  mov     rbx, rcx
0x1800129ca  mov     r14, rdx
0x1800129cd  mov     rcx, [r8+8]; hMem
0x1800129d1  call    cs:__imp_GlobalLock
0x1800129d7  mov     rdi, rax
0x1800129da  test    rax, rax
0x1800129dd  jz      loc_180012BA0
0x1800129e3  cmp     word ptr [rax], 8
0x1800129e7  lea     rcx, [rbx+48h]; ppsz
0x1800129eb  mov     esi, 1
0x1800129f0  jnz     loc_180012A76
0x1800129f6  lea     rdx, [rax+8]; lpString
0x1800129fa  call    ?Str_StrAndThunkA@@YAJPEAPEAGPEBDH@Z; Str_StrAndThunkA(ushort * *,char const *,int)
0x1800129ff  mov     rcx, rdi; hMem
0x180012a02  call    cs:__imp_GlobalUnlock
0x180012a08  xor     eax, eax
0x180012a0a  lea     r8, [rsp+4C0h+var_478]
0x180012a0f  mov     [rsp+4C0h+var_478.pUnkForRelease], rax
0x180012a14  xorps   xmm0, xmm0
0x180012a17  mov     rax, [r14]
0x180012a1a  mov     rcx, r14
0x180012a1d  lea     rdx, word_1800324A0
0x180012a24  movups  xmmword ptr [rsp+4C0h+var_478.tymed], xmm0
0x180012a29  mov     rax, [rax+18h]
0x180012a2d  test    esi, esi
0x180012a2f  jnz     short loc_180012A38
0x180012a31  lea     rdx, word_1800324C0
0x180012a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a3d  mov     rcx, qword ptr [rsp+4C0h+var_478.8]
0x180012a42  mov     edx, eax
0x180012a44  xor     eax, eax
0x180012a46  test    edx, edx
0x180012a48  cmovs   rcx, rax; hMem
0x180012a4c  mov     qword ptr [rsp+4C0h+var_478.8], rcx
0x180012a51  test    rcx, rcx
0x180012a54  jz      short loc_180012A9F
0x180012a56  call    cs:__imp_GlobalLock
0x180012a5c  mov     rdi, rax
0x180012a5f  test    rax, rax
0x180012a62  jz      short loc_180012A9F
0x180012a64  lea     rcx, [rbx+50h]; ppsz
0x180012a68  mov     rdx, rax; Src
0x180012a6b  test    esi, esi
0x180012a6d  jz      short loc_180012A91
0x180012a6f  call    ?Str_StrAndThunkA@@YAJPEAPEAGPEBDH@Z; Str_StrAndThunkA(ushort * *,char const *,int)
0x180012a74  jmp     short loc_180012A96
0x180012a76  mov     edx, [rax]
0x180012a78  add     rdx, rdi; Src
0x180012a7b  cmp     dword ptr [rax+10h], 0
0x180012a7f  jz      loc_1800129FA
0x180012a85  call    ?Str_StrAndThunkW@@YAJPEAPEAGPEBGH@Z; Str_StrAndThunkW(ushort * *,ushort const *,int)
0x180012a8a  xor     esi, esi
0x180012a8c  jmp     loc_1800129FF
0x180012a91  call    ?Str_StrAndThunkW@@YAJPEAPEAGPEBGH@Z; Str_StrAndThunkW(ushort * *,ushort const *,int)
0x180012a96  mov     rcx, rdi; hMem
0x180012a99  call    cs:__imp_GlobalUnlock
0x180012a9f  lea     rdi, [rbx+50h]
0x180012aa3  cmp     qword ptr [rdi], 0
0x180012aa7  jnz     short loc_180012ABF
0x180012aa9  mov     rdx, [rbx+48h]; Src
0x180012aad  mov     rcx, rdi; ppsz
0x180012ab0  call    ?Str_StrAndThunkW@@YAJPEAPEAGPEBGH@Z; Str_StrAndThunkW(ushort * *,ushort const *,int)
0x180012ab5  cmp     qword ptr [rdi], 0
0x180012ab9  jz      loc_180012B86
0x180012abf  mov     rax, [rbx+38h]
0x180012ac3  mov     dword ptr [rax], 1
0x180012ac9  mov     rax, [rbx+48h]
0x180012acd  mov     [rsp+4C0h+var_460], rax
0x180012ad2  mov     rax, [rbx+50h]
0x180012ad6  mov     [rsp+4C0h+var_480], rax
0x180012adb  mov     dword ptr [rbx+44h], 0
0x180012ae2  lea     rax, [rsp+4C0h+var_450]
0x180012ae7  lea     r8, [rbp+3C0h+var_240]; unsigned __int16 *
0x180012aee  mov     [rsp+4C0h+var_4A0], rax; unsigned __int16 *
0x180012af3  lea     rdx, [rsp+4C0h+var_480]; unsigned __int16 **
0x180012af8  lea     rcx, [rsp+4C0h+var_460]; unsigned __int16 **
0x180012afd  call    ?_EnumOneHdrop@@YAJPEAPEBG0PEAGK1K@Z; _EnumOneHdrop(ushort const * *,ushort const * *,ushort *,ulong,ushort *,ulong)
0x180012b02  mov     ecx, [rbx+44h]
0x180012b05  test    eax, eax
0x180012b07  jnz     short loc_180012B11
0x180012b09  lea     eax, [rcx+1]
0x180012b0c  mov     [rbx+44h], eax
0x180012b0f  jmp     short loc_180012AE2
0x180012b11  mov     eax, [rbx+40h]
0x180012b14  mov     r9, [rbx+50h]
0x180012b18  mov     r8, [rbx+48h]
0x180012b1c  mov     rdx, [rbx+20h]
0x180012b20  mov     [rsp+4C0h+var_488], ecx
0x180012b24  mov     rcx, [rbx+10h]
0x180012b28  mov     [rsp+4C0h+var_490], eax
0x180012b2c  mov     eax, [rbx+30h]
0x180012b2f  mov     [rsp+4C0h+var_498], eax
0x180012b33  lea     rax, [rsp+4C0h+var_480]
0x180012b38  mov     [rsp+4C0h+var_4A0], rax
0x180012b3d  mov     [rsp+4C0h+var_480], 0
0x180012b46  call    ?CDropOperation_Create@@YAJPEAVCFtpFolder@@PEAUHWND__@@PEBG2PEAPEAVCDropOperation@@KW4OPS@@H@Z; CDropOperation_Create(CFtpFolder *,HWND__ *,ushort const *,ushort const *,CDropOperation * *,ulong,OPS,int)
0x180012b4b  mov     edi, eax
0x180012b4d  test    eax, eax
0x180012b4f  js      short loc_180012B8B
0x180012b51  mov     qword ptr [rbx+48h], 0
0x180012b59  mov     edx, 1; int
0x180012b5e  mov     qword ptr [rbx+50h], 0
0x180012b66  mov     rbx, [rsp+4C0h+var_480]
0x180012b6b  mov     rcx, rbx; this
0x180012b6e  call    ?DoOperation@CDropOperation@@QEAAJH@Z; CDropOperation::DoOperation(int)
0x180012b73  mov     edi, eax
0x180012b75  mov     rcx, rbx
0x180012b78  mov     rax, [rbx]
0x180012b7b  mov     rax, [rax+10h]
0x180012b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b84  jmp     short loc_180012B8B
0x180012b86  mov     edi, 80070057h
0x180012b8b  cmp     qword ptr [rsp+4C0h+var_478.8], 0
0x180012b91  jz      short loc_180012BA5
0x180012b93  lea     rcx, [rsp+4C0h+var_478]; LPSTGMEDIUM
0x180012b98  call    cs:__imp_ReleaseStgMedium
0x180012b9e  jmp     short loc_180012BA5
0x180012ba0  mov     edi, 80070057h
0x180012ba5  mov     eax, edi
0x180012ba7  mov     rcx, [rbp+3C0h+var_30]
0x180012bae  xor     rcx, rsp; StackCookie
0x180012bb1  call    __security_check_cookie
0x180012bb6  add     rsp, 4A0h
0x180012bbd  pop     r14
0x180012bbf  pop     rdi
0x180012bc0  pop     rsi
0x180012bc1  pop     rbx
0x180012bc2  pop     rbp
0x180012bc3  retn
```
