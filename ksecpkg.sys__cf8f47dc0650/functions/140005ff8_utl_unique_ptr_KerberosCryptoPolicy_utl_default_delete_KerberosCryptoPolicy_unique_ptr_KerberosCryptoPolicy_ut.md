# utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)

- ea: `0x140005ff8`
- end: `0x140006026`
- name: `??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ`
- size: `46`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000561c`
- `0x140005bc4`
- `0x1400075b4`
- `0x140007600`
- `0x1400078f8`
- `0x140007f68`
- `0x140008104`

## callees

- `0x140005ff8`
- `0x1400075b4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140006013`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006013`

## pseudocode

```c
void __fastcall utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(
        KerberosCryptoPolicy **a1)
{
  KerberosCryptoPolicy *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    KerberosCryptoPolicy::~KerberosCryptoPolicy(*a1);
    ExFreePoolWithTag(v1, 0);
  }
}

```

## disassembly

```asm
0x140005ff8  push    rbx
0x140005ffa  sub     rsp, 20h
0x140005ffe  mov     rbx, [rcx]
0x140006001  test    rbx, rbx
0x140006004  jz      short loc_14000601F
0x140006006  mov     rcx, rbx; this
0x140006009  call    ??1KerberosCryptoPolicy@@QEAA@XZ; KerberosCryptoPolicy::~KerberosCryptoPolicy(void)
0x14000600e  xor     edx, edx; Tag
0x140006010  mov     rcx, rbx; P
0x140006013  call    cs:__imp_ExFreePoolWithTag
0x14000601a  nop     dword ptr [rax+rax+00h]
0x14000601f  add     rsp, 20h
0x140006023  pop     rbx
0x140006024  retn
```
