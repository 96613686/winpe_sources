# PCW_QUERY_ITEM::PCW_QUERY_ITEM(utl::unique_ptr<PCW_COUNTERSET,ReleaseDeleter<PCW_COUNTERSET>> &&,AllocatedUnicodeString &&,bool,ulong,unsigned __int64 const &,void *)

- ea: `0x1400090d8`
- end: `0x14000927b`
- name: `??0PCW_QUERY_ITEM@@QEAA@$$QEAV?$unique_ptr@VPCW_COUNTERSET@@U?$ReleaseDeleter@VPCW_COUNTERSET@@@@@utl@@$$QEAVAllocatedUnicodeString@@_NKAEB_KPEAX@Z`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000961c`

## callees

- `0x1400090d8`
- `0x14000d7d0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000917e`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000917e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000916c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400091b6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000916c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400091b6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009234`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000925a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009234`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000925a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000924e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000924e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400091c8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400091c8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140009228`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140009228`

## pseudocode

```c
__int64 __fastcall PCW_QUERY_ITEM::PCW_QUERY_ITEM(
        __int64 a1,
        __int64 *a2,
        __int128 *a3,
        char a4,
        int a5,
        __int64 *a6,
        __int64 a7)
{
  _QWORD *v7; // rsi
  __int64 *v9; // r14
  __int64 v10; // rcx
  __int64 v11; // rax
  __int128 v12; // xmm0
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rbx
  __int64 v16; // rcx
  _QWORD *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 **v20; // rcx
  _PCW_CALLBACK_INFORMATION v22; // [rsp+20h] [rbp-58h] BYREF

  v7 = (_QWORD *)(a1 + 16);
  v9 = (__int64 *)(a1 + 32);
  *(_OWORD *)a1 = 0;
  v22.EnumerateInstances.CancelEvent = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  v10 = *a6;
  *(_DWORD *)(a1 + 60) = a5;
  *(_QWORD *)(a1 + 48) = v10;
  *(_QWORD *)(a1 + 72) = a7;
  *(_DWORD *)(a1 + 56) = 0;
  *(_BYTE *)(a1 + 64) = a4;
  v11 = *a2;
  *a2 = 0;
  *(_QWORD *)(a1 + 80) = v11;
  v12 = *a3;
  v22.AddCounter.InstanceMask = (PCUNICODE_STRING)(a1 + 88);
  *(_OWORD *)(a1 + 88) = v12;
  *a3 = 0;
  v22.AddCounter.CounterMask = *(_QWORD *)(a1 + 48);
  v13 = *(_QWORD *)(a1 + 80);
  *(_OWORD *)&v22.CollectData.InstanceId = 0;
  v14 = *(_QWORD *)(v13 + 80);
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(v14 + 80, 0);
  PCW_COUNTERSET_BASE::Notify(*(PCW_COUNTERSET_BASE **)(*(_QWORD *)(a1 + 80) + 80LL), PcwCallbackAddCounter, &v22);
  PCW_COUNTERSET_BASE::Notify(*(PCW_COUNTERSET_BASE **)(a1 + 80), PcwCallbackAddCounter, &v22);
  v15 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 80LL);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v15 + 104, 0);
  v16 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 80LL);
  v17 = *(_QWORD **)(v16 + 120);
  v18 = v16 + 112;
  if ( *v17 != v18
    || (v7[1] = v17,
        *v7 = v18,
        *v17 = v7,
        *(_QWORD *)(v18 + 8) = v7,
        v19 = *(_QWORD *)(a1 + 80) + 88LL,
        v20 = *(__int64 ***)(*(_QWORD *)(a1 + 80) + 96LL),
        *v20 != (__int64 *)v19) )
  {
    __fastfail(3u);
  }
  v9[1] = (__int64)v20;
  *v9 = v19;
  *v20 = v9;
  *(_QWORD *)(v19 + 8) = v9;
  ExReleasePushLockExclusiveEx(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 80LL) + 104LL, 0);
  KeLeaveCriticalRegion();
  ExReleasePushLockSharedEx(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 80LL) + 80LL, 0);
  KeLeaveCriticalRegion();
  return a1;
}

```

## disassembly

```asm
0x1400090d8  push    rbx
0x1400090da  push    rsi
0x1400090db  push    rdi
0x1400090dc  push    r14
0x1400090de  sub     rsp, 58h
0x1400090e2  mov     rax, [rsp+78h+arg_28]
0x1400090ea  lea     rsi, [rcx+10h]
0x1400090ee  mov     rdi, rcx
0x1400090f1  lea     r14, [rcx+20h]
0x1400090f5  xorps   xmm0, xmm0
0x1400090f8  xor     r10d, r10d
0x1400090fb  movups  xmmword ptr [rcx], xmm0
0x1400090fe  mov     qword ptr [rsp+78h+var_58+20h], r10
0x140009103  xorps   xmm1, xmm1
0x140009106  movups  xmmword ptr [rsi], xmm1
0x140009109  movups  xmmword ptr [r14], xmm0
0x14000910d  mov     rcx, [rax]
0x140009110  mov     eax, [rsp+78h+arg_20]
0x140009117  mov     [rdi+3Ch], eax
0x14000911a  mov     rax, [rsp+78h+arg_30]
0x140009122  mov     [rdi+30h], rcx
0x140009126  lea     rcx, [rdi+58h]
0x14000912a  mov     [rdi+48h], rax
0x14000912e  mov     [rdi+38h], r10d
0x140009132  mov     [rdi+40h], r9b
0x140009136  mov     rax, [rdx]
0x140009139  mov     [rdx], r10
0x14000913c  mov     [rdi+50h], rax
0x140009140  movups  xmm0, xmmword ptr [r8]
0x140009144  mov     qword ptr [rsp+78h+var_58+8], rcx
0x140009149  movdqu  xmmword ptr [rcx], xmm0
0x14000914d  movdqu  xmmword ptr [r8], xmm1
0x140009152  mov     rax, [rdi+30h]
0x140009156  mov     qword ptr [rsp+78h+var_58], rax
0x14000915b  xorps   xmm0, xmm0
0x14000915e  mov     rax, [rdi+50h]
0x140009162  movdqu  xmmword ptr [rsp+78h+var_58+10h], xmm0
0x140009168  mov     rbx, [rax+50h]
0x14000916c  call    cs:__imp_KeEnterCriticalRegion
0x140009173  nop     dword ptr [rax+rax+00h]
0x140009178  xor     edx, edx
0x14000917a  lea     rcx, [rbx+50h]
0x14000917e  call    cs:__imp_ExAcquirePushLockSharedEx
0x140009185  nop     dword ptr [rax+rax+00h]
0x14000918a  mov     rcx, [rdi+50h]
0x14000918e  lea     r8, [rsp+78h+var_58]; union _PCW_CALLBACK_INFORMATION *
0x140009193  xor     edx, edx; enum _PCW_CALLBACK_TYPE
0x140009195  mov     rcx, [rcx+50h]; this
0x140009199  call    ?Notify@PCW_COUNTERSET_BASE@@QEBAXW4_PCW_CALLBACK_TYPE@@PEAT_PCW_CALLBACK_INFORMATION@@@Z; PCW_COUNTERSET_BASE::Notify(_PCW_CALLBACK_TYPE,_PCW_CALLBACK_INFORMATION *)
0x14000919e  mov     rcx, [rdi+50h]; this
0x1400091a2  lea     r8, [rsp+78h+var_58]; union _PCW_CALLBACK_INFORMATION *
0x1400091a7  xor     edx, edx; enum _PCW_CALLBACK_TYPE
0x1400091a9  call    ?Notify@PCW_COUNTERSET_BASE@@QEBAXW4_PCW_CALLBACK_TYPE@@PEAT_PCW_CALLBACK_INFORMATION@@@Z; PCW_COUNTERSET_BASE::Notify(_PCW_CALLBACK_TYPE,_PCW_CALLBACK_INFORMATION *)
0x1400091ae  mov     rax, [rdi+50h]
0x1400091b2  mov     rbx, [rax+50h]
0x1400091b6  call    cs:__imp_KeEnterCriticalRegion
0x1400091bd  nop     dword ptr [rax+rax+00h]
0x1400091c2  xor     edx, edx
0x1400091c4  lea     rcx, [rbx+68h]
0x1400091c8  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400091cf  nop     dword ptr [rax+rax+00h]
0x1400091d4  mov     rax, [rdi+50h]
0x1400091d8  mov     rcx, [rax+50h]
0x1400091dc  mov     rax, [rcx+78h]
0x1400091e0  add     rcx, 70h ; 'p'
0x1400091e4  cmp     [rax], rcx
0x1400091e7  jnz     loc_140009274
0x1400091ed  mov     [rsi+8], rax
0x1400091f1  mov     [rsi], rcx
0x1400091f4  mov     [rax], rsi
0x1400091f7  mov     [rcx+8], rsi
0x1400091fb  mov     rax, [rdi+50h]
0x1400091ff  add     rax, 58h ; 'X'
0x140009203  mov     rcx, [rax+8]
0x140009207  cmp     [rcx], rax
0x14000920a  jnz     short loc_140009274
0x14000920c  mov     [r14+8], rcx
0x140009210  xor     edx, edx
0x140009212  mov     [r14], rax
0x140009215  mov     [rcx], r14
0x140009218  mov     [rax+8], r14
0x14000921c  mov     rax, [rdi+50h]
0x140009220  mov     rcx, [rax+50h]
0x140009224  add     rcx, 68h ; 'h'
0x140009228  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000922f  nop     dword ptr [rax+rax+00h]
0x140009234  call    cs:__imp_KeLeaveCriticalRegion
0x14000923b  nop     dword ptr [rax+rax+00h]
0x140009240  mov     rax, [rdi+50h]
0x140009244  xor     edx, edx
0x140009246  mov     rcx, [rax+50h]
0x14000924a  add     rcx, 50h ; 'P'
0x14000924e  call    cs:__imp_ExReleasePushLockSharedEx
0x140009255  nop     dword ptr [rax+rax+00h]
0x14000925a  call    cs:__imp_KeLeaveCriticalRegion
0x140009261  nop     dword ptr [rax+rax+00h]
0x140009266  mov     rax, rdi
0x140009269  add     rsp, 58h
0x14000926d  pop     r14
0x14000926f  pop     rdi
0x140009270  pop     rsi
0x140009271  pop     rbx
0x140009272  retn
0x140009274  mov     ecx, 3
0x140009279  int     29h; Win8: RtlFailFast(ecx)
```
