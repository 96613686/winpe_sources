# MupUncHardeningPostProcessCreate

- ea: `0x14001cd00`
- end: `0x14001ce0f`
- name: `MupUncHardeningPostProcessCreate`
- size: `271`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001bb60`

## callees

- `0x14001cd00`
- `0x14001d4c0`
- `0x14001d4f8`

## import_xrefs

- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14001cd86`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14001cd86`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x14001cd5b`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x14001cd5b`
- `ntoskrnl!KeBugCheckEx` at `0x14001cdf6`
- `ntoskrnl!KeBugCheckEx` at `0x14001cdf6`
- `ntoskrnl!FsRtlIsEcpAcknowledged` at `0x14001cda7`
- `ntoskrnl!FsRtlIsEcpAcknowledged` at `0x14001cda7`

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
0x14001cd00  mov     [rsp+arg_18], rbx
0x14001cd05  push    rbp
0x14001cd06  push    rsi
0x14001cd07  push    rdi
0x14001cd08  sub     rsp, 30h
0x14001cd0c  mov     rdi, [rcx+28h]
0x14001cd10  mov     rbx, rcx
0x14001cd13  mov     rax, [rdi+0F8h]
0x14001cd1a  test    rax, rax
0x14001cd1d  jz      short loc_14001CD36
0x14001cd1f  mov     esi, [rax+58h]
0x14001cd22  xor     eax, eax
0x14001cd24  mov     [rsp+48h+EcpList], rax
0x14001cd29  mov     [rsp+48h+EcpContext], rax
0x14001cd2e  mov     [rsp+48h+EcpContextSize], eax
0x14001cd32  test    esi, esi
0x14001cd34  jnz     short loc_14001CD46
0x14001cd36  mov     rbx, [rsp+48h+arg_18]
0x14001cd3b  xor     eax, eax
0x14001cd3d  add     rsp, 30h
0x14001cd41  pop     rdi
0x14001cd42  pop     rsi
0x14001cd43  pop     rbp
0x14001cd44  retn
0x14001cd46  call    MupGetIoStatus
0x14001cd4b  test    eax, eax
0x14001cd4d  js      short loc_14001CD36
0x14001cd4f  mov     rbp, [rcx+10h]
0x14001cd53  lea     rdx, [rsp+48h+EcpList]; EcpList
0x14001cd58  mov     rcx, rbp; Irp
0x14001cd5b  call    cs:__imp_FsRtlGetEcpListFromIrp
0x14001cd62  nop     dword ptr [rax+rax+00h]
0x14001cd67  test    eax, eax
0x14001cd69  js      short loc_14001CDE1
0x14001cd6b  mov     rcx, [rsp+48h+EcpList]; EcpList
0x14001cd70  test    rcx, rcx
0x14001cd73  jz      short loc_14001CDE1
0x14001cd75  lea     r9, [rsp+48h+EcpContextSize]; EcpContextSize
0x14001cd7a  lea     r8, [rsp+48h+EcpContext]; EcpContext
0x14001cd7f  lea     rdx, GUID_ECP_NETWORK_OPEN_CONTEXT; EcpType
0x14001cd86  call    cs:__imp_FsRtlFindExtraCreateParameter
0x14001cd8d  nop     dword ptr [rax+rax+00h]
0x14001cd92  test    eax, eax
0x14001cd94  js      short loc_14001CDE1
0x14001cd96  mov     rcx, [rsp+48h+EcpContext]; EcpContext
0x14001cd9b  test    rcx, rcx
0x14001cd9e  jz      short loc_14001CDE1
0x14001cda0  cmp     [rsp+48h+EcpContextSize], 1Ch
0x14001cda5  jb      short loc_14001CDE1
0x14001cda7  call    cs:__imp_FsRtlIsEcpAcknowledged
0x14001cdae  nop     dword ptr [rax+rax+00h]
0x14001cdb3  test    al, al
0x14001cdb5  jz      short loc_14001CDE1
0x14001cdb7  mov     ecx, esi
0x14001cdb9  call    MupiGetNetworkOpenEcpIntegrityLevelFromHardeningCapabilities
0x14001cdbe  mov     rcx, [rsp+48h+EcpContext]
0x14001cdc3  test    eax, eax
0x14001cdc5  jz      short loc_14001CDCE
0x14001cdc7  mov     edx, [rcx+14h]
0x14001cdca  cmp     edx, eax
0x14001cdcc  jnz     short loc_14001CE03
0x14001cdce  mov     eax, [rcx+18h]
0x14001cdd1  and     esi, 1
0x14001cdd4  shl     esi, 3
0x14001cdd7  not     eax
0x14001cdd9  test    eax, esi
0x14001cddb  jz      loc_14001CD36
0x14001cde1  mov     r9, rbx; BugCheckParameter3
0x14001cde4  mov     [rsp+48h+BugCheckParameter4], rdi; BugCheckParameter4
0x14001cde9  mov     r8, rbp; BugCheckParameter2
0x14001cdec  mov     edx, 5; BugCheckParameter1
0x14001cdf1  mov     ecx, 103h; BugCheckCode
0x14001cdf6  call    cs:__imp_KeBugCheckEx
0x14001ce03  cmp     eax, 2
0x14001ce06  jnz     short loc_14001CDE1
0x14001ce08  cmp     edx, 3
0x14001ce0b  jnz     short loc_14001CDE1
0x14001ce0d  jmp     short loc_14001CDCE
```
