# SepSddlGetSidForString

- ea: `0x14000fc38`
- end: `0x14000fce4`
- name: `SepSddlGetSidForString`
- size: `172`
- prototype: `__int64 __fastcall(wchar_t *Str1)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000f878`

## callees

- `0x14000fc38`

## import_xrefs

- `ntoskrnl!SeExports` at `0x14000fcbe`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x14000fcaa`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x14000fcaa`
- `ntoskrnl!_wcsnicmp` at `0x14000fc6d`
- `ntoskrnl!_wcsnicmp` at `0x14000fc6d`

## pseudocode

```c
__int64 __fastcall SepSddlGetSidForString(wchar_t *Str1, _QWORD *a2, _QWORD *a3)
{
  __int64 v6; // rbx
  bool v8; // zf
  __int64 v9; // rax

  v6 = 0;
  while ( _wcsnicmp(Str1, (const wchar_t *)&qword_140011290[3 * v6 + 1] + 2, HIDWORD(qword_140011290[3 * v6 + 2])) )
  {
    v6 = (unsigned int)(v6 + 1);
    if ( (unsigned int)v6 >= 0xE )
    {
      *a2 = 0;
      return 3221225587LL;
    }
  }
  v8 = LODWORD(qword_140011290[3 * v6 + 1]) == 1;
  *a3 = &Str1[HIDWORD(qword_140011290[3 * v6 + 2])];
  if ( !v8 || IoIsWdmVersionAvailable(1u, 0x20u) )
    v9 = *(__int64 *)((char *)&SeExports->SeCreateTokenPrivilege + qword_140011290[3 * v6]);
  else
    v9 = 0;
  *a2 = v9;
  return 0;
}

```

## disassembly

```asm
0x14000fc38  push    rbx
0x14000fc3a  push    rsi
0x14000fc3b  push    rdi
0x14000fc3c  push    r12
0x14000fc3e  push    r14
0x14000fc40  push    r15
0x14000fc42  sub     rsp, 28h
0x14000fc46  mov     r15, r8
0x14000fc49  lea     r12, qword_140011290
0x14000fc50  mov     rdi, rdx
0x14000fc53  mov     r14, rcx
0x14000fc56  xor     ebx, ebx
0x14000fc58  lea     rsi, [rbx+rbx*2]
0x14000fc5c  mov     rcx, r14; Str1
0x14000fc5f  mov     r8d, [r12+rsi*8+14h]; MaxCount
0x14000fc64  lea     rdx, [r12+0Ch]
0x14000fc69  lea     rdx, [rdx+rsi*8]; Str2
0x14000fc6d  call    cs:__imp__wcsnicmp
0x14000fc74  nop     dword ptr [rax+rax+00h]
0x14000fc79  test    eax, eax
0x14000fc7b  jz      short loc_14000FC92
0x14000fc7d  inc     ebx
0x14000fc7f  cmp     ebx, 0Eh
0x14000fc82  jb      short loc_14000FC58
0x14000fc84  mov     qword ptr [rdi], 0
0x14000fc8b  mov     eax, 0C0000073h
0x14000fc90  jmp     short loc_14000FCD5
0x14000fc92  cmp     dword ptr [r12+rsi*8+8], 1
0x14000fc98  mov     eax, [r12+rsi*8+14h]
0x14000fc9d  lea     rdx, [r14+rax*2]
0x14000fca1  mov     [r15], rdx
0x14000fca4  jnz     short loc_14000FCBE
0x14000fca6  mov     dl, 20h ; ' '; MinorVersion
0x14000fca8  mov     cl, 1; MajorVersion
0x14000fcaa  call    cs:__imp_IoIsWdmVersionAvailable
0x14000fcb1  nop     dword ptr [rax+rax+00h]
0x14000fcb6  test    al, al
0x14000fcb8  jnz     short loc_14000FCBE
0x14000fcba  xor     eax, eax
0x14000fcbc  jmp     short loc_14000FCD0
0x14000fcbe  mov     rax, cs:__imp_SeExports
0x14000fcc5  mov     rdx, [r12+rsi*8]
0x14000fcc9  mov     rcx, [rax]
0x14000fccc  mov     rax, [rdx+rcx]
0x14000fcd0  mov     [rdi], rax
0x14000fcd3  xor     eax, eax
0x14000fcd5  add     rsp, 28h
0x14000fcd9  pop     r15
0x14000fcdb  pop     r14
0x14000fcdd  pop     r12
0x14000fcdf  pop     rdi
0x14000fce0  pop     rsi
0x14000fce1  pop     rbx
0x14000fce2  retn
```
