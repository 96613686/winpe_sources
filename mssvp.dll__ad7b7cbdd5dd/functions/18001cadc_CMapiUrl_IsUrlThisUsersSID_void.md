# CMapiUrl::IsUrlThisUsersSID(void)

- ea: `0x18001cadc`
- end: `0x18001cb57`
- name: `?IsUrlThisUsersSID@CMapiUrl@@QEAAHXZ`
- size: `123`
- prototype: `__int64 __fastcall(CMapiUrl *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c020`
- `0x18001ce70`
- `0x18001f8e0`
- `0x180020f80`

## callees

- `0x18001cadc`
- `0x18002941c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001cb0d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001cb3d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001cb0d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001cb3d`

## pseudocode

```c
_BOOL8 __fastcall CMapiUrl::IsUrlThisUsersSID(PCNZWCH *this)
{
  CMapiUrl::InitFormattedUrlSid();
  return CompareStringW(0x7Fu, 1u, *this, *((_DWORD *)*this - 4), L"mapi", -1) == 2
      && CompareStringW(
           0x7Fu,
           1u,
           this[1],
           *((_DWORD *)this[1] - 4),
           CMapiUrl::s_userSid,
           *((_DWORD *)CMapiUrl::s_userSid - 4)) == 2;
}

```

## disassembly

```asm
0x18001cadc  push    rbx
0x18001cade  sub     rsp, 30h
0x18001cae2  mov     rbx, rcx
0x18001cae5  call    ?InitFormattedUrlSid@CMapiUrl@@CAJXZ; CMapiUrl::InitFormattedUrlSid(void)
0x18001caea  mov     r8, [rbx]; lpString1
0x18001caed  lea     rax, aMapi_0; "mapi"
0x18001caf4  mov     edx, 1; dwCmpFlags
0x18001caf9  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001cb01  mov     [rsp+38h+lpString2], rax; lpString2
0x18001cb06  mov     r9d, [r8-10h]; cchCount1
0x18001cb0a  lea     ecx, [rdx+7Eh]; Locale
0x18001cb0d  call    cs:__imp_CompareStringW
0x18001cb13  cmp     eax, 2
0x18001cb16  jnz     short loc_18001CB4F
0x18001cb18  mov     rax, cs:?s_userSid@CMapiUrl@@0V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@A; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> CMapiUrl::s_userSid
0x18001cb1f  mov     edx, 1; dwCmpFlags
0x18001cb24  mov     r8, [rbx+8]; lpString1
0x18001cb28  mov     r9d, [rax-10h]
0x18001cb2c  lea     ecx, [rdx+7Eh]; Locale
0x18001cb2f  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x18001cb34  mov     r9d, [r8-10h]; cchCount1
0x18001cb38  mov     [rsp+38h+lpString2], rax; lpString2
0x18001cb3d  call    cs:__imp_CompareStringW
0x18001cb43  xor     ecx, ecx
0x18001cb45  cmp     eax, 2
0x18001cb48  setz    cl
0x18001cb4b  mov     eax, ecx
0x18001cb4d  jmp     short loc_18001CB51
0x18001cb4f  xor     eax, eax
0x18001cb51  add     rsp, 30h
0x18001cb55  pop     rbx
0x18001cb56  retn
```
