# IERegGetBool

- ea: `0x18003ec40`
- end: `0x18003ee95`
- name: `IERegGetBool`
- size: `597`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180064f64`

## callees

- `0x18003ebec`
- `0x18003ec40`
- `0x18003ee9c`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003ed9a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003edc7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003edf4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003ee21`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003ee4a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003ee73`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003ed9a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003edc7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003edf4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003ee21`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003ee4a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003ee73`

## pseudocode

```c
__int64 __fastcall IERegGetBool(unsigned int a1, _DWORD *a2)
{
  unsigned int ValueInternal; // ebx
  unsigned int v5; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v6; // [rsp+44h] [rbp-3Ch] BYREF
  unsigned int v7; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v8; // [rsp+4Ch] [rbp-34h] BYREF
  WCHAR String2[16]; // [rsp+50h] [rbp-30h] BYREF

  if ( a2 )
  {
    if ( LODWORD(qword_1800E4B80[5 * a1 + 2]) == 4 )
    {
      v8 = 0;
      v5 = 0;
      v7 = 4;
      v6 = 0;
      if ( a1 >= 0x55 )
        return (unsigned int)-2147219708;
      ValueInternal = IERegGetValueInternal(
                        a1,
                        &v8,
                        &v5,
                        &v7,
                        &v6,
                        (const unsigned __int16 *)qword_1800E4B80[5 * a1],
                        (const unsigned __int16 *)qword_1800E4B80[5 * a1 + 1]);
      if ( (ValueInternal & 0x80000000) != 0 )
        return ValueInternal;
      if ( v8 == 4 )
      {
        *a2 = v5 != 0;
        return ValueInternal;
      }
    }
    else if ( LODWORD(qword_1800E4B80[5 * a1 + 2]) == 1 )
    {
      v5 = 1;
      v7 = 6;
      v6 = 32;
      ValueInternal = IERegGetValue(a1, &v5, String2, &v6, &v7);
      if ( (ValueInternal & 0x80000000) != 0 )
        return ValueInternal;
      if ( v5 == 1 )
      {
        if ( CompareStringW(0x7Fu, 1u, L"YES", -1, String2, -1) == 2
          || CompareStringW(0x7Fu, 1u, L"TRUE", -1, String2, -1) == 2
          || CompareStringW(0x7Fu, 1u, L"1", -1, String2, -1) == 2 )
        {
          *a2 = 1;
          return ValueInternal;
        }
        if ( CompareStringW(0x7Fu, 1u, L"NO", -1, String2, -1) == 2
          || CompareStringW(0x7Fu, 1u, L"FALSE", -1, String2, -1) == 2
          || CompareStringW(0x7Fu, 1u, L"0", -1, String2, -1) == 2 )
        {
          *a2 = 0;
          return ValueInternal;
        }
      }
    }
    return (unsigned int)-2147219711;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18003ec40  mov     [rsp-28h+arg_10], rbx
0x18003ec45  push    rbp
0x18003ec46  push    rdi
0x18003ec47  push    r12
0x18003ec49  push    r14
0x18003ec4b  push    r15
0x18003ec4d  mov     rbp, rsp
0x18003ec50  sub     rsp, 80h
0x18003ec57  mov     rax, cs:__security_cookie
0x18003ec5e  xor     rax, rsp
0x18003ec61  mov     [rbp+var_10], rax
0x18003ec65  mov     rdi, rdx
0x18003ec68  test    rdx, rdx
0x18003ec6b  jz      loc_18003ED24
0x18003ec71  mov     eax, ecx
0x18003ec73  lea     r8, qword_1800E4B80
0x18003ec7a  lea     rdx, [rax+rax*4]
0x18003ec7e  cmp     dword ptr [r8+rdx*8+10h], 4
0x18003ec84  jnz     loc_18003ED2B
0x18003ec8a  mov     [rbp+var_34], 0
0x18003ec91  mov     [rbp+var_40], 0
0x18003ec98  mov     [rbp+var_38], 4
0x18003ec9f  mov     [rbp+var_3C], 0
0x18003eca6  cmp     ecx, 55h ; 'U'
0x18003eca9  jnb     short loc_18003ED1D
0x18003ecab  mov     rax, [r8+rdx*8+8]
0x18003ecb0  lea     r9, [rbp+var_38]; unsigned int *
0x18003ecb4  mov     [rsp+80h+var_50], rax; unsigned __int16 *
0x18003ecb9  mov     rax, [r8+rdx*8]
0x18003ecbd  lea     r8, [rbp+var_40]; void *
0x18003ecc1  mov     qword ptr [rsp+80h+cchCount2], rax; unsigned __int16 *
0x18003ecc6  lea     rdx, [rbp+var_34]; unsigned int *
0x18003ecca  lea     rax, [rbp+var_3C]
0x18003ecce  mov     [rsp+80h+lpString2], rax; unsigned int *
0x18003ecd3  call    ?IERegGetValueInternal@@YAJIPEAKPEAX00PEBG2@Z; IERegGetValueInternal(uint,ulong *,void *,ulong *,ulong *,ushort const *,ushort const *)
0x18003ecd8  mov     ebx, eax
0x18003ecda  test    eax, eax
0x18003ecdc  jns     short loc_18003ED04
0x18003ecde  mov     eax, ebx
0x18003ece0  mov     rcx, [rbp+var_10]
0x18003ece4  xor     rcx, rsp; StackCookie
0x18003ece7  call    __security_check_cookie
0x18003ecec  mov     rbx, [rsp+80h+arg_10]
0x18003ecf4  add     rsp, 80h
0x18003ecfb  pop     r15
0x18003ecfd  pop     r14
0x18003ecff  pop     r12
0x18003ed01  pop     rdi
0x18003ed02  pop     rbp
0x18003ed03  retn
0x18003ed04  cmp     [rbp+var_34], 4
0x18003ed08  jnz     short loc_18003ED16
0x18003ed0a  xor     eax, eax
0x18003ed0c  cmp     [rbp+var_40], eax
0x18003ed0f  setnz   al
0x18003ed12  mov     [rdi], eax
0x18003ed14  jmp     short loc_18003ECDE
0x18003ed16  mov     ebx, 80040701h
0x18003ed1b  jmp     short loc_18003ECDE
0x18003ed1d  mov     ebx, 80040704h
0x18003ed22  jmp     short loc_18003ECDE
0x18003ed24  mov     eax, 80004003h
0x18003ed29  jmp     short loc_18003ECE0
0x18003ed2b  mov     r14d, 1
0x18003ed31  cmp     [r8+rdx*8+10h], r14d
0x18003ed36  jnz     short loc_18003ED16
0x18003ed38  lea     rax, [rbp+var_38]
0x18003ed3c  mov     [rbp+var_40], r14d
0x18003ed40  lea     r9, [rbp+var_3C]; unsigned int *
0x18003ed44  mov     [rsp+80h+lpString2], rax; unsigned int *
0x18003ed49  lea     r8, [rbp+String2]; void *
0x18003ed4d  mov     [rbp+var_38], 6
0x18003ed54  lea     rdx, [rbp+var_40]; unsigned int *
0x18003ed58  mov     [rbp+var_3C], 20h ; ' '
0x18003ed5f  call    ?IERegGetValue@@YAJIPEAKPEAX00@Z; IERegGetValue(uint,ulong *,void *,ulong *,ulong *)
0x18003ed64  mov     ebx, eax
0x18003ed66  test    eax, eax
0x18003ed68  js      loc_18003ECDE
0x18003ed6e  cmp     [rbp+var_40], r14d
0x18003ed72  jnz     short loc_18003ED16
0x18003ed74  or      r15d, 0FFFFFFFFh
0x18003ed78  lea     rax, [rbp+String2]
0x18003ed7c  lea     r12d, [r14+7Eh]
0x18003ed80  mov     [rsp+80h+cchCount2], r15d; cchCount2
0x18003ed85  mov     r9d, r15d; cchCount1
0x18003ed88  mov     [rsp+80h+lpString2], rax; lpString2
0x18003ed8d  mov     ecx, r12d; Locale
0x18003ed90  lea     r8, aYes_0; "YES"
0x18003ed97  mov     edx, r14d; dwCmpFlags
0x18003ed9a  call    cs:__imp_CompareStringW
0x18003eda0  cmp     eax, 2
0x18003eda3  jz      loc_18003EE8D
0x18003eda9  lea     rax, [rbp+String2]
0x18003edad  mov     [rsp+80h+cchCount2], r15d; cchCount2
0x18003edb2  mov     r9d, r15d; cchCount1
0x18003edb5  mov     [rsp+80h+lpString2], rax; lpString2
0x18003edba  lea     r8, aTrue_0; "TRUE"
0x18003edc1  mov     edx, r14d; dwCmpFlags
0x18003edc4  mov     ecx, r12d; Locale
0x18003edc7  call    cs:__imp_CompareStringW
0x18003edcd  cmp     eax, 2
0x18003edd0  jz      loc_18003EE8D
0x18003edd6  lea     rax, [rbp+String2]
0x18003edda  mov     [rsp+80h+cchCount2], r15d; cchCount2
0x18003eddf  mov     r9d, r15d; cchCount1
0x18003ede2  mov     [rsp+80h+lpString2], rax; lpString2
0x18003ede7  lea     r8, a1; "1"
0x18003edee  mov     edx, r14d; dwCmpFlags
0x18003edf1  mov     ecx, r12d; Locale
0x18003edf4  call    cs:__imp_CompareStringW
0x18003edfa  cmp     eax, 2
0x18003edfd  jz      loc_18003EE8D
0x18003ee03  lea     rax, [rbp+String2]
0x18003ee07  mov     [rsp+80h+cchCount2], r15d; cchCount2
0x18003ee0c  mov     r9d, r15d; cchCount1
0x18003ee0f  mov     [rsp+80h+lpString2], rax; lpString2
0x18003ee14  lea     r8, aNo_1; "NO"
0x18003ee1b  mov     edx, r14d; dwCmpFlags
0x18003ee1e  mov     ecx, r12d; Locale
0x18003ee21  call    cs:__imp_CompareStringW
0x18003ee27  cmp     eax, 2
0x18003ee2a  jz      short loc_18003EE82
0x18003ee2c  lea     rax, [rbp+String2]
0x18003ee30  mov     [rsp+80h+cchCount2], r15d; cchCount2
0x18003ee35  mov     r9d, r15d; cchCount1
0x18003ee38  mov     [rsp+80h+lpString2], rax; lpString2
0x18003ee3d  lea     r8, aFalse_0; "FALSE"
0x18003ee44  mov     edx, r14d; dwCmpFlags
0x18003ee47  mov     ecx, r12d; Locale
0x18003ee4a  call    cs:__imp_CompareStringW
0x18003ee50  cmp     eax, 2
0x18003ee53  jz      short loc_18003EE82
0x18003ee55  lea     rax, [rbp+String2]
0x18003ee59  mov     [rsp+80h+cchCount2], r15d; cchCount2
0x18003ee5e  mov     r9d, r15d; cchCount1
0x18003ee61  mov     [rsp+80h+lpString2], rax; lpString2
0x18003ee66  lea     r8, a0_0; "0"
0x18003ee6d  mov     edx, r14d; dwCmpFlags
0x18003ee70  mov     ecx, r12d; Locale
0x18003ee73  call    cs:__imp_CompareStringW
0x18003ee79  cmp     eax, 2
0x18003ee7c  jnz     loc_18003ED16
0x18003ee82  mov     dword ptr [rdi], 0
0x18003ee88  jmp     loc_18003ECDE
0x18003ee8d  mov     [rdi], r14d
0x18003ee90  jmp     loc_18003ECDE
```
