# BackupWriteLinkData

- ea: `0x1800330cc`
- end: `0x18003329f`
- name: `BackupWriteLinkData`
- size: `467`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180070ff0`

## callees

- `0x18000ccf0`
- `0x1800330cc`
- `0x1800332a8`
- `0x180055abc`
- `0x18005933c`
- `0x180082751`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x1800331d6`
- `ntdll!NtSetInformationFile` at `0x1800331d6`
- `ntdll!RtlSetLastWin32Error` at `0x18003320a`
- `ntdll!RtlSetLastWin32Error` at `0x180033242`
- `ntdll!RtlSetLastWin32Error` at `0x180033291`
- `ntdll!RtlSetLastWin32Error` at `0x18003320a`
- `ntdll!RtlSetLastWin32Error` at `0x180033242`
- `ntdll!RtlSetLastWin32Error` at `0x180033291`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800331e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800331e8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180033192`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180033192`

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
0x1800330cc  mov     [rsp+FileHandle], rcx
0x1800330d1  push    rbx
0x1800330d2  push    rbp
0x1800330d3  push    rsi
0x1800330d4  push    rdi
0x1800330d5  push    r12
0x1800330d7  push    r13
0x1800330d9  push    r14
0x1800330db  push    r15
0x1800330dd  sub     rsp, 58h
0x1800330e1  mov     r15, rdx
0x1800330e4  mov     rdx, r8
0x1800330e7  mov     rcx, r15
0x1800330ea  call    BackupWriteBuffer
0x1800330ef  xor     r13d, r13d
0x1800330f2  test    eax, eax
0x1800330f4  jz      loc_18003324E
0x1800330fa  sub     eax, 1
0x1800330fd  jnz     loc_180033259
0x180033103  mov     rdx, [r15+440h]
0x18003310a  lea     ebx, [rax+2]
0x18003310d  mov     ebp, r13d
0x180033110  lea     r14d, [r13+5Ch]
0x180033114  mov     esi, r13d
0x180033117  movzx   ecx, word ptr [rdx]
0x18003311a  test    cx, cx
0x18003311d  jnz     loc_180033260
0x180033123  lea     r12d, [rbx+18h]
0x180033127  mov     ecx, r12d
0x18003312a  call    BackupAlloc
0x18003312f  mov     rdi, rax
0x180033132  test    rax, rax
0x180033135  jz      loc_18003323D
0x18003313b  lea     r13, [rsi+2]
0x18003313f  movsxd  r8, ebx; Size
0x180033142  mov     rdx, r13; Src
0x180033145  lea     rcx, [rax+14h]; void *
0x180033149  call    memcpy_0
0x18003314e  lea     eax, [rbx-2]
0x180033151  mov     ebx, 1
0x180033156  mov     [rdi+10h], eax
0x180033159  cmp     ebp, ebx
0x18003315b  jg      short loc_180033161
0x18003315d  movzx   r14d, word ptr [rsi]
0x180033161  cmovle  rsi, r13
0x180033165  mov     edx, 0C0000000h; dwDesiredAccess
0x18003316a  xor     eax, eax
0x18003316c  xor     r9d, r9d; lpSecurityAttributes
0x18003316f  mov     [rsp+98h+hTemplateFile], rax; hTemplateFile
0x180033174  mov     [rsp+98h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x18003317c  mov     [rsi], ax
0x18003317f  mov     rcx, [r15+440h]; lpFileName
0x180033186  lea     r8d, [rax+7]; dwShareMode
0x18003318a  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x180033192  call    cs:__imp_CreateFileW
0x180033199  nop     dword ptr [rax+rax+00h]
0x18003319e  mov     [rdi+8], rax
0x1800331a2  mov     [rsi], r14w
0x1800331a6  cmp     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x1800331ab  mov     [rdi], bl
0x1800331ad  jz      loc_18003328C
0x1800331b3  mov     rcx, [rsp+98h+FileHandle]; FileHandle
0x1800331bb  lea     rdx, [rsp+98h+IoStatusBlock]; IoStatusBlock
0x1800331c0  xorps   xmm0, xmm0
0x1800331c3  mov     [rsp+98h+dwCreationDisposition], 0Bh; FileInformationClass
0x1800331cb  mov     r9d, r12d; Length
0x1800331ce  mov     r8, rdi; FileInformation
0x1800331d1  movups  xmmword ptr [rsp+98h+IoStatusBlock], xmm0
0x1800331d6  call    cs:__imp_NtSetInformationFile
0x1800331dd  nop     dword ptr [rax+rax+00h]
0x1800331e2  mov     rcx, [rdi+8]; hObject
0x1800331e6  mov     esi, eax
0x1800331e8  call    cs:__imp_CloseHandle
0x1800331ef  nop     dword ptr [rax+rax+00h]
0x1800331f4  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x1800331fc  test    esi, esi
0x1800331fe  js      short loc_180033232
0x180033200  cmp     [rsp+98h+IoStatusBlock.Information], 3
0x180033206  jz      short loc_180033252
0x180033208  xor     ecx, ecx; LastError
0x18003320a  call    cs:__imp_RtlSetLastWin32Error
0x180033211  nop     dword ptr [rax+rax+00h]
0x180033216  mov     rcx, rdi
0x180033219  call    CompatCacheFree
0x18003321e  mov     eax, ebx
0x180033220  add     rsp, 58h
0x180033224  pop     r15
0x180033226  pop     r14
0x180033228  pop     r13
0x18003322a  pop     r12
0x18003322c  pop     rdi
0x18003322d  pop     rsi
0x18003322e  pop     rbp
0x18003322f  pop     rbx
0x180033230  retn
0x180033232  mov     ecx, esi
0x180033234  call    BaseSetLastNTError
0x180033239  xor     ebx, ebx
0x18003323b  jmp     short loc_180033216
0x18003323d  mov     ecx, 8; LastError
0x180033242  call    cs:__imp_RtlSetLastWin32Error
0x180033249  nop     dword ptr [rax+rax+00h]
0x18003324e  xor     eax, eax
0x180033250  jmp     short loc_180033220
0x180033252  mov     ecx, 0B7h
0x180033257  jmp     short loc_18003320A
0x180033259  cmp     eax, 1
0x18003325c  jnz     short loc_18003324E
0x18003325e  jmp     short loc_180033220
0x180033260  cmp     cx, r14w
0x180033264  lea     eax, [rbp+1]
0x180033267  cmovnz  eax, ebp
0x18003326a  mov     ebp, eax
0x18003326c  mov     rax, rdx
0x18003326f  cmovnz  rax, rsi
0x180033273  add     rdx, 2
0x180033277  mov     rsi, rax
0x18003327a  cmp     cx, r14w
0x18003327e  mov     eax, r13d
0x180033281  cmovnz  eax, ebx
0x180033284  lea     ebx, [rax+2]
0x180033287  jmp     loc_180033117
0x18003328c  mov     ecx, 2; LastError
0x180033291  call    cs:__imp_RtlSetLastWin32Error
0x180033298  nop     dword ptr [rax+rax+00h]
0x18003329d  jmp     short loc_180033239
```
