# ThreadTableClear

- ea: `0x1400032b0`
- end: `0x14000331a`
- name: `ThreadTableClear`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d100`

## callees

- `0x1400032b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400032f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400032f2`

## pseudocode

```c
void ThreadTableClear()
{
  __int64 v0; // rbx
  __int64 *v1; // rdi
  __int64 *v2; // rcx
  __int64 v3; // rax

  v0 = 0;
  do
  {
    v1 = &qword_1400072E8[3 * v0];
    while ( 1 )
    {
      v2 = (__int64 *)*v1;
      if ( (__int64 *)*v1 == v1 )
        break;
      if ( (__int64 *)v2[1] != v1 || (v3 = *v2, *(__int64 **)(*v2 + 8) != v2) )
        __fastfail(3u);
      *v1 = v3;
      *(_QWORD *)(v3 + 8) = v1;
      ExFreePoolWithTag(v2 - 1, 0x72744C46u);
    }
    v0 = (unsigned int)(v0 + 1);
  }
  while ( (unsigned int)v0 < 0x65 );
}

```

## disassembly

```asm
0x1400032b0  mov     [rsp+arg_0], rbx
0x1400032b5  push    rdi
0x1400032b6  sub     rsp, 20h
0x1400032ba  xor     ebx, ebx
0x1400032bc  lea     rcx, [rbx+rbx*2]
0x1400032c0  lea     rax, qword_1400072E8
0x1400032c7  lea     rdi, [rax+rcx*8]
0x1400032cb  mov     rcx, [rdi]
0x1400032ce  cmp     rcx, rdi
0x1400032d1  jz      short loc_140003300
0x1400032d3  cmp     [rcx+8], rdi
0x1400032d7  jnz     short loc_140003313
0x1400032d9  mov     rax, [rcx]
0x1400032dc  cmp     [rax+8], rcx
0x1400032e0  jnz     short loc_140003313
0x1400032e2  mov     [rdi], rax
0x1400032e5  add     rcx, 0FFFFFFFFFFFFFFF8h; P
0x1400032e9  mov     edx, 72744C46h; Tag
0x1400032ee  mov     [rax+8], rdi
0x1400032f2  call    cs:__imp_ExFreePoolWithTag
0x1400032f9  nop     dword ptr [rax+rax+00h]
0x1400032fe  jmp     short loc_1400032CB
0x140003300  inc     ebx
0x140003302  cmp     ebx, 65h ; 'e'
0x140003305  jb      short loc_1400032BC
0x140003307  mov     rbx, [rsp+28h+arg_0]
0x14000330c  add     rsp, 20h
0x140003310  pop     rdi
0x140003311  retn
0x140003313  mov     ecx, 3
0x140003318  int     29h; Win8: RtlFailFast(ecx)
```
