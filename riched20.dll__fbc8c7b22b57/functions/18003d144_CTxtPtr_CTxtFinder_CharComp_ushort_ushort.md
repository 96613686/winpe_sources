# CTxtPtr::CTxtFinder::CharComp(ushort,ushort)

- ea: `0x18003d144`
- end: `0x18003d277`
- name: `?CharComp@CTxtFinder@CTxtPtr@@AEBAHGG@Z`
- size: `307`
- prototype: `__int64 __fastcall(CTxtPtr::CTxtFinder *__hidden this, unsigned __int16, unsigned __int16)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180084000`
- `0x180084070`

## callees

- `0x18003d144`
- `0x18008f3bc`
- `0x1800903d4`
- `0x180093c00`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18003d1b7`
- `KERNEL32!CompareStringW` at `0x18003d1b7`
- `KERNEL32!CompareStringA` at `0x18003d24e`
- `KERNEL32!CompareStringA` at `0x18003d24e`

## pseudocode

```c
bool __fastcall CTxtPtr::CTxtFinder::CharComp(CTxtPtr::CTxtFinder *this, WCHAR a2, WCHAR a3)
{
  int v3; // ebx
  WCHAR String1; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR String2; // [rsp+38h] [rbp-C8h] BYREF
  PCNZCH lpString2[66]; // [rsp+40h] [rbp-C0h] BYREF
  int cchCount2; // [rsp+250h] [rbp+150h]
  PCNZCH lpString1[66]; // [rsp+260h] [rbp+160h] BYREF
  int cchCount1; // [rsp+470h] [rbp+370h]

  if ( !*((_DWORD *)this + 2) || (unsigned int)a2 - 55296 <= 0x7FF )
    return a2 == a3;
  String2 = a3;
  String1 = a2;
  if ( CW32System::_dwPlatformId == 1 )
  {
    CStrIn::CStrIn((CStrIn *)lpString1, &String1, 1, 0);
    CStrIn::CStrIn((CStrIn *)lpString2, &String2, 1, 0);
    v3 = CompareStringA(0x400u, 0x20001u, lpString1[0], cchCount1, lpString2[0], cchCount2);
    CConvertStr::Free((CConvertStr *)lpString2);
    CConvertStr::Free((CConvertStr *)lpString1);
  }
  else
  {
    v3 = CompareStringW(0x400u, 0x20001u, &String1, 1, &String2, 1);
  }
  return v3 == 2;
}

```

## disassembly

```asm
0x18003d144  mov     [rsp-8+arg_0], rbx
0x18003d149  push    rbp
0x18003d14a  lea     rbp, [rsp-390h]
0x18003d152  sub     rsp, 490h
0x18003d159  mov     rax, cs:__security_cookie
0x18003d160  xor     rax, rsp
0x18003d163  mov     [rbp+390h+var_10], rax
0x18003d16a  cmp     dword ptr [rcx+8], 0
0x18003d16e  jz      short loc_18003D1EE
0x18003d170  movzx   eax, dx
0x18003d173  sub     eax, 0D800h
0x18003d178  cmp     eax, 7FFh
0x18003d17d  jbe     short loc_18003D1EE
0x18003d17f  mov     ebx, 1
0x18003d184  mov     [rsp+490h+String2], r8w
0x18003d18a  cmp     cs:?_dwPlatformId@CW32System@@0KA, ebx; ulong CW32System::_dwPlatformId
0x18003d190  mov     [rsp+490h+String1], dx
0x18003d195  jz      short loc_18003D1F6
0x18003d197  lea     rax, [rsp+490h+String2]
0x18003d19c  mov     [rsp+490h+cchCount2], ebx; cchCount2
0x18003d1a0  mov     r9d, ebx; cchCount1
0x18003d1a3  mov     [rsp+490h+lpString2], rax; lpString2
0x18003d1a8  lea     r8, [rsp+490h+String1]; lpString1
0x18003d1ad  mov     edx, 20001h; dwCmpFlags
0x18003d1b2  mov     ecx, 400h; Locale
0x18003d1b7  call    cs:__imp_CompareStringW
0x18003d1be  nop     dword ptr [rax+rax+00h]
0x18003d1c3  mov     ebx, eax
0x18003d1c5  xor     eax, eax
0x18003d1c7  cmp     ebx, 2
0x18003d1ca  setz    al
0x18003d1cd  mov     rcx, [rbp+390h+var_10]
0x18003d1d4  xor     rcx, rsp; StackCookie
0x18003d1d7  call    __security_check_cookie
0x18003d1dc  mov     rbx, [rsp+490h+arg_0]
0x18003d1e4  add     rsp, 490h
0x18003d1eb  pop     rbp
0x18003d1ec  retn
0x18003d1ee  xor     eax, eax
0x18003d1f0  cmp     dx, r8w
0x18003d1f4  jmp     short loc_18003D1CA
0x18003d1f6  xor     r9d, r9d; unsigned int
0x18003d1f9  lea     rdx, [rsp+490h+String1]; unsigned __int16 *
0x18003d1fe  mov     r8d, ebx; int
0x18003d201  lea     rcx, [rbp+390h+lpString1]; this
0x18003d208  call    ??0CStrIn@@QEAA@PEBGHI@Z; CStrIn::CStrIn(ushort const *,int,uint)
0x18003d20d  xor     r9d, r9d; unsigned int
0x18003d210  lea     rdx, [rsp+490h+String2]; unsigned __int16 *
0x18003d215  mov     r8d, ebx; int
0x18003d218  lea     rcx, [rsp+490h+var_450]; this
0x18003d21d  call    ??0CStrIn@@QEAA@PEBGHI@Z; CStrIn::CStrIn(ushort const *,int,uint)
0x18003d222  mov     rcx, [rsp+490h+var_450]
0x18003d227  mov     edx, 20001h; dwCmpFlags
0x18003d22c  mov     eax, [rbp+390h+var_240]
0x18003d232  mov     r9d, [rbp+390h+cchCount1]; cchCount1
0x18003d239  mov     r8, [rbp+390h+lpString1]; lpString1
0x18003d240  mov     [rsp+490h+cchCount2], eax; cchCount2
0x18003d244  mov     [rsp+490h+lpString2], rcx; lpString2
0x18003d249  mov     ecx, 400h; Locale
0x18003d24e  call    cs:__imp_CompareStringA
0x18003d255  nop     dword ptr [rax+rax+00h]
0x18003d25a  lea     rcx, [rsp+490h+var_450]; this
0x18003d25f  mov     ebx, eax
0x18003d261  call    ?Free@CConvertStr@@IEAAXXZ; CConvertStr::Free(void)
0x18003d266  lea     rcx, [rbp+390h+lpString1]; this
0x18003d26d  call    ?Free@CConvertStr@@IEAAXXZ; CConvertStr::Free(void)
0x18003d272  jmp     loc_18003D1C5
```
