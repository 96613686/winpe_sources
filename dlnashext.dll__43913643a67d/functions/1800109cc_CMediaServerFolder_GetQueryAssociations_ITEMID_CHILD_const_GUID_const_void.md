# CMediaServerFolder::_GetQueryAssociations(_ITEMID_CHILD const *,_GUID const &,void * *)

- ea: `0x1800109cc`
- end: `0x180010a82`
- name: `?_GetQueryAssociations@CMediaServerFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z`
- size: `182`
- prototype: `int(CMediaServerFolder *__hidden this, const struct _ITEMID_CHILD *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800108c0`

## callees

- `0x1800109cc`

## import_xrefs

- `api-ms-win-shell-associations-l1-1-0!AssocCreateForClasses` at `0x180010a5d`
- `api-ms-win-shell-associations-l1-1-0!AssocCreateForClasses` at `0x180010a5d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010a20`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010a20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010a6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010a6f`

## string_xrefs

- `0x180010a01`: `Media Servers\Common`

## pseudocode

```c
__int64 __fastcall CMediaServerFolder::_GetQueryAssociations(
        CMediaServerFolder *this,
        const struct _ITEMID_CHILD *a2,
        const struct _GUID *a3,
        void **a4)
{
  LSTATUS v6; // eax
  signed int v7; // edx
  unsigned int v8; // ebx
  __int128 rgClasses; // [rsp+30h] [rbp-38h] BYREF
  __int128 rgClasses_16; // [rsp+40h] [rbp-28h]
  __int128 v12; // [rsp+50h] [rbp-18h]
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  hKey = 0;
  rgClasses = 0;
  LODWORD(rgClasses) = 8;
  rgClasses_16 = 0;
  v12 = 0;
  v6 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Media Servers\\Common", 0, 0x20019u, &hKey);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 >= 0 )
  {
    *(_QWORD *)&v12 = hKey;
    DWORD2(rgClasses_16) = 5;
  }
  v8 = AssocCreateForClasses((const ASSOCIATIONELEMENT *)&rgClasses, (v7 >= 0) + 1, a3, a4);
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x1800109cc  mov     rax, rsp
0x1800109cf  mov     [rax+8], rbx
0x1800109d3  mov     [rax+10h], rdx
0x1800109d7  push    rdi
0x1800109d8  sub     rsp, 60h
0x1800109dc  xorps   xmm0, xmm0
0x1800109df  mov     qword ptr [rax+10h], 0
0x1800109e7  movups  xmmword ptr [rax-38h], xmm0
0x1800109eb  mov     dword ptr [rax-38h], 8
0x1800109f2  mov     rbx, r9
0x1800109f5  mov     rdi, r8
0x1800109f8  mov     r9d, 20019h; samDesired
0x1800109fe  xor     r8d, r8d; ulOptions
0x180010a01  lea     rdx, SubKey; "Media Servers\\Common"
0x180010a08  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180010a0f  movups  xmmword ptr [rax-28h], xmm0
0x180010a13  movups  xmmword ptr [rax-18h], xmm0
0x180010a17  lea     rax, [rax+10h]
0x180010a1b  mov     [rsp+68h+phkResult], rax; phkResult
0x180010a20  call    cs:__imp_RegOpenKeyExW
0x180010a26  mov     edx, eax
0x180010a28  test    eax, eax
0x180010a2a  jle     short loc_180010A35
0x180010a2c  movzx   edx, ax
0x180010a2f  or      edx, 80070000h
0x180010a35  test    edx, edx
0x180010a37  js      short loc_180010A4B
0x180010a39  mov     rax, [rsp+68h+hKey]
0x180010a3e  mov     qword ptr [rsp+68h+var_18], rax
0x180010a43  mov     [rsp+68h+var_20], 5
0x180010a4b  not     edx
0x180010a4d  lea     rcx, [rsp+68h+rgClasses]; rgClasses
0x180010a52  shr     edx, 1Fh
0x180010a55  mov     r9, rbx; ppv
0x180010a58  inc     edx; cClasses
0x180010a5a  mov     r8, rdi; riid
0x180010a5d  call    cs:__imp_AssocCreateForClasses
0x180010a63  mov     rcx, [rsp+68h+hKey]; hKey
0x180010a68  mov     ebx, eax
0x180010a6a  test    rcx, rcx
0x180010a6d  jz      short loc_180010A75
0x180010a6f  call    cs:__imp_RegCloseKey
0x180010a75  mov     eax, ebx
0x180010a77  mov     rbx, [rsp+68h+arg_0]
0x180010a7c  add     rsp, 60h
0x180010a80  pop     rdi
0x180010a81  retn
```
