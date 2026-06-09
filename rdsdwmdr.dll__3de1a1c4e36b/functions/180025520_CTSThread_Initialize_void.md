# CTSThread::Initialize(void)

- ea: `0x180025520`
- end: `0x18002581a`
- name: `?Initialize@CTSThread@@UEAAJXZ`
- size: `762`
- prototype: `__int64 __fastcall(CTSThread *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180021cf0`

## callees

- `0x18000160c`
- `0x180014044`
- `0x18001d114`
- `0x18001f03c`
- `0x180023c08`
- `0x180023d54`
- `0x180023ea0`
- `0x180025520`
- `0x1800290fc`
- `0x18002a1c4`

## string_xrefs

- `0x180025664`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x18002558c`: `Failed to create thread signal event`
- `0x18002571e`: `CTSSyncWaitResult::CreateInstancePool failed!`
- `0x180025771`: `CTSMsg::CreateInstancePool failed!`
- `0x1800257b8`: `CTSBufferResult::CreateInstancePool failed!`
- `0x1800257ff`: `Failed to create ITSThreadInternal`

## pseudocode

```c
__int64 __fastcall CTSThread::Initialize(CTSThread *this)
{
  __int64 v2; // rdx
  int Instance; // ebx
  __int64 v4; // r8
  __int64 v5; // r9
  int ActivityIdPrefix; // eax
  int v7; // edx
  const char *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  int v32; // [rsp+28h] [rbp-50h]
  const char *v33; // [rsp+50h] [rbp-28h] BYREF
  int v34; // [rsp+80h] [rbp+8h] BYREF
  int v35; // [rsp+88h] [rbp+10h] BYREF
  const char *v36; // [rsp+90h] [rbp+18h] BYREF
  const char *v37; // [rsp+98h] [rbp+20h] BYREF

  *((_QWORD *)this + 83) = 0;
  *((_QWORD *)this + 84) = -1;
  Instance = PAL_System_CondAlloc(1);
  if ( Instance >= 0 )
  {
    *((_QWORD *)this + 75) = 0;
    *((_QWORD *)this + 24) = (char *)this + 208;
    v9 = 0;
    *((_DWORD *)this + 50) = 8;
    *((_QWORD *)this + 26) = 0;
    do
    {
      v10 = v9 + 2 * v9 + 1;
      ++v9;
      v11 = *((_QWORD *)this + 24) + 8 * v10;
      *(_QWORD *)(v11 + 8) = *((_QWORD *)this + 23);
      *((_QWORD *)this + 23) = v11;
    }
    while ( v9 != 16 );
    *((_DWORD *)this + 32) = -1;
    if ( (unsigned int)CTSCriticalSection::Initialize((CTSThread *)((char *)this + 88)) )
    {
      Instance = CTSObjectPool<CTSSyncWaitResult>::CreateInstance(v13, v12, (_QWORD *)this + 80);
      if ( Instance >= 0 )
      {
        Instance = CTSObjectPool<CTSMsg>::CreateInstance(v17, v16, (_QWORD *)this + 81);
        if ( Instance >= 0 )
        {
          Instance = CTSObjectPool<CTSBufferResult>::CreateInstance(v21, v20, (_QWORD *)this + 82);
          if ( Instance >= 0 )
          {
            Instance = CTSThreadInternal_CreateInstance(v25, v24, (char *)this + 720);
            if ( Instance >= 0 )
            {
              *((_DWORD *)this + 5) |= 2u;
              return 0;
            }
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v28, v29, v30);
              v7 = 22;
              v8 = "Failed to create ITSThreadInternal";
              goto LABEL_6;
            }
          }
          else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v24, v26, v27);
            v7 = 21;
            v8 = "CTSBufferResult::CreateInstancePool failed!";
            goto LABEL_6;
          }
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v20, v22, v23);
          v7 = 20;
          v8 = "CTSMsg::CreateInstancePool failed!";
          goto LABEL_6;
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v16, v18, v19);
        v7 = 19;
        v8 = "CTSSyncWaitResult::CreateInstancePool failed!";
        goto LABEL_6;
      }
    }
    else
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v34 = 199;
        v36 = "Initialize";
        v35 = -2147467259;
        v37 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
        v33 = "Fail to init lock queue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v13,
          (__int64)byte_18003FE03,
          v14,
          v15,
          (const unsigned __int16 **)&v33,
          (__int64)&v35,
          (const unsigned __int16 **)&v37,
          (__int64)&v34,
          (const unsigned __int16 **)&v36);
      }
      return (unsigned int)-2147024882;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v2, v4, v5);
    v7 = 17;
    v8 = "Failed to create thread signal event";
LABEL_6:
    v32 = Instance;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
      ActivityIdPrefix,
      (__int64)v8,
      v32);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180025520  push    rbx
0x180025522  push    rdi
0x180025523  sub     rsp, 68h
0x180025527  mov     rdi, rcx
0x18002552a  mov     qword ptr [rcx+298h], 0
0x180025535  lea     rdx, [rcx+2B0h]
0x18002553c  mov     qword ptr [rcx+2A0h], 0FFFFFFFFFFFFFFFFh
0x180025547  mov     ecx, 1; bManualReset
0x18002554c  call    PAL_System_CondAlloc
0x180025551  mov     ebx, eax
0x180025553  test    eax, eax
0x180025555  jns     short loc_1800255BB
0x180025557  mov     rcx, cs:WPP_GLOBAL_Control
0x18002555e  lea     rax, WPP_GLOBAL_Control
0x180025565  cmp     rcx, rax
0x180025568  jz      loc_180025811
0x18002556e  test    byte ptr [rcx+1Ch], 8
0x180025572  jz      loc_180025811
0x180025578  cmp     byte ptr [rcx+19h], 2
0x18002557c  jb      loc_180025811
0x180025582  call    RdpX_GetActivityIdPrefix
0x180025587  mov     edx, 11h
0x18002558c  lea     rcx, aFailedToCreate_1; "Failed to create thread signal event"
0x180025593  mov     dword ptr [rsp+78h+var_50], ebx
0x180025597  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x18002559e  mov     [rsp+78h+var_58], rcx
0x1800255a3  mov     r9d, eax
0x1800255a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800255ad  mov     rcx, [rcx+10h]
0x1800255b1  call    WPP_SF_DsD
0x1800255b6  jmp     loc_180025811
0x1800255bb  lea     rax, [rdi+0D0h]
0x1800255c2  mov     qword ptr [rdi+258h], 0
0x1800255cd  mov     [rdi+0C0h], rax
0x1800255d4  xor     r8d, r8d
0x1800255d7  mov     dword ptr [rdi+0C8h], 8
0x1800255e1  mov     qword ptr [rax], 0
0x1800255e8  mov     rax, [rdi+0C0h]
0x1800255ef  lea     rdx, ds:1[r8*2]
0x1800255f7  add     rdx, r8
0x1800255fa  inc     r8
0x1800255fd  lea     rdx, [rax+rdx*8]
0x180025601  mov     rax, [rdi+0B8h]
0x180025608  mov     [rdx+8], rax
0x18002560c  mov     [rdi+0B8h], rdx
0x180025613  cmp     r8, 10h
0x180025617  jnz     short loc_1800255E8
0x180025619  lea     rcx, [rdi+58h]; this
0x18002561d  mov     dword ptr [rdi+80h], 0FFFFFFFFh
0x180025627  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x18002562c  test    eax, eax
0x18002562e  jnz     loc_1800256D7
0x180025634  mov     eax, cs:dword_180044008
0x18002563a  cmp     eax, 2
0x18002563d  jbe     loc_1800256CD
0x180025643  lea     rax, aInitialize; "Initialize"
0x18002564a  mov     [rsp+78h+arg_0], 0C7h
0x180025655  mov     [rsp+78h+arg_10], rax
0x18002565d  lea     rdx, byte_18003FE03
0x180025664  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002566b  mov     [rsp+78h+arg_8], 80004005h
0x180025676  mov     [rsp+78h+arg_18], rax
0x18002567e  lea     rax, aFailToInitLock; "Fail to init lock queue"
0x180025685  mov     [rsp+78h+var_28], rax
0x18002568a  lea     rax, [rsp+78h+arg_10]
0x180025692  mov     [rsp+78h+var_38], rax
0x180025697  lea     rax, [rsp+78h+arg_0]
0x18002569f  mov     [rsp+78h+var_40], rax
0x1800256a4  lea     rax, [rsp+78h+arg_18]
0x1800256ac  mov     [rsp+78h+var_48], rax
0x1800256b1  lea     rax, [rsp+78h+arg_8]
0x1800256b9  mov     [rsp+78h+var_50], rax
0x1800256be  lea     rax, [rsp+78h+var_28]
0x1800256c3  mov     [rsp+78h+var_58], rax
0x1800256c8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800256cd  mov     ebx, 8007000Eh
0x1800256d2  jmp     loc_180025811
0x1800256d7  lea     r8, [rdi+280h]
0x1800256de  call    ?CreateInstance@?$CTSObjectPool@VCTSSyncWaitResult@@@@SAJIIPEAPEAV1@H@Z; CTSObjectPool<CTSSyncWaitResult>::CreateInstance(uint,uint,CTSObjectPool<CTSSyncWaitResult> * *,int)
0x1800256e3  mov     ebx, eax
0x1800256e5  test    eax, eax
0x1800256e7  jns     short loc_18002572A
0x1800256e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800256f0  lea     rax, WPP_GLOBAL_Control
0x1800256f7  cmp     rcx, rax
0x1800256fa  jz      loc_180025811
0x180025700  test    byte ptr [rcx+1Ch], 8
0x180025704  jz      loc_180025811
0x18002570a  cmp     byte ptr [rcx+19h], 2
0x18002570e  jb      loc_180025811
0x180025714  call    RdpX_GetActivityIdPrefix
0x180025719  mov     edx, 13h
0x18002571e  lea     rcx, aCtssyncwaitres_0; "CTSSyncWaitResult::CreateInstancePool f"...
0x180025725  jmp     loc_180025593
0x18002572a  lea     r8, [rdi+288h]
0x180025731  call    ?CreateInstance@?$CTSObjectPool@VCTSMsg@@@@SAJIIPEAPEAV1@H@Z; CTSObjectPool<CTSMsg>::CreateInstance(uint,uint,CTSObjectPool<CTSMsg> * *,int)
0x180025736  mov     ebx, eax
0x180025738  test    eax, eax
0x18002573a  jns     short loc_18002577D
0x18002573c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025743  lea     rax, WPP_GLOBAL_Control
0x18002574a  cmp     rcx, rax
0x18002574d  jz      loc_180025811
0x180025753  test    byte ptr [rcx+1Ch], 8
0x180025757  jz      loc_180025811
0x18002575d  cmp     byte ptr [rcx+19h], 2
0x180025761  jb      loc_180025811
0x180025767  call    RdpX_GetActivityIdPrefix
0x18002576c  mov     edx, 14h
0x180025771  lea     rcx, aCtsmsgCreatein; "CTSMsg::CreateInstancePool failed!"
0x180025778  jmp     loc_180025593
0x18002577d  lea     r8, [rdi+290h]
0x180025784  call    ?CreateInstance@?$CTSObjectPool@VCTSBufferResult@@@@SAJIIPEAPEAV1@H@Z; CTSObjectPool<CTSBufferResult>::CreateInstance(uint,uint,CTSObjectPool<CTSBufferResult> * *,int)
0x180025789  mov     ebx, eax
0x18002578b  test    eax, eax
0x18002578d  jns     short loc_1800257C4
0x18002578f  mov     rcx, cs:WPP_GLOBAL_Control
0x180025796  lea     rax, WPP_GLOBAL_Control
0x18002579d  cmp     rcx, rax
0x1800257a0  jz      short loc_180025811
0x1800257a2  test    byte ptr [rcx+1Ch], 8
0x1800257a6  jz      short loc_180025811
0x1800257a8  cmp     byte ptr [rcx+19h], 2
0x1800257ac  jb      short loc_180025811
0x1800257ae  call    RdpX_GetActivityIdPrefix
0x1800257b3  mov     edx, 15h
0x1800257b8  lea     rcx, aCtsbufferresul_1; "CTSBufferResult::CreateInstancePool fai"...
0x1800257bf  jmp     loc_180025593
0x1800257c4  lea     r8, [rdi+2D0h]
0x1800257cb  call    CTSThreadInternal_CreateInstance
0x1800257d0  mov     ebx, eax
0x1800257d2  test    eax, eax
0x1800257d4  jns     short loc_18002580B
0x1800257d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800257dd  lea     rax, WPP_GLOBAL_Control
0x1800257e4  cmp     rcx, rax
0x1800257e7  jz      short loc_180025811
0x1800257e9  test    byte ptr [rcx+1Ch], 8
0x1800257ed  jz      short loc_180025811
0x1800257ef  cmp     byte ptr [rcx+19h], 2
0x1800257f3  jb      short loc_180025811
0x1800257f5  call    RdpX_GetActivityIdPrefix
0x1800257fa  mov     edx, 16h
0x1800257ff  lea     rcx, aFailedToCreate_15; "Failed to create ITSThreadInternal"
0x180025806  jmp     loc_180025593
0x18002580b  or      dword ptr [rdi+14h], 2
0x18002580f  xor     ebx, ebx
0x180025811  mov     eax, ebx
0x180025813  add     rsp, 68h
0x180025817  pop     rdi
0x180025818  pop     rbx
0x180025819  retn
```
