# P<InternalSecurityContext>::~P<InternalSecurityContext>(void)

- ea: `0x18000a4f4`
- end: `0x18000a51c`
- name: `??1?$P@VInternalSecurityContext@@@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a5bc`
- `0x18000dc48`
- `0x1800165d0`
- `0x1800245d4`
- `0x180024d7e`

## callees

- `0x18000a4f4`
- `0x18000a524`

## import_xrefs

- `msvcrt!free` at `0x18000a50f`
- `msvcrt!free` at `0x18000a50f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall P<InternalSecurityContext>::~P<InternalSecurityContext>(__int64 *a1)
{
  __int64 v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    CACSecurityContext::~CACSecurityContext((CACSecurityContext *)(v1 + 8));
    free((void *)v1);
  }
}

```

## disassembly

```asm
0x18000a4f4  push    rbx
0x18000a4f6  sub     rsp, 20h
0x18000a4fa  mov     rbx, [rcx]
0x18000a4fd  test    rbx, rbx
0x18000a500  jz      short loc_18000A516
0x18000a502  lea     rcx, [rbx+8]; this
0x18000a506  call    ??1CACSecurityContext@@QEAA@XZ; CACSecurityContext::~CACSecurityContext(void)
0x18000a50b  nop
0x18000a50c  mov     rcx, rbx; Block
0x18000a50f  call    cs:__imp_free
0x18000a515  nop
0x18000a516  add     rsp, 20h
0x18000a51a  pop     rbx
0x18000a51b  retn
```
