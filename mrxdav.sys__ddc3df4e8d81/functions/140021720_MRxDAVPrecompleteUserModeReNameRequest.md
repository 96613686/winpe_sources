# MRxDAVPrecompleteUserModeReNameRequest

- ea: `0x140021720`
- end: `0x140021a49`
- name: `MRxDAVPrecompleteUserModeReNameRequest`
- size: `809`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, __int64, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140001680`
- `0x140001b64`
- `0x140021720`
- `0x140027a20`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140021783`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400217f5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002184a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400218a2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400218ea`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021946`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021783`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400217f5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002184a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400218a2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400218ea`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021946`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140021981`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140021981`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400219b9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400219b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400219cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400219f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021a0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021a29`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400219cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400219f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021a0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021a29`

## pseudocode

```c
__int64 __fastcall MRxDAVPrecompleteUserModeReNameRequest(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4, int a5)
{
  __int64 v5; // rdi
  void *v9; // rdx
  int v10; // ebp
  __int64 v11; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v13; // rdx
  void *v15; // rdx
  void *v16; // rdx
  void *v17; // rdx
  __int64 v18; // rbx
  HANDLE v19; // rax
  int v20; // esi
  __int64 v21; // rbx
  HANDLE v22; // rax
  _QWORD *v23; // rax
  __int64 v24; // r8
  _QWORD *v25; // rdx
  void *v26; // rcx

  v5 = 0;
  if ( !a5 )
  {
    v5 = *(_QWORD *)(a2 + 72);
    if ( v5 )
      v5 = *(_QWORD *)(v5 + 48);
  }
  v9 = (void *)a3[81];
  if ( v9 && (v10 = UMRxFreeSecondaryBuffer(a1, v9)) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      v13 = 67;
LABEL_9:
      WPP_SF_qD(v11, v13, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, CurrentThreadId, v10);
    }
  }
  else
  {
    v15 = (void *)a3[82];
    if ( v15 && (v10 = UMRxFreeSecondaryBuffer(a1, v15)) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        CurrentThreadId = PsGetCurrentThreadId();
        v13 = 68;
        goto LABEL_9;
      }
    }
    else
    {
      v16 = (void *)a3[83];
      if ( v16 && (v10 = UMRxFreeSecondaryBuffer(a1, v16)) != 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        {
          v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          CurrentThreadId = PsGetCurrentThreadId();
          v13 = 69;
          goto LABEL_9;
        }
      }
      else
      {
        v17 = (void *)a3[84];
        if ( v17 && (v10 = UMRxFreeSecondaryBuffer(a1, v17)) != 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
          {
            v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            CurrentThreadId = PsGetCurrentThreadId();
            v13 = 70;
            goto LABEL_9;
          }
        }
        else if ( a5 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
          {
            v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v19 = PsGetCurrentThreadId();
            WPP_SF_qqq(v18, 71, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v19, a1, a2);
          }
        }
        else
        {
          v20 = *(_DWORD *)(a1 + 128);
          if ( v20
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
          {
            v21 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v22 = PsGetCurrentThreadId();
            WPP_SF_qD(v21, 72, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v22, v20);
          }
          if ( *(_QWORD *)(v5 + 48) )
          {
            ExAcquireResourceExclusiveLite(&LockTokenEntryListLock, 1u);
            v23 = *(_QWORD **)(v5 + 56);
            v24 = *v23;
            if ( *(_QWORD **)(*v23 + 8LL) != v23 || (v25 = (_QWORD *)v23[1], (_QWORD *)*v25 != v23) )
              __fastfail(3u);
            *v25 = v24;
            *(_QWORD *)(v24 + 8) = v25;
            ExReleaseResourceLite(&LockTokenEntryListLock);
            ExFreePoolWithTag(*(PVOID *)(*(_QWORD *)(v5 + 56) + 24LL), 0);
            *(_QWORD *)(*(_QWORD *)(v5 + 56) + 24LL) = 0;
            ExFreePoolWithTag(*(PVOID *)(*(_QWORD *)(v5 + 56) + 32LL), 0);
            *(_QWORD *)(*(_QWORD *)(v5 + 56) + 32LL) = 0;
            ExFreePoolWithTag(*(PVOID *)(v5 + 56), 0);
            v26 = *(void **)(v5 + 48);
            *(_QWORD *)(v5 + 56) = 0;
            ExFreePoolWithTag(v26, 0);
            *(_QWORD *)(v5 + 48) = 0;
          }
        }
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140021720  push    rbx
0x140021722  push    rbp
0x140021723  push    rsi
0x140021724  push    rdi
0x140021725  push    r15
0x140021727  sub     rsp, 30h
0x14002172b  xor     edi, edi
0x14002172d  mov     rbx, r8
0x140021730  mov     r15, rdx
0x140021733  mov     rsi, rcx
0x140021736  cmp     [rsp+58h+arg_20], edi
0x14002173d  jnz     short loc_14002174C
0x14002173f  mov     rdi, [rdx+48h]
0x140021743  test    rdi, rdi
0x140021746  jz      short loc_14002174C
0x140021748  mov     rdi, [rdi+30h]
0x14002174c  mov     rdx, [r8+288h]
0x140021753  test    rdx, rdx
0x140021756  jz      short loc_1400217BB
0x140021758  call    UMRxFreeSecondaryBuffer
0x14002175d  mov     ebp, eax
0x14002175f  test    eax, eax
0x140021761  jz      short loc_1400217BB
0x140021763  mov     rbx, cs:WPP_GLOBAL_Control
0x14002176a  lea     rax, WPP_GLOBAL_Control
0x140021771  cmp     rbx, rax
0x140021774  jz      short loc_1400217AA
0x140021776  test    dword ptr [rbx+2Ch], 2000h
0x14002177d  jz      short loc_1400217AA
0x14002177f  mov     rbx, [rbx+18h]
0x140021783  call    cs:__imp_PsGetCurrentThreadId
0x14002178a  nop     dword ptr [rax+rax+00h]
0x14002178f  mov     edx, 43h ; 'C'
0x140021794  mov     r9, rax
0x140021797  mov     dword ptr [rsp+58h+var_38], ebp
0x14002179b  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x1400217a2  mov     rcx, rbx
0x1400217a5  call    WPP_SF_qD
0x1400217aa  mov     eax, 1
0x1400217af  add     rsp, 30h
0x1400217b3  pop     r15
0x1400217b5  pop     rdi
0x1400217b6  pop     rsi
0x1400217b7  pop     rbp
0x1400217b8  pop     rbx
0x1400217b9  retn
0x1400217bb  mov     rdx, [rbx+290h]
0x1400217c2  test    rdx, rdx
0x1400217c5  jz      short loc_140021808
0x1400217c7  mov     rcx, rsi
0x1400217ca  call    UMRxFreeSecondaryBuffer
0x1400217cf  mov     ebp, eax
0x1400217d1  test    eax, eax
0x1400217d3  jz      short loc_140021808
0x1400217d5  mov     rbx, cs:WPP_GLOBAL_Control
0x1400217dc  lea     rax, WPP_GLOBAL_Control
0x1400217e3  cmp     rbx, rax
0x1400217e6  jz      short loc_1400217AA
0x1400217e8  test    dword ptr [rbx+2Ch], 2000h
0x1400217ef  jz      short loc_1400217AA
0x1400217f1  mov     rbx, [rbx+18h]
0x1400217f5  call    cs:__imp_PsGetCurrentThreadId
0x1400217fc  nop     dword ptr [rax+rax+00h]
0x140021801  mov     edx, 44h ; 'D'
0x140021806  jmp     short loc_140021794
0x140021808  mov     rdx, [rbx+298h]
0x14002180f  test    rdx, rdx
0x140021812  jz      short loc_140021860
0x140021814  mov     rcx, rsi
0x140021817  call    UMRxFreeSecondaryBuffer
0x14002181c  mov     ebp, eax
0x14002181e  test    eax, eax
0x140021820  jz      short loc_140021860
0x140021822  mov     rbx, cs:WPP_GLOBAL_Control
0x140021829  lea     rax, WPP_GLOBAL_Control
0x140021830  cmp     rbx, rax
0x140021833  jz      loc_1400217AA
0x140021839  test    dword ptr [rbx+2Ch], 2000h
0x140021840  jz      loc_1400217AA
0x140021846  mov     rbx, [rbx+18h]
0x14002184a  call    cs:__imp_PsGetCurrentThreadId
0x140021851  nop     dword ptr [rax+rax+00h]
0x140021856  mov     edx, 45h ; 'E'
0x14002185b  jmp     loc_140021794
0x140021860  mov     rdx, [rbx+2A0h]
0x140021867  test    rdx, rdx
0x14002186a  jz      short loc_1400218B8
0x14002186c  mov     rcx, rsi
0x14002186f  call    UMRxFreeSecondaryBuffer
0x140021874  mov     ebp, eax
0x140021876  test    eax, eax
0x140021878  jz      short loc_1400218B8
0x14002187a  mov     rbx, cs:WPP_GLOBAL_Control
0x140021881  lea     rax, WPP_GLOBAL_Control
0x140021888  cmp     rbx, rax
0x14002188b  jz      loc_1400217AA
0x140021891  test    dword ptr [rbx+2Ch], 2000h
0x140021898  jz      loc_1400217AA
0x14002189e  mov     rbx, [rbx+18h]
0x1400218a2  call    cs:__imp_PsGetCurrentThreadId
0x1400218a9  nop     dword ptr [rax+rax+00h]
0x1400218ae  mov     edx, 46h ; 'F'
0x1400218b3  jmp     loc_140021794
0x1400218b8  cmp     [rsp+58h+arg_20], 0
0x1400218c0  jz      short loc_14002191C
0x1400218c2  mov     rbx, cs:WPP_GLOBAL_Control
0x1400218c9  lea     rax, WPP_GLOBAL_Control
0x1400218d0  cmp     rbx, rax
0x1400218d3  jz      loc_1400217AA
0x1400218d9  test    dword ptr [rbx+2Ch], 2000h
0x1400218e0  jz      loc_1400217AA
0x1400218e6  mov     rbx, [rbx+18h]
0x1400218ea  call    cs:__imp_PsGetCurrentThreadId
0x1400218f1  nop     dword ptr [rax+rax+00h]
0x1400218f6  mov     edx, 47h ; 'G'
0x1400218fb  mov     [rsp+58h+var_30], r15
0x140021900  mov     r9, rax
0x140021903  mov     [rsp+58h+var_38], rsi
0x140021908  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x14002190f  mov     rcx, rbx
0x140021912  call    WPP_SF_qqq
0x140021917  jmp     loc_1400217AA
0x14002191c  mov     esi, [rsi+80h]
0x140021922  test    esi, esi
0x140021924  jz      short loc_14002196D
0x140021926  mov     rbx, cs:WPP_GLOBAL_Control
0x14002192d  lea     rax, WPP_GLOBAL_Control
0x140021934  cmp     rbx, rax
0x140021937  jz      short loc_14002196D
0x140021939  test    dword ptr [rbx+2Ch], 2000h
0x140021940  jz      short loc_14002196D
0x140021942  mov     rbx, [rbx+18h]
0x140021946  call    cs:__imp_PsGetCurrentThreadId
0x14002194d  nop     dword ptr [rax+rax+00h]
0x140021952  mov     edx, 48h ; 'H'
0x140021957  mov     dword ptr [rsp+58h+var_38], esi
0x14002195b  mov     r9, rax
0x14002195e  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140021965  mov     rcx, rbx
0x140021968  call    WPP_SF_qD
0x14002196d  cmp     qword ptr [rdi+30h], 0
0x140021972  jz      loc_1400217AA
0x140021978  mov     dl, 1; Wait
0x14002197a  lea     rcx, LockTokenEntryListLock; Resource
0x140021981  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140021988  nop     dword ptr [rax+rax+00h]
0x14002198d  mov     rax, [rdi+38h]
0x140021991  mov     r8, [rax]
0x140021994  cmp     [r8+8], rax
0x140021998  jnz     loc_140021A42
0x14002199e  mov     rdx, [rax+8]
0x1400219a2  cmp     [rdx], rax
0x1400219a5  jnz     loc_140021A42
0x1400219ab  mov     [rdx], r8
0x1400219ae  lea     rcx, LockTokenEntryListLock; Resource
0x1400219b5  mov     [r8+8], rdx
0x1400219b9  call    cs:__imp_ExReleaseResourceLite
0x1400219c0  nop     dword ptr [rax+rax+00h]
0x1400219c5  mov     rcx, [rdi+38h]
0x1400219c9  xor     edx, edx; Tag
0x1400219cb  mov     rcx, [rcx+18h]; P
0x1400219cf  call    cs:__imp_ExFreePoolWithTag
0x1400219d6  nop     dword ptr [rax+rax+00h]
0x1400219db  mov     rax, [rdi+38h]
0x1400219df  xor     edx, edx; Tag
0x1400219e1  mov     qword ptr [rax+18h], 0
0x1400219e9  mov     rcx, [rdi+38h]
0x1400219ed  mov     rcx, [rcx+20h]; P
0x1400219f1  call    cs:__imp_ExFreePoolWithTag
0x1400219f8  nop     dword ptr [rax+rax+00h]
0x1400219fd  mov     rax, [rdi+38h]
0x140021a01  xor     edx, edx; Tag
0x140021a03  mov     qword ptr [rax+20h], 0
0x140021a0b  mov     rcx, [rdi+38h]; P
0x140021a0f  call    cs:__imp_ExFreePoolWithTag
0x140021a16  nop     dword ptr [rax+rax+00h]
0x140021a1b  mov     rcx, [rdi+30h]; P
0x140021a1f  xor     edx, edx; Tag
0x140021a21  mov     qword ptr [rdi+38h], 0
0x140021a29  call    cs:__imp_ExFreePoolWithTag
0x140021a30  nop     dword ptr [rax+rax+00h]
0x140021a35  mov     qword ptr [rdi+30h], 0
0x140021a3d  jmp     loc_1400217AA
0x140021a42  mov     ecx, 3
0x140021a47  int     29h; Win8: RtlFailFast(ecx)
```
