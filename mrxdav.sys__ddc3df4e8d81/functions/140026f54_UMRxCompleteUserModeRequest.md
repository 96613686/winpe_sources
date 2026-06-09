# UMRxCompleteUserModeRequest

- ea: `0x140026f54`
- end: `0x140027207`
- name: `UMRxCompleteUserModeRequest`
- size: `691`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400262c4`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x140001b64`
- `0x14000610c`
- `0x140006880`
- `0x140026f54`
- `0x140027658`
- `0x140028af4`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140026f9f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026fdb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027047`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400270c7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027126`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400271c8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026f9f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026fdb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027047`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400270c7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027126`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400271c8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140027085`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140027085`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400270f6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400270f6`

## pseudocode

```c
__int64 __fastcall UMRxCompleteUserModeRequest(__int64 a1, __int64 a2, __int64 a3, unsigned int *a4)
{
  __int64 v7; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v9; // rbx
  HANDLE v10; // rax
  unsigned int v11; // esi
  __int64 v12; // rbx
  HANDLE v13; // rax
  int v14; // r12d
  int v15; // ebp
  __int64 v16; // rdi
  __int64 v17; // rbx
  HANDLE v18; // rax
  __int64 v19; // r14
  __int64 v20; // rbx
  HANDLE v21; // rax
  __int64 (__fastcall *v22)(__int64, __int64, __int64, _QWORD, int); // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rbx
  HANDLE v26; // rax
  unsigned int v28; // [rsp+80h] [rbp+18h]
  __int64 v29; // [rsp+88h] [rbp+20h] BYREF

  v28 = a3;
  v29 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v7 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v7, 69, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
    {
      v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v10 = PsGetCurrentThreadId();
      WPP_SF_qqq(v9, 70, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v10, a1, a2);
    }
  }
  v11 = UMRxVerifyHeader(a1, a2, a3, &v29);
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
    {
      v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v13 = PsGetCurrentThreadId();
      WPP_SF_qD(v12, 71, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v13, v11);
    }
  }
  else
  {
    v14 = 0;
    v15 = 1;
    ExAcquireResourceExclusiveLite(&UMRxAsyncEngineContextListLock, 1u);
    v16 = v29;
    if ( *(_DWORD *)(v29 + 48) == 1 )
    {
      v15 = 0;
      *(_DWORD *)(v29 + 48) = 2;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
    {
      v17 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v18 = PsGetCurrentThreadId();
      WPP_SF_qq(v17, 72, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v18, v16);
    }
    ExReleaseResourceLite(&UMRxAsyncEngineContextListLock);
    v19 = *(_QWORD *)(v16 + 80);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) != 0 )
    {
      v20 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v21 = PsGetCurrentThreadId();
      WPP_SF_qqq(v20, 73, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v21, v16, v19);
    }
    v22 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, int))(v16 + 384);
    *(_DWORD *)(v16 + 128) = *(_DWORD *)(a2 + 32);
    if ( v22 )
      v14 = v22(v16, v19, a2, v28, v15);
    UMRxFinalizeAsyncEngineContext(&v29);
    if ( v14 && !v15 )
      UMRxAsyncEngineCalldownIrpCompletion(v24, v23, v19);
  }
  *a4 = v11;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
  {
    v25 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v26 = PsGetCurrentThreadId();
    WPP_SF_qD(v25, 74, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v26, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x140026f54  mov     rax, rsp
0x140026f57  mov     [rax+8], rbx
0x140026f5b  mov     [rax+18h], r8d
0x140026f5f  push    rbp
0x140026f60  push    rsi
0x140026f61  push    rdi
0x140026f62  push    r12
0x140026f64  push    r13
0x140026f66  push    r14
0x140026f68  push    r15
0x140026f6a  sub     rsp, 30h
0x140026f6e  mov     r13, r9
0x140026f71  mov     qword ptr [rax+20h], 0
0x140026f79  mov     r15, rdx
0x140026f7c  mov     rdi, rcx
0x140026f7f  mov     rbx, cs:WPP_GLOBAL_Control
0x140026f86  lea     rsi, WPP_GLOBAL_Control
0x140026f8d  cmp     rbx, rsi
0x140026f90  jz      short loc_140027008
0x140026f92  test    dword ptr [rbx+2Ch], 800h
0x140026f99  jz      short loc_140026FC2
0x140026f9b  mov     rbx, [rbx+18h]
0x140026f9f  call    cs:__imp_PsGetCurrentThreadId
0x140026fa6  nop     dword ptr [rax+rax+00h]
0x140026fab  mov     edx, 45h ; 'E'
0x140026fb0  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140026fb7  mov     r9, rax
0x140026fba  mov     rcx, rbx
0x140026fbd  call    WPP_SF_q
0x140026fc2  mov     rbx, cs:WPP_GLOBAL_Control
0x140026fc9  cmp     rbx, rsi
0x140026fcc  jz      short loc_140027008
0x140026fce  test    dword ptr [rbx+2Ch], 200h
0x140026fd5  jz      short loc_140027008
0x140026fd7  mov     rbx, [rbx+18h]
0x140026fdb  call    cs:__imp_PsGetCurrentThreadId
0x140026fe2  nop     dword ptr [rax+rax+00h]
0x140026fe7  mov     edx, 46h ; 'F'
0x140026fec  mov     [rsp+68h+var_40], r15
0x140026ff1  mov     r9, rax
0x140026ff4  mov     [rsp+68h+var_48], rdi
0x140026ff9  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140027000  mov     rcx, rbx
0x140027003  call    WPP_SF_qqq
0x140027008  lea     r9, [rsp+68h+arg_18]
0x140027010  mov     rdx, r15
0x140027013  mov     rcx, rdi
0x140027016  call    UMRxVerifyHeader
0x14002701b  mov     esi, eax
0x14002701d  test    eax, eax
0x14002701f  jz      short loc_140027073
0x140027021  mov     rbx, cs:WPP_GLOBAL_Control
0x140027028  lea     r14, WPP_GLOBAL_Control
0x14002702f  cmp     rbx, r14
0x140027032  jz      loc_1400271AB
0x140027038  mov     ecx, [rbx+2Ch]
0x14002703b  test    cl, cl
0x14002703d  jns     loc_1400271AB
0x140027043  mov     rbx, [rbx+18h]
0x140027047  call    cs:__imp_PsGetCurrentThreadId
0x14002704e  nop     dword ptr [rax+rax+00h]
0x140027053  mov     edx, 47h ; 'G'
0x140027058  mov     dword ptr [rsp+68h+var_48], esi
0x14002705c  mov     r9, rax
0x14002705f  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140027066  mov     rcx, rbx
0x140027069  call    WPP_SF_qD
0x14002706e  jmp     loc_1400271AB
0x140027073  xor     r12d, r12d
0x140027076  lea     rcx, UMRxAsyncEngineContextListLock; Resource
0x14002707d  lea     ebp, [r12+1]
0x140027082  mov     dl, bpl; Wait
0x140027085  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14002708c  nop     dword ptr [rax+rax+00h]
0x140027091  mov     rdi, [rsp+68h+arg_18]
0x140027099  cmp     [rdi+30h], ebp
0x14002709c  jnz     short loc_1400270A9
0x14002709e  xor     ebp, ebp
0x1400270a0  mov     dword ptr [rdi+30h], 2
0x1400270a7  jmp     short loc_1400270EF
0x1400270a9  mov     rbx, cs:WPP_GLOBAL_Control
0x1400270b0  lea     r14, WPP_GLOBAL_Control
0x1400270b7  cmp     rbx, r14
0x1400270ba  jz      short loc_1400270EF
0x1400270bc  mov     eax, [rbx+2Ch]
0x1400270bf  test    al, al
0x1400270c1  jns     short loc_1400270EF
0x1400270c3  mov     rbx, [rbx+18h]
0x1400270c7  call    cs:__imp_PsGetCurrentThreadId
0x1400270ce  nop     dword ptr [rax+rax+00h]
0x1400270d3  mov     edx, 48h ; 'H'
0x1400270d8  mov     [rsp+68h+var_48], rdi
0x1400270dd  mov     r9, rax
0x1400270e0  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x1400270e7  mov     rcx, rbx
0x1400270ea  call    WPP_SF_qq
0x1400270ef  lea     rcx, UMRxAsyncEngineContextListLock; Resource
0x1400270f6  call    cs:__imp_ExReleaseResourceLite
0x1400270fd  nop     dword ptr [rax+rax+00h]
0x140027102  mov     r14, [rdi+50h]
0x140027106  mov     rbx, cs:WPP_GLOBAL_Control
0x14002710d  lea     rax, WPP_GLOBAL_Control
0x140027114  cmp     rbx, rax
0x140027117  jz      short loc_140027153
0x140027119  test    dword ptr [rbx+2Ch], 400h
0x140027120  jz      short loc_140027153
0x140027122  mov     rbx, [rbx+18h]
0x140027126  call    cs:__imp_PsGetCurrentThreadId
0x14002712d  nop     dword ptr [rax+rax+00h]
0x140027132  mov     edx, 49h ; 'I'
0x140027137  mov     [rsp+68h+var_40], r14
0x14002713c  mov     r9, rax
0x14002713f  mov     [rsp+68h+var_48], rdi
0x140027144  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x14002714b  mov     rcx, rbx
0x14002714e  call    WPP_SF_qqq
0x140027153  mov     rax, [rdi+180h]
0x14002715a  mov     edx, [r15+20h]
0x14002715e  mov     [rdi+80h], edx
0x140027164  test    rax, rax
0x140027167  jz      short loc_140027186
0x140027169  mov     r9d, [rsp+68h+arg_10]
0x140027171  mov     r8, r15
0x140027174  mov     rdx, r14
0x140027177  mov     dword ptr [rsp+68h+var_48], ebp
0x14002717b  mov     rcx, rdi
0x14002717e  call    _guard_dispatch_icall
0x140027183  mov     r12d, eax
0x140027186  lea     rcx, [rsp+68h+arg_18]
0x14002718e  call    UMRxFinalizeAsyncEngineContext
0x140027193  test    r12d, r12d
0x140027196  jz      short loc_1400271A4
0x140027198  test    ebp, ebp
0x14002719a  jnz     short loc_1400271A4
0x14002719c  mov     r8, r14
0x14002719f  call    UMRxAsyncEngineCalldownIrpCompletion
0x1400271a4  lea     r14, WPP_GLOBAL_Control
0x1400271ab  mov     [r13+0], esi
0x1400271af  mov     rbx, cs:WPP_GLOBAL_Control
0x1400271b6  cmp     rbx, r14
0x1400271b9  jz      short loc_1400271EF
0x1400271bb  test    dword ptr [rbx+2Ch], 800h
0x1400271c2  jz      short loc_1400271EF
0x1400271c4  mov     rbx, [rbx+18h]
0x1400271c8  call    cs:__imp_PsGetCurrentThreadId
0x1400271cf  nop     dword ptr [rax+rax+00h]
0x1400271d4  mov     edx, 4Ah ; 'J'
0x1400271d9  mov     dword ptr [rsp+68h+var_48], esi
0x1400271dd  mov     r9, rax
0x1400271e0  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x1400271e7  mov     rcx, rbx
0x1400271ea  call    WPP_SF_qD
0x1400271ef  mov     rbx, [rsp+68h+arg_0]
0x1400271f4  mov     eax, esi
0x1400271f6  add     rsp, 30h
0x1400271fa  pop     r15
0x1400271fc  pop     r14
0x1400271fe  pop     r13
0x140027200  pop     r12
0x140027202  pop     rdi
0x140027203  pop     rsi
0x140027204  pop     rbp
0x140027205  retn
```
