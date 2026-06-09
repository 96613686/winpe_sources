# ThreadsDataInit

- ea: `0x18006169c`
- end: `0x180061871`
- name: `ThreadsDataInit`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180055758`

## callees

- `0x180002854`
- `0x18005f294`
- `0x18006169c`

## import_xrefs

- `KERNEL32!CreateIoCompletionPort` at `0x180061760`
- `KERNEL32!CreateIoCompletionPort` at `0x1800617af`
- `KERNEL32!CreateIoCompletionPort` at `0x180061760`
- `KERNEL32!CreateIoCompletionPort` at `0x1800617af`
- `KERNEL32!GetActiveProcessorCount` at `0x1800616da`
- `KERNEL32!GetActiveProcessorCount` at `0x1800616da`
- `KERNEL32!GetCurrentProcessorNumberEx` at `0x1800616c9`
- `KERNEL32!GetCurrentProcessorNumberEx` at `0x1800616c9`
- `KERNEL32!GetLastError` at `0x180061778`
- `KERNEL32!GetLastError` at `0x1800617c7`
- `KERNEL32!GetLastError` at `0x180061778`
- `KERNEL32!GetLastError` at `0x1800617c7`
- `KERNEL32!CloseHandle` at `0x18006180b`
- `KERNEL32!CloseHandle` at `0x18006182b`
- `KERNEL32!CloseHandle` at `0x18006180b`
- `KERNEL32!CloseHandle` at `0x18006182b`

## pseudocode

```c
__int64 ThreadsDataInit()
{
  int v0; // ebx
  int v1; // esi
  unsigned int v2; // edi
  DWORD ActiveProcessorCount; // eax
  int v4; // r9d
  unsigned int v5; // esi
  __int64 v6; // r9
  DWORD LastError; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 result; // rax
  struct _PROCESSOR_NUMBER v11; // [rsp+38h] [rbp+10h] BYREF

  v0 = g_cMaxActiveThreads;
  v1 = g_cMaxProcessingThreads;
  v2 = 0;
  v11 = 0;
  GetCurrentProcessorNumberEx(&v11);
  ActiveProcessorCount = GetActiveProcessorCount(v11.Group);
  if ( v1 == -1 )
    v1 = 1;
  v4 = 0;
  v5 = ActiveProcessorCount + v1;
  if ( v0 != -1 )
    v4 = v0;
  v6 = ActiveProcessorCount + v4;
  if ( (unsigned int)v6 > v5 )
  {
    v2 = 87;
    goto LABEL_24;
  }
  dword_1800FAF38 = v5;
  NumberOfConcurrentThreads = v6;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, v6);
    LODWORD(v6) = NumberOfConcurrentThreads;
  }
  qword_1800FB1C0 = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, v6);
  if ( qword_1800FB1C0 )
  {
    CompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, NumberOfConcurrentThreads);
    if ( CompletionPort )
      goto LABEL_24;
    LastError = GetLastError();
    v2 = LastError;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v9 = 45;
      goto LABEL_18;
    }
  }
  else
  {
    LastError = GetLastError();
    v2 = LastError;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v9 = 44;
LABEL_18:
      WPP_SF_D(v8[2], v9, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, LastError);
    }
  }
  if ( v2 )
  {
    if ( qword_1800FB1C0 )
    {
      CloseHandle(qword_1800FB1C0);
      qword_1800FB1C0 = 0;
    }
    if ( CompletionPort )
    {
      CloseHandle(CompletionPort);
      CompletionPort = 0;
    }
  }
LABEL_24:
  ++dword_1800FB180;
  if ( v2 )
    return v2;
  result = InitQData();
  ++dword_1800FB180;
  return result;
}

```

## disassembly

```asm
0x18006169c  mov     rax, rsp
0x18006169f  mov     [rax+8], rbx
0x1800616a3  mov     [rax+18h], rsi
0x1800616a7  mov     [rax+20h], rdi
0x1800616ab  mov     [rax+10h], edx
0x1800616ae  push    r14
0x1800616b0  sub     rsp, 20h
0x1800616b4  mov     ebx, cs:g_cMaxActiveThreads
0x1800616ba  lea     rcx, [rax+10h]; ProcNumber
0x1800616be  mov     esi, cs:g_cMaxProcessingThreads
0x1800616c4  xor     edi, edi
0x1800616c6  and     [rax+10h], edi
0x1800616c9  call    cs:__imp_GetCurrentProcessorNumberEx
0x1800616d0  nop     dword ptr [rax+rax+00h]
0x1800616d5  movzx   ecx, word ptr [rsp+28h+arg_8]; GroupNumber
0x1800616da  call    cs:__imp_GetActiveProcessorCount
0x1800616e1  nop     dword ptr [rax+rax+00h]
0x1800616e6  or      ecx, 0FFFFFFFFh
0x1800616e9  lea     r14d, [rdi+1]
0x1800616ed  cmp     esi, ecx
0x1800616ef  cmovz   esi, r14d
0x1800616f3  xor     r9d, r9d
0x1800616f6  add     esi, eax
0x1800616f8  cmp     ebx, ecx
0x1800616fa  cmovnz  r9d, ebx
0x1800616fe  add     r9d, eax
0x180061701  cmp     r9d, esi
0x180061704  jbe     short loc_18006170F
0x180061706  lea     edi, [r14+56h]
0x18006170a  jmp     loc_18006183F
0x18006170f  mov     cs:dword_1800FAF38, esi
0x180061715  mov     cs:NumberOfConcurrentThreads, r9d
0x18006171c  mov     rcx, cs:WPP_GLOBAL_Control
0x180061723  lea     rbx, WPP_GLOBAL_Control
0x18006172a  lea     rsi, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180061731  cmp     rcx, rbx
0x180061734  jz      short loc_180061757
0x180061736  test    dword ptr [rcx+1Ch], 8000000h
0x18006173d  jz      short loc_180061757
0x18006173f  mov     rcx, [rcx+10h]
0x180061743  mov     edx, 2Bh ; '+'
0x180061748  mov     r8, rsi
0x18006174b  call    WPP_SF_D
0x180061750  mov     r9d, cs:NumberOfConcurrentThreads; NumberOfConcurrentThreads
0x180061757  xor     r8d, r8d; CompletionKey
0x18006175a  xor     edx, edx; ExistingCompletionPort
0x18006175c  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x180061760  call    cs:__imp_CreateIoCompletionPort
0x180061767  nop     dword ptr [rax+rax+00h]
0x18006176c  mov     cs:qword_1800FB1C0, rax
0x180061773  test    rax, rax
0x180061776  jnz     short loc_18006179F
0x180061778  call    cs:__imp_GetLastError
0x18006177f  nop     dword ptr [rax+rax+00h]
0x180061784  mov     edi, eax
0x180061786  mov     rcx, cs:WPP_GLOBAL_Control
0x18006178d  cmp     rcx, rbx
0x180061790  jz      short loc_1800617FB
0x180061792  test    byte ptr [rcx+1Ch], 10h
0x180061796  jz      short loc_1800617FB
0x180061798  mov     edx, 2Ch ; ','
0x18006179d  jmp     short loc_1800617EC
0x18006179f  mov     r9d, cs:NumberOfConcurrentThreads; NumberOfConcurrentThreads
0x1800617a6  xor     r8d, r8d; CompletionKey
0x1800617a9  xor     edx, edx; ExistingCompletionPort
0x1800617ab  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x1800617af  call    cs:__imp_CreateIoCompletionPort
0x1800617b6  nop     dword ptr [rax+rax+00h]
0x1800617bb  mov     cs:CompletionPort, rax
0x1800617c2  test    rax, rax
0x1800617c5  jnz     short loc_18006183F
0x1800617c7  call    cs:__imp_GetLastError
0x1800617ce  nop     dword ptr [rax+rax+00h]
0x1800617d3  mov     edi, eax
0x1800617d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800617dc  cmp     rcx, rbx
0x1800617df  jz      short loc_1800617FB
0x1800617e1  test    byte ptr [rcx+1Ch], 10h
0x1800617e5  jz      short loc_1800617FB
0x1800617e7  mov     edx, 2Dh ; '-'
0x1800617ec  mov     rcx, [rcx+10h]
0x1800617f0  mov     r9d, eax
0x1800617f3  mov     r8, rsi
0x1800617f6  call    WPP_SF_D
0x1800617fb  test    edi, edi
0x1800617fd  jz      short loc_18006183F
0x1800617ff  mov     rcx, cs:qword_1800FB1C0; hObject
0x180061806  test    rcx, rcx
0x180061809  jz      short loc_18006181F
0x18006180b  call    cs:__imp_CloseHandle
0x180061812  nop     dword ptr [rax+rax+00h]
0x180061817  and     cs:qword_1800FB1C0, 0
0x18006181f  mov     rcx, cs:CompletionPort; hObject
0x180061826  test    rcx, rcx
0x180061829  jz      short loc_18006183F
0x18006182b  call    cs:__imp_CloseHandle
0x180061832  nop     dword ptr [rax+rax+00h]
0x180061837  and     cs:CompletionPort, 0
0x18006183f  add     cs:dword_1800FB180, r14d
0x180061846  test    edi, edi
0x180061848  jz      short loc_18006184E
0x18006184a  mov     eax, edi
0x18006184c  jmp     short loc_18006185A
0x18006184e  call    InitQData
0x180061853  add     cs:dword_1800FB180, r14d
0x18006185a  mov     rbx, [rsp+28h+arg_0]
0x18006185f  mov     rsi, [rsp+28h+arg_10]
0x180061864  mov     rdi, [rsp+28h+arg_18]
0x180061869  add     rsp, 20h
0x18006186d  pop     r14
0x18006186f  retn
```
