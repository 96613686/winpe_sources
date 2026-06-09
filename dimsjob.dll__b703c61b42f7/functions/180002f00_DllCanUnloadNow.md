# DllCanUnloadNow

- ea: `0x180002f00`
- end: `0x180002f63`
- name: `DllCanUnloadNow`
- size: `99`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002f00`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002f48`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002f56`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002f48`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002f56`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002f29`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002f29`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  char *v0; // rbx
  bool v1; // zf
  char *v2; // rcx

  v0 = (char *)&off_180011028 + SHIDWORD((*off_180011028)[1]);
  RtlAcquireSRWLockExclusive(&v0[*(int *)(*(_QWORD *)v0 + 4LL)]);
  v1 = _InterlockedExchangeAdd(&dword_180011020, 0) == 0;
  v2 = &v0[*(int *)(*(_QWORD *)v0 + 4LL)];
  if ( v1 )
  {
    RtlReleaseSRWLockExclusive(v2);
    return 0;
  }
  else
  {
    RtlReleaseSRWLockExclusive(v2);
    return 1;
  }
}

```

## disassembly

```asm
0x180002f00  push    rbx
0x180002f02  sub     rsp, 20h
0x180002f06  mov     rax, cs:off_180011028
0x180002f0d  lea     rbx, hModule
0x180002f14  add     rbx, 10h
0x180002f18  movsxd  rcx, dword ptr [rax+0Ch]
0x180002f1c  add     rbx, rcx
0x180002f1f  mov     rax, [rbx]
0x180002f22  movsxd  rcx, dword ptr [rax+4]
0x180002f26  add     rcx, rbx
0x180002f29  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180002f2f  xor     ecx, ecx
0x180002f31  lock xadd cs:dword_180011020, ecx
0x180002f39  mov     rax, [rbx]
0x180002f3c  test    ecx, ecx
0x180002f3e  movsxd  rdx, dword ptr [rax+4]
0x180002f42  lea     rcx, [rbx+rdx]
0x180002f46  jnz     short loc_180002F56
0x180002f48  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002f4e  xor     eax, eax
0x180002f50  add     rsp, 20h
0x180002f54  pop     rbx
0x180002f55  retn
0x180002f56  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002f5c  mov     eax, 1
0x180002f61  jmp     short loc_180002F50
```
