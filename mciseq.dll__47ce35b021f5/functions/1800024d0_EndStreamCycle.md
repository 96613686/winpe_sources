# EndStreamCycle

- ea: `0x1800024d0`
- end: `0x180002589`
- name: `EndStreamCycle`
- size: `185`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000240c`

## callees

- `0x1800024d0`
- `0x180005e7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000255f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000255f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002549`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002549`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002552`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002552`
- `USER32!PostThreadMessageW` at `0x180002531`
- `USER32!PostThreadMessageW` at `0x180002531`

## pseudocode

```c
void __fastcall EndStreamCycle(__int64 a1)
{
  __int64 v1; // rax
  __int64 i; // rsi
  int j; // ebp
  DWORD v5; // ecx
  void *v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rsi

  if ( a1 )
  {
    v1 = *(unsigned int *)(a1 + 296);
    *(_DWORD *)(a1 + 300) = 0;
    if ( (_DWORD)v1 != -1 )
    {
      for ( i = (qword_18000A628[2 * v1] + 16LL) & -(__int64)(qword_18000A628[2 * v1] != 0); i; i = v10 + 16 )
      {
        for ( j = 0; j < 2; ++j )
        {
          v5 = *(_DWORD *)(a1 + 304);
          if ( !v5 )
            break;
          PostThreadMessageW(v5, 0x401u, 0, 0);
          v6 = *(void **)(a1 + 312);
          LeaveSeq(v8, v7, v9);
          WaitForSingleObject(v6, 0xFFFFFFFF);
          CloseHandle(v6);
          EnterCriticalSection(&SeqCritSec);
        }
        v10 = *(_QWORD *)(i - 16);
        if ( !v10 )
          break;
      }
    }
  }
}

```

## disassembly

```asm
0x1800024d0  test    rcx, rcx
0x1800024d3  jz      locret_180002588
0x1800024d9  push    rbx
0x1800024da  push    rbp
0x1800024db  push    rsi
0x1800024dc  push    rdi
0x1800024dd  sub     rsp, 28h
0x1800024e1  mov     eax, [rcx+128h]
0x1800024e7  mov     rdi, rcx
0x1800024ea  mov     dword ptr [rcx+12Ch], 0
0x1800024f4  cmp     eax, 0FFFFFFFFh
0x1800024f7  jz      loc_180002580
0x1800024fd  add     rax, rax
0x180002500  lea     rcx, qword_18000A628
0x180002507  mov     rcx, [rcx+rax*8]
0x18000250b  lea     rax, [rcx+10h]
0x18000250f  neg     rcx
0x180002512  sbb     rsi, rsi
0x180002515  and     rsi, rax
0x180002518  jz      short loc_180002580
0x18000251a  xor     ebp, ebp
0x18000251c  mov     ecx, [rdi+130h]; idThread
0x180002522  test    ecx, ecx
0x180002524  jz      short loc_18000256C
0x180002526  xor     r9d, r9d; lParam
0x180002529  xor     r8d, r8d; wParam
0x18000252c  mov     edx, 401h; Msg
0x180002531  call    cs:__imp_PostThreadMessageW
0x180002537  mov     rbx, [rdi+138h]
0x18000253e  call    LeaveSeq
0x180002543  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002546  mov     rcx, rbx; hHandle
0x180002549  call    cs:__imp_WaitForSingleObject
0x18000254f  mov     rcx, rbx; hObject
0x180002552  call    cs:__imp_CloseHandle
0x180002558  lea     rcx, SeqCritSec; lpCriticalSection
0x18000255f  call    cs:__imp_EnterCriticalSection
0x180002565  inc     ebp
0x180002567  cmp     ebp, 2
0x18000256a  jl      short loc_18000251C
0x18000256c  test    rsi, rsi
0x18000256f  jz      short loc_180002580
0x180002571  mov     rsi, [rsi-10h]
0x180002575  test    rsi, rsi
0x180002578  jz      short loc_180002580
0x18000257a  add     rsi, 10h
0x18000257e  jnz     short loc_18000251A
0x180002580  add     rsp, 28h
0x180002584  pop     rdi
0x180002585  pop     rsi
0x180002586  pop     rbp
0x180002587  pop     rbx
0x180002588  retn
```
