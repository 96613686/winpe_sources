# _lambda_3af9af96f55fc1e235ca6cd5835f12ee_::operator()

- ea: `0x180008234`
- end: `0x180008351`
- name: `_lambda_3af9af96f55fc1e235ca6cd5835f12ee_::operator()`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000820c`

## callees

- `0x180006538`
- `0x180008234`
- `0x180008538`
- `0x180009920`
- `0x1800167f8`

## import_xrefs

- `ncrypt!NCryptFreeObject` at `0x1800082ed`
- `ncrypt!NCryptFreeObject` at `0x1800082ed`

## string_xrefs

- `0x180008254`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x1800082b8`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x1800082d0`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x18000831a`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`

## pseudocode

```c
__int64 __fastcall lambda_3af9af96f55fc1e235ca6cd5835f12ee_::operator()(__int64 **a1)
{
  __int64 *v2; // rcx
  __int64 v3; // rdx
  unsigned int v4; // ebx
  int v5; // eax
  unsigned int *v6; // r9
  int NCryptDwordProperty; // eax
  _QWORD v9[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  __int64 v11; // [rsp+50h] [rbp+20h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+58h] [rbp+28h] BYREF
  NCRYPT_HANDLE *p_hObject; // [rsp+60h] [rbp+30h] BYREF

  v2 = *a1;
  if ( !*v2 )
  {
    v3 = 1622;
LABEL_3:
    v4 = -2146893785;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)0x80090027LL,
      v9[0]);
    return v4;
  }
  if ( !*a1[1] )
  {
    v3 = 1623;
    goto LABEL_3;
  }
  hObject = 0;
  p_hObject = &hObject;
  v11 = *v2;
  v9[0] = &v11;
  v9[1] = &p_hObject;
  v5 = HResultErrorContract__lambda_9209c3bff2fe15152f61109abc0c1cf2_(v9);
  v4 = v5;
  if ( v5 >= 0 )
  {
    LODWORD(v11) = 0;
    NCryptDwordProperty = NgcUtils::GetNCryptDwordProperty(
                            (NgcUtils *)hObject,
                            (unsigned __int64)L"NgcKeyImplType",
                            (const unsigned __int16 *)&v11,
                            v6);
    v4 = NCryptDwordProperty;
    if ( NCryptDwordProperty >= 0 )
    {
      v4 = 0;
      *(_DWORD *)*a1[1] = v11;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x662,
        (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
        (const char *)(unsigned int)NCryptDwordProperty,
        v9[0]);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C7,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)(unsigned int)v5,
      v9[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65C,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)v4,
      v9[0]);
    if ( hObject )
      NCryptFreeObject(hObject);
  }
  return v4;
}

```

## disassembly

```asm
0x180008234  push    rbp
0x180008236  push    rbx
0x180008237  push    rdi
0x180008238  mov     rbp, rsp
0x18000823b  sub     rsp, 30h
0x18000823f  mov     rdi, rcx
0x180008242  mov     rcx, [rcx]
0x180008245  cmp     qword ptr [rcx], 0
0x180008249  jnz     short loc_18000826D
0x18000824b  mov     edx, 656h; void *
0x180008250  mov     rcx, [rbp+18h]; this
0x180008254  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18000825b  mov     ebx, 80090027h
0x180008260  mov     r9d, ebx; char *
0x180008263  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008268  jmp     loc_180008347
0x18000826d  mov     rax, [rdi+8]
0x180008271  cmp     qword ptr [rax], 0
0x180008275  jnz     short loc_18000827E
0x180008277  mov     edx, 657h
0x18000827c  jmp     short loc_180008250
0x18000827e  lea     rax, [rbp+hObject]
0x180008282  mov     [rbp+hObject], 0
0x18000828a  mov     [rbp+arg_10], rax
0x18000828e  mov     rax, [rcx]
0x180008291  lea     rcx, [rbp+var_10]
0x180008295  mov     [rbp+arg_0], rax
0x180008299  lea     rax, [rbp+arg_0]
0x18000829d  mov     [rbp+var_10], rax
0x1800082a1  lea     rax, [rbp+arg_10]
0x1800082a5  mov     [rbp+var_8], rax
0x1800082a9  call    HResultErrorContract__lambda_9209c3bff2fe15152f61109abc0c1cf2___; HResultErrorContract__lambda_9209c3bff2fe15152f61109abc0c1cf2_
0x1800082ae  mov     ebx, eax
0x1800082b0  test    eax, eax
0x1800082b2  jns     short loc_1800082F5
0x1800082b4  mov     rcx, [rbp+18h]; this
0x1800082b8  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x1800082bf  mov     r9d, eax; char *
0x1800082c2  mov     edx, 4C7h; void *
0x1800082c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800082cc  mov     rcx, [rbp+18h]; this
0x1800082d0  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x1800082d7  mov     r9d, ebx; char *
0x1800082da  mov     edx, 65Ch; void *
0x1800082df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800082e4  mov     rcx, [rbp+hObject]; hObject
0x1800082e8  test    rcx, rcx
0x1800082eb  jz      short loc_180008347
0x1800082ed  call    cs:__imp_NCryptFreeObject
0x1800082f3  jmp     short loc_180008347
0x1800082f5  mov     rcx, [rbp+hObject]; this
0x1800082f9  lea     r8, [rbp+arg_0]; unsigned __int16 *
0x1800082fd  lea     rdx, aNgckeyimpltype; "NgcKeyImplType"
0x180008304  mov     dword ptr [rbp+arg_0], 0
0x18000830b  call    ?GetNCryptDwordProperty@NgcUtils@@YAJ_KPEBGPEAK@Z; NgcUtils::GetNCryptDwordProperty(unsigned __int64,ushort const *,ulong *)
0x180008310  mov     ebx, eax
0x180008312  test    eax, eax
0x180008314  jns     short loc_180008330
0x180008316  mov     rcx, [rbp+18h]; this
0x18000831a  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180008321  mov     r9d, eax; char *
0x180008324  mov     edx, 662h; void *
0x180008329  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000832e  jmp     short loc_18000833E
0x180008330  mov     rax, [rdi+8]
0x180008334  xor     ebx, ebx
0x180008336  mov     rcx, [rax]
0x180008339  mov     eax, dword ptr [rbp+arg_0]
0x18000833c  mov     [rcx], eax
0x18000833e  lea     rcx, [rbp+hObject]
0x180008342  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180008347  mov     eax, ebx
0x180008349  add     rsp, 30h
0x18000834d  pop     rdi
0x18000834e  pop     rbx
0x18000834f  pop     rbp
0x180008350  retn
```
