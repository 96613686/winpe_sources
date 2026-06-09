# IsFileAtIntegrityLevel(ushort const *,int)

- ea: `0x14000a4b0`
- end: `0x14000a5cd`
- name: `?IsFileAtIntegrityLevel@@YAJPEBGH@Z`
- size: `285`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140004a18`
- `0x14000b334`

## callees

- `0x14000a4b0`
- `0x14000ae6c`

## import_xrefs

- `ADVAPI32!ConvertStringSidToSidW` at `0x14000a50b`
- `ADVAPI32!ConvertStringSidToSidW` at `0x14000a50b`
- `ADVAPI32!EqualSid` at `0x14000a541`
- `ADVAPI32!EqualSid` at `0x14000a541`
- `KERNEL32!CloseHandle` at `0x14000a596`
- `KERNEL32!CloseHandle` at `0x14000a596`
- `KERNEL32!LocalFree` at `0x14000a559`
- `KERNEL32!LocalFree` at `0x14000a56a`
- `KERNEL32!LocalFree` at `0x14000a559`
- `KERNEL32!LocalFree` at `0x14000a56a`
- `KERNEL32!CreateFileW` at `0x14000a4dd`
- `KERNEL32!CreateFileW` at `0x14000a4dd`
- `KERNEL32!GetLastError` at `0x14000a578`
- `KERNEL32!GetLastError` at `0x14000a5a4`
- `KERNEL32!GetLastError` at `0x14000a578`
- `KERNEL32!GetLastError` at `0x14000a5a4`

## pseudocode

```c
__int64 __fastcall IsFileAtIntegrityLevel(const unsigned __int16 *a1)
{
  HANDLE FileW; // rdi
  int HandleIntegrityLevel; // ebx
  signed int v3; // eax
  signed int LastError; // eax
  PSID pSid2; // [rsp+60h] [rbp+18h] BYREF
  PSID Sid; // [rsp+68h] [rbp+20h] BYREF

  FileW = CreateFileW(a1, 0x20000u, 0, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    HandleIntegrityLevel = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    Sid = 0;
    if ( ConvertStringSidToSidW(L"ME", &Sid) )
    {
      pSid2 = 0;
      HandleIntegrityLevel = RobustGetHandleIntegrityLevel(FileW, &pSid2);
      if ( HandleIntegrityLevel >= 0 )
      {
        HandleIntegrityLevel = !EqualSid(Sid, pSid2);
        LocalFree(pSid2);
      }
      LocalFree(Sid);
    }
    else
    {
      v3 = GetLastError();
      HandleIntegrityLevel = v3;
      if ( v3 > 0 )
        HandleIntegrityLevel = (unsigned __int16)v3 | 0x80070000;
    }
    CloseHandle(FileW);
  }
  return (unsigned int)HandleIntegrityLevel;
}

```

## disassembly

```asm
0x14000a4b0  mov     rax, rsp
0x14000a4b3  mov     [rax+8], rbx
0x14000a4b7  push    rdi
0x14000a4b8  sub     rsp, 40h
0x14000a4bc  mov     qword ptr [rax-18h], 0
0x14000a4c4  xor     r9d, r9d; lpSecurityAttributes
0x14000a4c7  mov     dword ptr [rax-20h], 0
0x14000a4ce  xor     r8d, r8d; dwShareMode
0x14000a4d1  mov     edx, 20000h; dwDesiredAccess
0x14000a4d6  mov     dword ptr [rax-28h], 3
0x14000a4dd  call    cs:__imp_CreateFileW
0x14000a4e4  nop     dword ptr [rax+rax+00h]
0x14000a4e9  mov     rdi, rax
0x14000a4ec  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000a4f0  jz      loc_14000A5A4
0x14000a4f6  lea     rdx, [rsp+48h+Sid]; Sid
0x14000a4fb  mov     [rsp+48h+Sid], 0
0x14000a504  lea     rcx, aMe; "ME"
0x14000a50b  call    cs:__imp_ConvertStringSidToSidW
0x14000a512  nop     dword ptr [rax+rax+00h]
0x14000a517  test    eax, eax
0x14000a519  jz      short loc_14000A578
0x14000a51b  lea     rdx, [rsp+48h+pSid2]; Sid
0x14000a520  mov     [rsp+48h+pSid2], 0
0x14000a529  mov     rcx, rdi; Handle
0x14000a52c  call    RobustGetHandleIntegrityLevel
0x14000a531  mov     ebx, eax
0x14000a533  test    eax, eax
0x14000a535  js      short loc_14000A565
0x14000a537  mov     rdx, [rsp+48h+pSid2]; pSid2
0x14000a53c  mov     rcx, [rsp+48h+Sid]; pSid1
0x14000a541  call    cs:__imp_EqualSid
0x14000a548  nop     dword ptr [rax+rax+00h]
0x14000a54d  mov     rcx, [rsp+48h+pSid2]; hMem
0x14000a552  xor     ebx, ebx
0x14000a554  test    eax, eax
0x14000a556  setz    bl
0x14000a559  call    cs:__imp_LocalFree
0x14000a560  nop     dword ptr [rax+rax+00h]
0x14000a565  mov     rcx, [rsp+48h+Sid]; hMem
0x14000a56a  call    cs:__imp_LocalFree
0x14000a571  nop     dword ptr [rax+rax+00h]
0x14000a576  jmp     short loc_14000A593
0x14000a578  call    cs:__imp_GetLastError
0x14000a57f  nop     dword ptr [rax+rax+00h]
0x14000a584  mov     ebx, eax
0x14000a586  test    eax, eax
0x14000a588  jle     short loc_14000A593
0x14000a58a  movzx   ebx, ax
0x14000a58d  or      ebx, 80070000h
0x14000a593  mov     rcx, rdi; hObject
0x14000a596  call    cs:__imp_CloseHandle
0x14000a59d  nop     dword ptr [rax+rax+00h]
0x14000a5a2  jmp     short loc_14000A5BF
0x14000a5a4  call    cs:__imp_GetLastError
0x14000a5ab  nop     dword ptr [rax+rax+00h]
0x14000a5b0  mov     ebx, eax
0x14000a5b2  test    eax, eax
0x14000a5b4  jle     short loc_14000A5BF
0x14000a5b6  movzx   ebx, ax
0x14000a5b9  or      ebx, 80070000h
0x14000a5bf  mov     eax, ebx
0x14000a5c1  mov     rbx, [rsp+48h+arg_0]
0x14000a5c6  add     rsp, 40h
0x14000a5ca  pop     rdi
0x14000a5cb  retn
```
