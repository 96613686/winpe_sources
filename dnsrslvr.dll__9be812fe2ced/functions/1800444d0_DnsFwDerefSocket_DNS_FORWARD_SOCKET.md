# DnsFwDerefSocket(_DNS_FORWARD_SOCKET *)

- ea: `0x1800444d0`
- end: `0x1800445c2`
- name: `?DnsFwDerefSocket@@YAXPEAU_DNS_FORWARD_SOCKET@@@Z`
- size: `242`
- prototype: `void __fastcall(struct _DNS_FORWARD_SOCKET *lpMem)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180043048`
- `0x1800432fc`
- `0x180043eb8`
- `0x180044174`

## callees

- `0x1800444d0`
- `0x180086700`
- `0x180086bd4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044573`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044573`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044581`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044581`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044556`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044597`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044556`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044597`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044504`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044504`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180044565`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180044565`
- `WS2_32!__imp_closesocket` at `0x180044541`
- `WS2_32!__imp_closesocket` at `0x180044541`

## pseudocode

```c
void __fastcall DnsFwDerefSocket(struct _DNS_FORWARD_SOCKET *lpMem)
{
  __int64 v2; // rax
  struct _DNS_FORWARD_SOCKET **v3; // rdx
  SOCKET v4; // rcx
  struct _TP_IO *v5; // rcx
  HANDLE ProcessHeap; // rax

  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_qd(lpMem, 12, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids, lpMem, *((_DWORD *)lpMem + 10));
  EnterCriticalSection(&g_SocketListLock);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpMem + 10, 0xFFFFFFFF) == 1 )
  {
    v2 = *(_QWORD *)lpMem;
    if ( *(struct _DNS_FORWARD_SOCKET **)(*(_QWORD *)lpMem + 8LL) != lpMem
      || (v3 = (struct _DNS_FORWARD_SOCKET **)*((_QWORD *)lpMem + 1), *v3 != lpMem) )
    {
      __fastfail(3u);
    }
    *v3 = (struct _DNS_FORWARD_SOCKET *)v2;
    *(_QWORD *)(v2 + 8) = v3;
    *((_QWORD *)lpMem + 1) = lpMem;
    *(_QWORD *)lpMem = lpMem;
    v4 = *((_QWORD *)lpMem + 6);
    if ( v4 != -1 )
    {
      closesocket(v4);
      *((_QWORD *)lpMem + 6) = 0;
    }
    LeaveCriticalSection(&g_SocketListLock);
    v5 = (struct _TP_IO *)*((_QWORD *)lpMem + 9);
    if ( v5 )
    {
      CloseThreadpoolIo(v5);
      *((_QWORD *)lpMem + 9) = 0;
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  else
  {
    LeaveCriticalSection(&g_SocketListLock);
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 13, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids);
}

```

## disassembly

```asm
0x1800444d0  push    rbx
0x1800444d2  sub     rsp, 30h
0x1800444d6  mov     rbx, rcx
0x1800444d9  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800444e0  jz      short loc_1800444FD
0x1800444e2  mov     eax, [rcx+28h]
0x1800444e5  lea     r8, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids
0x1800444ec  mov     edx, 0Ch
0x1800444f1  mov     [rsp+38h+var_18], eax
0x1800444f5  mov     r9, rcx
0x1800444f8  call    WPP_SF_qd
0x1800444fd  lea     rcx, ?g_SocketListLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180044504  call    cs:__imp_EnterCriticalSection
0x18004450a  or      eax, 0FFFFFFFFh
0x18004450d  lock xadd [rbx+28h], eax
0x180044512  cmp     eax, 1
0x180044515  jnz     short loc_180044590
0x180044517  mov     rax, [rbx]
0x18004451a  cmp     [rax+8], rbx
0x18004451e  jnz     short loc_180044589
0x180044520  mov     rdx, [rbx+8]
0x180044524  cmp     [rdx], rbx
0x180044527  jnz     short loc_180044589
0x180044529  mov     [rdx], rax
0x18004452c  mov     [rax+8], rdx
0x180044530  mov     [rbx+8], rbx
0x180044534  mov     [rbx], rbx
0x180044537  mov     rcx, [rbx+30h]; s
0x18004453b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18004453f  jz      short loc_18004454F
0x180044541  call    cs:__imp_closesocket
0x180044547  mov     qword ptr [rbx+30h], 0
0x18004454f  lea     rcx, ?g_SocketListLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180044556  call    cs:__imp_LeaveCriticalSection
0x18004455c  mov     rcx, [rbx+48h]; pio
0x180044560  test    rcx, rcx
0x180044563  jz      short loc_180044573
0x180044565  call    cs:__imp_CloseThreadpoolIo
0x18004456b  mov     qword ptr [rbx+48h], 0
0x180044573  call    cs:__imp_GetProcessHeap
0x180044579  mov     r8, rbx; lpMem
0x18004457c  xor     edx, edx; dwFlags
0x18004457e  mov     rcx, rax; hHeap
0x180044581  call    cs:__imp_HeapFree
0x180044587  jmp     short loc_18004459D
0x180044589  mov     ecx, 3
0x18004458e  int     29h; Win8: RtlFailFast(ecx)
0x180044590  lea     rcx, ?g_SocketListLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180044597  call    cs:__imp_LeaveCriticalSection
0x18004459d  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800445a4  jz      short loc_1800445BC
0x1800445a6  mov     edx, 0Dh
0x1800445ab  lea     r8, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids
0x1800445b2  mov     ecx, 40Bh
0x1800445b7  call    WPP_SF_
0x1800445bc  add     rsp, 30h
0x1800445c0  pop     rbx
0x1800445c1  retn
```
