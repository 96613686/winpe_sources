# Hns::Client::Notifications::NotificationCallbacks::UnregisterCallback(void *,void * *)

- ea: `0x18000ad58`
- end: `0x18000add1`
- name: `?UnregisterCallback@NotificationCallbacks@Notifications@Client@Hns@@QEAAXPEAXPEAPEAX@Z`
- size: `121`
- prototype: `void __fastcall(Hns::Client::Notifications::NotificationCallbacks *__hidden this, void *, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005ed0`
- `0x180009bc0`
- `0x180009c20`

## callees

- `0x180007904`
- `0x18000aaa0`
- `0x18000ad58`

## string_xrefs

- `0x18000ad7f`: `onecore\vm\dv\net\hns\computenetwork\src\notificationcallbacks.cpp`
- `0x18000ad9c`: `onecore\vm\dv\net\hns\computenetwork\src\notificationcallbacks.cpp`
- `0x18000adb9`: `onecore\vm\dv\net\hns\computenetwork\src\notificationcallbacks.cpp`

## pseudocode

```c
void __fastcall Hns::Client::Notifications::NotificationCallbacks::UnregisterCallback(
        RTL_SRWLOCK *this,
        void **a2,
        void **a3)
{
  void *v3; // rdx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a2 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\notificationcallbacks.cpp",
      (const char *)0x80070006LL,
      v4);
  if ( !a3 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x82,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\notificationcallbacks.cpp",
      (const char *)0x80004003LL,
      v4);
  v3 = *a2;
  *a3 = v3;
  if ( !Hns::Client::Notifications::NotificationCallbacks::RemoveNotificationContext(this, (unsigned __int64)v3) )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\notificationcallbacks.cpp",
      (const char *)0x80070006LL,
      v4);
}

```

## disassembly

```asm
0x18000ad58  sub     rsp, 28h
0x18000ad5c  test    rdx, rdx
0x18000ad5f  jz      short loc_18000AD97
0x18000ad61  test    r8, r8
0x18000ad64  jz      short loc_18000ADB4
0x18000ad66  mov     rdx, [rdx]; void *
0x18000ad69  mov     [r8], rdx
0x18000ad6c  call    ?RemoveNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@AEAA_NPEAX@Z; Hns::Client::Notifications::NotificationCallbacks::RemoveNotificationContext(void *)
0x18000ad71  test    al, al
0x18000ad73  jz      short loc_18000AD7A
0x18000ad75  add     rsp, 28h
0x18000ad79  retn
0x18000ad7a  mov     rcx, [rsp+28h]; this
0x18000ad7f  lea     r8, aOnecoreVmDvNet_1; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x18000ad86  mov     r9d, 80070006h; char *
0x18000ad8c  mov     edx, 87h; void *
0x18000ad91  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000ad97  mov     rcx, [rsp+28h]; this
0x18000ad9c  lea     r8, aOnecoreVmDvNet_1; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x18000ada3  mov     r9d, 80070006h; char *
0x18000ada9  mov     edx, 81h; void *
0x18000adae  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000adb4  mov     rcx, [rsp+28h]; this
0x18000adb9  lea     r8, aOnecoreVmDvNet_1; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x18000adc0  mov     r9d, 80004003h; char *
0x18000adc6  mov     edx, 82h; void *
0x18000adcb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
