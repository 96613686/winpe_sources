# SepSddlGetSidForString

- ea: `0x140011874`
- end: `0x140011925`
- name: `SepSddlGetSidForString`
- size: `177`
- prototype: `__int64 __fastcall(wchar_t *Str1)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400114b8`

## callees

- `0x140011874`

## import_xrefs

- `ntoskrnl!IoIsWdmVersionAvailable` at `0x1400118da`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x1400118da`
- `ntoskrnl!_wcsnicmp` at `0x1400118ae`
- `ntoskrnl!_wcsnicmp` at `0x1400118ae`
- `ntoskrnl!SeExports` at `0x1400118f1`

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
    if ( !_wcsnicmp(Str1, (const wchar_t *)&qword_1400091E0[3 * i + 1] + 2, HIDWORD(qword_1400091E0[3 * i + 2])) )
      break;
  }
  v7 = LODWORD(qword_1400091E0[3 * i + 1]) == 1;
  *a3 = &Str1[HIDWORD(qword_1400091E0[3 * i + 2])];
  if ( !v7 || IoIsWdmVersionAvailable(1u, 0x20u) )
  {
    _mm_lfence();
    v8 = *(__int64 *)((char *)&SeExports->SeCreateTokenPrivilege + qword_1400091E0[3 * i]);
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
0x140011874  push    rbx
0x140011876  push    rsi
0x140011877  push    rdi
0x140011878  push    r12
0x14001187a  push    r14
0x14001187c  push    r15
0x14001187e  sub     rsp, 28h
0x140011882  mov     r15, r8
0x140011885  lea     r12, qword_1400091E0
0x14001188c  mov     rdi, rdx
0x14001188f  mov     r14, rcx
0x140011892  xor     ebx, ebx
0x140011894  cmp     ebx, 0Eh
0x140011897  jnb     short loc_14001190A
0x140011899  lea     rsi, [rbx+rbx*2]
0x14001189d  mov     rcx, r14; Str1
0x1400118a0  mov     r8d, [r12+rsi*8+14h]; MaxCount
0x1400118a5  lea     rdx, [r12+0Ch]
0x1400118aa  lea     rdx, [rdx+rsi*8]; Str2
0x1400118ae  call    cs:__imp__wcsnicmp
0x1400118b5  nop     dword ptr [rax+rax+00h]
0x1400118ba  test    eax, eax
0x1400118bc  jz      short loc_1400118C2
0x1400118be  inc     ebx
0x1400118c0  jmp     short loc_140011894
0x1400118c2  cmp     dword ptr [r12+rsi*8+8], 1
0x1400118c8  mov     eax, [r12+rsi*8+14h]
0x1400118cd  lea     rdx, [r14+rax*2]
0x1400118d1  mov     [r15], rdx
0x1400118d4  jnz     short loc_1400118EE
0x1400118d6  mov     dl, 20h ; ' '; MinorVersion
0x1400118d8  mov     cl, 1; MajorVersion
0x1400118da  call    cs:__imp_IoIsWdmVersionAvailable
0x1400118e1  nop     dword ptr [rax+rax+00h]
0x1400118e6  test    al, al
0x1400118e8  jnz     short loc_1400118EE
0x1400118ea  xor     eax, eax
0x1400118ec  jmp     short loc_140011903
0x1400118ee  lfence
0x1400118f1  mov     rax, cs:__imp_SeExports
0x1400118f8  mov     rdx, [r12+rsi*8]
0x1400118fc  mov     rcx, [rax]
0x1400118ff  mov     rax, [rdx+rcx]
0x140011903  mov     [rdi], rax
0x140011906  xor     eax, eax
0x140011908  jmp     short loc_140011916
0x14001190a  mov     qword ptr [rdi], 0
0x140011911  mov     eax, 0C0000073h
0x140011916  add     rsp, 28h
0x14001191a  pop     r15
0x14001191c  pop     r14
0x14001191e  pop     r12
0x140011920  pop     rdi
0x140011921  pop     rsi
0x140011922  pop     rbx
0x140011923  retn
```
