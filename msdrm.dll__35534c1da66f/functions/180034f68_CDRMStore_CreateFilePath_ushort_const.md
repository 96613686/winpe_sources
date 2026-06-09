# CDRMStore::CreateFilePath(ushort const *)

- ea: `0x180034f68`
- end: `0x18003517e`
- name: `?CreateFilePath@CDRMStore@@AEAAJPEBG@Z`
- size: `534`
- prototype: `int(CDRMStore *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180036fc8`

## callees

- `0x180001244`
- `0x180001284`
- `0x180017210`
- `0x1800172d4`
- `0x180034f68`
- `0x180037e18`
- `0x18005bd72`

## import_xrefs

- `msvcrt!wcschr` at `0x180035029`
- `msvcrt!wcschr` at `0x1800350e3`
- `msvcrt!wcschr` at `0x180035029`
- `msvcrt!wcschr` at `0x1800350e3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003509d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180035130`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003509d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180035130`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035146`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035146`

## pseudocode

```c
__int64 __fastcall CDRMStore::CreateFilePath(CDRMStore *this, const unsigned __int16 *a2)
{
  __int64 v4; // rax
  unsigned __int16 *v5; // rdi
  void *v6; // r15
  signed int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned __int64 v10; // rsi
  unsigned __int16 *v11; // rax
  const wchar_t *v12; // rbp
  wchar_t *v13; // r14
  const unsigned __int16 *v14; // rdx
  unsigned int FileAttributesA; // eax
  const unsigned __int16 *v16; // rdx
  const unsigned __int16 *v17; // rdx
  unsigned int v18; // eax
  const unsigned __int16 *v19; // rdx
  signed int LastError; // eax

  v4 = -1;
  v5 = 0;
  do
    ++v4;
  while ( a2[v4] );
  if ( (_DWORD)v4 )
  {
    if ( g_fGlobalOptionUseServerProc )
    {
      v8 = *((_QWORD *)this + 6);
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)(v8 + 2 * v9) );
      LODWORD(v4) = v9 + v4 + 1;
    }
    v10 = (int)v4 + 1;
    v6 = operator new(saturated_mul(v10, 2u));
    if ( v6 && (v11 = (unsigned __int16 *)operator new(saturated_mul(v10, 2u)), (v5 = v11) != 0) )
    {
      *v11 = 0;
      v12 = a2 + 1;
      v7 = 0;
      if ( *a2 != 92 )
        v12 = a2;
      v13 = wcschr(v12, 0x5Cu);
      if ( v13 )
      {
        while ( 1 )
        {
          memset_0(v6, 0, 2 * v10);
          v7 = StringCchCopyNW((unsigned __int16 *)v6, v10, v12, v13 - v12);
          if ( v7 < 0 )
            break;
          v7 = StringCchCatW(v5, v10, (const unsigned __int16 *)v6);
          if ( v7 < 0 )
            break;
          FileAttributesA = DRMOS::GetFileAttributesA(v5, v14);
          if ( (FileAttributesA == -1 || (FileAttributesA & 0x10) == 0)
            && (!CreateDirectoryW(v5, 0) || DRMOS::GetFileAttributesA(v5, v16) == -1) )
          {
            goto LABEL_29;
          }
          v7 = StringCchCatW(v5, v10, L"\\");
          if ( v7 < 0 )
            break;
          v12 = v13 + 1;
          v13 = wcschr(v13 + 1, 0x5Cu);
          if ( !v13 )
            goto LABEL_23;
        }
      }
      else
      {
LABEL_23:
        if ( g_fGlobalOptionUseServerProc )
        {
          v7 = StringCchCatW(v5, v10, *((const unsigned __int16 **)this + 6));
          if ( v7 >= 0 )
          {
            v18 = DRMOS::GetFileAttributesA(v5, v17);
            if ( (v18 == -1 || (v18 & 0x10) == 0)
              && (!CreateDirectoryW(v5, (LPSECURITY_ATTRIBUTES)this + 1) || DRMOS::GetFileAttributesA(v5, v19) == -1) )
            {
LABEL_29:
              LastError = GetLastError();
              v7 = LastError;
              if ( LastError > 0 )
                v7 = (unsigned __int16)LastError | 0x80070000;
            }
          }
        }
      }
    }
    else
    {
      v7 = -2147024882;
    }
  }
  else
  {
    v6 = 0;
    v7 = -2147024809;
  }
  operator delete(v6);
  operator delete(v5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180034f68  push    rbx
0x180034f6a  push    rbp
0x180034f6b  push    rsi
0x180034f6c  push    rdi
0x180034f6d  push    r12
0x180034f6f  push    r13
0x180034f71  push    r14
0x180034f73  push    r15
0x180034f75  sub     rsp, 28h
0x180034f79  xor     r12d, r12d
0x180034f7c  mov     r14, rdx
0x180034f7f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180034f83  mov     r13, rcx
0x180034f86  mov     rax, rbx
0x180034f89  mov     edi, r12d
0x180034f8c  inc     rax
0x180034f8f  cmp     [rdx+rax*2], r12w
0x180034f94  jnz     short loc_180034F8C
0x180034f96  test    eax, eax
0x180034f98  jnz     short loc_180034FA7
0x180034f9a  mov     r15, r12
0x180034f9d  mov     ebx, 80070057h
0x180034fa2  jmp     loc_18003515B
0x180034fa7  cmp     cs:?g_fGlobalOptionUseServerProc@@3HA, r12d; int g_fGlobalOptionUseServerProc
0x180034fae  jz      short loc_180034FC5
0x180034fb0  mov     rdx, [rcx+30h]
0x180034fb4  mov     rcx, rbx
0x180034fb7  inc     rcx
0x180034fba  cmp     [rdx+rcx*2], r12w
0x180034fbf  jnz     short loc_180034FB7
0x180034fc1  inc     eax
0x180034fc3  add     eax, ecx
0x180034fc5  inc     eax
0x180034fc7  mov     ebp, 2
0x180034fcc  movsxd  rsi, eax
0x180034fcf  mov     eax, ebp
0x180034fd1  mul     rsi
0x180034fd4  cmovb   rax, rbx
0x180034fd8  mov     rcx, rax; Size
0x180034fdb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180034fe0  mov     r15, rax
0x180034fe3  test    rax, rax
0x180034fe6  jnz     short loc_180034FF2
0x180034fe8  mov     ebx, 8007000Eh
0x180034fed  jmp     loc_18003515B
0x180034ff2  mov     rax, rbp
0x180034ff5  mul     rsi
0x180034ff8  cmovb   rax, rbx
0x180034ffc  mov     rcx, rax; Size
0x180034fff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035004  mov     rdi, rax
0x180035007  test    rax, rax
0x18003500a  jz      short loc_180034FE8
0x18003500c  mov     [rax], r12w
0x180035010  lea     rbp, [r14+2]
0x180035014  mov     eax, 5Ch ; '\'
0x180035019  mov     ebx, r12d
0x18003501c  cmp     [r14], ax
0x180035020  mov     edx, eax; Ch
0x180035022  cmovnz  rbp, r14
0x180035026  mov     rcx, rbp; Str
0x180035029  call    cs:__imp_wcschr
0x18003502f  mov     r14, rax
0x180035032  test    rax, rax
0x180035035  jz      loc_1800350F8
0x18003503b  lea     r12, [rsi+rsi]
0x18003503f  mov     r8, r12; Size
0x180035042  xor     edx, edx; Val
0x180035044  mov     rcx, r15; void *
0x180035047  call    memset_0
0x18003504c  mov     r9, r14
0x18003504f  mov     r8, rbp; unsigned __int16 *
0x180035052  sub     r9, rbp
0x180035055  mov     rdx, rsi; unsigned __int64
0x180035058  sar     r9, 1; unsigned __int64
0x18003505b  mov     rcx, r15; unsigned __int16 *
0x18003505e  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180035063  mov     ebx, eax
0x180035065  test    eax, eax
0x180035067  js      loc_18003515B
0x18003506d  mov     r8, r15; unsigned __int16 *
0x180035070  mov     rdx, rsi; unsigned __int64
0x180035073  mov     rcx, rdi; unsigned __int16 *
0x180035076  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003507b  mov     ebx, eax
0x18003507d  test    eax, eax
0x18003507f  js      loc_18003515B
0x180035085  mov     rcx, rdi; lpFileName
0x180035088  call    ?GetFileAttributesA@DRMOS@@YAKPEBG@Z; DRMOS::GetFileAttributesA(ushort const *)
0x18003508d  or      ebx, 0FFFFFFFFh
0x180035090  cmp     eax, ebx
0x180035092  jz      short loc_180035098
0x180035094  test    al, 10h
0x180035096  jnz     short loc_1800350BB
0x180035098  xor     edx, edx; lpSecurityAttributes
0x18003509a  mov     rcx, rdi; lpPathName
0x18003509d  call    cs:__imp_CreateDirectoryW
0x1800350a3  test    eax, eax
0x1800350a5  jz      loc_180035146
0x1800350ab  mov     rcx, rdi; lpFileName
0x1800350ae  call    ?GetFileAttributesA@DRMOS@@YAKPEBG@Z; DRMOS::GetFileAttributesA(ushort const *)
0x1800350b3  cmp     eax, ebx
0x1800350b5  jz      loc_180035146
0x1800350bb  lea     r8, SubBlock; "\\"
0x1800350c2  mov     rdx, rsi; unsigned __int64
0x1800350c5  mov     rcx, rdi; unsigned __int16 *
0x1800350c8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800350cd  mov     ebx, eax
0x1800350cf  test    eax, eax
0x1800350d1  js      loc_18003515B
0x1800350d7  lea     rbp, [r14+2]
0x1800350db  mov     edx, 5Ch ; '\'; Ch
0x1800350e0  mov     rcx, rbp; Str
0x1800350e3  call    cs:__imp_wcschr
0x1800350e9  mov     r14, rax
0x1800350ec  test    rax, rax
0x1800350ef  jnz     loc_18003503F
0x1800350f5  xor     r12d, r12d
0x1800350f8  cmp     cs:?g_fGlobalOptionUseServerProc@@3HA, r12d; int g_fGlobalOptionUseServerProc
0x1800350ff  jz      short loc_18003515B
0x180035101  mov     r8, [r13+30h]; unsigned __int16 *
0x180035105  mov     rdx, rsi; unsigned __int64
0x180035108  mov     rcx, rdi; unsigned __int16 *
0x18003510b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180035110  mov     ebx, eax
0x180035112  test    eax, eax
0x180035114  js      short loc_18003515B
0x180035116  mov     rcx, rdi; lpFileName
0x180035119  call    ?GetFileAttributesA@DRMOS@@YAKPEBG@Z; DRMOS::GetFileAttributesA(ushort const *)
0x18003511e  or      esi, 0FFFFFFFFh
0x180035121  cmp     eax, esi
0x180035123  jz      short loc_180035129
0x180035125  test    al, 10h
0x180035127  jnz     short loc_18003515B
0x180035129  lea     rdx, [r13+18h]; lpSecurityAttributes
0x18003512d  mov     rcx, rdi; lpPathName
0x180035130  call    cs:__imp_CreateDirectoryW
0x180035136  test    eax, eax
0x180035138  jz      short loc_180035146
0x18003513a  mov     rcx, rdi; lpFileName
0x18003513d  call    ?GetFileAttributesA@DRMOS@@YAKPEBG@Z; DRMOS::GetFileAttributesA(ushort const *)
0x180035142  cmp     eax, esi
0x180035144  jnz     short loc_18003515B
0x180035146  call    cs:__imp_GetLastError
0x18003514c  mov     ebx, eax
0x18003514e  test    eax, eax
0x180035150  jle     short loc_18003515B
0x180035152  movzx   ebx, ax
0x180035155  or      ebx, 80070000h
0x18003515b  mov     rcx, r15; Block
0x18003515e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180035163  mov     rcx, rdi; Block
0x180035166  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003516b  mov     eax, ebx
0x18003516d  add     rsp, 28h
0x180035171  pop     r15
0x180035173  pop     r14
0x180035175  pop     r13
0x180035177  pop     r12
0x180035179  pop     rdi
0x18003517a  pop     rsi
0x18003517b  pop     rbp
0x18003517c  pop     rbx
0x18003517d  retn
```
