# CEventLog::Open(CLogInfo *)

- ea: `0x1800154e8`
- end: `0x180015564`
- name: `?Open@CEventLog@@QEAAJPEAVCLogInfo@@@Z`
- size: `124`
- prototype: `__int64 __fastcall(CEventLog *__hidden this, struct CLogInfo *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005540`
- `0x1800158c0`
- `0x1800172cc`
- `0x180017ab8`

## callees

- `0x1800154e8`

## import_xrefs

- `ADVAPI32!OpenEventLogW` at `0x180015533`
- `ADVAPI32!OpenEventLogW` at `0x180015533`
- `ADVAPI32!OpenBackupEventLogW` at `0x180015513`
- `ADVAPI32!OpenBackupEventLogW` at `0x180015513`
- `KERNEL32!GetLastError` at `0x180015542`
- `KERNEL32!GetLastError` at `0x180015542`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CEventLog::Open(CEventLog *this, struct CLogInfo *a2)
{
  unsigned int v3; // ebx
  HANDLE v4; // rax
  signed int LastError; // eax

  *(_QWORD *)this = a2;
  v3 = 0;
  _InterlockedIncrement((volatile signed __int32 *)a2 + 1190);
  if ( (*(_BYTE *)(*(_QWORD *)this + 24LL) & 1) != 0 )
    v4 = OpenBackupEventLogW(0, (LPCWSTR)a2 + 538);
  else
    v4 = OpenEventLogW((LPCWSTR)(((unsigned __int64)a2 + 32) & -(__int64)(*((_WORD *)a2 + 16) != 0)), (LPCWSTR)a2 + 277);
  *((_QWORD *)this + 1) = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v3;
}

```

## disassembly

```asm
0x1800154e8  mov     [rsp+arg_0], rbx
0x1800154ed  push    rdi
0x1800154ee  sub     rsp, 20h
0x1800154f2  mov     rdi, rcx
0x1800154f5  mov     [rcx], rdx
0x1800154f8  xor     ebx, ebx
0x1800154fa  lock inc dword ptr [rdx+1298h]
0x180015501  mov     rax, [rcx]
0x180015504  test    byte ptr [rax+18h], 1
0x180015508  jz      short loc_18001551B
0x18001550a  add     rdx, 434h; lpFileName
0x180015511  xor     ecx, ecx; lpUNCServerName
0x180015513  call    cs:__imp_OpenBackupEventLogW
0x180015519  jmp     short loc_180015539
0x18001551b  lea     r8, [rdx+20h]
0x18001551f  add     rdx, 22Ah; lpSourceName
0x180015526  movzx   eax, word ptr [r8]
0x18001552a  neg     ax
0x18001552d  sbb     rcx, rcx
0x180015530  and     rcx, r8; lpUNCServerName
0x180015533  call    cs:__imp_OpenEventLogW
0x180015539  mov     [rdi+8], rax
0x18001553d  test    rax, rax
0x180015540  jnz     short loc_180015557
0x180015542  call    cs:__imp_GetLastError
0x180015548  mov     ebx, eax
0x18001554a  test    eax, eax
0x18001554c  jle     short loc_180015557
0x18001554e  movzx   ebx, ax
0x180015551  or      ebx, 80070000h
0x180015557  mov     eax, ebx
0x180015559  mov     rbx, [rsp+28h+arg_0]
0x18001555e  add     rsp, 20h
0x180015562  pop     rdi
0x180015563  retn
```
