# MRxDAVFinalizeVNetRoot

- ea: `0x1400195b0`
- end: `0x140019886`
- name: `MRxDAVFinalizeVNetRoot`
- size: `726`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001b64`
- `0x140002ac4`
- `0x1400192b8`
- `0x1400195b0`
- `0x1400269d8`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1400195ef`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001962c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019751`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400197ce`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019819`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001984f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400195ef`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001962c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019751`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400197ce`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019819`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001984f`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14001967f`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14001967f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400196dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400196dd`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400196ef`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400196ef`
- `rdbss!RxCreateRxContext` at `0x140019717`
- `rdbss!RxCreateRxContext` at `0x140019717`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x1400197f4`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x1400197f4`

## pseudocode

```c
__int64 __fastcall MRxDAVFinalizeVNetRoot(__int64 a1)
{
  unsigned int v2; // ebp
  __int64 v3; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v5; // rdi
  __int64 v6; // rbx
  unsigned int v7; // eax
  __int64 v8; // rbx
  struct _RDBSS_DEVICE_OBJECT *v9; // rdi
  PRX_CONTEXT RxContext; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  struct _RX_CONTEXT *v13; // rdi
  __int64 v14; // rbx
  HANDLE v15; // rax
  __int64 v16; // rbx
  HANDLE v17; // rax
  __int64 v18; // rbx
  HANDLE v19; // rax
  __int64 v20; // rbx
  HANDLE v21; // rax

  v2 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
    {
      v3 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v3, 68, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
    {
      v5 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v6 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 88LL);
      v7 = (unsigned int)PsGetCurrentThreadId();
      WPP_SF_qZ(v5, 69, (unsigned int)WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v7, v6);
    }
  }
  if ( a1 )
  {
    v8 = *(_QWORD *)(a1 + 40);
    if ( v8 )
    {
      v9 = *(struct _RDBSS_DEVICE_OBJECT **)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL) + 48LL);
      *(_QWORD *)(a1 + 40) = 0;
      if ( *(_BYTE *)(v8 + 72) )
        SeDeleteClientSecurity(v8);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        WPP_SF_qqq(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          70,
          WPP_295ecfbeda123026d67516205ca0d119_Traceguids,
          *(_QWORD *)(a1 + 48),
          *(_QWORD *)(a1 + 32),
          a1);
      MRxDAVDereferenceNetRootContext(*(char **)(a1 + 48));
      *(_QWORD *)(a1 + 48) = 0;
      if ( *(_WORD *)(v8 + 114) )
      {
        ExFreePoolWithTag(*(PVOID *)(v8 + 120), 0);
        RtlInitUnicodeString((PUNICODE_STRING)(v8 + 112), 0);
      }
      if ( *(_DWORD *)(v8 + 100) || !*(_DWORD *)(v8 + 76) )
      {
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v2;
        if ( _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
        {
          v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v19 = PsGetCurrentThreadId();
          WPP_SF_q(v18, 71, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v19);
        }
      }
      else
      {
        RxContext = RxCreateRxContext(0, v9, 0);
        v13 = RxContext;
        if ( RxContext )
        {
          RxContext->MRxContext[3] = (PVOID)a1;
          RxContext->WriteOnlyOpenRetryContext = (PVOID)v8;
          v2 = UMRxAsyncEngOuterWrapper(
                 (__int64)RxContext,
                 v11,
                 v12,
                 6u,
                 (__int64 (__fastcall *)(__int64, __int64))MRxDAVFinalizeVNetRootContinuation,
                 (__int64)"MRxDAVFinalizeVNetRoot");
          if ( v2
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
          {
            v16 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v17 = PsGetCurrentThreadId();
            WPP_SF_qD(v16, 73, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v17, v2);
          }
          RxDereferenceAndDeleteRxContext_Real(v13);
        }
        else
        {
          v2 = -1073741670;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v2;
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
          {
            v14 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v15 = PsGetCurrentThreadId();
            WPP_SF_qD(v14, 72, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v15, -1073741670);
          }
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
  {
    v20 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v21 = PsGetCurrentThreadId();
    WPP_SF_qD(v20, 74, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v21, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x1400195b0  push    rbx
0x1400195b2  push    rbp
0x1400195b3  push    rsi
0x1400195b4  push    rdi
0x1400195b5  push    r12
0x1400195b7  push    r13
0x1400195b9  push    r14
0x1400195bb  push    r15
0x1400195bd  sub     rsp, 38h
0x1400195c1  xor     r14d, r14d
0x1400195c4  mov     rsi, rcx
0x1400195c7  mov     ebp, r14d
0x1400195ca  mov     rbx, cs:WPP_GLOBAL_Control
0x1400195d1  lea     r15, WPP_GLOBAL_Control
0x1400195d8  lea     r12, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x1400195df  cmp     rbx, r15
0x1400195e2  jz      short loc_140019650
0x1400195e4  bt      dword ptr [rbx+2Ch], 0Eh
0x1400195e9  jnb     short loc_14001960D
0x1400195eb  mov     rbx, [rbx+18h]
0x1400195ef  call    cs:__imp_PsGetCurrentThreadId
0x1400195f6  nop     dword ptr [rax+rax+00h]
0x1400195fb  lea     edx, [r14+44h]
0x1400195ff  mov     r8, r12
0x140019602  mov     r9, rax
0x140019605  mov     rcx, rbx
0x140019608  call    WPP_SF_q
0x14001960d  mov     rdi, cs:WPP_GLOBAL_Control
0x140019614  cmp     rdi, r15
0x140019617  jz      short loc_140019650
0x140019619  bt      dword ptr [rdi+2Ch], 0Eh
0x14001961e  jnb     short loc_140019650
0x140019620  mov     rax, [rsi+20h]
0x140019624  mov     rdi, [rdi+18h]
0x140019628  mov     rbx, [rax+58h]
0x14001962c  call    cs:__imp_PsGetCurrentThreadId
0x140019633  nop     dword ptr [rax+rax+00h]
0x140019638  mov     edx, 45h ; 'E'
0x14001963d  mov     [rsp+78h+var_58], rbx
0x140019642  mov     r9, rax
0x140019645  mov     r8, r12
0x140019648  mov     rcx, rdi
0x14001964b  call    WPP_SF_qZ
0x140019650  test    rsi, rsi
0x140019653  jz      loc_140019838
0x140019659  mov     rbx, [rsi+28h]
0x14001965d  test    rbx, rbx
0x140019660  jz      loc_140019838
0x140019666  mov     rax, [rsi+20h]
0x14001966a  mov     rcx, [rax+20h]
0x14001966e  mov     rdi, [rcx+30h]
0x140019672  mov     [rsi+28h], r14
0x140019676  cmp     [rbx+48h], r14b
0x14001967a  jz      short loc_14001968B
0x14001967c  mov     rcx, rbx
0x14001967f  call    cs:__imp_SeDeleteClientSecurity
0x140019686  nop     dword ptr [rax+rax+00h]
0x14001968b  mov     rcx, cs:WPP_GLOBAL_Control
0x140019692  cmp     rcx, r15
0x140019695  jz      short loc_1400196C3
0x140019697  test    dword ptr [rcx+2Ch], 2000h
0x14001969e  jz      short loc_1400196C3
0x1400196a0  mov     rax, [rsi+20h]
0x1400196a4  mov     edx, 46h ; 'F'
0x1400196a9  mov     r9, [rsi+30h]
0x1400196ad  mov     r8, r12
0x1400196b0  mov     rcx, [rcx+18h]
0x1400196b4  mov     [rsp+78h+var_50], rsi
0x1400196b9  mov     [rsp+78h+var_58], rax
0x1400196be  call    WPP_SF_qqq
0x1400196c3  mov     rcx, [rsi+30h]; P
0x1400196c7  call    MRxDAVDereferenceNetRootContext
0x1400196cc  mov     [rsi+30h], r14
0x1400196d0  cmp     [rbx+72h], r14w
0x1400196d5  jz      short loc_1400196FB
0x1400196d7  mov     rcx, [rbx+78h]; P
0x1400196db  xor     edx, edx; Tag
0x1400196dd  call    cs:__imp_ExFreePoolWithTag
0x1400196e4  nop     dword ptr [rax+rax+00h]
0x1400196e9  lea     rcx, [rbx+70h]; DestinationString
0x1400196ed  xor     edx, edx; SourceString
0x1400196ef  call    cs:__imp_RtlInitUnicodeString
0x1400196f6  nop     dword ptr [rax+rax+00h]
0x1400196fb  cmp     [rbx+64h], r14d
0x1400196ff  jnz     loc_140019802
0x140019705  cmp     [rbx+4Ch], r14d
0x140019709  jz      loc_140019802
0x14001970f  xor     r8d, r8d; InitialContextFlags
0x140019712  mov     rdx, rdi; RxDeviceObject
0x140019715  xor     ecx, ecx; Irp
0x140019717  call    cs:__imp_RxCreateRxContext
0x14001971e  nop     dword ptr [rax+rax+00h]
0x140019723  mov     rdi, rax
0x140019726  test    rax, rax
0x140019729  jnz     short loc_14001977B
0x14001972b  mov     ebp, 0C000009Ah
0x140019730  mov     rbx, cs:WPP_GLOBAL_Control
0x140019737  cmp     rbx, r15
0x14001973a  jz      loc_140019872
0x140019740  test    dword ptr [rbx+2Ch], 2000h
0x140019747  jz      loc_140019838
0x14001974d  mov     rbx, [rbx+18h]
0x140019751  call    cs:__imp_PsGetCurrentThreadId
0x140019758  nop     dword ptr [rax+rax+00h]
0x14001975d  lea     edx, [rdi+48h]
0x140019760  mov     dword ptr [rsp+78h+var_58], 0C000009Ah
0x140019768  mov     r9, rax
0x14001976b  mov     r8, r12
0x14001976e  mov     rcx, rbx
0x140019771  call    WPP_SF_qD
0x140019776  jmp     loc_140019838
0x14001977b  mov     [rax+0D8h], rsi
0x140019782  mov     r9d, 6
0x140019788  mov     [rax+0E0h], rbx
0x14001978f  mov     rcx, rdi
0x140019792  lea     rax, aMrxdavfinalize_0; "MRxDAVFinalizeVNetRoot"
0x140019799  mov     [rsp+78h+var_50], rax
0x14001979e  lea     rax, MRxDAVFinalizeVNetRootContinuation
0x1400197a5  mov     [rsp+78h+var_58], rax
0x1400197aa  call    UMRxAsyncEngOuterWrapper
0x1400197af  mov     ebp, eax
0x1400197b1  test    eax, eax
0x1400197b3  jz      short loc_1400197F1
0x1400197b5  mov     rbx, cs:WPP_GLOBAL_Control
0x1400197bc  cmp     rbx, r15
0x1400197bf  jz      short loc_1400197F1
0x1400197c1  test    dword ptr [rbx+2Ch], 2000h
0x1400197c8  jz      short loc_1400197F1
0x1400197ca  mov     rbx, [rbx+18h]
0x1400197ce  call    cs:__imp_PsGetCurrentThreadId
0x1400197d5  nop     dword ptr [rax+rax+00h]
0x1400197da  mov     edx, 49h ; 'I'
0x1400197df  mov     dword ptr [rsp+78h+var_58], ebp
0x1400197e3  mov     r9, rax
0x1400197e6  mov     r8, r12
0x1400197e9  mov     rcx, rbx
0x1400197ec  call    WPP_SF_qD
0x1400197f1  mov     rcx, rdi; RxContext
0x1400197f4  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x1400197fb  nop     dword ptr [rax+rax+00h]
0x140019800  jmp     short loc_140019838
0x140019802  mov     rbx, cs:WPP_GLOBAL_Control
0x140019809  cmp     rbx, r15
0x14001980c  jz      short loc_140019872
0x14001980e  bt      dword ptr [rbx+2Ch], 0Eh
0x140019813  jnb     short loc_140019838
0x140019815  mov     rbx, [rbx+18h]
0x140019819  call    cs:__imp_PsGetCurrentThreadId
0x140019820  nop     dword ptr [rax+rax+00h]
0x140019825  mov     edx, 47h ; 'G'
0x14001982a  mov     r8, r12
0x14001982d  mov     r9, rax
0x140019830  mov     rcx, rbx
0x140019833  call    WPP_SF_q
0x140019838  mov     rbx, cs:WPP_GLOBAL_Control
0x14001983f  cmp     rbx, r15
0x140019842  jz      short loc_140019872
0x140019844  bt      dword ptr [rbx+2Ch], 0Eh
0x140019849  jnb     short loc_140019872
0x14001984b  mov     rbx, [rbx+18h]
0x14001984f  call    cs:__imp_PsGetCurrentThreadId
0x140019856  nop     dword ptr [rax+rax+00h]
0x14001985b  mov     edx, 4Ah ; 'J'
0x140019860  mov     dword ptr [rsp+78h+var_58], ebp
0x140019864  mov     r9, rax
0x140019867  mov     r8, r12
0x14001986a  mov     rcx, rbx
0x14001986d  call    WPP_SF_qD
0x140019872  mov     eax, ebp
0x140019874  add     rsp, 38h
0x140019878  pop     r15
0x14001987a  pop     r14
0x14001987c  pop     r13
0x14001987e  pop     r12
0x140019880  pop     rdi
0x140019881  pop     rsi
0x140019882  pop     rbp
0x140019883  pop     rbx
0x140019884  retn
```
