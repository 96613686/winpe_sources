# TranslateAccount(_TRANSLATION_DIRECTION,ushort const *,ushort *,ulong,ushort * *)

- ea: `0x18000cae0`
- end: `0x18000cc12`
- name: `?TranslateAccount@@YAJW4_TRANSLATION_DIRECTION@@PEBGPEAGKPEAPEAG@Z`
- size: `306`
- prototype: `int __high(enum _TRANSLATION_DIRECTION, const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010710`
- `0x1800116c0`
- `0x180011fc0`

## callees

- `0x180001840`
- `0x18000cae0`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000cb8c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000cbb7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000cb8c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000cbb7`

## pseudocode

```c
__int64 __fastcall TranslateAccount(int a1, const WCHAR *a2, unsigned __int16 *a3, __int64 a4, _QWORD *a5)
{
  WCHAR *v7; // r8
  WCHAR String2[17]; // [rsp+30h] [rbp-48h] BYREF

  if ( a2 && a3 )
  {
    wcscpy(String2, L"NTTHORITY\\SYSTEM");
    if ( a1 )
    {
      if ( CompareStringW(0x7Fu, 1u, a2, -1, String2, -1) == 2
        || CompareStringW(0x7Fu, 1u, a2, -1, &String2[13], -1) == 2 )
      {
        *a3 = 0;
        if ( a5 && *a5 && !*(_WORD *)*a5 )
          *a5 = 0;
        return 0;
      }
      v7 = (WCHAR *)a2;
    }
    else
    {
      v7 = String2;
      if ( *a2 )
        v7 = (WCHAR *)a2;
    }
    StringCchCopyW(a3, 0x101u, v7);
    return 0;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18000cae0  mov     [rsp+arg_0], rbx
0x18000cae5  push    rbp
0x18000cae6  push    rsi
0x18000cae7  push    rdi
0x18000cae8  sub     rsp, 60h
0x18000caec  mov     rax, cs:__security_cookie
0x18000caf3  xor     rax, rsp
0x18000caf6  mov     [rsp+78h+var_20], rax
0x18000cafb  mov     rsi, [rsp+78h+arg_20]
0x18000cb03  xor     ebp, ebp
0x18000cb05  mov     rdi, r8
0x18000cb08  mov     rbx, rdx
0x18000cb0b  test    rdx, rdx
0x18000cb0e  jz      loc_18000CBF0
0x18000cb14  test    r8, r8
0x18000cb17  jz      loc_18000CBF0
0x18000cb1d  mov     rax, 54005300590053h
0x18000cb27  mov     qword ptr [rsp+78h+var_2E], rax
0x18000cb2c  mov     eax, dword ptr cs:aNtAuthoritySys+22h; "EM"
0x18000cb32  mov     [rsp+78h+var_26], eax
0x18000cb36  movzx   eax, word ptr cs:aNtAuthoritySys+26h; ""
0x18000cb3d  mov     [rsp+78h+var_22], ax
0x18000cb42  movups  xmm0, xmmword ptr cs:aNtAuthoritySys; "NT AUTHORITY\\SYSTEM"
0x18000cb49  movups  xmm1, xmmword ptr cs:aNtAuthoritySys+0Ah; "THORITY\\SYSTEM"
0x18000cb50  movups  xmmword ptr [rsp+78h+String2], xmm0
0x18000cb55  movups  xmmword ptr [rsp+78h+String2+0Ah], xmm1
0x18000cb5a  test    ecx, ecx
0x18000cb5c  jnz     short loc_18000CB6C
0x18000cb5e  cmp     [rdx], bp
0x18000cb61  lea     r8, [rsp+78h+String2]
0x18000cb66  cmovnz  r8, rdx
0x18000cb6a  jmp     short loc_18000CBC5
0x18000cb6c  or      r9d, 0FFFFFFFFh; cchCount1
0x18000cb70  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000cb78  lea     rax, [rsp+78h+String2]
0x18000cb7d  mov     r8, rbx; lpString1
0x18000cb80  mov     [rsp+78h+lpString2], rax; lpString2
0x18000cb85  lea     edx, [r9+2]; dwCmpFlags
0x18000cb89  lea     ecx, [rdx+7Eh]; Locale
0x18000cb8c  call    cs:__imp_CompareStringW
0x18000cb92  cmp     eax, 2
0x18000cb95  jz      short loc_18000CBD4
0x18000cb97  or      r9d, 0FFFFFFFFh; cchCount1
0x18000cb9b  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000cba3  lea     rax, [rsp+78h+var_2E]
0x18000cba8  mov     r8, rbx; lpString1
0x18000cbab  mov     [rsp+78h+lpString2], rax; lpString2
0x18000cbb0  lea     edx, [r9+2]; dwCmpFlags
0x18000cbb4  lea     ecx, [rdx+7Eh]; Locale
0x18000cbb7  call    cs:__imp_CompareStringW
0x18000cbbd  cmp     eax, 2
0x18000cbc0  jz      short loc_18000CBD4
0x18000cbc2  mov     r8, rbx; unsigned __int16 *
0x18000cbc5  mov     edx, 101h; unsigned __int64
0x18000cbca  mov     rcx, rdi; unsigned __int16 *
0x18000cbcd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cbd2  jmp     short loc_18000CBEC
0x18000cbd4  mov     [rdi], bp
0x18000cbd7  test    rsi, rsi
0x18000cbda  jz      short loc_18000CBEC
0x18000cbdc  mov     rax, [rsi]
0x18000cbdf  test    rax, rax
0x18000cbe2  jz      short loc_18000CBEC
0x18000cbe4  cmp     [rax], bp
0x18000cbe7  jnz     short loc_18000CBEC
0x18000cbe9  mov     [rsi], rbp
0x18000cbec  xor     eax, eax
0x18000cbee  jmp     short loc_18000CBF5
0x18000cbf0  mov     eax, 80004005h
0x18000cbf5  mov     rcx, [rsp+78h+var_20]
0x18000cbfa  xor     rcx, rsp; StackCookie
0x18000cbfd  call    __security_check_cookie
0x18000cc02  mov     rbx, [rsp+78h+arg_0]
0x18000cc0a  add     rsp, 60h
0x18000cc0e  pop     rdi
0x18000cc0f  pop     rsi
0x18000cc10  pop     rbp
0x18000cc11  retn
```
