# Queue::GetMessageW(Err &)

- ea: `0x1007796f`
- end: `0x10077a60`
- name: `?GetMessageW@Queue@@QAEPAVQMsg@@AAVErr@@@Z`
- size: `241`
- prototype: `struct QMsg *__thiscall(LPCRITICAL_SECTION lpCriticalSection, struct Err *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10061460`

## callees

- `0x100610f0`
- `0x10061803`
- `0x1007796f`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10077983`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10077983`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10077993`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10077993`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x10077a34`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x10077a34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10077a26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10077a26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1007798d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1007798d`

## pseudocode

```c
struct QMsg *__thiscall Queue::GetMessageW(struct _RTL_CRITICAL_SECTION *lpCriticalSection, struct Err *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // esi
  _DWORD *v3; // ebx
  DWORD v4; // edi
  unsigned int v5; // edx
  _DWORD *v6; // ecx
  LONG *p_LockCount; // eax
  _DWORD *v8; // edx
  int v9; // eax
  struct Err *v10; // ecx
  DWORD CurrentThreadId; // [esp+10h] [ebp-10h]
  DWORD TickCount; // [esp+14h] [ebp-Ch]
  unsigned int v15; // [esp+18h] [ebp-8h]
  HANDLE OwningThread; // [esp+1Ch] [ebp-4h]

  v2 = lpCriticalSection;
  v3 = 0;
  v4 = 0;
  CurrentThreadId = GetCurrentThreadId();
  while ( 1 )
  {
    EnterCriticalSection(v2);
    TickCount = GetTickCount();
    v5 = 0;
    v6 = 0;
    v15 = 0;
    OwningThread = v2[1].OwningThread;
    if ( OwningThread )
    {
      p_LockCount = &v2[1].LockCount;
      do
      {
        v8 = *(_DWORD **)(*p_LockCount + 4 * v5);
        v9 = v8[3];
        if ( v9 == CurrentThreadId )
        {
          v8[3] = 0;
          OwningThread = v2[1].OwningThread;
          v9 = 0;
        }
        v2 = lpCriticalSection;
        if ( v8[1] <= TickCount )
        {
          v3 = v8;
          Collection::RemoveObject((Collection *)&lpCriticalSection[1].LockCount, v8);
          goto LABEL_16;
        }
        if ( !v9 && (!v6 || (unsigned int)(v6[1] - v8[1]) < 0x80000000) )
          v6 = v8;
        p_LockCount = &lpCriticalSection[1].LockCount;
        v5 = v15 + 1;
        v15 = v5;
      }
      while ( v5 < (unsigned int)OwningThread );
      if ( !v6 )
        goto LABEL_15;
      v4 = v6[1] - TickCount;
      v6[3] = CurrentThreadId;
    }
    else
    {
LABEL_15:
      v4 = -1;
    }
LABEL_16:
    LeaveCriticalSection(v2);
    if ( v3 )
      return (struct QMsg *)v3;
    if ( WaitForSingleObject(v2[1].DebugInfo, v4) == -1 )
      System::ErrGetLastError(v10);
    if ( (*(_BYTE *)a2 & 8) != 0 )
      return 0;
  }
}

```

## disassembly

```asm
0x1007796f  mov     edi, edi
0x10077971  push    ebp
0x10077972  mov     ebp, esp
0x10077974  sub     esp, 14h
0x10077977  push    ebx
0x10077978  push    esi
0x10077979  mov     esi, ecx
0x1007797b  xor     ebx, ebx
0x1007797d  push    edi
0x1007797e  mov     [ebp+lpCriticalSection], esi
0x10077981  xor     edi, edi
0x10077983  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10077989  mov     [ebp+var_10], eax
0x1007798c  push    esi; lpCriticalSection
0x1007798d  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10077993  call    ds:__imp__GetTickCount@0; GetTickCount()
0x10077999  mov     [ebp+var_C], eax
0x1007799c  xor     edx, edx
0x1007799e  mov     eax, [esi+24h]
0x100779a1  xor     ecx, ecx
0x100779a3  mov     [ebp+var_8], edx
0x100779a6  mov     [ebp+var_4], eax
0x100779a9  test    eax, eax
0x100779ab  jz      short loc_10077A22
0x100779ad  lea     eax, [esi+1Ch]
0x100779b0  mov     eax, [eax]
0x100779b2  mov     edx, [eax+edx*4]
0x100779b5  mov     eax, [ebp+var_4]
0x100779b8  mov     [ebp+var_4], eax
0x100779bb  mov     eax, [edx+0Ch]
0x100779be  cmp     eax, [ebp+var_10]
0x100779c1  jnz     short loc_100779D2
0x100779c3  mov     dword ptr [edx+0Ch], 0
0x100779ca  mov     eax, [esi+24h]
0x100779cd  mov     [ebp+var_4], eax
0x100779d0  xor     eax, eax
0x100779d2  mov     esi, [ebp+var_C]
0x100779d5  cmp     [edx+4], esi
0x100779d8  mov     esi, [ebp+lpCriticalSection]
0x100779db  jbe     short loc_10077A15
0x100779dd  test    eax, eax
0x100779df  jnz     short loc_100779F4
0x100779e1  test    ecx, ecx
0x100779e3  jz      short loc_100779F2
0x100779e5  mov     eax, [ecx+4]
0x100779e8  sub     eax, [edx+4]
0x100779eb  cmp     eax, 80000000h
0x100779f0  jnb     short loc_100779F4
0x100779f2  mov     ecx, edx
0x100779f4  mov     edx, [ebp+var_8]
0x100779f7  lea     eax, [esi+1Ch]
0x100779fa  inc     edx
0x100779fb  mov     [ebp+var_8], edx
0x100779fe  cmp     edx, [ebp+var_4]
0x10077a01  jb      short loc_100779B0
0x10077a03  test    ecx, ecx
0x10077a05  jz      short loc_10077A22
0x10077a07  mov     edi, [ecx+4]
0x10077a0a  mov     eax, [ebp+var_10]
0x10077a0d  sub     edi, [ebp+var_C]
0x10077a10  mov     [ecx+0Ch], eax
0x10077a13  jmp     short loc_10077A25
0x10077a15  push    edx; void *
0x10077a16  lea     ecx, [esi+1Ch]; this
0x10077a19  mov     ebx, edx
0x10077a1b  call    ?RemoveObject@Collection@@QAEXPBX@Z; Collection::RemoveObject(void const *)
0x10077a20  jmp     short loc_10077A25
0x10077a22  or      edi, 0FFFFFFFFh
0x10077a25  push    esi; lpCriticalSection
0x10077a26  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10077a2c  test    ebx, ebx
0x10077a2e  jnz     short loc_10077A57
0x10077a30  push    edi; dwMilliseconds
0x10077a31  push    dword ptr [esi+18h]; hHandle
0x10077a34  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x10077a3a  cmp     eax, 0FFFFFFFFh
0x10077a3d  jnz     short loc_10077A47
0x10077a3f  push    [ebp+arg_0]
0x10077a42  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x10077a47  mov     eax, [ebp+arg_0]
0x10077a4a  test    byte ptr [eax], 8
0x10077a4d  jz      loc_1007798C
0x10077a53  xor     eax, eax
0x10077a55  jmp     short loc_10077A59
0x10077a57  mov     eax, ebx
0x10077a59  pop     edi
0x10077a5a  pop     esi
0x10077a5b  pop     ebx
0x10077a5c  leave
0x10077a5d  retn    4
```
