# DtcInternalErrorW(ushort const *)

- ea: `0x1400024bc`
- end: `0x1400025ad`
- name: `?DtcInternalErrorW@@YAXPEBG@Z`
- size: `241`
- prototype: `void __fastcall __noreturn(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140002010`
- `0x140002ed4`

## callees

- `0x140002494`
- `0x1400024bc`
- `0x1400025c0`

## import_xrefs

- `ADVAPI32!DeregisterEventSource` at `0x140002598`
- `ADVAPI32!DeregisterEventSource` at `0x140002598`
- `ADVAPI32!RegisterEventSourceW` at `0x14000252f`
- `ADVAPI32!RegisterEventSourceW` at `0x14000252f`
- `ADVAPI32!ReportEventW` at `0x14000258a`
- `ADVAPI32!ReportEventW` at `0x14000258a`

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
  JUMPOUT(0x1400025ACLL);
}

```

## disassembly

```asm
0x1400024bc  mov     rax, rsp
0x1400024bf  mov     [rax+10h], rbx
0x1400024c3  push    rdi
0x1400024c4  sub     rsp, 0D0h
0x1400024cb  movaps  xmm0, xmmword ptr cs:aNoMoreInformat; "No more information about the error is "...
0x1400024d2  lea     rdx, SourceName; "MSDTC"
0x1400024d9  movaps  xmm1, xmmword ptr cs:aNoMoreInformat+10h; "information about the error is availabl"...
0x1400024e0  mov     rdi, rcx
0x1400024e3  movaps  xmmword ptr [rax-78h], xmm0
0x1400024e7  xor     ecx, ecx; lpUNCServerName
0x1400024e9  movaps  xmm0, xmmword ptr cs:aNoMoreInformat+20h; "ion about the error is available."
0x1400024f0  movaps  xmmword ptr [rax-68h], xmm1
0x1400024f4  movaps  xmm1, xmmword ptr cs:aNoMoreInformat+30h; "t the error is available."
0x1400024fb  movaps  xmmword ptr [rax-58h], xmm0
0x1400024ff  movaps  xmm0, xmmword ptr cs:aNoMoreInformat+40h; "ror is available."
0x140002506  movaps  xmmword ptr [rax-48h], xmm1
0x14000250a  movaps  xmm1, xmmword ptr cs:aNoMoreInformat+50h; "vailable."
0x140002511  movaps  xmmword ptr [rax-38h], xmm0
0x140002515  movaps  xmmword ptr [rax-28h], xmm1
0x140002519  mov     eax, dword ptr cs:aNoMoreInformat+60h; "."
0x14000251f  mov     [rsp+0D8h+var_18], eax
0x140002526  mov     [rsp+0D8h+Strings], 0
0x14000252f  call    cs:__imp_RegisterEventSourceW
0x140002535  mov     rbx, rax
0x140002538  test    rax, rax
0x14000253b  jz      short loc_1400025A0
0x14000253d  mov     [rsp+0D8h+lpRawData], 0; lpRawData
0x140002546  lea     rax, [rsp+0D8h+Strings]
0x14000254b  mov     [rsp+0D8h+lpStrings], rax; lpStrings
0x140002550  lea     rcx, [rsp+0D8h+var_78]
0x140002555  mov     [rsp+0D8h+dwDataSize], 0; dwDataSize
0x14000255d  test    rdi, rdi
0x140002560  mov     r9d, 0C0001159h; dwEventID
0x140002566  cmovnz  rcx, rdi
0x14000256a  mov     [rsp+0D8h+Strings], rcx
0x14000256f  mov     ecx, 1
0x140002574  mov     [rsp+0D8h+wNumStrings], cx; wNumStrings
0x140002579  mov     r8d, ecx; wCategory
0x14000257c  mov     edx, ecx; wType
0x14000257e  mov     [rsp+0D8h+lpUserSid], 0; lpUserSid
0x140002587  mov     rcx, rbx; hEventLog
0x14000258a  call    cs:__imp_ReportEventW
0x140002590  call    ?DtcDebugBreak@@YAXXZ; DtcDebugBreak(void)
0x140002595  mov     rcx, rbx; hEventLog
0x140002598  call    cs:__imp_DeregisterEventSource
0x14000259e  jmp     short loc_1400025A5
0x1400025a0  call    ?DtcDebugBreak@@YAXXZ; DtcDebugBreak(void)
0x1400025a5  xor     ecx, ecx; struct _EXCEPTION_POINTERS *
0x1400025a7  call    ?DtcRaiseExceptionForWatsonCrashAnalysis@@YAXPEAU_EXCEPTION_POINTERS@@@Z; DtcRaiseExceptionForWatsonCrashAnalysis(_EXCEPTION_POINTERS *)
```
