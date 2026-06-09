# SepSddlGetSidForString

- ea: `0x1400461e4`
- end: `0x140046295`
- name: `SepSddlGetSidForString`
- size: `177`
- prototype: `__int64 __fastcall(wchar_t *Str1)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140045e28`

## callees

- `0x1400461e4`

## import_xrefs

- `ntoskrnl!IoIsWdmVersionAvailable` at `0x14004624a`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x14004624a`
- `ntoskrnl!_wcsnicmp` at `0x14004621e`
- `ntoskrnl!_wcsnicmp` at `0x14004621e`
- `ntoskrnl!SeExports` at `0x140046261`

## pseudocode

```c
__int64 __fastcall SepSddlGetSidForString(wchar_t *Str1, _QWORD *a2, _QWORD *a3)
{
  __int64 i; // rbx
  bool v7; // zf
  __int64 v8; // rax

  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 0xE )
    {
      *a2 = 0;
      return 3221225587LL;
    }
    if ( !_wcsnicmp(Str1, (const wchar_t *)&qword_140038200[3 * i + 1] + 2, HIDWORD(qword_140038200[3 * i + 2])) )
      break;
  }
  v7 = LODWORD(qword_140038200[3 * i + 1]) == 1;
  *a3 = &Str1[HIDWORD(qword_140038200[3 * i + 2])];
  if ( !v7 || IoIsWdmVersionAvailable(1u, 0x20u) )
  {
    _mm_lfence();
    v8 = *(__int64 *)((char *)&SeExports->SeCreateTokenPrivilege + qword_140038200[3 * i]);
  }
  else
  {
    v8 = 0;
  }
  *a2 = v8;
  return 0;
}

```

## disassembly

```asm
0x1400461e4  push    rbx
0x1400461e6  push    rsi
0x1400461e7  push    rdi
0x1400461e8  push    r12
0x1400461ea  push    r14
0x1400461ec  push    r15
0x1400461ee  sub     rsp, 28h
0x1400461f2  mov     r15, r8
0x1400461f5  lea     r12, qword_140038200
0x1400461fc  mov     rdi, rdx
0x1400461ff  mov     r14, rcx
0x140046202  xor     ebx, ebx
0x140046204  cmp     ebx, 0Eh
0x140046207  jnb     short loc_14004627A
0x140046209  lea     rsi, [rbx+rbx*2]
0x14004620d  mov     rcx, r14; Str1
0x140046210  mov     r8d, [r12+rsi*8+14h]; MaxCount
0x140046215  lea     rdx, [r12+0Ch]
0x14004621a  lea     rdx, [rdx+rsi*8]; Str2
0x14004621e  call    cs:__imp__wcsnicmp
0x140046225  nop     dword ptr [rax+rax+00h]
0x14004622a  test    eax, eax
0x14004622c  jz      short loc_140046232
0x14004622e  inc     ebx
0x140046230  jmp     short loc_140046204
0x140046232  cmp     dword ptr [r12+rsi*8+8], 1
0x140046238  mov     eax, [r12+rsi*8+14h]
0x14004623d  lea     rdx, [r14+rax*2]
0x140046241  mov     [r15], rdx
0x140046244  jnz     short loc_14004625E
0x140046246  mov     dl, 20h ; ' '; MinorVersion
0x140046248  mov     cl, 1; MajorVersion
0x14004624a  call    cs:__imp_IoIsWdmVersionAvailable
0x140046251  nop     dword ptr [rax+rax+00h]
0x140046256  test    al, al
0x140046258  jnz     short loc_14004625E
0x14004625a  xor     eax, eax
0x14004625c  jmp     short loc_140046273
0x14004625e  lfence
0x140046261  mov     rax, cs:__imp_SeExports
0x140046268  mov     rdx, [r12+rsi*8]
0x14004626c  mov     rcx, [rax]
0x14004626f  mov     rax, [rdx+rcx]
0x140046273  mov     [rdi], rax
0x140046276  xor     eax, eax
0x140046278  jmp     short loc_140046286
0x14004627a  mov     qword ptr [rdi], 0
0x140046281  mov     eax, 0C0000073h
0x140046286  add     rsp, 28h
0x14004628a  pop     r15
0x14004628c  pop     r14
0x14004628e  pop     r12
0x140046290  pop     rdi
0x140046291  pop     rsi
0x140046292  pop     rbx
0x140046293  retn
```
