# MIME_MAP::~MIME_MAP(void)

- ea: `0x180008004`
- end: `0x180008045`
- name: `??1MIME_MAP@@UEAA@XZ`
- size: `65`
- prototype: `void __fastcall(MIME_MAP *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007fc8`
- `0x1800080c0`

## callees

- `0x180004ad0`
- `0x180008004`
- `0x180008480`

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
0x180008004  push    rbx
0x180008006  sub     rsp, 20h
0x18000800a  lea     rax, ??_7MIME_MAP@@6B@; const MIME_MAP::`vftable'
0x180008011  mov     rbx, rcx
0x180008014  mov     [rcx], rax
0x180008017  mov     rcx, [rcx+10h]; this
0x18000801b  test    rcx, rcx
0x18000801e  jz      short loc_18000802D
0x180008020  call    ?Dereference@MIME_MAP_TABLE@@QEAAXXZ; MIME_MAP_TABLE::Dereference(void)
0x180008025  mov     qword ptr [rbx+10h], 0
0x18000802d  cmp     dword ptr [rbx+8], 0
0x180008031  jz      short loc_18000803F
0x180008033  xor     ecx, ecx; struct MIME_MAP_TABLE **
0x180008035  add     rsp, 20h
0x180008039  pop     rbx
0x18000803a  jmp     ?SetGlobalTable@MIME_MAP_TABLE@@SAXPEAPEAV1@@Z; MIME_MAP_TABLE::SetGlobalTable(MIME_MAP_TABLE * *)
0x18000803f  add     rsp, 20h
0x180008043  pop     rbx
0x180008044  retn
```
