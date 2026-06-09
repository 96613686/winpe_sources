# ConvertRouteKeyToRouteInfo

- ea: `0x18004a69c`
- end: `0x18004a8c9`
- name: `ConvertRouteKeyToRouteInfo`
- size: `557`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180021d18`

## callees

- `0x18000ac60`
- `0x18004a69c`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `IPHLPAPI!ConvertLengthToIpv4Mask` at `0x18004a71c`
- `IPHLPAPI!ConvertLengthToIpv4Mask` at `0x18004a71c`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18004a783`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18004a7ee`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18004a783`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18004a7ee`
- `iprtprio!ComputeRouteMetric` at `0x18004a872`
- `iprtprio!ComputeRouteMetric` at `0x18004a872`

## pseudocode

```c
__int64 __fastcall ConvertRouteKeyToRouteInfo(__int64 a1, __int64 a2, int a3, _DWORD *a4)
{
  unsigned int v8; // eax
  unsigned int v9; // edi
  int v10; // eax
  unsigned __int8 v11; // cl
  unsigned __int8 v12; // dl
  unsigned __int8 v13; // cl
  unsigned __int8 v14; // dl
  unsigned __int8 v15; // cl
  int v16; // eax
  bool v17; // zf
  ULONG InterfaceIndex; // [rsp+20h] [rbp-E0h] BYREF
  ULONG Mask[3]; // [rsp+24h] [rbp-DCh] BYREF
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v22[2044]; // [rsp+34h] [rbp-CCh] BYREF

  Mask[0] = 0;
  InterfaceIndex = 0;
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  memset_0(a4, 0, 0x48u);
  if ( a3 )
  {
    v8 = ConvertLengthToIpv4Mask(*(unsigned __int8 *)(a1 + 8), Mask);
    v9 = v8;
    if ( v8 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        return v9;
      LOWORD(v21) = 0;
      FormatRRASErrorString(&v21, L"ERROR: Failed to convert Destination Prefix length to Mask. error %d", v8);
      goto LABEL_5;
    }
    v9 = ConvertInterfaceLuidToIndex((const NET_LUID *)(a1 + 24), &InterfaceIndex);
    if ( v9 )
    {
LABEL_8:
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        return v9;
      LOWORD(v21) = 0;
      FormatRRASErrorString(&v21, L"ERROR: Failed to convert interface Luid to Index. error %d", v9);
LABEL_5:
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v21);
      return v9;
    }
    *a4 = *(_DWORD *)(a1 + 4);
    a4[1] = Mask[0];
    a4[3] = *(_DWORD *)(a1 + 40);
    v10 = *(_DWORD *)(a2 + 12);
    a4[8] = v10;
    a4[7] = v10;
    a4[6] = v10;
    a4[4] = -1;
    a4[5] = 0;
    a4[2] = 0;
  }
  else
  {
    v9 = ConvertInterfaceLuidToIndex((const NET_LUID *)(a1 + 40), &InterfaceIndex);
    if ( v9 )
      goto LABEL_8;
    *(_OWORD *)a4 = *(_OWORD *)(a1 + 4);
    a4[4] = *(unsigned __int8 *)(a1 + 20);
    a4[9] = *(_DWORD *)(a2 + 4);
    v11 = (*(_BYTE *)(a2 + 20) != 0) | 2;
    if ( !*(_BYTE *)(a2 + 21) )
      v11 = *(_BYTE *)(a2 + 20) != 0;
    v12 = v11;
    v13 = v11 | 4;
    if ( *(_BYTE *)(a2 + 22) == (_BYTE)v9 )
      v13 = v12;
    v14 = v13;
    v15 = v13 | 8;
    if ( *(_BYTE *)(a2 + 23) == (_BYTE)v9 )
      v15 = v14;
    a4[10] = v15;
    a4[11] = *(_DWORD *)(a2 + 12);
    *(_OWORD *)(a4 + 5) = *(_OWORD *)(a1 + 56);
  }
  a4[12] = InterfaceIndex;
  a4[14] = *(_DWORD *)(a2 + 16);
  a4[15] = ComputeRouteMetric(*(unsigned int *)(a2 + 16));
  v16 = 1;
  v17 = *(_DWORD *)(a2 + 16) == 2;
  a4[17] = a3;
  if ( v17 )
    v16 = 3;
  a4[13] = v16;
  a4[16] = a3 != 0 ? 3 : 1;
  return v9;
}

```

## disassembly

```asm
0x18004a69c  mov     [rsp-8+arg_10], rbx
0x18004a6a1  push    rbp
0x18004a6a2  push    rsi
0x18004a6a3  push    rdi
0x18004a6a4  push    r14
0x18004a6a6  push    r15
0x18004a6a8  lea     rbp, [rsp-740h]
0x18004a6b0  sub     rsp, 840h
0x18004a6b7  mov     rax, cs:__security_cookie
0x18004a6be  xor     rax, rsp
0x18004a6c1  mov     [rbp+760h+var_30], rax
0x18004a6c8  mov     r15d, r8d
0x18004a6cb  mov     [rsp+860h+Mask], 0
0x18004a6d3  mov     r14, rdx
0x18004a6d6  mov     [rsp+860h+InterfaceIndex], 0
0x18004a6de  mov     rsi, rcx
0x18004a6e1  xor     eax, eax
0x18004a6e3  xor     edx, edx; Val
0x18004a6e5  mov     [rsp+860h+var_830], eax
0x18004a6e9  mov     r8d, 7FCh; Size
0x18004a6ef  lea     rcx, [rsp+860h+var_82C]; void *
0x18004a6f4  mov     rbx, r9
0x18004a6f7  call    memset_0
0x18004a6fc  xor     edx, edx; Val
0x18004a6fe  mov     rcx, rbx; void *
0x18004a701  lea     r8d, [rdx+48h]; Size
0x18004a705  call    memset_0
0x18004a70a  test    r15d, r15d
0x18004a70d  jz      loc_18004A7E5
0x18004a713  movzx   ecx, byte ptr [rsi+8]; MaskLength
0x18004a717  lea     rdx, [rsp+860h+Mask]; Mask
0x18004a71c  call    cs:__imp_ConvertLengthToIpv4Mask
0x18004a722  mov     edi, eax
0x18004a724  test    eax, eax
0x18004a726  jz      short loc_18004A77A
0x18004a728  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004a72f  jz      loc_18004A8A1
0x18004a735  xor     ecx, ecx
0x18004a737  lea     rdx, aErrorFailedToC; "ERROR: Failed to convert Destination Pr"...
0x18004a73e  mov     word ptr [rsp+860h+var_830], cx
0x18004a743  mov     r8d, eax
0x18004a746  lea     rcx, [rsp+860h+var_830]
0x18004a74b  call    FormatRRASErrorString
0x18004a750  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004a757  jz      loc_18004A8A1
0x18004a75d  lea     r8, [rsp+860h+var_830]
0x18004a762  lea     rdx, RasRtrMgrTraceError
0x18004a769  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004a770  call    McTemplateU0z_EventWriteTransfer
0x18004a775  jmp     loc_18004A8A1
0x18004a77a  lea     rcx, [rsi+18h]; InterfaceLuid
0x18004a77e  lea     rdx, [rsp+860h+InterfaceIndex]; InterfaceIndex
0x18004a783  call    cs:__imp_ConvertInterfaceLuidToIndex
0x18004a789  mov     edi, eax
0x18004a78b  test    eax, eax
0x18004a78d  jz      short loc_18004A7AF
0x18004a78f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004a796  jz      loc_18004A8A1
0x18004a79c  xor     eax, eax
0x18004a79e  lea     rdx, aErrorFailedToC_0; "ERROR: Failed to convert interface Luid"...
0x18004a7a5  mov     word ptr [rsp+860h+var_830], ax
0x18004a7aa  mov     r8d, edi
0x18004a7ad  jmp     short loc_18004A746
0x18004a7af  mov     eax, [rsi+4]
0x18004a7b2  mov     [rbx], eax
0x18004a7b4  mov     eax, [rsp+860h+Mask]
0x18004a7b8  mov     [rbx+4], eax
0x18004a7bb  mov     eax, [rsi+28h]
0x18004a7be  mov     [rbx+0Ch], eax
0x18004a7c1  mov     eax, [r14+0Ch]
0x18004a7c5  mov     [rbx+20h], eax
0x18004a7c8  mov     [rbx+1Ch], eax
0x18004a7cb  mov     [rbx+18h], eax
0x18004a7ce  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x18004a7d5  mov     dword ptr [rbx+14h], 0
0x18004a7dc  mov     dword ptr [rbx+8], 0
0x18004a7e3  jmp     short loc_18004A860
0x18004a7e5  lea     rcx, [rsi+28h]; InterfaceLuid
0x18004a7e9  lea     rdx, [rsp+860h+InterfaceIndex]; InterfaceIndex
0x18004a7ee  call    cs:__imp_ConvertInterfaceLuidToIndex
0x18004a7f4  mov     edi, eax
0x18004a7f6  test    eax, eax
0x18004a7f8  jnz     short loc_18004A78F
0x18004a7fa  movups  xmm0, xmmword ptr [rsi+4]
0x18004a7fe  movdqu  xmmword ptr [rbx], xmm0
0x18004a802  movzx   eax, byte ptr [rsi+14h]
0x18004a806  mov     [rbx+10h], eax
0x18004a809  mov     eax, [r14+4]
0x18004a80d  mov     [rbx+24h], eax
0x18004a810  cmp     [r14+14h], dil
0x18004a814  setnz   dl
0x18004a817  mov     al, dl
0x18004a819  or      al, 2
0x18004a81b  cmp     [r14+15h], dil
0x18004a81f  movzx   ecx, al
0x18004a822  movzx   eax, dl
0x18004a825  cmovz   ecx, eax
0x18004a828  movzx   edx, cl
0x18004a82b  mov     al, dl
0x18004a82d  or      al, 4
0x18004a82f  cmp     [r14+16h], dil
0x18004a833  movzx   ecx, al
0x18004a836  cmovz   ecx, edx
0x18004a839  movzx   edx, cl
0x18004a83c  mov     al, dl
0x18004a83e  or      al, 8
0x18004a840  cmp     [r14+17h], dil
0x18004a844  movzx   ecx, al
0x18004a847  cmovz   ecx, edx
0x18004a84a  movzx   eax, cl
0x18004a84d  mov     [rbx+28h], eax
0x18004a850  mov     eax, [r14+0Ch]
0x18004a854  mov     [rbx+2Ch], eax
0x18004a857  movups  xmm0, xmmword ptr [rsi+38h]
0x18004a85b  movdqu  xmmword ptr [rbx+14h], xmm0
0x18004a860  mov     eax, [rsp+860h+InterfaceIndex]
0x18004a864  mov     [rbx+30h], eax
0x18004a867  mov     eax, [r14+10h]
0x18004a86b  mov     [rbx+38h], eax
0x18004a86e  mov     ecx, [r14+10h]
0x18004a872  call    cs:__imp_ComputeRouteMetric
0x18004a878  mov     [rbx+3Ch], eax
0x18004a87b  mov     eax, 1
0x18004a880  cmp     dword ptr [r14+10h], 2
0x18004a885  mov     [rbx+44h], r15d
0x18004a889  lea     ecx, [rax+2]
0x18004a88c  cmovz   eax, ecx
0x18004a88f  mov     [rbx+34h], eax
0x18004a892  mov     eax, r15d
0x18004a895  neg     eax
0x18004a897  sbb     ecx, ecx
0x18004a899  and     ecx, 2
0x18004a89c  inc     ecx
0x18004a89e  mov     [rbx+40h], ecx
0x18004a8a1  mov     eax, edi
0x18004a8a3  mov     rcx, [rbp+760h+var_30]
0x18004a8aa  xor     rcx, rsp; StackCookie
0x18004a8ad  call    __security_check_cookie
0x18004a8b2  mov     rbx, [rsp+860h+arg_10]
0x18004a8ba  add     rsp, 840h
0x18004a8c1  pop     r15
0x18004a8c3  pop     r14
0x18004a8c5  pop     rdi
0x18004a8c6  pop     rsi
0x18004a8c7  pop     rbp
0x18004a8c8  retn
```
