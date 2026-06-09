# CreateConnectionAndPropertyInstances(IWbemServices *,_GUID *,uchar,ushort const *,IWbemClassObject * *,IWbemClassObject * *)

- ea: `0x18002886c`
- end: `0x180028c40`
- name: `?CreateConnectionAndPropertyInstances@@YAJPEAUIWbemServices@@PEAU_GUID@@EPEBGPEAPEAUIWbemClassObject@@3@Z`
- size: `980`
- prototype: `__int64 __fastcall(struct IWbemServices *, IID *rclsid, unsigned __int8, OLECHAR *psz, struct IWbemClassObject **, struct IWbemClassObject **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000ebb0`
- `0x180014bc0`

## callees

- `0x18002886c`
- `0x180028c48`
- `0x180029a3c`
- `0x18002a61c`
- `0x18002a7d4`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800288ef`
- `OLEAUT32!__imp_SysAllocString` at `0x180028950`
- `OLEAUT32!__imp_SysAllocString` at `0x1800288ef`
- `OLEAUT32!__imp_SysAllocString` at `0x180028950`
- `OLEAUT32!__imp_SysFreeString` at `0x180028a3f`
- `OLEAUT32!__imp_SysFreeString` at `0x180028bbd`
- `OLEAUT32!__imp_SysFreeString` at `0x180028c0d`
- `OLEAUT32!__imp_SysFreeString` at `0x180028a3f`
- `OLEAUT32!__imp_SysFreeString` at `0x180028bbd`
- `OLEAUT32!__imp_SysFreeString` at `0x180028c0d`
- `OLEAUT32!__imp_VariantClear` at `0x18002892c`
- `OLEAUT32!__imp_VariantClear` at `0x18002898c`
- `OLEAUT32!__imp_VariantClear` at `0x180028ad0`
- `OLEAUT32!__imp_VariantClear` at `0x18002892c`
- `OLEAUT32!__imp_VariantClear` at `0x18002898c`
- `OLEAUT32!__imp_VariantClear` at `0x180028ad0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002893a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002893a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800288d1`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800288d1`

## pseudocode

```c
__int64 __fastcall CreateConnectionAndPropertyInstances(
        struct IWbemServices *a1,
        IID *rclsid,
        unsigned __int8 a3,
        OLECHAR *psz,
        struct IWbemClassObject **a5,
        struct IWbemClassObject **a6)
{
  HRESULT WmiObjectFromPath; // ebx
  bool v11; // sf
  struct IWbemServicesVtbl *lpVtbl; // rax
  bool v13; // sf
  struct IWbemServicesVtbl *v14; // rax
  struct IWbemClassObject *v16; // [rsp+30h] [rbp-48h] BYREF
  struct IWbemClassObject *v17; // [rsp+38h] [rbp-40h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-38h] BYREF
  __int64 v19; // [rsp+48h] [rbp-30h] BYREF
  LPOLESTR lpsz; // [rsp+50h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-20h] BYREF

  bstrString = 0;
  v16 = 0;
  v17 = 0;
  v19 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  WmiObjectFromPath = SpawnNewInstance(a1, L"HNet_Connection", &v16);
  if ( WmiObjectFromPath )
    goto LABEL_32;
  lpsz = 0;
  WmiObjectFromPath = StringFromCLSID(rclsid, &lpsz);
  if ( WmiObjectFromPath )
    goto LABEL_15;
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(lpsz);
  if ( pvarg.llVal )
  {
    WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v16->lpVtbl->Put)(
                          v16,
                          L"Guid",
                          0,
                          &pvarg,
                          0);
    VariantClear(&pvarg);
  }
  else
  {
    WmiObjectFromPath = -2147024882;
  }
  CoTaskMemFree(lpsz);
  v11 = WmiObjectFromPath < 0;
  if ( WmiObjectFromPath )
    goto LABEL_16;
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(psz);
  if ( !pvarg.llVal )
  {
    WmiObjectFromPath = -2147024882;
    goto LABEL_17;
  }
  WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v16->lpVtbl->Put)(
                        v16,
                        L"Name",
                        0,
                        &pvarg,
                        0);
  VariantClear(&pvarg);
  v11 = WmiObjectFromPath < 0;
  if ( WmiObjectFromPath )
  {
LABEL_16:
    if ( !v11 )
      goto LABEL_19;
LABEL_17:
    if ( v16 )
    {
      ((void (__fastcall *)(struct IWbemClassObject *))v16->lpVtbl->Release)(v16);
      v16 = 0;
    }
    goto LABEL_32;
  }
  WmiObjectFromPath = SetBooleanValue(v16, L"IsLanConnection", a3);
  if ( WmiObjectFromPath
    || (lpVtbl = a1->lpVtbl,
        v19 = 0,
        (WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemServices *, struct IWbemClassObject *, __int64, _QWORD, __int64 *))lpVtbl->PutInstance)(
                               a1,
                               v16,
                               16,
                               0,
                               &v19)) != 0) )
  {
LABEL_15:
    v11 = WmiObjectFromPath < 0;
    goto LABEL_16;
  }
  ((void (__fastcall *)(struct IWbemClassObject *))v16->lpVtbl->Release)(v16);
  v16 = 0;
  WmiObjectFromPath = (*(__int64 (__fastcall **)(__int64, __int64, BSTR *))(*(_QWORD *)v19 + 32LL))(
                        v19,
                        0xFFFFFFFFLL,
                        &bstrString);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  v11 = WmiObjectFromPath < 0;
  if ( WmiObjectFromPath )
    goto LABEL_16;
  WmiObjectFromPath = GetWmiObjectFromPath(a1, bstrString, &v16);
  if ( WmiObjectFromPath < 0 )
  {
    SysFreeString(bstrString);
    bstrString = 0;
    goto LABEL_17;
  }
LABEL_19:
  if ( WmiObjectFromPath )
    goto LABEL_32;
  WmiObjectFromPath = SpawnNewInstance(a1, L"HNet_ConnectionProperties", &v17);
  if ( WmiObjectFromPath )
    goto LABEL_32;
  pvarg.llVal = (LONGLONG)bstrString;
  pvarg.vt = 8;
  WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v17->lpVtbl->Put)(
                        v17,
                        L"Connection",
                        0,
                        &pvarg,
                        0);
  VariantClear(&pvarg);
  bstrString = 0;
  v13 = WmiObjectFromPath < 0;
  if ( WmiObjectFromPath )
    goto LABEL_29;
  WmiObjectFromPath = SetBooleanValue(v17, L"IsFirewalled", 1u);
  if ( WmiObjectFromPath )
    goto LABEL_28;
  WmiObjectFromPath = SetBooleanValue(v17, L"IsIcsPublic", 0);
  if ( WmiObjectFromPath )
    goto LABEL_28;
  WmiObjectFromPath = SetBooleanValue(v17, L"IsIcsPrivate", 0);
  if ( WmiObjectFromPath )
    goto LABEL_28;
  v14 = a1->lpVtbl;
  v19 = 0;
  WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemServices *, struct IWbemClassObject *, __int64, _QWORD, __int64 *))v14->PutInstance)(
                        a1,
                        v17,
                        16,
                        0,
                        &v19);
  if ( WmiObjectFromPath )
    goto LABEL_28;
  ((void (__fastcall *)(struct IWbemClassObject *))v17->lpVtbl->Release)(v17);
  v17 = 0;
  WmiObjectFromPath = (*(__int64 (__fastcall **)(__int64, __int64, BSTR *))(*(_QWORD *)v19 + 32LL))(
                        v19,
                        0xFFFFFFFFLL,
                        &bstrString);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  v13 = WmiObjectFromPath < 0;
  if ( !WmiObjectFromPath )
  {
    WmiObjectFromPath = GetWmiObjectFromPath(a1, bstrString, &v17);
    SysFreeString(bstrString);
    bstrString = 0;
LABEL_28:
    v13 = WmiObjectFromPath < 0;
  }
LABEL_29:
  if ( v13 )
  {
    DeleteWmiInstance(a1, v16);
    ((void (__fastcall *)(struct IWbemClassObject *))v16->lpVtbl->Release)(v16);
    v16 = 0;
    if ( v17 )
    {
      ((void (__fastcall *)(struct IWbemClassObject *))v17->lpVtbl->Release)(v17);
      v17 = 0;
    }
  }
LABEL_32:
  if ( bstrString )
    SysFreeString(bstrString);
  if ( !WmiObjectFromPath )
  {
    *a5 = v16;
    *a6 = v17;
  }
  return (unsigned int)WmiObjectFromPath;
}

```

## disassembly

```asm
0x18002886c  push    rbp
0x18002886e  push    rbx
0x18002886f  push    rsi
0x180028870  push    rdi
0x180028871  push    r12
0x180028873  push    r13
0x180028875  push    r14
0x180028877  push    r15
0x180028879  mov     rbp, rsp
0x18002887c  sub     rsp, 78h
0x180028880  xor     r12d, r12d
0x180028883  mov     r15b, r8b
0x180028886  mov     rsi, rdx
0x180028889  mov     [rbp+bstrString], r12
0x18002888d  xorps   xmm0, xmm0
0x180028890  mov     [rbp+var_48], r12
0x180028894  xor     eax, eax
0x180028896  mov     [rbp+var_40], r12
0x18002889a  lea     r8, [rbp+var_48]; struct IWbemClassObject **
0x18002889e  mov     [rbp+var_30], r12
0x1800288a2  lea     rdx, ?c_wszHnetConnection@@3QBGB; "HNet_Connection"
0x1800288a9  mov     qword ptr [rbp+pvarg+10h], rax
0x1800288ad  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800288b1  mov     r14, r9
0x1800288b4  mov     rdi, rcx
0x1800288b7  call    ?SpawnNewInstance@@YAJPEAUIWbemServices@@PEBGPEAPEAUIWbemClassObject@@@Z; SpawnNewInstance(IWbemServices *,ushort const *,IWbemClassObject * *)
0x1800288bc  mov     ebx, eax
0x1800288be  test    eax, eax
0x1800288c0  jnz     loc_180028C04
0x1800288c6  lea     rdx, [rbp+lpsz]; lplpsz
0x1800288ca  mov     [rbp+lpsz], r12
0x1800288ce  mov     rcx, rsi; rclsid
0x1800288d1  call    cs:__imp_StringFromCLSID
0x1800288d7  lea     r13d, [r12+8]
0x1800288dc  mov     ebx, eax
0x1800288de  test    eax, eax
0x1800288e0  jnz     loc_180028A4F
0x1800288e6  mov     rcx, [rbp+lpsz]; psz
0x1800288ea  mov     word ptr [rbp+pvarg], r13w
0x1800288ef  call    cs:__imp_SysAllocString
0x1800288f5  mov     qword ptr [rbp+pvarg+8], rax
0x1800288f9  mov     esi, 8007000Eh
0x1800288fe  test    rax, rax
0x180028901  jz      short loc_180028934
0x180028903  mov     rcx, [rbp+var_48]
0x180028907  lea     r9, [rbp+pvarg]
0x18002890b  xor     r8d, r8d
0x18002890e  mov     dword ptr [rsp+78h+var_58], r12d
0x180028913  lea     rdx, ?c_wszGuid@@3QBGB; "Guid"
0x18002891a  mov     rax, [rcx]
0x18002891d  mov     rax, [rax+28h]
0x180028921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028926  lea     rcx, [rbp+pvarg]; pvarg
0x18002892a  mov     ebx, eax
0x18002892c  call    cs:__imp_VariantClear
0x180028932  jmp     short loc_180028936
0x180028934  mov     ebx, esi
0x180028936  mov     rcx, [rbp+lpsz]; pv
0x18002893a  call    cs:__imp_CoTaskMemFree
0x180028940  test    ebx, ebx
0x180028942  jnz     loc_180028A51
0x180028948  mov     rcx, r14; psz
0x18002894b  mov     word ptr [rbp+pvarg], r13w
0x180028950  call    cs:__imp_SysAllocString
0x180028956  mov     qword ptr [rbp+pvarg+8], rax
0x18002895a  test    rax, rax
0x18002895d  jz      loc_180028A4B
0x180028963  mov     rcx, [rbp+var_48]
0x180028967  lea     r9, [rbp+pvarg]
0x18002896b  xor     r8d, r8d
0x18002896e  mov     dword ptr [rsp+78h+var_58], r12d
0x180028973  lea     rdx, ?c_wszName@@3QBGB; "Name"
0x18002897a  mov     rax, [rcx]
0x18002897d  mov     rax, [rax+28h]
0x180028981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028986  lea     rcx, [rbp+pvarg]; pvarg
0x18002898a  mov     ebx, eax
0x18002898c  call    cs:__imp_VariantClear
0x180028992  test    ebx, ebx
0x180028994  jnz     loc_180028A51
0x18002899a  mov     rcx, [rbp+var_48]; struct IWbemClassObject *
0x18002899e  lea     rdx, ?c_wszIsLanConnection@@3QBGB; "IsLanConnection"
0x1800289a5  mov     r8b, r15b; unsigned __int8
0x1800289a8  call    ?SetBooleanValue@@YAJPEAUIWbemClassObject@@PEBGE@Z; SetBooleanValue(IWbemClassObject *,ushort const *,uchar)
0x1800289ad  mov     ebx, eax
0x1800289af  test    eax, eax
0x1800289b1  jnz     loc_180028A4F
0x1800289b7  mov     rax, [rdi]
0x1800289ba  lea     rcx, [rbp+var_30]
0x1800289be  mov     rdx, [rbp+var_48]
0x1800289c2  lea     r8d, [rbx+10h]
0x1800289c6  mov     [rsp+78h+var_58], rcx
0x1800289cb  xor     r9d, r9d
0x1800289ce  mov     rcx, rdi
0x1800289d1  mov     [rbp+var_30], r12
0x1800289d5  mov     rax, [rax+70h]
0x1800289d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289de  mov     ebx, eax
0x1800289e0  test    eax, eax
0x1800289e2  jnz     short loc_180028A4F
0x1800289e4  mov     rcx, [rbp+var_48]
0x1800289e8  mov     rax, [rcx]
0x1800289eb  mov     rax, [rax+10h]
0x1800289ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289f4  mov     rcx, [rbp+var_30]
0x1800289f8  lea     r8, [rbp+bstrString]
0x1800289fc  mov     [rbp+var_48], r12
0x180028a00  or      edx, 0FFFFFFFFh
0x180028a03  mov     rax, [rcx]
0x180028a06  mov     rax, [rax+20h]
0x180028a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a0f  mov     rcx, [rbp+var_30]
0x180028a13  mov     ebx, eax
0x180028a15  mov     rax, [rcx]
0x180028a18  mov     rax, [rax+10h]
0x180028a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a21  test    ebx, ebx
0x180028a23  jnz     short loc_180028A51
0x180028a25  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x180028a29  lea     r8, [rbp+var_48]; struct IWbemClassObject **
0x180028a2d  mov     rcx, rdi; struct IWbemServices *
0x180028a30  call    ?GetWmiObjectFromPath@@YAJPEAUIWbemServices@@PEAGPEAPEAUIWbemClassObject@@@Z; GetWmiObjectFromPath(IWbemServices *,ushort *,IWbemClassObject * *)
0x180028a35  mov     ebx, eax
0x180028a37  test    eax, eax
0x180028a39  jns     short loc_180028A75
0x180028a3b  mov     rcx, [rbp+bstrString]; bstrString
0x180028a3f  call    cs:__imp_SysFreeString
0x180028a45  mov     [rbp+bstrString], r12
0x180028a49  jmp     short loc_180028A53
0x180028a4b  mov     ebx, esi
0x180028a4d  jmp     short loc_180028A53
0x180028a4f  test    ebx, ebx
0x180028a51  jns     short loc_180028A75
0x180028a53  mov     rcx, [rbp+var_48]
0x180028a57  test    rcx, rcx
0x180028a5a  jz      loc_180028C04
0x180028a60  mov     rax, [rcx]
0x180028a63  mov     rax, [rax+10h]
0x180028a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a6c  mov     [rbp+var_48], r12
0x180028a70  jmp     loc_180028C04
0x180028a75  test    ebx, ebx
0x180028a77  jnz     loc_180028C04
0x180028a7d  lea     r8, [rbp+var_40]; struct IWbemClassObject **
0x180028a81  mov     rcx, rdi; struct IWbemServices *
0x180028a84  lea     rdx, ?c_wszHnetProperties@@3QBGB; "HNet_ConnectionProperties"
0x180028a8b  call    ?SpawnNewInstance@@YAJPEAUIWbemServices@@PEBGPEAPEAUIWbemClassObject@@@Z; SpawnNewInstance(IWbemServices *,ushort const *,IWbemClassObject * *)
0x180028a90  mov     ebx, eax
0x180028a92  test    eax, eax
0x180028a94  jnz     loc_180028C04
0x180028a9a  mov     rax, [rbp+bstrString]
0x180028a9e  lea     r9, [rbp+pvarg]
0x180028aa2  mov     rcx, [rbp+var_40]
0x180028aa6  lea     rdx, ?c_wszConnection@@3QBGB; "Connection"
0x180028aad  mov     qword ptr [rbp+pvarg+8], rax
0x180028ab1  xor     r8d, r8d
0x180028ab4  mov     word ptr [rbp+pvarg], r13w
0x180028ab9  mov     dword ptr [rsp+78h+var_58], r12d
0x180028abe  mov     rax, [rcx]
0x180028ac1  mov     rax, [rax+28h]
0x180028ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028aca  lea     rcx, [rbp+pvarg]; pvarg
0x180028ace  mov     ebx, eax
0x180028ad0  call    cs:__imp_VariantClear
0x180028ad6  mov     [rbp+bstrString], r12
0x180028ada  test    ebx, ebx
0x180028adc  jnz     loc_180028BC9
0x180028ae2  mov     rcx, [rbp+var_40]; struct IWbemClassObject *
0x180028ae6  lea     rdx, ?c_wszIsFirewalled@@3QBGB; "IsFirewalled"
0x180028aed  mov     r8b, 1; unsigned __int8
0x180028af0  call    ?SetBooleanValue@@YAJPEAUIWbemClassObject@@PEBGE@Z; SetBooleanValue(IWbemClassObject *,ushort const *,uchar)
0x180028af5  mov     ebx, eax
0x180028af7  test    eax, eax
0x180028af9  jnz     loc_180028BC7
0x180028aff  mov     rcx, [rbp+var_40]; struct IWbemClassObject *
0x180028b03  lea     rdx, ?c_wszIsIcsPublic@@3QBGB; "IsIcsPublic"
0x180028b0a  xor     r8d, r8d; unsigned __int8
0x180028b0d  call    ?SetBooleanValue@@YAJPEAUIWbemClassObject@@PEBGE@Z; SetBooleanValue(IWbemClassObject *,ushort const *,uchar)
0x180028b12  mov     ebx, eax
0x180028b14  test    eax, eax
0x180028b16  jnz     loc_180028BC7
0x180028b1c  mov     rcx, [rbp+var_40]; struct IWbemClassObject *
0x180028b20  lea     rdx, ?c_wszIsIcsPrivate@@3QBGB; "IsIcsPrivate"
0x180028b27  xor     r8d, r8d; unsigned __int8
0x180028b2a  call    ?SetBooleanValue@@YAJPEAUIWbemClassObject@@PEBGE@Z; SetBooleanValue(IWbemClassObject *,ushort const *,uchar)
0x180028b2f  mov     ebx, eax
0x180028b31  test    eax, eax
0x180028b33  jnz     loc_180028BC7
0x180028b39  mov     rax, [rdi]
0x180028b3c  lea     rcx, [rbp+var_30]
0x180028b40  mov     rdx, [rbp+var_40]
0x180028b44  lea     r8d, [rbx+10h]
0x180028b48  mov     [rsp+78h+var_58], rcx
0x180028b4d  xor     r9d, r9d
0x180028b50  mov     rcx, rdi
0x180028b53  mov     [rbp+var_30], r12
0x180028b57  mov     rax, [rax+70h]
0x180028b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b60  mov     ebx, eax
0x180028b62  test    eax, eax
0x180028b64  jnz     short loc_180028BC7
0x180028b66  mov     rcx, [rbp+var_40]
0x180028b6a  mov     rax, [rcx]
0x180028b6d  mov     rax, [rax+10h]
0x180028b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b76  mov     rcx, [rbp+var_30]
0x180028b7a  lea     r8, [rbp+bstrString]
0x180028b7e  mov     [rbp+var_40], r12
0x180028b82  or      edx, 0FFFFFFFFh
0x180028b85  mov     rax, [rcx]
0x180028b88  mov     rax, [rax+20h]
0x180028b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b91  mov     rcx, [rbp+var_30]
0x180028b95  mov     ebx, eax
0x180028b97  mov     rax, [rcx]
0x180028b9a  mov     rax, [rax+10h]
0x180028b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ba3  test    ebx, ebx
0x180028ba5  jnz     short loc_180028BC9
0x180028ba7  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x180028bab  lea     r8, [rbp+var_40]; struct IWbemClassObject **
0x180028baf  mov     rcx, rdi; struct IWbemServices *
0x180028bb2  call    ?GetWmiObjectFromPath@@YAJPEAUIWbemServices@@PEAGPEAPEAUIWbemClassObject@@@Z; GetWmiObjectFromPath(IWbemServices *,ushort *,IWbemClassObject * *)
0x180028bb7  mov     rcx, [rbp+bstrString]; bstrString
0x180028bbb  mov     ebx, eax
0x180028bbd  call    cs:__imp_SysFreeString
0x180028bc3  mov     [rbp+bstrString], r12
0x180028bc7  test    ebx, ebx
0x180028bc9  jns     short loc_180028C04
0x180028bcb  mov     rdx, [rbp+var_48]; struct IWbemClassObject *
0x180028bcf  mov     rcx, rdi; struct IWbemServices *
0x180028bd2  call    ?DeleteWmiInstance@@YAJPEAUIWbemServices@@PEAUIWbemClassObject@@@Z; DeleteWmiInstance(IWbemServices *,IWbemClassObject *)
0x180028bd7  mov     rcx, [rbp+var_48]
0x180028bdb  mov     rax, [rcx]
0x180028bde  mov     rax, [rax+10h]
0x180028be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028be7  mov     rcx, [rbp+var_40]
0x180028beb  mov     [rbp+var_48], r12
0x180028bef  test    rcx, rcx
0x180028bf2  jz      short loc_180028C04
0x180028bf4  mov     rax, [rcx]
0x180028bf7  mov     rax, [rax+10h]
0x180028bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c00  mov     [rbp+var_40], r12
0x180028c04  mov     rcx, [rbp+bstrString]; bstrString
0x180028c08  test    rcx, rcx
0x180028c0b  jz      short loc_180028C13
0x180028c0d  call    cs:__imp_SysFreeString
0x180028c13  test    ebx, ebx
0x180028c15  jnz     short loc_180028C2D
0x180028c17  mov     rcx, [rbp+arg_20]
0x180028c1b  mov     rax, [rbp+var_48]
0x180028c1f  mov     [rcx], rax
0x180028c22  mov     rcx, [rbp+arg_28]
0x180028c26  mov     rax, [rbp+var_40]
0x180028c2a  mov     [rcx], rax
0x180028c2d  mov     eax, ebx
0x180028c2f  add     rsp, 78h
0x180028c33  pop     r15
0x180028c35  pop     r14
0x180028c37  pop     r13
0x180028c39  pop     r12
0x180028c3b  pop     rdi
0x180028c3c  pop     rsi
0x180028c3d  pop     rbx
0x180028c3e  pop     rbp
0x180028c3f  retn
```
