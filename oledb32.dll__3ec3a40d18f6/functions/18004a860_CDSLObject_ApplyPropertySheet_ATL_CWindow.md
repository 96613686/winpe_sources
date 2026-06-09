# CDSLObject::ApplyPropertySheet(ATL::CWindow *)

- ea: `0x18004a860`
- end: `0x18004adf5`
- name: `?ApplyPropertySheet@CDSLObject@@QEAAJPEAVCWindow@ATL@@@Z`
- size: `1429`
- prototype: `__int64 __fastcall(CDSLObject *__hidden this, struct ATL::CWindow *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180050974`
- `0x18005a474`

## callees

- `0x180013870`
- `0x180023aec`
- `0x180027cf4`
- `0x18002ec0c`
- `0x18004a860`
- `0x18004b938`
- `0x18007e6ca`
- `0x18007e700`
- `0x18007e7c0`
- `0x180087010`

## import_xrefs

- `MSDART!mpFree` at `0x18004acc1`
- `MSDART!mpFree` at `0x18004acc1`
- `USER32!MessageBoxW` at `0x18004a993`
- `USER32!MessageBoxW` at `0x18004ad8e`
- `USER32!MessageBoxW` at `0x18004a993`
- `USER32!MessageBoxW` at `0x18004ad8e`
- `USER32!LoadStringW` at `0x18004a904`
- `USER32!LoadStringW` at `0x18004a976`
- `USER32!LoadStringW` at `0x18004ad51`
- `USER32!LoadStringW` at `0x18004ad71`
- `USER32!LoadStringW` at `0x18004a904`
- `USER32!LoadStringW` at `0x18004a976`
- `USER32!LoadStringW` at `0x18004ad51`
- `USER32!LoadStringW` at `0x18004ad71`
- `ole32!CoCreateInstance` at `0x18004ab6b`
- `ole32!CoCreateInstance` at `0x18004ab6b`

## pseudocode

```c
__int64 __fastcall CDSLObject::ApplyPropertySheet(CDSLObject *this, HWND *a2)
{
  HWND *v2; // r12
  __int64 result; // rax
  __int64 v5; // r15
  unsigned int v6; // r8d
  int v7; // eax
  unsigned int v8; // ebx
  __int64 (__fastcall ***v9)(_QWORD, GUID *, LPVOID *); // rcx
  int v10; // eax
  _QWORD *v11; // rcx
  int v12; // eax
  int v13; // ebx
  int v14; // eax
  int InitializationString; // ebx
  HRESULT v16; // eax
  __int64 *v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // eax
  int v21; // eax
  __int64 v22; // [rsp+0h] [rbp-2898h] BYREF
  int v23; // [rsp+30h] [rbp-2868h]
  LPVOID ppv; // [rsp+38h] [rbp-2860h] BYREF
  unsigned __int16 *v25; // [rsp+40h] [rbp-2858h] BYREF
  int pExceptionObject; // [rsp+48h] [rbp-2850h] BYREF
  int v27; // [rsp+4Ch] [rbp-284Ch] BYREF
  int v28; // [rsp+50h] [rbp-2848h] BYREF
  int v29; // [rsp+54h] [rbp-2844h] BYREF
  int v30; // [rsp+58h] [rbp-2840h] BYREF
  int v31; // [rsp+5Ch] [rbp-283Ch] BYREF
  struct ATL::CWindow *v32; // [rsp+60h] [rbp-2838h]
  WCHAR Caption; // [rsp+70h] [rbp-2828h] BYREF
  _BYTE v34[1022]; // [rsp+72h] [rbp-2826h] BYREF
  WCHAR Text; // [rsp+470h] [rbp-2428h] BYREF
  _BYTE v36[1022]; // [rsp+472h] [rbp-2426h] BYREF
  WCHAR Buffer[2]; // [rsp+870h] [rbp-2028h] BYREF
  _BYTE v38[8188]; // [rsp+874h] [rbp-2024h] BYREF

  v2 = a2;
  v32 = (struct ATL::CWindow *)a2;
  if ( *((_BYTE *)this + 1009) )
    return 0;
  *((_BYTE *)this + 1009) = 1;
  v5 = *((_QWORD *)this + 14) + 104LL * *((int *)this + 30);
  result = CDSLObject::OnTrackSavePassword(this, (struct CDSLProviderInformation *)v5);
  if ( (int)result < 0 )
    goto LABEL_58;
  *(_DWORD *)Buffer = 0;
  memset_0(v38, 0, sizeof(v38));
  LoadStringW(hInstance, 0xAu, Buffer, 512);
  v7 = CDSLProviderInformation::Apply((CDSLProviderInformation *)v5, Buffer, v6);
  v8 = v7;
  v23 = v7;
  if ( v7 < 0 || v7 == 265946 )
  {
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(v7, L"<CDSLObject::ApplyPropertySheet|OLEDB|ERR> ", 0x1E0u);
    Caption = 0;
    memset_0(v34, 0, sizeof(v34));
    LoadStringW(hInstance, 0x5Eu, &Caption, 512);
    if ( MessageBoxW(*v2, Buffer, &Caption, 0x11u) == 1 )
    {
      v23 = 0;
      goto LABEL_63;
    }
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(v8, L"<CDSLObject::ApplyPropertySheet|OLEDB|ERR> ", 0x1F0u);
    if ( v8 == 265946 )
      v8 = -2147217842;
    result = v8;
LABEL_58:
    *((_BYTE *)this + 1009) = 0;
    return result;
  }
LABEL_63:
  try
  {
    v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, LPVOID *))**((_QWORD **)this + 124);
    if ( v9 )
    {
      ppv = 0;
      v10 = (**v9)(v9, &IID_IDBProperties, &ppv);
      v23 = v10;
      if ( v10 < 0 )
      {
        pExceptionObject = v10;
        throw (long *)&pExceptionObject;
      }
      v11 = (_QWORD *)*((_QWORD *)this + 124);
      if ( *(LPVOID *)(v5 + 96) == ppv )
      {
        v25 = 0;
        v14 = (**(__int64 (__fastcall ***)(_QWORD, char *, unsigned __int16 **))*v11)(*v11, (char *)this + 976, &v25);
        v13 = v14;
        v23 = v14;
        if ( v14 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
            OLEDBTraceErr(v14, L"<CDSLObject::ApplyPropertySheet|OLEDB|ERR> ", 0x222u);
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          v28 = v13;
          throw (long *)&v28;
        }
        (*(void (__fastcall **)(_QWORD))(***((_QWORD ***)this + 124) + 16LL))(**((_QWORD **)this + 124));
        **((_QWORD **)this + 124) = v25;
      }
      else
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 16LL))(*v11);
        v12 = (***(__int64 (__fastcall ****)(_QWORD, char *, _QWORD))(v5 + 96))(
                *(_QWORD *)(v5 + 96),
                (char *)this + 976,
                *((_QWORD *)this + 124));
        v13 = v12;
        v23 = v12;
        if ( v12 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
            OLEDBTraceErr(v12, L"<CDSLObject::ApplyPropertySheet|OLEDB|ERR> ", 0x214u);
          v27 = v13;
          throw (long *)&v27;
        }
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    else
    {
      v21 = (***(__int64 (__fastcall ****)(_QWORD, char *))(v5 + 96))(*(_QWORD *)(v5 + 96), (char *)this + 976);
      v13 = v21;
      v23 = v21;
      if ( v21 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(v21, L"<CDSLObject::ApplyPropertySheet|OLEDB|ERR> ", 0x231u);
        v29 = v13;
        throw (long *)&v29;
      }
    }
    if ( !*((_QWORD *)this + 130) )
      goto LABEL_65;
    ppv = 0;
    v25 = 0;
    try
    {
      if ( *(_BYTE *)(v5 + 88) )
      {
        InitializationString = GetInitializationString(*(struct IUnknown **)(v5 + 96), 1u, &v25);
        if ( InitializationString >= 0 )
        {
          v16 = CoCreateInstance(&CLSID_MSDAINITIALIZE, 0, 1u, &IID_IDataInitialize, &ppv);
          v13 = v16;
          v23 = v16;
          if ( v16 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
              OLEDBTraceErr(v16, L"<CDSLObject::ApplyPropertySheet|OLEDB|ERR> ", 0x258u);
          }
          else
          {
            v20 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, unsigned __int16 *, __int64))(*(_QWORD *)ppv + 64LL))(
                    ppv,
                    *((_QWORD *)this + 130),
                    v25,
                    4);
            v13 = v20;
            v23 = v20;
            if ( v20 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
                OLEDBTraceErr(v20, L"<CDSLObject::ApplyPropertySheet|OLEDB|ERR> ", 0x252u);
              v30 = v13;
              throw (long *)&v30;
            }
          }
          goto LABEL_70;
        }
      }
      else
      {
        InitializationString = -2147467259;
      }
      v23 = InitializationString;
      if ( (bidGblFlags & 2) != 0 )
        OLEDBTraceErr(InitializationString, L"<CDSLObject::ApplyPropertySheet|OLEDB|ERR> ", 0x242u);
      v31 = InitializationString;
      throw (long *)&v31;
    }
    catch ( long )
    {
      v17 = &v22;
      v13 = v23;
      v2 = (HWND *)v32;
    }
LABEL_70:
    if ( ppv )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      ppv = 0;
    }
    mpFree(v25, v17, v18, v19);
  }
  catch ( long )
  {
    v13 = v23;
    v2 = (HWND *)v32;
  }
LABEL_65:
  if ( v13 < 0 && v13 != -2147467262 )
  {
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(v13, L"<CDSLObject::ApplyPropertySheet|OLEDB|ERR> ", 0x26Fu);
    Caption = 0;
    memset_0(v34, 0, sizeof(v34));
    Text = 0;
    memset_0(v36, 0, sizeof(v36));
    LoadStringW(hInstance, 0x5Eu, &Caption, 512);
    LoadStringW(hInstance, 0xBu, &Text, 512);
    MessageBoxW(*v2, &Text, &Caption, 0x10u);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18004a860  mov     [rsp+arg_10], rbx
0x18004a865  mov     [rsp+arg_18], rsi
0x18004a86a  push    rdi
0x18004a86b  push    r12
0x18004a86d  push    r15
0x18004a86f  mov     eax, 2880h
0x18004a874  call    _alloca_probe
0x18004a879  sub     rsp, rax
0x18004a87c  mov     rax, cs:__security_cookie
0x18004a883  xor     rax, rsp
0x18004a886  mov     [rsp+2898h+var_28], rax
0x18004a88e  mov     r12, rdx
0x18004a891  mov     rsi, rcx
0x18004a894  mov     [rsp+2898h+var_2838], rdx
0x18004a899  xor     edi, edi
0x18004a89b  cmp     [rcx+3F1h], dil
0x18004a8a2  jz      short loc_18004A8AB
0x18004a8a4  xor     eax, eax
0x18004a8a6  jmp     loc_18004ADCC
0x18004a8ab  mov     byte ptr [rcx+3F1h], 1
0x18004a8b2  movsxd  rax, dword ptr [rcx+78h]
0x18004a8b6  imul    r15, rax, 68h ; 'h'
0x18004a8ba  add     r15, [rcx+70h]
0x18004a8be  mov     rdx, r15; struct CDSLProviderInformation *
0x18004a8c1  call    ?OnTrackSavePassword@CDSLObject@@QEAAJAEAVCDSLProviderInformation@@@Z; CDSLObject::OnTrackSavePassword(CDSLProviderInformation &)
0x18004a8c6  test    eax, eax
0x18004a8c8  js      loc_18004ADC5
0x18004a8ce  mov     dword ptr [rsp+2898h+Buffer], edi
0x18004a8d5  xor     edx, edx; Val
0x18004a8d7  mov     r8d, 1FFCh; Size
0x18004a8dd  lea     rcx, [rsp+2898h+var_2024]; void *
0x18004a8e5  call    memset_0
0x18004a8ea  mov     r9d, 200h; cchBufferMax
0x18004a8f0  lea     r8, [rsp+2898h+Buffer]; lpBuffer
0x18004a8f8  mov     edx, 0Ah; uID
0x18004a8fd  mov     rcx, cs:hInstance; hInstance
0x18004a904  call    cs:__imp_LoadStringW
0x18004a90a  lea     rdx, [rsp+2898h+Buffer]; unsigned __int16 *
0x18004a912  mov     rcx, r15; this
0x18004a915  call    ?Apply@CDSLProviderInformation@@QEAAJPEAGK@Z; CDSLProviderInformation::Apply(ushort *,ulong)
0x18004a91a  mov     ebx, eax
0x18004a91c  mov     [rsp+2898h+var_2868], eax
0x18004a920  test    eax, eax
0x18004a922  js      short loc_18004A92B
0x18004a924  cmp     eax, 40EDAh
0x18004a929  jnz     short loc_18004A9A6
0x18004a92b  test    byte ptr cs:_bidGblFlags, 2
0x18004a932  jz      short loc_18004A948
0x18004a934  mov     r8d, 1E0h; unsigned int
0x18004a93a  lea     rdx, aCdslobjectAppl; "<CDSLObject::ApplyPropertySheet|OLEDB|E"...
0x18004a941  mov     ecx, ebx; int
0x18004a943  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004a948  mov     [rsp+2898h+Caption], di
0x18004a94d  xor     edx, edx; Val
0x18004a94f  mov     r8d, 3FEh; Size
0x18004a955  lea     rcx, [rsp+2898h+var_2826]; void *
0x18004a95a  call    memset_0
0x18004a95f  mov     r9d, 200h; cchBufferMax
0x18004a965  lea     r8, [rsp+2898h+Caption]; lpBuffer
0x18004a96a  mov     edx, 5Eh ; '^'; uID
0x18004a96f  mov     rcx, cs:hInstance; hInstance
0x18004a976  call    cs:__imp_LoadStringW
0x18004a97c  mov     r9d, 11h; uType
0x18004a982  lea     r8, [rsp+2898h+Caption]; lpCaption
0x18004a987  lea     rdx, [rsp+2898h+Buffer]; lpText
0x18004a98f  mov     rcx, [r12]; hWnd
0x18004a993  call    cs:__imp_MessageBoxW
0x18004a999  cmp     eax, 1
0x18004a99c  jnz     loc_18004AD98
0x18004a9a2  mov     [rsp+2898h+var_2868], edi
0x18004a9a6  mov     r8, [rsi+3E0h]
0x18004a9ad  mov     rcx, [r8]
0x18004a9b0  test    rcx, rcx
0x18004a9b3  jz      loc_18004ABE3
0x18004a9b9  mov     [rsp+2898h+var_2860], rdi
0x18004a9be  mov     rax, [rcx]
0x18004a9c1  lea     r8, [rsp+2898h+var_2860]
0x18004a9c6  lea     rdx, IID_IDBProperties
0x18004a9cd  mov     rax, [rax]
0x18004a9d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a9d5  mov     [rsp+2898h+var_2868], eax
0x18004a9d9  test    eax, eax
0x18004a9db  jns     short loc_18004A9F2
0x18004a9dd  mov     [rsp+2898h+pExceptionObject], eax
0x18004a9e1  lea     rdx, _TI1J; pThrowInfo
0x18004a9e8  lea     rcx, [rsp+2898h+pExceptionObject]; pExceptionObject
0x18004a9ed  call    _CxxThrowException_0
0x18004a9f2  mov     rcx, [rsi+3E0h]
0x18004a9f9  mov     rax, [rsp+2898h+var_2860]
0x18004a9fe  cmp     [r15+60h], rax
0x18004aa02  jz      short loc_18004AA70
0x18004aa04  mov     rcx, [rcx]
0x18004aa07  mov     rax, [rcx]
0x18004aa0a  mov     rax, [rax+10h]
0x18004aa0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa13  mov     rcx, [r15+60h]
0x18004aa17  mov     rax, [rcx]
0x18004aa1a  lea     rdx, [rsi+3D0h]
0x18004aa21  mov     r8, [rsi+3E0h]
0x18004aa28  mov     rax, [rax]
0x18004aa2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa30  mov     ebx, eax
0x18004aa32  mov     [rsp+2898h+var_2868], eax
0x18004aa36  test    eax, eax
0x18004aa38  jns     loc_18004AB01
0x18004aa3e  test    byte ptr cs:_bidGblFlags, 2
0x18004aa45  jz      short loc_18004AA5B
0x18004aa47  mov     r8d, 214h; unsigned int
0x18004aa4d  lea     rdx, aCdslobjectAppl; "<CDSLObject::ApplyPropertySheet|OLEDB|E"...
0x18004aa54  mov     ecx, eax; int
0x18004aa56  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004aa5b  mov     [rsp+2898h+var_284C], ebx
0x18004aa5f  lea     rdx, _TI1J; pThrowInfo
0x18004aa66  lea     rcx, [rsp+2898h+var_284C]; pExceptionObject
0x18004aa6b  call    _CxxThrowException_0
0x18004aa70  mov     [rsp+2898h+var_2858], rdi
0x18004aa75  mov     rcx, [rcx]
0x18004aa78  mov     rax, [rcx]
0x18004aa7b  lea     rdx, [rsi+3D0h]
0x18004aa82  lea     r8, [rsp+2898h+var_2858]
0x18004aa87  mov     rax, [rax]
0x18004aa8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa8f  mov     ebx, eax
0x18004aa91  mov     [rsp+2898h+var_2868], eax
0x18004aa95  test    eax, eax
0x18004aa97  jns     short loc_18004AADC
0x18004aa99  test    byte ptr cs:_bidGblFlags, 2
0x18004aaa0  jz      short loc_18004AAB6
0x18004aaa2  mov     r8d, 222h; unsigned int
0x18004aaa8  lea     rdx, aCdslobjectAppl; "<CDSLObject::ApplyPropertySheet|OLEDB|E"...
0x18004aaaf  mov     ecx, eax; int
0x18004aab1  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004aab6  mov     rcx, [rsp+2898h+var_2860]
0x18004aabb  mov     rax, [rcx]
0x18004aabe  mov     rax, [rax+10h]
0x18004aac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aac7  mov     [rsp+2898h+var_2848], ebx
0x18004aacb  lea     rdx, _TI1J; pThrowInfo
0x18004aad2  lea     rcx, [rsp+2898h+var_2848]; pExceptionObject
0x18004aad7  call    _CxxThrowException_0
0x18004aadc  mov     rax, [rsi+3E0h]
0x18004aae3  mov     rcx, [rax]
0x18004aae6  mov     rax, [rcx]
0x18004aae9  mov     rax, [rax+10h]
0x18004aaed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aaf2  mov     rcx, [rsi+3E0h]
0x18004aaf9  mov     rax, [rsp+2898h+var_2858]
0x18004aafe  mov     [rcx], rax
0x18004ab01  mov     rcx, [rsp+2898h+var_2860]
0x18004ab06  mov     rax, [rcx]
0x18004ab09  mov     rax, [rax+10h]
0x18004ab0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ab12  cmp     [rsi+410h], rdi
0x18004ab19  jz      loc_18004ACC8
0x18004ab1f  mov     [rsp+2898h+var_2860], rdi
0x18004ab24  mov     [rsp+2898h+var_2858], rdi
0x18004ab29  cmp     [r15+58h], dil
0x18004ab2d  jz      loc_18004AC5A
0x18004ab33  lea     r8, [rsp+2898h+var_2858]; unsigned __int16 **
0x18004ab38  mov     dl, 1; unsigned __int8
0x18004ab3a  mov     rcx, [r15+60h]; struct IUnknown *
0x18004ab3e  call    ?GetInitializationString@@YAJPEAUIUnknown@@EPEAPEAG@Z; GetInitializationString(IUnknown *,uchar,ushort * *)
0x18004ab43  mov     ebx, eax
0x18004ab45  test    eax, eax
0x18004ab47  js      loc_18004AC5F
0x18004ab4d  lea     rax, [rsp+2898h+var_2860]
0x18004ab52  mov     [rsp+2898h+ppv], rax; ppv
0x18004ab57  lea     r9, IID_IDataInitialize; riid
0x18004ab5e  xor     edx, edx; pUnkOuter
0x18004ab60  lea     r8d, [rdx+1]; dwClsContext
0x18004ab64  lea     rcx, CLSID_MSDAINITIALIZE; rclsid
0x18004ab6b  call    cs:__imp_CoCreateInstance
0x18004ab71  mov     ebx, eax
0x18004ab73  mov     [rsp+2898h+var_2868], eax
0x18004ab77  test    eax, eax
0x18004ab79  js      loc_18004AC3A
0x18004ab7f  mov     rcx, [rsp+2898h+var_2860]
0x18004ab84  mov     rax, [rcx]
0x18004ab87  mov     r9d, 4
0x18004ab8d  mov     r8, [rsp+2898h+var_2858]
0x18004ab92  mov     rdx, [rsi+410h]
0x18004ab99  mov     rax, [rax+40h]
0x18004ab9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aba2  mov     ebx, eax
0x18004aba4  mov     [rsp+2898h+var_2868], eax
0x18004aba8  test    eax, eax
0x18004abaa  jns     loc_18004AC58
0x18004abb0  test    byte ptr cs:_bidGblFlags, 2
0x18004abb7  jz      short loc_18004ABCD
0x18004abb9  mov     r8d, 252h; unsigned int
0x18004abbf  lea     rdx, aCdslobjectAppl; "<CDSLObject::ApplyPropertySheet|OLEDB|E"...
0x18004abc6  mov     ecx, eax; int
0x18004abc8  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004abcd  mov     [rsp+2898h+var_2840], ebx
0x18004abd1  lea     rdx, _TI1J; pThrowInfo
0x18004abd8  lea     rcx, [rsp+2898h+var_2840]; pExceptionObject
0x18004abdd  call    _CxxThrowException_0
0x18004abe3  mov     rcx, [r15+60h]
0x18004abe7  mov     rax, [rcx]
0x18004abea  lea     rdx, [rsi+3D0h]
0x18004abf1  mov     rax, [rax]
0x18004abf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004abf9  mov     ebx, eax
0x18004abfb  mov     [rsp+2898h+var_2868], eax
0x18004abff  test    eax, eax
0x18004ac01  jns     loc_18004AB12
0x18004ac07  test    byte ptr cs:_bidGblFlags, 2
0x18004ac0e  jz      short loc_18004AC24
0x18004ac10  mov     r8d, 231h; unsigned int
0x18004ac16  lea     rdx, aCdslobjectAppl; "<CDSLObject::ApplyPropertySheet|OLEDB|E"...
0x18004ac1d  mov     ecx, eax; int
0x18004ac1f  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004ac24  mov     [rsp+2898h+var_2844], ebx
0x18004ac28  lea     rdx, _TI1J; pThrowInfo
0x18004ac2f  lea     rcx, [rsp+2898h+var_2844]; pExceptionObject
0x18004ac34  call    _CxxThrowException_0
0x18004ac3a  test    byte ptr cs:_bidGblFlags, 2
0x18004ac41  jz      short loc_18004AC58
0x18004ac43  mov     r8d, 258h; unsigned int
0x18004ac49  lea     rdx, aCdslobjectAppl; "<CDSLObject::ApplyPropertySheet|OLEDB|E"...
0x18004ac50  mov     ecx, eax; int
0x18004ac52  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004ac57  nop
0x18004ac58  jmp     short loc_18004ACA1
0x18004ac5a  mov     ebx, 80004005h
0x18004ac5f  mov     [rsp+2898h+var_2868], ebx
0x18004ac63  test    byte ptr cs:_bidGblFlags, 2
0x18004ac6a  jz      short loc_18004AC80
0x18004ac6c  mov     r8d, 242h; unsigned int
0x18004ac72  lea     rdx, aCdslobjectAppl; "<CDSLObject::ApplyPropertySheet|OLEDB|E"...
0x18004ac79  mov     ecx, ebx; int
0x18004ac7b  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004ac80  mov     [rsp+2898h+var_283C], ebx
0x18004ac84  lea     rdx, _TI1J; pThrowInfo
0x18004ac8b  lea     rcx, [rsp+2898h+var_283C]; pExceptionObject
0x18004ac90  call    _CxxThrowException_0
0x18004ac96  xor     edi, edi
0x18004ac98  mov     ebx, [rsp+2898h+var_2868]
0x18004ac9c  mov     r12, [rsp+2898h+var_2838]
0x18004aca1  mov     rcx, [rsp+2898h+var_2860]
0x18004aca6  test    rcx, rcx
0x18004aca9  jz      short loc_18004ACBC
0x18004acab  mov     rax, [rcx]
0x18004acae  mov     rax, [rax+10h]
0x18004acb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004acb7  mov     [rsp+2898h+var_2860], rdi
0x18004acbc  mov     rcx, [rsp+2898h+var_2858]
0x18004acc1  call    cs:__imp_mpFree
0x18004acc7  nop
0x18004acc8  jmp     short loc_18004ACD5
0x18004acca  xor     edi, edi
0x18004accc  mov     ebx, [rsp+2898h+var_2868]
0x18004acd0  mov     r12, [rsp+2898h+var_2838]
0x18004acd5  test    ebx, ebx
0x18004acd7  jns     loc_18004AD94
0x18004acdd  cmp     ebx, 80004002h
0x18004ace3  jz      loc_18004AD94
0x18004ace9  test    byte ptr cs:_bidGblFlags, 2
0x18004acf0  jz      short loc_18004AD06
0x18004acf2  mov     r8d, 26Fh; unsigned int
0x18004acf8  lea     rdx, aCdslobjectAppl; "<CDSLObject::ApplyPropertySheet|OLEDB|E"...
0x18004acff  mov     ecx, ebx; int
0x18004ad01  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004ad06  mov     [rsp+2898h+Caption], di
0x18004ad0b  xor     edx, edx; Val
0x18004ad0d  mov     r8d, 3FEh; Size
0x18004ad13  lea     rcx, [rsp+2898h+var_2826]; void *
0x18004ad18  call    memset_0
0x18004ad1d  mov     [rsp+2898h+Text], di
0x18004ad25  xor     edx, edx; Val
0x18004ad27  mov     r8d, 3FEh; Size
0x18004ad2d  lea     rcx, [rsp+2898h+var_2426]; void *
0x18004ad35  call    memset_0
0x18004ad3a  mov     r9d, 200h; cchBufferMax
0x18004ad40  lea     r8, [rsp+2898h+Caption]; lpBuffer
0x18004ad45  mov     edx, 5Eh ; '^'; uID
0x18004ad4a  mov     rcx, cs:hInstance; hInstance
0x18004ad51  call    cs:__imp_LoadStringW
0x18004ad57  mov     r9d, 200h; cchBufferMax
0x18004ad5d  lea     r8, [rsp+2898h+Text]; lpBuffer
0x18004ad65  mov     edx, 0Bh; uID
0x18004ad6a  mov     rcx, cs:hInstance; hInstance
0x18004ad71  call    cs:__imp_LoadStringW
0x18004ad77  mov     r9d, 10h; uType
0x18004ad7d  lea     r8, [rsp+2898h+Caption]; lpCaption
0x18004ad82  lea     rdx, [rsp+2898h+Text]; lpText
0x18004ad8a  mov     rcx, [r12]; hWnd
0x18004ad8e  call    cs:__imp_MessageBoxW
0x18004ad94  mov     eax, ebx
0x18004ad96  jmp     short loc_18004ADCC
0x18004ad98  test    byte ptr cs:_bidGblFlags, 2
0x18004ad9f  jz      short loc_18004ADB5
0x18004ada1  mov     r8d, 1F0h; unsigned int
0x18004ada7  lea     rdx, aCdslobjectAppl; "<CDSLObject::ApplyPropertySheet|OLEDB|E"...
0x18004adae  mov     ecx, ebx; int
0x18004adb0  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004adb5  mov     eax, 80040E4Eh
0x18004adba  cmp     ebx, 40EDAh
0x18004adc0  cmovz   ebx, eax
0x18004adc3  mov     eax, ebx
  ... truncated ...
```
