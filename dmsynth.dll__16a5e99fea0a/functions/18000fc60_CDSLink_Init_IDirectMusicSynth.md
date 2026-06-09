# CDSLink::Init(IDirectMusicSynth *)

- ea: `0x18000fc60`
- end: `0x18000fc6b`
- name: `?Init@CDSLink@@UEAAJPEAUIDirectMusicSynth@@@Z`
- size: `11`
- prototype: `__int64 __fastcall(CDSLink *__hidden this, struct IDirectMusicSynth *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CDSLink::Init(CDSLink *this, struct IDirectMusicSynth *a2)
{
  __int64 result; // rax

  *((_QWORD *)this + 3) = a2;
  result = 0;
  *((_QWORD *)this + 6) = this;
  return result;
}

```

## disassembly

```asm
0x18000fc60  mov     [rcx+18h], rdx
0x18000fc64  xor     eax, eax
0x18000fc66  mov     [rcx+30h], rcx
0x18000fc6a  retn
```
