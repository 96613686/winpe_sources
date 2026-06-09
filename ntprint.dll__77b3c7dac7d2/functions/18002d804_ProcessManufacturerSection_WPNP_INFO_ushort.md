# ProcessManufacturerSection(_WPNP_INFO *,ushort * *)

- ea: `0x18002d804`
- end: `0x18002da48`
- name: `?ProcessManufacturerSection@@YAJPEAU_WPNP_INFO@@PEAPEAG@Z`
- size: `580`
- prototype: `__int64 __fastcall(struct _WPNP_INFO *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002c77c`

## callees

- `0x1800078f0`
- `0x180007944`
- `0x18000b200`
- `0x18000d290`
- `0x18000d7e0`
- `0x18002c9fc`
- `0x18002ca6c`
- `0x18002d804`
- `0x18002e060`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d962`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d9f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002da2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d962`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d9f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002da2b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d93a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d93a`
- `KERNEL32!WritePrivateProfileStringW` at `0x18002d9d2`
- `KERNEL32!WritePrivateProfileStringW` at `0x18002d9d2`

## pseudocode

```c
__int64 __fastcall ProcessManufacturerSection(struct _WPNP_INFO *a1, unsigned __int16 **a2)
{
  int valid; // ebx
  int LineText; // eax
  wchar_t *v6; // rdi
  wchar_t *v7; // rax
  unsigned __int64 v8; // rsi
  const unsigned __int16 *v9; // r15
  __int64 v10; // r11
  unsigned __int64 v11; // rcx
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // r12
  int QuotedString; // eax
  wchar_t *v15; // rsi
  NCoreLibrary *v16; // rcx
  wchar_t *v17; // rax
  unsigned __int64 v19; // [rsp+20h] [rbp-10h] BYREF
  unsigned __int64 v20; // [rsp+28h] [rbp-8h] BYREF
  wchar_t *Str; // [rsp+80h] [rbp+50h] BYREF
  unsigned __int64 v22; // [rsp+88h] [rbp+58h] BYREF

  Str = 0;
  valid = ValidWPNPInfo(a1);
  if ( valid < 0 )
    return (unsigned int)valid;
  if ( !a2 )
    return (unsigned int)-2147024809;
  LineText = GetLineText(*(void **)a1, L"Manufacturer", *((const unsigned __int16 **)a1 + 3), &Str);
  v6 = Str;
  valid = LineText;
  if ( LineText >= 0 )
  {
    v22 = 0;
    v19 = 0;
    v20 = 0;
    valid = StringCchLengthW(Str, 0x1000u, &v22);
    if ( valid >= 0 )
    {
      v7 = wcschr(v6, 0x2Cu);
      v8 = v22;
      if ( !v7 || (*v7 = 0, valid = StringCchLengthW(v6, 0x1000u, &v19), valid >= 0) )
      {
        switch ( *((_DWORD *)a1 + 8) )
        {
          case 1:
            v9 = L"NTx86";
LABEL_14:
            valid = StringCchLengthW(v9, 0x1000u, &v20);
            if ( valid >= 0 )
            {
              v11 = v10 + v20 + 2;
              if ( v8 >= v11
                || ((v8 = v10 + v20 + 2,
                     v12 = (unsigned __int16 *)LocalAlloc(0x40u, (unsigned int)(2 * v11)),
                     (v13 = v12) != 0)
                  ? (valid = StringCchCopyW(v12, v8, v6))
                  : (valid = -2147024882),
                    LocalFree(v6),
                    v6 = v13,
                    valid >= 0) )
              {
                Str = 0;
                valid = StringCchCatW(v6, v8, L",");
                if ( valid >= 0 )
                {
                  valid = StringCchCatW(v6, v8, v9);
                  if ( valid >= 0 )
                  {
                    QuotedString = GetQuotedString(*((const unsigned __int16 **)a1 + 3), &Str);
                    v15 = Str;
                    valid = QuotedString;
                    if ( QuotedString >= 0 )
                    {
                      if ( WritePrivateProfileStringW(L"Manufacturer", Str, v6, *((LPCWSTR *)a1 + 1)) )
                        valid = 0;
                      else
                        valid = NCoreLibrary::GetLastErrorAsFailHR(v16);
                    }
                    if ( v15 )
                      LocalFree(v15);
                    if ( valid >= 0 )
                    {
                      v17 = wcschr(v6, 0x2Cu);
                      if ( v17 )
                      {
                        *v17 = 46;
                        *a2 = v6;
                        return (unsigned int)valid;
                      }
                      valid = -2147024883;
                    }
                  }
                }
              }
            }
            goto LABEL_33;
          case 5:
            v9 = L"NTia64";
            goto LABEL_14;
          case 7:
            v9 = L"NTamd64";
            goto LABEL_14;
        }
        valid = -2147024809;
      }
    }
  }
LABEL_33:
  if ( v6 )
    LocalFree(v6);
  return (unsigned int)valid;
}

```

## disassembly

```asm
0x18002d804  mov     [rsp-38h+arg_0], rbx
0x18002d809  push    rbp
0x18002d80a  push    rsi
0x18002d80b  push    rdi
0x18002d80c  push    r12
0x18002d80e  push    r13
0x18002d810  push    r14
0x18002d812  push    r15
0x18002d814  mov     rbp, rsp
0x18002d817  sub     rsp, 30h
0x18002d81b  xor     r12d, r12d
0x18002d81e  mov     r13, rdx
0x18002d821  mov     [rbp+Str], r12
0x18002d825  mov     r14, rcx
0x18002d828  call    ?ValidWPNPInfo@@YAJPEAU_WPNP_INFO@@@Z; ValidWPNPInfo(_WPNP_INFO *)
0x18002d82d  mov     ebx, eax
0x18002d82f  test    eax, eax
0x18002d831  js      loc_18002DA31
0x18002d837  test    r13, r13
0x18002d83a  jnz     short loc_18002D846
0x18002d83c  mov     ebx, 80070057h
0x18002d841  jmp     loc_18002DA31
0x18002d846  mov     r8, [r14+18h]; unsigned __int16 *
0x18002d84a  lea     r9, [rbp+Str]; unsigned __int16 **
0x18002d84e  mov     rcx, [r14]; void *
0x18002d851  lea     rdx, cszManufacturer; "Manufacturer"
0x18002d858  call    ?GetLineText@@YAJPEAXPEBG1PEAPEAG@Z; GetLineText(void *,ushort const *,ushort const *,ushort * *)
0x18002d85d  mov     rdi, [rbp+Str]
0x18002d861  mov     ebx, eax
0x18002d863  test    eax, eax
0x18002d865  js      loc_18002DA23
0x18002d86b  mov     r15d, 1000h
0x18002d871  mov     [rbp+arg_18], r12
0x18002d875  mov     edx, r15d; unsigned __int64
0x18002d878  mov     [rbp+var_10], r12
0x18002d87c  lea     r8, [rbp+arg_18]; unsigned __int64 *
0x18002d880  mov     [rbp+var_8], r12
0x18002d884  mov     rcx, rdi; unsigned __int16 *
0x18002d887  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002d88c  mov     ebx, eax
0x18002d88e  test    eax, eax
0x18002d890  js      loc_18002DA23
0x18002d896  mov     edx, 2Ch ; ','; Ch
0x18002d89b  mov     rcx, rdi; Str
0x18002d89e  call    ?wcschr@@YAPEAGPEAGG@Z; wcschr(ushort *,ushort)
0x18002d8a3  mov     rsi, [rbp+arg_18]
0x18002d8a7  test    rax, rax
0x18002d8aa  jz      short loc_18002D8CF
0x18002d8ac  lea     r8, [rbp+var_10]; unsigned __int64 *
0x18002d8b0  mov     [rax], r12w
0x18002d8b4  mov     edx, r15d; unsigned __int64
0x18002d8b7  mov     rcx, rdi; unsigned __int16 *
0x18002d8ba  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002d8bf  mov     ebx, eax
0x18002d8c1  test    eax, eax
0x18002d8c3  js      loc_18002DA23
0x18002d8c9  mov     r11, [rbp+var_10]
0x18002d8cd  jmp     short loc_18002D8D2
0x18002d8cf  mov     r11, rsi
0x18002d8d2  cmp     dword ptr [r14+20h], 1
0x18002d8d7  jnz     short loc_18002D8E2
0x18002d8d9  lea     r15, aNtx86_0; "NTx86"
0x18002d8e0  jmp     short loc_18002D904
0x18002d8e2  cmp     dword ptr [r14+20h], 5
0x18002d8e7  jnz     short loc_18002D8F2
0x18002d8e9  lea     r15, aNtia64_0; "NTia64"
0x18002d8f0  jmp     short loc_18002D904
0x18002d8f2  cmp     dword ptr [r14+20h], 7
0x18002d8f7  jnz     loc_18002DA1E
0x18002d8fd  lea     r15, aNtamd64; "NTamd64"
0x18002d904  lea     r8, [rbp+var_8]; unsigned __int64 *
0x18002d908  mov     edx, 1000h; unsigned __int64
0x18002d90d  mov     rcx, r15; unsigned __int16 *
0x18002d910  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002d915  mov     ebx, eax
0x18002d917  test    eax, eax
0x18002d919  js      loc_18002DA23
0x18002d91f  mov     rcx, [rbp+var_8]
0x18002d923  add     rcx, 2
0x18002d927  add     rcx, r11
0x18002d92a  cmp     rsi, rcx
0x18002d92d  jnb     short loc_18002D976
0x18002d92f  mov     rsi, rcx
0x18002d932  lea     edx, [rcx+rcx]; uBytes
0x18002d935  mov     ecx, 40h ; '@'; uFlags
0x18002d93a  call    cs:__imp_LocalAlloc
0x18002d940  mov     r12, rax
0x18002d943  test    rax, rax
0x18002d946  jnz     short loc_18002D94F
0x18002d948  mov     ebx, 8007000Eh
0x18002d94d  jmp     short loc_18002D95F
0x18002d94f  mov     r8, rdi; unsigned __int16 *
0x18002d952  mov     rdx, rsi; unsigned __int64
0x18002d955  mov     rcx, r12; unsigned __int16 *
0x18002d958  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d95d  mov     ebx, eax
0x18002d95f  mov     rcx, rdi; hMem
0x18002d962  call    cs:__imp_LocalFree
0x18002d968  mov     rdi, r12
0x18002d96b  xor     r12d, r12d
0x18002d96e  test    ebx, ebx
0x18002d970  js      loc_18002DA23
0x18002d976  lea     r8, asc_18004A964; ","
0x18002d97d  mov     [rbp+Str], r12
0x18002d981  mov     rdx, rsi; unsigned __int64
0x18002d984  mov     rcx, rdi; unsigned __int16 *
0x18002d987  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002d98c  mov     ebx, eax
0x18002d98e  test    eax, eax
0x18002d990  js      loc_18002DA23
0x18002d996  mov     r8, r15; unsigned __int16 *
0x18002d999  mov     rdx, rsi; unsigned __int64
0x18002d99c  mov     rcx, rdi; unsigned __int16 *
0x18002d99f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002d9a4  mov     ebx, eax
0x18002d9a6  test    eax, eax
0x18002d9a8  js      short loc_18002DA23
0x18002d9aa  mov     rcx, [r14+18h]; unsigned __int16 *
0x18002d9ae  lea     rdx, [rbp+Str]; unsigned __int16 **
0x18002d9b2  call    ?GetQuotedString@@YAJPEBGPEAPEAG@Z; GetQuotedString(ushort const *,ushort * *)
0x18002d9b7  mov     rsi, [rbp+Str]
0x18002d9bb  mov     ebx, eax
0x18002d9bd  test    eax, eax
0x18002d9bf  js      short loc_18002D9E8
0x18002d9c1  mov     r9, [r14+8]; lpFileName
0x18002d9c5  lea     rcx, cszManufacturer; "Manufacturer"
0x18002d9cc  mov     r8, rdi; lpString
0x18002d9cf  mov     rdx, rsi; lpKeyName
0x18002d9d2  call    cs:__imp_WritePrivateProfileStringW
0x18002d9d8  test    eax, eax
0x18002d9da  jz      short loc_18002D9E1
0x18002d9dc  mov     ebx, r12d
0x18002d9df  jmp     short loc_18002D9E8
0x18002d9e1  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002d9e6  mov     ebx, eax
0x18002d9e8  test    rsi, rsi
0x18002d9eb  jz      short loc_18002D9F6
0x18002d9ed  mov     rcx, rsi; hMem
0x18002d9f0  call    cs:__imp_LocalFree
0x18002d9f6  test    ebx, ebx
0x18002d9f8  js      short loc_18002DA23
0x18002d9fa  mov     edx, 2Ch ; ','; Ch
0x18002d9ff  mov     rcx, rdi; Str
0x18002da02  call    ?wcschr@@YAPEAGPEAGG@Z; wcschr(ushort *,ushort)
0x18002da07  test    rax, rax
0x18002da0a  jz      short loc_18002DA17
0x18002da0c  mov     word ptr [rax], 2Eh ; '.'
0x18002da11  mov     [r13+0], rdi
0x18002da15  jmp     short loc_18002DA31
0x18002da17  mov     ebx, 8007000Dh
0x18002da1c  jmp     short loc_18002DA23
0x18002da1e  mov     ebx, 80070057h
0x18002da23  test    rdi, rdi
0x18002da26  jz      short loc_18002DA31
0x18002da28  mov     rcx, rdi; hMem
0x18002da2b  call    cs:__imp_LocalFree
0x18002da31  mov     eax, ebx
0x18002da33  mov     rbx, [rsp+30h+arg_0]
0x18002da38  add     rsp, 30h
0x18002da3c  pop     r15
0x18002da3e  pop     r14
0x18002da40  pop     r13
0x18002da42  pop     r12
0x18002da44  pop     rdi
0x18002da45  pop     rsi
0x18002da46  pop     rbp
0x18002da47  retn
```
