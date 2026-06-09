# AllNotesOff

- ea: `0x180003ad4`
- end: `0x180003bb1`
- name: `AllNotesOff`
- size: `221`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004ff8`
- `0x180005270`

## callees

- `0x180003ad4`

## import_xrefs

- `WINMM!midiOutShortMsg` at `0x180003b18`
- `WINMM!midiOutShortMsg` at `0x180003b65`
- `WINMM!midiOutShortMsg` at `0x180003b18`
- `WINMM!midiOutShortMsg` at `0x180003b65`

## pseudocode

```c
void __fastcall AllNotesOff(__int64 a1, HMIDIOUT a2)
{
  __int64 v4; // rbx
  unsigned int v5; // edi
  int v6; // ebp
  __int64 v7; // rax
  DWORD dwMsg; // [rsp+58h] [rbp+10h]

  if ( a2 )
  {
    HIBYTE(dwMsg) = 0;
    v4 = 0;
    do
    {
      *(_WORD *)((char *)&dwMsg + 1) = 64;
      LOBYTE(dwMsg) = v4 - 80;
      midiOutShortMsg(a2, dwMsg);
      v5 = 0;
      BYTE2(dwMsg) = 64;
      do
      {
        v6 = 1 << (v5 & 0xF);
        if ( (*(_WORD *)(a1 + 16LL * (unsigned int)v4 + 2 * ((__int64)(int)v5 >> 4) + 708) & (unsigned __int16)v6) != 0 )
        {
          BYTE1(dwMsg) = v5;
          LOBYTE(dwMsg) = v4 + 0x80;
          midiOutShortMsg(a2, dwMsg);
          v7 = v5 >> 4;
          if ( (unsigned int)v7 < 8 )
            *(_WORD *)(a1 + 2 * (v7 + 8 * v4) + 708) &= ~(_WORD)v6;
        }
        ++v5;
      }
      while ( v5 < 0x80 );
      v4 = (unsigned int)(v4 + 1);
    }
    while ( (unsigned int)v4 < 0x10 );
  }
}

```

## disassembly

```asm
0x180003ad4  test    rdx, rdx
0x180003ad7  jz      locret_180003BB0
0x180003add  mov     [rsp+arg_0], rbx
0x180003ae2  mov     [rsp+arg_10], rbp
0x180003ae7  push    rsi
0x180003ae8  push    rdi
0x180003ae9  push    r12
0x180003aeb  push    r14
0x180003aed  push    r15
0x180003aef  sub     rsp, 20h
0x180003af3  mov     rsi, rdx
0x180003af6  mov     [rsp+48h+dwMsg], 0
0x180003afe  mov     r14, rcx
0x180003b01  xor     ebx, ebx
0x180003b03  lea     eax, [rbx-50h]
0x180003b06  mov     word ptr [rsp+48h+dwMsg+1], 40h ; '@'
0x180003b0d  mov     byte ptr [rsp+48h+dwMsg], al
0x180003b11  mov     rcx, rsi; hmo
0x180003b14  mov     edx, [rsp+48h+dwMsg]; dwMsg
0x180003b18  call    cs:__imp_midiOutShortMsg
0x180003b1e  mov     r12d, ebx
0x180003b21  lea     eax, [rbx+80h]
0x180003b27  shl     r12, 4
0x180003b2b  xor     edi, edi
0x180003b2d  add     r12, r14
0x180003b30  mov     byte ptr [rsp+48h+dwMsg], al
0x180003b34  mov     byte ptr [rsp+48h+dwMsg+2], 40h ; '@'
0x180003b39  movsxd  rax, edi
0x180003b3c  mov     ecx, edi
0x180003b3e  sar     rax, 4
0x180003b42  and     ecx, 0Fh
0x180003b45  mov     ebp, 1
0x180003b4a  shl     ebp, cl
0x180003b4c  movzx   eax, word ptr [r12+rax*2+2C4h]
0x180003b55  test    ebp, eax
0x180003b57  jz      short loc_180003B85
0x180003b59  mov     byte ptr [rsp+48h+dwMsg+1], dil
0x180003b5e  mov     rcx, rsi; hmo
0x180003b61  mov     edx, [rsp+48h+dwMsg]; dwMsg
0x180003b65  call    cs:__imp_midiOutShortMsg
0x180003b6b  mov     eax, edi
0x180003b6d  shr     eax, 4
0x180003b70  cmp     eax, 8
0x180003b73  jnb     short loc_180003B85
0x180003b75  lea     rcx, [rax+rbx*8]
0x180003b79  not     bp
0x180003b7c  and     [r14+rcx*2+2C4h], bp
0x180003b85  inc     edi
0x180003b87  cmp     edi, 80h
0x180003b8d  jb      short loc_180003B39
0x180003b8f  inc     ebx
0x180003b91  cmp     ebx, 10h
0x180003b94  jb      loc_180003B03
0x180003b9a  mov     rbx, [rsp+48h+arg_0]
0x180003b9f  mov     rbp, [rsp+48h+arg_10]
0x180003ba4  add     rsp, 20h
0x180003ba8  pop     r15
0x180003baa  pop     r14
0x180003bac  pop     r12
0x180003bae  pop     rdi
0x180003baf  pop     rsi
0x180003bb0  retn
```
