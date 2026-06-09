# DhcpRevertThreadCompartmentId

- ea: `0x180042934`
- end: `0x1800429c4`
- name: `DhcpRevertThreadCompartmentId`
- size: `144`
- prototype: `NET_IF_COMPARTMENT_ID __fastcall(NET_IF_COMPARTMENT_ID CompartmentId)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180021db0`
- `0x180032f50`
- `0x180033228`

## callees

- `0x180042934`
- `0x18004b4bc`
- `0x18004dd28`

## import_xrefs

- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180042945`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180042945`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180042979`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180042979`

## pseudocode

```c
NET_IF_COMPARTMENT_ID __fastcall DhcpRevertThreadCompartmentId(NET_IF_COMPARTMENT_ID CompartmentId)
{
  NET_IF_COMPARTMENT_ID result; // eax
  NET_IF_COMPARTMENT_ID v3; // esi
  unsigned int v4; // edi

  result = GetCurrentThreadCompartmentId();
  v3 = result;
  if ( CompartmentId != result )
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_Dd(1028, 12, WPP_7a9c28c0d9d83b6f632816efa12309d5_Traceguids, result, CompartmentId);
    result = SetCurrentThreadCompartmentId(CompartmentId);
    v4 = result;
    if ( result )
    {
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_ddD(1025, 13, WPP_7a9c28c0d9d83b6f632816efa12309d5_Traceguids, v3, CompartmentId, result);
      __fastfail(v4);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180042934  mov     [rsp+arg_0], rbx
0x180042939  mov     [rsp+arg_8], rsi
0x18004293e  push    rdi
0x18004293f  sub     rsp, 30h
0x180042943  mov     ebx, ecx
0x180042945  call    cs:__imp_GetCurrentThreadCompartmentId
0x18004294b  mov     esi, eax
0x18004294d  cmp     ebx, eax
0x18004294f  jz      short loc_1800429B4
0x180042951  test    byte ptr cs:xmmword_1800616A0, 10h
0x180042958  jz      short loc_180042977
0x18004295a  mov     edx, 0Ch
0x18004295f  mov     [rsp+38h+var_18], ebx
0x180042963  mov     ecx, 404h
0x180042968  lea     r8, WPP_7a9c28c0d9d83b6f632816efa12309d5_Traceguids
0x18004296f  mov     r9d, eax
0x180042972  call    WPP_SF_Dd
0x180042977  mov     ecx, ebx; CompartmentId
0x180042979  call    cs:__imp_SetCurrentThreadCompartmentId
0x18004297f  mov     edi, eax
0x180042981  test    eax, eax
0x180042983  jz      short loc_1800429B4
0x180042985  test    byte ptr cs:xmmword_1800616A0, 2
0x18004298c  jz      short loc_1800429AF
0x18004298e  mov     edx, 0Dh
0x180042993  mov     [rsp+38h+var_10], edi
0x180042997  mov     ecx, 401h
0x18004299c  mov     [rsp+38h+var_18], ebx
0x1800429a0  mov     r9d, esi
0x1800429a3  lea     r8, WPP_7a9c28c0d9d83b6f632816efa12309d5_Traceguids
0x1800429aa  call    WPP_SF_ddD
0x1800429af  mov     rcx, rdi
0x1800429b2  int     29h; Win8: RtlFailFast(ecx)
0x1800429b4  mov     rbx, [rsp+38h+arg_0]
0x1800429b9  mov     rsi, [rsp+38h+arg_8]
0x1800429be  add     rsp, 30h
0x1800429c2  pop     rdi
0x1800429c3  retn
```
