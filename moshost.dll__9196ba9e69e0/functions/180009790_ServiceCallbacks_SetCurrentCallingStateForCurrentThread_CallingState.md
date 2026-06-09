# ServiceCallbacks::SetCurrentCallingStateForCurrentThread(CallingState)

- ea: `0x180009790`
- end: `0x180009959`
- name: `?SetCurrentCallingStateForCurrentThread@ServiceCallbacks@@UEAA?AW4CallingState@@W42@@Z`
- size: `457`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task`

## callees

- `0x180001d24`
- `0x18000210c`
- `0x180009790`
- `0x180009c0c`
- `0x18000a070`
- `0x18000a2a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009932`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009932`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800097b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800097b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800097c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000986e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800097c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000986e`

## pseudocode

```c
__int64 __fastcall ServiceCallbacks::SetCurrentCallingStateForCurrentThread(__int64 a1, int a2)
{
  __int64 *v3; // r14
  int v4; // edi
  unsigned int v5; // r13d
  struct _RTL_CRITICAL_SECTION *v6; // r15
  DWORD CurrentThreadId; // r8d
  __int64 v8; // rcx
  __int64 *v9; // rax
  __int64 *v10; // rdx
  __int64 *j; // r8
  __int64 *v12; // rax
  __int64 *i; // rcx
  void *v14; // rax
  DWORD v15; // ebx
  __int64 v16; // rsi
  __int64 v17; // rbp
  __int64 inserted; // rcx
  __int64 v19; // rax
  _DWORD *v20; // rax
  __int64 v22; // [rsp+20h] [rbp-58h] BYREF
  int v23; // [rsp+28h] [rbp-50h]
  int v24; // [rsp+2Ch] [rbp-4Ch]

  v3 = (__int64 *)(a1 + 48);
  v4 = 0;
  v5 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  CurrentThreadId = GetCurrentThreadId();
  v8 = *v3;
  v9 = *(__int64 **)(*v3 + 8);
  v24 = 0;
  v10 = (__int64 *)v8;
  while ( !*((_BYTE *)v9 + 25) )
  {
    if ( *((_DWORD *)v9 + 7) >= CurrentThreadId )
    {
      v10 = v9;
      v9 = (__int64 *)*v9;
    }
    else
    {
      v9 = (__int64 *)v9[2];
    }
  }
  if ( *((_BYTE *)v10 + 25) || CurrentThreadId < *((_DWORD *)v10 + 7) )
  {
    v10 = (__int64 *)v8;
  }
  else if ( v10 != (__int64 *)v8 )
  {
    v5 = *((_DWORD *)v10 + 8);
  }
  if ( a2 )
  {
    v15 = GetCurrentThreadId();
    v16 = *v3;
    v17 = *(_QWORD *)(*v3 + 8);
    inserted = *v3;
    v19 = v17;
    while ( !*(_BYTE *)(v19 + 25) )
    {
      v17 = v19;
      if ( *(_DWORD *)(v19 + 28) >= v15 )
      {
        v4 = 1;
        inserted = v19;
        v19 = *(_QWORD *)v19;
      }
      else
      {
        v4 = 0;
        v19 = *(_QWORD *)(v19 + 16);
      }
    }
    if ( *(_BYTE *)(inserted + 25) || v15 < *(_DWORD *)(inserted + 28) )
    {
      if ( v3[1] == 0x666666666666666LL )
        std::_Throw_tree_length_error();
      v20 = operator new(0x28u);
      v20[7] = v15;
      v20[8] = 0;
      *(_QWORD *)v20 = v16;
      *((_QWORD *)v20 + 1) = v16;
      *((_QWORD *)v20 + 2) = v16;
      *((_WORD *)v20 + 12) = 0;
      v22 = v17;
      v23 = v4;
      v24 = 0;
      inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,enum CallingState>>>::_Insert_node(
                   v3,
                   &v22,
                   v20);
    }
    *(_DWORD *)(inserted + 32) = a2;
  }
  else
  {
    j = (__int64 *)v10[2];
    if ( *((_BYTE *)j + 25) )
    {
      v12 = v10;
      for ( i = (__int64 *)v10[1]; !*((_BYTE *)i + 25) && v12 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v12 = i;
    }
    else
    {
      for ( j = (__int64 *)*j; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        ;
    }
    v14 = (void *)std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,enum CallingState>>>::_Extract(
                    v3,
                    v10,
                    j);
    operator delete(v14);
  }
  if ( v6 )
    LeaveCriticalSection(v6);
  return v5;
}

```

## disassembly

```asm
0x180009790  mov     [rsp+arg_18], rbx
0x180009795  push    rbp
0x180009796  push    rsi
0x180009797  push    rdi
0x180009798  push    r12
0x18000979a  push    r13
0x18000979c  push    r14
0x18000979e  push    r15
0x1800097a0  sub     rsp, 40h
0x1800097a4  mov     r12d, edx
0x1800097a7  lea     r14, [rcx+30h]
0x1800097ab  xor     edi, edi
0x1800097ad  mov     r13d, edi
0x1800097b0  lea     r15, [rcx+8]
0x1800097b4  mov     rcx, r15; lpCriticalSection
0x1800097b7  call    cs:__imp_EnterCriticalSection
0x1800097bd  mov     [rsp+78h+arg_10], r15
0x1800097c5  call    cs:__imp_GetCurrentThreadId
0x1800097cb  mov     r8d, eax
0x1800097ce  mov     rcx, [r14]
0x1800097d1  mov     rax, [rcx+8]
0x1800097d5  xor     edx, edx
0x1800097d7  mov     [rsp+78h+var_4C], edx
0x1800097db  mov     rdx, rcx
0x1800097de  jmp     short loc_1800097F2
0x1800097e0  cmp     [rax+1Ch], r8d
0x1800097e4  jnb     short loc_1800097EC
0x1800097e6  mov     rax, [rax+10h]
0x1800097ea  jmp     short loc_1800097F2
0x1800097ec  mov     rdx, rax
0x1800097ef  mov     rax, [rax]
0x1800097f2  cmp     [rax+19h], dil
0x1800097f6  jz      short loc_1800097E0
0x1800097f8  cmp     [rdx+19h], dil
0x1800097fc  jnz     short loc_18000980F
0x1800097fe  cmp     r8d, [rdx+1Ch]
0x180009802  jb      short loc_18000980F
0x180009804  cmp     rdx, rcx
0x180009807  jz      short loc_180009812
0x180009809  mov     r13d, [rdx+20h]
0x18000980d  jmp     short loc_180009812
0x18000980f  mov     rdx, rcx
0x180009812  test    r12d, r12d
0x180009815  jnz     short loc_18000986E
0x180009817  mov     r8, [rdx+10h]
0x18000981b  cmp     [r8+19h], dil
0x18000981f  jz      short loc_18000983F
0x180009821  mov     rax, rdx
0x180009824  mov     rcx, [rdx+8]
0x180009828  jmp     short loc_180009837
0x18000982a  cmp     rax, [rcx+10h]
0x18000982e  jnz     short loc_180009854
0x180009830  mov     rax, rcx
0x180009833  mov     rcx, [rcx+8]
0x180009837  cmp     [rcx+19h], dil
0x18000983b  jz      short loc_18000982A
0x18000983d  jmp     short loc_180009854
0x18000983f  mov     r8, [r8]
0x180009842  cmp     [r8+19h], dil
0x180009846  jnz     short loc_180009854
0x180009848  mov     rax, [r8]
0x18000984b  mov     r8, rax
0x18000984e  cmp     [rax+19h], dil
0x180009852  jz      short loc_180009848
0x180009854  mov     rcx, r14
0x180009857  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKW4CallingState@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKW4CallingState@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKW4CallingState@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CallingState>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CallingState>>>,std::_Iterator_base0>)
0x18000985c  mov     edx, 28h ; '('
0x180009861  mov     rcx, rax; Block
0x180009864  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009869  jmp     loc_18000992A
0x18000986e  call    cs:__imp_GetCurrentThreadId
0x180009874  mov     ebx, eax
0x180009876  mov     rsi, [r14]
0x180009879  mov     rbp, [rsi+8]
0x18000987d  xor     eax, eax
0x18000987f  mov     [rsp+78h+arg_0], rax
0x180009887  mov     rcx, rsi
0x18000988a  mov     rax, rbp
0x18000988d  xor     edx, edx
0x18000988f  cmp     [rbp+19h], dl
0x180009892  jnz     short loc_1800098B4
0x180009894  mov     rbp, rax
0x180009897  cmp     [rax+1Ch], ebx
0x18000989a  jnb     short loc_1800098A4
0x18000989c  mov     edi, edx
0x18000989e  mov     rax, [rax+10h]
0x1800098a2  jmp     short loc_1800098AF
0x1800098a4  mov     edi, 1
0x1800098a9  mov     rcx, rax
0x1800098ac  mov     rax, [rax]
0x1800098af  cmp     [rax+19h], dl
0x1800098b2  jz      short loc_180009894
0x1800098b4  cmp     [rcx+19h], dl
0x1800098b7  jnz     short loc_1800098BE
0x1800098b9  cmp     ebx, [rcx+1Ch]
0x1800098bc  jnb     short loc_180009926
0x1800098be  mov     rax, 666666666666666h
0x1800098c8  cmp     [r14+8], rax
0x1800098cc  jz      loc_180009953
0x1800098d2  mov     [rsp+78h+var_58], r14
0x1800098d7  mov     [rsp+28h], rdx
0x1800098dc  mov     ecx, 28h ; '('; Size
0x1800098e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800098e6  nop
0x1800098e7  mov     [rax+1Ch], ebx
0x1800098ea  xor     ecx, ecx
0x1800098ec  mov     [rax+20h], ecx
0x1800098ef  mov     [rax], rsi
0x1800098f2  mov     [rax+8], rsi
0x1800098f6  mov     [rax+10h], rsi
0x1800098fa  mov     [rax+18h], cx
0x1800098fe  mov     [rsp+78h+var_58], rbp
0x180009903  mov     [rsp+78h+var_50], edi
0x180009907  mov     rcx, [rsp+78h+arg_0]
0x18000990f  mov     [rsp+78h+var_4C], ecx
0x180009913  mov     r8, rax
0x180009916  lea     rdx, [rsp+78h+var_58]
0x18000991b  mov     rcx, r14
0x18000991e  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKW4CallingState@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKW4CallingState@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBKW4CallingState@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CallingState>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ulong const,CallingState>,void *> *>,std::_Tree_node<std::pair<ulong const,CallingState>,void *> * const)
0x180009923  mov     rcx, rax
0x180009926  mov     [rcx+20h], r12d
0x18000992a  test    r15, r15
0x18000992d  jz      short loc_180009938
0x18000992f  mov     rcx, r15; lpCriticalSection
0x180009932  call    cs:__imp_LeaveCriticalSection
0x180009938  mov     eax, r13d
0x18000993b  mov     rbx, [rsp+78h+arg_18]
0x180009943  add     rsp, 40h
0x180009947  pop     r15
0x180009949  pop     r14
0x18000994b  pop     r13
0x18000994d  pop     r12
0x18000994f  pop     rdi
0x180009950  pop     rsi
0x180009951  pop     rbp
0x180009952  retn
0x180009953  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
