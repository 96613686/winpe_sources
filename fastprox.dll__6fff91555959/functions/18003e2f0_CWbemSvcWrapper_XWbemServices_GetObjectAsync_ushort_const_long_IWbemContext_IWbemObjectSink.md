# CWbemSvcWrapper::XWbemServices::GetObjectAsync(ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x18003e2f0`
- end: `0x18003e4da`
- name: `?GetObjectAsync@XWbemServices@CWbemSvcWrapper@@UEAAJQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `490`
- prototype: `int(CWbemSvcWrapper::XWbemServices *__hidden this, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180037120`
- `0x18003cf90`
- `0x18003e2f0`
- `0x18003e4e0`
- `0x18003eae0`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18003e43c`
- `wbemcomn!GetMemLogObject` at `0x18003e49c`
- `wbemcomn!GetMemLogObject` at `0x18003e43c`
- `wbemcomn!GetMemLogObject` at `0x18003e49c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e448`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e4a7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e448`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e4a7`
- `OLEAUT32!__imp_SysAllocString` at `0x18003e32d`
- `OLEAUT32!__imp_SysAllocString` at `0x18003e32d`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e41d`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e461`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e41d`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e461`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWbemSvcWrapper::XWbemServices::GetObjectAsync(
        CWbemSvcWrapper::XWbemServices *this,
        unsigned __int16 *const a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IWbemObjectSink *a5)
{
  OLECHAR *v9; // rdi
  int v10; // ebx
  char v11; // dl
  __int64 v12; // r8
  unsigned int v13; // r9d
  JAmsi *v14; // rcx
  CMemoryLog *v16; // rax
  CMemoryLog *MemLogObject; // rax

  if ( !*(_QWORD *)(*((_QWORD *)this + 1) + 32LL) )
    return 2147549448LL;
  if ( a2 )
  {
    v9 = SysAllocString(a2);
    v10 = -2147217402;
    if ( v9 )
    {
      v10 = 0;
    }
    else
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217402);
    }
  }
  else
  {
    v10 = 0;
    v9 = 0;
  }
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      WPP_4cf88f49dc983e1495872f01bb23639f_Traceguids,
      (unsigned int)v10);
  }
  if ( v10 < 0
    || (v10 = CProxySinkSecurity::EnsureSinkSecurity((CProxySinkSecurity *)(*((_QWORD *)this + 1) + 40LL), a5), v10 < 0) )
  {
LABEL_17:
    v16 = GetMemLogObject();
    CMemoryLog::Write(v16, v10);
LABEL_12:
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_4cf88f49dc983e1495872f01bb23639f_Traceguids,
        (unsigned int)v10);
    }
    if ( v9 )
      SysFreeString(v9);
    return (unsigned int)v10;
  }
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_JAmsi>::__private_IsEnabledPreCheck(
    (__int64)&`wil::Feature<__WilFeatureTraits_Feature_JAmsi>::GetImpl'::`2'::impl,
    v11,
    v12,
    v13);
  if ( !dword_1800D8070 || JAmsi::JAmsiProcessor(v14, a2, L"GetObject", (unsigned __int16 *)&dword_1800A657C, 0) >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD, struct IWbemContext *, struct IWbemObjectSink *))(**(_QWORD **)(*((_QWORD *)this + 1) + 32LL) + 56LL))(
            *(_QWORD *)(*((_QWORD *)this + 1) + 32LL),
            v9,
            a3,
            a4,
            a5);
    if ( v10 >= 0 )
      goto LABEL_12;
    goto LABEL_17;
  }
  if ( v9 )
    SysFreeString(v9);
  return 2147749889LL;
}

```

## disassembly

```asm
0x18003e2f0  mov     [rsp+arg_8], rbx
0x18003e2f5  mov     [rsp+arg_10], rbp
0x18003e2fa  push    rsi
0x18003e2fb  push    rdi
0x18003e2fc  push    r12
0x18003e2fe  push    r14
0x18003e300  push    r15
0x18003e302  sub     rsp, 30h
0x18003e306  mov     r15, r9
0x18003e309  mov     r12d, r8d
0x18003e30c  mov     rsi, rdx
0x18003e30f  mov     rbp, rcx
0x18003e312  mov     rax, [rcx+8]
0x18003e316  cmp     qword ptr [rax+20h], 0
0x18003e31b  jz      loc_18003E46E
0x18003e321  test    rdx, rdx
0x18003e324  jz      loc_18003E450
0x18003e32a  mov     rcx, rdx; psz
0x18003e32d  call    cs:__imp_SysAllocString
0x18003e333  mov     rdi, rax
0x18003e336  mov     ebx, 80041006h
0x18003e33b  xor     eax, eax
0x18003e33d  test    rdi, rdi
0x18003e340  cmovnz  ebx, eax
0x18003e343  jz      loc_18003E49C
0x18003e349  lea     rax, WPP_GLOBAL_Control
0x18003e350  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e357  cmp     rcx, rax
0x18003e35a  jz      short loc_18003E366
0x18003e35c  test    byte ptr [rcx+1Ch], 1
0x18003e360  jnz     loc_18003E475
0x18003e366  mov     [rsp+58h+arg_0], rdi
0x18003e36b  test    ebx, ebx
0x18003e36d  js      loc_18003E43C
0x18003e373  mov     rcx, [rbp+8]
0x18003e377  add     rcx, 28h ; '('; this
0x18003e37b  mov     r14, [rsp+58h+arg_20]
0x18003e383  mov     rdx, r14; struct IWbemObjectSink *
0x18003e386  call    ?EnsureSinkSecurity@CProxySinkSecurity@@QEAAJPEAUIWbemObjectSink@@@Z; CProxySinkSecurity::EnsureSinkSecurity(IWbemObjectSink *)
0x18003e38b  mov     ebx, eax
0x18003e38d  test    eax, eax
0x18003e38f  js      loc_18003E43C
0x18003e395  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_JAmsi@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_JAmsi@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_JAmsi> `wil::Feature<__WilFeatureTraits_Feature_JAmsi>::GetImpl(void)'::`2'::impl
0x18003e39c  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_JAmsi@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_JAmsi>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18003e3a1  cmp     cs:dword_1800D8070, 0
0x18003e3a8  jz      short loc_18003E3D0
0x18003e3aa  mov     [rsp+58h+var_38], 0; int
0x18003e3b2  lea     r9, dword_1800A657C; unsigned __int16 *
0x18003e3b9  lea     r8, aGetobject; "GetObject"
0x18003e3c0  mov     rdx, rsi; unsigned __int16 *
0x18003e3c3  call    ?JAmsiProcessor@JAmsi@@QEAAJPEAG00H@Z; JAmsi::JAmsiProcessor(ushort *,ushort *,ushort *,int)
0x18003e3c8  test    eax, eax
0x18003e3ca  js      loc_18003E459
0x18003e3d0  mov     rax, [rbp+8]
0x18003e3d4  mov     rcx, [rax+20h]
0x18003e3d8  mov     rax, [rcx]
0x18003e3db  mov     qword ptr [rsp+58h+var_38], r14
0x18003e3e0  mov     r9, r15
0x18003e3e3  mov     r8d, r12d
0x18003e3e6  mov     rdx, rdi
0x18003e3e9  mov     rax, [rax+38h]
0x18003e3ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e3f2  mov     ebx, eax
0x18003e3f4  test    eax, eax
0x18003e3f6  js      short loc_18003E43C
0x18003e3f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e3ff  lea     rax, WPP_GLOBAL_Control
0x18003e406  cmp     rcx, rax
0x18003e409  jz      short loc_18003E415
0x18003e40b  test    byte ptr [rcx+1Ch], 1
0x18003e40f  jnz     loc_18003E4B2
0x18003e415  test    rdi, rdi
0x18003e418  jz      short loc_18003E423
0x18003e41a  mov     rcx, rdi; bstrString
0x18003e41d  call    cs:__imp_SysFreeString
0x18003e423  mov     eax, ebx
0x18003e425  mov     rbx, [rsp+58h+arg_8]
0x18003e42a  mov     rbp, [rsp+58h+arg_10]
0x18003e42f  add     rsp, 30h
0x18003e433  pop     r15
0x18003e435  pop     r14
0x18003e437  pop     r12
0x18003e439  pop     rdi
0x18003e43a  pop     rsi
0x18003e43b  retn
0x18003e43c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003e442  nop
0x18003e443  mov     edx, ebx
0x18003e445  mov     rcx, rax
0x18003e448  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003e44e  jmp     short loc_18003E3F8
0x18003e450  xor     ebx, ebx
0x18003e452  xor     edi, edi
0x18003e454  jmp     loc_18003E349
0x18003e459  test    rdi, rdi
0x18003e45c  jz      short loc_18003E467
0x18003e45e  mov     rcx, rdi; bstrString
0x18003e461  call    cs:__imp_SysFreeString
0x18003e467  mov     eax, 80041001h
0x18003e46c  jmp     short loc_18003E425
0x18003e46e  mov     eax, 80010108h
0x18003e473  jmp     short loc_18003E425
0x18003e475  cmp     byte ptr [rcx+19h], 2
0x18003e479  jb      loc_18003E366
0x18003e47f  mov     edx, 1Dh
0x18003e484  mov     r9d, ebx
0x18003e487  lea     r8, WPP_4cf88f49dc983e1495872f01bb23639f_Traceguids
0x18003e48e  mov     rcx, [rcx+10h]
0x18003e492  call    WPP_SF_d
0x18003e497  jmp     loc_18003E366
0x18003e49c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003e4a2  mov     edx, ebx
0x18003e4a4  mov     rcx, rax
0x18003e4a7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003e4ad  jmp     loc_18003E349
0x18003e4b2  cmp     byte ptr [rcx+19h], 2
0x18003e4b6  jb      loc_18003E415
0x18003e4bc  mov     edx, 0Ch
0x18003e4c1  mov     r9d, ebx
0x18003e4c4  lea     r8, WPP_4cf88f49dc983e1495872f01bb23639f_Traceguids
0x18003e4cb  mov     rcx, [rcx+10h]
0x18003e4cf  call    WPP_SF_d
0x18003e4d4  jmp     loc_18003E415
```
