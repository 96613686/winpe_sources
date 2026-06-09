# CMsftDiscRecorder2::get_SupportedFeaturePages(tagSAFEARRAY * *)

- ea: `0x18002c580`
- end: `0x18002c6e4`
- name: `?get_SupportedFeaturePages@CMsftDiscRecorder2@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
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
- `0x18002c580`
- `0x1800436f8`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002c6b0`
- `ole32!CoTaskMemFree` at `0x18002c6b0`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::get_SupportedFeaturePages(CMsftDiscRecorder2 *this, struct tagSAFEARRAY **a2)
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 240, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    }
    v3 = -2147467261;
    goto LABEL_18;
  }
  *a2 = 0;
  v3 = (*(__int64 (__fastcall **)(char *, _QWORD, LPVOID *, int **))(*((_QWORD *)this + 1) + 120LL))(
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
    v6 = 241;
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
    v6 = 242;
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
0x18002c580  push    rbp
0x18002c582  push    rbx
0x18002c583  push    rdi
0x18002c584  mov     rbp, rsp
0x18002c587  sub     rsp, 30h
0x18002c58b  mov     [rbp+arg_18], 0
0x18002c593  mov     rdi, rdx
0x18002c596  mov     [rbp+pv], 0
0x18002c59e  mov     dword ptr [rbp+arg_8], 0
0x18002c5a5  test    rdx, rdx
0x18002c5a8  jnz     short loc_18002C5F1
0x18002c5aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c5b1  lea     rax, WPP_GLOBAL_Control
0x18002c5b8  cmp     rcx, rax
0x18002c5bb  jz      short loc_18002C5E7
0x18002c5bd  test    byte ptr [rcx+0BCh], 4
0x18002c5c4  jz      short loc_18002C5E7
0x18002c5c6  cmp     byte ptr [rcx+0B9h], 3
0x18002c5cd  jb      short loc_18002C5E7
0x18002c5cf  mov     rcx, [rcx+0B0h]
0x18002c5d6  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002c5dd  mov     edx, 0F0h
0x18002c5e2  call    WPP_SF_
0x18002c5e7  mov     ebx, 80004003h
0x18002c5ec  jmp     loc_18002C69A
0x18002c5f1  mov     qword ptr [rdx], 0
0x18002c5f8  lea     r9, [rbp+arg_8]
0x18002c5fc  add     rcx, 8
0x18002c600  lea     r8, [rbp+pv]
0x18002c604  xor     edx, edx
0x18002c606  mov     rax, [rcx]
0x18002c609  mov     rax, [rax+78h]
0x18002c60d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c612  mov     ebx, eax
0x18002c614  test    eax, eax
0x18002c616  jns     short loc_18002C644
0x18002c618  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c61f  lea     rax, WPP_GLOBAL_Control
0x18002c626  cmp     rcx, rax
0x18002c629  jz      short loc_18002C69A
0x18002c62b  test    byte ptr [rcx+0BCh], 4
0x18002c632  jz      short loc_18002C69A
0x18002c634  cmp     byte ptr [rcx+0B9h], 3
0x18002c63b  jb      short loc_18002C69A
0x18002c63d  mov     edx, 0F1h
0x18002c642  jmp     short loc_18002C684
0x18002c644  mov     edx, dword ptr [rbp+arg_8]; int *
0x18002c647  lea     r8, [rbp+arg_18]; unsigned int
0x18002c64b  mov     rcx, [rbp+pv]; this
0x18002c64f  call    ?CreateVariantSafeArrayFromV1Enums@Imapi2Utility@@YA?BJPEBJKPEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::CreateVariantSafeArrayFromV1Enums(long const *,ulong,tagSAFEARRAY * *)
0x18002c654  mov     ebx, eax
0x18002c656  test    eax, eax
0x18002c658  jns     short loc_18002C6A5
0x18002c65a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c661  lea     rax, WPP_GLOBAL_Control
0x18002c668  cmp     rcx, rax
0x18002c66b  jz      short loc_18002C69A
0x18002c66d  test    byte ptr [rcx+0BCh], 4
0x18002c674  jz      short loc_18002C69A
0x18002c676  cmp     byte ptr [rcx+0B9h], 3
0x18002c67d  jb      short loc_18002C69A
0x18002c67f  mov     edx, 0F2h
0x18002c684  mov     rcx, [rcx+0B0h]
0x18002c68b  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002c692  mov     r9d, ebx
0x18002c695  call    WPP_SF_d
0x18002c69a  lea     rcx, [rbp+arg_18]; this
0x18002c69e  call    ?SafeArrayDestroyAndNull@Imapi2Utility@@YAXAEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::SafeArrayDestroyAndNull(tagSAFEARRAY * &)
0x18002c6a3  jmp     short loc_18002C6AC
0x18002c6a5  mov     rax, [rbp+arg_18]
0x18002c6a9  mov     [rdi], rax
0x18002c6ac  mov     rcx, [rbp+pv]; pv
0x18002c6b0  call    cs:__imp_CoTaskMemFree
0x18002c6b6  mov     eax, ebx
0x18002c6b8  mov     [rbp+pv], 0
0x18002c6c0  and     eax, 80FF0000h
0x18002c6c5  cmp     eax, 80AA0000h
0x18002c6ca  jnz     short loc_18002C6DA
0x18002c6cc  lea     rdx, CLSID_MsftDiscRecorder2; int
0x18002c6d3  mov     ecx, ebx; dwMessageId
0x18002c6d5  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x18002c6da  mov     eax, ebx
0x18002c6dc  add     rsp, 30h
0x18002c6e0  pop     rdi
0x18002c6e1  pop     rbx
0x18002c6e2  pop     rbp
0x18002c6e3  retn
```
