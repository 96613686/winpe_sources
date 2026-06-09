# SepSddlGetSidForString

- ea: `0x14000db24`
- end: `0x14000dbd5`
- name: `SepSddlGetSidForString`
- size: `177`
- prototype: `__int64 __fastcall(wchar_t *Str1)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000d768`

## callees

- `0x14000db24`

## import_xrefs

- `ntoskrnl!IoIsWdmVersionAvailable` at `0x14000db8a`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x14000db8a`
- `ntoskrnl!_wcsnicmp` at `0x14000db5e`
- `ntoskrnl!_wcsnicmp` at `0x14000db5e`
- `ntoskrnl!SeExports` at `0x14000dba1`

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
    if ( !_wcsnicmp(Str1, (const wchar_t *)&qword_14000A100[3 * i + 1] + 2, HIDWORD(qword_14000A100[3 * i + 2])) )
      break;
  }
  v7 = LODWORD(qword_14000A100[3 * i + 1]) == 1;
  *a3 = &Str1[HIDWORD(qword_14000A100[3 * i + 2])];
  if ( !v7 || IoIsWdmVersionAvailable(1u, 0x20u) )
  {
    _mm_lfence();
    v8 = *(__int64 *)((char *)&SeExports->SeCreateTokenPrivilege + qword_14000A100[3 * i]);
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
0x14000db24  push    rbx
0x14000db26  push    rsi
0x14000db27  push    rdi
0x14000db28  push    r12
0x14000db2a  push    r14
0x14000db2c  push    r15
0x14000db2e  sub     rsp, 28h
0x14000db32  mov     r15, r8
0x14000db35  lea     r12, qword_14000A100
0x14000db3c  mov     rdi, rdx
0x14000db3f  mov     r14, rcx
0x14000db42  xor     ebx, ebx
0x14000db44  cmp     ebx, 0Eh
0x14000db47  jnb     short loc_14000DBBA
0x14000db49  lea     rsi, [rbx+rbx*2]
0x14000db4d  mov     rcx, r14; Str1
0x14000db50  mov     r8d, [r12+rsi*8+14h]; MaxCount
0x14000db55  lea     rdx, [r12+0Ch]
0x14000db5a  lea     rdx, [rdx+rsi*8]; Str2
0x14000db5e  call    cs:__imp__wcsnicmp
0x14000db65  nop     dword ptr [rax+rax+00h]
0x14000db6a  test    eax, eax
0x14000db6c  jz      short loc_14000DB72
0x14000db6e  inc     ebx
0x14000db70  jmp     short loc_14000DB44
0x14000db72  cmp     dword ptr [r12+rsi*8+8], 1
0x14000db78  mov     eax, [r12+rsi*8+14h]
0x14000db7d  lea     rdx, [r14+rax*2]
0x14000db81  mov     [r15], rdx
0x14000db84  jnz     short loc_14000DB9E
0x14000db86  mov     dl, 20h ; ' '; MinorVersion
0x14000db88  mov     cl, 1; MajorVersion
0x14000db8a  call    cs:__imp_IoIsWdmVersionAvailable
0x14000db91  nop     dword ptr [rax+rax+00h]
0x14000db96  test    al, al
0x14000db98  jnz     short loc_14000DB9E
0x14000db9a  xor     eax, eax
0x14000db9c  jmp     short loc_14000DBB3
0x14000db9e  lfence
0x14000dba1  mov     rax, cs:__imp_SeExports
0x14000dba8  mov     rdx, [r12+rsi*8]
0x14000dbac  mov     rcx, [rax]
0x14000dbaf  mov     rax, [rdx+rcx]
0x14000dbb3  mov     [rdi], rax
0x14000dbb6  xor     eax, eax
0x14000dbb8  jmp     short loc_14000DBC6
0x14000dbba  mov     qword ptr [rdi], 0
0x14000dbc1  mov     eax, 0C0000073h
0x14000dbc6  add     rsp, 28h
0x14000dbca  pop     r15
0x14000dbcc  pop     r14
0x14000dbce  pop     r12
0x14000dbd0  pop     rdi
0x14000dbd1  pop     rsi
0x14000dbd2  pop     rbx
0x14000dbd3  retn
```
