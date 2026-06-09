# CMsftDiscRecorder2::get_SupportedModePages(tagSAFEARRAY * *)

- ea: `0x18002c6f0`
- end: `0x18002c857`
- name: `?get_SupportedModePages@CMsftDiscRecorder2@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
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
- `0x18002c6f0`
- `0x1800436f8`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002c823`
- `ole32!CoTaskMemFree` at `0x18002c823`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::get_SupportedModePages(CMsftDiscRecorder2 *this, struct tagSAFEARRAY **a2)
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 252, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    }
    v3 = -2147467261;
    goto LABEL_18;
  }
  *a2 = 0;
  v3 = (*(__int64 (__fastcall **)(char *, _QWORD, LPVOID *, int **))(*((_QWORD *)this + 1) + 136LL))(
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
    v6 = 253;
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
    v6 = 254;
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
0x18002c6f0  push    rbp
0x18002c6f2  push    rbx
0x18002c6f3  push    rdi
0x18002c6f4  mov     rbp, rsp
0x18002c6f7  sub     rsp, 30h
0x18002c6fb  mov     [rbp+arg_18], 0
0x18002c703  mov     rdi, rdx
0x18002c706  mov     [rbp+pv], 0
0x18002c70e  mov     dword ptr [rbp+arg_8], 0
0x18002c715  test    rdx, rdx
0x18002c718  jnz     short loc_18002C761
0x18002c71a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c721  lea     rax, WPP_GLOBAL_Control
0x18002c728  cmp     rcx, rax
0x18002c72b  jz      short loc_18002C757
0x18002c72d  test    byte ptr [rcx+0BCh], 4
0x18002c734  jz      short loc_18002C757
0x18002c736  cmp     byte ptr [rcx+0B9h], 3
0x18002c73d  jb      short loc_18002C757
0x18002c73f  mov     rcx, [rcx+0B0h]
0x18002c746  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002c74d  mov     edx, 0FCh
0x18002c752  call    WPP_SF_
0x18002c757  mov     ebx, 80004003h
0x18002c75c  jmp     loc_18002C80D
0x18002c761  mov     qword ptr [rdx], 0
0x18002c768  lea     r9, [rbp+arg_8]
0x18002c76c  add     rcx, 8
0x18002c770  lea     r8, [rbp+pv]
0x18002c774  xor     edx, edx
0x18002c776  mov     rax, [rcx]
0x18002c779  mov     rax, [rax+88h]
0x18002c780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c785  mov     ebx, eax
0x18002c787  test    eax, eax
0x18002c789  jns     short loc_18002C7B7
0x18002c78b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c792  lea     rax, WPP_GLOBAL_Control
0x18002c799  cmp     rcx, rax
0x18002c79c  jz      short loc_18002C80D
0x18002c79e  test    byte ptr [rcx+0BCh], 4
0x18002c7a5  jz      short loc_18002C80D
0x18002c7a7  cmp     byte ptr [rcx+0B9h], 3
0x18002c7ae  jb      short loc_18002C80D
0x18002c7b0  mov     edx, 0FDh
0x18002c7b5  jmp     short loc_18002C7F7
0x18002c7b7  mov     edx, dword ptr [rbp+arg_8]; int *
0x18002c7ba  lea     r8, [rbp+arg_18]; unsigned int
0x18002c7be  mov     rcx, [rbp+pv]; this
0x18002c7c2  call    ?CreateVariantSafeArrayFromV1Enums@Imapi2Utility@@YA?BJPEBJKPEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::CreateVariantSafeArrayFromV1Enums(long const *,ulong,tagSAFEARRAY * *)
0x18002c7c7  mov     ebx, eax
0x18002c7c9  test    eax, eax
0x18002c7cb  jns     short loc_18002C818
0x18002c7cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c7d4  lea     rax, WPP_GLOBAL_Control
0x18002c7db  cmp     rcx, rax
0x18002c7de  jz      short loc_18002C80D
0x18002c7e0  test    byte ptr [rcx+0BCh], 4
0x18002c7e7  jz      short loc_18002C80D
0x18002c7e9  cmp     byte ptr [rcx+0B9h], 3
0x18002c7f0  jb      short loc_18002C80D
0x18002c7f2  mov     edx, 0FEh
0x18002c7f7  mov     rcx, [rcx+0B0h]
0x18002c7fe  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002c805  mov     r9d, ebx
0x18002c808  call    WPP_SF_d
0x18002c80d  lea     rcx, [rbp+arg_18]; this
0x18002c811  call    ?SafeArrayDestroyAndNull@Imapi2Utility@@YAXAEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::SafeArrayDestroyAndNull(tagSAFEARRAY * &)
0x18002c816  jmp     short loc_18002C81F
0x18002c818  mov     rax, [rbp+arg_18]
0x18002c81c  mov     [rdi], rax
0x18002c81f  mov     rcx, [rbp+pv]; pv
0x18002c823  call    cs:__imp_CoTaskMemFree
0x18002c829  mov     eax, ebx
0x18002c82b  mov     [rbp+pv], 0
0x18002c833  and     eax, 80FF0000h
0x18002c838  cmp     eax, 80AA0000h
0x18002c83d  jnz     short loc_18002C84D
0x18002c83f  lea     rdx, CLSID_MsftDiscRecorder2; int
0x18002c846  mov     ecx, ebx; dwMessageId
0x18002c848  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x18002c84d  mov     eax, ebx
0x18002c84f  add     rsp, 30h
0x18002c853  pop     rdi
0x18002c854  pop     rbx
0x18002c855  pop     rbp
0x18002c856  retn
```
