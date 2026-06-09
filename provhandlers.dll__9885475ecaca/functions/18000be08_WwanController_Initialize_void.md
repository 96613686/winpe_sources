# WwanController::Initialize(void)

- ea: `0x18000be08`
- end: `0x18000c070`
- name: `?Initialize@WwanController@@AEAAJXZ`
- size: `616`
- prototype: `__int64 __fastcall(WwanController *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d298`

## callees

- `0x1800011bc`
- `0x180001264`
- `0x180001338`
- `0x18000be08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000be1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000be1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c05c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c05c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000be64`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000be64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bf22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bf22`
- `wwapi!WwanRegisterNotification` at `0x18000bea5`
- `wwapi!WwanRegisterNotification` at `0x18000bea5`
- `wwapi!WwanOpenHandle` at `0x18000be3d`
- `wwapi!WwanOpenHandle` at `0x18000be3d`
- `wwapi!WwanCloseHandle` at `0x18000bf10`
- `wwapi!WwanCloseHandle` at `0x18000bf83`
- `wwapi!WwanCloseHandle` at `0x18000bf10`
- `wwapi!WwanCloseHandle` at `0x18000bf83`

## string_xrefs

- `0x18000bfba`: `CreateEvent failed`
- `0x18000bfea`: `WwanOpenHandle failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WwanController::Initialize(WwanController *this)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  _QWORD *v5; // rdi
  signed int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  HANDLE EventW; // rax
  __int64 v11; // rcx
  signed int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  void *v16; // rcx
  char *v17; // rdx
  const char *v18; // rax
  int v20; // [rsp+70h] [rbp+30h] BYREF
  const char *v21; // [rsp+78h] [rbp+38h] BYREF
  const char *v22; // [rsp+80h] [rbp+40h] BYREF
  const char *v23; // [rsp+88h] [rbp+48h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( *((_BYTE *)this + 8) )
  {
    *((_DWORD *)this + 14) = -2147483634;
    if ( (unsigned int)dword_180052170 > 2 )
    {
      v20 = *((_DWORD *)this + 14);
      v21 = "WwanController::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v2,
        (__int64)&unk_180049328,
        v3,
        v4,
        (const unsigned __int16 **)&v21,
        (__int64)&v20);
    }
  }
  else
  {
    v5 = (_QWORD *)((char *)this + 72);
    v6 = WwanOpenHandle(*((unsigned int *)this + 15), 0, (char *)this + 64, (char *)this + 72);
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    *((_DWORD *)this + 14) = v6;
    if ( v6 < 0 )
    {
      if ( (unsigned int)dword_180052170 <= 2 )
        goto LABEL_28;
      v17 = (char *)&unk_1800482B0;
      v20 = *((_DWORD *)this + 14);
      v21 = "WwanController::Initialize";
      v18 = "WwanOpenHandle failed";
LABEL_24:
      v22 = v18;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v7,
        (__int64)v17,
        v8,
        v9,
        (const unsigned __int16 **)&v22,
        (const unsigned __int16 **)&v21,
        (__int64)&v20);
      goto LABEL_28;
    }
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 10) = EventW;
    if ( EventW != (HANDLE)-1LL )
    {
      v11 = *v5;
      v20 = 0;
      v12 = WwanRegisterNotification(v11, 47, WwanController::_NotificationCallback, this, 0, &v20);
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      *((_DWORD *)this + 14) = v12;
      if ( v12 < 0 )
      {
        if ( *v5 != -1 )
        {
          WwanCloseHandle(*v5, 0);
          *v5 = -1;
        }
        v16 = (void *)*((_QWORD *)this + 10);
        if ( v16 != (void *)-1LL )
        {
          CloseHandle(v16);
          *((_QWORD *)this + 10) = -1;
        }
        if ( (unsigned int)dword_180052170 > 2 )
        {
          LODWORD(v21) = *((_DWORD *)this + 14);
          v22 = "WwanController::Initialize";
          v23 = "WwanRegisterNotification failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (__int64)v16,
            (__int64)byte_18004807D,
            v14,
            v15,
            (const unsigned __int16 **)&v23,
            (const unsigned __int16 **)&v22,
            (__int64)&v21);
        }
      }
      else
      {
        if ( (unsigned int)dword_180052170 > 5 )
        {
          v21 = "WwanController::Initialize";
          v22 = "Singleton initialied";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v13,
            (__int64)byte_18004836B,
            v14,
            v15,
            (const unsigned __int16 **)&v22,
            (const unsigned __int16 **)&v21);
        }
        *((_BYTE *)this + 8) = 1;
      }
      goto LABEL_28;
    }
    if ( *v5 != -1 )
    {
      WwanCloseHandle(*v5, 0);
      *v5 = -1;
    }
    *((_DWORD *)this + 14) = -2147467259;
    if ( (unsigned int)dword_180052170 > 2 )
    {
      v17 = byte_180047CD9;
      v20 = *((_DWORD *)this + 14);
      v21 = "WwanController::Initialize";
      v18 = "CreateEvent failed";
      goto LABEL_24;
    }
  }
LABEL_28:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return *((unsigned int *)this + 14);
}

```

## disassembly

```asm
0x18000be08  push    rbp
0x18000be0a  push    rbx
0x18000be0b  push    rsi
0x18000be0c  push    rdi
0x18000be0d  push    r14
0x18000be0f  mov     rbp, rsp
0x18000be12  sub     rsp, 40h
0x18000be16  mov     rbx, rcx
0x18000be19  add     rcx, 10h; lpCriticalSection
0x18000be1d  call    cs:__imp_EnterCriticalSection
0x18000be23  cmp     byte ptr [rbx+8], 0
0x18000be27  jnz     loc_18000C017
0x18000be2d  mov     ecx, [rbx+3Ch]
0x18000be30  lea     rdi, [rbx+48h]
0x18000be34  mov     r9, rdi
0x18000be37  lea     r8, [rbx+40h]
0x18000be3b  xor     edx, edx
0x18000be3d  call    cs:__imp_WwanOpenHandle
0x18000be43  test    eax, eax
0x18000be45  jle     short loc_18000BE4F
0x18000be47  movzx   eax, ax
0x18000be4a  or      eax, 80070000h
0x18000be4f  mov     [rbx+38h], eax
0x18000be52  test    eax, eax
0x18000be54  js      loc_18000BFC3
0x18000be5a  xor     r9d, r9d; lpName
0x18000be5d  xor     r8d, r8d; bInitialState
0x18000be60  xor     edx, edx; bManualReset
0x18000be62  xor     ecx, ecx; lpEventAttributes
0x18000be64  call    cs:__imp_CreateEventW
0x18000be6a  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000be6e  mov     [rbx+50h], rax
0x18000be72  cmp     rax, r14
0x18000be75  jz      loc_18000BF79
0x18000be7b  mov     rcx, [rdi]
0x18000be7e  lea     rax, [rbp+arg_0]
0x18000be82  mov     [rsp+40h+var_18], rax
0x18000be87  lea     r8, ?_NotificationCallback@WwanController@@CAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; WwanController::_NotificationCallback(_L2_NOTIFICATION_DATA *,void *)
0x18000be8e  mov     r9, rbx
0x18000be91  mov     [rsp+40h+var_20], 0
0x18000be9a  lea     edx, [r14+30h]
0x18000be9e  mov     [rbp+arg_0], 0
0x18000bea5  call    cs:__imp_WwanRegisterNotification
0x18000beab  test    eax, eax
0x18000bead  jle     short loc_18000BEB7
0x18000beaf  movzx   eax, ax
0x18000beb2  or      eax, 80070000h
0x18000beb7  mov     [rbx+38h], eax
0x18000beba  test    eax, eax
0x18000bebc  js      short loc_18000BF06
0x18000bebe  mov     eax, cs:dword_180052170
0x18000bec4  cmp     eax, 5
0x18000bec7  jbe     short loc_18000BEFD
0x18000bec9  lea     rax, aWwancontroller_16; "WwanController::Initialize"
0x18000bed0  mov     [rbp+arg_8], rax
0x18000bed4  lea     rdx, byte_18004836B
0x18000bedb  lea     rax, aSingletonIniti; "Singleton initialied"
0x18000bee2  mov     [rbp+arg_10], rax
0x18000bee6  lea     rax, [rbp+arg_8]
0x18000beea  mov     [rsp+40h+var_18], rax
0x18000beef  lea     rax, [rbp+arg_10]
0x18000bef3  mov     [rsp+40h+var_20], rax
0x18000bef8  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000befd  mov     byte ptr [rbx+8], 1
0x18000bf01  jmp     loc_18000C058
0x18000bf06  cmp     [rdi], r14
0x18000bf09  jz      short loc_18000BF19
0x18000bf0b  mov     rcx, [rdi]
0x18000bf0e  xor     edx, edx
0x18000bf10  call    cs:__imp_WwanCloseHandle
0x18000bf16  mov     [rdi], r14
0x18000bf19  mov     rcx, [rbx+50h]; hObject
0x18000bf1d  cmp     rcx, r14
0x18000bf20  jz      short loc_18000BF2C
0x18000bf22  call    cs:__imp_CloseHandle
0x18000bf28  mov     [rbx+50h], r14
0x18000bf2c  mov     eax, cs:dword_180052170
0x18000bf32  cmp     eax, 2
0x18000bf35  jbe     loc_18000C058
0x18000bf3b  mov     eax, [rbx+38h]
0x18000bf3e  lea     rdx, byte_18004807D
0x18000bf45  mov     dword ptr [rbp+arg_8], eax
0x18000bf48  lea     rax, aWwancontroller_16; "WwanController::Initialize"
0x18000bf4f  mov     [rbp+arg_10], rax
0x18000bf53  lea     rax, aWwanregisterno; "WwanRegisterNotification failed"
0x18000bf5a  mov     [rbp+arg_18], rax
0x18000bf5e  lea     rax, [rbp+arg_8]
0x18000bf62  mov     [rsp+40h+var_10], rax
0x18000bf67  lea     rax, [rbp+arg_10]
0x18000bf6b  mov     [rsp+40h+var_18], rax
0x18000bf70  lea     rax, [rbp+arg_18]
0x18000bf74  jmp     loc_18000C00B
0x18000bf79  cmp     [rdi], r14
0x18000bf7c  jz      short loc_18000BF8C
0x18000bf7e  mov     rcx, [rdi]
0x18000bf81  xor     edx, edx
0x18000bf83  call    cs:__imp_WwanCloseHandle
0x18000bf89  mov     [rdi], r14
0x18000bf8c  mov     dword ptr [rbx+38h], 80004005h
0x18000bf93  mov     eax, cs:dword_180052170
0x18000bf99  cmp     eax, 2
0x18000bf9c  jbe     loc_18000C058
0x18000bfa2  mov     eax, [rbx+38h]
0x18000bfa5  lea     rdx, byte_180047CD9
0x18000bfac  mov     [rbp+arg_0], eax
0x18000bfaf  lea     rax, aWwancontroller_16; "WwanController::Initialize"
0x18000bfb6  mov     [rbp+arg_8], rax
0x18000bfba  lea     rax, aCreateeventFai; "CreateEvent failed"
0x18000bfc1  jmp     short loc_18000BFF1
0x18000bfc3  mov     eax, cs:dword_180052170
0x18000bfc9  cmp     eax, 2
0x18000bfcc  jbe     loc_18000C058
0x18000bfd2  mov     eax, [rbx+38h]
0x18000bfd5  lea     rdx, unk_1800482B0
0x18000bfdc  mov     [rbp+arg_0], eax
0x18000bfdf  lea     rax, aWwancontroller_16; "WwanController::Initialize"
0x18000bfe6  mov     [rbp+arg_8], rax
0x18000bfea  lea     rax, aWwanopenhandle; "WwanOpenHandle failed"
0x18000bff1  mov     [rbp+arg_10], rax
0x18000bff5  lea     rax, [rbp+arg_0]
0x18000bff9  mov     [rsp+40h+var_10], rax
0x18000bffe  lea     rax, [rbp+arg_8]
0x18000c002  mov     [rsp+40h+var_18], rax
0x18000c007  lea     rax, [rbp+arg_10]
0x18000c00b  mov     [rsp+40h+var_20], rax
0x18000c010  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000c015  jmp     short loc_18000C058
0x18000c017  mov     dword ptr [rbx+38h], 8000000Eh
0x18000c01e  mov     eax, cs:dword_180052170
0x18000c024  cmp     eax, 2
0x18000c027  jbe     short loc_18000C058
0x18000c029  mov     eax, [rbx+38h]
0x18000c02c  lea     rdx, unk_180049328
0x18000c033  mov     [rbp+arg_0], eax
0x18000c036  lea     rax, aWwancontroller_16; "WwanController::Initialize"
0x18000c03d  mov     [rbp+arg_8], rax
0x18000c041  lea     rax, [rbp+arg_0]
0x18000c045  mov     [rsp+40h+var_18], rax
0x18000c04a  lea     rax, [rbp+arg_8]
0x18000c04e  mov     [rsp+40h+var_20], rax
0x18000c053  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000c058  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000c05c  call    cs:__imp_LeaveCriticalSection
0x18000c062  mov     eax, [rbx+38h]
0x18000c065  add     rsp, 40h
0x18000c069  pop     r14
0x18000c06b  pop     rdi
0x18000c06c  pop     rsi
0x18000c06d  pop     rbx
0x18000c06e  pop     rbp
0x18000c06f  retn
```
