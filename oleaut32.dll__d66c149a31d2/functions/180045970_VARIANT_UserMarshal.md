# VARIANT_UserMarshal

- ea: `0x180045970`
- end: `0x180045d3b`
- name: `VARIANT_UserMarshal`
- size: `971`
- prototype: `unsigned __int8 *__stdcall(unsigned int *, unsigned __int8 *, VARIANT *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003d540`
- `0x180045970`

## callees

- `0x18003d540`
- `0x180044ddc`
- `0x180044fb0`
- `0x180045970`
- `0x1800716f0`

## import_xrefs

- `combase!WdtpInterfacePointer_UserMarshal` at `0x180045bbe`
- `combase!WdtpInterfacePointer_UserMarshal` at `0x180045bbe`
- `combase!__imp_CoDoesOtherSideVariantMarshalingNeedTrailingPadding` at `0x180045d1a`
- `combase!__imp_CoDoesOtherSideVariantMarshalingNeedTrailingPadding` at `0x180045d1a`
- `RPCRT4!RpcRaiseException` at `0x180045a5c`
- `RPCRT4!RpcRaiseException` at `0x180045ad2`
- `RPCRT4!RpcRaiseException` at `0x180045c9f`
- `RPCRT4!RpcRaiseException` at `0x180045a5c`
- `RPCRT4!RpcRaiseException` at `0x180045ad2`
- `RPCRT4!RpcRaiseException` at `0x180045c9f`

## pseudocode

```c
unsigned __int8 *__stdcall VARIANT_UserMarshal(unsigned int *a1, unsigned __int8 *a2, VARIANT *a3)
{
  __int16 *v5; // r11
  unsigned __int8 *v6; // r10
  unsigned __int8 *v7; // r14
  unsigned __int16 v8; // dx
  unsigned __int16 v9; // ax
  int v10; // edx
  unsigned __int8 *v11; // rax
  unsigned __int16 **v12; // r10
  unsigned __int8 *v13; // rbx
  unsigned __int8 *v14; // rdi
  unsigned __int8 *v15; // rbx
  _QWORD *v16; // r10
  unsigned __int8 *v17; // rax
  GUID *v18; // rax
  unsigned __int8 *v19; // rbx
  _QWORD *v20; // r10
  unsigned __int8 *v21; // rbx
  _OWORD *v22; // r10
  unsigned __int8 *v23; // [rsp+68h] [rbp+38h] BYREF

  v23 = a2;
  if ( !a3 )
    return a2;
  AlignAndZeroGap(&v23, 7u);
  v6 = v23;
  v7 = v23;
  *((_DWORD *)v23 + 1) = 0;
  v8 = *v5;
  *((_WORD *)v7 + 4) = *v5;
  *((_WORD *)v7 + 5) = v5[1];
  *((_WORD *)v7 + 6) = v5[2];
  *((_WORD *)v7 + 7) = v5[3];
  v9 = v8 & 0x6000;
  if ( (v8 & 0x2000) == 0 )
    v9 = v8;
  v10 = v9;
  v11 = v6 + 20;
  v23 = v6 + 20;
  *((_DWORD *)v6 + 4) = v10;
  if ( (v10 & 0x4000) != 0 )
  {
    v12 = (unsigned __int16 **)*((_QWORD *)v5 + 1);
    if ( !v12 )
      goto LABEL_62;
    v13 = v11 + 4;
    *(_DWORD *)v11 = 4;
    v23 = v11 + 4;
    LOWORD(v10) = v10 & 0xBFFF;
    v14 = v11;
  }
  else
  {
    if ( v10 == 12 )
      RpcRaiseException(-2147024809);
    v23 = v6 + 20;
    v14 = 0;
    v13 = v6 + 20;
    v12 = (unsigned __int16 **)v5;
    if ( (_WORD)v10 != 14 )
      v12 = (unsigned __int16 **)(v5 + 4);
  }
  if ( (unsigned __int16)v10 > 0x2000u )
    goto LABEL_24;
  if ( (unsigned __int16)v10 == 0x2000 )
  {
    if ( !*v12 )
      goto LABEL_68;
    *(_DWORD *)v13 = *(_DWORD *)v12 | 1;
    v17 = LPSAFEARRAY_Marshal(a1, v13 + 4, v12, 0);
    goto LABEL_67;
  }
  if ( (unsigned __int16)v10 > 0xDu )
  {
    if ( (unsigned __int16)v10 <= 0x15u )
    {
      switch ( (unsigned __int16)v10 )
      {
        case 0x15u:
          goto LABEL_50;
        case 0xEu:
          AlignAndZeroGap(&v23, 7u);
          v21 = v23;
          *(_OWORD *)v23 = *v22;
          v13 = v21 + 16;
          v23 = v13;
          if ( v14 )
            *(_DWORD *)v14 = 16;
          goto LABEL_71;
        case 0x10u:
        case 0x11u:
          *v13++ = *(_BYTE *)v12;
          goto LABEL_70;
        case 0x12u:
          goto LABEL_51;
      }
      if ( (unsigned __int16)v10 != 19 )
      {
        if ( (unsigned __int16)v10 != 20 )
          goto LABEL_24;
LABEL_50:
        AlignAndZeroGap(&v23, 7u);
        v19 = v23;
        *(_QWORD *)v23 = *v20;
        v13 = v19 + 8;
LABEL_70:
        v23 = v13;
        goto LABEL_71;
      }
LABEL_59:
      *(_DWORD *)v13 = *(_DWORD *)v12;
LABEL_69:
      v13 += 4;
      goto LABEL_70;
    }
    if ( (unsigned __int16)v10 == 22 || (unsigned __int16)v10 == 23 )
      goto LABEL_59;
    if ( (unsigned __int16)v10 != 36 )
    {
      if ( (unsigned int)(unsigned __int16)v10 - 37 > 1 )
        goto LABEL_24;
      goto LABEL_59;
    }
    if ( v14 )
    {
      v13 = v14;
      if ( !*((_QWORD *)v5 + 2) )
LABEL_62:
        RpcRaiseException(1780);
    }
    else if ( !*((_QWORD *)v5 + 2) )
    {
      goto LABEL_68;
    }
    *(_DWORD *)v13 = *((_DWORD *)v5 + 4) | 1;
    v17 = (unsigned __int8 *)BRECORD_UserMarshal((_DWORD)a1, (int)v13 + 4, 1, *((_QWORD *)v5 + 2), *((_QWORD *)v5 + 1));
    goto LABEL_67;
  }
  if ( (unsigned __int16)v10 == 13 )
    goto LABEL_38;
  if ( (unsigned __int16)v10 <= 6u )
  {
    if ( (unsigned __int16)v10 != 6 )
    {
      if ( (_WORD)v10 && (unsigned __int16)v10 != 1 )
      {
        if ( (unsigned __int16)v10 != 2 )
        {
          if ( (unsigned __int16)v10 != 3 && (unsigned __int16)v10 != 4 )
          {
            if ( (unsigned __int16)v10 != 5 )
              goto LABEL_24;
            goto LABEL_27;
          }
          goto LABEL_59;
        }
        goto LABEL_51;
      }
      if ( !v14 )
        goto LABEL_71;
      goto LABEL_24;
    }
LABEL_27:
    AlignAndZeroGap(&v23, 7u);
    v15 = v23;
    *(_QWORD *)v23 = *v16;
    v13 = v15 + 8;
    v23 = v13;
    if ( v14 )
      *(_DWORD *)v14 = 8;
    goto LABEL_71;
  }
  switch ( (unsigned __int16)v10 )
  {
    case 7u:
      goto LABEL_27;
    case 8u:
      if ( !*v12 )
        goto LABEL_68;
      *(_DWORD *)v13 = *(_DWORD *)v12 | 1;
      v17 = BSTR_UserMarshal(a1, v13 + 4, v12);
LABEL_67:
      v23 = v17;
      v13 = v17;
      goto LABEL_71;
    case 9u:
LABEL_38:
      if ( *v12 )
      {
        *(_DWORD *)v13 = *(_DWORD *)v12 | 1;
        v18 = &IID_IUnknown;
        if ( (_WORD)v10 != 13 )
          v18 = &IID_IDispatch;
        v17 = (unsigned __int8 *)WdtpInterfacePointer_UserMarshal(a1, *a1, v13 + 4, *v12, v18);
        goto LABEL_67;
      }
LABEL_68:
      *(_DWORD *)v13 = 0;
      goto LABEL_69;
    case 0xAu:
      goto LABEL_59;
    case 0xBu:
LABEL_51:
      *(_WORD *)v13 = *(_WORD *)v12;
      v13 += 2;
      goto LABEL_70;
  }
  if ( (unsigned __int16)v10 != 12 )
LABEL_24:
    RpcRaiseException(-2147352568);
  *(_DWORD *)v13 = 1919251285;
  v13 = VARIANT_UserMarshal(a1, v13 + 4, (VARIANT *)v12);
  v23 = v13;
  *(_DWORD *)v14 = 24;
LABEL_71:
  *(_DWORD *)v7 = (unsigned int)((_DWORD)v13 - (_DWORD)v7 + 7) >> 3;
  if ( (unsigned int)CoDoesOtherSideVariantMarshalingNeedTrailingPadding(a1) )
  {
    AlignAndZeroGap(&v23, 7u);
    return v23;
  }
  return v13;
}

```

## disassembly

```asm
0x180045970  mov     [rsp-28h+arg_0], rbx
0x180045975  mov     [rsp-28h+arg_10], rsi
0x18004597a  mov     [rsp-28h+arg_8], rdx
0x18004597f  push    rbp
0x180045980  push    rdi
0x180045981  push    r12
0x180045983  push    r14
0x180045985  push    r15
0x180045987  mov     rbp, rsp
0x18004598a  sub     rsp, 30h
0x18004598e  xor     r15d, r15d
0x180045991  mov     r11, r8
0x180045994  mov     rsi, rcx
0x180045997  test    r8, r8
0x18004599a  jnz     short loc_1800459B6
0x18004599c  mov     rax, rdx
0x18004599f  mov     rbx, [rsp+30h+arg_0]
0x1800459a4  mov     rsi, [rsp+30h+arg_10]
0x1800459a9  add     rsp, 30h
0x1800459ad  pop     r15
0x1800459af  pop     r14
0x1800459b1  pop     r12
0x1800459b3  pop     rdi
0x1800459b4  pop     rbp
0x1800459b5  retn
0x1800459b6  mov     dl, 7; unsigned __int8
0x1800459b8  lea     rcx, [rbp+arg_8]; unsigned __int8 **
0x1800459bc  call    ?AlignAndZeroGap@@YAXAEAPEAEE@Z; AlignAndZeroGap(uchar * &,uchar)
0x1800459c1  mov     r10, [rbp+arg_8]
0x1800459c5  mov     r8d, 6000h
0x1800459cb  mov     r9d, 2000h
0x1800459d1  mov     r14, r10
0x1800459d4  mov     r12d, 0Eh
0x1800459da  mov     [r10+4], r15d
0x1800459de  movzx   edx, word ptr [r11]
0x1800459e2  mov     [r10+8], dx
0x1800459e7  movzx   eax, word ptr [r11+2]
0x1800459ec  mov     [r10+0Ah], ax
0x1800459f1  movzx   eax, word ptr [r11+4]
0x1800459f6  mov     [r10+0Ch], ax
0x1800459fb  movzx   eax, word ptr [r11+6]
0x180045a00  mov     [r10+0Eh], ax
0x180045a05  movzx   eax, dx
0x180045a08  and     ax, r8w
0x180045a0c  test    r9w, dx
0x180045a10  cmovz   ax, dx
0x180045a14  movzx   edx, ax
0x180045a17  lea     rax, [r10+14h]
0x180045a1b  bt      dx, 0Eh
0x180045a20  mov     [rbp+arg_8], rax
0x180045a24  mov     [r10+10h], edx
0x180045a28  jnb     short loc_180045A52
0x180045a2a  mov     r10, [r11+8]
0x180045a2e  test    r10, r10
0x180045a31  jz      loc_180045C9A
0x180045a37  lea     rbx, [rax+4]
0x180045a3b  mov     dword ptr [rax], 4
0x180045a41  mov     ecx, 0BFFFh
0x180045a46  mov     [rbp+arg_8], rbx
0x180045a4a  and     dx, cx
0x180045a4d  mov     rdi, rax
0x180045a50  jmp     short loc_180045A7A
0x180045a52  cmp     edx, 0Ch
0x180045a55  jnz     short loc_180045A63
0x180045a57  mov     ecx, 80070057h; exception
0x180045a5c  call    cs:__imp_RpcRaiseException
0x180045a62  int     3; Trap to Debugger
0x180045a63  mov     [rbp+arg_8], rax
0x180045a67  mov     rdi, r15
0x180045a6a  mov     rbx, rax
0x180045a6d  mov     r10, r11
0x180045a70  cmp     dx, r12w
0x180045a74  jz      short loc_180045A7A
0x180045a76  lea     r10, [r11+8]
0x180045a7a  movzx   ecx, dx
0x180045a7d  cmp     ecx, r9d
0x180045a80  ja      short loc_180045ACD
0x180045a82  jz      loc_180045CD6
0x180045a88  mov     r8d, 0Dh
0x180045a8e  cmp     ecx, r8d
0x180045a91  ja      loc_180045BC9
0x180045a97  jz      loc_180045B86
0x180045a9d  cmp     ecx, 6
0x180045aa0  ja      short loc_180045B14
0x180045aa2  jz      short loc_180045AE3
0x180045aa4  test    ecx, ecx
0x180045aa6  jz      short loc_180045AD9
0x180045aa8  sub     ecx, 1
0x180045aab  jz      short loc_180045AD9
0x180045aad  sub     ecx, 1
0x180045ab0  jz      loc_180045C18
0x180045ab6  sub     ecx, 1
0x180045ab9  jz      loc_180045C85
0x180045abf  sub     ecx, 1
0x180045ac2  jz      loc_180045C85
0x180045ac8  cmp     ecx, 1
0x180045acb  jz      short loc_180045AE3
0x180045acd  mov     ecx, 80020008h; exception
0x180045ad2  call    cs:__imp_RpcRaiseException
0x180045ad8  int     3; Trap to Debugger
0x180045ad9  test    rdi, rdi
0x180045adc  jnz     short loc_180045ACD
0x180045ade  jmp     loc_180045D09
0x180045ae3  mov     dl, 7; unsigned __int8
0x180045ae5  lea     rcx, [rbp+arg_8]; unsigned __int8 **
0x180045ae9  call    ?AlignAndZeroGap@@YAXAEAPEAEE@Z; AlignAndZeroGap(uchar * &,uchar)
0x180045aee  mov     rbx, [rbp+arg_8]
0x180045af2  mov     rcx, [r10]
0x180045af5  mov     [rbx], rcx
0x180045af8  add     rbx, 8
0x180045afc  mov     [rbp+arg_8], rbx
0x180045b00  test    rdi, rdi
0x180045b03  jz      loc_180045D09
0x180045b09  mov     dword ptr [rdi], 8
0x180045b0f  jmp     loc_180045D09
0x180045b14  sub     ecx, 7
0x180045b17  jz      short loc_180045AE3
0x180045b19  sub     ecx, 1
0x180045b1c  jz      short loc_180045B61
0x180045b1e  sub     ecx, 1
0x180045b21  jz      short loc_180045B86
0x180045b23  sub     ecx, 1
0x180045b26  jz      loc_180045C85
0x180045b2c  sub     ecx, 1
0x180045b2f  jz      loc_180045C18
0x180045b35  cmp     ecx, 1
0x180045b38  jnz     short loc_180045ACD
0x180045b3a  lea     rdx, [rbx+4]; unsigned __int8 *
0x180045b3e  mov     dword ptr [rbx], 72657355h
0x180045b44  mov     r8, r10; VARIANT *
0x180045b47  mov     rcx, rsi; unsigned int *
0x180045b4a  call    VARIANT_UserMarshal
0x180045b4f  mov     rbx, rax
0x180045b52  mov     [rbp+arg_8], rax
0x180045b56  mov     dword ptr [rdi], 18h
0x180045b5c  jmp     loc_180045D09
0x180045b61  cmp     [r10], r15
0x180045b64  jz      loc_180045CFE
0x180045b6a  mov     eax, [r10]
0x180045b6d  lea     rdx, [rbx+4]; unsigned __int8 *
0x180045b71  or      eax, 1
0x180045b74  mov     r8, r10; BSTR *
0x180045b77  mov     rcx, rsi; unsigned int *
0x180045b7a  mov     [rbx], eax
0x180045b7c  call    BSTR_UserMarshal
0x180045b81  jmp     loc_180045CF5
0x180045b86  cmp     [r10], r15
0x180045b89  jz      loc_180045CFE
0x180045b8f  mov     eax, [r10]
0x180045b92  lea     rcx, IID_IDispatch
0x180045b99  or      eax, 1
0x180045b9c  mov     [rbx], eax
0x180045b9e  cmp     dx, r8w
0x180045ba2  mov     r9, [r10]
0x180045ba5  lea     rax, IID_IUnknown
0x180045bac  mov     edx, [rsi]
0x180045bae  lea     r8, [rbx+4]
0x180045bb2  cmovnz  rax, rcx
0x180045bb6  mov     rcx, rsi
0x180045bb9  mov     [rsp+30h+var_10], rax
0x180045bbe  call    cs:__imp_WdtpInterfacePointer_UserMarshal
0x180045bc4  jmp     loc_180045CF5
0x180045bc9  cmp     ecx, 15h
0x180045bcc  ja      loc_180045C68
0x180045bd2  jz      short loc_180045BFA
0x180045bd4  sub     ecx, r12d
0x180045bd7  jz      short loc_180045C35
0x180045bd9  sub     ecx, 2
0x180045bdc  jz      short loc_180045C28
0x180045bde  sub     ecx, 1
0x180045be1  jz      short loc_180045C28
0x180045be3  sub     ecx, 1
0x180045be6  jz      short loc_180045C18
0x180045be8  sub     ecx, 1
0x180045beb  jz      loc_180045C85
0x180045bf1  cmp     ecx, 1
0x180045bf4  jnz     loc_180045ACD
0x180045bfa  mov     dl, 7; unsigned __int8
0x180045bfc  lea     rcx, [rbp+arg_8]; unsigned __int8 **
0x180045c00  call    ?AlignAndZeroGap@@YAXAEAPEAEE@Z; AlignAndZeroGap(uchar * &,uchar)
0x180045c05  mov     rbx, [rbp+arg_8]
0x180045c09  mov     rcx, [r10]
0x180045c0c  mov     [rbx], rcx
0x180045c0f  add     rbx, 8
0x180045c13  jmp     loc_180045D05
0x180045c18  movzx   eax, word ptr [r10]
0x180045c1c  mov     [rbx], ax
0x180045c1f  add     rbx, 2
0x180045c23  jmp     loc_180045D05
0x180045c28  mov     al, [r10]
0x180045c2b  mov     [rbx], al
0x180045c2d  inc     rbx
0x180045c30  jmp     loc_180045D05
0x180045c35  mov     dl, 7; unsigned __int8
0x180045c37  lea     rcx, [rbp+arg_8]; unsigned __int8 **
0x180045c3b  call    ?AlignAndZeroGap@@YAXAEAPEAEE@Z; AlignAndZeroGap(uchar * &,uchar)
0x180045c40  mov     rbx, [rbp+arg_8]
0x180045c44  movups  xmm0, xmmword ptr [r10]
0x180045c48  movdqu  xmmword ptr [rbx], xmm0
0x180045c4c  add     rbx, 10h
0x180045c50  mov     [rbp+arg_8], rbx
0x180045c54  test    rdi, rdi
0x180045c57  jz      loc_180045D09
0x180045c5d  mov     dword ptr [rdi], 10h
0x180045c63  jmp     loc_180045D09
0x180045c68  sub     ecx, 16h
0x180045c6b  jz      short loc_180045C85
0x180045c6d  sub     ecx, 1
0x180045c70  jz      short loc_180045C85
0x180045c72  sub     ecx, r8d
0x180045c75  jz      short loc_180045C8C
0x180045c77  sub     ecx, 1
0x180045c7a  jz      short loc_180045C85
0x180045c7c  cmp     ecx, 1
0x180045c7f  jnz     loc_180045ACD
0x180045c85  mov     eax, [r10]
0x180045c88  mov     [rbx], eax
0x180045c8a  jmp     short loc_180045D01
0x180045c8c  test    rdi, rdi
0x180045c8f  jz      short loc_180045CA6
0x180045c91  mov     rbx, rdi
0x180045c94  cmp     [r11+10h], r15
0x180045c98  jnz     short loc_180045CAC
0x180045c9a  mov     ecx, 6F4h; exception
0x180045c9f  call    cs:__imp_RpcRaiseException
0x180045ca5  int     3; Trap to Debugger
0x180045ca6  cmp     [r11+10h], r15
0x180045caa  jz      short loc_180045CFE
0x180045cac  mov     eax, [r11+10h]
0x180045cb0  lea     rdx, [rbx+4]
0x180045cb4  or      eax, 1
0x180045cb7  mov     r8d, 1
0x180045cbd  mov     [rbx], eax
0x180045cbf  mov     rcx, rsi
0x180045cc2  mov     rax, [r11+8]
0x180045cc6  mov     r9, [r11+10h]
0x180045cca  mov     [rsp+30h+var_10], rax
0x180045ccf  call    BRECORD_UserMarshal
0x180045cd4  jmp     short loc_180045CF5
0x180045cd6  cmp     [r10], r15
0x180045cd9  jz      short loc_180045CFE
0x180045cdb  mov     eax, [r10]
0x180045cde  lea     rdx, [rbx+4]
0x180045ce2  or      eax, 1
0x180045ce5  xor     r9d, r9d
0x180045ce8  mov     r8, r10
0x180045ceb  mov     [rbx], eax
0x180045ced  mov     rcx, rsi; unsigned int *
0x180045cf0  call    LPSAFEARRAY_Marshal
0x180045cf5  mov     [rbp+arg_8], rax
0x180045cf9  mov     rbx, rax
0x180045cfc  jmp     short loc_180045D09
0x180045cfe  mov     [rbx], r15d
0x180045d01  add     rbx, 4
0x180045d05  mov     [rbp+arg_8], rbx
0x180045d09  mov     eax, ebx
0x180045d0b  mov     rcx, rsi
0x180045d0e  sub     eax, r14d
0x180045d11  add     eax, 7
0x180045d14  shr     eax, 3
0x180045d17  mov     [r14], eax
0x180045d1a  call    cs:__imp_CoDoesOtherSideVariantMarshalingNeedTrailingPadding
0x180045d20  test    eax, eax
0x180045d22  jz      short loc_180045D33
0x180045d24  mov     dl, 7; unsigned __int8
0x180045d26  lea     rcx, [rbp+arg_8]; unsigned __int8 **
0x180045d2a  call    ?AlignAndZeroGap@@YAXAEAPEAEE@Z; AlignAndZeroGap(uchar * &,uchar)
0x180045d2f  mov     rbx, [rbp+arg_8]
0x180045d33  mov     rax, rbx
0x180045d36  jmp     loc_18004599F
```
