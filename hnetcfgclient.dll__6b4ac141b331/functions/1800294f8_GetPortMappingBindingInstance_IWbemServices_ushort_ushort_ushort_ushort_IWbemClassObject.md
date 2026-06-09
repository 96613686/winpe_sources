# GetPortMappingBindingInstance(IWbemServices *,ushort *,ushort *,ushort *,ushort,IWbemClassObject * *)

- ea: `0x1800294f8`
- end: `0x1800298ed`
- name: `?GetPortMappingBindingInstance@@YAJPEAUIWbemServices@@PEAG11GPEAPEAUIWbemClassObject@@@Z`
- size: `1013`
- prototype: `__int64 __fastcall(struct IWbemServices *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16, struct IWbemClassObject **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800197b8`
- `0x18001ad60`

## callees

- `0x180027e10`
- `0x180027fc4`
- `0x180028210`
- `0x1800294f8`
- `0x180029a3c`
- `0x18002a61c`
- `0x18002a7d4`
- `0x18002ae64`
- `0x18002f010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180029591`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002959f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800295c5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180029591`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002959f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800295c5`
- `OLEAUT32!__imp_SysAllocString` at `0x18002979c`
- `OLEAUT32!__imp_SysAllocString` at `0x18002979c`
- `OLEAUT32!__imp_SysFreeString` at `0x180029608`
- `OLEAUT32!__imp_SysFreeString` at `0x180029897`
- `OLEAUT32!__imp_SysFreeString` at `0x180029608`
- `OLEAUT32!__imp_SysFreeString` at `0x180029897`
- `OLEAUT32!__imp_VariantClear` at `0x1800297e0`
- `OLEAUT32!__imp_VariantClear` at `0x1800297e0`

## string_xrefs

- `0x180029564`: `Protocol`
- `0x1800296f2`: `Protocol`

## pseudocode

```c
__int64 __fastcall GetPortMappingBindingInstance(
        struct IWbemServices *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 a5,
        struct IWbemClassObject **a6)
{
  unsigned __int16 *v8; // rdi
  unsigned int v10; // r15d
  unsigned int WmiObjectFromPath; // ebx
  const unsigned __int16 *v12; // rdx
  struct IWbemServicesVtbl *lpVtbl; // rax
  struct IEnumWbemClassObject *v14; // rcx
  struct IWbemClassObject *v15; // rcx
  struct IWbemClassObject *v16; // rcx
  struct IWbemClassObject *v17; // rcx
  struct IWbemClassObject *v18; // rcx
  struct IWbemServicesVtbl *v19; // rax
  struct IWbemClassObject *v20; // rdx
  BSTR v21; // rcx
  BSTR bstrString; // [rsp+48h] [rbp-39h] BYREF
  unsigned __int16 *v24; // [rsp+50h] [rbp-31h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-29h] BYREF
  struct IEnumWbemClassObject *v26; // [rsp+70h] [rbp-11h] BYREF
  unsigned __int16 *v27; // [rsp+78h] [rbp-9h] BYREF
  BSTR v28; // [rsp+80h] [rbp-1h] BYREF
  unsigned __int16 *v29; // [rsp+88h] [rbp+7h] BYREF
  unsigned int v30; // [rsp+ECh] [rbp+6Bh]
  unsigned int v31; // [rsp+F4h] [rbp+73h]

  v31 = HIDWORD(a4);
  v30 = HIDWORD(a3);
  v26 = 0;
  bstrString = 0;
  v28 = 0;
  v8 = 0;
  v29 = 0;
  v27 = 0;
  v24 = 0;
  v10 = (unsigned int)a3;
  WmiObjectFromPath = BuildEscapedQuotedEqualsString(&v27, L"Connection", a3);
  if ( !WmiObjectFromPath )
  {
    WmiObjectFromPath = BuildEscapedQuotedEqualsString(&v24, L"Protocol", a4);
    if ( !WmiObjectFromPath )
    {
      WmiObjectFromPath = BuildAndString(&v29, v27, v24);
      operator delete[](v24);
      v8 = v29;
    }
    operator delete[](v27);
    if ( !WmiObjectFromPath )
    {
      WmiObjectFromPath = BuildSelectQueryBstr(&bstrString, v12, L"HNet_ConnectionPortMapping2", v8);
      operator delete[](v8);
      if ( !WmiObjectFromPath )
      {
        lpVtbl = a1->lpVtbl;
        v26 = 0;
        WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemServices *, unsigned __int16 *, BSTR, __int64, _QWORD, struct IEnumWbemClassObject **))lpVtbl->ExecQuery)(
                              a1,
                              a2,
                              bstrString,
                              48,
                              0,
                              &v26);
        SysFreeString(bstrString);
        if ( !WmiObjectFromPath )
        {
          v14 = v26;
          LODWORD(v24) = 0;
          *a6 = 0;
          if ( ((int (__fastcall *)(struct IEnumWbemClassObject *, __int64, __int64, struct IWbemClassObject **, unsigned __int16 **))v14->lpVtbl->Next)(
                 v14,
                 0xFFFFFFFFLL,
                 1,
                 a6,
                 &v24) >= 0
            && (_DWORD)v24 == 1 )
          {
            WmiObjectFromPath = 0;
          }
          else
          {
            WmiObjectFromPath = GetWmiObjectFromPath(a1, a4, a6);
            if ( !WmiObjectFromPath )
            {
              ((void (__fastcall *)(_QWORD))(*a6)->lpVtbl->Release)(*a6);
              *a6 = 0;
              WmiObjectFromPath = SpawnNewInstance(a1, L"HNet_ConnectionPortMapping2", a6);
              if ( !WmiObjectFromPath )
              {
                v15 = *a6;
                *(_QWORD *)&pvarg.vt = 8;
                *(_OWORD *)&pvarg.decVal.Lo32 = __PAIR64__(v30, v10);
                WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v15->lpVtbl->Put)(
                                      v15,
                                      L"Connection",
                                      0,
                                      &pvarg,
                                      0);
                if ( !WmiObjectFromPath )
                {
                  v16 = *a6;
                  pvarg.llVal = __PAIR64__(v31, (unsigned int)a4);
                  WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v16->lpVtbl->Put)(
                                        v16,
                                        L"Protocol",
                                        0,
                                        &pvarg,
                                        0);
                  if ( !WmiObjectFromPath )
                  {
                    WmiObjectFromPath = SetBooleanValue(*a6, L"Enabled", 0);
                    if ( !WmiObjectFromPath )
                    {
                      WmiObjectFromPath = SetBooleanValue(*a6, L"NameActive", 0);
                      if ( !WmiObjectFromPath )
                      {
                        v17 = *a6;
                        pvarg.vt = 3;
                        pvarg.lVal = 0;
                        WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v17->lpVtbl->Put)(
                                              v17,
                                              L"TargetIPAddress",
                                              0,
                                              &pvarg,
                                              0);
                        if ( !WmiObjectFromPath )
                        {
                          pvarg.vt = 8;
                          pvarg.llVal = (LONGLONG)SysAllocString(L" ");
                          if ( pvarg.llVal )
                          {
                            WmiObjectFromPath = ((__int64 (__fastcall *)(_QWORD, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))(*a6)->lpVtbl->Put)(
                                                  *a6,
                                                  L"TargetName",
                                                  0,
                                                  &pvarg,
                                                  0);
                            VariantClear(&pvarg);
                            if ( !WmiObjectFromPath )
                            {
                              v18 = *a6;
                              pvarg.lVal = a5;
                              pvarg.vt = 3;
                              WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v18->lpVtbl->Put)(
                                                    v18,
                                                    L"TargetPort",
                                                    0,
                                                    &pvarg,
                                                    0);
                              if ( !WmiObjectFromPath )
                              {
                                v19 = a1->lpVtbl;
                                v20 = *a6;
                                bstrString = 0;
                                WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemServices *, struct IWbemClassObject *, __int64, _QWORD, BSTR *))v19->PutInstance)(
                                                      a1,
                                                      v20,
                                                      18,
                                                      0,
                                                      &bstrString);
                                if ( !WmiObjectFromPath )
                                {
                                  ((void (__fastcall *)(_QWORD))(*a6)->lpVtbl->Release)(*a6);
                                  v21 = bstrString;
                                  *a6 = 0;
                                  WmiObjectFromPath = (*(__int64 (__fastcall **)(BSTR, __int64, BSTR *))(*(_QWORD *)v21 + 32LL))(
                                                        v21,
                                                        0xFFFFFFFFLL,
                                                        &v28);
                                  if ( !WmiObjectFromPath )
                                  {
                                    WmiObjectFromPath = GetWmiObjectFromPath(a1, v28, a6);
                                    SysFreeString(v28);
                                  }
                                  (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
                                }
                              }
                            }
                          }
                          else
                          {
                            WmiObjectFromPath = -2147024882;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
          ValidateFinishedWCOEnum(a1, v26);
          ((void (__fastcall *)(struct IEnumWbemClassObject *))v26->lpVtbl->Release)(v26);
        }
      }
    }
  }
  return WmiObjectFromPath;
}

```

## disassembly

```asm
0x1800294f8  mov     rax, rsp
0x1800294fb  mov     [rax+8], rbx
0x1800294ff  mov     [rax+20h], r9
0x180029503  mov     [rax+18h], r8
0x180029507  push    rbp
0x180029508  push    rsi
0x180029509  push    rdi
0x18002950a  push    r12
0x18002950c  push    r13
0x18002950e  push    r14
0x180029510  push    r15
0x180029512  lea     rbp, [rax-4Fh]
0x180029516  sub     rsp, 90h
0x18002951d  xor     r13d, r13d
0x180029520  mov     r12, rdx
0x180029523  mov     rsi, rcx
0x180029526  mov     [rbp+47h+var_58], r13
0x18002952a  lea     rdx, ?c_wszConnection@@3QBGB; "Connection"
0x180029531  mov     [rbp+47h+bstrString], r13
0x180029535  lea     rcx, [rbp+47h+var_50]; unsigned __int16 **
0x180029539  mov     [rbp+47h+var_48], r13
0x18002953d  mov     edi, r13d
0x180029540  mov     [rbp+47h+var_40], r13
0x180029544  mov     [rbp+47h+var_50], r13
0x180029548  mov     r14, r9
0x18002954b  mov     [rbp+47h+var_78], r13
0x18002954f  mov     r15, r8
0x180029552  call    ?BuildEscapedQuotedEqualsString@@YAJPEAPEAGPEBG1@Z; BuildEscapedQuotedEqualsString(ushort * *,ushort const *,ushort const *)
0x180029557  mov     ebx, eax
0x180029559  test    eax, eax
0x18002955b  jnz     loc_1800298D0
0x180029561  mov     r8, r14; unsigned __int16 *
0x180029564  lea     rdx, ?c_wszProtocol@@3QBGB; "Protocol"
0x18002956b  lea     rcx, [rbp+47h+var_78]; unsigned __int16 **
0x18002956f  call    ?BuildEscapedQuotedEqualsString@@YAJPEAPEAGPEBG1@Z; BuildEscapedQuotedEqualsString(ushort * *,ushort const *,ushort const *)
0x180029574  mov     ebx, eax
0x180029576  test    eax, eax
0x180029578  jnz     short loc_18002959B
0x18002957a  mov     r8, [rbp+47h+var_78]; unsigned __int16 *
0x18002957e  lea     rcx, [rbp+47h+var_40]; unsigned __int16 **
0x180029582  mov     rdx, [rbp+47h+var_50]; unsigned __int16 *
0x180029586  call    ?BuildAndString@@YAJPEAPEAGPEBG1@Z; BuildAndString(ushort * *,ushort const *,ushort const *)
0x18002958b  mov     rcx, [rbp+47h+var_78]
0x18002958f  mov     ebx, eax
0x180029591  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180029597  mov     rdi, [rbp+47h+var_40]
0x18002959b  mov     rcx, [rbp+47h+var_50]
0x18002959f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800295a5  test    ebx, ebx
0x1800295a7  jnz     loc_1800298D0
0x1800295ad  mov     r9, rdi; unsigned __int16 *
0x1800295b0  lea     r8, ?c_wszHnetConnectionPortMapping@@3QBGB; "HNet_ConnectionPortMapping2"
0x1800295b7  lea     rcx, [rbp+47h+bstrString]; unsigned __int16 **
0x1800295bb  call    ?BuildSelectQueryBstr@@YAJPEAPEAGPEBG11@Z; BuildSelectQueryBstr(ushort * *,ushort const *,ushort const *,ushort const *)
0x1800295c0  mov     rcx, rdi
0x1800295c3  mov     ebx, eax
0x1800295c5  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800295cb  test    ebx, ebx
0x1800295cd  jnz     loc_1800298D0
0x1800295d3  mov     rax, [rsi]
0x1800295d6  lea     rcx, [rbp+47h+var_58]
0x1800295da  mov     r8, [rbp+47h+bstrString]
0x1800295de  lea     r9d, [rbx+30h]
0x1800295e2  mov     [rsp+28h], rcx
0x1800295e7  mov     rdx, r12
0x1800295ea  mov     rcx, rsi
0x1800295ed  mov     [rbp+47h+var_58], r13
0x1800295f1  mov     rax, [rax+0A0h]
0x1800295f8  mov     [rsp+0C0h+var_A0], r13
0x1800295fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029602  mov     rcx, [rbp+47h+bstrString]; bstrString
0x180029606  mov     ebx, eax
0x180029608  call    cs:__imp_SysFreeString
0x18002960e  test    ebx, ebx
0x180029610  jnz     loc_1800298D0
0x180029616  mov     rdi, [rbp+47h+arg_28]
0x18002961a  lea     rdx, [rbp+47h+var_78]
0x18002961e  mov     rcx, [rbp+47h+var_58]
0x180029622  lea     r8d, [rbx+1]
0x180029626  mov     dword ptr [rbp+47h+var_78], r13d
0x18002962a  mov     r9, rdi
0x18002962d  mov     [rsp+0C0h+var_A0], rdx
0x180029632  or      edx, 0FFFFFFFFh
0x180029635  mov     [rdi], r13
0x180029638  mov     rax, [rcx]
0x18002963b  mov     rax, [rax+20h]
0x18002963f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029644  test    eax, eax
0x180029646  js      short loc_180029656
0x180029648  cmp     dword ptr [rbp+47h+var_78], 1
0x18002964c  jnz     short loc_180029656
0x18002964e  mov     ebx, r13d
0x180029651  jmp     loc_1800298B4
0x180029656  mov     r8, rdi; struct IWbemClassObject **
0x180029659  mov     rdx, r14; unsigned __int16 *
0x18002965c  mov     rcx, rsi; struct IWbemServices *
0x18002965f  call    ?GetWmiObjectFromPath@@YAJPEAUIWbemServices@@PEAGPEAPEAUIWbemClassObject@@@Z; GetWmiObjectFromPath(IWbemServices *,ushort *,IWbemClassObject * *)
0x180029664  mov     ebx, eax
0x180029666  test    eax, eax
0x180029668  jnz     loc_1800298B4
0x18002966e  mov     rcx, [rdi]
0x180029671  mov     rax, [rcx]
0x180029674  mov     rax, [rax+10h]
0x180029678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002967d  mov     r8, rdi; struct IWbemClassObject **
0x180029680  mov     [rdi], r13
0x180029683  lea     rdx, ?c_wszHnetConnectionPortMapping@@3QBGB; "HNet_ConnectionPortMapping2"
0x18002968a  mov     rcx, rsi; struct IWbemServices *
0x18002968d  call    ?SpawnNewInstance@@YAJPEAUIWbemServices@@PEBGPEAPEAUIWbemClassObject@@@Z; SpawnNewInstance(IWbemServices *,ushort const *,IWbemClassObject * *)
0x180029692  mov     ebx, eax
0x180029694  test    eax, eax
0x180029696  jnz     loc_1800298B4
0x18002969c  mov     rcx, [rdi]
0x18002969f  lea     r12d, [rbx+8]
0x1800296a3  xor     eax, eax
0x1800296a5  mov     dword ptr [rsp+0C0h+var_A0], r13d
0x1800296aa  mov     qword ptr [rbp+47h+pvarg+10h], rax
0x1800296ae  lea     r9, [rbp+47h+pvarg]
0x1800296b2  mov     eax, [rbp+47h+arg_14]
0x1800296b5  lea     rdx, ?c_wszConnection@@3QBGB; "Connection"
0x1800296bc  xorps   xmm0, xmm0
0x1800296bf  xor     r8d, r8d
0x1800296c2  movups  xmmword ptr [rbp+47h+pvarg], xmm0
0x1800296c6  mov     dword ptr [rbp+47h+pvarg+0Ch], eax
0x1800296c9  mov     word ptr [rbp+47h+pvarg], r12w
0x1800296ce  mov     dword ptr [rbp+47h+pvarg+8], r15d
0x1800296d2  mov     rax, [rcx]
0x1800296d5  mov     rax, [rax+28h]
0x1800296d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296de  mov     ebx, eax
0x1800296e0  test    eax, eax
0x1800296e2  jnz     loc_1800298B4
0x1800296e8  mov     rcx, [rdi]
0x1800296eb  lea     r9, [rbp+47h+pvarg]
0x1800296ef  mov     eax, [rbp+47h+arg_1C]
0x1800296f2  lea     rdx, ?c_wszProtocol@@3QBGB; "Protocol"
0x1800296f9  mov     dword ptr [rbp+47h+pvarg+0Ch], eax
0x1800296fc  xor     r8d, r8d
0x1800296ff  mov     dword ptr [rbp+47h+pvarg+8], r14d
0x180029703  mov     rax, [rcx]
0x180029706  mov     dword ptr [rsp+0C0h+var_A0], r13d
0x18002970b  mov     rax, [rax+28h]
0x18002970f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029714  mov     ebx, eax
0x180029716  test    eax, eax
0x180029718  jnz     loc_1800298B4
0x18002971e  mov     rcx, [rdi]; struct IWbemClassObject *
0x180029721  lea     rdx, ?c_wszEnabled@@3QBGB; "Enabled"
0x180029728  xor     r8d, r8d; unsigned __int8
0x18002972b  call    ?SetBooleanValue@@YAJPEAUIWbemClassObject@@PEBGE@Z; SetBooleanValue(IWbemClassObject *,ushort const *,uchar)
0x180029730  mov     ebx, eax
0x180029732  test    eax, eax
0x180029734  jnz     loc_1800298B4
0x18002973a  mov     rcx, [rdi]; struct IWbemClassObject *
0x18002973d  lea     rdx, ?c_wszNameActive@@3QBGB; "NameActive"
0x180029744  xor     r8d, r8d; unsigned __int8
0x180029747  call    ?SetBooleanValue@@YAJPEAUIWbemClassObject@@PEBGE@Z; SetBooleanValue(IWbemClassObject *,ushort const *,uchar)
0x18002974c  mov     ebx, eax
0x18002974e  test    eax, eax
0x180029750  jnz     loc_1800298B4
0x180029756  mov     rcx, [rdi]
0x180029759  lea     r14d, [r12-5]
0x18002975e  mov     word ptr [rbp+47h+pvarg], r14w
0x180029763  lea     r9, [rbp+47h+pvarg]
0x180029767  mov     dword ptr [rbp+47h+pvarg+8], r13d
0x18002976b  lea     rdx, ?c_wszTargetIPAddress@@3QBGB; "TargetIPAddress"
0x180029772  xor     r8d, r8d
0x180029775  mov     dword ptr [rsp+0C0h+var_A0], r13d
0x18002977a  mov     rax, [rcx]
0x18002977d  mov     rax, [rax+28h]
0x180029781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029786  mov     ebx, eax
0x180029788  test    eax, eax
0x18002978a  jnz     loc_1800298B4
0x180029790  lea     rcx, asc_18003597C; " "
0x180029797  mov     word ptr [rbp+47h+pvarg], r12w
0x18002979c  call    cs:__imp_SysAllocString
0x1800297a2  mov     rcx, rax
0x1800297a5  mov     dword ptr [rbp+47h+pvarg+8], eax
0x1800297a8  sar     rcx, 20h
0x1800297ac  mov     dword ptr [rbp+47h+pvarg+0Ch], ecx
0x1800297af  test    rax, rax
0x1800297b2  jz      loc_1800298AF
0x1800297b8  mov     rcx, [rdi]
0x1800297bb  lea     r9, [rbp+47h+pvarg]
0x1800297bf  xor     r8d, r8d
0x1800297c2  mov     dword ptr [rsp+0C0h+var_A0], r13d
0x1800297c7  lea     rdx, ?c_wszTargetName@@3QBGB; "TargetName"
0x1800297ce  mov     rax, [rcx]
0x1800297d1  mov     rax, [rax+28h]
0x1800297d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297da  lea     rcx, [rbp+47h+pvarg]; pvarg
0x1800297de  mov     ebx, eax
0x1800297e0  call    cs:__imp_VariantClear
0x1800297e6  test    ebx, ebx
0x1800297e8  jnz     loc_1800298B4
0x1800297ee  mov     rcx, [rdi]
0x1800297f1  lea     r9, [rbp+47h+pvarg]
0x1800297f5  movzx   eax, [rbp+47h+arg_20]
0x1800297f9  lea     rdx, ?c_wszTargetPort@@3QBGB; "TargetPort"
0x180029800  mov     dword ptr [rbp+47h+pvarg+8], eax
0x180029803  xor     r8d, r8d
0x180029806  mov     word ptr [rbp+47h+pvarg], r14w
0x18002980b  mov     rax, [rcx]
0x18002980e  mov     dword ptr [rsp+0C0h+var_A0], r13d
0x180029813  mov     rax, [rax+28h]
0x180029817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002981c  mov     ebx, eax
0x18002981e  test    eax, eax
0x180029820  jnz     loc_1800298B4
0x180029826  mov     rax, [rsi]
0x180029829  lea     rcx, [rbp+47h+bstrString]
0x18002982d  mov     rdx, [rdi]
0x180029830  lea     r8d, [r12+0Ah]
0x180029835  mov     [rsp+0C0h+var_A0], rcx
0x18002983a  xor     r9d, r9d
0x18002983d  mov     rcx, rsi
0x180029840  mov     [rbp+47h+bstrString], r13
0x180029844  mov     rax, [rax+70h]
0x180029848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002984d  mov     ebx, eax
0x18002984f  test    eax, eax
0x180029851  jnz     short loc_1800298B4
0x180029853  mov     rcx, [rdi]
0x180029856  mov     rax, [rcx]
0x180029859  mov     rax, [rax+10h]
0x18002985d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029862  mov     rcx, [rbp+47h+bstrString]
0x180029866  lea     r8, [rbp+47h+var_48]
0x18002986a  mov     [rdi], r13
0x18002986d  or      edx, 0FFFFFFFFh
0x180029870  mov     rax, [rcx]
0x180029873  mov     rax, [rax+20h]
0x180029877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002987c  mov     ebx, eax
0x18002987e  test    eax, eax
0x180029880  jnz     short loc_18002989D
0x180029882  mov     rdx, [rbp+47h+var_48]; unsigned __int16 *
0x180029886  mov     r8, rdi; struct IWbemClassObject **
0x180029889  mov     rcx, rsi; struct IWbemServices *
0x18002988c  call    ?GetWmiObjectFromPath@@YAJPEAUIWbemServices@@PEAGPEAPEAUIWbemClassObject@@@Z; GetWmiObjectFromPath(IWbemServices *,ushort *,IWbemClassObject * *)
0x180029891  mov     rcx, [rbp+47h+var_48]; bstrString
0x180029895  mov     ebx, eax
0x180029897  call    cs:__imp_SysFreeString
0x18002989d  mov     rcx, [rbp+47h+bstrString]
0x1800298a1  mov     rax, [rcx]
0x1800298a4  mov     rax, [rax+10h]
0x1800298a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298ad  jmp     short loc_1800298B4
0x1800298af  mov     ebx, 8007000Eh
0x1800298b4  mov     rdx, [rbp+47h+var_58]; struct IEnumWbemClassObject *
0x1800298b8  mov     rcx, rsi; struct IWbemServices *
0x1800298bb  call    ?ValidateFinishedWCOEnum@@YAXPEAUIWbemServices@@PEAUIEnumWbemClassObject@@@Z; ValidateFinishedWCOEnum(IWbemServices *,IEnumWbemClassObject *)
0x1800298c0  mov     rcx, [rbp+47h+var_58]
0x1800298c4  mov     rax, [rcx]
0x1800298c7  mov     rax, [rax+10h]
0x1800298cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298d0  mov     eax, ebx
0x1800298d2  mov     rbx, [rsp+0C0h+arg_0]
0x1800298da  add     rsp, 90h
0x1800298e1  pop     r15
0x1800298e3  pop     r14
0x1800298e5  pop     r13
0x1800298e7  pop     r12
0x1800298e9  pop     rdi
0x1800298ea  pop     rsi
0x1800298eb  pop     rbp
0x1800298ec  retn
```
