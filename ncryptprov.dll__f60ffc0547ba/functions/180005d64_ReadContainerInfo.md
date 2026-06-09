# ReadContainerInfo

- ea: `0x180005d64`
- end: `0x180006014`
- name: `ReadContainerInfo`
- size: `688`
- prototype: `__int64 __fastcall(HANDLE hFile, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005290`

## callees

- `0x180005d64`
- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x18000def0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005de1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005de1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180005dd1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180005dd1`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180005d85`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180005d85`

## string_xrefs

- `0x180005ef6`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x180005f23`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x180005f76`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x180005fc0`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x180005ff8`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`

## pseudocode

```c
__int64 __fastcall ReadContainerInfo(HANDLE hFile, _QWORD *a2, _DWORD *a3)
{
  DWORD FileSize; // eax
  unsigned __int64 v7; // rdi
  _DWORD *v8; // rax
  int v9; // r8d
  _DWORD *v10; // rbx
  DWORD LastError; // edi
  int v12; // r8d
  __int64 v14; // r9
  DWORD NumberOfBytesRead; // [rsp+98h] [rbp+20h] BYREF

  NumberOfBytesRead = 0;
  FileSize = GetFileSize(hFile, 0);
  v7 = FileSize;
  if ( FileSize - 40 > 0xFFFD8 )
  {
    LastError = -2146893798;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c",
        (_DWORD)WPP_GLOBAL_Control,
        (unsigned int)"Status",
        26,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c",
        123);
  }
  else
  {
    v8 = (_DWORD *)SafeAllocaAllocateFromHeap(FileSize);
    v10 = v8;
    if ( v8 )
    {
      if ( ReadFile(hFile, v8, v7, &NumberOfBytesRead, 0) )
      {
        if ( NumberOfBytesRead == (_DWORD)v7 )
        {
          if ( *v10 != 2 )
          {
            LastError = -2146893798;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c",
                (_DWORD)WPP_GLOBAL_Control,
                (unsigned int)"Status",
                26,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c",
                166);
            goto LABEL_6;
          }
          if ( (unsigned int)v7 <= v10[2]
            || (unsigned int)v7 <= v10[3]
            || (unsigned int)v7 <= v10[4]
            || (unsigned int)v7 <= v10[5]
            || (unsigned int)v7 <= v10[6]
            || (unsigned int)v7 <= v10[7]
            || (unsigned int)v7 <= v10[8]
            || (unsigned int)v7 <= v10[9] )
          {
            v14 = 948;
          }
          else
          {
            if ( (unsigned int)v10[2]
               + (unsigned int)v10[3]
               + (unsigned int)v10[4]
               + (unsigned int)v10[5]
               + (unsigned int)v10[6]
               + (unsigned int)v10[7]
               + (unsigned int)v10[8]
               + (unsigned __int64)(unsigned int)v10[9]
               + 40 <= v7 )
            {
              *a3 = v7;
              LastError = 0;
              *a2 = v10;
              return LastError;
            }
            v14 = 963;
          }
        }
        else
        {
          v14 = 918;
        }
        LastError = -2146893798;
        DebugTraceError(2148073498LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c", v14);
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c",
            v12,
            (unsigned int)"Status",
            LastError,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c",
            143);
      }
LABEL_6:
      MSCryptFree(v10);
      return LastError;
    }
    LastError = -2146893810;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c",
        v9,
        (unsigned int)"Status",
        14,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c",
        132);
  }
  return LastError;
}

```

## disassembly

```asm
0x180005d64  mov     rax, rsp
0x180005d67  push    rbx
0x180005d68  push    rbp
0x180005d69  push    rsi
0x180005d6a  push    rdi
0x180005d6b  push    r14
0x180005d6d  push    r15
0x180005d6f  sub     rsp, 48h
0x180005d73  mov     r15, rdx
0x180005d76  mov     dword ptr [rax+20h], 0
0x180005d7d  xor     edx, edx; lpFileSizeHigh
0x180005d7f  mov     r14, r8
0x180005d82  mov     rsi, rcx
0x180005d85  call    cs:__imp_GetFileSize
0x180005d8c  nop     dword ptr [rax+rax+00h]
0x180005d91  mov     edi, eax
0x180005d93  lea     r9d, [rdi-28h]
0x180005d97  cmp     r9d, 0FFFD8h
0x180005d9e  ja      loc_180005EC9
0x180005da4  mov     ecx, edi
0x180005da6  call    SafeAllocaAllocateFromHeap
0x180005dab  mov     rbx, rax
0x180005dae  test    rax, rax
0x180005db1  jz      loc_180005F4C
0x180005db7  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180005dbf  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x180005dc8  mov     r8d, edi; nNumberOfBytesToRead
0x180005dcb  mov     rdx, rax; lpBuffer
0x180005dce  mov     rcx, rsi; hFile
0x180005dd1  call    cs:__imp_ReadFile
0x180005dd8  nop     dword ptr [rax+rax+00h]
0x180005ddd  test    eax, eax
0x180005ddf  jnz     short loc_180005E24
0x180005de1  call    cs:__imp_GetLastError
0x180005de8  nop     dword ptr [rax+rax+00h]
0x180005ded  mov     edi, eax
0x180005def  mov     rax, cs:WPP_GLOBAL_Control
0x180005df6  lea     rcx, WPP_GLOBAL_Control
0x180005dfd  cmp     rax, rcx
0x180005e00  jz      short loc_180005E0C
0x180005e02  test    byte ptr [rax+1Ch], 1
0x180005e06  jnz     loc_180005F1F
0x180005e0c  mov     rcx, rbx
0x180005e0f  call    MSCryptFree
0x180005e14  mov     eax, edi
0x180005e16  add     rsp, 48h
0x180005e1a  pop     r15
0x180005e1c  pop     r14
0x180005e1e  pop     rdi
0x180005e1f  pop     rsi
0x180005e20  pop     rbp
0x180005e21  pop     rbx
0x180005e22  retn
0x180005e24  cmp     [rsp+78h+NumberOfBytesRead], edi
0x180005e2b  jnz     loc_180005FDD
0x180005e31  cmp     dword ptr [rbx], 2
0x180005e34  jnz     loc_180005F93
0x180005e3a  cmp     edi, [rbx+8]
0x180005e3d  jbe     loc_180005FED
0x180005e43  cmp     edi, [rbx+0Ch]
0x180005e46  jbe     loc_180005FED
0x180005e4c  cmp     edi, [rbx+10h]
0x180005e4f  jbe     loc_180005FED
0x180005e55  cmp     edi, [rbx+14h]
0x180005e58  jbe     loc_180005FED
0x180005e5e  cmp     edi, [rbx+18h]
0x180005e61  jbe     loc_180005FED
0x180005e67  cmp     edi, [rbx+1Ch]
0x180005e6a  jbe     loc_180005FED
0x180005e70  cmp     edi, [rbx+20h]
0x180005e73  jbe     loc_180005FED
0x180005e79  cmp     edi, [rbx+24h]
0x180005e7c  jbe     loc_180005FED
0x180005e82  mov     eax, [rbx+20h]
0x180005e85  mov     ecx, [rbx+24h]
0x180005e88  add     rcx, rax
0x180005e8b  mov     eax, [rbx+1Ch]
0x180005e8e  add     rcx, rax
0x180005e91  mov     eax, [rbx+18h]
0x180005e94  add     rcx, rax
0x180005e97  mov     eax, [rbx+14h]
0x180005e9a  add     rcx, rax
0x180005e9d  mov     eax, [rbx+10h]
0x180005ea0  add     rcx, rax
0x180005ea3  mov     eax, [rbx+0Ch]
0x180005ea6  add     rcx, rax
0x180005ea9  mov     eax, [rbx+8]
0x180005eac  add     rcx, 28h ; '('
0x180005eb0  add     rcx, rax
0x180005eb3  cmp     rcx, rdi
0x180005eb6  ja      loc_180005FE5
0x180005ebc  mov     [r14], edi
0x180005ebf  xor     edi, edi
0x180005ec1  mov     [r15], rbx
0x180005ec4  jmp     loc_180005E14
0x180005ec9  mov     eax, 8009001Ah
0x180005ece  mov     edi, eax
0x180005ed0  mov     r8, cs:WPP_GLOBAL_Control
0x180005ed7  lea     rcx, WPP_GLOBAL_Control
0x180005ede  cmp     r8, rcx
0x180005ee1  jz      loc_180005E14
0x180005ee7  test    byte ptr [r8+1Ch], 1
0x180005eec  jz      loc_180005E14
0x180005ef2  mov     rcx, [r8+10h]
0x180005ef6  lea     rdx, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005efd  mov     [rsp+78h+var_48], 37Bh
0x180005f05  mov     [rsp+78h+var_50], rdx
0x180005f0a  mov     dword ptr [rsp+78h+lpOverlapped], eax
0x180005f0e  lea     r9, aStatus; "Status"
0x180005f15  call    WPP_SF_sDsd
0x180005f1a  jmp     loc_180005E14
0x180005f1f  mov     rcx, [rax+10h]
0x180005f23  lea     rdx, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005f2a  mov     [rsp+78h+var_48], 38Fh
0x180005f32  mov     [rsp+78h+var_50], rdx
0x180005f37  mov     dword ptr [rsp+78h+lpOverlapped], edi
0x180005f3b  lea     r9, aStatus; "Status"
0x180005f42  call    WPP_SF_sDsd
0x180005f47  jmp     loc_180005E0C
0x180005f4c  mov     edi, 8009000Eh
0x180005f51  mov     rax, cs:WPP_GLOBAL_Control
0x180005f58  lea     rcx, WPP_GLOBAL_Control
0x180005f5f  cmp     rax, rcx
0x180005f62  jz      loc_180005E14
0x180005f68  test    byte ptr [rax+1Ch], 1
0x180005f6c  jz      loc_180005E14
0x180005f72  mov     rcx, [rax+10h]
0x180005f76  lea     rdx, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005f7d  mov     [rsp+78h+var_48], 384h
0x180005f85  mov     [rsp+78h+var_50], rdx
0x180005f8a  mov     dword ptr [rsp+78h+lpOverlapped], edi
0x180005f8e  jmp     loc_180005F0E
0x180005f93  mov     eax, 8009001Ah
0x180005f98  mov     edi, eax
0x180005f9a  mov     r8, cs:WPP_GLOBAL_Control
0x180005fa1  lea     rcx, WPP_GLOBAL_Control
0x180005fa8  cmp     r8, rcx
0x180005fab  jz      loc_180005E0C
0x180005fb1  test    byte ptr [r8+1Ch], 1
0x180005fb6  jz      loc_180005E0C
0x180005fbc  mov     rcx, [r8+10h]
0x180005fc0  lea     rdx, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005fc7  mov     [rsp+78h+var_48], 3A6h
0x180005fcf  mov     [rsp+78h+var_50], rdx
0x180005fd4  mov     dword ptr [rsp+78h+lpOverlapped], eax
0x180005fd8  jmp     loc_180005F3B
0x180005fdd  mov     r9d, 396h
0x180005fe3  jmp     short loc_180005FF3
0x180005fe5  mov     r9d, 3C3h
0x180005feb  jmp     short loc_180005FF3
0x180005fed  mov     r9d, 3B4h
0x180005ff3  mov     eax, 8009001Ah
0x180005ff8  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005fff  mov     ecx, eax
0x180006001  lea     rdx, aStatus; "Status"
0x180006008  mov     edi, eax
0x18000600a  call    DebugTraceError
0x18000600f  jmp     loc_180005E0C
```
