# ProcessModelsSection(_WPNP_INFO *,ushort const *,ushort * *)

- ea: `0x18002da50`
- end: `0x18002db5b`
- name: `?ProcessModelsSection@@YAJPEAU_WPNP_INFO@@PEBGPEAPEAG@Z`
- size: `267`
- prototype: `int(struct _WPNP_INFO *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002c77c`

## callees

- `0x18000b200`
- `0x18000d7e0`
- `0x18002c9fc`
- `0x18002ca6c`
- `0x18002da50`
- `0x18002e060`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002db03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002db38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002db03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002db38`
- `KERNEL32!WritePrivateProfileStringW` at `0x18002dae1`
- `KERNEL32!WritePrivateProfileStringW` at `0x18002dae1`

## pseudocode

```c
__int64 __fastcall ProcessModelsSection(struct _WPNP_INFO *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  int valid; // ebx
  __int64 v7; // r8
  const unsigned __int16 *v8; // rcx
  int QuotedString; // eax
  wchar_t *v10; // rdi
  NCoreLibrary *v11; // rcx
  wchar_t *v12; // rax
  LPCWSTR lpString; // [rsp+20h] [rbp-28h] BYREF
  LPCWSTR lpKeyName; // [rsp+68h] [rbp+20h] BYREF

  lpString = 0;
  valid = ValidWPNPInfo(a1);
  if ( valid >= 0 )
  {
    if ( a2 && v7 )
    {
      valid = GetLineText(*(void **)a1, a2, *((const unsigned __int16 **)a1 + 2), (unsigned __int16 **)&lpString);
      if ( valid < 0 )
      {
        v10 = (wchar_t *)lpString;
      }
      else
      {
        v8 = (const unsigned __int16 *)*((_QWORD *)a1 + 2);
        lpKeyName = 0;
        QuotedString = GetQuotedString(v8, (unsigned __int16 **)&lpKeyName);
        v10 = (wchar_t *)lpString;
        valid = QuotedString;
        if ( QuotedString >= 0 )
        {
          if ( WritePrivateProfileStringW(a2, lpKeyName, lpString, *((LPCWSTR *)a1 + 1)) )
            valid = 0;
          else
            valid = NCoreLibrary::GetLastErrorAsFailHR(v11);
        }
        if ( lpKeyName )
          LocalFree((HLOCAL)lpKeyName);
        if ( valid >= 0 )
        {
          v12 = wcschr(v10, 0x2Cu);
          if ( v12 )
            *v12 = 0;
          *a3 = v10;
          v10 = 0;
        }
      }
      if ( v10 )
        LocalFree(v10);
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  return (unsigned int)valid;
}

```

## disassembly

```asm
0x18002da50  mov     [rsp+arg_0], rbx
0x18002da55  mov     [rsp+arg_8], rsi
0x18002da5a  push    rdi
0x18002da5b  push    r14
0x18002da5d  push    r15
0x18002da5f  sub     rsp, 30h
0x18002da63  mov     r15, r8
0x18002da66  mov     [rsp+48h+lpString], 0
0x18002da6f  mov     r14, rdx
0x18002da72  mov     rsi, rcx
0x18002da75  call    ?ValidWPNPInfo@@YAJPEAU_WPNP_INFO@@@Z; ValidWPNPInfo(_WPNP_INFO *)
0x18002da7a  mov     ebx, eax
0x18002da7c  test    eax, eax
0x18002da7e  js      loc_18002DB45
0x18002da84  test    r14, r14
0x18002da87  jz      loc_18002DB40
0x18002da8d  test    r8, r8
0x18002da90  jz      loc_18002DB40
0x18002da96  mov     r8, [rsi+10h]; unsigned __int16 *
0x18002da9a  lea     r9, [rsp+48h+lpString]; unsigned __int16 **
0x18002da9f  mov     rcx, [rsi]; void *
0x18002daa2  mov     rdx, r14; unsigned __int16 *
0x18002daa5  call    ?GetLineText@@YAJPEAXPEBG1PEAPEAG@Z; GetLineText(void *,ushort const *,ushort const *,ushort * *)
0x18002daaa  mov     ebx, eax
0x18002daac  test    eax, eax
0x18002daae  js      short loc_18002DB2B
0x18002dab0  mov     rcx, [rsi+10h]; unsigned __int16 *
0x18002dab4  lea     rdx, [rsp+48h+lpKeyName]; unsigned __int16 **
0x18002dab9  mov     [rsp+48h+lpKeyName], 0
0x18002dac2  call    ?GetQuotedString@@YAJPEBGPEAPEAG@Z; GetQuotedString(ushort const *,ushort * *)
0x18002dac7  mov     rdi, [rsp+48h+lpString]
0x18002dacc  mov     ebx, eax
0x18002dace  test    eax, eax
0x18002dad0  js      short loc_18002DAF6
0x18002dad2  mov     r9, [rsi+8]; lpFileName
0x18002dad6  mov     r8, rdi; lpString
0x18002dad9  mov     rdx, [rsp+48h+lpKeyName]; lpKeyName
0x18002dade  mov     rcx, r14; lpAppName
0x18002dae1  call    cs:__imp_WritePrivateProfileStringW
0x18002dae7  test    eax, eax
0x18002dae9  jz      short loc_18002DAEF
0x18002daeb  xor     ebx, ebx
0x18002daed  jmp     short loc_18002DAF6
0x18002daef  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002daf4  mov     ebx, eax
0x18002daf6  cmp     [rsp+48h+lpKeyName], 0
0x18002dafc  jz      short loc_18002DB09
0x18002dafe  mov     rcx, [rsp+48h+lpKeyName]; hMem
0x18002db03  call    cs:__imp_LocalFree
0x18002db09  test    ebx, ebx
0x18002db0b  js      short loc_18002DB30
0x18002db0d  mov     edx, 2Ch ; ','; Ch
0x18002db12  mov     rcx, rdi; Str
0x18002db15  call    ?wcschr@@YAPEAGPEAGG@Z; wcschr(ushort *,ushort)
0x18002db1a  test    rax, rax
0x18002db1d  jz      short loc_18002DB24
0x18002db1f  xor     ecx, ecx
0x18002db21  mov     [rax], cx
0x18002db24  mov     [r15], rdi
0x18002db27  xor     edi, edi
0x18002db29  jmp     short loc_18002DB30
0x18002db2b  mov     rdi, [rsp+48h+lpString]
0x18002db30  test    rdi, rdi
0x18002db33  jz      short loc_18002DB45
0x18002db35  mov     rcx, rdi; hMem
0x18002db38  call    cs:__imp_LocalFree
0x18002db3e  jmp     short loc_18002DB45
0x18002db40  mov     ebx, 80070057h
0x18002db45  mov     rsi, [rsp+48h+arg_8]
0x18002db4a  mov     eax, ebx
0x18002db4c  mov     rbx, [rsp+48h+arg_0]
0x18002db51  add     rsp, 30h
0x18002db55  pop     r15
0x18002db57  pop     r14
0x18002db59  pop     rdi
0x18002db5a  retn
```
