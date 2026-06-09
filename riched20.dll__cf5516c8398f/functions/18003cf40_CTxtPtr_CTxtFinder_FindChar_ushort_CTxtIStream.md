# CTxtPtr::CTxtFinder::FindChar(ushort,CTxtIStream &)

- ea: `0x18003cf40`
- end: `0x18003d0cf`
- name: `?FindChar@CTxtFinder@CTxtPtr@@AEAAJGAEAVCTxtIStream@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(CTxtPtr::CTxtFinder *__hidden this, unsigned __int16, struct CTxtIStream *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180081474`

## callees

- `0x18003cf40`
- `0x18003d0d8`
- `0x18008cc28`
- `0x18008dbbc`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18003cfea`
- `KERNEL32!CompareStringW` at `0x18003cfea`
- `KERNEL32!CompareStringA` at `0x18003d04f`
- `KERNEL32!CompareStringA` at `0x18003d04f`

## pseudocode

```c
__int64 __fastcall CTxtPtr::CTxtFinder::FindChar(
        CTxtPtr::CTxtFinder *this,
        unsigned __int16 a2,
        __int64 (__fastcall **a3)(struct CTxtIStream *))
{
  int v3; // esi
  int v5; // edi
  WCHAR v7; // ax
  unsigned __int16 v8; // r14
  int v9; // r15d
  bool v10; // zf
  WCHAR String1; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR String2; // [rsp+38h] [rbp-C8h] BYREF
  PCNZCH lpString2[66]; // [rsp+40h] [rbp-C0h] BYREF
  int cchCount2; // [rsp+250h] [rbp+150h]
  PCNZCH lpString1[66]; // [rsp+260h] [rbp+160h] BYREF
  int cchCount1; // [rsp+470h] [rbp+370h]

  v3 = *(_DWORD *)this;
  v5 = a2;
  while ( *(_DWORD *)this )
  {
    --*(_DWORD *)this;
    v7 = a3[4]((struct CTxtIStream *)a3);
    v8 = v7;
    if ( *((_DWORD *)this + 2) && (unsigned int)(v5 - 55296) > 0x7FF )
    {
      String2 = v7;
      String1 = v5;
      if ( CW32System::_dwPlatformId == 1 )
      {
        CStrIn::CStrIn((CStrIn *)lpString1, &String1, 1, 0);
        CStrIn::CStrIn((CStrIn *)lpString2, &String2, 1, 0);
        v9 = CompareStringA(0x400u, 0x20001u, lpString1[0], cchCount1, lpString2[0], cchCount2);
        CConvertStr::Free((CConvertStr *)lpString2);
        CConvertStr::Free((CConvertStr *)lpString1);
      }
      else
      {
        v9 = CompareStringW(0x400u, 0x20001u, &String1, 1, &String2, 1);
      }
      v10 = v9 == 2;
    }
    else
    {
      v10 = (_WORD)v5 == v7;
    }
    if ( v10 || !*((_DWORD *)this + 3) && (unsigned int)CW32System::IsAlef(v5) && (unsigned int)CW32System::IsAlef(v8) )
      return (unsigned int)(v3 - *(_DWORD *)this);
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18003cf40  push    rbp
0x18003cf42  push    rbx
0x18003cf43  push    rsi
0x18003cf44  push    rdi
0x18003cf45  push    r13
0x18003cf47  push    r14
0x18003cf49  push    r15
0x18003cf4b  lea     rbp, [rsp-390h]
0x18003cf53  sub     rsp, 490h
0x18003cf5a  mov     rax, cs:__security_cookie
0x18003cf61  xor     rax, rsp
0x18003cf64  mov     [rbp+3C0h+var_40], rax
0x18003cf6b  mov     esi, [rcx]
0x18003cf6d  mov     r13, r8
0x18003cf70  movzx   edi, dx
0x18003cf73  mov     rbx, rcx
0x18003cf76  mov     eax, [rbx]
0x18003cf78  test    eax, eax
0x18003cf7a  jz      loc_18003D0AB
0x18003cf80  dec     eax
0x18003cf82  mov     rcx, r13
0x18003cf85  mov     [rbx], eax
0x18003cf87  mov     rax, [r13+20h]
0x18003cf8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf90  cmp     dword ptr [rbx+8], 0
0x18003cf94  movzx   r14d, ax
0x18003cf98  jz      loc_18003D074
0x18003cf9e  lea     ecx, [rdi-0D800h]
0x18003cfa4  cmp     ecx, 7FFh
0x18003cfaa  jbe     loc_18003D074
0x18003cfb0  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x18003cfb7  mov     [rsp+4C0h+String2], ax
0x18003cfbc  mov     [rsp+4C0h+String1], di
0x18003cfc1  jz      short loc_18003CFF5
0x18003cfc3  lea     rax, [rsp+4C0h+String2]
0x18003cfc8  mov     [rsp+4C0h+cchCount2], 1; cchCount2
0x18003cfd0  mov     r9d, 1; cchCount1
0x18003cfd6  mov     [rsp+4C0h+lpString2], rax; lpString2
0x18003cfdb  lea     r8, [rsp+4C0h+String1]; lpString1
0x18003cfe0  mov     edx, 20001h; dwCmpFlags
0x18003cfe5  mov     ecx, 400h; Locale
0x18003cfea  call    cs:__imp_CompareStringW
0x18003cff0  mov     r15d, eax
0x18003cff3  jmp     short loc_18003D06E
0x18003cff5  xor     r9d, r9d; unsigned int
0x18003cff8  lea     rdx, [rsp+4C0h+String1]; unsigned __int16 *
0x18003cffd  lea     rcx, [rbp+3C0h+lpString1]; this
0x18003d004  lea     r8d, [r9+1]; int
0x18003d008  call    ??0CStrIn@@QEAA@PEBGHI@Z; CStrIn::CStrIn(ushort const *,int,uint)
0x18003d00d  xor     r9d, r9d; unsigned int
0x18003d010  lea     rdx, [rsp+4C0h+String2]; unsigned __int16 *
0x18003d015  lea     rcx, [rsp+4C0h+var_480]; this
0x18003d01a  lea     r8d, [r9+1]; int
0x18003d01e  call    ??0CStrIn@@QEAA@PEBGHI@Z; CStrIn::CStrIn(ushort const *,int,uint)
0x18003d023  mov     rcx, [rsp+4C0h+var_480]
0x18003d028  mov     edx, 20001h; dwCmpFlags
0x18003d02d  mov     eax, [rbp+3C0h+var_270]
0x18003d033  mov     r9d, [rbp+3C0h+cchCount1]; cchCount1
0x18003d03a  mov     r8, [rbp+3C0h+lpString1]; lpString1
0x18003d041  mov     [rsp+4C0h+cchCount2], eax; cchCount2
0x18003d045  mov     [rsp+4C0h+lpString2], rcx; lpString2
0x18003d04a  mov     ecx, 400h; Locale
0x18003d04f  call    cs:__imp_CompareStringA
0x18003d055  lea     rcx, [rsp+4C0h+var_480]; this
0x18003d05a  mov     r15d, eax
0x18003d05d  call    ?Free@CConvertStr@@IEAAXXZ; CConvertStr::Free(void)
0x18003d062  lea     rcx, [rbp+3C0h+lpString1]; this
0x18003d069  call    ?Free@CConvertStr@@IEAAXXZ; CConvertStr::Free(void)
0x18003d06e  cmp     r15d, 2
0x18003d072  jmp     short loc_18003D078
0x18003d074  cmp     di, r14w
0x18003d078  jz      short loc_18003D0A5
0x18003d07a  cmp     dword ptr [rbx+0Ch], 0
0x18003d07e  jnz     loc_18003CF76
0x18003d084  movzx   ecx, di; unsigned __int16
0x18003d087  call    ?IsAlef@CW32System@@SAHG@Z; CW32System::IsAlef(ushort)
0x18003d08c  test    eax, eax
0x18003d08e  jz      loc_18003CF76
0x18003d094  movzx   ecx, r14w; unsigned __int16
0x18003d098  call    ?IsAlef@CW32System@@SAHG@Z; CW32System::IsAlef(ushort)
0x18003d09d  test    eax, eax
0x18003d09f  jz      loc_18003CF76
0x18003d0a5  sub     esi, [rbx]
0x18003d0a7  mov     eax, esi
0x18003d0a9  jmp     short loc_18003D0AE
0x18003d0ab  or      eax, 0FFFFFFFFh
0x18003d0ae  mov     rcx, [rbp+3C0h+var_40]
0x18003d0b5  xor     rcx, rsp; StackCookie
0x18003d0b8  call    __security_check_cookie
0x18003d0bd  add     rsp, 490h
0x18003d0c4  pop     r15
0x18003d0c6  pop     r14
0x18003d0c8  pop     r13
0x18003d0ca  pop     rdi
0x18003d0cb  pop     rsi
0x18003d0cc  pop     rbx
0x18003d0cd  pop     rbp
0x18003d0ce  retn
```
