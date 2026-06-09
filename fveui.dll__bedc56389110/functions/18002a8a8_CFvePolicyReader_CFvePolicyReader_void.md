# CFvePolicyReader::~CFvePolicyReader(void)

- ea: `0x18002a8a8`
- end: `0x18002a8e2`
- name: `??1CFvePolicyReader@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(CFvePolicyReader *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002af40`

## callees

- `0x18000b978`
- `0x18002a940`
- `0x18002b068`

## pseudocode

```c
void __fastcall CFvePolicyReader::~CFvePolicyReader(CFvePolicyReader *this)
{
  *(_QWORD *)this = &CFvePolicyReader::`vftable';
  CFvePolicyReader::CloseRootPolicyKeys(this);
  CFvePolicyReader::UnloadVolumePolicy(this);
  StringCchCopyW((unsigned __int16 *)this + 17, 0x104u, &qword_1800318B0);
}

```

## disassembly

```asm
0x18002a8a8  push    rbx
0x18002a8aa  sub     rsp, 20h
0x18002a8ae  lea     rax, ??_7CFvePolicyReader@@6B@; const CFvePolicyReader::`vftable'
0x18002a8b5  mov     rbx, rcx
0x18002a8b8  mov     [rcx], rax
0x18002a8bb  call    ?CloseRootPolicyKeys@CFvePolicyReader@@AEAAXXZ; CFvePolicyReader::CloseRootPolicyKeys(void)
0x18002a8c0  mov     rcx, rbx; this
0x18002a8c3  call    ?UnloadVolumePolicy@CFvePolicyReader@@AEAAXXZ; CFvePolicyReader::UnloadVolumePolicy(void)
0x18002a8c8  lea     rcx, [rbx+22h]; unsigned __int16 *
0x18002a8cc  mov     edx, 104h; unsigned __int64
0x18002a8d1  lea     r8, qword_1800318B0; unsigned __int16 *
0x18002a8d8  add     rsp, 20h
0x18002a8dc  pop     rbx
0x18002a8dd  jmp     ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
```
