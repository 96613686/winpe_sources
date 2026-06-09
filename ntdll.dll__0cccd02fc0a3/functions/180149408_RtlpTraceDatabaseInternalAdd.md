# RtlpTraceDatabaseInternalAdd

- ea: `0x180149408`
- end: `0x18014959b`
- name: `RtlpTraceDatabaseInternalAdd`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180148fb0`

## callees

- `0x180007060`
- `0x18014937c`
- `0x180149408`
- `0x1801495a4`
- `0x180163a80`
- `0x18016f020`

## string_xrefs

- `0x1801494fe`: `Trace database: failing attempt to save biiiiig trace (size %u) \n`

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
0x180149408  push    rbx
0x18014940a  push    rbp
0x18014940b  push    rsi
0x18014940c  push    rdi
0x18014940d  push    r13
0x18014940f  push    r14
0x180149411  push    r15
0x180149413  sub     rsp, 30h
0x180149417  mov     esi, edx
0x180149419  mov     rdi, r9
0x18014941c  mov     [rsp+68h+var_48], 0
0x180149425  mov     r15, r8
0x180149428  mov     rbx, rcx
0x18014942b  cmp     edx, 100h
0x180149431  ja      short loc_1801494A9
0x180149433  lea     r9, [rsp+68h+var_48]
0x180149438  mov     edx, esi
0x18014943a  call    RtlpTraceDatabaseInternalFind
0x18014943f  test    al, al
0x180149441  jz      short loc_18014945B
0x180149443  mov     rax, [rsp+68h+var_48]
0x180149448  inc     dword ptr [rax+4]
0x18014944b  test    rdi, rdi
0x18014944e  jz      short loc_180149453
0x180149450  mov     [rdi], rax
0x180149453  inc     qword ptr [rbx+78h]
0x180149457  mov     al, 1
0x180149459  jmp     short loc_1801494AB
0x18014945b  mov     rcx, [rbx+10h]
0x18014945f  lea     r13, ds:0[rsi*8]
0x180149467  lea     rbp, [r13+38h]
0x18014946b  mov     rax, [rcx+28h]
0x18014946f  sub     rax, [rcx+30h]
0x180149473  cmp     rbp, rax
0x180149476  jbe     short loc_1801494EC
0x180149478  mov     rax, [rbx+18h]
0x18014947c  test    rax, rax
0x18014947f  jz      short loc_180149487
0x180149481  cmp     [rbx+20h], rax
0x180149485  ja      short loc_18014949D
0x180149487  mov     r14d, 10000h
0x18014948d  mov     ecx, r14d
0x180149490  call    RtlpTraceDatabaseAllocate
0x180149495  mov     rcx, rax
0x180149498  test    rax, rax
0x18014949b  jnz     short loc_1801494BB
0x18014949d  test    rdi, rdi
0x1801494a0  jz      short loc_1801494A9
0x1801494a2  mov     qword ptr [rdi], 0
0x1801494a9  xor     al, al
0x1801494ab  add     rsp, 30h
0x1801494af  pop     r15
0x1801494b1  pop     r14
0x1801494b3  pop     r13
0x1801494b5  pop     rdi
0x1801494b6  pop     rsi
0x1801494b7  pop     rbp
0x1801494b8  pop     rbx
0x1801494b9  retn
0x1801494bb  mov     dword ptr [rax], 0ABCDBBBBh
0x1801494c1  mov     [rax+8], rbx
0x1801494c5  mov     [rax+18h], r14
0x1801494c9  mov     [rax+20h], rcx
0x1801494cd  add     rax, r14
0x1801494d0  mov     [rcx+28h], rax
0x1801494d4  lea     rax, [rcx+38h]
0x1801494d8  mov     [rcx+30h], rax
0x1801494dc  mov     rax, [rbx+10h]
0x1801494e0  mov     [rcx+10h], rax
0x1801494e4  add     [rbx+20h], r14
0x1801494e8  mov     [rbx+10h], rcx
0x1801494ec  mov     r14, [rcx+30h]
0x1801494f0  mov     rax, [rcx+28h]
0x1801494f4  sub     rax, r14
0x1801494f7  cmp     rbp, rax
0x1801494fa  jbe     short loc_18014950C
0x1801494fc  mov     edx, esi
0x1801494fe  lea     rcx, aTraceDatabaseF; "Trace database: failing attempt to save"...
0x180149505  call    DbgPrint
0x18014950a  jmp     short loc_18014949D
0x18014950c  lea     rax, [r14+rbp]
0x180149510  mov     r8, r13; Size
0x180149513  mov     [rcx+30h], rax
0x180149517  mov     rdx, r15; Src
0x18014951a  mov     dword ptr [r14], 0ABCDAAAAh
0x180149521  lea     rax, [r14+38h]
0x180149525  mov     [r14+8], esi
0x180149529  mov     rcx, rax; void *
0x18014952c  mov     dword ptr [r14+4], 1
0x180149534  mov     [r14+30h], rax
0x180149538  mov     qword ptr [r14+10h], 0
0x180149540  mov     qword ptr [r14+18h], 0
0x180149548  call    memmove
0x18014954d  mov     rax, [rbx+68h]
0x180149551  mov     rdx, r15
0x180149554  mov     ecx, esi
0x180149556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014955b  mov     ecx, [rbx+58h]
0x18014955e  xor     edx, edx
0x180149560  div     ecx
0x180149562  shr     ecx, 4
0x180149565  mov     r8d, edx
0x180149568  xor     edx, edx
0x18014956a  mov     eax, r8d
0x18014956d  div     ecx
0x18014956f  inc     dword ptr [rbx+rax*4+80h]
0x180149576  mov     rax, [rbx+60h]
0x18014957a  mov     rcx, [rax+r8*8]
0x18014957e  mov     [r14+28h], rcx
0x180149582  mov     rax, [rbx+60h]
0x180149586  mov     [rax+r8*8], r14
0x18014958a  test    rdi, rdi
0x18014958d  jz      short loc_180149592
0x18014958f  mov     [rdi], r14
0x180149592  inc     qword ptr [rbx+70h]
0x180149596  jmp     loc_180149457
```
