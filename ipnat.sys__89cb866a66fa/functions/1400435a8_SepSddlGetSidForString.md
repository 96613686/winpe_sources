# SepSddlGetSidForString

- ea: `0x1400435a8`
- end: `0x140043654`
- name: `SepSddlGetSidForString`
- size: `172`
- prototype: `__int64 __fastcall(wchar_t *Str1)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400431e8`

## callees

- `0x1400435a8`

## import_xrefs

- `ntoskrnl!IoIsWdmVersionAvailable` at `0x14004361a`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x14004361a`
- `ntoskrnl!_wcsnicmp` at `0x1400435dd`
- `ntoskrnl!_wcsnicmp` at `0x1400435dd`
- `ntoskrnl!SeExports` at `0x14004362e`

## pseudocode

```c
__int64 __fastcall SepSddlGetSidForString(wchar_t *Str1, _QWORD *a2, _QWORD *a3)
{
  __int64 v6; // rbx
  bool v8; // zf
  __int64 v9; // rax

  v6 = 0;
  while ( _wcsnicmp(Str1, (const wchar_t *)&qword_1400313E0[3 * v6 + 1] + 2, HIDWORD(qword_1400313E0[3 * v6 + 2])) )
  {
    v6 = (unsigned int)(v6 + 1);
    if ( (unsigned int)v6 >= 0xE )
    {
      *a2 = 0;
      return 3221225587LL;
    }
  }
  v8 = LODWORD(qword_1400313E0[3 * v6 + 1]) == 1;
  *a3 = &Str1[HIDWORD(qword_1400313E0[3 * v6 + 2])];
  if ( !v8 || IoIsWdmVersionAvailable(1u, 0x20u) )
    v9 = *(__int64 *)((char *)&SeExports->SeCreateTokenPrivilege + qword_1400313E0[3 * v6]);
  else
    v9 = 0;
  *a2 = v9;
  return 0;
}

```

## disassembly

```asm
0x1400435a8  push    rbx
0x1400435aa  push    rsi
0x1400435ab  push    rdi
0x1400435ac  push    r12
0x1400435ae  push    r14
0x1400435b0  push    r15
0x1400435b2  sub     rsp, 28h
0x1400435b6  mov     r15, r8
0x1400435b9  lea     r12, qword_1400313E0
0x1400435c0  mov     rdi, rdx
0x1400435c3  mov     r14, rcx
0x1400435c6  xor     ebx, ebx
0x1400435c8  lea     rsi, [rbx+rbx*2]
0x1400435cc  mov     rcx, r14; Str1
0x1400435cf  mov     r8d, [r12+rsi*8+14h]; MaxCount
0x1400435d4  lea     rdx, [r12+0Ch]
0x1400435d9  lea     rdx, [rdx+rsi*8]; Str2
0x1400435dd  call    cs:__imp__wcsnicmp
0x1400435e4  nop     dword ptr [rax+rax+00h]
0x1400435e9  test    eax, eax
0x1400435eb  jz      short loc_140043602
0x1400435ed  inc     ebx
0x1400435ef  cmp     ebx, 0Eh
0x1400435f2  jb      short loc_1400435C8
0x1400435f4  mov     qword ptr [rdi], 0
0x1400435fb  mov     eax, 0C0000073h
0x140043600  jmp     short loc_140043645
0x140043602  cmp     dword ptr [r12+rsi*8+8], 1
0x140043608  mov     eax, [r12+rsi*8+14h]
0x14004360d  lea     rdx, [r14+rax*2]
0x140043611  mov     [r15], rdx
0x140043614  jnz     short loc_14004362E
0x140043616  mov     dl, 20h ; ' '; MinorVersion
0x140043618  mov     cl, 1; MajorVersion
0x14004361a  call    cs:__imp_IoIsWdmVersionAvailable
0x140043621  nop     dword ptr [rax+rax+00h]
0x140043626  test    al, al
0x140043628  jnz     short loc_14004362E
0x14004362a  xor     eax, eax
0x14004362c  jmp     short loc_140043640
0x14004362e  mov     rax, cs:__imp_SeExports
0x140043635  mov     rdx, [r12+rsi*8]
0x140043639  mov     rcx, [rax]
0x14004363c  mov     rax, [rdx+rcx]
0x140043640  mov     [rdi], rax
0x140043643  xor     eax, eax
0x140043645  add     rsp, 28h
0x140043649  pop     r15
0x14004364b  pop     r14
0x14004364d  pop     r12
0x14004364f  pop     rdi
0x140043650  pop     rsi
0x140043651  pop     rbx
0x140043652  retn
```
