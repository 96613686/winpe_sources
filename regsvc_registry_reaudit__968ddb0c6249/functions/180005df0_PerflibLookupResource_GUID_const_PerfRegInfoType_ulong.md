# PerflibLookupResource(_GUID const *,_PerfRegInfoType,ulong)

- ea: `0x180005df0`
- end: `0x180005e62`
- name: `?PerflibLookupResource@@YAPEAURESOURCE_DESCRIPTOR@@PEBU_GUID@@W4_PerfRegInfoType@@K@Z`
- size: `114`
- prototype: `struct RESOURCE_DESCRIPTOR *__fastcall(const struct _GUID *, enum _PerfRegInfoType, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800044a0`

## callees

- `0x180007740`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180005e46`
- `ntdll!RtlReleaseSRWLockShared` at `0x180005e46`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180005e36`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180005e36`
- `ntdll!RtlAcquireSRWLockShared` at `0x180005e24`
- `ntdll!RtlAcquireSRWLockShared` at `0x180005e24`

## pseudocode

```c
struct RESOURCE_DESCRIPTOR *__fastcall PerflibLookupResource(const struct _GUID *a1, enum _PerfRegInfoType a2, int a3)
{
  __int128 v3; // xmm0
  PVOID v4; // rbx
  __int128 Buffer; // [rsp+20h] [rbp-38h] BYREF
  enum _PerfRegInfoType v7; // [rsp+30h] [rbp-28h]
  int v8; // [rsp+34h] [rbp-24h]
  __int64 v9; // [rsp+38h] [rbp-20h]

  v3 = (__int128)*a1;
  v7 = a2;
  v9 = 0;
  Buffer = v3;
  v8 = a3;
  RtlAcquireSRWLockShared(&qword_18002BED0);
  v4 = RtlLookupElementGenericTableAvl(&Table, &Buffer);
  RtlReleaseSRWLockShared(&qword_18002BED0);
  return (struct RESOURCE_DESCRIPTOR *)v4;
}

```

## disassembly

```asm
0x180005df0  push    rbx
0x180005df2  sub     rsp, 50h
0x180005df6  mov     rax, cs:__security_cookie
0x180005dfd  xor     rax, rsp
0x180005e00  mov     [rsp+58h+var_18], rax
0x180005e05  movups  xmm0, xmmword ptr [rcx]
0x180005e08  xor     eax, eax
0x180005e0a  mov     [rsp+58h+var_28], edx
0x180005e0e  lea     rcx, qword_18002BED0
0x180005e15  mov     [rsp+58h+var_20], rax
0x180005e1a  movups  [rsp+58h+Buffer], xmm0
0x180005e1f  mov     [rsp+58h+var_24], r8d
0x180005e24  call    cs:__imp_RtlAcquireSRWLockShared
0x180005e2a  lea     rdx, [rsp+58h+Buffer]; Buffer
0x180005e2f  lea     rcx, Table; Table
0x180005e36  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180005e3c  lea     rcx, qword_18002BED0
0x180005e43  mov     rbx, rax
0x180005e46  call    cs:__imp_RtlReleaseSRWLockShared
0x180005e4c  mov     rax, rbx
0x180005e4f  mov     rcx, [rsp+58h+var_18]
0x180005e54  xor     rcx, rsp; StackCookie
0x180005e57  call    __security_check_cookie
0x180005e5c  add     rsp, 50h
0x180005e60  pop     rbx
0x180005e61  retn
```
