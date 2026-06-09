# UlStartDataModule

- ea: `0x1400d85b0`
- end: `0x1400d87c9`
- name: `UlStartDataModule`
- size: `537`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x1400d85b0`
- `0x1400fe974`
- `0x140128d6c`
- `0x140131e20`
- `0x1401c3f58`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x1400d8628`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d864c`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d866a`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d868f`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d8744`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d875c`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d8628`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d864c`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d866a`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d868f`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d8744`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d875c`

## pseudocode

```c
__int64 UlStartDataModule()
{
  int v0; // eax
  int v1; // edx
  int v2; // ebx
  int v3; // eax
  int v4; // ecx
  __int64 result; // rax
  int v6; // [rsp+30h] [rbp+8h] BYREF

  if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
    WPP_SF_(1038, 148, WPP_3bc569ebedc33674d1577199996181a5_Traceguids);
  if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
    WPP_SF_d(1038, 149, WPP_3bc569ebedc33674d1577199996181a5_Traceguids, 160);
  LODWORD(UlVariableHeaderSize) = 160;
  UlH3ExtraHeaderCount = 4;
  UlH3DefaultPairSize = 480;
  UlFixedHeadersMdlLength = (MmSizeOfMdl((PVOID)0xFFF, 0x200u) + 7) & 0xFFFFFFF8;
  UlVariableHeadersMdlLength = (MmSizeOfMdl((PVOID)0xFFF, (unsigned int)UlVariableHeaderSize) + 7) & 0xFFFFFFF8;
  UlContentMdlLength = (MmSizeOfMdl((PVOID)0xFFF, 0x40000u) + 7) & 0xFFFFFFF8;
  v0 = MmSizeOfMdl((PVOID)0xFFF, (unsigned int)(UlVariableHeaderSize + 2560));
  LODWORD(UxTpChunkTrackerSize) = 1056;
  LODWORD(UxTpTransmitPacketSize) = 1392;
  UlResponseBufferSize = UlVariableHeaderSize + 2208;
  v1 = 2 * (UlH3DefaultPairSize + UlVariableHeaderSize);
  UlQuicSendFastTrackerExtraSize = 320;
  UlAuxiliaryMdlLength = (v0 + 7) & 0xFFFFFFF8;
  UlQuicSendFastTrackerSize = 544;
  UlHeaderBlockSize = 1056;
  g_UlInternalRequestSize = 3506;
  g_UlCacheTrackerSize = (UlFixedHeadersMdlLength + 871 + UlVariableHeadersMdlLength + v1 + UlContentMdlLength)
                       & 0xFFFFFFF8;
  g_UlFastTrackerSize = (UlAuxiliaryMdlLength + v1 + 2 * UlAuxiliaryMdlLength + UlContentMdlLength + 3559) & 0xFFFFFFF8;
  v2 = (MmSizeOfMdl((PVOID)0xFFF, 0x13u) + 7) & 0xFFFFFFF8;
  g_UlRangeCacheFastPathVarHdrMdlSize = MmSizeOfMdl((PVOID)0xFFF, 0x6Eu);
  g_UlRangeCacheTrackerLookasideSize = v2 + g_UlRangeCacheFastPathVarHdrMdlSize + 241;
  g_UlLogBufferSize = UlInitializeLogBufferGranularity();
  UxSslInitializeLookasideSizes();
  v6 = 0;
  v3 = UlCalculateFastForwardDataContextSize(16, &v6);
  v4 = v6;
  if ( v3 < 0 )
    v4 = 256;
  result = 0;
  UlFastForwardDataContextSize = v4;
  return result;
}

```

## disassembly

```asm
0x1400d85b0  mov     [rsp+arg_8], rbx
0x1400d85b5  mov     [rsp+arg_10], rsi
0x1400d85ba  push    rdi
0x1400d85bb  sub     rsp, 20h
0x1400d85bf  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x1400d85c6  mov     ebx, 40Eh
0x1400d85cb  jz      short loc_1400D85E0
0x1400d85cd  mov     edx, 94h
0x1400d85d2  lea     r8, WPP_3bc569ebedc33674d1577199996181a5_Traceguids
0x1400d85d9  mov     ecx, ebx
0x1400d85db  call    WPP_SF_
0x1400d85e0  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x1400d85e7  mov     edi, 0A0h
0x1400d85ec  jz      short loc_1400D8602
0x1400d85ee  lea     edx, [rdi-0Bh]
0x1400d85f1  mov     ecx, ebx
0x1400d85f3  mov     r9d, edi
0x1400d85f6  lea     r8, WPP_3bc569ebedc33674d1577199996181a5_Traceguids
0x1400d85fd  call    WPP_SF_d
0x1400d8602  mov     esi, 0FFFh
0x1400d8607  mov     cs:UlVariableHeaderSize, edi
0x1400d860d  mov     ecx, esi; Base
0x1400d860f  mov     cs:UlH3ExtraHeaderCount, 4
0x1400d8619  mov     edx, 200h; Length
0x1400d861e  mov     cs:UlH3DefaultPairSize, 1E0h
0x1400d8628  call    cs:__imp_MmSizeOfMdl
0x1400d862f  nop     dword ptr [rax+rax+00h]
0x1400d8634  mov     edx, cs:UlVariableHeaderSize; Length
0x1400d863a  mov     edi, 0FFFFFFF8h
0x1400d863f  add     eax, 7
0x1400d8642  mov     ecx, esi; Base
0x1400d8644  and     eax, edi
0x1400d8646  mov     cs:UlFixedHeadersMdlLength, eax
0x1400d864c  call    cs:__imp_MmSizeOfMdl
0x1400d8653  nop     dword ptr [rax+rax+00h]
0x1400d8658  mov     edx, 40000h; Length
0x1400d865d  mov     ecx, esi; Base
0x1400d865f  add     eax, 7
0x1400d8662  and     eax, edi
0x1400d8664  mov     cs:UlVariableHeadersMdlLength, eax
0x1400d866a  call    cs:__imp_MmSizeOfMdl
0x1400d8671  nop     dword ptr [rax+rax+00h]
0x1400d8676  mov     edx, cs:UlVariableHeaderSize
0x1400d867c  mov     ecx, esi; Base
0x1400d867e  add     eax, 7
0x1400d8681  add     edx, 0A00h; Length
0x1400d8687  and     eax, edi
0x1400d8689  mov     cs:UlContentMdlLength, eax
0x1400d868f  call    cs:__imp_MmSizeOfMdl
0x1400d8696  nop     dword ptr [rax+rax+00h]
0x1400d869b  mov     edx, cs:UlVariableHeaderSize
0x1400d86a1  mov     r10d, 420h
0x1400d86a7  mov     r8d, cs:UlContentMdlLength
0x1400d86ae  mov     cs:UxTpChunkTrackerSize, r10d
0x1400d86b5  lea     r9d, [rax+7]
0x1400d86b9  mov     cs:UxTpTransmitPacketSize, 570h
0x1400d86c3  mov     eax, cs:UlFixedHeadersMdlLength
0x1400d86c9  lea     ecx, [rdx+8A0h]
0x1400d86cf  add     edx, cs:UlH3DefaultPairSize
0x1400d86d5  add     eax, 367h
0x1400d86da  mov     cs:UlResponseBufferSize, ecx
0x1400d86e0  add     edx, edx
0x1400d86e2  and     r9d, edi
0x1400d86e5  mov     cs:UlQuicSendFastTrackerExtraSize, 140h
0x1400d86ef  mov     cs:UlAuxiliaryMdlLength, r9d
0x1400d86f6  mov     cs:UlQuicSendFastTrackerSize, 220h
0x1400d8700  lea     ecx, [rdx+r8]
0x1400d8704  mov     cs:UlHeaderBlockSize, r10d
0x1400d870b  add     ecx, cs:UlVariableHeadersMdlLength
0x1400d8711  add     ecx, eax
0x1400d8713  mov     cs:g_UlInternalRequestSize, 0DB2h
0x1400d871d  and     ecx, edi
0x1400d871f  lea     eax, [r8+0DE7h]
0x1400d8726  mov     cs:g_UlCacheTrackerSize, ecx
0x1400d872c  lea     ecx, [rdx+r9*2]
0x1400d8730  add     ecx, r9d
0x1400d8733  mov     edx, 13h; Length
0x1400d8738  add     eax, ecx
0x1400d873a  mov     ecx, esi; Base
0x1400d873c  and     eax, edi
0x1400d873e  mov     cs:g_UlFastTrackerSize, eax
0x1400d8744  call    cs:__imp_MmSizeOfMdl
0x1400d874b  nop     dword ptr [rax+rax+00h]
0x1400d8750  mov     edx, 6Eh ; 'n'; Length
0x1400d8755  mov     ecx, esi; Base
0x1400d8757  lea     ebx, [rax+7]
0x1400d875a  and     ebx, edi
0x1400d875c  call    cs:__imp_MmSizeOfMdl
0x1400d8763  nop     dword ptr [rax+rax+00h]
0x1400d8768  mov     cs:g_UlRangeCacheFastPathVarHdrMdlSize, eax
0x1400d876e  add     eax, 0F1h
0x1400d8773  add     eax, ebx
0x1400d8775  mov     cs:g_UlRangeCacheTrackerLookasideSize, eax
0x1400d877b  call    UlInitializeLogBufferGranularity
0x1400d8780  mov     cs:g_UlLogBufferSize, eax
0x1400d8786  call    UxSslInitializeLookasideSizes
0x1400d878b  lea     rdx, [rsp+28h+arg_0]
0x1400d8790  mov     [rsp+28h+arg_0], 0
0x1400d8798  mov     ecx, 10h
0x1400d879d  call    UlCalculateFastForwardDataContextSize
0x1400d87a2  mov     ecx, [rsp+28h+arg_0]
0x1400d87a6  test    eax, eax
0x1400d87a8  mov     edx, 100h
0x1400d87ad  cmovs   ecx, edx
0x1400d87b0  xor     eax, eax
0x1400d87b2  mov     cs:UlFastForwardDataContextSize, ecx
0x1400d87b8  mov     rbx, [rsp+28h+arg_8]
0x1400d87bd  mov     rsi, [rsp+28h+arg_10]
0x1400d87c2  add     rsp, 20h
0x1400d87c6  pop     rdi
0x1400d87c7  retn
```
