# SpGetInfo(_SecPkgInfoW *)

- ea: `0x180018990`
- end: `0x1800189bf`
- name: `?SpGetInfo@@YAJPEAU_SecPkgInfoW@@@Z`
- size: `47`
- prototype: `__int64 __fastcall(struct _SecPkgInfoW *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x1800189b1`: `PKU2U Security Package`

## pseudocode

```c
__int64 __fastcall SpGetInfo(struct _SecPkgInfoW *a1)
{
  *(_DWORD *)&a1->wVersion = 2031617;
  a1->fCapabilities = 10555667;
  a1->cbMaxToken = Pku2uGlobalMaxTokenSize;
  a1->Name = (SEC_WCHAR *)L"pku2u";
  a1->Comment = L"PKU2U Security Package";
  return 0;
}

```

## disassembly

```asm
0x180018990  mov     dword ptr [rcx+4], 1F0001h
0x180018997  mov     dword ptr [rcx], 0A11113h
0x18001899d  mov     eax, cs:?Pku2uGlobalMaxTokenSize@@3KA; ulong Pku2uGlobalMaxTokenSize
0x1800189a3  mov     [rcx+8], eax
0x1800189a6  lea     rax, pszPackageName; "pku2u"
0x1800189ad  mov     [rcx+10h], rax
0x1800189b1  lea     rax, aPku2uSecurityP; "PKU2U Security Package"
0x1800189b8  mov     [rcx+18h], rax
0x1800189bc  xor     eax, eax
0x1800189be  retn
```
