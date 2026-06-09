# WSPStartup

- ea: `0x18000cc50`
- end: `0x18000cff3`
- name: `WSPStartup`
- size: `931`
- prototype: `int __stdcall(WORD wVersionRequested, LPWSPDATA lpWSPData, LPWSAPROTOCOL_INFOW lpProtocolInfo, WSPUPCALLTABLE *__struct_ptr UpcallTable, LPWSPPROC_TABLE lpProcTable)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005f78`
- `0x18000ca20`
- `0x18000cc50`
- `0x18000db30`
- `0x18000dbb0`
- `0x18000ed0c`
- `0x18001e5a4`
- `0x18002324c`
- `0x18003ac78`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000cc8b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000cc8b`
- `ntdll!RtlGetNtProductType` at `0x18000ce3d`
- `ntdll!RtlGetNtProductType` at `0x18000cf2e`
- `ntdll!RtlGetNtProductType` at `0x18000ce3d`
- `ntdll!RtlGetNtProductType` at `0x18000cf2e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000ce8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000ce8e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000cfe2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000cfe2`
- `WS2_32!WahCreateHandleContextTable` at `0x18000ce6b`
- `WS2_32!WahCreateHandleContextTable` at `0x18000ce6b`

## pseudocode

```c
int __stdcall WSPStartup(
        WORD wVersionRequested,
        LPWSPDATA lpWSPData,
        LPWSAPROTOCOL_INFOW lpProtocolInfo,
        WSPUPCALLTABLE *UpcallTable,
        LPWSPPROC_TABLE lpProcTable)
{
  int v9; // ecx
  __int64 v10; // r9
  __int64 v11; // rax
  __int64 v12; // rax
  const wchar_t *v13; // r8
  WCHAR *szDescription; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  WCHAR *v17; // rcx
  int HandleContextTable; // edi
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  _NT_PRODUCT_TYPE ProductType; // [rsp+40h] [rbp-48h] BYREF
  enum _NT_PRODUCT_TYPE v28; // [rsp+44h] [rbp-44h] BYREF
  HMODULE phModule; // [rsp+48h] [rbp-40h] BYREF

  if ( !(unsigned int)MSWSOCK_Initialize() )
    return 10093;
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_sqqqq(
      v9,
      10,
      (unsigned int)WPP_89e6539435863adbd18cb3466bd38bc9_Traceguids,
      (unsigned int)"WSPStartup",
      wVersionRequested,
      (char)lpWSPData,
      (char)UpcallTable,
      0);
  if ( !TlsGetValue(MSAFD_SockTlsSlot) && !(unsigned int)MSAFD_SockThreadInitialize() )
    return 10055;
  if ( wVersionRequested == 514 )
  {
    SockAcquireRwLockExclusive();
    if ( !SockWspStartupCount )
    {
      phModule = 0;
      ProductType = 0;
      if ( RtlGetNtProductType(&ProductType) && ProductType == NtProductWinNt )
        SockSkipInitialShortWait = 1;
      if ( !SockContextTable )
      {
        HandleContextTable = WahCreateHandleContextTable(&SockContextTable);
        if ( HandleContextTable )
          goto LABEL_20;
      }
      if ( !GetModuleHandleExA(4u, (LPCSTR)WSPStartup, &phModule) )
      {
        HandleContextTable = 10107;
        goto LABEL_20;
      }
      v20 = *(_OWORD *)&UpcallTable->lpWPUCloseEvent;
      v21 = *(_OWORD *)&UpcallTable->lpWPUCreateEvent;
      SockUpcallTable = (__int64)&SockUpcallTableSave;
      SockUpcallTableSave = v20;
      v22 = *(_OWORD *)&UpcallTable->lpWPUFDIsSet;
      xmmword_1800645D0 = v21;
      v23 = *(_OWORD *)&UpcallTable->lpWPUModifyIFSHandle;
      xmmword_1800645E0 = v22;
      v24 = *(_OWORD *)&UpcallTable->lpWPUQueryBlockingCallback;
      xmmword_1800645F0 = v23;
      v25 = *(_OWORD *)&UpcallTable->lpWPUQueueApc;
      xmmword_180064600 = v24;
      v26 = *(_OWORD *)&UpcallTable->lpWPUSetEvent;
      xmmword_180064610 = v25;
      *(_QWORD *)&v25 = UpcallTable->lpWPUCloseThread;
      xmmword_180064620 = v26;
      qword_180064630 = v25;
    }
    v11 = *(_QWORD *)&lpProtocolInfo->ProviderId.Data1 - qword_180063794;
    if ( !v11 )
      v11 = *(_QWORD *)lpProtocolInfo->ProviderId.Data4 - qword_18006379C;
    if ( !v11 )
      goto LABEL_43;
    v12 = *(_QWORD *)&lpProtocolInfo->ProviderId.Data1 - qword_180063514;
    if ( !v12 )
      v12 = *(_QWORD *)lpProtocolInfo->ProviderId.Data4 - qword_18006351C;
    if ( !v12 )
    {
LABEL_43:
      v28 = 0;
      if ( RtlGetNtProductType(&v28) )
      {
        if ( v28 != NtProductWinNt && !SockSanEnabled )
        {
          SockSanInitialize();
          if ( SockSanEnabled == 1 )
          {
            HandleContextTable = SockpGetProtocolInfoArray();
            if ( HandleContextTable )
            {
              if ( !SockWspStartupCount )
                FreeLibrary(SockModuleHandle);
              goto LABEL_20;
            }
            SockSanGetTcpipCatalogId();
          }
        }
      }
    }
    ++SockWspStartupCount;
    v13 = L"Microsoft Windows Sockets Version 2.";
    *(_DWORD *)&lpWSPData->wVersion = 33686018;
    szDescription = lpWSPData->szDescription;
    v15 = 2147483646;
    v16 = 256;
    do
    {
      if ( !v15 )
        break;
      v10 = *v13;
      if ( !(_WORD)v10 )
        break;
      *szDescription = v10;
      ++v13;
      ++szDescription;
      --v15;
      --v16;
    }
    while ( v16 );
    v17 = szDescription - 1;
    HandleContextTable = 0;
    if ( v16 )
      v17 = szDescription;
    *v17 = 0;
    *lpProcTable = SockProcTable;
LABEL_20:
    SockReleaseRwLockExclusive(v17, v16, v13, v10);
    return HandleContextTable;
  }
  return 10092;
}

```

## disassembly

```asm
0x18000cc50  push    rbx
0x18000cc52  push    rbp
0x18000cc53  push    rsi
0x18000cc54  push    rdi
0x18000cc55  push    r14
0x18000cc57  push    r15
0x18000cc59  sub     rsp, 58h
0x18000cc5d  mov     rbx, r9
0x18000cc60  movzx   edi, cx
0x18000cc63  mov     rsi, r8
0x18000cc66  mov     r14, rdx
0x18000cc69  call    MSWSOCK_Initialize
0x18000cc6e  xor     ebp, ebp
0x18000cc70  test    eax, eax
0x18000cc72  jz      loc_18000CF80
0x18000cc78  test    byte ptr cs:xmmword_180063D60, 2
0x18000cc7f  jnz     loc_18000CF8A
0x18000cc85  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x18000cc8b  call    cs:__imp_TlsGetValue
0x18000cc92  nop     dword ptr [rax+rax+00h]
0x18000cc97  test    rax, rax
0x18000cc9a  jz      loc_18000CF0E
0x18000cca0  mov     r15d, 202h
0x18000cca6  cmp     di, r15w
0x18000ccaa  jnz     loc_18000CFBB
0x18000ccb0  call    SockAcquireRwLockExclusive
0x18000ccb5  cmp     cs:SockWspStartupCount, ebp
0x18000ccbb  jz      loc_18000CE2F
0x18000ccc1  mov     rax, [rsi+14h]
0x18000ccc5  sub     rax, cs:qword_180063794
0x18000cccc  jnz     short loc_18000CCD9
0x18000ccce  mov     rax, [rsi+1Ch]
0x18000ccd2  sub     rax, cs:qword_18006379C
0x18000ccd9  test    rax, rax
0x18000ccdc  jz      loc_18000CF25
0x18000cce2  mov     rax, [rsi+14h]
0x18000cce6  sub     rax, cs:qword_180063514
0x18000cced  jnz     short loc_18000CCFA
0x18000ccef  mov     rax, [rsi+1Ch]
0x18000ccf3  sub     rax, cs:qword_18006351C
0x18000ccfa  test    rax, rax
0x18000ccfd  jz      loc_18000CF25
0x18000cd03  inc     cs:SockWspStartupCount
0x18000cd09  lea     r8, aMicrosoftWindo; "Microsoft Windows Sockets Version 2."
0x18000cd10  mov     dword ptr [r14], 2020202h
0x18000cd17  lea     rax, [r14+4]
0x18000cd1b  mov     ecx, 7FFFFFFEh
0x18000cd20  mov     edx, 100h
0x18000cd25  test    rcx, rcx
0x18000cd28  jz      short loc_18000CD49
0x18000cd2a  movzx   r9d, word ptr [r8]
0x18000cd2e  test    r9w, r9w
0x18000cd32  jz      short loc_18000CD49
0x18000cd34  mov     [rax], r9w
0x18000cd38  add     r8, 2
0x18000cd3c  add     rax, 2
0x18000cd40  dec     rcx
0x18000cd43  sub     rdx, 1
0x18000cd47  jnz     short loc_18000CD25
0x18000cd49  movaps  xmm0, xmmword ptr cs:SockProcTable
0x18000cd50  lea     rcx, [rax-2]
0x18000cd54  movaps  xmm1, xmmword ptr cs:SockProcTable+10h
0x18000cd5b  test    rdx, rdx
0x18000cd5e  mov     edi, ebp
0x18000cd60  cmovnz  rcx, rax
0x18000cd64  mov     rax, [rsp+88h+lpProcTable]
0x18000cd6c  mov     [rcx], bp
0x18000cd6f  movups  xmmword ptr [rax], xmm0
0x18000cd72  movaps  xmm0, xmmword ptr cs:SockProcTable+20h
0x18000cd79  movups  xmmword ptr [rax+10h], xmm1
0x18000cd7d  movaps  xmm1, xmmword ptr cs:SockProcTable+30h
0x18000cd84  movups  xmmword ptr [rax+20h], xmm0
0x18000cd88  movaps  xmm0, xmmword ptr cs:SockProcTable+40h
0x18000cd8f  movups  xmmword ptr [rax+30h], xmm1
0x18000cd93  movaps  xmm1, xmmword ptr cs:SockProcTable+50h
0x18000cd9a  movups  xmmword ptr [rax+40h], xmm0
0x18000cd9e  movaps  xmm0, xmmword ptr cs:SockProcTable+60h
0x18000cda5  movups  xmmword ptr [rax+50h], xmm1
0x18000cda9  movaps  xmm1, xmmword ptr cs:SockProcTable+70h
0x18000cdb0  movups  xmmword ptr [rax+60h], xmm0
0x18000cdb4  movaps  xmm0, xmmword ptr cs:SockProcTable+80h
0x18000cdbb  movups  xmmword ptr [rax+70h], xmm1
0x18000cdbf  movaps  xmm1, xmmword ptr cs:SockProcTable+90h
0x18000cdc6  movups  xmmword ptr [rax+80h], xmm0
0x18000cdcd  movaps  xmm0, xmmword ptr cs:SockProcTable+0A0h
0x18000cdd4  movups  xmmword ptr [rax+90h], xmm1
0x18000cddb  movaps  xmm1, xmmword ptr cs:SockProcTable+0B0h
0x18000cde2  movups  xmmword ptr [rax+0A0h], xmm0
0x18000cde9  movaps  xmm0, xmmword ptr cs:SockProcTable+0C0h
0x18000cdf0  movups  xmmword ptr [rax+0B0h], xmm1
0x18000cdf7  movaps  xmm1, xmmword ptr cs:SockProcTable+0D0h
0x18000cdfe  movups  xmmword ptr [rax+0C0h], xmm0
0x18000ce05  movaps  xmm0, xmmword ptr cs:SockProcTable+0E0h
0x18000ce0c  movups  xmmword ptr [rax+0D0h], xmm1
0x18000ce13  movups  xmmword ptr [rax+0E0h], xmm0
0x18000ce1a  call    SockReleaseRwLockExclusive
0x18000ce1f  mov     eax, edi
0x18000ce21  add     rsp, 58h
0x18000ce25  pop     r15
0x18000ce27  pop     r14
0x18000ce29  pop     rdi
0x18000ce2a  pop     rsi
0x18000ce2b  pop     rbp
0x18000ce2c  pop     rbx
0x18000ce2d  retn
0x18000ce2f  lea     rcx, [rsp+88h+ProductType]; ProductType
0x18000ce34  mov     [rsp+88h+phModule], rbp
0x18000ce39  mov     [rsp+88h+ProductType], ebp
0x18000ce3d  call    cs:__imp_RtlGetNtProductType
0x18000ce44  nop     dword ptr [rax+rax+00h]
0x18000ce49  test    al, al
0x18000ce4b  jz      short loc_18000CE5B
0x18000ce4d  cmp     [rsp+88h+ProductType], 1
0x18000ce52  jnz     short loc_18000CE5B
0x18000ce54  mov     cs:SockSkipInitialShortWait, 1
0x18000ce5b  cmp     cs:SockContextTable, rbp
0x18000ce62  jnz     short loc_18000CE7D
0x18000ce64  lea     rcx, SockContextTable
0x18000ce6b  call    cs:__imp_WahCreateHandleContextTable
0x18000ce72  nop     dword ptr [rax+rax+00h]
0x18000ce77  mov     edi, eax
0x18000ce79  test    eax, eax
0x18000ce7b  jnz     short loc_18000CE1A
0x18000ce7d  lea     r8, [rsp+88h+phModule]; phModule
0x18000ce82  mov     ecx, 4; dwFlags
0x18000ce87  lea     rdx, WSPStartup; lpModuleName
0x18000ce8e  call    cs:__imp_GetModuleHandleExA
0x18000ce95  nop     dword ptr [rax+rax+00h]
0x18000ce9a  test    eax, eax
0x18000ce9c  jz      loc_18000CFC5
0x18000cea2  movups  xmm0, xmmword ptr [rbx]
0x18000cea5  lea     rax, SockUpcallTableSave
0x18000ceac  movups  xmm1, xmmword ptr [rbx+10h]
0x18000ceb0  mov     cs:SockUpcallTable, rax
0x18000ceb7  movups  cs:SockUpcallTableSave, xmm0
0x18000cebe  movups  xmm0, xmmword ptr [rbx+20h]
0x18000cec2  movups  cs:xmmword_1800645D0, xmm1
0x18000cec9  movups  xmm1, xmmword ptr [rbx+30h]
0x18000cecd  movups  cs:xmmword_1800645E0, xmm0
0x18000ced4  movups  xmm0, xmmword ptr [rbx+40h]
0x18000ced8  movups  cs:xmmword_1800645F0, xmm1
0x18000cedf  movups  xmm1, xmmword ptr [rbx+50h]
0x18000cee3  movups  cs:xmmword_180064600, xmm0
0x18000ceea  movups  xmm0, xmmword ptr [rbx+60h]
0x18000ceee  movups  cs:xmmword_180064610, xmm1
0x18000cef5  movsd   xmm1, qword ptr [rbx+70h]
0x18000cefa  movups  cs:xmmword_180064620, xmm0
0x18000cf01  movsd   cs:qword_180064630, xmm1
0x18000cf09  jmp     loc_18000CCC1
0x18000cf0e  call    MSAFD_SockThreadInitialize
0x18000cf13  test    eax, eax
0x18000cf15  jnz     loc_18000CCA0
0x18000cf1b  mov     eax, 2747h
0x18000cf20  jmp     loc_18000CE21
0x18000cf25  lea     rcx, [rsp+88h+var_44]; ProductType
0x18000cf2a  mov     [rsp+88h+var_44], ebp
0x18000cf2e  call    cs:__imp_RtlGetNtProductType
0x18000cf35  nop     dword ptr [rax+rax+00h]
0x18000cf3a  test    al, al
0x18000cf3c  jz      loc_18000CD03
0x18000cf42  cmp     [rsp+88h+var_44], 1
0x18000cf47  jz      loc_18000CD03
0x18000cf4d  cmp     cs:SockSanEnabled, ebp
0x18000cf53  jnz     loc_18000CD03
0x18000cf59  call    SockSanInitialize
0x18000cf5e  cmp     cs:SockSanEnabled, 1
0x18000cf65  jnz     loc_18000CD03
0x18000cf6b  call    SockpGetProtocolInfoArray
0x18000cf70  mov     edi, eax
0x18000cf72  test    eax, eax
0x18000cf74  jnz     short loc_18000CFCF
0x18000cf76  call    SockSanGetTcpipCatalogId
0x18000cf7b  jmp     loc_18000CD03
0x18000cf80  mov     eax, 276Dh
0x18000cf85  jmp     loc_18000CE21
0x18000cf8a  mov     [rsp+88h+var_50], rbp
0x18000cf8f  lea     r9, aWspstartup_0; "WSPStartup"
0x18000cf96  mov     [rsp+88h+var_58], rbx
0x18000cf9b  lea     r8, WPP_89e6539435863adbd18cb3466bd38bc9_Traceguids
0x18000cfa2  mov     [rsp+88h+var_60], r14
0x18000cfa7  mov     edx, 0Ah
0x18000cfac  mov     [rsp+88h+var_68], rdi
0x18000cfb1  call    WPP_SF_sqqqq
0x18000cfb6  jmp     loc_18000CC85
0x18000cfbb  mov     eax, 276Ch
0x18000cfc0  jmp     loc_18000CE21
0x18000cfc5  mov     edi, 277Bh
0x18000cfca  jmp     loc_18000CE1A
0x18000cfcf  cmp     cs:SockWspStartupCount, ebp
0x18000cfd5  jnz     loc_18000CE1A
0x18000cfdb  mov     rcx, cs:SockModuleHandle; hLibModule
0x18000cfe2  call    cs:__imp_FreeLibrary
0x18000cfe9  nop     dword ptr [rax+rax+00h]
0x18000cfee  jmp     loc_18000CE1A
```
