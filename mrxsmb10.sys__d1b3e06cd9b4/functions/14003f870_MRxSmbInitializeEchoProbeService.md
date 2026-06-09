# MRxSmbInitializeEchoProbeService

- ea: `0x14003f870`
- end: `0x14003f904`
- name: `MRxSmbInitializeEchoProbeService`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14000f7e8`

## callees

- `0x1400166c0`
- `0x14003f870`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14003f88d`
- `ntoskrnl!ExAllocatePool2` at `0x14003f88d`

## pseudocode

```c
__int64 MRxSmbInitializeEchoProbeService()
{
  _OWORD *Pool2; // rax
  _OWORD *v1; // rbx
  unsigned int v2; // edi

  dword_1400205C0 = 49;
  Pool2 = (_OWORD *)ExAllocatePool2(66, 49, 1665494355);
  P = Pool2;
  v1 = Pool2;
  if ( Pool2 )
  {
    v2 = 0;
    *Pool2 = 0;
    Pool2[1] = 0;
    *(_DWORD *)Pool2 = 1112364031;
    *((_BYTE *)Pool2 + 9) = 24;
    *((_WORD *)Pool2 + 5) = -16317;
    *((_DWORD *)Pool2 + 6) = -16777217;
    *((_BYTE *)Pool2 + 4) = 43;
    *((_BYTE *)Pool2 + 32) = 1;
    memmove((char *)Pool2 + 37, s_EchoData, 0xCu);
    *(_DWORD *)((char *)v1 + 33) = 786433;
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v2;
}

```

## disassembly

```asm
0x14003f870  push    rbx
0x14003f872  push    rbp
0x14003f873  push    rsi
0x14003f874  push    rdi
0x14003f875  sub     rsp, 28h
0x14003f879  mov     edx, 31h ; '1'
0x14003f87e  mov     r8d, 63456D53h
0x14003f884  mov     cs:dword_1400205C0, edx
0x14003f88a  lea     ecx, [rdx+11h]
0x14003f88d  call    cs:__imp_ExAllocatePool2
0x14003f894  nop     dword ptr [rax+rax+00h]
0x14003f899  mov     cs:P, rax
0x14003f8a0  mov     rbx, rax
0x14003f8a3  test    rax, rax
0x14003f8a6  jz      short loc_14003F8F3
0x14003f8a8  xor     edi, edi
0x14003f8aa  lea     rcx, [rax+25h]; void *
0x14003f8ae  xorps   xmm0, xmm0
0x14003f8b1  lea     rdx, s_EchoData; "JlJmIhClBsr"
0x14003f8b8  movups  xmmword ptr [rax], xmm0
0x14003f8bb  movups  xmmword ptr [rax+10h], xmm0
0x14003f8bf  mov     dword ptr [rax], 424D53FFh
0x14003f8c5  lea     ebp, [rdi+1]
0x14003f8c8  mov     byte ptr [rax+9], 18h
0x14003f8cc  lea     r8d, [rdi+0Ch]; Size
0x14003f8d0  mov     word ptr [rax+0Ah], 0C043h
0x14003f8d6  mov     dword ptr [rax+18h], 0FEFFFFFFh
0x14003f8dd  mov     byte ptr [rax+4], 2Bh ; '+'
0x14003f8e1  mov     [rax+20h], bpl
0x14003f8e5  call    memmove
0x14003f8ea  mov     dword ptr [rbx+21h], 0C0001h
0x14003f8f1  jmp     short loc_14003F8F8
0x14003f8f3  mov     edi, 0C000009Ah
0x14003f8f8  mov     eax, edi
0x14003f8fa  add     rsp, 28h
0x14003f8fe  pop     rdi
0x14003f8ff  pop     rsi
0x14003f900  pop     rbp
0x14003f901  pop     rbx
0x14003f902  retn
```
