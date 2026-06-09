# PsmpEndTimeCriticalTask

- ea: `0x180014d74`
- end: `0x180014deb`
- name: `PsmpEndTimeCriticalTask`
- size: `119`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000abf0`
- `0x18000e0f4`

## callees

- `0x180014d74`
- `0x180017ca4`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180014d8b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180014d8b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180014dac`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180014dac`

## pseudocode

```c
__int64 __fastcall PsmpEndTimeCriticalTask(__int64 a1)
{
  __int64 v1; // rdi
  int v3; // eax
  __int64 result; // rax

  v1 = a1 + 328;
  RtlAcquireSRWLockExclusive(a1 + 328);
  --*(_DWORD *)(a1 + 168);
  v3 = *(_DWORD *)(a1 + 172);
  if ( v3 )
    *(_DWORD *)(a1 + 172) = v3 - 1;
  result = RtlReleaseSRWLockExclusive(v1);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    return WPP_SF_i(
             *((_QWORD *)WPP_GLOBAL_Control + 2),
             22,
             &WPP_c1878895bf8430c1024ddd3cf0a685b6_Traceguids,
             *(_QWORD *)(a1 + 96));
  return result;
}

```

## disassembly

```asm
0x180014d74  mov     [rsp+arg_0], rbx
0x180014d79  push    rdi
0x180014d7a  sub     rsp, 20h
0x180014d7e  lea     rdi, [rcx+148h]
0x180014d85  mov     rbx, rcx
0x180014d88  mov     rcx, rdi
0x180014d8b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180014d91  dec     dword ptr [rbx+0A8h]
0x180014d97  mov     eax, [rbx+0ACh]
0x180014d9d  test    eax, eax
0x180014d9f  jz      short loc_180014DA9
0x180014da1  dec     eax
0x180014da3  mov     [rbx+0ACh], eax
0x180014da9  mov     rcx, rdi
0x180014dac  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180014db2  mov     rcx, cs:WPP_GLOBAL_Control
0x180014db9  test    byte ptr [rcx+1Ch], 1
0x180014dbd  jnz     short loc_180014DCA
0x180014dbf  mov     rbx, [rsp+28h+arg_0]
0x180014dc4  add     rsp, 20h
0x180014dc8  pop     rdi
0x180014dc9  retn
0x180014dca  cmp     byte ptr [rcx+19h], 4
0x180014dce  jb      short loc_180014DBF
0x180014dd0  mov     r9, [rbx+60h]
0x180014dd4  lea     r8, WPP_c1878895bf8430c1024ddd3cf0a685b6_Traceguids
0x180014ddb  mov     rcx, [rcx+10h]
0x180014ddf  mov     edx, 16h
0x180014de4  call    WPP_SF_i
0x180014de9  jmp     short loc_180014DBF
```
