# CSurfaceManager::ResetTokenThread(void)

- ea: `0x18012dd78`
- end: `0x18012de2f`
- name: `?ResetTokenThread@CSurfaceManager@@QEAAJXZ`
- size: `183`
- prototype: `__int64 __fastcall(CSurfaceManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18012f948`
- `0x1801e53d0`

## callees

- `0x180050270`
- `0x18012dd78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18012ddd6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18012ddd6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18012ddc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18012ddc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012dde0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012dde0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012ddb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012ddb4`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18012ddac`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18012ddac`

## pseudocode

```c
__int64 __fastcall CSurfaceManager::ResetTokenThread(CSurfaceManager *this)
{
  signed int v2; // edi
  char *v3; // rcx
  DWORD ThreadId; // ebx
  signed int LastError; // eax

  v2 = 0;
  v3 = (char *)*((_QWORD *)this + 15);
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    ThreadId = GetThreadId(v3);
    if ( GetCurrentThreadId() != ThreadId )
    {
      if ( *((_BYTE *)this + 144) )
      {
        return (unsigned int)-2147467260;
      }
      else
      {
        SetLastError(0);
        if ( !SetEvent(*((HANDLE *)this + 16)) )
        {
          LastError = GetLastError();
          v2 = LastError;
          if ( LastError > 0 )
            v2 = (unsigned __int16)LastError | 0x80070000;
          if ( v2 >= 0 )
            v2 = -2003304445;
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v2, 0x61u, 0);
        }
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18012dd78  mov     [rsp+arg_0], rbx
0x18012dd7d  mov     [rsp+arg_8], rsi
0x18012dd82  push    rdi
0x18012dd83  sub     rsp, 30h
0x18012dd87  mov     rsi, rcx
0x18012dd8a  xor     edi, edi
0x18012dd8c  mov     rcx, [rcx+78h]; Thread
0x18012dd90  lea     rax, [rcx-1]
0x18012dd94  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18012dd98  jbe     short loc_18012DDAC
0x18012dd9a  mov     rbx, [rsp+38h+arg_0]
0x18012dd9f  mov     eax, edi
0x18012dda1  mov     rsi, [rsp+38h+arg_8]
0x18012dda6  add     rsp, 30h
0x18012ddaa  pop     rdi
0x18012ddab  retn
0x18012ddac  call    cs:__imp_GetThreadId
0x18012ddb2  mov     ebx, eax
0x18012ddb4  call    cs:__imp_GetCurrentThreadId
0x18012ddba  cmp     eax, ebx
0x18012ddbc  jz      short loc_18012DD9A
0x18012ddbe  cmp     [rsi+90h], dil
0x18012ddc5  jnz     short loc_18012DE25
0x18012ddc7  xor     ecx, ecx; dwErrCode
0x18012ddc9  call    cs:__imp_SetLastError
0x18012ddcf  mov     rcx, [rsi+80h]; hEvent
0x18012ddd6  call    cs:__imp_SetEvent
0x18012dddc  test    eax, eax
0x18012ddde  jnz     short loc_18012DD9A
0x18012dde0  call    cs:__imp_GetLastError
0x18012dde6  mov     edi, eax
0x18012dde8  test    eax, eax
0x18012ddea  jle     short loc_18012DDF5
0x18012ddec  movzx   edi, ax
0x18012ddef  or      edi, 80070000h
0x18012ddf5  test    edi, edi
0x18012ddf7  mov     [rsp+38h+var_10], 0; void *
0x18012de00  mov     eax, 88980003h
0x18012de05  mov     [rsp+38h+var_18], 61h ; 'a'; unsigned int
0x18012de0d  cmovns  edi, eax
0x18012de10  xor     edx, edx; int *
0x18012de12  mov     r9d, edi; int
0x18012de15  xor     r8d, r8d; unsigned int
0x18012de18  lea     ecx, [rdx+14h]; unsigned int
0x18012de1b  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18012de20  jmp     loc_18012DD9A
0x18012de25  mov     edi, 80004004h
0x18012de2a  jmp     loc_18012DD9A
```
