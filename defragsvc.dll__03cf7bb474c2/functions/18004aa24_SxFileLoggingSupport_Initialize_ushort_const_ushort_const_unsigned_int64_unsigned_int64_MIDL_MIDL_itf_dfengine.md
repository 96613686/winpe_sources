# SxFileLoggingSupport::Initialize(ushort const *,ushort const *,unsigned __int64,unsigned __int64,__MIDL___MIDL_itf_dfengine_0000_0000_0006 *,DF_SHRINK_INHIBITOR_PHASE)

- ea: `0x18004aa24`
- end: `0x18004af87`
- name: `?Initialize@SxFileLoggingSupport@@QEAAJPEBG0_K1PEAU__MIDL___MIDL_itf_dfengine_0000_0000_0006@@W4DF_SHRINK_INHIBITOR_PHASE@@@Z`
- size: `1379`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, __int64, __int64, __int64, __int64, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180022280`
- `0x1800309c0`
- `0x18005a820`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180010bc0`
- `0x18001a630`
- `0x18001b300`
- `0x180046494`
- `0x18004aa24`
- `0x18004af90`
- `0x18004b63c`
- `0x180067b30`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004acdb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004acdb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004ad47`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004ada0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004ad47`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004ada0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004ad7d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004ad7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ad87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004add6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ad87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004add6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004af51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004af51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004ad18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004ad18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ad97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ad97`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall SxFileLoggingSupport::Initialize(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7)
{
  __int64 FileW; // rbx
  CSxGlobalTracer *v12; // rcx
  const wchar_t *v13; // r9
  int IsBootVolume; // edi
  __int16 v15; // ax
  SxFileLoggingSupport *v16; // rcx
  unsigned int *v17; // rdi
  ULONGLONG TickCount64; // r14
  ULONGLONG v19; // rdx
  char *v20; // r9
  _WORD *v21; // rdi
  unsigned int v22; // eax
  ULONGLONG v23; // rdx
  CSxGlobalTracer *v24; // rcx
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v28; // [rsp+4Ch] [rbp-B4h]
  __int16 v29; // [rsp+4Eh] [rbp-B2h]
  WCHAR FileName[268]; // [rsp+80h] [rbp-80h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v27, "SxFileLoggingSupport::Initialize", 0x49u, 1u);
  FileW = -1;
  BytesReturned = 0;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_7ca5c123dafd3d0bdbf44829d988681f_Traceguids, a2);
      v12 = WPP_GLOBAL_Control;
    }
    if ( v12 != (CSxGlobalTracer *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)v12 + 7) & 0x8000000) != 0 )
      {
        WPP_SF_S(*((_QWORD *)v12 + 2), 11, WPP_7ca5c123dafd3d0bdbf44829d988681f_Traceguids, a3);
        v12 = WPP_GLOBAL_Control;
      }
      if ( v12 != (CSxGlobalTracer *)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)v12 + 7) & 0x8000000) != 0 )
        {
          WPP_SF_d(*((_QWORD *)v12 + 2), 12, WPP_7ca5c123dafd3d0bdbf44829d988681f_Traceguids, (unsigned int)a4);
          v12 = WPP_GLOBAL_Control;
        }
        if ( v12 != (CSxGlobalTracer *)&WPP_GLOBAL_Control )
        {
          if ( (*((_DWORD *)v12 + 7) & 0x8000000) != 0 )
          {
            WPP_SF_d(*((_QWORD *)v12 + 2), 13, WPP_7ca5c123dafd3d0bdbf44829d988681f_Traceguids, (unsigned int)a5);
            v12 = WPP_GLOBAL_Control;
          }
          if ( v12 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x8000000) != 0 )
          {
            if ( a7 == 1 )
            {
              v13 = L"<analysis>";
            }
            else if ( a7 == 2 )
            {
              v13 = L"<eviction>";
            }
            else
            {
              v13 = L"<check>";
              if ( a7 != 3 )
                v13 = L"<unknown>";
            }
            WPP_SF_S(*((_QWORD *)v12 + 2), 14, WPP_7ca5c123dafd3d0bdbf44829d988681f_Traceguids, v13);
          }
        }
      }
    }
  }
  if ( *(_DWORD *)(a1 + 124) )
  {
    IsBootVolume = -2147418113;
    v15 = 97;
LABEL_70:
    v27 = IsBootVolume;
    goto LABEL_71;
  }
  *(_QWORD *)(a1 + 80) = a2;
  *(_QWORD *)(a1 + 88) = a3;
  *(_QWORD *)(a1 + 96) = a4;
  *(_QWORD *)(a1 + 104) = a5;
  *(_QWORD *)(a1 + 112) = a6;
  *(_DWORD *)(a1 + 120) = a7;
  v16 = (SxFileLoggingSupport *)(unsigned int)(*(_DWORD *)(a6 + 208) - 1);
  if ( ((unsigned int)v16 & 0xFFFFFFFD) != 0 )
  {
    IsBootVolume = -2147418113;
    v15 = 118;
    goto LABEL_70;
  }
  IsBootVolume = SxFileLoggingSupport::IsBootVolume(v16, a2, (int *)(a1 + 56));
  v27 = IsBootVolume;
  v15 = 122;
  if ( IsBootVolume < 0 )
    goto LABEL_71;
  v28 = 122;
  IsBootVolume = StringCchPrintfW(FileName, 0x105u, L"%s\\$Volume", a2);
  v27 = IsBootVolume;
  v15 = 125;
  if ( IsBootVolume < 0 )
    goto LABEL_71;
  v28 = 125;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_7ca5c123dafd3d0bdbf44829d988681f_Traceguids, FileName);
  }
  FileW = (__int64)CreateFileW(FileName, 0x80000000, 3u, 0, 3u, 0x2000080u, 0);
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    IsBootVolume = GetLastFailureAsHRESULT();
    v27 = IsBootVolume;
    v15 = 141;
LABEL_71:
    v29 = v15;
    goto LABEL_72;
  }
  v27 = 0;
  v28 = 141;
  v17 = (unsigned int *)CoTaskMemAlloc(0x400u);
  *(_QWORD *)a1 = v17;
  v15 = 149;
  if ( !v17 )
  {
    IsBootVolume = -2147024882;
    goto LABEL_70;
  }
  v27 = 0;
  v28 = 149;
  *v17 = 0;
  v17[1] = 1;
  *((_QWORD *)v17 + 1) = a4;
  TickCount64 = GetTickCount64();
  if ( !DeviceIoControl((HANDLE)FileW, 0x901FCu, v17, 0x18u, v17, 0x400u, &BytesReturned, 0) )
  {
    if ( GetLastError() != 234 )
    {
      GetLastError();
      IsBootVolume = GetLastFailureAsHRESULT();
      v27 = IsBootVolume;
      v15 = 199;
      goto LABEL_71;
    }
    CoTaskMemFree(*(LPVOID *)a1);
    *(_QWORD *)a1 = 0;
  }
  v19 = GetTickCount64();
  if ( *v17 )
  {
    v20 = (char *)v17 + *v17;
    *(_QWORD *)(a1 + 8) = v20;
    v21 = (_WORD *)(a1 + 60);
    if ( (v20[4] & 1) != 0 )
    {
      *v21 = 80;
      *(_DWORD *)(a1 + 16) = 1;
    }
    else
    {
      *v21 = 45;
    }
    if ( (v20[4] & 4) != 0 )
    {
      *(_WORD *)(a1 + 62) = 83;
      *(_DWORD *)(a1 + 20) = 1;
    }
    else
    {
      *(_WORD *)(a1 + 62) = 45;
    }
    if ( (v20[4] & 8) != 0 )
    {
      *(_WORD *)(a1 + 64) = 84;
      *(_DWORD *)(a1 + 24) = 1;
    }
    else
    {
      *(_WORD *)(a1 + 64) = 45;
    }
    if ( (v20[4] & 2) != 0 )
    {
      *(_WORD *)(a1 + 66) = 65;
      *(_DWORD *)(a1 + 28) = 1;
    }
    else
    {
      *(_WORD *)(a1 + 66) = 45;
    }
    v22 = *((_DWORD *)v20 + 1) & 0xFF000000;
    switch ( v22 )
    {
      case 0x1000000u:
        *(_WORD *)(a1 + 68) = 68;
        *(_DWORD *)(a1 + 32) = 1;
        break;
      case 0x2000000u:
        *(_WORD *)(a1 + 68) = 73;
        *(_DWORD *)(a1 + 44) = 1;
        break;
      case 0x3000000u:
        *(_WORD *)(a1 + 68) = 83;
        *(_DWORD *)(a1 + 36) = 1;
        break;
      default:
        *(_WORD *)(a1 + 68) = 63;
        *(_DWORD *)(a1 + 40) = 1;
        break;
    }
    *(_WORD *)(a1 + 70) = 0;
    v23 = v19 - TickCount64;
    *(_QWORD *)(a1 + 48) = v23;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        WPP_SF_LL(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, 83, *((unsigned int *)v20 + 5), *((_DWORD *)v20 + 4));
        v24 = WPP_GLOBAL_Control;
      }
      if ( v24 != (CSxGlobalTracer *)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)v24 + 7) & 0x8000000) != 0 )
        {
          WPP_SF_S(
            *((_QWORD *)v24 + 2),
            17,
            WPP_7ca5c123dafd3d0bdbf44829d988681f_Traceguids,
            *(_QWORD *)(a1 + 8) + 24LL);
          v24 = WPP_GLOBAL_Control;
        }
        if ( v24 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v24 + 7) & 0x8000000) != 0 )
          WPP_SF_S(*((_QWORD *)v24 + 2), 18, WPP_7ca5c123dafd3d0bdbf44829d988681f_Traceguids, a1 + 60);
      }
    }
    *(_DWORD *)(a1 + 128) = 1;
  }
  *(_DWORD *)(a1 + 124) = 1;
  IsBootVolume = v27;
LABEL_72:
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v27);
  return (unsigned int)IsBootVolume;
}

```

## disassembly

```asm
0x18004aa24  push    rbp
0x18004aa26  push    rbx
0x18004aa27  push    rsi
0x18004aa28  push    rdi
0x18004aa29  push    r12
0x18004aa2b  push    r13
0x18004aa2d  push    r14
0x18004aa2f  push    r15
0x18004aa31  lea     rbp, [rsp-1A8h]
0x18004aa39  sub     rsp, 2A8h
0x18004aa40  mov     rax, cs:__security_cookie
0x18004aa47  xor     rax, rsp
0x18004aa4a  mov     [rbp+1E0h+var_48], rax
0x18004aa51  mov     r13, r9
0x18004aa54  mov     r15, r8
0x18004aa57  mov     r14, rdx
0x18004aa5a  mov     rsi, rcx
0x18004aa5d  mov     r9d, 1; unsigned __int16
0x18004aa63  lea     r8d, [r9+48h]; unsigned __int16
0x18004aa67  lea     rdx, aSxfileloggings; "SxFileLoggingSupport::Initialize"
0x18004aa6e  lea     rcx, [rsp+2E0h+var_298]; this
0x18004aa73  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18004aa78  nop
0x18004aa79  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004aa7d  mov     [rsp+2E0h+BytesReturned], 0
0x18004aa85  lea     rax, WPP_GLOBAL_Control
0x18004aa8c  mov     edi, [rbp+1E0h+arg_30]
0x18004aa92  mov     r12, [rbp+1E0h+arg_20]
0x18004aa99  mov     rcx, cs:WPP_GLOBAL_Control
0x18004aaa0  cmp     rcx, rax
0x18004aaa3  jz      loc_18004ABD2
0x18004aaa9  test    dword ptr [rcx+1Ch], 8000000h
0x18004aab0  jz      short loc_18004AAD6
0x18004aab2  lea     edx, [rbx+0Bh]
0x18004aab5  mov     r9, r14
0x18004aab8  lea     r8, WPP_7ca5c123dafd3d0bdbf44829d988681f_Traceguids
0x18004aabf  mov     rcx, [rcx+10h]
0x18004aac3  call    WPP_SF_S
0x18004aac8  mov     rcx, cs:WPP_GLOBAL_Control
0x18004aacf  lea     rax, WPP_GLOBAL_Control
0x18004aad6  cmp     rcx, rax
0x18004aad9  jz      loc_18004ABD2
0x18004aadf  test    dword ptr [rcx+1Ch], 8000000h
0x18004aae6  jz      short loc_18004AB0E
0x18004aae8  mov     edx, 0Bh
0x18004aaed  mov     r9, r15
0x18004aaf0  lea     r8, WPP_7ca5c123dafd3d0bdbf44829d988681f_Traceguids
0x18004aaf7  mov     rcx, [rcx+10h]
0x18004aafb  call    WPP_SF_S
0x18004ab00  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ab07  lea     rax, WPP_GLOBAL_Control
0x18004ab0e  cmp     rcx, rax
0x18004ab11  jz      loc_18004ABD2
0x18004ab17  test    dword ptr [rcx+1Ch], 8000000h
0x18004ab1e  jz      short loc_18004AB46
0x18004ab20  mov     r9d, r13d
0x18004ab23  mov     edx, 0Ch
0x18004ab28  lea     r8, WPP_7ca5c123dafd3d0bdbf44829d988681f_Traceguids
0x18004ab2f  mov     rcx, [rcx+10h]
0x18004ab33  call    WPP_SF_d
0x18004ab38  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ab3f  lea     rax, WPP_GLOBAL_Control
0x18004ab46  cmp     rcx, rax
0x18004ab49  jz      loc_18004ABD2
0x18004ab4f  test    dword ptr [rcx+1Ch], 8000000h
0x18004ab56  jz      short loc_18004AB7E
0x18004ab58  mov     r9d, r12d
0x18004ab5b  mov     edx, 0Dh
0x18004ab60  lea     r8, WPP_7ca5c123dafd3d0bdbf44829d988681f_Traceguids
0x18004ab67  mov     rcx, [rcx+10h]
0x18004ab6b  call    WPP_SF_d
0x18004ab70  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ab77  lea     rax, WPP_GLOBAL_Control
0x18004ab7e  cmp     rcx, rax
0x18004ab81  jz      short loc_18004ABD2
0x18004ab83  test    dword ptr [rcx+1Ch], 8000000h
0x18004ab8a  jz      short loc_18004ABD2
0x18004ab8c  cmp     edi, 1
0x18004ab8f  jnz     short loc_18004AB9A
0x18004ab91  lea     r9, aAnalysis; "<analysis>"
0x18004ab98  jmp     short loc_18004ABBD
0x18004ab9a  cmp     edi, 2
0x18004ab9d  jnz     short loc_18004ABA8
0x18004ab9f  lea     r9, aEviction; "<eviction>"
0x18004aba6  jmp     short loc_18004ABBD
0x18004aba8  lea     r9, aCheck; "<check>"
0x18004abaf  lea     rax, aUnknown; "<unknown>"
0x18004abb6  cmp     edi, 3
0x18004abb9  cmovnz  r9, rax
0x18004abbd  mov     edx, 0Eh
0x18004abc2  lea     r8, WPP_7ca5c123dafd3d0bdbf44829d988681f_Traceguids
0x18004abc9  mov     rcx, [rcx+10h]
0x18004abcd  call    WPP_SF_S
0x18004abd2  cmp     dword ptr [rsi+7Ch], 0
0x18004abd6  jz      short loc_18004ABE7
0x18004abd8  mov     edi, 8000FFFFh
0x18004abdd  mov     eax, 61h ; 'a'
0x18004abe2  jmp     loc_18004AF3B
0x18004abe7  mov     [rsi+50h], r14
0x18004abeb  mov     [rsi+58h], r15
0x18004abef  mov     [rsi+60h], r13
0x18004abf3  mov     [rsi+68h], r12
0x18004abf7  mov     rax, [rbp+1E0h+arg_28]
0x18004abfe  mov     [rsi+70h], rax
0x18004ac02  mov     [rsi+78h], edi
0x18004ac05  mov     ecx, [rax+0D0h]
0x18004ac0b  mov     r15d, 1
0x18004ac11  sub     ecx, r15d; this
0x18004ac14  test    ecx, 0FFFFFFFDh
0x18004ac1a  jz      short loc_18004AC2A
0x18004ac1c  mov     edi, 8000FFFFh
0x18004ac21  lea     eax, [r15+75h]
0x18004ac25  jmp     loc_18004AF3B
0x18004ac2a  lea     r8, [rsi+38h]; int *
0x18004ac2e  mov     rdx, r14; unsigned __int16 *
0x18004ac31  call    ?IsBootVolume@SxFileLoggingSupport@@AEAAJPEBGPEAH@Z; SxFileLoggingSupport::IsBootVolume(ushort const *,int *)
0x18004ac36  mov     edi, eax
0x18004ac38  mov     [rsp+2E0h+var_298], eax
0x18004ac3c  xor     r12d, r12d
0x18004ac3f  test    eax, eax
0x18004ac41  lea     eax, [r12+7Ah]
0x18004ac46  js      loc_18004AF3F
0x18004ac4c  mov     [rsp+2E0h+var_294], ax
0x18004ac51  mov     r9, r14
0x18004ac54  lea     r8, aSVolume; "%s\\$Volume"
0x18004ac5b  mov     edx, 105h; unsigned __int64
0x18004ac60  lea     rcx, [rbp+1E0h+FileName]; unsigned __int16 *
0x18004ac64  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004ac69  mov     edi, eax
0x18004ac6b  mov     [rsp+2E0h+var_298], eax
0x18004ac6f  test    eax, eax
0x18004ac71  lea     eax, [r12+7Dh]
0x18004ac76  js      loc_18004AF3F
0x18004ac7c  mov     [rsp+2E0h+var_294], ax
0x18004ac81  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ac88  lea     rax, WPP_GLOBAL_Control
0x18004ac8f  cmp     rcx, rax
0x18004ac92  jz      short loc_18004ACB6
0x18004ac94  test    dword ptr [rcx+1Ch], 8000000h
0x18004ac9b  jz      short loc_18004ACB6
0x18004ac9d  lea     edx, [r12+0Fh]
0x18004aca2  lea     r9, [rbp+1E0h+FileName]
0x18004aca6  lea     r8, WPP_7ca5c123dafd3d0bdbf44829d988681f_Traceguids
0x18004acad  mov     rcx, [rcx+10h]
0x18004acb1  call    WPP_SF_S
0x18004acb6  mov     [rsp+2E0h+hTemplateFile], r12; hTemplateFile
0x18004acbb  mov     [rsp+2E0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x18004acc3  mov     eax, 3
0x18004acc8  mov     [rsp+2E0h+dwCreationDisposition], eax; dwCreationDisposition
0x18004accc  xor     r9d, r9d; lpSecurityAttributes
0x18004accf  mov     r8d, eax; dwShareMode
0x18004acd2  mov     edx, 80000000h; dwDesiredAccess
0x18004acd7  lea     rcx, [rbp+1E0h+FileName]; lpFileName
0x18004acdb  call    cs:__imp_CreateFileW
0x18004ace1  mov     rbx, rax
0x18004ace4  inc     rax
0x18004ace7  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004aced  jnz     short loc_18004AD04
0x18004acef  call    GetLastFailureAsHRESULT
0x18004acf4  mov     edi, eax
0x18004acf6  mov     [rsp+2E0h+var_298], eax
0x18004acfa  mov     eax, 8Dh
0x18004acff  jmp     loc_18004AF3F
0x18004ad04  mov     [rsp+2E0h+var_298], r12d
0x18004ad09  mov     eax, 8Dh
0x18004ad0e  mov     [rsp+2E0h+var_294], ax
0x18004ad13  mov     ecx, 400h; cb
0x18004ad18  call    cs:__imp_CoTaskMemAlloc
0x18004ad1e  mov     rdi, rax
0x18004ad21  mov     [rsi], rax
0x18004ad24  test    rax, rax
0x18004ad27  mov     eax, 95h
0x18004ad2c  jz      loc_18004AF36
0x18004ad32  mov     [rsp+2E0h+var_298], r12d
0x18004ad37  mov     [rsp+2E0h+var_294], ax
0x18004ad3c  mov     [rdi], r12d
0x18004ad3f  mov     [rdi+4], r15d
0x18004ad43  mov     [rdi+8], r13
0x18004ad47  call    cs:__imp_GetTickCount64
0x18004ad4d  mov     r14, rax
0x18004ad50  mov     [rsp+2E0h+lpOverlapped], r12; lpOverlapped
0x18004ad55  lea     rax, [rsp+2E0h+BytesReturned]
0x18004ad5a  mov     [rsp+2E0h+hTemplateFile], rax; lpBytesReturned
0x18004ad5f  mov     [rsp+2E0h+dwFlagsAndAttributes], 400h; nOutBufferSize
0x18004ad67  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rdi; lpOutBuffer
0x18004ad6c  mov     r9d, 18h; nInBufferSize
0x18004ad72  mov     r8, rdi; lpInBuffer
0x18004ad75  mov     edx, 901FCh; dwIoControlCode
0x18004ad7a  mov     rcx, rbx; hDevice
0x18004ad7d  call    cs:__imp_DeviceIoControl
0x18004ad83  test    eax, eax
0x18004ad85  jnz     short loc_18004ADA0
0x18004ad87  call    cs:__imp_GetLastError
0x18004ad8d  cmp     eax, 0EAh
0x18004ad92  jnz     short loc_18004ADD6
0x18004ad94  mov     rcx, [rsi]; pv
0x18004ad97  call    cs:__imp_CoTaskMemFree
0x18004ad9d  mov     [rsi], r12
0x18004ada0  call    cs:__imp_GetTickCount64
0x18004ada6  mov     rdx, rax
0x18004ada9  cmp     [rdi], r12d
0x18004adac  jz      loc_18004AF2C
0x18004adb2  mov     r9d, [rdi]
0x18004adb5  add     r9, rdi
0x18004adb8  mov     [rsi+8], r9
0x18004adbc  lea     rdi, [rsi+3Ch]
0x18004adc0  mov     ecx, 2Dh ; '-'
0x18004adc5  test    [r9+4], r15b
0x18004adc9  jz      short loc_18004ADF1
0x18004adcb  mov     word ptr [rdi], 50h ; 'P'
0x18004add0  mov     [rsi+10h], r15d
0x18004add4  jmp     short loc_18004ADF4
0x18004add6  call    cs:__imp_GetLastError
0x18004addc  call    GetLastFailureAsHRESULT
0x18004ade1  mov     edi, eax
0x18004ade3  mov     [rsp+2E0h+var_298], eax
0x18004ade7  mov     eax, 0C7h
0x18004adec  jmp     loc_18004AF3F
0x18004adf1  mov     [rdi], cx
0x18004adf4  mov     r8d, 53h ; 'S'
0x18004adfa  test    byte ptr [r9+4], 4
0x18004adff  jz      short loc_18004AE0C
0x18004ae01  mov     [rsi+3Eh], r8w
0x18004ae06  mov     [rsi+14h], r15d
0x18004ae0a  jmp     short loc_18004AE10
0x18004ae0c  mov     [rsi+3Eh], cx
0x18004ae10  test    byte ptr [r9+4], 8
0x18004ae15  jz      short loc_18004AE23
0x18004ae17  mov     word ptr [rsi+40h], 54h ; 'T'
0x18004ae1d  mov     [rsi+18h], r15d
0x18004ae21  jmp     short loc_18004AE27
0x18004ae23  mov     [rsi+40h], cx
0x18004ae27  test    byte ptr [r9+4], 2
0x18004ae2c  jz      short loc_18004AE3A
0x18004ae2e  mov     word ptr [rsi+42h], 41h ; 'A'
0x18004ae34  mov     [rsi+1Ch], r15d
0x18004ae38  jmp     short loc_18004AE3E
0x18004ae3a  mov     [rsi+42h], cx
0x18004ae3e  mov     eax, [r9+4]
0x18004ae42  and     eax, 0FF000000h
0x18004ae47  cmp     eax, 1000000h
0x18004ae4c  jz      short loc_18004AE7F
0x18004ae4e  cmp     eax, 2000000h
0x18004ae53  jz      short loc_18004AE73
0x18004ae55  cmp     eax, 3000000h
0x18004ae5a  jz      short loc_18004AE68
0x18004ae5c  mov     word ptr [rsi+44h], 3Fh ; '?'
0x18004ae62  mov     [rsi+28h], r15d
0x18004ae66  jmp     short loc_18004AE89
0x18004ae68  mov     [rsi+44h], r8w
0x18004ae6d  mov     [rsi+24h], r15d
0x18004ae71  jmp     short loc_18004AE89
0x18004ae73  mov     word ptr [rsi+44h], 49h ; 'I'
0x18004ae79  mov     [rsi+2Ch], r15d
0x18004ae7d  jmp     short loc_18004AE89
0x18004ae7f  mov     word ptr [rsi+44h], 44h ; 'D'
0x18004ae85  mov     [rsi+20h], r15d
0x18004ae89  mov     [rsi+46h], r12w
0x18004ae8e  sub     rdx, r14
0x18004ae91  mov     [rsi+30h], rdx
0x18004ae95  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ae9c  lea     r14, WPP_GLOBAL_Control
0x18004aea3  cmp     rcx, r14
0x18004aea6  jz      short loc_18004AF25
0x18004aea8  test    dword ptr [rcx+1Ch], 8000000h
0x18004aeaf  jz      short loc_18004AECD
0x18004aeb1  mov     eax, [r9+10h]
0x18004aeb5  mov     [rsp+2E0h+dwCreationDisposition], eax
0x18004aeb9  mov     r9d, [r9+14h]
0x18004aebd  mov     rcx, [rcx+10h]
0x18004aec1  call    WPP_SF_LL
0x18004aec6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004aecd  cmp     rcx, r14
0x18004aed0  jz      short loc_18004AF25
0x18004aed2  test    dword ptr [rcx+1Ch], 8000000h
0x18004aed9  jz      short loc_18004AEFF
0x18004aedb  mov     r9, [rsi+8]
0x18004aedf  add     r9, 18h
0x18004aee3  mov     edx, 11h
0x18004aee8  lea     r8, WPP_7ca5c123dafd3d0bdbf44829d988681f_Traceguids
0x18004aeef  mov     rcx, [rcx+10h]
0x18004aef3  call    WPP_SF_S
0x18004aef8  mov     rcx, cs:WPP_GLOBAL_Control
0x18004aeff  cmp     rcx, r14
0x18004af02  jz      short loc_18004AF25
0x18004af04  test    dword ptr [rcx+1Ch], 8000000h
0x18004af0b  jz      short loc_18004AF25
0x18004af0d  mov     edx, 12h
0x18004af12  mov     r9, rdi
0x18004af15  lea     r8, WPP_7ca5c123dafd3d0bdbf44829d988681f_Traceguids
0x18004af1c  mov     rcx, [rcx+10h]
0x18004af20  call    WPP_SF_S
0x18004af25  mov     [rsi+80h], r15d
0x18004af2c  mov     [rsi+7Ch], r15d
0x18004af30  mov     edi, [rsp+2E0h+var_298]
0x18004af34  jmp     short loc_18004AF44
0x18004af36  mov     edi, 8007000Eh
0x18004af3b  mov     [rsp+2E0h+var_298], edi
0x18004af3f  mov     [rsp+2E0h+var_292], ax
0x18004af44  lea     rcx, [rbx-1]
  ... truncated ...
```
