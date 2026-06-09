# QueueHardError

- ea: `0x180001200`
- end: `0x180001534`
- name: `QueueHardError`
- size: `820`
- prototype: `__int64 __fastcall(PVOID BaseAddress)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800097f0`

## callees

- `0x180001200`
- `0x180001aa0`
- `0x180002040`
- `0x18000b010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000125e`
- `ntdll!RtlAllocateHeap` at `0x18000125e`
- `ntdll!RtlFreeHeap` at `0x180001419`
- `ntdll!RtlFreeHeap` at `0x180001419`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1800013ef`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1800014cf`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1800013ef`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1800014cf`
- `ntdll!RtlEnterCriticalSection` at `0x1800012fe`
- `ntdll!RtlEnterCriticalSection` at `0x180001444`
- `ntdll!RtlEnterCriticalSection` at `0x1800012fe`
- `ntdll!RtlEnterCriticalSection` at `0x180001444`
- `ntdll!RtlLeaveCriticalSection` at `0x180001324`
- `ntdll!RtlLeaveCriticalSection` at `0x180001480`
- `ntdll!RtlLeaveCriticalSection` at `0x18000151c`
- `ntdll!RtlLeaveCriticalSection` at `0x180001324`
- `ntdll!RtlLeaveCriticalSection` at `0x180001480`
- `ntdll!RtlLeaveCriticalSection` at `0x18000151c`

## pseudocode

```c
int __fastcall QueueHardError(volatile signed __int32 *BaseAddress, __int64 a2, void *a3)
{
  _QWORD *v3; // rdi
  _QWORD *v4; // rsi
  volatile signed __int32 *v5; // rbp
  signed __int32 v6; // ebx
  _QWORD *Heap; // rax
  char *v8; // rcx
  __int64 v9; // rdx
  _QWORD *v10; // rax
  __int128 v11; // xmm0
  int result; // eax
  __int64 v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // rcx
  void (__fastcall *v16)(volatile signed __int32 *, _QWORD *); // rax
  __int64 v17; // rax
  _QWORD *v18; // rax

  v3 = 0;
  v4 = (_QWORD *)a2;
  v5 = BaseAddress;
  if ( BaseAddress )
    _InterlockedIncrement(BaseAddress + 19);
  *(_DWORD *)(a2 + 60) = 1;
  while ( 1 )
  {
    while ( 1 )
    {
      v6 = dword_18001029C;
      if ( dword_18001029C >= 3 )
        break;
      v13 = (unsigned int)(dword_18001029C + 1);
      if ( v6 == _InterlockedCompareExchange(&dword_18001029C, v13, dword_18001029C) )
      {
        while ( 1 )
        {
          CsrpCheckRequestThreads(v13, a2, a3);
          if ( CsrpStaticThreadCount > 0 )
          {
            v14 = 0;
            do
            {
              v15 = CsrLoadedServerDll[v14];
              if ( v15 )
              {
                v16 = *(void (__fastcall **)(volatile signed __int32 *, _QWORD *))(v15 + 88);
                if ( v16 )
                {
                  v16(v5, v4);
                  if ( *((_DWORD *)v4 + 15) != 1 )
                    break;
                }
              }
              v14 = (unsigned int)(v14 + 1);
            }
            while ( (unsigned int)v14 < 6 );
          }
          _InterlockedIncrement(&CsrpStaticThreadCount);
          if ( *((_DWORD *)v4 + 15) != -1 )
          {
            NtAlpcSendWaitReceivePort(CsrApiPort, 0x10000, v4, 0, 0, 0, 0, 0);
            if ( v5 )
              CsrDereferenceThread((__int64)v5);
          }
          if ( v3 )
            RtlFreeHeap(CsrHeap, 0, v3);
          result = _InterlockedDecrement(&dword_18001029C);
          if ( result < 3 )
            return result;
          RtlEnterCriticalSection(&CsrProcessStructureLock);
          v3 = off_18000F000;
          if ( *((_UNKNOWN ***)off_18000F000 + 1) != &off_18000F000 )
            goto LABEL_34;
          v17 = *(_QWORD *)off_18000F000;
          if ( *(_UNKNOWN **)(*(_QWORD *)off_18000F000 + 8LL) != off_18000F000 )
            goto LABEL_34;
          off_18000F000 = *(_UNKNOWN **)off_18000F000;
          *(_QWORD *)(v17 + 8) = &off_18000F000;
          RtlLeaveCriticalSection(&CsrProcessStructureLock);
          v5 = (volatile signed __int32 *)v3[2];
          v4 = v3 + 3;
        }
      }
    }
    if ( !v3 )
    {
      if ( dword_18001029C > 100 || (Heap = RtlAllocateHeap(CsrHeap, 0, 0x3D0u), (v3 = Heap) == 0) )
      {
        result = NtAlpcSendWaitReceivePort(CsrApiPort, 0x10000, v4, 0, 0, 0, 0, 0);
        if ( v5 )
          return CsrDereferenceThread((__int64)v5);
        return result;
      }
      v8 = (char *)(Heap + 3);
      v9 = 7;
      v10 = v4;
      do
      {
        v8 += 128;
        v11 = *(_OWORD *)v10;
        v10 += 16;
        *((_OWORD *)v8 - 8) = v11;
        *((_OWORD *)v8 - 7) = *((_OWORD *)v10 - 7);
        *((_OWORD *)v8 - 6) = *((_OWORD *)v10 - 6);
        *((_OWORD *)v8 - 5) = *((_OWORD *)v10 - 5);
        *((_OWORD *)v8 - 4) = *((_OWORD *)v10 - 4);
        *((_OWORD *)v8 - 3) = *((_OWORD *)v10 - 3);
        *((_OWORD *)v8 - 2) = *((_OWORD *)v10 - 2);
        *((_OWORD *)v8 - 1) = *((_OWORD *)v10 - 1);
        --v9;
      }
      while ( v9 );
      *(_OWORD *)v8 = *(_OWORD *)v10;
      *((_OWORD *)v8 + 1) = *((_OWORD *)v10 + 1);
      *((_OWORD *)v8 + 2) = *((_OWORD *)v10 + 2);
      *((_QWORD *)v8 + 6) = v10[6];
      v3[2] = v5;
    }
    RtlEnterCriticalSection(&CsrProcessStructureLock);
    if ( v6 == _InterlockedCompareExchange(&dword_18001029C, v6 + 1, v6) )
      break;
    result = RtlLeaveCriticalSection(&CsrProcessStructureLock);
    if ( !v3 )
      return result;
  }
  v18 = off_18000F008;
  if ( *off_18000F008 != (_UNKNOWN *)&off_18000F000 )
LABEL_34:
    __fastfail(3u);
  *v3 = &off_18000F000;
  v3[1] = v18;
  *v18 = v3;
  off_18000F008 = (_UNKNOWN **)v3;
  return RtlLeaveCriticalSection(&CsrProcessStructureLock);
}

```

## disassembly

```asm
0x180001200  mov     [rsp+arg_10], rbx
0x180001205  push    rbp
0x180001206  push    rsi
0x180001207  push    rdi
0x180001208  sub     rsp, 40h
0x18000120c  xor     edi, edi
0x18000120e  mov     rsi, rdx
0x180001211  mov     rbp, rcx
0x180001214  test    rcx, rcx
0x180001217  jz      short loc_18000121D
0x180001219  lock inc dword ptr [rcx+4Ch]
0x18000121d  mov     [rsp+58h+arg_0], r14
0x180001222  mov     [rsp+58h+arg_8], r15
0x180001227  mov     dword ptr [rdx+3Ch], 1
0x18000122e  mov     ebx, cs:dword_18001029C
0x180001234  cmp     ebx, 3
0x180001237  jl      loc_180001351
0x18000123d  test    rdi, rdi
0x180001240  jnz     loc_1800012F7
0x180001246  cmp     ebx, 64h ; 'd'
0x180001249  jg      loc_180001499
0x18000124f  mov     rcx, cs:CsrHeap; HeapHandle
0x180001256  xor     edx, edx; Flags
0x180001258  mov     r8d, 3D0h; Size
0x18000125e  call    cs:__imp_RtlAllocateHeap
0x180001265  nop     dword ptr [rax+rax+00h]
0x18000126a  mov     rdi, rax
0x18000126d  test    rax, rax
0x180001270  jz      loc_180001499
0x180001276  lea     rcx, [rax+18h]
0x18000127a  mov     edx, 7
0x18000127f  mov     rax, rsi
0x180001282  lea     rcx, [rcx+80h]
0x180001289  movups  xmm0, xmmword ptr [rax]
0x18000128c  lea     rax, [rax+80h]
0x180001293  movups  xmmword ptr [rcx-80h], xmm0
0x180001297  movups  xmm1, xmmword ptr [rax-70h]
0x18000129b  movups  xmmword ptr [rcx-70h], xmm1
0x18000129f  movups  xmm0, xmmword ptr [rax-60h]
0x1800012a3  movups  xmmword ptr [rcx-60h], xmm0
0x1800012a7  movups  xmm1, xmmword ptr [rax-50h]
0x1800012ab  movups  xmmword ptr [rcx-50h], xmm1
0x1800012af  movups  xmm0, xmmword ptr [rax-40h]
0x1800012b3  movups  xmmword ptr [rcx-40h], xmm0
0x1800012b7  movups  xmm1, xmmword ptr [rax-30h]
0x1800012bb  movups  xmmword ptr [rcx-30h], xmm1
0x1800012bf  movups  xmm0, xmmword ptr [rax-20h]
0x1800012c3  movups  xmmword ptr [rcx-20h], xmm0
0x1800012c7  movups  xmm1, xmmword ptr [rax-10h]
0x1800012cb  movups  xmmword ptr [rcx-10h], xmm1
0x1800012cf  sub     rdx, 1
0x1800012d3  jnz     short loc_180001282
0x1800012d5  movups  xmm0, xmmword ptr [rax]
0x1800012d8  movups  xmmword ptr [rcx], xmm0
0x1800012db  movups  xmm1, xmmword ptr [rax+10h]
0x1800012df  movups  xmmword ptr [rcx+10h], xmm1
0x1800012e3  movups  xmm0, xmmword ptr [rax+20h]
0x1800012e7  movups  xmmword ptr [rcx+20h], xmm0
0x1800012eb  mov     rax, [rax+30h]
0x1800012ef  mov     [rcx+30h], rax
0x1800012f3  mov     [rdi+10h], rbp
0x1800012f7  lea     rcx, CsrProcessStructureLock; CriticalSection
0x1800012fe  call    cs:__imp_RtlEnterCriticalSection
0x180001305  nop     dword ptr [rax+rax+00h]
0x18000130a  lea     ecx, [rbx+1]
0x18000130d  mov     eax, ebx
0x18000130f  lock cmpxchg cs:dword_18001029C, ecx
0x180001317  jz      loc_1800014F1
0x18000131d  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180001324  call    cs:__imp_RtlLeaveCriticalSection
0x18000132b  nop     dword ptr [rax+rax+00h]
0x180001330  test    rdi, rdi
0x180001333  jnz     loc_18000122E
0x180001339  mov     r15, [rsp+58h+arg_8]
0x18000133e  mov     r14, [rsp+58h+arg_0]
0x180001343  mov     rbx, [rsp+58h+arg_10]
0x180001348  add     rsp, 40h
0x18000134c  pop     rdi
0x18000134d  pop     rsi
0x18000134e  pop     rbp
0x18000134f  retn
0x180001351  lea     ecx, [rbx+1]
0x180001354  mov     eax, ebx
0x180001356  lock cmpxchg cs:dword_18001029C, ecx
0x18000135e  jnz     loc_18000122E
0x180001364  lea     r14, off_18000F000
0x18000136b  lea     r15, CsrLoadedServerDll
0x180001372  call    CsrpCheckRequestThreads
0x180001377  cmp     cs:CsrpStaticThreadCount, 0
0x18000137e  jle     short loc_1800013AC
0x180001380  xor     ebx, ebx
0x180001382  mov     rcx, [r15+rbx*8]
0x180001386  test    rcx, rcx
0x180001389  jz      short loc_1800013A5
0x18000138b  mov     rax, [rcx+58h]
0x18000138f  test    rax, rax
0x180001392  jz      short loc_1800013A5
0x180001394  mov     rdx, rsi
0x180001397  mov     rcx, rbp
0x18000139a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000139f  cmp     dword ptr [rsi+3Ch], 1
0x1800013a3  jnz     short loc_1800013AC
0x1800013a5  inc     ebx
0x1800013a7  cmp     ebx, 6
0x1800013aa  jb      short loc_180001382
0x1800013ac  lock inc cs:CsrpStaticThreadCount
0x1800013b3  cmp     dword ptr [rsi+3Ch], 0FFFFFFFFh
0x1800013b7  jz      short loc_180001408
0x1800013b9  mov     rcx, cs:CsrApiPort
0x1800013c0  xor     r9d, r9d
0x1800013c3  mov     [rsp+58h+var_20], 0
0x1800013cc  mov     r8, rsi
0x1800013cf  mov     [rsp+58h+var_28], 0
0x1800013d8  mov     edx, 10000h
0x1800013dd  mov     [rsp+58h+var_30], 0
0x1800013e6  mov     [rsp+58h+var_38], 0
0x1800013ef  call    cs:__imp_NtAlpcSendWaitReceivePort
0x1800013f6  nop     dword ptr [rax+rax+00h]
0x1800013fb  test    rbp, rbp
0x1800013fe  jz      short loc_180001408
0x180001400  mov     rcx, rbp; BaseAddress
0x180001403  call    CsrDereferenceThread
0x180001408  test    rdi, rdi
0x18000140b  jz      short loc_180001425
0x18000140d  mov     rcx, cs:CsrHeap; HeapHandle
0x180001414  mov     r8, rdi; BaseAddress
0x180001417  xor     edx, edx; Flags
0x180001419  call    cs:__imp_RtlFreeHeap
0x180001420  nop     dword ptr [rax+rax+00h]
0x180001425  mov     eax, 0FFFFFFFFh
0x18000142a  lock xadd cs:dword_18001029C, eax
0x180001432  dec     eax
0x180001434  cmp     eax, 3
0x180001437  jl      loc_180001339
0x18000143d  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180001444  call    cs:__imp_RtlEnterCriticalSection
0x18000144b  nop     dword ptr [rax+rax+00h]
0x180001450  mov     rdi, cs:off_18000F000
0x180001457  cmp     [rdi+8], r14
0x18000145b  jnz     loc_18000152D
0x180001461  mov     rax, [rdi]
0x180001464  cmp     [rax+8], rdi
0x180001468  jnz     loc_18000152D
0x18000146e  mov     cs:off_18000F000, rax
0x180001475  lea     rcx, CsrProcessStructureLock; CriticalSection
0x18000147c  mov     [rax+8], r14
0x180001480  call    cs:__imp_RtlLeaveCriticalSection
0x180001487  nop     dword ptr [rax+rax+00h]
0x18000148c  mov     rbp, [rdi+10h]
0x180001490  lea     rsi, [rdi+18h]
0x180001494  jmp     loc_180001372
0x180001499  mov     rcx, cs:CsrApiPort
0x1800014a0  xor     r9d, r9d
0x1800014a3  mov     [rsp+58h+var_20], 0
0x1800014ac  mov     r8, rsi
0x1800014af  mov     [rsp+58h+var_28], 0
0x1800014b8  mov     edx, 10000h
0x1800014bd  mov     [rsp+58h+var_30], 0
0x1800014c6  mov     [rsp+58h+var_38], 0
0x1800014cf  call    cs:__imp_NtAlpcSendWaitReceivePort
0x1800014d6  nop     dword ptr [rax+rax+00h]
0x1800014db  test    rbp, rbp
0x1800014de  jz      loc_180001339
0x1800014e4  mov     rcx, rbp; BaseAddress
0x1800014e7  call    CsrDereferenceThread
0x1800014ec  jmp     loc_180001339
0x1800014f1  mov     rax, cs:off_18000F008
0x1800014f8  lea     r14, off_18000F000
0x1800014ff  cmp     [rax], r14
0x180001502  jnz     short loc_18000152D
0x180001504  mov     [rdi], r14
0x180001507  lea     rcx, CsrProcessStructureLock; CriticalSection
0x18000150e  mov     [rdi+8], rax
0x180001512  mov     [rax], rdi
0x180001515  mov     cs:off_18000F008, rdi
0x18000151c  call    cs:__imp_RtlLeaveCriticalSection
0x180001523  nop     dword ptr [rax+rax+00h]
0x180001528  jmp     loc_180001339
0x18000152d  mov     ecx, 3
0x180001532  int     29h; Win8: RtlFailFast(ecx)
```
