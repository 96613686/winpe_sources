# PcFilterRequestComplete

- ea: `0x140001a90`
- end: `0x140001b78`
- name: `PcFilterRequestComplete`
- size: `232`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001a90`
- `0x140001bf0`

## import_xrefs

- `NDIS!NdisFOidRequestComplete` at `0x140001aea`
- `NDIS!NdisFOidRequestComplete` at `0x140001aea`
- `NDIS!NdisFreeCloneOidRequest` at `0x140001ad4`
- `NDIS!NdisFreeCloneOidRequest` at `0x140001ad4`
- `NDIS!NdisSetEvent` at `0x140001b1d`
- `NDIS!NdisSetEvent` at `0x140001b1d`

## pseudocode

```c
void __fastcall PcFilterRequestComplete(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // rdi
  NDIS_STATUS v4; // esi
  int v7; // ecx
  struct _NDIS_EVENT *v8; // rcx
  int v9; // ecx

  v3 = *(_QWORD *)(a2 + 216);
  v4 = a3;
  if ( !v3 )
  {
    *(_DWORD *)(a2 + 272) = a3;
    v8 = (struct _NDIS_EVENT *)(a2 + 248);
LABEL_8:
    NdisSetEvent(v8);
    return;
  }
  v7 = *(_DWORD *)(v3 + 4);
  if ( v7 == 2 || !v7 )
  {
    *(_DWORD *)(v3 + 52) = *(_DWORD *)(a2 + 52);
    goto LABEL_4;
  }
  v9 = v7 - 1;
  if ( !v9 )
  {
    v4 = PcpOidSet(a1, v3, a2, a3);
    goto LABEL_5;
  }
  *(_DWORD *)(v3 + 52) = *(_DWORD *)(a2 + 52);
  if ( v9 != 11 )
  {
LABEL_4:
    *(_DWORD *)(v3 + 56) = *(_DWORD *)(a2 + 56);
    goto LABEL_5;
  }
  *(_DWORD *)(v3 + 64) = *(_DWORD *)(a2 + 64);
  *(_DWORD *)(v3 + 68) = *(_DWORD *)(a2 + 68);
  *(_DWORD *)(v3 + 60) = *(_DWORD *)(a2 + 60);
LABEL_5:
  *(_QWORD *)(a2 + 216) = 0;
  NdisFreeCloneOidRequest(*(NDIS_HANDLE *)(a1 + 40), (PNDIS_OID_REQUEST)a2);
  NdisFOidRequestComplete(*(NDIS_HANDLE *)(a1 + 40), (PNDIS_OID_REQUEST)v3, v4);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 100), 0xFFFFFFFF) == 1 )
  {
    v8 = (struct _NDIS_EVENT *)(a1 + 104);
    goto LABEL_8;
  }
}

```

## disassembly

```asm
0x140001a90  push    rbx
0x140001a92  push    rbp
0x140001a93  push    rsi
0x140001a94  push    rdi
0x140001a95  sub     rsp, 28h
0x140001a99  mov     rdi, [rdx+0D8h]
0x140001aa0  mov     esi, r8d
0x140001aa3  mov     rbx, rdx
0x140001aa6  mov     rbp, rcx
0x140001aa9  test    rdi, rdi
0x140001aac  jz      short loc_140001B0F
0x140001aae  mov     ecx, [rdi+4]
0x140001ab1  cmp     ecx, 2
0x140001ab4  jnz     short loc_140001B31
0x140001ab6  mov     eax, [rdx+34h]
0x140001ab9  mov     [rdi+34h], eax
0x140001abc  mov     eax, [rdx+38h]
0x140001abf  mov     [rdi+38h], eax
0x140001ac2  mov     qword ptr [rbx+0D8h], 0
0x140001acd  mov     rdx, rbx; Request
0x140001ad0  mov     rcx, [rbp+28h]; SourceHandle
0x140001ad4  call    cs:__imp_NdisFreeCloneOidRequest
0x140001adb  nop     dword ptr [rax+rax+00h]
0x140001ae0  mov     rcx, [rbp+28h]; NdisFilterHandle
0x140001ae4  mov     r8d, esi; Status
0x140001ae7  mov     rdx, rdi; OidRequest
0x140001aea  call    cs:__imp_NdisFOidRequestComplete
0x140001af1  nop     dword ptr [rax+rax+00h]
0x140001af6  mov     eax, 0FFFFFFFFh
0x140001afb  lock xadd [rbp+64h], eax
0x140001b00  cmp     eax, 1
0x140001b03  jz      short loc_140001B2B
0x140001b05  add     rsp, 28h
0x140001b09  pop     rdi
0x140001b0a  pop     rsi
0x140001b0b  pop     rbp
0x140001b0c  pop     rbx
0x140001b0d  retn
0x140001b0f  mov     [rdx+110h], r8d
0x140001b16  lea     rcx, [rdx+0F8h]; Event
0x140001b1d  call    cs:__imp_NdisSetEvent
0x140001b24  nop     dword ptr [rax+rax+00h]
0x140001b29  jmp     short loc_140001B05
0x140001b2b  lea     rcx, [rbp+68h]
0x140001b2f  jmp     short loc_140001B1D
0x140001b31  test    ecx, ecx
0x140001b33  jz      short loc_140001AB6
0x140001b35  sub     ecx, 1
0x140001b38  jnz     short loc_140001B52
0x140001b3a  mov     r9d, r8d
0x140001b3d  mov     rdx, rdi
0x140001b40  mov     r8, rbx
0x140001b43  mov     rcx, rbp
0x140001b46  call    PcpOidSet
0x140001b4b  mov     esi, eax
0x140001b4d  jmp     loc_140001AC2
0x140001b52  mov     eax, [rdx+34h]
0x140001b55  mov     [rdi+34h], eax
0x140001b58  cmp     ecx, 0Bh
0x140001b5b  jnz     loc_140001ABC
0x140001b61  mov     eax, [rdx+40h]
0x140001b64  mov     [rdi+40h], eax
0x140001b67  mov     eax, [rdx+44h]
0x140001b6a  mov     [rdi+44h], eax
0x140001b6d  mov     eax, [rdx+3Ch]
0x140001b70  mov     [rdi+3Ch], eax
0x140001b73  jmp     loc_140001AC2
```
