# CW32System::CompareString(ulong,ulong,ushort const *,int,ushort const *,int)

- ea: `0x18003d5bc`
- end: `0x18003d6ac`
- name: `?CompareString@CW32System@@SAHKKPEBGH0H@Z`
- size: `240`
- prototype: `__int64 __fastcall(LCID Locale, DWORD dwCmpFlags, const unsigned __int16 *, int, PCNZWCH, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180067fb8`
- `0x180068118`

## callees

- `0x18003d5bc`
- `0x18008f3bc`
- `0x1800903d4`
- `0x180093c00`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18003d605`
- `KERNEL32!CompareStringW` at `0x18003d605`
- `KERNEL32!CompareStringA` at `0x18003d680`
- `KERNEL32!CompareStringA` at `0x18003d680`

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
0x18003d5bc  push    rbx
0x18003d5be  push    rbp
0x18003d5bf  push    rsi
0x18003d5c0  push    rdi
0x18003d5c1  sub     rsp, 488h
0x18003d5c8  mov     rax, cs:__security_cookie
0x18003d5cf  xor     rax, rsp
0x18003d5d2  mov     [rsp+4A8h+var_38], rax
0x18003d5da  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x18003d5e1  mov     r10d, r9d
0x18003d5e4  mov     rsi, [rsp+4A8h+arg_20]
0x18003d5ec  mov     rax, r8
0x18003d5ef  mov     ebp, [rsp+4A8h+arg_28]
0x18003d5f6  mov     edi, edx
0x18003d5f8  mov     ebx, ecx
0x18003d5fa  jz      short loc_18003D62E
0x18003d5fc  mov     [rsp+4A8h+cchCount2], ebp; cchCount2
0x18003d600  mov     [rsp+4A8h+lpString2], rsi; lpString2
0x18003d605  call    cs:__imp_CompareStringW
0x18003d60c  nop     dword ptr [rax+rax+00h]
0x18003d611  mov     rcx, [rsp+4A8h+var_38]
0x18003d619  xor     rcx, rsp; StackCookie
0x18003d61c  call    __security_check_cookie
0x18003d621  add     rsp, 488h
0x18003d628  pop     rdi
0x18003d629  pop     rsi
0x18003d62a  pop     rbp
0x18003d62b  pop     rbx
0x18003d62c  retn
0x18003d62e  xor     r9d, r9d; unsigned int
0x18003d631  lea     rcx, [rsp+4A8h+lpString1]; this
0x18003d639  mov     r8d, r10d; int
0x18003d63c  mov     rdx, rax; unsigned __int16 *
0x18003d63f  call    ??0CStrIn@@QEAA@PEBGHI@Z; CStrIn::CStrIn(ushort const *,int,uint)
0x18003d644  xor     r9d, r9d; unsigned int
0x18003d647  lea     rcx, [rsp+4A8h+var_478]; this
0x18003d64c  mov     r8d, ebp; int
0x18003d64f  mov     rdx, rsi; unsigned __int16 *
0x18003d652  call    ??0CStrIn@@QEAA@PEBGHI@Z; CStrIn::CStrIn(ushort const *,int,uint)
0x18003d657  mov     rcx, [rsp+4A8h+var_478]
0x18003d65c  mov     edx, edi; dwCmpFlags
0x18003d65e  mov     eax, [rsp+4A8h+var_268]
0x18003d665  mov     r9d, [rsp+4A8h+cchCount1]; cchCount1
0x18003d66d  mov     r8, [rsp+4A8h+lpString1]; lpString1
0x18003d675  mov     [rsp+4A8h+cchCount2], eax; cchCount2
0x18003d679  mov     [rsp+4A8h+lpString2], rcx; lpString2
0x18003d67e  mov     ecx, ebx; Locale
0x18003d680  call    cs:__imp_CompareStringA
0x18003d687  nop     dword ptr [rax+rax+00h]
0x18003d68c  lea     rcx, [rsp+4A8h+var_478]; this
0x18003d691  mov     ebx, eax
0x18003d693  call    ?Free@CConvertStr@@IEAAXXZ; CConvertStr::Free(void)
0x18003d698  lea     rcx, [rsp+4A8h+lpString1]; this
0x18003d6a0  call    ?Free@CConvertStr@@IEAAXXZ; CConvertStr::Free(void)
0x18003d6a5  mov     eax, ebx
0x18003d6a7  jmp     loc_18003D611
```
