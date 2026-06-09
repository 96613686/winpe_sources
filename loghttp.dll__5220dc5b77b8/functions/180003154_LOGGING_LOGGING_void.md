# LOGGING::~LOGGING(void)

- ea: `0x180003154`
- end: `0x18000318c`
- name: `??1LOGGING@@AEAA@XZ`
- size: `56`
- prototype: `void __fastcall(LOGGING *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003290`

## callees

- `0x180003154`
- `0x180003194`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x180003185`

## pseudocode

```c
void __fastcall LOGGING::~LOGGING(LOGGING *this)
{
  CUSTOM_LOG_FIELDS *v2; // rcx

  *((_DWORD *)this + 2) = 1734831980;
  *(_QWORD *)this = &LOGGING::`vftable';
  v2 = (CUSTOM_LOG_FIELDS *)*((_QWORD *)this + 13);
  if ( v2 )
    CUSTOM_LOG_FIELDS::`vector deleting destructor'(v2);
  STRA::~STRA((LOGGING *)((char *)this + 16));
}

```

## disassembly

```asm
0x180003154  push    rbx
0x180003156  sub     rsp, 20h
0x18000315a  lea     rax, ??_7LOGGING@@6B@; const LOGGING::`vftable'
0x180003161  mov     dword ptr [rcx+8], 67676F6Ch
0x180003168  mov     [rcx], rax
0x18000316b  mov     rbx, rcx
0x18000316e  mov     rcx, [rcx+68h]; this
0x180003172  test    rcx, rcx
0x180003175  jz      short loc_18000317C
0x180003177  call    ??_ECUSTOM_LOG_FIELDS@@QEAAPEAXI@Z; CUSTOM_LOG_FIELDS::`vector deleting destructor'(uint)
0x18000317c  lea     rcx, [rbx+10h]
0x180003180  add     rsp, 20h
0x180003184  pop     rbx
0x180003185  jmp     cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
```
