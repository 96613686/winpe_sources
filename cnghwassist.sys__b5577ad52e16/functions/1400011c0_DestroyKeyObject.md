# DestroyKeyObject

- ea: `0x1400011c0`
- end: `0x14000123c`
- name: `DestroyKeyObject`
- size: `124`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140001c30`
- `0x140002000`
- `0x140002270`

## callees

- `0x1400011c0`
- `0x140003e00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400011f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400011f3`
- `cng!BCryptDestroyKey` at `0x140001210`
- `cng!BCryptDestroyKey` at `0x140001210`

## pseudocode

```c
__int64 __fastcall DestroyKeyObject(_QWORD *a1)
{
  _QWORD *v1; // rbx
  void *v2; // rcx
  void *v3; // rcx
  __int64 result; // rax

  v1 = a1;
  if ( a1[3] )
  {
    (*(void (**)(void))(g_pHwCipherFunctionTable + 88))();
    v2 = (void *)v1[4];
    v1[3] = 0;
    ExFreePoolWithTag(v2, 0x48676E43u);
    v1[4] = 0;
  }
  v3 = (void *)v1[2];
  if ( v3 )
  {
    BCryptDestroyKey(v3);
    v1[2] = 0;
  }
  result = 112;
  do
  {
    *(_BYTE *)v1 = 0;
    v1 = (_QWORD *)((char *)v1 + 1);
    --result;
  }
  while ( result );
  return result;
}

```

## disassembly

```asm
0x1400011c0  push    rbx
0x1400011c2  sub     rsp, 20h
0x1400011c6  mov     rbx, rcx
0x1400011c9  mov     rcx, [rcx+18h]
0x1400011cd  test    rcx, rcx
0x1400011d0  jz      short loc_140001207
0x1400011d2  mov     rax, cs:g_pHwCipherFunctionTable
0x1400011d9  mov     rax, [rax+58h]
0x1400011dd  call    _guard_dispatch_icall
0x1400011e2  mov     rcx, [rbx+20h]; P
0x1400011e6  mov     edx, 48676E43h; Tag
0x1400011eb  mov     qword ptr [rbx+18h], 0
0x1400011f3  call    cs:__imp_ExFreePoolWithTag
0x1400011fa  nop     dword ptr [rax+rax+00h]
0x1400011ff  mov     qword ptr [rbx+20h], 0
0x140001207  mov     rcx, [rbx+10h]; hKey
0x14000120b  test    rcx, rcx
0x14000120e  jz      short loc_140001224
0x140001210  call    cs:__imp_BCryptDestroyKey
0x140001217  nop     dword ptr [rax+rax+00h]
0x14000121c  mov     qword ptr [rbx+10h], 0
0x140001224  mov     eax, 70h ; 'p'
0x140001229  mov     byte ptr [rbx], 0
0x14000122c  inc     rbx
0x14000122f  sub     rax, 1
0x140001233  jnz     short loc_140001229
0x140001235  add     rsp, 20h
0x140001239  pop     rbx
0x14000123a  retn
```
