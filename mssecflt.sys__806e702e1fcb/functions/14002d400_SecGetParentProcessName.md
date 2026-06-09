# SecGetParentProcessName

- ea: `0x14002d400`
- end: `0x14002d504`
- name: `SecGetParentProcessName`
- size: `260`
- prototype: `__int64 __fastcall(HANDLE ProcessId)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14002c580`

## callees

- `0x140006684`
- `0x1400067a4`
- `0x140006b6c`
- `0x1400100a4`
- `0x140011650`
- `0x14002d400`

## import_xrefs

- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002d478`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002d478`
- `ntoskrnl!PsInitialSystemProcess` at `0x14002d488`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d4cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d4cc`
- `ntoskrnl!ObfDereferenceObject` at `0x14002d4dd`
- `ntoskrnl!ObfDereferenceObject` at `0x14002d4dd`

## pseudocode

```c
NTSTATUS __fastcall SecGetParentProcessName(HANDLE ProcessId, __int64 a2, __int64 a3)
{
  struct _SLIST_ENTRY *v5; // rdi
  int v6; // ebx
  NTSTATUS result; // eax
  PSLIST_ENTRY ListEntry; // [rsp+20h] [rbp-38h] BYREF
  PUNICODE_STRING pImageFileName; // [rsp+28h] [rbp-30h] BYREF
  PEPROCESS Process; // [rsp+30h] [rbp-28h] BYREF

  ListEntry = 0;
  pImageFileName = 0;
  Process = 0;
  if ( (int)SecGetProcessContextByStartkey(a2, &ListEntry) < 0
    || (v5 = ListEntry,
        v6 = SecUnicodeToNullTerminatedUnicode(&ListEntry[9].Next + 1, a3),
        result = SecReleaseProcessContext(v5),
        v6 < 0) )
  {
    result = PsLookupProcessByProcessId(ProcessId, &Process);
    if ( result >= 0 )
    {
      if ( PsInitialSystemProcess == Process )
      {
        SecUnicodeToNullTerminatedUnicode(L"BD", a3);
      }
      else if ( SeLocateProcessImageName_0(Process, &pImageFileName) >= 0 )
      {
        SecUnicodeToNullTerminatedUnicode(pImageFileName, a3);
        ExFreePoolWithTag(pImageFileName, 0);
      }
      return ObfDereferenceObject(Process);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14002d400  mov     r11, rsp
0x14002d403  mov     [r11+20h], rbx
0x14002d407  push    rbp
0x14002d408  push    rsi
0x14002d409  push    rdi
0x14002d40a  sub     rsp, 40h
0x14002d40e  mov     rax, cs:__security_cookie
0x14002d415  xor     rax, rsp
0x14002d418  mov     [rsp+58h+var_20], rax
0x14002d41d  mov     rax, rdx
0x14002d420  mov     qword ptr [r11-38h], 0
0x14002d428  mov     rbp, rcx
0x14002d42b  mov     qword ptr [r11-30h], 0
0x14002d433  mov     rcx, rax
0x14002d436  mov     qword ptr [r11-28h], 0
0x14002d43e  lea     rdx, [r11-38h]
0x14002d442  mov     rsi, r8
0x14002d445  call    SecGetProcessContextByStartkey
0x14002d44a  test    eax, eax
0x14002d44c  js      short loc_14002D470
0x14002d44e  mov     rdi, [rsp+58h+ListEntry]
0x14002d453  mov     rdx, rsi
0x14002d456  lea     rcx, [rdi+98h]
0x14002d45d  call    SecUnicodeToNullTerminatedUnicode
0x14002d462  mov     rcx, rdi; ListEntry
0x14002d465  mov     ebx, eax
0x14002d467  call    SecReleaseProcessContext
0x14002d46c  test    ebx, ebx
0x14002d46e  jns     short loc_14002D4E9
0x14002d470  lea     rdx, [rsp+58h+Process]; Process
0x14002d475  mov     rcx, rbp; ProcessId
0x14002d478  call    cs:__imp_PsLookupProcessByProcessId
0x14002d47f  nop     dword ptr [rax+rax+00h]
0x14002d484  test    eax, eax
0x14002d486  js      short loc_14002D4E9
0x14002d488  mov     rax, cs:__imp_PsInitialSystemProcess
0x14002d48f  mov     rcx, [rsp+58h+Process]; Process
0x14002d494  cmp     [rax], rcx
0x14002d497  jnz     short loc_14002D4AA
0x14002d499  mov     rdx, rsi
0x14002d49c  lea     rcx, SecSystemImageName; "BD"
0x14002d4a3  call    SecUnicodeToNullTerminatedUnicode
0x14002d4a8  jmp     short loc_14002D4D8
0x14002d4aa  lea     rdx, [rsp+58h+pImageFileName]; pImageFileName
0x14002d4af  call    SeLocateProcessImageName_0
0x14002d4b4  test    eax, eax
0x14002d4b6  js      short loc_14002D4D8
0x14002d4b8  mov     rcx, [rsp+58h+pImageFileName]
0x14002d4bd  mov     rdx, rsi
0x14002d4c0  call    SecUnicodeToNullTerminatedUnicode
0x14002d4c5  mov     rcx, [rsp+58h+pImageFileName]; P
0x14002d4ca  xor     edx, edx; Tag
0x14002d4cc  call    cs:__imp_ExFreePoolWithTag
0x14002d4d3  nop     dword ptr [rax+rax+00h]
0x14002d4d8  mov     rcx, [rsp+58h+Process]; Object
0x14002d4dd  call    cs:__imp_ObfDereferenceObject
0x14002d4e4  nop     dword ptr [rax+rax+00h]
0x14002d4e9  mov     rcx, [rsp+58h+var_20]
0x14002d4ee  xor     rcx, rsp; StackCookie
0x14002d4f1  call    __security_check_cookie
0x14002d4f6  mov     rbx, [rsp+58h+arg_18]
0x14002d4fb  add     rsp, 40h
0x14002d4ff  pop     rdi
0x14002d500  pop     rsi
0x14002d501  pop     rbp
0x14002d502  retn
```
