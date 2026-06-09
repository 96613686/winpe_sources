# Session::ReadSync(SNI_Packet * *,int)

- ea: `0x10041ea90`
- end: `0x10041f27b`
- name: `?ReadSync@Session@@UEAAKPEAPEAVSNI_Packet@@H@Z`
- size: `2027`
- prototype: `unsigned int __fastcall(Session *__hidden this, struct SNI_Packet **, int)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x10041847c`
- `0x10041cbf8`
- `0x10041cfb0`
- `0x10041d628`
- `0x10041ea90`
- `0x100420258`
- `0x100420468`
- `0x10042059c`
- `0x10043a7c4`
- `0x10043a930`
- `0x10043baac`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x10041eb46`
- `KERNEL32!GetTickCount` at `0x10041ebb2`
- `KERNEL32!GetTickCount` at `0x10041ef55`
- `KERNEL32!GetTickCount` at `0x10041eb46`
- `KERNEL32!GetTickCount` at `0x10041ebb2`
- `KERNEL32!GetTickCount` at `0x10041ef55`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Session::ReadSync(Session *this, struct SNI_Packet **a2, signed int a3)
{
  SNI_Packet **v4; // r15
  unsigned int v6; // ebx
  char v7; // si
  unsigned int v8; // r12d
  DWORD TickCount; // esi
  _QWORD *v10; // r14
  signed int v11; // ecx
  __int64 v12; // r9
  unsigned int v13; // r15d
  __int64 v14; // rcx
  unsigned int v15; // eax
  char v16; // si
  __int64 v17; // r9
  bool v18; // zf
  Smux *v19; // rsi
  __int64 v20; // r13
  SNI_Packet **v21; // r14
  __int64 v22; // rcx
  void (*v23)(void); // rax
  char v24; // cl
  struct SNI_Packet **v25; // r15
  int v26; // ecx
  __int64 v27; // r8
  __int64 v28; // r14
  wchar_t *v29; // r8
  __int64 v30; // rdx
  __int64 v31; // rsi
  _QWORD v33[2]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v34; // [rsp+50h] [rbp-29h] BYREF
  int v35; // [rsp+58h] [rbp-21h]
  __int64 v36; // [rsp+60h] [rbp-19h]
  int v37; // [rsp+68h] [rbp-11h]
  Smux *v38; // [rsp+70h] [rbp-9h]
  Session *v39; // [rsp+78h] [rbp-1h]
  char v40; // [rsp+80h] [rbp+7h]
  DWORD v41; // [rsp+E0h] [rbp+67h]
  char v43; // [rsp+F0h] [rbp+77h]
  signed int v44; // [rsp+F8h] [rbp+7Fh]

  v33[1] = -2;
  v4 = a2;
  v33[0] = -1;
  v6 = 0;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E78A8[0] )
    bidScopeEnterW(v33, off_1005E78A8[0], *((unsigned int *)this + 11));
  v44 = a3;
  v41 = 0;
  if ( *v4 )
  {
    SNIPacketRelease(*v4);
    *v4 = 0;
  }
  v7 = *((_BYTE *)this + 161);
  if ( v7 || *((_BYTE *)this + 163) || *((_BYTE *)this + 164) )
  {
    v13 = -1;
    if ( (bidGblFlags & 2) != 0 && off_1005E4988[0] )
    {
      SniErrorIdFromStringId(50119 - (v7 != 0));
      bidTraceW(0, 1521664, off_1005E4988[0], 2);
    }
    SNISetLastError(2, 0xFFFFFFFFLL, 50119 - (unsigned int)(v7 != 0));
  }
  else
  {
    v8 = -1;
    if ( a3 == -1 )
    {
      TickCount = 0;
    }
    else
    {
      TickCount = GetTickCount();
      v41 = TickCount;
    }
    v10 = (_QWORD *)((char *)this + 136);
    if ( !*((_QWORD *)this + 17) )
    {
      while ( !Smux::TryBecomeWorker(*((Smux **)this + 6), this, 0) )
      {
        v34 = *((_QWORD *)this + 7);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v34 + 16) + 32LL) + 8LL))(*(_QWORD *)(v34 + 16) + 32LL);
        v35 = 1;
        if ( *v10 )
        {
          v17 = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)this + 6) + 124LL));
          if ( (bidGblFlags & 0x20002) == 0x20002 && `Smux::DecrementWorkerAccessCounter'::`10'::_bidPtrSA_030_109[0] )
            bidTraceW(0, 111616, `Smux::DecrementWorkerAccessCounter'::`10'::_bidPtrSA_030_109[0], v17);
          *a2 = (struct SNI_Packet *)DynamicQueue::DeQueue((Session *)((char *)this + 136));
          v13 = Session::PostReceiveFlowControl(this, a2);
          v18 = v13 == 0;
          v14 = *(_QWORD *)(v34 + 16);
          goto LABEL_48;
        }
        if ( a3 == -1 )
        {
          v11 = v44;
        }
        else
        {
          v11 = TickCount + a3 - GetTickCount();
          v44 = v11;
          if ( v11 < 0 )
          {
            v12 = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)this + 6) + 124LL));
            if ( (bidGblFlags & 0x20002) == 0x20002 && `Smux::DecrementWorkerAccessCounter'::`10'::_bidPtrSA_030_109[0] )
              bidTraceW(0, 111616, `Smux::DecrementWorkerAccessCounter'::`10'::_bidPtrSA_030_109[0], v12);
            v13 = 258;
            if ( (bidGblFlags & 2) != 0 && off_1005E49A8[0] )
            {
              SniErrorIdFromStringId(0xC3BFu);
              bidTraceW(0, 1686528, off_1005E49A8[0], 2);
            }
            SNISetLastError(2, 258, 50111);
            goto LABEL_24;
          }
        }
        *((_BYTE *)this + 201) = 1;
        v15 = CAutoSNICritSec::LeaveAndWait((CAutoSNICritSec *)&v34, (Session *)((char *)this + 184), v11);
        v13 = v15;
        if ( v15 )
        {
          Session::HandleWaitError(this, v15);
          goto LABEL_41;
        }
        v16 = *((_BYTE *)this + 161);
        if ( v16 || *((_BYTE *)this + 163) || *((_BYTE *)this + 164) )
        {
          if ( !*v10 )
            Smux::WakeUpNextWorker(*((Smux **)this + 6), 0, 0);
          v13 = -1;
          if ( (bidGblFlags & 2) != 0 && off_1005E49B0[0] )
          {
            SniErrorIdFromStringId(50119 - (v16 != 0));
            bidTraceW(0, 1729536, off_1005E49B0[0], 2);
          }
          SNISetLastError(2, 0xFFFFFFFFLL, 50119 - (unsigned int)(v16 != 0));
LABEL_41:
          if ( v35 )
          {
LABEL_24:
            v14 = *(_QWORD *)(v34 + 16);
            goto LABEL_25;
          }
          goto LABEL_98;
        }
        if ( v35 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v34 + 16) + 32LL) + 24LL))(*(_QWORD *)(v34 + 16) + 32LL);
        if ( *v10 )
        {
          v4 = a2;
          goto LABEL_93;
        }
        TickCount = v41;
      }
      v19 = (Smux *)*((_QWORD *)this + 6);
      v38 = v19;
      v39 = this;
      v40 = 0;
      if ( *v10 )
      {
        if ( v19 )
        {
          Smux::WakeUpNextWorker(v19, this, 0);
          v38 = 0;
        }
        v20 = *((_QWORD *)this + 7);
        v36 = v20;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v20 + 16) + 32LL) + 8LL))(*(_QWORD *)(v20 + 16) + 32LL);
        v37 = 1;
        v21 = a2;
        *a2 = (struct SNI_Packet *)DynamicQueue::DeQueue((Session *)((char *)this + 136));
        v13 = Session::PostReceiveFlowControl(this, a2);
        v22 = *(_QWORD *)(v20 + 16) + 32LL;
        v23 = *(void (**)(void))(*(_QWORD *)v22 + 24LL);
        if ( v13 )
        {
          ((void (__fastcall *)(__int64))v23)(v22);
          goto LABEL_99;
        }
LABEL_58:
        ((void (__fastcall *)(__int64))v23)(v22);
        goto LABEL_50;
      }
      v24 = *((_BYTE *)this + 161);
      v43 = v24;
      if ( v24 || *((_BYTE *)this + 163) || *((_BYTE *)this + 164) )
      {
        v13 = -1;
        if ( (bidGblFlags & 2) == 0 )
        {
LABEL_88:
          v27 = 50119 - (unsigned int)(v24 != 0);
LABEL_70:
          SNISetLastError(2, v8, v27);
LABEL_71:
          if ( v19 )
            Smux::WakeUpNextWorker(v19, this, 0);
          goto LABEL_98;
        }
        if ( off_1005E4990[0] )
        {
          SniErrorIdFromStringId(50119 - (v24 != 0));
          v29 = off_1005E4990[0];
          v30 = 1580032;
LABEL_86:
          bidTraceW(0, v30, v29, 2);
          v24 = v43;
        }
      }
      else
      {
        v25 = a2;
        while ( 1 )
        {
          if ( a3 == -1 )
          {
            v26 = v44;
          }
          else
          {
            v26 = v41 + a3 - GetTickCount();
            v44 = v26;
            if ( v26 < 0 )
            {
              v8 = 258;
              v13 = 258;
              if ( (bidGblFlags & 2) != 0 )
              {
                if ( off_1005E4998[0] )
                {
                  SniErrorIdFromStringId(0xC3BFu);
                  bidTraceW(0, 1592320, off_1005E4998[0], 2);
                }
                v19 = v38;
              }
              v27 = 50111;
              goto LABEL_70;
            }
          }
          v13 = Smux::Worker(*((Smux **)this + 6), v26, v25, *((_WORD *)this + 32), 1, 0, 0);
          if ( v13 )
            goto LABEL_71;
          v24 = *((_BYTE *)this + 161);
          v43 = v24;
          if ( v24 || *((_BYTE *)this + 163) || *((_BYTE *)this + 164) )
            break;
          v25 = a2;
          if ( *a2 )
          {
            if ( v19 )
            {
              Smux::WakeUpNextWorker(v19, this, 0);
              v19 = 0;
              v38 = 0;
            }
            v28 = *((_QWORD *)this + 7);
            v36 = v28;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v28 + 16) + 32LL) + 8LL))(*(_QWORD *)(v28 + 16) + 32LL);
            v37 = 1;
            v13 = Session::PostReceiveFlowControl(this, a2);
            v22 = *(_QWORD *)(v28 + 16) + 32LL;
            v23 = *(void (**)(void))(*(_QWORD *)v22 + 24LL);
            if ( v13 )
            {
              v23();
              goto LABEL_71;
            }
            goto LABEL_58;
          }
        }
        v13 = -1;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_88;
        if ( off_1005E49A0[0] )
        {
          SniErrorIdFromStringId(50119 - (v24 != 0));
          v29 = off_1005E49A0[0];
          v30 = 1618944;
          goto LABEL_86;
        }
      }
      v19 = v38;
      goto LABEL_88;
    }
LABEL_93:
    v31 = *((_QWORD *)this + 7);
    v36 = v31;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v31 + 16) + 32LL) + 8LL))(*(_QWORD *)(v31 + 16) + 32LL);
    v37 = 1;
    *v4 = (SNI_Packet *)DynamicQueue::DeQueue((Session *)((char *)this + 136));
    v13 = Session::PostReceiveFlowControl(this, v4);
    v14 = *(_QWORD *)(v31 + 16);
    v18 = v13 == 0;
LABEL_48:
    if ( v18 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(v14 + 32) + 24LL))(v14 + 32);
LABEL_50:
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E49B8[0] )
        bidTraceW(0, 1735680, off_1005E49B8[0], 0);
      goto LABEL_105;
    }
LABEL_25:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v14 + 32) + 24LL))(v14 + 32);
  }
LABEL_98:
  v21 = a2;
LABEL_99:
  if ( *v21 )
  {
    SNIPacketRelease(*v21);
    *v21 = 0;
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E49C0[0] )
    bidTraceW(0, 1747968, off_1005E49C0[0], v13);
  v6 = v13;
LABEL_105:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v33);
  return v6;
}

```

## disassembly

```asm
0x10041ea90  mov     [rsp-8+arg_8], rdx
0x10041ea95  push    rbp
0x10041ea96  push    rbx
0x10041ea97  push    rsi
0x10041ea98  push    rdi
0x10041ea99  push    r12
0x10041ea9b  push    r13
0x10041ea9d  push    r14
0x10041ea9f  push    r15
0x10041eaa1  lea     rbp, [rsp-1Fh]
0x10041eaa6  sub     rsp, 98h
0x10041eaad  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFEh
0x10041eab5  mov     r13d, r8d
0x10041eab8  mov     r15, rdx
0x10041eabb  mov     rdi, rcx
0x10041eabe  or      [rbp+57h+var_90], 0FFFFFFFFFFFFFFFFh
0x10041eac3  mov     eax, cs:_bidGblFlags
0x10041eac9  mov     ecx, 20004h
0x10041eace  and     eax, ecx
0x10041ead0  xor     ebx, ebx
0x10041ead2  cmp     eax, ecx
0x10041ead4  jnz     short loc_10041EAFE
0x10041ead6  mov     rax, cs:off_1005E78A8; "<Session::ReadSync|API|SNI> %u#, ppNewP"...
0x10041eadd  test    rax, rax
0x10041eae0  jz      short loc_10041EAFE
0x10041eae2  mov     dword ptr [rsp+0D0h+var_B0], r8d
0x10041eae7  mov     r9, rdx
0x10041eaea  mov     r8d, [rdi+2Ch]
0x10041eaee  mov     rdx, cs:off_1005E78A8; "<Session::ReadSync|API|SNI> %u#, ppNewP"...
0x10041eaf5  lea     rcx, [rbp+57h+var_90]
0x10041eaf9  call    _bidScopeEnterW
0x10041eafe  mov     [rbp+57h+arg_18], r13d
0x10041eb02  mov     [rbp+57h+arg_0], ebx
0x10041eb05  cmp     [r15], rbx
0x10041eb08  jz      short loc_10041EB15
0x10041eb0a  mov     rcx, [r15]; this
0x10041eb0d  call    SNIPacketRelease
0x10041eb12  mov     [r15], rbx
0x10041eb15  mov     sil, [rdi+0A1h]
0x10041eb1c  test    sil, sil
0x10041eb1f  jnz     loc_10041F1A7
0x10041eb25  cmp     [rdi+0A3h], bl
0x10041eb2b  jnz     loc_10041F1A7
0x10041eb31  cmp     [rdi+0A4h], bl
0x10041eb37  jnz     loc_10041F1A7
0x10041eb3d  or      r12d, 0FFFFFFFFh
0x10041eb41  cmp     r13d, r12d
0x10041eb44  jz      short loc_10041EB53
0x10041eb46  call    cs:__imp_GetTickCount
0x10041eb4c  mov     esi, eax
0x10041eb4e  mov     [rbp+57h+arg_0], eax
0x10041eb51  jmp     short loc_10041EB55
0x10041eb53  mov     esi, ebx
0x10041eb55  lea     r14, [rdi+88h]
0x10041eb5c  cmp     [r14], rbx
0x10041eb5f  jnz     loc_10041F15F
0x10041eb65  xor     r8d, r8d; bool
0x10041eb68  mov     rdx, rdi; struct Session *
0x10041eb6b  mov     rcx, [rdi+30h]; this
0x10041eb6f  call    ?TryBecomeWorker@Smux@@QEAA_NPEAVSession@@_N@Z; Smux::TryBecomeWorker(Session *,bool)
0x10041eb74  test    al, al
0x10041eb76  jnz     loc_10041EE4F
0x10041eb7c  mov     rax, [rdi+38h]
0x10041eb80  mov     [rbp+57h+var_80], rax
0x10041eb84  mov     rcx, [rax+10h]
0x10041eb88  add     rcx, 20h ; ' '
0x10041eb8c  mov     rax, [rcx]
0x10041eb8f  mov     rax, [rax+8]
0x10041eb93  call    cs:__guard_dispatch_icall_fptr
0x10041eb99  mov     [rbp+57h+var_78], 1
0x10041eba0  cmp     [r14], rbx
0x10041eba3  jnz     loc_10041ED8E
0x10041eba9  cmp     r13d, r12d
0x10041ebac  jz      loc_10041EC87
0x10041ebb2  call    cs:__imp_GetTickCount
0x10041ebb8  lea     ecx, [rsi+r13]
0x10041ebbc  sub     ecx, eax
0x10041ebbe  mov     [rbp+57h+arg_18], ecx
0x10041ebc1  jns     loc_10041EC8A
0x10041ebc7  mov     rax, [rdi+30h]
0x10041ebcb  or      r9d, 0FFFFFFFFh
0x10041ebcf  lock xadd [rax+7Ch], r9d
0x10041ebd5  dec     r9d
0x10041ebd8  mov     eax, cs:_bidGblFlags
0x10041ebde  and     eax, 20002h
0x10041ebe3  cmp     eax, 20002h
0x10041ebe8  jnz     short loc_10041EC09
0x10041ebea  mov     rax, cs:?_bidPtrSA_030_109@?9??DecrementWorkerAccessCounter@Smux@@QEAAJ_N@Z@4REBGEB; ushort const * const `Smux::DecrementWorkerAccessCounter(bool)'::`10'::_bidPtrSA_030_109
0x10041ebf1  test    rax, rax
0x10041ebf4  jz      short loc_10041EC09
0x10041ebf6  mov     r8, cs:?_bidPtrSA_030_109@?9??DecrementWorkerAccessCounter@Smux@@QEAAJ_N@Z@4REBGEB; ushort const * const `Smux::DecrementWorkerAccessCounter(bool)'::`10'::_bidPtrSA_030_109
0x10041ebfd  mov     edx, 1B400h
0x10041ec02  xor     ecx, ecx
0x10041ec04  call    _bidTraceW
0x10041ec09  mov     r12d, 102h
0x10041ec0f  mov     r15d, r12d
0x10041ec12  mov     r13d, 0C3BFh
0x10041ec18  mov     r14d, 2
0x10041ec1e  test    byte ptr cs:_bidGblFlags, r14b
0x10041ec25  jz      short loc_10041EC5A
0x10041ec27  mov     rax, cs:off_1005E49A8; "<Session::ReadSync|ERR|SNI> ProviderNum"...
0x10041ec2e  test    rax, rax
0x10041ec31  jz      short loc_10041EC5A
0x10041ec33  mov     ecx, r13d; unsigned int
0x10041ec36  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x10041ec3b  mov     dword ptr [rsp+0D0h+var_A8], r12d
0x10041ec40  mov     dword ptr [rsp+0D0h+var_B0], eax
0x10041ec44  mov     r9d, r14d
0x10041ec47  mov     r8, cs:off_1005E49A8; "<Session::ReadSync|ERR|SNI> ProviderNum"...
0x10041ec4e  mov     edx, 19BC00h
0x10041ec53  xor     ecx, ecx
0x10041ec55  call    _bidTraceW
0x10041ec5a  mov     r8d, r13d
0x10041ec5d  mov     edx, r12d
0x10041ec60  mov     ecx, r14d
0x10041ec63  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10041ec68  nop
0x10041ec69  mov     rax, [rbp+57h+var_80]
0x10041ec6d  mov     rcx, [rax+10h]
0x10041ec71  add     rcx, 20h ; ' '
0x10041ec75  mov     rax, [rcx]
0x10041ec78  mov     rax, [rax+18h]
0x10041ec7c  call    cs:__guard_dispatch_icall_fptr
0x10041ec82  jmp     loc_10041F211
0x10041ec87  mov     ecx, [rbp+57h+arg_18]
0x10041ec8a  mov     byte ptr [rdi+0C9h], 1
0x10041ec91  lea     rdx, [rdi+0B8h]; struct EventHandle *
0x10041ec98  mov     r8d, ecx; unsigned int
0x10041ec9b  lea     rcx, [rbp+57h+var_80]; this
0x10041ec9f  call    ?LeaveAndWait@CAutoSNICritSec@@QEAAKPEAVEventHandle@@K@Z; CAutoSNICritSec::LeaveAndWait(EventHandle *,ulong)
0x10041eca4  mov     r15d, eax
0x10041eca7  test    eax, eax
0x10041eca9  jnz     loc_10041ED82
0x10041ecaf  mov     sil, [rdi+0A1h]
0x10041ecb6  test    sil, sil
0x10041ecb9  jnz     short loc_10041ECFA
0x10041ecbb  cmp     [rdi+0A3h], bl
0x10041ecc1  jnz     short loc_10041ECFA
0x10041ecc3  cmp     [rdi+0A4h], bl
0x10041ecc9  jnz     short loc_10041ECFA
0x10041eccb  cmp     [rbp+57h+var_78], ebx
0x10041ecce  jz      short loc_10041ECE9
0x10041ecd0  mov     rax, [rbp+57h+var_80]
0x10041ecd4  mov     rcx, [rax+10h]
0x10041ecd8  add     rcx, 20h ; ' '
0x10041ecdc  mov     rax, [rcx]
0x10041ecdf  mov     rax, [rax+18h]
0x10041ece3  call    cs:__guard_dispatch_icall_fptr
0x10041ece9  cmp     [r14], rbx
0x10041ecec  jnz     loc_10041F15B
0x10041ecf2  mov     esi, [rbp+57h+arg_0]
0x10041ecf5  jmp     loc_10041EB65
0x10041ecfa  cmp     [r14], rbx
0x10041ecfd  jnz     short loc_10041ED0D
0x10041ecff  xor     r8d, r8d; bool
0x10041ed02  xor     edx, edx; struct Session *
0x10041ed04  mov     rcx, [rdi+30h]; this
0x10041ed08  call    ?WakeUpNextWorker@Smux@@QEAAXPEAVSession@@_N@Z; Smux::WakeUpNextWorker(Session *,bool)
0x10041ed0d  mov     r15d, r12d
0x10041ed10  mov     r13d, 0C3C7h
0x10041ed16  mov     r14d, 2
0x10041ed1c  test    byte ptr cs:_bidGblFlags, r14b
0x10041ed23  jz      short loc_10041ED5F
0x10041ed25  mov     rax, cs:off_1005E49B0; "<Session::ReadSync|ERR|SNI> ProviderNum"...
0x10041ed2c  test    rax, rax
0x10041ed2f  jz      short loc_10041ED5F
0x10041ed31  mov     al, sil
0x10041ed34  neg     al
0x10041ed36  sbb     ecx, ecx
0x10041ed38  add     ecx, r13d; unsigned int
0x10041ed3b  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x10041ed40  mov     dword ptr [rsp+0D0h+var_A8], r12d
0x10041ed45  mov     dword ptr [rsp+0D0h+var_B0], eax
0x10041ed49  mov     r9d, r14d
0x10041ed4c  mov     r8, cs:off_1005E49B0; "<Session::ReadSync|ERR|SNI> ProviderNum"...
0x10041ed53  mov     edx, 1A6400h
0x10041ed58  xor     ecx, ecx
0x10041ed5a  call    _bidTraceW
0x10041ed5f  neg     sil
0x10041ed62  sbb     r8d, r8d
0x10041ed65  add     r8d, r13d
0x10041ed68  mov     edx, r12d
0x10041ed6b  mov     ecx, r14d
0x10041ed6e  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10041ed73  nop
0x10041ed74  cmp     [rbp+57h+var_78], ebx
0x10041ed77  jz      loc_10041F211
0x10041ed7d  jmp     loc_10041EC69
0x10041ed82  mov     edx, eax; unsigned int
0x10041ed84  mov     rcx, rdi; this
0x10041ed87  call    ?HandleWaitError@Session@@AEAAXK@Z; Session::HandleWaitError(ulong)
0x10041ed8c  jmp     short loc_10041ED74
0x10041ed8e  mov     rax, [rdi+30h]
0x10041ed92  or      r9d, 0FFFFFFFFh
0x10041ed96  lock xadd [rax+7Ch], r9d
0x10041ed9c  dec     r9d
0x10041ed9f  mov     eax, cs:_bidGblFlags
0x10041eda5  and     eax, 20002h
0x10041edaa  cmp     eax, 20002h
0x10041edaf  jnz     short loc_10041EDD0
0x10041edb1  mov     rax, cs:?_bidPtrSA_030_109@?9??DecrementWorkerAccessCounter@Smux@@QEAAJ_N@Z@4REBGEB; ushort const * const `Smux::DecrementWorkerAccessCounter(bool)'::`10'::_bidPtrSA_030_109
0x10041edb8  test    rax, rax
0x10041edbb  jz      short loc_10041EDD0
0x10041edbd  mov     r8, cs:?_bidPtrSA_030_109@?9??DecrementWorkerAccessCounter@Smux@@QEAAJ_N@Z@4REBGEB; ushort const * const `Smux::DecrementWorkerAccessCounter(bool)'::`10'::_bidPtrSA_030_109
0x10041edc4  mov     edx, 1B400h
0x10041edc9  xor     ecx, ecx
0x10041edcb  call    _bidTraceW
0x10041edd0  mov     rcx, r14; this
0x10041edd3  call    ?DeQueue@DynamicQueue@@QEAAPEAXXZ; DynamicQueue::DeQueue(void)
0x10041edd8  mov     r15, [rbp+57h+arg_8]
0x10041eddc  mov     [r15], rax
0x10041eddf  mov     rdx, r15; struct SNI_Packet **
0x10041ede2  mov     rcx, rdi; this
0x10041ede5  call    ?PostReceiveFlowControl@Session@@AEAAKPEAPEAVSNI_Packet@@@Z; Session::PostReceiveFlowControl(SNI_Packet * *)
0x10041edea  mov     r15d, eax
0x10041eded  test    eax, eax
0x10041edef  mov     rax, [rbp+57h+var_80]
0x10041edf3  mov     rcx, [rax+10h]
0x10041edf7  jnz     loc_10041EC71
0x10041edfd  add     rcx, 20h ; ' '
0x10041ee01  mov     rax, [rcx]
0x10041ee04  mov     rax, [rax+18h]
0x10041ee08  call    cs:__guard_dispatch_icall_fptr
0x10041ee0e  mov     eax, cs:_bidGblFlags
0x10041ee14  and     eax, 20002h
0x10041ee19  cmp     eax, 20002h
0x10041ee1e  jnz     loc_10041F25C
0x10041ee24  mov     rax, cs:off_1005E49B8; "<Session::ReadSync|RET|SNI> %d{WINERR}"...
0x10041ee2b  test    rax, rax
0x10041ee2e  jz      loc_10041F25C
0x10041ee34  xor     r9d, r9d
0x10041ee37  mov     r8, cs:off_1005E49B8; "<Session::ReadSync|RET|SNI> %d{WINERR}"...
0x10041ee3e  mov     edx, 1A7C00h
0x10041ee43  xor     ecx, ecx
0x10041ee45  call    _bidTraceW
0x10041ee4a  jmp     loc_10041F25C
0x10041ee4f  mov     rsi, [rdi+30h]
0x10041ee53  mov     [rbp+57h+var_60], rsi
0x10041ee57  mov     [rbp+57h+var_58], rdi
0x10041ee5b  mov     [rbp+57h+var_50], bl
0x10041ee5e  cmp     [r14], rbx
0x10041ee61  jz      loc_10041EF1B
0x10041ee67  test    rsi, rsi
0x10041ee6a  jz      short loc_10041EE81
0x10041ee6c  xor     r8d, r8d; bool
0x10041ee6f  mov     rdx, rdi; struct Session *
0x10041ee72  mov     rcx, rsi; this
0x10041ee75  call    ?WakeUpNextWorker@Smux@@QEAAXPEAVSession@@_N@Z; Smux::WakeUpNextWorker(Session *,bool)
0x10041ee7a  mov     rsi, rbx
0x10041ee7d  mov     [rbp+57h+var_60], rbx
0x10041ee81  mov     r13, [rdi+38h]
0x10041ee85  mov     [rbp+57h+var_70], r13
0x10041ee89  mov     rcx, [r13+10h]
0x10041ee8d  add     rcx, 20h ; ' '
0x10041ee91  mov     rax, [rcx]
0x10041ee94  mov     rax, [rax+8]
0x10041ee98  call    cs:__guard_dispatch_icall_fptr
0x10041ee9e  mov     [rbp+57h+var_68], 1
0x10041eea5  mov     rcx, r14; this
0x10041eea8  call    ?DeQueue@DynamicQueue@@QEAAPEAXXZ; DynamicQueue::DeQueue(void)
0x10041eead  mov     r14, [rbp+57h+arg_8]
0x10041eeb1  mov     [r14], rax
0x10041eeb4  mov     rdx, r14; struct SNI_Packet **
0x10041eeb7  mov     rcx, rdi; this
0x10041eeba  call    ?PostReceiveFlowControl@Session@@AEAAKPEAPEAVSNI_Packet@@@Z; Session::PostReceiveFlowControl(SNI_Packet * *)
0x10041eebf  mov     r15d, eax
0x10041eec2  mov     rcx, [r13+10h]
0x10041eec6  add     rcx, 20h ; ' '
0x10041eeca  test    eax, eax
0x10041eecc  mov     rax, [rcx]
0x10041eecf  mov     rax, [rax+18h]
0x10041eed3  jz      short loc_10041EEF8
0x10041eed5  call    cs:__guard_dispatch_icall_fptr
0x10041eedb  nop
0x10041eedc  test    rsi, rsi
0x10041eedf  jz      loc_10041F215
0x10041eee5  xor     r8d, r8d; bool
0x10041eee8  mov     rdx, rdi; struct Session *
0x10041eeeb  mov     rcx, rsi; this
0x10041eeee  call    ?WakeUpNextWorker@Smux@@QEAAXPEAVSession@@_N@Z; Smux::WakeUpNextWorker(Session *,bool)
0x10041eef3  jmp     loc_10041F215
0x10041eef8  call    cs:__guard_dispatch_icall_fptr
0x10041eefe  nop
0x10041eeff  test    rsi, rsi
0x10041ef02  jz      loc_10041EE0E
0x10041ef08  xor     r8d, r8d; bool
0x10041ef0b  mov     rdx, rdi; struct Session *
0x10041ef0e  mov     rcx, rsi; this
0x10041ef11  call    ?WakeUpNextWorker@Smux@@QEAAXPEAVSession@@_N@Z; Smux::WakeUpNextWorker(Session *,bool)
0x10041ef16  jmp     loc_10041EE0E
0x10041ef1b  mov     cl, [rdi+0A1h]
0x10041ef21  mov     [rbp+57h+arg_10], cl
0x10041ef24  test    cl, cl
0x10041ef26  jnz     loc_10041F11B
0x10041ef2c  cmp     [rdi+0A3h], bl
0x10041ef32  jnz     loc_10041F11B
0x10041ef38  cmp     [rdi+0A4h], bl
0x10041ef3e  jnz     loc_10041F11B
0x10041ef44  mov     r15, [rbp+57h+arg_8]
0x10041ef48  mov     r14d, [rbp+57h+arg_0]
  ... truncated ...
```
