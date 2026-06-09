# CWbemSvcWrapper::XWbemServices::GetObjectW(ushort * const,long,IWbemContext *,IWbemClassObject * *,IWbemCallResult * *)

- ea: `0x18003cd70`
- end: `0x18003cf7b`
- name: `?GetObjectW@XWbemServices@CWbemSvcWrapper@@UEAAJQEAGJPEAUIWbemContext@@PEAPEAUIWbemClassObject@@PEAPEAUIWbemCallResult@@@Z`
- size: `523`
- prototype: `int(CWbemSvcWrapper::XWbemServices *__hidden this, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemClassObject **, struct IWbemCallResult **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180037120`
- `0x18003cd70`
- `0x18003cf90`
- `0x18003eae0`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18003cebb`
- `wbemcomn!GetMemLogObject` at `0x18003cf65`
- `wbemcomn!GetMemLogObject` at `0x18003cebb`
- `wbemcomn!GetMemLogObject` at `0x18003cf65`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003cec7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003cf70`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003cec7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003cf70`
- `OLEAUT32!__imp_SysAllocString` at `0x18003cdad`
- `OLEAUT32!__imp_SysAllocString` at `0x18003cdad`
- `OLEAUT32!__imp_SysFreeString` at `0x18003ce7f`
- `OLEAUT32!__imp_SysFreeString` at `0x18003cea8`
- `OLEAUT32!__imp_SysFreeString` at `0x18003cefd`
- `OLEAUT32!__imp_SysFreeString` at `0x18003ce7f`
- `OLEAUT32!__imp_SysFreeString` at `0x18003cea8`
- `OLEAUT32!__imp_SysFreeString` at `0x18003cefd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWbemSvcWrapper::XWbemServices::GetObjectW(
        CWbemSvcWrapper::XWbemServices *this,
        unsigned __int16 *const a2,
        __int64 a3,
        struct IWbemContext *a4,
        struct IWbemClassObject **a5,
        struct IWbemCallResult **a6)
{
  unsigned int v7; // r12d
  OLECHAR *v10; // rbx
  int v11; // edi
  JAmsi *v12; // rcx
  CMemoryLog *v14; // rax
  CMemoryLog *MemLogObject; // rax

  v7 = a3;
  if ( !*(_QWORD *)(*((_QWORD *)this + 1) + 32LL) )
    return 2147549448LL;
  if ( a2 )
  {
    v10 = SysAllocString(a2);
    v11 = -2147217402;
    if ( v10 )
    {
      v11 = 0;
    }
    else
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217402);
    }
  }
  else
  {
    v11 = 0;
    v10 = 0;
  }
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      WPP_4cf88f49dc983e1495872f01bb23639f_Traceguids,
      (unsigned int)v11);
  }
  if ( a5 )
    *a5 = 0;
  if ( v11 >= 0 )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_JAmsi>::__private_IsEnabledPreCheck(
      (__int64)&`wil::Feature<__WilFeatureTraits_Feature_JAmsi>::GetImpl'::`2'::impl,
      (char)a2,
      a3,
      (unsigned int)a4);
    if ( dword_1800D8070 && JAmsi::JAmsiProcessor(v12, a2, L"GetObject", (unsigned __int16 *)&dword_1800A657C, 0) < 0 )
    {
      if ( v10 )
        SysFreeString(v10);
      return 2147749889LL;
    }
    v11 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD, struct IWbemContext *, struct IWbemClassObject **, struct IWbemCallResult **))(**(_QWORD **)(*((_QWORD *)this + 1) + 32LL) + 48LL))(
            *(_QWORD *)(*((_QWORD *)this + 1) + 32LL),
            v10,
            v7,
            a4,
            a5,
            a6);
  }
  if ( v11 == -2147217406 )
  {
    if ( v10 )
      SysFreeString(v10);
    return 2147749890LL;
  }
  else
  {
    if ( v11 < 0 )
    {
      v14 = GetMemLogObject();
      CMemoryLog::Write(v14, v11);
    }
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_4cf88f49dc983e1495872f01bb23639f_Traceguids,
        (unsigned int)v11);
    }
    if ( v10 )
      SysFreeString(v10);
    return (unsigned int)v11;
  }
}

```

## disassembly

```asm
0x18003cd70  mov     [rsp+arg_8], rbx
0x18003cd75  mov     [rsp+arg_10], rbp
0x18003cd7a  push    rsi
0x18003cd7b  push    rdi
0x18003cd7c  push    r12
0x18003cd7e  push    r14
0x18003cd80  push    r15
0x18003cd82  sub     rsp, 40h
0x18003cd86  mov     r15, r9
0x18003cd89  mov     r12d, r8d
0x18003cd8c  mov     rsi, rdx
0x18003cd8f  mov     rbp, rcx
0x18003cd92  mov     rax, [rcx+8]
0x18003cd96  cmp     qword ptr [rax+20h], 0
0x18003cd9b  jz      loc_18003CF5B
0x18003cda1  test    rdx, rdx
0x18003cda4  jz      loc_18003CEB2
0x18003cdaa  mov     rcx, rdx; psz
0x18003cdad  call    cs:__imp_SysAllocString
0x18003cdb3  mov     rbx, rax
0x18003cdb6  mov     edi, 80041006h
0x18003cdbb  xor     eax, eax
0x18003cdbd  test    rbx, rbx
0x18003cdc0  cmovnz  edi, eax
0x18003cdc3  jz      loc_18003CF65
0x18003cdc9  lea     rax, WPP_GLOBAL_Control
0x18003cdd0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cdd7  cmp     rcx, rax
0x18003cdda  jz      short loc_18003CDE6
0x18003cddc  test    byte ptr [rcx+1Ch], 1
0x18003cde0  jnz     loc_18003CF0D
0x18003cde6  mov     [rsp+68h+arg_0], rbx
0x18003cdeb  mov     r14, [rsp+68h+arg_20]
0x18003cdf3  test    r14, r14
0x18003cdf6  jz      short loc_18003CDFF
0x18003cdf8  mov     qword ptr [r14], 0
0x18003cdff  test    edi, edi
0x18003ce01  js      short loc_18003CE4D
0x18003ce03  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_JAmsi@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_JAmsi@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_JAmsi> `wil::Feature<__WilFeatureTraits_Feature_JAmsi>::GetImpl(void)'::`2'::impl
0x18003ce0a  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_JAmsi@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_JAmsi>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18003ce0f  cmp     cs:dword_1800D8070, 0
0x18003ce16  jnz     loc_18003CECF
0x18003ce1c  mov     rax, [rbp+8]
0x18003ce20  mov     rcx, [rax+20h]
0x18003ce24  mov     rax, [rcx]
0x18003ce27  mov     rdx, [rsp+68h+arg_28]
0x18003ce2f  mov     [rsp+68h+var_40], rdx
0x18003ce34  mov     qword ptr [rsp+68h+var_48], r14
0x18003ce39  mov     r9, r15
0x18003ce3c  mov     r8d, r12d
0x18003ce3f  mov     rdx, rbx
0x18003ce42  mov     rax, [rax+30h]
0x18003ce46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce4b  mov     edi, eax
0x18003ce4d  mov     esi, 80041002h
0x18003ce52  cmp     edi, esi
0x18003ce54  jz      short loc_18003CEA0
0x18003ce56  test    edi, edi
0x18003ce58  js      short loc_18003CEBB
0x18003ce5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ce61  lea     rax, WPP_GLOBAL_Control
0x18003ce68  cmp     rcx, rax
0x18003ce6b  jz      short loc_18003CE77
0x18003ce6d  test    byte ptr [rcx+1Ch], 1
0x18003ce71  jnz     loc_18003CF34
0x18003ce77  test    rbx, rbx
0x18003ce7a  jz      short loc_18003CE85
0x18003ce7c  mov     rcx, rbx; bstrString
0x18003ce7f  call    cs:__imp_SysFreeString
0x18003ce85  mov     eax, edi
0x18003ce87  lea     r11, [rsp+68h+var_28]
0x18003ce8c  mov     rbx, [r11+38h]
0x18003ce90  mov     rbp, [r11+40h]
0x18003ce94  mov     rsp, r11
0x18003ce97  pop     r15
0x18003ce99  pop     r14
0x18003ce9b  pop     r12
0x18003ce9d  pop     rdi
0x18003ce9e  pop     rsi
0x18003ce9f  retn
0x18003cea0  test    rbx, rbx
0x18003cea3  jz      short loc_18003CEAE
0x18003cea5  mov     rcx, rbx; bstrString
0x18003cea8  call    cs:__imp_SysFreeString
0x18003ceae  mov     eax, esi
0x18003ceb0  jmp     short loc_18003CE87
0x18003ceb2  xor     edi, edi
0x18003ceb4  xor     ebx, ebx
0x18003ceb6  jmp     loc_18003CDC9
0x18003cebb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003cec1  nop
0x18003cec2  mov     edx, edi
0x18003cec4  mov     rcx, rax
0x18003cec7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003cecd  jmp     short loc_18003CE5A
0x18003cecf  mov     [rsp+68h+var_48], 0; int
0x18003ced7  lea     r9, dword_1800A657C; unsigned __int16 *
0x18003cede  lea     r8, aGetobject; "GetObject"
0x18003cee5  mov     rdx, rsi; unsigned __int16 *
0x18003cee8  call    ?JAmsiProcessor@JAmsi@@QEAAJPEAG00H@Z; JAmsi::JAmsiProcessor(ushort *,ushort *,ushort *,int)
0x18003ceed  test    eax, eax
0x18003ceef  jns     loc_18003CE1C
0x18003cef5  test    rbx, rbx
0x18003cef8  jz      short loc_18003CF03
0x18003cefa  mov     rcx, rbx; bstrString
0x18003cefd  call    cs:__imp_SysFreeString
0x18003cf03  mov     eax, 80041001h
0x18003cf08  jmp     loc_18003CE87
0x18003cf0d  cmp     byte ptr [rcx+19h], 2
0x18003cf11  jb      loc_18003CDE6
0x18003cf17  mov     edx, 1Dh
0x18003cf1c  mov     r9d, edi
0x18003cf1f  lea     r8, WPP_4cf88f49dc983e1495872f01bb23639f_Traceguids
0x18003cf26  mov     rcx, [rcx+10h]
0x18003cf2a  call    WPP_SF_d
0x18003cf2f  jmp     loc_18003CDE6
0x18003cf34  cmp     byte ptr [rcx+19h], 2
0x18003cf38  jb      loc_18003CE77
0x18003cf3e  mov     edx, 0Bh
0x18003cf43  mov     r9d, edi
0x18003cf46  lea     r8, WPP_4cf88f49dc983e1495872f01bb23639f_Traceguids
0x18003cf4d  mov     rcx, [rcx+10h]
0x18003cf51  call    WPP_SF_d
0x18003cf56  jmp     loc_18003CE77
0x18003cf5b  mov     eax, 80010108h
0x18003cf60  jmp     loc_18003CE87
0x18003cf65  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003cf6b  mov     edx, edi
0x18003cf6d  mov     rcx, rax
0x18003cf70  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003cf76  jmp     loc_18003CDC9
```
