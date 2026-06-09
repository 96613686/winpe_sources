# DtcInternalErrorW(ushort const *)

- ea: `0x18000dc8c`
- end: `0x18000dd7d`
- name: `?DtcInternalErrorW@@YAXPEBG@Z`
- size: `241`
- prototype: `void __fastcall __noreturn(const unsigned __int16 *)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x180003358`
- `0x1800042b4`
- `0x180006ca0`
- `0x180006dd8`
- `0x18000adf8`
- `0x18000bc44`
- `0x18000e574`
- `0x18001395f`
- `0x180013995`

## callees

- `0x18000db30`
- `0x18000dc8c`
- `0x18000dd90`

## import_xrefs

- `ADVAPI32!DeregisterEventSource` at `0x18000dd68`
- `ADVAPI32!DeregisterEventSource` at `0x18000dd68`
- `ADVAPI32!ReportEventW` at `0x18000dd5a`
- `ADVAPI32!ReportEventW` at `0x18000dd5a`
- `ADVAPI32!RegisterEventSourceW` at `0x18000dcff`
- `ADVAPI32!RegisterEventSourceW` at `0x18000dcff`

## pseudocode

```c
void __fastcall __noreturn DtcInternalErrorW(const unsigned __int16 *a1)
{
  HANDLE v2; // rbx
  const WCHAR *v3; // rcx
  LPCWSTR Strings; // [rsp+50h] [rbp-88h] BYREF
  _OWORD v5[6]; // [rsp+60h] [rbp-78h] BYREF
  int v6; // [rsp+C0h] [rbp-18h]

  v5[0] = *(_OWORD *)L"No more information about the error is available.";
  v5[1] = *(_OWORD *)L"information about the error is available.";
  v5[2] = *(_OWORD *)L"ion about the error is available.";
  v5[3] = *(_OWORD *)L"t the error is available.";
  v5[4] = *(_OWORD *)L"ror is available.";
  v5[5] = *(_OWORD *)L"vailable.";
  v6 = *(_DWORD *)L".";
  Strings = 0;
  v2 = RegisterEventSourceW(0, L"MSDTC");
  if ( v2 )
  {
    v3 = (const WCHAR *)v5;
    if ( a1 )
      v3 = a1;
    Strings = v3;
    ReportEventW(v2, 1u, 1u, 0xC0001159, 0, 1u, 0, &Strings, 0);
    DtcDebugBreak();
    DeregisterEventSource(v2);
  }
  else
  {
    DtcDebugBreak();
  }
  DtcRaiseExceptionForWatsonCrashAnalysis(0);
  JUMPOUT(0x18000DD7CLL);
}

```

## disassembly

```asm
0x18000dc8c  mov     rax, rsp
0x18000dc8f  mov     [rax+10h], rbx
0x18000dc93  push    rdi
0x18000dc94  sub     rsp, 0D0h
0x18000dc9b  movaps  xmm0, xmmword ptr cs:aNoMoreInformat; "No more information about the error is "...
0x18000dca2  lea     rdx, SourceName; "MSDTC"
0x18000dca9  movaps  xmm1, xmmword ptr cs:aNoMoreInformat+10h; "information about the error is availabl"...
0x18000dcb0  mov     rdi, rcx
0x18000dcb3  movaps  xmmword ptr [rax-78h], xmm0
0x18000dcb7  xor     ecx, ecx; lpUNCServerName
0x18000dcb9  movaps  xmm0, xmmword ptr cs:aNoMoreInformat+20h; "ion about the error is available."
0x18000dcc0  movaps  xmmword ptr [rax-68h], xmm1
0x18000dcc4  movaps  xmm1, xmmword ptr cs:aNoMoreInformat+30h; "t the error is available."
0x18000dccb  movaps  xmmword ptr [rax-58h], xmm0
0x18000dccf  movaps  xmm0, xmmword ptr cs:aNoMoreInformat+40h; "ror is available."
0x18000dcd6  movaps  xmmword ptr [rax-48h], xmm1
0x18000dcda  movaps  xmm1, xmmword ptr cs:aNoMoreInformat+50h; "vailable."
0x18000dce1  movaps  xmmword ptr [rax-38h], xmm0
0x18000dce5  movaps  xmmword ptr [rax-28h], xmm1
0x18000dce9  mov     eax, dword ptr cs:aNoMoreInformat+60h; "."
0x18000dcef  mov     [rsp+0D8h+var_18], eax
0x18000dcf6  mov     [rsp+0D8h+Strings], 0
0x18000dcff  call    cs:__imp_RegisterEventSourceW
0x18000dd05  mov     rbx, rax
0x18000dd08  test    rax, rax
0x18000dd0b  jz      short loc_18000DD70
0x18000dd0d  mov     [rsp+0D8h+lpRawData], 0; lpRawData
0x18000dd16  lea     rax, [rsp+0D8h+Strings]
0x18000dd1b  mov     [rsp+0D8h+lpStrings], rax; lpStrings
0x18000dd20  lea     rcx, [rsp+0D8h+var_78]
0x18000dd25  mov     [rsp+0D8h+dwDataSize], 0; dwDataSize
0x18000dd2d  test    rdi, rdi
0x18000dd30  mov     r9d, 0C0001159h; dwEventID
0x18000dd36  cmovnz  rcx, rdi
0x18000dd3a  mov     [rsp+0D8h+Strings], rcx
0x18000dd3f  mov     ecx, 1
0x18000dd44  mov     [rsp+0D8h+wNumStrings], cx; wNumStrings
0x18000dd49  mov     r8d, ecx; wCategory
0x18000dd4c  mov     edx, ecx; wType
0x18000dd4e  mov     [rsp+0D8h+lpUserSid], 0; lpUserSid
0x18000dd57  mov     rcx, rbx; hEventLog
0x18000dd5a  call    cs:__imp_ReportEventW
0x18000dd60  call    ?DtcDebugBreak@@YAXXZ; DtcDebugBreak(void)
0x18000dd65  mov     rcx, rbx; hEventLog
0x18000dd68  call    cs:__imp_DeregisterEventSource
0x18000dd6e  jmp     short loc_18000DD75
0x18000dd70  call    ?DtcDebugBreak@@YAXXZ; DtcDebugBreak(void)
0x18000dd75  xor     ecx, ecx; struct _EXCEPTION_POINTERS *
0x18000dd77  call    ?DtcRaiseExceptionForWatsonCrashAnalysis@@YAXPEAU_EXCEPTION_POINTERS@@@Z; DtcRaiseExceptionForWatsonCrashAnalysis(_EXCEPTION_POINTERS *)
```
