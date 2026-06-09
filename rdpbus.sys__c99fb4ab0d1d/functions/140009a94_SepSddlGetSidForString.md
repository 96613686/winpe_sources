# SepSddlGetSidForString

- ea: `0x140009a94`
- end: `0x140009b45`
- name: `SepSddlGetSidForString`
- size: `177`
- prototype: `__int64 __fastcall(wchar_t *Str1)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400096d8`

## callees

- `0x140009a94`

## import_xrefs

- `ntoskrnl!SeExports` at `0x140009b11`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x140009afa`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x140009afa`
- `ntoskrnl!_wcsnicmp` at `0x140009ace`
- `ntoskrnl!_wcsnicmp` at `0x140009ace`

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
    if ( !_wcsnicmp(Str1, (const wchar_t *)&qword_1400050D0[3 * i + 1] + 2, HIDWORD(qword_1400050D0[3 * i + 2])) )
      break;
  }
  v7 = LODWORD(qword_1400050D0[3 * i + 1]) == 1;
  *a3 = &Str1[HIDWORD(qword_1400050D0[3 * i + 2])];
  if ( !v7 || IoIsWdmVersionAvailable(1u, 0x20u) )
  {
    _mm_lfence();
    v8 = *(__int64 *)((char *)&SeExports->SeCreateTokenPrivilege + qword_1400050D0[3 * i]);
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
0x140009a94  push    rbx
0x140009a96  push    rsi
0x140009a97  push    rdi
0x140009a98  push    r12
0x140009a9a  push    r14
0x140009a9c  push    r15
0x140009a9e  sub     rsp, 28h
0x140009aa2  mov     r15, r8
0x140009aa5  lea     r12, qword_1400050D0
0x140009aac  mov     rdi, rdx
0x140009aaf  mov     r14, rcx
0x140009ab2  xor     ebx, ebx
0x140009ab4  cmp     ebx, 0Eh
0x140009ab7  jnb     short loc_140009B2A
0x140009ab9  lea     rsi, [rbx+rbx*2]
0x140009abd  mov     rcx, r14; Str1
0x140009ac0  mov     r8d, [r12+rsi*8+14h]; MaxCount
0x140009ac5  lea     rdx, [r12+0Ch]
0x140009aca  lea     rdx, [rdx+rsi*8]; Str2
0x140009ace  call    cs:__imp__wcsnicmp
0x140009ad5  nop     dword ptr [rax+rax+00h]
0x140009ada  test    eax, eax
0x140009adc  jz      short loc_140009AE2
0x140009ade  inc     ebx
0x140009ae0  jmp     short loc_140009AB4
0x140009ae2  cmp     dword ptr [r12+rsi*8+8], 1
0x140009ae8  mov     eax, [r12+rsi*8+14h]
0x140009aed  lea     rdx, [r14+rax*2]
0x140009af1  mov     [r15], rdx
0x140009af4  jnz     short loc_140009B0E
0x140009af6  mov     dl, 20h ; ' '; MinorVersion
0x140009af8  mov     cl, 1; MajorVersion
0x140009afa  call    cs:__imp_IoIsWdmVersionAvailable
0x140009b01  nop     dword ptr [rax+rax+00h]
0x140009b06  test    al, al
0x140009b08  jnz     short loc_140009B0E
0x140009b0a  xor     eax, eax
0x140009b0c  jmp     short loc_140009B23
0x140009b0e  lfence
0x140009b11  mov     rax, cs:__imp_SeExports
0x140009b18  mov     rdx, [r12+rsi*8]
0x140009b1c  mov     rcx, [rax]
0x140009b1f  mov     rax, [rdx+rcx]
0x140009b23  mov     [rdi], rax
0x140009b26  xor     eax, eax
0x140009b28  jmp     short loc_140009B36
0x140009b2a  mov     qword ptr [rdi], 0
0x140009b31  mov     eax, 0C0000073h
0x140009b36  add     rsp, 28h
0x140009b3a  pop     r15
0x140009b3c  pop     r14
0x140009b3e  pop     r12
0x140009b40  pop     rdi
0x140009b41  pop     rsi
0x140009b42  pop     rbx
0x140009b43  retn
```
