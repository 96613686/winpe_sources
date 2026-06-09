# GetInstallation(int,HINSTANCE__ * *,int)

- ea: `0x180029b70`
- end: `0x180029ff5`
- name: `?GetInstallation@@YAJHPEAPEAUHINSTANCE__@@H@Z`
- size: `1157`
- prototype: `__int64 __fastcall(int, HINSTANCE *, int)`
- caller_count: `8`
- callee_count: `19`
- tags: `loader_planting, installer_update`

## callers

- `0x18002a230`
- `0x18002c0d0`
- `0x18002c1d0`
- `0x18002ca2c`
- `0x18002d4d0`
- `0x18002dee0`
- `0x18002eef8`
- `0x18002f1dc`

## callees

- `0x180007300`
- `0x180007388`
- `0x180008710`
- `0x180008bcc`
- `0x18000da9c`
- `0x180029b38`
- `0x180029b70`
- `0x18002a3b8`
- `0x18002a570`
- `0x18002a868`
- `0x18002b19c`
- `0x18002b1cc`
- `0x18002ba30`
- `0x18002be40`
- `0x180030528`
- `0x18003e758`
- `0x180041ac0`
- `0x180045020`
- `0x180045030`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180029e49`
- `KERNEL32!GetProcAddress` at `0x180029e49`
- `KERNEL32!SetErrorMode` at `0x180029e85`
- `KERNEL32!SetErrorMode` at `0x180029e8f`
- `KERNEL32!SetErrorMode` at `0x180029e85`
- `KERNEL32!SetErrorMode` at `0x180029e8f`
- `USER32!LoadStringW` at `0x180029f14`
- `USER32!LoadStringW` at `0x180029f31`
- `USER32!LoadStringW` at `0x180029f14`
- `USER32!LoadStringW` at `0x180029f31`

## string_xrefs

- `0x180029ee5`: `A fatal error occurred. However, mscorees.dll could not be loaded to display the appropriate error message.\n\nPlease reinstall the .NET Framework.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetInstallation(CLRFullPath *a1, HINSTANCE *a2, int a3)
{
  int v5; // r14d
  int v7; // edi
  __int64 v8; // rsi
  int v9; // edx
  CLRFullPath *v10; // rcx
  unsigned __int16 **v11; // rdx
  CLRFullPath *v12; // rcx
  const unsigned __int16 *FullPath; // rax
  HMODULE LibraryWrapperForEE; // r8
  void (*ProcAddress)(void); // rax
  UINT v16; // eax
  char v17; // bl
  HINSTANCE ResourceInst; // rax
  HINSTANCE v19; // rax
  __int64 v20; // rcx
  unsigned __int16 *v21; // rax
  __int64 v22; // rcx
  size_t v23; // rsi
  CLRFullPath *v24; // rcx
  wchar_t *v25; // rbx
  unsigned __int16 *v26; // rax
  unsigned int ShimMBRTLStyle; // eax
  __int64 v28; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v29; // [rsp+38h] [rbp-C8h]
  __int64 v30; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v31; // [rsp+250h] [rbp+150h] BYREF
  _QWORD v32[3]; // [rsp+258h] [rbp+158h] BYREF
  WCHAR v33[8]; // [rsp+270h] [rbp+170h] BYREF
  __int128 v34; // [rsp+280h] [rbp+180h]
  __int128 v35; // [rsp+290h] [rbp+190h]
  __int128 v36; // [rsp+2A0h] [rbp+1A0h]
  __int64 v37; // [rsp+2B0h] [rbp+1B0h]
  int v38; // [rsp+2B8h] [rbp+1B8h]
  __int64 v39; // [rsp+2C0h] [rbp+1C0h]
  int v40; // [rsp+2C8h] [rbp+1C8h]
  __int64 v41; // [rsp+2D0h] [rbp+1D0h]
  __int64 v42; // [rsp+2D8h] [rbp+1D8h]
  __int64 v43; // [rsp+2E0h] [rbp+1E0h]
  int v44; // [rsp+2E8h] [rbp+1E8h]
  __int64 v45; // [rsp+2F0h] [rbp+1F0h]
  WCHAR Buffer[8]; // [rsp+470h] [rbp+370h] BYREF
  __int128 v47; // [rsp+480h] [rbp+380h]
  __int128 v48; // [rsp+490h] [rbp+390h]
  __int128 v49; // [rsp+4A0h] [rbp+3A0h]
  __int64 v50; // [rsp+4B0h] [rbp+3B0h]
  int v51; // [rsp+4B8h] [rbp+3B8h]
  __int64 v52; // [rsp+4C0h] [rbp+3C0h]
  int v53; // [rsp+4C8h] [rbp+3C8h]
  __int64 v54; // [rsp+4D0h] [rbp+3D0h]
  __int64 v55; // [rsp+4D8h] [rbp+3D8h]
  __int64 v56; // [rsp+4E0h] [rbp+3E0h]
  int v57; // [rsp+4E8h] [rbp+3E8h]
  __int64 v58; // [rsp+4F0h] [rbp+3F0h]

  v5 = (int)a1;
  if ( g_hMod )
  {
    *a2 = g_hMod;
    return 0;
  }
  v7 = 0;
  v8 = -1;
  if ( CLRFullPath::GetFullPath(a1) )
    goto LABEL_22;
  *(_OWORD *)v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 1;
  v38 = 0;
  v39 = 0;
  v40 = 1;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = -1;
  if ( a3 || (v9 = 1, !v5) )
    v9 = 0;
  v7 = RuntimeRequest::RequestRuntimeDll((RuntimeRequest *)v33, v9, 0);
  if ( v7 >= 0 )
  {
LABEL_19:
    if ( !CLRFullPath::GetFullPath(v10) )
    {
      v7 = -2147467259;
      goto LABEL_11;
    }
    RuntimeRequest::~RuntimeRequest((RuntimeRequest *)v33);
    if ( g_hMod )
    {
LABEL_29:
      *a2 = g_hMod;
      return (unsigned int)v7;
    }
LABEL_22:
    if ( !GetProcessExecutableHeap() )
      return 2147942414LL;
    FullPath = CLRFullPath::GetFullPath(v12);
    LibraryWrapperForEE = LoadLibraryWrapperForEE(FullPath);
    if ( !LibraryWrapperForEE && (!lpFileName || (LibraryWrapperForEE = LoadLibraryWrapperForEE(lpFileName)) == 0) )
    {
      v7 = -2146232576;
      if ( v5 )
      {
        if ( !(unsigned int)NoGuiFromShim() )
        {
          v16 = SetErrorMode(0);
          v17 = v16;
          SetErrorMode(v16);
          if ( (v17 & 1) == 0 )
          {
            memset_thunk_772440563353939046(Buffer, 0, 0x200u);
            memset_thunk_772440563353939046(v33, 0, 0x200u);
            if ( GetResourceInst() )
            {
              ResourceInst = GetResourceInst();
              LoadStringW(ResourceInst, 3u, Buffer, 256);
              v19 = GetResourceInst();
              LoadStringW(v19, 2u, v33, 256);
              v28 = 0;
              v29 = 0;
              v30 = 512;
              v20 = -1;
              do
                ++v20;
              while ( Buffer[v20] );
              v21 = CLRFullPath::GetFullPath((CLRFullPath *)v20);
              do
                ++v8;
              while ( v21[v8] );
              v23 = v22 + 1 + v8;
              v25 = (wchar_t *)CQuickMemoryBase<512,128>::_Alloc<0,0>(&v28, 2 * v23);
              if ( v25 )
              {
                v26 = CLRFullPath::GetFullPath(v24);
                swprintf_s(v25, v23, Buffer, v26);
                ShimMBRTLStyle = GetShimMBRTLStyle();
                UtilMessageBoxNonLocalized(0, v25, v33, ShimMBRTLStyle | 0x10, 0, 1, v28, v29, v30);
              }
              CQuickArray<unsigned short>::~CQuickArray<unsigned short>(&v28);
            }
            else
            {
              UtilMessageBoxNonLocalized(
                0,
                L"A fatal error occurred. However, mscorees.dll could not be loaded to display the appropriate error messa"
                 "ge.\n"
                 "\n"
                 "Please reinstall the .NET Framework.",
                L"Error",
                0x10u,
                0,
                1);
            }
          }
        }
      }
      return (unsigned int)v7;
    }
    _InterlockedExchange64((volatile __int64 *)&g_hMod, (__int64)LibraryWrapperForEE);
    ProcAddress = (void (*)(void))GetProcAddress(LibraryWrapperForEE, "SetLoadedByMscoree");
    if ( ProcAddress )
      ProcAddress();
    goto LABEL_29;
  }
  if ( !a3 )
  {
LABEL_13:
    if ( v5 && a3 )
    {
      v31 = *(unsigned __int16 **)v33;
      v32[0] = L"v1.0.3705";
      v32[1] = L"v4.0.0";
      v11 = (unsigned __int16 **)v32;
      if ( *(_QWORD *)v33 )
        v11 = &v31;
      v7 = RuntimeRequest::SetSupportedVersions((RuntimeRequest *)v33, v11, (unsigned int)(*(_QWORD *)v33 != 0) + 2, 1);
      if ( v7 >= 0 )
        RuntimeRequest::NoSupportedVersion((RuntimeRequest *)v33, 1);
    }
    goto LABEL_11;
  }
  *(_OWORD *)Buffer = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 1;
  v51 = 0;
  v52 = 0;
  v53 = 1;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = -1;
  v7 = RuntimeRequest::CopyString(v10, (const unsigned __int16 **)&Buffer[4], L"v1.0.3705", 1);
  if ( v7 >= 0 )
  {
    HIDWORD(v50) = 1;
    v7 = RuntimeRequest::RequestRuntimeDll((RuntimeRequest *)Buffer, 0, 0);
    RuntimeRequest::~RuntimeRequest((RuntimeRequest *)Buffer);
    if ( v7 < 0 )
      goto LABEL_13;
    goto LABEL_19;
  }
  RuntimeRequest::~RuntimeRequest((RuntimeRequest *)Buffer);
LABEL_11:
  RuntimeRequest::~RuntimeRequest((RuntimeRequest *)v33);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180029b70  push    rbp
0x180029b72  push    rbx
0x180029b73  push    rsi
0x180029b74  push    rdi
0x180029b75  push    r12
0x180029b77  push    r13
0x180029b79  push    r14
0x180029b7b  push    r15
0x180029b7d  lea     rbp, [rsp-588h]
0x180029b85  sub     rsp, 688h
0x180029b8c  mov     rax, cs:__security_cookie
0x180029b93  xor     rax, rsp
0x180029b96  mov     [rbp+5C0h+var_50], rax
0x180029b9d  mov     ebx, r8d
0x180029ba0  mov     r15, rdx
0x180029ba3  mov     r14d, ecx
0x180029ba6  mov     rax, cs:?g_hMod@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hMod
0x180029bad  xor     r12d, r12d
0x180029bb0  test    rax, rax
0x180029bb3  jz      short loc_180029BBF
0x180029bb5  mov     [rdx], rax
0x180029bb8  xor     eax, eax
0x180029bba  jmp     loc_180029FD2
0x180029bbf  mov     edi, r12d
0x180029bc2  call    ?GetFullPath@CLRFullPath@@QEAAPEAGXZ; CLRFullPath::GetFullPath(void)
0x180029bc7  mov     r13d, 1
0x180029bcd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180029bd1  test    rax, rax
0x180029bd4  jnz     loc_180029DF0
0x180029bda  xorps   xmm0, xmm0
0x180029bdd  movdqa  xmmword ptr [rbp+5C0h+var_450], xmm0
0x180029be5  xorps   xmm1, xmm1
0x180029be8  movdqa  [rbp+5C0h+var_440], xmm1
0x180029bf0  movdqa  [rbp+5C0h+var_430], xmm0
0x180029bf8  movdqa  [rbp+5C0h+var_420], xmm1
0x180029c00  mov     [rbp+5C0h+var_410], r13
0x180029c07  mov     [rbp+5C0h+var_408], r12d
0x180029c0e  mov     [rbp+5C0h+var_400], r12
0x180029c15  mov     [rbp+5C0h+var_3F8], r13d
0x180029c1c  mov     [rbp+5C0h+var_3F0], r12
0x180029c23  mov     [rbp+5C0h+var_3E8], r12
0x180029c2a  mov     [rbp+5C0h+var_3E0], r12
0x180029c31  mov     [rbp+5C0h+var_3D8], r12d
0x180029c38  mov     [rbp+5C0h+var_3D0], rsi
0x180029c3f  test    ebx, ebx
0x180029c41  jnz     short loc_180029C4B
0x180029c43  test    r14d, r14d
0x180029c46  mov     edx, r13d
0x180029c49  jnz     short loc_180029C4E
0x180029c4b  mov     edx, r12d; int
0x180029c4e  xor     r8d, r8d; int *
0x180029c51  lea     rcx, [rbp+5C0h+var_450]; this
0x180029c58  call    ?RequestRuntimeDll@RuntimeRequest@@QEAAJHPEAH@Z; RuntimeRequest::RequestRuntimeDll(int,int *)
0x180029c5d  mov     edi, eax
0x180029c5f  test    eax, eax
0x180029c61  jns     loc_180029DC7
0x180029c67  lea     rax, aV103705; "v1.0.3705"
0x180029c6e  test    ebx, ebx
0x180029c70  jz      loc_180029D49
0x180029c76  xorps   xmm0, xmm0
0x180029c79  movdqa  xmmword ptr [rbp+5C0h+Buffer], xmm0
0x180029c81  xorps   xmm1, xmm1
0x180029c84  movdqa  [rbp+5C0h+var_240], xmm1
0x180029c8c  movdqa  [rbp+5C0h+var_230], xmm0
0x180029c94  movups  [rbp+5C0h+var_220], xmm1
0x180029c9b  mov     [rbp+5C0h+var_210], 1
0x180029ca6  mov     [rbp+5C0h+var_208], r12d
0x180029cad  mov     [rbp+5C0h+var_200], r12
0x180029cb4  mov     [rbp+5C0h+var_1F8], r13d
0x180029cbb  mov     [rbp+5C0h+var_1F0], r12
0x180029cc2  mov     [rbp+5C0h+var_1E8], r12
0x180029cc9  mov     [rbp+5C0h+var_1E0], r12
0x180029cd0  mov     [rbp+5C0h+var_1D8], r12d
0x180029cd7  mov     [rbp+5C0h+var_1D0], rsi
0x180029cde  mov     r9d, r13d; int
0x180029ce1  mov     r8, rax; unsigned __int16 *
0x180029ce4  lea     rdx, [rbp+5C0h+Buffer+8]; unsigned __int16 **
0x180029ceb  call    ?CopyString@RuntimeRequest@@AEAAJPEAPEBGPEBGH@Z; RuntimeRequest::CopyString(ushort const * *,ushort const *,int)
0x180029cf0  mov     edi, eax
0x180029cf2  test    eax, eax
0x180029cf4  jns     short loc_180029D14
0x180029cf6  lea     rcx, [rbp+5C0h+Buffer]; this
0x180029cfd  call    ??1RuntimeRequest@@QEAA@XZ; RuntimeRequest::~RuntimeRequest(void)
0x180029d02  nop
0x180029d03  lea     rcx, [rbp+5C0h+var_450]; this
0x180029d0a  call    ??1RuntimeRequest@@QEAA@XZ; RuntimeRequest::~RuntimeRequest(void)
0x180029d0f  jmp     loc_180029FD0
0x180029d14  mov     dword ptr [rbp+5C0h+var_210+4], r13d
0x180029d1b  xor     r8d, r8d; int *
0x180029d1e  xor     edx, edx; int
0x180029d20  lea     rcx, [rbp+5C0h+Buffer]; this
0x180029d27  call    ?RequestRuntimeDll@RuntimeRequest@@QEAAJHPEAH@Z; RuntimeRequest::RequestRuntimeDll(int,int *)
0x180029d2c  mov     edi, eax
0x180029d2e  lea     rcx, [rbp+5C0h+Buffer]; this
0x180029d35  call    ??1RuntimeRequest@@QEAA@XZ; RuntimeRequest::~RuntimeRequest(void)
0x180029d3a  test    edi, edi
0x180029d3c  jns     loc_180029DC7
0x180029d42  lea     rax, aV103705; "v1.0.3705"
0x180029d49  test    r14d, r14d
0x180029d4c  jz      short loc_180029D03
0x180029d4e  test    ebx, ebx
0x180029d50  jz      short loc_180029D03
0x180029d52  mov     rcx, qword ptr [rbp+5C0h+var_450]
0x180029d59  mov     [rbp+5C0h+var_470], rcx
0x180029d60  mov     [rbp+5C0h+var_468], rax
0x180029d67  lea     rax, aV400; "v4.0.0"
0x180029d6e  mov     [rbp+5C0h+var_460], rax
0x180029d75  mov     rax, rcx
0x180029d78  neg     rax
0x180029d7b  sbb     r8d, r8d
0x180029d7e  neg     r8d
0x180029d81  add     r8d, 2; unsigned int
0x180029d85  lea     rdx, [rbp+5C0h+var_468]
0x180029d8c  lea     rax, [rbp+5C0h+var_470]
0x180029d93  test    rcx, rcx
0x180029d96  cmovnz  rdx, rax; unsigned __int16 **
0x180029d9a  mov     r9d, r13d; int
0x180029d9d  lea     rcx, [rbp+5C0h+var_450]; this
0x180029da4  call    ?SetSupportedVersions@RuntimeRequest@@QEAAJPEAPEAGKH@Z; RuntimeRequest::SetSupportedVersions(ushort * *,ulong,int)
0x180029da9  mov     edi, eax
0x180029dab  test    eax, eax
0x180029dad  js      loc_180029D03
0x180029db3  mov     edx, r13d; int
0x180029db6  lea     rcx, [rbp+5C0h+var_450]; this
0x180029dbd  call    ?NoSupportedVersion@RuntimeRequest@@QEAAJH@Z; RuntimeRequest::NoSupportedVersion(int)
0x180029dc2  jmp     loc_180029D03
0x180029dc7  call    ?GetFullPath@CLRFullPath@@QEAAPEAGXZ; CLRFullPath::GetFullPath(void)
0x180029dcc  test    rax, rax
0x180029dcf  jnz     short loc_180029DDB
0x180029dd1  mov     edi, 80004005h
0x180029dd6  jmp     loc_180029D03
0x180029ddb  lea     rcx, [rbp+5C0h+var_450]; this
0x180029de2  call    ??1RuntimeRequest@@QEAA@XZ; RuntimeRequest::~RuntimeRequest(void)
0x180029de7  cmp     cs:?g_hMod@@3PEAUHINSTANCE__@@EA, r12; HINSTANCE__ * g_hMod
0x180029dee  jnz     short loc_180029E59
0x180029df0  call    ?GetProcessExecutableHeap@@YAPEAXXZ; GetProcessExecutableHeap(void)
0x180029df5  test    rax, rax
0x180029df8  jnz     short loc_180029E04
0x180029dfa  mov     eax, 8007000Eh
0x180029dff  jmp     loc_180029FD2
0x180029e04  call    ?GetFullPath@CLRFullPath@@QEAAPEAGXZ; CLRFullPath::GetFullPath(void)
0x180029e09  mov     rcx, rax; unsigned __int16 *
0x180029e0c  call    ?LoadLibraryWrapperForEE@@YAPEAUHINSTANCE__@@PEBG@Z; LoadLibraryWrapperForEE(ushort const *)
0x180029e11  mov     r8, rax
0x180029e14  test    rax, rax
0x180029e17  jnz     short loc_180029E32
0x180029e19  mov     rcx, cs:lpFileName; unsigned __int16 *
0x180029e20  test    rcx, rcx
0x180029e23  jz      short loc_180029E68
0x180029e25  call    ?LoadLibraryWrapperForEE@@YAPEAUHINSTANCE__@@PEBG@Z; LoadLibraryWrapperForEE(ushort const *)
0x180029e2a  mov     r8, rax
0x180029e2d  test    rax, rax
0x180029e30  jz      short loc_180029E68
0x180029e32  lea     rcx, ?g_hMod@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hMod
0x180029e39  mov     rax, r8
0x180029e3c  xchg    rax, [rcx]
0x180029e3f  lea     rdx, aSetloadedbymsc; "SetLoadedByMscoree"
0x180029e46  mov     rcx, r8; hModule
0x180029e49  call    cs:__imp_GetProcAddress
0x180029e4f  test    rax, rax
0x180029e52  jz      short loc_180029E59
0x180029e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e59  mov     rax, cs:?g_hMod@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hMod
0x180029e60  mov     [r15], rax
0x180029e63  jmp     loc_180029FD0
0x180029e68  mov     edi, 80131700h
0x180029e6d  test    r14d, r14d
0x180029e70  jz      loc_180029FD0
0x180029e76  call    ?NoGuiFromShim@@YAHXZ; NoGuiFromShim(void)
0x180029e7b  test    eax, eax
0x180029e7d  jnz     loc_180029FD0
0x180029e83  xor     ecx, ecx; uMode
0x180029e85  call    cs:__imp_SetErrorMode
0x180029e8b  mov     ebx, eax
0x180029e8d  mov     ecx, eax; uMode
0x180029e8f  call    cs:__imp_SetErrorMode
0x180029e95  test    r13b, bl
0x180029e98  jnz     loc_180029FD0
0x180029e9e  mov     r14d, 200h
0x180029ea4  mov     r8d, r14d; Size
0x180029ea7  xor     edx, edx; Val
0x180029ea9  lea     rcx, [rbp+5C0h+Buffer]; void *
0x180029eb0  call    memset$thunk$772440563353939046
0x180029eb5  mov     r8d, r14d; Size
0x180029eb8  xor     edx, edx; Val
0x180029eba  lea     rcx, [rbp+5C0h+var_450]; void *
0x180029ec1  call    memset$thunk$772440563353939046
0x180029ec6  call    ?GetResourceInst@@YAPEAUHINSTANCE__@@XZ; GetResourceInst(void)
0x180029ecb  test    rax, rax
0x180029ece  jnz     short loc_180029EF8
0x180029ed0  mov     [rsp+6C0h+var_698], r13d; int
0x180029ed5  mov     qword ptr [rsp+6C0h+var_6A0], r12; int
0x180029eda  lea     r9d, [rax+10h]; unsigned int
0x180029ede  lea     r8, aError; "Error"
0x180029ee5  lea     rdx, aAFatalErrorOcc; "A fatal error occurred. However, mscore"...
0x180029eec  xor     ecx, ecx; HWND
0x180029eee  call    ?UtilMessageBoxNonLocalized@@YAHPEAUHWND__@@PEBG1IHHZZ; UtilMessageBoxNonLocalized(HWND__ *,ushort const *,ushort const *,uint,int,int,...)
0x180029ef3  jmp     loc_180029FD0
0x180029ef8  call    ?GetResourceInst@@YAPEAUHINSTANCE__@@XZ; GetResourceInst(void)
0x180029efd  mov     rcx, rax; hInstance
0x180029f00  mov     ebx, 100h
0x180029f05  mov     r9d, ebx; cchBufferMax
0x180029f08  lea     r8, [rbp+5C0h+Buffer]; lpBuffer
0x180029f0f  mov     edx, 3; uID
0x180029f14  call    cs:__imp_LoadStringW
0x180029f1a  call    ?GetResourceInst@@YAPEAUHINSTANCE__@@XZ; GetResourceInst(void)
0x180029f1f  mov     rcx, rax; hInstance
0x180029f22  mov     r9d, ebx; cchBufferMax
0x180029f25  lea     r8, [rbp+5C0h+var_450]; lpBuffer
0x180029f2c  mov     edx, 2; uID
0x180029f31  call    cs:__imp_LoadStringW
0x180029f37  mov     [rsp+6C0h+var_690], r12
0x180029f3c  mov     [rsp+6C0h+var_688], r12
0x180029f41  mov     [rsp+6C0h+var_680], r14
0x180029f46  lea     rax, [rbp+5C0h+Buffer]
0x180029f4d  mov     rcx, rsi
0x180029f50  inc     rcx; this
0x180029f53  cmp     [rax+rcx*2], r12w
0x180029f58  jnz     short loc_180029F50
0x180029f5a  call    ?GetFullPath@CLRFullPath@@QEAAPEAGXZ; CLRFullPath::GetFullPath(void)
0x180029f5f  inc     rsi
0x180029f62  cmp     [rax+rsi*2], r12w
0x180029f67  jnz     short loc_180029F5F
0x180029f69  inc     rcx
0x180029f6c  add     rsi, rcx
0x180029f6f  lea     rdx, [rsi+rsi]
0x180029f73  lea     rcx, [rsp+6C0h+var_690]
0x180029f78  call    ??$_Alloc@$0A@$0A@@?$CQuickMemoryBase@$0CAA@$0IA@@@IEAAPEAX_K@Z; CQuickMemoryBase<512,128>::_Alloc<0,0>(unsigned __int64)
0x180029f7d  mov     rbx, rax
0x180029f80  test    rax, rax
0x180029f83  jz      short loc_180029FC6
0x180029f85  call    ?GetFullPath@CLRFullPath@@QEAAPEAGXZ; CLRFullPath::GetFullPath(void)
0x180029f8a  mov     r9, rax
0x180029f8d  lea     r8, [rbp+5C0h+Buffer]; Format
0x180029f94  mov     rdx, rsi; BufferCount
0x180029f97  mov     rcx, rbx; Buffer
0x180029f9a  call    swprintf_s
0x180029f9f  call    ?GetShimMBRTLStyle@@YAIXZ; GetShimMBRTLStyle(void)
0x180029fa4  or      eax, 10h
0x180029fa7  mov     [rsp+6C0h+var_698], r13d; int
0x180029fac  mov     qword ptr [rsp+6C0h+var_6A0], r12; int
0x180029fb1  mov     r9d, eax; unsigned int
0x180029fb4  lea     r8, [rbp+5C0h+var_450]; unsigned __int16 *
0x180029fbb  mov     rdx, rbx; unsigned __int16 *
0x180029fbe  xor     ecx, ecx; HWND
0x180029fc0  call    ?UtilMessageBoxNonLocalized@@YAHPEAUHWND__@@PEBG1IHHZZ; UtilMessageBoxNonLocalized(HWND__ *,ushort const *,ushort const *,uint,int,int,...)
0x180029fc5  nop
0x180029fc6  lea     rcx, [rsp+6C0h+var_690]
0x180029fcb  call    ??1?$CQuickArray@G@@QEAA@XZ; CQuickArray<ushort>::~CQuickArray<ushort>(void)
0x180029fd0  mov     eax, edi
0x180029fd2  mov     rcx, [rbp+5C0h+var_50]
0x180029fd9  xor     rcx, rsp; StackCookie
0x180029fdc  call    __security_check_cookie
0x180029fe1  add     rsp, 688h
0x180029fe8  pop     r15
0x180029fea  pop     r14
0x180029fec  pop     r13
0x180029fee  pop     r12
0x180029ff0  pop     rdi
0x180029ff1  pop     rsi
0x180029ff2  pop     rbx
0x180029ff3  pop     rbp
0x180029ff4  retn
```
