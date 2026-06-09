# CAuthenticatorList::Age(_LARGE_INTEGER const &,_LARGE_INTEGER const &)

- ea: `0x1800179f0`
- end: `0x180017a56`
- name: `?Age@CAuthenticatorList@@AEAAKAEBT_LARGE_INTEGER@@0@Z`
- size: `102`
- prototype: `unsigned int __fastcall(PRTL_GENERIC_TABLE Table, const union _LARGE_INTEGER *, const union _LARGE_INTEGER *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180016600`
- `0x180022e2c`

## callees

- `0x1800179f0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180017a43`
- `ntdll!RtlLeaveCriticalSection` at `0x180017a43`
- `ntdll!RtlEnterCriticalSection` at `0x180017a0a`
- `ntdll!RtlEnterCriticalSection` at `0x180017a0a`
- `ntdll!RtlDeleteElementGenericTable` at `0x180017a35`
- `ntdll!RtlDeleteElementGenericTable` at `0x180017a35`
- `ntdll!RtlGetElementGenericTable` at `0x180017a15`
- `ntdll!RtlGetElementGenericTable` at `0x180017a15`

## pseudocode

```c
__int64 __fastcall CAuthenticatorList::Age(
        PRTL_GENERIC_TABLE Table,
        const union _LARGE_INTEGER *a2,
        const union _LARGE_INTEGER *a3)
{
  unsigned int v4; // edi
  LONGLONG *ElementGenericTable; // rax

  v4 = 0;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)&Table[1].InsertOrderList.Blink);
  do
  {
    ElementGenericTable = (LONGLONG *)RtlGetElementGenericTable(Table, 0);
    if ( !ElementGenericTable || *ElementGenericTable >= a2->QuadPart && *ElementGenericTable <= a3->QuadPart )
      break;
    ++v4;
  }
  while ( RtlDeleteElementGenericTable(Table, ElementGenericTable) );
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)&Table[1].InsertOrderList.Blink);
  return v4;
}

```

## disassembly

```asm
0x1800179f0  push    rbx
0x1800179f2  push    rbp
0x1800179f3  push    rsi
0x1800179f4  push    rdi
0x1800179f5  push    r14
0x1800179f7  sub     rsp, 20h
0x1800179fb  mov     rbx, rcx
0x1800179fe  xor     edi, edi
0x180017a00  add     rcx, 58h ; 'X'; CriticalSection
0x180017a04  mov     r14, r8
0x180017a07  mov     rsi, rdx
0x180017a0a  call    cs:__imp_RtlEnterCriticalSection
0x180017a10  xor     edx, edx; I
0x180017a12  mov     rcx, rbx; Table
0x180017a15  call    cs:__imp_RtlGetElementGenericTable
0x180017a1b  test    rax, rax
0x180017a1e  jz      short loc_180017A3F
0x180017a20  mov     rdx, [rax]
0x180017a23  cmp     rdx, [rsi]
0x180017a26  jl      short loc_180017A2D
0x180017a28  cmp     rdx, [r14]
0x180017a2b  jle     short loc_180017A3F
0x180017a2d  mov     rdx, rax; Buffer
0x180017a30  mov     rcx, rbx; Table
0x180017a33  inc     edi
0x180017a35  call    cs:__imp_RtlDeleteElementGenericTable
0x180017a3b  test    al, al
0x180017a3d  jnz     short loc_180017A10
0x180017a3f  lea     rcx, [rbx+58h]; CriticalSection
0x180017a43  call    cs:__imp_RtlLeaveCriticalSection
0x180017a49  mov     eax, edi
0x180017a4b  add     rsp, 20h
0x180017a4f  pop     r14
0x180017a51  pop     rdi
0x180017a52  pop     rsi
0x180017a53  pop     rbp
0x180017a54  pop     rbx
0x180017a55  retn
```
