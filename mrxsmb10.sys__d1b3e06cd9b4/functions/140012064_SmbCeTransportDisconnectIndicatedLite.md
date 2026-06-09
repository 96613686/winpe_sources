# SmbCeTransportDisconnectIndicatedLite

- ea: `0x140012064`
- end: `0x140012213`
- name: `SmbCeTransportDisconnectIndicatedLite`
- size: `431`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140012014`
- `0x140014e40`

## callees

- `0x140001e40`
- `0x140002470`
- `0x14000dfa8`
- `0x14000ebd8`
- `0x14000ed10`
- `0x140010358`
- `0x140012064`

## import_xrefs

- `rdbss!RxPostToWorkerThread` at `0x1400121cb`
- `rdbss!RxPostToWorkerThread` at `0x1400121cb`
- `mrxsmb!MRxSmbDeviceObject` at `0x1400121a2`

## pseudocode

```c
char __fastcall SmbCeTransportDisconnectIndicatedLite(char *pContext)
{
  char v2; // di
  char v3; // al
  signed __int32 v4; // r8d
  char result; // al

  v2 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids, pContext);
  v3 = pContext[672];
  if ( (v3 & 0x40) == 0 )
  {
    *((_DWORD *)pContext + 82) = -1073741300;
    *((_DWORD *)pContext + 3) = 11;
    pContext[672] = v3 & 0xB7 | 0x40;
    v2 = 1;
    MRxSmbTrackRefCount(pContext, "SmbCeTransportDisconnectIndicatedLite", 2819);
    SmbReferenceRecord(pContext + 792, "SmbCeTransportDisconnectIndicatedLite", 2819);
    _InterlockedAdd((volatile signed __int32 *)pContext + 2, 1u);
    v4 = _InterlockedIncrement((volatile signed __int32 *)pContext + 100);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_qDD(
        WPP_GLOBAL_Control->AttachedDevice,
        40,
        WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids,
        pContext,
        v4 - 1,
        v4);
  }
  result = pContext[672];
  if ( result >= 0 )
  {
    result |= 0x80u;
    pContext[672] = result;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    result = WPP_SF_qZ(
               WPP_GLOBAL_Control->AttachedDevice,
               41,
               (unsigned int)WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids,
               (_DWORD)pContext,
               (__int64)(pContext + 80));
  if ( v2 )
  {
    *((_QWORD *)pContext + 86) = pContext + 680;
    *((_QWORD *)pContext + 85) = pContext + 680;
    result = RxPostToWorkerThread(
               MRxSmbDeviceObject,
               NormalWorkQueue,
               (PRX_WORK_QUEUE_ITEM)pContext + 17,
               SmbCeResumeAllOutstandingRequestsOnError,
               pContext);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids);
  return result;
}

```

## disassembly

```asm
0x140012064  mov     [rsp+arg_0], rbx
0x140012069  mov     [rsp+arg_8], rdi
0x14001206e  push    r14
0x140012070  sub     rsp, 30h
0x140012074  mov     rbx, rcx
0x140012077  xor     dil, dil
0x14001207a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140012081  lea     r14, WPP_GLOBAL_Control
0x140012088  cmp     rcx, r14
0x14001208b  jz      short loc_1400120AE
0x14001208d  test    dword ptr [rcx+2Ch], 400h
0x140012094  jz      short loc_1400120AE
0x140012096  mov     rcx, [rcx+18h]
0x14001209a  lea     r8, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids
0x1400120a1  mov     edx, 27h ; '''
0x1400120a6  mov     r9, rbx
0x1400120a9  call    WPP_SF_q
0x1400120ae  mov     al, [rbx+2A0h]
0x1400120b4  test    al, 40h
0x1400120b6  jnz     loc_140012155
0x1400120bc  and     al, 0F7h
0x1400120be  mov     dword ptr [rbx+148h], 0C000020Ch
0x1400120c8  or      al, 40h
0x1400120ca  mov     dword ptr [rbx+0Ch], 0Bh
0x1400120d1  mov     r8d, 0B03h
0x1400120d7  mov     [rbx+2A0h], al
0x1400120dd  lea     rdx, aSmbcetransport; "SmbCeTransportDisconnectIndicatedLite"
0x1400120e4  mov     rcx, rbx
0x1400120e7  mov     edi, 1
0x1400120ec  call    MRxSmbTrackRefCount
0x1400120f1  lea     rcx, [rbx+318h]
0x1400120f8  mov     r8d, 0B03h
0x1400120fe  lea     rdx, aSmbcetransport; "SmbCeTransportDisconnectIndicatedLite"
0x140012105  call    SmbReferenceRecord
0x14001210a  lock add [rbx+8], edi
0x14001210e  mov     r8d, edi
0x140012111  lock xadd [rbx+190h], r8d
0x14001211a  add     r8d, edi
0x14001211d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140012124  cmp     rcx, r14
0x140012127  jz      short loc_140012155
0x140012129  test    dword ptr [rcx+2Ch], 200h
0x140012130  jz      short loc_140012155
0x140012132  mov     rcx, [rcx+18h]
0x140012136  lea     eax, [r8-1]
0x14001213a  mov     [rsp+38h+var_10], r8d
0x14001213f  lea     edx, [rdi+27h]
0x140012142  lea     r8, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids
0x140012149  mov     dword ptr [rsp+38h+pContext], eax
0x14001214d  mov     r9, rbx
0x140012150  call    WPP_SF_qDD
0x140012155  mov     al, [rbx+2A0h]
0x14001215b  test    al, al
0x14001215d  js      short loc_140012167
0x14001215f  or      al, 80h
0x140012161  mov     [rbx+2A0h], al
0x140012167  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001216e  cmp     rcx, r14
0x140012171  jz      short loc_14001219D
0x140012173  test    dword ptr [rcx+2Ch], 200h
0x14001217a  jz      short loc_14001219D
0x14001217c  mov     rcx, [rcx+18h]
0x140012180  lea     rax, [rbx+50h]
0x140012184  mov     edx, 29h ; ')'
0x140012189  mov     [rsp+38h+pContext], rax
0x14001218e  mov     r9, rbx
0x140012191  lea     r8, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids
0x140012198  call    WPP_SF_qZ
0x14001219d  test    dil, dil
0x1400121a0  jz      short loc_1400121D7
0x1400121a2  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x1400121a9  lea     r8, [rbx+2A8h]; pWorkQueueItem
0x1400121b0  mov     [r8+8], r8
0x1400121b4  lea     r9, SmbCeResumeAllOutstandingRequestsOnError; Routine
0x1400121bb  mov     [r8], r8
0x1400121be  mov     edx, 3; WorkQueueType
0x1400121c3  mov     [rsp+38h+pContext], rbx; pContext
0x1400121c8  mov     rcx, [rcx]; pMRxDeviceObject
0x1400121cb  call    cs:__imp_RxPostToWorkerThread
0x1400121d2  nop     dword ptr [rax+rax+00h]
0x1400121d7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400121de  cmp     rcx, r14
0x1400121e1  jz      short loc_140012201
0x1400121e3  test    dword ptr [rcx+2Ch], 400h
0x1400121ea  jz      short loc_140012201
0x1400121ec  mov     rcx, [rcx+18h]
0x1400121f0  lea     r8, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids
0x1400121f7  mov     edx, 2Ah ; '*'
0x1400121fc  call    WPP_SF_
0x140012201  mov     rbx, [rsp+38h+arg_0]
0x140012206  mov     rdi, [rsp+38h+arg_8]
0x14001220b  add     rsp, 30h
0x14001220f  pop     r14
0x140012211  retn
```
