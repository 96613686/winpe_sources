# VerifierStop(uint,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *)

- ea: `0x18000d9f8`
- end: `0x18000da9d`
- name: `?VerifierStop@@YAXIPEBD_K0101010@Z`
- size: `165`
- prototype: `void __fastcall(unsigned int, const char *, unsigned __int64, const char *, unsigned __int64, const char *, unsigned __int64, const char *, unsigned __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d8cc`

## callees

- `0x18000d9f8`

## import_xrefs

- `ntdll!DbgPrint` at `0x18000da7e`
- `ntdll!DbgPrint` at `0x18000da7e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000da01`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000da01`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000da8a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000da8a`

## string_xrefs

- `0x18000da15`: `owning thread`

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
0x18000d9f8  push    rbx
0x18000d9fa  sub     rsp, 60h
0x18000d9fe  mov     rbx, r8
0x18000da01  call    cs:__imp_IsDebuggerPresent
0x18000da08  nop     dword ptr [rax+rax+00h]
0x18000da0d  test    eax, eax
0x18000da0f  jz      loc_18000DA96
0x18000da15  lea     rax, aOwningThread; "owning thread"
0x18000da1c  mov     r9, rbx
0x18000da1f  mov     [rsp+68h+var_18], rax
0x18000da24  lea     r8, aDeletingActive; "deleting active critical section"
0x18000da2b  mov     rax, [rsp+68h+arg_40]
0x18000da33  lea     rcx, Format; "\n The application has detected an erro"...
0x18000da3a  mov     [rsp+68h+var_20], rax
0x18000da3f  mov     edx, 208h
0x18000da44  lea     rax, aExpectedLockCo; "expected lock count"
0x18000da4b  mov     [rsp+68h+var_28], rax
0x18000da50  lea     rax, aLockCount; "lock count"
0x18000da57  mov     [rsp+68h+var_30], 0FFFFFFFFFFFFFFFFh
0x18000da60  mov     [rsp+68h+var_38], rax
0x18000da65  mov     rax, [rsp+68h+arg_20]
0x18000da6d  mov     [rsp+68h+var_40], rax
0x18000da72  lea     rax, aCriticalSectio; "critical section address"
0x18000da79  mov     [rsp+68h+var_48], rax
0x18000da7e  call    cs:__imp_DbgPrint
0x18000da85  nop     dword ptr [rax+rax+00h]
0x18000da8a  call    cs:__imp_DebugBreak
0x18000da91  nop     dword ptr [rax+rax+00h]
0x18000da96  add     rsp, 60h
0x18000da9a  pop     rbx
0x18000da9b  retn
```
