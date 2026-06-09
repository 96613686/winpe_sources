# MRxSmbHandOverSrvCall

- ea: `0x140013700`
- end: `0x140013a76`
- name: `MRxSmbHandOverSrvCall`
- size: `886`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400010f0`
- `0x140002470`
- `0x140003e20`
- `0x140004030`
- `0x140008b70`
- `0x14000a230`
- `0x14000f8b4`
- `0x14001185c`
- `0x14001221c`
- `0x140013700`
- `0x140013a7c`
- `0x140014e40`
- `0x1400166c0`
- `0x1400169c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140013854`
- `ntoskrnl!ExAllocatePool2` at `0x14001397b`
- `ntoskrnl!ExAllocatePool2` at `0x140013854`
- `ntoskrnl!ExAllocatePool2` at `0x14001397b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001393c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400139dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001393c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400139dc`
- `mrxsmb!SmbCeUpdateTransportDispatchVectors` at `0x140013a28`
- `mrxsmb!SmbCeUpdateTransportDispatchVectors` at `0x140013a28`

## pseudocode

```c
__int64 __fastcall MRxSmbHandOverSrvCall(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4, char a5, int a6, __int64 a7)
{
  __int64 v11; // r15
  unsigned int v12; // edi
  unsigned int v13; // eax
  _DWORD *v14; // rbx
  int v15; // edi
  __int64 v16; // rsi
  unsigned int v18; // edx
  void *v19; // rcx
  void *v20; // rcx
  __int64 v21; // rcx
  int v22; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v23; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  PVOID pContext; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v27[66]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+288h] [rbp+188h] BYREF

  memset(v27, 0, 0x1D0u);
  v23 = 0;
  v22 = 0;
  v26 = 0;
  LOBYTE(v28) = 0;
  v24 = 0;
  SmbCepReferenceServerTransport(&a5, &v24);
  v11 = v24;
  if ( !v24 )
    return (unsigned int)-1073741300;
  if ( *(_DWORD *)(a1 + 144) == 3 )
  {
    v12 = -1073741311;
LABEL_15:
    SmbCepDereferenceServerTransport(&v24);
    return v12;
  }
  if ( _bittest64((const signed __int64 *)(a2 + 216), 0x30u) )
  {
    v12 = -1073741637;
    goto LABEL_15;
  }
  MRxSmbSMB1ResetSMB1UnusedCounter();
  MRxSmb1ObservedInthisPeriod = 1;
  pContext = 0;
  v13 = SmbCeInitializeServerEntry(a2, a1, (unsigned int)&pContext, 0, (__int64)&v28);
  v14 = pContext;
  v12 = v13;
  if ( v13 )
    goto LABEL_13;
  v15 = 2;
  if ( ((*(_DWORD *)(a1 + 144) - 2) & 0xFFFFFFFD) == 0 )
    *((_BYTE *)pContext + 673) |= 1u;
  v16 = a7;
  v14[3] = 3;
  *a4 = v14;
  if ( *(_QWORD *)v16 )
  {
    memset(v27, 0, 0x1D0u);
    LOBYTE(v27[38]) = 114;
    LODWORD(v27[50]) = 17039360;
    v27[51] = ExAllocatePool2(66, 260, 1682009427);
    if ( !v27[51] )
    {
      v12 = -1073741670;
      goto LABEL_13;
    }
    v18 = *(_DWORD *)(v16 + 16);
    v27[10] = v14;
    ParseNegotiateResponse((__int64)v27, v18, v18, &v23, *(_QWORD *)v16, &v26, &v22);
    if ( !v14[82] )
    {
      v14[82] = v27[6];
      if ( !LODWORD(v27[6]) )
      {
        if ( (v14[105] & 0x1000000) == 0 )
        {
          v19 = (void *)*((_QWORD *)v14 + 13);
          if ( v19 )
          {
            ExFreePoolWithTag(v19, 0);
            do
            {
              *((_QWORD *)v14 + 13) = 0;
              --v15;
            }
            while ( v15 );
          }
          *((_WORD *)v14 + 48) = v27[50];
          *((_WORD *)v14 + 49) = v27[50];
          if ( *((_WORD *)v14 + 48) )
            *((_QWORD *)v14 + 13) = ExAllocatePool2(66, *((unsigned __int16 *)v14 + 48), 1918070099);
          v20 = (void *)*((_QWORD *)v14 + 13);
          if ( v20 )
          {
            memmove(v20, (const void *)v27[51], *((unsigned __int16 *)v14 + 48));
          }
          else if ( *((_WORD *)v14 + 48) )
          {
            v14[24] = 0;
            v14[82] = -1073741670;
          }
        }
        if ( !v14[82] )
          v14[82] = SmbCeUpdateSrvCall(v14);
      }
    }
    ExFreePoolWithTag((PVOID)v27[51], 0);
    v27[51] = 0;
  }
  v12 = v14[82];
  if ( v12 )
  {
LABEL_13:
    if ( v14 )
    {
      MRxSmbTrackDerefCount(v14, "MRxSmbHandOverSrvCall", 1464);
      SmbReferenceRecord(v14 + 198, "MRxSmbHandOverSrvCall", 1464);
      SmbCepDereferenceServerEntry((char *)v14);
    }
    goto LABEL_15;
  }
  *((_OWORD *)v14 + 7) = *(_OWORD *)(a3 + 112);
  *(_DWORD *)(a3 + 112) = 0;
  *(_QWORD *)(a3 + 120) = 0;
  *((_QWORD *)v14 + 43) = v11;
  if ( v11 && (unsigned int)SmbCeUpdateTransportDispatchVectors(v11, MRxSmbVctConnectionEventHandler, v14) == 1 )
  {
    v21 = *((_QWORD *)v14 + 43);
    v28 = 3221225996LL;
    VctIndDisconnect(v21, 3221225996LL);
  }
  v14[115] = 1;
  SmbCeCompleteServerEntryInitialization((__int64)v14, 0);
  return v12;
}

```

## disassembly

```asm
0x140013700  push    rbp
0x140013702  push    rbx
0x140013703  push    rsi
0x140013704  push    rdi
0x140013705  push    r12
0x140013707  push    r13
0x140013709  push    r14
0x14001370b  push    r15
0x14001370d  lea     rbp, [rsp-138h]
0x140013715  sub     rsp, 238h
0x14001371c  mov     r14, r8
0x14001371f  mov     rbx, rdx
0x140013722  mov     rsi, rcx
0x140013725  xor     edx, edx; Val
0x140013727  mov     r8d, 1D0h; Size
0x14001372d  lea     rcx, [rsp+270h+var_210]; void *
0x140013732  mov     r12, r9
0x140013735  call    memset
0x14001373a  xor     r13d, r13d
0x14001373d  lea     rdx, [rsp+270h+var_228]
0x140013742  lea     rcx, [rbp+170h+arg_20]
0x140013749  mov     [rsp+270h+var_22C], r13d
0x14001374e  mov     [rsp+270h+var_230], r13d
0x140013753  mov     [rsp+270h+var_218], r13
0x140013758  mov     byte ptr [rbp+170h+arg_8], r13b
0x14001375f  mov     [rsp+270h+var_228], r13
0x140013764  call    SmbCepReferenceServerTransport
0x140013769  mov     r15, [rsp+270h+var_228]
0x14001376e  test    r15, r15
0x140013771  jnz     short loc_14001377D
0x140013773  mov     edi, 0C000020Ch
0x140013778  jmp     loc_1400138B5
0x14001377d  cmp     dword ptr [rsi+90h], 3
0x140013784  jnz     short loc_140013790
0x140013786  mov     edi, 0C0000201h
0x14001378b  jmp     loc_1400138AB
0x140013790  bt      qword ptr [rbx+0D8h], 30h ; '0'
0x140013799  jnb     short loc_1400137A5
0x14001379b  mov     edi, 0C00000BBh
0x1400137a0  jmp     loc_1400138AB
0x1400137a5  call    MRxSmbSMB1ResetSMB1UnusedCounter
0x1400137aa  lea     rax, [rbp+170h+arg_8]
0x1400137b1  mov     cs:MRxSmb1ObservedInthisPeriod, 1
0x1400137bb  xor     r9d, r9d
0x1400137be  mov     [rsp+270h+var_250], rax
0x1400137c3  lea     r8, [rsp+270h+pContext]
0x1400137c8  mov     [rsp+270h+pContext], r13
0x1400137cd  mov     rdx, rsi
0x1400137d0  mov     rcx, rbx
0x1400137d3  call    SmbCeInitializeServerEntry
0x1400137d8  mov     rbx, [rsp+270h+pContext]
0x1400137dd  mov     edi, eax
0x1400137df  test    eax, eax
0x1400137e1  jnz     loc_140013871
0x1400137e7  mov     eax, [rsi+90h]
0x1400137ed  mov     edi, 2
0x1400137f2  sub     eax, edi
0x1400137f4  test    eax, 0FFFFFFFDh
0x1400137f9  jnz     short loc_140013802
0x1400137fb  or      byte ptr [rbx+2A1h], 1
0x140013802  mov     rsi, [rbp+170h+arg_30]
0x140013809  mov     dword ptr [rbx+0Ch], 3
0x140013810  mov     [r12], rbx
0x140013814  cmp     [rsi], r13
0x140013817  jz      loc_1400139EF
0x14001381d  xor     edx, edx; Val
0x14001381f  lea     rcx, [rsp+270h+var_210]; void *
0x140013824  mov     r8d, 1D0h; Size
0x14001382a  call    memset
0x14001382f  mov     r12d, 42h ; 'B'
0x140013835  mov     [rbp+170h+var_E0], 72h ; 'r'
0x14001383c  mov     ecx, r12d
0x14001383f  mov     [rbp+170h+var_80], 1040000h
0x140013849  mov     edx, 104h
0x14001384e  mov     r8d, 64416D53h
0x140013854  call    cs:__imp_ExAllocatePool2
0x14001385b  nop     dword ptr [rax+rax+00h]
0x140013860  mov     [rbp+170h+Src], rax
0x140013867  test    rax, rax
0x14001386a  jnz     short loc_1400138CC
0x14001386c  mov     edi, 0C000009Ah
0x140013871  test    rbx, rbx
0x140013874  jz      short loc_1400138AB
0x140013876  mov     esi, 5B8h
0x14001387b  lea     rdx, aMrxsmbhandover; "MRxSmbHandOverSrvCall"
0x140013882  mov     r8d, esi
0x140013885  mov     rcx, rbx
0x140013888  call    MRxSmbTrackDerefCount
0x14001388d  lea     rcx, [rbx+318h]
0x140013894  mov     r8d, esi
0x140013897  lea     rdx, aMrxsmbhandover; "MRxSmbHandOverSrvCall"
0x14001389e  call    SmbReferenceRecord
0x1400138a3  mov     rcx, rbx; pContext
0x1400138a6  call    SmbCepDereferenceServerEntry
0x1400138ab  lea     rcx, [rsp+270h+var_228]
0x1400138b0  call    SmbCepDereferenceServerTransport
0x1400138b5  mov     eax, edi
0x1400138b7  add     rsp, 238h
0x1400138be  pop     r15
0x1400138c0  pop     r14
0x1400138c2  pop     r13
0x1400138c4  pop     r12
0x1400138c6  pop     rdi
0x1400138c7  pop     rsi
0x1400138c8  pop     rbx
0x1400138c9  pop     rbp
0x1400138ca  retn
0x1400138cc  mov     edx, [rsi+10h]
0x1400138cf  lea     rax, [rsp+270h+var_230]
0x1400138d4  mov     [rsp+270h+var_240], rax
0x1400138d9  lea     r9, [rsp+270h+var_22C]
0x1400138de  lea     rax, [rsp+270h+var_218]
0x1400138e3  mov     [rbp+170h+var_1C0], rbx
0x1400138e7  mov     [rsp+270h+var_248], rax
0x1400138ec  lea     rcx, [rsp+270h+var_210]
0x1400138f1  mov     rax, [rsi]
0x1400138f4  mov     r8d, edx
0x1400138f7  mov     [rsp+270h+var_250], rax
0x1400138fc  call    ParseNegotiateResponse
0x140013901  cmp     [rbx+148h], r13d
0x140013908  jnz     loc_1400139D3
0x14001390e  mov     eax, [rbp+170h+var_1E0]
0x140013911  mov     [rbx+148h], eax
0x140013917  cmp     [rbp+170h+var_1E0], r13d
0x14001391b  jnz     loc_1400139D3
0x140013921  test    dword ptr [rbx+1A4h], 1000000h
0x14001392b  jnz     loc_1400139BC
0x140013931  mov     rcx, [rbx+68h]; P
0x140013935  test    rcx, rcx
0x140013938  jz      short loc_140013951
0x14001393a  xor     edx, edx; Tag
0x14001393c  call    cs:__imp_ExFreePoolWithTag
0x140013943  nop     dword ptr [rax+rax+00h]
0x140013948  mov     [rbx+68h], r13
0x14001394c  sub     edi, 1
0x14001394f  jnz     short loc_140013948
0x140013951  movzx   eax, word ptr [rbp+170h+var_80]
0x140013958  mov     [rbx+60h], ax
0x14001395c  movzx   eax, word ptr [rbp+170h+var_80]
0x140013963  mov     [rbx+62h], ax
0x140013967  movzx   eax, word ptr [rbx+60h]
0x14001396b  test    ax, ax
0x14001396e  jz      short loc_14001398B
0x140013970  mov     edx, eax
0x140013972  mov     r8d, 72536D53h
0x140013978  mov     rcx, r12
0x14001397b  call    cs:__imp_ExAllocatePool2
0x140013982  nop     dword ptr [rax+rax+00h]
0x140013987  mov     [rbx+68h], rax
0x14001398b  mov     rcx, [rbx+68h]; void *
0x14001398f  test    rcx, rcx
0x140013992  jz      short loc_1400139A7
0x140013994  movzx   r8d, word ptr [rbx+60h]; Size
0x140013999  mov     rdx, [rbp+170h+Src]; Src
0x1400139a0  call    memmove
0x1400139a5  jmp     short loc_1400139BC
0x1400139a7  cmp     [rbx+60h], r13w
0x1400139ac  jbe     short loc_1400139BC
0x1400139ae  mov     [rbx+60h], r13d
0x1400139b2  mov     dword ptr [rbx+148h], 0C000009Ah
0x1400139bc  cmp     [rbx+148h], r13d
0x1400139c3  jnz     short loc_1400139D3
0x1400139c5  mov     rcx, rbx
0x1400139c8  call    SmbCeUpdateSrvCall
0x1400139cd  mov     [rbx+148h], eax
0x1400139d3  mov     rcx, [rbp+170h+Src]; P
0x1400139da  xor     edx, edx; Tag
0x1400139dc  call    cs:__imp_ExFreePoolWithTag
0x1400139e3  nop     dword ptr [rax+rax+00h]
0x1400139e8  mov     [rbp+170h+Src], r13
0x1400139ef  mov     edi, [rbx+148h]
0x1400139f5  test    edi, edi
0x1400139f7  jnz     loc_140013871
0x1400139fd  movups  xmm0, xmmword ptr [r14+70h]
0x140013a02  movdqu  xmmword ptr [rbx+70h], xmm0
0x140013a07  mov     [r14+70h], r13d
0x140013a0b  mov     [r14+78h], r13
0x140013a0f  mov     [rbx+158h], r15
0x140013a16  test    r15, r15
0x140013a19  jz      short loc_140013A5D
0x140013a1b  mov     r8, rbx
0x140013a1e  lea     rdx, MRxSmbVctConnectionEventHandler
0x140013a25  mov     rcx, r15
0x140013a28  call    cs:__imp_SmbCeUpdateTransportDispatchVectors
0x140013a2f  nop     dword ptr [rax+rax+00h]
0x140013a34  cmp     eax, 1
0x140013a37  jnz     short loc_140013A5D
0x140013a39  mov     rcx, [rbx+158h]
0x140013a40  mov     dword ptr [rbp+170h+arg_8], 0C000020Ch
0x140013a4a  mov     dword ptr [rbp+170h+arg_8+4], r13d
0x140013a51  mov     rdx, [rbp+170h+arg_8]
0x140013a58  call    VctIndDisconnect
0x140013a5d  xor     edx, edx
0x140013a5f  mov     dword ptr [rbx+1CCh], 1
0x140013a69  mov     rcx, rbx
0x140013a6c  call    SmbCeCompleteServerEntryInitialization
0x140013a71  jmp     loc_1400138B5
```
