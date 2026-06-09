# _ApplySetHoursToLimitDownloadBandwidthXml

- ea: `0x18000bd84`
- end: `0x18000be2c`
- name: `_ApplySetHoursToLimitDownloadBandwidthXml`
- size: `168`
- prototype: `LSTATUS __fastcall(LPCSTR lpValueName, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bbd0`

## callees

- `0x180001ba0`
- `0x18000bd04`
- `0x18000bd84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueA` at `0x18000be0d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueA` at `0x18000be0d`

## pseudocode

```c
LSTATUS __fastcall ApplySetHoursToLimitDownloadBandwidthXml(LPCSTR lpValueName, _DWORD *a2)
{
  LSTATUS result; // eax
  __int64 v4; // rax
  char Data[304]; // [rsp+40h] [rbp-148h] BYREF

  result = StringCchPrintfA(
             Data,
             0x122u,
             "<Range><RangeStartTime>%u</RangeStartTime><RangeEndTime>%u</RangeEndTime><PercentageMaxDownloadBandwidthIn>"
             "%u</PercentageMaxDownloadBandwidthIn><PercentageMaxDownloadBandwidthOut>%u</PercentageMaxDownloadBandwidthOut></Range>",
             *a2,
             a2[1],
             a2[2],
             a2[3]);
  if ( result >= 0 )
  {
    v4 = -1;
    do
      ++v4;
    while ( Data[v4] );
    return RegSetKeyValueA(
             HKEY_LOCAL_MACHINE,
             "SOFTWARE\\Policies\\Microsoft\\Windows\\DeliveryOptimization",
             lpValueName,
             1u,
             Data,
             v4 + 1);
  }
  return result;
}

```

## disassembly

```asm
0x18000bd84  push    rbx
0x18000bd86  sub     rsp, 180h
0x18000bd8d  mov     rax, cs:__security_cookie
0x18000bd94  xor     rax, rsp
0x18000bd97  mov     [rsp+188h+var_18], rax
0x18000bd9f  mov     eax, [rdx+0Ch]
0x18000bda2  lea     r8, aRangeRangestar; "<Range><RangeStartTime>%u</RangeStartTi"...
0x18000bda9  mov     r9d, [rdx]
0x18000bdac  mov     rbx, rcx
0x18000bdaf  mov     [rsp+188h+var_158], eax
0x18000bdb3  lea     rcx, [rsp+188h+Data]; char *
0x18000bdb8  mov     eax, [rdx+8]
0x18000bdbb  mov     [rsp+188h+cbData], eax
0x18000bdbf  mov     eax, [rdx+4]
0x18000bdc2  mov     edx, 122h; unsigned __int64
0x18000bdc7  mov     dword ptr [rsp+188h+lpData], eax
0x18000bdcb  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000bdd0  test    eax, eax
0x18000bdd2  js      short loc_18000BE13
0x18000bdd4  lea     rcx, [rsp+188h+Data]
0x18000bdd9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bddd  inc     rax
0x18000bde0  cmp     byte ptr [rcx+rax], 0
0x18000bde4  jnz     short loc_18000BDDD
0x18000bde6  inc     eax
0x18000bde8  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18000bdef  mov     [rsp+188h+cbData], eax; cbData
0x18000bdf3  mov     r9d, 1; dwType
0x18000bdf9  lea     rax, [rsp+188h+Data]
0x18000bdfe  mov     r8, rbx; lpValueName
0x18000be01  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000be08  mov     [rsp+188h+lpData], rax; lpData
0x18000be0d  call    cs:__imp_RegSetKeyValueA
0x18000be13  mov     rcx, [rsp+188h+var_18]
0x18000be1b  xor     rcx, rsp; StackCookie
0x18000be1e  call    __security_check_cookie
0x18000be23  add     rsp, 180h
0x18000be2a  pop     rbx
0x18000be2b  retn
```
