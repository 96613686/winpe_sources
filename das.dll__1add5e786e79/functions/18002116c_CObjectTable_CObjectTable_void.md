# CObjectTable::~CObjectTable(void)

- ea: `0x18002116c`
- end: `0x1800211c5`
- name: `??1CObjectTable@@QEAA@XZ`
- size: `89`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800154b4`

## callees

- `0x18002116c`

## import_xrefs

- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800211a7`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800211a7`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180021193`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180021193`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002119c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002119c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021187`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021187`

## pseudocode

```c
void __fastcall CObjectTable::~CObjectTable(PSRWLOCK SRWLock)
{
  struct _RTL_AVL_TABLE *v2; // rsi
  PVOID v3; // rbx

  v2 = (struct _RTL_AVL_TABLE *)&SRWLock[1];
  while ( 1 )
  {
    v3 = RtlEnumerateGenericTableAvl(v2, 1u);
    if ( !v3 )
      break;
    AcquireSRWLockExclusive(SRWLock);
    RtlDeleteElementGenericTableAvl(v2, v3);
    ReleaseSRWLockExclusive(SRWLock);
  }
}

```

## disassembly

```asm
0x18002116c  mov     [rsp+arg_0], rbx
0x180021171  mov     [rsp+arg_8], rsi
0x180021176  push    rdi
0x180021177  sub     rsp, 20h
0x18002117b  mov     rdi, rcx
0x18002117e  lea     rsi, [rcx+8]
0x180021182  jmp     short loc_1800211A2
0x180021184  mov     rcx, rdi; SRWLock
0x180021187  call    cs:__imp_AcquireSRWLockExclusive
0x18002118d  mov     rdx, rbx; Buffer
0x180021190  mov     rcx, rsi; Table
0x180021193  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180021199  mov     rcx, rdi; SRWLock
0x18002119c  call    cs:__imp_ReleaseSRWLockExclusive
0x1800211a2  mov     dl, 1; Restart
0x1800211a4  mov     rcx, rsi; Table
0x1800211a7  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1800211ad  mov     rbx, rax
0x1800211b0  test    rax, rax
0x1800211b3  jnz     short loc_180021184
0x1800211b5  mov     rbx, [rsp+28h+arg_0]
0x1800211ba  mov     rsi, [rsp+28h+arg_8]
0x1800211bf  add     rsp, 20h
0x1800211c3  pop     rdi
0x1800211c4  retn
```
