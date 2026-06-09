# RemoveToBeRunTriggerJobs

- ea: `0x18000b918`
- end: `0x18000b98d`
- name: `RemoveToBeRunTriggerJobs`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800041bc`

## callees

- `0x1800088f0`
- `0x18000b918`
- `0x18000d4c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b964`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b92c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b92c`

## pseudocode

```c
void __fastcall RemoveToBeRunTriggerJobs(int a1, int a2)
{
  _QWORD *v4; // rbx
  _DWORD *v5; // rdi
  int v6; // eax
  bool v7; // zf

  EnterCriticalSection(&JobsCriticalSection);
  v4 = pToBeRunJobHead;
  while ( v4 )
  {
    v5 = v4;
    v4 = (_QWORD *)*v4;
    if ( v5[6] == 1 )
    {
      if ( a1 )
      {
        v6 = 0;
        v7 = a1 == v5[10];
      }
      else
      {
        if ( !a2 )
          goto LABEL_10;
        v6 = 0;
        v7 = a2 == v5[11];
      }
      LOBYTE(v6) = v7;
      if ( v6 )
      {
LABEL_10:
        RemoveToBeRunJob((__int64)v5);
        FreeTriggerJob(v5);
      }
    }
  }
  LeaveCriticalSection(&JobsCriticalSection);
}

```

## disassembly

```asm
0x18000b918  push    rbx
0x18000b91a  push    rbp
0x18000b91b  push    rsi
0x18000b91c  push    rdi
0x18000b91d  sub     rsp, 28h
0x18000b921  mov     ebp, ecx
0x18000b923  mov     esi, edx
0x18000b925  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b92c  call    cs:__imp_EnterCriticalSection
0x18000b932  mov     rbx, cs:?pToBeRunJobHead@@3PEAU_CUCS_JOB_HEADER@@EA; _CUCS_JOB_HEADER * pToBeRunJobHead
0x18000b939  test    rbx, rbx
0x18000b93c  jz      short loc_18000B955
0x18000b93e  mov     rdi, rbx
0x18000b941  mov     rbx, [rbx]
0x18000b944  cmp     dword ptr [rdi+18h], 1
0x18000b948  jnz     short loc_18000B939
0x18000b94a  test    ebp, ebp
0x18000b94c  jz      short loc_18000B96B
0x18000b94e  xor     eax, eax
0x18000b950  cmp     ebp, [rdi+28h]
0x18000b953  jmp     short loc_18000B974
0x18000b955  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION JobsCriticalSection
0x18000b95c  add     rsp, 28h
0x18000b960  pop     rdi
0x18000b961  pop     rsi
0x18000b962  pop     rbp
0x18000b963  pop     rbx
0x18000b964  jmp     cs:__imp_LeaveCriticalSection
0x18000b96b  test    esi, esi
0x18000b96d  jz      short loc_18000B97B
0x18000b96f  xor     eax, eax
0x18000b971  cmp     esi, [rdi+2Ch]
0x18000b974  setz    al
0x18000b977  test    eax, eax
0x18000b979  jz      short loc_18000B939
0x18000b97b  mov     rcx, rdi
0x18000b97e  call    RemoveToBeRunJob
0x18000b983  mov     rcx, rdi; hMem
0x18000b986  call    FreeTriggerJob
0x18000b98b  jmp     short loc_18000B939
```
