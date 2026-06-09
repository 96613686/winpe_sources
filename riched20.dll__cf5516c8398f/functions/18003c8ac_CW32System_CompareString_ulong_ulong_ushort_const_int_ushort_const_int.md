# CW32System::CompareString(ulong,ulong,ushort const *,int,ushort const *,int)

- ea: `0x18003c8ac`
- end: `0x18003c98f`
- name: `?CompareString@CW32System@@SAHKKPEBGH0H@Z`
- size: `227`
- prototype: `__int64 __fastcall(LCID Locale, DWORD dwCmpFlags, const unsigned __int16 *, int, PCNZWCH, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800664d8`
- `0x180066638`

## callees

- `0x18003c8ac`
- `0x18008cc28`
- `0x18008dbbc`
- `0x180091140`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18003c8f5`
- `KERNEL32!CompareStringW` at `0x18003c8f5`
- `KERNEL32!CompareStringA` at `0x18003c969`
- `KERNEL32!CompareStringA` at `0x18003c969`

## pseudocode

```c
int __fastcall CW32System::CompareString(
        LCID Locale,
        DWORD dwCmpFlags,
        const unsigned __int16 *a3,
        int a4,
        PCNZWCH lpString2,
        int cchCount2)
{
  int v9; // ebx
  PCNZCH v10[66]; // [rsp+30h] [rbp-478h] BYREF
  int v11; // [rsp+240h] [rbp-268h]
  PCNZCH lpString1[66]; // [rsp+250h] [rbp-258h] BYREF
  int cchCount1; // [rsp+460h] [rbp-48h]

  if ( CW32System::_dwPlatformId != 1 )
    return CompareStringW(Locale, dwCmpFlags, a3, a4, lpString2, cchCount2);
  CStrIn::CStrIn((CStrIn *)lpString1, a3, a4, 0);
  CStrIn::CStrIn((CStrIn *)v10, lpString2, cchCount2, 0);
  v9 = CompareStringA(Locale, dwCmpFlags, lpString1[0], cchCount1, v10[0], v11);
  CConvertStr::Free((CConvertStr *)v10);
  CConvertStr::Free((CConvertStr *)lpString1);
  return v9;
}

```

## disassembly

```asm
0x18003c8ac  push    rbx
0x18003c8ae  push    rbp
0x18003c8af  push    rsi
0x18003c8b0  push    rdi
0x18003c8b1  sub     rsp, 488h
0x18003c8b8  mov     rax, cs:__security_cookie
0x18003c8bf  xor     rax, rsp
0x18003c8c2  mov     [rsp+4A8h+var_38], rax
0x18003c8ca  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x18003c8d1  mov     r10d, r9d
0x18003c8d4  mov     rsi, [rsp+4A8h+arg_20]
0x18003c8dc  mov     rax, r8
0x18003c8df  mov     ebp, [rsp+4A8h+arg_28]
0x18003c8e6  mov     edi, edx
0x18003c8e8  mov     ebx, ecx
0x18003c8ea  jz      short loc_18003C917
0x18003c8ec  mov     [rsp+4A8h+cchCount2], ebp; cchCount2
0x18003c8f0  mov     [rsp+4A8h+lpString2], rsi; lpString2
0x18003c8f5  call    cs:__imp_CompareStringW
0x18003c8fb  mov     rcx, [rsp+4A8h+var_38]
0x18003c903  xor     rcx, rsp; StackCookie
0x18003c906  call    __security_check_cookie
0x18003c90b  add     rsp, 488h
0x18003c912  pop     rdi
0x18003c913  pop     rsi
0x18003c914  pop     rbp
0x18003c915  pop     rbx
0x18003c916  retn
0x18003c917  xor     r9d, r9d; unsigned int
0x18003c91a  lea     rcx, [rsp+4A8h+lpString1]; this
0x18003c922  mov     r8d, r10d; int
0x18003c925  mov     rdx, rax; unsigned __int16 *
0x18003c928  call    ??0CStrIn@@QEAA@PEBGHI@Z; CStrIn::CStrIn(ushort const *,int,uint)
0x18003c92d  xor     r9d, r9d; unsigned int
0x18003c930  lea     rcx, [rsp+4A8h+var_478]; this
0x18003c935  mov     r8d, ebp; int
0x18003c938  mov     rdx, rsi; unsigned __int16 *
0x18003c93b  call    ??0CStrIn@@QEAA@PEBGHI@Z; CStrIn::CStrIn(ushort const *,int,uint)
0x18003c940  mov     rcx, [rsp+4A8h+var_478]
0x18003c945  mov     edx, edi; dwCmpFlags
0x18003c947  mov     eax, [rsp+4A8h+var_268]
0x18003c94e  mov     r9d, [rsp+4A8h+cchCount1]; cchCount1
0x18003c956  mov     r8, [rsp+4A8h+lpString1]; lpString1
0x18003c95e  mov     [rsp+4A8h+cchCount2], eax; cchCount2
0x18003c962  mov     [rsp+4A8h+lpString2], rcx; lpString2
0x18003c967  mov     ecx, ebx; Locale
0x18003c969  call    cs:__imp_CompareStringA
0x18003c96f  lea     rcx, [rsp+4A8h+var_478]; this
0x18003c974  mov     ebx, eax
0x18003c976  call    ?Free@CConvertStr@@IEAAXXZ; CConvertStr::Free(void)
0x18003c97b  lea     rcx, [rsp+4A8h+lpString1]; this
0x18003c983  call    ?Free@CConvertStr@@IEAAXXZ; CConvertStr::Free(void)
0x18003c988  mov     eax, ebx
0x18003c98a  jmp     loc_18003C8FB
```
