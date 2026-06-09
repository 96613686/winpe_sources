# UMRxFinalizeAsyncEngineContext

- ea: `0x140027658`
- end: `0x140027a17`
- name: `UMRxFinalizeAsyncEngineContext`
- size: `959`
- prototype: `char __fastcall(__int64 *)`
- caller_count: `10`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140005554`
- `0x14001bdf0`
- `0x14001e6a0`
- `0x1400269d8`
- `0x140026dfc`
- `0x140026f54`
- `0x140027f1c`
- `0x1400286f0`
- `0x1400287f4`
- `0x140028af4`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x140001838`
- `0x140001b64`
- `0x140027658`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14002769a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400276d2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027723`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002783d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400278c8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027906`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400279e0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002769a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400276d2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027723`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002783d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400278c8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027906`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400279e0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140027762`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140027762`
- `ntoskrnl!ExReleaseResourceLite` at `0x140027777`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400277ad`
- `ntoskrnl!ExReleaseResourceLite` at `0x140027777`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400277ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400279ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400279ac`
- `ntoskrnl!IoFreeMdl` at `0x140027872`
- `ntoskrnl!IoFreeMdl` at `0x140027872`
- `ntoskrnl!IoFreeIrp` at `0x140027881`
- `ntoskrnl!IoFreeIrp` at `0x140027881`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x1400277f1`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x1400277f1`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x14002799b`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x14002799b`
- `rdbss!RxCompleteRequestEx` at `0x14002798b`
- `rdbss!RxCompleteRequestEx` at `0x14002798b`
- `rdbss!RxLowIoCompletion` at `0x140027955`
- `rdbss!RxLowIoCompletion` at `0x140027955`

## pseudocode

```c
char __fastcall UMRxFinalizeAsyncEngineContext(__int64 *a1)
{
  __int64 v1; // rsi
  __int64 v3; // rbp
  __int64 v4; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v6; // rbx
  HANDLE v7; // rax
  signed __int32 v8; // edi
  __int64 v9; // rbx
  HANDLE v10; // rax
  __int64 v12; // rdx
  _QWORD *v13; // rcx
  unsigned int v14; // ebx
  IRP *v15; // r15
  char v16; // r12
  int v17; // ebx
  __int64 v18; // rdi
  HANDLE v19; // rax
  struct _MDL *MdlAddress; // rcx
  __int64 v21; // rbx
  HANDLE v22; // rax
  __int64 v23; // rbx
  __int64 v24; // rdi
  HANDLE v25; // rax
  int v26; // eax
  __int64 v27; // rbx
  HANDLE v28; // rax
  ULONG_PTR RegionSize; // [rsp+80h] [rbp+8h] BYREF

  v1 = *a1;
  v3 = *(_QWORD *)(*a1 + 80);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v4 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v4, 33, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v7 = PsGetCurrentThreadId();
      WPP_SF_qqq(v6, 34, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v7, v1, v3);
    }
  }
  v8 = _InterlockedDecrement((volatile signed __int32 *)(v1 + 4));
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xAu) )
      {
        v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v10 = PsGetCurrentThreadId();
        WPP_SF_qD(v9, 35, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v10, v8);
      }
    }
    return 0;
  }
  if ( (unsigned __int8)(*(_BYTE *)(v3 + 32) - 3) > 1u )
  {
    ExAcquireResourceExclusiveLite(&UMRxAsyncEngineContextListLock, 1u);
    if ( *(_DWORD *)(v1 + 4) )
    {
      ExReleaseResourceLite(&UMRxAsyncEngineContextListLock);
      return 0;
    }
    v12 = *(_QWORD *)(v1 + 32);
    if ( *(_QWORD *)(v12 + 8) != v1 + 32 || (v13 = *(_QWORD **)(v1 + 40), *v13 != v1 + 32) )
      __fastfail(3u);
    *v13 = v12;
    *(_QWORD *)(v12 + 8) = v13;
    ExReleaseResourceLite(&UMRxAsyncEngineContextListLock);
  }
  if ( *(_DWORD *)(v1 + 224) )
  {
    v14 = 0;
    do
    {
      RegionSize = 0;
      ZwFreeVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, (PVOID *)(v1 + 232 + 16LL * v14++), &RegionSize, 0x8000u);
    }
    while ( v14 < *(_DWORD *)(v1 + 224) );
  }
  v15 = *(IRP **)(v1 + 120);
  v16 = *(_BYTE *)(v1 + 208) & 1;
  if ( v15 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xAu) )
    {
      v17 = *(unsigned __int8 *)(v3 + 32);
      v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v19 = PsGetCurrentThreadId();
      WPP_SF_qqD(v18, 36, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v19, v15, v17);
    }
    MdlAddress = v15->MdlAddress;
    if ( MdlAddress )
      IoFreeMdl(MdlAddress);
    IoFreeIrp(v15);
  }
  if ( v16 && *(_DWORD *)(v1 + 56) && *(_DWORD *)(v1 + 48) != 3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xAu) )
      {
        v21 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v22 = PsGetCurrentThreadId();
        WPP_SF_q(v21, 37, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v22);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xAu) )
      {
        v23 = *(_QWORD *)(v3 + 40);
        v24 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v25 = PsGetCurrentThreadId();
        WPP_SF_qq(v24, 38, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v25, v23);
      }
    }
    v26 = *(_DWORD *)(v1 + 128);
    if ( *(_QWORD *)(v3 + 528) )
    {
      *(_DWORD *)(v3 + 176) = v26;
      *(_QWORD *)(v3 + 184) = *(_QWORD *)(v1 + 136);
      RxLowIoCompletion((PRX_CONTEXT)v3);
    }
    else
    {
      *(_DWORD *)(*(_QWORD *)(v3 + 40) + 48LL) = v26;
      *(_QWORD *)(*(_QWORD *)(v3 + 40) + 56LL) = *(_QWORD *)(v1 + 136);
      RxCompleteRequestEx(v3, *(_QWORD *)(v3 + 40), *(unsigned int *)(v1 + 128));
    }
  }
  RxDereferenceAndDeleteRxContext_Real(*(PRX_CONTEXT *)(v1 + 80));
  ExFreePoolWithTag((PVOID)v1, 0);
  *a1 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
  {
    v27 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v28 = PsGetCurrentThreadId();
    WPP_SF_q(v27, 41, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v28);
  }
  return 1;
}

```

## disassembly

```asm
0x140027658  push    rbx
0x14002765a  push    rbp
0x14002765b  push    rsi
0x14002765c  push    rdi
0x14002765d  push    r12
0x14002765f  push    r13
0x140027661  push    r14
0x140027663  push    r15
0x140027665  sub     rsp, 38h
0x140027669  mov     rsi, [rcx]
0x14002766c  mov     r13, rcx
0x14002766f  mov     rbp, [rsi+50h]
0x140027673  mov     rbx, cs:WPP_GLOBAL_Control
0x14002767a  lea     r14, WPP_GLOBAL_Control
0x140027681  lea     r15, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140027688  cmp     rbx, r14
0x14002768b  jz      short loc_1400276FB
0x14002768d  test    dword ptr [rbx+2Ch], 800h
0x140027694  jz      short loc_1400276B9
0x140027696  mov     rbx, [rbx+18h]
0x14002769a  call    cs:__imp_PsGetCurrentThreadId
0x1400276a1  nop     dword ptr [rax+rax+00h]
0x1400276a6  mov     edx, 21h ; '!'
0x1400276ab  mov     r8, r15
0x1400276ae  mov     r9, rax
0x1400276b1  mov     rcx, rbx
0x1400276b4  call    WPP_SF_q
0x1400276b9  mov     rbx, cs:WPP_GLOBAL_Control
0x1400276c0  cmp     rbx, r14
0x1400276c3  jz      short loc_1400276FB
0x1400276c5  test    dword ptr [rbx+2Ch], 200h
0x1400276cc  jz      short loc_1400276FB
0x1400276ce  mov     rbx, [rbx+18h]
0x1400276d2  call    cs:__imp_PsGetCurrentThreadId
0x1400276d9  nop     dword ptr [rax+rax+00h]
0x1400276de  mov     edx, 22h ; '"'
0x1400276e3  mov     [rsp+78h+var_50], rbp
0x1400276e8  mov     r9, rax
0x1400276eb  mov     [rsp+78h+var_58], rsi
0x1400276f0  mov     r8, r15
0x1400276f3  mov     rcx, rbx
0x1400276f6  call    WPP_SF_qqq
0x1400276fb  or      r12, 0FFFFFFFFFFFFFFFFh
0x1400276ff  mov     edi, r12d
0x140027702  lock xadd [rsi+4], edi
0x140027707  add     edi, r12d
0x14002770a  jz      short loc_14002774D
0x14002770c  mov     rbx, cs:WPP_GLOBAL_Control
0x140027713  cmp     rbx, r14
0x140027716  jz      short loc_140027746
0x140027718  bt      dword ptr [rbx+2Ch], 0Ah
0x14002771d  jnb     short loc_140027746
0x14002771f  mov     rbx, [rbx+18h]
0x140027723  call    cs:__imp_PsGetCurrentThreadId
0x14002772a  nop     dword ptr [rax+rax+00h]
0x14002772f  lea     edx, [r12+24h]
0x140027734  mov     dword ptr [rsp+78h+var_58], edi
0x140027738  mov     r9, rax
0x14002773b  mov     r8, r15
0x14002773e  mov     rcx, rbx
0x140027741  call    WPP_SF_qD
0x140027746  xor     al, al
0x140027748  jmp     loc_140027A05
0x14002774d  mov     al, [rbp+20h]
0x140027750  sub     al, 3
0x140027752  cmp     al, 1
0x140027754  jbe     short loc_1400277B9
0x140027756  lea     rbx, UMRxAsyncEngineContextListLock
0x14002775d  mov     dl, 1; Wait
0x14002775f  mov     rcx, rbx; Resource
0x140027762  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140027769  nop     dword ptr [rax+rax+00h]
0x14002776e  cmp     dword ptr [rsi+4], 0
0x140027772  jz      short loc_140027785
0x140027774  mov     rcx, rbx; Resource
0x140027777  call    cs:__imp_ExReleaseResourceLite
0x14002777e  nop     dword ptr [rax+rax+00h]
0x140027783  jmp     short loc_140027746
0x140027785  lea     rax, [rsi+20h]
0x140027789  mov     rdx, [rax]
0x14002778c  cmp     [rdx+8], rax
0x140027790  jnz     loc_140027963
0x140027796  mov     rcx, [rax+8]
0x14002779a  cmp     [rcx], rax
0x14002779d  jnz     loc_140027963
0x1400277a3  mov     [rcx], rdx
0x1400277a6  mov     [rdx+8], rcx
0x1400277aa  mov     rcx, rbx; Resource
0x1400277ad  call    cs:__imp_ExReleaseResourceLite
0x1400277b4  nop     dword ptr [rax+rax+00h]
0x1400277b9  cmp     dword ptr [rsi+0E0h], 0
0x1400277c0  jbe     short loc_140027807
0x1400277c2  xor     ebx, ebx
0x1400277c4  lea     rdi, [rsi+0E8h]
0x1400277cb  mov     edx, ebx
0x1400277cd  lea     r8, [rsp+78h+RegionSize]; RegionSize
0x1400277d5  shl     rdx, 4
0x1400277d9  mov     r9d, 8000h; FreeType
0x1400277df  add     rdx, rdi; BaseAddress
0x1400277e2  mov     [rsp+78h+RegionSize], 0
0x1400277ee  mov     rcx, r12; ProcessHandle
0x1400277f1  call    cs:__imp_ZwFreeVirtualMemory
0x1400277f8  nop     dword ptr [rax+rax+00h]
0x1400277fd  inc     ebx
0x1400277ff  cmp     ebx, [rsi+0E0h]
0x140027805  jb      short loc_1400277CB
0x140027807  mov     r12b, [rsi+0D0h]
0x14002780e  mov     r15, [rsi+78h]
0x140027812  and     r12b, 1
0x140027816  test    r15, r15
0x140027819  jz      short loc_14002788D
0x14002781b  mov     rdi, cs:WPP_GLOBAL_Control
0x140027822  lea     rax, WPP_GLOBAL_Control
0x140027829  cmp     rdi, rax
0x14002782c  jz      short loc_140027869
0x14002782e  bt      dword ptr [rdi+2Ch], 0Ah
0x140027833  jnb     short loc_140027869
0x140027835  movzx   ebx, byte ptr [rbp+20h]
0x140027839  mov     rdi, [rdi+18h]
0x14002783d  call    cs:__imp_PsGetCurrentThreadId
0x140027844  nop     dword ptr [rax+rax+00h]
0x140027849  mov     edx, 24h ; '$'
0x14002784e  mov     dword ptr [rsp+78h+var_50], ebx
0x140027852  mov     r9, rax
0x140027855  mov     [rsp+78h+var_58], r15
0x14002785a  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140027861  mov     rcx, rdi
0x140027864  call    WPP_SF_qqD
0x140027869  mov     rcx, [r15+8]; Mdl
0x14002786d  test    rcx, rcx
0x140027870  jz      short loc_14002787E
0x140027872  call    cs:__imp_IoFreeMdl
0x140027879  nop     dword ptr [rax+rax+00h]
0x14002787e  mov     rcx, r15; Irp
0x140027881  call    cs:__imp_IoFreeIrp
0x140027888  nop     dword ptr [rax+rax+00h]
0x14002788d  test    r12b, r12b
0x140027890  jz      loc_140027997
0x140027896  cmp     dword ptr [rsi+38h], 0
0x14002789a  jz      loc_140027997
0x1400278a0  cmp     dword ptr [rsi+30h], 3
0x1400278a4  jz      loc_140027997
0x1400278aa  mov     rbx, cs:WPP_GLOBAL_Control
0x1400278b1  lea     r15, WPP_GLOBAL_Control
0x1400278b8  cmp     rbx, r15
0x1400278bb  jz      short loc_14002792E
0x1400278bd  bt      dword ptr [rbx+2Ch], 0Ah
0x1400278c2  jnb     short loc_1400278EB
0x1400278c4  mov     rbx, [rbx+18h]
0x1400278c8  call    cs:__imp_PsGetCurrentThreadId
0x1400278cf  nop     dword ptr [rax+rax+00h]
0x1400278d4  mov     edx, 25h ; '%'
0x1400278d9  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x1400278e0  mov     r9, rax
0x1400278e3  mov     rcx, rbx
0x1400278e6  call    WPP_SF_q
0x1400278eb  mov     rdi, cs:WPP_GLOBAL_Control
0x1400278f2  cmp     rdi, r15
0x1400278f5  jz      short loc_14002792E
0x1400278f7  bt      dword ptr [rdi+2Ch], 0Ah
0x1400278fc  jnb     short loc_14002792E
0x1400278fe  mov     rbx, [rbp+28h]
0x140027902  mov     rdi, [rdi+18h]
0x140027906  call    cs:__imp_PsGetCurrentThreadId
0x14002790d  nop     dword ptr [rax+rax+00h]
0x140027912  mov     edx, 26h ; '&'
0x140027917  mov     [rsp+78h+var_58], rbx
0x14002791c  mov     r9, rax
0x14002791f  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140027926  mov     rcx, rdi
0x140027929  call    WPP_SF_qq
0x14002792e  cmp     qword ptr [rbp+210h], 0
0x140027936  mov     rcx, rbp; RxContext
0x140027939  mov     eax, [rsi+80h]
0x14002793f  jz      short loc_14002796A
0x140027941  mov     [rbp+0B0h], eax
0x140027947  mov     rax, [rsi+88h]
0x14002794e  mov     [rbp+0B8h], rax
0x140027955  call    cs:__imp_RxLowIoCompletion
0x14002795c  nop     dword ptr [rax+rax+00h]
0x140027961  jmp     short loc_140027997
0x140027963  mov     ecx, 3
0x140027968  int     29h; Win8: RtlFailFast(ecx)
0x14002796a  mov     rdx, [rbp+28h]
0x14002796e  mov     [rdx+30h], eax
0x140027971  mov     rdx, [rbp+28h]
0x140027975  mov     rax, [rsi+88h]
0x14002797c  mov     [rdx+38h], rax
0x140027980  mov     r8d, [rsi+80h]
0x140027987  mov     rdx, [rbp+28h]
0x14002798b  call    cs:__imp_RxCompleteRequestEx
0x140027992  nop     dword ptr [rax+rax+00h]
0x140027997  mov     rcx, [rsi+50h]; RxContext
0x14002799b  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x1400279a2  nop     dword ptr [rax+rax+00h]
0x1400279a7  xor     edx, edx; Tag
0x1400279a9  mov     rcx, rsi; P
0x1400279ac  call    cs:__imp_ExFreePoolWithTag
0x1400279b3  nop     dword ptr [rax+rax+00h]
0x1400279b8  mov     qword ptr [r13+0], 0
0x1400279c0  mov     rbx, cs:WPP_GLOBAL_Control
0x1400279c7  lea     rax, WPP_GLOBAL_Control
0x1400279ce  cmp     rbx, rax
0x1400279d1  jz      short loc_140027A03
0x1400279d3  test    dword ptr [rbx+2Ch], 800h
0x1400279da  jz      short loc_140027A03
0x1400279dc  mov     rbx, [rbx+18h]
0x1400279e0  call    cs:__imp_PsGetCurrentThreadId
0x1400279e7  nop     dword ptr [rax+rax+00h]
0x1400279ec  mov     edx, 29h ; ')'
0x1400279f1  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x1400279f8  mov     r9, rax
0x1400279fb  mov     rcx, rbx
0x1400279fe  call    WPP_SF_q
0x140027a03  mov     al, 1
0x140027a05  add     rsp, 38h
0x140027a09  pop     r15
0x140027a0b  pop     r14
0x140027a0d  pop     r13
0x140027a0f  pop     r12
0x140027a11  pop     rdi
0x140027a12  pop     rsi
0x140027a13  pop     rbp
0x140027a14  pop     rbx
0x140027a15  retn
```
