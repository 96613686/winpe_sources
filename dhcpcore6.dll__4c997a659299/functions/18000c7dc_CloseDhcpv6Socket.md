# CloseDhcpv6Socket

- ea: `0x18000c7dc`
- end: `0x18000c87e`
- name: `CloseDhcpv6Socket`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `13`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008f80`
- `0x18000bb2c`
- `0x18001189c`
- `0x180011b98`
- `0x180014070`
- `0x180014590`
- `0x180020d50`
- `0x180021150`
- `0x1800216a4`
- `0x1800218e0`
- `0x180021b58`
- `0x1800225c8`
- `0x180022b80`

## callees

- `0x180001d8c`
- `0x180004b30`
- `0x18000c7dc`
- `0x180033970`

## import_xrefs

- `WS2_32!__imp_closesocket` at `0x18000c80d`
- `WS2_32!__imp_closesocket` at `0x18000c80d`

## pseudocode

```c
__int64 __fastcall CloseDhcpv6Socket(__int64 a1)
{
  unsigned int v2; // edi
  SOCKET v3; // rcx
  int v5; // eax
  __int64 v6; // rcx
  int v7; // [rsp+20h] [rbp-18h]

  v2 = 0;
  v3 = *(_QWORD *)(a1 + 64);
  if ( v3 != -1 )
  {
    v5 = closesocket(v3);
    v2 = v5;
    if ( v5 )
    {
      if ( (xmmword_1800423E0 & 2) != 0 )
      {
        v7 = v5;
        WPP_SF_SD(
          1025,
          0x20u,
          (ULONGLONG)WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids,
          *(const wchar_t **)(a1 + 56),
          v7);
      }
      if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 4) != 0 )
        McTemplateU0qq_EtwEventWriteTransfer(v6, (__int64)ErrorClosingSocket, *(unsigned int *)(a1 + 48), v2);
      TraceLogErrorv6(a1, v2, 123);
    }
    *(_QWORD *)(a1 + 64) = -1;
  }
  *(_DWORD *)(a1 + 9052) = 0;
  return v2;
}

```

## disassembly

```asm
0x18000c7dc  mov     [rsp+arg_0], rbx
0x18000c7e1  push    rdi
0x18000c7e2  sub     rsp, 30h
0x18000c7e6  mov     rbx, rcx
0x18000c7e9  xor     edi, edi
0x18000c7eb  mov     rcx, [rcx+40h]; s
0x18000c7ef  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c7f3  jnz     short loc_18000C80D
0x18000c7f5  mov     dword ptr [rbx+235Ch], 0
0x18000c7ff  mov     eax, edi
0x18000c801  mov     rbx, [rsp+38h+arg_0]
0x18000c806  add     rsp, 30h
0x18000c80a  pop     rdi
0x18000c80b  retn
0x18000c80d  call    cs:__imp_closesocket
0x18000c814  nop     dword ptr [rax+rax+00h]
0x18000c819  mov     edi, eax
0x18000c81b  test    eax, eax
0x18000c81d  jnz     short loc_18000C829
0x18000c81f  mov     qword ptr [rbx+40h], 0FFFFFFFFFFFFFFFFh
0x18000c827  jmp     short loc_18000C7F5
0x18000c829  test    byte ptr cs:xmmword_1800423E0, 2
0x18000c830  jz      short loc_18000C850
0x18000c832  mov     r9, [rbx+38h]
0x18000c836  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x18000c83d  mov     edx, 20h ; ' '
0x18000c842  mov     [rsp+38h+var_18], edi
0x18000c846  mov     ecx, 401h
0x18000c84b  call    WPP_SF_SD
0x18000c850  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 4
0x18000c857  jz      short loc_18000C86C
0x18000c859  mov     r8d, [rbx+30h]
0x18000c85d  lea     rdx, ErrorClosingSocket
0x18000c864  mov     r9d, edi
0x18000c867  call    McTemplateU0qq_EtwEventWriteTransfer
0x18000c86c  mov     r8d, 7Bh ; '{'
0x18000c872  mov     edx, edi
0x18000c874  mov     rcx, rbx
0x18000c877  call    TraceLogErrorv6
0x18000c87c  jmp     short loc_18000C81F
```
