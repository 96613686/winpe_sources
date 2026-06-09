# OpenMidiPort

- ea: `0x18000145c`
- end: `0x1800014ef`
- name: `OpenMidiPort`
- size: `147`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001810`
- `0x180001bfc`

## callees

- `0x18000145c`
- `0x180005270`

## import_xrefs

- `WINMM!midiOutGetNumDevs` at `0x18000148c`
- `WINMM!midiOutGetNumDevs` at `0x18000148c`

## pseudocode

```c
__int64 __fastcall OpenMidiPort(__int64 a1)
{
  __int64 result; // rax
  int v3; // eax
  int v4; // ecx

  if ( *(_DWORD *)(a1 + 288) == 65533 || midiSeqMessage(*(_QWORD *)(a1 + 256), 0x15u, 0, 0) )
    return 0;
  if ( !midiOutGetNumDevs() )
    return 343;
  v3 = midiSeqMessage(*(_QWORD *)(a1 + 256), 0xCu, *(unsigned int *)(a1 + 288), 0);
  v4 = v3;
  switch ( v3 )
  {
    case 0:
      return 0;
    case 2:
      return 338;
    case 4:
      return 337;
  }
  result = 68;
  if ( v4 != 68 )
    return 343;
  return result;
}

```

## disassembly

```asm
0x18000145c  push    rbx
0x18000145e  sub     rsp, 20h
0x180001462  cmp     dword ptr [rcx+120h], 0FFFDh
0x18000146c  mov     rbx, rcx
0x18000146f  jz      short loc_1800014E7
0x180001471  mov     rcx, [rcx+100h]; dwUser
0x180001478  xor     r9d, r9d
0x18000147b  xor     r8d, r8d
0x18000147e  lea     edx, [r9+15h]
0x180001482  call    midiSeqMessage
0x180001487  test    rax, rax
0x18000148a  jnz     short loc_1800014E7
0x18000148c  call    cs:__imp_midiOutGetNumDevs
0x180001492  test    eax, eax
0x180001494  jnz     short loc_18000149D
0x180001496  mov     eax, 157h
0x18000149b  jmp     short loc_1800014E9
0x18000149d  mov     r8d, [rbx+120h]
0x1800014a4  xor     r9d, r9d
0x1800014a7  mov     rcx, [rbx+100h]; dwUser
0x1800014ae  lea     edx, [r9+0Ch]
0x1800014b2  call    midiSeqMessage
0x1800014b7  mov     rcx, rax
0x1800014ba  test    eax, eax
0x1800014bc  jz      short loc_1800014E7
0x1800014be  cmp     ecx, 2
0x1800014c1  jz      short loc_1800014E0
0x1800014c3  cmp     ecx, 4
0x1800014c6  jz      short loc_1800014D9
0x1800014c8  mov     eax, 44h ; 'D'
0x1800014cd  mov     edx, 157h
0x1800014d2  cmp     ecx, eax
0x1800014d4  cmovnz  eax, edx
0x1800014d7  jmp     short loc_1800014E9
0x1800014d9  mov     eax, 151h
0x1800014de  jmp     short loc_1800014E9
0x1800014e0  mov     eax, 152h
0x1800014e5  jmp     short loc_1800014E9
0x1800014e7  xor     eax, eax
0x1800014e9  add     rsp, 20h
0x1800014ed  pop     rbx
0x1800014ee  retn
```
