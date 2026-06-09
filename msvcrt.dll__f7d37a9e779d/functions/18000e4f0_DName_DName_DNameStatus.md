# DName::DName(DNameStatus)

- ea: `0x18000e4f0`
- end: `0x18000e586`
- name: `??0DName@@QEAA@W4DNameStatus@@@Z`
- size: `150`
- prototype: ``
- caller_count: `23`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e6cc`
- `0x18000f43c`
- `0x18001031c`
- `0x18001067c`
- `0x18001074c`
- `0x180010b98`
- `0x180010c90`
- `0x180011434`
- `0x18001152c`
- `0x18001181c`
- `0x180011bf0`
- `0x180011fb4`
- `0x1800125f8`
- `0x180012fc4`
- `0x180013188`
- `0x1800132bc`
- `0x180013490`
- `0x180013810`
- `0x180013920`
- `0x180013b44`
- `0x180013ec0`
- `0x180014230`
- `0x180014938`

## callees

- `0x18000e4f0`
- `0x1800124dc`

## pseudocode

```c
__int64 __fastcall DName::DName(__int64 a1, int a2)
{
  int v2; // r8d
  _QWORD *Memory; // rax
  int v6; // ecx
  int v7; // ecx

  v2 = a2;
  if ( ((a2 - 1) & 0xFFFFFFFD) != 0 )
    v2 = 0;
  *(_DWORD *)(a1 + 8) = v2 ^ (*(_DWORD *)(a1 + 8) ^ v2) & 0xFFFFFFF0;
  Memory = HeapManager::getMemory((HeapManager *)&qword_18009E1A0, 0x18u, 0);
  if ( Memory )
  {
    Memory[1] = 0;
    *Memory = &DNameStatusNode::`vftable';
    v6 = 0;
    *((_DWORD *)Memory + 4) = a2;
    if ( a2 == 2 )
      v6 = 4;
    *((_DWORD *)Memory + 5) = v6;
  }
  *(_DWORD *)(a1 + 8) &= 0xFFFFF00F;
  v7 = *(_DWORD *)(a1 + 8);
  *(_QWORD *)a1 = Memory;
  if ( !Memory )
    *(_DWORD *)(a1 + 8) = v7 & 0xFFFFFFF0 | 3;
  return a1;
}

```

## disassembly

```asm
0x18000e4f0  mov     [rsp+arg_0], rbx
0x18000e4f5  push    rdi
0x18000e4f6  sub     rsp, 20h
0x18000e4fa  lea     eax, [rdx-1]
0x18000e4fd  mov     r8d, edx
0x18000e500  test    eax, 0FFFFFFFDh
0x18000e505  mov     edi, edx
0x18000e507  mov     eax, 0
0x18000e50c  mov     rbx, rcx
0x18000e50f  cmovnz  r8d, eax
0x18000e513  mov     eax, r8d
0x18000e516  xor     eax, [rcx+8]
0x18000e519  and     eax, 0FFFFFFF0h
0x18000e51c  xor     eax, r8d
0x18000e51f  xor     r8d, r8d; int
0x18000e522  mov     [rcx+8], eax
0x18000e525  lea     rcx, qword_18009E1A0; this
0x18000e52c  lea     edx, [r8+18h]; unsigned __int64
0x18000e530  call    ?getMemory@HeapManager@@QEAAPEAX_KH@Z; HeapManager::getMemory(unsigned __int64,int)
0x18000e535  test    rax, rax
0x18000e538  jz      short loc_18000E55D
0x18000e53a  lea     rcx, ??_7DNameStatusNode@@6B@; const DNameStatusNode::`vftable'
0x18000e541  mov     qword ptr [rax+8], 0
0x18000e549  mov     [rax], rcx
0x18000e54c  xor     ecx, ecx
0x18000e54e  cmp     edi, 2
0x18000e551  mov     [rax+10h], edi
0x18000e554  lea     edx, [rcx+4]
0x18000e557  cmovz   ecx, edx
0x18000e55a  mov     [rax+14h], ecx
0x18000e55d  and     dword ptr [rbx+8], 0FFFFF00Fh
0x18000e564  mov     ecx, [rbx+8]
0x18000e567  mov     [rbx], rax
0x18000e56a  test    rax, rax
0x18000e56d  jnz     short loc_18000E578
0x18000e56f  and     ecx, 0FFFFFFF3h
0x18000e572  or      ecx, 3
0x18000e575  mov     [rbx+8], ecx
0x18000e578  mov     rax, rbx
0x18000e57b  mov     rbx, [rsp+28h+arg_0]
0x18000e580  add     rsp, 20h
0x18000e584  pop     rdi
0x18000e585  retn
```
