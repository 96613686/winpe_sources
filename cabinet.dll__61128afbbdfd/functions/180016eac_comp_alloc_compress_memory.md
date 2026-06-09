# comp_alloc_compress_memory

- ea: `0x180016eac`
- end: `0x180017111`
- name: `comp_alloc_compress_memory`
- size: `613`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180016e08`

## callees

- `0x180016eac`
- `0x180017118`
- `0x1800174f0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall comp_alloc_compress_memory(__int64 a1)
{
  unsigned int v1; // edx
  int v2; // r8d
  __int64 (__fastcall *v4)(__int64); // rax
  __int64 v5; // rax
  unsigned int v6; // eax
  unsigned int v7; // ecx
  unsigned int v8; // esi
  unsigned __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // r8
  char v17; // r9
  int i; // r10d
  char v19; // cl
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 (__fastcall *v22)(__int64); // rax
  __int64 v23; // rax

  v1 = 4;
  *(_QWORD *)(a1 + 16) = 0;
  v2 = 4;
  *(_QWORD *)(a1 + 17280) = 0;
  *(_QWORD *)(a1 + 17288) = 0;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 17272) = 0;
  *(_QWORD *)(a1 + 9600) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 2176) = 0;
  do
    v1 += 1 << dec_extra_bits[v2++];
  while ( v1 < *(_DWORD *)(a1 + 8) );
  v4 = *(__int64 (__fastcall **)(__int64))(a1 + 17312);
  *(_DWORD *)(a1 + 2208) = v2;
  v5 = v4(0x40000);
  *(_QWORD *)(a1 + 16) = v5;
  if ( v5 )
  {
    v6 = *(_DWORD *)(a1 + 8);
    v7 = v6 + 4353;
    if ( v6 + 4353 < v6 )
      return 0;
    v8 = v7 + *(_DWORD *)(a1 + 2492);
    if ( v8 < v7 )
      return 0;
    v9 = 4LL * v8;
    if ( v9 > 0xFFFFFFFF )
      return 0;
    v10 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 17312))((unsigned int)v9);
    *(_QWORD *)(a1 + 17280) = v10;
    if ( v10 )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 17312))((unsigned int)v9);
      *(_QWORD *)(a1 + 17288) = v11;
      if ( v11 )
      {
        v12 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 17312))(v8);
        *(_QWORD *)(a1 + 17272) = v12;
        if ( v12 )
        {
          *(_QWORD *)a1 = v12;
          v13 = (*(__int64 (__fastcall **)(__int64))(a1 + 17312))(0x10000);
          *(_QWORD *)(a1 + 72) = v13;
          if ( v13 )
          {
            v14 = (*(__int64 (__fastcall **)(__int64))(a1 + 17312))(0x20000);
            *(_QWORD *)(a1 + 64) = v14;
            if ( v14 )
            {
              v15 = (*(__int64 (__fastcall **)(__int64))(a1 + 17312))(0x2000);
              *(_QWORD *)(a1 + 80) = v15;
              if ( v15 )
              {
                create_slot_lookup_table(a1);
                v16 = 0;
                do
                {
                  v17 = 0;
                  for ( i = v16; i; v17 = v19 )
                  {
                    v19 = v17 + 1;
                    if ( (i & 1) == 0 )
                      v19 = v17;
                    i >>= 1;
                  }
                  *(_BYTE *)(v16 + a1 + 2225) = v17;
                  v16 = (unsigned int)(v16 + 1);
                }
                while ( (int)v16 < 256 );
                v20 = (*(__int64 (__fastcall **)(__int64))(a1 + 17312))(38912);
                *(_QWORD *)(a1 + 2176) = v20;
                if ( v20 )
                {
                  v21 = v20 + 38848;
                  *(_QWORD *)(a1 + 2184) = v20;
                  v22 = *(__int64 (__fastcall **)(__int64))(a1 + 17312);
                  *(_QWORD *)(a1 + 2192) = v21;
                  v23 = v22(98640);
                  *(_QWORD *)(a1 + 9600) = v23;
                  if ( v23 )
                  {
                    *(_DWORD *)(a1 + 2220) = 1;
                    return 1;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  comp_free_compress_memory(a1);
  return 0;
}

```

## disassembly

```asm
0x180016eac  mov     [rsp+arg_0], rbx
0x180016eb1  mov     [rsp+arg_8], rsi
0x180016eb6  push    rdi
0x180016eb7  sub     rsp, 20h
0x180016ebb  mov     edx, 4
0x180016ec0  mov     qword ptr [rcx+10h], 0
0x180016ec8  mov     r8d, edx
0x180016ecb  mov     qword ptr [rcx+4380h], 0
0x180016ed6  mov     rbx, rcx
0x180016ed9  mov     qword ptr [rcx+4388h], 0
0x180016ee4  mov     qword ptr [rcx], 0
0x180016eeb  mov     qword ptr [rcx+4378h], 0
0x180016ef6  mov     qword ptr [rcx+2580h], 0
0x180016f01  mov     qword ptr [rcx+48h], 0
0x180016f09  mov     qword ptr [rcx+40h], 0
0x180016f11  mov     qword ptr [rcx+50h], 0
0x180016f19  mov     qword ptr [rcx+880h], 0
0x180016f24  mov     ecx, r8d
0x180016f27  lea     rax, dec_extra_bits
0x180016f2e  mov     cl, [rcx+rax]
0x180016f31  mov     eax, 1
0x180016f36  shl     eax, cl
0x180016f38  add     edx, eax
0x180016f3a  inc     r8d
0x180016f3d  cmp     edx, [rbx+8]
0x180016f40  jb      short loc_180016F24
0x180016f42  mov     rax, [rbx+43A0h]
0x180016f49  mov     ecx, 40000h
0x180016f4e  mov     [rbx+8A0h], r8d
0x180016f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f5a  mov     [rbx+10h], rax
0x180016f5e  test    rax, rax
0x180016f61  jz      loc_1800170F7
0x180016f67  mov     eax, [rbx+8]
0x180016f6a  lea     ecx, [rax+1101h]
0x180016f70  cmp     ecx, eax
0x180016f72  jb      loc_1800170FF
0x180016f78  mov     esi, [rbx+9BCh]
0x180016f7e  add     esi, ecx
0x180016f80  cmp     esi, ecx
0x180016f82  jb      loc_1800170FF
0x180016f88  mov     edi, esi
0x180016f8a  mov     eax, 0FFFFFFFFh
0x180016f8f  shl     rdi, 2
0x180016f93  cmp     rdi, rax
0x180016f96  ja      loc_1800170FF
0x180016f9c  mov     rax, [rbx+43A0h]
0x180016fa3  mov     ecx, edi
0x180016fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016faa  mov     [rbx+4380h], rax
0x180016fb1  test    rax, rax
0x180016fb4  jz      loc_1800170F7
0x180016fba  mov     rax, [rbx+43A0h]
0x180016fc1  mov     ecx, edi
0x180016fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fc8  mov     [rbx+4388h], rax
0x180016fcf  test    rax, rax
0x180016fd2  jz      loc_1800170F7
0x180016fd8  mov     rax, [rbx+43A0h]
0x180016fdf  mov     ecx, esi
0x180016fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fe6  mov     [rbx+4378h], rax
0x180016fed  test    rax, rax
0x180016ff0  jz      loc_1800170F7
0x180016ff6  mov     [rbx], rax
0x180016ff9  mov     ecx, 10000h
0x180016ffe  mov     rax, [rbx+43A0h]
0x180017005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001700a  mov     [rbx+48h], rax
0x18001700e  test    rax, rax
0x180017011  jz      loc_1800170F7
0x180017017  mov     rax, [rbx+43A0h]
0x18001701e  mov     ecx, 20000h
0x180017023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017028  mov     [rbx+40h], rax
0x18001702c  test    rax, rax
0x18001702f  jz      loc_1800170F7
0x180017035  mov     rax, [rbx+43A0h]
0x18001703c  mov     ecx, 2000h
0x180017041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017046  mov     [rbx+50h], rax
0x18001704a  test    rax, rax
0x18001704d  jz      loc_1800170F7
0x180017053  mov     rcx, rbx
0x180017056  call    create_slot_lookup_table
0x18001705b  xor     r8d, r8d
0x18001705e  xor     r9b, r9b
0x180017061  mov     r10d, r8d
0x180017064  test    r8d, r8d
0x180017067  jz      short loc_180017083
0x180017069  lea     eax, [r9+1]
0x18001706d  test    r10b, 1
0x180017071  movzx   ecx, al
0x180017074  movzx   eax, r9b
0x180017078  cmovz   ecx, eax
0x18001707b  sar     r10d, 1
0x18001707e  mov     r9b, cl
0x180017081  jnz     short loc_180017069
0x180017083  mov     [r8+rbx+8B1h], r9b
0x18001708b  inc     r8d
0x18001708e  cmp     r8d, 100h
0x180017095  jl      short loc_18001705E
0x180017097  mov     rax, [rbx+43A0h]
0x18001709e  mov     ecx, 9800h
0x1800170a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170a8  mov     [rbx+880h], rax
0x1800170af  test    rax, rax
0x1800170b2  jz      short loc_1800170F7
0x1800170b4  lea     rcx, [rax+97C0h]
0x1800170bb  mov     [rbx+888h], rax
0x1800170c2  mov     rax, [rbx+43A0h]
0x1800170c9  mov     [rbx+890h], rcx
0x1800170d0  mov     ecx, 18150h
0x1800170d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170da  mov     [rbx+2580h], rax
0x1800170e1  test    rax, rax
0x1800170e4  jz      short loc_1800170F7
0x1800170e6  mov     dword ptr [rbx+8ACh], 1
0x1800170f0  mov     eax, 1
0x1800170f5  jmp     short loc_180017101
0x1800170f7  mov     rcx, rbx
0x1800170fa  call    comp_free_compress_memory
0x1800170ff  xor     eax, eax
0x180017101  mov     rbx, [rsp+28h+arg_0]
0x180017106  mov     rsi, [rsp+28h+arg_8]
0x18001710b  add     rsp, 20h
0x18001710f  pop     rdi
0x180017110  retn
```
