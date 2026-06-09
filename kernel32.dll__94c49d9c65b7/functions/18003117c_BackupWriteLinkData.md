# BackupWriteLinkData

- ea: `0x18003117c`
- end: `0x18003132a`
- name: `BackupWriteLinkData`
- size: `430`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180069e20`

## callees

- `0x18000f920`
- `0x18003117c`
- `0x180031330`
- `0x180050a38`
- `0x1800543f0`
- `0x18007a7d1`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x180031280`
- `ntdll!NtSetInformationFile` at `0x180031280`
- `ntdll!RtlSetLastWin32Error` at `0x1800312a8`
- `ntdll!RtlSetLastWin32Error` at `0x1800312d9`
- `ntdll!RtlSetLastWin32Error` at `0x180031322`
- `ntdll!RtlSetLastWin32Error` at `0x1800312a8`
- `ntdll!RtlSetLastWin32Error` at `0x1800312d9`
- `ntdll!RtlSetLastWin32Error` at `0x180031322`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003128c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003128c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031242`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031242`

## pseudocode

```c
__int64 __fastcall BackupWriteLinkData(void *a1, __int64 a2, __int64 a3)
{
  int v4; // eax
  __int64 result; // rax
  __int16 *v6; // rdx
  int v7; // ebx
  int v8; // ebp
  __int16 v9; // r14
  __int16 *v10; // rsi
  __int16 v11; // cx
  ULONG v12; // r12d
  __int64 v13; // rax
  HANDLE *v14; // rdi
  int v15; // eax
  unsigned int v16; // ebx
  bool v17; // zf
  NTSTATUS v18; // esi
  ULONG v19; // ecx
  int v20; // eax
  __int16 *v21; // rax
  int v22; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-58h] BYREF

  v4 = BackupWriteBuffer(a2, a3);
  if ( !v4 )
    return 0;
  result = (unsigned int)(v4 - 1);
  if ( !(_DWORD)result )
  {
    v6 = *(__int16 **)(a2 + 1088);
    v7 = 2;
    v8 = 0;
    v9 = 92;
    v10 = 0;
    while ( 1 )
    {
      v11 = *v6;
      if ( !*v6 )
        break;
      v20 = v8 + 1;
      if ( v11 != 92 )
        v20 = v8;
      v8 = v20;
      v21 = v6;
      if ( v11 != 92 )
        v21 = v10;
      ++v6;
      v10 = v21;
      v22 = 0;
      if ( v11 != 92 )
        v22 = v7;
      v7 = v22 + 2;
    }
    v12 = v7 + 24;
    v13 = BackupAlloc((unsigned int)(v7 + 24));
    v14 = (HANDLE *)v13;
    if ( v13 )
    {
      memcpy_0((void *)(v13 + 20), v10 + 1, v7);
      v15 = v7 - 2;
      v16 = 1;
      *((_DWORD *)v14 + 4) = v15;
      if ( v8 <= 1 )
        v9 = *v10++;
      *v10 = 0;
      v14[1] = CreateFileW(*(LPCWSTR *)(a2 + 1088), 0xC0000000, 7u, 0, 3u, 0x2000080u, 0);
      *v10 = v9;
      v17 = (char *)v14[1] + 1 == 0;
      *(_BYTE *)v14 = 1;
      if ( v17 )
      {
        RtlSetLastWin32Error(2u);
      }
      else
      {
        IoStatusBlock = 0;
        v18 = NtSetInformationFile(a1, &IoStatusBlock, v14, v12, FileLinkInformation);
        CloseHandle(v14[1]);
        v14[1] = (HANDLE)-1LL;
        if ( v18 >= 0 )
        {
          if ( IoStatusBlock.Information == 3 )
            v19 = 183;
          else
            v19 = 0;
          RtlSetLastWin32Error(v19);
          goto LABEL_13;
        }
        BaseSetLastNTError((unsigned int)v18);
      }
      v16 = 0;
LABEL_13:
      CompatCacheFree(v14);
      return v16;
    }
    RtlSetLastWin32Error(8u);
    return 0;
  }
  if ( (_DWORD)result != 1 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18003117c  mov     [rsp+FileHandle], rcx
0x180031181  push    rbx
0x180031182  push    rbp
0x180031183  push    rsi
0x180031184  push    rdi
0x180031185  push    r12
0x180031187  push    r13
0x180031189  push    r14
0x18003118b  push    r15
0x18003118d  sub     rsp, 58h
0x180031191  mov     r15, rdx
0x180031194  mov     rdx, r8
0x180031197  mov     rcx, r15
0x18003119a  call    BackupWriteBuffer
0x18003119f  xor     r13d, r13d
0x1800311a2  test    eax, eax
0x1800311a4  jz      loc_1800312DF
0x1800311aa  sub     eax, 1
0x1800311ad  jnz     loc_1800312EA
0x1800311b3  mov     rdx, [r15+440h]
0x1800311ba  lea     ebx, [rax+2]
0x1800311bd  mov     ebp, r13d
0x1800311c0  lea     r14d, [r13+5Ch]
0x1800311c4  mov     esi, r13d
0x1800311c7  movzx   ecx, word ptr [rdx]
0x1800311ca  test    cx, cx
0x1800311cd  jnz     loc_1800312F1
0x1800311d3  lea     r12d, [rbx+18h]
0x1800311d7  mov     ecx, r12d
0x1800311da  call    BackupAlloc
0x1800311df  mov     rdi, rax
0x1800311e2  test    rax, rax
0x1800311e5  jz      loc_1800312D4
0x1800311eb  lea     r13, [rsi+2]
0x1800311ef  movsxd  r8, ebx; Size
0x1800311f2  mov     rdx, r13; Src
0x1800311f5  lea     rcx, [rax+14h]; void *
0x1800311f9  call    memcpy_0
0x1800311fe  lea     eax, [rbx-2]
0x180031201  mov     ebx, 1
0x180031206  mov     [rdi+10h], eax
0x180031209  cmp     ebp, ebx
0x18003120b  jg      short loc_180031211
0x18003120d  movzx   r14d, word ptr [rsi]
0x180031211  cmovle  rsi, r13
0x180031215  mov     edx, 0C0000000h; dwDesiredAccess
0x18003121a  xor     eax, eax
0x18003121c  xor     r9d, r9d; lpSecurityAttributes
0x18003121f  mov     [rsp+98h+hTemplateFile], rax; hTemplateFile
0x180031224  mov     [rsp+98h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x18003122c  mov     [rsi], ax
0x18003122f  mov     rcx, [r15+440h]; lpFileName
0x180031236  lea     r8d, [rax+7]; dwShareMode
0x18003123a  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x180031242  call    cs:__imp_CreateFileW
0x180031248  mov     [rdi+8], rax
0x18003124c  mov     [rsi], r14w
0x180031250  cmp     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x180031255  mov     [rdi], bl
0x180031257  jz      loc_18003131D
0x18003125d  mov     rcx, [rsp+98h+FileHandle]; FileHandle
0x180031265  lea     rdx, [rsp+98h+IoStatusBlock]; IoStatusBlock
0x18003126a  xorps   xmm0, xmm0
0x18003126d  mov     [rsp+98h+dwCreationDisposition], 0Bh; FileInformationClass
0x180031275  mov     r9d, r12d; Length
0x180031278  mov     r8, rdi; FileInformation
0x18003127b  movups  xmmword ptr [rsp+98h+IoStatusBlock], xmm0
0x180031280  call    cs:__imp_NtSetInformationFile
0x180031286  mov     rcx, [rdi+8]; hObject
0x18003128a  mov     esi, eax
0x18003128c  call    cs:__imp_CloseHandle
0x180031292  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x18003129a  test    esi, esi
0x18003129c  js      short loc_1800312C9
0x18003129e  cmp     [rsp+98h+IoStatusBlock.Information], 3
0x1800312a4  jz      short loc_1800312E3
0x1800312a6  xor     ecx, ecx; LastError
0x1800312a8  call    cs:__imp_RtlSetLastWin32Error
0x1800312ae  mov     rcx, rdi
0x1800312b1  call    CompatCacheFree
0x1800312b6  mov     eax, ebx
0x1800312b8  add     rsp, 58h
0x1800312bc  pop     r15
0x1800312be  pop     r14
0x1800312c0  pop     r13
0x1800312c2  pop     r12
0x1800312c4  pop     rdi
0x1800312c5  pop     rsi
0x1800312c6  pop     rbp
0x1800312c7  pop     rbx
0x1800312c8  retn
0x1800312c9  mov     ecx, esi
0x1800312cb  call    BaseSetLastNTError
0x1800312d0  xor     ebx, ebx
0x1800312d2  jmp     short loc_1800312AE
0x1800312d4  mov     ecx, 8; LastError
0x1800312d9  call    cs:__imp_RtlSetLastWin32Error
0x1800312df  xor     eax, eax
0x1800312e1  jmp     short loc_1800312B8
0x1800312e3  mov     ecx, 0B7h
0x1800312e8  jmp     short loc_1800312A8
0x1800312ea  cmp     eax, 1
0x1800312ed  jnz     short loc_1800312DF
0x1800312ef  jmp     short loc_1800312B8
0x1800312f1  cmp     cx, r14w
0x1800312f5  lea     eax, [rbp+1]
0x1800312f8  cmovnz  eax, ebp
0x1800312fb  mov     ebp, eax
0x1800312fd  mov     rax, rdx
0x180031300  cmovnz  rax, rsi
0x180031304  add     rdx, 2
0x180031308  mov     rsi, rax
0x18003130b  cmp     cx, r14w
0x18003130f  mov     eax, r13d
0x180031312  cmovnz  eax, ebx
0x180031315  lea     ebx, [rax+2]
0x180031318  jmp     loc_1800311C7
0x18003131d  mov     ecx, 2; LastError
0x180031322  call    cs:__imp_RtlSetLastWin32Error
0x180031328  jmp     short loc_1800312D0
```
