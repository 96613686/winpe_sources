# ConvertMib2RouteToRouteInfo

- ea: `0x18004a120`
- end: `0x18004a338`
- name: `ConvertMib2RouteToRouteInfo`
- size: `536`
- prototype: `__int64 __fastcall(NET_LUID *InterfaceLuid)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004126c`

## callees

- `0x18000ac60`
- `0x1800435b4`
- `0x18004a120`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `IPHLPAPI!ConvertLengthToIpv4Mask` at `0x18004a1b1`
- `IPHLPAPI!ConvertLengthToIpv4Mask` at `0x18004a1b1`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18004a217`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18004a285`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18004a217`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18004a285`
- `iprtprio!ComputeRouteMetric` at `0x18004a2da`
- `iprtprio!ComputeRouteMetric` at `0x18004a2da`

## pseudocode

```c
__int64 __fastcall ConvertMib2RouteToRouteInfo(NET_LUID *InterfaceLuid, int a2, _DWORD *a3)
{
  unsigned int v6; // eax
  unsigned int v7; // esi
  int v8; // eax
  int v9; // eax
  bool v10; // zf
  _BYTE v12[4]; // [rsp+20h] [rbp-E0h] BYREF
  ULONG InterfaceIndex; // [rsp+24h] [rbp-DCh] BYREF
  ULONG Mask; // [rsp+28h] [rbp-D8h] BYREF
  int v15; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v16[2044]; // [rsp+34h] [rbp-CCh] BYREF

  Mask = 0;
  InterfaceIndex = 0;
  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  if ( InterfaceLuid && a3 )
  {
    memset_0(a3, 0, 0x48u);
    if ( a2 )
    {
      v6 = ConvertLengthToIpv4Mask(LOBYTE(InterfaceLuid[5].Value), &Mask);
      v7 = v6;
      if ( v6 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v15) = 0;
          FormatRRASErrorString(&v15, L"ERROR: Failed to convert Destination Prefix length to Mask. error %d", v6);
          goto LABEL_7;
        }
        return v7;
      }
      v7 = ConvertInterfaceLuidToIndex(InterfaceLuid, &InterfaceIndex);
      if ( v7 )
      {
LABEL_10:
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v15) = 0;
          FormatRRASErrorString(&v15, L"ERROR: Failed to convert interface Luid to Index. error %d", v7);
LABEL_7:
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v15);
        }
        return v7;
      }
      *a3 = InterfaceLuid[2].Value;
      a3[1] = Mask;
      a3[3] = InterfaceLuid[6].Value;
      v8 = *((_DWORD *)&InterfaceLuid[10].Info + 1);
      a3[8] = v8;
      a3[7] = v8;
      a3[6] = v8;
      a3[4] = -1;
      a3[5] = 0;
      a3[2] = 0;
    }
    else
    {
      v12[0] = 0;
      v7 = ConvertInterfaceLuidToIndex(InterfaceLuid, &InterfaceIndex);
      if ( v7 )
        goto LABEL_10;
      *(_OWORD *)a3 = *(_OWORD *)((char *)&InterfaceLuid[2].Info + 4);
      a3[4] = LOBYTE(InterfaceLuid[5].Value);
      a3[9] = *((_DWORD *)&InterfaceLuid[9].Info + 1);
      RowToRTMFlags(InterfaceLuid, v12);
      a3[10] = v12[0];
      a3[11] = *((_DWORD *)&InterfaceLuid[10].Info + 1);
      *(_OWORD *)(a3 + 5) = *(_OWORD *)((char *)&InterfaceLuid[6].Info + 4);
    }
    a3[12] = InterfaceIndex;
    a3[14] = InterfaceLuid[11].Value;
    a3[15] = ComputeRouteMetric(LODWORD(InterfaceLuid[11].Value));
    v9 = 1;
    v10 = LODWORD(InterfaceLuid[11].Value) == 2;
    a3[17] = a2;
    if ( v10 )
      v9 = 3;
    a3[13] = v9;
    a3[16] = a2 != 0 ? 3 : 1;
    return v7;
  }
  return 87;
}

```

## disassembly

```asm
0x18004a120  mov     [rsp-8+arg_8], rbx
0x18004a125  mov     [rsp-8+arg_18], rsi
0x18004a12a  push    rbp
0x18004a12b  push    rdi
0x18004a12c  push    r14
0x18004a12e  lea     rbp, [rsp-740h]
0x18004a136  sub     rsp, 840h
0x18004a13d  mov     rax, cs:__security_cookie
0x18004a144  xor     rax, rsp
0x18004a147  mov     [rbp+750h+var_20], rax
0x18004a14e  mov     rbx, r8
0x18004a151  mov     [rsp+850h+Mask], 0
0x18004a159  mov     r14d, edx
0x18004a15c  mov     [rsp+850h+InterfaceIndex], 0
0x18004a164  mov     rdi, rcx
0x18004a167  xor     eax, eax
0x18004a169  xor     edx, edx; Val
0x18004a16b  mov     [rsp+850h+var_820], eax
0x18004a16f  mov     r8d, 7FCh; Size
0x18004a175  lea     rcx, [rsp+850h+var_81C]; void *
0x18004a17a  call    memset_0
0x18004a17f  test    rdi, rdi
0x18004a182  jz      loc_18004A30C
0x18004a188  test    rbx, rbx
0x18004a18b  jz      loc_18004A30C
0x18004a191  xor     edx, edx; Val
0x18004a193  mov     rcx, rbx; void *
0x18004a196  lea     r8d, [rdx+48h]; Size
0x18004a19a  call    memset_0
0x18004a19f  test    r14d, r14d
0x18004a1a2  jz      loc_18004A278
0x18004a1a8  movzx   ecx, byte ptr [rdi+28h]; MaskLength
0x18004a1ac  lea     rdx, [rsp+850h+Mask]; Mask
0x18004a1b1  call    cs:__imp_ConvertLengthToIpv4Mask
0x18004a1b7  mov     esi, eax
0x18004a1b9  test    eax, eax
0x18004a1bb  jz      short loc_18004A20F
0x18004a1bd  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004a1c4  jz      loc_18004A308
0x18004a1ca  xor     ecx, ecx
0x18004a1cc  lea     rdx, aErrorFailedToC; "ERROR: Failed to convert Destination Pr"...
0x18004a1d3  mov     word ptr [rsp+850h+var_820], cx
0x18004a1d8  mov     r8d, eax
0x18004a1db  lea     rcx, [rsp+850h+var_820]
0x18004a1e0  call    FormatRRASErrorString
0x18004a1e5  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004a1ec  jz      loc_18004A308
0x18004a1f2  lea     r8, [rsp+850h+var_820]
0x18004a1f7  lea     rdx, RasRtrMgrTraceError
0x18004a1fe  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004a205  call    McTemplateU0z_EventWriteTransfer
0x18004a20a  jmp     loc_18004A308
0x18004a20f  lea     rdx, [rsp+850h+InterfaceIndex]; InterfaceIndex
0x18004a214  mov     rcx, rdi; InterfaceLuid
0x18004a217  call    cs:__imp_ConvertInterfaceLuidToIndex
0x18004a21d  mov     esi, eax
0x18004a21f  test    eax, eax
0x18004a221  jz      short loc_18004A243
0x18004a223  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004a22a  jz      loc_18004A308
0x18004a230  xor     eax, eax
0x18004a232  lea     rdx, aErrorFailedToC_0; "ERROR: Failed to convert interface Luid"...
0x18004a239  mov     word ptr [rsp+850h+var_820], ax
0x18004a23e  mov     r8d, esi
0x18004a241  jmp     short loc_18004A1DB
0x18004a243  mov     eax, [rdi+10h]
0x18004a246  mov     [rbx], eax
0x18004a248  mov     eax, [rsp+850h+Mask]
0x18004a24c  mov     [rbx+4], eax
0x18004a24f  mov     eax, [rdi+30h]
0x18004a252  mov     [rbx+0Ch], eax
0x18004a255  mov     eax, [rdi+54h]
0x18004a258  mov     [rbx+20h], eax
0x18004a25b  mov     [rbx+1Ch], eax
0x18004a25e  mov     [rbx+18h], eax
0x18004a261  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x18004a268  mov     dword ptr [rbx+14h], 0
0x18004a26f  mov     dword ptr [rbx+8], 0
0x18004a276  jmp     short loc_18004A2CA
0x18004a278  lea     rdx, [rsp+850h+InterfaceIndex]; InterfaceIndex
0x18004a27d  mov     [rsp+850h+var_830], 0
0x18004a282  mov     rcx, rdi; InterfaceLuid
0x18004a285  call    cs:__imp_ConvertInterfaceLuidToIndex
0x18004a28b  mov     esi, eax
0x18004a28d  test    eax, eax
0x18004a28f  jnz     short loc_18004A223
0x18004a291  movups  xmm0, xmmword ptr [rdi+14h]
0x18004a295  lea     rdx, [rsp+850h+var_830]
0x18004a29a  mov     rcx, rdi
0x18004a29d  movdqu  xmmword ptr [rbx], xmm0
0x18004a2a1  movzx   eax, byte ptr [rdi+28h]
0x18004a2a5  mov     [rbx+10h], eax
0x18004a2a8  mov     eax, [rdi+4Ch]
0x18004a2ab  mov     [rbx+24h], eax
0x18004a2ae  call    RowToRTMFlags
0x18004a2b3  movzx   ecx, [rsp+850h+var_830]
0x18004a2b8  mov     [rbx+28h], ecx
0x18004a2bb  mov     eax, [rdi+54h]
0x18004a2be  mov     [rbx+2Ch], eax
0x18004a2c1  movups  xmm0, xmmword ptr [rdi+34h]
0x18004a2c5  movdqu  xmmword ptr [rbx+14h], xmm0
0x18004a2ca  mov     eax, [rsp+850h+InterfaceIndex]
0x18004a2ce  mov     [rbx+30h], eax
0x18004a2d1  mov     eax, [rdi+58h]
0x18004a2d4  mov     [rbx+38h], eax
0x18004a2d7  mov     ecx, [rdi+58h]
0x18004a2da  call    cs:__imp_ComputeRouteMetric
0x18004a2e0  mov     [rbx+3Ch], eax
0x18004a2e3  mov     eax, 1
0x18004a2e8  cmp     dword ptr [rdi+58h], 2
0x18004a2ec  mov     [rbx+44h], r14d
0x18004a2f0  lea     ecx, [rax+2]
0x18004a2f3  cmovz   eax, ecx
0x18004a2f6  mov     [rbx+34h], eax
0x18004a2f9  mov     eax, r14d
0x18004a2fc  neg     eax
0x18004a2fe  sbb     ecx, ecx
0x18004a300  and     ecx, 2
0x18004a303  inc     ecx
0x18004a305  mov     [rbx+40h], ecx
0x18004a308  mov     eax, esi
0x18004a30a  jmp     short loc_18004A311
0x18004a30c  mov     eax, 57h ; 'W'
0x18004a311  mov     rcx, [rbp+750h+var_20]
0x18004a318  xor     rcx, rsp; StackCookie
0x18004a31b  call    __security_check_cookie
0x18004a320  lea     r11, [rsp+850h+var_10]
0x18004a328  mov     rbx, [r11+28h]
0x18004a32c  mov     rsi, [r11+38h]
0x18004a330  mov     rsp, r11
0x18004a333  pop     r14
0x18004a335  pop     rdi
0x18004a336  pop     rbp
0x18004a337  retn
```
