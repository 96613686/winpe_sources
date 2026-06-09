# Dhcpv6InitGlobalData

- ea: `0x180018e7c`
- end: `0x180018f4c`
- name: `Dhcpv6InitGlobalData`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001c260`

## callees

- `0x180018e7c`
- `0x180018f54`
- `0x18002d7d8`
- `0x1800335c4`
- `0x180033900`
- `0x180033de4`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180018e8c`
- `RPCRT4!UuidCreate` at `0x180018e8c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180018f2b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180018f2b`

## pseudocode

```c
__int64 Dhcpv6InitGlobalData()
{
  unsigned int v0; // eax
  int IsXBOXSystem; // eax
  const char *v2; // rcx
  HANDLE EventW; // rax

  DhcpInitializeGlobalVelocityData();
  v0 = UuidCreate(&Dhcpv6GlobalBootGuid);
  if ( v0 && (xmmword_1800423E0 & 2) != 0 )
    WPP_SF_d(1025, 152, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, v0);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_(1028, 10, WPP_c8e3512263513ba27315d9131f42c6f1_Traceguids);
  IsXBOXSystem = DhcpIsXBOXSystem();
  v2 = "MSFT 5.0 XBOX";
  if ( !IsXBOXSystem )
    v2 = "MSFT 5.0";
  Src = (void *)v2;
  word_18004267C = IsXBOXSystem != 0 ? 13 : 8;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_s();
  EventW = CreateEventW(0, 1, 0, 0);
  ++Dhcpv6GlobalInit;
  Dhcpv6GlobalHostStatus = EventW;
  return 0;
}

```

## disassembly

```asm
0x180018e7c  sub     rsp, 28h
0x180018e80  call    DhcpInitializeGlobalVelocityData
0x180018e85  lea     rcx, Dhcpv6GlobalBootGuid; Uuid
0x180018e8c  call    cs:__imp_UuidCreate
0x180018e93  nop     dword ptr [rax+rax+00h]
0x180018e98  test    eax, eax
0x180018e9a  jz      short loc_180018EBE
0x180018e9c  test    byte ptr cs:xmmword_1800423E0, 2
0x180018ea3  jz      short loc_180018EBE
0x180018ea5  mov     edx, 98h
0x180018eaa  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x180018eb1  mov     ecx, 401h
0x180018eb6  mov     r9d, eax
0x180018eb9  call    WPP_SF_d
0x180018ebe  test    byte ptr cs:xmmword_1800423E0, 10h
0x180018ec5  jz      short loc_180018EDD
0x180018ec7  mov     edx, 0Ah
0x180018ecc  lea     r8, WPP_c8e3512263513ba27315d9131f42c6f1_Traceguids
0x180018ed3  mov     ecx, 404h
0x180018ed8  call    WPP_SF_
0x180018edd  call    DhcpIsXBOXSystem
0x180018ee2  test    eax, eax
0x180018ee4  lea     rdx, aMsft50; "MSFT 5.0"
0x180018eeb  lea     rcx, aMsft50Xbox; "MSFT 5.0 XBOX"
0x180018ef2  cmovz   rcx, rdx
0x180018ef6  neg     eax
0x180018ef8  mov     cs:Src, rcx
0x180018eff  sbb     ax, ax
0x180018f02  and     ax, 5
0x180018f06  add     ax, 8
0x180018f0a  test    byte ptr cs:xmmword_1800423E0, 10h
0x180018f11  mov     cs:word_18004267C, ax
0x180018f18  jz      short loc_180018F1F
0x180018f1a  call    WPP_SF_s
0x180018f1f  xor     r9d, r9d; lpName
0x180018f22  xor     r8d, r8d; bInitialState
0x180018f25  xor     ecx, ecx; lpEventAttributes
0x180018f27  lea     edx, [r9+1]; bManualReset
0x180018f2b  call    cs:__imp_CreateEventW
0x180018f32  nop     dword ptr [rax+rax+00h]
0x180018f37  inc     cs:Dhcpv6GlobalInit
0x180018f3d  mov     cs:Dhcpv6GlobalHostStatus, rax
0x180018f44  xor     eax, eax
0x180018f46  add     rsp, 28h
0x180018f4a  retn
```
