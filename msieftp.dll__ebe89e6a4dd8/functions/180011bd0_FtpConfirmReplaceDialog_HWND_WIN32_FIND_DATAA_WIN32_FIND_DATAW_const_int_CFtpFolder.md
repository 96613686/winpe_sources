# FtpConfirmReplaceDialog(HWND__ *,_WIN32_FIND_DATAA *,_WIN32_FIND_DATAW const *,int,CFtpFolder *)

- ea: `0x180011bd0`
- end: `0x180011d0c`
- name: `?FtpConfirmReplaceDialog@@YAIPEAUHWND__@@PEAU_WIN32_FIND_DATAA@@PEBU_WIN32_FIND_DATAW@@HPEAVCFtpFolder@@@Z`
- size: `316`
- prototype: `unsigned int __usercall@<eax>(HWND@<rcx>, struct _WIN32_FIND_DATAA *@<rdx>, const struct _WIN32_FIND_DATAW *@<r8>, int@<r9d>, struct CFtpFolder *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d6d4`

## callees

- `0x180002240`
- `0x18000c3b8`
- `0x1800119e4`
- `0x180011a24`
- `0x1800170bc`

## import_xrefs

- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x180011c79`
- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x180011c79`

## pseudocode

```c
__int64 __fastcall FtpConfirmReplaceDialog(
        HWND a1,
        struct _WIN32_FIND_DATAA *a2,
        const struct _WIN32_FIND_DATAW *a3,
        __int64 a4,
        struct CFtpFolder *a5)
{
  unsigned int WireEncoding; // eax
  int v9; // eax
  unsigned int v10; // ebx
  _BYTE v12[40]; // [rsp+70h] [rbp-3B8h] BYREF
  struct CFtpFolder *v13; // [rsp+98h] [rbp-390h]
  __int64 v14; // [rsp+A8h] [rbp-380h]
  __int128 v15; // [rsp+B0h] [rbp-378h]
  __int64 v16; // [rsp+C0h] [rbp-368h]
  char v17[272]; // [rsp+D0h] [rbp-358h] BYREF
  WCHAR psz[264]; // [rsp+1E0h] [rbp-248h] BYREF

  v13 = a5;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  WireEncoding = CFtpFolder::GetWireEncoding(a5);
  WireBytesToUnicode(a2->cFileName, WireEncoding, psz, 260);
  v9 = CFtpFolder::GetWireEncoding(a5);
  SHUnicodeToAnsiCP(v9 != 0 ? 0xFDE9 : 0, a3->cFileName, v17, 260);
  v10 = CFtpConfirmDialog::Display(
          (CFtpConfirmDialog *)v12,
          a1,
          a2,
          a2->cFileName,
          psz,
          3u,
          a3,
          v17,
          a3->cFileName,
          3u,
          1,
          0,
          1u);
  CFtpConfirmDialog::~CFtpConfirmDialog((CFtpConfirmDialog *)v12);
  return v10;
}

```

## disassembly

```asm
0x180011bd0  mov     r11, rsp
0x180011bd3  mov     [r11+20h], rbx
0x180011bd7  push    rbp
0x180011bd8  push    rsi
0x180011bd9  push    rdi
0x180011bda  push    r14
0x180011bdc  push    r15
0x180011bde  sub     rsp, 400h
0x180011be5  mov     rax, cs:__security_cookie
0x180011bec  xor     rax, rsp
0x180011bef  mov     [rsp+428h+var_38], rax
0x180011bf7  mov     rdi, [rsp+428h+arg_20]
0x180011bff  xorps   xmm0, xmm0
0x180011c02  mov     [r11-390h], rdi
0x180011c09  mov     r14, rcx
0x180011c0c  mov     qword ptr [r11-380h], 0
0x180011c17  mov     rcx, rdi
0x180011c1a  movdqa  [rsp+428h+var_378], xmm0
0x180011c23  mov     rbp, r8
0x180011c26  mov     qword ptr [r11-368h], 0
0x180011c31  mov     r15, rdx
0x180011c34  call    ?GetWireEncoding@CFtpFolder@@QEAA?AW4WIREENC@@XZ; CFtpFolder::GetWireEncoding(void)
0x180011c39  mov     edx, eax
0x180011c3b  lea     r8, [rsp+428h+var_248]
0x180011c43  mov     r9d, 104h
0x180011c49  lea     rcx, [r15+2Ch]
0x180011c4d  call    ?WireBytesToUnicode@@YAJPEBDW4WIREENC@@PEAGK@Z; WireBytesToUnicode(char const *,WIREENC,ushort *,ulong)
0x180011c52  mov     rcx, rdi
0x180011c55  lea     rbx, [rbp+2Ch]
0x180011c59  call    ?GetWireEncoding@CFtpFolder@@QEAA?AW4WIREENC@@XZ; CFtpFolder::GetWireEncoding(void)
0x180011c5e  neg     eax
0x180011c60  lea     r8, [rsp+428h+var_358]
0x180011c68  mov     r9d, 104h
0x180011c6e  mov     rdx, rbx
0x180011c71  sbb     ecx, ecx
0x180011c73  and     ecx, 0FDE9h
0x180011c79  call    cs:__imp_SHUnicodeToAnsiCP
0x180011c7f  mov     eax, 1
0x180011c84  lea     r9, [r15+2Ch]; char *
0x180011c88  mov     [rsp+428h+var_3C8], eax; unsigned int
0x180011c8c  mov     r8, r15; void *
0x180011c8f  mov     [rsp+428h+var_3D0], 0; int
0x180011c97  mov     rdx, r14; HWND
0x180011c9a  mov     [rsp+428h+var_3D8], eax; int
0x180011c9e  lea     ecx, [rax+2]
0x180011ca1  mov     [rsp+428h+var_3E0], ecx; unsigned int
0x180011ca5  lea     rax, [rsp+428h+var_358]
0x180011cad  mov     [rsp+428h+var_3E8], rbx; LPCWSTR
0x180011cb2  mov     [rsp+428h+var_3F0], rax; char *
0x180011cb7  lea     rax, [rsp+428h+var_248]
0x180011cbf  mov     [rsp+428h+var_3F8], rbp; void *
0x180011cc4  mov     [rsp+428h+var_400], ecx; unsigned int
0x180011cc8  lea     rcx, [rsp+428h+var_3B8]; this
0x180011ccd  mov     [rsp+428h+psz], rax; psz
0x180011cd2  call    ?Display@CFtpConfirmDialog@@QEAAIPEAUHWND__@@PEBXPEBDPEBGI123IHHK@Z; CFtpConfirmDialog::Display(HWND__ *,void const *,char const *,ushort const *,uint,void const *,char const *,ushort const *,uint,int,int,ulong)
0x180011cd7  lea     rcx, [rsp+428h+var_3B8]; this
0x180011cdc  mov     ebx, eax
0x180011cde  call    ??1CFtpConfirmDialog@@QEAA@XZ; CFtpConfirmDialog::~CFtpConfirmDialog(void)
0x180011ce3  mov     eax, ebx
0x180011ce5  mov     rcx, [rsp+428h+var_38]
0x180011ced  xor     rcx, rsp; StackCookie
0x180011cf0  call    __security_check_cookie
0x180011cf5  mov     rbx, [rsp+428h+arg_18]
0x180011cfd  add     rsp, 400h
0x180011d04  pop     r15
0x180011d06  pop     r14
0x180011d08  pop     rdi
0x180011d09  pop     rsi
0x180011d0a  pop     rbp
0x180011d0b  retn
```
