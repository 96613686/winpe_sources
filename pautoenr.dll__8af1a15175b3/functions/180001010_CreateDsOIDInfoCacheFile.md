# _CreateDsOIDInfoCacheFile

- ea: `0x180001010`
- end: `0x1800010fa`
- name: `_CreateDsOIDInfoCacheFile`
- size: `234`
- prototype: `HANDLE __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003ac0`

## callees

- `0x180001010`
- `0x180001100`
- `0x180005200`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000109e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000109e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800010d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800010d6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000108f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000108f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800010bf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800010bf`

## pseudocode

```c
HANDLE __fastcall CreateDsOIDInfoCacheFile(int a1)
{
  WCHAR *DsOIDInfoCacheFileName; // rbx
  __int64 v3; // rsi
  DWORD dwFlagsAndAttributes; // ebp
  DWORD v5; // r15d
  DWORD dwCreationDisposition; // r14d
  DWORD v7; // r12d
  HANDLE FileW; // rdi
  DWORD LastError; // eax

  DsOIDInfoCacheFileName = GetDsOIDInfoCacheFileName(a1);
  if ( DsOIDInfoCacheFileName )
  {
    v3 = 0;
    dwFlagsAndAttributes = 4;
    if ( !a1 )
      dwFlagsAndAttributes = 128;
    v5 = -1073741824;
    dwCreationDisposition = 3 - (a1 != 0);
    v7 = a1 == 0;
    if ( !a1 )
      v5 = 0x80000000;
    while ( 1 )
    {
      FileW = CreateFileW(DsOIDInfoCacheFileName, v5, v7, 0, dwCreationDisposition, dwFlagsAndAttributes, 0);
      if ( FileW != (HANDLE)-1LL )
        break;
      LastError = GetLastError();
      if ( LastError == 32 )
      {
        if ( (unsigned int)v3 >= 6 )
          goto LABEL_15;
      }
      else
      {
        if ( LastError != 5 )
        {
          if ( LastError == 3 )
            LastError = 2;
LABEL_15:
          SetLastError(LastError);
          goto LABEL_16;
        }
        if ( (_DWORD)v3 )
          goto LABEL_15;
      }
      Sleep(*((_DWORD *)qword_18000B3E0 + v3));
      v3 = (unsigned int)(v3 + 1);
    }
  }
  else
  {
LABEL_16:
    FileW = 0;
  }
  PkiFree(DsOIDInfoCacheFileName);
  return FileW;
}

```

## disassembly

```asm
0x180001010  push    rbx
0x180001012  push    rbp
0x180001013  push    rsi
0x180001014  push    rdi
0x180001015  push    r12
0x180001017  push    r13
0x180001019  push    r14
0x18000101b  push    r15
0x18000101d  sub     rsp, 48h
0x180001021  mov     edi, ecx
0x180001023  call    _GetDsOIDInfoCacheFileName
0x180001028  mov     rbx, rax
0x18000102b  test    rax, rax
0x18000102e  jz      loc_1800010DC
0x180001034  xor     esi, esi
0x180001036  test    edi, edi
0x180001038  lea     r13, qword_18000B3E0
0x18000103f  mov     eax, 80h
0x180001044  mov     ebp, 4
0x180001049  cmovz   ebp, eax
0x18000104c  mov     r15d, 0C0000000h
0x180001052  mov     eax, edi
0x180001054  neg     eax
0x180001056  mov     eax, 80000000h
0x18000105b  sbb     r14d, r14d
0x18000105e  xor     r12d, r12d
0x180001061  add     r14d, 3
0x180001065  test    edi, edi
0x180001067  setz    r12b
0x18000106b  test    edi, edi
0x18000106d  cmovz   r15d, eax
0x180001071  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x18000107a  xor     r9d, r9d; lpSecurityAttributes
0x18000107d  mov     [rsp+88h+dwFlagsAndAttributes], ebp; dwFlagsAndAttributes
0x180001081  mov     r8d, r12d; dwShareMode
0x180001084  mov     edx, r15d; dwDesiredAccess
0x180001087  mov     [rsp+88h+dwCreationDisposition], r14d; dwCreationDisposition
0x18000108c  mov     rcx, rbx; lpFileName
0x18000108f  call    cs:__imp_CreateFileW
0x180001095  mov     rdi, rax
0x180001098  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000109c  jnz     short loc_1800010DE
0x18000109e  call    cs:__imp_GetLastError
0x1800010a4  cmp     eax, 20h ; ' '
0x1800010a7  jnz     short loc_1800010B0
0x1800010a9  cmp     esi, 6
0x1800010ac  jb      short loc_1800010BA
0x1800010ae  jmp     short loc_1800010D4
0x1800010b0  cmp     eax, 5
0x1800010b3  jnz     short loc_1800010C9
0x1800010b5  cmp     esi, 1
0x1800010b8  jnb     short loc_1800010D4
0x1800010ba  mov     ecx, [r13+rsi*4+0]; dwMilliseconds
0x1800010bf  call    cs:__imp_Sleep
0x1800010c5  inc     esi
0x1800010c7  jmp     short loc_180001071
0x1800010c9  cmp     eax, 3
0x1800010cc  mov     ecx, 2
0x1800010d1  cmovz   eax, ecx
0x1800010d4  mov     ecx, eax; dwErrCode
0x1800010d6  call    cs:__imp_SetLastError
0x1800010dc  xor     edi, edi
0x1800010de  mov     rcx, rbx; hMem
0x1800010e1  call    PkiFree
0x1800010e6  mov     rax, rdi
0x1800010e9  add     rsp, 48h
0x1800010ed  pop     r15
0x1800010ef  pop     r14
0x1800010f1  pop     r13
0x1800010f3  pop     r12
0x1800010f5  pop     rdi
0x1800010f6  pop     rsi
0x1800010f7  pop     rbp
0x1800010f8  pop     rbx
0x1800010f9  retn
```
