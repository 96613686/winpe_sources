# HoldWriterLock::HoldWriterLock(TaskScheduler *)

- ea: `0x180063b5c`
- end: `0x180063c91`
- name: `??0HoldWriterLock@@QEAA@PEAVTaskScheduler@@@Z`
- size: `309`
- prototype: `HoldWriterLock *__fastcall(HoldWriterLock *__hidden this, struct TaskScheduler *)`
- caller_count: `13`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800639f0`
- `0x180083e70`
- `0x180084a80`
- `0x180087660`
- `0x18008d4c0`
- `0x18008d6e0`
- `0x1800950e4`
- `0x1800aec60`
- `0x1800aee00`
- `0x1800aeed0`
- `0x1800af0d0`
- `0x1800af580`
- `0x1800b0bac`

## callees

- `0x180063b5c`
- `0x18009d024`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063b76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063be6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063c30`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063b76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063be6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063c30`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180063ba1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180063ba1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180063c2a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180063c2a`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180063bd3`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180063bd3`

## pseudocode

```c
HoldWriterLock *__fastcall HoldWriterLock::HoldWriterLock(HoldWriterLock *this, struct TaskScheduler *a2)
{
  int v3; // ebx
  __int64 v4; // rbx
  _QWORD *Value; // rax
  DWORD v6; // eax
  EVENT_LOG *v7; // rcx
  __int64 v9; // rdx
  HANDLE Handles[7]; // [rsp+20h] [rbp-38h] BYREF

  *(_QWORD *)this = a2;
  *((_DWORD *)this + 2) = 0;
  v3 = *((_DWORD *)a2 + 14);
  if ( v3 != GetCurrentThreadId() )
  {
    ++*((_DWORD *)this + 2);
    v4 = *(_QWORD *)this;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
    Value = TlsGetValue(*(_DWORD *)(v4 + 52));
    if ( Value )
      Value = (_QWORD *)Value[6];
    if ( Value )
    {
      Handles[1] = *(HANDLE *)(v4 + 40);
      Handles[0] = Value;
      v6 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
      if ( v6 )
      {
        if ( v6 == 1 )
        {
          *(_DWORD *)(v4 + 56) = GetCurrentThreadId();
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            v9 = 33;
            goto LABEL_20;
          }
        }
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          v9 = 32;
          goto LABEL_20;
        }
      }
    }
    else
    {
      WaitForSingleObject(*(HANDLE *)(v4 + 40), 0xFFFFFFFF);
      *(_DWORD *)(v4 + 56) = GetCurrentThreadId();
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        v9 = 31;
LABEL_20:
        WPP_SF_(*((_QWORD *)v7 + 2), v9, &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x180063b5c  push    rbx
0x180063b5e  push    rsi
0x180063b5f  push    rdi
0x180063b60  push    r14
0x180063b62  sub     rsp, 38h
0x180063b66  mov     [rcx], rdx
0x180063b69  mov     rdi, rcx
0x180063b6c  mov     dword ptr [rcx+8], 0
0x180063b73  mov     ebx, [rdx+38h]
0x180063b76  call    cs:__imp_GetCurrentThreadId
0x180063b7c  cmp     ebx, eax
0x180063b7e  jz      short loc_180063BFB
0x180063b80  inc     dword ptr [rdi+8]
0x180063b83  mov     rbx, [rdi]
0x180063b86  mov     rcx, cs:WPP_GLOBAL_Control
0x180063b8d  lea     r14, WPP_GLOBAL_Control
0x180063b94  mov     esi, 100h
0x180063b99  cmp     rcx, r14
0x180063b9c  jnz     short loc_180063C08
0x180063b9e  mov     ecx, [rbx+34h]; dwTlsIndex
0x180063ba1  call    cs:__imp_TlsGetValue
0x180063ba7  test    rax, rax
0x180063baa  jnz     loc_180063C51
0x180063bb0  mov     rcx, [rbx+28h]; hHandle
0x180063bb4  test    rax, rax
0x180063bb7  jz      short loc_180063C27
0x180063bb9  xor     r8d, r8d; bWaitAll
0x180063bbc  mov     [rsp+58h+var_30], rcx
0x180063bc1  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180063bc5  mov     [rsp+58h+Handles], rax
0x180063bca  lea     rdx, [rsp+58h+Handles]; lpHandles
0x180063bcf  lea     ecx, [r8+2]; nCount
0x180063bd3  call    cs:__imp_WaitForMultipleObjects
0x180063bd9  test    eax, eax
0x180063bdb  jz      loc_180063C66
0x180063be1  cmp     eax, 1
0x180063be4  jnz     short loc_180063BFB
0x180063be6  call    cs:__imp_GetCurrentThreadId
0x180063bec  mov     [rbx+38h], eax
0x180063bef  mov     rcx, cs:WPP_GLOBAL_Control
0x180063bf6  cmp     rcx, r14
0x180063bf9  jnz     short loc_180063C5A
0x180063bfb  mov     rax, rdi
0x180063bfe  add     rsp, 38h
0x180063c02  pop     r14
0x180063c04  pop     rdi
0x180063c05  pop     rsi
0x180063c06  pop     rbx
0x180063c07  retn
0x180063c08  test    [rcx+1Ch], esi
0x180063c0b  jz      short loc_180063B9E
0x180063c0d  mov     rcx, [rcx+10h]
0x180063c11  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x180063c18  mov     edx, 1Eh
0x180063c1d  call    WPP_SF_
0x180063c22  jmp     loc_180063B9E
0x180063c27  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180063c2a  call    cs:__imp_WaitForSingleObject
0x180063c30  call    cs:__imp_GetCurrentThreadId
0x180063c36  mov     [rbx+38h], eax
0x180063c39  mov     rcx, cs:WPP_GLOBAL_Control
0x180063c40  cmp     rcx, r14
0x180063c43  jz      short loc_180063BFB
0x180063c45  test    [rcx+1Ch], esi
0x180063c48  jz      short loc_180063BFB
0x180063c4a  mov     edx, 1Fh
0x180063c4f  jmp     short loc_180063C7C
0x180063c51  mov     rax, [rax+30h]
0x180063c55  jmp     loc_180063BB0
0x180063c5a  test    [rcx+1Ch], esi
0x180063c5d  jz      short loc_180063BFB
0x180063c5f  mov     edx, 21h ; '!'
0x180063c64  jmp     short loc_180063C7C
0x180063c66  mov     rcx, cs:WPP_GLOBAL_Control
0x180063c6d  cmp     rcx, r14
0x180063c70  jz      short loc_180063BFB
0x180063c72  test    [rcx+1Ch], esi
0x180063c75  jz      short loc_180063BFB
0x180063c77  mov     edx, 20h ; ' '
0x180063c7c  mov     rcx, [rcx+10h]
0x180063c80  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x180063c87  call    WPP_SF_
0x180063c8c  jmp     loc_180063BFB
```
