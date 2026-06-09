# CWriteEngineStaticDriveInformation::Init(IDiscRecorder2Ex *)

- ea: `0x180035988`
- end: `0x180035e57`
- name: `?Init@CWriteEngineStaticDriveInformation@@QEAAJPEAUIDiscRecorder2Ex@@@Z`
- size: `1231`
- prototype: `__int64 __fastcall(CWriteEngineStaticDriveInformation *__hidden this, struct IDiscRecorder2Ex *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180034750`

## callees

- `0x1800140f4`
- `0x180014134`
- `0x180016778`
- `0x180035988`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180035e37`
- `ole32!CoTaskMemFree` at `0x180035e37`
- `ole32!CoCreateInstance` at `0x180035d44`
- `ole32!CoCreateInstance` at `0x180035d44`

## pseudocode

```c
__int64 __fastcall CWriteEngineStaticDriveInformation::Init(
        CWriteEngineStaticDriveInformation *this,
        struct IDiscRecorder2Ex *a2)
{
  struct IDiscRecorder2ExVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetMaximumNonPageAlignedTransferSize)(IDiscRecorder2Ex *, ULONG *); // rax
  HRESULT v6; // eax
  unsigned int v7; // edi
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int16 v16; // r15
  LPVOID v17; // rcx
  unsigned int v19; // [rsp+30h] [rbp-20h] BYREF
  int v20; // [rsp+34h] [rbp-1Ch] BYREF
  unsigned int v21; // [rsp+38h] [rbp-18h] BYREF
  int v22; // [rsp+3Ch] [rbp-14h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v25; // [rsp+A8h] [rbp+58h] BYREF

  lpVtbl = a2->lpVtbl;
  v25 = 0;
  v19 = 0;
  v22 = -1;
  GetMaximumNonPageAlignedTransferSize = lpVtbl->GetMaximumNonPageAlignedTransferSize;
  v20 = -1;
  pv = 0;
  v21 = 0;
  ppv = 0;
  v6 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, unsigned int *))GetMaximumNonPageAlignedTransferSize)(
         a2,
         &v25);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
    {
      v9 = 35;
LABEL_82:
      WPP_SF_d(v8[27], v9, &WPP_d9598978672c34cd509ac261b9388a6f_Traceguids, (unsigned int)v6);
      goto LABEL_83;
    }
    goto LABEL_83;
  }
  if ( v25 > 0x10000 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u )
    {
      goto LABEL_17;
    }
    v11 = 36;
    goto LABEL_16;
  }
  if ( v25 >= 0x10000 )
    goto LABEL_18;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 2u )
  {
    v11 = 37;
LABEL_16:
    WPP_SF_Dd(v10[27], v11, &WPP_d9598978672c34cd509ac261b9388a6f_Traceguids, v25, 0x10000);
  }
LABEL_17:
  v25 = 0x10000;
LABEL_18:
  v6 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, unsigned int *))a2->lpVtbl->GetMaximumPageAlignedTransferSize)(
         a2,
         &v19);
  v7 = v6;
  if ( v6 >= 0 )
  {
    if ( v19 <= 0x10000 )
    {
      if ( v19 >= 0x10000 )
        goto LABEL_35;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 225) < 2u )
      {
LABEL_34:
        v19 = 0x10000;
LABEL_35:
        v6 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, int *))a2->lpVtbl->GetByteAlignmentMask)(a2, &v22);
        v7 = v6;
        if ( v6 < 0 )
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
          {
            v9 = 41;
            goto LABEL_82;
          }
          goto LABEL_83;
        }
        v6 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, _QWORD, LPVOID *, unsigned int *))a2->lpVtbl->GetFeaturePage)(
               a2,
               263,
               0,
               &pv,
               &v21);
        v7 = v6;
        if ( v6 == -1062600182 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 225) < 4u )
          {
            goto LABEL_71;
          }
          v15 = 42;
        }
        else if ( v6 == -1062600180 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 225) < 4u )
          {
            goto LABEL_71;
          }
          v15 = 43;
        }
        else
        {
          if ( v6 < 0 )
          {
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
            {
              v9 = 44;
              goto LABEL_82;
            }
            goto LABEL_83;
          }
          if ( v21 < 5 )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 225) < 4u )
            {
              goto LABEL_71;
            }
            v15 = 47;
          }
          else
          {
            if ( (*((_BYTE *)pv + 4) & 1) != 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 45, &WPP_d9598978672c34cd509ac261b9388a6f_Traceguids);
              }
              v16 = -1;
LABEL_72:
              v6 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &IID_IGlobalInterfaceTable, &ppv);
              v7 = v6;
              if ( v6 >= 0 )
              {
                v6 = (*(__int64 (__fastcall **)(LPVOID, struct IDiscRecorder2Ex *, GUID *, int *))(*(_QWORD *)ppv + 24LL))(
                       ppv,
                       a2,
                       &IID_IDiscRecorder2Ex,
                       &v20);
                v7 = v6;
                if ( v6 >= 0 )
                {
                  *((_QWORD *)this + 5) = ppv;
                  *((_DWORD *)this + 4) = v20;
                  *((_DWORD *)this + 5) = v25;
                  *((_DWORD *)this + 6) = v19;
                  *((_DWORD *)this + 7) = v22;
                  *((_QWORD *)this + 1) = a2;
                  *((_WORD *)this + 16) = v16;
                  goto LABEL_89;
                }
                v8 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u )
                {
                  v9 = 49;
                  goto LABEL_82;
                }
              }
              else
              {
                v8 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u )
                {
                  v9 = 48;
                  goto LABEL_82;
                }
              }
              goto LABEL_83;
            }
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 225) < 4u )
            {
LABEL_71:
              v16 = 0;
              goto LABEL_72;
            }
            v15 = 46;
          }
        }
        WPP_SF_(v14[27], v15, &WPP_d9598978672c34cd509ac261b9388a6f_Traceguids);
        goto LABEL_71;
      }
      v13 = 40;
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u )
      {
        goto LABEL_34;
      }
      v13 = 39;
    }
    WPP_SF_Dd(v12[27], v13, &WPP_d9598978672c34cd509ac261b9388a6f_Traceguids, v19, 0x10000);
    goto LABEL_34;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
  {
    v9 = 38;
    goto LABEL_82;
  }
LABEL_83:
  v17 = ppv;
  if ( ppv )
  {
    if ( v20 != -1 )
    {
      (*(void (**)(void))(*(_QWORD *)ppv + 32LL))();
      v17 = ppv;
    }
    if ( v17 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
      ppv = 0;
    }
  }
LABEL_89:
  CoTaskMemFree(pv);
  return v7;
}

```

## disassembly

```asm
0x180035988  mov     [rsp-38h+arg_0], rbx
0x18003598d  push    rbp
0x18003598e  push    rsi
0x18003598f  push    rdi
0x180035990  push    r12
0x180035992  push    r13
0x180035994  push    r14
0x180035996  push    r15
0x180035998  mov     rbp, rsp
0x18003599b  sub     rsp, 50h
0x18003599f  mov     rax, [rdx]
0x1800359a2  xor     esi, esi
0x1800359a4  mov     r12, rdx
0x1800359a7  mov     [rbp+arg_18], esi
0x1800359aa  mov     r13, rcx
0x1800359ad  mov     [rbp+var_20], esi
0x1800359b0  lea     rdx, [rbp+arg_18]
0x1800359b4  mov     [rbp+var_14], 0FFFFFFFFh
0x1800359bb  mov     rax, [rax+98h]
0x1800359c2  mov     rcx, r12
0x1800359c5  mov     [rbp+var_1C], 0FFFFFFFFh
0x1800359cc  mov     [rbp+pv], rsi
0x1800359d0  mov     [rbp+var_18], esi
0x1800359d3  mov     [rbp+var_10], rsi
0x1800359d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359dc  mov     edi, eax
0x1800359de  test    eax, eax
0x1800359e0  jns     short loc_180035A28
0x1800359e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800359e9  lea     rsi, WPP_GLOBAL_Control
0x1800359f0  cmp     rcx, rsi
0x1800359f3  jz      loc_180035DCA
0x1800359f9  mov     bl, 4
0x1800359fb  test    [rcx+0E4h], bl
0x180035a01  jz      loc_180035DCA
0x180035a07  mov     r15b, 3
0x180035a0a  cmp     [rcx+0E1h], r15b
0x180035a11  jb      loc_180035DCA
0x180035a17  mov     edx, 23h ; '#'
0x180035a1c  lea     r8, WPP_d9598978672c34cd509ac261b9388a6f_Traceguids
0x180035a23  jmp     loc_180035DBB
0x180035a28  mov     r9d, [rbp+arg_18]
0x180035a2c  lea     rsi, WPP_GLOBAL_Control
0x180035a33  mov     edi, 10000h
0x180035a38  lea     r14, WPP_d9598978672c34cd509ac261b9388a6f_Traceguids
0x180035a3f  mov     bl, 4
0x180035a41  mov     r15b, 3
0x180035a44  cmp     r9d, edi
0x180035a47  jbe     short loc_180035A6D
0x180035a49  mov     rcx, cs:WPP_GLOBAL_Control
0x180035a50  cmp     rcx, rsi
0x180035a53  jz      short loc_180035AA4
0x180035a55  test    [rcx+0E4h], bl
0x180035a5b  jz      short loc_180035AA4
0x180035a5d  cmp     [rcx+0E1h], r15b
0x180035a64  jb      short loc_180035AA4
0x180035a66  mov     edx, 24h ; '$'
0x180035a6b  jmp     short loc_180035A91
0x180035a6d  jnb     short loc_180035AA7
0x180035a6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180035a76  cmp     rcx, rsi
0x180035a79  jz      short loc_180035AA4
0x180035a7b  test    [rcx+0E4h], bl
0x180035a81  jz      short loc_180035AA4
0x180035a83  cmp     byte ptr [rcx+0E1h], 2
0x180035a8a  jb      short loc_180035AA4
0x180035a8c  mov     edx, 25h ; '%'
0x180035a91  mov     rcx, [rcx+0D8h]
0x180035a98  mov     r8, r14
0x180035a9b  mov     dword ptr [rsp+50h+ppv], edi
0x180035a9f  call    WPP_SF_Dd
0x180035aa4  mov     [rbp+arg_18], edi
0x180035aa7  mov     rax, [r12]
0x180035aab  lea     rdx, [rbp+var_20]
0x180035aaf  mov     rcx, r12
0x180035ab2  mov     rax, [rax+0A0h]
0x180035ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035abe  mov     edi, eax
0x180035ac0  test    eax, eax
0x180035ac2  jns     short loc_180035AF7
0x180035ac4  mov     rcx, cs:WPP_GLOBAL_Control
0x180035acb  cmp     rcx, rsi
0x180035ace  jz      loc_180035DCA
0x180035ad4  test    [rcx+0E4h], bl
0x180035ada  jz      loc_180035DCA
0x180035ae0  cmp     [rcx+0E1h], r15b
0x180035ae7  jb      loc_180035DCA
0x180035aed  mov     edx, 26h ; '&'
0x180035af2  jmp     loc_180035DB8
0x180035af7  mov     r9d, [rbp+var_20]
0x180035afb  mov     edi, 10000h
0x180035b00  cmp     r9d, edi
0x180035b03  jbe     short loc_180035B29
0x180035b05  mov     rcx, cs:WPP_GLOBAL_Control
0x180035b0c  cmp     rcx, rsi
0x180035b0f  jz      short loc_180035B60
0x180035b11  test    [rcx+0E4h], bl
0x180035b17  jz      short loc_180035B60
0x180035b19  cmp     [rcx+0E1h], r15b
0x180035b20  jb      short loc_180035B60
0x180035b22  mov     edx, 27h ; '''
0x180035b27  jmp     short loc_180035B4D
0x180035b29  jnb     short loc_180035B63
0x180035b2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180035b32  cmp     rcx, rsi
0x180035b35  jz      short loc_180035B60
0x180035b37  test    [rcx+0E4h], bl
0x180035b3d  jz      short loc_180035B60
0x180035b3f  cmp     byte ptr [rcx+0E1h], 2
0x180035b46  jb      short loc_180035B60
0x180035b48  mov     edx, 28h ; '('
0x180035b4d  mov     rcx, [rcx+0D8h]
0x180035b54  mov     r8, r14
0x180035b57  mov     dword ptr [rsp+50h+ppv], edi
0x180035b5b  call    WPP_SF_Dd
0x180035b60  mov     [rbp+var_20], edi
0x180035b63  mov     rax, [r12]
0x180035b67  lea     rdx, [rbp+var_14]
0x180035b6b  mov     rcx, r12
0x180035b6e  mov     rax, [rax+90h]
0x180035b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b7a  mov     edi, eax
0x180035b7c  test    eax, eax
0x180035b7e  jns     short loc_180035BB3
0x180035b80  mov     rcx, cs:WPP_GLOBAL_Control
0x180035b87  cmp     rcx, rsi
0x180035b8a  jz      loc_180035DCA
0x180035b90  test    [rcx+0E4h], bl
0x180035b96  jz      loc_180035DCA
0x180035b9c  cmp     [rcx+0E1h], r15b
0x180035ba3  jb      loc_180035DCA
0x180035ba9  mov     edx, 29h ; ')'
0x180035bae  jmp     loc_180035DB8
0x180035bb3  mov     rax, [r12]
0x180035bb7  lea     rcx, [rbp+var_18]
0x180035bbb  mov     [rsp+50h+ppv], rcx
0x180035bc0  lea     r9, [rbp+pv]
0x180035bc4  xor     r8d, r8d
0x180035bc7  mov     [rbp+arg_10], 0
0x180035bce  mov     edx, 107h
0x180035bd3  mov     rcx, r12
0x180035bd6  mov     rax, [rax+60h]
0x180035bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bdf  mov     edi, eax
0x180035be1  cmp     eax, 0C0AA020Ah
0x180035be6  jnz     short loc_180035C1A
0x180035be8  mov     rcx, cs:WPP_GLOBAL_Control
0x180035bef  cmp     rcx, rsi
0x180035bf2  jz      loc_180035D23
0x180035bf8  test    [rcx+0E4h], bl
0x180035bfe  jz      loc_180035D23
0x180035c04  cmp     [rcx+0E1h], bl
0x180035c0a  jb      loc_180035D23
0x180035c10  mov     edx, 2Ah ; '*'
0x180035c15  jmp     loc_180035D14
0x180035c1a  cmp     eax, 0C0AA020Ch
0x180035c1f  jnz     short loc_180035C53
0x180035c21  mov     rcx, cs:WPP_GLOBAL_Control
0x180035c28  cmp     rcx, rsi
0x180035c2b  jz      loc_180035D23
0x180035c31  test    [rcx+0E4h], bl
0x180035c37  jz      loc_180035D23
0x180035c3d  cmp     [rcx+0E1h], bl
0x180035c43  jb      loc_180035D23
0x180035c49  mov     edx, 2Bh ; '+'
0x180035c4e  jmp     loc_180035D14
0x180035c53  test    eax, eax
0x180035c55  jns     short loc_180035C8A
0x180035c57  mov     rcx, cs:WPP_GLOBAL_Control
0x180035c5e  cmp     rcx, rsi
0x180035c61  jz      loc_180035DCA
0x180035c67  test    [rcx+0E4h], bl
0x180035c6d  jz      loc_180035DCA
0x180035c73  cmp     [rcx+0E1h], r15b
0x180035c7a  jb      loc_180035DCA
0x180035c80  mov     edx, 2Ch ; ','
0x180035c85  jmp     loc_180035DB8
0x180035c8a  cmp     [rbp+var_18], 5
0x180035c8e  jb      short loc_180035CF3
0x180035c90  mov     rax, [rbp+pv]
0x180035c94  test    byte ptr [rax+4], 1
0x180035c98  jz      short loc_180035CD0
0x180035c9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180035ca1  cmp     rcx, rsi
0x180035ca4  jz      short loc_180035CCA
0x180035ca6  test    [rcx+0E4h], bl
0x180035cac  jz      short loc_180035CCA
0x180035cae  cmp     [rcx+0E1h], bl
0x180035cb4  jb      short loc_180035CCA
0x180035cb6  mov     rcx, [rcx+0D8h]
0x180035cbd  mov     edx, 2Dh ; '-'
0x180035cc2  mov     r8, r14
0x180035cc5  call    WPP_SF_
0x180035cca  or      r15d, 0FFFFFFFFh
0x180035cce  jmp     short loc_180035D27
0x180035cd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180035cd7  cmp     rcx, rsi
0x180035cda  jz      short loc_180035D23
0x180035cdc  test    [rcx+0E4h], bl
0x180035ce2  jz      short loc_180035D23
0x180035ce4  cmp     [rcx+0E1h], bl
0x180035cea  jb      short loc_180035D23
0x180035cec  mov     edx, 2Eh ; '.'
0x180035cf1  jmp     short loc_180035D14
0x180035cf3  mov     rcx, cs:WPP_GLOBAL_Control
0x180035cfa  cmp     rcx, rsi
0x180035cfd  jz      short loc_180035D23
0x180035cff  test    [rcx+0E4h], bl
0x180035d05  jz      short loc_180035D23
0x180035d07  cmp     [rcx+0E1h], bl
0x180035d0d  jb      short loc_180035D23
0x180035d0f  mov     edx, 2Fh ; '/'
0x180035d14  mov     rcx, [rcx+0D8h]
0x180035d1b  mov     r8, r14
0x180035d1e  call    WPP_SF_
0x180035d23  mov     r15d, [rbp+arg_10]
0x180035d27  xor     edx, edx; pUnkOuter
0x180035d29  lea     rax, [rbp+var_10]
0x180035d2d  lea     r9, IID_IGlobalInterfaceTable; riid
0x180035d34  mov     [rsp+50h+ppv], rax; ppv
0x180035d39  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180035d40  lea     r8d, [rdx+1]; dwClsContext
0x180035d44  call    cs:__imp_CoCreateInstance
0x180035d4a  mov     edi, eax
0x180035d4c  test    eax, eax
0x180035d4e  jns     short loc_180035D73
0x180035d50  mov     rcx, cs:WPP_GLOBAL_Control
0x180035d57  cmp     rcx, rsi
0x180035d5a  jz      short loc_180035DCA
0x180035d5c  test    [rcx+0E4h], bl
0x180035d62  jz      short loc_180035DCA
0x180035d64  cmp     [rcx+0E1h], bl
0x180035d6a  jb      short loc_180035DCA
0x180035d6c  mov     edx, 30h ; '0'
0x180035d71  jmp     short loc_180035DB8
0x180035d73  mov     rcx, [rbp+var_10]
0x180035d77  lea     r9, [rbp+var_1C]
0x180035d7b  lea     r8, IID_IDiscRecorder2Ex
0x180035d82  mov     rdx, r12
0x180035d85  mov     rax, [rcx]
0x180035d88  mov     rax, [rax+18h]
0x180035d8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d91  mov     edi, eax
0x180035d93  test    eax, eax
0x180035d95  jns     short loc_180035E06
0x180035d97  mov     rcx, cs:WPP_GLOBAL_Control
0x180035d9e  cmp     rcx, rsi
0x180035da1  jz      short loc_180035DCA
0x180035da3  test    [rcx+0E4h], bl
0x180035da9  jz      short loc_180035DCA
0x180035dab  cmp     [rcx+0E1h], bl
0x180035db1  jb      short loc_180035DCA
0x180035db3  mov     edx, 31h ; '1'
0x180035db8  mov     r8, r14
0x180035dbb  mov     rcx, [rcx+0D8h]
0x180035dc2  mov     r9d, eax
0x180035dc5  call    WPP_SF_d
0x180035dca  mov     rcx, [rbp+var_10]
0x180035dce  test    rcx, rcx
0x180035dd1  jz      short loc_180035E33
0x180035dd3  mov     edx, [rbp+var_1C]
0x180035dd6  cmp     edx, 0FFFFFFFFh
0x180035dd9  jz      short loc_180035DEB
0x180035ddb  mov     rax, [rcx]
0x180035dde  mov     rax, [rax+20h]
0x180035de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035de7  mov     rcx, [rbp+var_10]
0x180035deb  test    rcx, rcx
0x180035dee  jz      short loc_180035E33
0x180035df0  mov     rax, [rcx]
0x180035df3  mov     rax, [rax+10h]
0x180035df7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035dfc  mov     [rbp+var_10], 0
0x180035e04  jmp     short loc_180035E33
0x180035e06  mov     rax, [rbp+var_10]
0x180035e0a  mov     [r13+28h], rax
0x180035e0e  mov     eax, [rbp+var_1C]
0x180035e11  mov     [r13+10h], eax
0x180035e15  mov     eax, [rbp+arg_18]
0x180035e18  mov     [r13+14h], eax
0x180035e1c  mov     eax, [rbp+var_20]
0x180035e1f  mov     [r13+18h], eax
0x180035e23  mov     eax, [rbp+var_14]
0x180035e26  mov     [r13+1Ch], eax
0x180035e2a  mov     [r13+8], r12
0x180035e2e  mov     [r13+20h], r15w
0x180035e33  mov     rcx, [rbp+pv]; pv
0x180035e37  call    cs:__imp_CoTaskMemFree
0x180035e3d  mov     rbx, [rsp+50h+arg_0]
0x180035e45  mov     eax, edi
0x180035e47  add     rsp, 50h
0x180035e4b  pop     r15
0x180035e4d  pop     r14
0x180035e4f  pop     r13
0x180035e51  pop     r12
0x180035e53  pop     rdi
0x180035e54  pop     rsi
0x180035e55  pop     rbp
0x180035e56  retn
```
