# PerfDiagSuspend::GetScenarioArchivePath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,PerfDiagSuspend::CPowerTransitionType)

- ea: `0x18008eb44`
- end: `0x18008ebca`
- name: `?GetScenarioArchivePath@PerfDiagSuspend@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@W4CPowerTransitionType@1@@Z`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18008e668`

## callees

- `0x18001890c`
- `0x180019370`
- `0x18008dc04`
- `0x18008eb44`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18008eb5d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18008eb78`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18008eb5d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18008eb78`

## pseudocode

```c
__int64 __fastcall PerfDiagSuspend::GetScenarioArchivePath(__int64 a1, unsigned int a2)
{
  __int64 v2; // rsi
  UINT SystemDirectoryW; // eax
  UINT v5; // edi
  WCHAR *BufferSetLength; // rax
  UINT v7; // r14d
  UINT v8; // eax
  ATL::CAtlException *v10; // [rsp+20h] [rbp-38h] BYREF

  v2 = (int)a2;
  if ( a2 > 2 )
    return 2147942487LL;
  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  try
  {
    v5 = SystemDirectoryW;
    BufferSetLength = (WCHAR *)ATL::CSimpleStringT<unsigned short,0>::GetBufferSetLength(a1, SystemDirectoryW);
    v7 = v5 - 1;
    v8 = GetSystemDirectoryW(BufferSetLength, v5);
  }
  catch ( ATL::CAtlException *v10 )
  {
    return *(unsigned int *)v10;
  }
  if ( v7 != v8 )
    return 2147549183LL;
  ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, v7);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    a1,
    L"\\WDI\\SuspendPerformanceDiagnostics_SystemData_%ws.bin",
    off_1800DD238[v2]);
  return 0;
}

```

## disassembly

```asm
0x18008eb44  push    rbx
0x18008eb46  push    rsi
0x18008eb47  push    rdi
0x18008eb48  push    r14
0x18008eb4a  sub     rsp, 38h
0x18008eb4e  movsxd  rsi, edx
0x18008eb51  mov     rbx, rcx
0x18008eb54  cmp     esi, 2
0x18008eb57  ja      short loc_18008EBBA
0x18008eb59  xor     edx, edx; uSize
0x18008eb5b  xor     ecx, ecx; lpBuffer
0x18008eb5d  call    cs:__imp_GetSystemDirectoryW
0x18008eb63  mov     edi, eax
0x18008eb65  mov     edx, eax
0x18008eb67  mov     rcx, rbx
0x18008eb6a  call    ?GetBufferSetLength@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::GetBufferSetLength(int)
0x18008eb6f  lea     r14d, [rdi-1]
0x18008eb73  mov     edx, edi; uSize
0x18008eb75  mov     rcx, rax; lpBuffer
0x18008eb78  call    cs:__imp_GetSystemDirectoryW
0x18008eb7e  cmp     r14d, eax
0x18008eb81  jz      short loc_18008EB8A
0x18008eb83  mov     eax, 8000FFFFh
0x18008eb88  jmp     short loc_18008EBBF
0x18008eb8a  mov     edx, r14d
0x18008eb8d  mov     rcx, rbx
0x18008eb90  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x18008eb95  lea     rax, off_1800DD238; "S3"
0x18008eb9c  mov     r8, [rax+rsi*8]
0x18008eba0  lea     rdx, aWdiSuspendperf; "\\WDI\\SuspendPerformanceDiagnostics_Sy"...
0x18008eba7  mov     rcx, rbx
0x18008ebaa  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18008ebaf  nop
0x18008ebb0  xor     eax, eax
0x18008ebb2  jmp     short loc_18008EBBF
0x18008ebb4  mov     eax, [rsp+58h+arg_8]
0x18008ebb8  jmp     short loc_18008EBBF
0x18008ebba  mov     eax, 80070057h
0x18008ebbf  add     rsp, 38h
0x18008ebc3  pop     r14
0x18008ebc5  pop     rdi
0x18008ebc6  pop     rsi
0x18008ebc7  pop     rbx
0x18008ebc8  retn
```
