# QuirkIsEnabledForProcessWorker

- ea: `0x18001ce20`
- end: `0x18001d0b4`
- name: `QuirkIsEnabledForProcessWorker`
- size: `660`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001cd48`
- `0x18001cd6c`
- `0x18001ce20`
- `0x18001ddf0`
- `0x18001df5c`
- `0x18001e744`
- `0x18001e9b4`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18001cfa7`
- `ntdll!RtlFreeHeap` at `0x18001cfa7`
- `ntdll!RtlAllocateHeap` at `0x18001ce99`
- `ntdll!RtlAllocateHeap` at `0x18001ce99`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18001cefd`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18001cefd`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18001ceb3`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18001cec8`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18001ceb3`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18001cec8`
- `api-ms-win-core-appcompat-l1-1-1!BaseReadAppCompatDataForProcess` at `0x18001ce5f`
- `api-ms-win-core-appcompat-l1-1-1!BaseReadAppCompatDataForProcess` at `0x18001ce5f`
- `api-ms-win-core-appcompat-l1-1-1!BaseFreeAppCompatDataForProcess` at `0x18001d00c`
- `api-ms-win-core-appcompat-l1-1-1!BaseFreeAppCompatDataForProcess` at `0x18001d00c`

## pseudocode

```c
__int64 __fastcall QuirkIsEnabledForProcessWorker(HANDLE hProcess, unsigned int a2, int *a3)
{
  PVOID Heap; // r14
  int v7; // eax
  int LastErrorValue; // ebx
  const void *v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // rcx
  char ProcessTargetPlatform; // cl
  unsigned __int64 v13; // r8
  __int64 v14; // r10
  int v15; // eax
  int v16; // ecx
  int v17; // ecx
  bool v19; // cf
  __int64 ProcessOsMaxVersionTested; // rax
  __int64 v21; // rcx
  char v22; // al
  unsigned __int64 v23; // rdx
  __int64 v24; // rcx
  int inited; // ebx
  __int64 v26; // [rsp+30h] [rbp-10h] BYREF
  BOOL Wow64Process; // [rsp+70h] [rbp+30h] BYREF
  BOOL v28; // [rsp+88h] [rbp+48h] BYREF

  Heap = 0;
  v26 = 0;
  v28 = 0;
  Wow64Process = 0;
  if ( hProcess == (HANDLE)-1LL )
  {
    *a3 = QuirkIsEnabledWorker(a2);
    goto LABEL_15;
  }
  v7 = BaseReadAppCompatDataForProcess(hProcess, &v26, 0);
  LastErrorValue = v7;
  if ( v7 )
  {
    if ( v7 <= 0 )
      goto LABEL_16;
    LastErrorValue = (unsigned __int16)v7;
    goto LABEL_21;
  }
  v9 = *(const void **)(v26 + 4480);
  if ( v9 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, *(unsigned int *)(v26 + 4488));
    if ( !Heap )
    {
      LastErrorValue = -2147024882;
      goto LABEL_16;
    }
    if ( IsWow64Process((HANDLE)0xFFFFFFFFFFFFFFFFLL, &Wow64Process) && IsWow64Process(hProcess, &v28) )
    {
      if ( Wow64Process && !v28 )
      {
        LastErrorValue = -805306367;
        goto LABEL_16;
      }
      if ( ReadProcessMemory(hProcess, v9, Heap, *(unsigned int *)(v26 + 4488), 0) )
      {
        if ( QuirksLookupById(Heap, a2) )
        {
          SbGetProcessOsMaxVersionTested(v26);
          ProcessTargetPlatform = SbGetProcessTargetPlatform(v11, v10);
          v15 = 1;
          if ( ((unsigned int)(1LL << ProcessTargetPlatform) & *(_QWORD *)(v14 + 268)) != 0 )
          {
            v16 = QuirksGlobalOverride;
            if ( QuirksGlobalOverride == -1 )
            {
              v17 = *(_DWORD *)(v14 + 552);
              if ( (v17 & 1) != 0 )
                goto LABEL_14;
              v15 = 0;
              if ( (v17 & 2) != 0 )
                goto LABEL_14;
              v19 = v13 < *(_QWORD *)(v14 + 260);
              goto LABEL_26;
            }
            v15 = 0;
            goto LABEL_29;
          }
          goto LABEL_30;
        }
        goto LABEL_27;
      }
    }
    LastErrorValue = NtCurrentTeb()->LastErrorValue;
    if ( LastErrorValue <= 0 )
      goto LABEL_16;
    LastErrorValue = (unsigned __int16)LastErrorValue;
LABEL_21:
    LastErrorValue |= 0x80070000;
    goto LABEL_16;
  }
  v24 = QuirksTable;
  if ( QuirksTable )
  {
LABEL_41:
    if ( QuirksLookupById(v24, a2) )
    {
      ProcessOsMaxVersionTested = SbGetProcessOsMaxVersionTested(v26);
      v22 = SbGetProcessTargetPlatform(v21, ProcessOsMaxVersionTested);
      if ( ((unsigned int)(1LL << v22) & *(_QWORD *)(v14 + 268)) != 0 )
      {
        v16 = QuirksGlobalOverride;
        v15 = 0;
        if ( QuirksGlobalOverride == -1 )
        {
          v19 = v23 < *(_QWORD *)(v14 + 260);
LABEL_26:
          LOBYTE(v15) = v19;
LABEL_14:
          *a3 = v15;
          CptpQuirkSendEtwEvent((wchar_t *)v14, 0);
LABEL_15:
          LastErrorValue = 0;
          goto LABEL_16;
        }
LABEL_29:
        LOBYTE(v15) = v16 != 0;
        goto LABEL_14;
      }
LABEL_30:
      v15 = 0;
      goto LABEL_14;
    }
LABEL_27:
    LastErrorValue = -2147023728;
    goto LABEL_16;
  }
  inited = CptpQuirksInitOnce();
  if ( inited >= 0 )
  {
    v24 = QuirksTable;
    goto LABEL_41;
  }
  LastErrorValue = inited | 0x10000000;
LABEL_16:
  if ( v26 )
    BaseFreeAppCompatDataForProcess();
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)LastErrorValue;
}

```

## disassembly

```asm
0x18001ce20  mov     [rsp-28h+arg_8], rbx
0x18001ce25  push    rbp
0x18001ce26  push    rsi
0x18001ce27  push    rdi
0x18001ce28  push    r14
0x18001ce2a  push    r15
0x18001ce2c  mov     rbp, rsp
0x18001ce2f  sub     rsp, 40h
0x18001ce33  xor     r14d, r14d
0x18001ce36  mov     [rbp+var_10], 0
0x18001ce3e  mov     [rbp+arg_18], r14d
0x18001ce42  mov     r15, r8
0x18001ce45  mov     [rbp+Wow64Process], r14d
0x18001ce49  mov     edi, edx
0x18001ce4b  mov     rsi, rcx
0x18001ce4e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001ce52  jz      loc_18001CFD7
0x18001ce58  xor     r8d, r8d
0x18001ce5b  lea     rdx, [rbp+var_10]
0x18001ce5f  call    cs:__imp_BaseReadAppCompatDataForProcess
0x18001ce65  mov     ebx, eax
0x18001ce67  test    eax, eax
0x18001ce69  jnz     loc_18001CFE3
0x18001ce6f  mov     rcx, [rbp+var_10]
0x18001ce73  mov     rbx, [rcx+1180h]
0x18001ce7a  test    rbx, rbx
0x18001ce7d  jz      loc_18001D075
0x18001ce83  mov     r8d, [rcx+1188h]; Size
0x18001ce8a  xor     edx, edx; Flags
0x18001ce8c  mov     rcx, gs:60h
0x18001ce95  mov     rcx, [rcx+30h]; HeapHandle
0x18001ce99  call    cs:__imp_RtlAllocateHeap
0x18001ce9f  mov     r14, rax
0x18001cea2  test    rax, rax
0x18001cea5  jz      loc_18001D057
0x18001ceab  lea     rdx, [rbp+Wow64Process]; Wow64Process
0x18001ceaf  or      rcx, 0FFFFFFFFFFFFFFFFh; hProcess
0x18001ceb3  call    cs:__imp_IsWow64Process
0x18001ceb9  test    eax, eax
0x18001cebb  jz      loc_18001CFC0
0x18001cec1  lea     rdx, [rbp+arg_18]; Wow64Process
0x18001cec5  mov     rcx, rsi; hProcess
0x18001cec8  call    cs:__imp_IsWow64Process
0x18001cece  test    eax, eax
0x18001ced0  jz      loc_18001CFC0
0x18001ced6  cmp     [rbp+Wow64Process], 0
0x18001ceda  jnz     loc_18001D061
0x18001cee0  mov     rax, [rbp+var_10]
0x18001cee4  mov     r8, r14; lpBuffer
0x18001cee7  mov     rdx, rbx; lpBaseAddress
0x18001ceea  mov     [rsp+40h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x18001cef3  mov     rcx, rsi; hProcess
0x18001cef6  mov     r9d, [rax+1188h]; nSize
0x18001cefd  call    cs:__imp_ReadProcessMemory
0x18001cf03  test    eax, eax
0x18001cf05  jz      loc_18001CFC0
0x18001cf0b  mov     edx, edi
0x18001cf0d  mov     rcx, r14
0x18001cf10  call    QuirksLookupById
0x18001cf15  mov     r10, rax
0x18001cf18  test    rax, rax
0x18001cf1b  jz      loc_18001CFF9
0x18001cf21  mov     rcx, [rbp+var_10]
0x18001cf25  call    SbGetProcessOsMaxVersionTested
0x18001cf2a  mov     r8, rax
0x18001cf2d  call    SbGetProcessTargetPlatform
0x18001cf32  mov     ecx, eax
0x18001cf34  mov     eax, 1
0x18001cf39  mov     edx, eax
0x18001cf3b  shl     rdx, cl
0x18001cf3e  mov     ecx, edx
0x18001cf40  test    [r10+10Ch], rcx
0x18001cf47  jz      loc_18001D014
0x18001cf4d  mov     ecx, cs:QuirksGlobalOverride
0x18001cf53  cmp     ecx, 0FFFFFFFFh
0x18001cf56  jnz     loc_18001D000
0x18001cf5c  mov     ecx, [r10+228h]
0x18001cf63  test    al, cl
0x18001cf65  jnz     short loc_18001CF6E
0x18001cf67  xor     eax, eax
0x18001cf69  test    cl, 2
0x18001cf6c  jz      short loc_18001CFEA
0x18001cf6e  xor     r9d, r9d
0x18001cf71  mov     [r15], eax
0x18001cf74  mov     r8, rsi
0x18001cf77  mov     [rsp+40h+lpNumberOfBytesRead], 0; wchar_t *
0x18001cf80  mov     edx, eax
0x18001cf82  mov     rcx, r10; String
0x18001cf85  call    CptpQuirkSendEtwEvent
0x18001cf8a  xor     ebx, ebx
0x18001cf8c  mov     rcx, [rbp+var_10]
0x18001cf90  test    rcx, rcx
0x18001cf93  jnz     short loc_18001D00C
0x18001cf95  mov     rcx, gs:60h
0x18001cf9e  mov     r8, r14; P
0x18001cfa1  xor     edx, edx; Flags
0x18001cfa3  mov     rcx, [rcx+30h]; HeapHandle
0x18001cfa7  call    cs:__imp_RtlFreeHeap
0x18001cfad  mov     eax, ebx
0x18001cfaf  mov     rbx, [rsp+40h+arg_8]
0x18001cfb4  add     rsp, 40h
0x18001cfb8  pop     r15
0x18001cfba  pop     r14
0x18001cfbc  pop     rdi
0x18001cfbd  pop     rsi
0x18001cfbe  pop     rbp
0x18001cfbf  retn
0x18001cfc0  mov     ebx, gs:68h
0x18001cfc8  test    ebx, ebx
0x18001cfca  jle     short loc_18001CF8C
0x18001cfcc  movzx   ebx, bx
0x18001cfcf  or      ebx, 80070000h
0x18001cfd5  jmp     short loc_18001CF8C
0x18001cfd7  mov     ecx, edi
0x18001cfd9  call    QuirkIsEnabledWorker
0x18001cfde  mov     [r15], eax
0x18001cfe1  jmp     short loc_18001CF8A
0x18001cfe3  jle     short loc_18001CF8C
0x18001cfe5  movzx   ebx, ax
0x18001cfe8  jmp     short loc_18001CFCF
0x18001cfea  cmp     r8, [r10+104h]
0x18001cff1  setb    al
0x18001cff4  jmp     loc_18001CF6E
0x18001cff9  mov     ebx, 80070490h
0x18001cffe  jmp     short loc_18001CF8C
0x18001d000  xor     eax, eax
0x18001d002  test    ecx, ecx
0x18001d004  setnz   al
0x18001d007  jmp     loc_18001CF6E
0x18001d00c  call    cs:__imp_BaseFreeAppCompatDataForProcess
0x18001d012  jmp     short loc_18001CF95
0x18001d014  xor     eax, eax
0x18001d016  jmp     loc_18001CF6E
0x18001d01b  mov     rcx, [rbp+var_10]
0x18001d01f  call    SbGetProcessOsMaxVersionTested
0x18001d024  mov     rdx, rax
0x18001d027  call    SbGetProcessTargetPlatform
0x18001d02c  mov     ecx, eax
0x18001d02e  mov     eax, 1
0x18001d033  shl     rax, cl
0x18001d036  mov     ecx, eax
0x18001d038  test    [r10+10Ch], rcx
0x18001d03f  jz      short loc_18001D014
0x18001d041  mov     ecx, cs:QuirksGlobalOverride
0x18001d047  xor     eax, eax
0x18001d049  cmp     ecx, 0FFFFFFFFh
0x18001d04c  jnz     short loc_18001D002
0x18001d04e  cmp     rdx, [r10+104h]
0x18001d055  jmp     short loc_18001CFF1
0x18001d057  mov     ebx, 8007000Eh
0x18001d05c  jmp     loc_18001CF8C
0x18001d061  cmp     [rbp+arg_18], 0
0x18001d065  jnz     loc_18001CEE0
0x18001d06b  mov     ebx, 0D0000001h
0x18001d070  jmp     loc_18001CF8C
0x18001d075  mov     rcx, cs:QuirksTable
0x18001d07c  test    rcx, rcx
0x18001d07f  jnz     short loc_18001D09C
0x18001d081  call    CptpQuirksInitOnce
0x18001d086  mov     ebx, eax
0x18001d088  test    eax, eax
0x18001d08a  jns     short loc_18001D095
0x18001d08c  bts     ebx, 1Ch
0x18001d090  jmp     loc_18001CF8C
0x18001d095  mov     rcx, cs:QuirksTable
0x18001d09c  mov     edx, edi
0x18001d09e  call    QuirksLookupById
0x18001d0a3  mov     r10, rax
0x18001d0a6  test    rax, rax
0x18001d0a9  jz      loc_18001CFF9
0x18001d0af  jmp     loc_18001D01B
```
