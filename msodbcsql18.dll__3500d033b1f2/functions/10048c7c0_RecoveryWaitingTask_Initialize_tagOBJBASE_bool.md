# RecoveryWaitingTask::Initialize(tagOBJBASE *,bool)

- ea: `0x10048c7c0`
- end: `0x10048c870`
- name: `?Initialize@RecoveryWaitingTask@@QEAAJPEAUtagOBJBASE@@_N@Z`
- size: `176`
- prototype: `__int64 __fastcall(RecoveryWaitingTask *__hidden this, struct tagOBJBASE *, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x10048bc08`

## callees

- `0x10048c7c0`
- `0x100546a24`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x10048c80e`
- `KERNEL32!CreateEventW` at `0x10048c80e`
- `KERNEL32!GetLastError` at `0x10048c81d`
- `KERNEL32!GetLastError` at `0x10048c81d`

## pseudocode

```c
__int64 __fastcall RecoveryWaitingTask::Initialize(RecoveryWaitingTask *this, struct tagOBJBASE *a2, char a3)
{
  unsigned int v3; // ebx
  struct tagOBJBASE *v6; // rax
  bool v7; // al
  HANDLE EventW; // rax
  __int64 v9; // r9
  signed int LastError; // eax

  v3 = 0;
  if ( *((_DWORD *)a2 + 1) == 2 )
    v6 = (struct tagOBJBASE *)*((_QWORD *)a2 + 12);
  else
    v6 = a2;
  v7 = a3 && *((_DWORD *)v6 + 1057);
  *((_BYTE *)this + 40) = v7;
  if ( *((_QWORD *)this + 8) )
    goto LABEL_17;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 8) = EventW;
  if ( EventW )
  {
    *((_QWORD *)this + 7) = 0;
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
  }
  v3 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v3 = LastError;
  if ( (v3 & 0x80000000) == 0 )
  {
LABEL_17:
    *((_QWORD *)this + 4) = a2;
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    _mm_lfence();
    bidTraceHR(0, 65545, v3, v9);
  }
  return v3;
}

```

## disassembly

```asm
0x10048c7c0  mov     [rsp+arg_0], rbx
0x10048c7c5  mov     [rsp+arg_8], rsi
0x10048c7ca  push    rdi
0x10048c7cb  sub     rsp, 20h
0x10048c7cf  xor     ebx, ebx
0x10048c7d1  mov     rsi, rdx
0x10048c7d4  cmp     dword ptr [rdx+4], 2
0x10048c7d8  mov     rdi, rcx
0x10048c7db  jnz     short loc_10048C7E3
0x10048c7dd  mov     rax, [rdx+60h]
0x10048c7e1  jmp     short loc_10048C7E6
0x10048c7e3  mov     rax, rsi
0x10048c7e6  test    r8b, r8b
0x10048c7e9  jz      short loc_10048C7F7
0x10048c7eb  cmp     [rax+1084h], ebx
0x10048c7f1  jz      short loc_10048C7F7
0x10048c7f3  mov     al, 1
0x10048c7f5  jmp     short loc_10048C7F9
0x10048c7f7  xor     al, al
0x10048c7f9  mov     [rcx+28h], al
0x10048c7fc  cmp     [rcx+40h], rbx
0x10048c800  jnz     short loc_10048C85A
0x10048c802  xor     r9d, r9d; lpName
0x10048c805  xor     r8d, r8d; bInitialState
0x10048c808  xor     ecx, ecx; lpEventAttributes
0x10048c80a  lea     edx, [r9+1]; bManualReset
0x10048c80e  call    cs:__imp_CreateEventW
0x10048c814  mov     [rdi+40h], rax
0x10048c818  test    rax, rax
0x10048c81b  jnz     short loc_10048C825
0x10048c81d  call    cs:__imp_GetLastError
0x10048c823  jmp     short loc_10048C82B
0x10048c825  and     [rdi+38h], rbx
0x10048c829  xor     eax, eax
0x10048c82b  movzx   ebx, ax
0x10048c82e  or      ebx, 80070000h
0x10048c834  test    eax, eax
0x10048c836  cmovle  ebx, eax
0x10048c839  test    ebx, ebx
0x10048c83b  jns     short loc_10048C85A
0x10048c83d  test    byte ptr cs:_bidGblFlags, 2
0x10048c844  jz      short loc_10048C85E
0x10048c846  lfence
0x10048c849  mov     r8d, ebx
0x10048c84c  mov     edx, 10009h
0x10048c851  xor     ecx, ecx
0x10048c853  call    _bidTraceHR
0x10048c858  jmp     short loc_10048C85E
0x10048c85a  mov     [rdi+20h], rsi
0x10048c85e  mov     rsi, [rsp+28h+arg_8]
0x10048c863  mov     eax, ebx
0x10048c865  mov     rbx, [rsp+28h+arg_0]
0x10048c86a  add     rsp, 20h
0x10048c86e  pop     rdi
0x10048c86f  retn
```
