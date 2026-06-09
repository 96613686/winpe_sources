# CEventClass::put_EventClassID(ushort *)

- ea: `0x1800312f0`
- end: `0x180031480`
- name: `?put_EventClassID@CEventClass@@UEAAJPEAG@Z`
- size: `400`
- prototype: `int(CEventClass *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180008938`
- `0x180015850`
- `0x1800164f0`
- `0x1800312f0`
- `0x18003ecb0`
- `0x180043510`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003134e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003134e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18003136a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18003136a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800313b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800313b3`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180031333`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180031333`

## string_xrefs

- `0x18003138c`: `com\complus\src\events\tier1\eventclass.cpp`
- `0x180031445`: `com\complus\src\events\tier1\eventclass.cpp`

## pseudocode

```c
__int64 __fastcall CEventClass::put_EventClassID(CEventClass *this, unsigned __int16 *a2)
{
  _WORD *v4; // rdi
  __int64 v5; // r9
  HRESULT v6; // [rsp+30h] [rbp-98h]
  int v7; // [rsp+30h] [rbp-98h]
  LPOLESTR lpsz; // [rsp+38h] [rbp-90h] BYREF
  struct tagPROPVARIANT v9; // [rsp+40h] [rbp-88h] BYREF
  struct tagPROPVARIANT v10; // [rsp+60h] [rbp-68h] BYREF
  IID rclsid; // [rsp+80h] [rbp-48h] BYREF
  struct tagPROPVARIANT v12; // [rsp+90h] [rbp-38h] BYREF

  rclsid = 0;
  *(_OWORD *)&v12.vt = 0;
  if ( IIDFromString(a2, &rclsid) < 0 )
    return 2147942487LL;
  v4 = (_WORD *)((char *)this + 48);
  PropVariantClear((PROPVARIANT *)this + 6);
  lpsz = 0;
  v6 = StringFromCLSID(&rclsid, &lpsz);
  if ( v6 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\eventclass.cpp", 0x200u, 0x10u, v6);
  *v4 = 8;
  SetBSTR((unsigned __int16 **)this + 7, lpsz);
  CoTaskMemFree(lpsz);
  v12 = *(struct tagPROPVARIANT *)((_BYTE *)this + 14);
  v9 = *(struct tagPROPVARIANT *)((_BYTE *)this + 13);
  *(_OWORD *)&v10.vt = *(_OWORD *)v4;
  v10.bstrblobVal.pData = (BYTE *)*((_QWORD *)this + 8);
  v7 = ConcatenateECID_PARTID_APPID(&v10, &v9, &v12, v5, (unsigned __int16 *)this + 242);
  if ( v7 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\eventclass.cpp", 0x20Cu, 0x10u, v7);
  return 0;
}

```

## disassembly

```asm
0x1800312f0  mov     r11, rsp
0x1800312f3  mov     [r11+18h], rbx
0x1800312f7  push    rdi
0x1800312f8  sub     rsp, 0C0h
0x1800312ff  mov     rax, cs:__security_cookie
0x180031306  xor     rax, rsp
0x180031309  mov     [rsp+0C8h+var_18], rax
0x180031311  mov     rax, rdx
0x180031314  mov     rbx, rcx
0x180031317  mov     [rsp+0C8h+var_98], 0
0x18003131f  xorps   xmm0, xmm0
0x180031322  movups  xmmword ptr [r11-48h], xmm0
0x180031327  movups  xmmword ptr [r11-38h], xmm0
0x18003132c  lea     rdx, [r11-48h]; lpiid
0x180031330  mov     rcx, rax; lpsz
0x180031333  call    cs:__imp_IIDFromString
0x180031339  test    eax, eax
0x18003133b  jns     short loc_180031347
0x18003133d  mov     eax, 80070057h
0x180031342  jmp     loc_18003145F
0x180031347  lea     rdi, [rbx+30h]
0x18003134b  mov     rcx, rdi; pvar
0x18003134e  call    cs:__imp_PropVariantClear
0x180031354  mov     [rsp+0C8h+lpsz], 0
0x18003135d  lea     rdx, [rsp+0C8h+lpsz]; lplpsz
0x180031362  lea     rcx, [rsp+0C8h+rclsid]; rclsid
0x18003136a  call    cs:__imp_StringFromCLSID
0x180031370  mov     [rsp+0C8h+var_98], eax
0x180031374  mov     eax, [rsp+0C8h+var_98]
0x180031378  test    eax, eax
0x18003137a  jns     short loc_180031398
0x18003137c  mov     r8d, 10h; unsigned __int16
0x180031382  mov     r9d, [rsp+0C8h+var_98]; int
0x180031387  mov     edx, 200h; unsigned int
0x18003138c  lea     rcx, aComComplusSrcE; "com\\complus\\src\\events\\tier1\\event"...
0x180031393  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180031398  mov     eax, 8
0x18003139d  mov     [rdi], ax
0x1800313a0  lea     rcx, [rbx+38h]; unsigned __int16 **
0x1800313a4  mov     rdx, [rsp+0C8h+lpsz]; unsigned __int16 *
0x1800313a9  call    ?SetBSTR@@YAJAEAPEAGPEBG@Z; SetBSTR(ushort * &,ushort const *)
0x1800313ae  mov     rcx, [rsp+0C8h+lpsz]; pv
0x1800313b3  call    cs:__imp_CoTaskMemFree
0x1800313b9  movups  xmm0, xmmword ptr [rbx+150h]
0x1800313c0  movaps  xmmword ptr [rsp+0C8h+var_38], xmm0
0x1800313c8  movsd   xmm1, qword ptr [rbx+160h]
0x1800313d0  movsd   qword ptr [rsp+0C8h+var_38+10h], xmm1
0x1800313d9  movups  xmm0, xmmword ptr [rbx+138h]
0x1800313e0  movaps  xmmword ptr [rsp+0C8h+var_88], xmm0
0x1800313e5  movsd   xmm1, qword ptr [rbx+148h]
0x1800313ed  movsd   qword ptr [rsp+0C8h+var_88+10h], xmm1
0x1800313f3  movups  xmm0, xmmword ptr [rdi]
0x1800313f6  movaps  xmmword ptr [rsp+0C8h+var_68], xmm0
0x1800313fb  movsd   xmm1, qword ptr [rdi+10h]
0x180031400  movsd   qword ptr [rsp+0C8h+var_68+10h], xmm1
0x180031406  lea     rax, [rbx+1E4h]
0x18003140d  mov     [rsp+0C8h+var_A8], rax; unsigned __int16 *
0x180031412  lea     r8, [rsp+0C8h+var_38]; struct tagPROPVARIANT *
0x18003141a  lea     rdx, [rsp+0C8h+var_88]; struct tagPROPVARIANT *
0x18003141f  lea     rcx, [rsp+0C8h+var_68]; struct tagPROPVARIANT *
0x180031424  call    ?ConcatenateECID_PARTID_APPID@@YAJUtagPROPVARIANT@@00KPEAG@Z; ConcatenateECID_PARTID_APPID(tagPROPVARIANT,tagPROPVARIANT,tagPROPVARIANT,ulong,ushort *)
0x180031429  mov     [rsp+0C8h+var_98], eax
0x18003142d  mov     eax, [rsp+0C8h+var_98]
0x180031431  test    eax, eax
0x180031433  jns     short loc_180031451
0x180031435  mov     r8d, 10h; unsigned __int16
0x18003143b  mov     r9d, [rsp+0C8h+var_98]; int
0x180031440  mov     edx, 20Ch; unsigned int
0x180031445  lea     rcx, aComComplusSrcE; "com\\complus\\src\\events\\tier1\\event"...
0x18003144c  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180031451  mov     [rsp+0C8h+var_98], 0
0x180031459  jmp     short $+2
0x18003145b  mov     eax, [rsp+0C8h+var_98]
0x18003145f  mov     rcx, [rsp+0C8h+var_18]
0x180031467  xor     rcx, rsp; StackCookie
0x18003146a  call    __security_check_cookie
0x18003146f  mov     rbx, [rsp+0C8h+arg_10]
0x180031477  add     rsp, 0C0h
0x18003147e  pop     rdi
0x18003147f  retn
0x18004570a  push    rbp
0x18004570c  sub     rsp, 30h
0x180045710  mov     rbp, rdx
0x180045713  lea     rdx, [rbp+30h]; int *
0x180045717  call    ?ExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@AEAJ@Z; ExceptionFilter(_EXCEPTION_POINTERS *,long &)
0x18004571c  nop
0x18004571d  add     rsp, 30h
0x180045721  pop     rbp
0x180045722  retn
```
