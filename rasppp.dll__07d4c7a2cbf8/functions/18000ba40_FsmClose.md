# FsmClose

- ea: `0x18000ba40`
- end: `0x18000bc1f`
- name: `FsmClose`
- size: `479`
- prototype: ``
- caller_count: `12`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180004388`
- `0x180009560`
- `0x1800096e8`
- `0x18000d020`
- `0x18000d284`
- `0x18000d480`
- `0x18000e750`
- `0x18000e86c`
- `0x18000fe04`
- `0x1800109cc`
- `0x180013630`
- `0x180014f20`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18000ba40`
- `0x18000df18`
- `0x18000e100`
- `0x18000e364`
- `0x18000f528`
- `0x180011064`
- `0x18002a138`

## string_xrefs

- `0x18000baa2`: `FsmClose event received for protocol %x on port %d`

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
  if ( (byte_18004CF34 & 1) != 0 )
  {
    v6 = *(_QWORD *)(a1 + 16);
    LOWORD(v14) = 0;
    FormatRRASErrorString(
      &v14,
      L"FsmClose event received for protocol %x on port %d",
      *((unsigned int *)CpTable + 44 * v2),
      v6);
    if ( (byte_18004CF34 & 1) != 0 )
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
        PointerToCPCB[6] = dword_18004C9F8;
        PointerToCPCB[7] = dword_18004C9F4;
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
  if ( byte_18004CF33 < 0 )
  {
    LOWORD(v14) = 0;
    result = FormatRRASErrorString(
               &v14,
               L"Illegal transition->FsmClose received while in %hs state",
               FsmStates[*PointerToCPCB]);
    if ( byte_18004CF33 < 0 )
      return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v14);
  }
  return result;
}

```

## disassembly

```asm
0x18000ba40  mov     [rsp+arg_10], rbx
0x18000ba45  mov     [rsp+arg_18], rsi
0x18000ba4a  push    rdi
0x18000ba4b  sub     rsp, 850h
0x18000ba52  mov     rax, cs:__security_cookie
0x18000ba59  xor     rax, rsp
0x18000ba5c  mov     [rsp+858h+var_18], rax
0x18000ba64  mov     edi, edx
0x18000ba66  mov     rbx, rcx
0x18000ba69  call    GetPointerToCPCB
0x18000ba6e  xor     ecx, ecx
0x18000ba70  xor     edx, edx; Val
0x18000ba72  mov     [rsp+858h+var_818], ecx
0x18000ba76  mov     r8d, 7FCh; Size
0x18000ba7c  lea     rcx, [rsp+858h+var_814]; void *
0x18000ba81  mov     rsi, rax
0x18000ba84  call    memset_0
0x18000ba89  test    rsi, rsi
0x18000ba8c  jz      loc_18000BBFA
0x18000ba92  test    cs:byte_18004CF34, 1
0x18000ba99  jz      short loc_18000BAEA
0x18000ba9b  mov     r8, cs:CpTable
0x18000baa2  lea     rdx, aFsmcloseEventR; "FsmClose event received for protocol %x"...
0x18000baa9  mov     r9, [rbx+10h]
0x18000baad  xor     eax, eax
0x18000baaf  imul    rcx, rdi, 0B0h
0x18000bab6  mov     word ptr [rsp+858h+var_818], ax
0x18000babb  mov     r8d, [rcx+r8]
0x18000babf  lea     rcx, [rsp+858h+var_818]
0x18000bac4  call    FormatRRASErrorString
0x18000bac9  test    cs:byte_18004CF34, 1
0x18000bad0  jz      short loc_18000BAEA
0x18000bad2  lea     r8, [rsp+858h+var_818]
0x18000bad7  lea     rdx, RasPppTraceInfo
0x18000bade  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bae5  call    McTemplateU0z_EventWriteTransfer
0x18000baea  test    edi, edi
0x18000baec  jnz     short loc_18000BAF1
0x18000baee  mov     [rbx+30h], edi
0x18000baf1  mov     r8, cs:CpTable
0x18000baf8  xor     r9d, r9d
0x18000bafb  mov     edx, [rsi+8]
0x18000bafe  imul    rcx, rdi, 0B0h
0x18000bb05  mov     [rsp+858h+var_838], 0
0x18000bb0d  mov     r8d, [rcx+r8]
0x18000bb11  mov     ecx, [rbx+40h]
0x18000bb14  call    RemoveFromTimerQ
0x18000bb19  mov     ecx, [rsi]
0x18000bb1b  cmp     ecx, 5
0x18000bb1e  jg      short loc_18000BB64
0x18000bb20  jz      short loc_18000BB5C
0x18000bb22  test    ecx, ecx
0x18000bb24  jz      short loc_18000BB42
0x18000bb26  sub     ecx, 1
0x18000bb29  jz      short loc_18000BB54
0x18000bb2b  sub     ecx, 1
0x18000bb2e  jz      short loc_18000BB42
0x18000bb30  sub     ecx, 1
0x18000bb33  jz      short loc_18000BB3C
0x18000bb35  cmp     ecx, 1
0x18000bb38  jz      short loc_18000BB42
0x18000bb3a  jmp     short loc_18000BB78
0x18000bb3c  mov     dword ptr [rsi], 2
0x18000bb42  xor     r8d, r8d
0x18000bb45  mov     edx, edi
0x18000bb47  mov     rcx, rbx
0x18000bb4a  call    FsmThisLayerFinished
0x18000bb4f  jmp     loc_18000BBFA
0x18000bb54  mov     dword ptr [rsi], 0
0x18000bb5a  jmp     short loc_18000BB42
0x18000bb5c  mov     dword ptr [rsi], 4
0x18000bb62  jmp     short loc_18000BB42
0x18000bb64  sub     ecx, 6
0x18000bb67  jz      short loc_18000BBCA
0x18000bb69  sub     ecx, 1
0x18000bb6c  jz      short loc_18000BBD8
0x18000bb6e  sub     ecx, 1
0x18000bb71  jz      short loc_18000BBD8
0x18000bb73  cmp     ecx, 1
0x18000bb76  jz      short loc_18000BBCA
0x18000bb78  cmp     cs:byte_18004CF33, 0
0x18000bb7f  jge     short loc_18000BBFA
0x18000bb81  xor     eax, eax
0x18000bb83  lea     rdx, aIllegalTransit_1; "Illegal transition->FsmClose received w"...
0x18000bb8a  mov     word ptr [rsp+858h+var_818], ax
0x18000bb8f  lea     rcx, [rsp+858h+var_818]
0x18000bb94  movsxd  r8, dword ptr [rsi]
0x18000bb97  lea     rax, FsmStates
0x18000bb9e  mov     r8, [rax+r8*8]
0x18000bba2  call    FormatRRASErrorString
0x18000bba7  cmp     cs:byte_18004CF33, 0
0x18000bbae  jge     short loc_18000BBFA
0x18000bbb0  lea     r8, [rsp+858h+var_818]
0x18000bbb5  lea     rdx, RasPppTraceError
0x18000bbbc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bbc3  call    McTemplateU0z_EventWriteTransfer
0x18000bbc8  jmp     short loc_18000BBFA
0x18000bbca  mov     edx, edi
0x18000bbcc  mov     rcx, rbx
0x18000bbcf  call    FsmThisLayerDown
0x18000bbd4  test    eax, eax
0x18000bbd6  jz      short loc_18000BBFA
0x18000bbd8  mov     eax, cs:dword_18004C9F8
0x18000bbde  mov     edx, edi
0x18000bbe0  mov     [rsi+18h], eax
0x18000bbe3  mov     rcx, rbx
0x18000bbe6  mov     eax, cs:dword_18004C9F4
0x18000bbec  mov     [rsi+1Ch], eax
0x18000bbef  call    FsmSendTermReq
0x18000bbf4  mov     dword ptr [rsi], 4
0x18000bbfa  mov     rcx, [rsp+858h+var_18]
0x18000bc02  xor     rcx, rsp; StackCookie
0x18000bc05  call    __security_check_cookie
0x18000bc0a  lea     r11, [rsp+858h+var_8]
0x18000bc12  mov     rbx, [r11+20h]
0x18000bc16  mov     rsi, [r11+28h]
0x18000bc1a  mov     rsp, r11
0x18000bc1d  pop     rdi
0x18000bc1e  retn
```
