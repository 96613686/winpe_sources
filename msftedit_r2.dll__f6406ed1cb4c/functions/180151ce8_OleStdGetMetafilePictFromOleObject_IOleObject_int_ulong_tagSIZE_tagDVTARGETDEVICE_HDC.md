# OleStdGetMetafilePictFromOleObject(IOleObject *,int,ulong,tagSIZE *,tagDVTARGETDEVICE *,HDC__ *)

- ea: `0x180151ce8`
- end: `0x1801520a5`
- name: `?OleStdGetMetafilePictFromOleObject@@YAPEAXPEAUIOleObject@@HKPEAUtagSIZE@@PEAUtagDVTARGETDEVICE@@PEAUHDC__@@@Z`
- size: `957`
- prototype: `void *__fastcall(struct IOleObject *, int, unsigned int, struct tagSIZE *, struct tagDVTARGETDEVICE *, HDC hdcRef)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x18014a574`
- `0x18015a674`
- `0x18015b7ac`

## callees

- `0x18009abd0`
- `0x1800dce08`
- `0x1800dce48`
- `0x18013ce80`
- `0x180149110`
- `0x180150c90`
- `0x180151ce8`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180152012`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180152012`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180152057`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180152057`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180152029`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180152029`
- `ext-ms-win-gdi-draw-l1-1-1!SetWindowOrgEx` at `0x180151f62`
- `ext-ms-win-gdi-draw-l1-1-1!SetWindowOrgEx` at `0x180151f62`
- `ext-ms-win-gdi-draw-l1-1-1!SetWindowExtEx` at `0x180151f7a`
- `ext-ms-win-gdi-draw-l1-1-1!SetWindowExtEx` at `0x180151f7a`
- `ext-ms-win-gdi-metafile-l1-1-1!CloseMetaFile` at `0x180151fd0`
- `ext-ms-win-gdi-metafile-l1-1-1!CloseMetaFile` at `0x180151fd0`
- `ext-ms-win-gdi-metafile-l1-1-1!CreateMetaFileA` at `0x180151f2e`
- `ext-ms-win-gdi-metafile-l1-1-1!CreateMetaFileA` at `0x180151f2e`
- `ext-ms-win-gdi-metafile-l1-1-0!DeleteMetaFile` at `0x180151ff7`
- `ext-ms-win-gdi-metafile-l1-1-0!DeleteMetaFile` at `0x180151ff7`

## pseudocode

```c
void *__fastcall OleStdGetMetafilePictFromOleObject(
        struct IOleObject *a1,
        int a2,
        unsigned int a3,
        struct tagSIZE *a4,
        struct tagDVTARGETDEVICE *a5,
        HDC hdcRef)
{
  unsigned int v7; // ebx
  HMETAFILE v10; // rdi
  HBITMAP hBitmap; // r13
  struct COLE32_PROC *Ole32Procs; // rax
  __int64 v13; // rdx
  struct COLE32_PROC *v14; // rbx
  void *v15; // rbx
  int v17; // ebx
  HDC MetaFileA; // rax
  HDC v19; // r14
  int v20; // edi
  int v21; // ebx
  HGLOBAL v22; // rax
  _QWORD *v23; // rax
  int x[2]; // [rsp+60h] [rbp-79h] BYREF
  __int64 v25; // [rsp+68h] [rbp-71h] BYREF
  __int64 v26; // [rsp+70h] [rbp-69h] BYREF
  unsigned int v27; // [rsp+78h] [rbp-61h]
  unsigned int (__fastcall ***v28)(_QWORD, GUID *, __int64 *); // [rsp+80h] [rbp-59h] BYREF
  __int128 v29; // [rsp+88h] [rbp-51h] BYREF
  unsigned int v30; // [rsp+98h] [rbp-41h]
  int v31; // [rsp+9Ch] [rbp-3Dh]
  __int64 v32; // [rsp+A0h] [rbp-39h]
  struct tagSTGMEDIUM hemf; // [rsp+A8h] [rbp-31h] BYREF
  struct tagPOINT pt; // [rsp+C0h] [rbp-19h] BYREF
  struct tagSIZE sz; // [rsp+C8h] [rbp-11h] BYREF
  __int128 v36; // [rsp+D0h] [rbp-9h] BYREF

  v7 = a3;
  v32 = 0;
  v27 = a3;
  v30 = a3;
  v26 = 0;
  *(_QWORD *)x = 0;
  v28 = 0;
  v10 = 0;
  v25 = 0;
  v31 = -1;
  v29 = 0;
  memset(&hemf, 0, sizeof(hemf));
  if ( a2 )
  {
    LOWORD(v29) = 14;
    LODWORD(v32) = 64;
  }
  else
  {
    LOWORD(v29) = 3;
    LODWORD(v32) = 32;
  }
  if ( ((__int64 (__fastcall *)(struct IOleObject *, GUID *, _QWORD))a1->lpVtbl->QueryInterface)(
         a1,
         &IID_IOleCache,
         &v28)
    || (**v28)(v28, &IID_IDataObject, &v25) )
  {
    goto LABEL_18;
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, __int128 *, struct tagSTGMEDIUM *))(*(_QWORD *)v25 + 24LL))(
          v25,
          &v29,
          &hemf) )
  {
    hBitmap = hemf.hBitmap;
    Ole32Procs = CThreadData::GetOle32Procs();
    v14 = (struct COLE32_PROC *)((char *)Ole32Procs + 24);
    if ( *((_QWORD *)Ole32Procs + 3) || (SetProcAddr((FARPROC *)Ole32Procs + 3, 1, "OleDuplicateData"), *(_QWORD *)v14) )
    {
      LOWORD(v13) = a2 != 0 ? 14 : 3;
      v15 = (void *)(*(__int64 (__fastcall **)(HBITMAP, __int64, _QWORD))v14)(hBitmap, v13, 0);
    }
    else
    {
      v15 = 0;
    }
    goto LABEL_15;
  }
  if ( a2 )
    goto LABEL_34;
  LOWORD(v29) = 14;
  LODWORD(v32) = 64;
  if ( !(*(unsigned int (__fastcall **)(__int64, __int128 *, struct tagSTGMEDIUM *))(*(_QWORD *)v25 + 24LL))(
          v25,
          &v29,
          &hemf)
    && hemf.hBitmap )
  {
    v15 = 0;
    v10 = ConvertEnhancedMetafileToMetafile(hemf.hEnhMetaFile, hdcRef);
LABEL_15:
    CW32System::ReleaseStgMedium(&hemf);
    if ( v15 )
      goto LABEL_16;
    v7 = v27;
LABEL_18:
    if ( a2 )
      goto LABEL_34;
  }
  if ( !((__int64 (__fastcall *)(struct IOleObject *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
          a1,
          &IID_IViewObject2,
          &v26) )
  {
    if ( a4 )
    {
      v17 = 0;
      *(struct tagSIZE *)x = *a4;
    }
    else
    {
      v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int *))(*(_QWORD *)v26 + 72LL))(
              v26,
              v7,
              0xFFFFFFFFLL,
              0,
              x);
      if ( v17 )
        *(_QWORD *)x = 0;
    }
    if ( !v10 )
    {
      sz = 0;
      pt = 0;
      v36 = 0;
      MetaFileA = CreateMetaFileA(0);
      v19 = MetaFileA;
      if ( !MetaFileA )
        goto LABEL_28;
      v20 = x[0];
      v21 = x[1];
      *((_QWORD *)&v36 + 1) = *(_QWORD *)x;
      *(_QWORD *)&v36 = 0;
      SetWindowOrgEx(MetaFileA, 0, 0, &pt);
      SetWindowExtEx(v19, v20, v21, &sz);
      v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _QWORD, _QWORD, HDC, __int128 *, __int128 *, _QWORD, _QWORD))(*(_QWORD *)v26 + 24LL))(
              v26,
              v27,
              0xFFFFFFFFLL,
              0,
              0,
              0,
              v19,
              &v36,
              &v36,
              0,
              0);
      v10 = CloseMetaFile(v19);
      if ( !v10 )
        goto LABEL_28;
    }
    if ( !v17 )
    {
      v22 = GlobalAlloc(0x2042u, 0x18u);
      v15 = v22;
      if ( v22 )
      {
        v23 = GlobalLock(v22);
        if ( v23 )
        {
          v23[2] = v10;
          *((_DWORD *)v23 + 1) = x[0];
          *((_DWORD *)v23 + 2) = x[1];
          *(_DWORD *)v23 = 8;
          GlobalUnlock(v15);
        }
        goto LABEL_16;
      }
    }
    else
    {
LABEL_28:
      v15 = 0;
    }
    if ( v10 )
      DeleteMetaFile(v10);
LABEL_16:
    Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v25);
    Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v28);
    Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v26);
    return v15;
  }
LABEL_34:
  Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v25);
  Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v28);
  Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v26);
  return 0;
}

```

## disassembly

```asm
0x180151ce8  push    rbp
0x180151cea  push    rbx
0x180151ceb  push    rdi
0x180151cec  push    r12
0x180151cee  push    r13
0x180151cf0  push    r14
0x180151cf2  push    r15
0x180151cf4  lea     rbp, [rsp-17h]
0x180151cf9  sub     rsp, 0F0h
0x180151d00  mov     rax, cs:__security_cookie
0x180151d07  xor     rax, rsp
0x180151d0a  mov     [rbp+47h+var_40], rax
0x180151d0e  mov     r13, [rbp+47h+hdcRef]
0x180151d12  xor     eax, eax
0x180151d14  mov     r14d, edx
0x180151d17  mov     [rbp+47h+var_68], rax
0x180151d1b  xorps   xmm0, xmm0
0x180151d1e  mov     ebx, r8d
0x180151d21  movups  [rbp+47h+var_88], xmm0
0x180151d25  mov     r15, rcx
0x180151d28  mov     [rbp+47h+var_A8], ebx
0x180151d2b  xor     ecx, ecx
0x180151d2d  mov     dword ptr [rbp+47h+var_88], ebx
0x180151d30  mov     [rbp+47h+var_B0], rcx
0x180151d34  xorps   xmm1, xmm1
0x180151d37  mov     qword ptr [rbp+47h+x], rcx
0x180151d3b  mov     r12, r9
0x180151d3e  mov     [rbp+47h+var_A0], rcx
0x180151d42  mov     edi, ecx
0x180151d44  mov     [rbp+47h+var_B8], rcx
0x180151d48  lea     edx, [rcx+3]
0x180151d4b  mov     dword ptr [rbp+47h+var_88+4], 0FFFFFFFFh
0x180151d52  lea     eax, [rcx+0Eh]
0x180151d55  movups  [rbp+47h+var_98], xmm0
0x180151d59  movups  xmmword ptr [rbp+47h+hemf], xmm1
0x180151d5d  test    r14d, r14d
0x180151d60  jz      short loc_180151D6F
0x180151d62  mov     word ptr [rbp+47h+var_98], ax
0x180151d66  mov     dword ptr [rbp+47h+var_88+8], 40h ; '@'
0x180151d6d  jmp     short loc_180151D7A
0x180151d6f  mov     word ptr [rbp+47h+var_98], dx
0x180151d73  mov     dword ptr [rbp+47h+var_88+8], 20h ; ' '
0x180151d7a  mov     rax, [r15]
0x180151d7d  lea     r8, [rbp+47h+var_A0]
0x180151d81  lea     rdx, IID_IOleCache
0x180151d88  mov     rcx, r15
0x180151d8b  mov     rax, [rax]
0x180151d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151d93  test    eax, eax
0x180151d95  jnz     loc_180151EA9
0x180151d9b  mov     rcx, [rbp+47h+var_A0]
0x180151d9f  lea     r8, [rbp+47h+var_B8]
0x180151da3  lea     rdx, IID_IDataObject
0x180151daa  mov     rax, [rcx]
0x180151dad  mov     rax, [rax]
0x180151db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151db5  test    eax, eax
0x180151db7  jnz     loc_180151EA9
0x180151dbd  mov     rcx, [rbp+47h+var_B8]
0x180151dc1  lea     r8, [rbp+47h+hemf]
0x180151dc5  lea     rdx, [rbp+47h+var_98]
0x180151dc9  mov     rax, [rcx]
0x180151dcc  mov     rax, [rax+18h]
0x180151dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151dd5  test    eax, eax
0x180151dd7  jnz     short loc_180151E2B
0x180151dd9  mov     r13, [rbp+47h+hemf+8]
0x180151ddd  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x180151de2  lea     rbx, [rax+18h]
0x180151de6  cmp     [rbx], rdi
0x180151de9  jnz     short loc_180151E04
0x180151deb  lea     r8, aOleduplicateda; "OleDuplicateData"
0x180151df2  mov     edx, 1
0x180151df7  mov     rcx, rbx
0x180151dfa  call    ?SetProcAddr@@YAXAEAPEAXW4DLL_ENUM@@PEBD@Z; SetProcAddr(void * &,DLL_ENUM,char const *)
0x180151dff  cmp     [rbx], rdi
0x180151e02  jz      short loc_180151E27
0x180151e04  mov     eax, r14d
0x180151e07  mov     rcx, r13
0x180151e0a  neg     eax
0x180151e0c  mov     rax, [rbx]
0x180151e0f  sbb     dx, dx
0x180151e12  xor     r8d, r8d
0x180151e15  and     dx, 0Bh
0x180151e19  add     dx, 3
0x180151e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151e22  mov     rbx, rax
0x180151e25  jmp     short loc_180151E75
0x180151e27  xor     ebx, ebx
0x180151e29  jmp     short loc_180151E75
0x180151e2b  test    r14d, r14d
0x180151e2e  jnz     loc_180152068
0x180151e34  mov     rcx, [rbp+47h+var_B8]
0x180151e38  lea     eax, [r14+0Eh]
0x180151e3c  mov     word ptr [rbp+47h+var_98], ax
0x180151e40  lea     r8, [rbp+47h+hemf]
0x180151e44  mov     dword ptr [rbp+47h+var_88+8], 40h ; '@'
0x180151e4b  lea     rdx, [rbp+47h+var_98]
0x180151e4f  mov     rax, [rcx]
0x180151e52  mov     rax, [rax+18h]
0x180151e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151e5b  test    eax, eax
0x180151e5d  jnz     short loc_180151EB2
0x180151e5f  mov     rcx, [rbp+47h+hemf+8]; hemf
0x180151e63  test    rcx, rcx
0x180151e66  jz      short loc_180151EB2
0x180151e68  xor     ebx, ebx
0x180151e6a  mov     rdx, r13; hdcRef
0x180151e6d  call    ConvertEnhancedMetafileToMetafile
0x180151e72  mov     rdi, rax
0x180151e75  lea     rcx, [rbp+47h+hemf]; struct tagSTGMEDIUM *
0x180151e79  call    ?ReleaseStgMedium@CW32System@@SAXPEAUtagSTGMEDIUM@@@Z; CW32System::ReleaseStgMedium(tagSTGMEDIUM *)
0x180151e7e  test    rbx, rbx
0x180151e81  jz      short loc_180151EA6
0x180151e83  lea     rcx, [rbp+47h+var_B8]; void *
0x180151e87  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x180151e8c  lea     rcx, [rbp+47h+var_A0]; void *
0x180151e90  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x180151e95  lea     rcx, [rbp+47h+var_B0]; void *
0x180151e99  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x180151e9e  mov     rax, rbx
0x180151ea1  jmp     loc_180152085
0x180151ea6  mov     ebx, [rbp+47h+var_A8]
0x180151ea9  test    r14d, r14d
0x180151eac  jnz     loc_180152068
0x180151eb2  mov     rax, [r15]
0x180151eb5  lea     r8, [rbp+47h+var_B0]
0x180151eb9  lea     rdx, IID_IViewObject2
0x180151ec0  mov     rcx, r15
0x180151ec3  mov     rax, [rax]
0x180151ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151ecb  xor     r15d, r15d
0x180151ece  test    eax, eax
0x180151ed0  jnz     loc_180152068
0x180151ed6  test    r12, r12
0x180151ed9  jz      short loc_180151EE8
0x180151edb  mov     rax, [r12]
0x180151edf  mov     ebx, r15d
0x180151ee2  mov     qword ptr [rbp+47h+x], rax
0x180151ee6  jmp     short loc_180151F14
0x180151ee8  mov     rcx, [rbp+47h+var_B0]
0x180151eec  lea     rdx, [rbp+47h+x]
0x180151ef0  mov     [rsp+120h+var_100], rdx
0x180151ef5  xor     r9d, r9d
0x180151ef8  or      r8d, 0FFFFFFFFh
0x180151efc  mov     edx, ebx
0x180151efe  mov     rax, [rcx]
0x180151f01  mov     rax, [rax+48h]
0x180151f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151f0a  mov     ebx, eax
0x180151f0c  test    eax, eax
0x180151f0e  jz      short loc_180151F14
0x180151f10  mov     qword ptr [rbp+47h+x], r15
0x180151f14  test    rdi, rdi
0x180151f17  jnz     loc_180151FE4
0x180151f1d  xorps   xmm0, xmm0
0x180151f20  mov     qword ptr [rbp+47h+sz.cx], r15
0x180151f24  xor     ecx, ecx; pszFile
0x180151f26  mov     qword ptr [rbp+47h+pt.x], r15
0x180151f2a  movups  [rbp+47h+var_50], xmm0
0x180151f2e  call    cs:__imp_CreateMetaFileA
0x180151f35  nop     dword ptr [rax+rax+00h]
0x180151f3a  mov     r14, rax
0x180151f3d  test    rax, rax
0x180151f40  jz      loc_180151FE8
0x180151f46  mov     edi, [rbp+47h+x]
0x180151f49  lea     r9, [rbp+47h+pt]; lppt
0x180151f4d  mov     ebx, [rbp+47h+x+4]
0x180151f50  xor     r8d, r8d; y
0x180151f53  xor     edx, edx; x
0x180151f55  mov     dword ptr [rbp+47h+var_50+8], edi
0x180151f58  mov     rcx, rax; hdc
0x180151f5b  mov     dword ptr [rbp+47h+var_50+0Ch], ebx
0x180151f5e  mov     qword ptr [rbp+47h+var_50], r15
0x180151f62  call    cs:__imp_SetWindowOrgEx
0x180151f69  nop     dword ptr [rax+rax+00h]
0x180151f6e  lea     r9, [rbp+47h+sz]; lpsz
0x180151f72  mov     r8d, ebx; y
0x180151f75  mov     edx, edi; x
0x180151f77  mov     rcx, r14; hdc
0x180151f7a  call    cs:__imp_SetWindowExtEx
0x180151f81  nop     dword ptr [rax+rax+00h]
0x180151f86  mov     rcx, [rbp+47h+var_B0]
0x180151f8a  lea     rdx, [rbp+47h+var_50]
0x180151f8e  mov     [rsp+120h+var_D0], r15
0x180151f93  xor     r9d, r9d
0x180151f96  mov     [rsp+120h+var_D8], r15
0x180151f9b  or      r8d, 0FFFFFFFFh
0x180151f9f  mov     [rsp+120h+var_E0], rdx
0x180151fa4  lea     rdx, [rbp+47h+var_50]
0x180151fa8  mov     rax, [rcx]
0x180151fab  mov     [rsp+120h+var_E8], rdx
0x180151fb0  mov     edx, [rbp+47h+var_A8]
0x180151fb3  mov     [rsp+120h+var_F0], r14
0x180151fb8  mov     rax, [rax+18h]
0x180151fbc  mov     [rsp+120h+var_F8], r15
0x180151fc1  mov     [rsp+120h+var_100], r15
0x180151fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151fcb  mov     rcx, r14; hdc
0x180151fce  mov     ebx, eax
0x180151fd0  call    cs:__imp_CloseMetaFile
0x180151fd7  nop     dword ptr [rax+rax+00h]
0x180151fdc  mov     rdi, rax
0x180151fdf  test    rax, rax
0x180151fe2  jz      short loc_180151FE8
0x180151fe4  test    ebx, ebx
0x180151fe6  jz      short loc_180152008
0x180151fe8  mov     rbx, r15
0x180151feb  test    rdi, rdi
0x180151fee  jz      loc_180151E83
0x180151ff4  mov     rcx, rdi; hmf
0x180151ff7  call    cs:__imp_DeleteMetaFile
0x180151ffe  nop     dword ptr [rax+rax+00h]
0x180152003  jmp     loc_180151E83
0x180152008  mov     edx, 18h; dwBytes
0x18015200d  mov     ecx, 2042h; uFlags
0x180152012  call    cs:__imp_GlobalAlloc
0x180152019  nop     dword ptr [rax+rax+00h]
0x18015201e  mov     rbx, rax
0x180152021  test    rax, rax
0x180152024  jz      short loc_180151FEB
0x180152026  mov     rcx, rax; hMem
0x180152029  call    cs:__imp_GlobalLock
0x180152030  nop     dword ptr [rax+rax+00h]
0x180152035  test    rax, rax
0x180152038  jz      loc_180151E83
0x18015203e  mov     [rax+10h], rdi
0x180152042  mov     ecx, [rbp+47h+x]
0x180152045  mov     [rax+4], ecx
0x180152048  mov     ecx, [rbp+47h+x+4]
0x18015204b  mov     [rax+8], ecx
0x18015204e  mov     rcx, rbx; hMem
0x180152051  mov     dword ptr [rax], 8
0x180152057  call    cs:__imp_GlobalUnlock
0x18015205e  nop     dword ptr [rax+rax+00h]
0x180152063  jmp     loc_180151E83
0x180152068  lea     rcx, [rbp+47h+var_B8]; void *
0x18015206c  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x180152071  lea     rcx, [rbp+47h+var_A0]; void *
0x180152075  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x18015207a  lea     rcx, [rbp+47h+var_B0]; void *
0x18015207e  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x180152083  xor     eax, eax
0x180152085  mov     rcx, [rbp+47h+var_40]
0x180152089  xor     rcx, rsp; StackCookie
0x18015208c  call    __security_check_cookie
0x180152091  add     rsp, 0F0h
0x180152098  pop     r15
0x18015209a  pop     r14
0x18015209c  pop     r13
0x18015209e  pop     r12
0x1801520a0  pop     rdi
0x1801520a1  pop     rbx
0x1801520a2  pop     rbp
0x1801520a3  retn
```
