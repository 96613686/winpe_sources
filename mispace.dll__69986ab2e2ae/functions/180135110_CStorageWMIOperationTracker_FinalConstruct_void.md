# CStorageWMIOperationTracker::FinalConstruct(void)

- ea: `0x180135110`
- end: `0x18013529d`
- name: `?FinalConstruct@CStorageWMIOperationTracker@@QEAAJXZ`
- size: `397`
- prototype: `__int64 __fastcall(CStorageWMIOperationTracker *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180134e10`

## callees

- `0x180135110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801351bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013520e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180135261`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180135274`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801351bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013520e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180135261`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180135274`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180135185`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801351dc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18013522d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180135185`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801351dc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18013522d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18013516d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18013516d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801351a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801351f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18013524a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801351a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801351f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18013524a`

## pseudocode

```c
__int64 __fastcall CStorageWMIOperationTracker::FinalConstruct(CStorageWMIOperationTracker *this)
{
  char *v1; // rax
  __int64 v3; // rcx
  __int64 v4; // rdx
  char *v5; // rax
  __int64 v6; // rdx
  char *v7; // rax
  HANDLE EventW; // rax
  char *v9; // rcx
  HANDLE v10; // rdi
  HANDLE v11; // rax
  char *v12; // rcx
  HANDLE v13; // rdi
  HANDLE v14; // rax
  char *v15; // rcx
  HANDLE v16; // rdi
  unsigned int v17; // ebx
  signed int LastError; // eax

  v1 = (char *)this + 64;
  v3 = 16;
  if ( v1 )
  {
    v4 = 16;
    do
    {
      *v1++ = 0;
      --v4;
    }
    while ( v4 );
  }
  v5 = (char *)this + 48;
  if ( this != (CStorageWMIOperationTracker *)-48LL )
  {
    v6 = 16;
    do
    {
      *v5++ = 0;
      --v6;
    }
    while ( v6 );
  }
  v7 = (char *)this + 80;
  if ( this != (CStorageWMIOperationTracker *)-80LL )
  {
    do
    {
      *v7++ = 0;
      --v3;
    }
    while ( v3 );
  }
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  EventW = CreateEventW(0, 1, 0, 0);
  v9 = (char *)*((_QWORD *)this + 12);
  v10 = EventW;
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v9);
  *((_QWORD *)this + 12) = v10;
  if ( !v10 || GetLastError() == 183 )
    goto LABEL_21;
  v11 = CreateEventW(0, 0, 0, 0);
  v12 = (char *)*((_QWORD *)this + 13);
  v13 = v11;
  if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v12);
  *((_QWORD *)this + 13) = v13;
  if ( !v13 || GetLastError() == 183 )
    goto LABEL_21;
  v14 = CreateEventW(0, 1, 0, 0);
  v15 = (char *)*((_QWORD *)this + 14);
  v16 = v14;
  if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v15);
  *((_QWORD *)this + 14) = v16;
  if ( !v16 || (v17 = 0, GetLastError() == 183) )
  {
LABEL_21:
    LastError = GetLastError();
    v17 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v17;
}

```

## disassembly

```asm
0x180135110  mov     [rsp+arg_0], rbx
0x180135115  push    rdi
0x180135116  sub     rsp, 20h
0x18013511a  lea     rax, [rcx+40h]
0x18013511e  mov     rbx, rcx
0x180135121  mov     ecx, 10h
0x180135126  test    rax, rax
0x180135129  jz      short loc_180135139
0x18013512b  mov     edx, ecx
0x18013512d  mov     byte ptr [rax], 0
0x180135130  inc     rax
0x180135133  sub     rdx, 1
0x180135137  jnz     short loc_18013512D
0x180135139  lea     rax, [rbx+30h]
0x18013513d  test    rax, rax
0x180135140  jz      short loc_180135151
0x180135142  mov     rdx, rcx
0x180135145  mov     byte ptr [rax], 0
0x180135148  inc     rax
0x18013514b  sub     rdx, 1
0x18013514f  jnz     short loc_180135145
0x180135151  lea     rax, [rbx+50h]
0x180135155  test    rax, rax
0x180135158  jz      short loc_180135166
0x18013515a  mov     byte ptr [rax], 0
0x18013515d  inc     rax
0x180135160  sub     rcx, 1
0x180135164  jnz     short loc_18013515A
0x180135166  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18013516d  call    cs:__imp_InitializeCriticalSection
0x180135174  nop     dword ptr [rax+rax+00h]
0x180135179  xor     r9d, r9d; lpName
0x18013517c  xor     r8d, r8d; bInitialState
0x18013517f  xor     ecx, ecx; lpEventAttributes
0x180135181  lea     edx, [r9+1]; bManualReset
0x180135185  call    cs:__imp_CreateEventW
0x18013518c  nop     dword ptr [rax+rax+00h]
0x180135191  mov     rcx, [rbx+60h]; hObject
0x180135195  mov     rdi, rax
0x180135198  lea     rdx, [rcx-1]
0x18013519c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1801351a0  ja      short loc_1801351AE
0x1801351a2  call    cs:__imp_CloseHandle
0x1801351a9  nop     dword ptr [rax+rax+00h]
0x1801351ae  mov     [rbx+60h], rdi
0x1801351b2  test    rdi, rdi
0x1801351b5  jz      loc_180135274
0x1801351bb  call    cs:__imp_GetLastError
0x1801351c2  nop     dword ptr [rax+rax+00h]
0x1801351c7  cmp     eax, 0B7h
0x1801351cc  jz      loc_180135274
0x1801351d2  xor     r9d, r9d; lpName
0x1801351d5  xor     r8d, r8d; bInitialState
0x1801351d8  xor     edx, edx; bManualReset
0x1801351da  xor     ecx, ecx; lpEventAttributes
0x1801351dc  call    cs:__imp_CreateEventW
0x1801351e3  nop     dword ptr [rax+rax+00h]
0x1801351e8  mov     rcx, [rbx+68h]; hObject
0x1801351ec  mov     rdi, rax
0x1801351ef  lea     rdx, [rcx-1]
0x1801351f3  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1801351f7  ja      short loc_180135205
0x1801351f9  call    cs:__imp_CloseHandle
0x180135200  nop     dword ptr [rax+rax+00h]
0x180135205  mov     [rbx+68h], rdi
0x180135209  test    rdi, rdi
0x18013520c  jz      short loc_180135274
0x18013520e  call    cs:__imp_GetLastError
0x180135215  nop     dword ptr [rax+rax+00h]
0x18013521a  cmp     eax, 0B7h
0x18013521f  jz      short loc_180135274
0x180135221  xor     r9d, r9d; lpName
0x180135224  xor     r8d, r8d; bInitialState
0x180135227  xor     ecx, ecx; lpEventAttributes
0x180135229  lea     edx, [r9+1]; bManualReset
0x18013522d  call    cs:__imp_CreateEventW
0x180135234  nop     dword ptr [rax+rax+00h]
0x180135239  mov     rcx, [rbx+70h]; hObject
0x18013523d  mov     rdi, rax
0x180135240  lea     rdx, [rcx-1]
0x180135244  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180135248  ja      short loc_180135256
0x18013524a  call    cs:__imp_CloseHandle
0x180135251  nop     dword ptr [rax+rax+00h]
0x180135256  mov     [rbx+70h], rdi
0x18013525a  test    rdi, rdi
0x18013525d  jz      short loc_180135274
0x18013525f  xor     ebx, ebx
0x180135261  call    cs:__imp_GetLastError
0x180135268  nop     dword ptr [rax+rax+00h]
0x18013526d  cmp     eax, 0B7h
0x180135272  jnz     short loc_18013528F
0x180135274  call    cs:__imp_GetLastError
0x18013527b  nop     dword ptr [rax+rax+00h]
0x180135280  mov     ebx, eax
0x180135282  test    eax, eax
0x180135284  jle     short loc_18013528F
0x180135286  movzx   ebx, ax
0x180135289  or      ebx, 80070000h
0x18013528f  mov     eax, ebx
0x180135291  mov     rbx, [rsp+28h+arg_0]
0x180135296  add     rsp, 20h
0x18013529a  pop     rdi
0x18013529b  retn
```
