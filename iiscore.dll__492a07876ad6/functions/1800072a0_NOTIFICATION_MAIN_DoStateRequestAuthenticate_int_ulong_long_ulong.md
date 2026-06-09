# NOTIFICATION_MAIN::DoStateRequestAuthenticate(int,ulong,long,ulong)

- ea: `0x1800072a0`
- end: `0x180007547`
- name: `?DoStateRequestAuthenticate@NOTIFICATION_MAIN@@AEAA?AW4REQUEST_NOTIFICATION_STATUS@@HKJK@Z`
- size: `679`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, unsigned int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180005930`

## callees

- `0x180006010`
- `0x180006ca0`
- `0x1800072a0`
- `0x180009ba0`
- `0x180016340`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007414`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007488`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007414`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007488`

## pseudocode

```c
__int64 __fastcall NOTIFICATION_MAIN::DoStateRequestAuthenticate(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        int a5)
{
  unsigned __int64 v9; // rbp
  __int64 v10; // rdi
  __int64 v11; // rcx
  bool v12; // zf
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 result; // rax
  __int64 v16; // rdx
  unsigned int v17; // esi
  int v18; // eax
  unsigned int v19; // eax
  __int64 v20; // rax
  _WORD *v21; // rax
  _QWORD *v22; // r14
  volatile signed __int32 *v23; // r9
  __int64 v24; // rdx
  _QWORD *v25; // r14
  volatile signed __int32 *v26; // r8

  v9 = 0xFFFFFFFFLL;
  v10 = *(_QWORD *)(*(_QWORD *)(a1 + 136) + 8072LL) + 656LL;
  if ( !a2 && !*(_BYTE *)(a1 + 13) )
  {
    NOTIFICATION_CONTEXT::GetFirstModule((NOTIFICATION_CONTEXT *)a1);
    if ( *(_BYTE *)(v11 + 12) == (_BYTE)a2 )
      (**(void (__fastcall ***)(__int64, __int64, __int64))v10)(v10, 9, 1);
  }
  v12 = *(_BYTE *)(a1 + 12) == 0;
  v13 = *(_QWORD *)(a1 + 136);
  *(_BYTE *)(a1 + 13) = 0;
  if ( v12 )
  {
    v14 = v13 + 32;
    if ( !v13 )
      v14 = 0;
  }
  else if ( v13 )
  {
    v14 = v13 + 16;
  }
  else
  {
    v14 = 0;
  }
  result = NOTIFICATION_CONTEXT::CallModules(a1, a2, a3, a4, a5, v13, v14);
  v17 = result;
  if ( (_DWORD)result != 1 )
  {
    if ( *(_BYTE *)(a1 + 12) )
      goto LABEL_34;
    if ( *(_BYTE *)(a1 + 13) )
    {
      v18 = *(_DWORD *)(a1 + 124);
      if ( v18 != -1 )
      {
        v19 = v18 + 1;
        if ( v19 < *(_DWORD *)(a1 + 120) && *(_DWORD *)(*(_QWORD *)(a1 + 104) + 4LL * v19) != -1 )
          goto LABEL_34;
      }
    }
    v20 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 136) + 48LL))(*(_QWORD *)(a1 + 136));
    v16 = v20;
    if ( !v20 )
      goto LABEL_34;
    v21 = (_WORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    if ( v21 && *v21 )
    {
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 136) + 376LL))(*(_QWORD *)(a1 + 136), 11);
      if ( !(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 136) + 232LL))(*(_QWORD *)(a1 + 136)) )
      {
        v22 = *(_QWORD **)(v10 + 8);
        if ( v22 )
        {
          v9 = (unsigned __int64)GetCurrentThreadId() % v22[2];
          _InterlockedIncrement((volatile signed __int32 *)(*v22 + (unsigned int)dword_18004DD14 + v22[1] * v9));
          v23 = (volatile signed __int32 *)(**(_QWORD **)(v10 + 8) + (unsigned int)qword_18004DD44);
          if ( v23 )
          {
            if ( !*v23 )
              _InterlockedCompareExchange(v23, 1, 0);
          }
        }
        v24 = 6;
LABEL_33:
        *(_QWORD *)(*(_QWORD *)(a1 + 136) + 9336LL) = v9;
        (**(void (__fastcall ***)(__int64, __int64, __int64))v10)(v10, v24, 1);
      }
    }
    else if ( !(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 136) + 232LL))(*(_QWORD *)(a1 + 136)) )
    {
      v25 = *(_QWORD **)(v10 + 8);
      if ( v25 )
      {
        v9 = (unsigned __int64)GetCurrentThreadId() % v25[2];
        _InterlockedIncrement((volatile signed __int32 *)(*v25 + (unsigned int)dword_18004DD08 + v25[1] * v9));
        v26 = (volatile signed __int32 *)(**(_QWORD **)(v10 + 8) + (unsigned int)qword_18004DD38);
        if ( v26 )
        {
          if ( !*v26 )
            _InterlockedCompareExchange(v26, 1, 0);
        }
      }
      v24 = 5;
      goto LABEL_33;
    }
LABEL_34:
    if ( v17 || *(_BYTE *)(a1 + 13) )
    {
      return v17;
    }
    else if ( *(_BYTE *)(a1 + 12) )
    {
      return W3_CONTEXT::DoStatePostAuthenticateFinish(*(_QWORD *)(a1 + 136));
    }
    else
    {
      return NOTIFICATION_MAIN::DoStateAuthenticateFinish(a1, v16);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800072a0  push    rbx
0x1800072a2  push    rbp
0x1800072a3  push    rsi
0x1800072a4  push    rdi
0x1800072a5  push    r12
0x1800072a7  push    r14
0x1800072a9  push    r15
0x1800072ab  sub     rsp, 40h
0x1800072af  mov     rax, [rcx+88h]
0x1800072b6  mov     r14d, r9d
0x1800072b9  mov     r15d, r8d
0x1800072bc  mov     esi, edx
0x1800072be  mov     rbx, rcx
0x1800072c1  mov     ebp, 0FFFFFFFFh
0x1800072c6  mov     r12d, 1
0x1800072cc  mov     rdi, [rax+1F88h]
0x1800072d3  add     rdi, 290h
0x1800072da  test    edx, edx
0x1800072dc  jnz     short loc_180007304
0x1800072de  cmp     [rcx+0Dh], dl
0x1800072e1  jnz     short loc_180007304
0x1800072e3  call    ?GetFirstModule@NOTIFICATION_CONTEXT@@IEAAXXZ; NOTIFICATION_CONTEXT::GetFirstModule(void)
0x1800072e8  cmp     [rcx+0Ch], sil
0x1800072ec  jnz     short loc_180007304
0x1800072ee  mov     rax, [rdi]
0x1800072f1  mov     r8d, r12d
0x1800072f4  mov     edx, 9
0x1800072f9  mov     rcx, rdi
0x1800072fc  mov     rax, [rax]
0x1800072ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007304  cmp     byte ptr [rbx+0Ch], 0
0x180007308  mov     rax, [rbx+88h]
0x18000730f  mov     byte ptr [rbx+0Dh], 0
0x180007313  jnz     short loc_180007324
0x180007315  xor     edx, edx
0x180007317  lea     rcx, [rax+20h]
0x18000731b  test    rax, rax
0x18000731e  cmovz   rcx, rdx
0x180007322  jmp     short loc_180007333
0x180007324  test    rax, rax
0x180007327  jz      short loc_18000732F
0x180007329  lea     rcx, [rax+10h]
0x18000732d  jmp     short loc_180007333
0x18000732f  xor     edx, edx
0x180007331  mov     ecx, edx
0x180007333  mov     [rsp+78h+var_48], rcx
0x180007338  mov     r9d, r14d
0x18000733b  mov     [rsp+78h+var_50], rax
0x180007340  mov     r8d, r15d
0x180007343  mov     eax, [rsp+78h+arg_20]
0x18000734a  mov     edx, esi
0x18000734c  mov     rcx, rbx
0x18000734f  mov     [rsp+78h+var_58], eax
0x180007353  call    ?CallModules@NOTIFICATION_CONTEXT@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@HKJKPEAVW3_CONTEXT_BASE@@PEAVIHttpEventProvider@@@Z; NOTIFICATION_CONTEXT::CallModules(int,ulong,long,ulong,W3_CONTEXT_BASE *,IHttpEventProvider *)
0x180007358  mov     esi, eax
0x18000735a  cmp     eax, r12d
0x18000735d  jz      loc_180007537
0x180007363  cmp     byte ptr [rbx+0Ch], 0
0x180007367  jnz     loc_1800074F5
0x18000736d  cmp     byte ptr [rbx+0Dh], 0
0x180007371  jz      short loc_180007390
0x180007373  mov     eax, [rbx+7Ch]
0x180007376  cmp     eax, ebp
0x180007378  jz      short loc_180007390
0x18000737a  inc     eax
0x18000737c  cmp     eax, [rbx+78h]
0x18000737f  jnb     short loc_180007390
0x180007381  mov     ecx, eax
0x180007383  mov     rax, [rbx+68h]
0x180007387  cmp     [rax+rcx*4], ebp
0x18000738a  jnz     loc_1800074F5
0x180007390  mov     rcx, [rbx+88h]
0x180007397  mov     rax, [rcx]
0x18000739a  mov     rax, [rax+30h]
0x18000739e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073a3  mov     rdx, rax
0x1800073a6  test    rax, rax
0x1800073a9  jz      loc_1800074F5
0x1800073af  mov     rcx, [rax]
0x1800073b2  mov     rax, [rcx+10h]
0x1800073b6  mov     rcx, rdx
0x1800073b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073be  test    rax, rax
0x1800073c1  jz      loc_180007464
0x1800073c7  cmp     word ptr [rax], 0
0x1800073cb  jz      loc_180007464
0x1800073d1  mov     rcx, [rbx+88h]
0x1800073d8  mov     edx, 0Bh
0x1800073dd  mov     rax, [rcx]
0x1800073e0  mov     rax, [rax+178h]
0x1800073e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073ec  mov     rcx, [rbx+88h]
0x1800073f3  mov     rax, [rcx]
0x1800073f6  mov     rax, [rax+0E8h]
0x1800073fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007402  test    rax, rax
0x180007405  jnz     loc_1800074F5
0x18000740b  mov     r14, [rdi+8]
0x18000740f  test    r14, r14
0x180007412  jz      short loc_18000745D
0x180007414  call    cs:__imp_GetCurrentThreadId
0x18000741b  nop     dword ptr [rax+rax+00h]
0x180007420  mov     eax, eax
0x180007422  xor     edx, edx
0x180007424  div     qword ptr [r14+10h]
0x180007428  mov     eax, cs:dword_18004DD14
0x18000742e  mov     ecx, edx
0x180007430  imul    rcx, [r14+8]
0x180007435  mov     ebp, edx
0x180007437  add     rcx, rax
0x18000743a  add     rcx, [r14]
0x18000743d  lock inc dword ptr [rcx]
0x180007440  mov     rax, [rdi+8]
0x180007444  mov     r9d, dword ptr cs:qword_18004DD44
0x18000744b  add     r9, [rax]
0x18000744e  jz      short loc_18000745D
0x180007450  cmp     dword ptr [r9], 0
0x180007454  jnz     short loc_18000745D
0x180007456  xor     eax, eax
0x180007458  lock cmpxchg [r9], r12d
0x18000745d  mov     edx, 6
0x180007462  jmp     short loc_1800074D6
0x180007464  mov     rcx, [rbx+88h]
0x18000746b  mov     rax, [rcx]
0x18000746e  mov     rax, [rax+0E8h]
0x180007475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000747a  test    rax, rax
0x18000747d  jnz     short loc_1800074F5
0x18000747f  mov     r14, [rdi+8]
0x180007483  test    r14, r14
0x180007486  jz      short loc_1800074D1
0x180007488  call    cs:__imp_GetCurrentThreadId
0x18000748f  nop     dword ptr [rax+rax+00h]
0x180007494  mov     eax, eax
0x180007496  xor     edx, edx
0x180007498  div     qword ptr [r14+10h]
0x18000749c  mov     eax, cs:dword_18004DD08
0x1800074a2  mov     ecx, edx
0x1800074a4  imul    rcx, [r14+8]
0x1800074a9  mov     ebp, edx
0x1800074ab  add     rcx, rax
0x1800074ae  add     rcx, [r14]
0x1800074b1  lock inc dword ptr [rcx]
0x1800074b4  mov     rax, [rdi+8]
0x1800074b8  mov     r8d, dword ptr cs:qword_18004DD38
0x1800074bf  add     r8, [rax]
0x1800074c2  jz      short loc_1800074D1
0x1800074c4  cmp     dword ptr [r8], 0
0x1800074c8  jnz     short loc_1800074D1
0x1800074ca  xor     eax, eax
0x1800074cc  lock cmpxchg [r8], r12d
0x1800074d1  mov     edx, 5
0x1800074d6  mov     rax, [rbx+88h]
0x1800074dd  mov     r8d, r12d
0x1800074e0  mov     rcx, rdi
0x1800074e3  mov     [rax+2478h], rbp
0x1800074ea  mov     rax, [rdi]
0x1800074ed  mov     rax, [rax]
0x1800074f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074f5  test    esi, esi
0x1800074f7  jnz     short loc_180007535
0x1800074f9  cmp     [rbx+0Dh], sil
0x1800074fd  jnz     short loc_180007535
0x1800074ff  cmp     [rbx+0Ch], sil
0x180007503  jnz     short loc_18000751B
0x180007505  mov     rcx, rbx
0x180007508  add     rsp, 40h
0x18000750c  pop     r15
0x18000750e  pop     r14
0x180007510  pop     r12
0x180007512  pop     rdi
0x180007513  pop     rsi
0x180007514  pop     rbp
0x180007515  pop     rbx
0x180007516  jmp     ?DoStateAuthenticateFinish@NOTIFICATION_MAIN@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@XZ; NOTIFICATION_MAIN::DoStateAuthenticateFinish(void)
0x18000751b  mov     rcx, [rbx+88h]
0x180007522  add     rsp, 40h
0x180007526  pop     r15
0x180007528  pop     r14
0x18000752a  pop     r12
0x18000752c  pop     rdi
0x18000752d  pop     rsi
0x18000752e  pop     rbp
0x18000752f  pop     rbx
0x180007530  jmp     ?DoStatePostAuthenticateFinish@W3_CONTEXT@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@XZ; W3_CONTEXT::DoStatePostAuthenticateFinish(void)
0x180007535  mov     eax, esi
0x180007537  add     rsp, 40h
0x18000753b  pop     r15
0x18000753d  pop     r14
0x18000753f  pop     r12
0x180007541  pop     rdi
0x180007542  pop     rsi
0x180007543  pop     rbp
0x180007544  pop     rbx
0x180007545  retn
```
