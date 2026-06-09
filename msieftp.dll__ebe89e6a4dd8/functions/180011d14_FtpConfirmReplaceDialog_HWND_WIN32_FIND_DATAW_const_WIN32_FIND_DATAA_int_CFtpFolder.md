# FtpConfirmReplaceDialog(HWND__ *,_WIN32_FIND_DATAW const *,_WIN32_FIND_DATAA *,int,CFtpFolder *)

- ea: `0x180011d14`
- end: `0x180011e52`
- name: `?FtpConfirmReplaceDialog@@YAIPEAUHWND__@@PEBU_WIN32_FIND_DATAW@@PEAU_WIN32_FIND_DATAA@@HPEAVCFtpFolder@@@Z`
- size: `318`
- prototype: `unsigned int __fastcall(HWND, const struct _WIN32_FIND_DATAW *, struct _WIN32_FIND_DATAA *, int, struct CFtpFolder *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800121f0`

## callees

- `0x180002240`
- `0x18000c3b8`
- `0x1800119e4`
- `0x180011a24`
- `0x1800170bc`

## import_xrefs

- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x180011d9f`
- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x180011d9f`

## pseudocode

```c
__int64 __fastcall FtpConfirmReplaceDialog(
        HWND a1,
        const struct _WIN32_FIND_DATAW *a2,
        struct _WIN32_FIND_DATAA *a3,
        int a4,
        struct CFtpFolder *a5)
{
  WCHAR *psz; // rsi
  int WireEncoding; // eax
  unsigned int v11; // eax
  unsigned int v12; // ebx
  _BYTE v14[40]; // [rsp+70h] [rbp-3C8h] BYREF
  struct CFtpFolder *v15; // [rsp+98h] [rbp-3A0h]
  __int64 v16; // [rsp+A8h] [rbp-390h]
  __int128 v17; // [rsp+B0h] [rbp-388h]
  __int64 v18; // [rsp+C0h] [rbp-378h]
  char v19[272]; // [rsp+D0h] [rbp-368h] BYREF
  WCHAR v20[264]; // [rsp+1E0h] [rbp-258h] BYREF

  psz = a2->cFileName;
  v15 = a5;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  WireEncoding = CFtpFolder::GetWireEncoding(a5);
  SHUnicodeToAnsiCP(WireEncoding != 0 ? 0xFDE9 : 0, psz, v19, 260);
  v11 = CFtpFolder::GetWireEncoding(a5);
  WireBytesToUnicode(a3->cFileName, v11, v20, 260);
  v12 = CFtpConfirmDialog::Display(
          (CFtpConfirmDialog *)v14,
          a1,
          a2,
          v19,
          psz,
          3u,
          a3,
          a3->cFileName,
          v20,
          3u,
          a4,
          a4 > 1,
          1u);
  CFtpConfirmDialog::~CFtpConfirmDialog((CFtpConfirmDialog *)v14);
  return v12;
}

```

## disassembly

```asm
0x180011d14  push    rbx
0x180011d16  push    rbp
0x180011d17  push    rsi
0x180011d18  push    rdi
0x180011d19  push    r13
0x180011d1b  push    r14
0x180011d1d  push    r15
0x180011d1f  sub     rsp, 400h
0x180011d26  mov     rax, cs:__security_cookie
0x180011d2d  xor     rax, rsp
0x180011d30  mov     [rsp+438h+var_48], rax
0x180011d38  mov     rdi, [rsp+438h+arg_20]
0x180011d40  lea     rsi, [rdx+2Ch]
0x180011d44  mov     r15, rcx
0x180011d47  mov     [rsp+438h+var_3A0], rdi
0x180011d4f  xorps   xmm0, xmm0
0x180011d52  mov     [rsp+438h+var_390], 0
0x180011d5e  mov     rcx, rdi
0x180011d61  movdqa  [rsp+438h+var_388], xmm0
0x180011d6a  mov     ebp, r9d
0x180011d6d  mov     [rsp+438h+var_378], 0
0x180011d79  mov     r14, r8
0x180011d7c  mov     r13, rdx
0x180011d7f  call    ?GetWireEncoding@CFtpFolder@@QEAA?AW4WIREENC@@XZ; CFtpFolder::GetWireEncoding(void)
0x180011d84  neg     eax
0x180011d86  lea     r8, [rsp+438h+var_368]
0x180011d8e  mov     r9d, 104h
0x180011d94  mov     rdx, rsi
0x180011d97  sbb     ecx, ecx
0x180011d99  and     ecx, 0FDE9h
0x180011d9f  call    cs:__imp_SHUnicodeToAnsiCP
0x180011da5  mov     rcx, rdi
0x180011da8  lea     rbx, [r14+2Ch]
0x180011dac  call    ?GetWireEncoding@CFtpFolder@@QEAA?AW4WIREENC@@XZ; CFtpFolder::GetWireEncoding(void)
0x180011db1  mov     edx, eax
0x180011db3  lea     r8, [rsp+438h+var_258]
0x180011dbb  mov     r9d, 104h
0x180011dc1  mov     rcx, rbx
0x180011dc4  call    ?WireBytesToUnicode@@YAJPEBDW4WIREENC@@PEAGK@Z; WireBytesToUnicode(char const *,WIREENC,ushort *,ulong)
0x180011dc9  mov     [rsp+438h+var_3D8], 1; unsigned int
0x180011dd1  lea     r9, [rsp+438h+var_368]; char *
0x180011dd9  xor     eax, eax
0x180011ddb  mov     ecx, 3
0x180011de0  cmp     ebp, 1
0x180011de3  mov     r8, r13; void *
0x180011de6  mov     rdx, r15; HWND
0x180011de9  setnle  al
0x180011dec  mov     [rsp+438h+var_3E0], eax; int
0x180011df0  lea     rax, [rsp+438h+var_258]
0x180011df8  mov     [rsp+438h+var_3E8], ebp; int
0x180011dfc  mov     [rsp+438h+var_3F0], ecx; unsigned int
0x180011e00  mov     [rsp+438h+var_3F8], rax; LPCWSTR
0x180011e05  mov     [rsp+438h+var_400], rbx; char *
0x180011e0a  mov     [rsp+438h+var_408], r14; void *
0x180011e0f  mov     [rsp+438h+var_410], ecx; unsigned int
0x180011e13  lea     rcx, [rsp+438h+var_3C8]; this
0x180011e18  mov     [rsp+438h+psz], rsi; psz
0x180011e1d  call    ?Display@CFtpConfirmDialog@@QEAAIPEAUHWND__@@PEBXPEBDPEBGI123IHHK@Z; CFtpConfirmDialog::Display(HWND__ *,void const *,char const *,ushort const *,uint,void const *,char const *,ushort const *,uint,int,int,ulong)
0x180011e22  lea     rcx, [rsp+438h+var_3C8]; this
0x180011e27  mov     ebx, eax
0x180011e29  call    ??1CFtpConfirmDialog@@QEAA@XZ; CFtpConfirmDialog::~CFtpConfirmDialog(void)
0x180011e2e  mov     eax, ebx
0x180011e30  mov     rcx, [rsp+438h+var_48]
0x180011e38  xor     rcx, rsp; StackCookie
0x180011e3b  call    __security_check_cookie
0x180011e40  add     rsp, 400h
0x180011e47  pop     r15
0x180011e49  pop     r14
0x180011e4b  pop     r13
0x180011e4d  pop     rdi
0x180011e4e  pop     rsi
0x180011e4f  pop     rbp
0x180011e50  pop     rbx
0x180011e51  retn
```
