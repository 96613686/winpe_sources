# MIME_MAP::~MIME_MAP(void)

- ea: `0x1800019a0`
- end: `0x1800019d5`
- name: `??1MIME_MAP@@UEAA@XZ`
- size: `53`
- prototype: `void __fastcall(MIME_MAP *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800018d0`
- `0x180006550`

## callees

- `0x1800019a0`
- `0x180003fb0`
- `0x1800066b8`

## pseudocode

```c
void __fastcall MIME_MAP::~MIME_MAP(MIME_MAP *this)
{
  MIME_MAP_TABLE *v2; // rcx

  *(_QWORD *)this = &MIME_MAP::`vftable';
  v2 = (MIME_MAP_TABLE *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    MIME_MAP_TABLE::Dereference(v2);
    *((_QWORD *)this + 2) = 0;
  }
  if ( *((_DWORD *)this + 2) )
    MIME_MAP_TABLE::SetGlobalTable(0);
}

```

## disassembly

```asm
0x1800019a0  push    rbx
0x1800019a2  sub     rsp, 20h
0x1800019a6  lea     rax, ??_7MIME_MAP@@6B@; const MIME_MAP::`vftable'
0x1800019ad  mov     rbx, rcx
0x1800019b0  mov     [rcx], rax
0x1800019b3  mov     rcx, [rcx+10h]; this
0x1800019b7  test    rcx, rcx
0x1800019ba  jnz     loc_18000516E
0x1800019c0  cmp     dword ptr [rbx+8], 0
0x1800019c4  jnz     short loc_1800019CC
0x1800019c6  add     rsp, 20h
0x1800019ca  pop     rbx
0x1800019cb  retn
0x1800019cc  xor     ecx, ecx; struct MIME_MAP_TABLE **
0x1800019ce  call    ?SetGlobalTable@MIME_MAP_TABLE@@SAXPEAPEAV1@@Z; MIME_MAP_TABLE::SetGlobalTable(MIME_MAP_TABLE * *)
0x1800019d3  jmp     short loc_1800019C6
0x18000516e  call    ?Dereference@MIME_MAP_TABLE@@QEAAXXZ; MIME_MAP_TABLE::Dereference(void)
0x180005173  mov     qword ptr [rbx+10h], 0
0x18000517b  jmp     loc_1800019C0
```
