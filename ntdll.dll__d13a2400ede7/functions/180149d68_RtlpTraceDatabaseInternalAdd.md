# RtlpTraceDatabaseInternalAdd

- ea: `0x180149d68`
- end: `0x180149efb`
- name: `RtlpTraceDatabaseInternalAdd`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180149910`

## callees

- `0x180007060`
- `0x180149cdc`
- `0x180149d68`
- `0x180149f04`
- `0x180164280`
- `0x18016f020`

## string_xrefs

- `0x180149e5e`: `Trace database: failing attempt to save biiiiig trace (size %u) \n`

## pseudocode

```c
char __fastcall RtlpTraceDatabaseInternalAdd(__int64 a1, unsigned int a2, const void *a3, _QWORD *a4)
{
  __int64 v4; // rsi
  __int64 v8; // rax
  __int64 v10; // rcx
  unsigned __int64 v11; // rbp
  unsigned __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // r14
  unsigned int v15; // eax
  unsigned int v16; // ecx
  unsigned int v17; // edx
  _QWORD v18[9]; // [rsp+20h] [rbp-48h] BYREF

  v4 = a2;
  v18[0] = 0;
  if ( a2 <= 0x100 )
  {
    if ( (unsigned __int8)RtlpTraceDatabaseInternalFind(a1, a2, a3, v18) )
    {
      v8 = v18[0];
      ++*(_DWORD *)(v18[0] + 4LL);
      if ( a4 )
        *a4 = v8;
      ++*(_QWORD *)(a1 + 120);
      return 1;
    }
    v10 = *(_QWORD *)(a1 + 16);
    v11 = 8 * v4 + 56;
    if ( v11 > *(_QWORD *)(v10 + 40) - *(_QWORD *)(v10 + 48) )
    {
      v12 = *(_QWORD *)(a1 + 24);
      if ( v12 && *(_QWORD *)(a1 + 32) > v12 || (v13 = RtlpTraceDatabaseAllocate(0x10000), (v10 = v13) == 0) )
      {
LABEL_11:
        if ( a4 )
          *a4 = 0;
        return 0;
      }
      *(_DWORD *)v13 = -1412580421;
      *(_QWORD *)(v13 + 8) = a1;
      *(_QWORD *)(v13 + 24) = 0x10000;
      *(_QWORD *)(v13 + 32) = v13;
      *(_QWORD *)(v13 + 40) = v13 + 0x10000;
      *(_QWORD *)(v13 + 48) = v13 + 56;
      *(_QWORD *)(v13 + 16) = *(_QWORD *)(a1 + 16);
      *(_QWORD *)(a1 + 32) += 0x10000LL;
      *(_QWORD *)(a1 + 16) = v13;
    }
    v14 = *(_QWORD *)(v10 + 48);
    if ( v11 <= *(_QWORD *)(v10 + 40) - v14 )
    {
      *(_QWORD *)(v10 + 48) = v14 + v11;
      *(_DWORD *)v14 = -1412584790;
      *(_DWORD *)(v14 + 8) = v4;
      *(_DWORD *)(v14 + 4) = 1;
      *(_QWORD *)(v14 + 48) = v14 + 56;
      *(_QWORD *)(v14 + 16) = 0;
      *(_QWORD *)(v14 + 24) = 0;
      memmove((void *)(v14 + 56), a3, 8 * v4);
      v15 = (*(__int64 (__fastcall **)(_QWORD, const void *))(a1 + 104))((unsigned int)v4, a3);
      v16 = *(_DWORD *)(a1 + 88);
      v17 = v15 % v16;
      ++*(_DWORD *)(a1 + 4LL * (v17 / (v16 >> 4)) + 128);
      *(_QWORD *)(v14 + 40) = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 8LL * (v15 % v16));
      *(_QWORD *)(*(_QWORD *)(a1 + 96) + 8LL * v17) = v14;
      if ( a4 )
        *a4 = v14;
      ++*(_QWORD *)(a1 + 112);
      return 1;
    }
    DbgPrint("Trace database: failing attempt to save biiiiig trace (size %u) \n", v4);
    goto LABEL_11;
  }
  return 0;
}

```

## disassembly

```asm
0x180149d68  push    rbx
0x180149d6a  push    rbp
0x180149d6b  push    rsi
0x180149d6c  push    rdi
0x180149d6d  push    r13
0x180149d6f  push    r14
0x180149d71  push    r15
0x180149d73  sub     rsp, 30h
0x180149d77  mov     esi, edx
0x180149d79  mov     rdi, r9
0x180149d7c  mov     [rsp+68h+var_48], 0
0x180149d85  mov     r15, r8
0x180149d88  mov     rbx, rcx
0x180149d8b  cmp     edx, 100h
0x180149d91  ja      short loc_180149E09
0x180149d93  lea     r9, [rsp+68h+var_48]
0x180149d98  mov     edx, esi
0x180149d9a  call    RtlpTraceDatabaseInternalFind
0x180149d9f  test    al, al
0x180149da1  jz      short loc_180149DBB
0x180149da3  mov     rax, [rsp+68h+var_48]
0x180149da8  inc     dword ptr [rax+4]
0x180149dab  test    rdi, rdi
0x180149dae  jz      short loc_180149DB3
0x180149db0  mov     [rdi], rax
0x180149db3  inc     qword ptr [rbx+78h]
0x180149db7  mov     al, 1
0x180149db9  jmp     short loc_180149E0B
0x180149dbb  mov     rcx, [rbx+10h]
0x180149dbf  lea     r13, ds:0[rsi*8]
0x180149dc7  lea     rbp, [r13+38h]
0x180149dcb  mov     rax, [rcx+28h]
0x180149dcf  sub     rax, [rcx+30h]
0x180149dd3  cmp     rbp, rax
0x180149dd6  jbe     short loc_180149E4C
0x180149dd8  mov     rax, [rbx+18h]
0x180149ddc  test    rax, rax
0x180149ddf  jz      short loc_180149DE7
0x180149de1  cmp     [rbx+20h], rax
0x180149de5  ja      short loc_180149DFD
0x180149de7  mov     r14d, 10000h
0x180149ded  mov     ecx, r14d
0x180149df0  call    RtlpTraceDatabaseAllocate
0x180149df5  mov     rcx, rax
0x180149df8  test    rax, rax
0x180149dfb  jnz     short loc_180149E1B
0x180149dfd  test    rdi, rdi
0x180149e00  jz      short loc_180149E09
0x180149e02  mov     qword ptr [rdi], 0
0x180149e09  xor     al, al
0x180149e0b  add     rsp, 30h
0x180149e0f  pop     r15
0x180149e11  pop     r14
0x180149e13  pop     r13
0x180149e15  pop     rdi
0x180149e16  pop     rsi
0x180149e17  pop     rbp
0x180149e18  pop     rbx
0x180149e19  retn
0x180149e1b  mov     dword ptr [rax], 0ABCDBBBBh
0x180149e21  mov     [rax+8], rbx
0x180149e25  mov     [rax+18h], r14
0x180149e29  mov     [rax+20h], rcx
0x180149e2d  add     rax, r14
0x180149e30  mov     [rcx+28h], rax
0x180149e34  lea     rax, [rcx+38h]
0x180149e38  mov     [rcx+30h], rax
0x180149e3c  mov     rax, [rbx+10h]
0x180149e40  mov     [rcx+10h], rax
0x180149e44  add     [rbx+20h], r14
0x180149e48  mov     [rbx+10h], rcx
0x180149e4c  mov     r14, [rcx+30h]
0x180149e50  mov     rax, [rcx+28h]
0x180149e54  sub     rax, r14
0x180149e57  cmp     rbp, rax
0x180149e5a  jbe     short loc_180149E6C
0x180149e5c  mov     edx, esi
0x180149e5e  lea     rcx, aTraceDatabaseF; "Trace database: failing attempt to save"...
0x180149e65  call    DbgPrint
0x180149e6a  jmp     short loc_180149DFD
0x180149e6c  lea     rax, [r14+rbp]
0x180149e70  mov     r8, r13; Size
0x180149e73  mov     [rcx+30h], rax
0x180149e77  mov     rdx, r15; Src
0x180149e7a  mov     dword ptr [r14], 0ABCDAAAAh
0x180149e81  lea     rax, [r14+38h]
0x180149e85  mov     [r14+8], esi
0x180149e89  mov     rcx, rax; void *
0x180149e8c  mov     dword ptr [r14+4], 1
0x180149e94  mov     [r14+30h], rax
0x180149e98  mov     qword ptr [r14+10h], 0
0x180149ea0  mov     qword ptr [r14+18h], 0
0x180149ea8  call    memmove
0x180149ead  mov     rax, [rbx+68h]
0x180149eb1  mov     rdx, r15
0x180149eb4  mov     ecx, esi
0x180149eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180149ebb  mov     ecx, [rbx+58h]
0x180149ebe  xor     edx, edx
0x180149ec0  div     ecx
0x180149ec2  shr     ecx, 4
0x180149ec5  mov     r8d, edx
0x180149ec8  xor     edx, edx
0x180149eca  mov     eax, r8d
0x180149ecd  div     ecx
0x180149ecf  inc     dword ptr [rbx+rax*4+80h]
0x180149ed6  mov     rax, [rbx+60h]
0x180149eda  mov     rcx, [rax+r8*8]
0x180149ede  mov     [r14+28h], rcx
0x180149ee2  mov     rax, [rbx+60h]
0x180149ee6  mov     [rax+r8*8], r14
0x180149eea  test    rdi, rdi
0x180149eed  jz      short loc_180149EF2
0x180149eef  mov     [rdi], r14
0x180149ef2  inc     qword ptr [rbx+70h]
0x180149ef6  jmp     loc_180149DB7
```
