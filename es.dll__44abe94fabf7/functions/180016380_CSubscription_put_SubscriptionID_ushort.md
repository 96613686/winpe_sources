# CSubscription::put_SubscriptionID(ushort *)

- ea: `0x180016380`
- end: `0x1800164e9`
- name: `?put_SubscriptionID@CSubscription@@UEAAJPEAG@Z`
- size: `361`
- prototype: `int(CSubscription *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180008938`
- `0x180015850`
- `0x180016380`
- `0x1800164f0`
- `0x18003ecb0`
- `0x180043510`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800163d7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800163d7`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800163f3`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800163f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800164bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800164bc`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800163c6`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800163c6`

## string_xrefs

- `0x180016415`: `com\complus\src\events\tier1\subscription.cpp`

## pseudocode

```c
__int64 __fastcall CSubscription::put_SubscriptionID(CSubscription *this, unsigned __int16 *a2)
{
  _WORD *v3; // rdi
  __int64 v5; // r9
  HRESULT v6; // [rsp+30h] [rbp-98h]
  unsigned int v7; // [rsp+30h] [rbp-98h]
  LPOLESTR lpsz; // [rsp+38h] [rbp-90h] BYREF
  struct tagPROPVARIANT v9; // [rsp+40h] [rbp-88h] BYREF
  struct tagPROPVARIANT v10; // [rsp+60h] [rbp-68h] BYREF
  IID rclsid; // [rsp+80h] [rbp-48h] BYREF
  struct tagPROPVARIANT v12; // [rsp+90h] [rbp-38h] BYREF

  rclsid = 0;
  *(_OWORD *)&v12.vt = 0;
  if ( IIDFromString(a2, &rclsid) < 0 )
    return 2147942487LL;
  v3 = (_WORD *)((char *)this + 40);
  PropVariantClear((PROPVARIANT *)this + 5);
  lpsz = 0;
  v6 = StringFromCLSID(&rclsid, &lpsz);
  if ( v6 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\subscription.cpp", 0x30Fu, 0x10u, v6);
  *v3 = 8;
  SetBSTR((unsigned __int16 **)this + 6, lpsz);
  v12 = *(struct tagPROPVARIANT *)((char *)this + 448);
  v9 = *(struct tagPROPVARIANT *)((char *)this + 424);
  *(_OWORD *)&v10.vt = *(_OWORD *)v3;
  v10.bstrblobVal.pData = (BYTE *)*((_QWORD *)this + 7);
  v7 = ConcatenateECID_PARTID_APPID(&v10, &v9, &v12, v5, (unsigned __int16 *)this + 334);
  CoTaskMemFree(lpsz);
  return v7;
}

```

## disassembly

```asm
0x180016380  mov     r11, rsp
0x180016383  mov     [r11+18h], rbx
0x180016387  push    rdi
0x180016388  sub     rsp, 0C0h
0x18001638f  mov     rax, cs:__security_cookie
0x180016396  xor     rax, rsp
0x180016399  mov     [rsp+0C8h+var_18], rax
0x1800163a1  mov     rax, rdx
0x1800163a4  mov     rbx, rcx
0x1800163a7  mov     [rsp+0C8h+var_98], 0
0x1800163af  xorps   xmm0, xmm0
0x1800163b2  movups  xmmword ptr [r11-48h], xmm0
0x1800163b7  xorps   xmm1, xmm1
0x1800163ba  movups  xmmword ptr [r11-38h], xmm1
0x1800163bf  lea     rdx, [r11-48h]; lpiid
0x1800163c3  mov     rcx, rax; lpsz
0x1800163c6  call    cs:__imp_IIDFromString
0x1800163cc  test    eax, eax
0x1800163ce  js      short loc_180016423
0x1800163d0  lea     rdi, [rbx+28h]
0x1800163d4  mov     rcx, rdi; pvar
0x1800163d7  call    cs:__imp_PropVariantClear
0x1800163dd  mov     [rsp+0C8h+lpsz], 0
0x1800163e6  lea     rdx, [rsp+0C8h+lpsz]; lplpsz
0x1800163eb  lea     rcx, [rsp+0C8h+rclsid]; rclsid
0x1800163f3  call    cs:__imp_StringFromCLSID
0x1800163f9  mov     [rsp+0C8h+var_98], eax
0x1800163fd  mov     eax, [rsp+0C8h+var_98]
0x180016401  test    eax, eax
0x180016403  jns     short loc_18001642D
0x180016405  mov     r8d, 10h; unsigned __int16
0x18001640b  mov     r9d, [rsp+0C8h+var_98]; int
0x180016410  mov     edx, 30Fh; unsigned int
0x180016415  lea     rcx, aComComplusSrcE_15; "com\\complus\\src\\events\\tier1\\subsc"...
0x18001641c  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180016421  jmp     short loc_18001642D
0x180016423  mov     eax, 80070057h
0x180016428  jmp     loc_1800164C8
0x18001642d  mov     eax, 8
0x180016432  mov     [rdi], ax
0x180016435  lea     rcx, [rbx+30h]; unsigned __int16 **
0x180016439  mov     rdx, [rsp+0C8h+lpsz]; unsigned __int16 *
0x18001643e  call    ?SetBSTR@@YAJAEAPEAGPEBG@Z; SetBSTR(ushort * &,ushort const *)
0x180016443  movups  xmm0, xmmword ptr [rbx+1C0h]
0x18001644a  movaps  xmmword ptr [rsp+0C8h+var_38], xmm0
0x180016452  movsd   xmm1, qword ptr [rbx+1D0h]
0x18001645a  movsd   qword ptr [rsp+0C8h+var_38+10h], xmm1
0x180016463  movups  xmm0, xmmword ptr [rbx+1A8h]
0x18001646a  movaps  xmmword ptr [rsp+0C8h+var_88], xmm0
0x18001646f  movsd   xmm1, qword ptr [rbx+1B8h]
0x180016477  movsd   qword ptr [rsp+0C8h+var_88+10h], xmm1
0x18001647d  movups  xmm0, xmmword ptr [rdi]
0x180016480  movaps  xmmword ptr [rsp+0C8h+var_68], xmm0
0x180016485  movsd   xmm1, qword ptr [rdi+10h]
0x18001648a  movsd   qword ptr [rsp+0C8h+var_68+10h], xmm1
0x180016490  lea     rax, [rbx+29Ch]
0x180016497  mov     [rsp+0C8h+var_A8], rax; unsigned __int16 *
0x18001649c  lea     r8, [rsp+0C8h+var_38]; struct tagPROPVARIANT *
0x1800164a4  lea     rdx, [rsp+0C8h+var_88]; struct tagPROPVARIANT *
0x1800164a9  lea     rcx, [rsp+0C8h+var_68]; struct tagPROPVARIANT *
0x1800164ae  call    ?ConcatenateECID_PARTID_APPID@@YAJUtagPROPVARIANT@@00KPEAG@Z; ConcatenateECID_PARTID_APPID(tagPROPVARIANT,tagPROPVARIANT,tagPROPVARIANT,ulong,ushort *)
0x1800164b3  mov     [rsp+0C8h+var_98], eax
0x1800164b7  mov     rcx, [rsp+0C8h+lpsz]; pv
0x1800164bc  call    cs:__imp_CoTaskMemFree
0x1800164c2  jmp     short $+2
0x1800164c4  mov     eax, [rsp+0C8h+var_98]
0x1800164c8  mov     rcx, [rsp+0C8h+var_18]
0x1800164d0  xor     rcx, rsp; StackCookie
0x1800164d3  call    __security_check_cookie
0x1800164d8  mov     rbx, [rsp+0C8h+arg_10]
0x1800164e0  add     rsp, 0C0h
0x1800164e7  pop     rdi
0x1800164e8  retn
0x1800444bc  push    rbp
0x1800444be  sub     rsp, 30h
0x1800444c2  mov     rbp, rdx
0x1800444c5  lea     rdx, [rbp+30h]; int *
0x1800444c9  call    ?ExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@AEAJ@Z; ExceptionFilter(_EXCEPTION_POINTERS *,long &)
0x1800444ce  nop
0x1800444cf  add     rsp, 30h
0x1800444d3  pop     rbp
0x1800444d4  retn
```
