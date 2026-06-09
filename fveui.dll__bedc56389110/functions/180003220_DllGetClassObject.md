# DllGetClassObject

- ea: `0x180003220`
- end: `0x1800033a2`
- name: `DllGetClassObject`
- size: `386`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002f50`
- `0x18000303c`
- `0x180003220`
- `0x1800037a0`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT UniqueNo; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  void *v12; // [rsp+40h] [rbp+18h] BYREF

  v12 = 0;
  if ( ppv )
  {
    *ppv = 0;
    v8 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_FveUi.Data1;
    if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_FveUi.Data1 )
      v8 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_FveUi.Data4;
    if ( v8 )
    {
      v7 = 2147746065LL;
      UniqueNo = -2147221231;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v6 = 13;
        goto LABEL_5;
      }
    }
    else
    {
      v9 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IClassFactory.Data1;
      if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IClassFactory.Data1 )
        v9 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IClassFactory.Data4;
      if ( !v9 )
        goto LABEL_21;
      v10 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
      if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
        v10 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IUnknown.Data4;
      if ( v10 )
      {
        v7 = 2147746065LL;
        UniqueNo = -2147221231;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          v6 = 14;
          goto LABEL_5;
        }
      }
      else
      {
LABEL_21:
        UniqueNo = MakeUniqueNoThrow<CFveUiClassFactory>(&v12);
        if ( !UniqueNo )
          goto LABEL_26;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_2cd505cd70833f31b3a2527f23c3e5f0_Traceguids,
            (unsigned int)UniqueNo);
        if ( UniqueNo >= 0 )
        {
LABEL_26:
          *ppv = v12;
          v12 = 0;
        }
      }
    }
  }
  else
  {
    UniqueNo = -2147467261;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v6 = 12;
      v7 = 2147500035LL;
LABEL_5:
      WPP_SF_d(v5[2], v6, WPP_2cd505cd70833f31b3a2527f23c3e5f0_Traceguids, v7);
    }
  }
  std::unique_ptr<CFveUiDispatch>::~unique_ptr<CFveUiDispatch>(&v12, riid);
  return UniqueNo;
}

```

## disassembly

```asm
0x180003220  mov     [rsp+arg_0], rbx
0x180003225  push    rdi
0x180003226  sub     rsp, 20h
0x18000322a  mov     [rsp+28h+arg_10], 0
0x180003233  mov     rdi, r8
0x180003236  test    r8, r8
0x180003239  jnz     short loc_18000327D
0x18000323b  mov     ebx, 80004003h
0x180003240  mov     rcx, cs:WPP_GLOBAL_Control
0x180003247  lea     rax, WPP_GLOBAL_Control
0x18000324e  cmp     rcx, rax
0x180003251  jz      loc_18000338B
0x180003257  test    byte ptr [rcx+1Ch], 40h
0x18000325b  jz      loc_18000338B
0x180003261  lea     edx, [r8+0Ch]
0x180003265  mov     r9d, ebx
0x180003268  mov     rcx, [rcx+10h]
0x18000326c  lea     r8, WPP_2cd505cd70833f31b3a2527f23c3e5f0_Traceguids
0x180003273  call    WPP_SF_d
0x180003278  jmp     loc_18000338B
0x18000327d  mov     qword ptr [r8], 0
0x180003284  mov     rax, [rcx]
0x180003287  sub     rax, qword ptr cs:CLSID_FveUi.Data1
0x18000328e  jnz     short loc_18000329B
0x180003290  mov     rax, [rcx+8]
0x180003294  sub     rax, qword ptr cs:CLSID_FveUi.Data4
0x18000329b  test    rax, rax
0x18000329e  jz      short loc_1800032D1
0x1800032a0  mov     r9d, 80040111h
0x1800032a6  mov     ebx, r9d
0x1800032a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032b0  lea     rax, WPP_GLOBAL_Control
0x1800032b7  cmp     rcx, rax
0x1800032ba  jz      loc_18000338B
0x1800032c0  test    byte ptr [rcx+1Ch], 40h
0x1800032c4  jz      loc_18000338B
0x1800032ca  mov     edx, 0Dh
0x1800032cf  jmp     short loc_180003268
0x1800032d1  mov     rax, [rdx]
0x1800032d4  sub     rax, qword ptr cs:IID_IClassFactory.Data1
0x1800032db  jnz     short loc_1800032E8
0x1800032dd  mov     rax, [rdx+8]
0x1800032e1  sub     rax, qword ptr cs:IID_IClassFactory.Data4
0x1800032e8  test    rax, rax
0x1800032eb  jz      short loc_180003335
0x1800032ed  mov     rax, [rdx]
0x1800032f0  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x1800032f7  jnz     short loc_180003304
0x1800032f9  mov     rax, [rdx+8]
0x1800032fd  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180003304  test    rax, rax
0x180003307  jz      short loc_180003335
0x180003309  mov     r9d, 80040111h
0x18000330f  mov     ebx, r9d
0x180003312  mov     rcx, cs:WPP_GLOBAL_Control
0x180003319  lea     rax, WPP_GLOBAL_Control
0x180003320  cmp     rcx, rax
0x180003323  jz      short loc_18000338B
0x180003325  test    byte ptr [rcx+1Ch], 40h
0x180003329  jz      short loc_18000338B
0x18000332b  mov     edx, 0Eh
0x180003330  jmp     loc_180003268
0x180003335  lea     rcx, [rsp+28h+arg_10]
0x18000333a  call    ??$MakeUniqueNoThrow@VCFveUiClassFactory@@@@YAJAEAV?$unique_ptr@VCFveUiClassFactory@@U?$default_delete@VCFveUiClassFactory@@@std@@@std@@@Z; MakeUniqueNoThrow<CFveUiClassFactory>(std::unique_ptr<CFveUiClassFactory> &)
0x18000333f  mov     ebx, eax
0x180003341  test    eax, eax
0x180003343  jz      short loc_18000337A
0x180003345  mov     rcx, cs:WPP_GLOBAL_Control
0x18000334c  lea     rax, WPP_GLOBAL_Control
0x180003353  cmp     rcx, rax
0x180003356  jz      short loc_180003376
0x180003358  test    byte ptr [rcx+1Ch], 40h
0x18000335c  jz      short loc_180003376
0x18000335e  mov     rcx, [rcx+10h]
0x180003362  lea     r8, WPP_2cd505cd70833f31b3a2527f23c3e5f0_Traceguids
0x180003369  mov     edx, 0Fh
0x18000336e  mov     r9d, ebx
0x180003371  call    WPP_SF_d
0x180003376  test    ebx, ebx
0x180003378  js      short loc_18000338B
0x18000337a  mov     rax, [rsp+28h+arg_10]
0x18000337f  mov     [rdi], rax
0x180003382  mov     [rsp+28h+arg_10], 0
0x18000338b  lea     rcx, [rsp+28h+arg_10]
0x180003390  call    ??1?$unique_ptr@VCFveUiDispatch@@U?$default_delete@VCFveUiDispatch@@@std@@@std@@QEAA@XZ; std::unique_ptr<CFveUiDispatch>::~unique_ptr<CFveUiDispatch>(void)
0x180003395  mov     eax, ebx
0x180003397  mov     rbx, [rsp+28h+arg_0]
0x18000339c  add     rsp, 20h
0x1800033a0  pop     rdi
0x1800033a1  retn
```
