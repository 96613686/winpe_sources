# CAICProxy::UpdateContextProfiles(int)

- ea: `0x180010a20`
- end: `0x180010ed7`
- name: `?UpdateContextProfiles@CAICProxy@@AEAAKH@Z`
- size: `1207`
- prototype: `unsigned int __fastcall(CAICProxy *__hidden this, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callers

- `0x180043858`
- `0x180046fc0`

## callees

- `0x180010a20`
- `0x180011000`
- `0x180020884`
- `0x18002da10`
- `0x18002db70`
- `0x18002f140`
- `0x180089830`
- `0x180089de0`
- `0x18008d588`
- `0x1800b1c40`
- `0x18010a010`

## import_xrefs

- `ntdll!NtAlpcDeleteSectionView` at `0x180010e87`
- `ntdll!NtAlpcDeleteSectionView` at `0x180010e87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010b77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010b77`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010b30`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010b30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010bd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010c4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010e25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010e9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010bd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010c4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010e25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010e9b`

## pseudocode

```c
__int64 __fastcall CAICProxy::UpdateContextProfiles(CAICProxy *this, int a2)
{
  int v4; // esi
  __int64 v5; // r14
  unsigned int v6; // r12d
  int v7; // r13d
  unsigned int v8; // r15d
  struct MsgBase *v9; // rax
  struct MsgBase *v10; // rdi
  DWORD CurrentThreadId; // eax
  int v12; // r15d
  CCtfClientPort *Instance; // rax
  CCtfClientPort *v14; // rsi
  int v15; // esi
  int i; // r15d
  __int64 v17; // rdi
  __int64 v18; // r9
  __int64 result; // rax
  int v20; // eax
  unsigned int j; // r8d
  int v22; // eax
  __int64 v23; // rax
  __int64 v24; // r14
  __int64 v25; // rdi
  int k; // eax
  __int64 v27; // r8
  int m; // edx
  __int64 v29; // r8
  int v30; // eax
  unsigned int v31; // eax
  int v32; // eax
  struct MsgBase *v33; // r13
  HLOCAL hMem; // [rsp+40h] [rbp-61h] BYREF
  int v35; // [rsp+48h] [rbp-59h] BYREF
  unsigned int *v36; // [rsp+50h] [rbp-51h] BYREF
  int v37; // [rsp+58h] [rbp-49h] BYREF
  unsigned int **v38; // [rsp+60h] [rbp-41h]
  __int64 v39; // [rsp+68h] [rbp-39h]
  int v40; // [rsp+70h] [rbp-31h]
  int *v41; // [rsp+78h] [rbp-29h]
  int *v42; // [rsp+80h] [rbp-21h]
  int v43; // [rsp+88h] [rbp-19h]
  int v44; // [rsp+90h] [rbp-11h]
  HLOCAL *p_hMem; // [rsp+98h] [rbp-9h]
  __int64 v46; // [rsp+A0h] [rbp-1h]
  int v47; // [rsp+A8h] [rbp+7h]
  int *v48; // [rsp+B0h] [rbp+Fh]
  unsigned int *v49; // [rsp+B8h] [rbp+17h]
  __int64 v50; // [rsp+C0h] [rbp+1Fh]
  unsigned __int64 retaddr; // [rsp+100h] [rbp+5Fh]
  unsigned int v52; // [rsp+108h] [rbp+67h] BYREF
  int v53; // [rsp+118h] [rbp+77h] BYREF
  HLOCAL v54; // [rsp+120h] [rbp+7Fh] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InputSupportForBcp47>::GetImpl'::`2'::impl) )
    FailFastWithHR(-2147467259, retaddr, 0x43Du);
  v4 = *((_DWORD *)this + 20);
  v5 = *((_QWORD *)this + 12);
  v6 = 0;
  hMem = 0;
  v52 = 0;
  if ( v4 && a2 )
  {
    v53 = 1;
    v36 = &v52;
    v35 = 0;
    v38 = &v36;
    v37 = 6;
    v41 = &v53;
    v39 = 0;
    v42 = &v53;
    v40 = 4;
    p_hMem = &hMem;
    v48 = &v35;
    v49 = &v52;
    v43 = 0;
    v44 = 38;
    v46 = 0;
    v47 = 4;
    LODWORD(v50) = 0;
    LODWORD(v54) = 0;
    if ( (int)MsgBase::CalcParamMarshalingSize(1u, 2u, (struct tagCPROXY_PARAM *)&v37, (unsigned int *)&v54) < 0 )
      goto LABEL_15;
    v7 = (int)v54;
    v8 = (_DWORD)v54 + 72;
    if ( (unsigned int)v54 >= 0xFFFFFFB8 )
      goto LABEL_15;
    v9 = (struct MsgBase *)LocalAlloc(0x40u, v8);
    v10 = v9;
    if ( !v9 )
      goto LABEL_15;
    if ( v8 > 0x200 )
    {
      *((_DWORD *)v9 + 10) |= 0x4000000u;
      LOWORD(v8) = 72;
    }
    *((_WORD *)v9 + 1) = v8;
    *(_WORD *)v9 = v8 - 40;
    *((_DWORD *)v9 + 14) = 2;
    *((_DWORD *)v9 + 15) = v7;
    *((_QWORD *)v9 + 8) = (char *)v9 + 72;
    *((_DWORD *)v9 + 10) |= 0xA0000029;
    CurrentThreadId = GetCurrentThreadId();
    *((_DWORD *)v10 + 12) = v4;
    *((_DWORD *)v10 + 11) = CurrentThreadId;
    v12 = MsgBase::Marshal(v10, 2u, (struct tagCPROXY_PARAM *)&v37);
    if ( v12 >= 0 )
    {
      Instance = CCtfClientPort::CreateInstance();
      v14 = Instance;
      if ( !Instance )
      {
        LocalFree(v10);
        goto LABEL_15;
      }
      v54 = 0;
      v12 = CCtfClientPort::SendAsync(Instance, v10, (struct MsgBase **)&v54);
      if ( v12 >= 0 )
      {
        v33 = (struct MsgBase *)v54;
        v12 = MsgBase::Unmarshal((struct MsgBase *)v54, 2u, (struct tagCPROXY_PARAM *)&v37);
        if ( (*((_DWORD *)v33 + 10) & 0x4000000) != 0 )
          NtAlpcDeleteSectionView(*((_QWORD *)v14 + 1), 0, *((_QWORD *)v33 + 8));
        if ( v33 != v10 && v33 )
          LocalFree(v33);
      }
      CCtfClientPort::Release(v14);
    }
    LocalFree(v10);
    if ( v12 < 0 )
    {
LABEL_15:
      v52 = 0;
      CleanUpAutoParams(2u, (struct tagCPROXY_PARAM *)&v37);
    }
  }
  v15 = 0;
  for ( i = 0; v15 < *((_DWORD *)this + 32); ++v15 )
  {
    v17 = *((_QWORD *)this + 15) + *((_DWORD *)this + 33) * v15;
    if ( *(_DWORD *)v17 == 2 )
    {
      if ( *(_QWORD *)(v17 + 72) == *((_QWORD *)this + 12) )
        continue;
      v32 = *(_DWORD *)(v17 + 80);
      if ( (v32 & 1) == 0 )
        continue;
    }
    else
    {
      if ( hMem )
      {
        v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**((_QWORD **)this + 8) + 16LL))(
                *((_QWORD *)this + 8),
                *(unsigned __int16 *)(v17 + 4),
                v17 + 8,
                v17 + 24);
        for ( j = 0; j < v52; ++j )
        {
          if ( v20 == *((_DWORD *)hMem + j) )
          {
            v22 = *(_DWORD *)(v17 + 80);
            if ( (v22 & 1) == 0 )
            {
              v6 |= 4u;
              *(_DWORD *)(v17 + 80) = v22 | 1;
            }
            v23 = *(_QWORD *)(v17 + 40) - *(_QWORD *)&GUID_TFCAT_TIP_KEYBOARD.Data1;
            if ( !v23 )
              v23 = *(_QWORD *)(v17 + 48) - *(_QWORD *)GUID_TFCAT_TIP_KEYBOARD.Data4;
            if ( !v23 )
            {
              i = 1;
              if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InputSupportForBcp47>::GetImpl'::`2'::impl) )
              {
                v24 = *((_QWORD *)this + 8);
                v25 = *(unsigned __int16 *)(v17 + 4);
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InputSupportForBcp47>::GetImpl'::`2'::impl) )
                  FailFastWithHR(-2147467259, retaddr, 0x1CBu);
                if ( !(_WORD)v25 || (_WORD)v25 == (v25 & 0x3FF) )
                {
                  v27 = *(_QWORD *)(v24 + 40);
                  if ( v27 )
                  {
LABEL_53:
                    v5 = *(_QWORD *)(v27 + 8);
                    goto LABEL_19;
                  }
                }
                else
                {
                  for ( k = 0; k < *(_DWORD *)(v24 + 24); ++k )
                  {
                    v27 = *(_QWORD *)(*(_QWORD *)(v24 + 16) + 8LL * k);
                    if ( *(_WORD *)v27 == (_WORD)v25 )
                      goto LABEL_53;
                  }
                }
                v5 = v25 | (v25 << 16);
              }
            }
            goto LABEL_19;
          }
        }
      }
      v32 = *(_DWORD *)(v17 + 80);
      if ( (v32 & 1) == 0 )
        continue;
    }
    v6 |= 4u;
    *(_DWORD *)(v17 + 80) = v32 & 0xFFFFFFFE;
LABEL_19:
    ;
  }
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  v18 = *((_QWORD *)this + 12);
  if ( v18 )
  {
    for ( m = 0; m < *((_DWORD *)this + 32); ++m )
    {
      v29 = *((_QWORD *)this + 15) + *((_DWORD *)this + 33) * m;
      if ( *(_DWORD *)v29 == 2 && *(_QWORD *)(v29 + 72) == v18 )
      {
        v30 = *(_DWORD *)(v29 + 80);
        if ( i )
        {
          v31 = v30 & 0xFFFFFFFE;
        }
        else
        {
          if ( (v30 & 1) != 0 )
            break;
          v31 = v30 | 1;
          v6 |= 4u;
        }
        *(_DWORD *)(v29 + 80) = v31;
        break;
      }
    }
  }
  result = v6;
  *((_QWORD *)this + 12) = v5;
  return result;
}

```

## disassembly

```asm
0x180010a20  mov     rax, rsp
0x180010a23  push    rbp
0x180010a24  push    rbx
0x180010a25  push    r12
0x180010a27  push    r13
0x180010a29  push    r14
0x180010a2b  lea     rbp, [rax-5Fh]
0x180010a2f  sub     rsp, 0D0h
0x180010a36  mov     [rax+10h], rsi
0x180010a3a  mov     rbx, rcx
0x180010a3d  mov     [rax-30h], rdi
0x180010a41  mov     edi, edx
0x180010a43  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47> `wil::Feature<__WilFeatureTraits_Feature_InputSupportForBcp47>::GetImpl(void)'::`2'::impl
0x180010a4a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47>::__private_IsEnabled(void)
0x180010a4f  test    al, al
0x180010a51  jnz     loc_180010E30
0x180010a57  mov     esi, [rbx+50h]
0x180010a5a  xor     r13d, r13d
0x180010a5d  mov     r14, [rbx+60h]
0x180010a61  mov     r12d, r13d
0x180010a64  mov     [rsp+0F0h+var_30], r15
0x180010a6c  mov     [rbp+57h+hMem], r13
0x180010a70  mov     [rbp+57h+arg_0], r13d
0x180010a74  test    esi, esi
0x180010a76  jz      loc_180010BF9
0x180010a7c  test    edi, edi
0x180010a7e  jz      loc_180010BF9
0x180010a84  lea     rax, [rbp+57h+arg_0]
0x180010a88  mov     [rbp+57h+arg_10], 1
0x180010a8f  mov     [rbp+57h+var_A8], rax
0x180010a93  lea     r9, [rbp+57h+arg_18]; unsigned int *
0x180010a97  lea     rax, [rbp+57h+var_A8]
0x180010a9b  mov     [rbp+57h+var_B0], r13d
0x180010a9f  mov     [rbp+57h+var_98], rax
0x180010aa3  lea     r8, [rbp+57h+var_A0]; struct tagCPROXY_PARAM *
0x180010aa7  lea     rax, [rbp+57h+arg_10]
0x180010aab  mov     [rbp+57h+var_A0], 6
0x180010ab2  mov     [rbp+57h+var_80], rax
0x180010ab6  mov     edx, 2; unsigned int
0x180010abb  lea     rax, [rbp+57h+arg_10]
0x180010abf  mov     [rbp+57h+var_90], r13
0x180010ac3  mov     [rbp+57h+var_78], rax
0x180010ac7  mov     ecx, 1; unsigned int
0x180010acc  lea     rax, [rbp+57h+hMem]
0x180010ad0  mov     [rbp+57h+var_88], 4
0x180010ad7  mov     [rbp+57h+var_60], rax
0x180010adb  lea     rax, [rbp+57h+var_B0]
0x180010adf  mov     [rbp+57h+var_48], rax
0x180010ae3  lea     rax, [rbp+57h+arg_0]
0x180010ae7  mov     [rbp+57h+var_40], rax
0x180010aeb  mov     [rbp+57h+var_70], r13d
0x180010aef  mov     [rbp+57h+var_68], 26h ; '&'
0x180010af6  mov     [rbp+57h+var_58], r13
0x180010afa  mov     [rbp+57h+var_50], 4
0x180010b01  mov     dword ptr [rbp+57h+var_38], r13d
0x180010b05  mov     dword ptr [rbp+57h+arg_18], r13d
0x180010b09  call    ?CalcParamMarshalingSize@MsgBase@@SAJKKPEAUtagCPROXY_PARAM@@AEAK@Z; MsgBase::CalcParamMarshalingSize(ulong,ulong,tagCPROXY_PARAM *,ulong &)
0x180010b0e  test    eax, eax
0x180010b10  js      loc_180010BE7
0x180010b16  mov     r13d, dword ptr [rbp+57h+arg_18]
0x180010b1a  lea     r15d, [r13+48h]
0x180010b1e  cmp     r15d, 48h ; 'H'
0x180010b22  jb      loc_180010BE4
0x180010b28  mov     edx, r15d; uBytes
0x180010b2b  mov     ecx, 40h ; '@'; uFlags
0x180010b30  call    cs:__imp_LocalAlloc
0x180010b36  mov     rdi, rax
0x180010b39  test    rax, rax
0x180010b3c  jz      loc_180010BE4
0x180010b42  cmp     r15d, 200h
0x180010b49  ja      loc_180010E49
0x180010b4f  mov     [rax+2], r15w
0x180010b54  sub     r15w, 28h ; '('
0x180010b59  mov     [rax], r15w
0x180010b5d  mov     dword ptr [rax+38h], 2
0x180010b64  mov     [rax+3Ch], r13d
0x180010b68  add     rax, 48h ; 'H'
0x180010b6c  mov     [rdi+40h], rax
0x180010b70  or      dword ptr [rdi+28h], 0A0000029h
0x180010b77  call    cs:__imp_GetCurrentThreadId
0x180010b7d  lea     r8, [rbp+57h+var_A0]; struct tagCPROXY_PARAM *
0x180010b81  mov     [rdi+30h], esi
0x180010b84  mov     edx, 2; unsigned int
0x180010b89  mov     [rdi+2Ch], eax
0x180010b8c  mov     rcx, rdi; struct MsgBase *
0x180010b8f  call    ?Marshal@MsgBase@@SAJPEAU1@KPEAUtagCPROXY_PARAM@@@Z; MsgBase::Marshal(MsgBase *,ulong,tagCPROXY_PARAM *)
0x180010b94  mov     r15d, eax
0x180010b97  test    eax, eax
0x180010b99  js      short loc_180010BD2
0x180010b9b  call    ?CreateInstance@CCtfClientPort@@SAPEAV1@XZ; CCtfClientPort::CreateInstance(void)
0x180010ba0  mov     rsi, rax
0x180010ba3  test    rax, rax
0x180010ba6  jz      loc_180010E98
0x180010bac  lea     r8, [rbp+57h+arg_18]; struct MsgBase **
0x180010bb0  mov     [rbp+57h+arg_18], r12
0x180010bb4  mov     rdx, rdi; struct MsgBase *
0x180010bb7  mov     rcx, rax; this
0x180010bba  call    ?SendAsync@CCtfClientPort@@QEAAJPEAUMsgBase@@PEAPEAU2@@Z; CCtfClientPort::SendAsync(MsgBase *,MsgBase * *)
0x180010bbf  mov     r15d, eax
0x180010bc2  test    eax, eax
0x180010bc4  jns     loc_180010E5B
0x180010bca  mov     rcx, rsi; this
0x180010bcd  call    ?Release@CCtfClientPort@@QEAAKXZ; CCtfClientPort::Release(void)
0x180010bd2  mov     rcx, rdi; hMem
0x180010bd5  call    cs:__imp_LocalFree
0x180010bdb  test    r15d, r15d
0x180010bde  jns     loc_180010E11
0x180010be4  xor     r13d, r13d
0x180010be7  lea     rdx, [rbp+57h+var_A0]; struct tagCPROXY_PARAM *
0x180010beb  mov     [rbp+57h+arg_0], r13d
0x180010bef  mov     ecx, 2; unsigned int
0x180010bf4  call    ?CleanUpAutoParams@@YAXKPEAUtagCPROXY_PARAM@@@Z; CleanUpAutoParams(ulong,tagCPROXY_PARAM *)
0x180010bf9  mov     esi, r13d
0x180010bfc  mov     r15d, r12d
0x180010bff  cmp     [rbx+80h], r12d
0x180010c06  jle     short loc_180010C35
0x180010c08  mov     eax, esi
0x180010c0a  imul    eax, [rbx+84h]
0x180010c11  movsxd  rdi, eax
0x180010c14  add     rdi, [rbx+78h]
0x180010c18  cmp     dword ptr [rdi], 2
0x180010c1b  jnz     short loc_180010C84
0x180010c1d  mov     rax, [rbx+60h]
0x180010c21  cmp     [rdi+48h], rax
0x180010c25  jnz     loc_180010DF7
0x180010c2b  inc     esi
0x180010c2d  cmp     esi, [rbx+80h]
0x180010c33  jl      short loc_180010C08
0x180010c35  mov     rcx, [rbp+57h+hMem]; hMem
0x180010c39  mov     rdi, [rsp+0C8h]
0x180010c41  mov     rsi, [rsp+0F0h+arg_8]
0x180010c49  test    rcx, rcx
0x180010c4c  jz      short loc_180010C58
0x180010c4e  call    cs:__imp_LocalFree
0x180010c54  mov     [rbp+57h+hMem], r13
0x180010c58  mov     r9, [rbx+60h]
0x180010c5c  test    r9, r9
0x180010c5f  jnz     loc_180010D75
0x180010c65  mov     r15, [rsp+0F0h+var_30]
0x180010c6d  mov     eax, r12d
0x180010c70  mov     [rbx+60h], r14
0x180010c74  add     rsp, 0D0h
0x180010c7b  pop     r14
0x180010c7d  pop     r13
0x180010c7f  pop     r12
0x180010c81  pop     rbx
0x180010c82  pop     rbp
0x180010c83  retn
0x180010c84  cmp     [rbp+57h+hMem], 0
0x180010c89  jz      loc_180010EBF
0x180010c8f  mov     rcx, [rbx+40h]
0x180010c93  lea     r9, [rdi+18h]
0x180010c97  movzx   edx, word ptr [rdi+4]
0x180010c9b  lea     r8, [rdi+8]
0x180010c9f  mov     rax, [rcx]
0x180010ca2  mov     rax, [rax+10h]
0x180010ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cab  mov     r9d, [rbp+57h+arg_0]
0x180010caf  mov     r8d, r13d
0x180010cb2  cmp     r8d, r9d
0x180010cb5  jnb     loc_180010EBF
0x180010cbb  mov     rcx, [rbp+57h+hMem]
0x180010cbf  mov     edx, r8d
0x180010cc2  cmp     eax, [rcx+rdx*4]
0x180010cc5  jnz     loc_180010DCE
0x180010ccb  mov     eax, [rdi+50h]
0x180010cce  test    al, 1
0x180010cd0  jnz     short loc_180010CDC
0x180010cd2  or      r12d, 4
0x180010cd6  or      eax, 1
0x180010cd9  mov     [rdi+50h], eax
0x180010cdc  mov     rax, [rdi+28h]
0x180010ce0  sub     rax, qword ptr cs:GUID_TFCAT_TIP_KEYBOARD.Data1
0x180010ce7  jnz     short loc_180010CF4
0x180010ce9  mov     rax, [rdi+30h]
0x180010ced  sub     rax, qword ptr cs:GUID_TFCAT_TIP_KEYBOARD.Data4
0x180010cf4  test    rax, rax
0x180010cf7  jnz     loc_180010C2B
0x180010cfd  mov     r15d, 1
0x180010d03  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47> `wil::Feature<__WilFeatureTraits_Feature_InputSupportForBcp47>::GetImpl(void)'::`2'::impl
0x180010d0a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47>::__private_IsEnabled(void)
0x180010d0f  test    al, al
0x180010d11  jnz     loc_180010C2B
0x180010d17  mov     r14, [rbx+40h]
0x180010d1b  movzx   edi, word ptr [rdi+4]
0x180010d1f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47> `wil::Feature<__WilFeatureTraits_Feature_InputSupportForBcp47>::GetImpl(void)'::`2'::impl
0x180010d26  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47>::__private_IsEnabled(void)
0x180010d2b  test    al, al
0x180010d2d  jnz     loc_180010EA6
0x180010d33  test    di, di
0x180010d36  jz      loc_180010DD6
0x180010d3c  movzx   eax, di
0x180010d3f  mov     ecx, 3FFh
0x180010d44  and     ax, cx
0x180010d47  cmp     di, ax
0x180010d4a  jz      loc_180010DD6
0x180010d50  mov     r9d, [r14+18h]
0x180010d54  mov     eax, r13d
0x180010d57  cmp     eax, r9d
0x180010d5a  jge     loc_180010DE8
0x180010d60  mov     rcx, [r14+10h]
0x180010d64  movsxd  rdx, eax
0x180010d67  mov     r8, [rcx+rdx*8]
0x180010d6b  cmp     [r8], di
0x180010d6f  jz      short loc_180010DDF
0x180010d71  inc     eax
0x180010d73  jmp     short loc_180010D57
0x180010d75  mov     r10d, [rbx+80h]
0x180010d7c  mov     edx, r13d
0x180010d7f  nop
0x180010d80  cmp     edx, r10d
0x180010d83  jge     loc_180010C65
0x180010d89  mov     eax, edx
0x180010d8b  imul    eax, [rbx+84h]
0x180010d92  movsxd  r8, eax
0x180010d95  add     r8, [rbx+78h]
0x180010d99  cmp     dword ptr [r8], 2
0x180010d9d  jz      short loc_180010DA3
0x180010d9f  inc     edx
0x180010da1  jmp     short loc_180010D80
0x180010da3  cmp     [r8+48h], r9
0x180010da7  jnz     short loc_180010D9F
0x180010da9  mov     eax, [r8+50h]
0x180010dad  test    r15d, r15d
0x180010db0  jnz     loc_180010ECF
0x180010db6  test    al, 1
0x180010db8  jnz     loc_180010C65
0x180010dbe  or      eax, 1
0x180010dc1  or      r12d, 4
0x180010dc5  mov     [r8+50h], eax
0x180010dc9  jmp     loc_180010C65
0x180010dce  inc     r8d
0x180010dd1  jmp     loc_180010CB2
0x180010dd6  mov     r8, [r14+28h]
0x180010dda  test    r8, r8
0x180010ddd  jz      short loc_180010DE8
0x180010ddf  mov     r14, [r8+8]
0x180010de3  jmp     loc_180010C2B
0x180010de8  mov     r14, rdi
0x180010deb  shl     r14, 10h
0x180010def  or      r14, rdi
0x180010df2  jmp     loc_180010C2B
0x180010df7  mov     eax, [rdi+50h]
0x180010dfa  test    al, 1
0x180010dfc  jz      loc_180010C2B
0x180010e02  or      r12d, 4
0x180010e06  and     eax, 0FFFFFFFEh
0x180010e09  mov     [rdi+50h], eax
0x180010e0c  jmp     loc_180010C2B
0x180010e11  xor     r13d, r13d
0x180010e14  jmp     loc_180010BF9
0x180010e19  test    r13, r13
0x180010e1c  jz      loc_180010BCA
0x180010e22  mov     rcx, r13; hMem
0x180010e25  call    cs:__imp_LocalFree
0x180010e2b  jmp     loc_180010BCA
0x180010e30  mov     rdx, [rbp+5Fh]; unsigned __int64
0x180010e34  mov     ecx, 80004005h; int
0x180010e39  mov     r8d, 43Dh; unsigned __int64
0x180010e3f  call    ?FailFastWithHR@@YAXJ_K0@Z; FailFastWithHR(long,unsigned __int64,unsigned __int64)
0x180010e44  jmp     loc_180010A57
0x180010e49  or      dword ptr [rax+28h], 4000000h
0x180010e50  mov     r15d, 48h ; 'H'
0x180010e56  jmp     loc_180010B4F
0x180010e5b  mov     r13, [rbp+57h+arg_18]
0x180010e5f  lea     r8, [rbp+57h+var_A0]; struct tagCPROXY_PARAM *
0x180010e63  mov     rcx, r13; struct MsgBase *
0x180010e66  mov     edx, 2; unsigned int
0x180010e6b  call    ?Unmarshal@MsgBase@@SAJPEAU1@KPEAUtagCPROXY_PARAM@@@Z; MsgBase::Unmarshal(MsgBase *,ulong,tagCPROXY_PARAM *)
0x180010e70  test    dword ptr [r13+28h], 4000000h
0x180010e78  mov     r15d, eax
0x180010e7b  jz      short loc_180010E8D
0x180010e7d  mov     r8, [r13+40h]
0x180010e81  xor     edx, edx
0x180010e83  mov     rcx, [rsi+8]
0x180010e87  call    cs:__imp_NtAlpcDeleteSectionView
0x180010e8d  cmp     r13, rdi
0x180010e90  jz      loc_180010BCA
0x180010e96  jmp     short loc_180010E19
0x180010e98  mov     rcx, rdi; hMem
0x180010e9b  call    cs:__imp_LocalFree
0x180010ea1  jmp     loc_180010BE4
0x180010ea6  mov     rdx, [rbp+5Fh]; unsigned __int64
0x180010eaa  mov     ecx, 80004005h; int
0x180010eaf  mov     r8d, 1CBh; unsigned __int64
0x180010eb5  call    ?FailFastWithHR@@YAXJ_K0@Z; FailFastWithHR(long,unsigned __int64,unsigned __int64)
0x180010eba  jmp     loc_180010D33
0x180010ebf  mov     eax, [rdi+50h]
0x180010ec2  test    al, 1
0x180010ec4  jz      loc_180010C2B
0x180010eca  jmp     loc_180010E02
0x180010ecf  and     eax, 0FFFFFFFEh
0x180010ed2  jmp     loc_180010DC5
```
