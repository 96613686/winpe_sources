# NOTIFICATION_SEND_RESPONSE::DoWork(ulong,long,ulong,int)

- ea: `0x180005700`
- end: `0x18000591e`
- name: `?DoWork@NOTIFICATION_SEND_RESPONSE@@UEAA?AW4ASYNC_STATUS@@KJKH@Z`
- size: `542`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, int, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800018c8`
- `0x180005030`
- `0x180005700`
- `0x180006010`
- `0x1800161f0`
- `0x180038010`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x1800057fa`
- `iisutil!WriteRefTraceLog` at `0x1800057fa`

## pseudocode

```c
__int64 __fastcall NOTIFICATION_SEND_RESPONSE::DoWork(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        int a4,
        unsigned int a5)
{
  __int64 v5; // r10
  __int64 v8; // r14
  unsigned int v9; // eax
  __int64 result; // rax
  __int64 v11; // rbp
  void (__fastcall ***v12)(__int64, __int64); // r15
  int v13; // eax
  signed __int64 v14; // rdx
  char v15; // r12
  int v16; // edx
  unsigned int v17; // r8d
  W3_RESPONSE *v18; // rcx
  int v19; // eax
  unsigned int v20; // edi
  struct _HTTP_LOG_DATA *v21; // [rsp+20h] [rbp-58h]
  int v22; // [rsp+28h] [rbp-50h]
  unsigned int v23[4]; // [rsp+40h] [rbp-38h] BYREF
  int v24; // [rsp+80h] [rbp+8h] BYREF

  v5 = *(_QWORD *)(a1 + 24);
  if ( *(_DWORD *)(v5 + 88) )
    v8 = *(_QWORD *)(v5 + 96);
  else
    v8 = *(_QWORD *)(a1 + 24);
  v9 = *(_DWORD *)(a1 + 124);
  if ( (v9 == -1 || *(_DWORD *)(*(_QWORD *)(a1 + 104) + 4LL * v9) == -1 || *(_BYTE *)(a1 + 165)) && a5 )
  {
    (**(void (__fastcall ***)(__int64, _QWORD))(a1 + 136))(a1 + 136, a3);
    result = 0;
    *(_DWORD *)(a1 + 76) = a2;
    return result;
  }
  v11 = *(_QWORD *)(v8 + 392);
  v12 = (void (__fastcall ***)(__int64, __int64))(a1 + 136);
  v13 = NOTIFICATION_CONTEXT::CallModules(a1, a5, a2, a3, a4, v5, a1 + 136);
  if ( v13 == 1 )
    return 1;
  if ( v13 == 2 )
  {
    *(_BYTE *)(a1 + 165) = 1;
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v8 + 40LL))(v8) )
    {
      W3_RESPONSE::ClearEntity(*(W3_RESPONSE **)(v8 + 64), *(unsigned __int8 *)(a1 + 166));
      return 0;
    }
  }
  v14 = *(_QWORD *)(a1 + 24);
  v15 = *(_BYTE *)(a1 + 164);
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)(*(_QWORD *)(v8 + 64) + 16LL), v14, 0) )
  {
    (**v12)(a1 + 136, 2147943397LL);
    return 0;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v14 + 76));
  if ( W3_CONTEXT_BASE::sm_pTraceLog )
    WriteRefTraceLog(W3_CONTEXT_BASE::sm_pTraceLog, *(unsigned int *)(v14 + 76), v14);
  *(_DWORD *)(v11 + 9356) |= 2u;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 52));
  v16 = *(unsigned __int8 *)(a1 + 164);
  v17 = *(_DWORD *)(a1 + 160);
  v18 = *(W3_RESPONSE **)(v8 + 64);
  v22 = *(unsigned __int8 *)(a1 + 166);
  v21 = *(struct _HTTP_LOG_DATA **)(a1 + 152);
  v23[0] = 0;
  v24 = 0;
  v19 = W3_RESPONSE::DoActualSendResponse(v18, v16, v17, v23, v21, v22, &v24);
  v20 = v19;
  if ( !v15 || v19 < 0 || !v24 )
  {
    *(_DWORD *)(v11 + 9356) &= ~2u;
    IISCORE_ASYNC_CONTEXT::ResetIoCompletionContext(*(IISCORE_ASYNC_CONTEXT **)(v8 + 64));
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 52));
    (**v12)(a1 + 136, v20);
    *(_DWORD *)(a1 + 76) = v23[0];
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180005700  push    rbx
0x180005702  push    rsi
0x180005703  push    rdi
0x180005704  push    r14
0x180005706  sub     rsp, 58h
0x18000570a  mov     r10, [rcx+18h]
0x18000570e  xor     esi, esi
0x180005710  mov     edi, edx
0x180005712  mov     rbx, rcx
0x180005715  cmp     [r10+58h], esi
0x180005719  jnz     loc_1800058C4
0x18000571f  mov     r14, r10
0x180005722  mov     eax, [rcx+7Ch]
0x180005725  cmp     eax, 0FFFFFFFFh
0x180005728  jz      short loc_180005736
0x18000572a  mov     ecx, eax
0x18000572c  mov     rax, [rbx+68h]
0x180005730  cmp     dword ptr [rax+rcx*4], 0FFFFFFFFh
0x180005734  jnz     short loc_180005764
0x180005736  cmp     [rsp+78h+arg_20], esi
0x18000573d  jz      short loc_18000576D
0x18000573f  lea     rcx, [rbx+88h]
0x180005746  mov     rdx, [rcx]
0x180005749  mov     rax, [rdx]
0x18000574c  mov     edx, r8d
0x18000574f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005754  mov     eax, esi
0x180005756  mov     [rbx+4Ch], edi
0x180005759  add     rsp, 58h
0x18000575d  pop     r14
0x18000575f  pop     rdi
0x180005760  pop     rsi
0x180005761  pop     rbx
0x180005762  retn
0x180005764  cmp     [rbx+0A5h], sil
0x18000576b  jnz     short loc_180005736
0x18000576d  mov     edx, [rsp+78h+arg_20]
0x180005774  mov     rcx, rbx
0x180005777  mov     [rsp+78h+arg_8], rbp
0x18000577f  mov     rbp, [r14+188h]
0x180005786  mov     [rsp+78h+var_28], r15
0x18000578b  lea     r15, [rbx+88h]
0x180005792  mov     [rsp+78h+var_48], r15
0x180005797  mov     qword ptr [rsp+78h+var_50], r10
0x18000579c  mov     dword ptr [rsp+78h+var_58], r9d
0x1800057a1  mov     r9d, r8d
0x1800057a4  mov     r8d, edi
0x1800057a7  call    ?CallModules@NOTIFICATION_CONTEXT@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@HKJKPEAVW3_CONTEXT_BASE@@PEAVIHttpEventProvider@@@Z; NOTIFICATION_CONTEXT::CallModules(int,ulong,long,ulong,W3_CONTEXT_BASE *,IHttpEventProvider *)
0x1800057ac  cmp     eax, 1
0x1800057af  jz      loc_1800058E2
0x1800057b5  cmp     eax, 2
0x1800057b8  jz      loc_1800058E9
0x1800057be  mov     rdx, [rbx+18h]
0x1800057c2  xor     eax, eax
0x1800057c4  mov     rcx, [r14+40h]
0x1800057c8  mov     [rsp+78h+arg_10], r12
0x1800057d0  movzx   r12d, byte ptr [rbx+0A4h]
0x1800057d8  lock cmpxchg [rcx+10h], rdx
0x1800057de  jnz     loc_1800058CD
0x1800057e4  lock inc dword ptr [rdx+4Ch]
0x1800057e8  mov     rcx, cs:?sm_pTraceLog@W3_CONTEXT_BASE@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONTEXT_BASE::sm_pTraceLog
0x1800057ef  test    rcx, rcx
0x1800057f2  jz      short loc_180005806
0x1800057f4  mov     r8, rdx
0x1800057f7  mov     edx, [rdx+4Ch]
0x1800057fa  call    cs:__imp_WriteRefTraceLog
0x180005801  nop     dword ptr [rax+rax+00h]
0x180005806  or      dword ptr [rbp+248Ch], 2
0x18000580d  lock inc dword ptr [rbx+34h]
0x180005811  movzx   eax, byte ptr [rbx+0A6h]
0x180005818  lea     rcx, [rsp+78h+arg_0]
0x180005820  movzx   edx, byte ptr [rbx+0A4h]; int
0x180005827  lea     r9, [rsp+78h+var_38]; unsigned int *
0x18000582c  mov     r8d, [rbx+0A0h]; unsigned int
0x180005833  mov     [rsp+78h+var_48], rcx; int *
0x180005838  mov     rcx, [r14+40h]; this
0x18000583c  mov     [rsp+78h+var_50], eax; int
0x180005840  mov     rax, [rbx+98h]
0x180005847  mov     [rsp+78h+var_58], rax; struct _HTTP_LOG_DATA *
0x18000584c  mov     [rsp+78h+var_38], esi
0x180005850  mov     [rsp+78h+arg_0], esi
0x180005857  call    ?DoActualSendResponse@W3_RESPONSE@@QEAAJHKPEAKPEAU_HTTP_LOG_DATA@@HPEAH@Z; W3_RESPONSE::DoActualSendResponse(int,ulong,ulong *,_HTTP_LOG_DATA *,int,int *)
0x18000585c  mov     edi, eax
0x18000585e  test    r12b, r12b
0x180005861  jz      short loc_180005895
0x180005863  test    eax, eax
0x180005865  js      short loc_180005895
0x180005867  cmp     [rsp+78h+arg_0], esi
0x18000586e  jz      short loc_180005895
0x180005870  mov     eax, 1
0x180005875  mov     r12, [rsp+78h+arg_10]
0x18000587d  mov     rbp, [rsp+78h+arg_8]
0x180005885  mov     r15, [rsp+78h+var_28]
0x18000588a  add     rsp, 58h
0x18000588e  pop     r14
0x180005890  pop     rdi
0x180005891  pop     rsi
0x180005892  pop     rbx
0x180005893  retn
0x180005895  and     dword ptr [rbp+248Ch], 0FFFFFFFDh
0x18000589c  mov     rcx, [r14+40h]; this
0x1800058a0  call    ?ResetIoCompletionContext@IISCORE_ASYNC_CONTEXT@@QEAAPEAVW3_CONTEXT_BASE@@XZ; IISCORE_ASYNC_CONTEXT::ResetIoCompletionContext(void)
0x1800058a5  lock dec dword ptr [rbx+34h]
0x1800058a9  mov     edx, edi
0x1800058ab  mov     rax, [r15]
0x1800058ae  mov     rcx, r15
0x1800058b1  mov     rax, [rax]
0x1800058b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058b9  mov     eax, [rsp+78h+var_38]
0x1800058bd  mov     [rbx+4Ch], eax
0x1800058c0  mov     eax, esi
0x1800058c2  jmp     short loc_180005875
0x1800058c4  mov     r14, [r10+60h]
0x1800058c8  jmp     loc_180005722
0x1800058cd  mov     rax, [r15]
0x1800058d0  mov     edx, 800703E5h
0x1800058d5  mov     rcx, r15
0x1800058d8  mov     rax, [rax]
0x1800058db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058e0  jmp     short loc_1800058C0
0x1800058e2  mov     eax, 1
0x1800058e7  jmp     short loc_18000587D
0x1800058e9  mov     byte ptr [rbx+0A5h], 1
0x1800058f0  mov     rcx, r14
0x1800058f3  mov     rax, [r14]
0x1800058f6  mov     rax, [rax+28h]
0x1800058fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058ff  test    eax, eax
0x180005901  jz      loc_1800057BE
0x180005907  movzx   edx, byte ptr [rbx+0A6h]; int
0x18000590e  mov     rcx, [r14+40h]; this
0x180005912  call    ?ClearEntity@W3_RESPONSE@@QEAAXH@Z; W3_RESPONSE::ClearEntity(int)
0x180005917  mov     eax, esi
0x180005919  jmp     loc_18000587D
```
