# BlackScreenDiagnostics::CWatsonErrorReporting::TryInit(void)

- ea: `0x14000f500`
- end: `0x14000f5c0`
- name: `?TryInit@CWatsonErrorReporting@BlackScreenDiagnostics@@AEAA_NXZ`
- size: `192`
- prototype: `bool __fastcall(HREPORT *phReportHandle)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14000e994`
- `0x14000f444`
- `0x14000f4a8`

## callees

- `0x140005530`
- `0x1400061b8`
- `0x14000f0b0`
- `0x14000f500`
- `0x14000f5c8`

## import_xrefs

- `ext-ms-win-wer-reporting-l1-1-0!WerReportCreate` at `0x14000f58f`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCreate` at `0x14000f58f`

## pseudocode

```c
bool __fastcall BlackScreenDiagnostics::CWatsonErrorReporting::TryInit(HREPORT *phReportHandle)
{
  const WCHAR *v3; // rcx
  _WER_REPORT_INFORMATION pReportInformation; // [rsp+20h] [rbp-8B8h] BYREF

  if ( !*phReportHandle )
  {
    if ( !*((_BYTE *)phReportHandle + 8) )
      return 0;
    memset_0(&pReportInformation, 0, sizeof(pReportInformation));
    pReportInformation.dwSize = 2208;
    std::wstring::copy(phReportHandle + 6, pReportInformation.wzFriendlyEventName, phReportHandle[8]);
    std::wstring::copy(phReportHandle + 10, pReportInformation.wzDescription, phReportHandle[12]);
    if ( (unsigned __int8)std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged(phReportHandle + 2) )
      v3 = *(const WCHAR **)v3;
    if ( WerReportCreate(v3, WerReportCritical, &pReportInformation, phReportHandle) < 0 )
      *phReportHandle = 0;
  }
  return *phReportHandle != 0;
}

```

## disassembly

```asm
0x14000f500  push    rbx
0x14000f502  sub     rsp, 8D0h
0x14000f509  mov     rax, cs:__security_cookie
0x14000f510  xor     rax, rsp
0x14000f513  mov     [rsp+8D8h+var_18], rax
0x14000f51b  cmp     qword ptr [rcx], 0
0x14000f51f  mov     rbx, rcx
0x14000f522  jnz     short loc_14000F5A0
0x14000f524  cmp     byte ptr [rcx+8], 0
0x14000f528  jnz     short loc_14000F52E
0x14000f52a  xor     al, al
0x14000f52c  jmp     short loc_14000F5A7
0x14000f52e  xor     edx, edx; Val
0x14000f530  lea     rcx, [rsp+8D8h+pReportInformation]; void *
0x14000f535  mov     r8d, 8A0h; Size
0x14000f53b  call    memset_0
0x14000f540  lea     rcx, [rbx+30h]
0x14000f544  mov     [rsp+8D8h+pReportInformation.dwSize], 8A0h
0x14000f54c  mov     r8, [rcx+10h]
0x14000f550  lea     rdx, [rsp+8D8h+pReportInformation.wzFriendlyEventName]
0x14000f558  call    ?copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEAG_K_K@Z; std::wstring::copy(ushort * const,unsigned __int64,unsigned __int64)
0x14000f55d  lea     rcx, [rbx+50h]
0x14000f561  mov     r8, [rcx+10h]
0x14000f565  lea     rdx, [rsp+8D8h+pReportInformation.wzDescription]
0x14000f56d  call    ?copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEAG_K_K@Z; std::wstring::copy(ushort * const,unsigned __int64,unsigned __int64)
0x14000f572  lea     rcx, [rbx+10h]
0x14000f576  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<ushort>>::_Large_mode_engaged(void)
0x14000f57b  test    al, al
0x14000f57d  jz      short loc_14000F582
0x14000f57f  mov     rcx, [rcx]; pwzEventType
0x14000f582  mov     r9, rbx; phReportHandle
0x14000f585  lea     r8, [rsp+8D8h+pReportInformation]; pReportInformation
0x14000f58a  mov     edx, 1; repType
0x14000f58f  call    cs:__imp_WerReportCreate
0x14000f595  test    eax, eax
0x14000f597  jns     short loc_14000F5A0
0x14000f599  mov     qword ptr [rbx], 0
0x14000f5a0  cmp     qword ptr [rbx], 0
0x14000f5a4  setnz   al
0x14000f5a7  mov     rcx, [rsp+8D8h+var_18]
0x14000f5af  xor     rcx, rsp; StackCookie
0x14000f5b2  call    __security_check_cookie
0x14000f5b7  add     rsp, 8D0h
0x14000f5be  pop     rbx
0x14000f5bf  retn
```
