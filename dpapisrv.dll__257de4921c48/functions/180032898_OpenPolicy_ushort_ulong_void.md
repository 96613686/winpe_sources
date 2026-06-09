# OpenPolicy(ushort *,ulong,void * *)

- ea: `0x180032898`
- end: `0x1800328d3`
- name: `?OpenPolicy@@YAJPEAGKPEAPEAX@Z`
- size: `59`
- prototype: `NTSTATUS __fastcall(unsigned __int16 *, ACCESS_MASK, void **)`
- caller_count: `9`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030f00`
- `0x18003176c`
- `0x180032218`
- `0x180032474`
- `0x1800328dc`
- `0x180032a9c`
- `0x180032e84`
- `0x180034ff8`
- `0x180035134`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800328c1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800328c1`

## pseudocode

```c
NTSTATUS __fastcall OpenPolicy(unsigned __int16 *a1, ACCESS_MASK a2, void **a3)
{
  struct _LSA_OBJECT_ATTRIBUTES v4; // [rsp+30h] [rbp-38h] BYREF

  memset(&v4, 0, sizeof(v4));
  return LsaOpenPolicy(0, &v4, a2, a3);
}

```

## disassembly

```asm
0x180032898  mov     rax, rsp
0x18003289b  sub     rsp, 68h
0x18003289f  xorps   xmm1, xmm1
0x1800328a2  mov     r9, r8; PolicyHandle
0x1800328a5  mov     r8d, edx; DesiredAccess
0x1800328a8  xorps   xmm0, xmm0
0x1800328ab  lea     rdx, [rax-38h]; ObjectAttributes
0x1800328af  xor     ecx, ecx; SystemName
0x1800328b1  movups  xmmword ptr [rax-48h], xmm0
0x1800328b5  movups  xmmword ptr [rax-38h], xmm1
0x1800328b9  movups  xmmword ptr [rax-28h], xmm1
0x1800328bd  movups  xmmword ptr [rax-18h], xmm1
0x1800328c1  call    cs:__imp_LsaOpenPolicy
0x1800328c8  nop     dword ptr [rax+rax+00h]
0x1800328cd  add     rsp, 68h
0x1800328d1  retn
```
