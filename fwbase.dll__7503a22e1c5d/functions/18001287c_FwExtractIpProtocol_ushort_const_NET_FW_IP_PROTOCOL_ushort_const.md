# FwExtractIpProtocol(ushort const *,NET_FW_IP_PROTOCOL_ *,ushort const * *)

- ea: `0x18001287c`
- end: `0x1800128fd`
- name: `?FwExtractIpProtocol@@YAJPEBGPEAW4NET_FW_IP_PROTOCOL_@@PEAPEBG@Z`
- size: `129`
- prototype: `__int64 __fastcall(const unsigned __int16 *, enum NET_FW_IP_PROTOCOL_ *, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002be4c`

## callees

- `0x1800047e0`
- `0x18001287c`
- `0x180012904`

## string_xrefs

- `0x1800128d8`: `FwExtractIpProtocol`
- `0x1800128e8`: `FwExtractIpProtocol`

## pseudocode

```c
__int64 __fastcall FwExtractIpProtocol(
        const unsigned __int16 *a1,
        enum NET_FW_IP_PROTOCOL_ *a2,
        const unsigned __int16 **a3)
{
  enum NET_FW_IP_PROTOCOL_ v6; // eax

  if ( (unsigned int)FwIsNextToken(a1, L"TCP", a3) )
  {
    v6 = NET_FW_IP_PROTOCOL_TCP;
LABEL_3:
    *a2 = v6;
    return 0;
  }
  if ( (unsigned int)FwIsNextToken(a1, L"UDP", a3) )
  {
    v6 = NET_FW_IP_PROTOCOL_UDP;
    goto LABEL_3;
  }
  FwReportReturnError("FwExtractIpProtocol", 2147942413LL);
  return FwReportReturnError("FwExtractIpProtocol", 2147942413LL);
}

```

## disassembly

```asm
0x18001287c  mov     [rsp+arg_0], rbx
0x180012881  mov     [rsp+arg_8], rsi
0x180012886  push    rdi
0x180012887  sub     rsp, 20h
0x18001288b  mov     rsi, rdx
0x18001288e  mov     rbx, r8
0x180012891  lea     rdx, aTcp; "TCP"
0x180012898  mov     rdi, rcx
0x18001289b  call    ?FwIsNextToken@@YAHPEBG0PEAPEBG@Z; FwIsNextToken(ushort const *,ushort const *,ushort const * *)
0x1800128a0  test    eax, eax
0x1800128a2  jz      short loc_1800128BD
0x1800128a4  mov     eax, 6
0x1800128a9  mov     [rsi], eax
0x1800128ab  xor     eax, eax
0x1800128ad  mov     rbx, [rsp+28h+arg_0]
0x1800128b2  mov     rsi, [rsp+28h+arg_8]
0x1800128b7  add     rsp, 20h
0x1800128bb  pop     rdi
0x1800128bc  retn
0x1800128bd  mov     r8, rbx; unsigned __int16 **
0x1800128c0  lea     rdx, aUdp; "UDP"
0x1800128c7  mov     rcx, rdi; unsigned __int16 *
0x1800128ca  call    ?FwIsNextToken@@YAHPEBG0PEAPEBG@Z; FwIsNextToken(ushort const *,ushort const *,ushort const * *)
0x1800128cf  test    eax, eax
0x1800128d1  jnz     short loc_1800128F6
0x1800128d3  mov     ebx, 8007000Dh
0x1800128d8  lea     rcx, aFwextractippro; "FwExtractIpProtocol"
0x1800128df  mov     edx, ebx
0x1800128e1  call    FwReportReturnError
0x1800128e6  mov     edx, ebx
0x1800128e8  lea     rcx, aFwextractippro; "FwExtractIpProtocol"
0x1800128ef  call    FwReportReturnError
0x1800128f4  jmp     short loc_1800128AD
0x1800128f6  mov     eax, 11h
0x1800128fb  jmp     short loc_1800128A9
```
