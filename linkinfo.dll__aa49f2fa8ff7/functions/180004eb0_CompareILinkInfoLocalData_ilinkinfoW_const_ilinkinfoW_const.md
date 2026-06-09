# CompareILinkInfoLocalData(_ilinkinfoW const *,_ilinkinfoW const *)

- ea: `0x180004eb0`
- end: `0x180004f3d`
- name: `?CompareILinkInfoLocalData@@YA?AW4_comparisonresult@@PEBU_ilinkinfoW@@0@Z`
- size: `141`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000535c`
- `0x1800053f0`

## callees

- `0x1800019e0`
- `0x180003470`
- `0x180004e98`
- `0x180004eb0`
- `0x180005750`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004f10`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004f10`

## pseudocode

```c
__int64 __fastcall CompareILinkInfoLocalData(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  const struct _ilinkinfoW *v4; // r8
  int v5; // r8d
  unsigned int v6; // eax
  WCHAR String2[264]; // [rsp+20h] [rbp-438h] BYREF
  WCHAR String1[264]; // [rsp+230h] [rbp-228h] BYREF

  result = CompareVolumeIDs(a1 + *(unsigned int *)(a1 + 12), a2 + *(unsigned int *)(a2 + 12));
  if ( !(_DWORD)result )
  {
    GetLocalPathFromILinkInfo(v4, String1, (int)v4);
    GetLocalPathFromILinkInfo((const struct _ilinkinfoW *)a2, String2, v5);
    v6 = lstrcmpiW(String1, String2);
    return MapIntToComparisonResult(v6);
  }
  return result;
}

```

## disassembly

```asm
0x180004eb0  push    rbx
0x180004eb2  sub     rsp, 450h
0x180004eb9  mov     rax, cs:__security_cookie
0x180004ec0  xor     rax, rsp
0x180004ec3  mov     [rsp+458h+var_18], rax
0x180004ecb  mov     rbx, rdx
0x180004ece  mov     r8, rcx
0x180004ed1  mov     edx, [rdx+0Ch]
0x180004ed4  mov     ecx, [rcx+0Ch]
0x180004ed7  add     rdx, rbx
0x180004eda  add     rcx, r8
0x180004edd  call    ?CompareVolumeIDs@@YA?AW4_comparisonresult@@PEBU_volumeid@@0@Z; CompareVolumeIDs(_volumeid const *,_volumeid const *)
0x180004ee2  test    eax, eax
0x180004ee4  jnz     short loc_180004F23
0x180004ee6  lea     rdx, [rsp+458h+String1]; unsigned __int16 *
0x180004eee  mov     rcx, r8; struct _ilinkinfoW *
0x180004ef1  call    ?GetLocalPathFromILinkInfo@@YAXPEBU_ilinkinfoW@@PEAGH@Z; GetLocalPathFromILinkInfo(_ilinkinfoW const *,ushort *,int)
0x180004ef6  lea     rdx, [rsp+458h+String2]; unsigned __int16 *
0x180004efb  mov     rcx, rbx; struct _ilinkinfoW *
0x180004efe  call    ?GetLocalPathFromILinkInfo@@YAXPEBU_ilinkinfoW@@PEAGH@Z; GetLocalPathFromILinkInfo(_ilinkinfoW const *,ushort *,int)
0x180004f03  lea     rdx, [rsp+458h+String2]; lpString2
0x180004f08  lea     rcx, [rsp+458h+String1]; lpString1
0x180004f10  call    cs:__imp_lstrcmpiW
0x180004f17  nop     dword ptr [rax+rax+00h]
0x180004f1c  mov     ecx, eax
0x180004f1e  call    ?MapIntToComparisonResult@@YA?AW4_comparisonresult@@H@Z; MapIntToComparisonResult(int)
0x180004f23  mov     rcx, [rsp+458h+var_18]
0x180004f2b  xor     rcx, rsp; StackCookie
0x180004f2e  call    __security_check_cookie
0x180004f33  add     rsp, 450h
0x180004f3a  pop     rbx
0x180004f3b  retn
```
