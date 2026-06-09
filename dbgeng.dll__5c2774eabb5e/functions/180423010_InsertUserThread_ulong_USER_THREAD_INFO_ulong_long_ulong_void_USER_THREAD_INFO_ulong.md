# InsertUserThread(ulong,_USER_THREAD_INFO *,ulong,long,ulong,void *,_USER_THREAD_INFO *,ulong)

- ea: `0x180423010`
- end: `0x180423162`
- name: `?InsertUserThread@@YAJKPEAU_USER_THREAD_INFO@@KJKPEAX0K@Z`
- size: `338`
- prototype: `__int64 __fastcall(unsigned int, struct _USER_THREAD_INFO *, unsigned int, int, unsigned int, HANDLE hThread, struct _USER_THREAD_INFO *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180423eec`
- `0x180426884`

## callees

- `0x180423010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18042305a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180423071`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18042305a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180423071`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18042310e`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18042310e`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x180423049`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x180423049`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18042308f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18042311f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180423142`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18042308f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18042311f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180423142`

## pseudocode

```c
__int64 __fastcall InsertUserThread(
        char a1,
        struct _USER_THREAD_INFO *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        HANDLE hThread,
        struct _USER_THREAD_INFO *a7,
        unsigned int a8)
{
  __int64 v8; // rbx
  unsigned int v9; // r14d
  unsigned int v10; // edi
  int v11; // esi
  signed int LastError; // eax
  __int64 v14; // rax
  unsigned int i; // ecx
  void *v17; // rcx
  void *v18; // rcx

  v8 = a3;
  v9 = 1;
  v10 = a4;
  v11 = a1 & 1;
  if ( a4 )
    goto LABEL_17;
  if ( (a1 & 1) != 0 || SuspendThread(hThread) != -1 )
    goto LABEL_9;
  if ( GetLastError() )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v10 = -2147467259;
  }
  CloseHandle(hThread);
  if ( v10 )
  {
LABEL_17:
    if ( (_DWORD)v8 )
    {
      if ( v11 )
      {
        do
        {
          LODWORD(v8) = v8 - 1;
          v18 = (void *)*((_QWORD *)a2 + 2 * (unsigned int)v8);
          if ( v18 )
            CloseHandle(v18);
        }
        while ( (_DWORD)v8 );
      }
      else
      {
        do
        {
          LODWORD(v8) = v8 - 1;
          v17 = (void *)*((_QWORD *)a2 + 2 * (unsigned int)v8);
          if ( v17 )
          {
            ResumeThread(v17);
            CloseHandle(*((HANDLE *)a2 + 2 * (unsigned int)v8));
          }
        }
        while ( (_DWORD)v8 );
      }
    }
    return v10;
  }
  else
  {
LABEL_9:
    v14 = 2 * v8;
    *((_QWORD *)a2 + v14) = hThread;
    *((_QWORD *)a2 + v14 + 1) = a5;
    if ( a7 )
    {
      for ( i = 0; i < a8; ++i )
      {
        if ( *((_DWORD *)a7 + 4 * i + 2) == a5 )
          return 0;
      }
      return v9;
    }
    else
    {
      return 0;
    }
  }
}

```

## disassembly

```asm
0x180423010  push    rbx
0x180423012  push    rbp
0x180423013  push    rsi
0x180423014  push    rdi
0x180423015  push    r14
0x180423017  push    r15
0x180423019  sub     rsp, 28h
0x18042301d  mov     esi, ecx
0x18042301f  mov     ebx, r8d
0x180423022  mov     r14d, 1
0x180423028  mov     edi, r9d
0x18042302b  and     esi, r14d
0x18042302e  mov     rbp, rdx
0x180423031  test    r9d, r9d
0x180423034  jnz     loc_1804230F5
0x18042303a  mov     r15, [rsp+58h+hThread]
0x180423042  test    esi, esi
0x180423044  jnz     short loc_18042309F
0x180423046  mov     rcx, r15; hThread
0x180423049  call    cs:__imp_SuspendThread
0x180423050  nop     dword ptr [rax+rax+00h]
0x180423055  cmp     eax, 0FFFFFFFFh
0x180423058  jnz     short loc_18042309F
0x18042305a  call    cs:__imp_GetLastError
0x180423061  nop     dword ptr [rax+rax+00h]
0x180423066  test    eax, eax
0x180423068  jnz     short loc_180423071
0x18042306a  mov     edi, 80004005h
0x18042306f  jmp     short loc_18042308C
0x180423071  call    cs:__imp_GetLastError
0x180423078  nop     dword ptr [rax+rax+00h]
0x18042307d  mov     edi, eax
0x18042307f  test    eax, eax
0x180423081  jle     short loc_18042308C
0x180423083  movzx   edi, ax
0x180423086  or      edi, 80070000h
0x18042308c  mov     rcx, r15; hObject
0x18042308f  call    cs:__imp_CloseHandle
0x180423096  nop     dword ptr [rax+rax+00h]
0x18042309b  test    edi, edi
0x18042309d  jnz     short loc_1804230F5
0x18042309f  mov     r8, [rsp+58h+arg_30]
0x1804230a7  mov     rax, rbx
0x1804230aa  mov     edx, [rsp+58h+arg_20]
0x1804230b1  add     rax, rax
0x1804230b4  mov     [rbp+rax*8+0], r15
0x1804230b9  mov     [rbp+rax*8+8], edx
0x1804230bd  mov     dword ptr [rbp+rax*8+0Ch], 0
0x1804230c5  test    r8, r8
0x1804230c8  jnz     short loc_1804230D1
0x1804230ca  xor     eax, eax
0x1804230cc  jmp     loc_180423154
0x1804230d1  xor     ecx, ecx
0x1804230d3  cmp     ecx, [rsp+58h+arg_38]
0x1804230da  jnb     short loc_1804230F0
0x1804230dc  mov     eax, ecx
0x1804230de  add     rax, rax
0x1804230e1  cmp     [r8+rax*8+8], edx
0x1804230e6  jz      short loc_1804230ED
0x1804230e8  add     ecx, r14d
0x1804230eb  jmp     short loc_1804230D3
0x1804230ed  xor     r14d, r14d
0x1804230f0  mov     eax, r14d
0x1804230f3  jmp     short loc_180423154
0x1804230f5  test    ebx, ebx
0x1804230f7  jz      short loc_180423152
0x1804230f9  test    esi, esi
0x1804230fb  jnz     short loc_180423131
0x1804230fd  dec     ebx
0x1804230ff  mov     esi, ebx
0x180423101  add     rsi, rsi
0x180423104  mov     rcx, [rbp+rsi*8+0]; hThread
0x180423109  test    rcx, rcx
0x18042310c  jz      short loc_18042312B
0x18042310e  call    cs:__imp_ResumeThread
0x180423115  nop     dword ptr [rax+rax+00h]
0x18042311a  mov     rcx, [rbp+rsi*8+0]; hObject
0x18042311f  call    cs:__imp_CloseHandle
0x180423126  nop     dword ptr [rax+rax+00h]
0x18042312b  test    ebx, ebx
0x18042312d  jnz     short loc_1804230FD
0x18042312f  jmp     short loc_180423152
0x180423131  dec     ebx
0x180423133  mov     eax, ebx
0x180423135  add     rax, rax
0x180423138  mov     rcx, [rbp+rax*8+0]; hObject
0x18042313d  test    rcx, rcx
0x180423140  jz      short loc_18042314E
0x180423142  call    cs:__imp_CloseHandle
0x180423149  nop     dword ptr [rax+rax+00h]
0x18042314e  test    ebx, ebx
0x180423150  jnz     short loc_180423131
0x180423152  mov     eax, edi
0x180423154  add     rsp, 28h
0x180423158  pop     r15
0x18042315a  pop     r14
0x18042315c  pop     rdi
0x18042315d  pop     rsi
0x18042315e  pop     rbp
0x18042315f  pop     rbx
0x180423160  retn
```
