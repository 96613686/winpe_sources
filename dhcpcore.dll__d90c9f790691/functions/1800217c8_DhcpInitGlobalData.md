# DhcpInitGlobalData

- ea: `0x1800217c8`
- end: `0x18002189c`
- name: `DhcpInitGlobalData`
- size: `212`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180022350`

## callees

- `0x1800217c8`
- `0x180043ecc`
- `0x180044cb8`
- `0x18004d1e0`
- `0x18004d9e8`
- `0x18004e0c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021882`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021882`
- `RPCRT4!UuidCreate` at `0x1800217d8`
- `RPCRT4!UuidCreate` at `0x1800217d8`

## pseudocode

```c
__int64 DhcpInitGlobalData()
{
  unsigned int v0; // eax
  int IsXBOXSystem; // eax
  const char *v2; // r9
  HANDLE EventW; // rax

  DhcpInitializeGlobalVelocityData();
  v0 = UuidCreate(&DhcpGlobalBootGuid);
  if ( v0 && (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_d(1025, 219, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v0);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 10, WPP_c8e3512263513ba27315d9131f42c6f1_Traceguids);
  IsXBOXSystem = DhcpIsXBOXSystem();
  v2 = "MSFT 5.0 XBOX";
  if ( !IsXBOXSystem )
    v2 = "MSFT 5.0";
  Src = (void *)v2;
  word_18006188C = IsXBOXSystem != 0 ? 13 : 8;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_s(1028, 11, WPP_c8e3512263513ba27315d9131f42c6f1_Traceguids, v2);
  EventW = CreateEventW(0, 1, 0, 0);
  ++DhcpGlobalInit;
  DhcpGlobalHostStatus = EventW;
  return 0;
}

```

## disassembly

```asm
0x1800217c8  sub     rsp, 28h
0x1800217cc  call    DhcpInitializeGlobalVelocityData
0x1800217d1  lea     rcx, DhcpGlobalBootGuid; Uuid
0x1800217d8  call    cs:__imp_UuidCreate
0x1800217de  test    eax, eax
0x1800217e0  jz      short loc_180021804
0x1800217e2  test    byte ptr cs:xmmword_1800616A0, 2
0x1800217e9  jz      short loc_180021804
0x1800217eb  mov     edx, 0DBh
0x1800217f0  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x1800217f7  mov     ecx, 401h
0x1800217fc  mov     r9d, eax
0x1800217ff  call    WPP_SF_d
0x180021804  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002180b  jz      short loc_180021823
0x18002180d  mov     edx, 0Ah
0x180021812  lea     r8, WPP_c8e3512263513ba27315d9131f42c6f1_Traceguids
0x180021819  mov     ecx, 404h
0x18002181e  call    WPP_SF_
0x180021823  call    DhcpIsXBOXSystem
0x180021828  test    eax, eax
0x18002182a  lea     rdx, aMsft50; "MSFT 5.0"
0x180021831  lea     r9, aMsft50Xbox; "MSFT 5.0 XBOX"
0x180021838  cmovz   r9, rdx
0x18002183c  neg     eax
0x18002183e  mov     cs:Src, r9
0x180021845  sbb     ax, ax
0x180021848  and     ax, 5
0x18002184c  add     ax, 8
0x180021850  test    byte ptr cs:xmmword_1800616A0, 10h
0x180021857  mov     cs:word_18006188C, ax
0x18002185e  jz      short loc_180021876
0x180021860  mov     edx, 0Bh
0x180021865  lea     r8, WPP_c8e3512263513ba27315d9131f42c6f1_Traceguids
0x18002186c  mov     ecx, 404h
0x180021871  call    WPP_SF_s
0x180021876  xor     r9d, r9d; lpName
0x180021879  xor     r8d, r8d; bInitialState
0x18002187c  xor     ecx, ecx; lpEventAttributes
0x18002187e  lea     edx, [r9+1]; bManualReset
0x180021882  call    cs:__imp_CreateEventW
0x180021888  inc     cs:DhcpGlobalInit
0x18002188e  mov     cs:DhcpGlobalHostStatus, rax
0x180021895  xor     eax, eax
0x180021897  add     rsp, 28h
0x18002189b  retn
```
