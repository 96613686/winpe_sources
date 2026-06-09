# DpspInstanceCompleteNotification

- ea: `0x180006360`
- end: `0x1800064e1`
- name: `DpspInstanceCompleteNotification`
- size: `385`
- prototype: `__int64 __fastcall(struct INSTANCEINFO *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012670`

## callees

- `0x1800057b0`
- `0x180006360`
- `0x180009090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006463`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000646d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006463`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000646d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800063c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800063f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800063c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800063f5`

## string_xrefs

- `0x18000643e`: `DpspInstanceCompleteNotification`
- `0x1800064bc`: `DpspInstanceCompleteNotification`

## pseudocode

```c
__int64 __fastcall DpspInstanceCompleteNotification(struct INSTANCEINFO *a1, _DWORD *a2)
{
  unsigned int v2; // esi
  unsigned int v5; // eax
  __int64 v6; // rbx
  __int64 v7; // rcx
  int Args; // eax
  __int64 v9; // rcx
  int v11; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  *a2 = 1;
  v11 = 0;
  if ( !*((_QWORD *)a1 + 152) )
    return 0;
  if ( (*((_DWORD *)a1 + 26) & 0x20) != 0 )
    return 0;
  _InterlockedOr((volatile signed __int32 *)a1 + 26, 0x200u);
  v5 = *((_DWORD *)a1 + 28);
  if ( v5 > *((_DWORD *)a1 + 29) )
    return 0;
  while ( 1 )
  {
    v6 = *((_QWORD *)a1 + v5 + 102);
    if ( !v6 )
      break;
    EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 64));
    if ( (*(_BYTE *)(v6 + 152) & 0x20) != 0 && *(_DWORD *)(v6 + 24) == 2 )
    {
      v7 = *(_QWORD *)(v6 + 176);
      if ( v7 )
        EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 72));
      if ( **(_DWORD **)(v6 + 176) == 2 )
      {
        *((_QWORD *)a1 + 101) = v6;
        Args = DpspValidateSession((struct __SESSIONINFO *)v6, a1, &v11, 3u);
        v2 = Args;
        if ( Args < 0 )
        {
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpscli.cpp",
            (int)L"DpspInstanceCompleteNotification",
            1261,
            (int)L"Error = %d",
            Args);
          v2 = 0;
        }
      }
      v9 = *(_QWORD *)(v6 + 176);
      if ( v9 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 72));
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 64));
    if ( v11 == 1 )
    {
      *a2 = 0;
      return v2;
    }
    v5 = ++*((_DWORD *)a1 + 28);
    if ( v5 > *((_DWORD *)a1 + 29) )
      return v2;
  }
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpscli.cpp",
    (int)L"DpspInstanceCompleteNotification",
    1229,
    (int)L"Error = %d",
    5);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180006360  push    rsi
0x180006362  push    rdi
0x180006363  push    r14
0x180006365  sub     rsp, 30h
0x180006369  xor     esi, esi
0x18000636b  mov     dword ptr [rdx], 1
0x180006371  mov     r14, rdx
0x180006374  mov     rdi, rcx
0x180006377  mov     [rsp+48h+arg_0], esi
0x18000637b  cmp     [rcx+4C0h], rsi
0x180006382  jz      loc_1800064D6
0x180006388  mov     eax, [rcx+68h]
0x18000638b  test    al, 20h
0x18000638d  jnz     loc_1800064D6
0x180006393  lock or dword ptr [rcx+68h], 200h
0x18000639b  mov     eax, [rcx+70h]
0x18000639e  cmp     eax, [rcx+74h]
0x1800063a1  ja      loc_1800064D6
0x1800063a7  mov     [rsp+48h+arg_8], rbx
0x1800063ac  mov     [rsp+48h+arg_10], rbp
0x1800063b1  mov     ebx, eax
0x1800063b3  mov     rbx, [rdi+rbx*8+330h]
0x1800063bb  test    rbx, rbx
0x1800063be  jz      loc_1800064A7
0x1800063c4  lea     rcx, [rbx+40h]; lpCriticalSection
0x1800063c8  call    cs:__imp_EnterCriticalSection
0x1800063ce  test    byte ptr [rbx+98h], 20h
0x1800063d5  jz      loc_180006469
0x1800063db  cmp     dword ptr [rbx+18h], 2
0x1800063df  jnz     loc_180006469
0x1800063e5  mov     rcx, [rbx+0B0h]
0x1800063ec  test    rcx, rcx
0x1800063ef  jz      short loc_1800063FB
0x1800063f1  add     rcx, 48h ; 'H'; lpCriticalSection
0x1800063f5  call    cs:__imp_EnterCriticalSection
0x1800063fb  mov     rax, [rbx+0B0h]
0x180006402  cmp     dword ptr [rax], 2
0x180006405  jnz     short loc_180006453
0x180006407  mov     r9d, 3
0x18000640d  mov     [rdi+328h], rbx
0x180006414  lea     r8, [rsp+48h+arg_0]
0x180006419  mov     rdx, rdi; struct INSTANCEINFO *
0x18000641c  mov     rcx, rbx; struct __SESSIONINFO *
0x18000641f  call    DpspValidateSession
0x180006424  mov     esi, eax
0x180006426  test    eax, eax
0x180006428  jns     short loc_180006453
0x18000642a  movzx   eax, ax
0x18000642d  lea     r9, aErrorD; "Error = %d"
0x180006434  mov     r8d, 4EDh; int
0x18000643a  mov     dword ptr [rsp+48h+Args], eax; Args
0x18000643e  lea     rdx, aDpspinstanceco; "DpspInstanceCompleteNotification"
0x180006445  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000644c  call    WdipTraceError
0x180006451  xor     esi, esi
0x180006453  mov     rcx, [rbx+0B0h]
0x18000645a  test    rcx, rcx
0x18000645d  jz      short loc_180006469
0x18000645f  add     rcx, 48h ; 'H'; lpCriticalSection
0x180006463  call    cs:__imp_LeaveCriticalSection
0x180006469  lea     rcx, [rbx+40h]; lpCriticalSection
0x18000646d  call    cs:__imp_LeaveCriticalSection
0x180006473  cmp     [rsp+48h+arg_0], 1
0x180006478  jz      short loc_18000649E
0x18000647a  inc     dword ptr [rdi+70h]
0x18000647d  mov     eax, [rdi+70h]
0x180006480  cmp     eax, [rdi+74h]
0x180006483  jbe     loc_1800063B1
0x180006489  mov     eax, esi
0x18000648b  mov     rbp, [rsp+48h+arg_10]
0x180006490  mov     rbx, [rsp+48h+arg_8]
0x180006495  add     rsp, 30h
0x180006499  pop     r14
0x18000649b  pop     rdi
0x18000649c  pop     rsi
0x18000649d  retn
0x18000649e  mov     dword ptr [r14], 0
0x1800064a5  jmp     short loc_180006489
0x1800064a7  lea     r9, aErrorD; "Error = %d"
0x1800064ae  mov     dword ptr [rsp+48h+Args], 4005h; Args
0x1800064b6  mov     r8d, 4CDh; int
0x1800064bc  lea     rdx, aDpspinstanceco; "DpspInstanceCompleteNotification"
0x1800064c3  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800064ca  call    WdipTraceError
0x1800064cf  mov     eax, 80004005h
0x1800064d4  jmp     short loc_18000648B
0x1800064d6  mov     eax, esi
0x1800064d8  add     rsp, 30h
0x1800064dc  pop     r14
0x1800064de  pop     rdi
0x1800064df  pop     rsi
0x1800064e0  retn
```
