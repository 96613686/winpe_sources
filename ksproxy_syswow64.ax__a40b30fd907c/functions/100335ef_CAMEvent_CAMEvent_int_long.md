# CAMEvent::CAMEvent(int,long *)

- ea: `0x100335ef`
- end: `0x10033623`
- name: `??0CAMEvent@@QAE@HPAJ@Z`
- size: `52`
- prototype: `CAMEvent *__thiscall(CAMEvent *__hidden this, int, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x10014357`

## callees

- `0x100335ef`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x100335fe`
- `KERNEL32!CreateEventW` at `0x100335fe`

## pseudocode

```c
CAMEvent *__thiscall CAMEvent::CAMEvent(CAMEvent *this, int a2, int *a3)
{
  HANDLE EventW; // eax

  EventW = CreateEventW(0, 0, 0, 0);
  this->m_hEvent = EventW;
  if ( !EventW && a3 && *a3 >= 0 )
    *a3 = -2147024882;
  return this;
}

```

## disassembly

```asm
0x100335ef  mov     edi, edi
0x100335f1  push    ebp
0x100335f2  mov     ebp, esp
0x100335f4  push    esi
0x100335f5  push    edi
0x100335f6  xor     edi, edi
0x100335f8  mov     esi, ecx
0x100335fa  push    edi; lpName
0x100335fb  push    edi; bInitialState
0x100335fc  push    edi; bManualReset
0x100335fd  push    edi; lpEventAttributes
0x100335fe  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x10033604  mov     [esi], eax
0x10033606  test    eax, eax
0x10033608  jnz     short loc_1003361B
0x1003360a  mov     eax, [ebp+arg_4]
0x1003360d  test    eax, eax
0x1003360f  jz      short loc_1003361B
0x10033611  cmp     [eax], edi
0x10033613  jl      short loc_1003361B
0x10033615  mov     dword ptr [eax], 8007000Eh
0x1003361b  pop     edi
0x1003361c  mov     eax, esi
0x1003361e  pop     esi
0x1003361f  pop     ebp
0x10033620  retn    8
```
