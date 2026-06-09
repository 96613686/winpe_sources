# SepSddlGetSidForString

- ea: `0x1400217d4`
- end: `0x14002187e`
- name: `SepSddlGetSidForString`
- size: `170`
- prototype: `__int64 __fastcall(wchar_t *Str1)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140021428`

## callees

- `0x14000302d`
- `0x1400217d4`

## import_xrefs

- `ntoskrnl!SeExports` at `0x14002184a`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x140021833`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x140021833`

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
    if ( !wcsnicmp_0(Str1, (const wchar_t *)&qword_14000C690[3 * i + 1] + 2, HIDWORD(qword_14000C690[3 * i + 2])) )
      break;
  }
  v7 = LODWORD(qword_14000C690[3 * i + 1]) == 1;
  *a3 = &Str1[HIDWORD(qword_14000C690[3 * i + 2])];
  if ( !v7 || IoIsWdmVersionAvailable(1u, 0x20u) )
  {
    _mm_lfence();
    v8 = *(__int64 *)((char *)&SeExports->SeCreateTokenPrivilege + qword_14000C690[3 * i]);
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
0x1400217d4  push    rbx
0x1400217d6  push    rsi
0x1400217d7  push    rdi
0x1400217d8  push    r12
0x1400217da  push    r14
0x1400217dc  push    r15
0x1400217de  sub     rsp, 28h
0x1400217e2  mov     r15, r8
0x1400217e5  lea     r12, qword_14000C690
0x1400217ec  mov     rdi, rdx
0x1400217ef  mov     r14, rcx
0x1400217f2  xor     ebx, ebx
0x1400217f4  cmp     ebx, 0Eh
0x1400217f7  jnb     short loc_140021863
0x1400217f9  lea     rsi, [rbx+rbx*2]
0x1400217fd  mov     rcx, r14; Str1
0x140021800  mov     r8d, [r12+rsi*8+14h]; MaxCount
0x140021805  lea     rdx, [r12+0Ch]
0x14002180a  lea     rdx, [rdx+rsi*8]; Str2
0x14002180e  call    _wcsnicmp_0
0x140021813  test    eax, eax
0x140021815  jz      short loc_14002181B
0x140021817  inc     ebx
0x140021819  jmp     short loc_1400217F4
0x14002181b  cmp     dword ptr [r12+rsi*8+8], 1
0x140021821  mov     eax, [r12+rsi*8+14h]
0x140021826  lea     rdx, [r14+rax*2]
0x14002182a  mov     [r15], rdx
0x14002182d  jnz     short loc_140021847
0x14002182f  mov     dl, 20h ; ' '; MinorVersion
0x140021831  mov     cl, 1; MajorVersion
0x140021833  call    cs:__imp_IoIsWdmVersionAvailable
0x14002183a  nop     dword ptr [rax+rax+00h]
0x14002183f  test    al, al
0x140021841  jnz     short loc_140021847
0x140021843  xor     eax, eax
0x140021845  jmp     short loc_14002185C
0x140021847  lfence
0x14002184a  mov     rax, cs:__imp_SeExports
0x140021851  mov     rdx, [r12+rsi*8]
0x140021855  mov     rcx, [rax]
0x140021858  mov     rax, [rdx+rcx]
0x14002185c  mov     [rdi], rax
0x14002185f  xor     eax, eax
0x140021861  jmp     short loc_14002186F
0x140021863  mov     qword ptr [rdi], 0
0x14002186a  mov     eax, 0C0000073h
0x14002186f  add     rsp, 28h
0x140021873  pop     r15
0x140021875  pop     r14
0x140021877  pop     r12
0x140021879  pop     rdi
0x14002187a  pop     rsi
0x14002187b  pop     rbx
0x14002187c  retn
```
