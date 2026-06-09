# NUMBER_SET::Initialize(void)

- ea: `0x18005ee4c`
- end: `0x18005eeba`
- name: `?Initialize@NUMBER_SET@@QEAAEXZ`
- size: `110`
- prototype: `unsigned __int8 __fastcall(NUMBER_SET *__hidden this)`
- caller_count: `11`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001b20`
- `0x18001f4b4`
- `0x18005f2e8`
- `0x18005f480`
- `0x18005f568`
- `0x180062348`
- `0x180063d3c`
- `0x18006821c`
- `0x18006a3c0`
- `0x18006f3f4`
- `0x180073e8c`

## callees

- `0x18005ee4c`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18005ee6c`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18005ee6c`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18005ee77`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18005ee77`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18005eea7`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18005eea7`

## pseudocode

```c
unsigned __int8 __fastcall NUMBER_SET::Initialize(NUMBER_SET *this)
{
  struct _RTL_AVL_TABLE *v1; // rbx
  PVOID v3; // rax

  v1 = (struct _RTL_AVL_TABLE *)((char *)this + 16);
  if ( *((_QWORD *)this + 15) )
  {
    while ( 1 )
    {
      v3 = RtlEnumerateGenericTableAvl(v1, 1u);
      if ( !v3 )
        break;
      RtlDeleteElementGenericTableAvl(v1, v3);
    }
    *((_QWORD *)this + 15) = 0;
  }
  RtlInitializeGenericTableAvl(
    v1,
    NUMBER_SET::CompareNumberExtent,
    NUMBER_SET::AllocateTableEntry,
    NUMBER_SET::FreeTableEntry,
    0);
  return 1;
}

```

## disassembly

```asm
0x18005ee4c  mov     [rsp+arg_0], rbx
0x18005ee51  push    rdi
0x18005ee52  sub     rsp, 30h
0x18005ee56  cmp     qword ptr [rcx+78h], 0
0x18005ee5b  lea     rbx, [rcx+10h]
0x18005ee5f  mov     rdi, rcx
0x18005ee62  jz      short loc_18005EE86
0x18005ee64  jmp     short loc_18005EE72
0x18005ee66  mov     rdx, rax; Buffer
0x18005ee69  mov     rcx, rbx; Table
0x18005ee6c  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18005ee72  mov     dl, 1; Restart
0x18005ee74  mov     rcx, rbx; Table
0x18005ee77  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18005ee7d  test    rax, rax
0x18005ee80  jnz     short loc_18005EE66
0x18005ee82  mov     [rdi+78h], rax
0x18005ee86  lea     r9, ?FreeTableEntry@NUMBER_SET@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x18005ee8d  mov     [rsp+38h+TableContext], 0; TableContext
0x18005ee96  lea     r8, ?AllocateTableEntry@NUMBER_SET@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x18005ee9d  mov     rcx, rbx; Table
0x18005eea0  lea     rdx, ?CompareNumberExtent@NUMBER_SET@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x18005eea7  call    cs:__imp_RtlInitializeGenericTableAvl
0x18005eead  mov     rbx, [rsp+38h+arg_0]
0x18005eeb2  mov     al, 1
0x18005eeb4  add     rsp, 30h
0x18005eeb8  pop     rdi
0x18005eeb9  retn
```
