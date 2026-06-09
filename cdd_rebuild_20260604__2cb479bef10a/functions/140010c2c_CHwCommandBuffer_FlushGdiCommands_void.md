# CHwCommandBuffer::FlushGdiCommands(void)

- ea: `0x140010c2c`
- end: `0x140011197`
- name: `?FlushGdiCommands@CHwCommandBuffer@@QEAAJXZ`
- size: `1387`
- prototype: `__int64 __fastcall(CHwCommandBuffer *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140010850`
- `0x14002d4b4`

## callees

- `0x1400023c0`
- `0x140002420`
- `0x140010c2c`
- `0x1400111a0`
- `0x1400112f0`
- `0x1400113d4`
- `0x1400129cc`
- `0x140012c34`
- `0x1400371f0`
- `0x1400372d0`
- `0x140037640`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140010da5`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140010da5`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140010e11`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140010e11`
- `ntoskrnl!DbgPrint` at `0x140010e64`
- `ntoskrnl!DbgPrint` at `0x14001107d`
- `ntoskrnl!DbgPrint` at `0x140010e64`
- `ntoskrnl!DbgPrint` at `0x14001107d`
- `ntoskrnl!KdDebuggerEnabled` at `0x140010e4d`
- `ntoskrnl!KdDebuggerEnabled` at `0x140011066`
- `watchdog!WdLogSingleEntry1` at `0x140010d25`
- `watchdog!WdLogSingleEntry1` at `0x140010ee0`
- `watchdog!WdLogSingleEntry1` at `0x1400110e1`
- `watchdog!WdLogSingleEntry1` at `0x140011133`
- `watchdog!WdLogSingleEntry1` at `0x140010d25`
- `watchdog!WdLogSingleEntry1` at `0x140010ee0`
- `watchdog!WdLogSingleEntry1` at `0x1400110e1`
- `watchdog!WdLogSingleEntry1` at `0x140011133`
- `watchdog!WdLogNewEntry5_WdError` at `0x140010e8c`
- `watchdog!WdLogNewEntry5_WdError` at `0x140010ef7`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400110a4`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400110fa`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001114a`
- `watchdog!WdLogNewEntry5_WdError` at `0x140010e8c`
- `watchdog!WdLogNewEntry5_WdError` at `0x140010ef7`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400110a4`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400110fa`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001114a`
- `watchdog!WdLogSingleEntry0` at `0x140010e75`
- `watchdog!WdLogSingleEntry0` at `0x14001108e`
- `watchdog!WdLogSingleEntry0` at `0x140010e75`
- `watchdog!WdLogSingleEntry0` at `0x14001108e`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140010d3c`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140010d3c`

## string_xrefs

- `0x140010e5d`: `pLastCommand is not NULL in FlushGdiCommands`

## pseudocode

```c
__int64 __fastcall CHwCommandBuffer::FlushGdiCommands(CHwCommandBuffer *this)
{
  __int64 v2; // rcx
  int v3; // edi
  int v4; // r15d
  __int64 v5; // rdx
  int v6; // eax
  _QWORD *v7; // rax
  __int64 v8; // r15
  __int64 v9; // rax
  _QWORD **v10; // r14
  _QWORD *v11; // rsi
  _QWORD *v12; // rax
  CddResidencyState *v13; // rsi
  _QWORD *v15; // rax
  int v16; // eax
  _QWORD *v17; // rax
  __int64 v18; // rax
  struct _LIST_ENTRY *v19; // r15
  __int64 v20; // rax
  int v21; // eax
  struct _LIST_ENTRY *v22; // r15
  unsigned __int8 v23; // r9
  __int64 v24; // rax
  struct _LIST_ENTRY *v25; // rcx
  int v26; // eax
  _QWORD *j; // rdx
  _QWORD *i; // r13
  _QWORD *v29; // r12
  unsigned __int64 v30; // rsi
  _QWORD *v31; // rax
  _QWORD *v32; // rax
  _QWORD *v33; // rax
  int v34; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v35; // [rsp+38h] [rbp-C8h] BYREF
  struct _LIST_ENTRY *v36; // [rsp+40h] [rbp-C0h]
  _QWORD v37[48]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = *(_QWORD *)this;
  v3 = 0;
  if ( (*(_DWORD *)(v2 + 2744) & 0x540) == 0x140 )
  {
    v4 = *((_DWORD *)this + 8) - *((_DWORD *)this + 4);
    v34 = v4;
    if ( !v4 )
    {
      if ( *((_QWORD *)this + 5) && (_BYTE)KdDebuggerEnabled )
      {
        DbgPrint("pLastCommand is not NULL in FlushGdiCommands");
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 1137;
        v15 = (_QWORD *)WdLogNewEntry5_WdError();
        v15[3] = gCddImageInfo;
        v15[4] = (unsigned int)dword_14003E570;
        v15[5] = 215857758;
        WdLogGlobalForLineNumber = 1137;
        __debugbreak();
      }
      goto LABEL_10;
    }
    if ( *(_BYTE *)(v2 + 12716) )
    {
      CDDPDEV::AcquireResidencyLock((CDDPDEV *)v2);
      v29 = (_QWORD *)((char *)this + 2104);
      v30 = 0;
      for ( i = (_QWORD *)*((_QWORD *)this + 263); i != v29; i = (_QWORD *)*i )
      {
        v18 = *((unsigned int *)this + 2) + 3LL;
        v35 = 0;
        v19 = (struct _LIST_ENTRY *)&i[-2 * v18];
        v20 = *(_QWORD *)this;
        v36 = v19;
        v19[1].Blink = *(struct _LIST_ENTRY **)(v20 + 12752);
        v21 = CDDPDEV::EnsureResident(*(CDDPDEV **)this, (struct CddResidencyState *)v19, this, v23, &v35);
        v3 = v21;
        if ( v21 == 259 )
        {
          if ( v30 <= v35 )
            v30 = v35;
        }
        else if ( v21 < 0 )
        {
          WdLogSingleEntry1(2, v21);
          WdLogGlobalForLineNumber = 1058;
          v32 = (_QWORD *)WdLogNewEntry5_WdError();
          v32[3] = gCddImageInfo;
          v32[4] = (unsigned int)dword_14003E570;
          v32[5] = 215857758;
          WdLogGlobalForLineNumber = 1058;
          break;
        }
        v22 = v19 + 2;
        CDDPDEV::RemoveLruListEntry(*(CDDPDEV **)this, v22);
        if ( v36->Flink->Blink != *(struct _LIST_ENTRY **)this && (_BYTE)KdDebuggerEnabled )
        {
          DbgPrint("Invalid bitmap PPDEV");
          WdLogSingleEntry0(2);
          WdLogGlobalForLineNumber = 1063;
          v31 = (_QWORD *)WdLogNewEntry5_WdError();
          v31[3] = gCddImageInfo;
          v31[4] = (unsigned int)dword_14003E570;
          v31[5] = 215857758;
          WdLogGlobalForLineNumber = 1063;
          __debugbreak();
        }
        v24 = *(_QWORD *)this + 12784LL;
        v25 = *(struct _LIST_ENTRY **)v24;
        if ( *(_QWORD *)(*(_QWORD *)v24 + 8LL) != v24 )
LABEL_28:
          __fastfail(3u);
        v22->Flink = v25;
        v22->Blink = (struct _LIST_ENTRY *)v24;
        v25->Blink = v22;
        *(_QWORD *)v24 = v22;
      }
      CDDPDEV::ReleaseResidencyLock(*(CDDPDEV **)this);
      if ( v3 < 0 )
        goto LABEL_9;
      if ( v30 )
      {
        v26 = CDDPDEV::WaitForPagingQueueMonitoredFence(*(CDDPDEV **)this, v30);
        v3 = v26;
        if ( v26 < 0 )
        {
          WdLogSingleEntry1(2, v26);
          WdLogGlobalForLineNumber = 1077;
          v33 = (_QWORD *)WdLogNewEntry5_WdError();
          v33[3] = gCddImageInfo;
          v33[4] = (unsigned int)dword_14003E570;
          v33[5] = 215857758;
          WdLogGlobalForLineNumber = 1077;
        }
        else
        {
          for ( j = (_QWORD *)*v29; j != v29; j = (_QWORD *)*j )
            j[-2 * *((unsigned int *)this + 2) - 4] = 0;
        }
      }
      if ( v3 < 0 )
        goto LABEL_9;
      v4 = v34;
    }
    memset(v37, 0, 0x178u);
    v5 = *(_QWORD *)this;
    LODWORD(v37[0]) = *(_DWORD *)(*(_QWORD *)this + 2528LL);
    LODWORD(v37[1]) = *(_DWORD *)(v5 + 2524);
    v37[4] = *((_QWORD *)this + 2);
    v37[6] = (char *)this + 48;
    HIDWORD(v37[2]) = *((_DWORD *)this + 524);
    LODWORD(v37[2]) = v4;
    HIDWORD(v37[9]) = 32;
    if ( *((_BYTE *)this + 2144) )
    {
      HIDWORD(v37[9]) = 96;
      *((_BYTE *)this + 2144) = 0;
    }
    v6 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(v5 + 280))(v37, *(_QWORD *)(v5 + 3616));
    v3 = v6;
    if ( v6 < 0 )
    {
      WdLogSingleEntry1(4, v6);
      WdLogGlobalForLineNumber = 1120;
      v7 = (_QWORD *)WdLogNewEntry5_WdEvent();
      v7[3] = gCddImageInfo;
      v7[4] = (unsigned int)dword_14003E570;
      v7[5] = 215857758;
      WdLogGlobalForLineNumber = 1120;
    }
LABEL_9:
    if ( *(_BYTE *)(*(_QWORD *)this + 12716LL) )
    {
      if ( v3 >= 0 )
      {
        v16 = CDDPDEV::SignalCommandBufferMonitoredFence(*(CDDPDEV **)this);
        if ( v16 < 0 )
        {
          WdLogSingleEntry1(2, v16);
          WdLogGlobalForLineNumber = 1130;
          v17 = (_QWORD *)WdLogNewEntry5_WdError();
          v17[3] = gCddImageInfo;
          v17[4] = (unsigned int)dword_14003E570;
          v17[5] = 215857758;
          WdLogGlobalForLineNumber = 1130;
        }
      }
    }
  }
LABEL_10:
  v8 = *((_QWORD *)this + 267);
  v9 = *((_QWORD *)this + 2);
  *((_DWORD *)this + 524) = 0;
  *((_QWORD *)this + 4) = v9;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 530) = 0;
  ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v8);
  v10 = (_QWORD **)((char *)this + 2104);
  while ( 1 )
  {
    v11 = *v10;
    if ( *v10 == v10 )
      break;
    if ( (_QWORD **)v11[1] != v10 )
      goto LABEL_28;
    v12 = (_QWORD *)*v11;
    if ( *(_QWORD **)(*v11 + 8LL) != v11 )
      goto LABEL_28;
    *v10 = v12;
    v12[1] = v10;
    v13 = (CddResidencyState *)&v11[-2 * *((unsigned int *)this + 2) - 6];
    CddResidencyState::OnCommandBufferFlush(v13, this);
    if ( v3 >= 0 )
      v3 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 32LL))(*(_QWORD *)v13);
  }
  ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140010c2c  push    rbp
0x140010c2e  push    rbx
0x140010c2f  push    rsi
0x140010c30  push    rdi
0x140010c31  push    r12
0x140010c33  push    r13
0x140010c35  push    r14
0x140010c37  push    r15
0x140010c39  lea     rbp, [rsp-0E8h]
0x140010c41  sub     rsp, 1E8h
0x140010c48  mov     rax, cs:__security_cookie
0x140010c4f  xor     rax, rsp
0x140010c52  mov     [rbp+120h+var_50], rax
0x140010c59  xor     r13d, r13d
0x140010c5c  mov     rbx, rcx
0x140010c5f  mov     rcx, [rcx]; this
0x140010c62  mov     edi, r13d
0x140010c65  mov     eax, [rcx+0AB8h]
0x140010c6b  and     eax, 540h
0x140010c70  cmp     eax, 140h
0x140010c75  jnz     loc_140010D81
0x140010c7b  mov     r15d, [rbx+20h]
0x140010c7f  sub     r15d, [rbx+10h]
0x140010c83  mov     [rsp+220h+var_1F0], r15d
0x140010c88  jz      loc_140010E43
0x140010c8e  mov     r14d, 0CDDBA5Eh
0x140010c94  cmp     [rcx+31ACh], r13b
0x140010c9b  jnz     loc_140011039
0x140010ca1  xor     edx, edx; Val
0x140010ca3  lea     rcx, [rsp+220h+var_1D0]; void *
0x140010ca8  mov     r8d, 178h; Size
0x140010cae  call    memset
0x140010cb3  mov     rdx, [rbx]
0x140010cb6  mov     eax, [rdx+9E0h]
0x140010cbc  mov     [rsp+220h+var_1D0], eax
0x140010cc0  mov     eax, [rdx+9DCh]
0x140010cc6  mov     [rsp+220h+var_1C8], eax
0x140010cca  mov     rax, [rbx+10h]
0x140010cce  mov     [rsp+220h+var_1B0], rax
0x140010cd3  lea     rax, [rbx+30h]
0x140010cd7  mov     [rbp+120h+var_1A0], rax
0x140010cdb  mov     eax, [rbx+830h]
0x140010ce1  mov     [rsp+220h+var_1BC], eax
0x140010ce5  mov     [rsp+220h+var_1C0], r15d
0x140010cea  mov     [rbp+120h+var_184], 20h ; ' '
0x140010cf1  cmp     [rbx+860h], r13b
0x140010cf8  jnz     loc_140011184
0x140010cfe  mov     rax, [rdx+118h]
0x140010d05  lea     rcx, [rsp+220h+var_1D0]
0x140010d0a  mov     rdx, [rdx+0E20h]
0x140010d11  call    _guard_dispatch_icall
0x140010d16  movsxd  rdi, eax
0x140010d19  test    eax, eax
0x140010d1b  jns     short loc_140010D71
0x140010d1d  mov     rdx, rdi
0x140010d20  mov     ecx, 4
0x140010d25  call    cs:__imp_WdLogSingleEntry1
0x140010d2c  nop     dword ptr [rax+rax+00h]
0x140010d31  mov     esi, 460h
0x140010d36  mov     cs:WdLogGlobalForLineNumber, esi
0x140010d3c  call    cs:__imp_WdLogNewEntry5_WdEvent
0x140010d43  nop     dword ptr [rax+rax+00h]
0x140010d48  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140010d4f  mov     [rax+18h], rcx
0x140010d53  mov     ecx, cs:dword_14003E570
0x140010d59  mov     [rax+20h], rcx
0x140010d5d  mov     [rax+28h], r14
0x140010d61  mov     cs:WdLogGlobalForLineNumber, esi
0x140010d67  jmp     short loc_140010D71
0x140010d69  test    edi, edi
0x140010d6b  jns     loc_14001117A
0x140010d71  mov     rcx, [rbx]; this
0x140010d74  cmp     [rcx+31ACh], r13b
0x140010d7b  jnz     loc_140010EC3
0x140010d81  mov     r15, [rbx+858h]
0x140010d88  mov     rax, [rbx+10h]
0x140010d8c  mov     rcx, r15
0x140010d8f  mov     [rbx+830h], r13d
0x140010d96  mov     [rbx+20h], rax
0x140010d9a  mov     [rbx+28h], r13
0x140010d9e  mov     [rbx+848h], r13d
0x140010da5  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x140010dac  nop     dword ptr [rax+rax+00h]
0x140010db1  lea     r14, [rbx+838h]
0x140010db8  mov     rsi, [r14]
0x140010dbb  cmp     rsi, r14
0x140010dbe  jz      short loc_140010E0E
0x140010dc0  cmp     [rsi+8], r14
0x140010dc4  jnz     loc_140010FC2
0x140010dca  mov     rax, [rsi]
0x140010dcd  cmp     [rax+8], rsi
0x140010dd1  jnz     loc_140010FC2
0x140010dd7  mov     [r14], rax
0x140010dda  mov     rdx, rbx; struct CHwCommandBuffer *
0x140010ddd  mov     [rax+8], r14
0x140010de1  mov     eax, [rbx+8]
0x140010de4  add     rax, 3
0x140010de8  shl     rax, 4
0x140010dec  sub     rsi, rax
0x140010def  mov     rcx, rsi; this
0x140010df2  call    ?OnCommandBufferFlush@CddResidencyState@@QEAAXPEAVCHwCommandBuffer@@@Z; CddResidencyState::OnCommandBufferFlush(CHwCommandBuffer *)
0x140010df7  test    edi, edi
0x140010df9  js      short loc_140010DB8
0x140010dfb  mov     rcx, [rsi]
0x140010dfe  mov     rax, [rcx]
0x140010e01  mov     rax, [rax+20h]
0x140010e05  call    _guard_dispatch_icall
0x140010e0a  mov     edi, eax
0x140010e0c  jmp     short loc_140010DB8
0x140010e0e  mov     rcx, r15
0x140010e11  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x140010e18  nop     dword ptr [rax+rax+00h]
0x140010e1d  mov     eax, edi
0x140010e1f  mov     rcx, [rbp+120h+var_50]
0x140010e26  xor     rcx, rsp; StackCookie
0x140010e29  call    __security_check_cookie
0x140010e2e  add     rsp, 1E8h
0x140010e35  pop     r15
0x140010e37  pop     r14
0x140010e39  pop     r13
0x140010e3b  pop     r12
0x140010e3d  pop     rdi
0x140010e3e  pop     rsi
0x140010e3f  pop     rbx
0x140010e40  pop     rbp
0x140010e41  retn
0x140010e43  cmp     [rbx+28h], r13
0x140010e47  jz      loc_140010D81
0x140010e4d  mov     rax, cs:KdDebuggerEnabled
0x140010e54  cmp     [rax], r13b
0x140010e57  jz      loc_140010D81
0x140010e5d  lea     rcx, aPlastcommandIs; "pLastCommand is not NULL in FlushGdiCom"...
0x140010e64  call    cs:__imp_DbgPrint
0x140010e6b  nop     dword ptr [rax+rax+00h]
0x140010e70  mov     ecx, 2
0x140010e75  call    cs:__imp_WdLogSingleEntry0
0x140010e7c  nop     dword ptr [rax+rax+00h]
0x140010e81  mov     esi, 471h
0x140010e86  mov     cs:WdLogGlobalForLineNumber, esi
0x140010e8c  call    cs:__imp_WdLogNewEntry5_WdError
0x140010e93  nop     dword ptr [rax+rax+00h]
0x140010e98  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140010e9f  mov     r14d, 0CDDBA5Eh
0x140010ea5  mov     [rax+18h], rcx
0x140010ea9  mov     ecx, cs:dword_14003E570
0x140010eaf  mov     [rax+20h], rcx
0x140010eb3  mov     [rax+28h], r14
0x140010eb7  mov     cs:WdLogGlobalForLineNumber, esi
0x140010ebd  int     3; Trap to Debugger
0x140010ebe  jmp     loc_140010D81
0x140010ec3  test    edi, edi
0x140010ec5  js      loc_140010D81
0x140010ecb  call    ?SignalCommandBufferMonitoredFence@CDDPDEV@@QEAAJXZ; CDDPDEV::SignalCommandBufferMonitoredFence(void)
0x140010ed0  test    eax, eax
0x140010ed2  jns     loc_140010D81
0x140010ed8  movsxd  rdx, eax
0x140010edb  mov     ecx, 2
0x140010ee0  call    cs:__imp_WdLogSingleEntry1
0x140010ee7  nop     dword ptr [rax+rax+00h]
0x140010eec  mov     esi, 46Ah
0x140010ef1  mov     cs:WdLogGlobalForLineNumber, esi
0x140010ef7  call    cs:__imp_WdLogNewEntry5_WdError
0x140010efe  nop     dword ptr [rax+rax+00h]
0x140010f03  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140010f0a  mov     [rax+18h], rcx
0x140010f0e  mov     ecx, cs:dword_14003E570
0x140010f14  mov     [rax+20h], rcx
0x140010f18  mov     [rax+28h], r14
0x140010f1c  mov     cs:WdLogGlobalForLineNumber, esi
0x140010f22  jmp     loc_140010D81
0x140010f27  cmp     r13, r12
0x140010f2a  jz      loc_140010FC9
0x140010f30  mov     eax, [rbx+8]
0x140010f33  mov     r15, r13
0x140010f36  add     rax, 3
0x140010f3a  mov     [rsp+220h+var_1E8], 0
0x140010f43  shl     rax, 4
0x140010f47  mov     r8, rbx; struct CHwCommandBuffer *
0x140010f4a  sub     r15, rax
0x140010f4d  mov     rax, [rbx]
0x140010f50  mov     rdx, r15; struct CddResidencyState *
0x140010f53  mov     [rsp+220h+var_1E0], r15
0x140010f58  mov     rcx, [rax+31D0h]
0x140010f5f  lea     rax, [rsp+220h+var_1E8]
0x140010f64  mov     [r15+18h], rcx
0x140010f68  mov     rcx, [rbx]; this
0x140010f6b  mov     [rsp+220h+var_200], rax; unsigned __int64 *
0x140010f70  call    ?EnsureResident@CDDPDEV@@QEAAJPEAVCddResidencyState@@PEAVCHwCommandBuffer@@EPEA_K@Z; CDDPDEV::EnsureResident(CddResidencyState *,CHwCommandBuffer *,uchar,unsigned __int64 *)
0x140010f75  movsxd  rdi, eax
0x140010f78  cmp     edi, 103h
0x140010f7e  jz      loc_140011051
0x140010f84  test    eax, eax
0x140010f86  js      loc_1400110D9
0x140010f8c  mov     rcx, [rbx]; this
0x140010f8f  add     r15, 20h ; ' '
0x140010f93  mov     rdx, r15; struct _LIST_ENTRY *
0x140010f96  call    ?RemoveLruListEntry@CDDPDEV@@QEAAEPEAU_LIST_ENTRY@@@Z; CDDPDEV::RemoveLruListEntry(_LIST_ENTRY *)
0x140010f9b  mov     rax, [rsp+220h+var_1E0]
0x140010fa0  mov     rcx, [rax]
0x140010fa3  mov     rax, [rbx]
0x140010fa6  cmp     [rcx+8], rax
0x140010faa  jnz     loc_140011066
0x140010fb0  mov     rax, [rbx]
0x140010fb3  add     rax, 31F0h
0x140010fb9  mov     rcx, [rax]
0x140010fbc  cmp     [rcx+8], rax
0x140010fc0  jz      short loc_140011001
0x140010fc2  mov     ecx, 3
0x140010fc7  int     29h; Win8: RtlFailFast(ecx)
0x140010fc9  mov     rcx, [rbx]; this
0x140010fcc  call    ?ReleaseResidencyLock@CDDPDEV@@QEAAXXZ; CDDPDEV::ReleaseResidencyLock(void)
0x140010fd1  xor     r13d, r13d
0x140010fd4  test    edi, edi
0x140010fd6  js      loc_140010D71
0x140010fdc  test    rsi, rsi
0x140010fdf  jz      loc_140010D69
0x140010fe5  mov     rcx, [rbx]; this
0x140010fe8  mov     rdx, rsi; unsigned __int64
0x140010feb  call    ?WaitForPagingQueueMonitoredFence@CDDPDEV@@QEAAJ_K@Z; CDDPDEV::WaitForPagingQueueMonitoredFence(unsigned __int64)
0x140010ff0  movsxd  rdi, eax
0x140010ff3  test    eax, eax
0x140010ff5  js      loc_14001112B
0x140010ffb  mov     rdx, [r12]
0x140010fff  jmp     short loc_14001102F
0x140011001  mov     [r15], rcx
0x140011004  mov     [r15+8], rax
0x140011008  mov     [rcx+8], r15
0x14001100c  mov     [rax], r15
0x14001100f  mov     r13, [r13+0]
0x140011013  jmp     loc_140010F27
0x140011018  mov     ecx, [rbx+8]
0x14001101b  mov     rax, rdx
0x14001101e  add     rcx, 2
0x140011022  shl     rcx, 4
0x140011026  sub     rax, rcx
0x140011029  mov     [rax], r13
0x14001102c  mov     rdx, [rdx]
0x14001102f  cmp     rdx, r12
0x140011032  jnz     short loc_140011018
0x140011034  jmp     loc_140010D69
0x140011039  call    ?AcquireResidencyLock@CDDPDEV@@QEAAXXZ; CDDPDEV::AcquireResidencyLock(void)
0x14001103e  lea     r12, [rbx+838h]
0x140011045  mov     rsi, r13
0x140011048  mov     r13, [r12]
0x14001104c  jmp     loc_140010F27
0x140011051  cmp     rsi, [rsp+220h+var_1E8]
0x140011056  ja      loc_140010F8C
0x14001105c  mov     rsi, [rsp+220h+var_1E8]
0x140011061  jmp     loc_140010F8C
0x140011066  mov     rax, cs:KdDebuggerEnabled
0x14001106d  cmp     byte ptr [rax], 0
0x140011070  jz      loc_140010FB0
0x140011076  lea     rcx, aInvalidBitmapP; "Invalid bitmap PPDEV"
0x14001107d  call    cs:__imp_DbgPrint
0x140011084  nop     dword ptr [rax+rax+00h]
0x140011089  mov     ecx, 2
0x14001108e  call    cs:__imp_WdLogSingleEntry0
0x140011095  nop     dword ptr [rax+rax+00h]
0x14001109a  mov     cs:WdLogGlobalForLineNumber, 427h
0x1400110a4  call    cs:__imp_WdLogNewEntry5_WdError
0x1400110ab  nop     dword ptr [rax+rax+00h]
0x1400110b0  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400110b7  mov     [rax+18h], rcx
0x1400110bb  mov     ecx, cs:dword_14003E570
0x1400110c1  mov     [rax+20h], rcx
0x1400110c5  mov     [rax+28h], r14
0x1400110c9  mov     cs:WdLogGlobalForLineNumber, 427h
0x1400110d3  int     3; Trap to Debugger
0x1400110d4  jmp     loc_140010FB0
0x1400110d9  mov     rdx, rdi
0x1400110dc  mov     ecx, 2
0x1400110e1  call    cs:__imp_WdLogSingleEntry1
0x1400110e8  nop     dword ptr [rax+rax+00h]
0x1400110ed  mov     r15d, 422h
0x1400110f3  mov     cs:WdLogGlobalForLineNumber, r15d
0x1400110fa  call    cs:__imp_WdLogNewEntry5_WdError
0x140011101  nop     dword ptr [rax+rax+00h]
0x140011106  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001110d  mov     [rax+18h], rcx
0x140011111  mov     ecx, cs:dword_14003E570
0x140011117  mov     [rax+20h], rcx
0x14001111b  mov     [rax+28h], r14
0x14001111f  mov     cs:WdLogGlobalForLineNumber, r15d
0x140011126  jmp     loc_140010FC9
0x14001112b  mov     rdx, rdi
0x14001112e  mov     ecx, 2
0x140011133  call    cs:__imp_WdLogSingleEntry1
0x14001113a  nop     dword ptr [rax+rax+00h]
0x14001113f  mov     esi, 435h
0x140011144  mov     cs:WdLogGlobalForLineNumber, esi
0x14001114a  call    cs:__imp_WdLogNewEntry5_WdError
0x140011151  nop     dword ptr [rax+rax+00h]
0x140011156  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001115d  mov     [rax+18h], rcx
0x140011161  mov     ecx, cs:dword_14003E570
0x140011167  mov     [rax+20h], rcx
0x14001116b  mov     [rax+28h], r14
0x14001116f  mov     cs:WdLogGlobalForLineNumber, esi
0x140011175  jmp     loc_140010D69
0x14001117a  mov     r15d, [rsp+220h+var_1F0]
  ... truncated ...
```
