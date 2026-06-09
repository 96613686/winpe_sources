# CMsftDiscRecorder2::get_CurrentFeaturePages(tagSAFEARRAY * *)

- ea: `0x18002be40`
- end: `0x18002bfa4`
- name: `?get_CurrentFeaturePages@CMsftDiscRecorder2@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `356`
- prototype: `__int64 __fastcall(CMsftDiscRecorder2 *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002fc8`
- `0x1800140f4`
- `0x180016778`
- `0x18001cb0c`
- `0x18002be40`
- `0x1800436f8`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002bf70`
- `ole32!CoTaskMemFree` at `0x18002bf70`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::get_CurrentFeaturePages(CMsftDiscRecorder2 *this, struct tagSAFEARRAY **a2)
{
  struct tagSAFEARRAY **v2; // rdi
  signed int v3; // ebx
  struct tagSAFEARRAY **v4; // r9
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  const struct _GUID *v7; // r8
  int *v9; // [rsp+58h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+30h] BYREF
  SAFEARRAY *v11; // [rsp+68h] [rbp+38h] BYREF

  v11 = 0;
  v2 = a2;
  pv = 0;
  LODWORD(v9) = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 243, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    }
    v3 = -2147467261;
    goto LABEL_18;
  }
  *a2 = 0;
  LOBYTE(a2) = 1;
  v3 = (*(__int64 (__fastcall **)(char *, struct tagSAFEARRAY **, LPVOID *, int **))(*((_QWORD *)this + 1) + 120LL))(
         (char *)this + 8,
         a2,
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
    v6 = 244;
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
    v6 = 245;
    goto LABEL_17;
  }
  *v2 = v11;
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
0x18002be40  push    rbp
0x18002be42  push    rbx
0x18002be43  push    rdi
0x18002be44  mov     rbp, rsp
0x18002be47  sub     rsp, 30h
0x18002be4b  mov     [rbp+arg_18], 0
0x18002be53  mov     rdi, rdx
0x18002be56  mov     [rbp+pv], 0
0x18002be5e  mov     dword ptr [rbp+arg_8], 0
0x18002be65  test    rdx, rdx
0x18002be68  jnz     short loc_18002BEB1
0x18002be6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be71  lea     rax, WPP_GLOBAL_Control
0x18002be78  cmp     rcx, rax
0x18002be7b  jz      short loc_18002BEA7
0x18002be7d  test    byte ptr [rcx+0BCh], 4
0x18002be84  jz      short loc_18002BEA7
0x18002be86  cmp     byte ptr [rcx+0B9h], 3
0x18002be8d  jb      short loc_18002BEA7
0x18002be8f  mov     rcx, [rcx+0B0h]
0x18002be96  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002be9d  mov     edx, 0F3h
0x18002bea2  call    WPP_SF_
0x18002bea7  mov     ebx, 80004003h
0x18002beac  jmp     loc_18002BF5A
0x18002beb1  mov     qword ptr [rdx], 0
0x18002beb8  lea     r9, [rbp+arg_8]
0x18002bebc  add     rcx, 8
0x18002bec0  lea     r8, [rbp+pv]
0x18002bec4  mov     dl, 1
0x18002bec6  mov     rax, [rcx]
0x18002bec9  mov     rax, [rax+78h]
0x18002becd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bed2  mov     ebx, eax
0x18002bed4  test    eax, eax
0x18002bed6  jns     short loc_18002BF04
0x18002bed8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bedf  lea     rax, WPP_GLOBAL_Control
0x18002bee6  cmp     rcx, rax
0x18002bee9  jz      short loc_18002BF5A
0x18002beeb  test    byte ptr [rcx+0BCh], 4
0x18002bef2  jz      short loc_18002BF5A
0x18002bef4  cmp     byte ptr [rcx+0B9h], 3
0x18002befb  jb      short loc_18002BF5A
0x18002befd  mov     edx, 0F4h
0x18002bf02  jmp     short loc_18002BF44
0x18002bf04  mov     edx, dword ptr [rbp+arg_8]; int *
0x18002bf07  lea     r8, [rbp+arg_18]; unsigned int
0x18002bf0b  mov     rcx, [rbp+pv]; this
0x18002bf0f  call    ?CreateVariantSafeArrayFromV1Enums@Imapi2Utility@@YA?BJPEBJKPEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::CreateVariantSafeArrayFromV1Enums(long const *,ulong,tagSAFEARRAY * *)
0x18002bf14  mov     ebx, eax
0x18002bf16  test    eax, eax
0x18002bf18  jns     short loc_18002BF65
0x18002bf1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf21  lea     rax, WPP_GLOBAL_Control
0x18002bf28  cmp     rcx, rax
0x18002bf2b  jz      short loc_18002BF5A
0x18002bf2d  test    byte ptr [rcx+0BCh], 4
0x18002bf34  jz      short loc_18002BF5A
0x18002bf36  cmp     byte ptr [rcx+0B9h], 3
0x18002bf3d  jb      short loc_18002BF5A
0x18002bf3f  mov     edx, 0F5h
0x18002bf44  mov     rcx, [rcx+0B0h]
0x18002bf4b  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002bf52  mov     r9d, ebx
0x18002bf55  call    WPP_SF_d
0x18002bf5a  lea     rcx, [rbp+arg_18]; this
0x18002bf5e  call    ?SafeArrayDestroyAndNull@Imapi2Utility@@YAXAEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::SafeArrayDestroyAndNull(tagSAFEARRAY * &)
0x18002bf63  jmp     short loc_18002BF6C
0x18002bf65  mov     rax, [rbp+arg_18]
0x18002bf69  mov     [rdi], rax
0x18002bf6c  mov     rcx, [rbp+pv]; pv
0x18002bf70  call    cs:__imp_CoTaskMemFree
0x18002bf76  mov     eax, ebx
0x18002bf78  mov     [rbp+pv], 0
0x18002bf80  and     eax, 80FF0000h
0x18002bf85  cmp     eax, 80AA0000h
0x18002bf8a  jnz     short loc_18002BF9A
0x18002bf8c  lea     rdx, CLSID_MsftDiscRecorder2; int
0x18002bf93  mov     ecx, ebx; dwMessageId
0x18002bf95  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x18002bf9a  mov     eax, ebx
0x18002bf9c  add     rsp, 30h
0x18002bfa0  pop     rdi
0x18002bfa1  pop     rbx
0x18002bfa2  pop     rbp
0x18002bfa3  retn
```
