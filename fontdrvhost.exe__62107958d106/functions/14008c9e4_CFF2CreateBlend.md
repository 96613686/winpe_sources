# CFF2CreateBlend

- ea: `0x14008c9e4`
- end: `0x14008ca23`
- name: `CFF2CreateBlend`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140037bb8`

## callees

- `0x14008c9a0`
- `0x14008c9e4`

## pseudocode

```c
__int64 __fastcall CFF2CreateBlend(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rax

  v2 = ((__int64 (*)(void))AdobeCFFMakeBlend)();
  *(_QWORD *)(a1 + 120) = v2;
  if ( !v2 )
    return 3724541952LL;
  v3 = AdobeCFFMakeBlend(a1);
  *(_QWORD *)(a1 + 128) = v3;
  return v3 == 0 ? 0xDE000000 : 0;
}

```

## disassembly

```asm
0x14008c9e4  push    rbx
0x14008c9e6  sub     rsp, 20h
0x14008c9ea  mov     rbx, rcx
0x14008c9ed  call    AdobeCFFMakeBlend
0x14008c9f2  mov     [rbx+78h], rax
0x14008c9f6  test    rax, rax
0x14008c9f9  jz      short loc_14008CA18
0x14008c9fb  mov     rcx, rbx
0x14008c9fe  call    AdobeCFFMakeBlend
0x14008ca03  mov     [rbx+80h], rax
0x14008ca0a  neg     rax
0x14008ca0d  sbb     eax, eax
0x14008ca0f  not     eax
0x14008ca11  and     eax, 0DE000000h
0x14008ca16  jmp     short loc_14008CA1D
0x14008ca18  mov     eax, 0DE000000h
0x14008ca1d  add     rsp, 20h
0x14008ca21  pop     rbx
0x14008ca22  retn
```
