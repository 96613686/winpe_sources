# CFtpDrop::CopyFGD(IDataObject *,tagSTGMEDIUM *,int)

- ea: `0x18001262c`
- end: `0x180012917`
- name: `?CopyFGD@CFtpDrop@@IEAAJPEAUIDataObject@@PEAUtagSTGMEDIUM@@H@Z`
- size: `747`
- prototype: `__int64 __fastcall(CFtpDrop *__hidden this, struct IDataObject *, struct tagSTGMEDIUM *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014100`

## callees

- `0x180002240`
- `0x180002b60`
- `0x18001237c`
- `0x18001262c`
- `0x180012bcc`
- `0x1800144c4`
- `0x180028010`

## import_xrefs

- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x1800127da`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x1800127da`
- `KERNEL32!GlobalLock` at `0x180012672`
- `KERNEL32!GlobalLock` at `0x180012680`
- `KERNEL32!GlobalLock` at `0x180012672`
- `KERNEL32!GlobalLock` at `0x180012680`
- `KERNEL32!GlobalUnlock` at `0x1800128d7`
- `KERNEL32!GlobalUnlock` at `0x1800128e5`
- `KERNEL32!GlobalUnlock` at `0x1800128d7`
- `KERNEL32!GlobalUnlock` at `0x1800128e5`
- `ole32!ReleaseStgMedium` at `0x1800128b2`
- `ole32!ReleaseStgMedium` at `0x1800128b2`

## pseudocode

```c
__int64 __fastcall CFtpDrop::CopyFGD(CFtpDrop *this, struct IDataObject *a2, struct tagSTGMEDIUM *a3, int a4)
{
  HBITMAP hBitmap; // rcx
  unsigned int *v7; // rsi
  unsigned int *v8; // r14
  int v9; // ebx
  unsigned int v10; // edi
  unsigned int *v11; // rax
  unsigned int v12; // r12d
  _FILEDESCRIPTORW *v13; // rax
  __int64 v14; // rdx
  __int128 *v15; // rcx
  __int128 v16; // xmm0
  __int64 v17; // rax
  int v18; // eax
  CLIPFORMAT cfFormat; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+42h] [rbp-BEh]
  __int16 v22; // [rsp+46h] [rbp-BAh]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  __int64 v25; // [rsp+58h] [rbp-A8h]
  STGMEDIUM v26; // [rsp+60h] [rbp-A0h] BYREF
  struct IDataObject *v27; // [rsp+78h] [rbp-88h]
  _FILEDESCRIPTORW v28; // [rsp+80h] [rbp-80h] BYREF

  v27 = a2;
  hBitmap = a3->hBitmap;
  if ( a4 )
  {
    v7 = 0;
    v8 = (unsigned int *)GlobalLock(hBitmap);
    goto LABEL_4;
  }
  v8 = 0;
  v7 = (unsigned int *)GlobalLock(hBitmap);
  if ( !v7 )
  {
LABEL_4:
    if ( !v8 )
      return (unsigned int)-2147024809;
  }
  v10 = 0;
  cfFormat = g_dropTypes.cfFormat;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v11 = v8;
  if ( !v8 )
    v11 = v7;
  v24 = 1;
  v25 = 13;
  v9 = 0;
  v12 = *v11;
  *((_DWORD *)this + 17) = *v11;
  while ( v10 < v12 )
  {
    memset_0(&v28, 0, sizeof(v28));
    if ( a4 )
    {
      v13 = &v28;
      v14 = 4;
      v15 = (__int128 *)&v8[148 * v10 + 1];
      do
      {
        v16 = *v15;
        v15 += 8;
        *(_OWORD *)&v13->dwFlags = v16;
        v13 = (_FILEDESCRIPTORW *)((char *)v13 + 128);
        *(_OWORD *)&v13[-1].cFileName[204] = *(v15 - 7);
        *(_OWORD *)&v13[-1].cFileName[212] = *(v15 - 6);
        *(_OWORD *)&v13[-1].cFileName[220] = *(v15 - 5);
        *(_OWORD *)&v13[-1].cFileName[228] = *(v15 - 4);
        *(_OWORD *)&v13[-1].cFileName[236] = *(v15 - 3);
        *(_OWORD *)&v13[-1].cFileName[244] = *(v15 - 2);
        *(_OWORD *)&v13[-1].cFileName[252] = *(v15 - 1);
        --v14;
      }
      while ( v14 );
      *(_OWORD *)&v13->dwFlags = *v15;
      *(_OWORD *)&v13->clsid.Data4[4] = v15[1];
      *(_OWORD *)&v13->pointl.y = v15[2];
      *(_OWORD *)&v13->ftLastAccessTime.dwLowDateTime = v15[3];
      *(_OWORD *)&v13->nFileSizeHigh = v15[4];
    }
    else
    {
      v17 = 83LL * (int)v10;
      *(_OWORD *)&v28.dwFlags = *(_OWORD *)&v7[v17 + 1];
      *(_OWORD *)&v28.clsid.Data4[4] = *(_OWORD *)&v7[v17 + 5];
      *(_OWORD *)&v28.pointl.y = *(_OWORD *)&v7[v17 + 9];
      *(_OWORD *)&v28.ftLastAccessTime.dwLowDateTime = *(_OWORD *)&v7[v17 + 13];
      *(_QWORD *)&v28.nFileSizeHigh = *(_QWORD *)&v7[v17 + 17];
      SHAnsiToUnicode((PCSTR)&v7[v17 + 19], v28.cFileName, 260);
    }
    if ( (v28.dwFlags & 4) != 0 && (v28.dwFileAttributes & 0x10) != 0 )
    {
      v9 = CFtpDrop::_CreateFGDDirectory(this, &v28);
      goto LABEL_27;
    }
    memset(&v26, 0, sizeof(v26));
    v9 = ((__int64 (__fastcall *)(struct IDataObject *, CLIPFORMAT *, STGMEDIUM *))v27->lpVtbl->GetData)(
           v27,
           &cfFormat,
           &v26);
    if ( v9 < 0 )
      break;
    switch ( v26.tymed )
    {
      case 1u:
        v18 = CFtpDrop::CopyAsStream(
                this,
                v28.cFileName,
                v28.dwFileAttributes,
                v28.dwFlags,
                v28.nFileSizeHigh,
                v28.nFileSizeLow,
                (int (*)(struct IStream *, unsigned int, unsigned int, unsigned int, void *, union _ULARGE_INTEGER *))CFtpDrop::_CopyHglobal,
                v26.hBitmap);
        break;
      case 4u:
        v18 = CFtpDrop::CopyAsStream(
                this,
                v28.cFileName,
                v28.dwFileAttributes,
                v28.dwFlags,
                v28.nFileSizeHigh,
                v28.nFileSizeLow,
                (int (*)(struct IStream *, unsigned int, unsigned int, unsigned int, void *, union _ULARGE_INTEGER *))CFtpDrop::CopyStream,
                v26.hBitmap);
        break;
      case 8u:
        v18 = CFtpDrop::CopyStorage((HWND *)this, v28.cFileName, v26.pstg);
        break;
      default:
        v9 = -2147024809;
        goto LABEL_26;
    }
    v9 = v18;
LABEL_26:
    ReleaseStgMedium(&v26);
    if ( v9 < 0 )
      break;
LABEL_27:
    v10 = ++HIDWORD(v24);
  }
  if ( v8 )
    GlobalUnlock(v8);
  if ( v7 )
    GlobalUnlock(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001262c  mov     [rsp-8+arg_18], rbx
0x180012631  push    rbp
0x180012632  push    rsi
0x180012633  push    rdi
0x180012634  push    r12
0x180012636  push    r13
0x180012638  push    r14
0x18001263a  push    r15
0x18001263c  lea     rbp, [rsp-1E0h]
0x180012644  sub     rsp, 2E0h
0x18001264b  mov     rax, cs:__security_cookie
0x180012652  xor     rax, rsp
0x180012655  mov     [rbp+210h+var_40], rax
0x18001265c  mov     [rsp+310h+var_298], rdx
0x180012661  mov     r15, rcx
0x180012664  mov     rcx, [r8+8]; hMem
0x180012668  mov     r13d, r9d
0x18001266b  test    r9d, r9d
0x18001266e  jz      short loc_18001267D
0x180012670  xor     esi, esi
0x180012672  call    cs:__imp_GlobalLock
0x180012678  mov     r14, rax
0x18001267b  jmp     short loc_18001268E
0x18001267d  xor     r14d, r14d
0x180012680  call    cs:__imp_GlobalLock
0x180012686  mov     rsi, rax
0x180012689  test    rax, rax
0x18001268c  jnz     short loc_18001269D
0x18001268e  test    r14, r14
0x180012691  jnz     short loc_18001269D
0x180012693  mov     ebx, 80070057h
0x180012698  jmp     loc_1800128EB
0x18001269d  movzx   eax, cs:?g_dropTypes@@3PAUtagFORMATETC@@A.cfFormat; tagFORMATETC near * g_dropTypes ...
0x1800126a4  xor     edi, edi
0x1800126a6  mov     [rsp+310h+var_2D0], ax
0x1800126ab  xor     eax, eax
0x1800126ad  mov     [rsp+310h+var_2CE], eax
0x1800126b1  test    r14, r14
0x1800126b4  mov     [rsp+310h+var_2CA], ax
0x1800126b9  mov     [rsp+310h+var_2C8], rax
0x1800126be  mov     rax, r14
0x1800126c1  cmovz   rax, rsi
0x1800126c5  mov     [rsp+310h+var_2C0], 1
0x1800126ce  mov     [rsp+310h+var_2B8], 0Dh
0x1800126d7  xor     ebx, ebx
0x1800126d9  mov     r12d, [rax]
0x1800126dc  mov     [r15+44h], r12d
0x1800126e0  jmp     loc_1800128C6
0x1800126e5  xor     edx, edx; Val
0x1800126e7  lea     rcx, [rbp+210h+var_290]; void *
0x1800126eb  mov     r8d, 250h; Size
0x1800126f1  call    memset_0
0x1800126f6  movsxd  rax, edi
0x1800126f9  test    r13d, r13d
0x1800126fc  jz      loc_180012793
0x180012702  imul    rcx, rax, 250h
0x180012709  lea     rax, [rbp+210h+var_290]
0x18001270d  mov     edx, 4
0x180012712  add     rcx, 4
0x180012716  add     rcx, r14
0x180012719  movups  xmm0, xmmword ptr [rcx]
0x18001271c  lea     rcx, [rcx+80h]
0x180012723  movups  xmmword ptr [rax], xmm0
0x180012726  lea     rax, [rax+80h]
0x18001272d  movups  xmm1, xmmword ptr [rcx-70h]
0x180012731  movups  xmmword ptr [rax-70h], xmm1
0x180012735  movups  xmm0, xmmword ptr [rcx-60h]
0x180012739  movups  xmmword ptr [rax-60h], xmm0
0x18001273d  movups  xmm1, xmmword ptr [rcx-50h]
0x180012741  movups  xmmword ptr [rax-50h], xmm1
0x180012745  movups  xmm0, xmmword ptr [rcx-40h]
0x180012749  movups  xmmword ptr [rax-40h], xmm0
0x18001274d  movups  xmm1, xmmword ptr [rcx-30h]
0x180012751  movups  xmmword ptr [rax-30h], xmm1
0x180012755  movups  xmm0, xmmword ptr [rcx-20h]
0x180012759  movups  xmmword ptr [rax-20h], xmm0
0x18001275d  movups  xmm1, xmmword ptr [rcx-10h]
0x180012761  movups  xmmword ptr [rax-10h], xmm1
0x180012765  sub     rdx, 1
0x180012769  jnz     short loc_180012719
0x18001276b  movups  xmm0, xmmword ptr [rcx]
0x18001276e  movups  xmmword ptr [rax], xmm0
0x180012771  movups  xmm1, xmmword ptr [rcx+10h]
0x180012775  movups  xmmword ptr [rax+10h], xmm1
0x180012779  movups  xmm0, xmmword ptr [rcx+20h]
0x18001277d  movups  xmmword ptr [rax+20h], xmm0
0x180012781  movups  xmm1, xmmword ptr [rcx+30h]
0x180012785  movups  xmmword ptr [rax+30h], xmm1
0x180012789  movups  xmm0, xmmword ptr [rcx+40h]
0x18001278d  movups  xmmword ptr [rax+40h], xmm0
0x180012791  jmp     short loc_1800127E0
0x180012793  imul    rax, 14Ch
0x18001279a  mov     r8d, 104h; cwchBuf
0x1800127a0  lea     rdx, [rbp+210h+var_290.cFileName]; pwszDst
0x1800127a4  movups  xmm0, xmmword ptr [rax+rsi+4]
0x1800127a9  lea     rcx, [rax+4Ch]
0x1800127ad  add     rcx, rsi; pszSrc
0x1800127b0  movaps  xmmword ptr [rbp+210h+var_290.dwFlags], xmm0
0x1800127b4  movups  xmm1, xmmword ptr [rax+rsi+14h]
0x1800127b9  movaps  xmmword ptr [rbp+210h+var_290.clsid.Data4+4], xmm1
0x1800127bd  movups  xmm0, xmmword ptr [rax+rsi+24h]
0x1800127c2  movaps  xmmword ptr [rbp+210h+var_290.pointl.y], xmm0
0x1800127c6  movups  xmm1, xmmword ptr [rax+rsi+34h]
0x1800127cb  movaps  xmmword ptr [rbp+210h+var_290.ftLastAccessTime.dwLowDateTime], xmm1
0x1800127cf  movsd   xmm0, qword ptr [rax+rsi+44h]
0x1800127d5  movsd   qword ptr [rbp+210h+var_290.nFileSizeHigh], xmm0
0x1800127da  call    cs:__imp_SHAnsiToUnicode
0x1800127e0  test    byte ptr [rbp+210h+var_290.dwFlags], 4
0x1800127e4  jz      short loc_1800127FF
0x1800127e6  test    byte ptr [rbp+210h+var_290.dwFileAttributes], 10h
0x1800127ea  jz      short loc_1800127FF
0x1800127ec  lea     rdx, [rbp+210h+var_290]; struct _FILEDESCRIPTORW *
0x1800127f0  mov     rcx, r15; this
0x1800127f3  call    ?_CreateFGDDirectory@CFtpDrop@@AEAAJPEAU_FILEDESCRIPTORW@@@Z; CFtpDrop::_CreateFGDDirectory(_FILEDESCRIPTORW *)
0x1800127f8  mov     ebx, eax
0x1800127fa  jmp     loc_1800128BC
0x1800127ff  mov     rcx, [rsp+310h+var_298]
0x180012804  lea     r8, [rsp+310h+var_2B0]
0x180012809  xor     eax, eax
0x18001280b  lea     rdx, [rsp+310h+var_2D0]
0x180012810  mov     [rsp+310h+var_2B0.pUnkForRelease], rax
0x180012815  xorps   xmm0, xmm0
0x180012818  movups  xmmword ptr [rsp+310h+var_2B0.tymed], xmm0
0x18001281d  mov     rax, [rcx]
0x180012820  mov     rax, [rax+18h]
0x180012824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012829  mov     ebx, eax
0x18001282b  test    eax, eax
0x18001282d  js      loc_1800128CF
0x180012833  mov     eax, [rsp+310h+var_2B0.tymed]
0x180012837  mov     ecx, [rbp+210h+var_290.nFileSizeLow]
0x18001283a  mov     edx, [rbp+210h+var_290.nFileSizeHigh]
0x18001283d  mov     r9d, [rbp+210h+var_290.dwFlags]; unsigned int
0x180012841  mov     r8d, [rbp+210h+var_290.dwFileAttributes]; unsigned int
0x180012845  sub     eax, 1
0x180012848  jz      short loc_180012881
0x18001284a  sub     eax, 3
0x18001284d  jz      short loc_18001286E
0x18001284f  cmp     eax, 4
0x180012852  jz      short loc_18001285B
0x180012854  mov     ebx, 80070057h
0x180012859  jmp     short loc_1800128AD
0x18001285b  mov     r8, qword ptr [rsp+310h+var_2B0.8]; struct IStorage *
0x180012860  lea     rdx, [rbp+210h+var_290.cFileName]; unsigned __int16 *
0x180012864  mov     rcx, r15; this
0x180012867  call    ?CopyStorage@CFtpDrop@@IEAAJPEBGPEAUIStorage@@@Z; CFtpDrop::CopyStorage(ushort const *,IStorage *)
0x18001286c  jmp     short loc_1800128AB
0x18001286e  mov     rax, qword ptr [rsp+310h+var_2B0.8]
0x180012873  mov     [rsp+310h+var_2D8], rax
0x180012878  lea     rax, ?CopyStream@CFtpDrop@@SAJPEAUIStream@@KKKPEAXPEAT_ULARGE_INTEGER@@@Z; CFtpDrop::CopyStream(IStream *,ulong,ulong,ulong,void *,_ULARGE_INTEGER *)
0x18001287f  jmp     short loc_180012892
0x180012881  mov     rax, qword ptr [rsp+310h+var_2B0.8]
0x180012886  mov     [rsp+310h+var_2D8], rax; void *
0x18001288b  lea     rax, ?_CopyHglobal@CFtpDrop@@SAJPEAUIStream@@KKKPEAXPEAT_ULARGE_INTEGER@@@Z; CFtpDrop::_CopyHglobal(IStream *,ulong,ulong,ulong,void *,_ULARGE_INTEGER *)
0x180012892  mov     [rsp+310h+var_2E0], rax; int (*)(struct IStream *, unsigned int, unsigned int, unsigned int, void *, union _ULARGE_INTEGER *)
0x180012897  mov     [rsp+310h+var_2E8], ecx; unsigned int
0x18001289b  mov     rcx, r15; this
0x18001289e  mov     [rsp+310h+var_2F0], edx; unsigned int
0x1800128a2  lea     rdx, [rbp+210h+var_290.cFileName]; lpFileName
0x1800128a6  call    ?CopyAsStream@CFtpDrop@@IEAAJPEBGKKKKP6AJPEAUIStream@@KKKPEAXPEAT_ULARGE_INTEGER@@@Z2@Z; CFtpDrop::CopyAsStream(ushort const *,ulong,ulong,ulong,ulong,long (*)(IStream *,ulong,ulong,ulong,void *,_ULARGE_INTEGER *),void *)
0x1800128ab  mov     ebx, eax
0x1800128ad  lea     rcx, [rsp+310h+var_2B0]; LPSTGMEDIUM
0x1800128b2  call    cs:__imp_ReleaseStgMedium
0x1800128b8  test    ebx, ebx
0x1800128ba  js      short loc_1800128CF
0x1800128bc  mov     edi, dword ptr [rsp+310h+var_2C0+4]
0x1800128c0  inc     edi
0x1800128c2  mov     dword ptr [rsp+310h+var_2C0+4], edi
0x1800128c6  cmp     edi, r12d
0x1800128c9  jb      loc_1800126E5
0x1800128cf  test    r14, r14
0x1800128d2  jz      short loc_1800128DD
0x1800128d4  mov     rcx, r14; hMem
0x1800128d7  call    cs:__imp_GlobalUnlock
0x1800128dd  test    rsi, rsi
0x1800128e0  jz      short loc_1800128EB
0x1800128e2  mov     rcx, rsi; hMem
0x1800128e5  call    cs:__imp_GlobalUnlock
0x1800128eb  mov     eax, ebx
0x1800128ed  mov     rcx, [rbp+210h+var_40]
0x1800128f4  xor     rcx, rsp; StackCookie
0x1800128f7  call    __security_check_cookie
0x1800128fc  mov     rbx, [rsp+310h+arg_18]
0x180012904  add     rsp, 2E0h
0x18001290b  pop     r15
0x18001290d  pop     r14
0x18001290f  pop     r13
0x180012911  pop     r12
0x180012913  pop     rdi
0x180012914  pop     rsi
0x180012915  pop     rbp
0x180012916  retn
```
