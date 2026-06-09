# CPackage::CreateTempFileName(void)

- ea: `0x1800079ac`
- end: `0x180007b21`
- name: `?CreateTempFileName@CPackage@@IEAAJXZ`
- size: `373`
- prototype: `__int64 __fastcall(CPackage *__hidden this)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180007934`
- `0x180007cf8`
- `0x180008600`
- `0x1800098ac`
- `0x180009bc8`
- `0x180009dd8`

## callees

- `0x1800041d4`
- `0x1800079ac`
- `0x18000a6ec`
- `0x18000cbf0`

## import_xrefs

- `SHELL32!__imp_PathYetAnotherMakeUniqueName` at `0x180007a87`
- `SHELL32!__imp_PathYetAnotherMakeUniqueName` at `0x180007a87`
- `SHLWAPI!PathFileExistsW` at `0x180007a26`
- `SHLWAPI!PathFileExistsW` at `0x180007a26`
- `SHLWAPI!PathFindFileNameW` at `0x180007a05`
- `SHLWAPI!PathFindFileNameW` at `0x180007a05`
- `SHLWAPI!PathAppendW` at `0x180007a13`
- `SHLWAPI!PathAppendW` at `0x180007a13`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1800079ef`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1800079ef`
- `KERNEL32!lstrlenW` at `0x180007aa9`
- `KERNEL32!lstrlenW` at `0x180007aa9`

## pseudocode

```c
__int64 __fastcall CPackage::CreateTempFileName(CPackage *this)
{
  unsigned int v2; // ebx
  __int64 v3; // rbx
  const WCHAR *FileNameW; // rax
  __int64 v5; // rcx
  WCHAR *v6; // rdx
  WCHAR *v7; // rax
  WCHAR *v8; // rcx
  BOOL UniqueName; // eax
  unsigned __int64 v10; // rsi
  SIZE_T v11; // rax
  unsigned __int16 *v12; // rcx
  WCHAR Buffer[264]; // [rsp+20h] [rbp-458h] BYREF
  WCHAR pszPath[264]; // [rsp+230h] [rbp-248h] BYREF

  if ( *(_QWORD *)(*((_QWORD *)this + 14) + 592LL) )
    return 0;
  v3 = 260;
  if ( !GetTempPathW(0x104u, Buffer) )
    return (unsigned int)-2147467259;
  FileNameW = PathFindFileNameW((LPCWSTR)(*((_QWORD *)this + 14) + 72LL));
  if ( !PathAppendW(Buffer, FileNameW) )
    return (unsigned int)-2147467259;
  if ( !PathFileExistsW(Buffer) )
  {
    v2 = 0;
LABEL_15:
    v10 = (unsigned int)(lstrlenW(Buffer) + 1);
    v11 = 2 * v10;
    if ( !is_mul_ok(v10, 2u) )
      v11 = -1;
    *(_QWORD *)(*((_QWORD *)this + 14) + 592LL) = operator new(v11);
    v12 = *(unsigned __int16 **)(*((_QWORD *)this + 14) + 592LL);
    if ( v12 )
      StringCchCopyW(v12, v10, Buffer);
    else
      return (unsigned int)-2147024882;
    return v2;
  }
  v5 = 2147483646;
  v6 = Buffer;
  v7 = pszPath;
  do
  {
    if ( !v5 )
      break;
    if ( !*v6 )
      break;
    *v7++ = *v6++;
    --v5;
    --v3;
  }
  while ( v3 );
  v8 = v7 - 1;
  if ( v3 )
    v8 = v7;
  *v8 = 0;
  UniqueName = PathYetAnotherMakeUniqueName(Buffer, pszPath, 0, 0);
  v2 = !UniqueName ? 0x80004005 : 0;
  if ( UniqueName )
    goto LABEL_15;
  return v2;
}

```

## disassembly

```asm
0x1800079ac  push    rbx
0x1800079ae  push    rbp
0x1800079af  push    rsi
0x1800079b0  push    rdi
0x1800079b1  sub     rsp, 458h
0x1800079b8  mov     rax, cs:__security_cookie
0x1800079bf  xor     rax, rsp
0x1800079c2  mov     [rsp+478h+var_38], rax
0x1800079ca  mov     rax, [rcx+70h]
0x1800079ce  xor     ebp, ebp
0x1800079d0  mov     rdi, rcx
0x1800079d3  cmp     [rax+250h], rbp
0x1800079da  jz      short loc_1800079E3
0x1800079dc  mov     ebx, ebp
0x1800079de  jmp     loc_180007B03
0x1800079e3  mov     ebx, 104h
0x1800079e8  lea     rdx, [rsp+478h+Buffer]; lpBuffer
0x1800079ed  mov     ecx, ebx; nBufferLength
0x1800079ef  call    cs:__imp_GetTempPathW
0x1800079f5  test    eax, eax
0x1800079f7  jz      loc_180007AFE
0x1800079fd  mov     rcx, [rdi+70h]
0x180007a01  add     rcx, 48h ; 'H'; pszPath
0x180007a05  call    cs:__imp_PathFindFileNameW
0x180007a0b  mov     rdx, rax; pszMore
0x180007a0e  lea     rcx, [rsp+478h+Buffer]; pszPath
0x180007a13  call    cs:__imp_PathAppendW
0x180007a19  test    eax, eax
0x180007a1b  jz      loc_180007AFE
0x180007a21  lea     rcx, [rsp+478h+Buffer]; pszPath
0x180007a26  call    cs:__imp_PathFileExistsW
0x180007a2c  test    eax, eax
0x180007a2e  jz      short loc_180007AA2
0x180007a30  mov     ecx, 7FFFFFFEh
0x180007a35  lea     rdx, [rsp+478h+Buffer]
0x180007a3a  lea     rax, [rsp+478h+pszPath]
0x180007a42  test    rcx, rcx
0x180007a45  jz      short loc_180007A66
0x180007a47  movzx   r8d, word ptr [rdx]
0x180007a4b  test    r8w, r8w
0x180007a4f  jz      short loc_180007A66
0x180007a51  mov     [rax], r8w
0x180007a55  add     rdx, 2
0x180007a59  add     rax, 2
0x180007a5d  dec     rcx
0x180007a60  sub     rbx, 1
0x180007a64  jnz     short loc_180007A42
0x180007a66  lea     rcx, [rax-2]
0x180007a6a  test    rbx, rbx
0x180007a6d  lea     rdx, [rsp+478h+pszPath]; pszPath
0x180007a75  cmovnz  rcx, rax
0x180007a79  xor     r9d, r9d; pszFileSpec
0x180007a7c  xor     r8d, r8d; pszShort
0x180007a7f  mov     [rcx], bp
0x180007a82  lea     rcx, [rsp+478h+Buffer]; pszUniqueName
0x180007a87  call    cs:__imp_PathYetAnotherMakeUniqueName
0x180007a8d  mov     edx, eax
0x180007a8f  mov     ebx, 80004005h
0x180007a94  neg     eax
0x180007a96  sbb     ecx, ecx
0x180007a98  not     ecx
0x180007a9a  and     ebx, ecx
0x180007a9c  test    edx, edx
0x180007a9e  jz      short loc_180007B03
0x180007aa0  jmp     short loc_180007AA4
0x180007aa2  mov     ebx, ebp
0x180007aa4  lea     rcx, [rsp+478h+Buffer]; lpString
0x180007aa9  call    cs:__imp_lstrlenW
0x180007aaf  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180007ab6  lea     esi, [rax+1]
0x180007ab9  mov     eax, 2
0x180007abe  mul     rsi
0x180007ac1  cmovb   rax, rcx
0x180007ac5  mov     rcx, rax; unsigned __int64
0x180007ac8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007acd  mov     rcx, [rdi+70h]
0x180007ad1  mov     [rcx+250h], rax
0x180007ad8  mov     rax, [rdi+70h]
0x180007adc  mov     rcx, [rax+250h]; unsigned __int16 *
0x180007ae3  test    rcx, rcx
0x180007ae6  jnz     short loc_180007AEF
0x180007ae8  mov     ebx, 8007000Eh
0x180007aed  jmp     short loc_180007B03
0x180007aef  lea     r8, [rsp+478h+Buffer]; unsigned __int16 *
0x180007af4  mov     rdx, rsi; unsigned __int64
0x180007af7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007afc  jmp     short loc_180007B03
0x180007afe  mov     ebx, 80004005h
0x180007b03  mov     eax, ebx
0x180007b05  mov     rcx, [rsp+478h+var_38]
0x180007b0d  xor     rcx, rsp; StackCookie
0x180007b10  call    __security_check_cookie
0x180007b15  add     rsp, 458h
0x180007b1c  pop     rdi
0x180007b1d  pop     rsi
0x180007b1e  pop     rbp
0x180007b1f  pop     rbx
0x180007b20  retn
```
