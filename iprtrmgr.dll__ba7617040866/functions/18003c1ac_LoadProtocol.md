# LoadProtocol

- ea: `0x18003c1ac`
- end: `0x18003c9e4`
- name: `LoadProtocol`
- size: `2104`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800023f4`
- `0x1800292bc`

## callees

- `0x18000ac60`
- `0x18003c1ac`
- `0x1800583cc`
- `0x18005852a`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18003c2d2`
- `KERNEL32!LoadLibraryExW` at `0x18003c2d2`
- `KERNEL32!GetProcAddress` at `0x18003c347`
- `KERNEL32!GetProcAddress` at `0x18003c347`
- `KERNEL32!FreeLibrary` at `0x18003c360`
- `KERNEL32!FreeLibrary` at `0x18003c418`
- `KERNEL32!FreeLibrary` at `0x18003c556`
- `KERNEL32!FreeLibrary` at `0x18003c900`
- `KERNEL32!FreeLibrary` at `0x18003c9b2`
- `KERNEL32!FreeLibrary` at `0x18003c360`
- `KERNEL32!FreeLibrary` at `0x18003c418`
- `KERNEL32!FreeLibrary` at `0x18003c556`
- `KERNEL32!FreeLibrary` at `0x18003c900`
- `KERNEL32!FreeLibrary` at `0x18003c9b2`
- `KERNEL32!Sleep` at `0x18003c357`
- `KERNEL32!Sleep` at `0x18003c40f`
- `KERNEL32!Sleep` at `0x18003c54d`
- `KERNEL32!Sleep` at `0x18003c8f7`
- `KERNEL32!Sleep` at `0x18003c9a9`
- `KERNEL32!Sleep` at `0x18003c357`
- `KERNEL32!Sleep` at `0x18003c40f`
- `KERNEL32!Sleep` at `0x18003c54d`
- `KERNEL32!Sleep` at `0x18003c8f7`
- `KERNEL32!Sleep` at `0x18003c9a9`
- `KERNEL32!GetLastError` at `0x18003c2e0`
- `KERNEL32!GetLastError` at `0x18003c2e0`

## string_xrefs

- `0x18003c243`: `LoadProtocol`
- `0x18003c295`: `LoadProtocol: Loading %ws`
- `0x18003c2ff`: `LoadProtocol: %ws failed to load: %d\n`
- `0x18003c338`: `RegisterProtocol`
- `0x18003c37a`: `LoadProtocol: Could not find RegisterProtocol for %ws`
- `0x18003c439`: `LoadProtocol: %ws returned error %d while registering`
- `0x18003c493`: `LoadProtocol: %ws registered with version 0x%x. Our version is 0x%x\n`
- `0x18003c4cd`: `LoadProtocol: %ws returned ID of %x when it should be %x`
- `0x18003c4f2`: `LoadProtocol: %ws wanted functionalitf %x when we have %x`
- `0x18003c515`: `LoadProtocol: %ws doesnt support routing`
- `0x18003c965`: `LoadProtocol: %ws failed to provide atleast one entrypoint\n`
- `0x18003c784`: `LoadProtocol: %ws supports DEMAND but has no entry point`
- `0x18003c7bd`: `LoadProtocol: %ws supports MCAST but has an id of %x`
- `0x18003c8bf`: `LoadProtocol: %ws failed to start: %d\n`
- `0x18003c91f`: `LoadProtocol: Loaded %ws successfully`

## pseudocode

```c
__int64 __fastcall LoadProtocol(int *a1, __int64 a2, __int64 a3, unsigned int a4, int a5, int a6, int a7)
{
  __int64 v9; // r14
  HMODULE Library; // rax
  HMODULE v11; // r15
  DWORD LastError; // eax
  DWORD v13; // ebx
  FARPROC ProcAddress; // r12
  int v16; // ecx
  unsigned int v17; // r12d
  const wchar_t *v18; // rdx
  int v19; // r9d
  int v20; // edx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r10
  __int64 v24; // r11
  __int64 v25; // rsi
  __int64 v26; // r12
  __int64 v27; // r13
  __int64 v28; // rax
  const wchar_t *v29; // rdx
  __int64 v30; // rsi
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  _WORD *v35; // rdi
  void *v36; // rcx
  HANDLE v37; // rcx
  DWORD v38; // eax
  unsigned int v41; // [rsp+50h] [rbp-B0h] BYREF
  int v42; // [rsp+54h] [rbp-ACh]
  int v43; // [rsp+58h] [rbp-A8h]
  char v44[4]; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v45; // [rsp+60h] [rbp-A0h]
  __int64 v46; // [rsp+68h] [rbp-98h]
  __int64 v47; // [rsp+70h] [rbp-90h]
  __int64 v48; // [rsp+78h] [rbp-88h]
  __int64 v49; // [rsp+80h] [rbp-80h]
  __int64 v50; // [rsp+88h] [rbp-78h]
  __int64 v51; // [rsp+90h] [rbp-70h]
  __int64 v52; // [rsp+98h] [rbp-68h]
  __int64 v53; // [rsp+A0h] [rbp-60h]
  __int64 v54; // [rsp+A8h] [rbp-58h]
  __int64 v55; // [rsp+B0h] [rbp-50h]
  __int64 v56; // [rsp+B8h] [rbp-48h]
  __int64 v57; // [rsp+C0h] [rbp-40h]
  __int64 v58; // [rsp+C8h] [rbp-38h]
  __int64 v59; // [rsp+D0h] [rbp-30h]
  __int64 v60; // [rsp+D8h] [rbp-28h]
  __int64 v61; // [rsp+E0h] [rbp-20h]
  __int64 v62; // [rsp+E8h] [rbp-18h]
  __int64 v63; // [rsp+F0h] [rbp-10h]
  __int64 v64; // [rsp+F8h] [rbp-8h]
  __int64 v65; // [rsp+100h] [rbp+0h]
  __int64 v66; // [rsp+108h] [rbp+8h]
  __int64 v67; // [rsp+110h] [rbp+10h]
  __int64 v68; // [rsp+118h] [rbp+18h]
  __int64 v69; // [rsp+130h] [rbp+30h]
  __int64 v70; // [rsp+138h] [rbp+38h]
  __int64 v71; // [rsp+140h] [rbp+40h]
  __int64 v72; // [rsp+148h] [rbp+48h]
  __int64 v73; // [rsp+150h] [rbp+50h]
  _DWORD v74[28]; // [rsp+160h] [rbp+60h] BYREF
  int v75; // [rsp+1D0h] [rbp+D0h] BYREF
  char v76[2044]; // [rsp+1D4h] [rbp+D4h] BYREF

  memset_0(&v41, 0, 0x108u);
  memset_0(v74, 0, sizeof(v74));
  v75 = 0;
  memset_0(v76, 0, sizeof(v76));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v75) = 0;
    FormatRRASErrorString(&v75, L"Entered: %ws", L"LoadProtocol");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v75);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v75) = 0;
        FormatRRASErrorString(&v75, L"LoadProtocol: Loading %ws", a1 + 1);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v75);
      }
    }
  }
  v9 = (__int64)a1 + 86;
  Library = LoadLibraryExW((LPCWSTR)a1 + 43, 0, 0x1000u);
  v11 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v75) = 0;
      FormatRRASErrorString(&v75, L"LoadProtocol: %ws failed to load: %d\n", (char *)a1 + 86, LastError);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v75);
    }
    return v13;
  }
  *(_QWORD *)(a2 + 40) = Library;
  *(_DWORD *)(a2 + 60) = *a1;
  ProcAddress = GetProcAddress(Library, "RegisterProtocol");
  if ( !ProcAddress )
  {
    Sleep(0);
    FreeLibrary(v11);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v75) = 0;
      FormatRRASErrorString(&v75, L"LoadProtocol: Could not find RegisterProtocol for %ws", (char *)a1 + 86);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v75);
    }
    return 1;
  }
  memset_0(v44, 0, 0xFCu);
  v16 = *a1;
  v41 = 1536;
  v42 = v16;
  v74[0] = 1536;
  v74[1] = v16;
  v74[2] = 0;
  v43 = a7 != 0 ? 117 : 119;
  v17 = ((__int64 (__fastcall *)(unsigned int *, _DWORD *))ProcAddress)(&v41, v74);
  if ( v17 )
  {
    Sleep(0);
    FreeLibrary(v11);
    *(_QWORD *)(a2 + 40) = 0;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v75) = 0;
      FormatRRASErrorString(&v75, L"LoadProtocol: %ws returned error %d while registering", (char *)a1 + 86, v17);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v75);
    }
    return v17;
  }
  if ( v41 > 0x600 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v18 = L"LoadProtocol: %ws registered with version 0x%x. Our version is 0x%x\n";
LABEL_24:
      LOWORD(v75) = 0;
      FormatRRASErrorString(&v75, v18, a1 + 1);
      goto LABEL_34;
    }
    goto LABEL_36;
  }
  v19 = v42;
  if ( v42 != *a1 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v18 = L"LoadProtocol: %ws returned ID of %x when it should be %x";
      goto LABEL_24;
    }
LABEL_36:
    Sleep(0);
    FreeLibrary(v11);
    return 1003;
  }
  v20 = v43;
  if ( (~(a7 != 0 ? 117 : 119) & v43) != 0 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v18 = L"LoadProtocol: %ws wanted functionalitf %x when we have %x";
      goto LABEL_24;
    }
    goto LABEL_36;
  }
  if ( (v43 & 3) == 0 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v75) = 0;
      FormatRRASErrorString(&v75, L"LoadProtocol: %ws doesnt support routing", a1 + 1);
LABEL_34:
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v75);
      goto LABEL_36;
    }
    goto LABEL_36;
  }
  v21 = v45;
  v22 = v46;
  v23 = v47;
  v24 = v48;
  v25 = v49;
  v26 = v52;
  v27 = v53;
  *(_QWORD *)(a2 + 112) = v50;
  *(_QWORD *)(a2 + 120) = v51;
  *(_QWORD *)(a2 + 144) = v54;
  *(_QWORD *)(a2 + 152) = v55;
  *(_QWORD *)(a2 + 160) = v56;
  *(_QWORD *)(a2 + 168) = v57;
  *(_QWORD *)(a2 + 176) = v58;
  *(_QWORD *)(a2 + 184) = v59;
  *(_QWORD *)(a2 + 192) = v60;
  *(_QWORD *)(a2 + 200) = v61;
  *(_QWORD *)(a2 + 208) = v62;
  *(_QWORD *)(a2 + 216) = v63;
  *(_QWORD *)(a2 + 224) = v64;
  *(_QWORD *)(a2 + 232) = v65;
  *(_QWORD *)(a2 + 240) = v66;
  *(_QWORD *)(a2 + 248) = v67;
  *(_QWORD *)(a2 + 256) = v68;
  *(_QWORD *)(a2 + 280) = v69;
  *(_QWORD *)(a2 + 288) = v70;
  *(_QWORD *)(a2 + 296) = v71;
  *(_QWORD *)(a2 + 304) = v72;
  v28 = v73;
  *(_QWORD *)(a2 + 312) = v73;
  *(_DWORD *)(a2 + 64) = v20;
  *(_QWORD *)(a2 + 72) = v21;
  *(_QWORD *)(a2 + 80) = v22;
  *(_QWORD *)(a2 + 88) = v23;
  *(_QWORD *)(a2 + 96) = v24;
  *(_QWORD *)(a2 + 104) = v25;
  *(_QWORD *)(a2 + 128) = v26;
  *(_QWORD *)(a2 + 136) = v27;
  if ( !v21
    || !v22
    || !v23
    || !v24
    || !v25
    || !v26
    || !v27
    || !v54
    || !v55
    || !v56
    || !v57
    || !v63
    || !v64
    || !v65
    || !v66
    || !v67
    || !v68 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v29 = L"LoadProtocol: %ws failed to provide atleast one entrypoint\n";
      goto LABEL_88;
    }
LABEL_91:
    Sleep(0);
    FreeLibrary(v11);
    *(_QWORD *)(a2 + 40) = 0;
    return 1003;
  }
  if ( v70 && !v28 || (*(_QWORD *)(a2 + 296) != 0) != (*(_QWORD *)(a2 + 304) != 0) )
    return 1003;
  if ( (v20 & 4) != 0 && !*(_QWORD *)(a2 + 176) )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v29 = L"LoadProtocol: %ws supports DEMAND but has no entry point";
LABEL_88:
      LOWORD(v75) = 0;
      FormatRRASErrorString(&v75, v29, a1 + 1);
LABEL_89:
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v75);
      goto LABEL_91;
    }
    goto LABEL_91;
  }
  if ( (v20 & 0x20) != 0 && (v19 & 0xC0000000) != 0x40000000 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v75) = 0;
      FormatRRASErrorString(&v75, L"LoadProtocol: %ws supports MCAST but has an id of %x", a1 + 1);
      goto LABEL_89;
    }
    goto LABEL_91;
  }
  v30 = -1;
  *(_QWORD *)(a2 + 24) = a2 + 320;
  v31 = -1;
  do
    ++v31;
  while ( *(_WORD *)(v9 + 2 * v31) );
  memcpy_0((void *)(a2 + 320), (char *)a1 + 86, 2 * v31);
  v32 = -1;
  do
    ++v32;
  while ( *(_WORD *)(v9 + 2 * v32) );
  *(_WORD *)(*(_QWORD *)(a2 + 24) + 2 * v32) = 0;
  v33 = -1;
  do
    ++v33;
  while ( *(_WORD *)(v9 + 2 * v33) );
  v34 = -1;
  v35 = a1 + 1;
  v36 = (void *)(*(_QWORD *)(a2 + 24) + 2LL + 2 * v33);
  *(_QWORD *)(a2 + 32) = v36;
  do
    ++v34;
  while ( v35[v34] );
  memcpy_0(v36, v35, 2 * v34);
  do
    ++v30;
  while ( v35[v30] );
  *(_WORD *)(*(_QWORD *)(a2 + 32) + 2 * v30) = 0;
  v37 = g_hRoutingProtocolEventV6;
  if ( a7 )
    v37 = g_hRoutingProtocolEvent;
  v38 = (*(__int64 (__fastcall **)(HANDLE, char *, __int64, _QWORD, int, int))(a2 + 72))(
          v37,
          g_sfnDimFunctions,
          a3,
          a4,
          a5,
          a6);
  v13 = v38;
  if ( v38 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v75) = 0;
      FormatRRASErrorString(&v75, L"LoadProtocol: %ws failed to start: %d\n", v35, v38);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v75);
    }
    Sleep(0);
    FreeLibrary(v11);
    return v13;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v75) = 0;
    FormatRRASErrorString(&v75, L"LoadProtocol: Loaded %ws successfully", v35);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v75);
  }
  return 0;
}

```

## disassembly

```asm
0x18003c1ac  push    rbp
0x18003c1ae  push    rbx
0x18003c1af  push    rsi
0x18003c1b0  push    rdi
0x18003c1b1  push    r12
0x18003c1b3  push    r13
0x18003c1b5  push    r14
0x18003c1b7  push    r15
0x18003c1b9  lea     rbp, [rsp-8E8h]
0x18003c1c1  sub     rsp, 9E8h
0x18003c1c8  mov     rax, cs:__security_cookie
0x18003c1cf  xor     rax, rsp
0x18003c1d2  mov     [rbp+920h+var_50], rax
0x18003c1d9  mov     [rsp+0A20h+var_9D8], r8
0x18003c1de  mov     rbx, rdx
0x18003c1e1  mov     rdi, rcx
0x18003c1e4  mov     [rsp+0A20h+var_9E0], r9d
0x18003c1e9  xor     edx, edx; Val
0x18003c1eb  lea     rcx, [rsp+0A20h+var_9D0]; void *
0x18003c1f0  mov     r8d, 108h; Size
0x18003c1f6  call    memset_0
0x18003c1fb  xor     edx, edx; Val
0x18003c1fd  lea     rcx, [rbp+920h+var_8C0]; void *
0x18003c201  lea     r8d, [rdx+70h]; Size
0x18003c205  call    memset_0
0x18003c20a  xor     r13d, r13d
0x18003c20d  lea     rcx, [rbp+920h+var_84C]; void *
0x18003c214  xor     edx, edx; Val
0x18003c216  mov     [rbp+920h+var_850], r13d
0x18003c21d  mov     r8d, 7FCh; Size
0x18003c223  call    memset_0
0x18003c228  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x18003c22f  lea     r12, RasRtrmgrTraceInfo
0x18003c236  lea     rsi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003c23d  jge     loc_18003C2C3
0x18003c243  lea     r8, aLoadprotocol; "LoadProtocol"
0x18003c24a  mov     word ptr [rbp+920h+var_850], r13w
0x18003c252  lea     rdx, aEnteredWs; "Entered: %ws"
0x18003c259  lea     rcx, [rbp+920h+var_850]
0x18003c260  call    FormatRRASErrorString
0x18003c265  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x18003c26c  jge     short loc_18003C2C3
0x18003c26e  lea     r8, [rbp+920h+var_850]
0x18003c275  mov     rdx, r12
0x18003c278  mov     rcx, rsi
0x18003c27b  call    McTemplateU0z_EventWriteTransfer
0x18003c280  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x18003c287  jge     short loc_18003C2C3
0x18003c289  lea     r8, [rdi+4]
0x18003c28d  mov     word ptr [rbp+920h+var_850], r13w
0x18003c295  lea     rdx, aLoadprotocolLo; "LoadProtocol: Loading %ws"
0x18003c29c  lea     rcx, [rbp+920h+var_850]
0x18003c2a3  call    FormatRRASErrorString
0x18003c2a8  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x18003c2af  jge     short loc_18003C2C3
0x18003c2b1  lea     r8, [rbp+920h+var_850]
0x18003c2b8  mov     rdx, r12
0x18003c2bb  mov     rcx, rsi
0x18003c2be  call    McTemplateU0z_EventWriteTransfer
0x18003c2c3  lea     r14, [rdi+56h]
0x18003c2c7  xor     edx, edx; hFile
0x18003c2c9  mov     rcx, r14; lpLibFileName
0x18003c2cc  mov     r8d, 1000h; dwFlags
0x18003c2d2  call    cs:__imp_LoadLibraryExW
0x18003c2d8  mov     r15, rax
0x18003c2db  test    rax, rax
0x18003c2de  jnz     short loc_18003C334
0x18003c2e0  call    cs:__imp_GetLastError
0x18003c2e6  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x18003c2ed  mov     ebx, eax
0x18003c2ef  jge     short loc_18003C32D
0x18003c2f1  mov     r9d, eax
0x18003c2f4  mov     word ptr [rbp+920h+var_850], r13w
0x18003c2fc  mov     r8, r14
0x18003c2ff  lea     rdx, aLoadprotocolWs_4; "LoadProtocol: %ws failed to load: %d\n"
0x18003c306  lea     rcx, [rbp+920h+var_850]
0x18003c30d  call    FormatRRASErrorString
0x18003c312  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x18003c319  jge     short loc_18003C32D
0x18003c31b  lea     r8, [rbp+920h+var_850]
0x18003c322  mov     rdx, r12
0x18003c325  mov     rcx, rsi
0x18003c328  call    McTemplateU0z_EventWriteTransfer
0x18003c32d  mov     eax, ebx
0x18003c32f  jmp     loc_18003C9C1
0x18003c334  mov     [rbx+28h], r15
0x18003c338  lea     rdx, ProcName; "RegisterProtocol"
0x18003c33f  mov     eax, [rdi]
0x18003c341  mov     rcx, r15; hModule
0x18003c344  mov     [rbx+3Ch], eax
0x18003c347  call    cs:__imp_GetProcAddress
0x18003c34d  mov     r12, rax
0x18003c350  test    rax, rax
0x18003c353  jnz     short loc_18003C3B6
0x18003c355  xor     ecx, ecx; dwMilliseconds
0x18003c357  call    cs:__imp_Sleep
0x18003c35d  mov     rcx, r15; hLibModule
0x18003c360  call    cs:__imp_FreeLibrary
0x18003c366  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x18003c36d  jge     short loc_18003C3AC
0x18003c36f  mov     r8, r14
0x18003c372  mov     word ptr [rbp+920h+var_850], r13w
0x18003c37a  lea     rdx, aLoadprotocolCo; "LoadProtocol: Could not find RegisterPr"...
0x18003c381  lea     rcx, [rbp+920h+var_850]
0x18003c388  call    FormatRRASErrorString
0x18003c38d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x18003c394  jge     short loc_18003C3AC
0x18003c396  lea     r8, [rbp+920h+var_850]
0x18003c39d  mov     rcx, rsi
0x18003c3a0  lea     rdx, RasRtrmgrTraceInfo
0x18003c3a7  call    McTemplateU0z_EventWriteTransfer
0x18003c3ac  mov     eax, 1
0x18003c3b1  jmp     loc_18003C9C1
0x18003c3b6  xor     edx, edx; Val
0x18003c3b8  lea     rcx, [rsp+0A20h+var_9C4]; void *
0x18003c3bd  mov     r8d, 0FCh; Size
0x18003c3c3  call    memset_0
0x18003c3c8  mov     ecx, [rdi]
0x18003c3ca  mov     edx, 600h
0x18003c3cf  mov     eax, [rbp+920h+arg_30]
0x18003c3d5  neg     eax
0x18003c3d7  mov     [rsp+0A20h+var_9D0], edx
0x18003c3db  mov     [rsp+0A20h+var_9CC], ecx
0x18003c3df  mov     rax, r12
0x18003c3e2  sbb     esi, esi
0x18003c3e4  mov     [rbp+920h+var_8C0], edx
0x18003c3e7  mov     [rbp+920h+var_8BC], ecx
0x18003c3ea  lea     rdx, [rbp+920h+var_8C0]
0x18003c3ee  and     esi, 0FFFFFFFEh
0x18003c3f1  mov     [rbp+920h+var_8B8], r13d
0x18003c3f5  add     esi, 77h ; 'w'
0x18003c3f8  lea     rcx, [rsp+0A20h+var_9D0]
0x18003c3fd  mov     [rsp+0A20h+var_9C8], esi
0x18003c401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c406  mov     r12d, eax
0x18003c409  test    eax, eax
0x18003c40b  jz      short loc_18003C477
0x18003c40d  xor     ecx, ecx; dwMilliseconds
0x18003c40f  call    cs:__imp_Sleep
0x18003c415  mov     rcx, r15; hLibModule
0x18003c418  call    cs:__imp_FreeLibrary
0x18003c41e  mov     [rbx+28h], r13
0x18003c422  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18003c429  jz      short loc_18003C46F
0x18003c42b  mov     r9d, r12d
0x18003c42e  mov     word ptr [rbp+920h+var_850], r13w
0x18003c436  mov     r8, r14
0x18003c439  lea     rdx, aLoadprotocolWs_1; "LoadProtocol: %ws returned error %d whi"...
0x18003c440  lea     rcx, [rbp+920h+var_850]
0x18003c447  call    FormatRRASErrorString
0x18003c44c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18003c453  jz      short loc_18003C46F
0x18003c455  lea     r8, [rbp+920h+var_850]
0x18003c45c  lea     rdx, RasRtrMgrTraceError
0x18003c463  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003c46a  call    McTemplateU0z_EventWriteTransfer
0x18003c46f  mov     eax, r12d
0x18003c472  jmp     loc_18003C9C1
0x18003c477  mov     r9d, [rsp+0A20h+var_9D0]
0x18003c47c  mov     ecx, 600h
0x18003c481  cmp     r9d, ecx
0x18003c484  jbe     short loc_18003C4B8
0x18003c486  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x18003c48d  jge     loc_18003C54B
0x18003c493  lea     rdx, aLoadprotocolWs_5; "LoadProtocol: %ws registered with versi"...
0x18003c49a  mov     [rsp+0A20h+var_A00], ecx
0x18003c49e  lea     r8, [rdi+4]
0x18003c4a2  mov     word ptr [rbp+920h+var_850], r13w
0x18003c4aa  lea     rcx, [rbp+920h+var_850]
0x18003c4b1  call    FormatRRASErrorString
0x18003c4b6  jmp     short loc_18003C528
0x18003c4b8  mov     ecx, [rdi]
0x18003c4ba  mov     r9d, [rsp+0A20h+var_9CC]
0x18003c4bf  cmp     r9d, ecx
0x18003c4c2  jz      short loc_18003C4D6
0x18003c4c4  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x18003c4cb  jge     short loc_18003C54B
0x18003c4cd  lea     rdx, aLoadprotocolWs; "LoadProtocol: %ws returned ID of %x whe"...
0x18003c4d4  jmp     short loc_18003C49A
0x18003c4d6  mov     edx, [rsp+0A20h+var_9C8]
0x18003c4da  mov     eax, esi
0x18003c4dc  not     eax
0x18003c4de  test    edx, eax
0x18003c4e0  jz      short loc_18003C4FB
0x18003c4e2  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x18003c4e9  jge     short loc_18003C54B
0x18003c4eb  mov     r9d, edx
0x18003c4ee  mov     [rsp+0A20h+var_A00], esi
0x18003c4f2  lea     rdx, aLoadprotocolWs_2; "LoadProtocol: %ws wanted functionalitf "...
0x18003c4f9  jmp     short loc_18003C49E
0x18003c4fb  test    dl, 3
0x18003c4fe  jnz     short loc_18003C561
0x18003c500  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x18003c507  jge     short loc_18003C54B
0x18003c509  lea     r8, [rdi+4]
0x18003c50d  mov     word ptr [rbp+920h+var_850], r13w
0x18003c515  lea     rdx, aLoadprotocolWs_6; "LoadProtocol: %ws doesnt support routin"...
0x18003c51c  lea     rcx, [rbp+920h+var_850]
0x18003c523  call    FormatRRASErrorString
0x18003c528  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x18003c52f  jge     short loc_18003C54B
0x18003c531  lea     r8, [rbp+920h+var_850]
0x18003c538  lea     rdx, RasRtrmgrTraceInfo
0x18003c53f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003c546  call    McTemplateU0z_EventWriteTransfer
0x18003c54b  xor     ecx, ecx; dwMilliseconds
0x18003c54d  call    cs:__imp_Sleep
0x18003c553  mov     rcx, r15; hLibModule
0x18003c556  call    cs:__imp_FreeLibrary
0x18003c55c  jmp     loc_18003C9BC
0x18003c561  mov     rax, [rbp+920h+var_998]
0x18003c565  mov     rcx, [rsp+0A20h+var_9C0]
0x18003c56a  mov     r8, [rsp+0A20h+var_9B8]
0x18003c56f  mov     r10, [rsp+0A20h+var_9B0]
0x18003c574  mov     r11, [rsp+0A20h+var_9A8]
0x18003c579  mov     rsi, [rbp+920h+var_9A0]
0x18003c57d  mov     r12, [rbp+920h+var_988]
0x18003c581  mov     r13, [rbp+920h+var_980]
0x18003c585  mov     [rbx+70h], rax
0x18003c589  mov     rax, [rbp+920h+var_990]
0x18003c58d  mov     [rbx+78h], rax
0x18003c591  mov     rax, [rbp+920h+var_978]
0x18003c595  mov     [rbx+90h], rax
0x18003c59c  mov     rax, [rbp+920h+var_970]
0x18003c5a0  mov     [rbx+98h], rax
0x18003c5a7  mov     rax, [rbp+920h+var_968]
0x18003c5ab  mov     [rbx+0A0h], rax
0x18003c5b2  mov     rax, [rbp+920h+var_960]
0x18003c5b6  mov     [rbx+0A8h], rax
0x18003c5bd  mov     rax, [rbp+920h+var_958]
0x18003c5c1  mov     [rbx+0B0h], rax
0x18003c5c8  mov     rax, [rbp+920h+var_950]
0x18003c5cc  mov     [rbx+0B8h], rax
0x18003c5d3  mov     rax, [rbp+920h+var_948]
0x18003c5d7  mov     [rbx+0C0h], rax
0x18003c5de  mov     rax, [rbp+920h+var_940]
0x18003c5e2  mov     [rbx+0C8h], rax
0x18003c5e9  mov     rax, [rbp+920h+var_938]
0x18003c5ed  mov     [rbx+0D0h], rax
0x18003c5f4  mov     rax, [rbp+920h+var_930]
0x18003c5f8  mov     [rbx+0D8h], rax
0x18003c5ff  mov     rax, [rbp+920h+var_928]
0x18003c603  mov     [rbx+0E0h], rax
0x18003c60a  mov     rax, [rbp+920h+var_920]
0x18003c60e  mov     [rbx+0E8h], rax
0x18003c615  mov     rax, [rbp+920h+var_918]
0x18003c619  mov     [rbx+0F0h], rax
0x18003c620  mov     rax, [rbp+920h+var_910]
0x18003c624  mov     [rbx+0F8h], rax
0x18003c62b  mov     rax, [rbp+920h+var_908]
0x18003c62f  mov     [rbx+100h], rax
0x18003c636  mov     rax, [rbp+920h+var_8F0]
0x18003c63a  mov     [rbx+118h], rax
0x18003c641  mov     rax, [rbp+920h+var_8E8]
0x18003c645  mov     [rbx+120h], rax
0x18003c64c  mov     rax, [rbp+920h+var_8E0]
0x18003c650  mov     [rbx+128h], rax
0x18003c657  mov     rax, [rbp+920h+var_8D8]
0x18003c65b  mov     [rbx+130h], rax
0x18003c662  mov     rax, [rbp+920h+var_8D0]
0x18003c666  mov     [rbx+138h], rax
0x18003c66d  mov     [rbx+40h], edx
0x18003c670  mov     [rbx+48h], rcx
0x18003c674  mov     [rbx+50h], r8
0x18003c678  mov     [rbx+58h], r10
0x18003c67c  mov     [rbx+60h], r11
0x18003c680  mov     [rbx+68h], rsi
0x18003c684  mov     [rbx+80h], r12
0x18003c68b  mov     [rbx+88h], r13
0x18003c692  test    rcx, rcx
0x18003c695  jz      loc_18003C959
0x18003c69b  test    r8, r8
0x18003c69e  jz      loc_18003C959
0x18003c6a4  test    r10, r10
0x18003c6a7  jz      loc_18003C959
0x18003c6ad  test    r11, r11
0x18003c6b0  jz      loc_18003C959
0x18003c6b6  test    rsi, rsi
0x18003c6b9  jz      loc_18003C959
0x18003c6bf  test    r12, r12
0x18003c6c2  jz      loc_18003C959
0x18003c6c8  xor     r12d, r12d
0x18003c6cb  test    r13, r13
0x18003c6ce  jz      loc_18003C95C
0x18003c6d4  cmp     [rbp+920h+var_978], r12
0x18003c6d8  jz      loc_18003C95C
0x18003c6de  cmp     [rbp+920h+var_970], r12
0x18003c6e2  jz      loc_18003C95C
0x18003c6e8  cmp     [rbp+920h+var_968], r12
0x18003c6ec  jz      loc_18003C95C
0x18003c6f2  cmp     [rbp+920h+var_960], r12
0x18003c6f6  jz      loc_18003C95C
0x18003c6fc  cmp     [rbp+920h+var_930], r12
0x18003c700  jz      loc_18003C95C
0x18003c706  cmp     [rbp+920h+var_928], r12
0x18003c70a  jz      loc_18003C95C
0x18003c710  cmp     [rbp+920h+var_920], r12
0x18003c714  jz      loc_18003C95C
0x18003c71a  cmp     [rbp+920h+var_918], r12
0x18003c71e  jz      loc_18003C95C
  ... truncated ...
```
