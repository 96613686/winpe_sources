# PerfDiagBoot::Impl::getUserScenarioArchivePath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *)

- ea: `0x180041a40`
- end: `0x180041b1e`
- name: `?getUserScenarioArchivePath@Impl@PerfDiagBoot@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z`
- size: `222`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800279d8`

## callees

- `0x18001890c`
- `0x180019370`
- `0x180041a40`
- `0x18008dc04`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180041a57`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180041a71`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180041a57`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180041a71`

## pseudocode

```c
__int64 __fastcall PerfDiagBoot::Impl::getUserScenarioArchivePath(__int64 a1, __int64 a2)
{
  UINT SystemDirectoryW; // ebx
  WCHAR *BufferSetLength; // rax
  int v7; // [rsp+20h] [rbp-88h]
  int v8; // [rsp+28h] [rbp-80h]
  int v9; // [rsp+30h] [rbp-78h]
  int v10; // [rsp+38h] [rbp-70h]
  int v11; // [rsp+40h] [rbp-68h]
  int v12; // [rsp+48h] [rbp-60h]
  int v13; // [rsp+50h] [rbp-58h]
  int v14; // [rsp+58h] [rbp-50h]
  int v15; // [rsp+60h] [rbp-48h]
  ATL::CAtlException *v16; // [rsp+70h] [rbp-38h] BYREF

  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  BufferSetLength = (WCHAR *)ATL::CSimpleStringT<unsigned short,0>::GetBufferSetLength(a1, SystemDirectoryW);
  if ( SystemDirectoryW - 1 != GetSystemDirectoryW(BufferSetLength, SystemDirectoryW) )
    return 2147549183LL;
  ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, SystemDirectoryW - 1);
  v15 = 93;
  v14 = 72;
  v13 = 144;
  v12 = 170;
  v11 = 47;
  v10 = 23;
  v9 = 156;
  v8 = 168;
  v7 = 19935;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    a1,
    L"\\WDI\\{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}\\",
    2252548619LL,
    15485,
    v7,
    v8,
    v9,
    v10,
    v11,
    v12,
    v13,
    v14,
    v15);
  try
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      a1,
      L"%ws_UserData.bin",
      a2);
  }
  catch ( ATL::CAtlException *v16 )
  {
    return *(unsigned int *)v16;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    a1,
    L"%ws_UserData.bin",
    a2);
}

```

## disassembly

```asm
0x180041a40  push    rbx
0x180041a42  push    rsi
0x180041a43  push    rdi
0x180041a44  push    r14
0x180041a46  sub     rsp, 88h
0x180041a4d  mov     r14, rdx
0x180041a50  mov     rdi, rcx
0x180041a53  xor     edx, edx; uSize
0x180041a55  xor     ecx, ecx; lpBuffer
0x180041a57  call    cs:__imp_GetSystemDirectoryW
0x180041a5d  mov     ebx, eax
0x180041a5f  lea     esi, [rax-1]
0x180041a62  mov     edx, eax
0x180041a64  mov     rcx, rdi
0x180041a67  call    ?GetBufferSetLength@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::GetBufferSetLength(int)
0x180041a6c  mov     rcx, rax; lpBuffer
0x180041a6f  mov     edx, ebx; uSize
0x180041a71  call    cs:__imp_GetSystemDirectoryW
0x180041a77  cmp     esi, eax
0x180041a79  jz      short loc_180041A85
0x180041a7b  mov     eax, 8000FFFFh
0x180041a80  jmp     loc_180041B11
0x180041a85  mov     edx, esi
0x180041a87  mov     rcx, rdi
0x180041a8a  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180041a8f  mov     [rsp+0A8h+var_48], 5Dh ; ']'
0x180041a97  mov     [rsp+0A8h+var_50], 48h ; 'H'
0x180041a9f  mov     [rsp+0A8h+var_58], 90h
0x180041aa7  mov     [rsp+0A8h+var_60], 0AAh
0x180041aaf  mov     [rsp+0A8h+var_68], 2Fh ; '/'
0x180041ab7  mov     [rsp+0A8h+var_70], 17h
0x180041abf  mov     [rsp+0A8h+var_78], 9Ch
0x180041ac7  mov     [rsp+0A8h+var_80], 0A8h
0x180041acf  mov     [rsp+0A8h+var_88], 4DDFh
0x180041ad7  mov     r9d, 3C7Dh
0x180041add  mov     r8d, 86432A0Bh
0x180041ae3  lea     rdx, aWdi08x04x04x02_0; "\\WDI\\{%08x-%04x-%04x-%02x%02x-%02x%02"...
0x180041aea  mov     rcx, rdi
0x180041aed  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180041af2  nop
0x180041af3  mov     r8, r14
0x180041af6  lea     rdx, aWsUserdataBin; "%ws_UserData.bin"
0x180041afd  mov     rcx, rdi
0x180041b00  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180041b05  nop
0x180041b06  xor     eax, eax
0x180041b08  jmp     short loc_180041B11
0x180041b0a  mov     eax, [rsp+0A8h+arg_10]
0x180041b11  add     rsp, 88h
0x180041b18  pop     r14
0x180041b1a  pop     rdi
0x180041b1b  pop     rsi
0x180041b1c  pop     rbx
0x180041b1d  retn
```
