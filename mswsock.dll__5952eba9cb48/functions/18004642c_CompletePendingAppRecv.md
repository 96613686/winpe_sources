# CompletePendingAppRecv

- ea: `0x18004642c`
- end: `0x1800466a1`
- name: `CompletePendingAppRecv`
- size: `629`
- prototype: `__int64 __fastcall(PVOID CompletionContext)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18003cdc8`
- `0x18003d480`

## callees

- `0x180023f14`
- `0x1800389d8`
- `0x18003ae8c`
- `0x18003f28c`
- `0x18003f2e0`
- `0x1800462b0`
- `0x18004642c`
- `0x1800496e4`
- `0x18004a288`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800465f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800465f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004653b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004653b`

## pseudocode

```c
void __fastcall CompletePendingAppRecv(char *CompletionContext, __int64 a2, unsigned int a3)
{
  __int64 v3; // rdi
  unsigned int v6; // ebp
  int v7; // r14d
  __int64 v8; // r15
  __int64 v9; // r12
  unsigned int v10; // r13d
  PVOID *v11; // rdx
  _QWORD *v12; // rax
  PVOID *v13; // rcx
  _QWORD *v14; // rdx
  void *v15; // [rsp+30h] [rbp-58h]
  unsigned int v16; // [rsp+90h] [rbp+8h] BYREF
  int v17; // [rsp+98h] [rbp+10h]
  unsigned int v18; // [rsp+A0h] [rbp+18h]
  void *v19; // [rsp+A8h] [rbp+20h]

  v18 = a3;
  v3 = *(_QWORD *)(a2 + 120);
  v16 = 0;
  v6 = 0;
  v7 = 0;
  if ( v3 )
  {
    if ( (CompletionContext[801] & 8) != 0 )
    {
      if ( *(_DWORD *)(v3 + 80) )
      {
        do
        {
          if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD, unsigned int *))(*((_QWORD *)CompletionContext + 2)
                                                                              + 312LL))(
                 *((_QWORD *)CompletionContext + 13),
                 *(_QWORD *)(*(_QWORD *)(v3 + 72) + 24LL * v6 + 16),
                 &v16)
            && (xmmword_180063D60 & 2) != 0 )
          {
            WPP_SF_dq(1025, 111, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v16, v3);
          }
          ++v6;
        }
        while ( v6 < *(_DWORD *)(v3 + 80) );
      }
      *(_DWORD *)(v3 + 80) = 0;
      v7 = 1;
    }
    else
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned int *))(*((_QWORD *)CompletionContext + 2) + 328LL))(
        *((_QWORD *)CompletionContext + 13),
        *(_QWORD *)(v3 + 96),
        *(unsigned int *)(*((_QWORD *)CompletionContext + 2) + 20LL),
        &v16);
    }
    v6 = 1;
  }
  v8 = *(_QWORD *)(a2 + 136);
  v9 = *(_QWORD *)(a2 + 8);
  v10 = *(_DWORD *)(a2 + 40);
  v17 = *(_DWORD *)(a2 + 36);
  v15 = *(void **)(a2 + 64);
  v19 = *(void **)(a2 + 72);
  EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  if ( v7 )
    ReleaseWsaBufExArray(CompletionContext, *(_QWORD *)(v3 + 72));
  if ( v6 )
  {
    *(_DWORD *)v3 = 1145324612;
    v11 = (PVOID *)*((_QWORD *)CompletionContext + 97);
    if ( *v11 != CompletionContext + 768 )
      goto LABEL_31;
    *(_QWORD *)(v3 + 40) = CompletionContext + 768;
    *(_QWORD *)(v3 + 48) = v11;
    *v11 = (PVOID)(v3 + 40);
    *((_QWORD *)CompletionContext + 97) = v3 + 40;
  }
  v12 = CompletionContext + 320;
  v13 = (PVOID *)*((_QWORD *)CompletionContext + 40);
  if ( v13[1] != CompletionContext + 320 || (v14 = *v13, *((PVOID **)*v13 + 1) != v13) )
LABEL_31:
    __fastfail(3u);
  *v12 = v14;
  v14[1] = v12;
  if ( *((_QWORD *)CompletionContext + 63) == a2 )
    *((_QWORD *)CompletionContext + 63) = 0;
  ReleaseWsaBufArray(CompletionContext, *(_QWORD *)(a2 + 48));
  ReleaseApplicationBuffer(CompletionContext, a2);
  if ( *((_DWORD *)CompletionContext + 44) == 1 || CompletionContext[208] )
    CheckForSocketDuplicationProtocol(CompletionContext);
  LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  if ( v8 )
  {
    if ( v17 )
      IndicateRedirError(CompletionContext, v8, *((_DWORD *)CompletionContext + 201) == 0 ? 0xC000020D : 0);
  }
  else if ( v9 )
  {
    if ( (BYTE1(xmmword_180063D60) & 0x10) != 0 )
      WPP_SF_d(1036, 112, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v10);
    CompleteOverlappedIO(*(_QWORD *)(*(_QWORD *)CompletionContext + 8LL), v9, v15, v19, v18, v10);
  }
}

```

## disassembly

```asm
0x18004642c  mov     rax, rsp
0x18004642f  mov     [rax+18h], r8d
0x180046433  push    rbx
0x180046434  push    rbp
0x180046435  push    rsi
0x180046436  push    rdi
0x180046437  push    r12
0x180046439  push    r13
0x18004643b  push    r14
0x18004643d  push    r15
0x18004643f  sub     rsp, 48h
0x180046443  mov     rdi, [rdx+78h]
0x180046447  xor     r15d, r15d
0x18004644a  mov     [rax+8], r15d
0x18004644e  mov     rsi, rdx
0x180046451  mov     rbx, rcx
0x180046454  mov     ebp, r15d
0x180046457  mov     r14d, r15d
0x18004645a  lea     r12d, [r15+1]
0x18004645e  test    rdi, rdi
0x180046461  jz      loc_180046509
0x180046467  test    byte ptr [rcx+321h], 8
0x18004646e  jz      short loc_1800464E2
0x180046470  cmp     [rdi+50h], r15d
0x180046474  jbe     short loc_1800464D9
0x180046476  mov     rcx, [rbx+10h]
0x18004647a  lea     r8, [rsp+88h+arg_0]
0x180046482  mov     rdx, [rdi+48h]
0x180046486  mov     eax, ebp
0x180046488  lea     r9, [rax+rax*2]
0x18004648c  mov     rax, [rcx+138h]
0x180046493  mov     rdx, [rdx+r9*8+10h]
0x180046498  mov     rcx, [rbx+68h]
0x18004649c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800464a1  test    eax, eax
0x1800464a3  jz      short loc_1800464D1
0x1800464a5  test    byte ptr cs:xmmword_180063D60, 2
0x1800464ac  jz      short loc_1800464D1
0x1800464ae  mov     r9d, [rsp+88h+arg_0]
0x1800464b6  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x1800464bd  mov     edx, 6Fh ; 'o'
0x1800464c2  mov     [rsp+88h+var_68], rdi
0x1800464c7  mov     ecx, 401h
0x1800464cc  call    WPP_SF_dq
0x1800464d1  add     ebp, r12d
0x1800464d4  cmp     ebp, [rdi+50h]
0x1800464d7  jb      short loc_180046476
0x1800464d9  mov     [rdi+50h], r15d
0x1800464dd  mov     r14d, r12d
0x1800464e0  jmp     short loc_180046506
0x1800464e2  mov     r8, [rcx+10h]
0x1800464e6  lea     r9, [rsp+88h+arg_0]
0x1800464ee  mov     rdx, [rdi+60h]
0x1800464f2  mov     rcx, [rcx+68h]
0x1800464f6  mov     rax, [r8+148h]
0x1800464fd  mov     r8d, [r8+14h]
0x180046501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046506  mov     ebp, r12d
0x180046509  mov     eax, [rsi+24h]
0x18004650c  lea     rcx, [rbx+30h]; lpCriticalSection
0x180046510  mov     r15, [rsi+88h]
0x180046517  mov     r12, [rsi+8]
0x18004651b  mov     r13d, [rsi+28h]
0x18004651f  mov     [rsp+88h+arg_8], eax
0x180046526  mov     rax, [rsi+40h]
0x18004652a  mov     [rsp+88h+var_58], rax
0x18004652f  mov     rax, [rsi+48h]
0x180046533  mov     [rsp+88h+arg_18], rax
0x18004653b  call    cs:__imp_EnterCriticalSection
0x180046542  nop     dword ptr [rax+rax+00h]
0x180046547  test    r14d, r14d
0x18004654a  jz      short loc_180046558
0x18004654c  mov     rdx, [rdi+48h]
0x180046550  mov     rcx, rbx
0x180046553  call    ReleaseWsaBufExArray
0x180046558  xor     r14d, r14d
0x18004655b  test    ebp, ebp
0x18004655d  jz      short loc_18004658B
0x18004655f  lea     rcx, [rbx+300h]
0x180046566  mov     dword ptr [rdi], 44444444h
0x18004656c  mov     rdx, [rcx+8]
0x180046570  cmp     [rdx], rcx
0x180046573  jnz     loc_18004669A
0x180046579  lea     rax, [rdi+28h]
0x18004657d  mov     [rax], rcx
0x180046580  mov     [rax+8], rdx
0x180046584  mov     [rdx], rax
0x180046587  mov     [rcx+8], rax
0x18004658b  lea     rax, [rbx+140h]
0x180046592  mov     rcx, [rax]
0x180046595  cmp     [rcx+8], rax
0x180046599  jnz     loc_18004669A
0x18004659f  mov     rdx, [rcx]
0x1800465a2  cmp     [rdx+8], rcx
0x1800465a6  jnz     loc_18004669A
0x1800465ac  mov     [rax], rdx
0x1800465af  mov     [rdx+8], rax
0x1800465b3  cmp     [rbx+1F8h], rsi
0x1800465ba  jnz     short loc_1800465C3
0x1800465bc  mov     [rbx+1F8h], r14
0x1800465c3  mov     rdx, [rsi+30h]
0x1800465c7  mov     rcx, rbx
0x1800465ca  call    ReleaseWsaBufArray
0x1800465cf  mov     rdx, rsi
0x1800465d2  mov     rcx, rbx
0x1800465d5  call    ReleaseApplicationBuffer
0x1800465da  cmp     dword ptr [rbx+0B0h], 1
0x1800465e1  jz      short loc_1800465EC
0x1800465e3  cmp     [rbx+0D0h], r14b
0x1800465ea  jz      short loc_1800465F4
0x1800465ec  mov     rcx, rbx; CompletionContext
0x1800465ef  call    CheckForSocketDuplicationProtocol
0x1800465f4  lea     rcx, [rbx+30h]; lpCriticalSection
0x1800465f8  call    cs:__imp_LeaveCriticalSection
0x1800465ff  nop     dword ptr [rax+rax+00h]
0x180046604  test    r15, r15
0x180046607  jz      short loc_180046645
0x180046609  cmp     [rsp+88h+arg_8], r14d
0x180046611  jz      short loc_180046633
0x180046613  mov     eax, [rbx+324h]
0x180046619  mov     rdx, r15
0x18004661c  neg     eax
0x18004661e  mov     rcx, rbx
0x180046621  sbb     r8d, r8d
0x180046624  not     r8d
0x180046627  and     r8d, 0C000020Dh
0x18004662e  call    IndicateRedirError
0x180046633  add     rsp, 48h
0x180046637  pop     r15
0x180046639  pop     r14
0x18004663b  pop     r13
0x18004663d  pop     r12
0x18004663f  pop     rdi
0x180046640  pop     rsi
0x180046641  pop     rbp
0x180046642  pop     rbx
0x180046643  retn
0x180046645  test    r12, r12
0x180046648  jz      short loc_180046633
0x18004664a  test    byte ptr cs:xmmword_180063D60+1, 10h
0x180046651  jz      short loc_18004666C
0x180046653  mov     edx, 70h ; 'p'
0x180046658  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18004665f  mov     ecx, 40Ch
0x180046664  mov     r9d, r13d
0x180046667  call    WPP_SF_d
0x18004666c  mov     rcx, [rbx]
0x18004666f  mov     rdx, r12
0x180046672  mov     eax, [rsp+88h+arg_10]
0x180046679  mov     r9, [rsp+88h+arg_18]
0x180046681  mov     r8, [rsp+88h+var_58]
0x180046686  mov     rcx, [rcx+8]
0x18004668a  mov     [rsp+88h+var_60], r13d
0x18004668f  mov     dword ptr [rsp+88h+var_68], eax
0x180046693  call    CompleteOverlappedIO
0x180046698  jmp     short loc_180046633
0x18004669a  mov     ecx, 3
0x18004669f  int     29h; Win8: RtlFailFast(ecx)
```
