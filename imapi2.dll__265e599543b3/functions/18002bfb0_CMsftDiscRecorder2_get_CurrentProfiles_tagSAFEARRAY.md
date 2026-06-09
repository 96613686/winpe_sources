# CMsftDiscRecorder2::get_CurrentProfiles(tagSAFEARRAY * *)

- ea: `0x18002bfb0`
- end: `0x18002c117`
- name: `?get_CurrentProfiles@CMsftDiscRecorder2@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
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
- `0x18002bfb0`
- `0x1800436f8`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002c0e3`
- `ole32!CoTaskMemFree` at `0x18002c0e3`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::get_CurrentProfiles(CMsftDiscRecorder2 *this, struct tagSAFEARRAY **a2)
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 249, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    }
    v3 = -2147467261;
    goto LABEL_18;
  }
  *a2 = 0;
  LOBYTE(a2) = 1;
  v3 = (*(__int64 (__fastcall **)(char *, struct tagSAFEARRAY **, LPVOID *, int **))(*((_QWORD *)this + 1) + 128LL))(
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
    v6 = 250;
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
    v6 = 251;
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
0x18002bfb0  push    rbp
0x18002bfb2  push    rbx
0x18002bfb3  push    rdi
0x18002bfb4  mov     rbp, rsp
0x18002bfb7  sub     rsp, 30h
0x18002bfbb  mov     [rbp+arg_18], 0
0x18002bfc3  mov     rdi, rdx
0x18002bfc6  mov     [rbp+pv], 0
0x18002bfce  mov     dword ptr [rbp+arg_8], 0
0x18002bfd5  test    rdx, rdx
0x18002bfd8  jnz     short loc_18002C021
0x18002bfda  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bfe1  lea     rax, WPP_GLOBAL_Control
0x18002bfe8  cmp     rcx, rax
0x18002bfeb  jz      short loc_18002C017
0x18002bfed  test    byte ptr [rcx+0BCh], 4
0x18002bff4  jz      short loc_18002C017
0x18002bff6  cmp     byte ptr [rcx+0B9h], 3
0x18002bffd  jb      short loc_18002C017
0x18002bfff  mov     rcx, [rcx+0B0h]
0x18002c006  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002c00d  mov     edx, 0F9h
0x18002c012  call    WPP_SF_
0x18002c017  mov     ebx, 80004003h
0x18002c01c  jmp     loc_18002C0CD
0x18002c021  mov     qword ptr [rdx], 0
0x18002c028  lea     r9, [rbp+arg_8]
0x18002c02c  add     rcx, 8
0x18002c030  lea     r8, [rbp+pv]
0x18002c034  mov     dl, 1
0x18002c036  mov     rax, [rcx]
0x18002c039  mov     rax, [rax+80h]
0x18002c040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c045  mov     ebx, eax
0x18002c047  test    eax, eax
0x18002c049  jns     short loc_18002C077
0x18002c04b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c052  lea     rax, WPP_GLOBAL_Control
0x18002c059  cmp     rcx, rax
0x18002c05c  jz      short loc_18002C0CD
0x18002c05e  test    byte ptr [rcx+0BCh], 4
0x18002c065  jz      short loc_18002C0CD
0x18002c067  cmp     byte ptr [rcx+0B9h], 3
0x18002c06e  jb      short loc_18002C0CD
0x18002c070  mov     edx, 0FAh
0x18002c075  jmp     short loc_18002C0B7
0x18002c077  mov     edx, dword ptr [rbp+arg_8]; int *
0x18002c07a  lea     r8, [rbp+arg_18]; unsigned int
0x18002c07e  mov     rcx, [rbp+pv]; this
0x18002c082  call    ?CreateVariantSafeArrayFromV1Enums@Imapi2Utility@@YA?BJPEBJKPEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::CreateVariantSafeArrayFromV1Enums(long const *,ulong,tagSAFEARRAY * *)
0x18002c087  mov     ebx, eax
0x18002c089  test    eax, eax
0x18002c08b  jns     short loc_18002C0D8
0x18002c08d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c094  lea     rax, WPP_GLOBAL_Control
0x18002c09b  cmp     rcx, rax
0x18002c09e  jz      short loc_18002C0CD
0x18002c0a0  test    byte ptr [rcx+0BCh], 4
0x18002c0a7  jz      short loc_18002C0CD
0x18002c0a9  cmp     byte ptr [rcx+0B9h], 3
0x18002c0b0  jb      short loc_18002C0CD
0x18002c0b2  mov     edx, 0FBh
0x18002c0b7  mov     rcx, [rcx+0B0h]
0x18002c0be  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002c0c5  mov     r9d, ebx
0x18002c0c8  call    WPP_SF_d
0x18002c0cd  lea     rcx, [rbp+arg_18]; this
0x18002c0d1  call    ?SafeArrayDestroyAndNull@Imapi2Utility@@YAXAEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::SafeArrayDestroyAndNull(tagSAFEARRAY * &)
0x18002c0d6  jmp     short loc_18002C0DF
0x18002c0d8  mov     rax, [rbp+arg_18]
0x18002c0dc  mov     [rdi], rax
0x18002c0df  mov     rcx, [rbp+pv]; pv
0x18002c0e3  call    cs:__imp_CoTaskMemFree
0x18002c0e9  mov     eax, ebx
0x18002c0eb  mov     [rbp+pv], 0
0x18002c0f3  and     eax, 80FF0000h
0x18002c0f8  cmp     eax, 80AA0000h
0x18002c0fd  jnz     short loc_18002C10D
0x18002c0ff  lea     rdx, CLSID_MsftDiscRecorder2; int
0x18002c106  mov     ecx, ebx; dwMessageId
0x18002c108  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x18002c10d  mov     eax, ebx
0x18002c10f  add     rsp, 30h
0x18002c113  pop     rdi
0x18002c114  pop     rbx
0x18002c115  pop     rbp
0x18002c116  retn
```
