# LPA::ApduHelper::OnStart(void)

- ea: `0x18006c330`
- end: `0x18006c3c8`
- name: `?OnStart@ApduHelper@LPA@@UEAAJXZ`
- size: `152`
- prototype: `__int64 __fastcall(LPA::ApduHelper *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18006ba8c`
- `0x18006c330`
- `0x18006d8d0`
- `0x180071a34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006c369`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006c369`

## pseudocode

```c
__int64 __fastcall LPA::ApduHelper::OnStart(LPA::ApduHelper *this)
{
  char *v1; // rdi
  int LastErrorToHResultAndForceFailure; // ebx
  HANDLE EventW; // rax
  CommonUtil *v5; // rcx
  __int64 v6; // rdx

  v1 = (char *)this + 56;
  if ( *((_DWORD *)this + 14) )
  {
    return (unsigned int)-2147019873;
  }
  else
  {
    LastErrorToHResultAndForceFailure = 0;
    LPA::Util::SetRunningState(v1, 1, "LpaApduHelper");
    EventW = CreateEventW(0, 0, 0, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 48,
      EventW);
    if ( *((_QWORD *)this + 6)
      || (LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v5),
          LastErrorToHResultAndForceFailure >= 0) )
    {
      v6 = 2;
    }
    else
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        (char *)this + 48,
        0);
      v6 = 0;
    }
    LPA::Util::SetRunningState(v1, v6, "LpaApduHelper");
  }
  return (unsigned int)LastErrorToHResultAndForceFailure;
}

```

## disassembly

```asm
0x18006c330  mov     [rsp+arg_0], rbx
0x18006c335  mov     [rsp+arg_8], rsi
0x18006c33a  push    rdi
0x18006c33b  sub     rsp, 20h
0x18006c33f  lea     rdi, [rcx+38h]
0x18006c343  mov     rsi, rcx
0x18006c346  cmp     dword ptr [rdi], 0
0x18006c349  jnz     short loc_18006C3B1
0x18006c34b  xor     ebx, ebx
0x18006c34d  lea     r8, aLpaapduhelper; "LpaApduHelper"
0x18006c354  mov     rcx, rdi
0x18006c357  lea     edx, [rbx+1]
0x18006c35a  call    ?SetRunningState@Util@LPA@@YAXAEAW4RUNNING_STATE@@W43@PEBD@Z; LPA::Util::SetRunningState(RUNNING_STATE &,RUNNING_STATE,char const *)
0x18006c35f  xor     r9d, r9d; lpName
0x18006c362  xor     r8d, r8d; bInitialState
0x18006c365  xor     edx, edx; bManualReset
0x18006c367  xor     ecx, ecx; lpEventAttributes
0x18006c369  call    cs:__imp_CreateEventW
0x18006c36f  mov     rdx, rax
0x18006c372  lea     rcx, [rsi+30h]
0x18006c376  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18006c37b  cmp     [rsi+30h], rbx
0x18006c37f  jnz     short loc_18006C39B
0x18006c381  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x18006c386  mov     ebx, eax
0x18006c388  test    eax, eax
0x18006c38a  jns     short loc_18006C39B
0x18006c38c  xor     edx, edx
0x18006c38e  lea     rcx, [rsi+30h]
0x18006c392  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18006c397  xor     edx, edx
0x18006c399  jmp     short loc_18006C3A0
0x18006c39b  mov     edx, 2
0x18006c3a0  lea     r8, aLpaapduhelper; "LpaApduHelper"
0x18006c3a7  mov     rcx, rdi
0x18006c3aa  call    ?SetRunningState@Util@LPA@@YAXAEAW4RUNNING_STATE@@W43@PEBD@Z; LPA::Util::SetRunningState(RUNNING_STATE &,RUNNING_STATE,char const *)
0x18006c3af  jmp     short loc_18006C3B6
0x18006c3b1  mov     ebx, 8007139Fh
0x18006c3b6  mov     rsi, [rsp+28h+arg_8]
0x18006c3bb  mov     eax, ebx
0x18006c3bd  mov     rbx, [rsp+28h+arg_0]
0x18006c3c2  add     rsp, 20h
0x18006c3c6  pop     rdi
0x18006c3c7  retn
```
