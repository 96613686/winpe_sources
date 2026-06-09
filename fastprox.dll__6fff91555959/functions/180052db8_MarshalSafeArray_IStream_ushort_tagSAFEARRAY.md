# MarshalSafeArray(IStream *,ushort,tagSAFEARRAY *)

- ea: `0x180052db8`
- end: `0x18005317f`
- name: `?MarshalSafeArray@@YAJPEAUIStream@@GPEAUtagSAFEARRAY@@@Z`
- size: `967`
- prototype: `__int64 __fastcall(struct IStream *, __int16, struct tagSAFEARRAY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180052a30`

## callees

- `0x180037120`
- `0x180052db8`
- `0x180053190`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180053115`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180053115`
- `wbemcomn!GetMemLogObject` at `0x180052f15`
- `wbemcomn!GetMemLogObject` at `0x180052f6e`
- `wbemcomn!GetMemLogObject` at `0x180052fc8`
- `wbemcomn!GetMemLogObject` at `0x18005300c`
- `wbemcomn!GetMemLogObject` at `0x180053053`
- `wbemcomn!GetMemLogObject` at `0x18005309a`
- `wbemcomn!GetMemLogObject` at `0x180053126`
- `wbemcomn!GetMemLogObject` at `0x180052f15`
- `wbemcomn!GetMemLogObject` at `0x180052f6e`
- `wbemcomn!GetMemLogObject` at `0x180052fc8`
- `wbemcomn!GetMemLogObject` at `0x18005300c`
- `wbemcomn!GetMemLogObject` at `0x180053053`
- `wbemcomn!GetMemLogObject` at `0x18005309a`
- `wbemcomn!GetMemLogObject` at `0x180053126`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052f20`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052f79`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052fd3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180053017`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005305e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800530a5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180053131`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052f20`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052f79`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052fd3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180053017`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005305e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800530a5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180053131`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x180052e51`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x180052e51`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180052e0b`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180052e0b`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180052df1`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180052df1`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180052e8c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180052e8c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180052eb6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180053172`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180052eb6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180053172`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MarshalSafeArray(struct IStream *a1, __int16 a2, struct tagSAFEARRAY *a3)
{
  HRESULT LBound; // edi
  unsigned __int16 **v7; // rsi
  int i; // edi
  CMemoryLog *v10; // rax
  CMemoryLog *v11; // rax
  CWbemRefreshingSvc *v12; // r10
  __int64 v13; // rdx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v15; // rax
  CMemoryLog *v16; // rax
  CMemoryLog *v17; // rax
  LPUNKNOWN *v18; // r15
  int j; // edi
  HRESULT v20; // esi
  CMemoryLog *v21; // rax
  int v22; // [rsp+30h] [rbp-20h] BYREF
  LONG plUbound; // [rsp+34h] [rbp-1Ch] BYREF
  LONG plLbound; // [rsp+38h] [rbp-18h] BYREF
  UINT Elemsize; // [rsp+3Ch] [rbp-14h] BYREF
  void *ppvData[2]; // [rsp+40h] [rbp-10h] BYREF

  plLbound = 0;
  plUbound = 0;
  LBound = SafeArrayGetLBound(a3, 1u, &plLbound);
  if ( LBound < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, LBound);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)LBound;
    }
    v13 = 21;
LABEL_23:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids, (unsigned int)LBound);
    return (unsigned int)LBound;
  }
  LBound = SafeArrayGetUBound(a3, 1u, &plUbound);
  if ( LBound < 0 )
  {
    v16 = GetMemLogObject();
    CMemoryLog::Write(v16, LBound);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)LBound;
    }
    v13 = 22;
    goto LABEL_23;
  }
  v22 = plUbound - plLbound + 1;
  LBound = ((__int64 (__fastcall *)(struct IStream *, int *, __int64, _QWORD))a1->lpVtbl->Write)(a1, &v22, 4, 0);
  if ( LBound < 0 )
  {
    v15 = GetMemLogObject();
    CMemoryLog::Write(v15, LBound);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)LBound;
    }
    v13 = 23;
    goto LABEL_23;
  }
  Elemsize = SafeArrayGetElemsize(a3);
  LBound = ((__int64 (__fastcall *)(struct IStream *, UINT *, __int64, _QWORD))a1->lpVtbl->Write)(a1, &Elemsize, 4, 0);
  if ( LBound < 0 )
  {
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, LBound);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)LBound;
    }
    v13 = 24;
    goto LABEL_23;
  }
  ppvData[0] = 0;
  LBound = SafeArrayAccessData(a3, ppvData);
  if ( LBound < 0 )
  {
    v11 = GetMemLogObject();
    CMemoryLog::Write(v11, LBound);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)LBound;
    }
    v13 = 25;
    goto LABEL_23;
  }
  ppvData[1] = a3;
  if ( a2 == 8 )
  {
    v7 = (unsigned __int16 **)ppvData[0];
    for ( i = 0; i < v22; ++i )
      MarshalBSTR(a1, v7[i]);
  }
  else if ( a2 == 13 )
  {
    v18 = (LPUNKNOWN *)ppvData[0];
    for ( j = 0; j < v22; ++j )
    {
      v20 = CoMarshalInterface(a1, &IID_IWbemClassObject, v18[j], 0, 0, 0);
      if ( v20 < 0 )
      {
        v21 = GetMemLogObject();
        CMemoryLog::Write(v21, v20);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
            (unsigned int)v20);
        }
        SafeArrayUnaccessData(a3);
        return (unsigned int)v20;
      }
    }
  }
  else
  {
    LBound = ((__int64 (__fastcall *)(struct IStream *, void *, _QWORD, _QWORD))a1->lpVtbl->Write)(
               a1,
               ppvData[0],
               v22 * Elemsize,
               0);
    if ( LBound < 0 )
    {
      v10 = GetMemLogObject();
      CMemoryLog::Write(v10, LBound);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
          (unsigned int)LBound);
      }
      goto LABEL_9;
    }
  }
  LBound = 0;
LABEL_9:
  SafeArrayUnaccessData(a3);
  return (unsigned int)LBound;
}

```

## disassembly

```asm
0x180052db8  push    rbp
0x180052dba  push    rbx
0x180052dbb  push    rsi
0x180052dbc  push    rdi
0x180052dbd  push    r13
0x180052dbf  push    r14
0x180052dc1  push    r15
0x180052dc3  mov     rbp, rsp
0x180052dc6  sub     rsp, 50h
0x180052dca  mov     rbx, r8
0x180052dcd  movzx   esi, dx
0x180052dd0  mov     r14, rcx
0x180052dd3  mov     [rbp+plLbound], 0
0x180052dda  mov     [rbp+plUbound], 0
0x180052de1  lea     r8, [rbp+plLbound]; plLbound
0x180052de5  mov     r13d, 1
0x180052deb  mov     edx, r13d; nDim
0x180052dee  mov     rcx, rbx; psa
0x180052df1  call    cs:__imp_SafeArrayGetLBound
0x180052df7  mov     edi, eax
0x180052df9  test    eax, eax
0x180052dfb  js      loc_180052FC8
0x180052e01  lea     r8, [rbp+plUbound]; plUbound
0x180052e05  mov     edx, r13d; nDim
0x180052e08  mov     rcx, rbx; psa
0x180052e0b  call    cs:__imp_SafeArrayGetUBound
0x180052e11  mov     edi, eax
0x180052e13  test    eax, eax
0x180052e15  js      loc_180053053
0x180052e1b  mov     eax, [rbp+plUbound]
0x180052e1e  sub     eax, [rbp+plLbound]
0x180052e21  add     eax, r13d
0x180052e24  mov     [rbp+var_20], eax
0x180052e27  mov     rax, [r14]
0x180052e2a  xor     r9d, r9d
0x180052e2d  lea     r15d, [r13+3]
0x180052e31  mov     r8d, r15d
0x180052e34  lea     rdx, [rbp+var_20]
0x180052e38  mov     rcx, r14
0x180052e3b  mov     rax, [rax+20h]
0x180052e3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e44  mov     edi, eax
0x180052e46  test    eax, eax
0x180052e48  js      loc_18005300C
0x180052e4e  mov     rcx, rbx; psa
0x180052e51  call    cs:__imp_SafeArrayGetElemsize
0x180052e57  mov     [rbp+var_14], eax
0x180052e5a  mov     rax, [r14]
0x180052e5d  xor     r9d, r9d
0x180052e60  mov     r8d, r15d
0x180052e63  lea     rdx, [rbp+var_14]
0x180052e67  mov     rcx, r14
0x180052e6a  mov     rax, [rax+20h]
0x180052e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e73  mov     edi, eax
0x180052e75  test    eax, eax
0x180052e77  js      loc_18005309A
0x180052e7d  mov     [rbp+ppvData], 0
0x180052e85  lea     rdx, [rbp+ppvData]; ppvData
0x180052e89  mov     rcx, rbx; psa
0x180052e8c  call    cs:__imp_SafeArrayAccessData
0x180052e92  mov     edi, eax
0x180052e94  test    eax, eax
0x180052e96  js      loc_180052F6E
0x180052e9c  mov     [rbp+var_8], rbx
0x180052ea0  cmp     si, 8
0x180052ea4  jnz     short loc_180052EE6
0x180052ea6  mov     rsi, [rbp+ppvData]
0x180052eaa  xor     edi, edi
0x180052eac  cmp     [rbp+var_20], edi
0x180052eaf  jg      short loc_180052ECD
0x180052eb1  xor     edi, edi
0x180052eb3  mov     rcx, rbx; psa
0x180052eb6  call    cs:__imp_SafeArrayUnaccessData
0x180052ebc  mov     eax, edi
0x180052ebe  add     rsp, 50h
0x180052ec2  pop     r15
0x180052ec4  pop     r14
0x180052ec6  pop     r13
0x180052ec8  pop     rdi
0x180052ec9  pop     rsi
0x180052eca  pop     rbx
0x180052ecb  pop     rbp
0x180052ecc  retn
0x180052ecd  movsxd  rdx, edi
0x180052ed0  mov     rdx, [rsi+rdx*8]; unsigned __int16 *
0x180052ed4  mov     rcx, r14; struct IStream *
0x180052ed7  call    ?MarshalBSTR@@YAJPEAUIStream@@PEAG@Z; MarshalBSTR(IStream *,ushort *)
0x180052edc  add     edi, r13d
0x180052edf  cmp     edi, [rbp+var_20]
0x180052ee2  jge     short loc_180052EB1
0x180052ee4  jmp     short loc_180052ECD
0x180052ee6  cmp     si, 0Dh
0x180052eea  jz      loc_1800530E1
0x180052ef0  mov     rax, [r14]
0x180052ef3  mov     r8d, [rbp+var_14]
0x180052ef7  imul    r8d, [rbp+var_20]
0x180052efc  xor     r9d, r9d
0x180052eff  mov     rdx, [rbp+ppvData]
0x180052f03  mov     rcx, r14
0x180052f06  mov     rax, [rax+20h]
0x180052f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f0f  mov     edi, eax
0x180052f11  test    eax, eax
0x180052f13  jns     short loc_180052EB1
0x180052f15  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180052f1b  mov     edx, edi
0x180052f1d  mov     rcx, rax
0x180052f20  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180052f26  lea     rcx, WPP_GLOBAL_Control
0x180052f2d  mov     rax, cs:WPP_GLOBAL_Control
0x180052f34  cmp     rax, rcx
0x180052f37  jz      loc_180052EB3
0x180052f3d  test    [rax+1Ch], r13b
0x180052f41  jz      loc_180052EB3
0x180052f47  cmp     byte ptr [rax+19h], 2
0x180052f4b  jb      loc_180052EB3
0x180052f51  mov     edx, 1Bh
0x180052f56  mov     r9d, edi
0x180052f59  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x180052f60  mov     rcx, [rax+10h]
0x180052f64  call    WPP_SF_d
0x180052f69  jmp     loc_180052EB3
0x180052f6e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180052f74  mov     edx, edi
0x180052f76  mov     rcx, rax
0x180052f79  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180052f7f  lea     rcx, WPP_GLOBAL_Control
0x180052f86  mov     r10, cs:WPP_GLOBAL_Control
0x180052f8d  cmp     r10, rcx
0x180052f90  jz      loc_180052EBC
0x180052f96  test    [r10+1Ch], r13b
0x180052f9a  jz      loc_180052EBC
0x180052fa0  cmp     byte ptr [r10+19h], 2
0x180052fa5  jb      loc_180052EBC
0x180052fab  mov     edx, 19h
0x180052fb0  mov     r9d, edi
0x180052fb3  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x180052fba  mov     rcx, [r10+10h]
0x180052fbe  call    WPP_SF_d
0x180052fc3  jmp     loc_180052EBC
0x180052fc8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180052fce  mov     edx, edi
0x180052fd0  mov     rcx, rax
0x180052fd3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180052fd9  lea     rcx, WPP_GLOBAL_Control
0x180052fe0  mov     r10, cs:WPP_GLOBAL_Control
0x180052fe7  cmp     r10, rcx
0x180052fea  jz      loc_180052EBC
0x180052ff0  test    [r10+1Ch], r13b
0x180052ff4  jz      loc_180052EBC
0x180052ffa  cmp     byte ptr [r10+19h], 2
0x180052fff  jb      loc_180052EBC
0x180053005  mov     edx, 15h
0x18005300a  jmp     short loc_180052FB0
0x18005300c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180053012  mov     edx, edi
0x180053014  mov     rcx, rax
0x180053017  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005301d  lea     rcx, WPP_GLOBAL_Control
0x180053024  mov     r10, cs:WPP_GLOBAL_Control
0x18005302b  cmp     r10, rcx
0x18005302e  jz      loc_180052EBC
0x180053034  test    [r10+1Ch], r13b
0x180053038  jz      loc_180052EBC
0x18005303e  cmp     byte ptr [r10+19h], 2
0x180053043  jb      loc_180052EBC
0x180053049  mov     edx, 17h
0x18005304e  jmp     loc_180052FB0
0x180053053  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180053059  mov     edx, edi
0x18005305b  mov     rcx, rax
0x18005305e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180053064  lea     rcx, WPP_GLOBAL_Control
0x18005306b  mov     r10, cs:WPP_GLOBAL_Control
0x180053072  cmp     r10, rcx
0x180053075  jz      loc_180052EBC
0x18005307b  test    [r10+1Ch], r13b
0x18005307f  jz      loc_180052EBC
0x180053085  cmp     byte ptr [r10+19h], 2
0x18005308a  jb      loc_180052EBC
0x180053090  mov     edx, 16h
0x180053095  jmp     loc_180052FB0
0x18005309a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800530a0  mov     edx, edi
0x1800530a2  mov     rcx, rax
0x1800530a5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800530ab  lea     rcx, WPP_GLOBAL_Control
0x1800530b2  mov     r10, cs:WPP_GLOBAL_Control
0x1800530b9  cmp     r10, rcx
0x1800530bc  jz      loc_180052EBC
0x1800530c2  test    [r10+1Ch], r13b
0x1800530c6  jz      loc_180052EBC
0x1800530cc  cmp     byte ptr [r10+19h], 2
0x1800530d1  jb      loc_180052EBC
0x1800530d7  mov     edx, 18h
0x1800530dc  jmp     loc_180052FB0
0x1800530e1  mov     r15, [rbp+ppvData]
0x1800530e5  xor     edi, edi
0x1800530e7  cmp     edi, [rbp+var_20]
0x1800530ea  jge     loc_180052EB1
0x1800530f0  movsxd  r8, edi
0x1800530f3  mov     [rsp+50h+mshlflags], 0; mshlflags
0x1800530fb  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x180053104  xor     r9d, r9d; dwDestContext
0x180053107  mov     r8, [r15+r8*8]; pUnk
0x18005310b  lea     rdx, IID_IWbemClassObject; riid
0x180053112  mov     rcx, r14; pStm
0x180053115  call    cs:__imp_CoMarshalInterface
0x18005311b  mov     esi, eax
0x18005311d  test    eax, eax
0x18005311f  js      short loc_180053126
0x180053121  add     edi, r13d
0x180053124  jmp     short loc_1800530E7
0x180053126  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005312c  mov     edx, esi
0x18005312e  mov     rcx, rax
0x180053131  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180053137  lea     rcx, WPP_GLOBAL_Control
0x18005313e  mov     rax, cs:WPP_GLOBAL_Control
0x180053145  cmp     rax, rcx
0x180053148  jz      short loc_18005316F
0x18005314a  test    [rax+1Ch], r13b
0x18005314e  jz      short loc_18005316F
0x180053150  cmp     byte ptr [rax+19h], 2
0x180053154  jb      short loc_18005316F
0x180053156  mov     edx, 1Ah
0x18005315b  mov     r9d, esi
0x18005315e  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x180053165  mov     rcx, [rax+10h]
0x180053169  call    WPP_SF_d
0x18005316e  nop
0x18005316f  mov     rcx, rbx; psa
0x180053172  call    cs:__imp_SafeArrayUnaccessData
0x180053178  mov     eax, esi
0x18005317a  jmp     loc_180052EBE
```
