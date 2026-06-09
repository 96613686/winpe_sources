# Csl::AcquiredPrivileges::~AcquiredPrivileges(void)

- ea: `0x140022e90`
- end: `0x140022ebb`
- name: `??1AcquiredPrivileges@Csl@@QEAA@XZ`
- size: `43`
- prototype: `void __fastcall(Csl::AcquiredPrivileges *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400187e4`

## callees

- `0x140022e90`

## import_xrefs

- `ntdll!RtlReleasePrivilege` at `0x140022ea1`
- `ntdll!RtlReleasePrivilege` at `0x140022ea1`

## pseudocode

```c
void __fastcall Csl::AcquiredPrivileges::~AcquiredPrivileges(void **this)
{
  void *v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    RtlReleasePrivilege(v2);
    *this = 0;
  }
}

```

## disassembly

```asm
0x140022e90  push    rbx
0x140022e92  sub     rsp, 20h
0x140022e96  mov     rbx, rcx
0x140022e99  mov     rcx, [rcx]; ReturnedState
0x140022e9c  test    rcx, rcx
0x140022e9f  jz      short loc_140022EB4
0x140022ea1  call    cs:__imp_RtlReleasePrivilege
0x140022ea8  nop     dword ptr [rax+rax+00h]
0x140022ead  mov     qword ptr [rbx], 0
0x140022eb4  add     rsp, 20h
0x140022eb8  pop     rbx
0x140022eb9  retn
```
