# PcwpDeleteObject(void *)

- ea: `0x14000cad0`
- end: `0x14000cafd`
- name: `?PcwpDeleteObject@@YAXPEAX@Z`
- size: `45`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140009284`
- `0x14000b5b0`
- `0x14000b654`
- `0x14000cad0`

## pseudocode

```c
void __fastcall PcwpDeleteObject(PCW_USER_REGISTRATION *a1)
{
  if ( *(_DWORD *)a1 )
  {
    if ( *(_DWORD *)a1 == 1 )
    {
      PCW_USER_REGISTRATION::~PCW_USER_REGISTRATION(a1);
    }
    else if ( *(_DWORD *)a1 == 2 )
    {
      PCW_NOTIFIER::~PCW_NOTIFIER(a1);
    }
  }
  else
  {
    PCW_QUERY::~PCW_QUERY(a1);
  }
}

```

## disassembly

```asm
0x14000cad0  sub     rsp, 28h
0x14000cad4  mov     edx, [rcx]
0x14000cad6  test    edx, edx
0x14000cad8  jz      short loc_14000CAF2
0x14000cada  sub     edx, 1
0x14000cadd  jz      short loc_14000CAEB
0x14000cadf  cmp     edx, 1
0x14000cae2  jnz     short loc_14000CAF7
0x14000cae4  call    ??1PCW_NOTIFIER@@QEAA@XZ; PCW_NOTIFIER::~PCW_NOTIFIER(void)
0x14000cae9  jmp     short loc_14000CAF7
0x14000caeb  call    ??1PCW_USER_REGISTRATION@@AEAA@XZ; PCW_USER_REGISTRATION::~PCW_USER_REGISTRATION(void)
0x14000caf0  jmp     short loc_14000CAF7
0x14000caf2  call    ??1PCW_QUERY@@AEAA@XZ; PCW_QUERY::~PCW_QUERY(void)
0x14000caf7  add     rsp, 28h
0x14000cafb  retn
```
