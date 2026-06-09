# Hns::Client::Notifications::NotificationCallbacks::OnNotificationPending(Hns::Client::Notifications::NotificationCallbacks::NotificationContext *)

- ea: `0x18000a40c`
- end: `0x18000a54f`
- name: `?OnNotificationPending@NotificationCallbacks@Notifications@Client@Hns@@AEAAXPEAUNotificationContext@1234@@Z`
- size: `323`
- prototype: `void(Hns::Client::Notifications::NotificationCallbacks *__hidden this, struct Hns::Client::Notifications::NotificationCallbacks::NotificationContext *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000ade0`

## callees

- `0x180002188`
- `0x180009d10`
- `0x18000a2f8`
- `0x18000a3c8`
- `0x18000a40c`
- `0x18000ac88`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000a52b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000a52b`

## string_xrefs

- `0x18000a4bc`: `onecore\vm\dv\net\hns\computenetwork\src\notificationcallbacks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Hns::Client::Notifications::NotificationCallbacks::OnNotificationPending(
        Hns::Client::Notifications::NotificationCallbacks *this,
        struct Hns::Client::Notifications::NotificationCallbacks::NotificationContext *a2)
{
  struct Hns::Client::Notifications::NotificationCallbacks::NotificationContext *v2; // rbx
  char v4; // di
  char v5; // si
  int v6; // eax
  Hns::Client::Notifications::NotificationCallbacks *v7; // rcx
  void *v8; // rdi
  DWORD LastError; // ebx
  unsigned int v10; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v11; // [rsp+34h] [rbp-34h] BYREF
  void *v12; // [rsp+38h] [rbp-30h] BYREF
  unsigned int *v13; // [rsp+40h] [rbp-28h] BYREF
  unsigned int *v14; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  char v18; // [rsp+80h] [rbp+18h]
  void **v20; // [rsp+88h] [rbp+20h] BYREF

  v2 = a2;
  if ( Hns::Client::Notifications::NotificationCallbacks::StartCallback(this, a2) )
  {
    try
    {
      v11 = 0;
      v10 = 0;
      v4 = 1;
      v18 = 1;
      v5 = 1;
      v12 = 0;
      v20 = &v12;
      v13 = &v10;
      v14 = &v11;
      v6 = Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void *,unsigned short const *,unsigned short * *,unsigned short * *),void * &,unsigned short const * &,unsigned short * * &,unsigned short * *>(
             *((_QWORD *)this + 2),
             (_DWORD)v2,
             (unsigned int)&v14,
             (unsigned int)&v13,
             (__int64)&v20);
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x134,
          (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\notificationcallbacks.cpp",
          (const char *)(unsigned int)v6,
          (int)"Failed to query notification for handle %p",
          *(const char **)v2);
        v4 = 0;
        v18 = 0;
      }
    }
    catch ( ... )
    {
      v11 = 0x1000000;
      v10 = 0;
      v8 = v12;
      if ( v12 )
      {
        LastError = GetLastError();
        MIDL_user_free(v8);
        SetLastError(LastError);
      }
      v12 = 0;
      LOBYTE(v20) = 0;
      v2 = a2;
      v4 = v18;
      v5 = 0;
    }
    if ( v4 )
      (*((void (__fastcall **)(_QWORD, _QWORD, _QWORD, void *))v2 + 1))(v11, *((_QWORD *)v2 + 2), v10, v12);
    if ( Hns::Client::Notifications::NotificationCallbacks::CompleteCallback(v7, v2) && v5 )
      SetThreadpoolWait(*((PTP_WAIT *)v2 + 4), *((HANDLE *)v2 + 3), 0);
    if ( v12 )
      MIDL_user_free(v12);
  }
}

```

## disassembly

```asm
0x18000a40c  mov     [rsp+arg_0], rbx
0x18000a411  mov     [rsp+arg_8], rdx
0x18000a416  push    rsi
0x18000a417  push    rdi
0x18000a418  push    r14
0x18000a41a  sub     rsp, 50h
0x18000a41e  mov     rbx, rdx
0x18000a421  mov     r14, rcx
0x18000a424  call    ?StartCallback@NotificationCallbacks@Notifications@Client@Hns@@AEAA_NPEAUNotificationContext@1234@@Z; Hns::Client::Notifications::NotificationCallbacks::StartCallback(Hns::Client::Notifications::NotificationCallbacks::NotificationContext *)
0x18000a429  test    al, al
0x18000a42b  jz      loc_18000A541
0x18000a431  mov     [rsp+68h+var_34], 0
0x18000a439  mov     [rsp+68h+var_38], 0
0x18000a441  mov     dil, 1
0x18000a444  mov     [rsp+68h+arg_10], dil
0x18000a44c  mov     sil, dil
0x18000a44f  mov     [rsp+68h+var_30], 0
0x18000a458  lea     rax, [rsp+68h+var_30]
0x18000a45d  mov     [rsp+68h+arg_18], rax
0x18000a465  lea     rax, [rsp+68h+var_38]
0x18000a46a  mov     [rsp+68h+var_28], rax
0x18000a46f  lea     rax, [rsp+68h+var_34]
0x18000a474  mov     [rsp+68h+var_20], rax
0x18000a479  lea     rax, [rsp+68h+arg_18]
0x18000a481  mov     qword ptr [rsp+68h+var_48], rax
0x18000a486  lea     r9, [rsp+68h+var_28]
0x18000a48b  lea     r8, [rsp+68h+var_20]
0x18000a490  mov     rdx, rbx
0x18000a493  mov     rcx, [r14+10h]
0x18000a497  call    ??$InvokeRpcFunction@P6AJPEAXPEBGPEAPEAG2@ZAEAPEAXAEAPEBGAEAPEAPEAGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG2@ZAEAPEAXAEAPEBGAEAPEAPEAG$$QEAPEAPEAG@Z
0x18000a49c  test    eax, eax
0x18000a49e  jns     short loc_18000A4D8
0x18000a4a0  mov     rcx, [rsp+68h]; this
0x18000a4a5  mov     rdx, [rbx]
0x18000a4a8  mov     [rsp+68h+var_40], rdx; char *
0x18000a4ad  lea     rdx, aFailedToQueryN; "Failed to query notification for handle"...
0x18000a4b4  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18000a4b9  mov     r9d, eax; char *
0x18000a4bc  lea     r8, aOnecoreVmDvNet_1; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x18000a4c3  mov     edx, 134h; void *
0x18000a4c8  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000a4cd  xor     dil, dil
0x18000a4d0  mov     [rsp+68h+arg_10], dil
0x18000a4d8  jmp     short loc_18000A4EF
0x18000a4da  mov     rbx, [rsp+68h+arg_8]
0x18000a4df  mov     dil, [rsp+68h+arg_10]
0x18000a4e7  mov     sil, byte ptr [rsp+68h+arg_18]
0x18000a4ef  test    dil, dil
0x18000a4f2  jz      short loc_18000A50F
0x18000a4f4  mov     r9, [rsp+68h+var_30]
0x18000a4f9  mov     r8d, [rsp+68h+var_38]
0x18000a4fe  mov     rdx, [rbx+10h]
0x18000a502  mov     ecx, [rsp+68h+var_34]
0x18000a506  mov     rax, [rbx+8]
0x18000a50a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a50f  mov     rdx, rbx; struct Hns::Client::Notifications::NotificationCallbacks::NotificationContext *
0x18000a512  call    ?CompleteCallback@NotificationCallbacks@Notifications@Client@Hns@@AEAA_NPEAUNotificationContext@1234@@Z; Hns::Client::Notifications::NotificationCallbacks::CompleteCallback(Hns::Client::Notifications::NotificationCallbacks::NotificationContext *)
0x18000a517  test    al, al
0x18000a519  jz      short loc_18000A532
0x18000a51b  test    sil, sil
0x18000a51e  jz      short loc_18000A532
0x18000a520  xor     r8d, r8d; pftTimeout
0x18000a523  mov     rdx, [rbx+18h]; h
0x18000a527  mov     rcx, [rbx+20h]; pwa
0x18000a52b  call    cs:__imp_SetThreadpoolWait
0x18000a531  nop
0x18000a532  mov     rcx, [rsp+68h+var_30]; void *
0x18000a537  test    rcx, rcx
0x18000a53a  jz      short loc_18000A541
0x18000a53c  call    MIDL_user_free
0x18000a541  mov     rbx, [rsp+68h+arg_0]
0x18000a546  add     rsp, 50h
0x18000a54a  pop     r14
0x18000a54c  pop     rdi
0x18000a54d  pop     rsi
0x18000a54e  retn
```
