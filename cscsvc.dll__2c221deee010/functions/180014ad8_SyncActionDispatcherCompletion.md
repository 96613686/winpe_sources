# SyncActionDispatcherCompletion

- ea: `0x180014ad8`
- end: `0x180014d01`
- name: `SyncActionDispatcherCompletion`
- size: `553`
- prototype: `__int64 __fastcall(ULONG, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800264b0`

## callees

- `0x18000304c`
- `0x180014ad8`
- `0x180015cf0`
- `0x18001f140`
- `0x1800360c0`
- `0x180036394`
- `0x18003c460`
- `0x1800413c8`
- `0x1800756ac`
- `0x180089010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180014bc2`
- `ntdll!RtlNtStatusToDosError` at `0x180014beb`
- `ntdll!RtlNtStatusToDosError` at `0x180014bc2`
- `ntdll!RtlNtStatusToDosError` at `0x180014beb`

## string_xrefs

- `0x180014b50`: `SyncActionDispatcherCompletion`
- `0x180014b1d`: `SyncActionDispatcherCompletion: 0x%p, %u`
- `0x180014c81`: `SyncActionDispatcherCompletion: queued work item for retry`
- `0x180014c3f`: `SyncActionDispatcherCompletion: failed to queue work item for retry, error = %d`
- `0x180014cc7`: `SyncActionDispatcherCompletion: %d`

## pseudocode

```c
__int64 __fastcall SyncActionDispatcherCompletion(ULONG a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbp
  ULONG v8; // ebx
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // rcx
  int v12; // eax
  NTSTATUS v13; // eax
  CObjectMonitor *v14; // rax
  __int128 v16; // [rsp+30h] [rbp-58h] BYREF
  __int128 v17; // [rsp+40h] [rbp-48h]

  v4 = *(_QWORD *)(a2 + 24);
  v16 = 0;
  v17 = 0;
  v8 = a1;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    SyncTraceOutputInternal(L"SyncActionDispatcherCompletion: 0x%p, %u", a2, a1);
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 12), 20, WPP_ab3993576fe8311113e3a81f00d548d5_Traceguids, a2, v8);
  }
  while ( 1 )
  {
    do
    {
      while ( 1 )
      {
        v9 = *(_QWORD *)(a3 + 16);
        *((_QWORD *)&v16 + 1) = *(_QWORD *)(a3 + 8);
        LODWORD(v17) = *(_DWORD *)(a3 + 240);
        DWORD1(v17) = *(_DWORD *)(a3 + 248);
        DWORD2(v17) = *(_DWORD *)(a3 + 104);
        *(_QWORD *)&v16 = v9;
        HIDWORD(v17) = v8;
        SyncItemValidateAndTraceItem(L"SyncActionDispatcherCompletion");
        v10 = (*(__int64 (__fastcall **)(__int128 *, __int64))(a3 + 56))(&v16, a4);
        v11 = ((unsigned __int16)v10 ^ (unsigned __int16)*(_DWORD *)(a3 + 32)) & 0x1F8;
        *(_DWORD *)(a3 + 32) ^= v11;
        if ( !v10 )
        {
          SyncActionQueueFreeActionItem(v11, a3);
          goto LABEL_16;
        }
        v12 = *(_DWORD *)(a3 + 248);
        if ( v12 != 0xFFFFFFF )
          break;
        v8 = RtlNtStatusToDosError(-1073741823);
        *(_DWORD *)(a3 + 104) = 513;
      }
      *(_DWORD *)(a3 + 248) = v12 + 1;
      v13 = SyncActionQueueRequeue(v4, a3);
      v8 = RtlNtStatusToDosError(v13);
    }
    while ( v8 );
    v8 = CscTpQueueWorkItem(
           *(PTP_CALLBACK_ENVIRON *)(a2 + 88),
           SyncActionDispatcher,
           SyncActionWorkItemCancelled,
           (void *)a2,
           1);
    if ( !v8 )
      break;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(L"SyncActionDispatcherCompletion: failed to queue work item for retry, error = %d", v8);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 22, WPP_ab3993576fe8311113e3a81f00d548d5_Traceguids, v8);
    }
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control )
    return v8;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    SyncTraceOutputInternal(L"SyncActionDispatcherCompletion: queued work item for retry");
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 21, WPP_ab3993576fe8311113e3a81f00d548d5_Traceguids);
LABEL_16:
    v14 = WPP_GLOBAL_Control;
  }
  if ( v14 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v14 + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncActionDispatcherCompletion: %d", v8);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 23, WPP_ab3993576fe8311113e3a81f00d548d5_Traceguids, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x180014ad8  push    rbx
0x180014ada  push    rbp
0x180014adb  push    rsi
0x180014adc  push    rdi
0x180014add  push    r14
0x180014adf  push    r15
0x180014ae1  sub     rsp, 58h
0x180014ae5  mov     rbp, [rdx+18h]
0x180014ae9  xorps   xmm0, xmm0
0x180014aec  movups  [rsp+88h+var_58], xmm0
0x180014af1  mov     r14, r9
0x180014af4  mov     rdi, r8
0x180014af7  movups  [rsp+88h+var_48], xmm0
0x180014afc  mov     rsi, rdx
0x180014aff  mov     ebx, ecx
0x180014b01  mov     rax, cs:WPP_GLOBAL_Control
0x180014b08  lea     r15, WPP_GLOBAL_Control
0x180014b0f  cmp     rax, r15
0x180014b12  jz      short loc_180014B4C
0x180014b14  test    byte ptr [rax+6Ch], 4
0x180014b18  jz      short loc_180014B4C
0x180014b1a  mov     r8d, ecx
0x180014b1d  lea     rcx, aSyncactiondisp_6; "SyncActionDispatcherCompletion: 0x%p, %"...
0x180014b24  call    SyncTraceOutputInternal
0x180014b29  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b30  lea     r8, WPP_ab3993576fe8311113e3a81f00d548d5_Traceguids
0x180014b37  mov     edx, 14h
0x180014b3c  mov     [rsp+88h+var_68], ebx
0x180014b40  mov     r9, rsi
0x180014b43  mov     rcx, [rcx+60h]
0x180014b47  call    WPP_SF_qD
0x180014b4c  mov     rax, [rdi+8]
0x180014b50  lea     rcx, aSyncactiondisp; "SyncActionDispatcherCompletion"
0x180014b57  mov     rdx, [rdi+10h]
0x180014b5b  mov     qword ptr [rsp+88h+var_58+8], rax
0x180014b60  mov     eax, [rdi+0F0h]
0x180014b66  mov     dword ptr [rsp+88h+var_48], eax
0x180014b6a  mov     eax, [rdi+0F8h]
0x180014b70  mov     dword ptr [rsp+88h+var_48+4], eax
0x180014b74  mov     eax, [rdi+68h]
0x180014b77  mov     dword ptr [rsp+88h+var_48+8], eax
0x180014b7b  mov     qword ptr [rsp+88h+var_58], rdx
0x180014b80  mov     dword ptr [rsp+88h+var_48+0Ch], ebx
0x180014b84  call    SyncItemValidateAndTraceItem
0x180014b89  mov     rax, [rdi+38h]
0x180014b8d  lea     rcx, [rsp+88h+var_58]
0x180014b92  mov     rdx, r14
0x180014b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b9a  mov     ecx, [rdi+20h]
0x180014b9d  xor     ecx, eax
0x180014b9f  and     ecx, 1F8h
0x180014ba5  xor     [rdi+20h], ecx
0x180014ba8  test    eax, eax
0x180014baa  jz      loc_180014CAB
0x180014bb0  mov     eax, [rdi+0F8h]
0x180014bb6  cmp     eax, 0FFFFFFFh
0x180014bbb  jnz     short loc_180014BD6
0x180014bbd  mov     ecx, 0C0000001h; Status
0x180014bc2  call    cs:__imp_RtlNtStatusToDosError
0x180014bc8  mov     ebx, eax
0x180014bca  mov     dword ptr [rdi+68h], 201h
0x180014bd1  jmp     loc_180014B4C
0x180014bd6  inc     eax
0x180014bd8  mov     rdx, rdi
0x180014bdb  mov     rcx, rbp
0x180014bde  mov     [rdi+0F8h], eax
0x180014be4  call    SyncActionQueueRequeue
0x180014be9  mov     ecx, eax; Status
0x180014beb  call    cs:__imp_RtlNtStatusToDosError
0x180014bf1  mov     ebx, eax
0x180014bf3  test    eax, eax
0x180014bf5  jnz     loc_180014B4C
0x180014bfb  mov     rcx, [rsi+58h]; pcbe
0x180014bff  lea     r8, SyncActionWorkItemCancelled
0x180014c06  mov     r9, rsi
0x180014c09  mov     [rsp+88h+var_68], 1; int
0x180014c11  lea     rdx, SyncActionDispatcher
0x180014c18  call    CscTpQueueWorkItem
0x180014c1d  mov     ebx, eax
0x180014c1f  test    eax, eax
0x180014c21  jz      short loc_180014C6F
0x180014c23  mov     rax, cs:WPP_GLOBAL_Control
0x180014c2a  cmp     rax, r15
0x180014c2d  jz      loc_180014B4C
0x180014c33  test    byte ptr [rax+6Ch], 1
0x180014c37  jz      loc_180014B4C
0x180014c3d  mov     edx, ebx
0x180014c3f  lea     rcx, aSyncactiondisp_5; "SyncActionDispatcherCompletion: failed "...
0x180014c46  call    SyncTraceOutputInternal
0x180014c4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c52  lea     r8, WPP_ab3993576fe8311113e3a81f00d548d5_Traceguids
0x180014c59  mov     edx, 16h
0x180014c5e  mov     r9d, ebx
0x180014c61  mov     rcx, [rcx+60h]
0x180014c65  call    WPP_SF_d
0x180014c6a  jmp     loc_180014B4C
0x180014c6f  mov     rax, cs:WPP_GLOBAL_Control
0x180014c76  cmp     rax, r15
0x180014c79  jz      short loc_180014CF2
0x180014c7b  test    byte ptr [rax+6Ch], 1
0x180014c7f  jz      short loc_180014CBA
0x180014c81  lea     rcx, aSyncactiondisp_3; "SyncActionDispatcherCompletion: queued "...
0x180014c88  call    SyncTraceOutputInternal
0x180014c8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c94  lea     r8, WPP_ab3993576fe8311113e3a81f00d548d5_Traceguids
0x180014c9b  mov     edx, 15h
0x180014ca0  mov     rcx, [rcx+60h]
0x180014ca4  call    WPP_SF_
0x180014ca9  jmp     short loc_180014CB3
0x180014cab  mov     rdx, rdi
0x180014cae  call    SyncActionQueueFreeActionItem
0x180014cb3  mov     rax, cs:WPP_GLOBAL_Control
0x180014cba  cmp     rax, r15
0x180014cbd  jz      short loc_180014CF2
0x180014cbf  test    byte ptr [rax+6Ch], 8
0x180014cc3  jz      short loc_180014CF2
0x180014cc5  mov     edx, ebx
0x180014cc7  lea     rcx, aSyncactiondisp_1; "SyncActionDispatcherCompletion: %d"
0x180014cce  call    SyncTraceOutputInternal
0x180014cd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180014cda  lea     r8, WPP_ab3993576fe8311113e3a81f00d548d5_Traceguids
0x180014ce1  mov     edx, 17h
0x180014ce6  mov     r9d, ebx
0x180014ce9  mov     rcx, [rcx+60h]
0x180014ced  call    WPP_SF_d
0x180014cf2  mov     eax, ebx
0x180014cf4  add     rsp, 58h
0x180014cf8  pop     r15
0x180014cfa  pop     r14
0x180014cfc  pop     rdi
0x180014cfd  pop     rsi
0x180014cfe  pop     rbp
0x180014cff  pop     rbx
0x180014d00  retn
```
