# CSSList::PersistSubsets(CExCollection *)

- ea: `0x18005be30`
- end: `0x18005c09a`
- name: `?PersistSubsets@CSSList@@QEAAJPEAVCExCollection@@@Z`
- size: `618`
- prototype: `int(CSSList *__hidden this, struct CExCollection *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18005f624`

## callees

- `0x1800095c8`
- `0x18005a3f4`
- `0x18005be30`
- `0x180062aa4`
- `0x18006a284`
- `0x180075c5a`
- `0x180075c90`

## import_xrefs

- `msvcrt!realloc` at `0x18005bfc0`
- `msvcrt!realloc` at `0x18005bfc0`
- `msvcrt!free` at `0x18005bfd1`
- `msvcrt!free` at `0x18005c060`
- `msvcrt!free` at `0x18005c086`
- `msvcrt!free` at `0x18005bfd1`
- `msvcrt!free` at `0x18005c060`
- `msvcrt!free` at `0x18005c086`
- `KERNEL32!CloseHandle` at `0x18005bf55`
- `KERNEL32!CloseHandle` at `0x18005c069`
- `KERNEL32!CloseHandle` at `0x18005c08f`
- `KERNEL32!CloseHandle` at `0x18005bf55`
- `KERNEL32!CloseHandle` at `0x18005c069`
- `KERNEL32!CloseHandle` at `0x18005c08f`
- `KERNEL32!CreateFileA` at `0x18005bf00`
- `KERNEL32!CreateFileA` at `0x18005bf00`
- `KERNEL32!WriteFile` at `0x18005bf48`
- `KERNEL32!WriteFile` at `0x18005c046`
- `KERNEL32!WriteFile` at `0x18005bf48`
- `KERNEL32!WriteFile` at `0x18005c046`

## pseudocode

```c
__int64 __fastcall CSSList::PersistSubsets(CSSList *this, struct CExCollection *a2)
{
  __int64 v4; // rcx
  __int64 v6; // rbx
  int v7; // edi
  int v8; // edx
  __int64 v9; // rax
  int v10; // eax
  const CHAR *UserCHSLocalStoragePathnameByLanguage; // rax
  HANDLE v12; // rsi
  __int64 v13; // rbx
  char *v14; // rdi
  int v15; // r13d
  __int64 v16; // r14
  signed int v17; // r12d
  char *v18; // rax
  char *v19; // r15
  unsigned int v20; // r10d
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-59h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+48h] [rbp-51h] BYREF
  __int64 Buffer; // [rsp+60h] [rbp-39h] BYREF
  int v24; // [rsp+68h] [rbp-31h]
  int v25; // [rsp+6Ch] [rbp-2Dh]
  char v26[64]; // [rsp+70h] [rbp-29h] BYREF

  memset_0(&Buffer, 0, 0x50u);
  v4 = *((_QWORD *)this + 1);
  NumberOfBytesWritten = 0;
  if ( !v4 )
    return 0;
  v6 = 0;
  v7 = 0;
  do
  {
    v8 = *(_DWORD *)(v4 + 128);
    v9 = v4;
    if ( (v8 & 0x10) == 0 )
      v9 = v6;
    v6 = v9;
    v10 = v7 + 1;
    if ( (v8 & 7) != 0 )
      v10 = v7;
    v7 = v10;
    v4 = *(_QWORD *)(v4 + 120);
  }
  while ( v4 );
  UserCHSLocalStoragePathnameByLanguage = CExCollection::GetUserCHSLocalStoragePathnameByLanguage(a2);
  if ( UserCHSLocalStoragePathnameByLanguage )
  {
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    SecurityAttributes.lpSecurityDescriptor = 0;
    v12 = CreateFileA(UserCHSLocalStoragePathnameByLanguage, 0x40000000u, 0, &SecurityAttributes, 2u, 0x80000080, 0);
    if ( v12 != (HANDLE)-1LL )
    {
      Buffer = 305419897;
      v24 = v7;
      v25 = 0;
      if ( v6 )
        StringCchCopyA(v26, 0x33u, (const char *)(v6 + 16));
      if ( !WriteFile(v12, &Buffer, 0x50u, &NumberOfBytesWritten, 0) )
      {
        CloseHandle(v12);
        MsgBox(6192, 0x10u);
        return 2147500037LL;
      }
      v13 = *((_QWORD *)this + 1);
      v14 = 0;
      while ( 1 )
      {
        if ( (*(_BYTE *)(v13 + 128) & 7) == 0 )
        {
          v15 = *(_DWORD *)(v13 + 8);
          v16 = (unsigned int)(v15 - 1);
          v17 = 4 * v16 + 116;
          v18 = (char *)realloc(v14, v17);
          v19 = v18;
          if ( v18 )
          {
            *(_DWORD *)v18 = v15;
            v14 = v18;
            StringCchCopyA(v18 + 4, 0x33u, (const char *)(v13 + 16));
            StringCchCopyA(v19 + 55, v20, (const char *)(v13 + 67));
            for ( *((_DWORD *)v19 + 27) = *(_DWORD *)(v13 + 128); (int)v16 >= 0; v16 = (unsigned int)(v16 - 1) )
              *(_DWORD *)&v19[4 * v16 + 112] = CStructuralSubset::EnumHashes((CStructuralSubset *)v13, v16);
            if ( !WriteFile(v12, v19, v17, &NumberOfBytesWritten, 0) )
            {
              MsgBox(6192, 0x10u);
              free(v19);
              CloseHandle(v12);
              return 2147500037LL;
            }
          }
          else
          {
            free(v14);
            v14 = 0;
          }
        }
        v13 = *(_QWORD *)(v13 + 120);
        if ( !v13 )
        {
          free(v14);
          CloseHandle(v12);
          return 0;
        }
      }
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18005be30  mov     [rsp-8+arg_10], rbx
0x18005be35  push    rbp
0x18005be36  push    rsi
0x18005be37  push    rdi
0x18005be38  push    r12
0x18005be3a  push    r13
0x18005be3c  push    r14
0x18005be3e  push    r15
0x18005be40  lea     rbp, [rsp-27h]
0x18005be45  sub     rsp, 0C0h
0x18005be4c  mov     rax, cs:__security_cookie
0x18005be53  xor     rax, rsp
0x18005be56  mov     [rbp+57h+var_40], rax
0x18005be5a  mov     rsi, rdx
0x18005be5d  mov     r14, rcx
0x18005be60  mov     r15d, 50h ; 'P'
0x18005be66  lea     rcx, [rbp+57h+Buffer]; void *
0x18005be6a  mov     r8d, r15d; Size
0x18005be6d  xor     edx, edx; Val
0x18005be6f  call    memset_0
0x18005be74  mov     rcx, [r14+8]
0x18005be78  xor     r13d, r13d
0x18005be7b  mov     [rbp+57h+NumberOfBytesWritten], r13d
0x18005be7f  test    rcx, rcx
0x18005be82  jnz     short loc_18005BE8B
0x18005be84  xor     eax, eax
0x18005be86  jmp     loc_18005BF6F
0x18005be8b  mov     rbx, r13
0x18005be8e  mov     edi, r13d
0x18005be91  mov     edx, [rcx+80h]
0x18005be97  mov     rax, rcx
0x18005be9a  test    dl, 10h
0x18005be9d  cmovz   rax, rbx
0x18005bea1  test    dl, 7
0x18005bea4  mov     rbx, rax
0x18005bea7  lea     eax, [rdi+1]
0x18005beaa  cmovnz  eax, edi
0x18005bead  mov     edi, eax
0x18005beaf  mov     rax, [rcx+78h]
0x18005beb3  mov     rcx, rax
0x18005beb6  test    rax, rax
0x18005beb9  jnz     short loc_18005BE91
0x18005bebb  mov     rcx, rsi; this
0x18005bebe  call    ?GetUserCHSLocalStoragePathnameByLanguage@CExCollection@@QEAAPEBDXZ; CExCollection::GetUserCHSLocalStoragePathnameByLanguage(void)
0x18005bec3  test    rax, rax
0x18005bec6  jz      loc_18005BF6A
0x18005becc  mov     [rsp+0F0h+hTemplateFile], r13; hTemplateFile
0x18005bed1  lea     r9, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x18005bed5  mov     [rsp+0F0h+dwFlagsAndAttributes], 80000080h; dwFlagsAndAttributes
0x18005bedd  xor     r8d, r8d; dwShareMode
0x18005bee0  mov     edx, 40000000h; dwDesiredAccess
0x18005bee5  mov     [rsp+0F0h+dwCreationDisposition], 2; dwCreationDisposition
0x18005beed  mov     rcx, rax; lpFileName
0x18005bef0  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x18005bef8  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], r13
0x18005befc  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], r13
0x18005bf00  call    cs:__imp_CreateFileA
0x18005bf06  mov     rsi, rax
0x18005bf09  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005bf0d  jz      short loc_18005BF6A
0x18005bf0f  mov     [rbp+57h+Buffer], 12345679h
0x18005bf17  mov     [rbp+57h+var_88], edi
0x18005bf1a  mov     [rbp+57h+var_84], r13d
0x18005bf1e  test    rbx, rbx
0x18005bf21  jz      short loc_18005BF35
0x18005bf23  lea     r8, [rbx+10h]; char *
0x18005bf27  mov     edx, 33h ; '3'; unsigned __int64
0x18005bf2c  lea     rcx, [rbp+57h+var_80]; char *
0x18005bf30  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18005bf35  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005bf39  mov     qword ptr [rsp+0F0h+dwCreationDisposition], r13; lpOverlapped
0x18005bf3e  mov     r8d, r15d; nNumberOfBytesToWrite
0x18005bf41  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x18005bf45  mov     rcx, rsi; hFile
0x18005bf48  call    cs:__imp_WriteFile
0x18005bf4e  test    eax, eax
0x18005bf50  jnz     short loc_18005BF96
0x18005bf52  mov     rcx, rsi; hObject
0x18005bf55  call    cs:__imp_CloseHandle
0x18005bf5b  mov     edx, 10h; unsigned int
0x18005bf60  mov     ecx, 1830h; int
0x18005bf65  call    ?MsgBox@@YAHHI@Z; MsgBox(int,uint)
0x18005bf6a  mov     eax, 80004005h
0x18005bf6f  mov     rcx, [rbp+57h+var_40]
0x18005bf73  xor     rcx, rsp; StackCookie
0x18005bf76  call    __security_check_cookie
0x18005bf7b  mov     rbx, [rsp+0F0h+arg_10]
0x18005bf83  add     rsp, 0C0h
0x18005bf8a  pop     r15
0x18005bf8c  pop     r14
0x18005bf8e  pop     r13
0x18005bf90  pop     r12
0x18005bf92  pop     rdi
0x18005bf93  pop     rsi
0x18005bf94  pop     rbp
0x18005bf95  retn
0x18005bf96  mov     rbx, [r14+8]
0x18005bf9a  mov     rdi, r13
0x18005bf9d  test    byte ptr [rbx+80h], 7
0x18005bfa4  jnz     loc_18005C050
0x18005bfaa  mov     r13d, [rbx+8]
0x18005bfae  mov     rcx, rdi; Block
0x18005bfb1  lea     r14d, [r13-1]
0x18005bfb5  lea     r12d, ds:74h[r14*4]
0x18005bfbd  movsxd  rdx, r12d; Size
0x18005bfc0  call    cs:__imp_realloc
0x18005bfc6  mov     r15, rax
0x18005bfc9  test    rax, rax
0x18005bfcc  jnz     short loc_18005BFDF
0x18005bfce  mov     rcx, rdi; Block
0x18005bfd1  call    cs:__imp_free
0x18005bfd7  xor     r13d, r13d
0x18005bfda  mov     rdi, r15
0x18005bfdd  jmp     short loc_18005C050
0x18005bfdf  mov     r10d, 33h ; '3'
0x18005bfe5  mov     [rax], r13d
0x18005bfe8  mov     edx, r10d; unsigned __int64
0x18005bfeb  lea     r8, [rbx+10h]; char *
0x18005bfef  lea     rcx, [rax+4]; char *
0x18005bff3  mov     rdi, r15
0x18005bff6  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18005bffb  lea     r8, [rbx+43h]; char *
0x18005bfff  mov     edx, r10d; unsigned __int64
0x18005c002  lea     rcx, [r15+37h]; char *
0x18005c006  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18005c00b  mov     r10d, [rbx+80h]
0x18005c012  xor     r13d, r13d
0x18005c015  mov     [r15+6Ch], r10d
0x18005c019  test    r14d, r14d
0x18005c01c  js      short loc_18005C034
0x18005c01e  mov     edx, r14d; int
0x18005c021  mov     rcx, rbx; this
0x18005c024  call    ?EnumHashes@CStructuralSubset@@QEAAKH@Z; CStructuralSubset::EnumHashes(int)
0x18005c029  mov     [r15+r14*4+70h], eax
0x18005c02e  sub     r14d, 1
0x18005c032  jns     short loc_18005C01E
0x18005c034  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005c038  mov     qword ptr [rsp+0F0h+dwCreationDisposition], r13; lpOverlapped
0x18005c03d  mov     r8d, r12d; nNumberOfBytesToWrite
0x18005c040  mov     rdx, r15; lpBuffer
0x18005c043  mov     rcx, rsi; hFile
0x18005c046  call    cs:__imp_WriteFile
0x18005c04c  test    eax, eax
0x18005c04e  jz      short loc_18005C074
0x18005c050  mov     rbx, [rbx+78h]
0x18005c054  test    rbx, rbx
0x18005c057  jnz     loc_18005BF9D
0x18005c05d  mov     rcx, rdi; Block
0x18005c060  call    cs:__imp_free
0x18005c066  mov     rcx, rsi; hObject
0x18005c069  call    cs:__imp_CloseHandle
0x18005c06f  jmp     loc_18005BE84
0x18005c074  mov     edx, 10h; unsigned int
0x18005c079  mov     ecx, 1830h; int
0x18005c07e  call    ?MsgBox@@YAHHI@Z; MsgBox(int,uint)
0x18005c083  mov     rcx, r15; Block
0x18005c086  call    cs:__imp_free
0x18005c08c  mov     rcx, rsi; hObject
0x18005c08f  call    cs:__imp_CloseHandle
0x18005c095  jmp     loc_18005BF6A
```
