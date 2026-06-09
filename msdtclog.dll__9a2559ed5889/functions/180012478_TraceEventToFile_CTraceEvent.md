# TraceEventToFile(CTraceEvent &)

- ea: `0x180012478`
- end: `0x18001262a`
- name: `?TraceEventToFile@@YAXAEAVCTraceEvent@@@Z`
- size: `434`
- prototype: `void __fastcall(struct CTraceEvent *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001135c`

## callees

- `0x18000df74`
- `0x18001238c`
- `0x180012478`
- `0x180012830`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800124ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012583`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800124ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012583`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800125ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800125ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800124a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800124a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800124fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012530`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800124fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012530`
- `msvcrt!_wfopen` at `0x18001256b`
- `msvcrt!_wfopen` at `0x18001256b`
- `msvcrt!fflush` at `0x1800125e9`
- `msvcrt!fflush` at `0x1800125e9`
- `msvcrt!fclose` at `0x1800125f2`
- `msvcrt!fclose` at `0x1800125f2`
- `msvcrt!fwprintf` at `0x1800125e0`
- `msvcrt!fwprintf` at `0x1800125e0`

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

  EnterCriticalSection(&stru_18001F9D8);
  v2 = 0;
  pv[0] = 0;
  if ( !TraceOutputSettings::TraceFilePath )
    goto LABEL_19;
  if ( !byte_18001F358 )
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
                &word_180021810,
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
  if ( (int)StringCbPrintfW(&word_180021810, 0x20Au, L"%s\\MSDTC-%d.log", TraceOutputSettings::TraceFilePath, v6) >= 0 )
  {
LABEL_10:
    v4 = _wfopen(&word_180021810, L"a+");
    byte_18001F358 = 0;
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
  LeaveCriticalSection(&stru_18001F9D8);
}

```

## disassembly

```asm
0x180012478  mov     [rsp+arg_8], rbx
0x18001247d  mov     [rsp+arg_10], rsi
0x180012482  push    rdi
0x180012483  sub     rsp, 450h
0x18001248a  mov     rax, cs:__security_cookie
0x180012491  xor     rax, rsp
0x180012494  mov     [rsp+458h+var_18], rax
0x18001249c  mov     rsi, rcx
0x18001249f  lea     rcx, stru_18001F9D8; lpCriticalSection
0x1800124a6  call    cs:__imp_EnterCriticalSection
0x1800124ac  xor     ebx, ebx
0x1800124ae  cmp     cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA, rbx; ushort * TraceOutputSettings::TraceFilePath
0x1800124b5  mov     [rsp+458h+pv], rbx
0x1800124ba  jz      loc_1800125F8
0x1800124c0  cmp     cs:byte_18001F358, bl
0x1800124c6  jz      loc_18001255D
0x1800124cc  cmp     cs:?ImageNameInTraceFileNameEnabled@TraceOutputSettings@@2_NA, bl; bool TraceOutputSettings::ImageNameInTraceFileNameEnabled
0x1800124d2  jz      short loc_1800124F7
0x1800124d4  lea     rcx, [rsp+458h+pv]; unsigned __int16 **
0x1800124d9  call    ?GetImageName@@YAJPEAPEAG@Z; GetImageName(ushort * *)
0x1800124de  mov     rbx, [rsp+458h+pv]
0x1800124e3  test    eax, eax
0x1800124e5  jns     short loc_1800124F7
0x1800124e7  test    rbx, rbx
0x1800124ea  jz      short loc_18001252E
0x1800124ec  mov     rcx, rbx; pv
0x1800124ef  call    cs:__imp_CoTaskMemFree
0x1800124f5  xor     ebx, ebx
0x1800124f7  test    rbx, rbx
0x1800124fa  jz      short loc_18001252E
0x1800124fc  call    cs:__imp_GetCurrentProcessId
0x180012502  mov     r9, cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA; ushort * TraceOutputSettings::TraceFilePath
0x180012509  lea     r8, aSMsdtcSDLog; "%s\\MSDTC-%s-%d.log"
0x180012510  mov     [rsp+458h+var_430], eax
0x180012514  lea     rcx, word_180021810; unsigned __int16 *
0x18001251b  mov     edx, 20Ah; unsigned __int64
0x180012520  mov     [rsp+458h+var_438], rbx
0x180012525  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001252a  test    eax, eax
0x18001252c  jns     short loc_18001255D
0x18001252e  xor     edi, edi
0x180012530  call    cs:__imp_GetCurrentProcessId
0x180012536  mov     r9, cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA; ushort * TraceOutputSettings::TraceFilePath
0x18001253d  lea     r8, aSMsdtcDLog; "%s\\MSDTC-%d.log"
0x180012544  mov     edx, 20Ah; unsigned __int64
0x180012549  mov     dword ptr [rsp+458h+var_438], eax
0x18001254d  lea     rcx, word_180021810; unsigned __int16 *
0x180012554  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012559  test    eax, eax
0x18001255b  js      short loc_18001257B
0x18001255d  lea     rdx, aA; "a+"
0x180012564  lea     rcx, word_180021810; FileName
0x18001256b  call    cs:__imp__wfopen
0x180012571  mov     rdi, rax
0x180012574  mov     cs:byte_18001F358, 0
0x18001257b  test    rbx, rbx
0x18001257e  jz      short loc_180012589
0x180012580  mov     rcx, rbx; pv
0x180012583  call    cs:__imp_CoTaskMemFree
0x180012589  test    rdi, rdi
0x18001258c  jz      short loc_1800125F8
0x18001258e  lea     rax, [rsp+458h+var_418]
0x180012593  mov     r8d, 200h
0x180012599  mov     [rsp+458h+pv], rax
0x18001259e  lea     rdx, [rsp+458h+var_418]
0x1800125a3  mov     rax, [rsi]
0x1800125a6  mov     rcx, rsi
0x1800125a9  mov     rax, [rax+10h]
0x1800125ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125b2  cmp     eax, 8007007Ah
0x1800125b7  jnz     short loc_1800125CD
0x1800125b9  mov     rax, [rsi]
0x1800125bc  lea     rdx, [rsp+458h+pv]
0x1800125c1  mov     rcx, rsi
0x1800125c4  mov     rax, [rax+8]
0x1800125c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125cd  test    eax, eax
0x1800125cf  js      short loc_1800125EF
0x1800125d1  mov     r8, [rsp+458h+pv]
0x1800125d6  lea     rdx, aS_1; "%s\n"
0x1800125dd  mov     rcx, rdi; Stream
0x1800125e0  call    cs:__imp_fwprintf
0x1800125e6  mov     rcx, rdi; Stream
0x1800125e9  call    cs:__imp_fflush
0x1800125ef  mov     rcx, rdi; Stream
0x1800125f2  call    cs:__imp_fclose
0x1800125f8  lea     rcx, stru_18001F9D8; lpCriticalSection
0x1800125ff  call    cs:__imp_LeaveCriticalSection
0x180012605  mov     rcx, [rsp+458h+var_18]
0x18001260d  xor     rcx, rsp; StackCookie
0x180012610  call    __security_check_cookie
0x180012615  lea     r11, [rsp+458h+var_8]
0x18001261d  mov     rbx, [r11+18h]
0x180012621  mov     rsi, [r11+20h]
0x180012625  mov     rsp, r11
0x180012628  pop     rdi
0x180012629  retn
```
