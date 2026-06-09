# LRPC_CASSOCIATION::~LRPC_CASSOCIATION(void)

- ea: `0x18004c684`
- end: `0x18004c87e`
- name: `??1LRPC_CASSOCIATION@@UEAA@XZ`
- size: `506`
- prototype: `void __fastcall(LRPC_CASSOCIATION *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callers

- `0x18004c4d0`
- `0x1800b8d30`

## callees

- `0x180021ce0`
- `0x180022870`
- `0x1800274e0`
- `0x180028d40`
- `0x180030af8`
- `0x18004a8c8`
- `0x18004c684`
- `0x18004c884`
- `0x18004cdec`
- `0x180087cbc`
- `0x1800b8288`
- `0x1800d2010`

## import_xrefs

- `ntdll!NtClose` at `0x18004c78b`
- `ntdll!NtClose` at `0x18004c78b`
- `ntdll!RtlDeleteCriticalSection` at `0x18004c838`
- `ntdll!RtlDeleteCriticalSection` at `0x18004c838`

## pseudocode

```c
void __fastcall LRPC_CASSOCIATION::~LRPC_CASSOCIATION(LRPC_CASSOCIATION *this)
{
  int v2; // ecx
  LRPC_CASSOCIATION *v3; // rsi
  LRPC_CASSOCIATION *v4; // rbx
  void *v5; // rcx
  unsigned int i; // eax
  __int64 v7; // rcx
  unsigned int v8; // esi
  __int64 v9; // rax
  void *v10; // rdx
  int v11; // ecx
  unsigned int v12; // edx
  RPC_THREAD_POOL_ALPC *v13; // rcx
  LRPC_CASSOCIATION *v14; // rcx
  char *v15; // rbx
  void *v16; // rcx
  LRPC_CASSOCIATION *v17; // rcx
  LRPC_BROKEN_PIPE_DATA *v18; // rbp
  unsigned int v19; // edx
  int v20; // [rsp+28h] [rbp-40h]
  int v21; // [rsp+30h] [rbp-38h]

  *(_QWORD *)this = &LRPC_CASSOCIATION::`vftable';
  v2 = *((_DWORD *)this + 19) - 2;
  if ( v2 )
  {
    v11 = v2 - 2;
    if ( !v11 )
    {
LABEL_19:
      LRPC_CASSOCIATION::TrimCachedViews(this, 1);
      LogEvent(0x4Cu, 0x64u, *((void **)this + 17), 0, 0, v20, v21);
      NtClose(*((HANDLE *)this + 17));
      v13 = (RPC_THREAD_POOL_ALPC *)*((_QWORD *)this + 29);
      *((_QWORD *)this + 17) = 0;
      *((_DWORD *)this + 82) = -1;
      if ( v13 )
      {
        RPC_THREAD_POOL_ALPC::`scalar deleting destructor'(v13, v12);
        *((_QWORD *)this + 29) = 0;
      }
      goto LABEL_5;
    }
    if ( v11 != 1 )
      goto LABEL_5;
  }
  if ( *((_QWORD *)this + 36) )
  {
    FreeEEInfoChain();
    *((_QWORD *)this + 36) = 0;
  }
  if ( *((_DWORD *)this + 19) != 2 )
    goto LABEL_19;
LABEL_5:
  v3 = (LRPC_CASSOCIATION *)*((_QWORD *)this + 38);
  while ( v3 != (LRPC_CASSOCIATION *)((char *)this + 304) )
  {
    v14 = v3;
    v15 = (char *)v3 - 24;
    v3 = *(LRPC_CASSOCIATION **)v3;
    RpcpfRemoveEntryListAndZeroOutLinks(v14);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v15 + 32LL))(v15);
  }
  v4 = (LRPC_CASSOCIATION *)*((_QWORD *)this + 45);
  while ( v4 != (LRPC_CASSOCIATION *)((char *)this + 360) )
  {
    v17 = v4;
    v18 = (LRPC_CASSOCIATION *)((char *)v4 - 24);
    v4 = *(LRPC_CASSOCIATION **)v4;
    RpcpfRemoveEntryListAndZeroOutLinks(v17);
    if ( v18 )
      LRPC_BROKEN_PIPE_DATA::`scalar deleting destructor'(v18, v19);
  }
  v5 = (void *)*((_QWORD *)this + 42);
  if ( v5 )
  {
    FreeWrapper(v5);
    *((_QWORD *)this + 42) = 0;
  }
  for ( i = 0; i < *((_DWORD *)this + 24); i = v8 )
  {
    v7 = i;
    v8 = i + 1;
    v9 = *((_QWORD *)this + 11);
    v10 = *(void **)(v9 + 8 * v7);
    if ( v10 )
    {
      --*((_DWORD *)this + 25);
      *(_QWORD *)(v9 + 8 * v7) = 0;
      FreeWrapper(v10);
    }
  }
  v16 = (void *)*((_QWORD *)this + 10);
  if ( v16 )
  {
    FreeWrapper(v16);
    *((_QWORD *)this + 10) = 0;
  }
  if ( dword_1800F9624 )
    LogEventToEtw(0x61u, 0x64u, (__int64)this, 0, 0);
  LPC_NORMALIZED_SID::FreeOldSid((LRPC_CASSOCIATION *)((char *)this + 192));
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 144));
  QUEUE::~QUEUE((LRPC_CASSOCIATION *)((char *)this + 88));
  *((_DWORD *)this + 2) = -1713459815;
}

```

## disassembly

```asm
0x18004c684  push    rbx
0x18004c686  push    rbp
0x18004c687  push    rsi
0x18004c688  push    rdi
0x18004c689  push    r14
0x18004c68b  sub     rsp, 40h
0x18004c68f  mov     rdi, rcx
0x18004c692  lea     rax, ??_7LRPC_CASSOCIATION@@6B@; const LRPC_CASSOCIATION::`vftable'
0x18004c699  mov     [rcx], rax
0x18004c69c  mov     ecx, [rcx+4Ch]
0x18004c69f  sub     ecx, 2
0x18004c6a2  jnz     loc_18004C748
0x18004c6a8  mov     rcx, [rdi+120h]
0x18004c6af  test    rcx, rcx
0x18004c6b2  jz      short loc_18004C6C4
0x18004c6b4  call    FreeEEInfoChain
0x18004c6b9  mov     qword ptr [rdi+120h], 0
0x18004c6c4  cmp     dword ptr [rdi+4Ch], 2
0x18004c6c8  jnz     loc_18004C75B
0x18004c6ce  lea     r14, [rdi+130h]
0x18004c6d5  mov     rsi, [r14]
0x18004c6d8  cmp     rsi, r14
0x18004c6db  jnz     loc_18004C7CB
0x18004c6e1  lea     rsi, [rdi+168h]
0x18004c6e8  mov     rbx, [rsi]
0x18004c6eb  cmp     rbx, rsi
0x18004c6ee  jnz     loc_18004C859
0x18004c6f4  mov     rcx, [rdi+150h]; lpMem
0x18004c6fb  test    rcx, rcx
0x18004c6fe  jnz     short loc_18004C736
0x18004c700  xor     eax, eax
0x18004c702  cmp     eax, [rdi+60h]
0x18004c705  jnb     loc_18004C7EE
0x18004c70b  mov     ecx, eax
0x18004c70d  lea     esi, [rax+1]
0x18004c710  mov     rax, [rdi+58h]
0x18004c714  mov     rdx, [rax+rcx*8]
0x18004c718  test    rdx, rdx
0x18004c71b  jnz     short loc_18004C721
0x18004c71d  mov     eax, esi
0x18004c71f  jmp     short loc_18004C702
0x18004c721  dec     dword ptr [rdi+64h]
0x18004c724  mov     qword ptr [rax+rcx*8], 0
0x18004c72c  mov     rcx, rdx; lpMem
0x18004c72f  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18004c734  jmp     short loc_18004C71D
0x18004c736  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18004c73b  mov     qword ptr [rdi+150h], 0
0x18004c746  jmp     short loc_18004C700
0x18004c748  sub     ecx, 2
0x18004c74b  jz      short loc_18004C75B
0x18004c74d  cmp     ecx, 1
0x18004c750  jnz     loc_18004C6CE
0x18004c756  jmp     loc_18004C6A8
0x18004c75b  mov     edx, 1; int
0x18004c760  mov     rcx, rdi; this
0x18004c763  call    ?TrimCachedViews@LRPC_CASSOCIATION@@AEAAXH@Z; LRPC_CASSOCIATION::TrimCachedViews(int)
0x18004c768  mov     r8, [rdi+88h]; void *
0x18004c76f  xor     r9d, r9d; void *
0x18004c772  mov     dl, 64h ; 'd'; unsigned __int8
0x18004c774  mov     [rsp+68h+var_48], 0; unsigned __int64
0x18004c77d  mov     cl, 4Ch ; 'L'; unsigned __int8
0x18004c77f  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x18004c784  mov     rcx, [rdi+88h]; Handle
0x18004c78b  call    cs:__imp_NtClose
0x18004c791  mov     rcx, [rdi+0E8h]; this
0x18004c798  mov     qword ptr [rdi+88h], 0
0x18004c7a3  mov     dword ptr [rdi+148h], 0FFFFFFFFh
0x18004c7ad  test    rcx, rcx
0x18004c7b0  jz      loc_18004C6CE
0x18004c7b6  call    ??_GRPC_THREAD_POOL_ALPC@@QEAAPEAXI@Z; RPC_THREAD_POOL_ALPC::`scalar deleting destructor'(uint)
0x18004c7bb  mov     qword ptr [rdi+0E8h], 0
0x18004c7c6  jmp     loc_18004C6CE
0x18004c7cb  mov     rcx, rsi
0x18004c7ce  lea     rbx, [rsi-18h]
0x18004c7d2  mov     rsi, [rsi]
0x18004c7d5  call    RpcpfRemoveEntryListAndZeroOutLinks
0x18004c7da  mov     rax, [rbx]
0x18004c7dd  mov     rcx, rbx
0x18004c7e0  mov     rax, [rax+20h]
0x18004c7e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c7e9  jmp     loc_18004C6D8
0x18004c7ee  mov     rcx, [rdi+50h]; lpMem
0x18004c7f2  test    rcx, rcx
0x18004c7f5  jz      short loc_18004C804
0x18004c7f7  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18004c7fc  mov     qword ptr [rdi+50h], 0
0x18004c804  cmp     cs:dword_1800F9624, 0
0x18004c80b  jz      short loc_18004C825
0x18004c80d  xor     r9d, r9d; __int64
0x18004c810  mov     [rsp+68h+var_48], 0; __int64
0x18004c819  mov     r8, rdi; __int64
0x18004c81c  mov     dl, 64h ; 'd'; unsigned __int8
0x18004c81e  mov     cl, 61h ; 'a'; unsigned __int8
0x18004c820  call    ?LogEventToEtw@@YAXEE_J00@Z; LogEventToEtw(uchar,uchar,__int64,__int64,__int64)
0x18004c825  lea     rcx, [rdi+0C0h]; this
0x18004c82c  call    ?FreeOldSid@LPC_NORMALIZED_SID@@AEAAXXZ; LPC_NORMALIZED_SID::FreeOldSid(void)
0x18004c831  lea     rcx, [rdi+90h]; CriticalSection
0x18004c838  call    cs:__imp_RtlDeleteCriticalSection
0x18004c83e  lea     rcx, [rdi+58h]; this
0x18004c842  call    ??1QUEUE@@QEAA@XZ; QUEUE::~QUEUE(void)
0x18004c847  mov     dword ptr [rdi+8], 99DEAD99h
0x18004c84e  add     rsp, 40h
0x18004c852  pop     r14
0x18004c854  pop     rdi
0x18004c855  pop     rsi
0x18004c856  pop     rbp
0x18004c857  pop     rbx
0x18004c858  retn
0x18004c859  mov     rcx, rbx
0x18004c85c  lea     rbp, [rbx-18h]
0x18004c860  mov     rbx, [rbx]
0x18004c863  call    RpcpfRemoveEntryListAndZeroOutLinks
0x18004c868  test    rbp, rbp
0x18004c86b  jz      loc_18004C6EB
0x18004c871  mov     rcx, rbp; this
0x18004c874  call    ??_GLRPC_BROKEN_PIPE_DATA@@QEAAPEAXI@Z; LRPC_BROKEN_PIPE_DATA::`scalar deleting destructor'(uint)
0x18004c879  jmp     loc_18004C6EB
```
