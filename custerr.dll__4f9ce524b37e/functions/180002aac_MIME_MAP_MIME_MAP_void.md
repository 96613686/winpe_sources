# MIME_MAP::~MIME_MAP(void)

- ea: `0x180002aac`
- end: `0x180002ae8`
- name: `??1MIME_MAP@@UEAA@XZ`
- size: `60`
- prototype: `void __fastcall(MIME_MAP *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002a14`
- `0x180002b50`

## callees

- `0x180002aac`
- `0x180002c28`
- `0x180007710`

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
0x180002aac  push    rbx
0x180002aae  sub     rsp, 20h
0x180002ab2  lea     rax, ??_7MIME_MAP@@6B@; const MIME_MAP::`vftable'
0x180002ab9  mov     rbx, rcx
0x180002abc  mov     [rcx], rax
0x180002abf  mov     rcx, [rcx+10h]; this
0x180002ac3  test    rcx, rcx
0x180002ac6  jz      short loc_180002AD5
0x180002ac8  call    ?Dereference@MIME_MAP_TABLE@@QEAAXXZ; MIME_MAP_TABLE::Dereference(void)
0x180002acd  mov     qword ptr [rbx+10h], 0
0x180002ad5  cmp     dword ptr [rbx+8], 0
0x180002ad9  jz      short loc_180002AE2
0x180002adb  xor     ecx, ecx; struct MIME_MAP_TABLE **
0x180002add  call    ?SetGlobalTable@MIME_MAP_TABLE@@SAXPEAPEAV1@@Z; MIME_MAP_TABLE::SetGlobalTable(MIME_MAP_TABLE * *)
0x180002ae2  add     rsp, 20h
0x180002ae6  pop     rbx
0x180002ae7  retn
```
