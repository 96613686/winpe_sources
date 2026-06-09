# CDSBaseUpdate::DeleteProperty(tagPROPVARIANT &)

- ea: `0x180014500`
- end: `0x1800145af`
- name: `?DeleteProperty@CDSBaseUpdate@@AEAAXAEAUtagPROPVARIANT@@@Z`
- size: `175`
- prototype: `void __fastcall(CDSBaseUpdate *__hidden this, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180014260`

## callees

- `0x180014500`

## import_xrefs

- `msvcrt!free` at `0x18001453a`
- `msvcrt!free` at `0x180014552`
- `msvcrt!free` at `0x180014564`
- `msvcrt!free` at `0x180014571`
- `msvcrt!free` at `0x18001457e`
- `msvcrt!free` at `0x18001458b`
- `msvcrt!free` at `0x180014598`
- `msvcrt!free` at `0x18001453a`
- `msvcrt!free` at `0x180014552`
- `msvcrt!free` at `0x180014564`
- `msvcrt!free` at `0x180014571`
- `msvcrt!free` at `0x18001457e`
- `msvcrt!free` at `0x18001458b`
- `msvcrt!free` at `0x180014598`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CDSBaseUpdate::DeleteProperty(CDSBaseUpdate *this, struct tagPROPVARIANT *a2)
{
  __int64 i; // rsi

  switch ( a2->vt )
  {
    case 0x1Fu:
      goto LABEL_14;
    case 0x41u:
      goto LABEL_7;
    case 0x48u:
LABEL_14:
      free(a2->puuid);
      return;
    case 0x1013u:
LABEL_7:
      free(a2->bstrblobVal.pData);
      return;
  }
  if ( a2->vt != 4127 )
  {
    if ( a2->vt != 4168 )
      return;
    goto LABEL_7;
  }
  for ( i = 0; (unsigned int)i < a2->lVal; i = (unsigned int)(i + 1) )
    free(*(void **)&a2->bstrblobVal.pData[8 * i]);
  free(a2->bstrblobVal.pData);
}

```

## disassembly

```asm
0x180014500  mov     [rsp+arg_0], rbx
0x180014505  mov     [rsp+arg_8], rsi
0x18001450a  push    rdi
0x18001450b  sub     rsp, 20h
0x18001450f  mov     rbx, rdx
0x180014512  movzx   ecx, word ptr [rdx]
0x180014515  sub     ecx, 1Fh
0x180014518  jz      short loc_180014594
0x18001451a  sub     ecx, 22h ; '"'
0x18001451d  jz      short loc_180014587
0x18001451f  sub     ecx, 7
0x180014522  jz      short loc_18001457A
0x180014524  sub     ecx, 0FCBh
0x18001452a  jz      short loc_18001456D
0x18001452c  sub     ecx, 0Ch
0x18001452f  jz      short loc_180014543
0x180014531  cmp     ecx, 29h ; ')'
0x180014534  jnz     short loc_18001459F
0x180014536  mov     rcx, [rdx+10h]; Block
0x18001453a  call    cs:__imp_free
0x180014540  nop
0x180014541  jmp     short loc_18001459F
0x180014543  xor     esi, esi
0x180014545  cmp     [rdx+8], esi
0x180014548  jbe     short loc_180014560
0x18001454a  mov     rax, [rbx+10h]
0x18001454e  mov     rcx, [rax+rsi*8]; Block
0x180014552  call    cs:__imp_free
0x180014558  nop
0x180014559  inc     esi
0x18001455b  cmp     esi, [rbx+8]
0x18001455e  jb      short loc_18001454A
0x180014560  mov     rcx, [rbx+10h]; Block
0x180014564  call    cs:__imp_free
0x18001456a  nop
0x18001456b  jmp     short loc_18001459F
0x18001456d  mov     rcx, [rdx+10h]; Block
0x180014571  call    cs:__imp_free
0x180014577  nop
0x180014578  jmp     short loc_18001459F
0x18001457a  mov     rcx, [rdx+8]; Block
0x18001457e  call    cs:__imp_free
0x180014584  nop
0x180014585  jmp     short loc_18001459F
0x180014587  mov     rcx, [rdx+10h]; Block
0x18001458b  call    cs:__imp_free
0x180014591  nop
0x180014592  jmp     short loc_18001459F
0x180014594  mov     rcx, [rdx+8]; Block
0x180014598  call    cs:__imp_free
0x18001459e  nop
0x18001459f  mov     rbx, [rsp+28h+arg_0]
0x1800145a4  mov     rsi, [rsp+28h+arg_8]
0x1800145a9  add     rsp, 20h
0x1800145ad  pop     rdi
0x1800145ae  retn
```
