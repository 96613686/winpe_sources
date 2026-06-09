# CreateFtpPidlFromFtpWirePathHelper(char const *,ulong *,_ITEMIDLIST * *,int,int,_ITEMIDLIST * *,char * *)

- ea: `0x18001b710`
- end: `0x18001b916`
- name: `?CreateFtpPidlFromFtpWirePathHelper@@YAJPEBDPEAKPEAPEFAU_ITEMIDLIST@@HH2PEAPEAD@Z`
- size: `518`
- prototype: `__int64 __usercall@<rax>(PCSTR pszStart@<rcx>, unsigned int *@<rdx>, struct _ITEMIDLIST **@<r8>, int@<r9d>, int, struct _ITEMIDLIST **, char **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001b614`

## callees

- `0x180002240`
- `0x18000c3b8`
- `0x18001b710`
- `0x18001bf54`
- `0x180026ef0`

## import_xrefs

- `SHLWAPI!StrChrA` at `0x18001b783`
- `SHLWAPI!StrChrA` at `0x18001b783`
- `USER32!CharNextA` at `0x18001b772`
- `USER32!CharNextA` at `0x18001b7f1`
- `USER32!CharNextA` at `0x18001b772`
- `USER32!CharNextA` at `0x18001b7f1`

## pseudocode

```c
__int64 __fastcall CreateFtpPidlFromFtpWirePathHelper(
        PCSTR pszStart,
        unsigned int *a2,
        struct _ITEMIDLIST **a3,
        __int64 a4,
        int a5,
        struct _ITEMIDLIST **a6,
        char **a7)
{
  const CHAR *v8; // rbx
  PSTR v9; // rax
  __int64 v10; // rdi
  const CHAR *v11; // r8
  unsigned int v12; // eax
  __int64 v13; // rcx
  char *v14; // rdx
  __int64 v15; // rax
  char *v16; // rax
  CHAR v17; // bl
  LPSTR v18; // rax
  __int64 v19; // rdx
  _BYTE *v20; // rcx
  _BYTE *v21; // rax
  BOOL v22; // ecx
  char v23; // al
  __int64 v24; // rdx
  char *v25; // rcx
  char *v26; // rax
  int v27; // ebx
  int v28; // ebx
  struct _ITEMIDLIST *v30; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v31[272]; // [rsp+40h] [rbp-C0h] BYREF
  char v32[272]; // [rsp+150h] [rbp+50h] BYREF
  WCHAR pszPath[264]; // [rsp+260h] [rbp+160h] BYREF

  v8 = pszStart;
  v30 = 0;
  *a7 = 0;
  *a3 = 0;
  if ( *pszStart == 47 )
    v8 = CharNextA(pszStart);
  v9 = StrChrA(v8, 0x2Fu);
  v10 = 2147483646;
  v11 = v9;
  if ( v9 )
  {
    v12 = (_DWORD)v9 - (_DWORD)v8 + 1;
    if ( v12 > 0x104 )
    {
      v13 = 260;
    }
    else
    {
      if ( !v12 )
      {
LABEL_15:
        v17 = *v11;
        v18 = CharNextA(v11);
        v19 = 260;
        v20 = v31;
        do
        {
          if ( !v10 )
            break;
          if ( !*v18 )
            break;
          *v20++ = *v18++;
          --v10;
          --v19;
        }
        while ( v19 );
        v21 = v20 - 1;
        if ( v19 )
          v21 = v20;
        v22 = v17 != 47;
        *v21 = 0;
        v23 = v31[0];
        goto LABEL_29;
      }
      v13 = v12;
    }
    v14 = v32;
    v15 = 2147483646;
    do
    {
      if ( !v15 )
        break;
      if ( !*v8 )
        break;
      *v14++ = *v8++;
      --v15;
      --v13;
    }
    while ( v13 );
    v16 = v14 - 1;
    if ( v13 )
      v16 = v14;
    *v16 = 0;
    goto LABEL_15;
  }
  v24 = 260;
  v25 = v32;
  do
  {
    if ( !v10 )
      break;
    if ( !*v8 )
      break;
    *v25++ = *v8++;
    --v10;
    --v24;
  }
  while ( v24 );
  v26 = v25 - 1;
  if ( v24 )
    v26 = v25;
  v22 = 1;
  *v26 = 0;
  v23 = 0;
  v31[0] = 0;
LABEL_29:
  v27 = v23 != 0 && v22;
  WireBytesToUnicode(v32, 0, pszPath, 260);
  v28 = FtpItemID_CreateFake(pszPath, v32, 1, v27, 0, &v30);
  if ( v28 >= 0 )
  {
    if ( v31[0] )
    {
      Str_SetPtrA(a7, v31);
      *a6 = v30;
    }
    else
    {
      *a3 = v30;
    }
  }
  return (unsigned int)v28;
}

```

## disassembly

```asm
0x18001b710  mov     [rsp-8+arg_8], rbx
0x18001b715  mov     [rsp-8+arg_18], rsi
0x18001b71a  push    rbp
0x18001b71b  push    rdi
0x18001b71c  push    r12
0x18001b71e  push    r14
0x18001b720  push    r15
0x18001b722  lea     rbp, [rsp-380h]
0x18001b72a  sub     rsp, 480h
0x18001b731  mov     rax, cs:__security_cookie
0x18001b738  xor     rax, rsp
0x18001b73b  mov     [rbp+3A0h+var_30], rax
0x18001b742  mov     r15, [rbp+3A0h+arg_30]
0x18001b749  mov     r14, r8
0x18001b74c  mov     r12, [rbp+3A0h+arg_28]
0x18001b753  mov     rbx, rcx
0x18001b756  mov     [rsp+4A0h+var_470], 0
0x18001b75f  mov     qword ptr [r15], 0
0x18001b766  mov     qword ptr [r8], 0
0x18001b76d  cmp     byte ptr [rcx], 2Fh ; '/'
0x18001b770  jnz     short loc_18001B77B
0x18001b772  call    cs:__imp_CharNextA
0x18001b778  mov     rbx, rax
0x18001b77b  mov     edx, 2Fh ; '/'; wMatch
0x18001b780  mov     rcx, rbx; pszStart
0x18001b783  call    cs:__imp_StrChrA
0x18001b789  mov     edi, 7FFFFFFEh
0x18001b78e  mov     esi, 104h
0x18001b793  mov     r8, rax
0x18001b796  test    rax, rax
0x18001b799  jz      loc_18001B83A
0x18001b79f  sub     eax, ebx
0x18001b7a1  inc     eax
0x18001b7a3  cmp     eax, esi
0x18001b7a5  ja      short loc_18001B7AF
0x18001b7a7  test    eax, eax
0x18001b7a9  jz      short loc_18001B7EB
0x18001b7ab  mov     ecx, eax
0x18001b7ad  jmp     short loc_18001B7B2
0x18001b7af  mov     rcx, rsi
0x18001b7b2  lea     rdx, [rbp+3A0h+var_350]
0x18001b7b6  mov     rax, rdi
0x18001b7b9  test    rcx, rcx
0x18001b7bc  jz      short loc_18001B7DD
0x18001b7be  test    rax, rax
0x18001b7c1  jz      short loc_18001B7DD
0x18001b7c3  mov     r9b, [rbx]
0x18001b7c6  test    r9b, r9b
0x18001b7c9  jz      short loc_18001B7DD
0x18001b7cb  mov     [rdx], r9b
0x18001b7ce  inc     rbx
0x18001b7d1  inc     rdx
0x18001b7d4  dec     rax
0x18001b7d7  sub     rcx, 1
0x18001b7db  jnz     short loc_18001B7BE
0x18001b7dd  test    rcx, rcx
0x18001b7e0  lea     rax, [rdx-1]
0x18001b7e4  cmovnz  rax, rdx
0x18001b7e8  mov     byte ptr [rax], 0
0x18001b7eb  mov     bl, [r8]
0x18001b7ee  mov     rcx, r8; lpsz
0x18001b7f1  call    cs:__imp_CharNextA
0x18001b7f7  mov     rdx, rsi
0x18001b7fa  lea     rcx, [rsp+4A0h+var_460]
0x18001b7ff  test    rdi, rdi
0x18001b802  jz      short loc_18001B81E
0x18001b804  mov     r8b, [rax]
0x18001b807  test    r8b, r8b
0x18001b80a  jz      short loc_18001B81E
0x18001b80c  mov     [rcx], r8b
0x18001b80f  inc     rax
0x18001b812  inc     rcx
0x18001b815  dec     rdi
0x18001b818  sub     rdx, 1
0x18001b81c  jnz     short loc_18001B7FF
0x18001b81e  lea     rax, [rcx-1]
0x18001b822  test    rdx, rdx
0x18001b825  cmovnz  rax, rcx
0x18001b829  xor     ecx, ecx
0x18001b82b  cmp     bl, 2Fh ; '/'
0x18001b82e  setnz   cl
0x18001b831  mov     byte ptr [rax], 0
0x18001b834  mov     al, [rsp+4A0h+var_460]
0x18001b838  jmp     short loc_18001B876
0x18001b83a  mov     rdx, rsi
0x18001b83d  lea     rcx, [rbp+3A0h+var_350]
0x18001b841  test    rdi, rdi
0x18001b844  jz      short loc_18001B85D
0x18001b846  mov     al, [rbx]
0x18001b848  test    al, al
0x18001b84a  jz      short loc_18001B85D
0x18001b84c  mov     [rcx], al
0x18001b84e  inc     rbx
0x18001b851  inc     rcx
0x18001b854  dec     rdi
0x18001b857  sub     rdx, 1
0x18001b85b  jnz     short loc_18001B841
0x18001b85d  test    rdx, rdx
0x18001b860  lea     rax, [rcx-1]
0x18001b864  cmovnz  rax, rcx
0x18001b868  mov     ecx, 1
0x18001b86d  mov     byte ptr [rax], 0
0x18001b870  xor     al, al
0x18001b872  mov     [rsp+4A0h+var_460], al
0x18001b876  neg     al
0x18001b878  lea     r8, [rbp+3A0h+pszPath]
0x18001b87f  mov     r9d, esi
0x18001b882  sbb     ebx, ebx
0x18001b884  xor     edx, edx
0x18001b886  and     ebx, ecx
0x18001b888  lea     rcx, [rbp+3A0h+var_350]
0x18001b88c  call    ?WireBytesToUnicode@@YAJPEBDW4WIREENC@@PEAGK@Z; WireBytesToUnicode(char const *,WIREENC,ushort *,ulong)
0x18001b891  lea     rax, [rsp+4A0h+var_470]
0x18001b896  mov     r9d, ebx; int
0x18001b899  mov     [rsp+4A0h+var_478], rax; struct _ITEMIDLIST **
0x18001b89e  lea     rdx, [rbp+3A0h+var_350]; char *
0x18001b8a2  mov     r8d, 1; int
0x18001b8a8  mov     [rsp+4A0h+var_480], 0; int
0x18001b8b0  lea     rcx, [rbp+3A0h+pszPath]; pszPath
0x18001b8b7  call    ?FtpItemID_CreateFake@@YAJPEBGPEBDHHHPEAPEFAU_ITEMIDLIST@@@Z; FtpItemID_CreateFake(ushort const *,char const *,int,int,int,_ITEMIDLIST * *)
0x18001b8bc  mov     ebx, eax
0x18001b8be  test    eax, eax
0x18001b8c0  js      short loc_18001B8E9
0x18001b8c2  cmp     [rsp+4A0h+var_460], 0
0x18001b8c7  jz      short loc_18001B8E1
0x18001b8c9  lea     rdx, [rsp+4A0h+var_460]
0x18001b8ce  mov     rcx, r15
0x18001b8d1  call    Str_SetPtrA
0x18001b8d6  mov     rcx, [rsp+4A0h+var_470]
0x18001b8db  mov     [r12], rcx
0x18001b8df  jmp     short loc_18001B8E9
0x18001b8e1  mov     rax, [rsp+4A0h+var_470]
0x18001b8e6  mov     [r14], rax
0x18001b8e9  mov     eax, ebx
0x18001b8eb  mov     rcx, [rbp+3A0h+var_30]
0x18001b8f2  xor     rcx, rsp; StackCookie
0x18001b8f5  call    __security_check_cookie
0x18001b8fa  lea     r11, [rsp+4A0h+var_20]
0x18001b902  mov     rbx, [r11+38h]
0x18001b906  mov     rsi, [r11+48h]
0x18001b90a  mov     rsp, r11
0x18001b90d  pop     r15
0x18001b90f  pop     r14
0x18001b911  pop     r12
0x18001b913  pop     rdi
0x18001b914  pop     rbp
0x18001b915  retn
```
