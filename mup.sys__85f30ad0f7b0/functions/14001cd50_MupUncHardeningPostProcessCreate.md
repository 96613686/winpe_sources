# MupUncHardeningPostProcessCreate

- ea: `0x14001cd50`
- end: `0x14001ce5f`
- name: `MupUncHardeningPostProcessCreate`
- size: `271`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001bbb0`

## callees

- `0x14001cd50`
- `0x14001d510`
- `0x14001d548`

## import_xrefs

- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14001cdd6`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14001cdd6`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x14001cdab`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x14001cdab`
- `ntoskrnl!KeBugCheckEx` at `0x14001ce46`
- `ntoskrnl!KeBugCheckEx` at `0x14001ce46`
- `ntoskrnl!FsRtlIsEcpAcknowledged` at `0x14001cdf7`
- `ntoskrnl!FsRtlIsEcpAcknowledged` at `0x14001cdf7`

## pseudocode

```c
__int64 __fastcall MupUncHardeningPostProcessCreate(ULONG_PTR BugCheckParameter3)
{
  ULONG_PTR BugCheckParameter4; // rdi
  __int64 v3; // rax
  unsigned int v4; // esi
  __int64 v6; // rcx
  IRP *v7; // rbp
  int NetworkOpenEcpIntegrityLevelFromHardeningCapabilities; // eax
  int v9; // edx
  ULONG EcpContextSize; // [rsp+50h] [rbp+8h] BYREF
  PVOID EcpContext; // [rsp+58h] [rbp+10h] BYREF
  PECP_LIST EcpList; // [rsp+60h] [rbp+18h] BYREF

  BugCheckParameter4 = *(_QWORD *)(BugCheckParameter3 + 40);
  v3 = *(_QWORD *)(BugCheckParameter4 + 248);
  if ( v3 )
  {
    v4 = *(_DWORD *)(v3 + 88);
    EcpList = 0;
    EcpContext = 0;
    EcpContextSize = 0;
    if ( v4 )
    {
      if ( (int)MupGetIoStatus() >= 0 )
      {
        if ( (v7 = *(IRP **)(v6 + 16), FsRtlGetEcpListFromIrp(v7, &EcpList) < 0)
          || !EcpList
          || FsRtlFindExtraCreateParameter(EcpList, &GUID_ECP_NETWORK_OPEN_CONTEXT, &EcpContext, &EcpContextSize) < 0
          || !EcpContext
          || EcpContextSize < 0x1C
          || !FsRtlIsEcpAcknowledged(EcpContext)
          || (NetworkOpenEcpIntegrityLevelFromHardeningCapabilities = MupiGetNetworkOpenEcpIntegrityLevelFromHardeningCapabilities(v4)) != 0
          && (v9 = *((_DWORD *)EcpContext + 5), v9 != NetworkOpenEcpIntegrityLevelFromHardeningCapabilities)
          && (NetworkOpenEcpIntegrityLevelFromHardeningCapabilities != 2 || v9 != 3)
          || ((8 * (v4 & 1)) & ~*((_DWORD *)EcpContext + 6)) != 0 )
        {
          KeBugCheckEx(0x103u, 5u, (ULONG_PTR)v7, BugCheckParameter3, BugCheckParameter4);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14001cd50  mov     [rsp+arg_18], rbx
0x14001cd55  push    rbp
0x14001cd56  push    rsi
0x14001cd57  push    rdi
0x14001cd58  sub     rsp, 30h
0x14001cd5c  mov     rdi, [rcx+28h]
0x14001cd60  mov     rbx, rcx
0x14001cd63  mov     rax, [rdi+0F8h]
0x14001cd6a  test    rax, rax
0x14001cd6d  jz      short loc_14001CD86
0x14001cd6f  mov     esi, [rax+58h]
0x14001cd72  xor     eax, eax
0x14001cd74  mov     [rsp+48h+EcpList], rax
0x14001cd79  mov     [rsp+48h+EcpContext], rax
0x14001cd7e  mov     [rsp+48h+EcpContextSize], eax
0x14001cd82  test    esi, esi
0x14001cd84  jnz     short loc_14001CD96
0x14001cd86  mov     rbx, [rsp+48h+arg_18]
0x14001cd8b  xor     eax, eax
0x14001cd8d  add     rsp, 30h
0x14001cd91  pop     rdi
0x14001cd92  pop     rsi
0x14001cd93  pop     rbp
0x14001cd94  retn
0x14001cd96  call    MupGetIoStatus
0x14001cd9b  test    eax, eax
0x14001cd9d  js      short loc_14001CD86
0x14001cd9f  mov     rbp, [rcx+10h]
0x14001cda3  lea     rdx, [rsp+48h+EcpList]; EcpList
0x14001cda8  mov     rcx, rbp; Irp
0x14001cdab  call    cs:__imp_FsRtlGetEcpListFromIrp
0x14001cdb2  nop     dword ptr [rax+rax+00h]
0x14001cdb7  test    eax, eax
0x14001cdb9  js      short loc_14001CE31
0x14001cdbb  mov     rcx, [rsp+48h+EcpList]; EcpList
0x14001cdc0  test    rcx, rcx
0x14001cdc3  jz      short loc_14001CE31
0x14001cdc5  lea     r9, [rsp+48h+EcpContextSize]; EcpContextSize
0x14001cdca  lea     r8, [rsp+48h+EcpContext]; EcpContext
0x14001cdcf  lea     rdx, GUID_ECP_NETWORK_OPEN_CONTEXT; EcpType
0x14001cdd6  call    cs:__imp_FsRtlFindExtraCreateParameter
0x14001cddd  nop     dword ptr [rax+rax+00h]
0x14001cde2  test    eax, eax
0x14001cde4  js      short loc_14001CE31
0x14001cde6  mov     rcx, [rsp+48h+EcpContext]; EcpContext
0x14001cdeb  test    rcx, rcx
0x14001cdee  jz      short loc_14001CE31
0x14001cdf0  cmp     [rsp+48h+EcpContextSize], 1Ch
0x14001cdf5  jb      short loc_14001CE31
0x14001cdf7  call    cs:__imp_FsRtlIsEcpAcknowledged
0x14001cdfe  nop     dword ptr [rax+rax+00h]
0x14001ce03  test    al, al
0x14001ce05  jz      short loc_14001CE31
0x14001ce07  mov     ecx, esi
0x14001ce09  call    MupiGetNetworkOpenEcpIntegrityLevelFromHardeningCapabilities
0x14001ce0e  mov     rcx, [rsp+48h+EcpContext]
0x14001ce13  test    eax, eax
0x14001ce15  jz      short loc_14001CE1E
0x14001ce17  mov     edx, [rcx+14h]
0x14001ce1a  cmp     edx, eax
0x14001ce1c  jnz     short loc_14001CE53
0x14001ce1e  mov     eax, [rcx+18h]
0x14001ce21  and     esi, 1
0x14001ce24  shl     esi, 3
0x14001ce27  not     eax
0x14001ce29  test    eax, esi
0x14001ce2b  jz      loc_14001CD86
0x14001ce31  mov     r9, rbx; BugCheckParameter3
0x14001ce34  mov     [rsp+48h+BugCheckParameter4], rdi; BugCheckParameter4
0x14001ce39  mov     r8, rbp; BugCheckParameter2
0x14001ce3c  mov     edx, 5; BugCheckParameter1
0x14001ce41  mov     ecx, 103h; BugCheckCode
0x14001ce46  call    cs:__imp_KeBugCheckEx
0x14001ce53  cmp     eax, 2
0x14001ce56  jnz     short loc_14001CE31
0x14001ce58  cmp     edx, 3
0x14001ce5b  jnz     short loc_14001CE31
0x14001ce5d  jmp     short loc_14001CE1E
```
