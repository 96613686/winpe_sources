# VerifierStop(uint,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *)

- ea: `0x180012c84`
- end: `0x180012d12`
- name: `?VerifierStop@@YAXIPEBD_K0101010@Z`
- size: `142`
- prototype: `void __fastcall(unsigned int, const char *, unsigned __int64, const char *, unsigned __int64, const char *, unsigned __int64, const char *, unsigned __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800120e8`

## callees

- `0x180012c84`

## import_xrefs

- `ntdll!DbgPrint` at `0x180012d00`
- `ntdll!DbgPrint` at `0x180012d00`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180012d06`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180012d06`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180012c8d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180012c8d`

## string_xrefs

- `0x180012c97`: `owning thread`

## pseudocode

```c
void __fastcall VerifierStop(
        __int64 a1,
        const char *a2,
        int a3,
        const char *a4,
        unsigned __int64 a5,
        const char *a6,
        unsigned __int64 a7,
        const char *a8,
        unsigned __int64 a9)
{
  if ( IsDebuggerPresent() )
  {
    DbgPrint(
      "\n"
      " The application has detected an error \n"
      "Code = %d, message = %s,\n"
      "param1=%Id, description1=%s,\n"
      "param2=%Id, description2=%s,\n"
      "param3=%Id, description3=%s,\n"
      "param4=%Id, description4=%s\n",
      520,
      "deleting active critical section",
      a3,
      "critical section address",
      a5,
      "lock count",
      -1,
      "expected lock count",
      a9,
      "owning thread");
    DebugBreak();
  }
}

```

## disassembly

```asm
0x180012c84  push    rbx
0x180012c86  sub     rsp, 60h
0x180012c8a  mov     rbx, r8
0x180012c8d  call    cs:__imp_IsDebuggerPresent
0x180012c93  test    eax, eax
0x180012c95  jz      short loc_180012D0C
0x180012c97  lea     rax, aOwningThread; "owning thread"
0x180012c9e  mov     r9, rbx
0x180012ca1  mov     [rsp+68h+var_18], rax
0x180012ca6  lea     r8, aDeletingActive; "deleting active critical section"
0x180012cad  mov     rax, [rsp+68h+arg_40]
0x180012cb5  lea     rcx, Format; "\n The application has detected an erro"...
0x180012cbc  mov     [rsp+68h+var_20], rax
0x180012cc1  mov     edx, 208h
0x180012cc6  lea     rax, aExpectedLockCo; "expected lock count"
0x180012ccd  mov     [rsp+68h+var_28], rax
0x180012cd2  lea     rax, aLockCount; "lock count"
0x180012cd9  mov     [rsp+68h+var_30], 0FFFFFFFFFFFFFFFFh
0x180012ce2  mov     [rsp+68h+var_38], rax
0x180012ce7  mov     rax, [rsp+68h+arg_20]
0x180012cef  mov     [rsp+68h+var_40], rax
0x180012cf4  lea     rax, aCriticalSectio; "critical section address"
0x180012cfb  mov     [rsp+68h+var_48], rax
0x180012d00  call    cs:__imp_DbgPrint
0x180012d06  call    cs:__imp_DebugBreak
0x180012d0c  add     rsp, 60h
0x180012d10  pop     rbx
0x180012d11  retn
```
