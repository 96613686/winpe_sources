# CInvokeInfoHelper::InitSubject(void)

- ea: `0x18003ab44`
- end: `0x18003ac2a`
- name: `?InitSubject@CInvokeInfoHelper@@AEAAJXZ`
- size: `230`
- prototype: `__int64 __fastcall(CInvokeInfoHelper *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18003a274`

## callees

- `0x18000138c`
- `0x18000c754`
- `0x18003ab44`
- `0x18003b328`
- `0x18003c1d0`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18003ab6d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18003ab6d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18003abd3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18003abd3`
- `SHLWAPI!PathUndecorateW` at `0x18003aba1`
- `SHLWAPI!PathUndecorateW` at `0x18003aba1`

## pseudocode

```c
__int64 __fastcall CInvokeInfoHelper::InitSubject(CInvokeInfoHelper *this)
{
  const unsigned __int16 *StringNonWhitespace; // rax
  const WCHAR *v3; // rbx
  const unsigned __int16 *FileNameW; // rax
  LPWSTR *v5; // rsi
  int v6; // ebx
  const unsigned __int16 **v7; // rax
  const unsigned __int16 *v8; // rax
  unsigned __int64 v9; // rbp
  unsigned __int16 *v10; // rax

  StringNonWhitespace = FirstStringNonWhitespace(*(const unsigned __int16 **)(*(_QWORD *)this + 32LL));
  v3 = &Src;
  if ( StringNonWhitespace )
    v3 = StringNonWhitespace;
  FileNameW = PathFindFileNameW(v3);
  if ( FileNameW != v3 )
    *((_DWORD *)this + 20) = 1;
  v5 = (LPWSTR *)((char *)this + 8);
  v6 = StripAcceleratorKeys(FileNameW, (unsigned __int16 **)this + 1);
  if ( v6 >= 0 )
  {
    if ( *((_DWORD *)this + 20) )
      PathUndecorateW(*v5);
    v7 = *(const unsigned __int16 ***)(*(_QWORD *)this + 24LL);
    if ( v7 && *v7 )
    {
      v8 = FirstStringNonWhitespace(*v7);
      return (unsigned int)StripAcceleratorKeys(v8, (unsigned __int16 **)this + 2);
    }
    else
    {
      v9 = lstrlenW(*v5) + 1;
      v10 = (unsigned __int16 *)operator new[](saturated_mul(v9, 2u));
      *((_QWORD *)this + 2) = v10;
      if ( v10 )
      {
        StringCchCopyW(v10, v9, *v5);
        *((_DWORD *)this + 21) = *((_DWORD *)this + 20);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003ab44  push    rbx
0x18003ab46  push    rbp
0x18003ab47  push    rsi
0x18003ab48  push    rdi
0x18003ab49  sub     rsp, 28h
0x18003ab4d  mov     rdi, rcx
0x18003ab50  mov     rcx, [rcx]
0x18003ab53  mov     rcx, [rcx+20h]; unsigned __int16 *
0x18003ab57  call    ?FirstStringNonWhitespace@@YAPEBGPEBG@Z; FirstStringNonWhitespace(ushort const *)
0x18003ab5c  test    rax, rax
0x18003ab5f  lea     rbx, Src
0x18003ab66  cmovnz  rbx, rax
0x18003ab6a  mov     rcx, rbx; pszPath
0x18003ab6d  call    cs:__imp_PathFindFileNameW
0x18003ab73  cmp     rax, rbx
0x18003ab76  jz      short loc_18003AB7F
0x18003ab78  mov     dword ptr [rdi+50h], 1
0x18003ab7f  lea     rsi, [rdi+8]
0x18003ab83  mov     rcx, rax; unsigned __int16 *
0x18003ab86  mov     rdx, rsi; unsigned __int16 **
0x18003ab89  call    ?StripAcceleratorKeys@@YAJPEBGPEAPEAG@Z; StripAcceleratorKeys(ushort const *,ushort * *)
0x18003ab8e  mov     ebx, eax
0x18003ab90  test    eax, eax
0x18003ab92  js      loc_18003AC1F
0x18003ab98  cmp     dword ptr [rdi+50h], 0
0x18003ab9c  jz      short loc_18003ABA7
0x18003ab9e  mov     rcx, [rsi]; pszPath
0x18003aba1  call    cs:__imp_PathUndecorateW
0x18003aba7  mov     rcx, [rdi]
0x18003abaa  mov     rax, [rcx+18h]
0x18003abae  test    rax, rax
0x18003abb1  jz      short loc_18003ABD0
0x18003abb3  mov     rcx, [rax]; unsigned __int16 *
0x18003abb6  test    rcx, rcx
0x18003abb9  jz      short loc_18003ABD0
0x18003abbb  call    ?FirstStringNonWhitespace@@YAPEBGPEBG@Z; FirstStringNonWhitespace(ushort const *)
0x18003abc0  lea     rdx, [rdi+10h]; unsigned __int16 **
0x18003abc4  mov     rcx, rax; unsigned __int16 *
0x18003abc7  call    ?StripAcceleratorKeys@@YAJPEBGPEAPEAG@Z; StripAcceleratorKeys(ushort const *,ushort * *)
0x18003abcc  mov     ebx, eax
0x18003abce  jmp     short loc_18003AC1F
0x18003abd0  mov     rcx, [rsi]; lpString
0x18003abd3  call    cs:__imp_lstrlenW
0x18003abd9  inc     eax
0x18003abdb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003abe2  movsxd  rbp, eax
0x18003abe5  mov     eax, 2
0x18003abea  mul     rbp
0x18003abed  cmovb   rax, rcx
0x18003abf1  mov     rcx, rax; unsigned __int64
0x18003abf4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003abf9  mov     [rdi+10h], rax
0x18003abfd  test    rax, rax
0x18003ac00  jz      short loc_18003AC1A
0x18003ac02  mov     r8, [rsi]; unsigned __int16 *
0x18003ac05  mov     rdx, rbp; unsigned __int64
0x18003ac08  mov     rcx, rax; unsigned __int16 *
0x18003ac0b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003ac10  mov     r11d, [rdi+50h]
0x18003ac14  mov     [rdi+54h], r11d
0x18003ac18  jmp     short loc_18003AC1F
0x18003ac1a  mov     ebx, 8007000Eh
0x18003ac1f  mov     eax, ebx
0x18003ac21  add     rsp, 28h
0x18003ac25  pop     rdi
0x18003ac26  pop     rsi
0x18003ac27  pop     rbp
0x18003ac28  pop     rbx
0x18003ac29  retn
```
