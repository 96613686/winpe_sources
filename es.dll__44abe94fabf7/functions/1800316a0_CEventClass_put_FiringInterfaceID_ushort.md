# CEventClass::put_FiringInterfaceID(ushort *)

- ea: `0x1800316a0`
- end: `0x18003179b`
- name: `?put_FiringInterfaceID@CEventClass@@UEAAJPEAG@Z`
- size: `251`
- prototype: `int(CEventClass *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180008938`
- `0x1800164f0`
- `0x1800316a0`
- `0x18003ecb0`
- `0x180043510`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180031708`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180031708`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180031721`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180031721`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003176e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003176e`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800316e9`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800316e9`

## string_xrefs

- `0x180031743`: `com\complus\src\events\tier1\eventclass.cpp`

## pseudocode

```c
__int64 __fastcall CEventClass::put_FiringInterfaceID(CEventClass *this, unsigned __int16 *a2)
{
  char v3; // bl
  HRESULT v6; // [rsp+20h] [rbp-38h]
  LPOLESTR lpsz[2]; // [rsp+28h] [rbp-30h] BYREF
  GUID iid; // [rsp+38h] [rbp-20h] BYREF

  iid = 0;
  if ( a2 && *a2 )
  {
    *(_OWORD *)lpsz = 0;
    if ( IIDFromString(a2, &iid) < 0 )
      return (unsigned int)-2147024809;
    v3 = 1;
  }
  else
  {
    v3 = 0;
  }
  PropVariantClear((PROPVARIANT *)this + 15);
  if ( v3 )
  {
    lpsz[0] = 0;
    v6 = StringFromCLSID(&iid, lpsz);
    if ( v6 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\eventclass.cpp", 0x2AEu, 0x10u, v6);
    *((_WORD *)this + 60) = 8;
    SetBSTR((unsigned __int16 **)this + 16, lpsz[0]);
    CoTaskMemFree(lpsz[0]);
  }
  return 0;
}

```

## disassembly

```asm
0x1800316a0  mov     [rsp+arg_10], rbx
0x1800316a5  mov     [rsp+arg_18], rsi
0x1800316aa  push    rdi
0x1800316ab  sub     rsp, 50h
0x1800316af  mov     rax, cs:__security_cookie
0x1800316b6  xor     rax, rsp
0x1800316b9  mov     [rsp+58h+var_10], rax
0x1800316be  mov     rax, rdx
0x1800316c1  mov     rdi, rcx
0x1800316c4  xor     esi, esi
0x1800316c6  mov     [rsp+58h+var_38], esi
0x1800316ca  xorps   xmm0, xmm0
0x1800316cd  movups  xmmword ptr [rsp+58h+iid.Data1], xmm0
0x1800316d2  test    rax, rax
0x1800316d5  jz      short loc_180031701
0x1800316d7  cmp     [rdx], si
0x1800316da  jz      short loc_180031701
0x1800316dc  movups  xmmword ptr [rsp+58h+lpsz], xmm0
0x1800316e1  lea     rdx, [rsp+58h+iid]; lpiid
0x1800316e6  mov     rcx, rax; lpsz
0x1800316e9  call    cs:__imp_IIDFromString
0x1800316ef  test    eax, eax
0x1800316f1  js      short loc_1800316F7
0x1800316f3  mov     bl, 1
0x1800316f5  jmp     short loc_180031704
0x1800316f7  mov     [rsp+58h+var_38], 80070057h
0x1800316ff  jmp     short loc_180031778
0x180031701  mov     bl, sil
0x180031704  lea     rcx, [rdi+78h]; pvar
0x180031708  call    cs:__imp_PropVariantClear
0x18003170e  test    bl, bl
0x180031710  jz      short loc_180031774
0x180031712  mov     [rsp+58h+lpsz], rsi
0x180031717  lea     rdx, [rsp+58h+lpsz]; lplpsz
0x18003171c  lea     rcx, [rsp+58h+iid]; rclsid
0x180031721  call    cs:__imp_StringFromCLSID
0x180031727  mov     [rsp+58h+var_38], eax
0x18003172b  mov     eax, [rsp+58h+var_38]
0x18003172f  test    eax, eax
0x180031731  jns     short loc_18003174F
0x180031733  mov     r8d, 10h; unsigned __int16
0x180031739  mov     r9d, [rsp+58h+var_38]; int
0x18003173e  mov     edx, 2AEh; unsigned int
0x180031743  lea     rcx, aComComplusSrcE; "com\\complus\\src\\events\\tier1\\event"...
0x18003174a  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18003174f  mov     eax, 8
0x180031754  mov     [rdi+78h], ax
0x180031758  lea     rcx, [rdi+80h]; unsigned __int16 **
0x18003175f  mov     rdx, [rsp+58h+lpsz]; unsigned __int16 *
0x180031764  call    ?SetBSTR@@YAJAEAPEAGPEBG@Z; SetBSTR(ushort * &,ushort const *)
0x180031769  mov     rcx, [rsp+58h+lpsz]; pv
0x18003176e  call    cs:__imp_CoTaskMemFree
0x180031774  mov     [rsp+58h+var_38], esi
0x180031778  jmp     short $+2
0x18003177a  mov     eax, [rsp+58h+var_38]
0x18003177e  mov     rcx, [rsp+58h+var_10]
0x180031783  xor     rcx, rsp; StackCookie
0x180031786  call    __security_check_cookie
0x18003178b  mov     rbx, [rsp+58h+arg_10]
0x180031790  mov     rsi, [rsp+58h+arg_18]
0x180031795  add     rsp, 50h
0x180031799  pop     rdi
0x18003179a  retn
0x18004572a  push    rbp
0x18004572c  sub     rsp, 20h
0x180045730  mov     rbp, rdx
0x180045733  lea     rdx, [rbp+20h]; int *
0x180045737  call    ?ExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@AEAJ@Z
0x18004573c  nop
0x18004573d  add     rsp, 20h
0x180045741  pop     rbp
0x180045742  retn
```
