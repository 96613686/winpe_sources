# PerfDiagBoot::Impl::getSystemScenarioArchivePath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180041e28`
- end: `0x180041e94`
- name: `?getSystemScenarioArchivePath@Impl@PerfDiagBoot@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `108`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800279d8`

## callees

- `0x18001890c`
- `0x180019370`
- `0x180041e28`
- `0x1800ae71c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180041e3e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180041e58`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180041e3e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180041e58`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PerfDiagBoot::Impl::getSystemScenarioArchivePath(__int64 a1)
{
  UINT SystemDirectoryW; // ebx
  WCHAR *BufferSetLength; // rax

  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  BufferSetLength = (WCHAR *)ATL::CSimpleStringT<unsigned short,0>::GetBufferSetLength(a1, SystemDirectoryW);
  if ( SystemDirectoryW - 1 != GetSystemDirectoryW(BufferSetLength, SystemDirectoryW) )
    return 2147549183LL;
  ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, SystemDirectoryW - 1);
  ATL::CSimpleStringT<unsigned short,0>::Append(a1, L"\\WDI\\BootPerformanceDiagnostics_SystemData.bin");
  return 0;
}

```

## disassembly

```asm
0x180041e28  mov     [rsp+arg_0], rbx
0x180041e2d  mov     [rsp+arg_8], rsi
0x180041e32  push    rdi
0x180041e33  sub     rsp, 20h
0x180041e37  mov     rdi, rcx
0x180041e3a  xor     edx, edx; uSize
0x180041e3c  xor     ecx, ecx; lpBuffer
0x180041e3e  call    cs:__imp_GetSystemDirectoryW
0x180041e44  mov     edx, eax
0x180041e46  mov     rcx, rdi
0x180041e49  mov     ebx, eax
0x180041e4b  lea     esi, [rax-1]
0x180041e4e  call    ?GetBufferSetLength@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::GetBufferSetLength(int)
0x180041e53  mov     rcx, rax; lpBuffer
0x180041e56  mov     edx, ebx; uSize
0x180041e58  call    cs:__imp_GetSystemDirectoryW
0x180041e5e  cmp     esi, eax
0x180041e60  jz      short loc_180041E69
0x180041e62  mov     eax, 8000FFFFh
0x180041e67  jmp     short loc_180041E84
0x180041e69  mov     edx, esi
0x180041e6b  mov     rcx, rdi
0x180041e6e  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180041e73  lea     rdx, aWdiBootperform; "\\WDI\\BootPerformanceDiagnostics_Syste"...
0x180041e7a  mov     rcx, rdi
0x180041e7d  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x180041e82  xor     eax, eax
0x180041e84  mov     rbx, [rsp+28h+arg_0]
0x180041e89  mov     rsi, [rsp+28h+arg_8]
0x180041e8e  add     rsp, 20h
0x180041e92  pop     rdi
0x180041e93  retn
```
