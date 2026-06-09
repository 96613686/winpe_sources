# Microsoft::FoundationServices::Common::FastMutex::FastMutex(void)

- ea: `0x180053344`
- end: `0x1800533cb`
- name: `??0FastMutex@Common@FoundationServices@Microsoft@@QEAA@XZ`
- size: `135`
- prototype: `__int64 __fastcall(Microsoft::FoundationServices::Common::FastMutex *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180052f50`
- `0x180057d98`

## callees

- `0x18000343a`
- `0x1800516b8`
- `0x180053344`
- `0x180053c68`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180053364`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180053364`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005338a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005338a`

## string_xrefs

- `0x1800533ad`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\utils\FastMutex.h`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall Microsoft::FoundationServices::Common::FastMutex::FastMutex(
        struct _RTL_CRITICAL_SECTION *this)
{
  DWORD LastError; // eax
  int v4; // eax
  _BYTE pExceptionObject[1216]; // [rsp+30h] [rbp-4D8h] BYREF

  if ( !InitializeCriticalSectionAndSpinCount(this, 0) )
  {
    LastError = GetLastError();
    v4 = HR_FROM_WIN32(LastError);
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\utils\\FastMutex.h",
      0x1Cu,
      L"InitializeCriticalSectionAndSpinCount(&m_cs, 0)",
      v4);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x180053344  push    rbx
0x180053346  sub     rsp, 500h
0x18005334d  mov     rax, cs:__security_cookie
0x180053354  xor     rax, rsp
0x180053357  mov     [rsp+508h+var_18], rax
0x18005335f  xor     edx, edx; dwSpinCount
0x180053361  mov     rbx, rcx
0x180053364  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18005336a  test    eax, eax
0x18005336c  jz      short loc_18005338A
0x18005336e  mov     rax, rbx
0x180053371  mov     rcx, [rsp+508h+var_18]
0x180053379  xor     rcx, rsp; StackCookie
0x18005337c  call    __security_check_cookie
0x180053381  add     rsp, 500h
0x180053388  pop     rbx
0x180053389  retn
0x18005338a  call    cs:__imp_GetLastError
0x180053390  mov     ecx, eax; unsigned int
0x180053392  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x180053397  lea     rcx, [rsp+508h+pExceptionObject]; this
0x18005339c  mov     [rsp+508h+var_4E8], eax; int
0x1800533a0  lea     r9, aInitializecrit; "InitializeCriticalSectionAndSpinCount(&"...
0x1800533a7  mov     r8d, 1Ch; unsigned int
0x1800533ad  lea     rdx, aDsSecurityRmSr_4; "ds\\security\\rm\\src\\client\\promethi"...
0x1800533b4  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800533b9  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x1800533c0  lea     rcx, [rsp+508h+pExceptionObject]; pExceptionObject
0x1800533c5  call    _CxxThrowException_0
```
