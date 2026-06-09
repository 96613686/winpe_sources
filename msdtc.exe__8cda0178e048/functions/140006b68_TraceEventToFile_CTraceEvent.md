# TraceEventToFile(CTraceEvent &)

- ea: `0x140006b68`
- end: `0x140006d1a`
- name: `?TraceEventToFile@@YAXAEAVCTraceEvent@@@Z`
- size: `434`
- prototype: `void __fastcall(struct CTraceEvent *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140005a4c`

## callees

- `0x1400027a4`
- `0x140006a7c`
- `0x140006b68`
- `0x140006f10`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006bdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006c73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006bdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006c73`
- `msvcrt!fflush` at `0x140006cd9`
- `msvcrt!fflush` at `0x140006cd9`
- `msvcrt!fclose` at `0x140006ce2`
- `msvcrt!fclose` at `0x140006ce2`
- `msvcrt!fwprintf` at `0x140006cd0`
- `msvcrt!fwprintf` at `0x140006cd0`
- `msvcrt!_wfopen` at `0x140006c5b`
- `msvcrt!_wfopen` at `0x140006c5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140006bec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140006c20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140006bec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140006c20`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006b96`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006b96`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006cef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006cef`

## pseudocode

```c
void __fastcall TraceEventToFile(struct CTraceEvent *a1)
{
  void *v2; // rbx
  int ImageName; // eax
  FILE *v4; // rdi
  int v5; // eax
  __int64 v6; // [rsp+20h] [rbp-438h]
  DWORD CurrentProcessId; // [rsp+28h] [rbp-430h]
  LPVOID pv[2]; // [rsp+30h] [rbp-428h] BYREF
  _BYTE v9[1024]; // [rsp+40h] [rbp-418h] BYREF

  EnterCriticalSection(&stru_140010720);
  v2 = 0;
  pv[0] = 0;
  if ( !TraceOutputSettings::TraceFilePath )
    goto LABEL_19;
  if ( !byte_14000E318 )
    goto LABEL_10;
  if ( TraceOutputSettings::ImageNameInTraceFileNameEnabled )
  {
    ImageName = GetImageName((unsigned __int16 **)pv);
    v2 = pv[0];
    if ( ImageName < 0 )
    {
      if ( !pv[0] )
        goto LABEL_9;
      CoTaskMemFree(pv[0]);
      v2 = 0;
    }
  }
  if ( v2 )
  {
    CurrentProcessId = GetCurrentProcessId();
    if ( (int)StringCbPrintfW(
                &word_1400107D0,
                0x20Au,
                L"%s\\MSDTC-%s-%d.log",
                TraceOutputSettings::TraceFilePath,
                v2,
                CurrentProcessId) >= 0 )
      goto LABEL_10;
  }
LABEL_9:
  v4 = 0;
  LODWORD(v6) = GetCurrentProcessId();
  if ( (int)StringCbPrintfW(&word_1400107D0, 0x20Au, L"%s\\MSDTC-%d.log", TraceOutputSettings::TraceFilePath, v6) >= 0 )
  {
LABEL_10:
    v4 = _wfopen(&word_1400107D0, L"a+");
    byte_14000E318 = 0;
  }
  if ( v2 )
    CoTaskMemFree(v2);
  if ( v4 )
  {
    pv[0] = v9;
    v5 = (*(__int64 (__fastcall **)(struct CTraceEvent *, _BYTE *, __int64))(*(_QWORD *)a1 + 16LL))(a1, v9, 512);
    if ( v5 == -2147024774 )
      v5 = (*(__int64 (__fastcall **)(struct CTraceEvent *, LPVOID *))(*(_QWORD *)a1 + 8LL))(a1, pv);
    if ( v5 >= 0 )
    {
      fwprintf(v4, L"%s\n", pv[0]);
      fflush(v4);
    }
    fclose(v4);
  }
LABEL_19:
  LeaveCriticalSection(&stru_140010720);
}

```

## disassembly

```asm
0x140006b68  mov     [rsp+arg_8], rbx
0x140006b6d  mov     [rsp+arg_10], rsi
0x140006b72  push    rdi
0x140006b73  sub     rsp, 450h
0x140006b7a  mov     rax, cs:__security_cookie
0x140006b81  xor     rax, rsp
0x140006b84  mov     [rsp+458h+var_18], rax
0x140006b8c  mov     rsi, rcx
0x140006b8f  lea     rcx, stru_140010720; lpCriticalSection
0x140006b96  call    cs:__imp_EnterCriticalSection
0x140006b9c  xor     ebx, ebx
0x140006b9e  cmp     cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA, rbx; ushort * TraceOutputSettings::TraceFilePath
0x140006ba5  mov     [rsp+458h+pv], rbx
0x140006baa  jz      loc_140006CE8
0x140006bb0  cmp     cs:byte_14000E318, bl
0x140006bb6  jz      loc_140006C4D
0x140006bbc  cmp     cs:?ImageNameInTraceFileNameEnabled@TraceOutputSettings@@2_NA, bl; bool TraceOutputSettings::ImageNameInTraceFileNameEnabled
0x140006bc2  jz      short loc_140006BE7
0x140006bc4  lea     rcx, [rsp+458h+pv]; unsigned __int16 **
0x140006bc9  call    ?GetImageName@@YAJPEAPEAG@Z; GetImageName(ushort * *)
0x140006bce  mov     rbx, [rsp+458h+pv]
0x140006bd3  test    eax, eax
0x140006bd5  jns     short loc_140006BE7
0x140006bd7  test    rbx, rbx
0x140006bda  jz      short loc_140006C1E
0x140006bdc  mov     rcx, rbx; pv
0x140006bdf  call    cs:__imp_CoTaskMemFree
0x140006be5  xor     ebx, ebx
0x140006be7  test    rbx, rbx
0x140006bea  jz      short loc_140006C1E
0x140006bec  call    cs:__imp_GetCurrentProcessId
0x140006bf2  mov     r9, cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA; ushort * TraceOutputSettings::TraceFilePath
0x140006bf9  lea     r8, aSMsdtcSDLog; "%s\\MSDTC-%s-%d.log"
0x140006c00  mov     [rsp+458h+var_430], eax
0x140006c04  lea     rcx, word_1400107D0; unsigned __int16 *
0x140006c0b  mov     edx, 20Ah; unsigned __int64
0x140006c10  mov     [rsp+458h+var_438], rbx
0x140006c15  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140006c1a  test    eax, eax
0x140006c1c  jns     short loc_140006C4D
0x140006c1e  xor     edi, edi
0x140006c20  call    cs:__imp_GetCurrentProcessId
0x140006c26  mov     r9, cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA; ushort * TraceOutputSettings::TraceFilePath
0x140006c2d  lea     r8, aSMsdtcDLog; "%s\\MSDTC-%d.log"
0x140006c34  mov     edx, 20Ah; unsigned __int64
0x140006c39  mov     dword ptr [rsp+458h+var_438], eax
0x140006c3d  lea     rcx, word_1400107D0; unsigned __int16 *
0x140006c44  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140006c49  test    eax, eax
0x140006c4b  js      short loc_140006C6B
0x140006c4d  lea     rdx, aA; "a+"
0x140006c54  lea     rcx, word_1400107D0; FileName
0x140006c5b  call    cs:__imp__wfopen
0x140006c61  mov     rdi, rax
0x140006c64  mov     cs:byte_14000E318, 0
0x140006c6b  test    rbx, rbx
0x140006c6e  jz      short loc_140006C79
0x140006c70  mov     rcx, rbx; pv
0x140006c73  call    cs:__imp_CoTaskMemFree
0x140006c79  test    rdi, rdi
0x140006c7c  jz      short loc_140006CE8
0x140006c7e  lea     rax, [rsp+458h+var_418]
0x140006c83  mov     r8d, 200h
0x140006c89  mov     [rsp+458h+pv], rax
0x140006c8e  lea     rdx, [rsp+458h+var_418]
0x140006c93  mov     rax, [rsi]
0x140006c96  mov     rcx, rsi
0x140006c99  mov     rax, [rax+10h]
0x140006c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ca2  cmp     eax, 8007007Ah
0x140006ca7  jnz     short loc_140006CBD
0x140006ca9  mov     rax, [rsi]
0x140006cac  lea     rdx, [rsp+458h+pv]
0x140006cb1  mov     rcx, rsi
0x140006cb4  mov     rax, [rax+8]
0x140006cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006cbd  test    eax, eax
0x140006cbf  js      short loc_140006CDF
0x140006cc1  mov     r8, [rsp+458h+pv]
0x140006cc6  lea     rdx, aS_0; "%s\n"
0x140006ccd  mov     rcx, rdi; Stream
0x140006cd0  call    cs:__imp_fwprintf
0x140006cd6  mov     rcx, rdi; Stream
0x140006cd9  call    cs:__imp_fflush
0x140006cdf  mov     rcx, rdi; Stream
0x140006ce2  call    cs:__imp_fclose
0x140006ce8  lea     rcx, stru_140010720; lpCriticalSection
0x140006cef  call    cs:__imp_LeaveCriticalSection
0x140006cf5  mov     rcx, [rsp+458h+var_18]
0x140006cfd  xor     rcx, rsp; StackCookie
0x140006d00  call    __security_check_cookie
0x140006d05  lea     r11, [rsp+458h+var_8]
0x140006d0d  mov     rbx, [r11+18h]
0x140006d11  mov     rsi, [r11+20h]
0x140006d15  mov     rsp, r11
0x140006d18  pop     rdi
0x140006d19  retn
```
