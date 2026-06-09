# FsmDown

- ea: `0x18000bc28`
- end: `0x18000be05`
- name: `FsmDown`
- size: `477`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180001e00`
- `0x18000e100`
- `0x1800155b8`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18000bc28`
- `0x18000d020`
- `0x18000e100`
- `0x18000e750`
- `0x18000f528`
- `0x180011064`
- `0x18002a138`

## string_xrefs

- `0x18000bc8c`: `FsmDown event received for protocol %x on port %d`

## pseudocode

```c
unsigned int __fastcall FsmDown(__int64 a1, __int64 a2)
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
  int v14; // [rsp+30h] [rbp-818h] BYREF
  char v15[2044]; // [rsp+34h] [rbp-814h] BYREF

  v2 = (unsigned int)a2;
  v14 = 0;
  PointerToCPCB = (int *)GetPointerToCPCB(a1, a2);
  result = (unsigned int)memset_0(v15, 0, sizeof(v15));
  if ( PointerToCPCB )
  {
    if ( (byte_18004CF34 & 1) != 0 )
    {
      v6 = *(_QWORD *)(a1 + 16);
      LOWORD(v14) = 0;
      FormatRRASErrorString(
        &v14,
        L"FsmDown event received for protocol %x on port %d",
        *((unsigned int *)CpTable + 44 * v2),
        v6);
      if ( (byte_18004CF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v14);
    }
    result = RemoveFromTimerQ(*(_DWORD *)(a1 + 64), PointerToCPCB[2], *((_DWORD *)CpTable + 44 * v2), 0, 0);
    v7 = *PointerToCPCB;
    if ( *PointerToCPCB > 5 )
    {
      v11 = v7 - 6;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            if ( v13 != 1 )
              goto LABEL_25;
            result = FsmThisLayerDown(a1, (unsigned int)v2);
LABEL_15:
            if ( !result )
              return result;
          }
        }
      }
    }
    else if ( v7 != 5 )
    {
      if ( !v7 )
        goto LABEL_25;
      v8 = v7 - 1;
      if ( !v8 )
        goto LABEL_25;
      v9 = v8 - 1;
      if ( !v9 )
      {
LABEL_12:
        result = FsmReset(a1, (unsigned int)v2);
        if ( !result )
          return result;
        *PointerToCPCB = 0;
        goto LABEL_18;
      }
      v10 = v9 - 1;
      if ( v10 )
      {
        if ( v10 == 1 )
          goto LABEL_12;
LABEL_25:
        if ( byte_18004CF33 < 0 )
        {
          LOWORD(v14) = 0;
          result = FormatRRASErrorString(
                     &v14,
                     L"Illegal transition->FsmDown received while in %hs state",
                     FsmStates[*PointerToCPCB]);
          if ( byte_18004CF33 < 0 )
            result = McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v14);
        }
LABEL_18:
        if ( !(_DWORD)v2 )
          *(_DWORD *)(a1 + 48) = 0;
        return result;
      }
      result = FsmThisLayerStarted(a1, (unsigned int)v2);
      goto LABEL_15;
    }
    result = FsmReset(a1, (unsigned int)v2);
    if ( !result )
      return result;
    *PointerToCPCB = 1;
    goto LABEL_18;
  }
  return result;
}

```

## disassembly

```asm
0x18000bc28  mov     [rsp+arg_10], rbx
0x18000bc2d  mov     [rsp+arg_18], rsi
0x18000bc32  push    rdi
0x18000bc33  sub     rsp, 840h
0x18000bc3a  mov     rax, cs:__security_cookie
0x18000bc41  xor     rax, rsp
0x18000bc44  mov     [rsp+848h+var_18], rax
0x18000bc4c  mov     edi, edx
0x18000bc4e  mov     rbx, rcx
0x18000bc51  call    GetPointerToCPCB
0x18000bc56  xor     r8d, r8d
0x18000bc59  lea     rcx, [rsp+848h+var_814]; void *
0x18000bc5e  mov     [rsp+848h+var_818], r8d
0x18000bc63  xor     edx, edx; Val
0x18000bc65  mov     r8d, 7FCh; Size
0x18000bc6b  mov     rsi, rax
0x18000bc6e  call    memset_0
0x18000bc73  test    rsi, rsi
0x18000bc76  jz      loc_18000BD68
0x18000bc7c  test    cs:byte_18004CF34, 1
0x18000bc83  jz      short loc_18000BCD4
0x18000bc85  mov     r8, cs:CpTable
0x18000bc8c  lea     rdx, aFsmdownEventRe; "FsmDown event received for protocol %x "...
0x18000bc93  mov     r9, [rbx+10h]
0x18000bc97  xor     eax, eax
0x18000bc99  imul    rcx, rdi, 0B0h
0x18000bca0  mov     word ptr [rsp+848h+var_818], ax
0x18000bca5  mov     r8d, [rcx+r8]
0x18000bca9  lea     rcx, [rsp+848h+var_818]
0x18000bcae  call    FormatRRASErrorString
0x18000bcb3  test    cs:byte_18004CF34, 1
0x18000bcba  jz      short loc_18000BCD4
0x18000bcbc  lea     r8, [rsp+848h+var_818]
0x18000bcc1  lea     rdx, RasPppTraceInfo
0x18000bcc8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bccf  call    McTemplateU0z_EventWriteTransfer
0x18000bcd4  mov     r8, cs:CpTable
0x18000bcdb  xor     r9d, r9d
0x18000bcde  mov     edx, [rsi+8]
0x18000bce1  imul    rcx, rdi, 0B0h
0x18000bce8  mov     [rsp+848h+var_828], 0
0x18000bcf0  mov     r8d, [rcx+r8]
0x18000bcf4  mov     ecx, [rbx+40h]
0x18000bcf7  call    RemoveFromTimerQ
0x18000bcfc  mov     ecx, [rsi]
0x18000bcfe  cmp     ecx, 5
0x18000bd01  jg      loc_18000BD8D
0x18000bd07  jz      short loc_18000BD4D
0x18000bd09  test    ecx, ecx
0x18000bd0b  jz      loc_18000BDA1
0x18000bd11  sub     ecx, 1
0x18000bd14  jz      loc_18000BDA1
0x18000bd1a  sub     ecx, 1
0x18000bd1d  jz      short loc_18000BD29
0x18000bd1f  sub     ecx, 1
0x18000bd22  jz      short loc_18000BD3F
0x18000bd24  cmp     ecx, 1
0x18000bd27  jnz     short loc_18000BDA1
0x18000bd29  mov     edx, edi
0x18000bd2b  mov     rcx, rbx
0x18000bd2e  call    FsmReset
0x18000bd33  test    eax, eax
0x18000bd35  jz      short loc_18000BD68
0x18000bd37  mov     dword ptr [rsi], 0
0x18000bd3d  jmp     short loc_18000BD61
0x18000bd3f  mov     edx, edi
0x18000bd41  mov     rcx, rbx
0x18000bd44  call    FsmThisLayerStarted
0x18000bd49  test    eax, eax
0x18000bd4b  jz      short loc_18000BD68
0x18000bd4d  mov     edx, edi
0x18000bd4f  mov     rcx, rbx
0x18000bd52  call    FsmReset
0x18000bd57  test    eax, eax
0x18000bd59  jz      short loc_18000BD68
0x18000bd5b  mov     dword ptr [rsi], 1
0x18000bd61  test    edi, edi
0x18000bd63  jnz     short loc_18000BD68
0x18000bd65  mov     [rbx+30h], edi
0x18000bd68  mov     rcx, [rsp+848h+var_18]
0x18000bd70  xor     rcx, rsp; StackCookie
0x18000bd73  call    __security_check_cookie
0x18000bd78  lea     r11, [rsp+848h+var_8]
0x18000bd80  mov     rbx, [r11+20h]
0x18000bd84  mov     rsi, [r11+28h]
0x18000bd88  mov     rsp, r11
0x18000bd8b  pop     rdi
0x18000bd8c  retn
0x18000bd8d  sub     ecx, 6
0x18000bd90  jz      short loc_18000BD4D
0x18000bd92  sub     ecx, 1
0x18000bd95  jz      short loc_18000BD4D
0x18000bd97  sub     ecx, 1
0x18000bd9a  jz      short loc_18000BD4D
0x18000bd9c  cmp     ecx, 1
0x18000bd9f  jz      short loc_18000BDF6
0x18000bda1  cmp     cs:byte_18004CF33, 0
0x18000bda8  jge     short loc_18000BD61
0x18000bdaa  xor     eax, eax
0x18000bdac  lea     rdx, aIllegalTransit_5; "Illegal transition->FsmDown received wh"...
0x18000bdb3  mov     word ptr [rsp+848h+var_818], ax
0x18000bdb8  lea     rcx, [rsp+848h+var_818]
0x18000bdbd  movsxd  r8, dword ptr [rsi]
0x18000bdc0  lea     rax, FsmStates
0x18000bdc7  mov     r8, [rax+r8*8]
0x18000bdcb  call    FormatRRASErrorString
0x18000bdd0  cmp     cs:byte_18004CF33, 0
0x18000bdd7  jge     short loc_18000BD61
0x18000bdd9  lea     r8, [rsp+848h+var_818]
0x18000bdde  lea     rdx, RasPppTraceError
0x18000bde5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bdec  call    McTemplateU0z_EventWriteTransfer
0x18000bdf1  jmp     loc_18000BD61
0x18000bdf6  mov     edx, edi
0x18000bdf8  mov     rcx, rbx
0x18000bdfb  call    FsmThisLayerDown
0x18000be00  jmp     loc_18000BD49
```
