# DhcpFreeLeaseInfoArray

- ea: `0x180001fe0`
- end: `0x180002157`
- name: `DhcpFreeLeaseInfoArray`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001bd0`

## callees

- `0x180001fe0`
- `0x1800127f0`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180001ff6`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180001ff6`
- `api-ms-win-downlevel-kernel32-l1-1-0!HeapFree` at `0x18000210f`
- `api-ms-win-downlevel-kernel32-l1-1-0!HeapFree` at `0x18000210f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180002125`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180002133`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000213e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000214c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180002125`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180002133`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000213e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000214c`

## pseudocode

```c
void __fastcall DhcpFreeLeaseInfoArray(unsigned int a1, LPVOID *a2)
{
  LPWSTR CommandLineW; // rax
  unsigned int v5; // esi
  char *v6; // rbx
  __int64 v7; // rdi
  HLOCAL *v8; // r14
  HLOCAL *v9; // rax
  HLOCAL *v10; // r14
  HLOCAL *v11; // rax

  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_S(1028, 142, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
  }
  if ( a2 && *a2 && a1 )
  {
    v5 = 0;
    do
    {
      v6 = (char *)*a2;
      v7 = 120LL * v5;
      v8 = (HLOCAL *)((char *)*a2 + v7 + 48);
      if ( v8 && *v8 )
      {
        LocalFree(*v8);
        *v8 = 0;
      }
      v9 = (HLOCAL *)&v6[v7 + 64];
      if ( v9 && *v9 )
        LocalFree(*v9);
      *(_OWORD *)&v6[v7 + 32] = 0;
      *(_OWORD *)&v6[v7 + 48] = 0;
      *(_QWORD *)&v6[v7 + 64] = 0;
      v10 = (HLOCAL *)&v6[v7 + 96];
      if ( v10 && *v10 )
      {
        LocalFree(*v10);
        *v10 = 0;
      }
      v11 = (HLOCAL *)&v6[v7 + 112];
      if ( v11 && *v11 )
        LocalFree(*v11);
      ++v5;
      *(_OWORD *)&v6[v7 + 72] = 0;
      *(_OWORD *)&v6[v7 + 88] = 0;
      *(_OWORD *)&v6[v7 + 104] = 0;
    }
    while ( v5 < a1 );
    if ( *a2 )
    {
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, *a2);
      *a2 = 0;
    }
  }
}

```

## disassembly

```asm
0x180001fe0  push    rbp
0x180001fe2  push    r15
0x180001fe4  sub     rsp, 28h
0x180001fe8  mov     r15, rdx
0x180001feb  mov     ebp, ecx
0x180001fed  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180001ff4  jz      short loc_180002015
0x180001ff6  call    cs:__imp_GetCommandLineW
0x180001ffc  mov     edx, 8Eh
0x180002001  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180002008  mov     r9, rax
0x18000200b  mov     ecx, 404h
0x180002010  call    WPP_SF_S
0x180002015  test    r15, r15
0x180002018  jz      loc_18000211D
0x18000201e  cmp     qword ptr [r15], 0
0x180002022  jz      loc_18000211D
0x180002028  test    ebp, ebp
0x18000202a  jz      loc_18000211D
0x180002030  mov     [rsp+38h+arg_8], rsi
0x180002035  mov     [rsp+38h+arg_18], r12
0x18000203a  xor     r12d, r12d
0x18000203d  mov     esi, r12d
0x180002040  test    ebp, ebp
0x180002042  jz      loc_1800020F3
0x180002048  mov     [rsp+38h+arg_0], rbx
0x18000204d  mov     [rsp+38h+arg_10], rdi
0x180002052  mov     [rsp+38h+var_18], r14
0x180002057  mov     rbx, [r15]
0x18000205a  mov     eax, esi
0x18000205c  imul    rdi, rax, 78h ; 'x'
0x180002060  lea     r14, [rbx+30h]
0x180002064  add     r14, rdi
0x180002067  jz      short loc_180002075
0x180002069  mov     rcx, [r14]; hMem
0x18000206c  test    rcx, rcx
0x18000206f  jnz     loc_180002125
0x180002075  lea     rax, [rbx+40h]
0x180002079  add     rax, rdi
0x18000207c  jz      short loc_18000208A
0x18000207e  mov     rcx, [rax]; hMem
0x180002081  test    rcx, rcx
0x180002084  jnz     loc_180002133
0x18000208a  xorps   xmm0, xmm0
0x18000208d  lea     r14, [rbx+60h]
0x180002091  xor     eax, eax
0x180002093  movups  xmmword ptr [rdi+rbx+20h], xmm0
0x180002098  movups  xmmword ptr [rdi+rbx+30h], xmm0
0x18000209d  mov     [rdi+rbx+40h], rax
0x1800020a2  add     r14, rdi
0x1800020a5  jz      short loc_1800020B3
0x1800020a7  mov     rcx, [r14]; hMem
0x1800020aa  test    rcx, rcx
0x1800020ad  jnz     loc_18000213E
0x1800020b3  lea     rax, [rbx+70h]
0x1800020b7  add     rax, rdi
0x1800020ba  jz      short loc_1800020C8
0x1800020bc  mov     rcx, [rax]; hMem
0x1800020bf  test    rcx, rcx
0x1800020c2  jnz     loc_18000214C
0x1800020c8  xorps   xmm0, xmm0
0x1800020cb  inc     esi
0x1800020cd  movups  xmmword ptr [rdi+rbx+48h], xmm0
0x1800020d2  movups  xmmword ptr [rdi+rbx+58h], xmm0
0x1800020d7  movups  xmmword ptr [rdi+rbx+68h], xmm0
0x1800020dc  cmp     esi, ebp
0x1800020de  jb      loc_180002057
0x1800020e4  mov     r14, [rsp+38h+var_18]
0x1800020e9  mov     rdi, [rsp+38h+arg_10]
0x1800020ee  mov     rbx, [rsp+38h+arg_0]
0x1800020f3  mov     r8, [r15]; lpMem
0x1800020f6  mov     rsi, [rsp+38h+arg_8]
0x1800020fb  test    r8, r8
0x1800020fe  jz      short loc_180002118
0x180002100  mov     rcx, gs:60h
0x180002109  xor     edx, edx; dwFlags
0x18000210b  mov     rcx, [rcx+30h]; hHeap
0x18000210f  call    cs:__imp_HeapFree
0x180002115  mov     [r15], r12
0x180002118  mov     r12, [rsp+38h+arg_18]
0x18000211d  add     rsp, 28h
0x180002121  pop     r15
0x180002123  pop     rbp
0x180002124  retn
0x180002125  call    cs:__imp_LocalFree
0x18000212b  mov     [r14], r12
0x18000212e  jmp     loc_180002075
0x180002133  call    cs:__imp_LocalFree
0x180002139  jmp     loc_18000208A
0x18000213e  call    cs:__imp_LocalFree
0x180002144  mov     [r14], r12
0x180002147  jmp     loc_1800020B3
0x18000214c  call    cs:__imp_LocalFree
0x180002152  jmp     loc_1800020C8
```
