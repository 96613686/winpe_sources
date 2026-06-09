# FsmOpen

- ea: `0x18000be0c`
- end: `0x18000bfb9`
- name: `FsmOpen`
- size: `429`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001413c`
- `0x180015ae0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18000be0c`
- `0x18000d284`
- `0x18000e750`
- `0x180011064`
- `0x18002a138`

## string_xrefs

- `0x18000be6e`: `FsmOpen event received for protocol %x on port %d`
- `0x18000bf4f`: `Illegal transition->FsmOpen received while in %hs state`

## pseudocode

```c
__int64 __fastcall FsmOpen(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  int *PointerToCPCB; // rbx
  __int64 result; // rax
  __int64 v6; // r9
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // [rsp+20h] [rbp-818h] BYREF
  char v14[2044]; // [rsp+24h] [rbp-814h] BYREF

  v2 = (unsigned int)a2;
  v13 = 0;
  PointerToCPCB = (int *)GetPointerToCPCB(a1, a2);
  result = (__int64)memset_0(v14, 0, sizeof(v14));
  if ( !PointerToCPCB )
    return result;
  if ( (byte_18004CF34 & 1) != 0 )
  {
    v6 = *(_QWORD *)(a1 + 16);
    LOWORD(v13) = 0;
    result = FormatRRASErrorString(
               &v13,
               L"FsmOpen event received for protocol %x on port %d",
               *((unsigned int *)CpTable + 44 * v2),
               v6);
    if ( (byte_18004CF34 & 1) != 0 )
      result = McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v13);
  }
  v7 = *PointerToCPCB;
  if ( *PointerToCPCB > 5 )
  {
    v11 = v7 - 6;
    if ( !v11 )
      return result;
    v12 = v11 - 1;
    if ( !v12 || (unsigned int)(v12 - 1) < 2 )
      return result;
    goto LABEL_20;
  }
  if ( v7 == 5 )
    return result;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( !v8 )
      return result;
    v9 = v8 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( !v10 )
        return result;
      if ( v10 == 1 )
      {
        *PointerToCPCB = 5;
        return result;
      }
LABEL_20:
      if ( byte_18004CF33 < 0 )
      {
        LOWORD(v13) = 0;
        result = FormatRRASErrorString(
                   &v13,
                   L"Illegal transition->FsmOpen received while in %hs state",
                   FsmStates[*PointerToCPCB]);
        if ( byte_18004CF33 < 0 )
          return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v13);
      }
      return result;
    }
    PointerToCPCB[6] = dword_18004C9F8;
    PointerToCPCB[7] = dword_18004C9F4;
    result = FsmSendConfigReq(a1, (unsigned int)v2);
    if ( (_DWORD)result )
      *PointerToCPCB = 6;
  }
  else
  {
    result = FsmThisLayerStarted(a1, (unsigned int)v2);
    if ( (_DWORD)result )
      *PointerToCPCB = 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000be0c  mov     [rsp+arg_10], rbx
0x18000be11  mov     [rsp+arg_18], rsi
0x18000be16  push    rdi
0x18000be17  sub     rsp, 830h
0x18000be1e  mov     rax, cs:__security_cookie
0x18000be25  xor     rax, rsp
0x18000be28  mov     [rsp+838h+var_18], rax
0x18000be30  mov     esi, edx
0x18000be32  mov     rdi, rcx
0x18000be35  call    GetPointerToCPCB
0x18000be3a  xor     ecx, ecx
0x18000be3c  xor     edx, edx; Val
0x18000be3e  mov     [rsp+838h+var_818], ecx
0x18000be42  mov     r8d, 7FCh; Size
0x18000be48  lea     rcx, [rsp+838h+var_814]; void *
0x18000be4d  mov     rbx, rax
0x18000be50  call    memset_0
0x18000be55  test    rbx, rbx
0x18000be58  jz      loc_18000BF94
0x18000be5e  test    cs:byte_18004CF34, 1
0x18000be65  jz      short loc_18000BEB6
0x18000be67  mov     r8, cs:CpTable
0x18000be6e  lea     rdx, aFsmopenEventRe; "FsmOpen event received for protocol %x "...
0x18000be75  mov     r9, [rdi+10h]
0x18000be79  xor     eax, eax
0x18000be7b  imul    rcx, rsi, 0B0h
0x18000be82  mov     word ptr [rsp+838h+var_818], ax
0x18000be87  mov     r8d, [rcx+r8]
0x18000be8b  lea     rcx, [rsp+838h+var_818]
0x18000be90  call    FormatRRASErrorString
0x18000be95  test    cs:byte_18004CF34, 1
0x18000be9c  jz      short loc_18000BEB6
0x18000be9e  lea     r8, [rsp+838h+var_818]
0x18000bea3  lea     rdx, RasPppTraceInfo
0x18000beaa  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000beb1  call    McTemplateU0z_EventWriteTransfer
0x18000beb6  mov     ecx, [rbx]
0x18000beb8  cmp     ecx, 5
0x18000bebb  jg      short loc_18000BF30
0x18000bebd  jz      loc_18000BF94
0x18000bec3  test    ecx, ecx
0x18000bec5  jz      short loc_18000BF1A
0x18000bec7  sub     ecx, 1
0x18000beca  jz      loc_18000BF94
0x18000bed0  sub     ecx, 1
0x18000bed3  jz      short loc_18000BEEE
0x18000bed5  sub     ecx, 1
0x18000bed8  jz      loc_18000BF94
0x18000bede  cmp     ecx, 1
0x18000bee1  jnz     short loc_18000BF44
0x18000bee3  mov     dword ptr [rbx], 5
0x18000bee9  jmp     loc_18000BF94
0x18000beee  mov     eax, cs:dword_18004C9F8
0x18000bef4  mov     edx, esi
0x18000bef6  mov     [rbx+18h], eax
0x18000bef9  mov     rcx, rdi
0x18000befc  mov     eax, cs:dword_18004C9F4
0x18000bf02  mov     [rbx+1Ch], eax
0x18000bf05  call    FsmSendConfigReq
0x18000bf0a  test    eax, eax
0x18000bf0c  jz      loc_18000BF94
0x18000bf12  mov     dword ptr [rbx], 6
0x18000bf18  jmp     short loc_18000BF94
0x18000bf1a  mov     edx, esi
0x18000bf1c  mov     rcx, rdi
0x18000bf1f  call    FsmThisLayerStarted
0x18000bf24  test    eax, eax
0x18000bf26  jz      short loc_18000BF94
0x18000bf28  mov     dword ptr [rbx], 1
0x18000bf2e  jmp     short loc_18000BF94
0x18000bf30  sub     ecx, 6
0x18000bf33  jz      short loc_18000BF94
0x18000bf35  sub     ecx, 1
0x18000bf38  jz      short loc_18000BF94
0x18000bf3a  sub     ecx, 1
0x18000bf3d  jz      short loc_18000BF94
0x18000bf3f  cmp     ecx, 1
0x18000bf42  jz      short loc_18000BF94
0x18000bf44  cmp     cs:byte_18004CF33, 0
0x18000bf4b  jge     short loc_18000BF94
0x18000bf4d  xor     eax, eax
0x18000bf4f  lea     rdx, aIllegalTransit_7; "Illegal transition->FsmOpen received wh"...
0x18000bf56  mov     word ptr [rsp+838h+var_818], ax
0x18000bf5b  lea     rcx, [rsp+838h+var_818]
0x18000bf60  movsxd  r8, dword ptr [rbx]
0x18000bf63  lea     rax, FsmStates
0x18000bf6a  mov     r8, [rax+r8*8]
0x18000bf6e  call    FormatRRASErrorString
0x18000bf73  cmp     cs:byte_18004CF33, 0
0x18000bf7a  jge     short loc_18000BF94
0x18000bf7c  lea     r8, [rsp+838h+var_818]
0x18000bf81  lea     rdx, RasPppTraceError
0x18000bf88  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bf8f  call    McTemplateU0z_EventWriteTransfer
0x18000bf94  mov     rcx, [rsp+838h+var_18]
0x18000bf9c  xor     rcx, rsp; StackCookie
0x18000bf9f  call    __security_check_cookie
0x18000bfa4  lea     r11, [rsp+838h+var_8]
0x18000bfac  mov     rbx, [r11+20h]
0x18000bfb0  mov     rsi, [r11+28h]
0x18000bfb4  mov     rsp, r11
0x18000bfb7  pop     rdi
0x18000bfb8  retn
```
