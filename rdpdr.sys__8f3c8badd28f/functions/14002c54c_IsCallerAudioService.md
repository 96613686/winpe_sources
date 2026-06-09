# IsCallerAudioService

- ea: `0x14002c54c`
- end: `0x14002c5d0`
- name: `IsCallerAudioService`
- size: `132`
- prototype: `void *()`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task`

## callers

- `0x14001a59c`

## callees

- `0x140001e30`
- `0x1400023f4`
- `0x140003188`
- `0x14002a4f8`
- `0x14002c54c`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x14002c55b`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14002c55b`

## pseudocode

```c
void *IsCallerAudioService()
{
  ULONG v0; // eax
  void *result; // rax
  void *v2; // rdi
  BOOL v3; // ebx
  unsigned int v4[10]; // [rsp+20h] [rbp-28h] BYREF

  v0 = RtlLengthRequiredSid(6u);
  result = operator new(v0, 0x100u);
  v2 = result;
  if ( result )
  {
    v4[0] = -1618417719;
    v4[1] = 1911656217;
    v4[2] = -1669870755;
    v4[3] = -116925420;
    v4[4] = 1366760775;
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
0x14002c54c  mov     [rsp+arg_0], rbx
0x14002c551  push    rdi
0x14002c552  sub     rsp, 40h
0x14002c556  mov     ecx, 6; SubAuthorityCount
0x14002c55b  call    cs:__imp_RtlLengthRequiredSid
0x14002c562  nop     dword ptr [rax+rax+00h]
0x14002c567  mov     ecx, eax; unsigned __int64
0x14002c569  mov     edx, 100h; unsigned __int64
0x14002c56e  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x14002c573  mov     rdi, rax
0x14002c576  test    rax, rax
0x14002c579  jz      short loc_14002C5C4
0x14002c57b  lea     rdx, [rsp+48h+var_28]; unsigned int *
0x14002c580  mov     [rsp+48h+var_28], 9F88E7C9h
0x14002c588  mov     rcx, rdi; Sid
0x14002c58b  mov     [rsp+48h+var_24], 71F18F19h
0x14002c593  mov     [rsp+48h+var_20], 9C77CB5Dh
0x14002c59b  mov     [rsp+48h+var_1C], 0F907DC14h
0x14002c5a3  mov     [rsp+48h+var_18], 51771D47h
0x14002c5ab  call    ?InitializeServiceSid@@YAXPEAXQEAK@Z; InitializeServiceSid(void *,ulong * const)
0x14002c5b0  mov     rcx, rdi; void *
0x14002c5b3  call    ?DrCheckCurrentProcessForServiceSid@@YAHPEAX@Z; DrCheckCurrentProcessForServiceSid(void *)
0x14002c5b8  mov     rcx, rdi; void *
0x14002c5bb  mov     ebx, eax
0x14002c5bd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002c5c2  mov     eax, ebx
0x14002c5c4  mov     rbx, [rsp+48h+arg_0]
0x14002c5c9  add     rsp, 40h
0x14002c5cd  pop     rdi
0x14002c5ce  retn
```
