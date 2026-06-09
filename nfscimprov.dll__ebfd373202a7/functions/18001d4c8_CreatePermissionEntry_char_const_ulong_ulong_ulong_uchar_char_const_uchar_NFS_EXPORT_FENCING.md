# CreatePermissionEntry(char const *,ulong,ulong *,ulong *,uchar *,char const *,uchar,_NFS_EXPORT_FENCING * *)

- ea: `0x18001d4c8`
- end: `0x18001d792`
- name: `?CreatePermissionEntry@@YAKPEBDKPEAK1PEAE0EPEAPEAU_NFS_EXPORT_FENCING@@@Z`
- size: `714`
- prototype: `unsigned int __usercall@<eax>(const char *@<rcx>, unsigned int@<edx>, unsigned int *@<r8>, unsigned int *@<r9>, unsigned __int8 *, const char *, unsigned __int8, struct _NFS_EXPORT_FENCING **)`
- caller_count: `4`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x18000c814`
- `0x18001d024`
- `0x180020720`
- `0x18002783c`

## callees

- `0x180006a28`
- `0x180006a54`
- `0x180009670`
- `0x18001cda0`
- `0x18001d4c8`
- `0x18001e3c0`
- `0x180021120`
- `0x1800219fc`
- `0x180021af0`
- `0x180024f40`
- `0x180026a4c`
- `0x180035b40`

## import_xrefs

- `msvcrt!free` at `0x18001d670`
- `msvcrt!free` at `0x18001d6b5`
- `msvcrt!free` at `0x18001d6f9`
- `msvcrt!free` at `0x18001d74d`
- `msvcrt!free` at `0x18001d670`
- `msvcrt!free` at `0x18001d6b5`
- `msvcrt!free` at `0x18001d6f9`
- `msvcrt!free` at `0x18001d74d`
- `KERNEL32!HeapAlloc` at `0x18001d53b`
- `KERNEL32!HeapAlloc` at `0x18001d57f`
- `KERNEL32!HeapAlloc` at `0x18001d53b`
- `KERNEL32!HeapAlloc` at `0x18001d57f`
- `KERNEL32!GetProcessHeap` at `0x18001d529`
- `KERNEL32!GetProcessHeap` at `0x18001d571`
- `KERNEL32!GetProcessHeap` at `0x18001d529`
- `KERNEL32!GetProcessHeap` at `0x18001d571`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CreatePermissionEntry(
        const char *a1,
        int a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned __int8 *a5,
        char *a6,
        unsigned __int8 a7,
        struct _NFS_EXPORT_FENCING **a8)
{
  const char *v10; // r14
  char v11; // r12
  HANDLE ProcessHeap; // rax
  unsigned int ErrorFromHr; // ebx
  _DWORD *v14; // rax
  _DWORD *v15; // rdi
  unsigned __int64 v16; // rax
  SIZE_T v17; // rsi
  HANDLE v18; // rax
  char *v19; // rax
  int v20; // eax
  int v21; // eax
  const unsigned __int16 **v23; // rax
  bool v24; // zf
  wchar_t **v25; // rax
  unsigned __int8 valid; // si
  const unsigned __int16 **v27; // rax
  unsigned int v28; // r8d
  int v29; // esi
  unsigned __int8 v30[4]; // [rsp+20h] [rbp-E0h] BYREF
  int v31; // [rsp+24h] [rbp-DCh]
  unsigned int *v32; // [rsp+28h] [rbp-D8h]
  unsigned int *v33; // [rsp+30h] [rbp-D0h]
  struct _NFS_EXPORT_FENCING **v34; // [rsp+38h] [rbp-C8h]
  void *v35; // [rsp+40h] [rbp-C0h] BYREF
  char v36; // [rsp+48h] [rbp-B8h] BYREF
  void *Block; // [rsp+D0h] [rbp-30h] BYREF
  char v38; // [rsp+D8h] [rbp-28h] BYREF
  void *v39; // [rsp+1E0h] [rbp+E0h] BYREF
  char v40; // [rsp+1E8h] [rbp+E8h] BYREF
  void *v41; // [rsp+2F0h] [rbp+1F0h] BYREF
  char v42; // [rsp+2F8h] [rbp+1F8h] BYREF
  WCHAR pStringBuf[72]; // [rsp+400h] [rbp+300h] BYREF

  v32 = a4;
  v33 = a3;
  v10 = a6;
  v34 = a8;
  v11 = 0;
  v31 = 0;
  v30[0] = 0;
  *a8 = 0;
  ProcessHeap = GetProcessHeap();
  ErrorFromHr = 8;
  v14 = HeapAlloc(ProcessHeap, 8u, 0x70u);
  v15 = v14;
  if ( v14 )
  {
    v14[21] = 2;
    v14[22] = 7;
    v16 = -1;
    do
      ++v16;
    while ( a1[v16] );
    v17 = v16 + 1;
    if ( v16 + 1 < v16 )
    {
      v20 = -2147024362;
    }
    else
    {
      v18 = GetProcessHeap();
      v19 = (char *)HeapAlloc(v18, 8u, v17);
      *((_QWORD *)v15 + 1) = v19;
      if ( v19 )
      {
        ErrorFromHr = 0;
        v20 = StringCchCopyA(v19, v17, a1);
        if ( v20 >= 0 )
          goto LABEL_11;
      }
      else
      {
        v20 = -2147024882;
      }
    }
    ErrorFromHr = NfsGetErrorFromHr(v20);
    if ( ErrorFromHr )
    {
LABEL_20:
      FreeNfsPermissionEntry(v15);
      return ErrorFromHr;
    }
LABEL_11:
    if ( !a6 )
    {
      v21 = StringCchCopyW(pStringBuf, 0x41u, L"00.00.00.00");
      if ( v21 < 0 )
      {
        ErrorFromHr = NfsGetErrorFromHr(v21);
        if ( ErrorFromHr )
          goto LABEL_20;
      }
    }
    if ( a7 )
    {
      if ( a2 == 1 )
      {
        if ( a6 )
          goto LABEL_37;
        v27 = (const unsigned __int16 **)ATL::CA2WEX<128>::CA2WEX<128>(&v41, a1);
        ErrorFromHr = NfsGetIpAddressString(*v27, pStringBuf, v28);
        if ( v41 != &v42 )
          free(v41);
        if ( ErrorFromHr )
          goto LABEL_20;
      }
      else
      {
        switch ( a2 )
        {
          case 2:
            v25 = (wchar_t **)ATL::CA2WEX<128>::CA2WEX<128>(&v39, a1);
            valid = IsValidGroupName(*v25);
            if ( v39 != &v40 )
              free(v39);
            v24 = valid == 0;
            break;
          case 3:
            v23 = (const unsigned __int16 **)ATL::CA2WEX<128>::CA2WEX<128>(&Block, a1);
            ErrorFromHr = NfsIsNetgroupNameValid(*v23, v30);
            if ( Block != &v38 )
              free(Block);
            if ( ErrorFromHr )
              goto LABEL_20;
            v24 = v30[0] == 0;
            break;
          case 4:
            goto LABEL_35;
          default:
LABEL_19:
            ErrorFromHr = 87;
            goto LABEL_20;
        }
        if ( v24 )
          goto LABEL_19;
      }
    }
LABEL_35:
    if ( !a6 )
    {
      v11 = 1;
      v10 = *(const char **)ATL::CW2AEX<128>::CW2AEX<128>(&v35, pStringBuf);
    }
LABEL_37:
    v29 = StringCchCopyA((char *)v15 + 16, 0x41u, v10);
    if ( (v11 & 1) != 0 && v35 != &v36 )
      free(v35);
    if ( v29 >= 0 || (ErrorFromHr = NfsGetErrorFromHr(v29)) == 0 )
    {
      UpdatePermissionEntry(v15, v33, v32, a5);
      *v15 = a2;
      *v34 = (struct _NFS_EXPORT_FENCING *)v15;
      return ErrorFromHr;
    }
    goto LABEL_20;
  }
  return ErrorFromHr;
}

```

## disassembly

```asm
0x18001d4c8  push    rbp
0x18001d4ca  push    rbx
0x18001d4cb  push    rsi
0x18001d4cc  push    rdi
0x18001d4cd  push    r12
0x18001d4cf  push    r13
0x18001d4d1  push    r14
0x18001d4d3  push    r15
0x18001d4d5  lea     rbp, [rsp-3A8h]
0x18001d4dd  sub     rsp, 4A8h
0x18001d4e4  mov     rax, cs:__security_cookie
0x18001d4eb  xor     rax, rsp
0x18001d4ee  mov     [rbp+3E0h+var_50], rax
0x18001d4f5  mov     [rsp+4E0h+var_4B8], r9
0x18001d4fa  mov     [rsp+4E0h+var_4B0], r8
0x18001d4ff  mov     r13d, edx
0x18001d502  mov     r15, rcx
0x18001d505  mov     r14, [rbp+3E0h+arg_28]
0x18001d50c  mov     rax, [rbp+3E0h+arg_38]
0x18001d513  mov     [rsp+4E0h+var_4A8], rax
0x18001d518  xor     esi, esi
0x18001d51a  mov     r12d, esi
0x18001d51d  mov     [rsp+4E0h+var_4BC], esi
0x18001d521  mov     [rsp+4E0h+var_4C0], sil
0x18001d526  mov     [rax], rsi
0x18001d529  call    cs:__imp_GetProcessHeap
0x18001d52f  mov     rcx, rax; hHeap
0x18001d532  lea     ebx, [rsi+8]
0x18001d535  lea     r8d, [rsi+70h]; dwBytes
0x18001d539  mov     edx, ebx; dwFlags
0x18001d53b  call    cs:__imp_HeapAlloc
0x18001d541  mov     rdi, rax
0x18001d544  test    rax, rax
0x18001d547  jz      loc_18001D623
0x18001d54d  mov     dword ptr [rax+54h], 2
0x18001d554  mov     dword ptr [rax+58h], 7
0x18001d55b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001d55f  inc     rax
0x18001d562  cmp     [r15+rax], sil
0x18001d566  jnz     short loc_18001D55F
0x18001d568  lea     rsi, [rax+1]
0x18001d56c  cmp     rsi, rax
0x18001d56f  jb      short loc_18001D5AB
0x18001d571  call    cs:__imp_GetProcessHeap
0x18001d577  mov     rcx, rax; hHeap
0x18001d57a  mov     r8, rsi; dwBytes
0x18001d57d  mov     edx, ebx; dwFlags
0x18001d57f  call    cs:__imp_HeapAlloc
0x18001d585  mov     [rdi+8], rax
0x18001d589  test    rax, rax
0x18001d58c  jz      short loc_18001D5A4
0x18001d58e  xor     ebx, ebx
0x18001d590  mov     r8, r15; char *
0x18001d593  mov     rdx, rsi; unsigned __int64
0x18001d596  mov     rcx, rax; char *
0x18001d599  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18001d59e  test    eax, eax
0x18001d5a0  jns     short loc_18001D5BD
0x18001d5a2  jmp     short loc_18001D5B0
0x18001d5a4  mov     eax, 8007000Eh
0x18001d5a9  jmp     short loc_18001D5B0
0x18001d5ab  mov     eax, 80070216h
0x18001d5b0  mov     ecx, eax; int
0x18001d5b2  call    ?NfsGetErrorFromHr@@YAKJ@Z; NfsGetErrorFromHr(long)
0x18001d5b7  mov     ebx, eax
0x18001d5b9  test    eax, eax
0x18001d5bb  jnz     short loc_18001D61B
0x18001d5bd  test    r14, r14
0x18001d5c0  jnz     short loc_18001D5EA
0x18001d5c2  lea     r8, a00000000; "00.00.00.00"
0x18001d5c9  lea     edx, [r14+41h]; unsigned __int64
0x18001d5cd  lea     rcx, [rbp+3E0h+pStringBuf]; unsigned __int16 *
0x18001d5d4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d5d9  test    eax, eax
0x18001d5db  jns     short loc_18001D5EA
0x18001d5dd  mov     ecx, eax; int
0x18001d5df  call    ?NfsGetErrorFromHr@@YAKJ@Z; NfsGetErrorFromHr(long)
0x18001d5e4  mov     ebx, eax
0x18001d5e6  test    eax, eax
0x18001d5e8  jnz     short loc_18001D61B
0x18001d5ea  cmp     [rbp+3E0h+arg_30], r12b
0x18001d5f1  jz      loc_18001D708
0x18001d5f7  mov     eax, r13d
0x18001d5fa  sub     eax, 1
0x18001d5fd  jz      loc_18001D6C1
0x18001d603  sub     eax, 1
0x18001d606  jz      short loc_18001D687
0x18001d608  sub     eax, 1
0x18001d60b  jz      short loc_18001D648
0x18001d60d  cmp     eax, 1
0x18001d610  jz      loc_18001D708
0x18001d616  mov     ebx, 57h ; 'W'
0x18001d61b  mov     rcx, rdi
0x18001d61e  call    FreeNfsPermissionEntry
0x18001d623  mov     eax, ebx
0x18001d625  mov     rcx, [rbp+3E0h+var_50]
0x18001d62c  xor     rcx, rsp; StackCookie
0x18001d62f  call    __security_check_cookie
0x18001d634  add     rsp, 4A8h
0x18001d63b  pop     r15
0x18001d63d  pop     r14
0x18001d63f  pop     r13
0x18001d641  pop     r12
0x18001d643  pop     rdi
0x18001d644  pop     rsi
0x18001d645  pop     rbx
0x18001d646  pop     rbp
0x18001d647  retn
0x18001d648  mov     rdx, r15
0x18001d64b  lea     rcx, [rbp+3E0h+Block]
0x18001d64f  call    ??0?$CA2WEX@$0IA@@ATL@@QEAA@PEBD@Z; ATL::CA2WEX<128>::CA2WEX<128>(char const *)
0x18001d654  lea     rdx, [rsp+4E0h+var_4C0]; unsigned __int8 *
0x18001d659  mov     rcx, [rax]; unsigned __int16 *
0x18001d65c  call    ?NfsIsNetgroupNameValid@@YAKPEBGPEAE@Z; NfsIsNetgroupNameValid(ushort const *,uchar *)
0x18001d661  mov     ebx, eax
0x18001d663  mov     rcx, [rbp+3E0h+Block]; Block
0x18001d667  lea     rax, [rbp+3E0h+var_408]
0x18001d66b  cmp     rcx, rax
0x18001d66e  jz      short loc_18001D677
0x18001d670  call    cs:__imp_free
0x18001d676  nop
0x18001d677  test    ebx, ebx
0x18001d679  jnz     short loc_18001D61B
0x18001d67b  cmp     [rsp+4E0h+var_4C0], bl
0x18001d67f  jnz     loc_18001D708
0x18001d685  jmp     short loc_18001D616
0x18001d687  mov     rdx, r15
0x18001d68a  lea     rcx, [rbp+3E0h+var_300]
0x18001d691  call    ??0?$CA2WEX@$0IA@@ATL@@QEAA@PEBD@Z; ATL::CA2WEX<128>::CA2WEX<128>(char const *)
0x18001d696  nop
0x18001d697  mov     rcx, [rax]; String1
0x18001d69a  call    ?IsValidGroupName@@YAEPEBG@Z; IsValidGroupName(ushort const *)
0x18001d69f  mov     sil, al
0x18001d6a2  mov     rcx, [rbp+3E0h+var_300]; Block
0x18001d6a9  lea     rax, [rbp+3E0h+var_2F8]
0x18001d6b0  cmp     rcx, rax
0x18001d6b3  jz      short loc_18001D6BC
0x18001d6b5  call    cs:__imp_free
0x18001d6bb  nop
0x18001d6bc  test    sil, sil
0x18001d6bf  jmp     short loc_18001D67F
0x18001d6c1  test    r14, r14
0x18001d6c4  jnz     short loc_18001D725
0x18001d6c6  mov     rdx, r15
0x18001d6c9  lea     rcx, [rbp+3E0h+var_1F0]
0x18001d6d0  call    ??0?$CA2WEX@$0IA@@ATL@@QEAA@PEBD@Z; ATL::CA2WEX<128>::CA2WEX<128>(char const *)
0x18001d6d5  lea     rdx, [rbp+3E0h+pStringBuf]; pStringBuf
0x18001d6dc  mov     rcx, [rax]; unsigned __int16 *
0x18001d6df  call    ?NfsGetIpAddressString@@YAKPEBGPEAGK@Z; NfsGetIpAddressString(ushort const *,ushort *,ulong)
0x18001d6e4  mov     ebx, eax
0x18001d6e6  mov     rcx, [rbp+3E0h+var_1F0]; Block
0x18001d6ed  lea     rax, [rbp+3E0h+var_1E8]
0x18001d6f4  cmp     rcx, rax
0x18001d6f7  jz      short loc_18001D700
0x18001d6f9  call    cs:__imp_free
0x18001d6ff  nop
0x18001d700  test    ebx, ebx
0x18001d702  jnz     loc_18001D61B
0x18001d708  test    r14, r14
0x18001d70b  jnz     short loc_18001D725
0x18001d70d  lea     rdx, [rbp+3E0h+pStringBuf]
0x18001d714  lea     rcx, [rsp+4E0h+var_4A0]
0x18001d719  call    ??0?$CW2AEX@$0IA@@ATL@@QEAA@PEBG@Z; ATL::CW2AEX<128>::CW2AEX<128>(ushort const *)
0x18001d71e  lea     r12d, [r14+1]
0x18001d722  mov     r14, [rax]
0x18001d725  lea     rcx, [rdi+10h]; char *
0x18001d729  mov     r8, r14; char *
0x18001d72c  mov     edx, 41h ; 'A'; unsigned __int64
0x18001d731  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18001d736  mov     esi, eax
0x18001d738  test    r12b, 1
0x18001d73c  jz      short loc_18001D754
0x18001d73e  mov     rcx, [rsp+4E0h+var_4A0]; Block
0x18001d743  lea     rax, [rsp+4E0h+var_498]
0x18001d748  cmp     rcx, rax
0x18001d74b  jz      short loc_18001D754
0x18001d74d  call    cs:__imp_free
0x18001d753  nop
0x18001d754  test    esi, esi
0x18001d756  jns     short loc_18001D769
0x18001d758  mov     ecx, esi; int
0x18001d75a  call    ?NfsGetErrorFromHr@@YAKJ@Z; NfsGetErrorFromHr(long)
0x18001d75f  mov     ebx, eax
0x18001d761  test    eax, eax
0x18001d763  jnz     loc_18001D61B
0x18001d769  mov     r9, [rbp+3E0h+arg_20]
0x18001d770  mov     r8, [rsp+4E0h+var_4B8]
0x18001d775  mov     rdx, [rsp+4E0h+var_4B0]
0x18001d77a  mov     rcx, rdi
0x18001d77d  call    UpdatePermissionEntry
0x18001d782  mov     [rdi], r13d
0x18001d785  mov     rax, [rsp+4E0h+var_4A8]
0x18001d78a  mov     [rax], rdi
0x18001d78d  jmp     loc_18001D623
```
