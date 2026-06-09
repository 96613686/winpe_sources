# GetConnectionInstanceByGuid(IWbemServices *,ushort *,_GUID *,IWbemClassObject * *)

- ea: `0x1800291dc`
- end: `0x180029329`
- name: `?GetConnectionInstanceByGuid@@YAJPEAUIWbemServices@@PEAGPEAU_GUID@@PEAPEAUIWbemClassObject@@@Z`
- size: `333`
- prototype: `__int64 __fastcall(struct IWbemServices *, unsigned __int16 *, struct _GUID *, struct IWbemClassObject **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002914c`

## callees

- `0x180028078`
- `0x180028210`
- `0x1800291dc`
- `0x18002ae64`
- `0x18002f010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18002926c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002926c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800292b7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800292b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029244`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029244`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002921a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002921a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetConnectionInstanceByGuid(
        struct IWbemServices *a1,
        unsigned __int16 *a2,
        struct _GUID *a3,
        struct IWbemClassObject **a4)
{
  HRESULT v7; // ebx
  const unsigned __int16 *v8; // rdx
  struct IWbemServicesVtbl *lpVtbl; // rax
  struct IEnumWbemClassObject *v10; // rcx
  unsigned __int16 *v12; // [rsp+40h] [rbp-20h] BYREF
  struct IEnumWbemClassObject *v13; // [rsp+48h] [rbp-18h] BYREF
  LPOLESTR lpsz; // [rsp+50h] [rbp-10h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-8h] BYREF

  v12 = 0;
  bstrString = 0;
  lpsz = 0;
  v13 = 0;
  v7 = StringFromCLSID(a3, &lpsz);
  if ( !v7 )
  {
    v7 = BuildQuotedEqualsString(&v12, L"Guid", lpsz);
    CoTaskMemFree(lpsz);
    if ( !v7 )
    {
      v7 = BuildSelectQueryBstr(&bstrString, v8, L"HNet_Connection", v12);
      operator delete[](v12);
      if ( !v7 )
      {
        lpVtbl = a1->lpVtbl;
        v13 = 0;
        v7 = ((__int64 (__fastcall *)(struct IWbemServices *, unsigned __int16 *, BSTR, __int64, _QWORD, struct IEnumWbemClassObject **))lpVtbl->ExecQuery)(
               a1,
               a2,
               bstrString,
               48,
               0,
               &v13);
        SysFreeString(bstrString);
        if ( !v7 )
        {
          v10 = v13;
          LODWORD(v12) = 0;
          *a4 = 0;
          v7 = ((__int64 (__fastcall *)(struct IEnumWbemClassObject *, __int64, __int64, struct IWbemClassObject **, unsigned __int16 **))v10->lpVtbl->Next)(
                 v10,
                 0xFFFFFFFFLL,
                 1,
                 a4,
                 &v12);
          if ( v7 >= 0 && (_DWORD)v12 != 1 )
            v7 = -2147467259;
          ValidateFinishedWCOEnum(a1, v13);
          ((void (__fastcall *)(struct IEnumWbemClassObject *))v13->lpVtbl->Release)(v13);
        }
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800291dc  push    rbp
0x1800291de  push    rbx
0x1800291df  push    rsi
0x1800291e0  push    rdi
0x1800291e1  push    r14
0x1800291e3  mov     rbp, rsp
0x1800291e6  sub     rsp, 60h
0x1800291ea  mov     r14, rdx
0x1800291ed  mov     [rbp+var_20], 0
0x1800291f5  mov     rdi, rcx
0x1800291f8  mov     [rbp+bstrString], 0
0x180029200  lea     rdx, [rbp+lpsz]; lplpsz
0x180029204  mov     [rbp+lpsz], 0
0x18002920c  mov     rcx, r8; rclsid
0x18002920f  mov     [rbp+var_18], 0
0x180029217  mov     rsi, r9
0x18002921a  call    cs:__imp_StringFromCLSID
0x180029220  mov     ebx, eax
0x180029222  test    eax, eax
0x180029224  jnz     loc_18002931C
0x18002922a  mov     r8, [rbp+lpsz]; unsigned __int16 *
0x18002922e  lea     rdx, ?c_wszGuid@@3QBGB; "Guid"
0x180029235  lea     rcx, [rbp+var_20]; unsigned __int16 **
0x180029239  call    ?BuildQuotedEqualsString@@YAJPEAPEAGPEBG1@Z; BuildQuotedEqualsString(ushort * *,ushort const *,ushort const *)
0x18002923e  mov     rcx, [rbp+lpsz]; pv
0x180029242  mov     ebx, eax
0x180029244  call    cs:__imp_CoTaskMemFree
0x18002924a  test    ebx, ebx
0x18002924c  jnz     loc_18002931C
0x180029252  mov     r9, [rbp+var_20]; unsigned __int16 *
0x180029256  lea     r8, ?c_wszHnetConnection@@3QBGB; "HNet_Connection"
0x18002925d  lea     rcx, [rbp+bstrString]; unsigned __int16 **
0x180029261  call    ?BuildSelectQueryBstr@@YAJPEAPEAGPEBG11@Z; BuildSelectQueryBstr(ushort * *,ushort const *,ushort const *,ushort const *)
0x180029266  mov     rcx, [rbp+var_20]
0x18002926a  mov     ebx, eax
0x18002926c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180029272  test    ebx, ebx
0x180029274  jnz     loc_18002931C
0x18002927a  mov     rax, [rdi]
0x18002927d  lea     rcx, [rbp+var_18]
0x180029281  mov     r8, [rbp+bstrString]
0x180029285  lea     r9d, [rbx+30h]
0x180029289  mov     [rsp+60h+var_38], rcx
0x18002928e  mov     rdx, r14
0x180029291  mov     rcx, rdi
0x180029294  mov     [rbp+var_18], 0
0x18002929c  mov     rax, [rax+0A0h]
0x1800292a3  mov     [rsp+60h+var_40], 0
0x1800292ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292b1  mov     rcx, [rbp+bstrString]; bstrString
0x1800292b5  mov     ebx, eax
0x1800292b7  call    cs:__imp_SysFreeString
0x1800292bd  test    ebx, ebx
0x1800292bf  jnz     short loc_18002931C
0x1800292c1  mov     rcx, [rbp+var_18]
0x1800292c5  lea     rdx, [rbp+var_20]
0x1800292c9  mov     dword ptr [rbp+var_20], ebx
0x1800292cc  lea     r8d, [rbx+1]
0x1800292d0  mov     qword ptr [rsi], 0
0x1800292d7  mov     r9, rsi
0x1800292da  mov     [rsp+60h+var_40], rdx
0x1800292df  or      edx, 0FFFFFFFFh
0x1800292e2  mov     rax, [rcx]
0x1800292e5  mov     rax, [rax+20h]
0x1800292e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292ee  mov     ebx, eax
0x1800292f0  test    eax, eax
0x1800292f2  js      short loc_180029300
0x1800292f4  cmp     dword ptr [rbp+var_20], 1
0x1800292f8  mov     eax, 80004005h
0x1800292fd  cmovnz  ebx, eax
0x180029300  mov     rdx, [rbp+var_18]; struct IEnumWbemClassObject *
0x180029304  mov     rcx, rdi; struct IWbemServices *
0x180029307  call    ?ValidateFinishedWCOEnum@@YAXPEAUIWbemServices@@PEAUIEnumWbemClassObject@@@Z; ValidateFinishedWCOEnum(IWbemServices *,IEnumWbemClassObject *)
0x18002930c  mov     rcx, [rbp+var_18]
0x180029310  mov     rax, [rcx]
0x180029313  mov     rax, [rax+10h]
0x180029317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002931c  mov     eax, ebx
0x18002931e  add     rsp, 60h
0x180029322  pop     r14
0x180029324  pop     rdi
0x180029325  pop     rsi
0x180029326  pop     rbx
0x180029327  pop     rbp
0x180029328  retn
```
