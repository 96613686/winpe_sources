# CUSTOM_ERROR_TABLE::~CUSTOM_ERROR_TABLE(void)

- ea: `0x180002a14`
- end: `0x180002aa3`
- name: `??1CUSTOM_ERROR_TABLE@@AEAA@XZ`
- size: `143`
- prototype: `void __fastcall(CUSTOM_ERROR_TABLE *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002c00`

## callees

- `0x180002a14`
- `0x180002aac`
- `0x180002b1c`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180002a71`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002a7e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002a88`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002a71`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002a7e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002a88`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002a9c`

## pseudocode

```c
void __fastcall CUSTOM_ERROR_TABLE::~CUSTOM_ERROR_TABLE(CUSTOM_ERROR_TABLE *this)
{
  CUSTOM_ERROR_ENTRY **v2; // rdi
  CUSTOM_ERROR_ENTRY *v3; // rcx
  CUSTOM_ERROR_ENTRY *v4; // rax
  CUSTOM_ERROR_ENTRY **v5; // rdx

  *(_QWORD *)this = &CUSTOM_ERROR_TABLE::`vftable';
  v2 = (CUSTOM_ERROR_ENTRY **)((char *)this + 8);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == (CUSTOM_ERROR_ENTRY *)v2 )
      break;
    v4 = *(CUSTOM_ERROR_ENTRY **)v3;
    if ( *(CUSTOM_ERROR_ENTRY **)(*(_QWORD *)v3 + 8LL) != v3
      || (v5 = (CUSTOM_ERROR_ENTRY **)*((_QWORD *)v3 + 1), *v5 != v3) )
    {
      __fastfail(3u);
    }
    *v5 = v4;
    *((_QWORD *)v4 + 1) = v5;
    CUSTOM_ERROR_ENTRY::`scalar deleting destructor'(v3, (unsigned int)v5);
  }
  MIME_MAP::~MIME_MAP((CUSTOM_ERROR_TABLE *)((char *)this + 264));
  STRU::~STRU((CUSTOM_ERROR_TABLE *)((char *)this + 192));
  STRU::~STRU((CUSTOM_ERROR_TABLE *)((char *)this + 136));
  STRU::~STRU((CUSTOM_ERROR_TABLE *)((char *)this + 80));
  STRU::~STRU((CUSTOM_ERROR_TABLE *)((char *)this + 24));
}

```

## disassembly

```asm
0x180002a14  mov     [rsp+arg_0], rbx
0x180002a19  push    rdi
0x180002a1a  sub     rsp, 20h
0x180002a1e  lea     rax, ??_7CUSTOM_ERROR_TABLE@@6B@; const CUSTOM_ERROR_TABLE::`vftable'
0x180002a25  mov     rbx, rcx
0x180002a28  mov     [rcx], rax
0x180002a2b  lea     rdi, [rcx+8]
0x180002a2f  mov     rcx, [rdi]; this
0x180002a32  cmp     rcx, rdi
0x180002a35  jz      short loc_180002A5E
0x180002a37  mov     rax, [rcx]
0x180002a3a  cmp     [rax+8], rcx
0x180002a3e  jnz     short loc_180002A57
0x180002a40  mov     rdx, [rcx+8]; unsigned int
0x180002a44  cmp     [rdx], rcx
0x180002a47  jnz     short loc_180002A57
0x180002a49  mov     [rdx], rax
0x180002a4c  mov     [rax+8], rdx
0x180002a50  call    ??_GCUSTOM_ERROR_ENTRY@@QEAAPEAXI@Z; CUSTOM_ERROR_ENTRY::`scalar deleting destructor'(uint)
0x180002a55  jmp     short loc_180002A2F
0x180002a57  mov     ecx, 3
0x180002a5c  int     29h; Win8: RtlFailFast(ecx)
0x180002a5e  lea     rcx, [rbx+108h]; this
0x180002a65  call    ??1MIME_MAP@@UEAA@XZ; MIME_MAP::~MIME_MAP(void)
0x180002a6a  lea     rcx, [rbx+0C0h]
0x180002a71  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002a77  lea     rcx, [rbx+88h]
0x180002a7e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002a84  lea     rcx, [rbx+50h]
0x180002a88  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002a8e  lea     rcx, [rbx+18h]
0x180002a92  mov     rbx, [rsp+28h+arg_0]
0x180002a97  add     rsp, 20h
0x180002a9b  pop     rdi
0x180002a9c  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
