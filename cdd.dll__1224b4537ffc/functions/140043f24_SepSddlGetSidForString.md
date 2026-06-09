# SepSddlGetSidForString

- ea: `0x140043f24`
- end: `0x140043fd5`
- name: `SepSddlGetSidForString`
- size: `177`
- prototype: `__int64 __fastcall(wchar_t *Str1)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140043b68`

## callees

- `0x140043f24`

## import_xrefs

- `ntoskrnl!SeExports` at `0x140043fa1`
- `ntoskrnl!_wcsnicmp` at `0x140043f5e`
- `ntoskrnl!_wcsnicmp` at `0x140043f5e`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x140043f8a`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x140043f8a`

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
    if ( !_wcsnicmp(Str1, (const wchar_t *)&qword_14003E3A0[3 * i + 1] + 2, HIDWORD(qword_14003E3A0[3 * i + 2])) )
      break;
  }
  v7 = LODWORD(qword_14003E3A0[3 * i + 1]) == 1;
  *a3 = &Str1[HIDWORD(qword_14003E3A0[3 * i + 2])];
  if ( !v7 || IoIsWdmVersionAvailable(1u, 0x20u) )
  {
    _mm_lfence();
    v8 = *(__int64 *)((char *)&SeExports->SeCreateTokenPrivilege + qword_14003E3A0[3 * i]);
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
0x140043f24  push    rbx
0x140043f26  push    rsi
0x140043f27  push    rdi
0x140043f28  push    r12
0x140043f2a  push    r14
0x140043f2c  push    r15
0x140043f2e  sub     rsp, 28h
0x140043f32  mov     r15, r8
0x140043f35  lea     r12, qword_14003E3A0
0x140043f3c  mov     rdi, rdx
0x140043f3f  mov     r14, rcx
0x140043f42  xor     ebx, ebx
0x140043f44  cmp     ebx, 0Eh
0x140043f47  jnb     short loc_140043FBA
0x140043f49  lea     rsi, [rbx+rbx*2]
0x140043f4d  mov     rcx, r14; Str1
0x140043f50  mov     r8d, [r12+rsi*8+14h]; MaxCount
0x140043f55  lea     rdx, [r12+0Ch]
0x140043f5a  lea     rdx, [rdx+rsi*8]; Str2
0x140043f5e  call    cs:__imp__wcsnicmp
0x140043f65  nop     dword ptr [rax+rax+00h]
0x140043f6a  test    eax, eax
0x140043f6c  jz      short loc_140043F72
0x140043f6e  inc     ebx
0x140043f70  jmp     short loc_140043F44
0x140043f72  cmp     dword ptr [r12+rsi*8+8], 1
0x140043f78  mov     eax, [r12+rsi*8+14h]
0x140043f7d  lea     rdx, [r14+rax*2]
0x140043f81  mov     [r15], rdx
0x140043f84  jnz     short loc_140043F9E
0x140043f86  mov     dl, 20h ; ' '; MinorVersion
0x140043f88  mov     cl, 1; MajorVersion
0x140043f8a  call    cs:__imp_IoIsWdmVersionAvailable
0x140043f91  nop     dword ptr [rax+rax+00h]
0x140043f96  test    al, al
0x140043f98  jnz     short loc_140043F9E
0x140043f9a  xor     eax, eax
0x140043f9c  jmp     short loc_140043FB3
0x140043f9e  lfence
0x140043fa1  mov     rax, cs:__imp_SeExports
0x140043fa8  mov     rdx, [r12+rsi*8]
0x140043fac  mov     rcx, [rax]
0x140043faf  mov     rax, [rdx+rcx]
0x140043fb3  mov     [rdi], rax
0x140043fb6  xor     eax, eax
0x140043fb8  jmp     short loc_140043FC6
0x140043fba  mov     qword ptr [rdi], 0
0x140043fc1  mov     eax, 0C0000073h
0x140043fc6  add     rsp, 28h
0x140043fca  pop     r15
0x140043fcc  pop     r14
0x140043fce  pop     r12
0x140043fd0  pop     rdi
0x140043fd1  pop     rsi
0x140043fd2  pop     rbx
0x140043fd3  retn
```
