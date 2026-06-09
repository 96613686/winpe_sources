# LRPC_CCALL::ReinitCachedCall(_RPC_CLIENT_INTERFACE *,LRPC_CAUSAL_FLOW *)

- ea: `0x180019ae4`
- end: `0x180019cfe`
- name: `?ReinitCachedCall@LRPC_CCALL@@QEAAJPEAU_RPC_CLIENT_INTERFACE@@PEAVLRPC_CAUSAL_FLOW@@@Z`
- size: `538`
- prototype: `__int64 __fastcall(LRPC_CCALL *__hidden this, struct _RPC_CLIENT_INTERFACE *, struct LRPC_CAUSAL_FLOW *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800a05d0`

## callees

- `0x180019ae4`
- `0x18001b00c`
- `0x18001d65c`
- `0x1800283bc`
- `0x180028a00`
- `0x18002b7c0`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x180019bba`
- `ntdll!NtOpenThreadToken` at `0x180019bba`
- `ntdll!RtlLeaveCriticalSection` at `0x180019c5b`
- `ntdll!RtlLeaveCriticalSection` at `0x180019c5b`
- `ntdll!RtlEnterCriticalSection` at `0x180019c2b`
- `ntdll!RtlEnterCriticalSection` at `0x180019c2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180019ba4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180019ba4`

## pseudocode

```c
__int64 __fastcall LRPC_CCALL::ReinitCachedCall(
        LRPC_CCALL *this,
        struct _RPC_CLIENT_INTERFACE *a2,
        struct LRPC_CAUSAL_FLOW *a3)
{
  __int64 v3; // r9
  struct LRPC_CAUSAL_FLOW *v4; // rsi
  signed __int32 v6; // eax
  _QWORD *v7; // rcx
  unsigned int v8; // ebx
  _QWORD *v10; // rbx
  __int64 *v11; // r14
  HANDLE CurrentThread; // rax
  NTSTATUS v13; // eax
  __int64 v14; // rax
  unsigned int i; // ecx
  struct LRPC_CAUSAL_FLOW **v16; // r8
  signed __int32 v17[8]; // [rsp+0h] [rbp-88h] BYREF
  _DWORD v18[18]; // [rsp+40h] [rbp-48h] BYREF

  v3 = *((_QWORD *)this + 35);
  v4 = a3;
  v6 = _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 188), 1u);
  *((_QWORD *)this + 80) = a2;
  *((_DWORD *)this + 73) = v6 + 1;
  *((_DWORD *)this + 168) = 0;
  *((_DWORD *)this + 176) = -1073606632;
  v7 = (_QWORD *)*((_QWORD *)this + 89);
  if ( v7 )
  {
    do
    {
      v10 = (_QWORD *)*v7;
      FreeEEInfoRecord(v7);
      v7 = v10;
    }
    while ( v10 );
    *((_QWORD *)this + 89) = 0;
  }
  *((_QWORD *)this + 85) = 0;
  *((_QWORD *)this + 74) = 0;
  *((_DWORD *)this + 198) = 0;
  *((_DWORD *)this + 75) = 0;
  if ( (*((_DWORD *)this + 72) & 2) == 0 )
  {
    REFERENCED_OBJECT::SingleThreadedAddReference(this);
    return 0;
  }
  v8 = 0;
  if ( *(_DWORD *)(*((_QWORD *)this + 34) + 416LL) != 1 )
    goto LABEL_12;
  v11 = (__int64 *)((char *)this + 800);
  CurrentThread = GetCurrentThread();
  v8 = 14;
  v13 = NtOpenThreadToken(CurrentThread, 0xEu, 1u, (PHANDLE)this + 100);
  switch ( v13 )
  {
    case -1073741700:
      v14 = 4294967293LL;
LABEL_10:
      *v11 = v14;
LABEL_11:
      v8 = 0;
LABEL_12:
      *((_DWORD *)this + 4) += 2;
      _InterlockedOr(v17, 0);
      if ( dword_1800F9624 )
      {
        for ( i = 0; i < 4; ++i )
        {
          a3 = (struct LRPC_CAUSAL_FLOW *)"HbBr";
          if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[i] == 114 )
            goto LABEL_19;
        }
        if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
        {
          LOBYTE(v3) = 43;
          LOBYTE(a3) = 114;
          McTemplateU0uuxxx_EtwEventWriteTransfer(
            *((_DWORD *)this + 3),
            *((_DWORD *)this + 4),
            (_DWORD)a3,
            v3,
            (char)this,
            *((_DWORD *)this + 3),
            *((_DWORD *)this + 4));
        }
      }
      goto LABEL_19;
    case -1073741790:
      v8 = 5;
      break;
    case -1073741658:
      v14 = 4294967294LL;
      goto LABEL_10;
    case 0:
      goto LABEL_11;
  }
  *v11 = 0;
  v18[2] = v13;
  v18[0] = 3;
  RpcpErrorAddRecord(2u, v8, 0x460u, 1, (struct tagParam *)v18);
LABEL_19:
  if ( v4 )
  {
    _InterlockedAnd((volatile signed __int32 *)this + 72, 0xFFFFFBFF);
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)v4 + 2);
    v16 = (struct LRPC_CAUSAL_FLOW **)*((_QWORD *)v4 + 16);
    if ( *v16 != (struct LRPC_CAUSAL_FLOW *)((char *)v4 + 120) )
      __fastfail(3u);
    *((_QWORD *)this + 102) = (char *)v4 + 120;
    *((_QWORD *)this + 103) = v16;
    *v16 = (LRPC_CCALL *)((char *)this + 816);
    *((_QWORD *)v4 + 16) = (char *)this + 816;
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v4 + 2);
    REFERENCED_OBJECT::AddReference(v4);
    *((_QWORD *)this + 70) = v4;
  }
  return v8;
}

```

## disassembly

```asm
0x180019ae4  push    rbx
0x180019ae6  push    rbp
0x180019ae7  push    rsi
0x180019ae8  push    rdi
0x180019ae9  push    r14
0x180019aeb  sub     rsp, 60h
0x180019aef  mov     r9, [rcx+118h]
0x180019af6  mov     rsi, r8
0x180019af9  mov     rdi, rcx
0x180019afc  mov     eax, 1
0x180019b01  lock xadd [r9+0BCh], eax
0x180019b0a  mov     [rcx+280h], rdx
0x180019b11  inc     eax
0x180019b13  mov     [rcx+124h], eax
0x180019b19  xor     ebp, ebp
0x180019b1b  mov     [rcx+2A0h], ebp
0x180019b21  mov     dword ptr [rcx+2C0h], 0C0021018h
0x180019b2b  mov     rcx, [rcx+2C8h]; lpMem
0x180019b32  test    rcx, rcx
0x180019b35  jnz     short loc_180019B72
0x180019b37  mov     [rdi+2A8h], rbp
0x180019b3e  mov     [rdi+250h], rbp
0x180019b45  mov     [rdi+318h], ebp
0x180019b4b  mov     [rdi+12Ch], ebp
0x180019b51  mov     eax, [rdi+120h]
0x180019b57  test    al, 2
0x180019b59  jnz     short loc_180019B8B
0x180019b5b  mov     rcx, rdi; this
0x180019b5e  call    ?SingleThreadedAddReference@REFERENCED_OBJECT@@QEAAXXZ; REFERENCED_OBJECT::SingleThreadedAddReference(void)
0x180019b63  mov     ebx, ebp
0x180019b65  mov     eax, ebx
0x180019b67  add     rsp, 60h
0x180019b6b  pop     r14
0x180019b6d  pop     rdi
0x180019b6e  pop     rsi
0x180019b6f  pop     rbp
0x180019b70  pop     rbx
0x180019b71  retn
0x180019b72  mov     rbx, [rcx]
0x180019b75  call    FreeEEInfoRecord
0x180019b7a  mov     rcx, rbx
0x180019b7d  test    rbx, rbx
0x180019b80  jnz     short loc_180019B72
0x180019b82  mov     [rdi+2C8h], rbp
0x180019b89  jmp     short loc_180019B37
0x180019b8b  mov     rax, [rdi+110h]
0x180019b92  mov     ebx, ebp
0x180019b94  cmp     dword ptr [rax+1A0h], 1
0x180019b9b  jnz     short loc_180019BD5
0x180019b9d  lea     r14, [rdi+320h]
0x180019ba4  call    cs:__imp_GetCurrentThread
0x180019baa  mov     ebx, 0Eh
0x180019baf  mov     r9, r14; TokenHandle
0x180019bb2  mov     edx, ebx; DesiredAccess
0x180019bb4  mov     rcx, rax; ThreadHandle
0x180019bb7  mov     r8b, 1; OpenAsSelf
0x180019bba  call    cs:__imp_NtOpenThreadToken
0x180019bc0  cmp     eax, 0C000007Ch
0x180019bc5  jnz     loc_180019C98
0x180019bcb  mov     eax, 0FFFFFFFDh
0x180019bd0  mov     [r14], rax
0x180019bd3  mov     ebx, ebp
0x180019bd5  mov     eax, [rdi+10h]
0x180019bd8  add     eax, 2
0x180019bdb  mov     [rdi+10h], eax
0x180019bde  lock or [rsp+88h+var_88], ebp
0x180019be2  movsxd  rdx, dword ptr [rdi+10h]
0x180019be6  cmp     cs:dword_1800F9624, ebp
0x180019bec  jz      short loc_180019C13
0x180019bee  mov     ecx, ebp
0x180019bf0  cmp     ecx, 4
0x180019bf3  jnb     short loc_180019C0A
0x180019bf5  movsxd  rax, ecx
0x180019bf8  lea     r8, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x180019bff  cmp     byte ptr [rax+r8], 72h ; 'r'
0x180019c04  jz      short loc_180019C13
0x180019c06  inc     ecx
0x180019c08  jmp     short loc_180019BF0
0x180019c0a  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x180019c11  jnz     short loc_180019C75
0x180019c13  test    rsi, rsi
0x180019c16  jz      loc_180019B65
0x180019c1c  lock and dword ptr [rdi+120h], 0FFFFFBFFh
0x180019c27  lea     rcx, [rsi+50h]; CriticalSection
0x180019c2b  call    cs:__imp_RtlEnterCriticalSection
0x180019c31  lea     rdx, [rsi+78h]
0x180019c35  mov     r8, [rdx+8]
0x180019c39  cmp     [r8], rdx
0x180019c3c  jnz     loc_180019CF7
0x180019c42  lea     rax, [rdi+330h]
0x180019c49  mov     [rax], rdx
0x180019c4c  lea     rcx, [rsi+50h]; CriticalSection
0x180019c50  mov     [rax+8], r8
0x180019c54  mov     [r8], rax
0x180019c57  mov     [rdx+8], rax
0x180019c5b  call    cs:__imp_RtlLeaveCriticalSection
0x180019c61  mov     rcx, rsi; this
0x180019c64  call    ?AddReference@REFERENCED_OBJECT@@QEAAHXZ; REFERENCED_OBJECT::AddReference(void)
0x180019c69  mov     [rdi+230h], rsi
0x180019c70  jmp     loc_180019B65
0x180019c75  movsxd  rcx, dword ptr [rdi+0Ch]
0x180019c79  mov     r9b, 2Bh ; '+'
0x180019c7c  mov     [rsp+88h+var_58], rdx
0x180019c81  mov     r8b, 72h ; 'r'
0x180019c84  mov     [rsp+88h+var_60], rcx
0x180019c89  mov     [rsp+88h+var_68], rdi
0x180019c8e  call    McTemplateU0uuxxx_EtwEventWriteTransfer
0x180019c93  jmp     loc_180019C13
0x180019c98  cmp     eax, 0C0000022h
0x180019c9d  jz      short loc_180019CBA
0x180019c9f  cmp     eax, 0C00000A6h
0x180019ca4  jz      short loc_180019CB0
0x180019ca6  test    eax, eax
0x180019ca8  jz      loc_180019BD3
0x180019cae  jmp     short loc_180019CBF
0x180019cb0  mov     eax, 0FFFFFFFEh
0x180019cb5  jmp     loc_180019BD0
0x180019cba  mov     ebx, 5
0x180019cbf  mov     rcx, rbp
0x180019cc2  mov     r9d, 1; int
0x180019cc8  mov     [r14], rcx
0x180019ccb  mov     r8d, 460h; unsigned __int16
0x180019cd1  mov     [rsp+88h+var_40], eax
0x180019cd5  mov     edx, ebx; int
0x180019cd7  lea     rax, [rsp+88h+var_48]
0x180019cdc  mov     [rsp+88h+var_48], 3
0x180019ce4  lea     ecx, [r9+1]; unsigned int
0x180019ce8  mov     [rsp+88h+var_68], rax; struct tagParam *
0x180019ced  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180019cf2  jmp     loc_180019C13
0x180019cf7  mov     ecx, 3
0x180019cfc  int     29h; Win8: RtlFailFast(ecx)
```
