# win_musl::FiberThread::ThreadProc(win_mp_lib::null_type)

- ea: `0x180031440`
- end: `0x1800315dc`
- name: `?ThreadProc@FiberThread@win_musl@@AEAAXVnull_type@win_mp_lib@@@Z`
- size: `412`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000531c`
- `0x180031440`
- `0x1800315e4`
- `0x180031600`
- `0x1800680c4`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800315c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800315c4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003145f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003145f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800314d4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800314d4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180031488`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180031571`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180031488`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180031571`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800314a7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800314a7`
- `api-ms-win-core-fibers-l2-1-0!SwitchToFiber` at `0x18003150a`
- `api-ms-win-core-fibers-l2-1-0!SwitchToFiber` at `0x18003150a`
- `api-ms-win-core-fibers-l2-1-0!ConvertThreadToFiber` at `0x180031471`
- `api-ms-win-core-fibers-l2-1-0!ConvertThreadToFiber` at `0x180031471`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall win_musl::FiberThread::ThreadProc(__int64 a1)
{
  HRESULT v2; // eax
  int v3; // edi
  LPVOID v4; // rax
  win_musl::CriticalSection *v5; // rbx
  __int64 v6; // r14
  win_musl::FiberBase *v7; // rbx
  __m128i v8; // xmm6
  unsigned __int64 v9; // xmm0_8
  DWORD LastError; // eax
  __m128i v11; // [rsp+30h] [rbp-48h] BYREF

  v2 = CoInitializeEx(0, 0);
  v3 = -2147221008;
  if ( v2 != -2147221008 )
    v3 = v2;
  v4 = ConvertThreadToFiber(0);
  *(_QWORD *)(a1 + 16) = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1;
    *(_DWORD *)(a1 + 24) = LastError;
  }
  SetEvent(*(HANDLE *)(a1 + 72));
  while ( 1 )
  {
    WaitForSingleObject(*(HANDLE *)(a1 + 88), 0xFFFFFFFF);
    v5 = (win_musl::CriticalSection *)(*(_QWORD *)(a1 + 8) + 16LL);
    win_musl::CriticalSection::Enter(v5);
    if ( *(_BYTE *)(a1 + 28) )
      break;
    if ( v5 )
      win_musl::CriticalSection::Leave(v5);
    v6 = *(_QWORD *)(a1 + 32);
    *(_QWORD *)(a1 + 32) = 0;
    *(_QWORD *)(v6 + 64) = a1;
    SwitchToFiber(*(LPVOID *)(v6 + 32));
    v7 = *(win_musl::FiberBase **)(a1 + 40);
    if ( v7 && dword_1801C4F30 != -1 )
    {
      *(_QWORD *)(a1 + 40) = 0;
      win_musl::FiberBase::ClearFiberState(v7);
      (*(void (__fastcall **)(win_musl::FiberBase *))(*(_QWORD *)v7 + 16LL))(v7);
    }
    if ( *(_QWORD *)(a1 + 48) )
    {
      if ( *(_QWORD *)(a1 + 56) )
      {
        if ( dword_1801C4F30 != -1 )
        {
          v8 = *(__m128i *)(a1 + 48);
          *(_QWORD *)(a1 + 48) = 0;
          *(_QWORD *)(a1 + 56) = 0;
          v11 = v8;
          v9 = _mm_srli_si128(v8, 8).m128i_u64[0];
          SetEvent(*(HANDLE *)(v9 + 16));
          if ( v8.m128i_i64[0] )
          {
            if ( v9 )
              win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v11);
          }
        }
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  if ( v5 )
    win_musl::CriticalSection::Leave(v5);
  if ( v3 >= 0 )
    CoUninitialize();
}

```

## disassembly

```asm
0x180031440  push    rbx
0x180031442  push    rsi
0x180031443  push    rdi
0x180031444  push    r14
0x180031446  sub     rsp, 58h
0x18003144a  mov     [rsp+78h+var_58], 0FFFFFFFFFFFFFFFEh
0x180031453  movaps  [rsp+78h+var_38], xmm6
0x180031458  mov     rsi, rcx
0x18003145b  xor     edx, edx; dwCoInit
0x18003145d  xor     ecx, ecx; pvReserved
0x18003145f  call    cs:__imp_CoInitializeEx
0x180031465  mov     edi, 800401F0h
0x18003146a  cmp     eax, edi
0x18003146c  cmovnz  edi, eax
0x18003146f  xor     ecx, ecx; lpParameter
0x180031471  call    cs:__imp_ConvertThreadToFiber
0x180031477  mov     [rsi+10h], rax
0x18003147b  test    rax, rax
0x18003147e  jz      loc_1800315C4
0x180031484  mov     rcx, [rsi+48h]; hEvent
0x180031488  call    cs:__imp_SetEvent
0x18003148e  jmp     short loc_1800314A0
0x180031490  mov     rax, [r14]
0x180031493  mov     rcx, r14
0x180031496  mov     rax, [rax+10h]
0x18003149a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003149f  nop
0x1800314a0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800314a3  mov     rcx, [rsi+58h]; hHandle
0x1800314a7  call    cs:__imp_WaitForSingleObject
0x1800314ad  mov     rbx, [rsi+8]
0x1800314b1  add     rbx, 10h
0x1800314b5  mov     rcx, rbx; this
0x1800314b8  call    ?Enter@CriticalSection@win_musl@@QEAAXXZ; win_musl::CriticalSection::Enter(void)
0x1800314bd  cmp     byte ptr [rsi+1Ch], 0
0x1800314c1  jz      short loc_1800314E9
0x1800314c3  test    rbx, rbx
0x1800314c6  jz      short loc_1800314D0
0x1800314c8  mov     rcx, rbx; this
0x1800314cb  call    ?Leave@CriticalSection@win_musl@@QEAAXXZ; win_musl::CriticalSection::Leave(void)
0x1800314d0  test    edi, edi
0x1800314d2  js      short loc_1800314DA
0x1800314d4  call    cs:__imp_CoUninitialize
0x1800314da  movaps  xmm6, [rsp+78h+var_38]
0x1800314df  add     rsp, 58h
0x1800314e3  pop     r14
0x1800314e5  pop     rdi
0x1800314e6  pop     rsi
0x1800314e7  pop     rbx
0x1800314e8  retn
0x1800314e9  test    rbx, rbx
0x1800314ec  jz      short loc_1800314F6
0x1800314ee  mov     rcx, rbx; this
0x1800314f1  call    ?Leave@CriticalSection@win_musl@@QEAAXXZ; win_musl::CriticalSection::Leave(void)
0x1800314f6  mov     r14, [rsi+20h]
0x1800314fa  mov     qword ptr [rsi+20h], 0
0x180031502  mov     [r14+40h], rsi
0x180031506  mov     rcx, [r14+20h]; lpFiber
0x18003150a  call    cs:__imp_SwitchToFiber
0x180031510  mov     rbx, [rsi+28h]
0x180031514  test    rbx, rbx
0x180031517  jz      short loc_180031522
0x180031519  cmp     cs:dword_1801C4F30, 0FFFFFFFFh
0x180031520  jnz     short loc_18003159E
0x180031522  cmp     qword ptr [rsi+30h], 0
0x180031527  jz      loc_180031490
0x18003152d  cmp     qword ptr [rsi+38h], 0
0x180031532  jz      loc_180031490
0x180031538  cmp     cs:dword_1801C4F30, 0FFFFFFFFh
0x18003153f  jz      loc_180031490
0x180031545  movups  xmm6, xmmword ptr [rsi+30h]
0x180031549  mov     qword ptr [rsi+30h], 0
0x180031551  mov     qword ptr [rsi+38h], 0
0x180031559  movdqa  [rsp+78h+var_48], xmm6
0x18003155f  movdqa  xmm0, xmm6
0x180031563  psrldq  xmm0, 8
0x180031568  movq    rbx, xmm0
0x18003156d  mov     rcx, [rbx+10h]; hEvent
0x180031571  call    cs:__imp_SetEvent
0x180031577  nop
0x180031578  movq    rax, xmm6
0x18003157d  test    rax, rax
0x180031580  jz      loc_180031490
0x180031586  test    rbx, rbx
0x180031589  jz      loc_180031490
0x18003158f  lea     rcx, [rsp+78h+var_48]
0x180031594  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180031599  jmp     loc_180031490
0x18003159e  mov     qword ptr [rsi+28h], 0
0x1800315a6  mov     rcx, rbx; this
0x1800315a9  call    ?ClearFiberState@FiberBase@win_musl@@IEAAXXZ; win_musl::FiberBase::ClearFiberState(void)
0x1800315ae  nop
0x1800315af  mov     rax, [rbx]
0x1800315b2  mov     rcx, rbx
0x1800315b5  mov     rax, [rax+10h]
0x1800315b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800315be  nop
0x1800315bf  jmp     loc_180031522
0x1800315c4  call    cs:__imp_GetLastError
0x1800315ca  mov     ecx, 1
0x1800315cf  test    eax, eax
0x1800315d1  cmovz   eax, ecx
0x1800315d4  mov     [rsi+18h], eax
0x1800315d7  jmp     loc_180031484
```
