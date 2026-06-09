# CreateMapping(void *,ushort const *,ushort const *,ulong,CM_SCOPEFLAGS,ulong)

- ea: `0x180024594`
- end: `0x1800247a0`
- name: `?CreateMapping@@YAPEAXPEAXPEBG1KW4CM_SCOPEFLAGS@@K@Z`
- size: `524`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800248e4`
- `0x1800a73bc`

## callees

- `0x180022348`
- `0x180024594`
- `0x18002568c`
- `0x180025e58`
- `0x18006ed20`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800246d6`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002476c`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180024792`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800246d6`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002476c`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180024792`

## pseudocode

```c
HANDLE __fastcall CreateMapping(void *a1, __int16 *a2, __int64 a3, DWORD a4, int a5, DWORD flProtect)
{
  HANDLE FileMappingW; // rbx
  __int16 *i; // rcx
  __int16 v11; // ax
  const wchar_t *v12; // r9
  int v14; // [rsp+30h] [rbp-D0h] BYREF
  LPSECURITY_ATTRIBUTES lpFileMappingAttributes; // [rsp+38h] [rbp-C8h]
  __int128 v16; // [rsp+40h] [rbp-C0h]
  __int128 v17; // [rsp+50h] [rbp-B0h]
  __int64 v18; // [rsp+60h] [rbp-A0h]
  __int64 v19; // [rsp+68h] [rbp-98h]
  __int128 v20; // [rsp+70h] [rbp-90h]
  _BYTE v21[518]; // [rsp+80h] [rbp-80h] BYREF
  char v22; // [rsp+286h] [rbp+186h] BYREF
  WCHAR Name[264]; // [rsp+290h] [rbp+190h] BYREF

  FileMappingW = 0;
  for ( i = (__int16 *)v21; *a2 && &v22 > (char *)i; ++i )
  {
    if ( *a2 == 92 )
      v11 = 42;
    else
      v11 = *a2;
    ++a2;
    *i = v11;
  }
  *i = 0;
  if ( !*a2 )
  {
    v12 = L"Local\\";
    if ( (a5 & 1) == 0 )
      v12 = L"Global\\";
    if ( (int)StringCchPrintfW(Name, 0x104u, L"%s%s*%s", v12, v21, a3) >= 0 )
    {
      v14 = a5;
      v16 = 0;
      lpFileMappingAttributes = 0;
      v17 = 0;
      v19 = 0;
      LODWORD(v17) = 24;
      v18 = 0;
      v20 = 0;
      if ( ((int)CSecurityAttributesForSharedObjects::InitializeForSharedSection((CSecurityAttributesForSharedObjects *)&v14) < 0
         || (FileMappingW = CreateFileMappingW(a1, lpFileMappingAttributes, flProtect, 0, a4, Name)) == 0)
        && ((a5 & 1) != 0
         || (int)StringCchPrintfW(Name, 0x104u, L"%s%s*%s", L"Local\\", v21, a3) < 0
         || (FileMappingW = CreateFileMappingW(a1, 0, flProtect, 0, a4, Name)) == 0) )
      {
        FileMappingW = CreateFileMappingW(a1, 0, flProtect, 0, a4, 0);
      }
      CSecurityAttributesForSharedObjects::~CSecurityAttributesForSharedObjects((CSecurityAttributesForSharedObjects *)&v14);
    }
  }
  return FileMappingW;
}

```

## disassembly

```asm
0x180024594  mov     [rsp-8+arg_8], rbx
0x180024599  push    rbp
0x18002459a  push    rsi
0x18002459b  push    rdi
0x18002459c  push    r12
0x18002459e  push    r13
0x1800245a0  push    r14
0x1800245a2  push    r15
0x1800245a4  lea     rbp, [rsp-3B0h]
0x1800245ac  sub     rsp, 4B0h
0x1800245b3  mov     rax, cs:__security_cookie
0x1800245ba  xor     rax, rsp
0x1800245bd  mov     [rbp+3E0h+var_40], rax
0x1800245c4  mov     r14d, [rbp+3E0h+flProtect]
0x1800245cb  mov     r13, r8
0x1800245ce  xor     r8d, r8d
0x1800245d1  mov     rdi, rcx
0x1800245d4  mov     ebx, r8d
0x1800245d7  lea     rcx, [rbp+3E0h+var_460]
0x1800245db  mov     esi, r9d
0x1800245de  jmp     short loc_1800245F0
0x1800245e0  mov     eax, 2Ah ; '*'
0x1800245e5  add     rdx, 2
0x1800245e9  mov     [rcx], ax
0x1800245ec  add     rcx, 2
0x1800245f0  cmp     [rdx], r8w
0x1800245f4  jz      short loc_180024611
0x1800245f6  lea     rax, [rbp+3E0h+var_25A]
0x1800245fd  cmp     rax, rcx
0x180024600  jbe     short loc_180024611
0x180024602  mov     eax, 5Ch ; '\'
0x180024607  cmp     ax, [rdx]
0x18002460a  jz      short loc_1800245E0
0x18002460c  movzx   eax, word ptr [rdx]
0x18002460f  jmp     short loc_1800245E5
0x180024611  mov     [rcx], r8w
0x180024615  cmp     r8w, [rdx]
0x180024619  jnz     loc_1800246EE
0x18002461f  mov     r12d, [rbp+3E0h+arg_20]
0x180024626  lea     rax, aGlobal; "Global\\"
0x18002462d  mov     r15d, r12d
0x180024630  mov     [rsp+4E0h+lpName], r13
0x180024635  and     r15d, 1
0x180024639  lea     r9, aLocal; "Local\\"
0x180024640  lea     r8, c_szObjectNameTemplate; "%s%s*%s"
0x180024647  mov     edx, 104h; unsigned __int64
0x18002464c  cmovz   r9, rax
0x180024650  lea     rcx, [rbp+3E0h+Name]; unsigned __int16 *
0x180024657  lea     rax, [rbp+3E0h+var_460]
0x18002465b  mov     qword ptr [rsp+4E0h+dwMaximumSizeLow], rax
0x180024660  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024665  test    eax, eax
0x180024667  js      loc_1800246EE
0x18002466d  xorps   xmm0, xmm0
0x180024670  mov     [rsp+4E0h+var_4B0], r12d
0x180024675  xor     r12d, r12d
0x180024678  movdqa  [rsp+4E0h+var_4A0], xmm0
0x18002467e  xor     eax, eax
0x180024680  mov     [rsp+4E0h+lpFileMappingAttributes], r12
0x180024685  xorps   xmm1, xmm1
0x180024688  mov     [rsp+4E0h+var_480], rax
0x18002468d  movups  [rsp+4E0h+var_490], xmm0
0x180024692  lea     rcx, [rsp+4E0h+var_4B0]; this
0x180024697  mov     [rsp+4E0h+var_478], r12
0x18002469c  mov     dword ptr [rsp+4E0h+var_490], 18h
0x1800246a4  mov     dword ptr [rsp+4E0h+var_480], r12d
0x1800246a9  movdqa  [rsp+4E0h+var_470], xmm1
0x1800246af  call    ?InitializeForSharedSection@CSecurityAttributesForSharedObjects@@QEAAJXZ; CSecurityAttributesForSharedObjects::InitializeForSharedSection(void)
0x1800246b4  test    eax, eax
0x1800246b6  js      short loc_18002471B
0x1800246b8  mov     rdx, [rsp+4E0h+lpFileMappingAttributes]; lpFileMappingAttributes
0x1800246bd  lea     rax, [rbp+3E0h+Name]
0x1800246c4  mov     [rsp+4E0h+lpName], rax; lpName
0x1800246c9  xor     r9d, r9d; dwMaximumSizeHigh
0x1800246cc  mov     r8d, r14d; flProtect
0x1800246cf  mov     [rsp+4E0h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x1800246d3  mov     rcx, rdi; hFile
0x1800246d6  call    cs:__imp_CreateFileMappingW
0x1800246dc  mov     rbx, rax
0x1800246df  test    rax, rax
0x1800246e2  jz      short loc_18002471B
0x1800246e4  lea     rcx, [rsp+4E0h+var_4B0]; this
0x1800246e9  call    ??1CSecurityAttributesForSharedObjects@@QEAA@XZ; CSecurityAttributesForSharedObjects::~CSecurityAttributesForSharedObjects(void)
0x1800246ee  mov     rax, rbx
0x1800246f1  mov     rcx, [rbp+3E0h+var_40]
0x1800246f8  xor     rcx, rsp; StackCookie
0x1800246fb  call    __security_check_cookie
0x180024700  mov     rbx, [rsp+4E0h+arg_8]
0x180024708  add     rsp, 4B0h
0x18002470f  pop     r15
0x180024711  pop     r14
0x180024713  pop     r13
0x180024715  pop     r12
0x180024717  pop     rdi
0x180024718  pop     rsi
0x180024719  pop     rbp
0x18002471a  retn
0x18002471b  test    r15d, r15d
0x18002471e  jnz     short loc_18002477E
0x180024720  lea     rax, [rbp+3E0h+var_460]
0x180024724  mov     [rsp+4E0h+lpName], r13
0x180024729  lea     r9, aLocal; "Local\\"
0x180024730  mov     qword ptr [rsp+4E0h+dwMaximumSizeLow], rax
0x180024735  lea     r8, c_szObjectNameTemplate; "%s%s*%s"
0x18002473c  mov     edx, 104h; unsigned __int64
0x180024741  lea     rcx, [rbp+3E0h+Name]; unsigned __int16 *
0x180024748  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002474d  test    eax, eax
0x18002474f  js      short loc_18002477E
0x180024751  lea     rax, [rbp+3E0h+Name]
0x180024758  xor     r9d, r9d; dwMaximumSizeHigh
0x18002475b  mov     [rsp+4E0h+lpName], rax; lpName
0x180024760  mov     r8d, r14d; flProtect
0x180024763  xor     edx, edx; lpFileMappingAttributes
0x180024765  mov     [rsp+4E0h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x180024769  mov     rcx, rdi; hFile
0x18002476c  call    cs:__imp_CreateFileMappingW
0x180024772  mov     rbx, rax
0x180024775  test    rax, rax
0x180024778  jnz     loc_1800246E4
0x18002477e  mov     [rsp+4E0h+lpName], r12; lpName
0x180024783  xor     r9d, r9d; dwMaximumSizeHigh
0x180024786  mov     r8d, r14d; flProtect
0x180024789  mov     [rsp+4E0h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x18002478d  xor     edx, edx; lpFileMappingAttributes
0x18002478f  mov     rcx, rdi; hFile
0x180024792  call    cs:__imp_CreateFileMappingW
0x180024798  mov     rbx, rax
0x18002479b  jmp     loc_1800246E4
```
