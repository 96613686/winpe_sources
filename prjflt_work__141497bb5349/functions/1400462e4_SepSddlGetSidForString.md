# SepSddlGetSidForString

- ea: `0x1400462e4`
- end: `0x140046390`
- name: `SepSddlGetSidForString`
- size: `172`
- prototype: `__int64 __fastcall(wchar_t *Str1)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140045f24`

## callees

- `0x1400462e4`

## import_xrefs

- `ntoskrnl!IoIsWdmVersionAvailable` at `0x140046356`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x140046356`
- `ntoskrnl!_wcsnicmp` at `0x140046319`
- `ntoskrnl!_wcsnicmp` at `0x140046319`
- `ntoskrnl!SeExports` at `0x14004636a`

## pseudocode

```c
__int64 __fastcall SepSddlGetSidForString(wchar_t *Str1, _QWORD *a2, _QWORD *a3)
{
  __int64 v6; // rbx
  bool v8; // zf
  __int64 v9; // rax

  v6 = 0;
  while ( _wcsnicmp(Str1, (const wchar_t *)&qword_14001A200[3 * v6 + 1] + 2, HIDWORD(qword_14001A200[3 * v6 + 2])) )
  {
    v6 = (unsigned int)(v6 + 1);
    if ( (unsigned int)v6 >= 0xE )
    {
      *a2 = 0;
      return 3221225587LL;
    }
  }
  v8 = LODWORD(qword_14001A200[3 * v6 + 1]) == 1;
  *a3 = &Str1[HIDWORD(qword_14001A200[3 * v6 + 2])];
  if ( !v8 || IoIsWdmVersionAvailable(1u, 0x20u) )
    v9 = *(__int64 *)((char *)&SeExports->SeCreateTokenPrivilege + qword_14001A200[3 * v6]);
  else
    v9 = 0;
  *a2 = v9;
  return 0;
}

```

## disassembly

```asm
0x1400462e4  push    rbx
0x1400462e6  push    rsi
0x1400462e7  push    rdi
0x1400462e8  push    r12
0x1400462ea  push    r14
0x1400462ec  push    r15
0x1400462ee  sub     rsp, 28h
0x1400462f2  mov     r15, r8
0x1400462f5  lea     r12, qword_14001A200
0x1400462fc  mov     rdi, rdx
0x1400462ff  mov     r14, rcx
0x140046302  xor     ebx, ebx
0x140046304  lea     rsi, [rbx+rbx*2]
0x140046308  mov     rcx, r14; Str1
0x14004630b  mov     r8d, [r12+rsi*8+14h]; MaxCount
0x140046310  lea     rdx, [r12+0Ch]
0x140046315  lea     rdx, [rdx+rsi*8]; Str2
0x140046319  call    cs:__imp__wcsnicmp
0x140046320  nop     dword ptr [rax+rax+00h]
0x140046325  test    eax, eax
0x140046327  jz      short loc_14004633E
0x140046329  inc     ebx
0x14004632b  cmp     ebx, 0Eh
0x14004632e  jb      short loc_140046304
0x140046330  mov     qword ptr [rdi], 0
0x140046337  mov     eax, 0C0000073h
0x14004633c  jmp     short loc_140046381
0x14004633e  cmp     dword ptr [r12+rsi*8+8], 1
0x140046344  mov     eax, [r12+rsi*8+14h]
0x140046349  lea     rdx, [r14+rax*2]
0x14004634d  mov     [r15], rdx
0x140046350  jnz     short loc_14004636A
0x140046352  mov     dl, 20h ; ' '; MinorVersion
0x140046354  mov     cl, 1; MajorVersion
0x140046356  call    cs:__imp_IoIsWdmVersionAvailable
0x14004635d  nop     dword ptr [rax+rax+00h]
0x140046362  test    al, al
0x140046364  jnz     short loc_14004636A
0x140046366  xor     eax, eax
0x140046368  jmp     short loc_14004637C
0x14004636a  mov     rax, cs:__imp_SeExports
0x140046371  mov     rdx, [r12+rsi*8]
0x140046375  mov     rcx, [rax]
0x140046378  mov     rax, [rdx+rcx]
0x14004637c  mov     [rdi], rax
0x14004637f  xor     eax, eax
0x140046381  add     rsp, 28h
0x140046385  pop     r15
0x140046387  pop     r14
0x140046389  pop     r12
0x14004638b  pop     rdi
0x14004638c  pop     rsi
0x14004638d  pop     rbx
0x14004638e  retn
```
