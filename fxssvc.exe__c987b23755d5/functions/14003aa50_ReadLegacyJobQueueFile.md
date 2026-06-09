# ReadLegacyJobQueueFile

- ea: `0x14003aa50`
- end: `0x14003ac72`
- name: `ReadLegacyJobQueueFile`
- size: `546`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14003a754`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x14003aa50`
- `0x14003e800`
- `0x140065d14`
- `0x140065dbc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003aabc`
- `KERNEL32!GetLastError` at `0x14003aba6`
- `KERNEL32!GetLastError` at `0x14003aabc`
- `KERNEL32!GetLastError` at `0x14003aba6`
- `KERNEL32!GetFileSize` at `0x14003aaf7`
- `KERNEL32!GetFileSize` at `0x14003aaf7`
- `KERNEL32!ReadFile` at `0x14003ab9c`
- `KERNEL32!ReadFile` at `0x14003ab9c`
- `KERNEL32!SetFilePointer` at `0x14003aaaf`
- `KERNEL32!SetFilePointer` at `0x14003aaaf`

## pseudocode

```c
__int64 __fastcall ReadLegacyJobQueueFile(HANDLE hFile, struct _JOB_QUEUE_FILE **a2)
{
  struct _JOB_QUEUE_FILE *v4; // rdi
  DWORD LastError; // eax
  unsigned int v6; // ebx
  CMapDeviceId *v7; // rcx
  __int64 v8; // rdx
  DWORD FileSize; // eax
  DWORD v10; // ebx
  struct _JOB_QUEUE_FILE *v11; // rax
  CMapDeviceId *v12; // rcx
  __int64 v13; // rdx
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp+18h] BYREF

  NumberOfBytesRead = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 341, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
  if ( SetFilePointer(hFile, 0, 0, 0) == -1 )
  {
    v4 = 0;
    LastError = GetLastError();
    v6 = LastError;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 342;
LABEL_27:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, LastError);
    }
  }
  else
  {
    FileSize = GetFileSize(hFile, 0);
    v10 = FileSize;
    if ( FileSize < 0x678 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 343, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, FileSize);
      }
      return 1392;
    }
    v11 = (struct _JOB_QUEUE_FILE *)pMemAlloc(FileSize);
    v4 = v11;
    if ( !v11 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 344, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v10);
      }
      return 8;
    }
    if ( ReadFile(hFile, v11, v10, &NumberOfBytesRead, 0) )
    {
      if ( v10 == NumberOfBytesRead )
      {
        if ( ValidateJobQueueOffsets(v4, NumberOfBytesRead) )
        {
          v6 = 0;
          *a2 = v4;
          return v6;
        }
        v6 = 13;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_42;
        }
        v13 = 347;
      }
      else
      {
        v6 = 38;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_42;
        }
        v13 = 346;
      }
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v6);
LABEL_42:
      pMemFree(v4);
      return v6;
    }
    LastError = GetLastError();
    v6 = LastError;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 345;
      goto LABEL_27;
    }
  }
  if ( v6 && v4 )
    goto LABEL_42;
  return v6;
}

```

## disassembly

```asm
0x14003aa50  mov     rax, rsp
0x14003aa53  push    rbx
0x14003aa54  push    rsi
0x14003aa55  push    rdi
0x14003aa56  push    r12
0x14003aa58  push    r14
0x14003aa5a  push    r15
0x14003aa5c  sub     rsp, 38h
0x14003aa60  mov     r14, rdx
0x14003aa63  mov     dword ptr [rax+18h], 0
0x14003aa6a  mov     rsi, rcx
0x14003aa6d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aa74  lea     r15, WPP_GLOBAL_Control
0x14003aa7b  lea     r12, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003aa82  cmp     rcx, r15
0x14003aa85  jz      short loc_14003AAA4
0x14003aa87  test    byte ptr [rcx+1Ch], 4
0x14003aa8b  jz      short loc_14003AAA4
0x14003aa8d  cmp     byte ptr [rcx+19h], 5
0x14003aa91  jb      short loc_14003AAA4
0x14003aa93  mov     rcx, [rcx+10h]
0x14003aa97  mov     edx, 155h
0x14003aa9c  mov     r8, r12
0x14003aa9f  call    WPP_SF_
0x14003aaa4  xor     r9d, r9d; dwMoveMethod
0x14003aaa7  xor     r8d, r8d; lpDistanceToMoveHigh
0x14003aaaa  xor     edx, edx; lDistanceToMove
0x14003aaac  mov     rcx, rsi; hFile
0x14003aaaf  call    cs:__imp_SetFilePointer
0x14003aab5  cmp     eax, 0FFFFFFFFh
0x14003aab8  jnz     short loc_14003AAF2
0x14003aaba  xor     edi, edi
0x14003aabc  call    cs:__imp_GetLastError
0x14003aac2  mov     ebx, eax
0x14003aac4  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aacb  cmp     rcx, r15
0x14003aace  jz      loc_14003ABDA
0x14003aad4  test    byte ptr [rcx+1Ch], 4
0x14003aad8  jz      loc_14003ABDA
0x14003aade  cmp     byte ptr [rcx+19h], 2
0x14003aae2  jb      loc_14003ABDA
0x14003aae8  mov     edx, 156h
0x14003aaed  jmp     loc_14003ABCB
0x14003aaf2  xor     edx, edx; lpFileSizeHigh
0x14003aaf4  mov     rcx, rsi; hFile
0x14003aaf7  call    cs:__imp_GetFileSize
0x14003aafd  mov     ebx, eax
0x14003aaff  cmp     eax, 678h
0x14003ab04  jnb     short loc_14003AB3C
0x14003ab06  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ab0d  cmp     rcx, r15
0x14003ab10  jz      short loc_14003AB32
0x14003ab12  test    byte ptr [rcx+1Ch], 4
0x14003ab16  jz      short loc_14003AB32
0x14003ab18  cmp     byte ptr [rcx+19h], 3
0x14003ab1c  jb      short loc_14003AB32
0x14003ab1e  mov     rcx, [rcx+10h]
0x14003ab22  mov     edx, 157h
0x14003ab27  mov     r9d, ebx
0x14003ab2a  mov     r8, r12
0x14003ab2d  call    WPP_SF_d
0x14003ab32  mov     ebx, 570h
0x14003ab37  jmp     loc_14003AC62
0x14003ab3c  mov     rcx, rbx; dwBytes
0x14003ab3f  call    pMemAlloc
0x14003ab44  mov     rdi, rax
0x14003ab47  test    rax, rax
0x14003ab4a  jnz     short loc_14003AB82
0x14003ab4c  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ab53  cmp     rcx, r15
0x14003ab56  jz      short loc_14003AB78
0x14003ab58  test    byte ptr [rcx+1Ch], 4
0x14003ab5c  jz      short loc_14003AB78
0x14003ab5e  cmp     byte ptr [rcx+19h], 2
0x14003ab62  jb      short loc_14003AB78
0x14003ab64  mov     rcx, [rcx+10h]
0x14003ab68  mov     edx, 158h
0x14003ab6d  mov     r9d, ebx
0x14003ab70  mov     r8, r12
0x14003ab73  call    WPP_SF_d
0x14003ab78  mov     ebx, 8
0x14003ab7d  jmp     loc_14003AC62
0x14003ab82  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14003ab8a  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x14003ab93  mov     r8d, ebx; nNumberOfBytesToRead
0x14003ab96  mov     rdx, rdi; lpBuffer
0x14003ab99  mov     rcx, rsi; hFile
0x14003ab9c  call    cs:__imp_ReadFile
0x14003aba2  test    eax, eax
0x14003aba4  jnz     short loc_14003ABE9
0x14003aba6  call    cs:__imp_GetLastError
0x14003abac  mov     ebx, eax
0x14003abae  mov     rcx, cs:WPP_GLOBAL_Control
0x14003abb5  cmp     rcx, r15
0x14003abb8  jz      short loc_14003ABDA
0x14003abba  test    byte ptr [rcx+1Ch], 4
0x14003abbe  jz      short loc_14003ABDA
0x14003abc0  cmp     byte ptr [rcx+19h], 2
0x14003abc4  jb      short loc_14003ABDA
0x14003abc6  mov     edx, 159h
0x14003abcb  mov     rcx, [rcx+10h]
0x14003abcf  mov     r9d, eax
0x14003abd2  mov     r8, r12
0x14003abd5  call    WPP_SF_d
0x14003abda  test    ebx, ebx
0x14003abdc  jz      loc_14003AC62
0x14003abe2  test    rdi, rdi
0x14003abe5  jz      short loc_14003AC62
0x14003abe7  jmp     short loc_14003AC53
0x14003abe9  mov     edx, [rsp+68h+NumberOfBytesRead]; unsigned int
0x14003abf0  cmp     ebx, edx
0x14003abf2  jz      short loc_14003AC18
0x14003abf4  mov     ebx, 26h ; '&'
0x14003abf9  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ac00  cmp     rcx, r15
0x14003ac03  jz      short loc_14003AC53
0x14003ac05  test    byte ptr [rcx+1Ch], 4
0x14003ac09  jz      short loc_14003AC53
0x14003ac0b  cmp     byte ptr [rcx+19h], 2
0x14003ac0f  jb      short loc_14003AC53
0x14003ac11  mov     edx, 15Ah
0x14003ac16  jmp     short loc_14003AC44
0x14003ac18  mov     rcx, rdi; struct _JOB_QUEUE_FILE *
0x14003ac1b  call    ?ValidateJobQueueOffsets@@YAHPEAU_JOB_QUEUE_FILE@@K@Z; ValidateJobQueueOffsets(_JOB_QUEUE_FILE *,ulong)
0x14003ac20  test    eax, eax
0x14003ac22  jnz     short loc_14003AC5D
0x14003ac24  lea     ebx, [rax+0Dh]
0x14003ac27  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ac2e  cmp     rcx, r15
0x14003ac31  jz      short loc_14003AC53
0x14003ac33  test    byte ptr [rcx+1Ch], 4
0x14003ac37  jz      short loc_14003AC53
0x14003ac39  cmp     byte ptr [rcx+19h], 2
0x14003ac3d  jb      short loc_14003AC53
0x14003ac3f  mov     edx, 15Bh
0x14003ac44  mov     rcx, [rcx+10h]
0x14003ac48  mov     r9d, ebx
0x14003ac4b  mov     r8, r12
0x14003ac4e  call    WPP_SF_d
0x14003ac53  mov     rcx, rdi; lpMem
0x14003ac56  call    pMemFree
0x14003ac5b  jmp     short loc_14003AC62
0x14003ac5d  xor     ebx, ebx
0x14003ac5f  mov     [r14], rdi
0x14003ac62  mov     eax, ebx
0x14003ac64  add     rsp, 38h
0x14003ac68  pop     r15
0x14003ac6a  pop     r14
0x14003ac6c  pop     r12
0x14003ac6e  pop     rdi
0x14003ac6f  pop     rsi
0x14003ac70  pop     rbx
0x14003ac71  retn
```
