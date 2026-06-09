# GenAddTebMemory(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *)

- ea: `0x18001766c`
- end: `0x18001788a`
- name: `?GenAddTebMemory@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@@Z`
- size: `542`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _INTERNAL_PROCESS *, struct _INTERNAL_THREAD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005700`

## callees

- `0x18001766c`
- `0x18001f334`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall GenAddTebMemory(
        struct _MINIDUMP_STATE *a1,
        struct _INTERNAL_PROCESS *a2,
        struct _INTERNAL_THREAD *a3)
{
  unsigned int v4; // ebx
  unsigned __int64 v5; // rax
  unsigned int v8; // eax
  unsigned __int64 v9; // rcx
  unsigned int v10; // eax
  struct _INTERNAL_PROCESS *v11; // rsi
  struct _INTERNAL_PROCESS *v12; // r14
  int v13; // edx
  __int64 *v14; // rcx
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // rdx
  unsigned int v18; // eax
  unsigned __int64 v19; // rcx
  unsigned int v20; // eax
  unsigned int v21; // eax
  int v23; // [rsp+20h] [rbp-40h]
  __int64 v24; // [rsp+20h] [rbp-40h]
  unsigned int v25; // [rsp+28h] [rbp-38h]
  unsigned int v26; // [rsp+28h] [rbp-38h]
  _QWORD v27[4]; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int64 v28; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v29; // [rsp+A8h] [rbp+48h]

  v27[1] = a1;
  v27[0] = &GenMiniDumpProviderCallbacks::`vftable';
  v4 = 0;
  v25 = *((_DWORD *)a3 + 26);
  v5 = *((_QWORD *)a3 + 12);
  v27[2] = a2;
  v27[3] = 8;
  v8 = GenAddMemoryBlock(a1, (__int64)a2, 8u, 0, v5, v25);
  v9 = *((_QWORD *)a3 + 21);
  if ( v8 )
    v4 = v8;
  if ( v9 && (*((_DWORD *)a1 + 14) & 0x100000) == 0 )
  {
    v10 = GenAddMemoryBlock(a1, (__int64)a2, 8u, 0, v9, *((_DWORD *)a1 + 39) * (*((_DWORD *)a2 + 23) + 1));
    v11 = (struct _INTERNAL_PROCESS *)*((_QWORD *)a2 + 15);
LABEL_13:
    if ( v10 )
      v4 = v10;
    while ( v11 != (struct _INTERNAL_PROCESS *)((char *)a2 + 120) )
    {
      v12 = v11;
      v11 = *(struct _INTERNAL_PROCESS **)v11;
      if ( (*((_BYTE *)v12 - 8) & 0x21) == 0x21 && *((_DWORD *)v12 - 8) )
      {
        v13 = *((_DWORD *)a1 + 39);
        v14 = (__int64 *)*((_QWORD *)a1 + 2);
        v15 = (unsigned int)(*((_DWORD *)v12 - 9) * v13);
        v28 = 0;
        v23 = v13;
        v16 = *v14;
        v17 = *(_QWORD *)a1;
        v29 = *((_QWORD *)a3 + 21) + v15;
        v18 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, unsigned __int64 *, int))(v16 + 240))(
                v14,
                v17,
                v29,
                &v28,
                v23);
        v4 = v18;
        if ( !v18 )
        {
          v19 = v28;
          if ( *((_DWORD *)a1 + 39) != 8 )
            v19 = (int)v28;
          v26 = *((_DWORD *)v12 - 8);
          v28 = v19;
          v10 = GenAddMemoryBlock(a1, (__int64)a2, 8u, 0, v19, v26);
          goto LABEL_13;
        }
        LODWORD(v24) = v18;
        (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
          *((_QWORD *)a1 + 5),
          2,
          "GenGenTebMemory.TLS(0x%I64x) failed, 0x%08x",
          v29,
          v24);
      }
    }
  }
  v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD *))(**((_QWORD **)a1 + 2)
                                                                                            + 408LL))(
          *((_QWORD *)a1 + 2),
          *((_QWORD *)a2 + 8),
          *((_QWORD *)a3 + 1),
          *((unsigned int *)a1 + 14),
          *((_QWORD *)a3 + 12),
          *((_DWORD *)a3 + 26),
          v27);
  if ( v20 )
  {
    return v20;
  }
  else if ( (*((_DWORD *)a1 + 14) & 0x400) == 0 )
  {
    v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)a1 + 2) + 392LL))(
            *((_QWORD *)a1 + 2),
            *((_QWORD *)a2 + 8),
            *((_QWORD *)a3 + 1));
    if ( v21 )
      return v21;
  }
  return v4;
}

```

## disassembly

```asm
0x18001766c  mov     [rsp-38h+arg_10], rbx
0x180017671  push    rbp
0x180017672  push    rsi
0x180017673  push    rdi
0x180017674  push    r12
0x180017676  push    r13
0x180017678  push    r14
0x18001767a  push    r15
0x18001767c  mov     rbp, rsp
0x18001767f  sub     rsp, 60h
0x180017683  lea     rax, ??_7GenMiniDumpProviderCallbacks@@6B@; const GenMiniDumpProviderCallbacks::`vftable'
0x18001768a  mov     [rbp+var_18], rcx
0x18001768e  mov     [rbp+var_20], rax
0x180017692  mov     r15, r8
0x180017695  mov     eax, [r8+68h]
0x180017699  xor     ebx, ebx
0x18001769b  mov     [rsp+60h+var_38], eax
0x18001769f  xor     r9d, r9d
0x1800176a2  mov     rax, [r8+60h]
0x1800176a6  mov     r13, rdx
0x1800176a9  mov     rdi, rcx
0x1800176ac  mov     [rbp+var_10], rdx
0x1800176b0  lea     esi, [rbx+8]
0x1800176b3  mov     [rbp+var_8], 8
0x1800176bb  mov     r8d, esi
0x1800176be  mov     [rsp+60h+var_40], rax
0x1800176c3  call    ?GenAddMemoryBlock@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@W4MEMBLOCK_TYPE@@W4MEMBLOCK_FILTER_TYPE@@_KK@Z; GenAddMemoryBlock(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,MEMBLOCK_TYPE,MEMBLOCK_FILTER_TYPE,unsigned __int64,ulong)
0x1800176c8  mov     rcx, [r15+0A8h]
0x1800176cf  test    eax, eax
0x1800176d1  cmovnz  ebx, eax
0x1800176d4  test    rcx, rcx
0x1800176d7  jz      loc_1800177EA
0x1800176dd  test    dword ptr [rdi+38h], 100000h
0x1800176e4  jnz     loc_1800177EA
0x1800176ea  mov     eax, [r13+5Ch]
0x1800176ee  xor     r9d, r9d
0x1800176f1  inc     eax
0x1800176f3  mov     r8d, esi
0x1800176f6  imul    eax, [rdi+9Ch]
0x1800176fd  mov     rdx, r13
0x180017700  mov     [rsp+60h+var_38], eax
0x180017704  mov     [rsp+60h+var_40], rcx
0x180017709  mov     rcx, rdi
0x18001770c  call    ?GenAddMemoryBlock@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@W4MEMBLOCK_TYPE@@W4MEMBLOCK_FILTER_TYPE@@_KK@Z; GenAddMemoryBlock(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,MEMBLOCK_TYPE,MEMBLOCK_FILTER_TYPE,unsigned __int64,ulong)
0x180017711  lea     r12, [r13+78h]
0x180017715  mov     rsi, [r12]
0x180017719  jmp     loc_1800177DC
0x18001771e  lea     r14, [rsi]
0x180017721  mov     rsi, [rsi]
0x180017724  mov     eax, [r14-8]
0x180017728  and     eax, 21h
0x18001772b  cmp     al, 21h ; '!'
0x18001772d  jnz     loc_1800177E1
0x180017733  cmp     dword ptr [r14-20h], 0
0x180017738  jz      loc_1800177E1
0x18001773e  mov     edx, [rdi+9Ch]
0x180017744  lea     r9, [rbp+arg_0]
0x180017748  mov     rcx, [rdi+10h]
0x18001774c  mov     r8d, edx
0x18001774f  imul    r8d, [r14-24h]
0x180017754  mov     [rbp+arg_0], 0
0x18001775c  mov     dword ptr [rsp+60h+var_40], edx
0x180017760  mov     rax, [rcx]
0x180017763  mov     rdx, [rdi]
0x180017766  add     r8, [r15+0A8h]
0x18001776d  mov     [rbp+arg_8], r8
0x180017771  mov     rax, [rax+0F0h]
0x180017778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001777d  mov     ebx, eax
0x18001777f  test    eax, eax
0x180017781  jz      short loc_1800177A9
0x180017783  mov     rcx, [rdi+28h]
0x180017787  lea     r8, aGengentebmemor; "GenGenTebMemory.TLS(0x%I64x) failed, 0x"...
0x18001778e  mov     r9, [rbp+arg_8]
0x180017792  mov     dword ptr [rsp+60h+var_40], ebx
0x180017796  mov     rdx, [rcx]
0x180017799  mov     rax, [rdx+8]
0x18001779d  mov     edx, 2
0x1800177a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177a7  jmp     short loc_1800177E1
0x1800177a9  cmp     dword ptr [rdi+9Ch], 8
0x1800177b0  mov     rcx, [rbp+arg_0]
0x1800177b4  jz      short loc_1800177B9
0x1800177b6  movsxd  rcx, ecx
0x1800177b9  mov     eax, [r14-20h]
0x1800177bd  xor     r9d, r9d
0x1800177c0  mov     [rsp+60h+var_38], eax
0x1800177c4  mov     rdx, r13
0x1800177c7  mov     [rbp+arg_0], rcx
0x1800177cb  mov     [rsp+60h+var_40], rcx
0x1800177d0  mov     rcx, rdi
0x1800177d3  lea     r8d, [r9+8]
0x1800177d7  call    ?GenAddMemoryBlock@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@W4MEMBLOCK_TYPE@@W4MEMBLOCK_FILTER_TYPE@@_KK@Z; GenAddMemoryBlock(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,MEMBLOCK_TYPE,MEMBLOCK_FILTER_TYPE,unsigned __int64,ulong)
0x1800177dc  test    eax, eax
0x1800177de  cmovnz  ebx, eax
0x1800177e1  cmp     rsi, r12
0x1800177e4  jnz     loc_18001771E
0x1800177ea  mov     rcx, [rdi+10h]
0x1800177ee  lea     rdx, [rbp+var_20]
0x1800177f2  mov     r9d, [rdi+38h]
0x1800177f6  mov     r8, [r15+8]
0x1800177fa  mov     [rsp+60h+var_30], rdx
0x1800177ff  mov     edx, [r15+68h]
0x180017803  mov     rax, [rcx]
0x180017806  mov     [rsp+60h+var_38], edx
0x18001780a  mov     rdx, [r15+60h]
0x18001780e  mov     [rsp+60h+var_40], rdx
0x180017813  mov     rax, [rax+198h]
0x18001781a  mov     rdx, [r13+40h]
0x18001781e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017823  test    eax, eax
0x180017825  jz      short loc_18001782B
0x180017827  mov     ebx, eax
0x180017829  jmp     short loc_180017870
0x18001782b  mov     r9d, [rdi+38h]
0x18001782f  bt      r9d, 0Ah
0x180017834  jb      short loc_180017870
0x180017836  mov     rcx, [rdi+10h]
0x18001783a  lea     rdx, [rbp+var_20]
0x18001783e  mov     r8, [r15+8]
0x180017842  mov     [rsp+60h+var_30], rdx
0x180017847  mov     edx, [r15+68h]
0x18001784b  mov     rax, [rcx]
0x18001784e  mov     [rsp+60h+var_38], edx
0x180017852  mov     rdx, [r15+60h]
0x180017856  mov     [rsp+60h+var_40], rdx
0x18001785b  mov     rax, [rax+188h]
0x180017862  mov     rdx, [r13+40h]
0x180017866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001786b  test    eax, eax
0x18001786d  cmovnz  ebx, eax
0x180017870  mov     eax, ebx
0x180017872  mov     rbx, [rsp+60h+arg_10]
0x18001787a  add     rsp, 60h
0x18001787e  pop     r15
0x180017880  pop     r14
0x180017882  pop     r13
0x180017884  pop     r12
0x180017886  pop     rdi
0x180017887  pop     rsi
0x180017888  pop     rbp
0x180017889  retn
```
