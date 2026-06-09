# VerifierStop(uint,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *)

- ea: `0x18000e728`
- end: `0x18000e7b6`
- name: `?VerifierStop@@YAXIPEBD_K0101010@Z`
- size: `142`
- prototype: `void __fastcall(__int64, const char *, int, const char *, unsigned __int64, const char *, unsigned __int64, const char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000e5d0`

## callees

- `0x18000e728`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e731`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e731`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000e7aa`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000e7aa`
- `ntdll!DbgPrint` at `0x18000e7a4`
- `ntdll!DbgPrint` at `0x18000e7a4`

## string_xrefs

- `0x18000e73b`: `owning thread`

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
0x18000e728  push    rbx
0x18000e72a  sub     rsp, 60h
0x18000e72e  mov     rbx, r8
0x18000e731  call    cs:__imp_IsDebuggerPresent
0x18000e737  test    eax, eax
0x18000e739  jz      short loc_18000E7B0
0x18000e73b  lea     rax, aOwningThread; "owning thread"
0x18000e742  mov     r9, rbx
0x18000e745  mov     [rsp+68h+var_18], rax
0x18000e74a  lea     r8, aDeletingActive; "deleting active critical section"
0x18000e751  mov     rax, [rsp+68h+arg_40]
0x18000e759  lea     rcx, Format; "\n The application has detected an erro"...
0x18000e760  mov     [rsp+68h+var_20], rax
0x18000e765  mov     edx, 208h
0x18000e76a  lea     rax, aExpectedLockCo; "expected lock count"
0x18000e771  mov     [rsp+68h+var_28], rax
0x18000e776  lea     rax, aLockCount; "lock count"
0x18000e77d  mov     [rsp+68h+var_30], 0FFFFFFFFFFFFFFFFh
0x18000e786  mov     [rsp+68h+var_38], rax
0x18000e78b  mov     rax, [rsp+68h+arg_20]
0x18000e793  mov     [rsp+68h+var_40], rax
0x18000e798  lea     rax, aCriticalSectio; "critical section address"
0x18000e79f  mov     [rsp+68h+var_48], rax
0x18000e7a4  call    cs:__imp_DbgPrint
0x18000e7aa  call    cs:__imp_DebugBreak
0x18000e7b0  add     rsp, 60h
0x18000e7b4  pop     rbx
0x18000e7b5  retn
```
