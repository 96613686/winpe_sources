# FsmClose

- ea: `0x18000be68`
- end: `0x18000c048`
- name: `FsmClose`
- size: `480`
- prototype: ``
- caller_count: `12`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000442c`
- `0x180009920`
- `0x180009aac`
- `0x18000d450`
- `0x18000d6b4`
- `0x18000d8b4`
- `0x18000eb90`
- `0x18000ecac`
- `0x1800102bc`
- `0x180010f00`
- `0x180013cf4`
- `0x180015660`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18000be68`
- `0x18000e358`
- `0x18000e540`
- `0x18000e7a4`
- `0x18000f984`
- `0x1800115d0`
- `0x18002b0dc`

## string_xrefs

- `0x18000beca`: `FsmClose event received for protocol %x on port %d`

## pseudocode

```c
unsigned int __fastcall FsmClose(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  int *PointerToCPCB; // rsi
  unsigned int result; // eax
  __int64 v6; // r9
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // [rsp+40h] [rbp-818h] BYREF
  char v15[2044]; // [rsp+44h] [rbp-814h] BYREF

  v2 = (unsigned int)a2;
  v14 = 0;
  PointerToCPCB = (int *)GetPointerToCPCB(a1, a2);
  result = (unsigned int)memset_0(v15, 0, sizeof(v15));
  if ( !PointerToCPCB )
    return result;
  if ( (byte_18004DF34 & 1) != 0 )
  {
    v6 = *(_QWORD *)(a1 + 16);
    LOWORD(v14) = 0;
    FormatRRASErrorString(
      &v14,
      L"FsmClose event received for protocol %x on port %d",
      *((unsigned int *)CpTable + 44 * v2),
      v6);
    if ( (byte_18004DF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v14);
  }
  if ( !(_DWORD)v2 )
    *(_DWORD *)(a1 + 48) = 0;
  result = RemoveFromTimerQ(*(_DWORD *)(a1 + 64), PointerToCPCB[2], *((_DWORD *)CpTable + 44 * v2), 0, 0);
  v7 = *PointerToCPCB;
  if ( *PointerToCPCB > 5 )
  {
    v11 = v7 - 6;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( !v12 || (v13 = v12 - 1) == 0 )
      {
LABEL_27:
        PointerToCPCB[6] = dword_18004D9F8;
        PointerToCPCB[7] = dword_18004D9F4;
        result = FsmSendTermReq(a1, (unsigned int)v2);
        *PointerToCPCB = 4;
        return result;
      }
      if ( v13 != 1 )
        goto LABEL_23;
    }
    result = FsmThisLayerDown(a1, (unsigned int)v2);
    if ( !result )
      return result;
    goto LABEL_27;
  }
  if ( v7 == 5 )
  {
    *PointerToCPCB = 4;
    return FsmThisLayerFinished(a1, v2, 0);
  }
  if ( !v7 )
    return FsmThisLayerFinished(a1, v2, 0);
  v8 = v7 - 1;
  if ( !v8 )
  {
    *PointerToCPCB = 0;
    return FsmThisLayerFinished(a1, v2, 0);
  }
  v9 = v8 - 1;
  if ( !v9 )
    return FsmThisLayerFinished(a1, v2, 0);
  v10 = v9 - 1;
  if ( !v10 )
  {
    *PointerToCPCB = 2;
    return FsmThisLayerFinished(a1, v2, 0);
  }
  if ( v10 == 1 )
    return FsmThisLayerFinished(a1, v2, 0);
LABEL_23:
  if ( byte_18004DF33 < 0 )
  {
    LOWORD(v14) = 0;
    result = FormatRRASErrorString(
               &v14,
               L"Illegal transition->FsmClose received while in %hs state",
               FsmStates[*PointerToCPCB]);
    if ( byte_18004DF33 < 0 )
      return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v14);
  }
  return result;
}

```

## disassembly

```asm
0x18000be68  mov     [rsp+arg_10], rbx
0x18000be6d  mov     [rsp+arg_18], rsi
0x18000be72  push    rdi
0x18000be73  sub     rsp, 850h
0x18000be7a  mov     rax, cs:__security_cookie
0x18000be81  xor     rax, rsp
0x18000be84  mov     [rsp+858h+var_18], rax
0x18000be8c  mov     edi, edx
0x18000be8e  mov     rbx, rcx
0x18000be91  call    GetPointerToCPCB
0x18000be96  xor     ecx, ecx
0x18000be98  xor     edx, edx; Val
0x18000be9a  mov     [rsp+858h+var_818], ecx
0x18000be9e  mov     r8d, 7FCh; Size
0x18000bea4  lea     rcx, [rsp+858h+var_814]; void *
0x18000bea9  mov     rsi, rax
0x18000beac  call    memset_0
0x18000beb1  test    rsi, rsi
0x18000beb4  jz      loc_18000C022
0x18000beba  test    cs:byte_18004DF34, 1
0x18000bec1  jz      short loc_18000BF12
0x18000bec3  mov     r8, cs:CpTable
0x18000beca  lea     rdx, aFsmcloseEventR; "FsmClose event received for protocol %x"...
0x18000bed1  mov     r9, [rbx+10h]
0x18000bed5  xor     eax, eax
0x18000bed7  imul    rcx, rdi, 0B0h
0x18000bede  mov     word ptr [rsp+858h+var_818], ax
0x18000bee3  mov     r8d, [rcx+r8]
0x18000bee7  lea     rcx, [rsp+858h+var_818]
0x18000beec  call    FormatRRASErrorString
0x18000bef1  test    cs:byte_18004DF34, 1
0x18000bef8  jz      short loc_18000BF12
0x18000befa  lea     r8, [rsp+858h+var_818]
0x18000beff  lea     rdx, RasPppTraceInfo
0x18000bf06  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bf0d  call    McTemplateU0z_EventWriteTransfer
0x18000bf12  test    edi, edi
0x18000bf14  jnz     short loc_18000BF19
0x18000bf16  mov     [rbx+30h], edi
0x18000bf19  mov     r8, cs:CpTable
0x18000bf20  xor     r9d, r9d
0x18000bf23  mov     edx, [rsi+8]
0x18000bf26  imul    rcx, rdi, 0B0h
0x18000bf2d  mov     [rsp+858h+var_838], 0
0x18000bf35  mov     r8d, [rcx+r8]
0x18000bf39  mov     ecx, [rbx+40h]
0x18000bf3c  call    RemoveFromTimerQ
0x18000bf41  mov     ecx, [rsi]
0x18000bf43  cmp     ecx, 5
0x18000bf46  jg      short loc_18000BF8C
0x18000bf48  jz      short loc_18000BF84
0x18000bf4a  test    ecx, ecx
0x18000bf4c  jz      short loc_18000BF6A
0x18000bf4e  sub     ecx, 1
0x18000bf51  jz      short loc_18000BF7C
0x18000bf53  sub     ecx, 1
0x18000bf56  jz      short loc_18000BF6A
0x18000bf58  sub     ecx, 1
0x18000bf5b  jz      short loc_18000BF64
0x18000bf5d  cmp     ecx, 1
0x18000bf60  jz      short loc_18000BF6A
0x18000bf62  jmp     short loc_18000BFA0
0x18000bf64  mov     dword ptr [rsi], 2
0x18000bf6a  xor     r8d, r8d
0x18000bf6d  mov     edx, edi
0x18000bf6f  mov     rcx, rbx
0x18000bf72  call    FsmThisLayerFinished
0x18000bf77  jmp     loc_18000C022
0x18000bf7c  mov     dword ptr [rsi], 0
0x18000bf82  jmp     short loc_18000BF6A
0x18000bf84  mov     dword ptr [rsi], 4
0x18000bf8a  jmp     short loc_18000BF6A
0x18000bf8c  sub     ecx, 6
0x18000bf8f  jz      short loc_18000BFF2
0x18000bf91  sub     ecx, 1
0x18000bf94  jz      short loc_18000C000
0x18000bf96  sub     ecx, 1
0x18000bf99  jz      short loc_18000C000
0x18000bf9b  cmp     ecx, 1
0x18000bf9e  jz      short loc_18000BFF2
0x18000bfa0  cmp     cs:byte_18004DF33, 0
0x18000bfa7  jge     short loc_18000C022
0x18000bfa9  xor     eax, eax
0x18000bfab  lea     rdx, aIllegalTransit_1; "Illegal transition->FsmClose received w"...
0x18000bfb2  mov     word ptr [rsp+858h+var_818], ax
0x18000bfb7  lea     rcx, [rsp+858h+var_818]
0x18000bfbc  movsxd  r8, dword ptr [rsi]
0x18000bfbf  lea     rax, FsmStates
0x18000bfc6  mov     r8, [rax+r8*8]
0x18000bfca  call    FormatRRASErrorString
0x18000bfcf  cmp     cs:byte_18004DF33, 0
0x18000bfd6  jge     short loc_18000C022
0x18000bfd8  lea     r8, [rsp+858h+var_818]
0x18000bfdd  lea     rdx, RasPppTraceError
0x18000bfe4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bfeb  call    McTemplateU0z_EventWriteTransfer
0x18000bff0  jmp     short loc_18000C022
0x18000bff2  mov     edx, edi
0x18000bff4  mov     rcx, rbx
0x18000bff7  call    FsmThisLayerDown
0x18000bffc  test    eax, eax
0x18000bffe  jz      short loc_18000C022
0x18000c000  mov     eax, cs:dword_18004D9F8
0x18000c006  mov     edx, edi
0x18000c008  mov     [rsi+18h], eax
0x18000c00b  mov     rcx, rbx
0x18000c00e  mov     eax, cs:dword_18004D9F4
0x18000c014  mov     [rsi+1Ch], eax
0x18000c017  call    FsmSendTermReq
0x18000c01c  mov     dword ptr [rsi], 4
0x18000c022  mov     rcx, [rsp+858h+var_18]
0x18000c02a  xor     rcx, rsp; StackCookie
0x18000c02d  call    __security_check_cookie
0x18000c032  lea     r11, [rsp+858h+var_8]
0x18000c03a  mov     rbx, [r11+20h]
0x18000c03e  mov     rsi, [r11+28h]
0x18000c042  mov     rsp, r11
0x18000c045  pop     rdi
0x18000c046  retn
```
