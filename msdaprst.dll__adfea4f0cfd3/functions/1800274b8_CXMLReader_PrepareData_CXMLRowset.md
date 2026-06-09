# CXMLReader::PrepareData(CXMLRowset *)

- ea: `0x1800274b8`
- end: `0x1800275de`
- name: `?PrepareData@CXMLReader@@AEAAXPEAVCXMLRowset@@@Z`
- size: `294`
- prototype: `void __fastcall(CXMLReader *__hidden this, struct CXMLRowset *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800263a4`

## callees

- `0x180003c38`
- `0x1800274b8`

## pseudocode

```c
void __fastcall CXMLReader::PrepareData(CXMLReader *this, struct CXMLRowset *a2)
{
  struct CXMLRowset *v2; // r10
  unsigned int v3; // r11d
  CMetaData *v4; // rsi
  __int64 v5; // rbp
  __int64 v6; // rbx
  __int64 v7; // rdi
  unsigned __int16 v8; // dx
  int v9; // r11d
  _DWORD *v10; // rcx
  char Flags; // al

  v2 = a2;
  *(_DWORD *)(*((unsigned int *)a2 + 55) + *((_QWORD *)a2 + 28) + 28LL) = *((_DWORD *)this + 119);
  if ( *((_DWORD *)this + 119) != 2 )
  {
    v3 = 1;
    if ( *((_DWORD *)a2 + 38) )
    {
      v4 = (struct CXMLRowset *)((char *)a2 + 304);
      do
      {
        v5 = v3;
        v6 = *(_QWORD *)(*((_QWORD *)v2 + 35) + 8LL * v3);
        v7 = *(_QWORD *)(*((_QWORD *)v2 + 36) + 8LL * v3);
        if ( (CMetaData::mdGetFlags(v4, v3 - 1) & 0x2000) != 0 )
        {
          v10 = *(_DWORD **)(*((_QWORD *)v2 + 68) + 8 * v5);
          *(_QWORD *)(v6 + 8) = v10;
          *(_QWORD *)(v7 + 8) = v10;
          *(_QWORD *)v6 = 8;
          *(_QWORD *)v7 = 8;
          *(_DWORD *)(*(_QWORD *)v10 + 612LL) = 0;
          *(_DWORD *)(*(_QWORD *)v10 + 248LL) = 0;
          v10[2] = 0;
        }
        else
        {
          Flags = CMetaData::mdGetFlags(v4, v8);
          *(_DWORD *)v6 = 0;
          *(_QWORD *)(v6 + 8) = 0;
          *(_DWORD *)(v6 + 4) = 0x10000000;
          *(_DWORD *)v7 = 0;
          *(_QWORD *)(v7 + 8) = 0;
          *(_DWORD *)(v7 + 4) = (Flags & 0x60) != 0 ? 3 : 8;
        }
        v3 = v9 + 1;
      }
      while ( v3 <= *((_DWORD *)v2 + 38) );
    }
  }
}

```

## disassembly

```asm
0x1800274b8  push    rbx
0x1800274ba  push    rbp
0x1800274bb  push    rsi
0x1800274bc  push    rdi
0x1800274bd  push    r12
0x1800274bf  push    r14
0x1800274c1  sub     rsp, 28h
0x1800274c5  mov     r9d, [rdx+0DCh]
0x1800274cc  mov     r10, rdx
0x1800274cf  mov     r8, [rdx+0E0h]
0x1800274d6  mov     eax, [rcx+1DCh]
0x1800274dc  mov     [r9+r8+1Ch], eax
0x1800274e1  cmp     dword ptr [rcx+1DCh], 2
0x1800274e8  jz      loc_1800275D0
0x1800274ee  mov     r12d, 1
0x1800274f4  mov     r11d, r12d
0x1800274f7  cmp     [rdx+98h], r12d
0x1800274fe  jb      loc_1800275D0
0x180027504  lea     rsi, [rdx+130h]
0x18002750b  mov     rax, [r10+118h]
0x180027512  mov     rcx, rsi; this
0x180027515  mov     ebp, r11d
0x180027518  mov     rbx, [rax+rbp*8]
0x18002751c  mov     rax, [r10+120h]
0x180027523  mov     rdi, [rax+rbp*8]
0x180027527  movzx   eax, r11w
0x18002752b  sub     ax, r12w
0x18002752f  movzx   edx, ax; unsigned __int16
0x180027532  movzx   r14d, ax
0x180027536  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x18002753b  bt      eax, 0Dh
0x18002753f  jnb     short loc_180027585
0x180027541  mov     rax, [r10+220h]
0x180027548  mov     rcx, [rax+rbp*8]
0x18002754c  mov     [rbx+8], rcx
0x180027550  mov     [rdi+8], rcx
0x180027554  mov     qword ptr [rbx], 8
0x18002755b  mov     qword ptr [rdi], 8
0x180027562  mov     rax, [rcx]
0x180027565  mov     dword ptr [rax+264h], 0
0x18002756f  mov     rax, [rcx]
0x180027572  mov     dword ptr [rax+0F8h], 0
0x18002757c  mov     dword ptr [rcx+8], 0
0x180027583  jmp     short loc_1800275C0
0x180027585  mov     rcx, rsi; this
0x180027588  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x18002758d  and     eax, 60h
0x180027590  mov     dword ptr [rbx], 0
0x180027596  neg     eax
0x180027598  mov     qword ptr [rbx+8], 0
0x1800275a0  mov     dword ptr [rbx+4], 10000000h
0x1800275a7  sbb     eax, eax
0x1800275a9  mov     dword ptr [rdi], 0
0x1800275af  and     eax, 0FFFFFFFBh
0x1800275b2  mov     qword ptr [rdi+8], 0
0x1800275ba  add     eax, 8
0x1800275bd  mov     [rdi+4], eax
0x1800275c0  add     r11d, r12d
0x1800275c3  cmp     r11d, [r10+98h]
0x1800275ca  jbe     loc_18002750B
0x1800275d0  add     rsp, 28h
0x1800275d4  pop     r14
0x1800275d6  pop     r12
0x1800275d8  pop     rdi
0x1800275d9  pop     rsi
0x1800275da  pop     rbp
0x1800275db  pop     rbx
0x1800275dc  retn
```
