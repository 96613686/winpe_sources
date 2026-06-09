# Queue::GetMessageW(Err &)

- ea: `0x10077aff`
- end: `0x10077bf0`
- name: `?GetMessageW@Queue@@QAEPAVQMsg@@AAVErr@@@Z`
- size: `241`
- prototype: `struct QMsg *__thiscall(LPCRITICAL_SECTION lpCriticalSection, struct Err *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x100615f0`

## callees

- `0x10061284`
- `0x10061993`
- `0x10077aff`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10077b13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10077b13`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10077b23`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10077b23`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x10077bc4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x10077bc4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10077bb6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10077bb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10077b1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10077b1d`

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
0x10077aff  mov     edi, edi
0x10077b01  push    ebp
0x10077b02  mov     ebp, esp
0x10077b04  sub     esp, 14h
0x10077b07  push    ebx
0x10077b08  push    esi
0x10077b09  mov     esi, ecx
0x10077b0b  xor     ebx, ebx
0x10077b0d  push    edi
0x10077b0e  mov     [ebp+lpCriticalSection], esi
0x10077b11  xor     edi, edi
0x10077b13  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10077b19  mov     [ebp+var_10], eax
0x10077b1c  push    esi; lpCriticalSection
0x10077b1d  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10077b23  call    ds:__imp__GetTickCount@0; GetTickCount()
0x10077b29  mov     [ebp+var_C], eax
0x10077b2c  xor     edx, edx
0x10077b2e  mov     eax, [esi+24h]
0x10077b31  xor     ecx, ecx
0x10077b33  mov     [ebp+var_8], edx
0x10077b36  mov     [ebp+var_4], eax
0x10077b39  test    eax, eax
0x10077b3b  jz      short loc_10077BB2
0x10077b3d  lea     eax, [esi+1Ch]
0x10077b40  mov     eax, [eax]
0x10077b42  mov     edx, [eax+edx*4]
0x10077b45  mov     eax, [ebp+var_4]
0x10077b48  mov     [ebp+var_4], eax
0x10077b4b  mov     eax, [edx+0Ch]
0x10077b4e  cmp     eax, [ebp+var_10]
0x10077b51  jnz     short loc_10077B62
0x10077b53  mov     dword ptr [edx+0Ch], 0
0x10077b5a  mov     eax, [esi+24h]
0x10077b5d  mov     [ebp+var_4], eax
0x10077b60  xor     eax, eax
0x10077b62  mov     esi, [ebp+var_C]
0x10077b65  cmp     [edx+4], esi
0x10077b68  mov     esi, [ebp+lpCriticalSection]
0x10077b6b  jbe     short loc_10077BA5
0x10077b6d  test    eax, eax
0x10077b6f  jnz     short loc_10077B84
0x10077b71  test    ecx, ecx
0x10077b73  jz      short loc_10077B82
0x10077b75  mov     eax, [ecx+4]
0x10077b78  sub     eax, [edx+4]
0x10077b7b  cmp     eax, 80000000h
0x10077b80  jnb     short loc_10077B84
0x10077b82  mov     ecx, edx
0x10077b84  mov     edx, [ebp+var_8]
0x10077b87  lea     eax, [esi+1Ch]
0x10077b8a  inc     edx
0x10077b8b  mov     [ebp+var_8], edx
0x10077b8e  cmp     edx, [ebp+var_4]
0x10077b91  jb      short loc_10077B40
0x10077b93  test    ecx, ecx
0x10077b95  jz      short loc_10077BB2
0x10077b97  mov     edi, [ecx+4]
0x10077b9a  mov     eax, [ebp+var_10]
0x10077b9d  sub     edi, [ebp+var_C]
0x10077ba0  mov     [ecx+0Ch], eax
0x10077ba3  jmp     short loc_10077BB5
0x10077ba5  push    edx; void *
0x10077ba6  lea     ecx, [esi+1Ch]; this
0x10077ba9  mov     ebx, edx
0x10077bab  call    ?RemoveObject@Collection@@QAEXPBX@Z; Collection::RemoveObject(void const *)
0x10077bb0  jmp     short loc_10077BB5
0x10077bb2  or      edi, 0FFFFFFFFh
0x10077bb5  push    esi; lpCriticalSection
0x10077bb6  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10077bbc  test    ebx, ebx
0x10077bbe  jnz     short loc_10077BE7
0x10077bc0  push    edi; dwMilliseconds
0x10077bc1  push    dword ptr [esi+18h]; hHandle
0x10077bc4  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x10077bca  cmp     eax, 0FFFFFFFFh
0x10077bcd  jnz     short loc_10077BD7
0x10077bcf  push    [ebp+arg_0]
0x10077bd2  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x10077bd7  mov     eax, [ebp+arg_0]
0x10077bda  test    byte ptr [eax], 8
0x10077bdd  jz      loc_10077B1C
0x10077be3  xor     eax, eax
0x10077be5  jmp     short loc_10077BE9
0x10077be7  mov     eax, ebx
0x10077be9  pop     edi
0x10077bea  pop     esi
0x10077beb  pop     ebx
0x10077bec  leave
0x10077bed  retn    4
```
