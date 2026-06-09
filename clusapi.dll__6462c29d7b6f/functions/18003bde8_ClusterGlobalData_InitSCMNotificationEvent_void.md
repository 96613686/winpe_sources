# ClusterGlobalData::InitSCMNotificationEvent(void)

- ea: `0x18003bde8`
- end: `0x18003be62`
- name: `?InitSCMNotificationEvent@ClusterGlobalData@@AEAAXXZ`
- size: `122`
- prototype: `void __fastcall(ClusterGlobalData *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18003be68`
- `0x18007ab58`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x18003180c`
- `0x18003bde8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003be10`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003be10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003be1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003be1e`

## string_xrefs

- `0x18003be26`: `Couldn't create Services Running event`

## pseudocode

```c
void __fastcall ClusterGlobalData::InitSCMNotificationEvent(ClusterGlobalData *this)
{
  HANDLE EventW; // rax
  DWORD LastError; // eax
  _BYTE pExceptionObject[272]; // [rsp+20h] [rbp-128h] BYREF

  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)this = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    ClusRtl::ExceptionMsg::ExceptionMsg(
      (ClusRtl::ExceptionMsg *)pExceptionObject,
      LastError,
      L"Couldn't create Services Running event");
    throw (ClusRtl::ExceptionMsg *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x18003bde8  push    rbx
0x18003bdea  sub     rsp, 140h
0x18003bdf1  mov     rax, cs:__security_cookie
0x18003bdf8  xor     rax, rsp
0x18003bdfb  mov     [rsp+148h+var_18], rax
0x18003be03  mov     rbx, rcx
0x18003be06  xor     r9d, r9d; lpName
0x18003be09  xor     ecx, ecx; lpEventAttributes
0x18003be0b  xor     r8d, r8d; bInitialState
0x18003be0e  xor     edx, edx; bManualReset
0x18003be10  call    cs:__imp_CreateEventW
0x18003be16  mov     [rbx], rax
0x18003be19  test    rax, rax
0x18003be1c  jnz     short loc_18003BE49
0x18003be1e  call    cs:__imp_GetLastError
0x18003be24  mov     edx, eax; int
0x18003be26  lea     r8, aCouldnTCreateS; "Couldn't create Services Running event"
0x18003be2d  lea     rcx, [rsp+148h+pExceptionObject]; this
0x18003be32  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x18003be37  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x18003be3e  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x18003be43  call    _CxxThrowException_0
0x18003be49  mov     rcx, [rsp+148h+var_18]
0x18003be51  xor     rcx, rsp; StackCookie
0x18003be54  call    __security_check_cookie
0x18003be59  add     rsp, 140h
0x18003be60  pop     rbx
0x18003be61  retn
```
