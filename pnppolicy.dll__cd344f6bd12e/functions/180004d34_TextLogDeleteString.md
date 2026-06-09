# TextLogDeleteString

- ea: `0x180004d34`
- end: `0x180004e04`
- name: `TextLogDeleteString`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x180005e5c`

## callees

- `0x180004d34`
- `0x180005a5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004dca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004dca`
- `KERNEL32!SetFilePointer` at `0x180004dbf`
- `KERNEL32!SetFilePointer` at `0x180004dbf`

## pseudocode

```c
__int64 __fastcall TextLogDeleteString(__int64 a1, unsigned int a2)
{
  _BYTE *v5; // r8
  _BYTE *v6; // rdx
  _BYTE *v7; // rax
  unsigned int v9; // r10d
  __int64 i; // r9
  DWORD LastError; // ebx
  unsigned int v12; // r14d

  if ( a2 >= *(_DWORD *)(a1 + 40) )
    return 87;
  v5 = (_BYTE *)(*(_QWORD *)(a1 + 16) + a2);
  v6 = v5;
  v7 = v5;
  do
  {
    if ( (unsigned __int64)v7 >= *(_QWORD *)(a1 + 24) )
      break;
    v7 = v6 + 1;
  }
  while ( *v6++ != 10 );
  v9 = *(_DWORD *)(a1 + 24) - (_DWORD)v6;
  for ( i = 0; (unsigned int)i < v9; i = (unsigned int)(i + 1) )
    v5[i] = v6[i];
  LastError = 0;
  v12 = (_DWORD)v5 - (_DWORD)v6;
  *(_QWORD *)(a1 + 24) += (int)v5 - (int)v6;
  if ( SetFilePointer(*(HANDLE *)a1, *(_DWORD *)(a1 + 24) - *(_DWORD *)(a1 + 16), 0, 0) == -1 )
    LastError = GetLastError();
  if ( !LastError )
    return (unsigned int)TextLogUpdateFileOffsets(a1, a2, v12);
  return LastError;
}

```

## disassembly

```asm
0x180004d34  push    rbx
0x180004d36  push    rsi
0x180004d37  push    rdi
0x180004d38  push    r14
0x180004d3a  sub     rsp, 38h
0x180004d3e  mov     esi, edx
0x180004d40  mov     rdi, rcx
0x180004d43  cmp     edx, [rcx+28h]
0x180004d46  jb      short loc_180004D52
0x180004d48  mov     eax, 57h ; 'W'
0x180004d4d  jmp     loc_180004DFA
0x180004d52  mov     r8, rsi
0x180004d55  add     r8, [rcx+10h]
0x180004d59  mov     rdx, r8
0x180004d5c  mov     [rsp+58h+var_30], rdx
0x180004d61  mov     rax, r8
0x180004d64  cmp     rax, [rcx+18h]
0x180004d68  jnb     short loc_180004D7D
0x180004d6a  lea     rax, [rdx+1]
0x180004d6e  mov     [rsp+58h+var_30], rax
0x180004d73  cmp     byte ptr [rdx], 0Ah
0x180004d76  mov     rdx, rax
0x180004d79  jz      short loc_180004D7D
0x180004d7b  jmp     short loc_180004D64
0x180004d7d  mov     r14d, edx
0x180004d80  sub     r14d, r8d
0x180004d83  mov     r10d, [rcx+18h]
0x180004d87  sub     r10d, edx
0x180004d8a  xor     r9d, r9d
0x180004d8d  mov     [rsp+58h+var_34], r9d
0x180004d92  cmp     r9d, r10d
0x180004d95  jnb     short loc_180004DA4
0x180004d97  mov     al, [r9+rdx]
0x180004d9b  mov     [r9+r8], al
0x180004d9f  inc     r9d
0x180004da2  jmp     short loc_180004D8D
0x180004da4  xor     ebx, ebx
0x180004da6  neg     r14d
0x180004da9  movsxd  rax, r14d
0x180004dac  add     [rcx+18h], rax
0x180004db0  mov     edx, [rcx+18h]
0x180004db3  sub     edx, [rcx+10h]; lDistanceToMove
0x180004db6  xor     r9d, r9d; dwMoveMethod
0x180004db9  xor     r8d, r8d; lpDistanceToMoveHigh
0x180004dbc  mov     rcx, [rcx]; hFile
0x180004dbf  call    cs:__imp_SetFilePointer
0x180004dc5  cmp     eax, 0FFFFFFFFh
0x180004dc8  jnz     short loc_180004DD2
0x180004dca  call    cs:__imp_GetLastError
0x180004dd0  mov     ebx, eax
0x180004dd2  mov     [rsp+58h+var_38], ebx
0x180004dd6  test    ebx, ebx
0x180004dd8  jnz     short loc_180004DED
0x180004dda  mov     r8d, r14d
0x180004ddd  mov     edx, esi
0x180004ddf  mov     rcx, rdi
0x180004de2  call    TextLogUpdateFileOffsets
0x180004de7  mov     ebx, eax
0x180004de9  mov     [rsp+58h+var_38], eax
0x180004ded  jmp     short loc_180004DF8
0x180004def  mov     ebx, 0Dh
0x180004df4  mov     [rsp+58h+var_38], ebx
0x180004df8  mov     eax, ebx
0x180004dfa  add     rsp, 38h
0x180004dfe  pop     r14
0x180004e00  pop     rdi
0x180004e01  pop     rsi
0x180004e02  pop     rbx
0x180004e03  retn
```
