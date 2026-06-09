# GetOverlayFilePathUsingChecksum

- ea: `0x180077800`
- end: `0x180077ac8`
- name: `GetOverlayFilePathUsingChecksum`
- size: `712`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: ``

## callers

- `0x180075be0`
- `0x180078e00`

## callees

- `0x1800773d0`
- `0x180077800`
- `0x180077ad0`
- `0x180077e50`
- `0x1800781e8`
- `0x18007832c`
- `0x180078400`
- `0x1800790b0`
- `0x18009c1e8`
- `0x1800e8234`
- `0x180128940`
- `0x18015ecc0`
- `0x180162810`

## pseudocode

```c
__int64 __fastcall GetOverlayFilePathUsingChecksum(
        __int64 a1,
        __int64 a2,
        wchar_t *a3,
        __int64 a4,
        unsigned int *a5,
        wchar_t *Destination)
{
  __int64 result; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  wchar_t *v12; // r14
  const wchar_t *NtSystemRoot; // rax
  __int64 v14; // rdi
  size_t v15; // rbx
  wchar_t v16; // cx
  wchar_t *Source; // rsi
  bool v18; // zf
  wchar_t *v19; // rbx
  unsigned int v20; // r14d
  int OverlayPackageKeyForLanguage; // ebp
  int OverlayPackagePathFromKey; // eax
  int started; // r8d
  __int64 v24; // rax
  int v25; // eax
  int v26; // edi
  int v28; // ecx
  unsigned int v29; // eax
  unsigned int v30; // ecx
  rsize_t v31; // rdx
  HANDLE Handle; // [rsp+50h] [rbp-338h] BYREF
  wchar_t *String1; // [rsp+58h] [rbp-330h]
  unsigned int v34; // [rsp+60h] [rbp-328h] BYREF
  int v35; // [rsp+64h] [rbp-324h] BYREF
  __int64 v36; // [rsp+68h] [rbp-320h]
  char v37; // [rsp+70h] [rbp-318h] BYREF

  v36 = a4;
  Handle = (HANDLE)46006272;
  String1 = (wchar_t *)&v37;
  if ( !a1 || !a2 || !a5 )
    return 3221225485LL;
  result = RtlAppendUnicodeToString(&Handle, a2);
  if ( (int)result < 0 )
  {
    if ( (_DWORD)result == -1073741789 )
      return 3221225659LL;
  }
  else
  {
    v12 = String1;
    Handle = 0;
    NtSystemRoot = (const wchar_t *)RtlGetNtSystemRoot(v10, v9, v11);
    v14 = -1;
    v15 = -1;
    do
      ++v15;
    while ( NtSystemRoot[v15] );
    if ( wcsnicmp(v12, NtSystemRoot, v15) )
    {
      if ( (int)IsProgramFilesPath(v12) < 0 )
        return 3221225659LL;
      v16 = aProgramFiles[0];
      Source = L"\\Program Files";
      v15 = (size_t)Handle;
    }
    else
    {
      v16 = aWindows[0];
      Source = (wchar_t *)L"\\Windows";
    }
    v18 = v12[v15] == 92;
    v19 = &v12[v15];
    if ( !v18 || (result = 0, v16 != 92) )
      result = 3221225659LL;
    if ( (int)result >= 0 )
    {
      v20 = *a5;
      v34 = *a5;
      v35 = 0;
      if ( Destination && v20 >= 2 )
        *Destination = 0;
      Handle = 0;
      OverlayPackageKeyForLanguage = GetOverlayPackageKeyForLanguage(a1, &Handle);
      if ( OverlayPackageKeyForLanguage >= 0 )
      {
        OverlayPackageKeyForLanguage = GetOverlayPackageTypeFromKey(Handle, &v35);
        if ( OverlayPackageKeyForLanguage >= 0 )
        {
          OverlayPackagePathFromKey = GetOverlayPackagePathFromKey(Handle, &v34, Destination);
          v20 = v34;
          OverlayPackageKeyForLanguage = OverlayPackagePathFromKey;
        }
        if ( Handle )
          NtClose(Handle);
      }
      started = -1073741789;
      if ( OverlayPackageKeyForLanguage < 0 )
      {
        if ( Destination && *a5 >= 2 )
          *Destination = 0;
        if ( OverlayPackageKeyForLanguage != -1073741789 )
          return (unsigned int)OverlayPackageKeyForLanguage;
      }
      v24 = -1;
      do
        ++v24;
      while ( v19[v24] );
      v25 = 2 * v24;
      do
        ++v14;
      while ( Source[v14] );
      v26 = 2 * v14;
      if ( (v35 & 1) != 0 && v36 && a3 )
      {
        return (unsigned int)BuildCumulativeOverlayFilePath(v20, Source, a3, v36, (__int64)a5, Destination);
      }
      else
      {
        v28 = v26 + v25;
        v29 = *a5;
        v30 = v20 + v28;
        v31 = v30 + 8;
        if ( v30 < 0x208 )
          v31 = v30;
        *a5 = v31;
        if ( (unsigned int)v31 > v29 )
          return (unsigned int)started;
        started = StartPathWithLongPathPrefixIfNeeded(v20, v31, Destination);
        if ( started < 0 )
          return (unsigned int)started;
        return (unsigned int)AppendStandardOverlayFilePath(v19, Source);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180077800  push    rbx
0x180077802  push    rbp
0x180077803  push    rsi
0x180077804  push    rdi
0x180077805  push    r12
0x180077807  push    r13
0x180077809  push    r14
0x18007780b  push    r15
0x18007780d  sub     rsp, 348h
0x180077814  mov     rax, cs:__security_cookie
0x18007781b  xor     rax, rsp
0x18007781e  mov     [rsp+388h+var_58], rax
0x180077826  mov     r12, [rsp+388h+arg_20]
0x18007782e  lea     rax, [rsp+388h+var_318]
0x180077833  mov     r15, [rsp+388h+Destination]
0x18007783b  xor     ebx, ebx
0x18007783d  mov     [rsp+388h+var_320], r9
0x180077842  mov     r13, r8
0x180077845  mov     [rsp+388h+Handle], 2BE0000h
0x18007784e  mov     rbp, rcx
0x180077851  mov     [rsp+388h+String1], rax
0x180077856  test    rcx, rcx
0x180077859  jz      loc_180077A6B
0x18007785f  test    rdx, rdx
0x180077862  jz      loc_180077A6B
0x180077868  test    r12, r12
0x18007786b  jz      loc_180077A6B
0x180077871  lea     rcx, [rsp+388h+Handle]
0x180077876  call    RtlAppendUnicodeToString
0x18007787b  test    eax, eax
0x18007787d  js      loc_180077A9A
0x180077883  mov     r14, [rsp+388h+String1]
0x180077888  mov     [rsp+388h+Handle], rbx
0x18007788d  call    RtlGetNtSystemRoot
0x180077892  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180077899  mov     rbx, rdi
0x18007789c  nop     dword ptr [rax+00h]
0x1800778a0  inc     rbx
0x1800778a3  cmp     word ptr [rax+rbx*2], 0
0x1800778a8  jnz     short loc_1800778A0
0x1800778aa  mov     r8, rbx; MaxCount
0x1800778ad  mov     rdx, rax; String2
0x1800778b0  mov     rcx, r14; String1
0x1800778b3  call    _wcsnicmp
0x1800778b8  test    eax, eax
0x1800778ba  jnz     loc_180077A75
0x1800778c0  movzx   ecx, word ptr cs:aWindows; "\\Windows"
0x1800778c7  lea     rsi, aWindows; "\\Windows"
0x1800778ce  cmp     word ptr [r14+rbx*2], 5Ch ; '\'
0x1800778d4  lea     rbx, [r14+rbx*2]
0x1800778d8  jnz     loc_180077A90
0x1800778de  xor     eax, eax
0x1800778e0  cmp     cx, 5Ch ; '\'
0x1800778e4  jnz     loc_180077A90
0x1800778ea  test    eax, eax
0x1800778ec  js      loc_1800779E1
0x1800778f2  mov     r14d, [r12]
0x1800778f6  mov     [rsp+388h+var_328], r14d
0x1800778fb  mov     [rsp+388h+var_324], 0
0x180077903  test    r15, r15
0x180077906  jz      short loc_180077914
0x180077908  cmp     r14d, 2
0x18007790c  jb      short loc_180077914
0x18007790e  xor     eax, eax
0x180077910  mov     [r15], ax
0x180077914  lea     rdx, [rsp+388h+Handle]
0x180077919  mov     [rsp+388h+Handle], 0
0x180077922  mov     rcx, rbp
0x180077925  call    _GetOverlayPackageKeyForLanguage
0x18007792a  mov     ebp, eax
0x18007792c  test    eax, eax
0x18007792e  js      short loc_18007796D
0x180077930  mov     rcx, [rsp+388h+Handle]
0x180077935  lea     rdx, [rsp+388h+var_324]
0x18007793a  call    _GetOverlayPackageTypeFromKey
0x18007793f  mov     ebp, eax
0x180077941  test    eax, eax
0x180077943  js      short loc_18007795E
0x180077945  mov     rcx, [rsp+388h+Handle]
0x18007794a  lea     rdx, [rsp+388h+var_328]
0x18007794f  mov     r8, r15
0x180077952  call    _GetOverlayPackagePathFromKey
0x180077957  mov     r14d, [rsp+388h+var_328]
0x18007795c  mov     ebp, eax
0x18007795e  mov     rcx, [rsp+388h+Handle]; Handle
0x180077963  test    rcx, rcx
0x180077966  jz      short loc_18007796D
0x180077968  call    NtClose
0x18007796d  mov     r8d, 0C0000023h
0x180077973  test    ebp, ebp
0x180077975  js      loc_180077A49
0x18007797b  mov     rax, rdi
0x18007797e  xchg    ax, ax
0x180077980  inc     rax
0x180077983  cmp     word ptr [rbx+rax*2], 0
0x180077988  jnz     short loc_180077980
0x18007798a  add     eax, eax
0x18007798c  nop     dword ptr [rax+00h]
0x180077990  inc     rdi
0x180077993  cmp     word ptr [rsi+rdi*2], 0
0x180077998  jnz     short loc_180077990
0x18007799a  add     edi, edi
0x18007799c  test    byte ptr [rsp+388h+var_324], 1
0x1800779a1  jz      short loc_180077A06
0x1800779a3  mov     rcx, [rsp+388h+var_320]
0x1800779a8  test    rcx, rcx
0x1800779ab  jz      short loc_180077A06
0x1800779ad  test    r13, r13
0x1800779b0  jz      short loc_180077A06
0x1800779b2  mov     [rsp+388h+var_348], r15; Destination
0x1800779b7  mov     r9d, edi
0x1800779ba  mov     [rsp+388h+var_350], r12; __int64
0x1800779bf  mov     r8, rbx
0x1800779c2  mov     [rsp+388h+var_358], rcx; __int64
0x1800779c7  mov     edx, eax
0x1800779c9  mov     [rsp+388h+var_360], r13; wchar_t *
0x1800779ce  mov     ecx, r14d; SourceSize
0x1800779d1  mov     [rsp+388h+Source], rsi; Source
0x1800779d6  call    _BuildCumulativeOverlayFilePath
0x1800779db  mov     r8d, eax
0x1800779de  mov     eax, r8d
0x1800779e1  mov     rcx, [rsp+388h+var_58]
0x1800779e9  xor     rcx, rsp; StackCookie
0x1800779ec  call    __security_check_cookie
0x1800779f1  add     rsp, 348h
0x1800779f8  pop     r15
0x1800779fa  pop     r14
0x1800779fc  pop     r13
0x1800779fe  pop     r12
0x180077a00  pop     rdi
0x180077a01  pop     rsi
0x180077a02  pop     rbp
0x180077a03  pop     rbx
0x180077a04  retn
0x180077a06  lea     ecx, [rdi+rax]
0x180077a09  mov     eax, [r12]
0x180077a0d  add     ecx, r14d
0x180077a10  cmp     ecx, 208h
0x180077a16  lea     edx, [rcx+8]
0x180077a19  cmovb   edx, ecx; DestinationSize
0x180077a1c  mov     [r12], edx
0x180077a20  cmp     edx, eax
0x180077a22  ja      short loc_1800779DE
0x180077a24  mov     r8, r15; Destination
0x180077a27  mov     ecx, r14d; SourceSize
0x180077a2a  call    _StartPathWithLongPathPrefixIfNeeded
0x180077a2f  mov     r8d, eax
0x180077a32  test    eax, eax
0x180077a34  js      short loc_1800779DE
0x180077a36  mov     r9, r15
0x180077a39  mov     r8, r12
0x180077a3c  mov     rdx, rsi; wchar_t *
0x180077a3f  mov     rcx, rbx; Source
0x180077a42  call    _AppendStandardOverlayFilePath
0x180077a47  jmp     short loc_1800779DB
0x180077a49  test    r15, r15
0x180077a4c  jz      short loc_180077A5B
0x180077a4e  cmp     dword ptr [r12], 2
0x180077a53  jb      short loc_180077A5B
0x180077a55  xor     eax, eax
0x180077a57  mov     [r15], ax
0x180077a5b  cmp     ebp, r8d
0x180077a5e  jz      loc_18007797B
0x180077a64  mov     eax, ebp
0x180077a66  jmp     loc_1800779E1
0x180077a6b  mov     eax, 0C000000Dh
0x180077a70  jmp     loc_1800779E1
0x180077a75  lea     rdx, [rsp+388h+Handle]
0x180077a7a  mov     rcx, r14; String1
0x180077a7d  call    _IsProgramFilesPath
0x180077a82  test    eax, eax
0x180077a84  jns     short loc_180077AB0
0x180077a86  mov     eax, 0C00000BBh
0x180077a8b  jmp     loc_1800779E1
0x180077a90  mov     eax, 0C00000BBh
0x180077a95  jmp     loc_1800778EA
0x180077a9a  mov     r8d, 0C0000023h
0x180077aa0  mov     ecx, 0C00000BBh
0x180077aa5  cmp     eax, r8d
0x180077aa8  cmovz   eax, ecx
0x180077aab  jmp     loc_1800779E1
0x180077ab0  movzx   ecx, word ptr cs:aProgramFiles; "\\Program Files"
0x180077ab7  lea     rsi, aProgramFiles; "\\Program Files"
0x180077abe  mov     rbx, [rsp+388h+Handle]
0x180077ac3  jmp     loc_1800778CE
```
