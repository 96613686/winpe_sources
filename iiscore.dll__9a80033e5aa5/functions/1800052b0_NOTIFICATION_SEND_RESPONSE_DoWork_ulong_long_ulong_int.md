# NOTIFICATION_SEND_RESPONSE::DoWork(ulong,long,ulong,int)

- ea: `0x1800052b0`
- end: `0x1800054c6`
- name: `?DoWork@NOTIFICATION_SEND_RESPONSE@@UEAA?AW4ASYNC_STATUS@@KJKH@Z`
- size: `534`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001850`
- `0x180004c00`
- `0x1800052b0`
- `0x180005ba0`
- `0x180014ff0`
- `0x180035010`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x1800053a9`
- `iisutil!WriteRefTraceLog` at `0x1800053a9`

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
0x1800052b0  push    rbx
0x1800052b2  push    rsi
0x1800052b3  push    rdi
0x1800052b4  push    r14
0x1800052b6  sub     rsp, 58h
0x1800052ba  mov     r10, [rcx+18h]
0x1800052be  xor     esi, esi
0x1800052c0  mov     edi, edx
0x1800052c2  mov     rbx, rcx
0x1800052c5  cmp     [r10+58h], esi
0x1800052c9  jnz     loc_18000546C
0x1800052cf  mov     r14, r10
0x1800052d2  mov     eax, [rcx+7Ch]
0x1800052d5  cmp     eax, 0FFFFFFFFh
0x1800052d8  jz      short loc_1800052E6
0x1800052da  mov     ecx, eax
0x1800052dc  mov     rax, [rbx+68h]
0x1800052e0  cmp     dword ptr [rax+rcx*4], 0FFFFFFFFh
0x1800052e4  jnz     short loc_180005313
0x1800052e6  cmp     [rsp+78h+arg_20], esi
0x1800052ed  jz      short loc_18000531C
0x1800052ef  lea     rcx, [rbx+88h]
0x1800052f6  mov     rdx, [rcx]
0x1800052f9  mov     rax, [rdx]
0x1800052fc  mov     edx, r8d
0x1800052ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005304  mov     eax, esi
0x180005306  mov     [rbx+4Ch], edi
0x180005309  add     rsp, 58h
0x18000530d  pop     r14
0x18000530f  pop     rdi
0x180005310  pop     rsi
0x180005311  pop     rbx
0x180005312  retn
0x180005313  cmp     [rbx+0A5h], sil
0x18000531a  jnz     short loc_1800052E6
0x18000531c  mov     edx, [rsp+78h+arg_20]
0x180005323  mov     rcx, rbx
0x180005326  mov     [rsp+78h+arg_8], rbp
0x18000532e  mov     rbp, [r14+188h]
0x180005335  mov     [rsp+78h+var_28], r15
0x18000533a  lea     r15, [rbx+88h]
0x180005341  mov     [rsp+78h+var_48], r15
0x180005346  mov     qword ptr [rsp+78h+var_50], r10
0x18000534b  mov     dword ptr [rsp+78h+var_58], r9d
0x180005350  mov     r9d, r8d
0x180005353  mov     r8d, edi
0x180005356  call    ?CallModules@NOTIFICATION_CONTEXT@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@HKJKPEAVW3_CONTEXT_BASE@@PEAVIHttpEventProvider@@@Z; NOTIFICATION_CONTEXT::CallModules(int,ulong,long,ulong,W3_CONTEXT_BASE *,IHttpEventProvider *)
0x18000535b  cmp     eax, 1
0x18000535e  jz      loc_18000548A
0x180005364  cmp     eax, 2
0x180005367  jz      loc_180005491
0x18000536d  mov     rdx, [rbx+18h]
0x180005371  xor     eax, eax
0x180005373  mov     rcx, [r14+40h]
0x180005377  mov     [rsp+78h+arg_10], r12
0x18000537f  movzx   r12d, byte ptr [rbx+0A4h]
0x180005387  lock cmpxchg [rcx+10h], rdx
0x18000538d  jnz     loc_180005475
0x180005393  lock inc dword ptr [rdx+4Ch]
0x180005397  mov     rcx, cs:?sm_pTraceLog@W3_CONTEXT_BASE@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONTEXT_BASE::sm_pTraceLog
0x18000539e  test    rcx, rcx
0x1800053a1  jz      short loc_1800053AF
0x1800053a3  mov     r8, rdx
0x1800053a6  mov     edx, [rdx+4Ch]
0x1800053a9  call    cs:__imp_WriteRefTraceLog
0x1800053af  or      dword ptr [rbp+248Ch], 2
0x1800053b6  lock inc dword ptr [rbx+34h]
0x1800053ba  movzx   eax, byte ptr [rbx+0A6h]
0x1800053c1  lea     rcx, [rsp+78h+arg_0]
0x1800053c9  movzx   edx, byte ptr [rbx+0A4h]; int
0x1800053d0  lea     r9, [rsp+78h+var_38]; unsigned int *
0x1800053d5  mov     r8d, [rbx+0A0h]; unsigned int
0x1800053dc  mov     [rsp+78h+var_48], rcx; int *
0x1800053e1  mov     rcx, [r14+40h]; this
0x1800053e5  mov     [rsp+78h+var_50], eax; int
0x1800053e9  mov     rax, [rbx+98h]
0x1800053f0  mov     [rsp+78h+var_58], rax; struct _HTTP_LOG_DATA *
0x1800053f5  mov     [rsp+78h+var_38], esi
0x1800053f9  mov     [rsp+78h+arg_0], esi
0x180005400  call    ?DoActualSendResponse@W3_RESPONSE@@QEAAJHKPEAKPEAU_HTTP_LOG_DATA@@HPEAH@Z; W3_RESPONSE::DoActualSendResponse(int,ulong,ulong *,_HTTP_LOG_DATA *,int,int *)
0x180005405  mov     edi, eax
0x180005407  test    r12b, r12b
0x18000540a  jz      short loc_18000543D
0x18000540c  test    eax, eax
0x18000540e  js      short loc_18000543D
0x180005410  cmp     [rsp+78h+arg_0], esi
0x180005417  jz      short loc_18000543D
0x180005419  mov     eax, 1
0x18000541e  mov     r12, [rsp+78h+arg_10]
0x180005426  mov     rbp, [rsp+78h+arg_8]
0x18000542e  mov     r15, [rsp+78h+var_28]
0x180005433  add     rsp, 58h
0x180005437  pop     r14
0x180005439  pop     rdi
0x18000543a  pop     rsi
0x18000543b  pop     rbx
0x18000543c  retn
0x18000543d  and     dword ptr [rbp+248Ch], 0FFFFFFFDh
0x180005444  mov     rcx, [r14+40h]; this
0x180005448  call    ?ResetIoCompletionContext@IISCORE_ASYNC_CONTEXT@@QEAAPEAVW3_CONTEXT_BASE@@XZ; IISCORE_ASYNC_CONTEXT::ResetIoCompletionContext(void)
0x18000544d  lock dec dword ptr [rbx+34h]
0x180005451  mov     edx, edi
0x180005453  mov     rax, [r15]
0x180005456  mov     rcx, r15
0x180005459  mov     rax, [rax]
0x18000545c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005461  mov     eax, [rsp+78h+var_38]
0x180005465  mov     [rbx+4Ch], eax
0x180005468  mov     eax, esi
0x18000546a  jmp     short loc_18000541E
0x18000546c  mov     r14, [r10+60h]
0x180005470  jmp     loc_1800052D2
0x180005475  mov     rax, [r15]
0x180005478  mov     edx, 800703E5h
0x18000547d  mov     rcx, r15
0x180005480  mov     rax, [rax]
0x180005483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005488  jmp     short loc_180005468
0x18000548a  mov     eax, 1
0x18000548f  jmp     short loc_180005426
0x180005491  mov     byte ptr [rbx+0A5h], 1
0x180005498  mov     rcx, r14
0x18000549b  mov     rax, [r14]
0x18000549e  mov     rax, [rax+28h]
0x1800054a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054a7  test    eax, eax
0x1800054a9  jz      loc_18000536D
0x1800054af  movzx   edx, byte ptr [rbx+0A6h]; int
0x1800054b6  mov     rcx, [r14+40h]; this
0x1800054ba  call    ?ClearEntity@W3_RESPONSE@@QEAAXH@Z; W3_RESPONSE::ClearEntity(int)
0x1800054bf  mov     eax, esi
0x1800054c1  jmp     loc_180005426
```
