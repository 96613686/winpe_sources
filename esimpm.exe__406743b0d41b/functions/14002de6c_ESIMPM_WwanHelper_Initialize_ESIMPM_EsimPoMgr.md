# ESIMPM::WwanHelper::Initialize(ESIMPM::EsimPoMgr *)

- ea: `0x14002de6c`
- end: `0x14002dfa6`
- name: `?Initialize@WwanHelper@ESIMPM@@QEAAKPEAVEsimPoMgr@2@@Z`
- size: `314`
- prototype: `unsigned int __fastcall(ESIMPM::WwanHelper *__hidden this, struct ESIMPM::EsimPoMgr *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140024d88`

## callees

- `0x140001308`
- `0x140015218`
- `0x14002dd08`
- `0x14002de6c`
- `0x14002dfac`

## import_xrefs

- `wwapi!WwanRegisterNotification` at `0x14002df0e`
- `wwapi!WwanRegisterNotification` at `0x14002df0e`
- `wwapi!WwanOpenHandle` at `0x14002de91`
- `wwapi!WwanOpenHandle` at `0x14002de91`
- `wwapi!WwanCloseHandle` at `0x14002df81`
- `wwapi!WwanCloseHandle` at `0x14002df81`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ESIMPM::WwanHelper::Initialize(ESIMPM::WwanHelper *this, struct ESIMPM::EsimPoMgr *a2)
{
  unsigned int v3; // eax
  __int64 v4; // r8
  __int64 v5; // r9
  unsigned int v6; // edi
  unsigned int v8; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int Interface; // eax
  unsigned int v12; // [rsp+60h] [rbp+20h] BYREF
  int v13; // [rsp+68h] [rbp+28h] BYREF
  int v14; // [rsp+6Ch] [rbp+2Ch]
  int v15; // [rsp+70h] [rbp+30h] BYREF
  const char *v16; // [rsp+78h] [rbp+38h] BYREF

  v14 = HIDWORD(a2);
  v13 = 0;
  v3 = WwanOpenHandle(1, 0, &v13, this);
  v6 = v3;
  if ( v3 )
  {
    if ( (unsigned int)dword_140075078 > 2 )
    {
      v16 = "ESIMPM::WwanHelper::Initialize";
      v12 = v3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)"ESIMPM::WwanHelper::Initialize",
        (__int64)byte_14006C56B,
        v4,
        v5,
        (__int64)&v12,
        (const unsigned __int16 **)&v16);
    }
    return v6;
  }
  v15 = 0;
  v8 = WwanRegisterNotification(*(_QWORD *)this, 6, ESIMPM::WwanHelper::s_WwapiNotification, this, 0, &v15, this, 1);
  v6 = v8;
  if ( v8 )
  {
    if ( (unsigned int)dword_140075078 > 2 )
    {
      v16 = "ESIMPM::WwanHelper::Initialize";
      v12 = v8;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)"ESIMPM::WwanHelper::Initialize",
        (__int64)byte_14006C52D,
        v9,
        v10,
        (__int64)&v12,
        (const unsigned __int16 **)&v16);
    }
    goto LABEL_12;
  }
  Interface = ESIMPM::WwanHelper::GetInterface(this, (ESIMPM::WwanHelper *)((char *)this + 8));
  if ( Interface )
  {
LABEL_11:
    v6 = Interface;
LABEL_12:
    WwanCloseHandle(*(_QWORD *)this, 0);
    *(_QWORD *)this = 0;
    return v6;
  }
  if ( *((_BYTE *)this + 48) )
  {
    Interface = ESIMPM::WwanHelper::QueryModemInfo(this, (ESIMPM::WwanHelper *)((char *)this + 8));
    if ( Interface )
      goto LABEL_11;
    ESIMPM::MessageDispatcher::_EnQueueDevicePresenceEvent((ESIMPM::WwanHelper *)((char *)this + 8));
  }
  return 0;
}

```

## disassembly

```asm
0x14002de6c  mov     [rsp-18h+arg_8], rdx
0x14002de71  push    rbp
0x14002de72  push    rbx
0x14002de73  push    rdi
0x14002de74  mov     rbp, rsp
0x14002de77  sub     rsp, 40h
0x14002de7b  mov     rbx, rcx
0x14002de7e  mov     dword ptr [rbp+arg_8], 0
0x14002de85  mov     r9, rcx
0x14002de88  lea     r8, [rbp+arg_8]
0x14002de8c  xor     edx, edx
0x14002de8e  lea     ecx, [rdx+1]
0x14002de91  call    cs:__imp_WwanOpenHandle
0x14002de97  mov     edi, eax
0x14002de99  test    eax, eax
0x14002de9b  jz      short loc_14002DEDB
0x14002de9d  mov     ecx, cs:dword_140075078
0x14002dea3  cmp     ecx, 2
0x14002dea6  jbe     short loc_14002DED4
0x14002dea8  lea     rcx, aEsimpmWwanhelp_6; "ESIMPM::WwanHelper::Initialize"
0x14002deaf  mov     [rbp+arg_18], rcx
0x14002deb3  mov     [rbp+arg_0], eax
0x14002deb6  lea     rax, [rbp+arg_18]
0x14002deba  mov     [rsp+40h+var_18], rax
0x14002debf  lea     rax, [rbp+arg_0]
0x14002dec3  mov     [rsp+40h+var_20], rax
0x14002dec8  lea     rdx, byte_14006C56B
0x14002decf  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14002ded4  mov     eax, edi
0x14002ded6  jmp     loc_14002DF9E
0x14002dedb  mov     [rbp+var_10], rbx
0x14002dedf  mov     [rbp+var_8], 1
0x14002dee3  mov     [rbp+arg_10], 0
0x14002deea  lea     rax, [rbp+arg_10]
0x14002deee  mov     [rsp+40h+var_18], rax
0x14002def3  mov     [rsp+40h+var_20], 0
0x14002defc  mov     r9, rbx
0x14002deff  lea     r8, ?s_WwapiNotification@WwanHelper@ESIMPM@@CAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; ESIMPM::WwanHelper::s_WwapiNotification(_L2_NOTIFICATION_DATA *,void *)
0x14002df06  mov     edx, 6
0x14002df0b  mov     rcx, [rbx]
0x14002df0e  call    cs:__imp_WwanRegisterNotification
0x14002df14  mov     edi, eax
0x14002df16  test    eax, eax
0x14002df18  jz      short loc_14002DF53
0x14002df1a  mov     ecx, cs:dword_140075078
0x14002df20  cmp     ecx, 2
0x14002df23  jbe     short loc_14002DF7C
0x14002df25  lea     rcx, aEsimpmWwanhelp_6; "ESIMPM::WwanHelper::Initialize"
0x14002df2c  mov     [rbp+arg_18], rcx
0x14002df30  mov     [rbp+arg_0], eax
0x14002df33  lea     rax, [rbp+arg_18]
0x14002df37  mov     [rsp+40h+var_18], rax
0x14002df3c  lea     rax, [rbp+arg_0]
0x14002df40  mov     [rsp+40h+var_20], rax
0x14002df45  lea     rdx, byte_14006C52D
0x14002df4c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14002df51  jmp     short loc_14002DF7C
0x14002df53  lea     rdi, [rbx+8]
0x14002df57  mov     rdx, rdi; struct ESIMPM::InternalModemInfo *
0x14002df5a  mov     rcx, rbx; this
0x14002df5d  call    ?GetInterface@WwanHelper@ESIMPM@@QEAAKAEAUInternalModemInfo@2@@Z; ESIMPM::WwanHelper::GetInterface(ESIMPM::InternalModemInfo &)
0x14002df62  test    eax, eax
0x14002df64  jnz     short loc_14002DF7A
0x14002df66  cmp     [rbx+30h], al
0x14002df69  jz      short loc_14002DF9C
0x14002df6b  mov     rdx, rdi; struct ESIMPM::InternalModemInfo *
0x14002df6e  mov     rcx, rbx; this
0x14002df71  call    ?QueryModemInfo@WwanHelper@ESIMPM@@QEAAKAEAUInternalModemInfo@2@@Z; ESIMPM::WwanHelper::QueryModemInfo(ESIMPM::InternalModemInfo &)
0x14002df76  test    eax, eax
0x14002df78  jz      short loc_14002DF93
0x14002df7a  mov     edi, eax
0x14002df7c  xor     edx, edx
0x14002df7e  mov     rcx, [rbx]
0x14002df81  call    cs:__imp_WwanCloseHandle
0x14002df87  mov     qword ptr [rbx], 0
0x14002df8e  jmp     loc_14002DED4
0x14002df93  mov     rcx, rdi; struct ESIMPM::InternalModemInfo *
0x14002df96  call    ?_EnQueueDevicePresenceEvent@MessageDispatcher@ESIMPM@@SAKPEBUInternalModemInfo@2@@Z; ESIMPM::MessageDispatcher::_EnQueueDevicePresenceEvent(ESIMPM::InternalModemInfo const *)
0x14002df9b  nop
0x14002df9c  xor     eax, eax
0x14002df9e  add     rsp, 40h
0x14002dfa2  pop     rdi
0x14002dfa3  pop     rbx
0x14002dfa4  pop     rbp
0x14002dfa5  retn
```
