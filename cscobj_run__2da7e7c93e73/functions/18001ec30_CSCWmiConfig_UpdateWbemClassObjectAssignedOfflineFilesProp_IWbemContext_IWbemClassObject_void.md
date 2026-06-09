# CSCWmiConfig::UpdateWbemClassObjectAssignedOfflineFilesProp(IWbemContext *,IWbemClassObject *,void *)

- ea: `0x18001ec30`
- end: `0x18001ee53`
- name: `?UpdateWbemClassObjectAssignedOfflineFilesProp@CSCWmiConfig@@YAJPEAUIWbemContext@@PEAUIWbemClassObject@@PEAX@Z`
- size: `547`
- prototype: `__int64 __fastcall(CSCWmiConfig *__hidden this, struct IWbemContext *, struct IWbemClassObject *, void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180022030`

## callees

- `0x1800140c8`
- `0x18001886c`
- `0x18001957c`
- `0x18001c868`
- `0x18001c898`
- `0x18001ca10`
- `0x18001cbf0`
- `0x18001cc7c`
- `0x18001ce64`
- `0x18001d74c`
- `0x18001d8e4`
- `0x18001d954`
- `0x18001d9d8`
- `0x18001da18`
- `0x18001ec30`
- `0x1800296a0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001ec4e`
- `OLEAUT32!__imp_VariantInit` at `0x18001ec4e`
- `OLEAUT32!__imp_VariantClear` at `0x18001eda7`
- `OLEAUT32!__imp_VariantClear` at `0x18001ee25`
- `OLEAUT32!__imp_VariantClear` at `0x18001eda7`
- `OLEAUT32!__imp_VariantClear` at `0x18001ee25`

## pseudocode

```c
__int64 __fastcall CSCWmiConfig::UpdateWbemClassObjectAssignedOfflineFilesProp(
        CSCWmiConfig *this,
        struct IWbemContext *a2,
        struct IWbemClassObject *a3,
        void *a4)
{
  unsigned int v6; // eax
  int i; // ebx
  int LowerBound; // edi
  int v9; // edi
  VARIANTARG *v10; // rax
  char v11; // al
  struct tagSAFEARRAY *v13; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v14[4]; // [rsp+38h] [rbp-38h] BYREF
  int v15; // [rsp+3Ch] [rbp-34h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-30h] BYREF
  VARIANTARG v17; // [rsp+58h] [rbp-18h] BYREF
  CSCWmiConfig *v18; // [rsp+90h] [rbp+20h] BYREF
  __int64 v19; // [rsp+A8h] [rbp+38h] BYREF

  v18 = this;
  VariantInit(&pvarg);
  v6 = CSCWmiConfig::AddSettingAuthorityFlag(1);
  if ( (int)CSCWmiConfig::GetUserStateSettingForWbemClassObject(L"AssignedOfflineFiles", &pvarg, a3, v6) >= 0 )
  {
    if ( pvarg.vt == 8204 )
    {
      ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(&v18, pvarg.llVal);
      ATL::CComSafeArrayBound::`default constructor closure'((ATL::CComSafeArrayBound *)v14);
      v15 = 0;
      ATL::CComSafeArray<unsigned short *,8>::CComSafeArray<unsigned short *,8>(&v13, v14);
      for ( i = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v18);
            i < (unsigned int)ATL::CComSafeArray<unsigned short *,8>::GetCount(&v18);
            ++i )
      {
        if ( !v18 )
          goto LABEL_20;
        LowerBound = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v18);
        if ( i < LowerBound || i > (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v18) )
          goto LABEL_19;
        ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(
          &v19,
          *(_QWORD *)(*((_QWORD *)v18 + 2) + 24LL * (i - LowerBound) + 8));
        if ( !v19 )
LABEL_20:
          ATL::AtlThrowImpl(-2147467259);
        v9 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v19);
        if ( v9 > 0 || (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v19) < 0 )
LABEL_19:
          ATL::AtlThrowImpl(-2147024809);
        ATL::CComSafeArray<unsigned short *,8>::Add(&v13, *(_QWORD *)(v19 + 16) + 8 * (3LL * -v9 + 1));
        ATL::CComSafeArray<unsigned short *,8>::Destroy(&v19);
      }
      v10 = (VARIANTARG *)ATL::CComVariant::CComVariant((ATL::CComVariant *)&v17, v13);
      if ( &pvarg != v10 )
        ATL::CComVariant::InternalCopy(&pvarg, v10);
      VariantClear(&v17);
      ATL::CComSafeArray<unsigned short *,8>::Destroy(&v13);
      ATL::CComSafeArray<unsigned short *,8>::Destroy(&v18);
    }
    v17.vt = 0;
    ATL::CComVariant::InternalCopy(&v17, &pvarg);
    v11 = WmiProp_SetProperty(a2, L"AssignedOfflineFiles", &v17);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
    {
      WPP_SF_SD(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        81,
        (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
        (unsigned int)L"AssignedOfflineFiles",
        v11);
    }
  }
  VariantClear(&pvarg);
  return 0;
}

```

## disassembly

```asm
0x18001ec30  mov     [rsp-18h+arg_8], rbx
0x18001ec35  mov     [rsp-18h+arg_0], rcx
0x18001ec3a  push    rbp
0x18001ec3b  push    rsi
0x18001ec3c  push    rdi
0x18001ec3d  mov     rbp, rsp
0x18001ec40  sub     rsp, 70h
0x18001ec44  lea     rcx, [rbp+pvarg]; pvarg
0x18001ec48  mov     rbx, r8
0x18001ec4b  mov     rsi, rdx
0x18001ec4e  call    cs:__imp_VariantInit
0x18001ec54  mov     ecx, 1
0x18001ec59  call    ?AddSettingAuthorityFlag@CSCWmiConfig@@YA?AW4USERSTATE_SETTING_SOURCES@@W42@@Z; CSCWmiConfig::AddSettingAuthorityFlag(USERSTATE_SETTING_SOURCES)
0x18001ec5e  mov     r9d, eax
0x18001ec61  lea     rdx, [rbp+pvarg]
0x18001ec65  mov     r8, rbx
0x18001ec68  lea     rcx, CSCWMI_STR_PROP_ASSIGNEDOFFLINEFILES; "AssignedOfflineFiles"
0x18001ec6f  call    ?GetUserStateSettingForWbemClassObject@CSCWmiConfig@@YAJPEBGAEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::GetUserStateSettingForWbemClassObject(ushort const *,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES)
0x18001ec74  test    eax, eax
0x18001ec76  js      loc_18001EE21
0x18001ec7c  mov     eax, 200Ch
0x18001ec81  cmp     word ptr [rbp+pvarg], ax
0x18001ec85  jnz     loc_18001EDBF
0x18001ec8b  mov     rdx, qword ptr [rbp+pvarg+8]
0x18001ec8f  lea     rcx, [rbp+arg_0]
0x18001ec93  call    ??0?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(tagSAFEARRAY const *)
0x18001ec98  lea     rcx, [rbp+var_38]; this
0x18001ec9c  call    ??_FCComSafeArrayBound@ATL@@QEAAXXZ; ATL::CComSafeArrayBound::`default constructor closure'(void)
0x18001eca1  lea     rdx, [rbp+var_38]
0x18001eca5  mov     [rbp+var_34], 0
0x18001ecac  lea     rcx, [rbp+var_40]
0x18001ecb0  call    ??0?$CComSafeArray@PEAG$07@ATL@@QEAA@PEBUtagSAFEARRAYBOUND@@I@Z; ATL::CComSafeArray<ushort *,8>::CComSafeArray<ushort *,8>(tagSAFEARRAYBOUND const *,uint)
0x18001ecb5  lea     rcx, [rbp+arg_0]
0x18001ecb9  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001ecbe  mov     ebx, eax
0x18001ecc0  jmp     loc_18001ED70
0x18001ecc5  cmp     [rbp+arg_0], 0
0x18001ecca  jz      loc_18001EE48
0x18001ecd0  lea     rcx, [rbp+arg_0]
0x18001ecd4  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001ecd9  mov     edi, eax
0x18001ecdb  cmp     ebx, eax
0x18001ecdd  jl      loc_18001EE3D
0x18001ece3  lea     rcx, [rbp+arg_0]
0x18001ece7  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18001ecec  cmp     ebx, eax
0x18001ecee  jg      loc_18001EE3D
0x18001ecf4  mov     eax, ebx
0x18001ecf6  sub     eax, edi
0x18001ecf8  cdqe
0x18001ecfa  lea     rcx, [rax+rax*2]
0x18001ecfe  mov     rax, [rbp+arg_0]
0x18001ed02  mov     rdx, [rax+10h]
0x18001ed06  mov     rdx, [rdx+rcx*8+8]
0x18001ed0b  lea     rcx, [rbp+arg_18]
0x18001ed0f  call    ??0?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(tagSAFEARRAY const *)
0x18001ed14  cmp     [rbp+arg_18], 0
0x18001ed19  jz      loc_18001EE48
0x18001ed1f  lea     rcx, [rbp+arg_18]
0x18001ed23  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001ed28  mov     edi, eax
0x18001ed2a  test    eax, eax
0x18001ed2c  jg      loc_18001EE3D
0x18001ed32  lea     rcx, [rbp+arg_18]
0x18001ed36  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18001ed3b  test    eax, eax
0x18001ed3d  js      loc_18001EE3D
0x18001ed43  neg     edi
0x18001ed45  movsxd  rax, edi
0x18001ed48  lea     rdx, [rax+rax*2]
0x18001ed4c  mov     rax, [rbp+arg_18]
0x18001ed50  lea     rdx, [rdx+1]
0x18001ed54  mov     rcx, [rax+10h]
0x18001ed58  lea     rdx, [rcx+rdx*8]
0x18001ed5c  lea     rcx, [rbp+var_40]
0x18001ed60  call    ?Add@?$CComSafeArray@PEAG$07@ATL@@QEAAJAEBQEAGH@Z; ATL::CComSafeArray<ushort *,8>::Add(ushort * const &,int)
0x18001ed65  lea     rcx, [rbp+arg_18]
0x18001ed69  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x18001ed6e  inc     ebx
0x18001ed70  lea     rcx, [rbp+arg_0]
0x18001ed74  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x18001ed79  cmp     ebx, eax
0x18001ed7b  jb      loc_18001ECC5
0x18001ed81  mov     rdx, [rbp+var_40]; struct tagSAFEARRAY *
0x18001ed85  lea     rcx, [rbp+var_18]; this
0x18001ed89  call    ??0CComVariant@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComVariant::CComVariant(tagSAFEARRAY const *)
0x18001ed8e  lea     rcx, [rbp+pvarg]
0x18001ed92  cmp     rcx, rax
0x18001ed95  jz      short loc_18001EDA3
0x18001ed97  mov     rdx, rax; struct tagVARIANT *
0x18001ed9a  lea     rcx, [rbp+pvarg]; this
0x18001ed9e  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x18001eda3  lea     rcx, [rbp+var_18]; pvarg
0x18001eda7  call    cs:__imp_VariantClear
0x18001edad  lea     rcx, [rbp+var_40]
0x18001edb1  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x18001edb6  lea     rcx, [rbp+arg_0]
0x18001edba  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x18001edbf  xor     eax, eax
0x18001edc1  lea     rdx, [rbp+pvarg]; struct tagVARIANT *
0x18001edc5  lea     rcx, [rbp+var_18]; this
0x18001edc9  mov     word ptr [rbp+var_18], ax
0x18001edcd  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x18001edd2  lea     r8, [rbp+var_18]
0x18001edd6  mov     rcx, rsi
0x18001edd9  lea     rdx, CSCWMI_STR_PROP_ASSIGNEDOFFLINEFILES; "AssignedOfflineFiles"
0x18001ede0  call    ?WmiProp_SetProperty@@YAJPEAUIWbemClassObject@@PEBGVCComVariant@ATL@@@Z; WmiProp_SetProperty(IWbemClassObject *,ushort const *,ATL::CComVariant)
0x18001ede5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001edec  lea     rdx, WPP_GLOBAL_Control
0x18001edf3  cmp     rcx, rdx
0x18001edf6  jz      short loc_18001EE21
0x18001edf8  test    dword ptr [rcx+1Ch], 4000000h
0x18001edff  jz      short loc_18001EE21
0x18001ee01  mov     rcx, [rcx+10h]
0x18001ee05  lea     r9, CSCWMI_STR_PROP_ASSIGNEDOFFLINEFILES; "AssignedOfflineFiles"
0x18001ee0c  mov     edx, 51h ; 'Q'
0x18001ee11  mov     [rsp+70h+var_50], eax
0x18001ee15  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18001ee1c  call    WPP_SF_SD
0x18001ee21  lea     rcx, [rbp+pvarg]; pvarg
0x18001ee25  call    cs:__imp_VariantClear
0x18001ee2b  mov     rbx, [rsp+70h+arg_8]
0x18001ee33  xor     eax, eax
0x18001ee35  add     rsp, 70h
0x18001ee39  pop     rdi
0x18001ee3a  pop     rsi
0x18001ee3b  pop     rbp
0x18001ee3c  retn
0x18001ee3d  mov     ecx, 80070057h; int
0x18001ee42  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001ee48  mov     ecx, 80004005h; int
0x18001ee4d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
