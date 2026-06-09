# diaRelease(_MODULE_ENTRY *,void *)

- ea: `0x180016c04`
- end: `0x180016d0d`
- name: `?diaRelease@@YAXPEAU_MODULE_ENTRY@@PEAX@Z`
- size: `265`
- prototype: `void(struct _MODULE_ENTRY *, void *)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800035b0`
- `0x180008740`
- `0x18000a820`
- `0x180017308`

## callees

- `0x18000dfac`
- `0x180016c04`
- `0x180016d14`
- `0x180021374`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180016cd2`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180016cd2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180016c98`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180016c98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016cb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ceb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016cb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ceb`

## string_xrefs

- `0x180016cba`: `........DeleteFile(%u,%ws)\n`
- `0x180016cf4`: `........RemoveDirectory(%u,%ws)\n`

## pseudocode

```c
void __fastcall diaRelease(struct _MODULE_ENTRY *a1, DIA *a2)
{
  const WCHAR *v3; // rbx
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rdi
  int v7; // ecx
  DWORD LastError; // eax
  int v9; // ecx
  DWORD v10; // eax

  if ( a2 )
    DIA::`scalar deleting destructor'(a2, (unsigned int)a2);
  if ( a1 )
  {
    if ( ((*((_DWORD *)a1 + 6041) - 4) & 0xFFFFFFFB) == 0 )
    {
      v3 = (const WCHAR *)((char *)a1 + 23120);
      if ( *v3 )
      {
        v4 = -1;
        v5 = -1;
        do
          ++v5;
        while ( v3[v5] );
        do
          ++v4;
        while ( *(&qword_1802B1A00 + v4) );
        if ( (int)v5 > (int)v4 && (unsigned int)v5 < 0x209 )
        {
          while ( 1 )
          {
            v6 = (int)v5;
            if ( v3[(int)v5] == 92 )
              break;
            LODWORD(v5) = v5 - 1;
            if ( (int)v5 <= (int)v4 )
              return;
          }
          DeleteFileW(v3);
          if ( (unsigned int)spew() )
          {
            if ( v7 )
              LastError = 0;
            else
              LastError = GetLastError();
            _pwprint(0, L"........DeleteFile(%u,%ws)\n", LastError, v3);
          }
          v3[v6] = 0;
          RemoveDirectoryW(v3);
          if ( (unsigned int)spew() )
          {
            if ( v9 )
              v10 = 0;
            else
              v10 = GetLastError();
            _pwprint(0, L"........RemoveDirectory(%u,%ws)\n", v10, v3);
          }
          *v3 = 0;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180016c04  mov     [rsp+arg_0], rbx
0x180016c09  mov     [rsp+arg_8], rsi
0x180016c0e  push    rdi
0x180016c0f  sub     rsp, 20h
0x180016c13  xor     esi, esi
0x180016c15  mov     rbx, rcx
0x180016c18  test    rdx, rdx
0x180016c1b  jnz     short loc_180016C42
0x180016c1d  test    rbx, rbx
0x180016c20  jz      short loc_180016C32
0x180016c22  mov     eax, [rbx+5E64h]
0x180016c28  sub     eax, 4
0x180016c2b  test    eax, 0FFFFFFFBh
0x180016c30  jz      short loc_180016C4C
0x180016c32  mov     rbx, [rsp+28h+arg_0]
0x180016c37  mov     rsi, [rsp+28h+arg_8]
0x180016c3c  add     rsp, 20h
0x180016c40  pop     rdi
0x180016c41  retn
0x180016c42  mov     rcx, rdx; this
0x180016c45  call    ??_GDIA@@QEAAPEAXI@Z; DIA::`scalar deleting destructor'(uint)
0x180016c4a  jmp     short loc_180016C1D
0x180016c4c  add     rbx, 5A50h
0x180016c53  cmp     [rbx], si
0x180016c56  jz      short loc_180016C32
0x180016c58  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180016c5c  mov     rax, rcx
0x180016c5f  inc     rax
0x180016c62  cmp     [rbx+rax*2], si
0x180016c66  jnz     short loc_180016C5F
0x180016c68  lea     rdx, qword_1802B1A00
0x180016c6f  inc     rcx
0x180016c72  cmp     [rdx+rcx*2], si
0x180016c76  jnz     short loc_180016C6F
0x180016c78  cmp     eax, ecx
0x180016c7a  jle     short loc_180016C32
0x180016c7c  cmp     eax, 209h
0x180016c81  jnb     short loc_180016C32
0x180016c83  movsxd  rdi, eax
0x180016c86  cmp     word ptr [rbx+rdi*2], 5Ch ; '\'
0x180016c8b  jz      short loc_180016C95
0x180016c8d  dec     eax
0x180016c8f  cmp     eax, ecx
0x180016c91  jg      short loc_180016C83
0x180016c93  jmp     short loc_180016C32
0x180016c95  mov     rcx, rbx; lpFileName
0x180016c98  call    cs:__imp_DeleteFileW
0x180016c9e  mov     ecx, eax
0x180016ca0  call    ?spew@@YAHXZ; spew(void)
0x180016ca5  test    eax, eax
0x180016ca7  jz      short loc_180016CCB
0x180016ca9  test    ecx, ecx
0x180016cab  jz      short loc_180016CB1
0x180016cad  mov     eax, esi
0x180016caf  jmp     short loc_180016CB7
0x180016cb1  call    cs:__imp_GetLastError
0x180016cb7  mov     r9, rbx
0x180016cba  lea     rdx, aDeletefileUWs; "........DeleteFile(%u,%ws)\n"
0x180016cc1  mov     r8d, eax
0x180016cc4  xor     ecx, ecx; struct _PROCESS_ENTRY *
0x180016cc6  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x180016ccb  mov     rcx, rbx; lpPathName
0x180016cce  mov     [rbx+rdi*2], si
0x180016cd2  call    cs:__imp_RemoveDirectoryW
0x180016cd8  mov     ecx, eax
0x180016cda  call    ?spew@@YAHXZ; spew(void)
0x180016cdf  test    eax, eax
0x180016ce1  jz      short loc_180016D05
0x180016ce3  test    ecx, ecx
0x180016ce5  jz      short loc_180016CEB
0x180016ce7  mov     eax, esi
0x180016ce9  jmp     short loc_180016CF1
0x180016ceb  call    cs:__imp_GetLastError
0x180016cf1  mov     r9, rbx
0x180016cf4  lea     rdx, aRemovedirector; "........RemoveDirectory(%u,%ws)\n"
0x180016cfb  mov     r8d, eax
0x180016cfe  xor     ecx, ecx; struct _PROCESS_ENTRY *
0x180016d00  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x180016d05  mov     [rbx], si
0x180016d08  jmp     loc_180016C32
```
