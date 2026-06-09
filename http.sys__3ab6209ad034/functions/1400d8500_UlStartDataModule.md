# UlStartDataModule

- ea: `0x1400d8500`
- end: `0x1400d8719`
- name: `UlStartDataModule`
- size: `537`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x1400d8500`
- `0x1400fe9a4`
- `0x140128e5c`
- `0x140131f10`
- `0x1401c3f58`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x1400d8578`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d859c`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d85ba`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d85df`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d8694`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d86ac`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d8578`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d859c`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d85ba`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d85df`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d8694`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d86ac`

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
0x1400d8500  mov     [rsp+arg_8], rbx
0x1400d8505  mov     [rsp+arg_10], rsi
0x1400d850a  push    rdi
0x1400d850b  sub     rsp, 20h
0x1400d850f  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x1400d8516  mov     ebx, 40Eh
0x1400d851b  jz      short loc_1400D8530
0x1400d851d  mov     edx, 94h
0x1400d8522  lea     r8, WPP_3bc569ebedc33674d1577199996181a5_Traceguids
0x1400d8529  mov     ecx, ebx
0x1400d852b  call    WPP_SF_
0x1400d8530  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x1400d8537  mov     edi, 0A0h
0x1400d853c  jz      short loc_1400D8552
0x1400d853e  lea     edx, [rdi-0Bh]
0x1400d8541  mov     ecx, ebx
0x1400d8543  mov     r9d, edi
0x1400d8546  lea     r8, WPP_3bc569ebedc33674d1577199996181a5_Traceguids
0x1400d854d  call    WPP_SF_d
0x1400d8552  mov     esi, 0FFFh
0x1400d8557  mov     cs:UlVariableHeaderSize, edi
0x1400d855d  mov     ecx, esi; Base
0x1400d855f  mov     cs:UlH3ExtraHeaderCount, 4
0x1400d8569  mov     edx, 200h; Length
0x1400d856e  mov     cs:UlH3DefaultPairSize, 1E0h
0x1400d8578  call    cs:__imp_MmSizeOfMdl
0x1400d857f  nop     dword ptr [rax+rax+00h]
0x1400d8584  mov     edx, cs:UlVariableHeaderSize; Length
0x1400d858a  mov     edi, 0FFFFFFF8h
0x1400d858f  add     eax, 7
0x1400d8592  mov     ecx, esi; Base
0x1400d8594  and     eax, edi
0x1400d8596  mov     cs:UlFixedHeadersMdlLength, eax
0x1400d859c  call    cs:__imp_MmSizeOfMdl
0x1400d85a3  nop     dword ptr [rax+rax+00h]
0x1400d85a8  mov     edx, 40000h; Length
0x1400d85ad  mov     ecx, esi; Base
0x1400d85af  add     eax, 7
0x1400d85b2  and     eax, edi
0x1400d85b4  mov     cs:UlVariableHeadersMdlLength, eax
0x1400d85ba  call    cs:__imp_MmSizeOfMdl
0x1400d85c1  nop     dword ptr [rax+rax+00h]
0x1400d85c6  mov     edx, cs:UlVariableHeaderSize
0x1400d85cc  mov     ecx, esi; Base
0x1400d85ce  add     eax, 7
0x1400d85d1  add     edx, 0A00h; Length
0x1400d85d7  and     eax, edi
0x1400d85d9  mov     cs:UlContentMdlLength, eax
0x1400d85df  call    cs:__imp_MmSizeOfMdl
0x1400d85e6  nop     dword ptr [rax+rax+00h]
0x1400d85eb  mov     edx, cs:UlVariableHeaderSize
0x1400d85f1  mov     r10d, 420h
0x1400d85f7  mov     r8d, cs:UlContentMdlLength
0x1400d85fe  mov     cs:UxTpChunkTrackerSize, r10d
0x1400d8605  lea     r9d, [rax+7]
0x1400d8609  mov     cs:UxTpTransmitPacketSize, 570h
0x1400d8613  mov     eax, cs:UlFixedHeadersMdlLength
0x1400d8619  lea     ecx, [rdx+8A0h]
0x1400d861f  add     edx, cs:UlH3DefaultPairSize
0x1400d8625  add     eax, 367h
0x1400d862a  mov     cs:UlResponseBufferSize, ecx
0x1400d8630  add     edx, edx
0x1400d8632  and     r9d, edi
0x1400d8635  mov     cs:UlQuicSendFastTrackerExtraSize, 140h
0x1400d863f  mov     cs:UlAuxiliaryMdlLength, r9d
0x1400d8646  mov     cs:UlQuicSendFastTrackerSize, 220h
0x1400d8650  lea     ecx, [rdx+r8]
0x1400d8654  mov     cs:UlHeaderBlockSize, r10d
0x1400d865b  add     ecx, cs:UlVariableHeadersMdlLength
0x1400d8661  add     ecx, eax
0x1400d8663  mov     cs:g_UlInternalRequestSize, 0DB2h
0x1400d866d  and     ecx, edi
0x1400d866f  lea     eax, [r8+0DE7h]
0x1400d8676  mov     cs:g_UlCacheTrackerSize, ecx
0x1400d867c  lea     ecx, [rdx+r9*2]
0x1400d8680  add     ecx, r9d
0x1400d8683  mov     edx, 13h; Length
0x1400d8688  add     eax, ecx
0x1400d868a  mov     ecx, esi; Base
0x1400d868c  and     eax, edi
0x1400d868e  mov     cs:g_UlFastTrackerSize, eax
0x1400d8694  call    cs:__imp_MmSizeOfMdl
0x1400d869b  nop     dword ptr [rax+rax+00h]
0x1400d86a0  mov     edx, 6Eh ; 'n'; Length
0x1400d86a5  mov     ecx, esi; Base
0x1400d86a7  lea     ebx, [rax+7]
0x1400d86aa  and     ebx, edi
0x1400d86ac  call    cs:__imp_MmSizeOfMdl
0x1400d86b3  nop     dword ptr [rax+rax+00h]
0x1400d86b8  mov     cs:g_UlRangeCacheFastPathVarHdrMdlSize, eax
0x1400d86be  add     eax, 0F1h
0x1400d86c3  add     eax, ebx
0x1400d86c5  mov     cs:g_UlRangeCacheTrackerLookasideSize, eax
0x1400d86cb  call    UlInitializeLogBufferGranularity
0x1400d86d0  mov     cs:g_UlLogBufferSize, eax
0x1400d86d6  call    UxSslInitializeLookasideSizes
0x1400d86db  lea     rdx, [rsp+28h+arg_0]
0x1400d86e0  mov     [rsp+28h+arg_0], 0
0x1400d86e8  mov     ecx, 10h
0x1400d86ed  call    UlCalculateFastForwardDataContextSize
0x1400d86f2  mov     ecx, [rsp+28h+arg_0]
0x1400d86f6  test    eax, eax
0x1400d86f8  mov     edx, 100h
0x1400d86fd  cmovs   ecx, edx
0x1400d8700  xor     eax, eax
0x1400d8702  mov     cs:UlFastForwardDataContextSize, ecx
0x1400d8708  mov     rbx, [rsp+28h+arg_8]
0x1400d870d  mov     rsi, [rsp+28h+arg_10]
0x1400d8712  add     rsp, 20h
0x1400d8716  pop     rdi
0x1400d8717  retn
```
