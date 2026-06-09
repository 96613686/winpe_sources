# CEnergyTaskHandler::RunSleepStudyReport(void)

- ea: `0x1800029bc`
- end: `0x180002aaa`
- name: `?RunSleepStudyReport@CEnergyTaskHandler@@AEAAJXZ`
- size: `238`
- prototype: `__int64 __fastcall(CEnergyTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002da0`

## callees

- `0x1800029bc`
- `0x180002c8c`
- `0x180003118`
- `0x180003ac0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002a89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002a89`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x1800029fd`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x1800029fd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002a5f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002a5f`

## pseudocode

```c
__int64 __fastcall CEnergyTaskHandler::RunSleepStudyReport(CEnergyTaskHandler *this)
{
  signed int SleepStudyTraceDirectory; // ebx
  int v2; // eax
  CEnergyTaskHandler *v3; // rcx
  unsigned int v4; // r8d
  unsigned int pvData; // [rsp+40h] [rbp-238h] BYREF
  DWORD pcbData[3]; // [rsp+44h] [rbp-234h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-228h] BYREF

  pvData = 0;
  SleepStudyTraceDirectory = GetSleepStudyTraceDirectory(pszPath);
  if ( SleepStudyTraceDirectory >= 0 )
  {
    v2 = SHCreateDirectoryExW(0, pszPath, 0);
    SleepStudyTraceDirectory = v2;
    if ( !v2 || v2 == 183 )
    {
      pcbData[0] = 4;
      if ( RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Control\\Session Manager\\Power",
             L"SleepStudyHistoryDays",
             0x10u,
             0,
             &pvData,
             pcbData) )
      {
        v4 = 28;
        pvData = 28;
      }
      else
      {
        v4 = pvData;
      }
      SleepStudyTraceDirectory = CEnergyTaskHandler::TracesCleanup(v3, pszPath, v4);
    }
    else if ( v2 > 0 )
    {
      SleepStudyTraceDirectory = (unsigned __int16)v2 | 0x80070000;
    }
  }
  CoTaskMemFree(0);
  return (unsigned int)SleepStudyTraceDirectory;
}

```

## disassembly

```asm
0x1800029bc  push    rbx
0x1800029be  sub     rsp, 270h
0x1800029c5  mov     rax, cs:__security_cookie
0x1800029cc  xor     rax, rsp
0x1800029cf  mov     [rsp+278h+var_18], rax
0x1800029d7  lea     rcx, [rsp+278h+pszPath]; unsigned __int16 *
0x1800029dc  mov     [rsp+278h+var_238], 0
0x1800029e4  call    GetSleepStudyTraceDirectory
0x1800029e9  mov     ebx, eax
0x1800029eb  test    eax, eax
0x1800029ed  js      loc_180002A87
0x1800029f3  xor     r8d, r8d; psa
0x1800029f6  lea     rdx, [rsp+278h+pszPath]; pszPath
0x1800029fb  xor     ecx, ecx; hwnd
0x1800029fd  call    cs:__imp_SHCreateDirectoryExW
0x180002a03  mov     ebx, eax
0x180002a05  test    eax, eax
0x180002a07  jz      short loc_180002A1F
0x180002a09  cmp     eax, 0B7h
0x180002a0e  jz      short loc_180002A1F
0x180002a10  test    eax, eax
0x180002a12  jle     short loc_180002A87
0x180002a14  movzx   ebx, ax
0x180002a17  or      ebx, 80070000h
0x180002a1d  jmp     short loc_180002A87
0x180002a1f  lea     rax, [rsp+278h+var_234]
0x180002a24  mov     [rsp+278h+var_234], 4
0x180002a2c  mov     [rsp+278h+pcbData], rax; pcbData
0x180002a31  lea     r8, Value; "SleepStudyHistoryDays"
0x180002a38  lea     rax, [rsp+278h+var_238]
0x180002a3d  mov     r9d, 10h; dwFlags
0x180002a43  mov     [rsp+278h+pvData], rax; pvData
0x180002a48  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Ses"...
0x180002a4f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180002a56  mov     [rsp+278h+pdwType], 0; pdwType
0x180002a5f  call    cs:__imp_RegGetValueW
0x180002a65  test    eax, eax
0x180002a67  jz      short loc_180002A76
0x180002a69  mov     r8d, 1Ch
0x180002a6f  mov     [rsp+278h+var_238], r8d
0x180002a74  jmp     short loc_180002A7B
0x180002a76  mov     r8d, [rsp+278h+var_238]; unsigned int
0x180002a7b  lea     rdx, [rsp+278h+pszPath]; unsigned __int16 *
0x180002a80  call    ?TracesCleanup@CEnergyTaskHandler@@AEAAJPEBGK@Z; CEnergyTaskHandler::TracesCleanup(ushort const *,ulong)
0x180002a85  mov     ebx, eax
0x180002a87  xor     ecx, ecx; pv
0x180002a89  call    cs:__imp_CoTaskMemFree
0x180002a8f  mov     eax, ebx
0x180002a91  mov     rcx, [rsp+278h+var_18]
0x180002a99  xor     rcx, rsp; StackCookie
0x180002a9c  call    __security_check_cookie
0x180002aa1  add     rsp, 270h
0x180002aa8  pop     rbx
0x180002aa9  retn
```
