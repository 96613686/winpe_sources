# AdvertisingIdHelpers::GenerateAndWriteNewIdToRegistry(HKEY__ *)

- ea: `0x180006354`
- end: `0x180006416`
- name: `?GenerateAndWriteNewIdToRegistry@AdvertisingIdHelpers@@YAJPEAUHKEY__@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(HKEY hKey, HKEY)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800060c0`
- `0x180006274`

## callees

- `0x180006324`
- `0x180006354`
- `0x18000641c`
- `0x1800064d0`
- `0x180009dd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800063cb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800063cb`

## pseudocode

```c
__int64 __fastcall AdvertisingIdHelpers::GenerateAndWriteNewIdToRegistry(
        HKEY hKey,
        unsigned __int16 *a2,
        unsigned int a3)
{
  int NewId; // eax
  unsigned int v5; // ebx
  unsigned int v7; // eax
  int lpData; // [rsp+20h] [rbp-78h]
  unsigned int lpDataa; // [rsp+20h] [rbp-78h]
  BYTE Data[80]; // [rsp+30h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  NewId = AdvertisingIdHelpers::GenerateNewId((AdvertisingIdHelpers *)Data, a2, a3);
  v5 = NewId;
  if ( NewId >= 0 )
  {
    v7 = RegSetValueExW(hKey, L"Id", 0, 1u, Data, 0x42u);
    if ( v7 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x83,
               (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
               (const char *)v7,
               lpDataa);
    else
      return 0;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x7C,
      (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
      (const char *)(unsigned int)NewId,
      lpData);
    return v5;
  }
}

```

## disassembly

```asm
0x180006354  mov     [rsp+arg_8], rbx
0x180006359  push    rdi
0x18000635a  sub     rsp, 90h
0x180006361  mov     rax, cs:__security_cookie
0x180006368  xor     rax, rsp
0x18000636b  mov     [rsp+98h+var_18], rax
0x180006373  mov     rdi, rcx
0x180006376  lea     rcx, [rsp+98h+Data]; this
0x18000637b  call    ?GenerateNewId@AdvertisingIdHelpers@@YAJPEAGI@Z; AdvertisingIdHelpers::GenerateNewId(ushort *,uint)
0x180006380  mov     ebx, eax
0x180006382  test    eax, eax
0x180006384  jns     short loc_1800063A6
0x180006386  mov     rcx, [rsp+98h]; this
0x18000638e  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180006395  mov     r9d, eax; char *
0x180006398  mov     edx, 7Ch ; '|'; void *
0x18000639d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800063a2  mov     eax, ebx
0x1800063a4  jmp     short loc_1800063F5
0x1800063a6  lea     rax, [rsp+98h+Data]
0x1800063ab  mov     [rsp+98h+cbData], 42h ; 'B'; cbData
0x1800063b3  mov     r9d, 1; dwType
0x1800063b9  mov     [rsp+98h+lpData], rax; unsigned int
0x1800063be  xor     r8d, r8d; Reserved
0x1800063c1  lea     rdx, ValueName; "Id"
0x1800063c8  mov     rcx, rdi; hKey
0x1800063cb  call    cs:__imp_RegSetValueExW
0x1800063d1  test    eax, eax
0x1800063d3  jz      short loc_1800063F3
0x1800063d5  mov     rcx, [rsp+98h]; this
0x1800063dd  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x1800063e4  mov     r9d, eax; char *
0x1800063e7  mov     edx, 83h; void *
0x1800063ec  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800063f1  jmp     short loc_1800063F5
0x1800063f3  xor     eax, eax
0x1800063f5  mov     rcx, [rsp+98h+var_18]
0x1800063fd  xor     rcx, rsp; StackCookie
0x180006400  call    __security_check_cookie
0x180006405  mov     rbx, [rsp+98h+arg_8]
0x18000640d  add     rsp, 90h
0x180006414  pop     rdi
0x180006415  retn
```
