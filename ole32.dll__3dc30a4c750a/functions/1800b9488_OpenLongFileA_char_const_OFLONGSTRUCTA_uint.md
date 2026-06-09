# OpenLongFileA(char const *,_OFLONGSTRUCTA *,uint)

- ea: `0x1800b9488`
- end: `0x1800b96d3`
- name: `?OpenLongFileA@@YAHPEBDPEAU_OFLONGSTRUCTA@@I@Z`
- size: `587`
- prototype: `int __fastcall(const char *lpFileName, _OFLONGSTRUCTA *lpReOpenBuff, unsigned int uStyle)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x1800b92cc`

## callees

- `0x1800b9488`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b94a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b94d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b96a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b94a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b94d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b96a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9631`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b968c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b96ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9631`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b968c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b96ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b9616`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b9616`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1800b94c7`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1800b95b9`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1800b94c7`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1800b95b9`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800b95fc`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800b9683`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800b95fc`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800b9683`
- `api-ms-win-core-processenvironment-l1-2-0!SearchPathA` at `0x1800b9581`
- `api-ms-win-core-processenvironment-l1-2-0!SearchPathA` at `0x1800b9581`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x1800b969d`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x1800b969d`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x1800b9658`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x1800b9658`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x1800b9627`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x1800b9627`

## pseudocode

```c
__int64 __fastcall OpenLongFileA(const char *lpFileName, _OFLONGSTRUCTA *lpReOpenBuff, unsigned int uStyle)
{
  DWORD v6; // ecx
  unsigned int v7; // edi
  DWORD v8; // esi
  unsigned int v9; // eax
  DWORD v10; // r15d
  DWORD v11; // ecx
  DWORD v12; // ebp
  HANDLE FileA; // rax
  HANDLE CurrentProcess; // rax
  DWORD LastError; // r14d
  unsigned int v16; // ecx
  __int64 result; // rax
  int dwCreationDisposition; // [rsp+88h] [rbp+10h]
  int isWow64Process; // [rsp+90h] [rbp+18h] BYREF
  void *pFsRedirection; // [rsp+98h] [rbp+20h] BYREF

  SetLastError(0);
  if ( (uStyle & 0x100) != 0 )
  {
    if ( GetFullPathNameA(lpFileName, 0x103u, lpReOpenBuff->szPathName, 0) <= 0x103 )
    {
      lpReOpenBuff->nErrCode = 0;
      v7 = 0;
      goto $finally_exit;
    }
    goto LABEL_3;
  }
  v7 = 1;
  if ( (uStyle & 2) != 0 )
    v8 = -1073741824;
  else
    v8 = (((uStyle & 1) == 0) + 1) << 30;
  v9 = uStyle & 0x70;
  if ( (uStyle & 0x70) != 0 )
  {
    switch ( v9 )
    {
      case 0x10u:
        v10 = 0;
        goto LABEL_17;
      case 0x20u:
        v10 = 5;
        goto LABEL_17;
      case 0x30u:
        v10 = 6;
        goto LABEL_17;
    }
  }
  v10 = 7;
LABEL_17:
  if ( (uStyle & 0x1000) != 0 )
    v8 = -1073741824;
  dwCreationDisposition = 3 - ((uStyle & 0x1000) != 0);
  if ( (uStyle & 0x8000) == 0 )
  {
    v11 = SearchPathA(0, lpFileName, 0, 0x103u, lpReOpenBuff->szPathName, 0);
    if ( v11 > 0x103 )
      goto LABEL_3;
    if ( v11 )
    {
      if ( (uStyle & 0x4000) != 0 )
        goto $finally_exit;
    }
    else
    {
      if ( (uStyle & 0x4000) != 0 )
      {
        v6 = 2;
        goto LABEL_4;
      }
      if ( GetFullPathNameA(lpFileName, 0x103u, lpReOpenBuff->szPathName, 0) - 1 > 0x102 )
      {
LABEL_3:
        v6 = 13;
LABEL_4:
        SetLastError(v6);
        v7 = -1;
        goto $finally_exit;
      }
    }
  }
  v12 = uStyle & 0xFFFF0000;
  FileA = CreateFileA(lpReOpenBuff->szPathName, v8, v10, 0, dwCreationDisposition, v12, 0);
  v7 = (unsigned int)FileA;
  if ( FileA == (HANDLE)-1LL )
  {
    isWow64Process = 0;
    CurrentProcess = GetCurrentProcess();
    if ( IsWow64Process(CurrentProcess, &isWow64Process) )
    {
      LastError = GetLastError();
      if ( LastError == 2 )
      {
        if ( isWow64Process )
        {
          pFsRedirection = 0;
          if ( Wow64DisableWow64FsRedirection(&pFsRedirection) )
          {
            v7 = (unsigned int)CreateFileA(lpReOpenBuff->szPathName, v8, v10, 0, dwCreationDisposition, v12, 0);
            LastError = GetLastError();
            Wow64RevertWow64FsRedirection(pFsRedirection);
          }
          SetLastError(LastError);
        }
      }
    }
  }
$finally_exit:
  v16 = (unsigned __int16)GetLastError();
  result = v7;
  lpReOpenBuff->nErrCode = v16;
  return result;
}

```

## disassembly

```asm
0x1800b9488  mov     [rsp+arg_0], rbx
0x1800b948d  push    rbp
0x1800b948e  push    rsi
0x1800b948f  push    rdi
0x1800b9490  push    r12
0x1800b9492  push    r13
0x1800b9494  push    r14
0x1800b9496  push    r15
0x1800b9498  sub     rsp, 40h
0x1800b949c  mov     r13, lpFileName
0x1800b949f  mov     ebp, uStyle
0x1800b94a2  xor     ecx, ecx; dwErrCode
0x1800b94a4  mov     r12, lpReOpenBuff
0x1800b94a7  call    cs:__imp_SetLastError
0x1800b94ad  bt      ebp, 8
0x1800b94b1  jnb     short loc_1800B94F3
0x1800b94b3  mov     r14d, 103h
0x1800b94b9  lea     r8, [r12+4]; lpBuffer
0x1800b94be  mov     edx, r14d; nBufferLength
0x1800b94c1  xor     r9d, r9d; lpFilePart
0x1800b94c4  mov     lpFileName, r13; lpFileName
0x1800b94c7  call    cs:__imp_GetFullPathNameA
0x1800b94cd  cmp     eax, r14d
0x1800b94d0  jbe     short loc_1800B94E6
0x1800b94d2  mov     ecx, 0Dh; dwErrCode
0x1800b94d7  call    cs:__imp_SetLastError
0x1800b94dd  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800b94e1  jmp     $finally_exit
0x1800b94e6  xor     ebx, ebx
0x1800b94e8  mov     [r12], ebx
0x1800b94ec  mov     edi, ebx
0x1800b94ee  jmp     $finally_exit
0x1800b94f3  mov     edi, 1
0x1800b94f8  mov     ecx, 0C0000000h
0x1800b94fd  test    bpl, 2
0x1800b9501  jz      short loc_1800B9507
0x1800b9503  mov     esi, ecx
0x1800b9505  jmp     short loc_1800B9512
0x1800b9507  mov     esi, ebp
0x1800b9509  not     esi
0x1800b950b  and     esi, edi
0x1800b950d  add     esi, edi
0x1800b950f  shl     esi, 1Eh
0x1800b9512  mov     eax, ebp
0x1800b9514  xor     ebx, ebx
0x1800b9516  and     eax, 70h
0x1800b9519  jz      short loc_1800B953D
0x1800b951b  cmp     eax, 10h
0x1800b951e  jz      short loc_1800B9538
0x1800b9520  cmp     eax, 20h ; ' '
0x1800b9523  jz      short loc_1800B9530
0x1800b9525  cmp     eax, 30h ; '0'
0x1800b9528  jnz     short loc_1800B953D
0x1800b952a  lea     r15d, [rbx+6]
0x1800b952e  jmp     short loc_1800B9543
0x1800b9530  mov     r15d, 5
0x1800b9536  jmp     short loc_1800B9543
0x1800b9538  mov     r15d, ebx
0x1800b953b  jmp     short loc_1800B9543
0x1800b953d  mov     r15d, 7
0x1800b9543  mov     eax, ebp
0x1800b9545  and     eax, 1000h
0x1800b954a  cmovnz  esi, ecx
0x1800b954d  neg     eax
0x1800b954f  sbb     edx, edx
0x1800b9551  add     edx, 3
0x1800b9554  mov     [rsp+78h+dwCreationDisposition], edx
0x1800b955b  lea     lpReOpenBuff, [r12+4]
0x1800b9560  bt      ebp, 0Fh
0x1800b9564  jb      short loc_1800B95D5
0x1800b9566  mov     [rsp+78h+lpFilePart], rbx; lpFilePart
0x1800b956b  mov     r14d, 103h
0x1800b9571  mov     [rsp+78h+lpBuffer], lpReOpenBuff; lpBuffer
0x1800b9576  mov     r9d, r14d; nBufferLength
0x1800b9579  mov     lpReOpenBuff, r13; lpFileName
0x1800b957c  xor     uStyle, uStyle; lpExtension
0x1800b957f  xor     ecx, ecx; lpPath
0x1800b9581  call    cs:__imp_SearchPathA
0x1800b9587  mov     ecx, eax
0x1800b9589  cmp     eax, r14d
0x1800b958c  ja      loc_1800B94D2
0x1800b9592  mov     eax, ebp
0x1800b9594  and     eax, 4000h
0x1800b9599  test    ecx, ecx
0x1800b959b  jnz     short loc_1800B95CD
0x1800b959d  test    eax, eax
0x1800b959f  jz      short loc_1800B95AB
0x1800b95a1  mov     ecx, 2
0x1800b95a6  jmp     loc_1800B94D7
0x1800b95ab  xor     r9d, r9d; lpFilePart
0x1800b95ae  lea     r8, [r12+4]; lpBuffer
0x1800b95b3  mov     edx, r14d; nBufferLength
0x1800b95b6  mov     lpFileName, r13; lpFileName
0x1800b95b9  call    cs:__imp_GetFullPathNameA
0x1800b95bf  dec     eax
0x1800b95c1  cmp     eax, 102h
0x1800b95c6  jbe     short loc_1800B95D5
0x1800b95c8  jmp     loc_1800B94D2
0x1800b95cd  test    eax, eax
0x1800b95cf  jnz     $finally_exit
0x1800b95d5  mov     eax, [rsp+78h+dwCreationDisposition]
0x1800b95dc  lea     lpFileName, [r12+4]; lpFileName
0x1800b95e1  mov     [rsp+78h+hTemplateFile], rbx; hTemplateFile
0x1800b95e6  and     ebp, 0FFFF0000h
0x1800b95ec  mov     dword ptr [rsp+78h+lpFilePart], ebp; dwFlagsAndAttributes
0x1800b95f0  xor     r9d, r9d; lpSecurityAttributes
0x1800b95f3  mov     uStyle, r15d; dwShareMode
0x1800b95f6  mov     dword ptr [rsp+78h+lpBuffer], eax; dwCreationDisposition
0x1800b95fa  mov     edx, esi; dwDesiredAccess
0x1800b95fc  call    cs:__imp_CreateFileA
0x1800b9602  mov     rdi, rax
0x1800b9605  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b9609  jnz     $finally_exit
0x1800b960f  mov     [rsp+78h+isWow64Process], ebx
0x1800b9616  call    cs:__imp_GetCurrentProcess
0x1800b961c  mov     lpFileName, rax; hProcess
0x1800b961f  lea     lpReOpenBuff, [rsp+78h+isWow64Process]; Wow64Process
0x1800b9627  call    cs:__imp_IsWow64Process
0x1800b962d  test    eax, eax
0x1800b962f  jz      short $finally_exit
0x1800b9631  call    cs:__imp_GetLastError
0x1800b9637  mov     r14d, eax
0x1800b963a  cmp     eax, 2
0x1800b963d  jnz     short $finally_exit
0x1800b963f  cmp     [rsp+78h+isWow64Process], ebx
0x1800b9646  jz      short $finally_exit
0x1800b9648  lea     lpFileName, [rsp+78h+pFsRedirection]; OldValue
0x1800b9650  mov     [rsp+78h+pFsRedirection], rbx
0x1800b9658  call    cs:__imp_Wow64DisableWow64FsRedirection
0x1800b965e  test    eax, eax
0x1800b9660  jz      short loc_1800B96A3
0x1800b9662  mov     eax, [rsp+78h+dwCreationDisposition]
0x1800b9669  lea     lpFileName, [r12+4]; lpFileName
0x1800b966e  mov     [rsp+78h+hTemplateFile], rbx; hTemplateFile
0x1800b9673  xor     r9d, r9d; lpSecurityAttributes
0x1800b9676  mov     dword ptr [rsp+78h+lpFilePart], ebp; dwFlagsAndAttributes
0x1800b967a  mov     uStyle, r15d; dwShareMode
0x1800b967d  mov     edx, esi; dwDesiredAccess
0x1800b967f  mov     dword ptr [rsp+78h+lpBuffer], eax; dwCreationDisposition
0x1800b9683  call    cs:__imp_CreateFileA
0x1800b9689  mov     rdi, rax
0x1800b968c  call    cs:__imp_GetLastError
0x1800b9692  mov     lpFileName, [rsp+78h+pFsRedirection]; OlValue
0x1800b969a  mov     r14d, eax
0x1800b969d  call    cs:__imp_Wow64RevertWow64FsRedirection
0x1800b96a3  mov     ecx, r14d; dwErrCode
0x1800b96a6  call    cs:__imp_SetLastError
0x1800b96ac  call    cs:__imp_GetLastError
0x1800b96b2  mov     rbx, [rsp+78h+arg_0]
0x1800b96ba  movzx   ecx, ax
0x1800b96bd  mov     eax, edi
0x1800b96bf  mov     [r12], ecx
0x1800b96c3  add     rsp, 40h
0x1800b96c7  pop     r15
0x1800b96c9  pop     r14
0x1800b96cb  pop     r13
0x1800b96cd  pop     r12
0x1800b96cf  pop     rdi
0x1800b96d0  pop     rsi
0x1800b96d1  pop     rbp
0x1800b96d2  retn
```
