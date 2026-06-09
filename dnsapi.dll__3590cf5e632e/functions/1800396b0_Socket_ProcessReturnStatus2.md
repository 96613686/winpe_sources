# Socket_ProcessReturnStatus2

- ea: `0x1800396b0`
- end: `0x18003978f`
- name: `Socket_ProcessReturnStatus2`
- size: `223`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800393a8`
- `0x180039798`

## callees

- `0x180021490`
- `0x1800396b0`
- `0x180051718`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800396f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800396f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003977e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003977e`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18003975c`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18003975c`

## pseudocode

```c
__int64 __fastcall Socket_ProcessReturnStatus2(__int64 a1, int a2, unsigned int a3)
{
  unsigned int v3; // esi
  struct _RTL_CRITICAL_SECTION *v7; // r15
  _QWORD *i; // rbx
  _QWORD *j; // rbx
  unsigned __int64 v10; // rbx

  v3 = a3;
  if ( a3 != 997 )
  {
    if ( a3 )
    {
      v7 = (struct _RTL_CRITICAL_SECTION *)(a1 + 65888);
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 65888));
      if ( a2 )
      {
        for ( i = *(_QWORD **)(a1 + 16); i != (_QWORD *)(a1 + 16); i = (_QWORD *)*i )
          Trace_LogRecvEvent(*(i - 1), v3, 1);
        for ( j = *(_QWORD **)(a1 + 32); j != (_QWORD *)(a1 + 32); j = (_QWORD *)*j )
          Trace_LogRecvEvent(*(j - 1), v3, 1);
      }
      v10 = -(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFFCuLL;
      if ( *(_DWORD *)(v10 + a1 + 180) )
      {
        CancelThreadpoolIo(*(PTP_IO *)(a1 + 64));
        *(_DWORD *)(v10 + a1 + 180) = 0;
        DeRefTcpConnection(a1);
      }
      LeaveCriticalSection(v7);
    }
    else
    {
      return 997;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800396b0  push    rbx
0x1800396b2  push    rbp
0x1800396b3  push    rsi
0x1800396b4  push    rdi
0x1800396b5  push    r14
0x1800396b7  push    r15
0x1800396b9  sub     rsp, 28h
0x1800396bd  mov     eax, 3E5h
0x1800396c2  mov     esi, r8d
0x1800396c5  mov     ebp, edx
0x1800396c7  mov     rdi, rcx
0x1800396ca  cmp     r8d, eax
0x1800396cd  jnz     short loc_1800396DF
0x1800396cf  mov     eax, esi
0x1800396d1  add     rsp, 28h
0x1800396d5  pop     r15
0x1800396d7  pop     r14
0x1800396d9  pop     rdi
0x1800396da  pop     rsi
0x1800396db  pop     rbp
0x1800396dc  pop     rbx
0x1800396dd  retn
0x1800396df  test    esi, esi
0x1800396e1  jnz     short loc_1800396E7
0x1800396e3  mov     esi, eax
0x1800396e5  jmp     short loc_1800396CF
0x1800396e7  lea     r15, [rcx+10160h]
0x1800396ee  mov     rcx, r15; lpCriticalSection
0x1800396f1  call    cs:__imp_EnterCriticalSection
0x1800396f8  nop     dword ptr [rax+rax+00h]
0x1800396fd  test    ebp, ebp
0x1800396ff  jz      short loc_180039745
0x180039701  lea     r14, [rdi+10h]
0x180039705  mov     rbx, [r14]
0x180039708  jmp     short loc_18003971E
0x18003970a  mov     rcx, [rbx-8]
0x18003970e  mov     r8d, 1
0x180039714  mov     edx, esi
0x180039716  call    Trace_LogRecvEvent
0x18003971b  mov     rbx, [rbx]
0x18003971e  cmp     rbx, r14
0x180039721  jnz     short loc_18003970A
0x180039723  lea     r14, [rdi+20h]
0x180039727  mov     rbx, [r14]
0x18003972a  jmp     short loc_180039740
0x18003972c  mov     rcx, [rbx-8]
0x180039730  mov     r8d, 1
0x180039736  mov     edx, esi
0x180039738  call    Trace_LogRecvEvent
0x18003973d  mov     rbx, [rbx]
0x180039740  cmp     rbx, r14
0x180039743  jnz     short loc_18003972C
0x180039745  neg     ebp
0x180039747  sbb     rbx, rbx
0x18003974a  and     rbx, 0FFFFFFFFFFFFFFFCh
0x18003974e  cmp     dword ptr [rbx+rdi+0B4h], 0
0x180039756  jz      short loc_18003977B
0x180039758  mov     rcx, [rdi+40h]; pio
0x18003975c  call    cs:__imp_CancelThreadpoolIo
0x180039763  nop     dword ptr [rax+rax+00h]
0x180039768  mov     rcx, rdi
0x18003976b  mov     dword ptr [rbx+rdi+0B4h], 0
0x180039776  call    DeRefTcpConnection
0x18003977b  mov     rcx, r15; lpCriticalSection
0x18003977e  call    cs:__imp_LeaveCriticalSection
0x180039785  nop     dword ptr [rax+rax+00h]
0x18003978a  jmp     loc_1800396CF
```
