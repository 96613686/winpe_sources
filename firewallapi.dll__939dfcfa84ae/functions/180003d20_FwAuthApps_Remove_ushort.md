# FwAuthApps::Remove(ushort *)

- ea: `0x180003d20`
- end: `0x180003e54`
- name: `?Remove@FwAuthApps@@UEAAJPEAG@Z`
- size: `308`
- prototype: `int(FwAuthApps *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callees

- `0x1800037dc`
- `0x180003d20`
- `0x180003e5c`
- `0x18000d0f0`
- `0x1800294b0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180003d5c`
- `OLEAUT32!__imp_SysStringLen` at `0x180003d5c`
- `fwbase!FwBaseFree` at `0x180003e08`
- `fwbase!FwBaseFree` at `0x180003e08`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x180003d82`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x180003d82`
- `fwbase!FwReportReturnError` at `0x180003df7`
- `fwbase!FwReportReturnError` at `0x180003e2b`
- `fwbase!FwReportReturnError` at `0x180003df7`
- `fwbase!FwReportReturnError` at `0x180003e2b`

## string_xrefs

- `0x180003df0`: `FwAuthApps::Remove`
- `0x180003e24`: `FwAuthApps::Remove`

## pseudocode

```c
__int64 __fastcall FwAuthApps::Remove(FwAuthApps *this, unsigned __int16 *a2)
{
  signed int v4; // ebx
  __int64 v5; // rdx
  int ExpandedCanonicalLongPathName; // eax
  int v7; // eax
  __int64 v9; // [rsp+30h] [rbp-28h] BYREF
  void *v10; // [rsp+38h] [rbp-20h] BYREF
  int v11; // [rsp+40h] [rbp-18h] BYREF

  v11 = 0;
  v9 = 0;
  v10 = 0;
  if ( SysStringLen(a2) )
  {
    ExpandedCanonicalLongPathName = FwGetExpandedCanonicalLongPathName(a2, &v9, &v11);
    v4 = ExpandedCanonicalLongPathName;
    if ( ExpandedCanonicalLongPathName >= 0 )
    {
      if ( !v11 )
        goto LABEL_12;
      v7 = FWOpenPolicyStore(0x221u, 0, 2u, 2u, 0, &v10);
      v4 = v7;
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
      if ( v4 < 0 )
        goto LABEL_3;
      ExpandedCanonicalLongPathName = DeleteAllMatchingAuthAppRules((__int64)v10, v9, *((_DWORD *)this + 6));
      v4 = ExpandedCanonicalLongPathName;
      if ( ExpandedCanonicalLongPathName >= 0 )
        goto LABEL_12;
    }
    v5 = (unsigned int)ExpandedCanonicalLongPathName;
    goto LABEL_11;
  }
  v4 = -2147024809;
LABEL_3:
  v5 = (unsigned int)v4;
LABEL_11:
  FwReportReturnError("FwAuthApps::Remove", v5);
LABEL_12:
  FwBaseFree(v9);
  CloseLocalPolicyStore(v10);
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwAuthApps::Remove", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180003d20  mov     [rsp+arg_10], rbx
0x180003d25  push    rdi
0x180003d26  sub     rsp, 50h
0x180003d2a  mov     rax, cs:__security_cookie
0x180003d31  xor     rax, rsp
0x180003d34  mov     [rsp+58h+var_10], rax
0x180003d39  mov     rdi, rcx
0x180003d3c  mov     [rsp+58h+var_18], 0
0x180003d44  mov     rcx, rdx; pbstr
0x180003d47  mov     [rsp+58h+var_28], 0
0x180003d50  mov     rbx, rdx
0x180003d53  mov     [rsp+58h+var_20], 0
0x180003d5c  call    cs:__imp_SysStringLen
0x180003d63  nop     dword ptr [rax+rax+00h]
0x180003d68  test    eax, eax
0x180003d6a  jnz     short loc_180003D75
0x180003d6c  mov     ebx, 80070057h
0x180003d71  mov     edx, ebx
0x180003d73  jmp     short loc_180003DF0
0x180003d75  lea     r8, [rsp+58h+var_18]
0x180003d7a  mov     rcx, rbx
0x180003d7d  lea     rdx, [rsp+58h+var_28]
0x180003d82  call    cs:__imp_FwGetExpandedCanonicalLongPathName
0x180003d89  nop     dword ptr [rax+rax+00h]
0x180003d8e  mov     ebx, eax
0x180003d90  test    eax, eax
0x180003d92  js      short loc_180003DEE
0x180003d94  cmp     [rsp+58h+var_18], 0
0x180003d99  jz      short loc_180003E03
0x180003d9b  lea     rax, [rsp+58h+var_20]
0x180003da0  mov     r8d, 2
0x180003da6  mov     [rsp+58h+var_30], rax
0x180003dab  mov     r9d, r8d
0x180003dae  mov     ecx, 221h
0x180003db3  mov     [rsp+58h+var_38], 0
0x180003dbb  xor     edx, edx
0x180003dbd  call    FWOpenPolicyStore
0x180003dc2  mov     ebx, eax
0x180003dc4  test    eax, eax
0x180003dc6  jle     short loc_180003DD1
0x180003dc8  movzx   ebx, ax
0x180003dcb  or      ebx, 80070000h
0x180003dd1  test    ebx, ebx
0x180003dd3  js      short loc_180003D71
0x180003dd5  mov     r8d, [rdi+18h]
0x180003dd9  mov     rdx, [rsp+58h+var_28]
0x180003dde  mov     rcx, [rsp+58h+var_20]
0x180003de3  call    ?DeleteAllMatchingAuthAppRules@@YAJPEAXPEAGW4_tag_FW_PROFILE_TYPE@@@Z; DeleteAllMatchingAuthAppRules(void *,ushort *,_tag_FW_PROFILE_TYPE)
0x180003de8  mov     ebx, eax
0x180003dea  test    eax, eax
0x180003dec  jns     short loc_180003E03
0x180003dee  mov     edx, eax
0x180003df0  lea     rcx, aFwauthappsRemo; "FwAuthApps::Remove"
0x180003df7  call    cs:__imp_FwReportReturnError
0x180003dfe  nop     dword ptr [rax+rax+00h]
0x180003e03  mov     rcx, [rsp+58h+var_28]
0x180003e08  call    cs:__imp_FwBaseFree
0x180003e0f  nop     dword ptr [rax+rax+00h]
0x180003e14  mov     rcx, [rsp+58h+var_20]; void *
0x180003e19  call    ?CloseLocalPolicyStore@@YAXPEAX@Z; CloseLocalPolicyStore(void *)
0x180003e1e  test    ebx, ebx
0x180003e20  jns     short loc_180003E39
0x180003e22  mov     edx, ebx
0x180003e24  lea     rcx, aFwauthappsRemo; "FwAuthApps::Remove"
0x180003e2b  call    cs:__imp_FwReportReturnError
0x180003e32  nop     dword ptr [rax+rax+00h]
0x180003e37  mov     ebx, eax
0x180003e39  mov     eax, ebx
0x180003e3b  mov     rcx, [rsp+58h+var_10]
0x180003e40  xor     rcx, rsp; StackCookie
0x180003e43  call    __security_check_cookie
0x180003e48  mov     rbx, [rsp+58h+arg_10]
0x180003e4d  add     rsp, 50h
0x180003e51  pop     rdi
0x180003e52  retn
```
