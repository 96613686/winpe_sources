# GetProcessAppContainerSID(ulong,ulong,void *)

- ea: `0x1800530e0`
- end: `0x1800531e6`
- name: `?GetProcessAppContainerSID@@YAJKKPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004c320`

## callees

- `0x180025024`
- `0x1800530e0`
- `0x1800542c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800531bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800531bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800530fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180053156`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800530fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180053156`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053139`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053196`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053139`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053196`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800531b1`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800531b1`

## pseudocode

```c
__int64 __fastcall GetProcessAppContainerSID(unsigned int a1, DWORD a2, void *a3)
{
  unsigned int v6; // ecx
  int ProcessToken; // ebx
  DWORD CurrentProcessId; // eax
  unsigned int v9; // ecx
  signed int LastError; // eax
  HANDLE hObject; // [rsp+48h] [rbp+20h] BYREF

  if ( !a1 || a1 == GetCurrentProcessId() )
  {
    if ( byte_180299E87 )
      goto LABEL_18;
    hObject = 0;
    CurrentProcessId = GetCurrentProcessId();
    ProcessToken = GetProcessToken(v9, CurrentProcessId, &hObject);
    if ( ProcessToken >= 0 )
    {
      ProcessToken = GetTokenPackageSID(hObject, 0x100u, qword_18029AB50);
      if ( ProcessToken >= 0 )
        byte_180299E87 = 1;
      CloseHandle(hObject);
    }
    if ( byte_180299E87 )
    {
LABEL_18:
      if ( CopySid(a2, a3, qword_18029AB50) )
      {
        return 0;
      }
      else
      {
        LastError = GetLastError();
        ProcessToken = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  else
  {
    hObject = 0;
    ProcessToken = GetProcessToken(v6, a1, &hObject);
    if ( ProcessToken >= 0 )
    {
      ProcessToken = GetTokenPackageSID(hObject, a2, a3);
      CloseHandle(hObject);
    }
  }
  return (unsigned int)ProcessToken;
}

```

## disassembly

```asm
0x1800530e0  mov     [rsp+arg_0], rbx
0x1800530e5  mov     [rsp+arg_8], rsi
0x1800530ea  push    rdi
0x1800530eb  sub     rsp, 20h
0x1800530ef  mov     rdi, r8
0x1800530f2  mov     esi, edx
0x1800530f4  mov     ebx, ecx
0x1800530f6  test    ecx, ecx
0x1800530f8  jz      short loc_180053144
0x1800530fa  call    cs:__imp_GetCurrentProcessId
0x180053100  cmp     ebx, eax
0x180053102  jz      short loc_180053144
0x180053104  lea     r8, [rsp+28h+hObject]; void **
0x180053109  mov     [rsp+28h+hObject], 0
0x180053112  mov     edx, ebx; unsigned int
0x180053114  call    ?GetProcessToken@@YAJKKPEAPEAX@Z; GetProcessToken(ulong,ulong,void * *)
0x180053119  mov     ebx, eax
0x18005311b  test    eax, eax
0x18005311d  js      loc_1800531D4
0x180053123  mov     rcx, [rsp+28h+hObject]; void *
0x180053128  mov     r8, rdi; void *
0x18005312b  mov     edx, esi; unsigned int
0x18005312d  call    ?GetTokenPackageSID@@YAJPEAXK0@Z; GetTokenPackageSID(void *,ulong,void *)
0x180053132  mov     rcx, [rsp+28h+hObject]; hObject
0x180053137  mov     ebx, eax
0x180053139  call    cs:__imp_CloseHandle
0x18005313f  jmp     loc_1800531D4
0x180053144  cmp     cs:byte_180299E87, 0
0x18005314b  jnz     short loc_1800531A5
0x18005314d  mov     [rsp+28h+hObject], 0
0x180053156  call    cs:__imp_GetCurrentProcessId
0x18005315c  mov     edx, eax; unsigned int
0x18005315e  lea     r8, [rsp+28h+hObject]; void **
0x180053163  call    ?GetProcessToken@@YAJKKPEAPEAX@Z; GetProcessToken(ulong,ulong,void * *)
0x180053168  mov     ebx, eax
0x18005316a  test    eax, eax
0x18005316c  js      short loc_18005319C
0x18005316e  mov     rcx, [rsp+28h+hObject]; void *
0x180053173  lea     r8, qword_18029AB50; void *
0x18005317a  mov     edx, 100h; unsigned int
0x18005317f  call    ?GetTokenPackageSID@@YAJPEAXK0@Z; GetTokenPackageSID(void *,ulong,void *)
0x180053184  mov     ebx, eax
0x180053186  test    eax, eax
0x180053188  js      short loc_180053191
0x18005318a  mov     cs:byte_180299E87, 1
0x180053191  mov     rcx, [rsp+28h+hObject]; hObject
0x180053196  call    cs:__imp_CloseHandle
0x18005319c  cmp     cs:byte_180299E87, 0
0x1800531a3  jz      short loc_1800531D4
0x1800531a5  lea     r8, qword_18029AB50; pSourceSid
0x1800531ac  mov     rdx, rdi; pDestinationSid
0x1800531af  mov     ecx, esi; nDestinationSidLength
0x1800531b1  call    cs:__imp_CopySid
0x1800531b7  test    eax, eax
0x1800531b9  jz      short loc_1800531BF
0x1800531bb  xor     ebx, ebx
0x1800531bd  jmp     short loc_1800531D4
0x1800531bf  call    cs:__imp_GetLastError
0x1800531c5  mov     ebx, eax
0x1800531c7  test    eax, eax
0x1800531c9  jle     short loc_1800531D4
0x1800531cb  movzx   ebx, ax
0x1800531ce  or      ebx, 80070000h
0x1800531d4  mov     rsi, [rsp+28h+arg_8]
0x1800531d9  mov     eax, ebx
0x1800531db  mov     rbx, [rsp+28h+arg_0]
0x1800531e0  add     rsp, 20h
0x1800531e4  pop     rdi
0x1800531e5  retn
```
