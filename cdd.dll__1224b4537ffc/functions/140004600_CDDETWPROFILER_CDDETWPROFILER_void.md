# CDDETWPROFILER::~CDDETWPROFILER(void)

- ea: `0x140004600`
- end: `0x140004628`
- name: `??1CDDETWPROFILER@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(CDDETWPROFILER *__hidden this)`
- caller_count: `22`
- callee_count: `2`
- tags: ``

## callers

- `0x140002504`
- `0x140003840`
- `0x140004904`
- `0x140005cc0`
- `0x140006a70`
- `0x140007b00`
- `0x14000a254`
- `0x14000d63c`
- `0x1400161b0`
- `0x140017518`
- `0x140019458`
- `0x14001fa08`
- `0x140020e48`
- `0x140022e70`
- `0x1400235c0`
- `0x140023e60`
- `0x14002a758`
- `0x14002ea64`
- `0x14002fbd4`
- `0x140030070`
- `0x140030dc0`
- `0x140031318`

## callees

- `0x140004600`
- `0x1400372d0`

## pseudocode

```c
void __fastcall CDDETWPROFILER::~CDDETWPROFILER(CDDETWPROFILER *this, __int64 a2)
{
  if ( !*((_DWORD *)this + 6) )
  {
    LOBYTE(a2) = 2;
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)this + 264LL))(
      *((unsigned int *)this + 2),
      a2,
      *((_QWORD *)this + 2));
  }
}

```

## disassembly

```asm
0x140004600  sub     rsp, 28h
0x140004604  cmp     dword ptr [rcx+18h], 0
0x140004608  jnz     short loc_140004622
0x14000460a  mov     rax, [rcx]
0x14000460d  mov     dl, 2
0x14000460f  mov     r8, [rcx+10h]
0x140004613  mov     ecx, [rcx+8]
0x140004616  mov     rax, [rax+108h]
0x14000461d  call    _guard_dispatch_icall
0x140004622  add     rsp, 28h
0x140004626  retn
```
