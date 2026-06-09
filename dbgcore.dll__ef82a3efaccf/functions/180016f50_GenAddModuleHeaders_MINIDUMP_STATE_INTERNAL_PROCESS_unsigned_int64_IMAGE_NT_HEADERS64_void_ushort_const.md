# GenAddModuleHeaders(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,unsigned __int64,_IMAGE_NT_HEADERS64 *,void *,ushort const *)

- ea: `0x180016f50`
- end: `0x18001721a`
- name: `?GenAddModuleHeaders@@YAXPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@_KPEAU_IMAGE_NT_HEADERS64@@PEAXPEBG@Z`
- size: `714`
- prototype: `void __usercall(struct _MINIDUMP_STATE *@<rcx>, struct _INTERNAL_PROCESS *@<rdx>, unsigned __int64@<r8>, struct _IMAGE_NT_HEADERS64 *@<r9>, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180017b8c`

## callees

- `0x180016b74`
- `0x180016f50`
- `0x180017a38`
- `0x18001f334`
- `0x180026b18`
- `0x18002c010`

## string_xrefs

- `0x180017056`: `Unable to add directory %x from module "%ws", (%x,%x,%x)`
- `0x180017118`: `Unable to add debug directory %x from module "%ws", (%x,%x,%x,%x)`

## pseudocode

```c
void __fastcall GenAddModuleHeaders(
        struct _MINIDUMP_STATE *a1,
        struct _INTERNAL_PROCESS *a2,
        unsigned __int64 a3,
        struct _IMAGE_NT_HEADERS64 *a4,
        _DWORD *a5,
        const unsigned __int16 *a6)
{
  struct _IMAGE_NT_HEADERS64 *v6; // r13
  unsigned __int64 v7; // rdi
  struct _INTERNAL_PROCESS *v9; // rbp
  unsigned int v11; // ebx
  const unsigned __int16 *v12; // r15
  int v13; // r8d
  __int64 v14; // rsi
  __int64 VirtualAddress; // rax
  unsigned int Size; // ecx
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  unsigned int *v20; // rbx
  unsigned int v21; // edi
  unsigned int v22; // r8d
  unsigned __int8 *v23; // rax
  unsigned __int8 *v24; // rbp
  unsigned __int8 *v25; // [rsp+20h] [rbp-78h]
  unsigned int v26[2]; // [rsp+28h] [rbp-70h]
  unsigned int v27[2]; // [rsp+28h] [rbp-70h]
  __int64 v28; // [rsp+30h] [rbp-68h]
  __int64 v29; // [rsp+38h] [rbp-60h]
  __int64 v30; // [rsp+40h] [rbp-58h]
  unsigned int v31[18]; // [rsp+50h] [rbp-48h] BYREF

  v6 = a4;
  v7 = (unsigned __int64)a5;
  v9 = a2;
  v11 = a5[15] + a4->OptionalHeader.SizeOfHeaders;
  v12 = a6;
  v13 = GenAddMemoryBlock(a1, (__int64)a2, 0xEu, 0, a3, v11);
  if ( v13 )
  {
    LODWORD(v25) = v13;
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      2,
      "Unable to add module \"%ws\" PE header, (0x%08X,0x%I64x)(%x,%x)",
      a6,
      v25,
      a3,
      v11,
      a5[15]);
  }
  v14 = 0;
  do
  {
    while ( 1 )
    {
      VirtualAddress = v6->OptionalHeader.DataDirectory[v14].VirtualAddress;
      if ( !(_DWORD)VirtualAddress )
        break;
      Size = v6->OptionalHeader.DataDirectory[v14].Size;
      if ( !Size )
        break;
      v17 = GenAddMemoryBlock(a1, (__int64)v9, 0xEu, 0, a3 + VirtualAddress, Size);
      v19 = v17;
      if ( v17 )
      {
        LODWORD(v29) = v6->OptionalHeader.DataDirectory[v14].Size;
        LODWORD(v28) = v6->OptionalHeader.DataDirectory[v14].VirtualAddress;
        v26[0] = v17;
        (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
          *((_QWORD *)a1 + 5),
          2,
          "Unable to add directory %x from module \"%ws\", (%x,%x,%x)",
          (unsigned int)v14,
          v12,
          *(_QWORD *)v26,
          v28,
          v29);
      }
      if ( (_DWORD)v14 != 6 )
        break;
      v31[0] = 0;
      v20 = (unsigned int *)GenImageDirectoryEntryToData(v7, v18, v19, v31);
      if ( !v20 )
        break;
      v21 = v31[0] / 0x1C;
      if ( !(v31[0] / 0x1C) )
      {
        v7 = (unsigned __int64)a5;
        break;
      }
      do
      {
        v22 = GenAddMemoryBlock(a1, (__int64)v9, 0xEu, 0, a3 + v20[5], v20[4]);
        if ( v22 )
        {
          LODWORD(v30) = v20[6];
          LODWORD(v29) = v20[5];
          LODWORD(v28) = v20[4];
          v27[0] = v22;
          (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
            *((_QWORD *)a1 + 5),
            2,
            "Unable to add debug directory %x from module \"%ws\", (%x,%x,%x,%x)",
            v20[3],
            a6,
            *(_QWORD *)v27,
            v28,
            v29,
            v30);
        }
        if ( (*((_DWORD *)a1 + 14) & 0x100000) != 0 && v20[3] == 2 )
        {
          v23 = (unsigned __int8 *)AllocMemory(a1, v20[4]);
          v24 = v23;
          if ( v23 )
          {
            if ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, unsigned __int64, unsigned __int8 *, unsigned int))(**((_QWORD **)a1 + 2) + 240LL))(
                    *((_QWORD *)a1 + 2),
                    *(_QWORD *)a1,
                    a3 + v20[5],
                    v23,
                    v20[4]) )
              GenAddUpdateMemoryRegion(a1, a2, 1, a3 + v20[5], v24, v20[4]);
            (*(void (__fastcall **)(_QWORD, unsigned __int8 *))(**((_QWORD **)a1 + 4) + 24LL))(*((_QWORD *)a1 + 4), v24);
          }
          v9 = a2;
        }
        v20 += 7;
        --v21;
      }
      while ( v21 );
      v6 = a4;
      v14 = 7;
      v7 = (unsigned __int64)a5;
      v12 = a6;
    }
    v14 = (unsigned int)(v14 + 1);
  }
  while ( (unsigned int)v14 < 0x10 );
}

```

## disassembly

```asm
0x180016f50  mov     rax, rsp
0x180016f53  mov     [rax+8], rbx
0x180016f57  mov     [rax+20h], r9
0x180016f5b  mov     [rax+10h], rdx
0x180016f5f  push    rbp
0x180016f60  push    rsi
0x180016f61  push    rdi
0x180016f62  push    r12
0x180016f64  push    r13
0x180016f66  push    r14
0x180016f68  push    r15
0x180016f6a  sub     rsp, 60h
0x180016f6e  mov     ebx, [r9+54h]
0x180016f72  mov     r13, r9
0x180016f75  mov     rdi, [rsp+98h+arg_20]
0x180016f7d  xor     r9d, r9d
0x180016f80  mov     r12, r8
0x180016f83  mov     rbp, rdx
0x180016f86  mov     r14, rcx
0x180016f89  add     ebx, [rdi+3Ch]
0x180016f8c  mov     [rax-70h], ebx
0x180016f8f  mov     [rax-78h], r8
0x180016f93  lea     r8d, [r9+0Eh]
0x180016f97  call    ?GenAddMemoryBlock@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@W4MEMBLOCK_TYPE@@W4MEMBLOCK_FILTER_TYPE@@_KK@Z; GenAddMemoryBlock(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,MEMBLOCK_TYPE,MEMBLOCK_FILTER_TYPE,unsigned __int64,ulong)
0x180016f9c  mov     r15, [rsp+98h+arg_28]
0x180016fa4  mov     r8d, eax
0x180016fa7  test    eax, eax
0x180016fa9  jz      short loc_180016FDF
0x180016fab  mov     rcx, [r14+28h]
0x180016faf  mov     r9, r15
0x180016fb2  mov     rdx, [rcx]
0x180016fb5  mov     rax, [rdx+8]
0x180016fb9  mov     edx, [rdi+3Ch]
0x180016fbc  mov     dword ptr [rsp+98h+var_60], edx
0x180016fc0  mov     edx, 2
0x180016fc5  mov     dword ptr [rsp+98h+var_68], ebx
0x180016fc9  mov     qword ptr [rsp+98h+var_70], r12
0x180016fce  mov     dword ptr [rsp+98h+var_78], r8d
0x180016fd3  lea     r8, aUnableToAddMod; "Unable to add module \"%ws\" PE header,"...
0x180016fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fdf  xor     esi, esi
0x180016fe1  mov     eax, [r13+rsi*8+88h]
0x180016fe9  test    eax, eax
0x180016feb  jz      loc_1800171F7
0x180016ff1  mov     ecx, [r13+rsi*8+8Ch]
0x180016ff9  test    ecx, ecx
0x180016ffb  jz      loc_1800171F7
0x180017001  mov     [rsp+98h+var_70], ecx
0x180017005  xor     r9d, r9d
0x180017008  add     rax, r12
0x18001700b  mov     rdx, rbp
0x18001700e  mov     rcx, r14
0x180017011  mov     [rsp+98h+var_78], rax
0x180017016  lea     r8d, [r9+0Eh]
0x18001701a  call    ?GenAddMemoryBlock@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@W4MEMBLOCK_TYPE@@W4MEMBLOCK_FILTER_TYPE@@_KK@Z; GenAddMemoryBlock(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,MEMBLOCK_TYPE,MEMBLOCK_FILTER_TYPE,unsigned __int64,ulong)
0x18001701f  mov     r8d, eax
0x180017022  test    eax, eax
0x180017024  jz      short loc_180017067
0x180017026  mov     rcx, [r14+28h]
0x18001702a  mov     r9d, esi
0x18001702d  mov     rdx, [rcx]
0x180017030  mov     rax, [rdx+8]
0x180017034  mov     edx, [r13+rsi*8+8Ch]
0x18001703c  mov     dword ptr [rsp+98h+var_60], edx
0x180017040  mov     edx, [r13+rsi*8+88h]
0x180017048  mov     dword ptr [rsp+98h+var_68], edx
0x18001704c  mov     edx, 2
0x180017051  mov     [rsp+98h+var_70], r8d
0x180017056  lea     r8, aUnableToAddDir; "Unable to add directory %x from module "...
0x18001705d  mov     [rsp+98h+var_78], r15
0x180017062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017067  cmp     esi, 6
0x18001706a  jnz     loc_1800171F7
0x180017070  lea     r9, [rsp+98h+var_48]; unsigned int *
0x180017075  mov     [rsp+98h+var_48], 0
0x18001707d  mov     rcx, rdi; void *
0x180017080  call    ?GenImageDirectoryEntryToData@@YAPEAXPEAXEGPEAK@Z; GenImageDirectoryEntryToData(void *,uchar,ushort,ulong *)
0x180017085  mov     rbx, rax
0x180017088  test    rax, rax
0x18001708b  jz      loc_1800171F7
0x180017091  mov     edi, [rsp+98h+var_48]
0x180017095  mov     rax, 2492492492492493h
0x18001709f  mul     rdi
0x1800170a2  sub     rdi, rdx
0x1800170a5  shr     rdi, 1
0x1800170a8  add     rdi, rdx
0x1800170ab  shr     rdi, 4
0x1800170af  test    edi, edi
0x1800170b1  jz      loc_1800171EF
0x1800170b7  mov     r13, [rsp+98h+arg_28]
0x1800170bf  mov     ecx, [rbx+14h]
0x1800170c2  xor     r9d, r9d
0x1800170c5  mov     eax, [rbx+10h]
0x1800170c8  add     rcx, r12
0x1800170cb  mov     [rsp+98h+var_70], eax
0x1800170cf  mov     rdx, rbp
0x1800170d2  mov     [rsp+98h+var_78], rcx
0x1800170d7  mov     rcx, r14
0x1800170da  lea     r8d, [r9+0Eh]
0x1800170de  call    ?GenAddMemoryBlock@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@W4MEMBLOCK_TYPE@@W4MEMBLOCK_FILTER_TYPE@@_KK@Z; GenAddMemoryBlock(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,MEMBLOCK_TYPE,MEMBLOCK_FILTER_TYPE,unsigned __int64,ulong)
0x1800170e3  mov     r8d, eax
0x1800170e6  test    eax, eax
0x1800170e8  jz      short loc_180017129
0x1800170ea  mov     rcx, [r14+28h]
0x1800170ee  mov     r9d, [rbx+0Ch]
0x1800170f2  mov     rdx, [rcx]
0x1800170f5  mov     rax, [rdx+8]
0x1800170f9  mov     edx, [rbx+18h]
0x1800170fc  mov     [rsp+98h+var_58], edx
0x180017100  mov     edx, [rbx+14h]
0x180017103  mov     dword ptr [rsp+98h+var_60], edx
0x180017107  mov     edx, [rbx+10h]
0x18001710a  mov     dword ptr [rsp+98h+var_68], edx
0x18001710e  mov     edx, 2
0x180017113  mov     [rsp+98h+var_70], r8d
0x180017118  lea     r8, aUnableToAddDeb; "Unable to add debug directory %x from m"...
0x18001711f  mov     [rsp+98h+var_78], r13
0x180017124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017129  test    dword ptr [r14+38h], 100000h
0x180017131  jz      loc_1800171C3
0x180017137  cmp     dword ptr [rbx+0Ch], 2
0x18001713b  jnz     loc_1800171C3
0x180017141  mov     edx, [rbx+10h]; unsigned int
0x180017144  mov     rcx, r14; struct _MINIDUMP_STATE *
0x180017147  call    ?AllocMemory@@YAPEAXPEAU_MINIDUMP_STATE@@K@Z; AllocMemory(_MINIDUMP_STATE *,ulong)
0x18001714c  mov     rbp, rax
0x18001714f  test    rax, rax
0x180017152  jz      short loc_1800171BB
0x180017154  mov     rcx, [r14+10h]
0x180017158  mov     r9, rbp
0x18001715b  mov     r8d, [rbx+14h]
0x18001715f  add     r8, r12
0x180017162  mov     rdx, [rcx]
0x180017165  mov     rax, [rdx+0F0h]
0x18001716c  mov     edx, [rbx+10h]
0x18001716f  mov     dword ptr [rsp+98h+var_78], edx
0x180017173  mov     rdx, [r14]
0x180017176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001717b  test    eax, eax
0x18001717d  jnz     short loc_1800171A8
0x18001717f  mov     r9d, [rbx+14h]
0x180017183  mov     r8d, 1; int
0x180017189  mov     eax, [rbx+10h]
0x18001718c  add     r9, r12; unsigned __int64
0x18001718f  mov     rdx, [rsp+98h+arg_8]; struct _INTERNAL_PROCESS *
0x180017197  mov     rcx, r14; struct _MINIDUMP_STATE *
0x18001719a  mov     [rsp+98h+var_70], eax; unsigned int
0x18001719e  mov     [rsp+98h+var_78], rbp; unsigned __int8 *
0x1800171a3  call    ?GenAddUpdateMemoryRegion@@YAHPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@H_KPEAEK@Z; GenAddUpdateMemoryRegion(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,int,unsigned __int64,uchar *,ulong)
0x1800171a8  mov     rcx, [r14+20h]
0x1800171ac  mov     rdx, rbp
0x1800171af  mov     rax, [rcx]
0x1800171b2  mov     rax, [rax+18h]
0x1800171b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171bb  mov     rbp, [rsp+98h+arg_8]
0x1800171c3  add     rbx, 1Ch
0x1800171c7  add     edi, 0FFFFFFFFh
0x1800171ca  jnz     loc_1800170BF
0x1800171d0  mov     r13, [rsp+98h+arg_18]
0x1800171d8  inc     esi
0x1800171da  mov     rdi, [rsp+98h+arg_20]
0x1800171e2  mov     r15, [rsp+98h+arg_28]
0x1800171ea  jmp     loc_180016FE1
0x1800171ef  mov     rdi, [rsp+98h+arg_20]
0x1800171f7  inc     esi
0x1800171f9  cmp     esi, 10h
0x1800171fc  jb      loc_180016FE1
0x180017202  mov     rbx, [rsp+98h+arg_0]
0x18001720a  add     rsp, 60h
0x18001720e  pop     r15
0x180017210  pop     r14
0x180017212  pop     r13
0x180017214  pop     r12
0x180017216  pop     rdi
0x180017217  pop     rsi
0x180017218  pop     rbp
0x180017219  retn
```
