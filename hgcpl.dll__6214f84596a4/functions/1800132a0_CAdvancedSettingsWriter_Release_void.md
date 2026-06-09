# CAdvancedSettingsWriter::Release(void)

- ea: `0x1800132a0`
- end: `0x1800132d9`
- name: `?Release@CAdvancedSettingsWriter@@UEAAKXZ`
- size: `57`
- prototype: `unsigned int __fastcall(CAdvancedSettingsWriter *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x18000bd88`
- `0x180012c64`
- `0x1800132a0`

## pseudocode

```c
__int64 __fastcall CAdvancedSettingsWriter::Release(CAdvancedSettingsWriter *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v2 && this )
  {
    CAdvancedSettingsWriter::~CAdvancedSettingsWriter(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x1800132a0  mov     [rsp+arg_0], rbx
0x1800132a5  push    rdi
0x1800132a6  sub     rsp, 20h
0x1800132aa  mov     rbx, rcx
0x1800132ad  or      edi, 0FFFFFFFFh
0x1800132b0  lock xadd [rcx+8], edi
0x1800132b5  sub     edi, 1
0x1800132b8  jnz     short loc_1800132CC
0x1800132ba  test    rcx, rcx
0x1800132bd  jz      short loc_1800132CC
0x1800132bf  call    ??1CAdvancedSettingsWriter@@QEAA@XZ; CAdvancedSettingsWriter::~CAdvancedSettingsWriter(void)
0x1800132c4  mov     rcx, rbx; lpMem
0x1800132c7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800132cc  mov     rbx, [rsp+28h+arg_0]
0x1800132d1  mov     eax, edi
0x1800132d3  add     rsp, 20h
0x1800132d7  pop     rdi
0x1800132d8  retn
```
