# DirectoryIsNotLowIL

- ea: `0x140009900`
- end: `0x140009a01`
- name: `DirectoryIsNotLowIL`
- size: `257`
- prototype: `__int64 __fastcall(PCWSTR pszPath)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140008f78`

## callees

- `0x140009900`
- `0x14000ae6c`
- `0x1400105d8`

## import_xrefs

- `ADVAPI32!ConvertStringSidToSidW` at `0x14000995c`
- `ADVAPI32!ConvertStringSidToSidW` at `0x14000995c`
- `ADVAPI32!EqualSid` at `0x14000998c`
- `ADVAPI32!EqualSid` at `0x14000998c`
- `KERNEL32!CloseHandle` at `0x1400099e2`
- `KERNEL32!CloseHandle` at `0x1400099e2`
- `KERNEL32!LocalFree` at `0x1400099c2`
- `KERNEL32!LocalFree` at `0x1400099d3`
- `KERNEL32!LocalFree` at `0x1400099c2`
- `KERNEL32!LocalFree` at `0x1400099d3`
- `KERNEL32!CreateFileW` at `0x140009932`
- `KERNEL32!CreateFileW` at `0x140009932`

## pseudocode

```c
__int64 __fastcall DirectoryIsNotLowIL(PCWSTR pszPath)
{
  unsigned int IsRoot; // ebx
  HANDLE FileW; // rdi
  int HandleIntegrityLevel; // eax
  PSID pSid2; // [rsp+58h] [rbp+10h] BYREF
  PSID Sid; // [rsp+60h] [rbp+18h] BYREF

  IsRoot = 0;
  FileW = CreateFileW(pszPath, 0x20000u, 0, 0, 3u, 0x2000000u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    Sid = 0;
    if ( ConvertStringSidToSidW(L"LW", &Sid) )
    {
      pSid2 = 0;
      HandleIntegrityLevel = RobustGetHandleIntegrityLevel(FileW, &pSid2);
      if ( HandleIntegrityLevel < 0 )
      {
        if ( HandleIntegrityLevel == -2147023556 )
          IsRoot = PathCchIsRoot(pszPath);
      }
      else
      {
        LOBYTE(IsRoot) = !EqualSid(Sid, pSid2);
      }
      if ( pSid2 )
        LocalFree(pSid2);
      LocalFree(Sid);
    }
    CloseHandle(FileW);
  }
  return IsRoot;
}

```

## disassembly

```asm
0x140009900  mov     rax, rsp
0x140009903  mov     [rax+8], rbx
0x140009907  mov     [rax+20h], rsi
0x14000990b  push    rdi
0x14000990c  sub     rsp, 40h
0x140009910  xor     ebx, ebx
0x140009912  xor     r9d, r9d; lpSecurityAttributes
0x140009915  mov     [rax-18h], rbx
0x140009919  xor     r8d, r8d; dwShareMode
0x14000991c  mov     dword ptr [rax-20h], 2000000h
0x140009923  mov     edx, 20000h; dwDesiredAccess
0x140009928  mov     dword ptr [rax-28h], 3
0x14000992f  mov     rsi, rcx
0x140009932  call    cs:__imp_CreateFileW
0x140009939  nop     dword ptr [rax+rax+00h]
0x14000993e  mov     rdi, rax
0x140009941  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140009945  jz      loc_1400099EE
0x14000994b  lea     rdx, [rsp+48h+Sid]; Sid
0x140009950  mov     [rsp+48h+Sid], rbx
0x140009955  lea     rcx, StringSid; "LW"
0x14000995c  call    cs:__imp_ConvertStringSidToSidW
0x140009963  nop     dword ptr [rax+rax+00h]
0x140009968  test    eax, eax
0x14000996a  jz      short loc_1400099DF
0x14000996c  lea     rdx, [rsp+48h+pSid2]; Sid
0x140009971  mov     [rsp+48h+pSid2], rbx
0x140009976  mov     rcx, rdi; Handle
0x140009979  call    RobustGetHandleIntegrityLevel
0x14000997e  test    eax, eax
0x140009980  js      short loc_14000999F
0x140009982  mov     rdx, [rsp+48h+pSid2]; pSid2
0x140009987  mov     rcx, [rsp+48h+Sid]; pSid1
0x14000998c  call    cs:__imp_EqualSid
0x140009993  nop     dword ptr [rax+rax+00h]
0x140009998  test    eax, eax
0x14000999a  setz    bl
0x14000999d  jmp     short loc_1400099B8
0x14000999f  cmp     eax, 8007053Ch
0x1400099a4  jnz     short loc_1400099B8
0x1400099a6  mov     rcx, rsi; pszPath
0x1400099a9  call    PathCchIsRoot
0x1400099ae  test    eax, eax
0x1400099b0  mov     ecx, 1
0x1400099b5  cmovnz  ebx, ecx
0x1400099b8  mov     rcx, [rsp+48h+pSid2]; hMem
0x1400099bd  test    rcx, rcx
0x1400099c0  jz      short loc_1400099CE
0x1400099c2  call    cs:__imp_LocalFree
0x1400099c9  nop     dword ptr [rax+rax+00h]
0x1400099ce  mov     rcx, [rsp+48h+Sid]; hMem
0x1400099d3  call    cs:__imp_LocalFree
0x1400099da  nop     dword ptr [rax+rax+00h]
0x1400099df  mov     rcx, rdi; hObject
0x1400099e2  call    cs:__imp_CloseHandle
0x1400099e9  nop     dword ptr [rax+rax+00h]
0x1400099ee  mov     rsi, [rsp+48h+arg_18]
0x1400099f3  mov     eax, ebx
0x1400099f5  mov     rbx, [rsp+48h+arg_0]
0x1400099fa  add     rsp, 40h
0x1400099fe  pop     rdi
0x1400099ff  retn
```
