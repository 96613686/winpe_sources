# ExdiLiveKernelTargetInfo::FindSysAppBaseAddressByHwDbgBlock(IeXdiServer3 * const,_GUID const *,ProcessInfo *,ulong,ulong,_DBGKD_GET_VERSION64 *)

- ea: `0x18037133c`
- end: `0x180371776`
- name: `?FindSysAppBaseAddressByHwDbgBlock@ExdiLiveKernelTargetInfo@@AEAAJQEAUIeXdiServer3@@PEBU_GUID@@PEAVProcessInfo@@KKPEAU_DBGKD_GET_VERSION64@@@Z`
- size: `1082`
- prototype: `__int64 __usercall@<rax>(ExdiLiveKernelTargetInfo *__hidden this@<rcx>, struct IeXdiServer3 *const@<rdx>, const struct _GUID *@<r8>, struct ProcessInfo *@<r9>, unsigned int, unsigned int, struct _DBGKD_GET_VERSION64 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180372e94`

## callees

- `0x180071a60`
- `0x1800b94c4`
- `0x1800f0f40`
- `0x1802cc8c4`
- `0x18036ef44`
- `0x180370148`
- `0x18037133c`
- `0x180371990`
- `0x180374624`
- `0x18038605c`
- `0x1804da4c0`
- `0x1804dafb0`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1803715aa`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1803715aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180371397`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180371648`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180371397`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180371648`
- `ntdll!RtlComputeCrc32` at `0x1803714d6`
- `ntdll!RtlComputeCrc32` at `0x1803714d6`

## string_xrefs

- `0x180371687`: `Failed reading HWDbg block link: status=0x%x.\n`
- `0x180371699`: `HwDbgBlockHeuristicSessionSucceeded`
- `0x1803716d3`: `HwDbgBlockHeuristicSessionSucceeded`
- `0x18037163c`: `Invalid HWDbg block. Validating the HWB DBG block descriptor failed.\n`
- `0x180371738`: `Failed reading HWDbg block: status=0x%x.\n`

## pseudocode

```c
int __fastcall ExdiLiveKernelTargetInfo::FindSysAppBaseAddressByHwDbgBlock(
        ExdiLiveKernelTargetInfo *this,
        struct IeXdiServer3 *const a2,
        const struct _GUID *a3,
        struct ProcessInfo *a4,
        unsigned int Register,
        unsigned int a6,
        struct _DBGKD_GET_VERSION64 *a7)
{
  unsigned int v8; // eax
  DWORD TickCount; // [rsp+58h] [rbp-A8h]

  if ( !a2 || !a3 || !a4 || !a7 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
  TickCount = GetTickCount();
  CheckExdiPhysicalCachedMemory(a2);
  v8 = (*(__int64 (__fastcall **)(TargetInfo *, __int64, UCHAR *, __int64))(*(_QWORD *)g_Target + 312LL))(
         g_Target,
         8,
         &g_HwDbgBlockPageBuffer,
         4088);
  VerbOut(L"Failed reading HWDbg block: status=0x%x.\n", v8);
  return -2147418113;
}

```

## disassembly

```asm
0x18037133c  mov     [rsp-8+arg_18], rbx
0x180371341  push    rbp
0x180371342  push    rsi
0x180371343  push    rdi
0x180371344  push    r12
0x180371346  push    r13
0x180371348  push    r14
0x18037134a  push    r15
0x18037134c  lea     rbp, [rsp-1D0h]
0x180371354  sub     rsp, 2D0h
0x18037135b  mov     rax, cs:__security_cookie
0x180371362  xor     rax, rsp
0x180371365  mov     [rbp+200h+var_40], rax
0x18037136c  mov     rsi, [rbp+200h+arg_30]
0x180371373  xor     edi, edi
0x180371375  mov     r12, r8
0x180371378  mov     rbx, rdx
0x18037137b  mov     r13, rcx
0x18037137e  test    rdx, rdx
0x180371381  jz      short loc_180371392
0x180371383  test    r8, r8
0x180371386  jz      short loc_180371392
0x180371388  test    r9, r9
0x18037138b  jz      short loc_180371392
0x18037138d  test    rsi, rsi
0x180371390  jnz     short loc_180371397
0x180371392  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180371397  call    cs:__imp_GetTickCount
0x18037139e  nop     dword ptr [rax+rax+00h]
0x1803713a3  mov     rcx, rbx; struct IeXdiServer3 *
0x1803713a6  mov     [rsp+300h+var_2B0], edi
0x1803713aa  mov     [rsp+300h+var_2A8], eax
0x1803713ae  call    ?CheckExdiPhysicalCachedMemory@@YAXQEAUIeXdiServer3@@@Z; CheckExdiPhysicalCachedMemory(IeXdiServer3 * const)
0x1803713b3  mov     r15, rdi
0x1803713b6  mov     r14d, edi
0x1803713b9  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; TargetInfo * g_Target
0x1803713c0  lea     r8, [rsp+300h+var_2B0]
0x1803713c5  lea     r10, ?g_HwDbgBlockPageBuffer@@3PAEA; uchar near * g_HwDbgBlockPageBuffer
0x1803713cc  mov     byte ptr [rsp+300h+var_2D0], dil
0x1803713d1  mov     qword ptr [rsp+300h+var_2D8], r8
0x1803713d6  lea     rdx, [r15+8]
0x1803713da  mov     r9d, 0FF8h
0x1803713e0  mov     [rsp+300h+var_2E0], edi
0x1803713e4  mov     rax, [rcx]
0x1803713e7  mov     r8, r10
0x1803713ea  mov     rax, [rax+138h]
0x1803713f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803713f6  test    eax, eax
0x1803713f8  js      loc_180371738
0x1803713fe  cmp     [rsp+300h+var_2B0], 0FF8h
0x180371406  jnz     loc_180371738
0x18037140c  mov     r8d, 10h; Size
0x180371412  lea     rdx, qword_180671490; Buf2
0x180371419  lea     rcx, ?g_HwDbgBlockPageBuffer@@3PAEA; Buf1
0x180371420  call    memcmp
0x180371425  test    eax, eax
0x180371427  jnz     short loc_18037147C
0x180371429  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; TargetInfo * g_Target
0x180371430  lea     rdx, [rsp+300h+var_2B0]
0x180371435  mov     byte ptr [rsp+300h+var_2D0], dil
0x18037143a  lea     r8, ?g_HwDbgBlockPageBuffer@@3PAEA; uchar near * g_HwDbgBlockPageBuffer
0x180371441  mov     qword ptr [rsp+300h+var_2D8], rdx
0x180371446  mov     r9d, 0FF8h
0x18037144c  mov     rdx, cs:qword_1807E5E00
0x180371453  mov     rax, [rcx]
0x180371456  mov     [rsp+300h+var_2E0], edi; int
0x18037145a  mov     rax, [rax+138h]
0x180371461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180371466  test    eax, eax
0x180371468  js      loc_180371687
0x18037146e  cmp     [rsp+300h+var_2B0], 0FF8h
0x180371476  jnz     loc_180371687
0x18037147c  mov     r8d, 10h; Size
0x180371482  lea     rdx, qword_1806714A0; Buf2
0x180371489  lea     rcx, ?g_HwDbgBlockPageBuffer@@3PAEA; Buf1
0x180371490  call    memcmp
0x180371495  test    eax, eax
0x180371497  jnz     loc_180371666
0x18037149d  cmp     dword ptr cs:qword_1807E5E00, 1
0x1803714a4  jb      loc_180371666
0x1803714aa  movzx   eax, word ptr cs:qword_1807E5E00+4
0x1803714b1  cmp     eax, 68h ; 'h'
0x1803714b4  jb      loc_180371666
0x1803714ba  mov     edi, cs:dword_1807E5E08
0x1803714c0  lea     rdx, ?g_HwDbgBlockPageBuffer@@3PAEA; Buffer
0x1803714c7  mov     r8d, eax; Length
0x1803714ca  mov     cs:dword_1807E5E08, 0
0x1803714d4  xor     ecx, ecx; InitialCrc
0x1803714d6  call    cs:__imp_RtlComputeCrc32
0x1803714dd  nop     dword ptr [rax+rax+00h]
0x1803714e2  cmp     eax, edi
0x1803714e4  jnz     loc_18037172F
0x1803714ea  cmp     [rsp+300h+var_2B0], 0FF8h
0x1803714f2  mov     cs:dword_1807E5E08, edi
0x1803714f8  ja      loc_180371721
0x1803714fe  movaps  xmm0, cs:?g_HwDbgBlockPageBuffer@@3PAEA; uchar near * g_HwDbgBlockPageBuffer
0x180371505  lea     rax, ?g_HwDbgBlockPageBuffer@@3PAEA; uchar near * g_HwDbgBlockPageBuffer
0x18037150c  mov     [rsp+300h+var_288], rax
0x180371511  lea     rcx, [rbp+200h+var_280]
0x180371515  lea     rax, [rbp+200h+var_260]
0x180371519  mov     [rbp+200h+var_280], rax
0x18037151d  lea     rax, [rsp+300h+var_288]
0x180371522  mov     [rbp+200h+var_278], rax
0x180371526  lea     rax, [rsp+300h+var_2AC]
0x18037152b  mov     [rbp+200h+var_270], rax
0x18037152f  movdqu  [rbp+200h+var_260], xmm0
0x180371534  call    Debugger__DataModel__ConvertException__lambda_a396cf424c129c038814b36fb23d457d___
0x180371539  xor     edi, edi
0x18037153b  mov     [rsp+300h+var_2AC], eax
0x18037153f  test    eax, eax
0x180371541  js      loc_18037174B
0x180371547  mov     r8, cs:qword_1807E5E28
0x18037154e  test    r8, r8
0x180371551  jz      loc_180371666
0x180371557  cmp     cs:qword_1807E5E10, rdi
0x18037155e  jz      loc_180371666
0x180371564  cmp     cs:qword_1807E5E40, rdi
0x18037156b  jz      loc_180371666
0x180371571  mov     rdx, [r13+1098h]
0x180371578  mov     rcx, rbx
0x18037157b  call    SetVaTranslationParams
0x180371580  test    eax, eax
0x180371582  js      loc_18037174B
0x180371588  xor     edx, edx; Val
0x18037158a  lea     rcx, [rbp+200h+Buffer]; void *
0x18037158e  mov     r8d, 208h; Size
0x180371594  call    memset
0x180371599  mov     r8d, 104h; nSize
0x18037159f  lea     rdx, [rbp+200h+Buffer]; lpBuffer
0x1803715a3  lea     rcx, aValidateHwDbgB; "VALIDATE_HW_DBG_BLOCK"
0x1803715aa  call    cs:__imp_GetEnvironmentVariableW
0x1803715b1  nop     dword ptr [rax+rax+00h]
0x1803715b6  test    eax, eax
0x1803715b8  jz      loc_1803716CD
0x1803715be  mov     r9, cs:qword_1807E5E10
0x1803715c5  lea     rax, [rsp+300h+var_290]
0x1803715ca  mov     r8d, dword ptr [rbp+200h+Register]; Register
0x1803715d1  mov     rdx, r12; VpId
0x1803715d4  mov     [rsp+300h+var_2C0], rax; __int64
0x1803715d9  mov     rcx, rbx; struct IeXdiServer3 *
0x1803715dc  lea     rax, [rsp+300h+var_2A0]
0x1803715e1  mov     [rsp+300h+var_298], rdi
0x1803715e6  mov     [rsp+300h+var_2C8], rax; __int64
0x1803715eb  lea     rax, [rsp+300h+var_298]
0x1803715f0  mov     [rsp+300h+var_2D0], rax; __int64
0x1803715f5  mov     eax, [rbp+200h+arg_28]
0x1803715fb  mov     [rsp+300h+var_2D8], eax; int
0x1803715ff  mov     [rsp+300h+var_290], rdi
0x180371604  mov     [rsp+300h+var_2A0], rdi
0x180371609  call    FindSystemAppAtAddress
0x18037160e  test    eax, eax
0x180371610  js      short loc_18037163C
0x180371612  mov     rax, cs:qword_1807E5E10
0x180371619  cmp     [rsp+300h+var_2A0], rax
0x18037161e  jnz     short loc_18037163C
0x180371620  mov     rax, [rsp+300h+var_298]
0x180371625  cmp     cs:qword_1807E5E40, rax
0x18037162c  jnz     short loc_18037163C
0x18037162e  mov     rax, [rsp+300h+var_290]
0x180371633  cmp     cs:qword_1807E5E48, rax
0x18037163a  jz      short loc_180371693
0x18037163c  lea     rcx, aInvalidHwdbgBl; "Invalid HWDbg block. Validating the HWB"...
0x180371643  call    ?VerbOut@@YAXPEBGZZ; VerbOut(ushort const *,...)
0x180371648  call    cs:__imp_GetTickCount
0x18037164f  nop     dword ptr [rax+rax+00h]
0x180371654  sub     eax, [rsp+300h+var_2A8]
0x180371658  cmp     eax, 493E0h
0x18037165d  ja      short loc_1803716C6
0x18037165f  mov     eax, 8000FFFFh
0x180371664  jmp     short loc_18037166B
0x180371666  mov     eax, 80004005h
0x18037166b  inc     r14d
0x18037166e  cmp     r14d, 100h
0x180371675  ja      loc_18037174B
0x18037167b  add     r15, 1000h
0x180371682  jmp     loc_1803713B9
0x180371687  lea     rcx, aFailedReadingH_0; "Failed reading HWDbg block link: status"...
0x18037168e  jmp     loc_18037173F
0x180371693  mov     r8d, 1; unsigned int
0x180371699  lea     rdx, aHwdbgblockheur; "HwDbgBlockHeuristicSessionSucceeded"
0x1803716a0  lea     rcx, aExdi_0; "EXDI"
0x1803716a7  call    ?FeatureUsed@FeatureUsageTracker@@SAXQEBG0K@Z; FeatureUsageTracker::FeatureUsed(ushort const * const,ushort const * const,ulong)
0x1803716ac  mov     r8, cs:qword_1807E5E40; unsigned __int64
0x1803716b3  mov     r9, rsi; struct _DBGKD_GET_VERSION64 *
0x1803716b6  mov     rdx, rbx; struct IeXdiServer3 *
0x1803716b9  mov     rcx, r13; this
0x1803716bc  call    ?GetMemKdVer@ExdiLiveKernelTargetInfo@@QEAAJPEAUIeXdiServer3@@_KPEAU_DBGKD_GET_VERSION64@@@Z; ExdiLiveKernelTargetInfo::GetMemKdVer(IeXdiServer3 *,unsigned __int64,_DBGKD_GET_VERSION64 *)
0x1803716c1  jmp     loc_18037174B
0x1803716c6  mov     eax, 80004005h
0x1803716cb  jmp     short loc_18037174B
0x1803716cd  mov     r8d, 1; unsigned int
0x1803716d3  lea     rdx, aHwdbgblockheur; "HwDbgBlockHeuristicSessionSucceeded"
0x1803716da  lea     rcx, aExdi_0; "EXDI"
0x1803716e1  call    ?FeatureUsed@FeatureUsageTracker@@SAXQEBG0K@Z; FeatureUsageTracker::FeatureUsed(ushort const * const,ushort const * const,ulong)
0x1803716e6  mov     rdx, cs:qword_1807E5E10
0x1803716ed  lea     rcx, aFoundHwdbgbloc_1; "Found HwDbgBlock.HvBaseAddress at 0x%I6"...
0x1803716f4  call    ?VerbOut@@YAXPEBGZZ; VerbOut(ushort const *,...)
0x1803716f9  mov     rdx, cs:qword_1807E5E40
0x180371700  lea     rcx, aFoundHwdbgbloc; "Found HwDbgBlock.KdVersionBlock at 0x%I"...
0x180371707  call    ?VerbOut@@YAXPEBGZZ; VerbOut(ushort const *,...)
0x18037170c  mov     rdx, cs:qword_1807E5E48
0x180371713  lea     rcx, aFoundHwdbgbloc_0; "Found HwDbgBlock.KdDebuggerDataBlock at"...
0x18037171a  call    ?VerbOut@@YAXPEBGZZ; VerbOut(ushort const *,...)
0x18037171f  jmp     short loc_1803716AC
0x180371721  lea     rcx, aHwdbgBlockTorn; "HWDbg block torn to multiple PA pages."...
0x180371728  call    ?VerbOut@@YAXPEBGZZ; VerbOut(ushort const *,...)
0x18037172d  jmp     short loc_180371746
0x18037172f  lea     rcx, aHwdbgBlockHasA; "HWDbg block has an invalid CRC field.\n"
0x180371736  jmp     short loc_180371728
0x180371738  lea     rcx, aFailedReadingH; "Failed reading HWDbg block: status=0x%x"...
0x18037173f  mov     edx, eax
0x180371741  call    ?VerbOut@@YAXPEBGZZ; VerbOut(ushort const *,...)
0x180371746  mov     eax, 8000FFFFh
0x18037174b  mov     rcx, [rbp+200h+var_40]
0x180371752  xor     rcx, rsp; StackCookie
0x180371755  call    __security_check_cookie
0x18037175a  mov     rbx, [rsp+300h+arg_18]
0x180371762  add     rsp, 2D0h
0x180371769  pop     r15
0x18037176b  pop     r14
0x18037176d  pop     r13
0x18037176f  pop     r12
0x180371771  pop     rdi
0x180371772  pop     rsi
0x180371773  pop     rbp
0x180371774  retn
```
