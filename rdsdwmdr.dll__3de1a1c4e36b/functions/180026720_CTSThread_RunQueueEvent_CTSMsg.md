# CTSThread::RunQueueEvent(CTSMsg *)

- ea: `0x180026720`
- end: `0x180026a4b`
- name: `?RunQueueEvent@CTSThread@@IEAAJPEAVCTSMsg@@@Z`
- size: `811`
- prototype: `__int64 __fastcall(CTSThread *__hidden this, struct CTSMsg *)`
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180022f00`
- `0x180026480`

## callees

- `0x18000f068`
- `0x18000f08c`
- `0x18001d04c`
- `0x18001d114`
- `0x18001efd8`
- `0x18001f424`
- `0x180022390`
- `0x180024eb0`
- `0x18002515c`
- `0x180025c7c`
- `0x180026234`
- `0x180026254`
- `0x180026720`
- `0x180027b98`
- `0x180027de4`
- `0x18002a1c4`
- `0x18002b960`
- `0x18002c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002681f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002681f`

## pseudocode

```c
_BOOL8 __fastcall CTSThread::RunQueueEvent(CTSThread *this, struct CTSMsg *a2)
{
  struct ITSAsyncResult *v2; // rbx
  struct CTSMsg *v3; // r14
  __int64 v5; // rdx
  __int64 v6; // rcx
  BOOL Item; // edi
  __int64 v8; // r8
  __int64 v9; // r9
  int ActivityIdPrefix; // eax
  __int64 v11; // rax
  struct ITSAsyncResult *v12; // rdi
  CTSReaderWriterLock *v13; // rdi
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // esi
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // esi
  unsigned int v21; // eax
  int v22; // eax
  int v23; // r8d
  CTSReaderWriterLock *v24; // rcx
  unsigned int v25; // r12d
  __int64 v26; // rdx
  int v27; // edi
  __int64 v28; // r8
  __int64 v29; // r9
  unsigned int v30; // eax
  DWORD v32; // [rsp+30h] [rbp-30h] BYREF
  int v33; // [rsp+34h] [rbp-2Ch]
  struct ITSAsyncResult *v34; // [rsp+38h] [rbp-28h] BYREF
  GUID ActivityId; // [rsp+40h] [rbp-20h] BYREF

  v2 = 0;
  *(_QWORD *)&ActivityId.Data1 = 0;
  v34 = 0;
  v3 = a2;
  if ( a2 )
  {
    v33 = 0;
  }
  else
  {
    Item = CTSThread::GetItem(this, 0, (struct CTSMsg **)&ActivityId);
    if ( Item < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(v6, v5, v8, v9);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          64,
          (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
          ActivityIdPrefix,
          (__int64)"GetItem failed!",
          Item);
      }
      goto LABEL_38;
    }
    v3 = *(struct CTSMsg **)&ActivityId.Data1;
    v33 = 1;
  }
  if ( !v3 )
  {
    Item = 1;
    goto LABEL_38;
  }
  v11 = *((_QWORD *)v3 + 20);
  ActivityId.Data1 = *((_DWORD *)v3 + 38);
  ActivityId.Data2 = *((_WORD *)v3 + 78);
  ActivityId.Data3 = *((_WORD *)v3 + 79);
  *(_QWORD *)ActivityId.Data4 = v11;
  EventActivityIdControl(2u, &ActivityId);
  v12 = CTSMsg::GetResult(v3);
  if ( v12 )
  {
    TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v34);
    v2 = v12;
    v34 = v12;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(&v34);
  }
  v13 = (CTSThread *)((char *)this + 148);
  CTSReaderWriterLock::ReadLock((CTSThread *)((char *)this + 148));
  v14 = *((unsigned int *)this + 174);
  if ( (_DWORD)v14 )
  {
    v17 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 92) + 80LL))(
            *((_QWORD *)this + 92),
            v14,
            *((unsigned int *)this + 175));
    if ( v17 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v21 = RdpX_GetActivityIdPrefix(v16, v15, v18, v19);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_903e1551464439edae082eb88b6439cd_Traceguids, v21, v17);
      }
      v20 = 0;
      if ( *((_DWORD *)this + 37) == 1
        && (v22 = PAL_System_AtomicCompareAndExchange((char *)this + 148, 0x1FFFF), v22 == v23) )
      {
        v32 = 0;
        PAL_System_ThreadGetId(&v32);
        PAL_System_AtomicCompareAndExchange((char *)this + 152, v32);
        PAL_System_AtomicCompareAndExchange((char *)this + 156, 1);
        v13 = (CTSThread *)((char *)this + 148);
      }
      else
      {
        CTSReaderWriterLock::ReadUnlock((CTSThread *)((char *)this + 148));
        CTSReaderWriterLock::_WriteLockSpin(v24);
      }
      *((_DWORD *)this + 174) = 0;
      CTSReaderWriterLock::WriteUnlock(v13);
      goto LABEL_26;
    }
    v20 = 1;
  }
  else
  {
    v20 = 0;
  }
  CTSReaderWriterLock::ReadUnlock((CTSThread *)((char *)this + 148));
LABEL_26:
  v25 = CTSMsg::Invoke(v3);
  if ( v20 )
  {
    v27 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 92) + 88LL))(*((_QWORD *)this + 92));
    if ( v27 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v30 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v26, v28, v29);
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_903e1551464439edae082eb88b6439cd_Traceguids, v30, v27);
    }
  }
  if ( v2 )
  {
    (*(void (__fastcall **)(struct ITSAsyncResult *, _QWORD))(*(_QWORD *)v2 + 32LL))(v2, v25);
    (*(void (__fastcall **)(struct ITSAsyncResult *))(*(_QWORD *)v2 + 16LL))(v2);
  }
  if ( v33 )
  {
    CTSMsg::Terminate((struct CTSMsg *)((char *)v3 + 16));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 5) + 16LL))(*((_QWORD *)v3 + 5));
  }
  Item = 0;
LABEL_38:
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v34);
  return Item;
}

```

## disassembly

```asm
0x180026720  mov     [rsp-38h+arg_10], rbx
0x180026725  push    rbp
0x180026726  push    rsi
0x180026727  push    rdi
0x180026728  push    r12
0x18002672a  push    r13
0x18002672c  push    r14
0x18002672e  push    r15
0x180026730  mov     rbp, rsp
0x180026733  sub     rsp, 60h
0x180026737  mov     rax, cs:__security_cookie
0x18002673e  xor     rax, rsp
0x180026741  mov     [rbp+var_10], rax
0x180026745  xor     ebx, ebx
0x180026747  mov     qword ptr [rbp+ActivityId.Data1], 0
0x18002674f  mov     [rbp+var_28], rbx
0x180026753  mov     r14, rdx
0x180026756  mov     r15, rcx
0x180026759  lea     r12d, [rbx+1]
0x18002675d  test    rdx, rdx
0x180026760  jnz     short loc_1800267DD
0x180026762  lea     r8, [rbp+ActivityId]; struct CTSMsg **
0x180026766  call    ?GetItem@CTSThread@@AEAAJPEAVITSEventFilter@@PEAPEAVCTSMsg@@@Z; CTSThread::GetItem(ITSEventFilter *,CTSMsg * *)
0x18002676b  mov     edi, eax
0x18002676d  test    eax, eax
0x18002676f  jns     short loc_1800267D3
0x180026771  mov     rax, cs:WPP_GLOBAL_Control
0x180026778  lea     r13, WPP_GLOBAL_Control
0x18002677f  cmp     rax, r13
0x180026782  jz      loc_180026A1C
0x180026788  test    byte ptr [rax+1Ch], 8
0x18002678c  jz      loc_180026A1C
0x180026792  cmp     byte ptr [rax+19h], 2
0x180026796  jb      loc_180026A1C
0x18002679c  call    RdpX_GetActivityIdPrefix
0x1800267a1  lea     rcx, aGetitemFailed_0; "GetItem failed!"
0x1800267a8  mov     [rsp+60h+var_38], edi
0x1800267ac  mov     [rsp+60h+var_40], rcx
0x1800267b1  lea     edx, [rbx+40h]
0x1800267b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800267bb  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x1800267c2  mov     r9d, eax
0x1800267c5  mov     rcx, [rcx+10h]
0x1800267c9  call    WPP_SF_DsD
0x1800267ce  jmp     loc_180026A1C
0x1800267d3  mov     r14, qword ptr [rbp+ActivityId.Data1]
0x1800267d7  mov     [rbp+var_2C], r12d
0x1800267db  jmp     short loc_1800267E0
0x1800267dd  mov     [rbp+var_2C], ebx
0x1800267e0  test    r14, r14
0x1800267e3  jz      loc_180026A19
0x1800267e9  mov     ecx, [r14+98h]
0x1800267f0  lea     rdx, [rbp+ActivityId]; ActivityId
0x1800267f4  mov     rax, [r14+0A0h]
0x1800267fb  mov     [rbp+ActivityId.Data1], ecx
0x1800267fe  movzx   ecx, word ptr [r14+9Ch]
0x180026806  mov     [rbp+ActivityId.Data2], cx
0x18002680a  movzx   ecx, word ptr [r14+9Eh]
0x180026812  mov     [rbp+ActivityId.Data3], cx
0x180026816  mov     ecx, 2; ControlCode
0x18002681b  mov     qword ptr [rbp+ActivityId.Data4], rax
0x18002681f  call    cs:__imp_EventActivityIdControl
0x180026825  mov     rcx, r14; this
0x180026828  call    ?GetResult@CTSMsg@@QEAAPEAVITSAsyncResult@@XZ; CTSMsg::GetResult(void)
0x18002682d  mov     rdi, rax
0x180026830  test    rax, rax
0x180026833  jz      short loc_18002684E
0x180026835  lea     rcx, [rbp+var_28]
0x180026839  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x18002683e  mov     rbx, rdi
0x180026841  lea     rcx, [rbp+var_28]
0x180026845  mov     [rbp+var_28], rbx
0x180026849  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18002684e  lea     rdi, [r15+94h]
0x180026855  mov     rcx, rdi; this
0x180026858  call    ?ReadLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadLock(void)
0x18002685d  mov     edx, [r15+2B8h]
0x180026864  lea     r13, WPP_GLOBAL_Control
0x18002686b  test    edx, edx
0x18002686d  jz      loc_18002695E
0x180026873  mov     rcx, [r15+2E0h]
0x18002687a  mov     r8d, [r15+2BCh]
0x180026881  mov     rax, [rcx]
0x180026884  mov     rax, [rax+50h]
0x180026888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002688d  mov     esi, eax
0x18002688f  test    eax, eax
0x180026891  js      short loc_18002689B
0x180026893  mov     esi, r12d
0x180026896  jmp     loc_180026960
0x18002689b  mov     rax, cs:WPP_GLOBAL_Control
0x1800268a2  cmp     rax, r13
0x1800268a5  jz      short loc_1800268DB
0x1800268a7  test    [rax+1Ch], r12b
0x1800268ab  jz      short loc_1800268DB
0x1800268ad  cmp     byte ptr [rax+19h], 3
0x1800268b1  jb      short loc_1800268DB
0x1800268b3  call    RdpX_GetActivityIdPrefix
0x1800268b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800268bf  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x1800268c6  mov     edx, 41h ; 'A'
0x1800268cb  mov     dword ptr [rsp+60h+var_40], esi
0x1800268cf  mov     r9d, eax
0x1800268d2  mov     rcx, [rcx+10h]
0x1800268d6  call    WPP_SF_Dd
0x1800268db  lea     r12, [r15+94h]
0x1800268e2  xor     esi, esi
0x1800268e4  mov     eax, [r12]
0x1800268e8  cmp     eax, 1
0x1800268eb  jnz     short loc_18002693C
0x1800268ed  mov     edx, 1FFFFh
0x1800268f2  mov     r8d, eax
0x1800268f5  mov     rcx, r12
0x1800268f8  call    PAL_System_AtomicCompareAndExchange
0x1800268fd  cmp     eax, r8d
0x180026900  jnz     short loc_18002693C
0x180026902  mov     edi, [r12+4]
0x180026907  lea     rcx, [rbp+var_30]
0x18002690b  mov     [rbp+var_30], esi
0x18002690e  call    PAL_System_ThreadGetId
0x180026913  mov     edx, [rbp+var_30]
0x180026916  lea     rcx, [r12+4]
0x18002691b  mov     r8d, edi
0x18002691e  call    PAL_System_AtomicCompareAndExchange
0x180026923  lea     rcx, [r12+8]
0x180026928  mov     r8d, [rcx]
0x18002692b  lea     edx, [rsi+1]
0x18002692e  call    PAL_System_AtomicCompareAndExchange
0x180026933  lea     rdi, [r15+94h]
0x18002693a  jmp     short loc_180026949
0x18002693c  mov     rcx, r12; this
0x18002693f  call    ?ReadUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadUnlock(void)
0x180026944  call    ?_WriteLockSpin@CTSReaderWriterLock@@AEAAXXZ; CTSReaderWriterLock::_WriteLockSpin(void)
0x180026949  mov     rcx, rdi; this
0x18002694c  mov     dword ptr [r15+2B8h], 0
0x180026957  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x18002695c  jmp     short loc_180026968
0x18002695e  xor     esi, esi
0x180026960  mov     rcx, rdi; this
0x180026963  call    ?ReadUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadUnlock(void)
0x180026968  mov     rcx, r14; this
0x18002696b  call    ?Invoke@CTSMsg@@QEAAJXZ; CTSMsg::Invoke(void)
0x180026970  mov     r12d, eax
0x180026973  test    esi, esi
0x180026975  jz      short loc_1800269D0
0x180026977  mov     rcx, [r15+2E0h]
0x18002697e  mov     rdx, [rcx]
0x180026981  mov     rax, [rdx+58h]
0x180026985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002698a  mov     edi, eax
0x18002698c  test    eax, eax
0x18002698e  jns     short loc_1800269D0
0x180026990  mov     rcx, cs:WPP_GLOBAL_Control
0x180026997  cmp     rcx, r13
0x18002699a  jz      short loc_1800269D0
0x18002699c  test    byte ptr [rcx+1Ch], 1
0x1800269a0  jz      short loc_1800269D0
0x1800269a2  cmp     byte ptr [rcx+19h], 3
0x1800269a6  jb      short loc_1800269D0
0x1800269a8  call    RdpX_GetActivityIdPrefix
0x1800269ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800269b4  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x1800269bb  mov     edx, 42h ; 'B'
0x1800269c0  mov     dword ptr [rsp+60h+var_40], edi
0x1800269c4  mov     r9d, eax
0x1800269c7  mov     rcx, [rcx+10h]
0x1800269cb  call    WPP_SF_Dd
0x1800269d0  test    rbx, rbx
0x1800269d3  jz      short loc_1800269F6
0x1800269d5  mov     rax, [rbx]
0x1800269d8  mov     edx, r12d
0x1800269db  mov     rcx, rbx
0x1800269de  mov     rax, [rax+20h]
0x1800269e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269e7  mov     rax, [rbx]
0x1800269ea  mov     rcx, rbx
0x1800269ed  mov     rax, [rax+10h]
0x1800269f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269f6  cmp     [rbp+var_2C], 0
0x1800269fa  jz      short loc_180026A15
0x1800269fc  lea     rcx, [r14+10h]; this
0x180026a00  call    ?Terminate@CTSMsg@@UEAAJXZ; CTSMsg::Terminate(void)
0x180026a05  mov     rcx, [r14+28h]
0x180026a09  mov     rax, [rcx]
0x180026a0c  mov     rax, [rax+10h]
0x180026a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a15  xor     edi, edi
0x180026a17  jmp     short loc_180026A1C
0x180026a19  mov     edi, r12d
0x180026a1c  lea     rcx, [rbp+var_28]
0x180026a20  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180026a25  mov     eax, edi
0x180026a27  mov     rcx, [rbp+var_10]
0x180026a2b  xor     rcx, rsp; StackCookie
0x180026a2e  call    __security_check_cookie
0x180026a33  mov     rbx, [rsp+60h+arg_10]
0x180026a3b  add     rsp, 60h
0x180026a3f  pop     r15
0x180026a41  pop     r14
0x180026a43  pop     r13
0x180026a45  pop     r12
0x180026a47  pop     rdi
0x180026a48  pop     rsi
0x180026a49  pop     rbp
0x180026a4a  retn
```
