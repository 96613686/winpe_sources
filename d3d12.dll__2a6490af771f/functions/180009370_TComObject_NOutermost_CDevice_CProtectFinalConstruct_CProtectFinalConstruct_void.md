# TComObject<NOutermost::CDevice>::CProtectFinalConstruct::~CProtectFinalConstruct(void)

- ea: `0x180009370`
- end: `0x180009378`
- name: `??1CProtectFinalConstruct@?$TComObject@VCDevice@NOutermost@@@@QEAA@XZ`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180013cff`

## pseudocode

```c
__int64 __fastcall TComObject<NOutermost::CDevice>::CProtectFinalConstruct::~CProtectFinalConstruct(__int64 *a1)
{
  __int64 result; // rax

  result = *a1;
  _InterlockedDecrement((volatile signed __int32 *)(*a1 + 8));
  return result;
}

```

## disassembly

```asm
0x180009370  mov     rax, [rcx]
0x180009373  lock dec dword ptr [rax+8]
0x180009377  retn
```
