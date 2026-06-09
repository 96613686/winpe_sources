# CRuntimePlugin::GetRuntimeCrashApi(ulong *,long (**)(void *,_WER_RUNTIME_EXCEPTION_INFORMATION * const,ulong,wchar_t *,ulong *,wchar_t *,ulong *),long (**)(void *,_WER_RUNTIME_EXCEPTION_INFORMATION * const,int *,wchar_t *,ulong *,int *),tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> *,void * *)

- ea: `0x18002dcdc`
- end: `0x18002e351`
- name: `?GetRuntimeCrashApi@CRuntimePlugin@@AEAAJPEAKPEAP6AJPEAXQEAU_WER_RUNTIME_EXCEPTION_INFORMATION@@KPEA_W030@ZPEAP6AJ12PEAH305@ZPEAV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEAPEAX@Z`
- size: `1653`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002e360`

## callees

- `0x180002890`
- `0x1800028b4`
- `0x1800047cc`
- `0x18000760c`
- `0x180009ed8`
- `0x180009f00`
- `0x180009f8c`
- `0x180016b78`
- `0x18001bec8`
- `0x18002d92c`
- `0x18002dcdc`
- `0x18003e5a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e2c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e2c4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002e0d0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002e10e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002e0d0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002e10e`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002deac`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002df64`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002deac`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002df64`

## pseudocode

```c
__int64 __fastcall CRuntimePlugin::GetRuntimeCrashApi(
        __int64 a1,
        __int64 a2,
        FARPROC *a3,
        FARPROC *a4,
        HMODULE *a5,
        _QWORD *a6)
{
  __int64 v6; // r12
  unsigned int RuntimeDllsListStart; // ebx
  __int64 v8; // rcx
  LPCVOID v9; // r15
  unsigned int v10; // edx
  int v11; // ebx
  SIZE_T v12; // rbx
  _QWORD *v13; // rax
  _QWORD *v14; // r12
  SIZE_T v15; // r9
  __int64 v16; // rbx
  __int64 v17; // rdx
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r8
  WCHAR *v21; // r9
  WCHAR *v22; // rcx
  int v23; // r11d
  __int64 v24; // rax
  WCHAR v25; // r10
  char v26; // al
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  int v30; // [rsp+40h] [rbp-2F8h]
  unsigned int v31; // [rsp+44h] [rbp-2F4h]
  SIZE_T NumberOfBytesRead; // [rsp+48h] [rbp-2F0h] BYREF
  LPCVOID lpBaseAddress; // [rsp+50h] [rbp-2E8h] BYREF
  int v34; // [rsp+58h] [rbp-2E0h]
  WCHAR *v35; // [rsp+60h] [rbp-2D8h]
  __int64 v36; // [rsp+68h] [rbp-2D0h]
  __int64 v37; // [rsp+70h] [rbp-2C8h]
  unsigned int v38; // [rsp+78h] [rbp-2C0h]
  int v39; // [rsp+7Ch] [rbp-2BCh]
  __int64 v40; // [rsp+80h] [rbp-2B8h]
  WCHAR *v41; // [rsp+88h] [rbp-2B0h]
  __int64 v42; // [rsp+90h] [rbp-2A8h]
  __int64 v43; // [rsp+98h] [rbp-2A0h]
  HMODULE *v44; // [rsp+A0h] [rbp-298h]
  FARPROC *v45; // [rsp+A8h] [rbp-290h]
  FARPROC *v46; // [rsp+B0h] [rbp-288h]
  __int64 v47; // [rsp+B8h] [rbp-280h]
  _QWORD *v48; // [rsp+C0h] [rbp-278h]
  _QWORD *v49; // [rsp+C8h] [rbp-270h]
  __int128 Buffer; // [rsp+D0h] [rbp-268h] BYREF
  __int64 v51; // [rsp+E0h] [rbp-258h]
  WCHAR Value[264]; // [rsp+F0h] [rbp-248h] BYREF

  v45 = a4;
  v46 = a3;
  v47 = a2;
  v6 = a1;
  v37 = a1;
  v44 = a5;
  v48 = a6;
  v40 = 0;
  lpBaseAddress = 0;
  RuntimeDllsListStart = WerpGetRuntimeDllsListStart(*(void **)(a1 + 760), (struct _WER_RUNTIME_DLL **)&lpBaseAddress);
  v8 = RuntimeDllsListStart + 0x80000000;
  if ( (int)v8 >= 0 && RuntimeDllsListStart != -2147023728 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids,
        RuntimeDllsListStart);
    return RuntimeDllsListStart;
  }
  v9 = lpBaseAddress;
  if ( lpBaseAddress )
  {
    v10 = 0;
    v11 = 0;
    v30 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids, lpBaseAddress);
      v10 = 0;
    }
    while ( 1 )
    {
      if ( v11 )
        return v11 == 0 ? 0x80004005 : 0;
      if ( !v9 )
        return v11 == 0 ? 0x80004005 : 0;
      v31 = v10 + 1;
      v38 = v10 + 1;
      if ( v10 >= 0x10 )
        return v11 == 0 ? 0x80004005 : 0;
      Buffer = 0;
      v51 = 0;
      v34 = 0;
      NumberOfBytesRead = 0;
      if ( !ReadProcessMemory(*(HANDLE *)(v6 + 760), v9, &Buffer, 0x18u, &NumberOfBytesRead) || NumberOfBytesRead != 24 )
      {
        GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
        return v11 == 0 ? 0x80004005 : 0;
      }
      v34 = DWORD2(Buffer);
      if ( (unsigned int)(DWORD2(Buffer) - 24) > 0x208 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids,
            DWORD2(Buffer));
        return v11 == 0 ? 0x80004005 : 0;
      }
      NumberOfBytesRead = 0;
      v12 = DWORD2(Buffer);
      v13 = operator new[](DWORD2(Buffer), (const struct std::nothrow_t *)&std::nothrow);
      v14 = v13;
      v49 = v13;
      if ( !v13 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
        v11 = v30;
        return v11 == 0 ? 0x80004005 : 0;
      }
      v15 = v12;
      v16 = v37;
      if ( !ReadProcessMemory(*(HANDLE *)(v37 + 760), v9, v13, v15, &NumberOfBytesRead) )
      {
        v9 = 0;
        lpBaseAddress = 0;
        goto LABEL_68;
      }
      v9 = (LPCVOID)*v14;
      lpBaseAddress = v9;
      if ( v9 == (LPCVOID)-24LL )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v19 = (unsigned int)((_DWORD)v9 + 50);
          goto LABEL_33;
        }
        goto LABEL_68;
      }
      Value[0] = 0;
      v20 = 2147483646;
      v43 = 2147483646;
      v21 = (WCHAR *)(v14 + 3);
      v41 = (WCHAR *)(v14 + 3);
      v17 = 260;
      v42 = 260;
      v22 = Value;
      v35 = Value;
      v23 = 0;
      v24 = 0;
      v36 = 0;
      while ( v17 )
      {
        if ( !v20 )
          goto LABEL_41;
        v25 = *v21;
        if ( *v21 == (_WORD)v40 )
          goto LABEL_41;
        v41 = ++v21;
        *v22++ = v25;
        v35 = v22;
        v42 = --v17;
        v43 = --v20;
        v36 = ++v24;
      }
      v35 = --v22;
      v36 = v24 - 1;
      v23 = -2147024774;
LABEL_41:
      *v22 = 0;
      if ( v23 < 0 )
        break;
      if ( RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\Windows Error Reporting\\RuntimeExceptionHelperModules",
             Value,
             0x10u,
             0,
             0,
             0) )
      {
        if ( RegGetValueW(
               HKEY_CURRENT_USER,
               L"Software\\Microsoft\\Windows\\Windows Error Reporting\\RuntimeExceptionHelperModules",
               Value,
               0x10u,
               0,
               0,
               0) )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v19 = 28;
LABEL_33:
            WPP_SF_(v18[2], v19, &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
          }
LABEL_68:
          v11 = v30;
          goto LABEL_69;
        }
        v26 = 1;
        *(_DWORD *)(v16 + 2808) = 1;
      }
      else
      {
        v26 = 2;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          (unsigned int)&WPP_f577d8521c9b39ef05153804ed8add08_Traceguids,
          (unsigned int)Value,
          v26);
      if ( (int)CRuntimePlugin::AskModuleToClaimCrash(v16, Value, v14[2], v47, v46, v45, v44) < 0 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_68;
        v28 = 32;
LABEL_60:
        WPP_SF_S(v27[2], v28, &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids, Value);
        goto LABEL_68;
      }
      if ( *(_DWORD *)(v16 + 2808) )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_68;
        v28 = 31;
        goto LABEL_60;
      }
      v11 = 1;
      v30 = 1;
      v39 = 1;
      *v48 = v14[2];
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids, Value);
LABEL_69:
      operator delete(v14, (const struct std::nothrow_t *)v17);
      v10 = v31;
      v6 = v37;
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v19 = 27;
      goto LABEL_33;
    }
    goto LABEL_68;
  }
  if ( RuntimeDllsListStart != -2147023728 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
  return (unsigned int)-2147023728;
}

```

## disassembly

```asm
0x18002dcdc  push    rbx
0x18002dcde  push    rsi
0x18002dcdf  push    r12
0x18002dce1  push    r15
0x18002dce3  sub     rsp, 318h
0x18002dcea  mov     rax, cs:__security_cookie
0x18002dcf1  xor     rax, rsp
0x18002dcf4  mov     [rsp+338h+var_38], rax
0x18002dcfc  mov     [rsp+338h+var_290], r9
0x18002dd04  mov     [rsp+338h+var_288], r8
0x18002dd0c  mov     [rsp+338h+var_280], rdx
0x18002dd14  mov     r12, rcx
0x18002dd17  mov     [rsp+338h+var_2C8], rcx
0x18002dd1c  mov     rax, [rsp+338h+arg_20]
0x18002dd24  mov     [rsp+338h+var_298], rax
0x18002dd2c  mov     rax, [rsp+338h+arg_28]
0x18002dd34  mov     [rsp+338h+var_278], rax
0x18002dd3c  xor     eax, eax
0x18002dd3e  mov     [rsp+338h+var_2B8], rax
0x18002dd46  mov     [rsp+338h+lpBaseAddress], rax
0x18002dd4b  lea     rdx, [rsp+338h+lpBaseAddress]; struct _WER_RUNTIME_DLL **
0x18002dd50  mov     rcx, [rcx+2F8h]; void *
0x18002dd57  call    ?WerpGetRuntimeDllsListStart@@YAJPEAXPEAPEAU_WER_RUNTIME_DLL@@@Z; WerpGetRuntimeDllsListStart(void *,_WER_RUNTIME_DLL * *)
0x18002dd5c  mov     ebx, eax
0x18002dd5e  mov     eax, 80000000h
0x18002dd63  lea     ecx, [rbx+rax]
0x18002dd66  test    eax, ecx
0x18002dd68  jnz     short loc_18002DDB0
0x18002dd6a  cmp     ebx, 80070490h
0x18002dd70  jz      short loc_18002DDB0
0x18002dd72  lea     rsi, WPP_GLOBAL_Control
0x18002dd79  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dd80  cmp     rcx, rsi
0x18002dd83  jz      loc_18002E331
0x18002dd89  test    byte ptr [rcx+1Ch], 1
0x18002dd8d  jz      loc_18002E331
0x18002dd93  mov     edx, 15h
0x18002dd98  mov     r9d, ebx
0x18002dd9b  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x18002dda2  mov     rcx, [rcx+10h]
0x18002dda6  call    WPP_SF_d
0x18002ddab  jmp     loc_18002E331
0x18002ddb0  mov     r15, [rsp+338h+lpBaseAddress]
0x18002ddb5  xor     r8d, r8d
0x18002ddb8  test    r15, r15
0x18002ddbb  jnz     short loc_18002DE02
0x18002ddbd  cmp     ebx, 80070490h
0x18002ddc3  jz      short loc_18002DDCA
0x18002ddc5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002ddca  lea     rsi, WPP_GLOBAL_Control
0x18002ddd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ddd8  cmp     rcx, rsi
0x18002dddb  jz      short loc_18002DDF8
0x18002dddd  test    byte ptr [rcx+1Ch], 4
0x18002dde1  jz      short loc_18002DDF8
0x18002dde3  mov     edx, 16h
0x18002dde8  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x18002ddef  mov     rcx, [rcx+10h]
0x18002ddf3  call    WPP_SF_
0x18002ddf8  mov     ebx, 80070490h
0x18002ddfd  jmp     loc_18002E331
0x18002de02  mov     edx, r8d
0x18002de05  mov     [rsp+338h+var_2F4], edx
0x18002de09  mov     ebx, r8d
0x18002de0c  mov     [rsp+338h+var_2F8], ebx
0x18002de10  lea     rsi, WPP_GLOBAL_Control
0x18002de17  mov     rcx, cs:WPP_GLOBAL_Control
0x18002de1e  cmp     rcx, rsi
0x18002de21  jz      short loc_18002DE46
0x18002de23  test    byte ptr [rcx+1Ch], 8
0x18002de27  jz      short loc_18002DE46
0x18002de29  mov     edx, 17h
0x18002de2e  mov     r9, r15
0x18002de31  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x18002de38  mov     rcx, [rcx+10h]
0x18002de3c  call    WPP_SF_q
0x18002de41  mov     edx, ebx
0x18002de43  xor     r8d, r8d
0x18002de46  test    ebx, ebx
0x18002de48  jnz     loc_18002DF34
0x18002de4e  test    r15, r15
0x18002de51  jz      loc_18002DF34
0x18002de57  mov     eax, edx
0x18002de59  inc     edx
0x18002de5b  mov     [rsp+338h+var_2F4], edx
0x18002de5f  mov     [rsp+338h+var_2C0], edx
0x18002de63  cmp     eax, 10h
0x18002de66  jnb     loc_18002DF34
0x18002de6c  xorps   xmm0, xmm0
0x18002de6f  xor     eax, eax
0x18002de71  movups  [rsp+338h+Buffer], xmm0
0x18002de79  mov     [rsp+338h+var_258], rax
0x18002de81  mov     [rsp+338h+var_2E0], r8d
0x18002de86  mov     [rsp+338h+NumberOfBytesRead], r8
0x18002de8b  lea     rax, [rsp+338h+NumberOfBytesRead]
0x18002de90  mov     [rsp+338h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18002de95  lea     r9d, [rbx+18h]; nSize
0x18002de99  lea     r8, [rsp+338h+Buffer]; lpBuffer
0x18002dea1  mov     rdx, r15; lpBaseAddress
0x18002dea4  mov     rcx, [r12+2F8h]; hProcess
0x18002deac  call    cs:__imp_ReadProcessMemory
0x18002deb2  xor     ecx, ecx
0x18002deb4  test    eax, eax
0x18002deb6  jz      loc_18002E2C4
0x18002debc  cmp     [rsp+338h+NumberOfBytesRead], 18h
0x18002dec2  jnz     loc_18002E2C4
0x18002dec8  mov     r9d, dword ptr [rsp+338h+Buffer+8]
0x18002ded0  mov     [rsp+338h+var_2E0], r9d
0x18002ded5  lea     eax, [r9-18h]
0x18002ded9  cmp     eax, 208h
0x18002dede  ja      loc_18002E290
0x18002dee4  mov     [rsp+338h+NumberOfBytesRead], rcx
0x18002dee9  mov     ebx, r9d
0x18002deec  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002def3  mov     ecx, r9d; unsigned __int64
0x18002def6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002defb  mov     r12, rax
0x18002defe  mov     [rsp+338h+var_270], rax
0x18002df06  test    rax, rax
0x18002df09  jnz     short loc_18002DF45
0x18002df0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002df12  cmp     rcx, rsi
0x18002df15  jz      short loc_18002DF30
0x18002df17  test    byte ptr [rcx+1Ch], 1
0x18002df1b  jz      short loc_18002DF30
0x18002df1d  lea     edx, [rax+19h]
0x18002df20  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x18002df27  mov     rcx, [rcx+10h]
0x18002df2b  call    WPP_SF_
0x18002df30  mov     ebx, [rsp+338h+var_2F8]
0x18002df34  neg     ebx
0x18002df36  sbb     ebx, ebx
0x18002df38  not     ebx
0x18002df3a  and     ebx, 80004005h
0x18002df40  jmp     loc_18002E331
0x18002df45  lea     rax, [rsp+338h+NumberOfBytesRead]
0x18002df4a  mov     [rsp+338h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18002df4f  mov     r9, rbx; nSize
0x18002df52  mov     r8, r12; lpBuffer
0x18002df55  mov     rdx, r15; lpBaseAddress
0x18002df58  mov     rbx, [rsp+338h+var_2C8]
0x18002df5d  mov     rcx, [rbx+2F8h]; hProcess
0x18002df64  call    cs:__imp_ReadProcessMemory
0x18002df6a  xor     r10d, r10d
0x18002df6d  test    eax, eax
0x18002df6f  jz      loc_18002E26B
0x18002df75  mov     r15, [r12]
0x18002df79  mov     [rsp+338h+lpBaseAddress], r15
0x18002df7e  lea     rax, [r15+18h]
0x18002df82  test    rax, rax
0x18002df85  jnz     short loc_18002DFB9
0x18002df87  mov     rcx, cs:WPP_GLOBAL_Control
0x18002df8e  cmp     rcx, rsi
0x18002df91  jz      loc_18002E273
0x18002df97  test    byte ptr [rcx+1Ch], 1
0x18002df9b  jz      loc_18002E273
0x18002dfa1  lea     edx, [rax+1Ah]
0x18002dfa4  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x18002dfab  mov     rcx, [rcx+10h]
0x18002dfaf  call    WPP_SF_
0x18002dfb4  jmp     loc_18002E273
0x18002dfb9  mov     [rsp+338h+Value], r10w
0x18002dfc2  mov     r8d, 7FFFFFFEh
0x18002dfc8  mov     [rsp+338h+var_2A0], r8
0x18002dfd0  lea     r9, [r12+18h]
0x18002dfd5  mov     [rsp+338h+var_2B0], r9
0x18002dfdd  mov     edx, 104h
0x18002dfe2  mov     [rsp+338h+var_2A8], rdx
0x18002dfea  lea     rcx, [rsp+338h+Value]
0x18002dff2  mov     [rsp+338h+var_2D8], rcx
0x18002dff7  mov     r11d, r10d
0x18002dffa  mov     rax, r10
0x18002dffd  mov     [rsp+338h+var_2D0], rax
0x18002e002  test    rdx, rdx
0x18002e005  jz      short loc_18002E05F
0x18002e007  test    r8, r8
0x18002e00a  jz      short loc_18002E05A
0x18002e00c  movzx   r10d, word ptr [r9]
0x18002e010  cmp     r10w, word ptr [rsp+338h+var_2B8]
0x18002e019  jz      short loc_18002E057
0x18002e01b  add     r9, 2
0x18002e01f  mov     [rsp+338h+var_2B0], r9
0x18002e027  mov     [rcx], r10w
0x18002e02b  add     rcx, 2
0x18002e02f  mov     [rsp+338h+var_2D8], rcx
0x18002e034  dec     rdx
0x18002e037  mov     [rsp+338h+var_2A8], rdx
0x18002e03f  dec     r8
0x18002e042  mov     [rsp+338h+var_2A0], r8
0x18002e04a  inc     rax
0x18002e04d  mov     [rsp+338h+var_2D0], rax
0x18002e052  xor     r10d, r10d
0x18002e055  jmp     short loc_18002E002
0x18002e057  xor     r10d, r10d
0x18002e05a  test    rdx, rdx
0x18002e05d  jnz     short loc_18002E076
0x18002e05f  sub     rcx, 2
0x18002e063  mov     [rsp+338h+var_2D8], rcx
0x18002e068  dec     rax
0x18002e06b  mov     [rsp+338h+var_2D0], rax
0x18002e070  mov     r11d, 8007007Ah
0x18002e076  mov     eax, r10d
0x18002e079  mov     [rcx], ax
0x18002e07c  test    r11d, r11d
0x18002e07f  jns     short loc_18002E0A5
0x18002e081  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e088  cmp     rcx, rsi
0x18002e08b  jz      loc_18002E273
0x18002e091  test    byte ptr [rcx+1Ch], 1
0x18002e095  jz      loc_18002E273
0x18002e09b  mov     edx, 1Bh
0x18002e0a0  jmp     loc_18002DFA4
0x18002e0a5  mov     [rsp+338h+pcbData], r10; pcbData
0x18002e0aa  mov     [rsp+338h+pvData], r10; pvData
0x18002e0af  mov     [rsp+338h+lpNumberOfBytesRead], r10; pdwType
0x18002e0b4  mov     r9d, 10h; dwFlags
0x18002e0ba  lea     r8, [rsp+338h+Value]; lpValue
0x18002e0c2  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\Windows E"...
0x18002e0c9  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002e0d0  call    cs:__imp_RegGetValueW
0x18002e0d6  xor     r10d, r10d
0x18002e0d9  test    eax, eax
0x18002e0db  jnz     short loc_18002E0E3
0x18002e0dd  lea     eax, [r10+2]
0x18002e0e1  jmp     short loc_18002E127
0x18002e0e3  mov     [rsp+338h+pcbData], r10; pcbData
0x18002e0e8  mov     [rsp+338h+pvData], r10; pvData
0x18002e0ed  mov     [rsp+338h+lpNumberOfBytesRead], r10; pdwType
0x18002e0f2  mov     r9d, 10h; dwFlags
0x18002e0f8  lea     r8, [rsp+338h+Value]; lpValue
0x18002e100  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\Windows E"...
0x18002e107  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18002e10e  call    cs:__imp_RegGetValueW
0x18002e114  test    eax, eax
0x18002e116  jnz     loc_18002E24F
0x18002e11c  mov     eax, 1
0x18002e121  mov     [rbx+0AF8h], eax
0x18002e127  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e12e  cmp     rcx, rsi
0x18002e131  jz      short loc_18002E15A
0x18002e133  test    byte ptr [rcx+1Ch], 8
0x18002e137  jz      short loc_18002E15A
0x18002e139  mov     edx, 1Dh
0x18002e13e  mov     dword ptr [rsp+338h+lpNumberOfBytesRead], eax
0x18002e142  lea     r9, [rsp+338h+Value]
0x18002e14a  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x18002e151  mov     rcx, [rcx+10h]
0x18002e155  call    WPP_SF_Sd
0x18002e15a  mov     rax, [rsp+338h+var_298]
0x18002e162  mov     [rsp+338h+pcbData], rax
0x18002e167  mov     rax, [rsp+338h+var_290]
0x18002e16f  mov     [rsp+338h+pvData], rax
0x18002e174  mov     rax, [rsp+338h+var_288]
0x18002e17c  mov     [rsp+338h+lpNumberOfBytesRead], rax
0x18002e181  mov     r9, [rsp+338h+var_280]
0x18002e189  mov     r8, [r12+10h]
0x18002e18e  lea     rdx, [rsp+338h+Value]
0x18002e196  mov     rcx, rbx
0x18002e199  call    ?AskModuleToClaimCrash@CRuntimePlugin@@AEAAJPEB_WPEAXPEAKPEAP6AJ1QEAU_WER_RUNTIME_EXCEPTION_INFORMATION@@KPEA_W242@ZPEAP6AJ13PEAH426@ZPEAV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@@Z; CRuntimePlugin::AskModuleToClaimCrash(wchar_t const *,void *,ulong *,long (**)(void *,_WER_RUNTIME_EXCEPTION_INFORMATION * const,ulong,wchar_t *,ulong *,wchar_t *,ulong *),long (**)(void *,_WER_RUNTIME_EXCEPTION_INFORMATION * const,int *,wchar_t *,ulong *,int *),tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> *)
0x18002e19e  xor     r10d, r10d
0x18002e1a1  test    eax, eax
0x18002e1a3  js      loc_18002E236
0x18002e1a9  cmp     [rbx+0AF8h], r10d
0x18002e1b0  jnz     short loc_18002E205
0x18002e1b2  lea     ebx, [r10+1]
0x18002e1b6  mov     [rsp+338h+var_2F8], ebx
0x18002e1ba  mov     [rsp+338h+var_2BC], ebx
0x18002e1be  mov     rax, [r12+10h]
0x18002e1c3  mov     rcx, [rsp+338h+var_278]
0x18002e1cb  mov     [rcx], rax
0x18002e1ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e1d5  cmp     rcx, rsi
0x18002e1d8  jz      loc_18002E277
0x18002e1de  test    byte ptr [rcx+1Ch], 8
0x18002e1e2  jz      loc_18002E277
0x18002e1e8  lea     edx, [rbx+1Dh]
0x18002e1eb  lea     r9, [rsp+338h+Value]
0x18002e1f3  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x18002e1fa  mov     rcx, [rcx+10h]
0x18002e1fe  call    WPP_SF_S
0x18002e203  jmp     short loc_18002E277
0x18002e205  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e20c  cmp     rcx, rsi
0x18002e20f  jz      short loc_18002E273
0x18002e211  test    byte ptr [rcx+1Ch], 8
0x18002e215  jz      short loc_18002E273
0x18002e217  mov     edx, 1Fh
0x18002e21c  lea     r9, [rsp+338h+Value]
0x18002e224  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x18002e22b  mov     rcx, [rcx+10h]
0x18002e22f  call    WPP_SF_S
0x18002e234  jmp     short loc_18002E273
0x18002e236  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e23d  cmp     rcx, rsi
0x18002e240  jz      short loc_18002E273
0x18002e242  test    byte ptr [rcx+1Ch], 8
0x18002e246  jz      short loc_18002E273
0x18002e248  mov     edx, 20h ; ' '
0x18002e24d  jmp     short loc_18002E21C
0x18002e24f  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
