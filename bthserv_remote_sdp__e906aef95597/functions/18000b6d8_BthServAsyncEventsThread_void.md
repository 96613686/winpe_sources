# BthServAsyncEventsThread(void *)

- ea: `0x18000b6d8`
- end: `0x18000ba8a`
- name: `?BthServAsyncEventsThread@@YAKPEAX@Z`
- size: `946`
- prototype: `unsigned int __fastcall(HANDLE hEvent)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000ba90`

## callees

- `0x18000b6d8`
- `0x180010128`
- `0x180012004`
- `0x1800120b8`
- `0x180012384`
- `0x18001ca3c`
- `0x18001cde0`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000b80c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000b80c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b7ad`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b7ad`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18000b8e3`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18000b8e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ba12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ba12`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18000b9e8`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18000b9e8`

## pseudocode

```c
__int64 __fastcall BthServAsyncEventsThread(HANDLE hEvent)
{
  _BYTE *v2; // rcx
  char v3; // di
  bool v4; // dl
  _UNKNOWN **v5; // rax
  bool v6; // dl
  bool v7; // dl
  int v8; // edx
  DWORD v9; // ebx
  int v10; // r8d
  _BYTE *v11; // rcx
  _UNKNOWN **v12; // rax
  bool v13; // dl
  __int64 v14; // rdx
  __int64 v15; // r8
  volatile signed __int32 *v16; // rbx
  _BYTE *v17; // rcx
  bool v18; // dl
  PVOID v19; // rax
  HANDLE *v21; // [rsp+50h] [rbp-18h] BYREF
  volatile signed __int32 *v22; // [rsp+58h] [rbp-10h]

  v2 = WPP_GLOBAL_Control;
  v3 = 1;
  v4 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  v5 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v2 = WPP_GLOBAL_Control;
    v5 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  v6 = v2 != (_BYTE *)&WPP_GLOBAL_Control && v2[25] >= 4u;
  if ( v6 || v5 != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)v2 + 2), v6, v5 != &WPP_RECORDER_INITIALIZED, *((_QWORD *)v2 + 5));
  BthServStartAutoConfigServiceMonitor();
  SetEvent(hEvent);
  v7 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  do
  {
    v9 = WaitForSingleObjectEx(::hEvent, 0xFFFFFFFF, 1);
    v11 = WPP_GLOBAL_Control;
    LOBYTE(v8) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
    v12 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v10, *((_QWORD *)WPP_GLOBAL_Control + 5));
      v11 = WPP_GLOBAL_Control;
      v12 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
    }
  }
  while ( v9 );
  v13 = v11 != (_BYTE *)&WPP_GLOBAL_Control && v11[25] >= 4u;
  if ( v13 || v12 != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)v11 + 2), v13, v12 != &WPP_RECORDER_INITIALIZED, *((_QWORD *)v11 + 5));
  BthServStopAutoConfigServiceMonitor();
  BthServGlobals::GetSafeRadioHandle(&Globals, &v21);
  if ( v21 && (char *)*v21 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CancelIoEx(*v21, 0);
  if ( v22 )
  {
    if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
    {
      v16 = v22;
      (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
    }
  }
  v17 = WPP_GLOBAL_Control;
  v18 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v18 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v18,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v17 = WPP_GLOBAL_Control;
  }
  v19 = pv;
  if ( pv )
  {
    LOBYTE(v14) = v17 != (_BYTE *)&WPP_GLOBAL_Control && v17[25] >= 4u;
    LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v14 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)v17 + 2), (_BYTE)v14, (_BYTE)v15, *((_QWORD *)v17 + 5));
      v19 = pv;
    }
    CM_Unregister_Notification(v19, v14, v15);
    pv = 0;
    v17 = WPP_GLOBAL_Control;
  }
  if ( *(&pv + 1) )
  {
    LocalFree(*(&pv + 1));
    *(&pv + 1) = 0;
    v17 = WPP_GLOBAL_Control;
  }
  if ( v17 == (_BYTE *)&WPP_GLOBAL_Control || v17[25] < 5u )
    v3 = 0;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)v17 + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v17 + 5));
  return 0;
}

```

## disassembly

```asm
0x18000b6d8  mov     rax, rsp
0x18000b6db  mov     [rax+8], rbx
0x18000b6df  mov     [rax+10h], rbp
0x18000b6e3  mov     [rax+18h], rdi
0x18000b6e7  mov     [rax+20h], r12
0x18000b6eb  push    r15
0x18000b6ed  sub     rsp, 60h
0x18000b6f1  mov     rbx, rcx
0x18000b6f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6fb  lea     rbp, WPP_GLOBAL_Control
0x18000b702  mov     edi, 1
0x18000b707  cmp     rcx, rbp
0x18000b70a  jz      short loc_18000B717
0x18000b70c  cmp     byte ptr [rcx+19h], 5
0x18000b710  jb      short loc_18000B717
0x18000b712  mov     dl, dil
0x18000b715  jmp     short loc_18000B719
0x18000b717  xor     dl, dl
0x18000b719  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18000b720  lea     r15, WPP_RECORDER_INITIALIZED
0x18000b727  cmp     rax, r15
0x18000b72a  lea     r12, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000b731  setnz   r8b
0x18000b735  test    dl, dl
0x18000b737  jnz     short loc_18000B73E
0x18000b739  test    r8b, r8b
0x18000b73c  jz      short loc_18000B765
0x18000b73e  mov     r9, [rcx+28h]
0x18000b742  mov     rcx, [rcx+10h]
0x18000b746  mov     [rsp+68h+var_30], r12
0x18000b74b  mov     [rsp+68h+var_38], 80h
0x18000b752  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000b757  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b75e  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18000b765  cmp     rcx, rbp
0x18000b768  jz      short loc_18000B775
0x18000b76a  cmp     byte ptr [rcx+19h], 4
0x18000b76e  jb      short loc_18000B775
0x18000b770  mov     dl, dil
0x18000b773  jmp     short loc_18000B777
0x18000b775  xor     dl, dl
0x18000b777  cmp     rax, r15
0x18000b77a  setnz   r8b
0x18000b77e  test    dl, dl
0x18000b780  jnz     short loc_18000B787
0x18000b782  test    r8b, r8b
0x18000b785  jz      short loc_18000B7A5
0x18000b787  mov     r9, [rcx+28h]
0x18000b78b  mov     rcx, [rcx+10h]
0x18000b78f  mov     [rsp+68h+var_20], rbx
0x18000b794  mov     [rsp+68h+var_30], r12
0x18000b799  mov     [rsp+68h+var_38], 81h
0x18000b7a0  call    WPP_RECORDER_AND_TRACE_SF_si
0x18000b7a5  call    ?BthServStartAutoConfigServiceMonitor@@YAXXZ; BthServStartAutoConfigServiceMonitor(void)
0x18000b7aa  mov     rcx, rbx; hEvent
0x18000b7ad  call    cs:__imp_SetEvent
0x18000b7b4  nop     dword ptr [rax+rax+00h]
0x18000b7b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b7c0  cmp     rcx, rbp
0x18000b7c3  jz      short loc_18000B7D0
0x18000b7c5  cmp     byte ptr [rcx+19h], 4
0x18000b7c9  jb      short loc_18000B7D0
0x18000b7cb  mov     dl, dil
0x18000b7ce  jmp     short loc_18000B7D2
0x18000b7d0  xor     dl, dl
0x18000b7d2  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18000b7d9  setnz   r8b
0x18000b7dd  test    dl, dl
0x18000b7df  jnz     short loc_18000B7E6
0x18000b7e1  test    r8b, r8b
0x18000b7e4  jz      short loc_18000B7FF
0x18000b7e6  mov     r9, [rcx+28h]
0x18000b7ea  mov     rcx, [rcx+10h]
0x18000b7ee  mov     [rsp+68h+var_30], r12
0x18000b7f3  mov     [rsp+68h+var_38], 82h
0x18000b7fa  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000b7ff  mov     rcx, cs:hEvent; hHandle
0x18000b806  mov     r8d, edi; bAlertable
0x18000b809  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000b80c  call    cs:__imp_WaitForSingleObjectEx
0x18000b813  nop     dword ptr [rax+rax+00h]
0x18000b818  mov     ebx, eax
0x18000b81a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b821  cmp     rcx, rbp
0x18000b824  jz      short loc_18000B831
0x18000b826  cmp     byte ptr [rcx+19h], 4
0x18000b82a  jb      short loc_18000B831
0x18000b82c  mov     dl, dil
0x18000b82f  jmp     short loc_18000B833
0x18000b831  xor     dl, dl
0x18000b833  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18000b83a  cmp     rax, r15
0x18000b83d  setnz   r8b
0x18000b841  test    dl, dl
0x18000b843  jnz     short loc_18000B84A
0x18000b845  test    r8b, r8b
0x18000b848  jz      short loc_18000B875
0x18000b84a  mov     r9, [rcx+28h]
0x18000b84e  mov     rcx, [rcx+10h]
0x18000b852  mov     dword ptr [rsp+68h+var_20], ebx
0x18000b856  mov     [rsp+68h+var_30], r12
0x18000b85b  mov     [rsp+68h+var_38], 83h
0x18000b862  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18000b867  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b86e  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18000b875  test    ebx, ebx
0x18000b877  jnz     short loc_18000B7FF
0x18000b879  cmp     rcx, rbp
0x18000b87c  jz      short loc_18000B889
0x18000b87e  cmp     byte ptr [rcx+19h], 4
0x18000b882  jb      short loc_18000B889
0x18000b884  mov     dl, dil
0x18000b887  jmp     short loc_18000B88B
0x18000b889  xor     dl, dl
0x18000b88b  cmp     rax, r15
0x18000b88e  setnz   r8b
0x18000b892  test    dl, dl
0x18000b894  jnz     short loc_18000B89B
0x18000b896  test    r8b, r8b
0x18000b899  jz      short loc_18000B8B4
0x18000b89b  mov     r9, [rcx+28h]
0x18000b89f  mov     rcx, [rcx+10h]
0x18000b8a3  mov     [rsp+68h+var_30], r12
0x18000b8a8  mov     [rsp+68h+var_38], 84h
0x18000b8af  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000b8b4  call    ?BthServStopAutoConfigServiceMonitor@@YAXXZ; BthServStopAutoConfigServiceMonitor(void)
0x18000b8b9  lea     rdx, [rsp+68h+var_18]
0x18000b8be  lea     rcx, ?Globals@@3VBthServGlobals@@A; BthServGlobals Globals
0x18000b8c5  call    ?GetSafeRadioHandle@BthServGlobals@@QEAA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ; BthServGlobals::GetSafeRadioHandle(void)
0x18000b8ca  mov     rax, [rsp+68h+var_18]
0x18000b8cf  test    rax, rax
0x18000b8d2  jz      short loc_18000B8EF
0x18000b8d4  mov     rcx, [rax]; hFile
0x18000b8d7  lea     rax, [rcx-1]
0x18000b8db  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b8df  ja      short loc_18000B8EF
0x18000b8e1  xor     edx, edx; lpOverlapped
0x18000b8e3  call    cs:__imp_CancelIoEx
0x18000b8ea  nop     dword ptr [rax+rax+00h]
0x18000b8ef  mov     rcx, [rsp+68h+var_10]
0x18000b8f4  test    rcx, rcx
0x18000b8f7  jz      short loc_18000B935
0x18000b8f9  or      eax, 0FFFFFFFFh
0x18000b8fc  lock xadd [rcx+8], eax
0x18000b901  cmp     eax, edi
0x18000b903  jnz     short loc_18000B935
0x18000b905  mov     rbx, [rsp+68h+var_10]
0x18000b90a  mov     rcx, rbx
0x18000b90d  mov     rax, [rbx]
0x18000b910  mov     rax, [rax]
0x18000b913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b918  or      eax, 0FFFFFFFFh
0x18000b91b  lock xadd [rbx+0Ch], eax
0x18000b920  cmp     eax, edi
0x18000b922  jnz     short loc_18000B935
0x18000b924  mov     rcx, [rsp+68h+var_10]
0x18000b929  mov     rax, [rcx]
0x18000b92c  mov     rax, [rax+8]
0x18000b930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b935  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b93c  cmp     rcx, rbp
0x18000b93f  jz      short loc_18000B94C
0x18000b941  cmp     byte ptr [rcx+19h], 4
0x18000b945  jb      short loc_18000B94C
0x18000b947  mov     dl, dil
0x18000b94a  jmp     short loc_18000B94E
0x18000b94c  xor     dl, dl
0x18000b94e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18000b955  setnz   r8b
0x18000b959  test    dl, dl
0x18000b95b  jnz     short loc_18000B962
0x18000b95d  test    r8b, r8b
0x18000b960  jz      short loc_18000B98E
0x18000b962  mov     rax, qword ptr cs:pv
0x18000b969  mov     r9, [rcx+28h]
0x18000b96d  mov     rcx, [rcx+10h]
0x18000b971  mov     [rsp+68h+var_20], rax
0x18000b976  mov     [rsp+68h+var_30], r12
0x18000b97b  mov     [rsp+68h+var_38], 85h
0x18000b982  call    WPP_RECORDER_AND_TRACE_SF_si
0x18000b987  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b98e  mov     rax, qword ptr cs:pv
0x18000b995  test    rax, rax
0x18000b998  jz      short loc_18000BA03
0x18000b99a  cmp     rcx, rbp
0x18000b99d  jz      short loc_18000B9AA
0x18000b99f  cmp     byte ptr [rcx+19h], 4
0x18000b9a3  jb      short loc_18000B9AA
0x18000b9a5  mov     dl, dil
0x18000b9a8  jmp     short loc_18000B9AC
0x18000b9aa  xor     dl, dl
0x18000b9ac  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18000b9b3  setnz   r8b
0x18000b9b7  test    dl, dl
0x18000b9b9  jnz     short loc_18000B9C0
0x18000b9bb  test    r8b, r8b
0x18000b9be  jz      short loc_18000B9E5
0x18000b9c0  mov     r9, [rcx+28h]
0x18000b9c4  mov     rcx, [rcx+10h]
0x18000b9c8  mov     [rsp+68h+var_20], rax
0x18000b9cd  mov     [rsp+68h+var_30], r12
0x18000b9d2  mov     [rsp+68h+var_38], 86h
0x18000b9d9  call    WPP_RECORDER_AND_TRACE_SF_si
0x18000b9de  mov     rax, qword ptr cs:pv
0x18000b9e5  mov     rcx, rax
0x18000b9e8  call    cs:__imp_CM_Unregister_Notification
0x18000b9ef  nop     dword ptr [rax+rax+00h]
0x18000b9f4  and     qword ptr cs:pv, 0
0x18000b9fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba03  mov     rax, qword ptr cs:pv+8
0x18000ba0a  test    rax, rax
0x18000ba0d  jz      short loc_18000BA2D
0x18000ba0f  mov     rcx, rax; hMem
0x18000ba12  call    cs:__imp_LocalFree
0x18000ba19  nop     dword ptr [rax+rax+00h]
0x18000ba1e  and     qword ptr cs:pv+8, 0
0x18000ba26  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba2d  cmp     rcx, rbp
0x18000ba30  jz      short loc_18000BA38
0x18000ba32  cmp     byte ptr [rcx+19h], 5
0x18000ba36  jnb     short loc_18000BA3B
0x18000ba38  xor     dil, dil
0x18000ba3b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18000ba42  setnz   r8b
0x18000ba46  test    dil, dil
0x18000ba49  jnz     short loc_18000BA50
0x18000ba4b  test    r8b, r8b
0x18000ba4e  jz      short loc_18000BA6C
0x18000ba50  mov     r9, [rcx+28h]
0x18000ba54  mov     dl, dil
0x18000ba57  mov     rcx, [rcx+10h]
0x18000ba5b  mov     [rsp+68h+var_30], r12
0x18000ba60  mov     [rsp+68h+var_38], 87h
0x18000ba67  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000ba6c  lea     r11, [rsp+68h+var_8]
0x18000ba71  xor     eax, eax
0x18000ba73  mov     rbx, [r11+10h]
0x18000ba77  mov     rbp, [r11+18h]
0x18000ba7b  mov     rdi, [r11+20h]
0x18000ba7f  mov     r12, [r11+28h]
0x18000ba83  mov     rsp, r11
0x18000ba86  pop     r15
0x18000ba88  retn
```
