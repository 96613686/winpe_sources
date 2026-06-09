# NOTIFICATION_MAIN::DoStateRequestAuthenticate(int,ulong,long,ulong)

- ea: `0x180006e00`
- end: `0x18000709a`
- name: `?DoStateRequestAuthenticate@NOTIFICATION_MAIN@@AEAA?AW4REQUEST_NOTIFICATION_STATUS@@HKJK@Z`
- size: `666`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800054d0`

## callees

- `0x180005ba0`
- `0x180006810`
- `0x180006e00`
- `0x18000d7c4`
- `0x180015120`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006fe2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006fe2`

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
          _InterlockedIncrement((volatile signed __int32 *)(*v22 + (unsigned int)dword_18004AD14 + v22[1] * v9));
          v23 = (volatile signed __int32 *)(**(_QWORD **)(v10 + 8) + (unsigned int)qword_18004AD44);
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
        _InterlockedIncrement((volatile signed __int32 *)(*v25 + (unsigned int)dword_18004AD08 + v25[1] * v9));
        v26 = (volatile signed __int32 *)(**(_QWORD **)(v10 + 8) + (unsigned int)qword_18004AD38);
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
      return W3_CONTEXT::DoStatePostAuthenticateFinish(*(_QWORD *)(a1 + 136), v16);
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
0x180006e00  push    rbx
0x180006e02  push    rbp
0x180006e03  push    rsi
0x180006e04  push    rdi
0x180006e05  push    r12
0x180006e07  push    r14
0x180006e09  push    r15
0x180006e0b  sub     rsp, 40h
0x180006e0f  mov     rax, [rcx+88h]
0x180006e16  mov     r14d, r9d
0x180006e19  mov     r15d, r8d
0x180006e1c  mov     esi, edx
0x180006e1e  mov     rbx, rcx
0x180006e21  mov     ebp, 0FFFFFFFFh
0x180006e26  mov     r12d, 1
0x180006e2c  mov     rdi, [rax+1F88h]
0x180006e33  add     rdi, 290h
0x180006e3a  test    edx, edx
0x180006e3c  jnz     short loc_180006E64
0x180006e3e  cmp     [rcx+0Dh], dl
0x180006e41  jnz     short loc_180006E64
0x180006e43  call    ?GetFirstModule@NOTIFICATION_CONTEXT@@IEAAXXZ; NOTIFICATION_CONTEXT::GetFirstModule(void)
0x180006e48  cmp     [rcx+0Ch], sil
0x180006e4c  jnz     short loc_180006E64
0x180006e4e  mov     rax, [rdi]
0x180006e51  mov     r8d, r12d
0x180006e54  mov     edx, 9
0x180006e59  mov     rcx, rdi
0x180006e5c  mov     rax, [rax]
0x180006e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e64  cmp     byte ptr [rbx+0Ch], 0
0x180006e68  mov     rax, [rbx+88h]
0x180006e6f  mov     byte ptr [rbx+0Dh], 0
0x180006e73  jnz     short loc_180006E84
0x180006e75  xor     edx, edx
0x180006e77  lea     rcx, [rax+20h]
0x180006e7b  test    rax, rax
0x180006e7e  cmovz   rcx, rdx
0x180006e82  jmp     short loc_180006E93
0x180006e84  test    rax, rax
0x180006e87  jz      short loc_180006E8F
0x180006e89  lea     rcx, [rax+10h]
0x180006e8d  jmp     short loc_180006E93
0x180006e8f  xor     edx, edx
0x180006e91  mov     ecx, edx
0x180006e93  mov     [rsp+78h+var_48], rcx
0x180006e98  mov     r9d, r14d
0x180006e9b  mov     [rsp+78h+var_50], rax
0x180006ea0  mov     r8d, r15d
0x180006ea3  mov     eax, [rsp+78h+arg_20]
0x180006eaa  mov     edx, esi
0x180006eac  mov     rcx, rbx
0x180006eaf  mov     [rsp+78h+var_58], eax
0x180006eb3  call    ?CallModules@NOTIFICATION_CONTEXT@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@HKJKPEAVW3_CONTEXT_BASE@@PEAVIHttpEventProvider@@@Z; NOTIFICATION_CONTEXT::CallModules(int,ulong,long,ulong,W3_CONTEXT_BASE *,IHttpEventProvider *)
0x180006eb8  mov     esi, eax
0x180006eba  cmp     eax, r12d
0x180006ebd  jz      loc_18000708B
0x180006ec3  cmp     byte ptr [rbx+0Ch], 0
0x180006ec7  jnz     loc_180007049
0x180006ecd  cmp     byte ptr [rbx+0Dh], 0
0x180006ed1  jz      short loc_180006EF0
0x180006ed3  mov     eax, [rbx+7Ch]
0x180006ed6  cmp     eax, ebp
0x180006ed8  jz      short loc_180006EF0
0x180006eda  inc     eax
0x180006edc  cmp     eax, [rbx+78h]
0x180006edf  jnb     short loc_180006EF0
0x180006ee1  mov     ecx, eax
0x180006ee3  mov     rax, [rbx+68h]
0x180006ee7  cmp     [rax+rcx*4], ebp
0x180006eea  jnz     loc_180007049
0x180006ef0  mov     rcx, [rbx+88h]
0x180006ef7  mov     rax, [rcx]
0x180006efa  mov     rax, [rax+30h]
0x180006efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f03  mov     rdx, rax
0x180006f06  test    rax, rax
0x180006f09  jz      loc_180007049
0x180006f0f  mov     rcx, [rax]
0x180006f12  mov     rax, [rcx+10h]
0x180006f16  mov     rcx, rdx
0x180006f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f1e  test    rax, rax
0x180006f21  jz      loc_180006FBE
0x180006f27  cmp     word ptr [rax], 0
0x180006f2b  jz      loc_180006FBE
0x180006f31  mov     rcx, [rbx+88h]
0x180006f38  mov     edx, 0Bh
0x180006f3d  mov     rax, [rcx]
0x180006f40  mov     rax, [rax+178h]
0x180006f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f4c  mov     rcx, [rbx+88h]
0x180006f53  mov     rax, [rcx]
0x180006f56  mov     rax, [rax+0E8h]
0x180006f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f62  test    rax, rax
0x180006f65  jnz     loc_180007049
0x180006f6b  mov     r14, [rdi+8]
0x180006f6f  test    r14, r14
0x180006f72  jz      short loc_180006FB7
0x180006f74  call    cs:__imp_GetCurrentThreadId
0x180006f7a  mov     eax, eax
0x180006f7c  xor     edx, edx
0x180006f7e  div     qword ptr [r14+10h]
0x180006f82  mov     eax, cs:dword_18004AD14
0x180006f88  mov     ecx, edx
0x180006f8a  imul    rcx, [r14+8]
0x180006f8f  mov     ebp, edx
0x180006f91  add     rcx, rax
0x180006f94  add     rcx, [r14]
0x180006f97  lock inc dword ptr [rcx]
0x180006f9a  mov     rax, [rdi+8]
0x180006f9e  mov     r9d, dword ptr cs:qword_18004AD44
0x180006fa5  add     r9, [rax]
0x180006fa8  jz      short loc_180006FB7
0x180006faa  cmp     dword ptr [r9], 0
0x180006fae  jnz     short loc_180006FB7
0x180006fb0  xor     eax, eax
0x180006fb2  lock cmpxchg [r9], r12d
0x180006fb7  mov     edx, 6
0x180006fbc  jmp     short loc_18000702A
0x180006fbe  mov     rcx, [rbx+88h]
0x180006fc5  mov     rax, [rcx]
0x180006fc8  mov     rax, [rax+0E8h]
0x180006fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fd4  test    rax, rax
0x180006fd7  jnz     short loc_180007049
0x180006fd9  mov     r14, [rdi+8]
0x180006fdd  test    r14, r14
0x180006fe0  jz      short loc_180007025
0x180006fe2  call    cs:__imp_GetCurrentThreadId
0x180006fe8  mov     eax, eax
0x180006fea  xor     edx, edx
0x180006fec  div     qword ptr [r14+10h]
0x180006ff0  mov     eax, cs:dword_18004AD08
0x180006ff6  mov     ecx, edx
0x180006ff8  imul    rcx, [r14+8]
0x180006ffd  mov     ebp, edx
0x180006fff  add     rcx, rax
0x180007002  add     rcx, [r14]
0x180007005  lock inc dword ptr [rcx]
0x180007008  mov     rax, [rdi+8]
0x18000700c  mov     r8d, dword ptr cs:qword_18004AD38
0x180007013  add     r8, [rax]
0x180007016  jz      short loc_180007025
0x180007018  cmp     dword ptr [r8], 0
0x18000701c  jnz     short loc_180007025
0x18000701e  xor     eax, eax
0x180007020  lock cmpxchg [r8], r12d
0x180007025  mov     edx, 5
0x18000702a  mov     rax, [rbx+88h]
0x180007031  mov     r8d, r12d
0x180007034  mov     rcx, rdi
0x180007037  mov     [rax+2478h], rbp
0x18000703e  mov     rax, [rdi]
0x180007041  mov     rax, [rax]
0x180007044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007049  test    esi, esi
0x18000704b  jnz     short loc_180007089
0x18000704d  cmp     [rbx+0Dh], sil
0x180007051  jnz     short loc_180007089
0x180007053  cmp     [rbx+0Ch], sil
0x180007057  jnz     short loc_18000706F
0x180007059  mov     rcx, rbx
0x18000705c  add     rsp, 40h
0x180007060  pop     r15
0x180007062  pop     r14
0x180007064  pop     r12
0x180007066  pop     rdi
0x180007067  pop     rsi
0x180007068  pop     rbp
0x180007069  pop     rbx
0x18000706a  jmp     ?DoStateAuthenticateFinish@NOTIFICATION_MAIN@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@XZ; NOTIFICATION_MAIN::DoStateAuthenticateFinish(void)
0x18000706f  mov     rcx, [rbx+88h]
0x180007076  add     rsp, 40h
0x18000707a  pop     r15
0x18000707c  pop     r14
0x18000707e  pop     r12
0x180007080  pop     rdi
0x180007081  pop     rsi
0x180007082  pop     rbp
0x180007083  pop     rbx
0x180007084  jmp     ?DoStatePostAuthenticateFinish@W3_CONTEXT@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@XZ; W3_CONTEXT::DoStatePostAuthenticateFinish(void)
0x180007089  mov     eax, esi
0x18000708b  add     rsp, 40h
0x18000708f  pop     r15
0x180007091  pop     r14
0x180007093  pop     r12
0x180007095  pop     rdi
0x180007096  pop     rsi
0x180007097  pop     rbp
0x180007098  pop     rbx
0x180007099  retn
```
