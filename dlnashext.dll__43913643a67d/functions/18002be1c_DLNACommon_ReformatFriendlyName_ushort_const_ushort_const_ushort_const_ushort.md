# DLNACommon::ReformatFriendlyName(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x18002be1c`
- end: `0x18002c0d3`
- name: `?ReformatFriendlyName@DLNACommon@@YAJPEBG00PEAPEAG@Z`
- size: `695`
- prototype: `__int64 __fastcall(wchar_t *Str, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e9cc`

## callees

- `0x18001049c`
- `0x18001d3ec`
- `0x1800202f8`
- `0x18002ba5c`
- `0x18002bdb4`
- `0x18002bdec`
- `0x18002be1c`
- `0x18002c0dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18002bf1f`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18002bf1f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002be8a`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002be8a`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002be72`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002be72`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x18002bf9c`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x18002bfb2`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x18002bf9c`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x18002bfb2`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18002bfdd`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18002c00e`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18002bfdd`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18002c00e`

## pseudocode

```c
__int64 __fastcall DLNACommon::ReformatFriendlyName(
        wchar_t *Str,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  wchar_t *v8; // rdi
  wchar_t *v9; // rax
  wchar_t *v10; // r14
  int v11; // ebx
  int v12; // eax
  LPWSTR v13; // rbx
  LPWSTR *v14; // rcx
  __int64 v16; // [rsp+20h] [rbp-79h] BYREF
  __int64 v17; // [rsp+28h] [rbp-71h]
  __int64 v18; // [rsp+30h] [rbp-69h]
  LPWSTR v19; // [rsp+38h] [rbp-61h] BYREF
  DWORD v20[2]; // [rsp+40h] [rbp-59h]
  __int64 v21; // [rsp+48h] [rbp-51h]
  LPWSTR v22; // [rsp+50h] [rbp-49h] BYREF
  DWORD v23[2]; // [rsp+58h] [rbp-41h]
  __int64 v24; // [rsp+60h] [rbp-39h]
  LPWSTR v25; // [rsp+68h] [rbp-31h] BYREF
  DWORD v26[2]; // [rsp+70h] [rbp-29h]
  __int64 v27; // [rsp+78h] [rbp-21h]
  LPWSTR lpsz; // [rsp+80h] [rbp-19h] BYREF
  DWORD cchLength[2]; // [rsp+88h] [rbp-11h]
  __int64 v30; // [rsp+90h] [rbp-9h]
  __int64 v31; // [rsp+98h] [rbp-1h] BYREF
  __int64 v32; // [rsp+A0h] [rbp+7h]
  __int64 v33; // [rsp+A8h] [rbp+Fh]

  if ( Str && a2 && a3 && a4 )
  {
    *(_QWORD *)a4 = 0;
    v8 = wcsrchr(Str, 0x3Au);
    if ( v8 && (v9 = wcschr(Str, 0x3Au), (v10 = v9) != 0) && v9 < v8 )
    {
      v22 = 0;
      *(_QWORD *)v23 = 0;
      v24 = 0;
      v16 = 0;
      v17 = 0;
      v18 = 0;
      v19 = 0;
      *(_QWORD *)v20 = 0;
      v21 = 0;
      v11 = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Initialize(
              &v22,
              Str,
              v9 - Str);
      if ( v11 >= 0 )
      {
        v11 = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Initialize(
                &v16,
                v10 + 1,
                v8 - v10 - 1);
        if ( v11 >= 0 )
        {
          Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::TrimWhitespace(&v22);
          Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::TrimWhitespace(&v16);
          v12 = (unsigned int)_o__wtoi(v16)
              ? Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::InitializeFormat(
                  &v19,
                  a2,
                  v16)
              : Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::Initialize(
                  &v19,
                  &v16);
          v11 = v12;
          if ( v12 >= 0 )
          {
            v31 = 0;
            v32 = 0;
            v33 = 0;
            lpsz = 0;
            *(_QWORD *)cchLength = 0;
            v30 = 0;
            v25 = 0;
            *(_QWORD *)v26 = 0;
            v27 = 0;
            Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::Initialize(&lpsz, &v22);
            Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::Initialize(&v25, &v19);
            Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&lpsz);
            CharUpperBuffW(lpsz, cchLength[0]);
            Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&v25);
            CharUpperBuffW(v25, v26[0]);
            if ( Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::CompareOrdinal(
                   (__int64)&v22,
                   (__int64)&lpsz) == 2 )
            {
              Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&v22);
              CharLowerBuffW(v22, v23[0]);
            }
            if ( Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::CompareOrdinal(
                   (__int64)&v19,
                   (__int64)&v25) == 2 )
            {
              Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&v19);
              v13 = v19;
              CharLowerBuffW(v19, v20[0]);
            }
            else
            {
              v13 = v19;
            }
            v11 = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::InitializeFormat(
                    &v31,
                    a3,
                    v13);
            if ( v11 >= 0 )
            {
              *(_QWORD *)a4 = v31;
              v31 = 0;
              v33 = 0;
              v32 = 0;
            }
            Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&v25);
            Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&lpsz);
            Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&v31);
          }
        }
      }
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&v19);
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&v16);
      v14 = &v22;
    }
    else
    {
      v16 = 0;
      v17 = 0;
      v18 = 0;
      v11 = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Initialize(
              &v16,
              Str,
              -1);
      if ( v11 >= 0 )
      {
        *(_QWORD *)a4 = v16;
        v16 = 0;
        v18 = 0;
        v17 = 0;
      }
      v14 = (LPWSTR *)&v16;
    }
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(v14);
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002be1c  push    rbp
0x18002be1e  push    rbx
0x18002be1f  push    rsi
0x18002be20  push    rdi
0x18002be21  push    r12
0x18002be23  push    r13
0x18002be25  push    r14
0x18002be27  push    r15
0x18002be29  lea     rbp, [rsp-1Fh]
0x18002be2e  sub     rsp, 0B8h
0x18002be35  xor     r13d, r13d
0x18002be38  mov     rsi, r9
0x18002be3b  mov     r12, r8
0x18002be3e  mov     r15, rdx
0x18002be41  mov     rbx, rcx
0x18002be44  test    rcx, rcx
0x18002be47  jz      loc_18002C0B8
0x18002be4d  test    rdx, rdx
0x18002be50  jz      loc_18002C0B8
0x18002be56  test    r8, r8
0x18002be59  jz      loc_18002C0B8
0x18002be5f  test    r9, r9
0x18002be62  jz      loc_18002C0B8
0x18002be68  lea     r14d, [r13+3Ah]
0x18002be6c  mov     [r9], r13
0x18002be6f  mov     edx, r14d; Ch
0x18002be72  call    cs:__imp_wcsrchr
0x18002be78  mov     rdi, rax
0x18002be7b  test    rax, rax
0x18002be7e  jz      loc_18002C078
0x18002be84  mov     edx, r14d; Ch
0x18002be87  mov     rcx, rbx; Str
0x18002be8a  call    cs:__imp_wcschr
0x18002be90  mov     r14, rax
0x18002be93  test    rax, rax
0x18002be96  jz      loc_18002C078
0x18002be9c  cmp     rax, rdi
0x18002be9f  jnb     loc_18002C078
0x18002bea5  mov     r8, rax
0x18002bea8  mov     [rbp+57h+var_A0], r13
0x18002beac  sub     r8, rbx
0x18002beaf  mov     qword ptr [rbp+57h+var_98], r13
0x18002beb3  sar     r8, 1
0x18002beb6  lea     rcx, [rbp+57h+var_A0]
0x18002beba  mov     rdx, rbx
0x18002bebd  mov     [rbp+57h+var_90], r13
0x18002bec1  mov     [rbp+57h+var_D0], r13
0x18002bec5  mov     [rbp+57h+var_C8], r13
0x18002bec9  mov     [rbp+57h+var_C0], r13
0x18002becd  mov     [rbp+57h+var_B8], r13
0x18002bed1  mov     qword ptr [rbp+57h+var_B0], r13
0x18002bed5  mov     [rbp+57h+var_A8], r13
0x18002bed9  call    ?_Initialize@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18002bede  mov     ebx, eax
0x18002bee0  test    eax, eax
0x18002bee2  js      loc_18002C060
0x18002bee8  sub     rdi, r14
0x18002beeb  lea     rdx, [r14+2]
0x18002beef  sar     rdi, 1
0x18002bef2  lea     rcx, [rbp+57h+var_D0]
0x18002bef6  lea     r8, [rdi-1]
0x18002befa  call    ?_Initialize@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18002beff  mov     ebx, eax
0x18002bf01  test    eax, eax
0x18002bf03  js      loc_18002C060
0x18002bf09  lea     rcx, [rbp+57h+var_A0]
0x18002bf0d  call    ?TrimWhitespace@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA_NXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::TrimWhitespace(void)
0x18002bf12  lea     rcx, [rbp+57h+var_D0]
0x18002bf16  call    ?TrimWhitespace@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA_NXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::TrimWhitespace(void)
0x18002bf1b  mov     rcx, [rbp+57h+var_D0]
0x18002bf1f  call    cs:__imp__o__wtoi
0x18002bf25  lea     rcx, [rbp+57h+var_B8]
0x18002bf29  test    eax, eax
0x18002bf2b  jz      short loc_18002BF3B
0x18002bf2d  mov     r8, [rbp+57h+var_D0]
0x18002bf31  mov     rdx, r15
0x18002bf34  call    ?InitializeFormat@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18002bf39  jmp     short loc_18002BF44
0x18002bf3b  lea     rdx, [rbp+57h+var_D0]
0x18002bf3f  call    ?Initialize@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::Initialize(Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> const &)
0x18002bf44  mov     ebx, eax
0x18002bf46  test    eax, eax
0x18002bf48  js      loc_18002C060
0x18002bf4e  lea     rdx, [rbp+57h+var_A0]
0x18002bf52  mov     [rbp+57h+var_58], r13
0x18002bf56  lea     rcx, [rbp+57h+lpsz]
0x18002bf5a  mov     [rbp+57h+var_50], r13
0x18002bf5e  mov     [rbp+57h+var_48], r13
0x18002bf62  mov     [rbp+57h+lpsz], r13
0x18002bf66  mov     qword ptr [rbp+57h+cchLength], r13
0x18002bf6a  mov     [rbp+57h+var_60], r13
0x18002bf6e  mov     [rbp+57h+var_88], r13
0x18002bf72  mov     qword ptr [rbp+57h+var_80], r13
0x18002bf76  mov     [rbp+57h+var_78], r13
0x18002bf7a  call    ?Initialize@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::Initialize(Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> const &)
0x18002bf7f  lea     rdx, [rbp+57h+var_B8]
0x18002bf83  lea     rcx, [rbp+57h+var_88]
0x18002bf87  call    ?Initialize@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::Initialize(Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> const &)
0x18002bf8c  lea     rcx, [rbp+57h+lpsz]
0x18002bf90  call    ?_EnsureCount@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_EnsureCount(void)
0x18002bf95  mov     edx, [rbp+57h+cchLength]; cchLength
0x18002bf98  mov     rcx, [rbp+57h+lpsz]; lpsz
0x18002bf9c  call    cs:__imp_CharUpperBuffW
0x18002bfa2  lea     rcx, [rbp+57h+var_88]
0x18002bfa6  call    ?_EnsureCount@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_EnsureCount(void)
0x18002bfab  mov     edx, [rbp+57h+var_80]; cchLength
0x18002bfae  mov     rcx, [rbp+57h+var_88]; lpsz
0x18002bfb2  call    cs:__imp_CharUpperBuffW
0x18002bfb8  lea     rdx, [rbp+57h+lpsz]
0x18002bfbc  lea     rcx, [rbp+57h+var_A0]
0x18002bfc0  call    ?CompareOrdinal@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::CompareOrdinal(Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> const &)
0x18002bfc5  cmp     eax, 2
0x18002bfc8  jnz     short loc_18002BFE5
0x18002bfca  lea     rcx, [rbp+57h+var_A0]
0x18002bfce  call    ?_EnsureCount@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_EnsureCount(void)
0x18002bfd3  mov     rdi, [rbp+57h+var_A0]
0x18002bfd7  mov     edx, [rbp+57h+var_98]; cchLength
0x18002bfda  mov     rcx, rdi; lpsz
0x18002bfdd  call    cs:__imp_CharLowerBuffW
0x18002bfe3  jmp     short loc_18002BFE9
0x18002bfe5  mov     rdi, [rbp+57h+var_A0]
0x18002bfe9  lea     rdx, [rbp+57h+var_88]
0x18002bfed  lea     rcx, [rbp+57h+var_B8]
0x18002bff1  call    ?CompareOrdinal@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::CompareOrdinal(Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> const &)
0x18002bff6  cmp     eax, 2
0x18002bff9  jnz     short loc_18002C016
0x18002bffb  lea     rcx, [rbp+57h+var_B8]
0x18002bfff  call    ?_EnsureCount@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_EnsureCount(void)
0x18002c004  mov     rbx, [rbp+57h+var_B8]
0x18002c008  mov     edx, [rbp+57h+var_B0]; cchLength
0x18002c00b  mov     rcx, rbx; lpsz
0x18002c00e  call    cs:__imp_CharLowerBuffW
0x18002c014  jmp     short loc_18002C01A
0x18002c016  mov     rbx, [rbp+57h+var_B8]
0x18002c01a  mov     r9, rdi
0x18002c01d  lea     rcx, [rbp+57h+var_58]
0x18002c021  mov     r8, rbx
0x18002c024  mov     rdx, r12
0x18002c027  call    ?InitializeFormat@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18002c02c  mov     ebx, eax
0x18002c02e  test    eax, eax
0x18002c030  js      short loc_18002C045
0x18002c032  mov     rax, [rbp+57h+var_58]
0x18002c036  mov     [rsi], rax
0x18002c039  mov     [rbp+57h+var_58], r13
0x18002c03d  mov     [rbp+57h+var_48], r13
0x18002c041  mov     [rbp+57h+var_50], r13
0x18002c045  lea     rcx, [rbp+57h+var_88]
0x18002c049  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x18002c04e  lea     rcx, [rbp+57h+lpsz]
0x18002c052  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x18002c057  lea     rcx, [rbp+57h+var_58]
0x18002c05b  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x18002c060  lea     rcx, [rbp+57h+var_B8]
0x18002c064  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x18002c069  lea     rcx, [rbp+57h+var_D0]
0x18002c06d  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x18002c072  lea     rcx, [rbp+57h+var_A0]
0x18002c076  jmp     short loc_18002C0B1
0x18002c078  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002c07c  mov     [rbp+57h+var_D0], r13
0x18002c080  mov     rdx, rbx
0x18002c083  mov     [rbp+57h+var_C8], r13
0x18002c087  lea     rcx, [rbp+57h+var_D0]
0x18002c08b  mov     [rbp+57h+var_C0], r13
0x18002c08f  call    ?_Initialize@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18002c094  mov     ebx, eax
0x18002c096  test    eax, eax
0x18002c098  js      short loc_18002C0AD
0x18002c09a  mov     rax, [rbp+57h+var_D0]
0x18002c09e  mov     [rsi], rax
0x18002c0a1  mov     [rbp+57h+var_D0], r13
0x18002c0a5  mov     [rbp+57h+var_C0], r13
0x18002c0a9  mov     [rbp+57h+var_C8], r13
0x18002c0ad  lea     rcx, [rbp+57h+var_D0]
0x18002c0b1  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x18002c0b6  jmp     short loc_18002C0BD
0x18002c0b8  mov     ebx, 80004003h
0x18002c0bd  mov     eax, ebx
0x18002c0bf  add     rsp, 0B8h
0x18002c0c6  pop     r15
0x18002c0c8  pop     r14
0x18002c0ca  pop     r13
0x18002c0cc  pop     r12
0x18002c0ce  pop     rdi
0x18002c0cf  pop     rsi
0x18002c0d0  pop     rbx
0x18002c0d1  pop     rbp
0x18002c0d2  retn
```
