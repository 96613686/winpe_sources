# NegoExtsFreeContext

- ea: `0x14000e344`
- end: `0x14000e3b1`
- name: `NegoExtsFreeContext`
- size: `109`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400221e0`
- `0x140022280`
- `0x140022510`
- `0x14002c664`

## callees

- `0x14000e344`
- `0x140010240`

## import_xrefs

- `ntoskrnl!tolower` at `0x14000e37c`
- `ntoskrnl!tolower` at `0x14000e37c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e399`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e399`

## pseudocode

```c
void __fastcall NegoExtsFreeContext(_QWORD *P)
{
  __int64 v1; // rax
  __int64 v2; // rdi
  __int64 v4; // rcx
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  v1 = P[3];
  v2 = 0;
  if ( v1 )
  {
    v4 = P[4];
    if ( v4 )
    {
      v5 = 0;
      (*(void (__fastcall **)(__int64, __int64 *))(v1 + 8))(v4, &v5);
    }
  }
  do
  {
    *((_BYTE *)P + v2) = tolower(*((unsigned __int8 *)P + v2));
    ++v2;
  }
  while ( v2 != 8 );
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14000e344  mov     [rsp+arg_8], rbx
0x14000e349  push    rdi
0x14000e34a  sub     rsp, 20h
0x14000e34e  mov     rax, [rcx+18h]
0x14000e352  xor     edi, edi
0x14000e354  mov     rbx, rcx
0x14000e357  test    rax, rax
0x14000e35a  jz      short loc_14000E378
0x14000e35c  mov     rcx, [rcx+20h]
0x14000e360  test    rcx, rcx
0x14000e363  jz      short loc_14000E378
0x14000e365  mov     [rsp+28h+arg_0], rdi
0x14000e36a  lea     rdx, [rsp+28h+arg_0]
0x14000e36f  mov     rax, [rax+8]
0x14000e373  call    _guard_dispatch_icall
0x14000e378  movzx   ecx, byte ptr [rbx+rdi]; C
0x14000e37c  call    cs:__imp_tolower
0x14000e383  nop     dword ptr [rax+rax+00h]
0x14000e388  mov     [rbx+rdi], al
0x14000e38b  inc     rdi
0x14000e38e  cmp     rdi, 8
0x14000e392  jnz     short loc_14000E378
0x14000e394  xor     edx, edx; Tag
0x14000e396  mov     rcx, rbx; P
0x14000e399  call    cs:__imp_ExFreePoolWithTag
0x14000e3a0  nop     dword ptr [rax+rax+00h]
0x14000e3a5  mov     rbx, [rsp+28h+arg_8]
0x14000e3aa  add     rsp, 20h
0x14000e3ae  pop     rdi
0x14000e3af  retn
```
