# CMFApi::Init(void)

- ea: `0x1805be590`
- end: `0x1805beb28`
- name: `?Init@CMFApi@@QEAAJXZ`
- size: `1432`
- prototype: `__int64 __fastcall(CMFApi *__hidden this)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180090568`
- `0x1800f854c`
- `0x180309b10`
- `0x18030bdb0`

## callees

- `0x18002a374`
- `0x1800829d4`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x1805be590`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1805be61e`
- `KERNEL32!LoadLibraryW` at `0x1805be61e`
- `KERNEL32!GetLastError` at `0x1805be9b2`
- `KERNEL32!GetLastError` at `0x1805beac4`
- `KERNEL32!GetLastError` at `0x1805be9b2`
- `KERNEL32!GetLastError` at `0x1805beac4`
- `KERNEL32!GetProcAddress` at `0x1805be63e`
- `KERNEL32!GetProcAddress` at `0x1805be6b4`
- `KERNEL32!GetProcAddress` at `0x1805be703`
- `KERNEL32!GetProcAddress` at `0x1805be761`
- `KERNEL32!GetProcAddress` at `0x1805be7bf`
- `KERNEL32!GetProcAddress` at `0x1805be81d`
- `KERNEL32!GetProcAddress` at `0x1805be87b`
- `KERNEL32!GetProcAddress` at `0x1805be8d9`
- `KERNEL32!GetProcAddress` at `0x1805be937`
- `KERNEL32!GetProcAddress` at `0x1805be995`
- `KERNEL32!GetProcAddress` at `0x1805bea09`
- `KERNEL32!GetProcAddress` at `0x1805bea6a`
- `KERNEL32!GetProcAddress` at `0x1805be63e`
- `KERNEL32!GetProcAddress` at `0x1805be6b4`
- `KERNEL32!GetProcAddress` at `0x1805be703`
- `KERNEL32!GetProcAddress` at `0x1805be761`
- `KERNEL32!GetProcAddress` at `0x1805be7bf`
- `KERNEL32!GetProcAddress` at `0x1805be81d`
- `KERNEL32!GetProcAddress` at `0x1805be87b`
- `KERNEL32!GetProcAddress` at `0x1805be8d9`
- `KERNEL32!GetProcAddress` at `0x1805be937`
- `KERNEL32!GetProcAddress` at `0x1805be995`
- `KERNEL32!GetProcAddress` at `0x1805bea09`
- `KERNEL32!GetProcAddress` at `0x1805bea6a`

## string_xrefs

- `0x1805be75a`: `MFCreateMemoryBuffer`
- `0x1805be7b8`: `MFCreateMediaType`
- `0x1805be874`: `MFCreateDXGIDeviceManager`
- `0x1805be6fc`: `MFCreateSample`
- `0x1805bea63`: `MFCreateAttributes`
- `0x1805be617`: `mfplat.dll`
- `0x1805be747`: `_pfnMFCreateSample`
- `0x1805be7a5`: `_pfnMFCreateMemoryBuffer`
- `0x1805beab1`: `_pfnMFCreateAttributes`
- `0x1805be803`: `_pfnMFCreateMediaType`
- `0x1805be816`: `MFCreateDXGISurfaceBuffer`
- `0x1805be861`: `_pfnMFCreateDXGISurfaceBuffer`
- `0x1805be8bf`: `_pfnMFCreateDXGIDeviceManager`
- `0x1805be8d2`: `MFCreateVideoSampleAllocatorEx`
- `0x1805be91d`: `_pfnMFCreateVideoSampleAllocatorEx`

## pseudocode

```c
__int64 __fastcall CMFApi::Init(CMFApi *this, __int64 a2, __int64 a3)
{
  unsigned int v4; // ebx
  int ActivityIdPrefix; // eax
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // eax
  int v11; // edx
  const char *v12; // rcx
  FARPROC v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  FARPROC v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  FARPROC v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  FARPROC v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  FARPROC v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  FARPROC v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  FARPROC v31; // rax
  __int64 v32; // rdx
  __int64 v33; // r8
  FARPROC v34; // rax
  __int64 v35; // rdx
  __int64 v36; // r8
  FARPROC v37; // rax
  signed int LastError; // eax
  int v39; // r8d
  int v40; // r9d
  FARPROC v41; // rax
  __int64 v42; // rdx
  __int64 v43; // r8
  FARPROC v44; // rax
  __int64 v45; // rdx
  __int64 v46; // r8
  signed int v47; // eax
  signed int v49; // [rsp+48h] [rbp+10h] BYREF
  const char *v50; // [rsp+50h] [rbp+18h] BYREF

  if ( CMFApi::g_fCMFApi_DisableMFDLL )
  {
    v4 = -2147467259;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, a2, a3);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_db3a594a455a3ed0b19703917d125bc2_Traceguids,
        ActivityIdPrefix,
        (__int64)"MF disabled",
        5);
    }
    goto LABEL_73;
  }
  LibraryW = LoadLibraryW(L"mfplat.dll");
  *((_QWORD *)this + 19) = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "MFStartup");
    *((_QWORD *)this + 7) = ProcAddress;
    if ( !ProcAddress )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_13;
      }
      v10 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v8, v9);
      v11 = 11;
      v12 = "_pfnMFStartup";
LABEL_12:
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        (unsigned int)WPP_db3a594a455a3ed0b19703917d125bc2_Traceguids,
        v10,
        (__int64)v12);
LABEL_13:
      v4 = -2147467261;
LABEL_73:
      *((_QWORD *)this + 7) = 0;
      *((_QWORD *)this + 8) = 0;
      *((_QWORD *)this + 9) = 0;
      *((_QWORD *)this + 10) = 0;
      *((_QWORD *)this + 11) = 0;
      *((_QWORD *)this + 12) = 0;
      *((_QWORD *)this + 13) = 0;
      *((_QWORD *)this + 14) = 0;
      *((_QWORD *)this + 15) = 0;
      *((_QWORD *)this + 16) = 0;
      *((_QWORD *)this + 17) = 0;
      *((_QWORD *)this + 18) = 0;
      return v4;
    }
    v13 = GetProcAddress(*((HMODULE *)this + 19), "MFShutdown");
    *((_QWORD *)this + 8) = v13;
    if ( !v13 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_13;
      }
      v10 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v14, v15);
      v11 = 12;
      v12 = "_pfnMFShutdown";
      goto LABEL_12;
    }
    v16 = GetProcAddress(*((HMODULE *)this + 19), "MFCreateSample");
    *((_QWORD *)this + 9) = v16;
    if ( !v16 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_13;
      }
      v10 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v17, v18);
      v11 = 13;
      v12 = "_pfnMFCreateSample";
      goto LABEL_12;
    }
    v19 = GetProcAddress(*((HMODULE *)this + 19), "MFCreateMemoryBuffer");
    *((_QWORD *)this + 10) = v19;
    if ( !v19 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_13;
      }
      v10 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v20, v21);
      v11 = 14;
      v12 = "_pfnMFCreateMemoryBuffer";
      goto LABEL_12;
    }
    v22 = GetProcAddress(*((HMODULE *)this + 19), "MFCreateMediaType");
    *((_QWORD *)this + 11) = v22;
    if ( !v22 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_13;
      }
      v10 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v23, v24);
      v11 = 15;
      v12 = "_pfnMFCreateMediaType";
      goto LABEL_12;
    }
    v25 = GetProcAddress(*((HMODULE *)this + 19), "MFCreateDXGISurfaceBuffer");
    *((_QWORD *)this + 13) = v25;
    if ( !v25 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_13;
      }
      v10 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v26, v27);
      v11 = 16;
      v12 = "_pfnMFCreateDXGISurfaceBuffer";
      goto LABEL_12;
    }
    v28 = GetProcAddress(*((HMODULE *)this + 19), "MFCreateDXGIDeviceManager");
    *((_QWORD *)this + 12) = v28;
    if ( !v28 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_13;
      }
      v10 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v29, v30);
      v11 = 17;
      v12 = "_pfnMFCreateDXGIDeviceManager";
      goto LABEL_12;
    }
    v31 = GetProcAddress(*((HMODULE *)this + 19), "MFCreateVideoSampleAllocatorEx");
    *((_QWORD *)this + 14) = v31;
    if ( !v31 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_13;
      }
      v10 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v32, v33);
      v11 = 18;
      v12 = "_pfnMFCreateVideoSampleAllocatorEx";
      goto LABEL_12;
    }
    v34 = GetProcAddress(*((HMODULE *)this + 19), "MFTEnumEx");
    *((_QWORD *)this + 15) = v34;
    if ( !v34 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_13;
      }
      v10 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v35, v36);
      v11 = 19;
      v12 = "_pfnMFTEnumEx";
      goto LABEL_12;
    }
    v37 = GetProcAddress(*((HMODULE *)this + 19), "MFTEnum2");
    *((_QWORD *)this + 16) = v37;
    if ( !v37 && (unsigned int)dword_1808B5850 > 4 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v49 = LastError;
      v50 = "MFTEnum2 not supported. Not an error.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1808B5850,
        (unsigned int)word_180886EBA,
        v39,
        v40,
        (__int64)&v50,
        (__int64)&v49);
    }
    v41 = GetProcAddress(*((HMODULE *)this + 19), "MFTGetInfo");
    *((_QWORD *)this + 17) = v41;
    if ( !v41 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_13;
      }
      v10 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v42, v43);
      v11 = 20;
      v12 = "_pfnMFTGetInfo";
      goto LABEL_12;
    }
    v44 = GetProcAddress(*((HMODULE *)this + 19), "MFCreateAttributes");
    *((_QWORD *)this + 18) = v44;
    if ( !v44 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_13;
      }
      v10 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v45, v46);
      v11 = 21;
      v12 = "_pfnMFCreateAttributes";
      goto LABEL_12;
    }
    v4 = 0;
    *((_DWORD *)this + 12) = 0;
  }
  else
  {
    v47 = GetLastError();
    v4 = v47;
    if ( v47 > 0 )
      v4 = (unsigned __int16)v47 | 0x80070000;
    if ( (v4 & 0x80000000) != 0 )
      goto LABEL_73;
  }
  return v4;
}

```

## disassembly

```asm
0x1805be590  mov     [rsp+arg_0], rbx
0x1805be595  mov     [rsp+arg_18], rsi
0x1805be59a  push    rdi
0x1805be59b  sub     rsp, 30h
0x1805be59f  xor     esi, esi
0x1805be5a1  mov     rdi, rcx
0x1805be5a4  cmp     cs:?g_fCMFApi_DisableMFDLL@CMFApi@@0HA, esi; int CMFApi::g_fCMFApi_DisableMFDLL
0x1805be5aa  jz      short loc_1805BE617
0x1805be5ac  mov     ebx, 80004005h
0x1805be5b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1805be5b8  lea     rax, WPP_GLOBAL_Control
0x1805be5bf  cmp     rcx, rax
0x1805be5c2  jz      loc_1805BEADD
0x1805be5c8  test    byte ptr [rcx+1Ch], 8
0x1805be5cc  jz      loc_1805BEADD
0x1805be5d2  cmp     byte ptr [rcx+19h], 2
0x1805be5d6  jb      loc_1805BEADD
0x1805be5dc  call    RdpX_GetActivityIdPrefix
0x1805be5e1  lea     rcx, aMfDisabled; "MF disabled"
0x1805be5e8  mov     dword ptr [rsp+38h+var_10], 80004005h
0x1805be5f0  mov     [rsp+38h+var_18], rcx
0x1805be5f5  lea     edx, [rsi+0Ah]
0x1805be5f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1805be5ff  lea     r8, WPP_db3a594a455a3ed0b19703917d125bc2_Traceguids
0x1805be606  mov     r9d, eax
0x1805be609  mov     rcx, [rcx+10h]
0x1805be60d  call    WPP_SF_DsD
0x1805be612  jmp     loc_1805BEADD
0x1805be617  lea     rcx, aMfplatDll_1; "mfplat.dll"
0x1805be61e  call    cs:__imp_LoadLibraryW
0x1805be624  mov     [rdi+98h], rax
0x1805be62b  test    rax, rax
0x1805be62e  jz      loc_1805BEAC4
0x1805be634  lea     rdx, aMfstartup; "MFStartup"
0x1805be63b  mov     rcx, rax; hModule
0x1805be63e  call    cs:__imp_GetProcAddress
0x1805be644  mov     [rdi+38h], rax
0x1805be648  test    rax, rax
0x1805be64b  jnz     short loc_1805BE6A6
0x1805be64d  mov     rcx, cs:WPP_GLOBAL_Control
0x1805be654  lea     rax, WPP_GLOBAL_Control
0x1805be65b  cmp     rcx, rax
0x1805be65e  jz      short loc_1805BE69C
0x1805be660  test    byte ptr [rcx+1Ch], 8
0x1805be664  jz      short loc_1805BE69C
0x1805be666  cmp     byte ptr [rcx+19h], 2
0x1805be66a  jb      short loc_1805BE69C
0x1805be66c  call    RdpX_GetActivityIdPrefix
0x1805be671  mov     edx, 0Bh
0x1805be676  lea     rcx, aPfnmfstartup; "_pfnMFStartup"
0x1805be67d  mov     [rsp+38h+var_18], rcx
0x1805be682  lea     r8, WPP_db3a594a455a3ed0b19703917d125bc2_Traceguids
0x1805be689  mov     rcx, cs:WPP_GLOBAL_Control
0x1805be690  mov     r9d, eax
0x1805be693  mov     rcx, [rcx+10h]
0x1805be697  call    WPP_SF_Ds
0x1805be69c  mov     ebx, 80004003h
0x1805be6a1  jmp     loc_1805BEADD
0x1805be6a6  mov     rcx, [rdi+98h]; hModule
0x1805be6ad  lea     rdx, aMfshutdown; "MFShutdown"
0x1805be6b4  call    cs:__imp_GetProcAddress
0x1805be6ba  mov     [rdi+40h], rax
0x1805be6be  test    rax, rax
0x1805be6c1  jnz     short loc_1805BE6F5
0x1805be6c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1805be6ca  lea     rax, WPP_GLOBAL_Control
0x1805be6d1  cmp     rcx, rax
0x1805be6d4  jz      short loc_1805BE69C
0x1805be6d6  test    byte ptr [rcx+1Ch], 8
0x1805be6da  jz      short loc_1805BE69C
0x1805be6dc  cmp     byte ptr [rcx+19h], 2
0x1805be6e0  jb      short loc_1805BE69C
0x1805be6e2  call    RdpX_GetActivityIdPrefix
0x1805be6e7  mov     edx, 0Ch
0x1805be6ec  lea     rcx, aPfnmfshutdown; "_pfnMFShutdown"
0x1805be6f3  jmp     short loc_1805BE67D
0x1805be6f5  mov     rcx, [rdi+98h]; hModule
0x1805be6fc  lea     rdx, aMfcreatesample_2; "MFCreateSample"
0x1805be703  call    cs:__imp_GetProcAddress
0x1805be709  mov     [rdi+48h], rax
0x1805be70d  test    rax, rax
0x1805be710  jnz     short loc_1805BE753
0x1805be712  mov     rcx, cs:WPP_GLOBAL_Control
0x1805be719  lea     rax, WPP_GLOBAL_Control
0x1805be720  cmp     rcx, rax
0x1805be723  jz      loc_1805BE69C
0x1805be729  test    byte ptr [rcx+1Ch], 8
0x1805be72d  jz      loc_1805BE69C
0x1805be733  cmp     byte ptr [rcx+19h], 2
0x1805be737  jb      loc_1805BE69C
0x1805be73d  call    RdpX_GetActivityIdPrefix
0x1805be742  mov     edx, 0Dh
0x1805be747  lea     rcx, aPfnmfcreatesam; "_pfnMFCreateSample"
0x1805be74e  jmp     loc_1805BE67D
0x1805be753  mov     rcx, [rdi+98h]; hModule
0x1805be75a  lea     rdx, aMfcreatememory; "MFCreateMemoryBuffer"
0x1805be761  call    cs:__imp_GetProcAddress
0x1805be767  mov     [rdi+50h], rax
0x1805be76b  test    rax, rax
0x1805be76e  jnz     short loc_1805BE7B1
0x1805be770  mov     rcx, cs:WPP_GLOBAL_Control
0x1805be777  lea     rax, WPP_GLOBAL_Control
0x1805be77e  cmp     rcx, rax
0x1805be781  jz      loc_1805BE69C
0x1805be787  test    byte ptr [rcx+1Ch], 8
0x1805be78b  jz      loc_1805BE69C
0x1805be791  cmp     byte ptr [rcx+19h], 2
0x1805be795  jb      loc_1805BE69C
0x1805be79b  call    RdpX_GetActivityIdPrefix
0x1805be7a0  mov     edx, 0Eh
0x1805be7a5  lea     rcx, aPfnmfcreatemem; "_pfnMFCreateMemoryBuffer"
0x1805be7ac  jmp     loc_1805BE67D
0x1805be7b1  mov     rcx, [rdi+98h]; hModule
0x1805be7b8  lea     rdx, aMfcreatemediat; "MFCreateMediaType"
0x1805be7bf  call    cs:__imp_GetProcAddress
0x1805be7c5  mov     [rdi+58h], rax
0x1805be7c9  test    rax, rax
0x1805be7cc  jnz     short loc_1805BE80F
0x1805be7ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1805be7d5  lea     rax, WPP_GLOBAL_Control
0x1805be7dc  cmp     rcx, rax
0x1805be7df  jz      loc_1805BE69C
0x1805be7e5  test    byte ptr [rcx+1Ch], 8
0x1805be7e9  jz      loc_1805BE69C
0x1805be7ef  cmp     byte ptr [rcx+19h], 2
0x1805be7f3  jb      loc_1805BE69C
0x1805be7f9  call    RdpX_GetActivityIdPrefix
0x1805be7fe  mov     edx, 0Fh
0x1805be803  lea     rcx, aPfnmfcreatemed; "_pfnMFCreateMediaType"
0x1805be80a  jmp     loc_1805BE67D
0x1805be80f  mov     rcx, [rdi+98h]; hModule
0x1805be816  lea     rdx, aMfcreatedxgisu; "MFCreateDXGISurfaceBuffer"
0x1805be81d  call    cs:__imp_GetProcAddress
0x1805be823  mov     [rdi+68h], rax
0x1805be827  test    rax, rax
0x1805be82a  jnz     short loc_1805BE86D
0x1805be82c  mov     rcx, cs:WPP_GLOBAL_Control
0x1805be833  lea     rax, WPP_GLOBAL_Control
0x1805be83a  cmp     rcx, rax
0x1805be83d  jz      loc_1805BE69C
0x1805be843  test    byte ptr [rcx+1Ch], 8
0x1805be847  jz      loc_1805BE69C
0x1805be84d  cmp     byte ptr [rcx+19h], 2
0x1805be851  jb      loc_1805BE69C
0x1805be857  call    RdpX_GetActivityIdPrefix
0x1805be85c  mov     edx, 10h
0x1805be861  lea     rcx, aPfnmfcreatedxg; "_pfnMFCreateDXGISurfaceBuffer"
0x1805be868  jmp     loc_1805BE67D
0x1805be86d  mov     rcx, [rdi+98h]; hModule
0x1805be874  lea     rdx, aMfcreatedxgide_0; "MFCreateDXGIDeviceManager"
0x1805be87b  call    cs:__imp_GetProcAddress
0x1805be881  mov     [rdi+60h], rax
0x1805be885  test    rax, rax
0x1805be888  jnz     short loc_1805BE8CB
0x1805be88a  mov     rcx, cs:WPP_GLOBAL_Control
0x1805be891  lea     rax, WPP_GLOBAL_Control
0x1805be898  cmp     rcx, rax
0x1805be89b  jz      loc_1805BE69C
0x1805be8a1  test    byte ptr [rcx+1Ch], 8
0x1805be8a5  jz      loc_1805BE69C
0x1805be8ab  cmp     byte ptr [rcx+19h], 2
0x1805be8af  jb      loc_1805BE69C
0x1805be8b5  call    RdpX_GetActivityIdPrefix
0x1805be8ba  mov     edx, 11h
0x1805be8bf  lea     rcx, aPfnmfcreatedxg_0; "_pfnMFCreateDXGIDeviceManager"
0x1805be8c6  jmp     loc_1805BE67D
0x1805be8cb  mov     rcx, [rdi+98h]; hModule
0x1805be8d2  lea     rdx, aMfcreatevideos; "MFCreateVideoSampleAllocatorEx"
0x1805be8d9  call    cs:__imp_GetProcAddress
0x1805be8df  mov     [rdi+70h], rax
0x1805be8e3  test    rax, rax
0x1805be8e6  jnz     short loc_1805BE929
0x1805be8e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1805be8ef  lea     rax, WPP_GLOBAL_Control
0x1805be8f6  cmp     rcx, rax
0x1805be8f9  jz      loc_1805BE69C
0x1805be8ff  test    byte ptr [rcx+1Ch], 8
0x1805be903  jz      loc_1805BE69C
0x1805be909  cmp     byte ptr [rcx+19h], 2
0x1805be90d  jb      loc_1805BE69C
0x1805be913  call    RdpX_GetActivityIdPrefix
0x1805be918  mov     edx, 12h
0x1805be91d  lea     rcx, aPfnmfcreatevid; "_pfnMFCreateVideoSampleAllocatorEx"
0x1805be924  jmp     loc_1805BE67D
0x1805be929  mov     rcx, [rdi+98h]; hModule
0x1805be930  lea     rdx, aMftenumex; "MFTEnumEx"
0x1805be937  call    cs:__imp_GetProcAddress
0x1805be93d  mov     [rdi+78h], rax
0x1805be941  test    rax, rax
0x1805be944  jnz     short loc_1805BE987
0x1805be946  mov     rcx, cs:WPP_GLOBAL_Control
0x1805be94d  lea     rax, WPP_GLOBAL_Control
0x1805be954  cmp     rcx, rax
0x1805be957  jz      loc_1805BE69C
0x1805be95d  test    byte ptr [rcx+1Ch], 8
0x1805be961  jz      loc_1805BE69C
0x1805be967  cmp     byte ptr [rcx+19h], 2
0x1805be96b  jb      loc_1805BE69C
0x1805be971  call    RdpX_GetActivityIdPrefix
0x1805be976  mov     edx, 13h
0x1805be97b  lea     rcx, aPfnmftenumex; "_pfnMFTEnumEx"
0x1805be982  jmp     loc_1805BE67D
0x1805be987  mov     rcx, [rdi+98h]; hModule
0x1805be98e  lea     rdx, aMftenum2; "MFTEnum2"
0x1805be995  call    cs:__imp_GetProcAddress
0x1805be99b  mov     [rdi+80h], rax
0x1805be9a2  test    rax, rax
0x1805be9a5  jnz     short loc_1805BE9FB
0x1805be9a7  mov     eax, cs:dword_1808B5850
0x1805be9ad  cmp     eax, 4
0x1805be9b0  jbe     short loc_1805BE9FB
0x1805be9b2  call    cs:__imp_GetLastError
0x1805be9b8  test    eax, eax
0x1805be9ba  jle     short loc_1805BE9C4
0x1805be9bc  movzx   eax, ax
0x1805be9bf  or      eax, 80070000h
0x1805be9c4  mov     [rsp+38h+arg_8], eax
0x1805be9c8  lea     rdx, word_180886EBA
0x1805be9cf  lea     rax, aMftenum2NotSup; "MFTEnum2 not supported. Not an error."
0x1805be9d6  mov     [rsp+38h+arg_10], rax
0x1805be9db  lea     rcx, dword_1808B5850
0x1805be9e2  lea     rax, [rsp+38h+arg_8]
0x1805be9e7  mov     [rsp+38h+var_10], rax
0x1805be9ec  lea     rax, [rsp+38h+arg_10]
0x1805be9f1  mov     [rsp+38h+var_18], rax
0x1805be9f6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1805be9fb  mov     rcx, [rdi+98h]; hModule
0x1805bea02  lea     rdx, aMftgetinfo; "MFTGetInfo"
0x1805bea09  call    cs:__imp_GetProcAddress
0x1805bea0f  mov     [rdi+88h], rax
0x1805bea16  test    rax, rax
0x1805bea19  jnz     short loc_1805BEA5C
0x1805bea1b  mov     rcx, cs:WPP_GLOBAL_Control
0x1805bea22  lea     rax, WPP_GLOBAL_Control
0x1805bea29  cmp     rcx, rax
0x1805bea2c  jz      loc_1805BE69C
0x1805bea32  test    byte ptr [rcx+1Ch], 8
0x1805bea36  jz      loc_1805BE69C
0x1805bea3c  cmp     byte ptr [rcx+19h], 2
0x1805bea40  jb      loc_1805BE69C
0x1805bea46  call    RdpX_GetActivityIdPrefix
0x1805bea4b  mov     edx, 14h
0x1805bea50  lea     rcx, aPfnmftgetinfo; "_pfnMFTGetInfo"
0x1805bea57  jmp     loc_1805BE67D
0x1805bea5c  mov     rcx, [rdi+98h]; hModule
0x1805bea63  lea     rdx, aMfcreateattrib; "MFCreateAttributes"
0x1805bea6a  call    cs:__imp_GetProcAddress
0x1805bea70  mov     [rdi+90h], rax
0x1805bea77  test    rax, rax
0x1805bea7a  jnz     short loc_1805BEABD
0x1805bea7c  mov     rcx, cs:WPP_GLOBAL_Control
0x1805bea83  lea     rax, WPP_GLOBAL_Control
0x1805bea8a  cmp     rcx, rax
0x1805bea8d  jz      loc_1805BE69C
0x1805bea93  test    byte ptr [rcx+1Ch], 8
0x1805bea97  jz      loc_1805BE69C
0x1805bea9d  cmp     byte ptr [rcx+19h], 2
0x1805beaa1  jb      loc_1805BE69C
0x1805beaa7  call    RdpX_GetActivityIdPrefix
0x1805beaac  mov     edx, 15h
0x1805beab1  lea     rcx, aPfnmfcreateatt; "_pfnMFCreateAttributes"
0x1805beab8  jmp     loc_1805BE67D
0x1805beabd  mov     ebx, esi
0x1805beabf  mov     [rdi+30h], esi
0x1805beac2  jmp     short loc_1805BEB16
0x1805beac4  call    cs:__imp_GetLastError
0x1805beaca  mov     ebx, eax
0x1805beacc  test    eax, eax
0x1805beace  jle     short loc_1805BEAD9
0x1805bead0  movzx   ebx, ax
0x1805bead3  or      ebx, 80070000h
0x1805bead9  test    ebx, ebx
0x1805beadb  jns     short loc_1805BEB16
0x1805beadd  mov     [rdi+38h], rsi
0x1805beae1  mov     [rdi+40h], rsi
0x1805beae5  mov     [rdi+48h], rsi
0x1805beae9  mov     [rdi+50h], rsi
0x1805beaed  mov     [rdi+58h], rsi
0x1805beaf1  mov     [rdi+60h], rsi
0x1805beaf5  mov     [rdi+68h], rsi
0x1805beaf9  mov     [rdi+70h], rsi
0x1805beafd  mov     [rdi+78h], rsi
0x1805beb01  mov     [rdi+80h], rsi
0x1805beb08  mov     [rdi+88h], rsi
0x1805beb0f  mov     [rdi+90h], rsi
0x1805beb16  mov     rsi, [rsp+38h+arg_18]
0x1805beb1b  mov     eax, ebx
0x1805beb1d  mov     rbx, [rsp+38h+arg_0]
0x1805beb22  add     rsp, 30h
0x1805beb26  pop     rdi
0x1805beb27  retn
```
