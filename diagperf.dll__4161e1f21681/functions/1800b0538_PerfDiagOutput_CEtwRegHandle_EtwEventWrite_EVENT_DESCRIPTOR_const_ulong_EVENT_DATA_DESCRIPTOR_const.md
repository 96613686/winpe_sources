# PerfDiagOutput::CEtwRegHandle::EtwEventWrite(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR const *)

- ea: `0x1800b0538`
- end: `0x1800b055c`
- name: `?EtwEventWrite@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEBU_EVENT_DATA_DESCRIPTOR@@@Z`
- size: `36`
- prototype: `__int64 __fastcall(PerfDiagOutput::CEtwRegHandle *__hidden this, const struct _EVENT_DESCRIPTOR *, unsigned int, const struct _EVENT_DATA_DESCRIPTOR *)`
- caller_count: `13`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800af088`
- `0x1800af194`
- `0x1800af2a8`
- `0x1800b1b38`
- `0x1800b1c44`
- `0x1800b1d54`
- `0x1800b1e64`
- `0x1800b5a80`
- `0x1800b6e98`
- `0x1800b6fa4`
- `0x1800c9c38`
- `0x1800c9d48`
- `0x1800c9e58`

## callees

- `0x1800b0538`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800b0545`
- `ntdll!EtwEventWrite` at `0x1800b0545`

## pseudocode

```c
__int64 __fastcall PerfDiagOutput::CEtwRegHandle::EtwEventWrite(
        PerfDiagOutput::CEtwRegHandle *this,
        const struct _EVENT_DESCRIPTOR *a2,
        __int64 a3,
        const struct _EVENT_DATA_DESCRIPTOR *a4)
{
  __int64 result; // rax

  result = EtwEventWrite(*(_QWORD *)this, a2, 1, a4);
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800b0538  sub     rsp, 28h
0x1800b053c  mov     rcx, [rcx]
0x1800b053f  mov     r8d, 1
0x1800b0545  call    cs:__imp_EtwEventWrite
0x1800b054b  test    eax, eax
0x1800b054d  jle     short loc_1800B0557
0x1800b054f  movzx   eax, ax
0x1800b0552  or      eax, 80070000h
0x1800b0557  add     rsp, 28h
0x1800b055b  retn
```
