# NcaSyncedListCreate

- ea: `0x18000b488`
- end: `0x18000b4ec`
- name: `NcaSyncedListCreate`
- size: `100`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ce40`
- `0x18000d720`
- `0x18000e250`
- `0x18000ebf0`
- `0x18000f1b0`
- `0x18000fcf0`

## callees

- `0x180004f34`
- `0x18000b488`
- `0x180018ffc`

## pseudocode

```c
__int64 __fastcall NcaSyncedListCreate(__int64 a1)
{
  int v2; // ebx

  v2 = NcaCriticalSectionCreate((LPCRITICAL_SECTION)a1);
  if ( v2 >= 0 )
  {
    *(_QWORD *)(a1 + 56) = a1 + 48;
    *(_QWORD *)(a1 + 48) = a1 + 48;
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids, (unsigned int)v2);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000b488  mov     [rsp+arg_0], rbx
0x18000b48d  push    rdi
0x18000b48e  sub     rsp, 20h
0x18000b492  mov     rdi, rcx
0x18000b495  call    NcaCriticalSectionCreate
0x18000b49a  mov     ebx, eax
0x18000b49c  test    eax, eax
0x18000b49e  jns     short loc_18000B4D3
0x18000b4a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4a7  lea     rax, WPP_GLOBAL_Control
0x18000b4ae  cmp     rcx, rax
0x18000b4b1  jz      short loc_18000B4DE
0x18000b4b3  test    byte ptr [rcx+1Ch], 1
0x18000b4b7  jz      short loc_18000B4DE
0x18000b4b9  mov     rcx, [rcx+10h]
0x18000b4bd  lea     r8, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x18000b4c4  mov     edx, 18h
0x18000b4c9  mov     r9d, ebx
0x18000b4cc  call    WPP_SF_d
0x18000b4d1  jmp     short loc_18000B4DE
0x18000b4d3  lea     rax, [rdi+30h]
0x18000b4d7  mov     [rax+8], rax
0x18000b4db  mov     [rax], rax
0x18000b4de  mov     eax, ebx
0x18000b4e0  mov     rbx, [rsp+28h+arg_0]
0x18000b4e5  add     rsp, 20h
0x18000b4e9  pop     rdi
0x18000b4ea  retn
```
