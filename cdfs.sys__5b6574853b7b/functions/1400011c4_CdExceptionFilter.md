# CdExceptionFilter

- ea: `0x1400011c4`
- end: `0x14000123a`
- name: `CdExceptionFilter`
- size: `118`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140001240`
- `0x140001474`
- `0x140002250`
- `0x1400028e0`

## callees

- `0x1400011c4`

## import_xrefs

- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1400011f7`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1400011f7`
- `ntoskrnl!KeBugCheckEx` at `0x140001221`
- `ntoskrnl!KeBugCheckEx` at `0x140001221`

## pseudocode

```c
__int64 __fastcall CdExceptionFilter(__int64 a1, ULONG_PTR *a2)
{
  NTSTATUS *v2; // r8
  NTSTATUS v5; // ecx

  v2 = (NTSTATUS *)*a2;
  v5 = *(_DWORD *)*a2;
  if ( v5 == -1073741818 && (unsigned int)v2[6] >= 3 )
    v5 = v2[12];
  if ( a1 )
  {
    if ( *(_DWORD *)(a1 + 24) )
      return 1;
    *(_DWORD *)(a1 + 24) = v5;
  }
  if ( !FsRtlIsNtstatusExpected(v5) )
    KeBugCheckEx(0x26u, 0x40264u, *a2, a2[1], *(_QWORD *)(*a2 + 16));
  return 1;
}

```

## disassembly

```asm
0x1400011c4  push    rbx
0x1400011c6  sub     rsp, 30h
0x1400011ca  mov     r8, [rdx]
0x1400011cd  mov     rax, rcx
0x1400011d0  mov     rbx, rdx
0x1400011d3  mov     ecx, [r8]
0x1400011d6  cmp     ecx, 0C0000006h
0x1400011dc  jnz     short loc_1400011E9
0x1400011de  cmp     dword ptr [r8+18h], 3
0x1400011e3  jb      short loc_1400011E9
0x1400011e5  mov     ecx, [r8+30h]; Exception
0x1400011e9  test    rax, rax
0x1400011ec  jz      short loc_1400011F7
0x1400011ee  cmp     dword ptr [rax+18h], 0
0x1400011f2  jnz     short loc_14000122E
0x1400011f4  mov     [rax+18h], ecx
0x1400011f7  call    cs:__imp_FsRtlIsNtstatusExpected
0x1400011fe  nop     dword ptr [rax+rax+00h]
0x140001203  test    al, al
0x140001205  jnz     short loc_14000122E
0x140001207  mov     r8, [rbx]; BugCheckParameter2
0x14000120a  mov     edx, 40264h; BugCheckParameter1
0x14000120f  mov     r9, [rbx+8]; BugCheckParameter3
0x140001213  mov     ecx, 26h ; '&'; BugCheckCode
0x140001218  mov     rax, [r8+10h]
0x14000121c  mov     [rsp+38h+BugCheckParameter4], rax; BugCheckParameter4
0x140001221  call    cs:__imp_KeBugCheckEx
0x14000122e  mov     eax, 1
0x140001233  add     rsp, 30h
0x140001237  pop     rbx
0x140001238  retn
```
