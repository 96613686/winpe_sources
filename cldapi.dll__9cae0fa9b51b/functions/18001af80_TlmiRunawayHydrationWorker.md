# TlmiRunawayHydrationWorker

- ea: `0x18001af80`
- end: `0x18001b455`
- name: `TlmiRunawayHydrationWorker`
- size: `1237`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000231e`
- `0x18001a694`
- `0x18001ae98`
- `0x18001af80`
- `0x18001d0ac`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001b041`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001b041`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001b097`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001b097`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18001b277`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18001b401`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18001b277`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18001b401`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001b2af`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001b329`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001b3ce`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001b41a`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001b2af`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001b329`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001b3ce`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001b41a`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18001b110`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18001b110`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001afac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001b291`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001afac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001b291`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b137`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b15b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b1fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b223`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b24c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b137`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b15b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b1fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b223`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b24c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b14b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b16f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b14b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b16f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b212`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b237`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b260`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b212`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b237`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b260`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001b003`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001b023`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001b003`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001b023`

## pseudocode

```c
__int64 __fastcall TlmiRunawayHydrationWorker(PVOID Parameter)
{
  _QWORD *v1; // rbx
  __int64 v2; // rcx
  _QWORD *v3; // rax
  const void **v4; // rdi
  _QWORD *inserted; // rbx
  unsigned int v6; // r14d
  HANDLE ProcessHeap; // rax
  HANDLE v8; // rax
  LPVOID v9; // rax
  void *v10; // rsi
  void *v11; // rcx
  __int64 v12; // rcx
  unsigned int v13; // eax
  HANDLE v14; // rax
  HANDLE v15; // rax
  void *v16; // rbx
  HANDLE v17; // rax
  PVOID v18; // r15
  PVOID v19; // r14
  int v20; // r12d
  DWORD v21; // esi
  DWORD v22; // r13d
  PVOID v23; // rbx
  unsigned int v24; // edi
  char v25; // al
  _DWORD *i; // rax
  BOOLEAN v27; // dl
  DWORD v29; // [rsp+20h] [rbp-49h]
  __int64 v30; // [rsp+28h] [rbp-41h]
  __int128 v31; // [rsp+30h] [rbp-39h] BYREF
  int Buffer; // [rsp+40h] [rbp-29h] BYREF
  __int128 v33; // [rsp+48h] [rbp-21h]
  unsigned __int8 NewElement; // [rsp+D8h] [rbp+6Fh] BYREF
  int v35; // [rsp+E0h] [rbp+77h]
  DWORD TickCount; // [rsp+E8h] [rbp+7Fh]

  v30 = 0;
  v35 = 780000;
  TickCount = GetTickCount();
  v29 = TickCount;
  while ( byte_18002A930 )
  {
    if ( NtCurrentPeb()->Ldr->ShutdownInProgress )
      break;
    *((_QWORD *)&v31 + 1) = &v31;
    *(_QWORD *)&v31 = &v31;
    if ( WaitForSingleObject(qword_18002AA40, 0xFFFFFFFF) || WaitForSingleObject(qword_18002AA48, 0xEA60u) != 258 )
      break;
    RtlAcquireSRWLockExclusive(&qword_18002A9B8);
    if ( (__int128 *)xmmword_18002AA30 != &xmmword_18002AA30 )
    {
      v31 = xmmword_18002AA30;
      *(_QWORD *)(xmmword_18002AA30 + 8) = &v31;
      **((_QWORD **)&xmmword_18002AA30 + 1) = &v31;
    }
    *((_QWORD *)&xmmword_18002AA30 + 1) = &xmmword_18002AA30;
    *(_QWORD *)&xmmword_18002AA30 = &xmmword_18002AA30;
    RtlReleaseSRWLockExclusive(&qword_18002A9B8);
    while ( 1 )
    {
      v1 = (_QWORD *)v31;
      if ( (__int128 *)v31 == &v31 )
        break;
      memset_0(&Buffer, 0, 0x50u);
      NewElement = 0;
      v2 = *v1;
      if ( *(_QWORD **)(*v1 + 8LL) != v1 || (v3 = (_QWORD *)v1[1], (_QWORD *)*v3 != v1) )
        __fastfail(3u);
      *v3 = v2;
      v4 = (const void **)(v1 - 3);
      *(_QWORD *)(v2 + 8) = v3;
      Buffer = *((_DWORD *)v1 - 5);
      v33 = *((_OWORD *)v1 - 1);
      inserted = RtlInsertElementGenericTableAvl(&stru_18002A9C8, &Buffer, 0x50u, &NewElement);
      if ( inserted )
      {
        if ( !NewElement )
          goto LABEL_17;
        v6 = *((unsigned __int16 *)v4 + 5);
        ProcessHeap = GetProcessHeap();
        inserted[2] = HeapAlloc(ProcessHeap, 0, v6);
        v8 = GetProcessHeap();
        v9 = HeapAlloc(v8, 0, v6);
        v10 = (void *)inserted[2];
        inserted[4] = v9;
        if ( v10 )
        {
          if ( v9 )
          {
            memcpy_0(v10, v4[2], v6);
            v11 = (void *)inserted[4];
            *((_WORD *)inserted + 4) = *((_WORD *)v4 + 4);
            *((_WORD *)inserted + 5) = *((_WORD *)v4 + 5);
            memcpy_0(v11, v4[2], v6);
            v12 = inserted[4];
            *((_WORD *)inserted + 12) = *((_WORD *)v4 + 4);
            *((_WORD *)inserted + 13) = *((_WORD *)v4 + 5);
            TlmiRemoveUsername(v12);
LABEL_17:
            ++*((_DWORD *)inserted + 10);
            inserted[6] += v4[5];
            ++*((_DWORD *)inserted + 14);
            inserted[8] += v4[5];
            v13 = *((_DWORD *)inserted + 18);
            if ( v13 <= *(_DWORD *)v4 )
              v13 = *(_DWORD *)v4;
            *((_DWORD *)inserted + 18) = v13;
            goto LABEL_20;
          }
          v15 = GetProcessHeap();
          HeapFree(v15, 0, v10);
        }
        v16 = (void *)inserted[4];
        if ( v16 )
        {
          v17 = GetProcessHeap();
          HeapFree(v17, 0, v16);
        }
        RtlDeleteElementGenericTableAvl(&stru_18002A9C8, &Buffer);
      }
LABEL_20:
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v4);
    }
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = GetTickCount();
    v22 = v21 - TickCount;
    v23 = RtlEnumerateGenericTableAvl(&stru_18002A9C8, 1u);
    if ( v23 )
    {
      do
      {
        if ( *((int *)v23 + 10) > 50 || *((__int64 *)v23 + 6) > 786432000 )
          TlmiLogRunawayHydration(v23, 0, v21, 0);
        v24 = v35;
        *((_QWORD *)v23 + 6) = 0;
        *((_DWORD *)v23 + 10) = 0;
        if ( v22 > v24 )
        {
          if ( *((_DWORD *)v23 + 14) > v20 )
          {
            v20 = *((_DWORD *)v23 + 14);
            v18 = v23;
          }
          if ( *((_QWORD *)v23 + 8) > v30 )
          {
            v19 = v23;
            v30 = *((_QWORD *)v23 + 8);
          }
        }
        v23 = RtlEnumerateGenericTableAvl(&stru_18002A9C8, 0);
      }
      while ( v23 );
      if ( v18 && v19 && (v24 == 780000 || v20 > 30 || v30 > 786432000) )
      {
        v25 = 1;
        goto LABEL_43;
      }
    }
    else
    {
      v24 = v35;
    }
    v25 = 0;
LABEL_43:
    if ( v22 > v24 )
    {
      if ( v25 )
      {
        TlmiLogRunawayHydration(v18, 1, v21, v24);
        if ( v18 != v19 )
          TlmiLogRunawayHydration(v19, 1, v21, v24);
      }
      TickCount = v21;
      v30 = 0;
      v35 = 4200000;
    }
    if ( v21 - v29 > 0x5265C0 )
    {
      for ( i = RtlEnumerateGenericTableAvl(&stru_18002A9C8, 1u); i; i = RtlEnumerateGenericTableAvl(
                                                                           &stru_18002A9C8,
                                                                           v27) )
      {
        if ( v21 - i[18] <= 0x5265C0 )
        {
          v27 = 0;
        }
        else
        {
          RtlDeleteElementGenericTableAvl(&stru_18002A9C8, i);
          v27 = 1;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001af80  mov     [rsp-8+arg_0], rbx
0x18001af85  push    rbp
0x18001af86  push    rsi
0x18001af87  push    rdi
0x18001af88  push    r12
0x18001af8a  push    r13
0x18001af8c  push    r14
0x18001af8e  push    r15
0x18001af90  lea     rbp, [rsp-27h]
0x18001af95  sub     rsp, 90h
0x18001af9c  mov     edi, 0BE6E0h
0x18001afa1  mov     [rbp+57h+var_98], 0
0x18001afa9  mov     [rbp+57h+arg_10], edi
0x18001afac  call    cs:__imp_GetTickCount
0x18001afb3  nop     dword ptr [rax+rax+00h]
0x18001afb8  mov     [rbp+57h+arg_18], eax
0x18001afbb  mov     [rbp+57h+var_A0], eax
0x18001afbe  lea     rbx, xmmword_18002AA30
0x18001afc5  cmp     cs:byte_18002A930, 0
0x18001afcc  jz      loc_18001B437
0x18001afd2  mov     rax, gs:60h
0x18001afdb  mov     rcx, [rax+18h]
0x18001afdf  cmp     byte ptr [rcx+48h], 0
0x18001afe3  jnz     loc_18001B437
0x18001afe9  mov     rcx, cs:qword_18002AA40; hHandle
0x18001aff0  lea     rax, [rbp+57h+var_90]
0x18001aff4  mov     qword ptr [rbp+57h+var_90+8], rax
0x18001aff8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001affb  lea     rax, [rbp+57h+var_90]
0x18001afff  mov     qword ptr [rbp+57h+var_90], rax
0x18001b003  call    cs:__imp_WaitForSingleObject
0x18001b00a  nop     dword ptr [rax+rax+00h]
0x18001b00f  test    eax, eax
0x18001b011  jnz     loc_18001B437
0x18001b017  mov     rcx, cs:qword_18002AA48; hHandle
0x18001b01e  mov     edx, 0EA60h; dwMilliseconds
0x18001b023  call    cs:__imp_WaitForSingleObject
0x18001b02a  nop     dword ptr [rax+rax+00h]
0x18001b02f  cmp     eax, 102h
0x18001b034  jnz     loc_18001B437
0x18001b03a  lea     rcx, qword_18002A9B8
0x18001b041  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001b048  nop     dword ptr [rax+rax+00h]
0x18001b04d  mov     rax, qword ptr cs:xmmword_18002AA30
0x18001b054  lea     rcx, xmmword_18002AA30
0x18001b05b  cmp     rax, rcx
0x18001b05e  jz      short loc_18001B082
0x18001b060  movaps  xmm0, cs:xmmword_18002AA30
0x18001b067  lea     rcx, [rbp+57h+var_90]
0x18001b06b  movdqu  [rbp+57h+var_90], xmm0
0x18001b070  mov     [rax+8], rcx
0x18001b074  lea     rcx, [rbp+57h+var_90]
0x18001b078  mov     rax, qword ptr cs:xmmword_18002AA30+8
0x18001b07f  mov     [rax], rcx
0x18001b082  lea     rcx, qword_18002A9B8
0x18001b089  mov     qword ptr cs:xmmword_18002AA30+8, rbx
0x18001b090  mov     qword ptr cs:xmmword_18002AA30, rbx
0x18001b097  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001b09e  nop     dword ptr [rax+rax+00h]
0x18001b0a3  mov     rbx, qword ptr [rbp+57h+var_90]
0x18001b0a7  lea     rax, [rbp+57h+var_90]
0x18001b0ab  cmp     rbx, rax
0x18001b0ae  jz      loc_18001B288
0x18001b0b4  xor     edx, edx; Val
0x18001b0b6  lea     rcx, [rbp+57h+Buffer]; void *
0x18001b0ba  lea     r8d, [rdx+50h]; Size
0x18001b0be  call    memset_0
0x18001b0c3  mov     [rbp+57h+NewElement], 0
0x18001b0c7  mov     rcx, [rbx]
0x18001b0ca  cmp     [rcx+8], rbx
0x18001b0ce  jnz     loc_18001B430
0x18001b0d4  mov     rax, [rbx+8]
0x18001b0d8  cmp     [rax], rbx
0x18001b0db  jnz     loc_18001B430
0x18001b0e1  mov     [rax], rcx
0x18001b0e4  lea     rdi, [rbx-18h]
0x18001b0e8  mov     [rcx+8], rax
0x18001b0ec  lea     r9, [rbp+57h+NewElement]; NewElement
0x18001b0f0  mov     eax, [rdi+4]
0x18001b0f3  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18001b0f7  mov     [rbp+57h+Buffer], eax
0x18001b0fa  lea     rcx, stru_18002A9C8; Table
0x18001b101  movups  xmm0, xmmword ptr [rdi+8]
0x18001b105  mov     r8d, 50h ; 'P'; BufferSize
0x18001b10b  movdqu  [rbp+57h+var_78], xmm0
0x18001b110  call    cs:__imp_RtlInsertElementGenericTableAvl
0x18001b117  nop     dword ptr [rax+rax+00h]
0x18001b11c  mov     rbx, rax
0x18001b11f  test    rax, rax
0x18001b122  jz      loc_18001B1FE
0x18001b128  cmp     [rbp+57h+NewElement], 0
0x18001b12c  jz      loc_18001B1DD
0x18001b132  movzx   r14d, word ptr [rdi+0Ah]
0x18001b137  call    cs:__imp_GetProcessHeap
0x18001b13e  nop     dword ptr [rax+rax+00h]
0x18001b143  mov     r8d, r14d; dwBytes
0x18001b146  xor     edx, edx; dwFlags
0x18001b148  mov     rcx, rax; hHeap
0x18001b14b  call    cs:__imp_HeapAlloc
0x18001b152  nop     dword ptr [rax+rax+00h]
0x18001b157  mov     [rbx+10h], rax
0x18001b15b  call    cs:__imp_GetProcessHeap
0x18001b162  nop     dword ptr [rax+rax+00h]
0x18001b167  mov     r8d, r14d; dwBytes
0x18001b16a  xor     edx, edx; dwFlags
0x18001b16c  mov     rcx, rax; hHeap
0x18001b16f  call    cs:__imp_HeapAlloc
0x18001b176  nop     dword ptr [rax+rax+00h]
0x18001b17b  mov     rsi, [rbx+10h]
0x18001b17f  mov     [rbx+20h], rax
0x18001b183  test    rsi, rsi
0x18001b186  jz      loc_18001B243
0x18001b18c  test    rax, rax
0x18001b18f  jz      loc_18001B223
0x18001b195  mov     rdx, [rdi+10h]; Src
0x18001b199  mov     r8d, r14d; Size
0x18001b19c  mov     rcx, rsi; void *
0x18001b19f  call    memcpy_0
0x18001b1a4  movzx   eax, word ptr [rdi+8]
0x18001b1a8  mov     r8d, r14d; Size
0x18001b1ab  mov     rcx, [rbx+20h]; void *
0x18001b1af  mov     [rbx+8], ax
0x18001b1b3  movzx   eax, word ptr [rdi+0Ah]
0x18001b1b7  mov     [rbx+0Ah], ax
0x18001b1bb  mov     rdx, [rdi+10h]; Src
0x18001b1bf  call    memcpy_0
0x18001b1c4  movzx   edx, word ptr [rdi+8]
0x18001b1c8  mov     rcx, [rbx+20h]
0x18001b1cc  mov     [rbx+18h], dx
0x18001b1d0  movzx   eax, word ptr [rdi+0Ah]
0x18001b1d4  mov     [rbx+1Ah], ax
0x18001b1d8  call    TlmiRemoveUsername
0x18001b1dd  inc     dword ptr [rbx+28h]
0x18001b1e0  mov     rax, [rdi+28h]
0x18001b1e4  add     [rbx+30h], rax
0x18001b1e8  inc     dword ptr [rbx+38h]
0x18001b1eb  mov     rax, [rdi+28h]
0x18001b1ef  add     [rbx+40h], rax
0x18001b1f3  mov     eax, [rbx+48h]
0x18001b1f6  cmp     eax, [rdi]
0x18001b1f8  cmovbe  eax, [rdi]
0x18001b1fb  mov     [rbx+48h], eax
0x18001b1fe  call    cs:__imp_GetProcessHeap
0x18001b205  nop     dword ptr [rax+rax+00h]
0x18001b20a  mov     r8, rdi; lpMem
0x18001b20d  xor     edx, edx; dwFlags
0x18001b20f  mov     rcx, rax; hHeap
0x18001b212  call    cs:__imp_HeapFree
0x18001b219  nop     dword ptr [rax+rax+00h]
0x18001b21e  jmp     loc_18001B0A3
0x18001b223  call    cs:__imp_GetProcessHeap
0x18001b22a  nop     dword ptr [rax+rax+00h]
0x18001b22f  mov     r8, rsi; lpMem
0x18001b232  xor     edx, edx; dwFlags
0x18001b234  mov     rcx, rax; hHeap
0x18001b237  call    cs:__imp_HeapFree
0x18001b23e  nop     dword ptr [rax+rax+00h]
0x18001b243  mov     rbx, [rbx+20h]
0x18001b247  test    rbx, rbx
0x18001b24a  jz      short loc_18001B26C
0x18001b24c  call    cs:__imp_GetProcessHeap
0x18001b253  nop     dword ptr [rax+rax+00h]
0x18001b258  mov     r8, rbx; lpMem
0x18001b25b  xor     edx, edx; dwFlags
0x18001b25d  mov     rcx, rax; hHeap
0x18001b260  call    cs:__imp_HeapFree
0x18001b267  nop     dword ptr [rax+rax+00h]
0x18001b26c  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18001b270  lea     rcx, stru_18002A9C8; Table
0x18001b277  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18001b27e  nop     dword ptr [rax+rax+00h]
0x18001b283  jmp     loc_18001B1FE
0x18001b288  xor     r15d, r15d
0x18001b28b  xor     r14d, r14d
0x18001b28e  xor     r12d, r12d
0x18001b291  call    cs:__imp_GetTickCount
0x18001b298  nop     dword ptr [rax+rax+00h]
0x18001b29d  mov     dl, 1; Restart
0x18001b29f  lea     rcx, stru_18002A9C8; Table
0x18001b2a6  mov     r13d, eax
0x18001b2a9  mov     esi, eax
0x18001b2ab  sub     r13d, [rbp+57h+arg_18]
0x18001b2af  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18001b2b6  nop     dword ptr [rax+rax+00h]
0x18001b2bb  mov     rbx, rax
0x18001b2be  test    rax, rax
0x18001b2c1  jz      loc_18001B363
0x18001b2c7  cmp     dword ptr [rbx+28h], 32h ; '2'
0x18001b2cb  jg      short loc_18001B2D7
0x18001b2cd  cmp     qword ptr [rbx+30h], 2EE00000h
0x18001b2d5  jle     short loc_18001B2E7
0x18001b2d7  xor     edx, edx
0x18001b2d9  xor     r9d, r9d
0x18001b2dc  mov     r8d, esi
0x18001b2df  mov     rcx, rbx
0x18001b2e2  call    TlmiLogRunawayHydration
0x18001b2e7  mov     edi, [rbp+57h+arg_10]
0x18001b2ea  mov     qword ptr [rbx+30h], 0
0x18001b2f2  mov     dword ptr [rbx+28h], 0
0x18001b2f9  cmp     r13d, edi
0x18001b2fc  jbe     short loc_18001B320
0x18001b2fe  cmp     [rbx+38h], r12d
0x18001b302  jle     short loc_18001B30B
0x18001b304  mov     r12d, [rbx+38h]
0x18001b308  mov     r15, rbx
0x18001b30b  mov     rax, [rbp+57h+var_98]
0x18001b30f  cmp     [rbx+40h], rax
0x18001b313  jle     short loc_18001B320
0x18001b315  mov     rax, [rbx+40h]
0x18001b319  mov     r14, rbx
0x18001b31c  mov     [rbp+57h+var_98], rax
0x18001b320  xor     edx, edx; Restart
0x18001b322  lea     rcx, stru_18002A9C8; Table
0x18001b329  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18001b330  nop     dword ptr [rax+rax+00h]
0x18001b335  mov     rbx, rax
0x18001b338  test    rax, rax
0x18001b33b  jnz     short loc_18001B2C7
0x18001b33d  test    r15, r15
0x18001b340  jz      short loc_18001B366
0x18001b342  test    r14, r14
0x18001b345  jz      short loc_18001B366
0x18001b347  cmp     edi, 0BE6E0h
0x18001b34d  jz      short loc_18001B35F
0x18001b34f  cmp     r12d, 1Eh
0x18001b353  jg      short loc_18001B35F
0x18001b355  cmp     [rbp+57h+var_98], 2EE00000h
0x18001b35d  jle     short loc_18001B366
0x18001b35f  mov     al, 1
0x18001b361  jmp     short loc_18001B368
0x18001b363  mov     edi, [rbp+57h+arg_10]
0x18001b366  xor     al, al
0x18001b368  cmp     r13d, edi
0x18001b36b  jbe     short loc_18001B3AE
0x18001b36d  test    al, al
0x18001b36f  jz      short loc_18001B39C
0x18001b371  mov     edx, 1
0x18001b376  mov     r9d, edi
0x18001b379  mov     r8d, esi
0x18001b37c  mov     rcx, r15
0x18001b37f  call    TlmiLogRunawayHydration
0x18001b384  cmp     r15, r14
0x18001b387  jz      short loc_18001B39C
0x18001b389  mov     edx, 1
0x18001b38e  mov     r9d, edi
0x18001b391  mov     r8d, esi
0x18001b394  mov     rcx, r14
0x18001b397  call    TlmiLogRunawayHydration
0x18001b39c  mov     [rbp+57h+arg_18], esi
0x18001b39f  mov     [rbp+57h+var_98], 0
0x18001b3a7  mov     [rbp+57h+arg_10], 401640h
0x18001b3ae  mov     eax, esi
0x18001b3b0  lea     rbx, xmmword_18002AA30
0x18001b3b7  sub     eax, [rbp+57h+var_A0]
0x18001b3ba  cmp     eax, 5265C0h
0x18001b3bf  jbe     loc_18001AFC5
0x18001b3c5  mov     dl, 1; Restart
0x18001b3c7  lea     rcx, stru_18002A9C8; Table
0x18001b3ce  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18001b3d5  nop     dword ptr [rax+rax+00h]
0x18001b3da  lea     rbx, xmmword_18002AA30
0x18001b3e1  test    rax, rax
0x18001b3e4  jz      loc_18001AFC5
0x18001b3ea  mov     ecx, esi
0x18001b3ec  sub     ecx, [rax+48h]
0x18001b3ef  cmp     ecx, 5265C0h
0x18001b3f5  jbe     short loc_18001B411
0x18001b3f7  mov     rdx, rax; Buffer
0x18001b3fa  lea     rcx, stru_18002A9C8; Table
0x18001b401  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18001b408  nop     dword ptr [rax+rax+00h]
0x18001b40d  mov     dl, 1
0x18001b40f  jmp     short loc_18001B413
0x18001b411  xor     dl, dl; Restart
0x18001b413  lea     rcx, stru_18002A9C8; Table
0x18001b41a  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18001b421  nop     dword ptr [rax+rax+00h]
0x18001b426  test    rax, rax
0x18001b429  jnz     short loc_18001B3EA
0x18001b42b  jmp     loc_18001AFBE
0x18001b430  mov     ecx, 3
0x18001b435  int     29h; Win8: RtlFailFast(ecx)
0x18001b437  mov     rbx, [rsp+0C0h+arg_0]
0x18001b43f  xor     eax, eax
0x18001b441  add     rsp, 90h
0x18001b448  pop     r15
0x18001b44a  pop     r14
0x18001b44c  pop     r13
0x18001b44e  pop     r12
0x18001b450  pop     rdi
0x18001b451  pop     rsi
0x18001b452  pop     rbp
0x18001b453  retn
```
