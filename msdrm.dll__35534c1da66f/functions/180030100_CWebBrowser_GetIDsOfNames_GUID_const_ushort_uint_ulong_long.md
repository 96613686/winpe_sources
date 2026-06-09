# CWebBrowser::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x180030100`
- end: `0x1800301ad`
- name: `?GetIDsOfNames@CWebBrowser@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `173`
- prototype: `__int64 __fastcall(CWebBrowser *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned int, LCID Locale, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180030100`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180030163`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180030163`

## pseudocode

```c
__int64 __fastcall CWebBrowser::GetIDsOfNames(
        CWebBrowser *this,
        const struct _GUID *a2,
        unsigned __int16 **a3,
        unsigned int a4,
        LCID Locale,
        int *a6)
{
  unsigned int v10; // edi
  __int64 i; // rbx
  const WCHAR *v12; // r8
  int v13; // eax
  int v14; // ecx

  if ( !a6 )
    return 2147942487LL;
  v10 = 0;
  for ( i = 0; (unsigned int)i < a4; i = (unsigned int)(i + 1) )
  {
    v12 = (const WCHAR *)*((_QWORD *)this + 9);
    if ( v12 )
    {
      v13 = CompareStringW(Locale, 0x20000u, v12, -1, a3[i], -1);
      if ( v13 != 2 )
        v10 = -2147352570;
      v14 = 1;
      if ( v13 != 2 )
        v14 = -1;
    }
    else
    {
      v10 = -2147352570;
      v14 = -1;
    }
    a6[i] = v14;
  }
  return v10;
}

```

## disassembly

```asm
0x180030100  push    rbx
0x180030102  push    rsi
0x180030103  push    rdi
0x180030104  push    r12
0x180030106  push    r13
0x180030108  push    r14
0x18003010a  push    r15
0x18003010c  sub     rsp, 30h
0x180030110  cmp     [rsp+68h+arg_28], 0
0x180030119  mov     r14d, r9d
0x18003011c  mov     r12, r8
0x18003011f  mov     r15, rcx
0x180030122  jnz     short loc_18003012B
0x180030124  mov     eax, 80070057h
0x180030129  jmp     short loc_18003019D
0x18003012b  xor     edi, edi
0x18003012d  xor     ebx, ebx
0x18003012f  test    r14d, r14d
0x180030132  jz      short loc_18003019B
0x180030134  or      r13d, 0FFFFFFFFh
0x180030138  mov     eax, 80020006h
0x18003013d  mov     r8, [r15+48h]; lpString1
0x180030141  test    r8, r8
0x180030144  jz      short loc_18003017F
0x180030146  mov     rax, [r12+rbx*8]
0x18003014a  mov     r9d, r13d; cchCount1
0x18003014d  mov     ecx, [rsp+68h+Locale]; Locale
0x180030154  mov     edx, 20000h; dwCmpFlags
0x180030159  mov     [rsp+68h+cchCount2], r13d; cchCount2
0x18003015e  mov     [rsp+68h+lpString2], rax; lpString2
0x180030163  call    cs:__imp_CompareStringW
0x180030169  cmp     eax, 2
0x18003016c  mov     ecx, 80020006h
0x180030171  cmovnz  edi, ecx
0x180030174  mov     ecx, 1
0x180030179  cmovnz  ecx, r13d
0x18003017d  jmp     short loc_180030184
0x18003017f  mov     edi, eax
0x180030181  mov     ecx, r13d
0x180030184  mov     rax, [rsp+68h+arg_28]
0x18003018c  mov     [rax+rbx*4], ecx
0x18003018f  inc     ebx
0x180030191  mov     eax, 80020006h
0x180030196  cmp     ebx, r14d
0x180030199  jb      short loc_18003013D
0x18003019b  mov     eax, edi
0x18003019d  add     rsp, 30h
0x1800301a1  pop     r15
0x1800301a3  pop     r14
0x1800301a5  pop     r13
0x1800301a7  pop     r12
0x1800301a9  pop     rdi
0x1800301aa  pop     rsi
0x1800301ab  pop     rbx
0x1800301ac  retn
```
