# TaskScheduler::LockWriter(void *)

- ea: `0x18000b4d0`
- end: `0x18000b632`
- name: `?LockWriter@TaskScheduler@@QEAA_NPEAX@Z`
- size: `354`
- prototype: `bool __fastcall(TaskScheduler *__hidden this, void *)`
- caller_count: `41`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800094cc`
- `0x180009d48`
- `0x18000a24c`
- `0x18000b0b0`
- `0x18000b640`
- `0x18002a660`
- `0x18002e8c0`
- `0x180030bb0`
- `0x1800361b8`
- `0x180047114`
- `0x180047dec`
- `0x180048804`
- `0x1800490d0`
- `0x18004926c`
- `0x180059bd4`
- `0x18005f580`
- `0x1800606e4`
- `0x180068880`
- `0x180069668`
- `0x180069b90`
- `0x180075d40`
- `0x180077d24`
- `0x180078060`
- `0x180078934`
- `0x18007cb80`
- `0x18007d400`
- `0x18007f434`
- `0x18008030c`
- `0x18008385c`
- `0x18008a480`
- `0x180095384`
- `0x18009a840`
- `0x18009aae4`
- `0x1800aea50`
- `0x1800aeb50`
- `0x1800af6e0`
- `0x1800afd10`
- `0x1800d2310`
- `0x1800d2440`
- `0x1800d26d0`
- `0x1800d27d0`

## callees

- `0x18000b4d0`
- `0x18009d024`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b53a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b5ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b53a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b5ac`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b568`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b568`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b5a6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b5a6`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000b527`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000b527`

## pseudocode

```c
char __fastcall TaskScheduler::LockWriter(TaskScheduler *this, void *a2)
{
  void *v4; // rax
  DWORD v5; // eax
  EVENT_LOG *v6; // rcx
  _QWORD *Value; // rax
  __int64 v9; // rdx
  HANDLE Handles[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
  if ( !a2 )
  {
    Value = TlsGetValue(*((_DWORD *)this + 13));
    if ( Value )
      a2 = (void *)Value[6];
    else
      a2 = 0;
  }
  v4 = (void *)*((_QWORD *)this + 5);
  if ( !a2 )
  {
    WaitForSingleObject(*((HANDLE *)this + 5), 0xFFFFFFFF);
    *((_DWORD *)this + 14) = GetCurrentThreadId();
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      return 0;
    v9 = 31;
    goto LABEL_18;
  }
  Handles[0] = a2;
  Handles[1] = v4;
  v5 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
  if ( v5 )
  {
    if ( v5 != 1 )
      return 0;
    *((_DWORD *)this + 14) = GetCurrentThreadId();
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      return 0;
    v9 = 33;
LABEL_18:
    WPP_SF_(*((_QWORD *)v6 + 2), v9, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
  return 1;
}

```

## disassembly

```asm
0x18000b4d0  mov     [rsp+arg_0], rbx
0x18000b4d5  mov     [rsp+arg_8], rsi
0x18000b4da  push    rdi
0x18000b4db  sub     rsp, 30h
0x18000b4df  mov     rbx, rdx
0x18000b4e2  mov     rdi, rcx
0x18000b4e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4ec  lea     rsi, WPP_GLOBAL_Control
0x18000b4f3  cmp     rcx, rsi
0x18000b4f6  jnz     short loc_18000B577
0x18000b4f8  test    rbx, rbx
0x18000b4fb  jz      short loc_18000B565
0x18000b4fd  mov     rax, [rdi+28h]
0x18000b501  test    rbx, rbx
0x18000b504  jz      loc_18000B59E
0x18000b50a  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x18000b510  mov     [rsp+38h+Handles], rbx
0x18000b515  xor     r8d, r8d; bWaitAll
0x18000b518  mov     [rsp+38h+var_10], rax
0x18000b51d  lea     rdx, [rsp+38h+Handles]; lpHandles
0x18000b522  mov     ecx, 2; nCount
0x18000b527  call    cs:__imp_WaitForMultipleObjects
0x18000b52d  test    eax, eax
0x18000b52f  jz      loc_18000B601
0x18000b535  cmp     eax, 1
0x18000b538  jnz     short loc_18000B553
0x18000b53a  call    cs:__imp_GetCurrentThreadId
0x18000b540  mov     [rdi+38h], eax
0x18000b543  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b54a  cmp     rcx, rsi
0x18000b54d  jnz     loc_18000B5DA
0x18000b553  xor     al, al
0x18000b555  mov     rbx, [rsp+38h+arg_0]
0x18000b55a  mov     rsi, [rsp+38h+arg_8]
0x18000b55f  add     rsp, 30h
0x18000b563  pop     rdi
0x18000b564  retn
0x18000b565  mov     ecx, [rdi+34h]; dwTlsIndex
0x18000b568  call    cs:__imp_TlsGetValue
0x18000b56e  test    rax, rax
0x18000b571  jnz     short loc_18000B5D1
0x18000b573  xor     ebx, ebx
0x18000b575  jmp     short loc_18000B4FD
0x18000b577  test    dword ptr [rcx+1Ch], 100h
0x18000b57e  jz      loc_18000B4F8
0x18000b584  mov     rcx, [rcx+10h]
0x18000b588  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x18000b58f  mov     edx, 1Eh
0x18000b594  call    WPP_SF_
0x18000b599  jmp     loc_18000B4F8
0x18000b59e  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000b5a3  mov     rcx, rax; hHandle
0x18000b5a6  call    cs:__imp_WaitForSingleObject
0x18000b5ac  call    cs:__imp_GetCurrentThreadId
0x18000b5b2  mov     [rdi+38h], eax
0x18000b5b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5bc  cmp     rcx, rsi
0x18000b5bf  jz      short loc_18000B553
0x18000b5c1  test    dword ptr [rcx+1Ch], 100h
0x18000b5c8  jz      short loc_18000B553
0x18000b5ca  mov     edx, 1Fh
0x18000b5cf  jmp     short loc_18000B5EC
0x18000b5d1  mov     rbx, [rax+30h]
0x18000b5d5  jmp     loc_18000B4FD
0x18000b5da  test    dword ptr [rcx+1Ch], 100h
0x18000b5e1  jz      loc_18000B553
0x18000b5e7  mov     edx, 21h ; '!'
0x18000b5ec  mov     rcx, [rcx+10h]
0x18000b5f0  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x18000b5f7  call    WPP_SF_
0x18000b5fc  jmp     loc_18000B553
0x18000b601  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b608  cmp     rcx, rsi
0x18000b60b  jz      short loc_18000B62B
0x18000b60d  test    dword ptr [rcx+1Ch], 100h
0x18000b614  jz      short loc_18000B62B
0x18000b616  mov     rcx, [rcx+10h]
0x18000b61a  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x18000b621  mov     edx, 20h ; ' '
0x18000b626  call    WPP_SF_
0x18000b62b  mov     al, 1
0x18000b62d  jmp     loc_18000B555
```
