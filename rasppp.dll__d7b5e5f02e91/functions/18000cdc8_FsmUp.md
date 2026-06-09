# FsmUp

- ea: `0x18000cdc8`
- end: `0x18000cf33`
- name: `FsmUp`
- size: `363`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001e0c`
- `0x180014808`
- `0x180016260`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18000cdc8`
- `0x18000d6b4`
- `0x1800115d0`
- `0x18002b0dc`

## string_xrefs

- `0x18000ce2a`: `FsmUp event received for protocol %x on port %d`

## pseudocode

```c
ULONG __fastcall FsmUp(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  int *PointerToCPCB; // rbx
  ULONG result; // eax
  __int64 v6; // r9
  int v7; // [rsp+20h] [rbp-818h] BYREF
  _BYTE v8[2044]; // [rsp+24h] [rbp-814h] BYREF

  v2 = (unsigned int)a2;
  v7 = 0;
  PointerToCPCB = (int *)GetPointerToCPCB(a1, a2);
  result = (unsigned int)memset_0(v8, 0, sizeof(v8));
  if ( PointerToCPCB )
  {
    if ( (byte_18004DF34 & 1) != 0 )
    {
      v6 = *(_QWORD *)(a1 + 16);
      LOWORD(v7) = 0;
      result = FormatRRASErrorString(
                 (wchar_t *)&v7,
                 L"FsmUp event received for protocol %x on port %d",
                 *((unsigned int *)CpTable + 44 * v2),
                 v6);
      if ( (byte_18004DF34 & 1) != 0 )
        result = McTemplateU0z_EventWriteTransfer(
                   &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                   (const EVENT_DESCRIPTOR *)RasPppTraceInfo,
                   (const wchar_t *)&v7);
    }
    if ( !(_DWORD)v2 )
      *(_DWORD *)(a1 + 48) = 0;
    if ( *PointerToCPCB )
    {
      if ( *PointerToCPCB == 1 )
      {
        PointerToCPCB[6] = dword_18004D9F8;
        PointerToCPCB[7] = dword_18004D9F4;
        result = FsmSendConfigReq(a1, (unsigned int)v2);
        if ( result )
          *PointerToCPCB = 6;
        else
          PointerToCPCB[11] = 0;
      }
      else if ( byte_18004DF33 < 0 )
      {
        LOWORD(v7) = 0;
        result = FormatRRASErrorString(
                   (wchar_t *)&v7,
                   L"Illegal transition -> FsmUp received while in %hs state",
                   FsmStates[*PointerToCPCB]);
        if ( byte_18004DF33 < 0 )
          return McTemplateU0z_EventWriteTransfer(
                   &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                   (const EVENT_DESCRIPTOR *)RasPppTraceError,
                   (const wchar_t *)&v7);
      }
    }
    else
    {
      *PointerToCPCB = 2;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000cdc8  mov     [rsp+arg_10], rbx
0x18000cdcd  mov     [rsp+arg_18], rsi
0x18000cdd2  push    rdi
0x18000cdd3  sub     rsp, 830h
0x18000cdda  mov     rax, cs:__security_cookie
0x18000cde1  xor     rax, rsp
0x18000cde4  mov     [rsp+838h+var_18], rax
0x18000cdec  mov     esi, edx
0x18000cdee  mov     rdi, rcx
0x18000cdf1  call    GetPointerToCPCB
0x18000cdf6  xor     ecx, ecx
0x18000cdf8  xor     edx, edx; Val
0x18000cdfa  mov     [rsp+838h+var_818], ecx
0x18000cdfe  mov     r8d, 7FCh; Size
0x18000ce04  lea     rcx, [rsp+838h+var_814]; void *
0x18000ce09  mov     rbx, rax
0x18000ce0c  call    memset_0
0x18000ce11  test    rbx, rbx
0x18000ce14  jz      loc_18000CF0D
0x18000ce1a  test    cs:byte_18004DF34, 1
0x18000ce21  jz      short loc_18000CE72
0x18000ce23  mov     r8, cs:CpTable
0x18000ce2a  lea     rdx, aFsmupEventRece; "FsmUp event received for protocol %x on"...
0x18000ce31  mov     r9, [rdi+10h]
0x18000ce35  xor     eax, eax
0x18000ce37  imul    rcx, rsi, 0B0h
0x18000ce3e  mov     word ptr [rsp+838h+var_818], ax
0x18000ce43  mov     r8d, [rcx+r8]
0x18000ce47  lea     rcx, [rsp+838h+var_818]
0x18000ce4c  call    FormatRRASErrorString
0x18000ce51  test    cs:byte_18004DF34, 1
0x18000ce58  jz      short loc_18000CE72
0x18000ce5a  lea     r8, [rsp+838h+var_818]
0x18000ce5f  lea     rdx, RasPppTraceInfo
0x18000ce66  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ce6d  call    McTemplateU0z_EventWriteTransfer
0x18000ce72  test    esi, esi
0x18000ce74  jnz     short loc_18000CE79
0x18000ce76  mov     [rdi+30h], esi
0x18000ce79  mov     ecx, [rbx]
0x18000ce7b  test    ecx, ecx
0x18000ce7d  jz      loc_18000CF07
0x18000ce83  cmp     ecx, 1
0x18000ce86  jz      short loc_18000CEDA
0x18000ce88  cmp     cs:byte_18004DF33, 0
0x18000ce8f  jge     short loc_18000CF0D
0x18000ce91  xor     eax, eax
0x18000ce93  lea     rdx, aIllegalTransit_6; "Illegal transition -> FsmUp received wh"...
0x18000ce9a  mov     word ptr [rsp+838h+var_818], ax
0x18000ce9f  lea     rcx, [rsp+838h+var_818]
0x18000cea4  movsxd  r8, dword ptr [rbx]
0x18000cea7  lea     rax, FsmStates
0x18000ceae  mov     r8, [rax+r8*8]
0x18000ceb2  call    FormatRRASErrorString
0x18000ceb7  cmp     cs:byte_18004DF33, 0
0x18000cebe  jge     short loc_18000CF0D
0x18000cec0  lea     r8, [rsp+838h+var_818]
0x18000cec5  lea     rdx, RasPppTraceError
0x18000cecc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ced3  call    McTemplateU0z_EventWriteTransfer
0x18000ced8  jmp     short loc_18000CF0D
0x18000ceda  mov     eax, cs:dword_18004D9F8
0x18000cee0  mov     edx, esi
0x18000cee2  mov     [rbx+18h], eax
0x18000cee5  mov     rcx, rdi
0x18000cee8  mov     eax, cs:dword_18004D9F4
0x18000ceee  mov     [rbx+1Ch], eax
0x18000cef1  call    FsmSendConfigReq
0x18000cef6  test    eax, eax
0x18000cef8  jnz     short loc_18000CEFF
0x18000cefa  mov     [rbx+2Ch], eax
0x18000cefd  jmp     short loc_18000CF0D
0x18000ceff  mov     dword ptr [rbx], 6
0x18000cf05  jmp     short loc_18000CF0D
0x18000cf07  mov     dword ptr [rbx], 2
0x18000cf0d  mov     rcx, [rsp+838h+var_18]
0x18000cf15  xor     rcx, rsp; StackCookie
0x18000cf18  call    __security_check_cookie
0x18000cf1d  lea     r11, [rsp+838h+var_8]
0x18000cf25  mov     rbx, [r11+20h]
0x18000cf29  mov     rsi, [r11+28h]
0x18000cf2d  mov     rsp, r11
0x18000cf30  pop     rdi
0x18000cf31  retn
```
