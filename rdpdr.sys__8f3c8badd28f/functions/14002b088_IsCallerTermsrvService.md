# IsCallerTermsrvService

- ea: `0x14002b088`
- end: `0x14002b10c`
- name: `IsCallerTermsrvService`
- size: `132`
- prototype: `void *()`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task`

## callers

- `0x14002acc0`

## callees

- `0x140001e30`
- `0x1400023f4`
- `0x140003188`
- `0x14002a4f8`
- `0x14002b088`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x14002b097`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14002b097`

## pseudocode

```c
void *IsCallerTermsrvService()
{
  ULONG v0; // eax
  void *result; // rax
  void *v2; // rdi
  unsigned int v3; // ebx
  unsigned int v4[10]; // [rsp+20h] [rbp-28h] BYREF

  v0 = RtlLengthRequiredSid(6u);
  result = operator new(v0, 0x100u);
  v2 = result;
  if ( result )
  {
    v4[0] = 446051430;
    v4[1] = 1559341753;
    v4[2] = -133025767;
    v4[3] = 1950928533;
    v4[4] = 810483104;
    InitializeServiceSid(result, v4);
    v3 = DrCheckCurrentProcessForServiceSid(v2);
    operator delete(v2);
    return (void *)v3;
  }
  return result;
}

```

## disassembly

```asm
0x14002b088  mov     [rsp+arg_0], rbx
0x14002b08d  push    rdi
0x14002b08e  sub     rsp, 40h
0x14002b092  mov     ecx, 6; SubAuthorityCount
0x14002b097  call    cs:__imp_RtlLengthRequiredSid
0x14002b09e  nop     dword ptr [rax+rax+00h]
0x14002b0a3  mov     ecx, eax; unsigned __int64
0x14002b0a5  mov     edx, 100h; unsigned __int64
0x14002b0aa  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x14002b0af  mov     rdi, rax
0x14002b0b2  test    rax, rax
0x14002b0b5  jz      short loc_14002B100
0x14002b0b7  lea     rdx, [rsp+48h+var_28]; unsigned int *
0x14002b0bc  mov     [rsp+48h+var_28], 1A963466h
0x14002b0c4  mov     rcx, rdi; Sid
0x14002b0c7  mov     [rsp+48h+var_24], 5CF1AAB9h
0x14002b0cf  mov     [rsp+48h+var_20], 0F8123019h
0x14002b0d7  mov     [rsp+48h+var_1C], 7448CE95h
0x14002b0df  mov     [rsp+48h+var_18], 304EFDA0h
0x14002b0e7  call    ?InitializeServiceSid@@YAXPEAXQEAK@Z; InitializeServiceSid(void *,ulong * const)
0x14002b0ec  mov     rcx, rdi; void *
0x14002b0ef  call    ?DrCheckCurrentProcessForServiceSid@@YAHPEAX@Z; DrCheckCurrentProcessForServiceSid(void *)
0x14002b0f4  mov     rcx, rdi; void *
0x14002b0f7  mov     ebx, eax
0x14002b0f9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002b0fe  mov     eax, ebx
0x14002b100  mov     rbx, [rsp+48h+arg_0]
0x14002b105  add     rsp, 40h
0x14002b109  pop     rdi
0x14002b10a  retn
```
