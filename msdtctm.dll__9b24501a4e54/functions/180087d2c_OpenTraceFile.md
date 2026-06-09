# OpenTraceFile

- ea: `0x180087d2c`
- end: `0x180087e21`
- name: `OpenTraceFile`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180087e28`

## callees

- `0x180084dfc`
- `0x180087c40`
- `0x180087d2c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180087d88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180087dba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180087d88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180087dba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087d7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087e0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087d7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087e0d`
- `msvcrt!_wfopen` at `0x180087df5`
- `msvcrt!_wfopen` at `0x180087df5`

## pseudocode

```c
FILE *OpenTraceFile()
{
  void *v0; // rbx
  FILE *v1; // rdi
  int ImageName; // eax
  __int64 v4; // [rsp+20h] [rbp-18h]
  DWORD CurrentProcessId; // [rsp+28h] [rbp-10h]
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF

  v0 = 0;
  v1 = 0;
  pv = 0;
  if ( !TraceOutputSettings::TraceFilePath )
    return v1;
  if ( byte_180153E1C )
  {
    if ( TraceOutputSettings::ImageNameInTraceFileNameEnabled )
    {
      ImageName = GetImageName((unsigned __int16 **)&pv);
      v0 = pv;
      if ( ImageName < 0 )
      {
        if ( !pv )
          goto LABEL_9;
        CoTaskMemFree(pv);
        v0 = 0;
      }
    }
    if ( !v0
      || (CurrentProcessId = GetCurrentProcessId(),
          (int)StringCbPrintfW(
                 &FileName,
                 0x20Au,
                 L"%s\\MSDTC-%s-%d.log",
                 TraceOutputSettings::TraceFilePath,
                 v0,
                 CurrentProcessId) < 0) )
    {
LABEL_9:
      LODWORD(v4) = GetCurrentProcessId();
      if ( (int)StringCbPrintfW(&FileName, 0x20Au, L"%s\\MSDTC-%d.log", TraceOutputSettings::TraceFilePath, v4) < 0 )
        goto LABEL_11;
    }
  }
  v1 = _wfopen(&FileName, L"a+");
  byte_180153E1C = 0;
LABEL_11:
  if ( v0 )
    CoTaskMemFree(v0);
  return v1;
}

```

## disassembly

```asm
0x180087d2c  mov     [rsp+arg_8], rbx
0x180087d31  push    rdi
0x180087d32  sub     rsp, 30h
0x180087d36  xor     ebx, ebx
0x180087d38  xor     edi, edi
0x180087d3a  cmp     cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA, rbx; ushort * TraceOutputSettings::TraceFilePath
0x180087d41  mov     [rsp+38h+pv], rbx
0x180087d46  jz      loc_180087E13
0x180087d4c  cmp     cs:byte_180153E1C, bl
0x180087d52  jz      loc_180087DE7
0x180087d58  cmp     cs:?ImageNameInTraceFileNameEnabled@TraceOutputSettings@@2_NA, bl; bool TraceOutputSettings::ImageNameInTraceFileNameEnabled
0x180087d5e  jz      short loc_180087D83
0x180087d60  lea     rcx, [rsp+38h+pv]; unsigned __int16 **
0x180087d65  call    ?GetImageName@@YAJPEAPEAG@Z; GetImageName(ushort * *)
0x180087d6a  mov     rbx, [rsp+38h+pv]
0x180087d6f  test    eax, eax
0x180087d71  jns     short loc_180087D83
0x180087d73  test    rbx, rbx
0x180087d76  jz      short loc_180087DBA
0x180087d78  mov     rcx, rbx; pv
0x180087d7b  call    cs:__imp_CoTaskMemFree
0x180087d81  xor     ebx, ebx
0x180087d83  test    rbx, rbx
0x180087d86  jz      short loc_180087DBA
0x180087d88  call    cs:__imp_GetCurrentProcessId
0x180087d8e  mov     r9, cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA; ushort * TraceOutputSettings::TraceFilePath
0x180087d95  lea     r8, aSMsdtcSDLog; "%s\\MSDTC-%s-%d.log"
0x180087d9c  mov     [rsp+38h+var_10], eax
0x180087da0  lea     rcx, FileName; unsigned __int16 *
0x180087da7  mov     edx, 20Ah; unsigned __int64
0x180087dac  mov     [rsp+38h+var_18], rbx
0x180087db1  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180087db6  test    eax, eax
0x180087db8  jns     short loc_180087DE7
0x180087dba  call    cs:__imp_GetCurrentProcessId
0x180087dc0  mov     r9, cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA; ushort * TraceOutputSettings::TraceFilePath
0x180087dc7  lea     r8, aSMsdtcDLog; "%s\\MSDTC-%d.log"
0x180087dce  mov     edx, 20Ah; unsigned __int64
0x180087dd3  mov     dword ptr [rsp+38h+var_18], eax
0x180087dd7  lea     rcx, FileName; unsigned __int16 *
0x180087dde  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180087de3  test    eax, eax
0x180087de5  js      short loc_180087E05
0x180087de7  lea     rdx, aA; "a+"
0x180087dee  lea     rcx, FileName; FileName
0x180087df5  call    cs:__imp__wfopen
0x180087dfb  mov     rdi, rax
0x180087dfe  mov     cs:byte_180153E1C, 0
0x180087e05  test    rbx, rbx
0x180087e08  jz      short loc_180087E13
0x180087e0a  mov     rcx, rbx; pv
0x180087e0d  call    cs:__imp_CoTaskMemFree
0x180087e13  mov     rbx, [rsp+38h+arg_8]
0x180087e18  mov     rax, rdi
0x180087e1b  add     rsp, 30h
0x180087e1f  pop     rdi
0x180087e20  retn
```
