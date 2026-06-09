# CEventClass::put_MultiInterfacePublisherFilterCLSID(ushort *)

- ea: `0x1800317b0`
- end: `0x1800318ac`
- name: `?put_MultiInterfacePublisherFilterCLSID@CEventClass@@UEAAJPEAG@Z`
- size: `252`
- prototype: `int(CEventClass *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180008938`
- `0x1800164f0`
- `0x1800317b0`
- `0x18003ecb0`
- `0x180043510`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180031816`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180031816`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18003182f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18003182f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800317fd`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800317fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003187f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003187f`

## string_xrefs

- `0x180031851`: `com\complus\src\events\tier1\eventclass.cpp`

## pseudocode

```c
__int64 __fastcall CEventClass::put_MultiInterfacePublisherFilterCLSID(CEventClass *this, unsigned __int16 *a2)
{
  char v3; // bl
  HRESULT v5; // [rsp+20h] [rbp-38h]
  HRESULT v6; // [rsp+20h] [rbp-38h]
  LPOLESTR lpsz; // [rsp+28h] [rbp-30h] BYREF
  GUID pclsid; // [rsp+30h] [rbp-28h] BYREF

  if ( !a2 || (v3 = 1, !*a2) )
    v3 = 0;
  pclsid = 0;
  if ( !v3 || (v5 = CLSIDFromString(a2, &pclsid), v5 >= 0) )
  {
    PropVariantClear((PROPVARIANT *)this + 30);
    if ( v3 )
    {
      lpsz = 0;
      v6 = StringFromCLSID(&pclsid, &lpsz);
      if ( v6 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\eventclass.cpp", 0x39Eu, 0x10u, v6);
      *((_WORD *)this + 120) = 8;
      SetBSTR((unsigned __int16 **)this + 31, lpsz);
      CoTaskMemFree(lpsz);
    }
    return 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800317b0  mov     [rsp+arg_10], rbx
0x1800317b5  mov     [rsp+arg_18], rsi
0x1800317ba  push    rdi
0x1800317bb  sub     rsp, 50h
0x1800317bf  mov     rax, cs:__security_cookie
0x1800317c6  xor     rax, rsp
0x1800317c9  mov     [rsp+58h+var_18], rax
0x1800317ce  mov     rax, rdx
0x1800317d1  mov     rdi, rcx
0x1800317d4  xor     esi, esi
0x1800317d6  mov     [rsp+58h+var_38], esi
0x1800317da  test    rax, rax
0x1800317dd  jz      short loc_1800317E6
0x1800317df  cmp     [rdx], si
0x1800317e2  mov     bl, 1
0x1800317e4  jnz     short loc_1800317E9
0x1800317e6  mov     bl, sil
0x1800317e9  xorps   xmm0, xmm0
0x1800317ec  movups  xmmword ptr [rsp+58h+pclsid.Data1], xmm0
0x1800317f1  test    bl, bl
0x1800317f3  jz      short loc_18003180F
0x1800317f5  lea     rdx, [rsp+58h+pclsid]; pclsid
0x1800317fa  mov     rcx, rax; lpsz
0x1800317fd  call    cs:__imp_CLSIDFromString
0x180031803  mov     [rsp+58h+var_38], eax
0x180031807  mov     eax, [rsp+58h+var_38]
0x18003180b  test    eax, eax
0x18003180d  js      short loc_180031889
0x18003180f  lea     rcx, [rdi+0F0h]; pvar
0x180031816  call    cs:__imp_PropVariantClear
0x18003181c  test    bl, bl
0x18003181e  jz      short loc_180031885
0x180031820  mov     [rsp+58h+lpsz], rsi
0x180031825  lea     rdx, [rsp+58h+lpsz]; lplpsz
0x18003182a  lea     rcx, [rsp+58h+pclsid]; rclsid
0x18003182f  call    cs:__imp_StringFromCLSID
0x180031835  mov     [rsp+58h+var_38], eax
0x180031839  mov     eax, [rsp+58h+var_38]
0x18003183d  test    eax, eax
0x18003183f  jns     short loc_18003185D
0x180031841  mov     r8d, 10h; unsigned __int16
0x180031847  mov     r9d, [rsp+58h+var_38]; int
0x18003184c  mov     edx, 39Eh; unsigned int
0x180031851  lea     rcx, aComComplusSrcE; "com\\complus\\src\\events\\tier1\\event"...
0x180031858  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18003185d  mov     eax, 8
0x180031862  mov     [rdi+0F0h], ax
0x180031869  lea     rcx, [rdi+0F8h]; unsigned __int16 **
0x180031870  mov     rdx, [rsp+58h+lpsz]; unsigned __int16 *
0x180031875  call    ?SetBSTR@@YAJAEAPEAGPEBG@Z; SetBSTR(ushort * &,ushort const *)
0x18003187a  mov     rcx, [rsp+58h+lpsz]; pv
0x18003187f  call    cs:__imp_CoTaskMemFree
0x180031885  mov     [rsp+58h+var_38], esi
0x180031889  jmp     short $+2
0x18003188b  mov     eax, [rsp+58h+var_38]
0x18003188f  mov     rcx, [rsp+58h+var_18]
0x180031894  xor     rcx, rsp; StackCookie
0x180031897  call    __security_check_cookie
0x18003189c  mov     rbx, [rsp+58h+arg_10]
0x1800318a1  mov     rsi, [rsp+58h+arg_18]
0x1800318a6  add     rsp, 50h
0x1800318aa  pop     rdi
0x1800318ab  retn
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
