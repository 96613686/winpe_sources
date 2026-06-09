# CsrInsertThread

- ea: `0x180002fd0`
- end: `0x180003091`
- name: `CsrInsertThread`
- size: `193`
- prototype: `NTSTATUS __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002a00`
- `0x180002c90`
- `0x180009370`
- `0x18000a070`

## callees

- `0x180002fd0`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x180002fff`
- `ntdll!NtQueryInformationThread` at `0x180002fff`

## pseudocode

```c
NTSTATUS __fastcall CsrInsertThread(__int64 a1, __int64 a2)
{
  NTSTATUS result; // eax
  _QWORD *v5; // rdx
  __int64 *v6; // rcx
  __int64 v7; // rdx
  int ThreadInformation; // [rsp+48h] [rbp+10h] BYREF

  ThreadInformation = 0;
  result = NtQueryInformationThread(*(HANDLE *)(a2 + 64), ThreadIsTerminated, &ThreadInformation, 4u, 0);
  if ( result >= 0 )
  {
    if ( ThreadInformation == 1 )
    {
      return -1073741749;
    }
    else
    {
      v5 = *(_QWORD **)(a1 + 40);
      if ( *v5 != a1 + 32
        || (*(_QWORD *)(a2 + 8) = a1 + 32,
            *(_QWORD *)(a2 + 16) = v5,
            *v5 = a2 + 8,
            *(_QWORD *)(a1 + 40) = a2 + 8,
            v6 = &CsrThreadHashTable[2 * ((*(_DWORD *)(a2 + 48) >> 2) & 0x3FF)],
            v7 = *v6,
            *(__int64 **)(*v6 + 8) != v6) )
      {
        __fastfail(3u);
      }
      *(_QWORD *)(a2 + 24) = v7;
      *(_QWORD *)(a2 + 32) = v6;
      *(_QWORD *)(v7 + 8) = a2 + 24;
      *v6 = a2 + 24;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002fd0  mov     [rsp+arg_0], rbx
0x180002fd5  push    rdi
0x180002fd6  sub     rsp, 30h
0x180002fda  mov     rbx, rdx
0x180002fdd  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x180002fe2  xor     eax, eax
0x180002fe4  mov     rdi, rcx
0x180002fe7  mov     r9d, 4; ThreadInformationLength
0x180002fed  mov     [rsp+38h+ThreadInformation], eax
0x180002ff1  mov     edx, 14h; ThreadInformationClass
0x180002ff6  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180002ffb  mov     rcx, [rbx+40h]; ThreadHandle
0x180002fff  call    cs:__imp_NtQueryInformationThread
0x180003006  nop     dword ptr [rax+rax+00h]
0x18000300b  test    eax, eax
0x18000300d  js      short loc_18000306D
0x18000300f  cmp     [rsp+38h+ThreadInformation], 1
0x180003014  jz      short loc_180003080
0x180003016  mov     rdx, [rdi+28h]
0x18000301a  lea     rax, [rdi+20h]
0x18000301e  cmp     [rdx], rax
0x180003021  jnz     short loc_180003079
0x180003023  mov     [rbx+8], rax
0x180003027  lea     rcx, [rbx+8]
0x18000302b  mov     [rcx+8], rdx
0x18000302f  mov     [rdx], rcx
0x180003032  mov     [rax+8], rcx
0x180003036  lea     rcx, CsrThreadHashTable
0x18000303d  mov     eax, [rbx+30h]
0x180003040  shr     rax, 2
0x180003044  and     eax, 3FFh
0x180003049  shl     rax, 4
0x18000304d  add     rcx, rax
0x180003050  mov     rdx, [rcx]
0x180003053  cmp     [rdx+8], rcx
0x180003057  jnz     short loc_180003079
0x180003059  lea     rax, [rbx+18h]
0x18000305d  mov     [rax], rdx
0x180003060  mov     [rax+8], rcx
0x180003064  mov     [rdx+8], rax
0x180003068  mov     [rcx], rax
0x18000306b  xor     eax, eax
0x18000306d  mov     rbx, [rsp+38h+arg_0]
0x180003072  add     rsp, 30h
0x180003076  pop     rdi
0x180003077  retn
0x180003079  mov     ecx, 3
0x18000307e  int     29h; Win8: RtlFailFast(ecx)
0x180003080  mov     rbx, [rsp+38h+arg_0]
0x180003085  mov     eax, 0C000004Bh
0x18000308a  add     rsp, 30h
0x18000308e  pop     rdi
0x18000308f  retn
```
