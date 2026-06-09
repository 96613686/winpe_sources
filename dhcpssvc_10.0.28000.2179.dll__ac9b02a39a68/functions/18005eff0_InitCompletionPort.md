# InitCompletionPort

- ea: `0x18005eff0`
- end: `0x18005f19a`
- name: `InitCompletionPort`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18005546c`

## callees

- `0x18000282c`
- `0x18005eff0`

## import_xrefs

- `KERNEL32!CreateIoCompletionPort` at `0x18005f0a2`
- `KERNEL32!CreateIoCompletionPort` at `0x18005f0f1`
- `KERNEL32!CreateIoCompletionPort` at `0x18005f0a2`
- `KERNEL32!CreateIoCompletionPort` at `0x18005f0f1`
- `KERNEL32!GetActiveProcessorCount` at `0x18005f01e`
- `KERNEL32!GetActiveProcessorCount` at `0x18005f01e`
- `KERNEL32!GetCurrentProcessorNumberEx` at `0x18005f00d`
- `KERNEL32!GetCurrentProcessorNumberEx` at `0x18005f00d`
- `KERNEL32!GetLastError` at `0x18005f0ba`
- `KERNEL32!GetLastError` at `0x18005f109`
- `KERNEL32!GetLastError` at `0x18005f0ba`
- `KERNEL32!GetLastError` at `0x18005f109`
- `KERNEL32!CloseHandle` at `0x18005f14d`
- `KERNEL32!CloseHandle` at `0x18005f170`
- `KERNEL32!CloseHandle` at `0x18005f14d`
- `KERNEL32!CloseHandle` at `0x18005f170`

## pseudocode

```c
__int64 __fastcall InitCompletionPort(int a1, int a2)
{
  DWORD v3; // esi
  DWORD ActiveProcessorCount; // eax
  int v6; // ecx
  DWORD v7; // r9d
  unsigned int v8; // ecx
  int v9; // eax
  __int64 v10; // r9
  DWORD LastError; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  struct _PROCESSOR_NUMBER v15; // [rsp+30h] [rbp+8h] BYREF

  v3 = 0;
  v15 = 0;
  GetCurrentProcessorNumberEx(&v15);
  ActiveProcessorCount = GetActiveProcessorCount(v15.Group);
  v6 = 1;
  v7 = ActiveProcessorCount;
  if ( a1 != -1 )
    v6 = a1;
  v8 = ActiveProcessorCount + v6;
  v9 = 0;
  if ( a2 != -1 )
    v9 = a2;
  v10 = v9 + v7;
  if ( (unsigned int)v10 > v8 )
    return 87;
  dword_1800FCF28 = v8;
  NumberOfConcurrentThreads = v10;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, v10);
    LODWORD(v10) = NumberOfConcurrentThreads;
  }
  qword_1800FD188 = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, v10);
  if ( !qword_1800FD188 )
  {
    LastError = GetLastError();
    v3 = LastError;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v14 = 44;
LABEL_18:
      WPP_SF_D(v13[2], v14, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, LastError);
      goto LABEL_19;
    }
    goto LABEL_19;
  }
  CompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, NumberOfConcurrentThreads);
  if ( !CompletionPort )
  {
    LastError = GetLastError();
    v3 = LastError;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v14 = 45;
      goto LABEL_18;
    }
LABEL_19:
    if ( v3 )
    {
      if ( qword_1800FD188 )
      {
        CloseHandle(qword_1800FD188);
        qword_1800FD188 = 0;
      }
      if ( CompletionPort )
      {
        CloseHandle(CompletionPort);
        CompletionPort = 0;
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18005eff0  mov     rax, rsp
0x18005eff3  mov     [rax+10h], rbx
0x18005eff7  mov     [rax+18h], rsi
0x18005effb  push    rdi
0x18005effc  sub     rsp, 20h
0x18005f000  mov     ebx, ecx
0x18005f002  xor     esi, esi
0x18005f004  lea     rcx, [rax+8]; ProcNumber
0x18005f008  mov     [rax+8], esi
0x18005f00b  mov     edi, edx
0x18005f00d  call    cs:__imp_GetCurrentProcessorNumberEx
0x18005f014  nop     dword ptr [rax+rax+00h]
0x18005f019  movzx   ecx, word ptr [rsp+28h+arg_0]; GroupNumber
0x18005f01e  call    cs:__imp_GetActiveProcessorCount
0x18005f025  nop     dword ptr [rax+rax+00h]
0x18005f02a  or      edx, 0FFFFFFFFh
0x18005f02d  lea     ecx, [rsi+1]
0x18005f030  cmp     ebx, edx
0x18005f032  mov     r9d, eax
0x18005f035  cmovnz  ecx, ebx
0x18005f038  add     ecx, eax
0x18005f03a  xor     eax, eax
0x18005f03c  cmp     edi, edx
0x18005f03e  cmovnz  eax, edi
0x18005f041  add     r9d, eax
0x18005f044  cmp     r9d, ecx
0x18005f047  jbe     short loc_18005F051
0x18005f049  lea     eax, [rsi+57h]
0x18005f04c  jmp     loc_18005F189
0x18005f051  mov     cs:dword_1800FCF28, ecx
0x18005f057  mov     cs:NumberOfConcurrentThreads, r9d
0x18005f05e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f065  lea     rbx, WPP_GLOBAL_Control
0x18005f06c  lea     rdi, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x18005f073  cmp     rcx, rbx
0x18005f076  jz      short loc_18005F099
0x18005f078  test    dword ptr [rcx+1Ch], 8000000h
0x18005f07f  jz      short loc_18005F099
0x18005f081  mov     rcx, [rcx+10h]
0x18005f085  mov     edx, 2Bh ; '+'
0x18005f08a  mov     r8, rdi
0x18005f08d  call    WPP_SF_D
0x18005f092  mov     r9d, cs:NumberOfConcurrentThreads; NumberOfConcurrentThreads
0x18005f099  xor     r8d, r8d; CompletionKey
0x18005f09c  xor     edx, edx; ExistingCompletionPort
0x18005f09e  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x18005f0a2  call    cs:__imp_CreateIoCompletionPort
0x18005f0a9  nop     dword ptr [rax+rax+00h]
0x18005f0ae  mov     cs:qword_1800FD188, rax
0x18005f0b5  test    rax, rax
0x18005f0b8  jnz     short loc_18005F0E1
0x18005f0ba  call    cs:__imp_GetLastError
0x18005f0c1  nop     dword ptr [rax+rax+00h]
0x18005f0c6  mov     esi, eax
0x18005f0c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f0cf  cmp     rcx, rbx
0x18005f0d2  jz      short loc_18005F13D
0x18005f0d4  test    byte ptr [rcx+1Ch], 10h
0x18005f0d8  jz      short loc_18005F13D
0x18005f0da  mov     edx, 2Ch ; ','
0x18005f0df  jmp     short loc_18005F12E
0x18005f0e1  mov     r9d, cs:NumberOfConcurrentThreads; NumberOfConcurrentThreads
0x18005f0e8  xor     r8d, r8d; CompletionKey
0x18005f0eb  xor     edx, edx; ExistingCompletionPort
0x18005f0ed  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x18005f0f1  call    cs:__imp_CreateIoCompletionPort
0x18005f0f8  nop     dword ptr [rax+rax+00h]
0x18005f0fd  mov     cs:CompletionPort, rax
0x18005f104  test    rax, rax
0x18005f107  jnz     short loc_18005F187
0x18005f109  call    cs:__imp_GetLastError
0x18005f110  nop     dword ptr [rax+rax+00h]
0x18005f115  mov     esi, eax
0x18005f117  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f11e  cmp     rcx, rbx
0x18005f121  jz      short loc_18005F13D
0x18005f123  test    byte ptr [rcx+1Ch], 10h
0x18005f127  jz      short loc_18005F13D
0x18005f129  mov     edx, 2Dh ; '-'
0x18005f12e  mov     rcx, [rcx+10h]
0x18005f132  mov     r9d, eax
0x18005f135  mov     r8, rdi
0x18005f138  call    WPP_SF_D
0x18005f13d  test    esi, esi
0x18005f13f  jz      short loc_18005F187
0x18005f141  mov     rcx, cs:qword_1800FD188; hObject
0x18005f148  test    rcx, rcx
0x18005f14b  jz      short loc_18005F164
0x18005f14d  call    cs:__imp_CloseHandle
0x18005f154  nop     dword ptr [rax+rax+00h]
0x18005f159  mov     cs:qword_1800FD188, 0
0x18005f164  mov     rcx, cs:CompletionPort; hObject
0x18005f16b  test    rcx, rcx
0x18005f16e  jz      short loc_18005F187
0x18005f170  call    cs:__imp_CloseHandle
0x18005f177  nop     dword ptr [rax+rax+00h]
0x18005f17c  mov     cs:CompletionPort, 0
0x18005f187  mov     eax, esi
0x18005f189  mov     rbx, [rsp+28h+arg_8]
0x18005f18e  mov     rsi, [rsp+28h+arg_10]
0x18005f193  add     rsp, 20h
0x18005f197  pop     rdi
0x18005f198  retn
```
