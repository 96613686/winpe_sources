# CMsftDiscRecorder2::get_SupportedProfiles(tagSAFEARRAY * *)

- ea: `0x18002c860`
- end: `0x18002c9c7`
- name: `?get_SupportedProfiles@CMsftDiscRecorder2@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `359`
- prototype: `__int64 __fastcall(CMsftDiscRecorder2 *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002fc8`
- `0x1800140f4`
- `0x180016778`
- `0x18001cb0c`
- `0x18002c860`
- `0x1800436f8`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002c993`
- `ole32!CoTaskMemFree` at `0x18002c993`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::get_SupportedProfiles(CMsftDiscRecorder2 *this, struct tagSAFEARRAY **a2)
{
  signed int v3; // ebx
  struct tagSAFEARRAY **v4; // r9
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  const struct _GUID *v7; // r8
  int *v9; // [rsp+58h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+30h] BYREF
  SAFEARRAY *v11; // [rsp+68h] [rbp+38h] BYREF

  v11 = 0;
  pv = 0;
  LODWORD(v9) = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 246, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    }
    v3 = -2147467261;
    goto LABEL_18;
  }
  *a2 = 0;
  v3 = (*(__int64 (__fastcall **)(char *, _QWORD, LPVOID *, int **))(*((_QWORD *)this + 1) + 128LL))(
         (char *)this + 8,
         0,
         &pv,
         &v9);
  if ( v3 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
    {
      goto LABEL_18;
    }
    v6 = 247;
LABEL_17:
    WPP_SF_d(v5[22], v6, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, (unsigned int)v3);
LABEL_18:
    Imapi2Utility::SafeArrayDestroyAndNull((Imapi2Utility *)&v11, a2);
    goto LABEL_20;
  }
  v3 = Imapi2Utility::CreateVariantSafeArrayFromV1Enums((LONG *)pv, (const int *)(unsigned int)v9, &v11, v4);
  if ( v3 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
    {
      goto LABEL_18;
    }
    v6 = 248;
    goto LABEL_17;
  }
  *a2 = v11;
LABEL_20:
  CoTaskMemFree(pv);
  pv = 0;
  if ( (v3 & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(v3, (__int64)&CLSID_MsftDiscRecorder2, v7);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002c860  push    rbp
0x18002c862  push    rbx
0x18002c863  push    rdi
0x18002c864  mov     rbp, rsp
0x18002c867  sub     rsp, 30h
0x18002c86b  mov     [rbp+arg_18], 0
0x18002c873  mov     rdi, rdx
0x18002c876  mov     [rbp+pv], 0
0x18002c87e  mov     dword ptr [rbp+arg_8], 0
0x18002c885  test    rdx, rdx
0x18002c888  jnz     short loc_18002C8D1
0x18002c88a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c891  lea     rax, WPP_GLOBAL_Control
0x18002c898  cmp     rcx, rax
0x18002c89b  jz      short loc_18002C8C7
0x18002c89d  test    byte ptr [rcx+0BCh], 4
0x18002c8a4  jz      short loc_18002C8C7
0x18002c8a6  cmp     byte ptr [rcx+0B9h], 3
0x18002c8ad  jb      short loc_18002C8C7
0x18002c8af  mov     rcx, [rcx+0B0h]
0x18002c8b6  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002c8bd  mov     edx, 0F6h
0x18002c8c2  call    WPP_SF_
0x18002c8c7  mov     ebx, 80004003h
0x18002c8cc  jmp     loc_18002C97D
0x18002c8d1  mov     qword ptr [rdx], 0
0x18002c8d8  lea     r9, [rbp+arg_8]
0x18002c8dc  add     rcx, 8
0x18002c8e0  lea     r8, [rbp+pv]
0x18002c8e4  xor     edx, edx
0x18002c8e6  mov     rax, [rcx]
0x18002c8e9  mov     rax, [rax+80h]
0x18002c8f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c8f5  mov     ebx, eax
0x18002c8f7  test    eax, eax
0x18002c8f9  jns     short loc_18002C927
0x18002c8fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c902  lea     rax, WPP_GLOBAL_Control
0x18002c909  cmp     rcx, rax
0x18002c90c  jz      short loc_18002C97D
0x18002c90e  test    byte ptr [rcx+0BCh], 4
0x18002c915  jz      short loc_18002C97D
0x18002c917  cmp     byte ptr [rcx+0B9h], 3
0x18002c91e  jb      short loc_18002C97D
0x18002c920  mov     edx, 0F7h
0x18002c925  jmp     short loc_18002C967
0x18002c927  mov     edx, dword ptr [rbp+arg_8]; int *
0x18002c92a  lea     r8, [rbp+arg_18]; unsigned int
0x18002c92e  mov     rcx, [rbp+pv]; this
0x18002c932  call    ?CreateVariantSafeArrayFromV1Enums@Imapi2Utility@@YA?BJPEBJKPEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::CreateVariantSafeArrayFromV1Enums(long const *,ulong,tagSAFEARRAY * *)
0x18002c937  mov     ebx, eax
0x18002c939  test    eax, eax
0x18002c93b  jns     short loc_18002C988
0x18002c93d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c944  lea     rax, WPP_GLOBAL_Control
0x18002c94b  cmp     rcx, rax
0x18002c94e  jz      short loc_18002C97D
0x18002c950  test    byte ptr [rcx+0BCh], 4
0x18002c957  jz      short loc_18002C97D
0x18002c959  cmp     byte ptr [rcx+0B9h], 3
0x18002c960  jb      short loc_18002C97D
0x18002c962  mov     edx, 0F8h
0x18002c967  mov     rcx, [rcx+0B0h]
0x18002c96e  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002c975  mov     r9d, ebx
0x18002c978  call    WPP_SF_d
0x18002c97d  lea     rcx, [rbp+arg_18]; this
0x18002c981  call    ?SafeArrayDestroyAndNull@Imapi2Utility@@YAXAEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::SafeArrayDestroyAndNull(tagSAFEARRAY * &)
0x18002c986  jmp     short loc_18002C98F
0x18002c988  mov     rax, [rbp+arg_18]
0x18002c98c  mov     [rdi], rax
0x18002c98f  mov     rcx, [rbp+pv]; pv
0x18002c993  call    cs:__imp_CoTaskMemFree
0x18002c999  mov     eax, ebx
0x18002c99b  mov     [rbp+pv], 0
0x18002c9a3  and     eax, 80FF0000h
0x18002c9a8  cmp     eax, 80AA0000h
0x18002c9ad  jnz     short loc_18002C9BD
0x18002c9af  lea     rdx, CLSID_MsftDiscRecorder2; int
0x18002c9b6  mov     ecx, ebx; dwMessageId
0x18002c9b8  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x18002c9bd  mov     eax, ebx
0x18002c9bf  add     rsp, 30h
0x18002c9c3  pop     rdi
0x18002c9c4  pop     rbx
0x18002c9c5  pop     rbp
0x18002c9c6  retn
```
