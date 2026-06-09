# DhcpSetThreadCompartmentId

- ea: `0x180042a74`
- end: `0x180042b32`
- name: `DhcpSetThreadCompartmentId`
- size: `190`
- prototype: `__int64 __fastcall(__int64 CompartmentId, NET_IF_COMPARTMENT_ID *, int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180021db0`
- `0x180032f50`
- `0x180033228`

## callees

- `0x180042a74`
- `0x18004c590`
- `0x18004d9e8`

## import_xrefs

- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180042adf`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180042adf`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180042aee`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180042aee`

## pseudocode

```c
__int64 __fastcall DhcpSetThreadCompartmentId(__int64 CompartmentId, NET_IF_COMPARTMENT_ID *a2, int *a3)
{
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // r14d
  int v5; // r15d
  NET_IF_COMPARTMENT_ID v7; // ebp
  unsigned int v8; // ebx

  CurrentThreadCompartmentId = 0;
  v5 = 0;
  v7 = CompartmentId;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_d(1028, 14, WPP_7a9c28c0d9d83b6f632816efa12309d5_Traceguids, (unsigned int)CompartmentId);
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( !a2 || !a3 )
  {
    v8 = 87;
    goto LABEL_16;
  }
  v8 = 0;
  if ( DhcpGlobalCompartmentAware && v7 )
  {
    CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
    if ( v7 != CurrentThreadCompartmentId )
    {
      v8 = SetCurrentThreadCompartmentId(v7);
      if ( v8 )
        goto LABEL_16;
      v5 = 1;
    }
    *a2 = CurrentThreadCompartmentId;
    *a3 = v5;
  }
LABEL_16:
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_ddlD(CompartmentId, a2, a3, v7, CurrentThreadCompartmentId, v5, v8);
  return v8;
}

```

## disassembly

```asm
0x180042a74  push    rbx
0x180042a76  push    rbp
0x180042a77  push    rsi
0x180042a78  push    rdi
0x180042a79  push    r14
0x180042a7b  push    r15
0x180042a7d  sub     rsp, 48h
0x180042a81  xor     r14d, r14d
0x180042a84  mov     rdi, r8
0x180042a87  xor     r15d, r15d
0x180042a8a  mov     rsi, rdx
0x180042a8d  mov     ebp, ecx
0x180042a8f  test    byte ptr cs:xmmword_1800616A0, 10h
0x180042a96  jz      short loc_180042AB0
0x180042a98  lea     edx, [r14+0Eh]
0x180042a9c  mov     ecx, 404h
0x180042aa1  mov     r9d, ebp
0x180042aa4  lea     r8, WPP_7a9c28c0d9d83b6f632816efa12309d5_Traceguids
0x180042aab  call    WPP_SF_d
0x180042ab0  test    rsi, rsi
0x180042ab3  jz      short loc_180042AB8
0x180042ab5  mov     [rsi], r14d
0x180042ab8  test    rdi, rdi
0x180042abb  jz      short loc_180042AC0
0x180042abd  mov     [rdi], r14d
0x180042ac0  test    rsi, rsi
0x180042ac3  jnz     short loc_180042ACC
0x180042ac5  mov     ebx, 57h ; 'W'
0x180042aca  jmp     short loc_180042B04
0x180042acc  test    rdi, rdi
0x180042acf  jz      short loc_180042AC5
0x180042ad1  xor     ebx, ebx
0x180042ad3  cmp     cs:DhcpGlobalCompartmentAware, ebx
0x180042ad9  jz      short loc_180042B04
0x180042adb  test    ebp, ebp
0x180042add  jz      short loc_180042B04
0x180042adf  call    cs:__imp_GetCurrentThreadCompartmentId
0x180042ae5  mov     r14d, eax
0x180042ae8  cmp     ebp, eax
0x180042aea  jz      short loc_180042AFE
0x180042aec  mov     ecx, ebp; CompartmentId
0x180042aee  call    cs:__imp_SetCurrentThreadCompartmentId
0x180042af4  mov     ebx, eax
0x180042af6  test    eax, eax
0x180042af8  jnz     short loc_180042B04
0x180042afa  lea     r15d, [rax+1]
0x180042afe  mov     [rsi], r14d
0x180042b01  mov     [rdi], r15d
0x180042b04  test    byte ptr cs:xmmword_1800616A0, 10h
0x180042b0b  jz      short loc_180042B23
0x180042b0d  mov     [rsp+78h+var_48], ebx
0x180042b11  mov     r9d, ebp
0x180042b14  mov     [rsp+78h+var_50], r15d
0x180042b19  mov     [rsp+78h+var_58], r14d
0x180042b1e  call    WPP_SF_ddlD
0x180042b23  mov     eax, ebx
0x180042b25  add     rsp, 48h
0x180042b29  pop     r15
0x180042b2b  pop     r14
0x180042b2d  pop     rdi
0x180042b2e  pop     rsi
0x180042b2f  pop     rbp
0x180042b30  pop     rbx
0x180042b31  retn
```
