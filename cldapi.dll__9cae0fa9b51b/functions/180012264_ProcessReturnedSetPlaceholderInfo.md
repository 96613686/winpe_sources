# ProcessReturnedSetPlaceholderInfo

- ea: `0x180012264`
- end: `0x18001234b`
- name: `ProcessReturnedSetPlaceholderInfo`
- size: `231`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000b248`
- `0x18000e250`

## callees

- `0x180012264`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800122ad`
- `ntdll!RtlNtStatusToDosError` at `0x1800122ad`

## pseudocode

```c
__int64 __fastcall ProcessReturnedSetPlaceholderInfo(__int64 a1, unsigned int a2, __int64 a3, unsigned int a4, int *a5)
{
  int v5; // esi
  __int64 v6; // r14
  unsigned int v7; // ebx
  unsigned __int64 v11; // r13
  NTSTATUS v12; // ecx
  signed int v13; // ecx
  signed int v14; // eax
  __int64 v15; // rdx

  v5 = 0;
  v6 = 0;
  v7 = 0;
  if ( a4 )
  {
    v11 = a2;
    do
    {
      if ( v6 + 80 > v11 )
        break;
      v12 = *(_DWORD *)(v6 + a1 + 64);
      if ( v12 == -1 )
      {
        v13 = -1;
      }
      else
      {
        v14 = RtlNtStatusToDosError(v12);
        v13 = v14;
        if ( v14 > 0 )
          v13 = (unsigned __int16)v14 | 0x80070000;
      }
      v15 = 88LL * v7;
      *(_DWORD *)(v15 + a3 + 72) = v13;
      if ( *(int *)(v6 + a1 + 64) >= 0 )
      {
        *(_OWORD *)(v15 + a3 + 8) = *(_OWORD *)(v6 + a1 + 16);
        *(_OWORD *)(v15 + a3 + 24) = *(_OWORD *)(v6 + a1 + 32);
        *(_QWORD *)(v15 + a3 + 40) = *(_QWORD *)(v6 + a1 + 48);
        *(_QWORD *)(v15 + a3 + 80) = *(_QWORD *)(v6 + a1 + 72);
      }
      if ( v13 < 0 && v5 >= 0 )
        v5 = v13;
      v6 = (unsigned int)(*(_DWORD *)(v6 + a1) + v6);
      ++v7;
    }
    while ( v7 < a4 );
  }
  if ( a5 && *a5 >= 0 )
    *a5 = v5;
  return v7;
}

```

## disassembly

```asm
0x180012264  push    rbx
0x180012266  push    rbp
0x180012267  push    rsi
0x180012268  push    rdi
0x180012269  push    r12
0x18001226b  push    r13
0x18001226d  push    r14
0x18001226f  push    r15
0x180012271  sub     rsp, 28h
0x180012275  xor     esi, esi
0x180012277  xor     r14d, r14d
0x18001227a  xor     ebx, ebx
0x18001227c  mov     r12d, r9d
0x18001227f  mov     r15, r8
0x180012282  mov     rbp, rcx
0x180012285  test    r9d, r9d
0x180012288  jz      loc_180012323
0x18001228e  mov     r13d, edx
0x180012291  lea     rax, [r14+50h]
0x180012295  cmp     rax, r13
0x180012298  ja      loc_180012323
0x18001229e  mov     ecx, [r14+rbp+40h]; Status
0x1800122a3  cmp     ecx, 0FFFFFFFFh
0x1800122a6  jnz     short loc_1800122AD
0x1800122a8  or      ecx, 0FFFFFFFFh
0x1800122ab  jmp     short loc_1800122C8
0x1800122ad  call    cs:__imp_RtlNtStatusToDosError
0x1800122b4  nop     dword ptr [rax+rax+00h]
0x1800122b9  mov     ecx, eax
0x1800122bb  test    eax, eax
0x1800122bd  jle     short loc_1800122C8
0x1800122bf  movzx   ecx, ax
0x1800122c2  or      ecx, 80070000h
0x1800122c8  mov     eax, ebx
0x1800122ca  imul    rdx, rax, 58h ; 'X'
0x1800122ce  mov     [rdx+r15+48h], ecx
0x1800122d3  cmp     dword ptr [r14+rbp+40h], 0
0x1800122d9  jl      short loc_18001230B
0x1800122db  movups  xmm0, xmmword ptr [r14+rbp+10h]
0x1800122e1  movups  xmmword ptr [rdx+r15+8], xmm0
0x1800122e7  movups  xmm1, xmmword ptr [r14+rbp+20h]
0x1800122ed  movups  xmmword ptr [rdx+r15+18h], xmm1
0x1800122f3  movsd   xmm0, qword ptr [r14+rbp+30h]
0x1800122fa  movsd   qword ptr [rdx+r15+28h], xmm0
0x180012301  mov     rax, [r14+rbp+48h]
0x180012306  mov     [rdx+r15+50h], rax
0x18001230b  test    ecx, ecx
0x18001230d  jns     short loc_180012314
0x18001230f  test    esi, esi
0x180012311  cmovns  esi, ecx
0x180012314  add     r14d, [r14+rbp]
0x180012318  inc     ebx
0x18001231a  cmp     ebx, r12d
0x18001231d  jb      loc_180012291
0x180012323  mov     rcx, [rsp+68h+arg_20]
0x18001232b  test    rcx, rcx
0x18001232e  jz      short loc_180012337
0x180012330  cmp     dword ptr [rcx], 0
0x180012333  jl      short loc_180012337
0x180012335  mov     [rcx], esi
0x180012337  mov     eax, ebx
0x180012339  add     rsp, 28h
0x18001233d  pop     r15
0x18001233f  pop     r14
0x180012341  pop     r13
0x180012343  pop     r12
0x180012345  pop     rdi
0x180012346  pop     rsi
0x180012347  pop     rbp
0x180012348  pop     rbx
0x180012349  retn
```
