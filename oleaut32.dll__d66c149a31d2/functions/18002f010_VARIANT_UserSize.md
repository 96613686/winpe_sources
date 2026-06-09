# VARIANT_UserSize

- ea: `0x18002f010`
- end: `0x18002f37b`
- name: `VARIANT_UserSize`
- size: `875`
- prototype: `unsigned int __stdcall(unsigned int *, unsigned int, VARIANT *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002f010`
- `0x18002f3a0`

## callees

- `0x18002f010`
- `0x18002f3a0`
- `0x18002f6e0`
- `0x180030ac8`
- `0x180030af8`
- `0x180042248`

## import_xrefs

- `combase!WdtpInterfacePointer_UserSize` at `0x18002f1cb`
- `combase!WdtpInterfacePointer_UserSize` at `0x18002f1cb`
- `combase!__imp_CoDoesOtherSideVariantMarshalingNeedTrailingPadding` at `0x18002f0fb`
- `combase!__imp_CoDoesOtherSideVariantMarshalingNeedTrailingPadding` at `0x18002f0fb`
- `RPCRT4!RpcRaiseException` at `0x18002f04e`
- `RPCRT4!RpcRaiseException` at `0x18002f12a`
- `RPCRT4!RpcRaiseException` at `0x18002f14e`
- `RPCRT4!RpcRaiseException` at `0x18002f23c`
- `RPCRT4!RpcRaiseException` at `0x18002f04e`
- `RPCRT4!RpcRaiseException` at `0x18002f12a`
- `RPCRT4!RpcRaiseException` at `0x18002f14e`
- `RPCRT4!RpcRaiseException` at `0x18002f23c`

## pseudocode

```c
unsigned int __stdcall VARIANT_UserSize(unsigned int *a1, unsigned int a2, VARIANT *a3)
{
  unsigned int v5; // eax
  unsigned int v6; // ebx
  unsigned __int16 vt; // r8
  BSTR *pbstrVal; // rdi
  int v9; // r9d
  unsigned int v10; // edx
  bool v11; // cf
  unsigned int v13; // eax
  unsigned int v14; // eax
  GUID *v15; // rax
  unsigned int v16; // eax
  unsigned int v17; // eax
  int v18; // ecx
  int v19; // ecx
  unsigned int v20; // edx
  unsigned int v21; // ecx
  IRecordInfo *pRecInfo; // r9
  unsigned int v23; // [rsp+78h] [rbp+40h] BYREF

  if ( !a3 )
    return a2;
  v5 = (a2 + 7) & 0xFFFFFFF8;
  if ( v5 < a2 || (v6 = v5 + 20, v5 + 20 < v5) )
LABEL_4:
    RpcRaiseException(-2147418096);
  vt = a3->vt & 0x6000;
  v23 = v5 + 20;
  if ( (a3->vt & 0x2000) == 0 )
    vt = a3->vt;
  if ( (vt & 0x4000) != 0 )
  {
    pbstrVal = a3->pbstrVal;
    if ( !pbstrVal )
      goto LABEL_28;
    v10 = v5 + 24;
    if ( v5 + 24 < v5 + 20 )
      goto LABEL_4;
    v23 = v5 + 24;
    vt &= ~0x4000u;
    v6 = v5 + 24;
    v9 = 1;
  }
  else
  {
    if ( vt == 12 )
      RpcRaiseException(-2147024809);
    pbstrVal = &a3->bstrVal;
    v9 = 0;
    v10 = v5 + 20;
  }
  if ( vt == 0x2000 )
  {
    v6 = v10 + 4;
    if ( v10 + 4 < v10 )
      goto LABEL_4;
    v23 = v10 + 4;
    if ( !*(_DWORD *)pbstrVal )
      goto LABEL_24;
    v13 = LPSAFEARRAY_Size(a1);
    goto LABEL_39;
  }
  if ( vt > 0x2000u )
    goto LABEL_33;
  if ( vt > 0xDu )
  {
    if ( vt <= 0x15u )
    {
      switch ( vt )
      {
        case 0x15u:
          goto LABEL_48;
        case 0xEu:
          Safe_Length_Align(&v23, 7);
          v21 = v23;
          v20 = 16;
          break;
        case 0x10u:
        case 0x11u:
          v20 = 1;
          v21 = v6;
          break;
        default:
          v18 = vt - 18;
          if ( vt == 18 )
            goto LABEL_20;
LABEL_64:
          v19 = v18 - 1;
          if ( !v19 )
            goto LABEL_34;
          if ( v19 != 1 )
            goto LABEL_33;
          goto LABEL_48;
      }
      ULongAdd_RpcRaiseIfFailed(v21, v20, &v23);
      v6 = v23;
      goto LABEL_24;
    }
    if ( vt == 22 || vt == 23 )
      goto LABEL_34;
    if ( vt != 36 )
    {
      if ( (unsigned int)vt - 37 >= 2 )
        goto LABEL_33;
      goto LABEL_34;
    }
    if ( v9 )
    {
LABEL_78:
      pRecInfo = a3->pRecInfo;
      if ( !pRecInfo )
        goto LABEL_24;
      v13 = BRECORD_UserSize((_DWORD)a1, v6, 1, (_DWORD)pRecInfo, a3->llVal);
      goto LABEL_39;
    }
    ULongAdd_RpcRaiseIfFailed(v6, 4u, &v23);
    if ( a3->pRecInfo )
    {
      v6 = v23;
      goto LABEL_78;
    }
LABEL_28:
    RpcRaiseException(1780);
  }
  if ( vt == 13 )
    goto LABEL_40;
  if ( vt > 6u )
  {
    if ( vt != 7 )
    {
      if ( vt == 8 )
      {
        v16 = v6;
        v6 += 4;
        if ( v6 < v16 )
          goto LABEL_4;
        v23 = v6;
        if ( !*(_DWORD *)pbstrVal )
          goto LABEL_24;
        v13 = BSTR_UserSize(a1, v6, pbstrVal);
        goto LABEL_39;
      }
      if ( vt != 9 )
      {
        if ( vt != 10 )
        {
          if ( vt == 11 )
          {
LABEL_20:
            v6 = v10 + 2;
LABEL_21:
            v11 = v6 < v10;
LABEL_22:
            if ( v11 )
              goto LABEL_4;
            v23 = v6;
            goto LABEL_24;
          }
          if ( vt == 12 )
          {
            ULongAdd_RpcRaiseIfFailed(v6, 4u, &v23);
            v13 = VARIANT_UserSize(a1, v23, (VARIANT *)pbstrVal);
LABEL_39:
            v6 = v13;
            v23 = v13;
            goto LABEL_24;
          }
LABEL_33:
          RpcRaiseException(-2147352568);
        }
LABEL_34:
        v6 = v10 + 4;
        goto LABEL_21;
      }
LABEL_40:
      v14 = v6;
      v6 += 4;
      if ( v6 < v14 )
        goto LABEL_4;
      v23 = v6;
      if ( !*(_DWORD *)pbstrVal )
        goto LABEL_24;
      v15 = &IID_IUnknown;
      if ( vt != 13 )
        v15 = &IID_IDispatch;
      v13 = WdtpInterfacePointer_UserSize(a1, *a1, v6, *pbstrVal, v15);
      goto LABEL_39;
    }
LABEL_48:
    v17 = (v10 + 7) & 0xFFFFFFF8;
    if ( v17 < v10 )
      goto LABEL_4;
    v6 = v17 + 8;
    v11 = v17 + 8 < v17;
    goto LABEL_22;
  }
  if ( vt == 6 )
    goto LABEL_48;
  if ( vt && vt != 1 )
  {
    if ( vt == 2 )
      goto LABEL_20;
    v18 = vt - 3;
    if ( vt == 3 )
      goto LABEL_34;
    goto LABEL_64;
  }
  if ( v9 )
    goto LABEL_33;
LABEL_24:
  if ( (unsigned int)CoDoesOtherSideVariantMarshalingNeedTrailingPadding(a1) )
  {
    Safe_Length_Align(&v23, 7);
    return v23;
  }
  return v6;
}

```

## disassembly

```asm
0x18002f010  push    rbp
0x18002f012  push    rbx
0x18002f013  push    rsi
0x18002f014  push    rdi
0x18002f015  push    r14
0x18002f017  push    r15
0x18002f019  mov     rbp, rsp
0x18002f01c  sub     rsp, 38h
0x18002f020  xor     r15d, r15d
0x18002f023  mov     rsi, r8
0x18002f026  mov     r14, rcx
0x18002f029  test    r8, r8
0x18002f02c  jz      loc_18002F15A
0x18002f032  lea     eax, [rdx+7]
0x18002f035  mov     r11d, 0FFFFFFF8h
0x18002f03b  and     eax, r11d
0x18002f03e  cmp     eax, edx
0x18002f040  jb      short loc_18002F049
0x18002f042  lea     ebx, [rax+14h]
0x18002f045  cmp     ebx, eax
0x18002f047  jnb     short loc_18002F055
0x18002f049  mov     ecx, 80010010h; exception
0x18002f04e  call    cs:__imp_RpcRaiseException
0x18002f054  int     3; Trap to Debugger
0x18002f055  movzx   r8d, word ptr [r8]
0x18002f059  mov     ecx, 6000h
0x18002f05e  and     r8w, cx
0x18002f062  mov     [rbp+arg_8], ebx
0x18002f065  mov     r10d, 2000h
0x18002f06b  test    [rsi], r10w
0x18002f06f  cmovz   r8w, [rsi]
0x18002f074  bt      r8w, 0Eh
0x18002f07a  jb      loc_18002F118
0x18002f080  cmp     r8w, 0Ch
0x18002f085  jz      loc_18002F237
0x18002f08b  lea     rdi, [rsi+8]
0x18002f08f  mov     r9d, r15d
0x18002f092  mov     edx, ebx
0x18002f094  movzx   ecx, r8w
0x18002f098  cmp     ecx, r10d
0x18002f09b  jz      loc_18002F15E
0x18002f0a1  ja      loc_18002F149
0x18002f0a7  mov     r10d, 0Dh
0x18002f0ad  cmp     ecx, r10d
0x18002f0b0  ja      loc_18002F281
0x18002f0b6  jz      loc_18002F18B
0x18002f0bc  cmp     ecx, 6
0x18002f0bf  jbe     short loc_18002F131
0x18002f0c1  sub     ecx, 7
0x18002f0c4  jz      loc_18002F1FB
0x18002f0ca  sub     ecx, 1
0x18002f0cd  jz      loc_18002F1D3
0x18002f0d3  sub     ecx, 1
0x18002f0d6  jz      loc_18002F18B
0x18002f0dc  sub     ecx, 1
0x18002f0df  jz      short loc_18002F155
0x18002f0e1  sub     ecx, 1
0x18002f0e4  jnz     loc_18002F257
0x18002f0ea  lea     ebx, [rdx+2]
0x18002f0ed  cmp     ebx, edx
0x18002f0ef  jb      loc_18002F049
0x18002f0f5  mov     [rbp+arg_8], ebx
0x18002f0f8  mov     rcx, r14
0x18002f0fb  call    cs:__imp_CoDoesOtherSideVariantMarshalingNeedTrailingPadding
0x18002f101  test    eax, eax
0x18002f103  jnz     loc_18002F365
0x18002f109  mov     eax, ebx
0x18002f10b  add     rsp, 38h
0x18002f10f  pop     r15
0x18002f111  pop     r14
0x18002f113  pop     rdi
0x18002f114  pop     rsi
0x18002f115  pop     rbx
0x18002f116  pop     rbp
0x18002f117  retn
0x18002f118  mov     rdi, [rsi+8]
0x18002f11c  test    rdi, rdi
0x18002f11f  jnz     loc_18002F213
0x18002f125  mov     ecx, 6F4h; exception
0x18002f12a  call    cs:__imp_RpcRaiseException
0x18002f130  int     3; Trap to Debugger
0x18002f131  jz      loc_18002F1FB
0x18002f137  test    ecx, ecx
0x18002f139  jz      short loc_18002F144
0x18002f13b  sub     ecx, 1
0x18002f13e  jnz     loc_18002F243
0x18002f144  test    r9d, r9d
0x18002f147  jz      short loc_18002F0F8
0x18002f149  mov     ecx, 80020008h; exception
0x18002f14e  call    cs:__imp_RpcRaiseException
0x18002f154  int     3; Trap to Debugger
0x18002f155  lea     ebx, [rdx+4]
0x18002f158  jmp     short loc_18002F0ED
0x18002f15a  mov     eax, edx
0x18002f15c  jmp     short loc_18002F10B
0x18002f15e  lea     ebx, [rdx+4]
0x18002f161  cmp     ebx, edx
0x18002f163  jb      loc_18002F049
0x18002f169  mov     [rbp+arg_8], ebx
0x18002f16c  cmp     [rdi], r15d
0x18002f16f  jz      short loc_18002F0F8
0x18002f171  xor     r9d, r9d
0x18002f174  mov     r8, rdi
0x18002f177  mov     edx, ebx
0x18002f179  mov     rcx, r14; unsigned int *
0x18002f17c  call    LPSAFEARRAY_Size
0x18002f181  mov     ebx, eax
0x18002f183  mov     [rbp+arg_8], eax
0x18002f186  jmp     loc_18002F0F8
0x18002f18b  mov     eax, ebx
0x18002f18d  add     ebx, 4
0x18002f190  cmp     ebx, eax
0x18002f192  jb      loc_18002F049
0x18002f198  mov     [rbp+arg_8], ebx
0x18002f19b  cmp     [rdi], r15d
0x18002f19e  jz      loc_18002F0F8
0x18002f1a4  mov     r9, [rdi]
0x18002f1a7  lea     rcx, IID_IDispatch
0x18002f1ae  mov     edx, [r14]
0x18002f1b1  lea     rax, IID_IUnknown
0x18002f1b8  cmp     r8w, r10w
0x18002f1bc  mov     r8d, ebx
0x18002f1bf  cmovnz  rax, rcx
0x18002f1c3  mov     rcx, r14
0x18002f1c6  mov     [rsp+38h+var_18], rax
0x18002f1cb  call    cs:__imp_WdtpInterfacePointer_UserSize
0x18002f1d1  jmp     short loc_18002F181
0x18002f1d3  mov     eax, ebx
0x18002f1d5  add     ebx, 4
0x18002f1d8  cmp     ebx, eax
0x18002f1da  jb      loc_18002F049
0x18002f1e0  mov     [rbp+arg_8], ebx
0x18002f1e3  cmp     [rdi], r15d
0x18002f1e6  jz      loc_18002F0F8
0x18002f1ec  mov     r8, rdi; BSTR *
0x18002f1ef  mov     edx, ebx; unsigned int
0x18002f1f1  mov     rcx, r14; unsigned int *
0x18002f1f4  call    BSTR_UserSize
0x18002f1f9  jmp     short loc_18002F181
0x18002f1fb  lea     eax, [rdx+7]
0x18002f1fe  and     eax, r11d
0x18002f201  cmp     eax, edx
0x18002f203  jb      loc_18002F049
0x18002f209  lea     ebx, [rax+8]
0x18002f20c  cmp     ebx, eax
0x18002f20e  jmp     loc_18002F0EF
0x18002f213  lea     edx, [rbx+4]
0x18002f216  cmp     edx, ebx
0x18002f218  jb      loc_18002F049
0x18002f21e  mov     eax, 0BFFFh
0x18002f223  mov     [rbp+arg_8], edx
0x18002f226  and     r8w, ax
0x18002f22a  mov     ebx, edx
0x18002f22c  mov     r9d, 1
0x18002f232  jmp     loc_18002F094
0x18002f237  mov     ecx, 80070057h; exception
0x18002f23c  call    cs:__imp_RpcRaiseException
0x18002f242  int     3; Trap to Debugger
0x18002f243  sub     ecx, 1
0x18002f246  jz      loc_18002F0EA
0x18002f24c  sub     ecx, 1
0x18002f24f  jz      loc_18002F155
0x18002f255  jmp     short loc_18002F2A4
0x18002f257  cmp     ecx, 1
0x18002f25a  jnz     loc_18002F149
0x18002f260  lea     edx, [rcx+3]; unsigned int
0x18002f263  mov     ecx, ebx; unsigned int
0x18002f265  lea     r8, [rbp+arg_8]; unsigned int *
0x18002f269  call    ?ULongAdd_RpcRaiseIfFailed@@YAXKKPEAK@Z; ULongAdd_RpcRaiseIfFailed(ulong,ulong,ulong *)
0x18002f26e  mov     edx, [rbp+arg_8]; unsigned int
0x18002f271  mov     r8, rdi; VARIANT *
0x18002f274  mov     rcx, r14; unsigned int *
0x18002f277  call    VARIANT_UserSize
0x18002f27c  jmp     loc_18002F181
0x18002f281  cmp     ecx, 15h
0x18002f284  ja      short loc_18002F2EB
0x18002f286  jz      loc_18002F1FB
0x18002f28c  sub     ecx, 0Eh
0x18002f28f  jz      short loc_18002F2C4
0x18002f291  sub     ecx, 2
0x18002f294  jz      short loc_18002F2BB
0x18002f296  sub     ecx, 1
0x18002f299  jz      short loc_18002F2BB
0x18002f29b  sub     ecx, 1
0x18002f29e  jz      loc_18002F0EA
0x18002f2a4  sub     ecx, 1
0x18002f2a7  jz      loc_18002F155
0x18002f2ad  cmp     ecx, 1
0x18002f2b0  jz      loc_18002F1FB
0x18002f2b6  jmp     loc_18002F149
0x18002f2bb  mov     edx, 1
0x18002f2c0  mov     ecx, ebx
0x18002f2c2  jmp     short loc_18002F2DA
0x18002f2c4  mov     edx, 7; int
0x18002f2c9  lea     rcx, [rbp+arg_8]; unsigned int *
0x18002f2cd  call    ?Safe_Length_Align@@YAXAEAKH@Z; Safe_Length_Align(ulong &,int)
0x18002f2d2  mov     ecx, [rbp+arg_8]; unsigned int
0x18002f2d5  mov     edx, 10h; unsigned int
0x18002f2da  lea     r8, [rbp+arg_8]; unsigned int *
0x18002f2de  call    ?ULongAdd_RpcRaiseIfFailed@@YAXKKPEAK@Z; ULongAdd_RpcRaiseIfFailed(ulong,ulong,ulong *)
0x18002f2e3  mov     ebx, [rbp+arg_8]
0x18002f2e6  jmp     loc_18002F0F8
0x18002f2eb  sub     ecx, 16h
0x18002f2ee  jz      loc_18002F155
0x18002f2f4  sub     ecx, 1
0x18002f2f7  jz      loc_18002F155
0x18002f2fd  sub     ecx, r10d
0x18002f300  jz      short loc_18002F319
0x18002f302  sub     ecx, 1
0x18002f305  jz      loc_18002F155
0x18002f30b  cmp     ecx, 1
0x18002f30e  jz      loc_18002F155
0x18002f314  jmp     loc_18002F149
0x18002f319  test    r9d, r9d
0x18002f31c  jnz     short loc_18002F33A
0x18002f31e  lea     r8, [rbp+arg_8]; unsigned int *
0x18002f322  mov     ecx, ebx; unsigned int
0x18002f324  lea     edx, [r9+4]; unsigned int
0x18002f328  call    ?ULongAdd_RpcRaiseIfFailed@@YAXKKPEAK@Z; ULongAdd_RpcRaiseIfFailed(ulong,ulong,ulong *)
0x18002f32d  cmp     [rsi+10h], r15
0x18002f331  jz      loc_18002F125
0x18002f337  mov     ebx, [rbp+arg_8]
0x18002f33a  mov     r9, [rsi+10h]
0x18002f33e  test    r9, r9
0x18002f341  jz      loc_18002F0F8
0x18002f347  mov     rax, [rsi+8]
0x18002f34b  mov     r8d, 1
0x18002f351  mov     edx, ebx
0x18002f353  mov     [rsp+38h+var_18], rax
0x18002f358  mov     rcx, r14
0x18002f35b  call    BRECORD_UserSize
0x18002f360  jmp     loc_18002F181
0x18002f365  mov     edx, 7; int
0x18002f36a  lea     rcx, [rbp+arg_8]; unsigned int *
0x18002f36e  call    ?Safe_Length_Align@@YAXAEAKH@Z; Safe_Length_Align(ulong &,int)
0x18002f373  mov     ebx, [rbp+arg_8]
0x18002f376  jmp     loc_18002F109
```
