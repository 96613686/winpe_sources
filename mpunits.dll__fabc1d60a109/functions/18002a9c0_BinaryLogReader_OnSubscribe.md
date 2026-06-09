# BinaryLogReader_OnSubscribe

- ea: `0x18002a9c0`
- end: `0x18002adc3`
- name: `BinaryLogReader_OnSubscribe`
- size: `1027`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180006e64`
- `0x180006ef8`
- `0x18000ab88`
- `0x18000ac44`
- `0x18000af38`
- `0x180026440`
- `0x18002677c`
- `0x18002906c`
- `0x180029cc4`
- `0x18002a9c0`
- `0x18002d8a0`
- `0x180042c5c`
- `0x180044836`
- `0x180044842`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `msvcrt!malloc` at `0x18002aa79`
- `msvcrt!malloc` at `0x18002ad03`
- `msvcrt!malloc` at `0x18002aa79`
- `msvcrt!malloc` at `0x18002ad03`
- `msvcrt!_close` at `0x18002aad2`
- `msvcrt!_close` at `0x18002aad2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002abac`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002ac82`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002abac`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002ac82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad7e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002abf9`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002abf9`

## string_xrefs

- `0x18002ab94`: `mpunits.dll`
- `0x18002ac08`: `MSFT DSC CU BINARY-LOG-READER`
- `0x18002ac37`: `FAILED-TO-OPEN-FILE`
- `0x18002abde`: `BinaryLogReader`
- `0x18002aca4`: `BinaryLogReader`

## pseudocode

```c
__int64 __fastcall BinaryLogReader_OnSubscribe(__int64 a1, __int64 a2)
{
  __int64 v3; // rsi
  unsigned int ClassesFromMOF; // ebx
  wchar_t *v5; // rcx
  _QWORD *v6; // rax
  int v7; // ecx
  int v9; // eax
  __int64 v10; // r8
  wchar_t *v11; // rdx
  wchar_t *v12; // rcx
  unsigned int LogFilesNames; // eax
  __int64 v14; // rdi
  HMODULE v15; // rax
  void *v16; // rbx
  HMODULE ModuleHandleA; // rax
  int String_LoadString; // eax
  unsigned int v19; // eax
  unsigned int v20; // r14d
  void *v21; // rax
  char v22; // al
  __int64 v23; // rdi
  MI_Instance *extendedError; // [rsp+30h] [rbp-30h] BYREF
  __int64 v25; // [rsp+38h] [rbp-28h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-20h] BYREF

  extendedError = 0;
  v25 = 0;
  if ( (unsigned int)s_observerProtocolFT(
                       a2,
                       (int)BinaryLogReader_Operation_OnCancel,
                       (int)BinaryLogReader_Operation_OnDestroy,
                       (int)&v25,
                       160) )
    return 0;
  v3 = v25 + 152;
  memset_0((void *)(v25 + 152), 0, 0xA0u);
  ClassesFromMOF = BinaryLogReader_Core_Init(v3);
  if ( ClassesFromMOF || (v5 = *(wchar_t **)(a1 + 56)) != 0 && (ClassesFromMOF = ReadClassesFromMOF(v5)) != 0 )
  {
LABEL_7:
    *(_DWORD *)&EventDescriptor.Id = 217;
    *(_DWORD *)&EventDescriptor.Level = 4;
    EventDescriptor.Keyword = 1;
    Etw_Trace0(&EventDescriptor);
    v7 = *(_DWORD *)(v3 + 4);
    if ( v7 != -1 )
    {
      _close(v7);
      *(_DWORD *)(v3 + 4) = -1;
      trace_BinLogWriter_ClosedLogFile();
    }
    ((void (__fastcall *)(__int64, _QWORD, MI_Instance *))ObserverProtocol_PostError)(
      v25,
      ClassesFromMOF,
      extendedError);
    if ( extendedError )
    {
      if ( extendedError->ft )
        ((void (*)(void))extendedError->ft->Delete)();
    }
    ((void (__fastcall *)(__int64))ObserverProtocol_Release)(v25);
    return 0;
  }
  v6 = malloc(0x18u);
  *(_QWORD *)(v3 + 152) = v6;
  if ( !v6 )
  {
    *(_DWORD *)&EventDescriptor.Id = 203;
    *(_DWORD *)&EventDescriptor.Level = 4;
    EventDescriptor.Keyword = 1;
    Etw_Trace0(&EventDescriptor);
    ClassesFromMOF = 27;
    goto LABEL_7;
  }
  *(_OWORD *)v6 = 0;
  v6[2] = 0;
  v9 = *(_DWORD *)(a1 + 64);
  v10 = *(_QWORD *)(v3 + 152);
  *(_DWORD *)v3 = v9;
  v11 = *(wchar_t **)(a1 + 48);
  v12 = *(wchar_t **)(a1 + 40);
  if ( (v9 & 2) != 0 )
    LogFilesNames = SetOneFileName(v12, v11);
  else
    LogFilesNames = GetLogFilesNames(v12, v11, v10);
  ClassesFromMOF = LogFilesNames;
  if ( LogFilesNames )
  {
    if ( **(_DWORD **)(v3 + 152) )
    {
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      String_LoadString = Intlstr_GetString_LoadString(ModuleHandleA, 2011);
      CreateOMIError_shared(String_LoadString, 5, (int)L"BinaryLogReader", 8, (__int64)&OMI_Error_rtti, &extendedError);
      *(_DWORD *)&EventDescriptor.Id = 205;
      *(_DWORD *)&EventDescriptor.Level = 4;
      EventDescriptor.Keyword = 1;
      Etw_Trace0(&EventDescriptor);
    }
    else
    {
      v14 = *(_QWORD *)(a1 + 48);
      v15 = GetModuleHandleA("mpunits.dll");
      v16 = (void *)Intlstr_FormatString_FormatMessage(v15, 2010, v14);
      CreateOMIError_shared((int)v16, 4, (int)L"BinaryLogReader", 5, (__int64)&OMI_Error_rtti, &extendedError);
      LocalFree(v16);
      if ( extendedError )
      {
        *(_QWORD *)&EventDescriptor.Id = L"MSFT DSC CU BINARY-LOG-READER";
        ((void (__fastcall *)(MI_Instance *, __int64, EVENT_DESCRIPTOR *, __int64, _DWORD))extendedError->ft->SetElementAt)(
          extendedError,
          2,
          &EventDescriptor,
          13,
          0);
        *(_QWORD *)&EventDescriptor.Id = L"FAILED-TO-OPEN-FILE";
        ((void (__fastcall *)(MI_Instance *, __int64, EVENT_DESCRIPTOR *, __int64, _DWORD))extendedError->ft->SetElementAt)(
          extendedError,
          3,
          &EventDescriptor,
          13,
          0);
      }
      *(_DWORD *)&EventDescriptor.Id = 204;
      *(_DWORD *)&EventDescriptor.Level = 4;
      EventDescriptor.Keyword = 1;
      Etw_Trace0(&EventDescriptor);
      ClassesFromMOF = 4;
    }
    goto LABEL_7;
  }
  *(_QWORD *)(v3 + 112) = v25;
  *(_BYTE *)(v3 + 136) = 0;
  if ( *(_QWORD *)(a1 + 72) )
  {
    v19 = *(_DWORD *)(a1 + 80);
    *(_DWORD *)(v3 + 96) = v19;
    v20 = v19;
    v21 = malloc(v19);
    *(_QWORD *)(v3 + 88) = v21;
    if ( !v21 )
      goto LABEL_7;
    memcpy_0(v21, *(const void **)(a1 + 72), v20);
    v22 = 0;
  }
  else
  {
    v22 = 1;
  }
  *(_BYTE *)(v3 + 104) = v22;
  *(_QWORD *)(v3 + 144) = 0;
  v23 = ((__int64 (__fastcall *)(__int64))ObserverProtocol_GetDisposable)(v25);
  ClassesFromMOF = RxcScheduler_Schedule(
                     0,
                     (unsigned int)ReadLogFiles,
                     (unsigned int)ObserverProtocol_Release,
                     v25,
                     0,
                     v3 + 144);
  if ( ClassesFromMOF )
  {
    GetLastError();
    *(_DWORD *)&EventDescriptor.Id = 216;
    *(_DWORD *)&EventDescriptor.Level = 4;
    EventDescriptor.Keyword = 1;
    Etw_Trace1_int(&EventDescriptor);
    if ( v23 )
      (*(void (__fastcall **)(_QWORD))(v23 + 24))(*(_QWORD *)v23);
    goto LABEL_7;
  }
  return v23;
}

```

## disassembly

```asm
0x18002a9c0  mov     [rsp-28h+arg_10], rbx
0x18002a9c5  mov     [rsp-28h+arg_18], rsi
0x18002a9ca  push    rbp
0x18002a9cb  push    rdi
0x18002a9cc  push    r13
0x18002a9ce  push    r14
0x18002a9d0  push    r15
0x18002a9d2  mov     rbp, rsp
0x18002a9d5  sub     rsp, 60h
0x18002a9d9  mov     rax, cs:__security_cookie
0x18002a9e0  xor     rax, rsp
0x18002a9e3  mov     [rbp+var_10], rax
0x18002a9e7  mov     rax, cs:off_180047BB0
0x18002a9ee  lea     r9, [rbp+var_28]
0x18002a9f2  mov     r10, rdx
0x18002a9f5  lea     r8, BinaryLogReader_Operation_OnDestroy
0x18002a9fc  xor     r15d, r15d
0x18002a9ff  lea     rdx, BinaryLogReader_Operation_OnCancel
0x18002aa06  mov     rdi, rcx
0x18002aa09  mov     [rbp+var_30], r15
0x18002aa0d  mov     [rbp+var_28], r15
0x18002aa11  mov     ebx, 0A0h
0x18002aa16  mov     rax, [rax]
0x18002aa19  mov     rcx, r10
0x18002aa1c  mov     [rsp+60h+var_40], rbx
0x18002aa21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa26  test    eax, eax
0x18002aa28  jnz     loc_18002AB2C
0x18002aa2e  mov     rsi, [rbp+var_28]
0x18002aa32  mov     r8d, ebx; Size
0x18002aa35  add     rsi, 98h
0x18002aa3c  xor     edx, edx; Val
0x18002aa3e  mov     rcx, rsi; void *
0x18002aa41  call    memset_0
0x18002aa46  mov     rcx, rsi
0x18002aa49  call    BinaryLogReader_Core_Init
0x18002aa4e  lea     r13d, [r15+1]
0x18002aa52  mov     ebx, eax
0x18002aa54  test    eax, eax
0x18002aa56  jnz     short loc_18002AAAF
0x18002aa58  mov     rcx, [rdi+38h]; FileName
0x18002aa5c  test    rcx, rcx
0x18002aa5f  jz      short loc_18002AA74
0x18002aa61  lea     rdx, [rsi+48h]
0x18002aa65  lea     r8, [rbp+var_30]
0x18002aa69  call    ReadClassesFromMOF
0x18002aa6e  mov     ebx, eax
0x18002aa70  test    eax, eax
0x18002aa72  jnz     short loc_18002AAAF
0x18002aa74  mov     ecx, 18h; Size
0x18002aa79  call    cs:__imp_malloc
0x18002aa7f  mov     [rsi+98h], rax
0x18002aa86  test    rax, rax
0x18002aa89  jnz     loc_18002AB53
0x18002aa8f  lea     rcx, [rbp+EventDescriptor]
0x18002aa93  mov     dword ptr [rbp+EventDescriptor.Id], 0CBh
0x18002aa9a  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x18002aaa1  mov     [rbp+EventDescriptor.Keyword], r13
0x18002aaa5  call    Etw_Trace0
0x18002aaaa  mov     ebx, 1Bh
0x18002aaaf  lea     rcx, [rbp+EventDescriptor]
0x18002aab3  mov     dword ptr [rbp+EventDescriptor.Id], 0D9h
0x18002aaba  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x18002aac1  mov     [rbp+EventDescriptor.Keyword], r13
0x18002aac5  call    Etw_Trace0
0x18002aaca  mov     ecx, [rsi+4]; FileHandle
0x18002aacd  cmp     ecx, 0FFFFFFFFh
0x18002aad0  jz      short loc_18002AAE4
0x18002aad2  call    cs:__imp__close
0x18002aad8  mov     dword ptr [rsi+4], 0FFFFFFFFh
0x18002aadf  call    trace_BinLogWriter_ClosedLogFile
0x18002aae4  mov     rax, cs:off_180047BB0
0x18002aaeb  mov     edx, ebx
0x18002aaed  mov     r8, [rbp+var_30]
0x18002aaf1  mov     rcx, [rbp+var_28]
0x18002aaf5  mov     rax, [rax+50h]
0x18002aaf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aafe  mov     rcx, [rbp+var_30]
0x18002ab02  test    rcx, rcx
0x18002ab05  jz      short loc_18002AB18
0x18002ab07  mov     rax, [rcx]
0x18002ab0a  test    rax, rax
0x18002ab0d  jz      short loc_18002AB18
0x18002ab0f  mov     rax, [rax+10h]
0x18002ab13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab18  mov     rax, cs:off_180047BB0
0x18002ab1f  mov     rcx, [rbp+var_28]
0x18002ab23  mov     rax, [rax+10h]
0x18002ab27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab2c  xor     eax, eax
0x18002ab2e  mov     rcx, [rbp+var_10]
0x18002ab32  xor     rcx, rsp; StackCookie
0x18002ab35  call    __security_check_cookie
0x18002ab3a  lea     r11, [rsp+60h+var_s0]
0x18002ab3f  mov     rbx, [r11+40h]
0x18002ab43  mov     rsi, [r11+48h]
0x18002ab47  mov     rsp, r11
0x18002ab4a  pop     r15
0x18002ab4c  pop     r14
0x18002ab4e  pop     r13
0x18002ab50  pop     rdi
0x18002ab51  pop     rbp
0x18002ab52  retn
0x18002ab53  xor     ecx, ecx
0x18002ab55  xorps   xmm0, xmm0
0x18002ab58  movups  xmmword ptr [rax], xmm0
0x18002ab5b  mov     [rax+10h], rcx
0x18002ab5f  mov     eax, [rdi+40h]
0x18002ab62  mov     r8, [rsi+98h]
0x18002ab69  mov     [rsi], eax
0x18002ab6b  mov     rdx, [rdi+30h]; String
0x18002ab6f  mov     rcx, [rdi+28h]; Source
0x18002ab73  test    al, 2
0x18002ab75  jz      short loc_18002AB7E
0x18002ab77  call    SetOneFileName
0x18002ab7c  jmp     short loc_18002AB83
0x18002ab7e  call    GetLogFilesNames
0x18002ab83  mov     ebx, eax
0x18002ab85  test    eax, eax
0x18002ab87  jz      loc_18002ACE3
0x18002ab8d  mov     rax, [rsi+98h]
0x18002ab94  lea     rcx, ModuleName; "mpunits.dll"
0x18002ab9b  cmp     [rax], r15d
0x18002ab9e  jnz     loc_18002AC82
0x18002aba4  mov     rbx, [rdi+28h]
0x18002aba8  mov     rdi, [rdi+30h]
0x18002abac  call    cs:__imp_GetModuleHandleA
0x18002abb2  mov     r9, rbx
0x18002abb5  mov     r8, rdi
0x18002abb8  mov     rcx, rax
0x18002abbb  mov     edx, 7DAh
0x18002abc0  call    _Intlstr_FormatString_FormatMessage
0x18002abc5  mov     rbx, rax
0x18002abc8  lea     rcx, OMI_Error_rtti
0x18002abcf  mov     r9d, 5; int
0x18002abd5  lea     rax, [rbp+var_30]
0x18002abd9  mov     [rsp+60h+extendedError], rax; extendedError
0x18002abde  lea     r8, aBinarylogreade_1; "BinaryLogReader"
0x18002abe5  mov     [rsp+60h+var_40], rcx; __int64
0x18002abea  mov     rcx, rbx; int
0x18002abed  lea     edx, [r9-1]; int
0x18002abf1  call    CreateOMIError_shared
0x18002abf6  mov     rcx, rbx; hMem
0x18002abf9  call    cs:__imp_LocalFree
0x18002abff  mov     rcx, [rbp+var_30]
0x18002ac03  test    rcx, rcx
0x18002ac06  jz      short loc_18002AC5D
0x18002ac08  lea     rax, aMsftDscCuBinar_0; "MSFT DSC CU BINARY-LOG-READER"
0x18002ac0f  mov     dword ptr [rsp+60h+var_40], r15d
0x18002ac14  mov     qword ptr [rbp+EventDescriptor.Id], rax
0x18002ac18  lea     r8, [rbp+EventDescriptor]
0x18002ac1c  mov     rax, [rcx]
0x18002ac1f  mov     ebx, 0Dh
0x18002ac24  mov     r9d, ebx
0x18002ac27  mov     rax, [rax+50h]
0x18002ac2b  lea     edx, [rbx-0Bh]
0x18002ac2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac33  mov     rcx, [rbp+var_30]
0x18002ac37  lea     rax, aFailedToOpenFi; "FAILED-TO-OPEN-FILE"
0x18002ac3e  mov     qword ptr [rbp+EventDescriptor.Id], rax
0x18002ac42  lea     r8, [rbp+EventDescriptor]
0x18002ac46  mov     r9d, ebx
0x18002ac49  mov     dword ptr [rsp+60h+var_40], r15d
0x18002ac4e  lea     edx, [rbx-0Ah]
0x18002ac51  mov     rax, [rcx]
0x18002ac54  mov     rax, [rax+50h]
0x18002ac58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac5d  lea     rcx, [rbp+EventDescriptor]
0x18002ac61  mov     dword ptr [rbp+EventDescriptor.Id], 0CCh
0x18002ac68  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x18002ac6f  mov     [rbp+EventDescriptor.Keyword], r13
0x18002ac73  call    Etw_Trace0
0x18002ac78  mov     ebx, 4
0x18002ac7d  jmp     loc_18002AAAF
0x18002ac82  call    cs:__imp_GetModuleHandleA
0x18002ac88  mov     rcx, rax
0x18002ac8b  mov     edx, 7DBh
0x18002ac90  call    _Intlstr_GetString_LoadString
0x18002ac95  lea     rcx, [rbp+var_30]
0x18002ac99  mov     r9d, 8; int
0x18002ac9f  mov     [rsp+60h+extendedError], rcx; extendedError
0x18002aca4  lea     r8, aBinarylogreade_1; "BinaryLogReader"
0x18002acab  lea     rcx, OMI_Error_rtti
0x18002acb2  mov     [rsp+60h+var_40], rcx; __int64
0x18002acb7  mov     rcx, rax; int
0x18002acba  lea     edx, [r9-3]; int
0x18002acbe  call    CreateOMIError_shared
0x18002acc3  lea     rcx, [rbp+EventDescriptor]
0x18002acc7  mov     dword ptr [rbp+EventDescriptor.Id], 0CDh
0x18002acce  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x18002acd5  mov     [rbp+EventDescriptor.Keyword], r13
0x18002acd9  call    Etw_Trace0
0x18002acde  jmp     loc_18002AAAF
0x18002ace3  mov     rax, [rbp+var_28]
0x18002ace7  mov     [rsi+70h], rax
0x18002aceb  mov     [rsi+88h], r15b
0x18002acf2  cmp     [rdi+48h], r15
0x18002acf6  jz      short loc_18002AD2A
0x18002acf8  mov     eax, [rdi+50h]
0x18002acfb  mov     ecx, eax; Size
0x18002acfd  mov     [rsi+60h], eax
0x18002ad00  mov     r14d, eax
0x18002ad03  call    cs:__imp_malloc
0x18002ad09  mov     [rsi+58h], rax
0x18002ad0d  test    rax, rax
0x18002ad10  jz      loc_18002AAAF
0x18002ad16  mov     rdx, [rdi+48h]; Src
0x18002ad1a  mov     r8d, r14d; Size
0x18002ad1d  mov     rcx, rax; void *
0x18002ad20  call    memcpy_0
0x18002ad25  mov     al, r15b
0x18002ad28  jmp     short loc_18002AD2D
0x18002ad2a  mov     al, r13b
0x18002ad2d  mov     [rsi+68h], al
0x18002ad30  lea     rbx, [rsi+90h]
0x18002ad37  mov     [rbx], r15
0x18002ad3a  mov     rax, cs:off_180047BB0
0x18002ad41  mov     rcx, [rbp+var_28]
0x18002ad45  mov     rax, [rax+18h]
0x18002ad49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad4e  mov     r8, cs:off_180047BB0
0x18002ad55  lea     rdx, ReadLogFiles
0x18002ad5c  mov     r9, [rbp+var_28]
0x18002ad60  xor     ecx, ecx
0x18002ad62  mov     [rsp+60h+extendedError], rbx
0x18002ad67  mov     rdi, rax
0x18002ad6a  mov     [rsp+60h+var_40], r15
0x18002ad6f  mov     r8, [r8+10h]
0x18002ad73  call    RxcScheduler_Schedule
0x18002ad78  mov     ebx, eax
0x18002ad7a  test    eax, eax
0x18002ad7c  jz      short loc_18002ADBB
0x18002ad7e  call    cs:__imp_GetLastError
0x18002ad84  lea     rcx, [rbp+EventDescriptor]; EventDescriptor
0x18002ad88  mov     dword ptr [rbp+EventDescriptor.Id], 0D8h
0x18002ad8f  mov     edx, eax
0x18002ad91  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x18002ad98  mov     [rbp+EventDescriptor.Keyword], r13
0x18002ad9c  call    Etw_Trace1_int
0x18002ada1  test    rdi, rdi
0x18002ada4  jz      loc_18002AAAF
0x18002adaa  mov     rcx, [rdi]
0x18002adad  mov     rax, [rdi+18h]
0x18002adb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002adb6  jmp     loc_18002AAAF
0x18002adbb  mov     rax, rdi
0x18002adbe  jmp     loc_18002AB2E
```
