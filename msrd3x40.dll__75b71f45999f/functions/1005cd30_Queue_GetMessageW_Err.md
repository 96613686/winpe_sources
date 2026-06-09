# Queue::GetMessageW(Err &)

- ea: `0x1005cd30`
- end: `0x1005ce57`
- name: `?GetMessageW@Queue@@QAEPAVQMsg@@AAVErr@@@Z`
- size: `295`
- prototype: `struct QMsg *__thiscall(LPCRITICAL_SECTION lpCriticalSection, struct Err *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1004f3b0`

## callees

- `0x1004eda0`
- `0x1005cd30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1005cd58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1005cd58`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1005ce2d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1005ce2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1005ce1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1005ce1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1005cd4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1005cd4e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1005cd5e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1005cd5e`

## pseudocode

```c
struct QMsg *__thiscall Queue::GetMessageW(LPCRITICAL_SECTION lpCriticalSection, struct Err *a2)
{
  LPCRITICAL_SECTION v2; // esi
  DWORD TickCount; // eax
  HANDLE OwningThread; // ebx
  int v5; // edx
  unsigned int v6; // edi
  int v7; // ecx
  int v8; // eax
  DWORD v9; // ebx
  HANDLE v10; // edx
  unsigned int v11; // eax
  _DWORD *v12; // edx
  char *v13; // ecx
  char *v14; // ecx
  struct QMsg *result; // eax
  struct Err *v16; // ecx
  struct QMsg *v18; // [esp+14h] [ebp-14h]
  LONG LockCount; // [esp+18h] [ebp-10h]
  DWORD CurrentThreadId; // [esp+1Ch] [ebp-Ch]
  DWORD v21; // [esp+20h] [ebp-8h]
  int v22; // [esp+24h] [ebp-4h]

  v2 = lpCriticalSection;
  v18 = 0;
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  while ( 1 )
  {
    EnterCriticalSection(v2);
    TickCount = GetTickCount();
    OwningThread = v2[1].OwningThread;
    v5 = 0;
    v6 = 0;
    v21 = TickCount;
    if ( OwningThread )
    {
      do
      {
        LockCount = v2[1].LockCount;
        v7 = *(_DWORD *)(LockCount + 4 * v6);
        v8 = *(_DWORD *)(v7 + 12);
        if ( v8 == CurrentThreadId )
        {
          *(_DWORD *)(v7 + 12) = 0;
          v8 = 0;
          OwningThread = v2[1].OwningThread;
          LockCount = v2[1].LockCount;
        }
        v2 = lpCriticalSection;
        if ( *(_DWORD *)(v7 + 4) <= v21 )
        {
          v10 = lpCriticalSection[1].OwningThread;
          v18 = (struct QMsg *)v7;
          if ( v10 )
          {
            *(_DWORD *)(LockCount + 4 * (_DWORD)v10) = v7;
            v11 = 0;
            v12 = (_DWORD *)lpCriticalSection[1].LockCount;
            if ( *v12 != v7 )
            {
              do
                ++v11;
              while ( v12[v11] != v7 );
            }
            v13 = (char *)lpCriticalSection[1].OwningThread;
            v9 = v22;
            if ( v11 < (unsigned int)v13 )
            {
              v14 = v13 - 1;
              lpCriticalSection[1].OwningThread = v14;
              v12[v11] = v12[(_DWORD)v14];
            }
          }
          else
          {
            v9 = v22;
          }
          goto LABEL_20;
        }
        if ( !v8 && (!v5 || (unsigned int)(*(_DWORD *)(v5 + 4) - *(_DWORD *)(v7 + 4)) < 0x80000000) )
          v5 = v7;
        ++v6;
      }
      while ( v6 < (unsigned int)OwningThread );
      if ( !v5 )
        goto LABEL_18;
      v9 = *(_DWORD *)(v5 + 4) - v21;
      v22 = v9;
      *(_DWORD *)(v5 + 12) = CurrentThreadId;
    }
    else
    {
LABEL_18:
      v9 = -1;
      v22 = -1;
    }
LABEL_20:
    LeaveCriticalSection(v2);
    result = v18;
    if ( v18 )
      return result;
    if ( WaitForSingleObject(v2[1].DebugInfo, v9) == -1 )
      System::ErrGetLastError(v16);
    if ( (*(_BYTE *)a2 & 8) != 0 )
      return 0;
  }
}

```

## disassembly

```asm
0x1005cd30  mov     edi, edi
0x1005cd32  push    ebp
0x1005cd33  mov     ebp, esp
0x1005cd35  sub     esp, 1Ch
0x1005cd38  push    ebx
0x1005cd39  push    esi
0x1005cd3a  mov     esi, ecx
0x1005cd3c  mov     [ebp+var_14], 0
0x1005cd43  push    edi
0x1005cd44  mov     [ebp+lpCriticalSection], esi
0x1005cd47  mov     [ebp+var_4], 0
0x1005cd4e  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1005cd54  mov     [ebp+var_C], eax
0x1005cd57  push    esi; lpCriticalSection
0x1005cd58  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1005cd5e  call    ds:__imp__GetTickCount@0; GetTickCount()
0x1005cd64  mov     ebx, [esi+24h]
0x1005cd67  xor     edx, edx
0x1005cd69  xor     edi, edi
0x1005cd6b  mov     [ebp+var_8], eax
0x1005cd6e  test    ebx, ebx
0x1005cd70  jz      loc_1005CE10
0x1005cd76  mov     eax, [esi+1Ch]
0x1005cd79  mov     [ebp+var_10], eax
0x1005cd7c  mov     ecx, [eax+edi*4]
0x1005cd7f  mov     [ebp+var_18], ecx
0x1005cd82  mov     eax, [ecx+0Ch]
0x1005cd85  cmp     eax, [ebp+var_C]
0x1005cd88  jnz     short loc_1005CD9F
0x1005cd8a  mov     dword ptr [ecx+0Ch], 0
0x1005cd91  xor     eax, eax
0x1005cd93  mov     ecx, [esi+1Ch]
0x1005cd96  mov     ebx, [esi+24h]
0x1005cd99  mov     [ebp+var_10], ecx
0x1005cd9c  mov     ecx, [ebp+var_18]
0x1005cd9f  mov     esi, [ebp+var_8]
0x1005cda2  cmp     [ecx+4], esi
0x1005cda5  mov     esi, [ebp+lpCriticalSection]
0x1005cda8  jbe     short loc_1005CDDB
0x1005cdaa  test    eax, eax
0x1005cdac  jnz     short loc_1005CDC1
0x1005cdae  test    edx, edx
0x1005cdb0  jz      short loc_1005CDBF
0x1005cdb2  mov     eax, [edx+4]
0x1005cdb5  sub     eax, [ecx+4]
0x1005cdb8  cmp     eax, 80000000h
0x1005cdbd  jnb     short loc_1005CDC1
0x1005cdbf  mov     edx, ecx
0x1005cdc1  inc     edi
0x1005cdc2  cmp     edi, ebx
0x1005cdc4  jb      short loc_1005CD76
0x1005cdc6  test    edx, edx
0x1005cdc8  jz      short loc_1005CE10
0x1005cdca  mov     ebx, [edx+4]
0x1005cdcd  sub     ebx, [ebp+var_8]
0x1005cdd0  mov     eax, [ebp+var_C]
0x1005cdd3  mov     [ebp+var_4], ebx
0x1005cdd6  mov     [edx+0Ch], eax
0x1005cdd9  jmp     short loc_1005CE1B
0x1005cddb  mov     edx, [esi+24h]
0x1005cdde  mov     [ebp+var_14], ecx
0x1005cde1  test    edx, edx
0x1005cde3  jz      short loc_1005CE18
0x1005cde5  mov     eax, [ebp+var_10]
0x1005cde8  mov     [eax+edx*4], ecx
0x1005cdeb  xor     eax, eax
0x1005cded  mov     edx, [esi+1Ch]
0x1005cdf0  cmp     [edx], ecx
0x1005cdf2  jz      short loc_1005CDFA
0x1005cdf4  inc     eax
0x1005cdf5  cmp     [edx+eax*4], ecx
0x1005cdf8  jnz     short loc_1005CDF4
0x1005cdfa  mov     ecx, [esi+24h]
0x1005cdfd  mov     ebx, [ebp+var_4]
0x1005ce00  cmp     eax, ecx
0x1005ce02  jnb     short loc_1005CE1B
0x1005ce04  dec     ecx
0x1005ce05  mov     [esi+24h], ecx
0x1005ce08  mov     ecx, [edx+ecx*4]
0x1005ce0b  mov     [edx+eax*4], ecx
0x1005ce0e  jmp     short loc_1005CE1B
0x1005ce10  or      ebx, 0FFFFFFFFh
0x1005ce13  mov     [ebp+var_4], ebx
0x1005ce16  jmp     short loc_1005CE1B
0x1005ce18  mov     ebx, [ebp+var_4]
0x1005ce1b  push    esi; lpCriticalSection
0x1005ce1c  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1005ce22  mov     eax, [ebp+var_14]
0x1005ce25  test    eax, eax
0x1005ce27  jnz     short loc_1005CE4E
0x1005ce29  push    ebx; dwMilliseconds
0x1005ce2a  push    dword ptr [esi+18h]; hHandle
0x1005ce2d  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x1005ce33  cmp     eax, 0FFFFFFFFh
0x1005ce36  jnz     short loc_1005CE40
0x1005ce38  push    [ebp+arg_0]
0x1005ce3b  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x1005ce40  mov     eax, [ebp+arg_0]
0x1005ce43  test    byte ptr [eax], 8
0x1005ce46  jz      loc_1005CD57
0x1005ce4c  xor     eax, eax
0x1005ce4e  pop     edi
0x1005ce4f  pop     esi
0x1005ce50  pop     ebx
0x1005ce51  mov     esp, ebp
0x1005ce53  pop     ebp
0x1005ce54  retn    4
```
