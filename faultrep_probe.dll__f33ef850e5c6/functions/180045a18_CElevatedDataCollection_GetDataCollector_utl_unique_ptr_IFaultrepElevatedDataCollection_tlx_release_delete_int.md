# CElevatedDataCollection::GetDataCollector(utl::unique_ptr<IFaultrepElevatedDataCollection,tlx::release_delete> *,int,ushort)

- ea: `0x180045a18`
- end: `0x180045dd0`
- name: `?GetDataCollector@CElevatedDataCollection@@IEAAJPEAV?$unique_ptr@UIFaultrepElevatedDataCollection@@Urelease_delete@tlx@@@utl@@HG@Z`
- size: `952`
- prototype: `__int64 __fastcall(_QWORD *, IUnknown **, unsigned int, unsigned __int16)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004415c`
- `0x1800445c4`
- `0x180044f94`

## callees

- `0x180009f00`
- `0x180045a18`
- `0x180045fa4`
- `0x1800469bc`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180045b28`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180045b28`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180045c71`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180045c71`

## pseudocode

```c
__int64 __fastcall CElevatedDataCollection::GetDataCollector(
        _QWORD *a1,
        IUnknown **a2,
        unsigned int a3,
        unsigned __int16 a4)
{
  int v4; // r15d
  IUnknown *v7; // rdx
  IUnknown *v8; // rcx
  int v10; // ebx
  IUnknown *v11; // rdx
  HRESULT v12; // ebx
  IUnknown *v13; // rcx
  IUnknown *v15; // rbx
  __int64 v16; // rcx
  void (*AddRef)(void); // rax
  int v18; // edx
  int v19; // r8d
  HRESULT v20; // r15d
  const char *v21; // r9
  int v22; // ebx
  __int64 v23; // rcx
  IUnknown *v24; // rdx
  IUnknown *v25; // rcx
  IUnknown *v26; // rax
  LPVOID ppv; // [rsp+40h] [rbp-20h] BYREF
  IUnknown **p_pProxy; // [rsp+48h] [rbp-18h]
  IUnknown *pProxy; // [rsp+98h] [rbp+38h] BYREF

  v4 = a4;
  v7 = *a2;
  v8 = 0;
  pProxy = 0;
  *a2 = 0;
  if ( v7 )
  {
    ((void (__fastcall *)(IUnknown *))v7->lpVtbl->Release)(v7);
    v8 = pProxy;
  }
  v10 = v4;
  if ( v4 )
  {
    if ( v4 == 332 )
    {
      v11 = v8;
      v8 = *(IUnknown **)((char *)a1 + (-(__int64)(a3 != 0) & 0xFFFFFFFFFFFFFFE8uLL) + 784);
    }
    else
    {
      if ( v4 != 452 )
        goto LABEL_11;
      v11 = v8;
      v8 = *(IUnknown **)((char *)a1 + (-(__int64)(a3 != 0) & 0xFFFFFFFFFFFFFFE8uLL) + 792);
    }
  }
  else
  {
    v11 = v8;
    v8 = *(IUnknown **)((char *)a1 + (-(__int64)(a3 != 0) & 0xFFFFFFFFFFFFFFE8uLL) + 776);
  }
  pProxy = v8;
  if ( v11 )
  {
    ((void (__fastcall *)(IUnknown *))v11->lpVtbl->Release)(v11);
    v8 = pProxy;
  }
LABEL_11:
  if ( v8 )
  {
LABEL_57:
    AddRef = (void (*)(void))v8->lpVtbl->AddRef;
    goto LABEL_58;
  }
  if ( !a3 && !(_WORD)v4 )
  {
    ppv = 0;
    p_pProxy = &pProxy;
    pProxy = 0;
    v12 = CoCreateInstance(
            &GUID_6e3d2e94_e6d8_4afd_afde_abd26ca88bf5,
            0,
            1u,
            &GUID_f61082c5_ed37_4a0e_a1b1_08ee41314935,
            &ppv);
    if ( ppv )
    {
      v13 = *p_pProxy;
      *p_pProxy = (IUnknown *)ppv;
      if ( v13 )
        ((void (__fastcall *)(IUnknown *))v13->lpVtbl->Release)(v13);
    }
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          &WPP_b503122a8e753e2116c8130bd5de03da_Traceguids,
          (unsigned int)v12);
      if ( pProxy )
        ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
      return (unsigned int)v12;
    }
    v15 = pProxy;
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->AddRef)(pProxy);
    v16 = a1[97];
    a1[97] = v15;
    if ( !v16 )
      goto LABEL_59;
    AddRef = *(void (**)(void))(*(_QWORD *)v16 + 16LL);
LABEL_58:
    AddRef();
LABEL_59:
    v24 = *a2;
    v25 = 0;
    v26 = pProxy;
    pProxy = 0;
    *a2 = v26;
    if ( v24 )
    {
      ((void (__fastcall *)(IUnknown *))v24->lpVtbl->Release)(v24);
      v25 = pProxy;
    }
    if ( v25 )
      ((void (__fastcall *)(IUnknown *))v25->lpVtbl->Release)(v25);
    return 0;
  }
  v20 = CElevatedDataCollection::SpawnDataCollector(a1, &pProxy, a3, (unsigned __int16)v4);
  if ( v20 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v21 = "elevated";
      if ( !a3 )
        v21 = "non-elevated";
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v19, (_DWORD)v21, v20);
    }
LABEL_32:
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    return (unsigned int)v20;
  }
  v20 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0);
  if ( v20 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        &WPP_b503122a8e753e2116c8130bd5de03da_Traceguids,
        (unsigned int)v20);
    goto LABEL_32;
  }
  if ( !v10 )
  {
    if ( a3 )
    {
      v23 = a1[94];
      a1[94] = pProxy;
    }
    else
    {
      v23 = a1[97];
      a1[97] = pProxy;
    }
    goto LABEL_54;
  }
  v22 = v10 - 332;
  if ( !v22 )
  {
    if ( a3 )
    {
      v23 = a1[95];
      a1[95] = pProxy;
    }
    else
    {
      v23 = a1[98];
      a1[98] = pProxy;
    }
    goto LABEL_54;
  }
  if ( v22 == 120 )
  {
    if ( a3 )
    {
      v23 = a1[96];
      a1[96] = pProxy;
    }
    else
    {
      v23 = a1[99];
      a1[99] = pProxy;
    }
LABEL_54:
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v8 = pProxy;
    goto LABEL_57;
  }
  if ( pProxy )
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180045a18  mov     [rsp-28h+arg_0], rbx
0x180045a1d  mov     [rsp-28h+arg_10], rsi
0x180045a22  push    rbp
0x180045a23  push    rdi
0x180045a24  push    r12
0x180045a26  push    r14
0x180045a28  push    r15
0x180045a2a  mov     rbp, rsp
0x180045a2d  sub     rsp, 60h
0x180045a31  xor     r12d, r12d
0x180045a34  movzx   r15d, r9w
0x180045a38  mov     r14, rdx
0x180045a3b  mov     rdi, rcx
0x180045a3e  mov     rdx, [rdx]
0x180045a41  mov     ecx, r12d
0x180045a44  mov     [rbp+pProxy], rcx
0x180045a48  mov     esi, r8d
0x180045a4b  mov     [r14], r12
0x180045a4e  test    rdx, rdx
0x180045a51  jz      short loc_180045A66
0x180045a53  mov     rax, [rdx]
0x180045a56  mov     rcx, rdx
0x180045a59  mov     rax, [rax+10h]
0x180045a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a62  mov     rcx, [rbp+pProxy]
0x180045a66  mov     ebx, r15d
0x180045a69  mov     edx, r15d
0x180045a6c  test    r15d, r15d
0x180045a6f  jz      short loc_180045AAE
0x180045a71  sub     edx, 14Ch
0x180045a77  jz      short loc_180045A96
0x180045a79  cmp     edx, 78h ; 'x'
0x180045a7c  jnz     short loc_180045AE0
0x180045a7e  mov     rdx, rcx
0x180045a81  mov     eax, esi
0x180045a83  neg     eax
0x180045a85  sbb     rcx, rcx
0x180045a88  and     rcx, 0FFFFFFFFFFFFFFE8h
0x180045a8c  mov     rcx, [rcx+rdi+318h]
0x180045a94  jmp     short loc_180045AC4
0x180045a96  mov     rdx, rcx
0x180045a99  mov     eax, esi
0x180045a9b  neg     eax
0x180045a9d  sbb     rcx, rcx
0x180045aa0  and     rcx, 0FFFFFFFFFFFFFFE8h
0x180045aa4  mov     rcx, [rcx+rdi+310h]
0x180045aac  jmp     short loc_180045AC4
0x180045aae  mov     rdx, rcx
0x180045ab1  mov     eax, esi
0x180045ab3  neg     eax
0x180045ab5  sbb     rcx, rcx
0x180045ab8  and     rcx, 0FFFFFFFFFFFFFFE8h
0x180045abc  mov     rcx, [rcx+rdi+308h]
0x180045ac4  mov     [rbp+pProxy], rcx
0x180045ac8  test    rdx, rdx
0x180045acb  jz      short loc_180045AE0
0x180045acd  mov     rax, [rdx]
0x180045ad0  mov     rcx, rdx
0x180045ad3  mov     rax, [rax+10h]
0x180045ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045adc  mov     rcx, [rbp+pProxy]
0x180045ae0  test    rcx, rcx
0x180045ae3  jnz     loc_180045D6F
0x180045ae9  test    esi, esi
0x180045aeb  jnz     loc_180045BDB
0x180045af1  test    r15w, r15w
0x180045af5  jnz     loc_180045BDB
0x180045afb  lea     rax, [rbp+pProxy]
0x180045aff  mov     [rbp+var_20], r12
0x180045b03  mov     [rbp+var_18], rax
0x180045b07  lea     r8d, [rcx+1]; dwClsContext
0x180045b0b  lea     rax, [rbp+var_20]
0x180045b0f  mov     [rbp+pProxy], r12
0x180045b13  lea     r9, _GUID_f61082c5_ed37_4a0e_a1b1_08ee41314935; riid
0x180045b1a  mov     [rsp+60h+ppv], rax; ppv
0x180045b1f  xor     edx, edx; pUnkOuter
0x180045b21  lea     rcx, _GUID_6e3d2e94_e6d8_4afd_afde_abd26ca88bf5; rclsid
0x180045b28  call    cs:__imp_CoCreateInstance
0x180045b2e  mov     ebx, eax
0x180045b30  mov     rax, [rbp+var_20]
0x180045b34  test    rax, rax
0x180045b37  jz      short loc_180045B54
0x180045b39  mov     rdx, [rbp+var_18]
0x180045b3d  mov     rcx, [rdx]
0x180045b40  mov     [rdx], rax
0x180045b43  test    rcx, rcx
0x180045b46  jz      short loc_180045B54
0x180045b48  mov     rdx, [rcx]
0x180045b4b  mov     rax, [rdx+10h]
0x180045b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b54  test    ebx, ebx
0x180045b56  jns     short loc_180045BA5
0x180045b58  mov     rcx, cs:WPP_GLOBAL_Control
0x180045b5f  lea     rax, WPP_GLOBAL_Control
0x180045b66  cmp     rcx, rax
0x180045b69  jz      short loc_180045B89
0x180045b6b  test    byte ptr [rcx+1Ch], 1
0x180045b6f  jz      short loc_180045B89
0x180045b71  mov     rcx, [rcx+10h]
0x180045b75  lea     r8, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids
0x180045b7c  mov     edx, 32h ; '2'
0x180045b81  mov     r9d, ebx
0x180045b84  call    WPP_SF_d
0x180045b89  mov     rcx, [rbp+pProxy]
0x180045b8d  test    rcx, rcx
0x180045b90  jz      short loc_180045B9E
0x180045b92  mov     rax, [rcx]
0x180045b95  mov     rax, [rax+10h]
0x180045b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b9e  mov     eax, ebx
0x180045ba0  jmp     loc_180045DB7
0x180045ba5  mov     rbx, [rbp+pProxy]
0x180045ba9  mov     rcx, rbx
0x180045bac  mov     rax, [rbx]
0x180045baf  mov     rax, [rax+8]
0x180045bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045bb8  mov     rcx, [rdi+308h]
0x180045bbf  mov     [rdi+308h], rbx
0x180045bc6  test    rcx, rcx
0x180045bc9  jz      loc_180045D7B
0x180045bcf  mov     rax, [rcx]
0x180045bd2  mov     rax, [rax+10h]
0x180045bd6  jmp     loc_180045D76
0x180045bdb  movzx   r9d, r15w
0x180045bdf  lea     rdx, [rbp+pProxy]
0x180045be3  mov     r8d, esi
0x180045be6  mov     rcx, rdi
0x180045be9  call    ?SpawnDataCollector@CElevatedDataCollection@@IEAAJPEAV?$unique_ptr@UIFaultrepElevatedDataCollection@@Urelease_delete@tlx@@@utl@@HG@Z; CElevatedDataCollection::SpawnDataCollector(utl::unique_ptr<IFaultrepElevatedDataCollection,tlx::release_delete> *,int,ushort)
0x180045bee  mov     r15d, eax
0x180045bf1  test    eax, eax
0x180045bf3  jns     short loc_180045C4D
0x180045bf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180045bfc  lea     rax, WPP_GLOBAL_Control
0x180045c03  cmp     rcx, rax
0x180045c06  jz      short loc_180045C30
0x180045c08  test    byte ptr [rcx+1Ch], 1
0x180045c0c  jz      short loc_180045C30
0x180045c0e  mov     rcx, [rcx+10h]
0x180045c12  lea     rax, aNonElevated; "non-elevated"
0x180045c19  test    esi, esi
0x180045c1b  mov     dword ptr [rsp+60h+ppv], r15d
0x180045c20  lea     r9, aElevated; "elevated"
0x180045c27  cmovz   r9, rax
0x180045c2b  call    WPP_SF_sd
0x180045c30  mov     rcx, [rbp+pProxy]
0x180045c34  test    rcx, rcx
0x180045c37  jz      short loc_180045C45
0x180045c39  mov     rax, [rcx]
0x180045c3c  mov     rax, [rax+10h]
0x180045c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c45  mov     eax, r15d
0x180045c48  jmp     loc_180045DB7
0x180045c4d  mov     rcx, [rbp+pProxy]; pProxy
0x180045c51  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180045c54  mov     [rsp+60h+dwCapabilities], r12d; dwCapabilities
0x180045c59  mov     r8d, edx; dwAuthzSvc
0x180045c5c  mov     [rsp+60h+pAuthInfo], r12; pAuthInfo
0x180045c61  xor     r9d, r9d; pServerPrincName
0x180045c64  mov     [rsp+60h+dwImpLevel], 3; dwImpLevel
0x180045c6c  mov     dword ptr [rsp+60h+ppv], r12d; dwAuthnLevel
0x180045c71  call    cs:__imp_CoSetProxyBlanket
0x180045c77  mov     r15d, eax
0x180045c7a  test    eax, eax
0x180045c7c  jns     short loc_180045CB4
0x180045c7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180045c85  lea     rax, WPP_GLOBAL_Control
0x180045c8c  cmp     rcx, rax
0x180045c8f  jz      short loc_180045C30
0x180045c91  test    byte ptr [rcx+1Ch], 1
0x180045c95  jz      short loc_180045C30
0x180045c97  mov     rcx, [rcx+10h]
0x180045c9b  lea     r8, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids
0x180045ca2  mov     edx, 34h ; '4'
0x180045ca7  mov     r9d, r15d
0x180045caa  call    WPP_SF_d
0x180045caf  jmp     loc_180045C30
0x180045cb4  test    ebx, ebx
0x180045cb6  jz      short loc_180045D34
0x180045cb8  sub     ebx, 14Ch
0x180045cbe  jz      short loc_180045D0C
0x180045cc0  cmp     ebx, 78h ; 'x'
0x180045cc3  jz      short loc_180045CE4
0x180045cc5  mov     rcx, [rbp+pProxy]
0x180045cc9  test    rcx, rcx
0x180045ccc  jz      short loc_180045CDA
0x180045cce  mov     rax, [rcx]
0x180045cd1  mov     rax, [rax+10h]
0x180045cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045cda  mov     eax, 80070057h
0x180045cdf  jmp     loc_180045DB7
0x180045ce4  mov     rax, [rbp+pProxy]
0x180045ce8  test    esi, esi
0x180045cea  jz      short loc_180045CFC
0x180045cec  mov     rcx, [rdi+300h]
0x180045cf3  mov     [rdi+300h], rax
0x180045cfa  jmp     short loc_180045D5A
0x180045cfc  mov     rcx, [rdi+318h]
0x180045d03  mov     [rdi+318h], rax
0x180045d0a  jmp     short loc_180045D5A
0x180045d0c  mov     rax, [rbp+pProxy]
0x180045d10  test    esi, esi
0x180045d12  jz      short loc_180045D24
0x180045d14  mov     rcx, [rdi+2F8h]
0x180045d1b  mov     [rdi+2F8h], rax
0x180045d22  jmp     short loc_180045D5A
0x180045d24  mov     rcx, [rdi+310h]
0x180045d2b  mov     [rdi+310h], rax
0x180045d32  jmp     short loc_180045D5A
0x180045d34  mov     rax, [rbp+pProxy]
0x180045d38  test    esi, esi
0x180045d3a  jz      short loc_180045D4C
0x180045d3c  mov     rcx, [rdi+2F0h]
0x180045d43  mov     [rdi+2F0h], rax
0x180045d4a  jmp     short loc_180045D5A
0x180045d4c  mov     rcx, [rdi+308h]
0x180045d53  mov     [rdi+308h], rax
0x180045d5a  test    rcx, rcx
0x180045d5d  jz      short loc_180045D6B
0x180045d5f  mov     rax, [rcx]
0x180045d62  mov     rax, [rax+10h]
0x180045d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d6b  mov     rcx, [rbp+pProxy]
0x180045d6f  mov     rax, [rcx]
0x180045d72  mov     rax, [rax+8]
0x180045d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d7b  mov     rdx, [r14]
0x180045d7e  mov     rcx, r12
0x180045d81  mov     rax, [rbp+pProxy]
0x180045d85  mov     [rbp+pProxy], rcx
0x180045d89  mov     [r14], rax
0x180045d8c  test    rdx, rdx
0x180045d8f  jz      short loc_180045DA4
0x180045d91  mov     rax, [rdx]
0x180045d94  mov     rcx, rdx
0x180045d97  mov     rax, [rax+10h]
0x180045d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045da0  mov     rcx, [rbp+pProxy]
0x180045da4  test    rcx, rcx
0x180045da7  jz      short loc_180045DB5
0x180045da9  mov     rax, [rcx]
0x180045dac  mov     rax, [rax+10h]
0x180045db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045db5  xor     eax, eax
0x180045db7  lea     r11, [rsp+60h+var_s0]
0x180045dbc  mov     rbx, [r11+30h]
0x180045dc0  mov     rsi, [r11+40h]
0x180045dc4  mov     rsp, r11
0x180045dc7  pop     r15
0x180045dc9  pop     r14
0x180045dcb  pop     r12
0x180045dcd  pop     rdi
0x180045dce  pop     rbp
0x180045dcf  retn
```
