# NatFncObj::Call(VAR *,int,VAR *,VAR *,ulong)

- ea: `0x18000d220`
- end: `0x18000d65b`
- name: `?Call@NatFncObj@@UEAAJPEAVVAR@@H00K@Z`
- size: `1083`
- prototype: `__int64 __fastcall(NatFncObj *__hidden this, struct VAR *, int, struct VAR *, struct VAR *, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x18000d220`
- `0x18000d9fc`
- `0x18000f5e0`
- `0x18000f630`
- `0x180032b08`
- `0x180033780`
- `0x18003493c`
- `0x1800522b0`
- `0x180057694`
- `0x180096010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000d4f4`
- `KERNEL32!DeleteCriticalSection` at `0x18000d4f4`
- `KERNEL32!TlsGetValue` at `0x18000d241`
- `KERNEL32!TlsGetValue` at `0x18000d5ad`
- `KERNEL32!TlsGetValue` at `0x18000d241`
- `KERNEL32!TlsGetValue` at `0x18000d5ad`
- `KERNEL32!GetTickCount` at `0x18000d52d`
- `KERNEL32!GetTickCount` at `0x18000d581`
- `KERNEL32!GetTickCount` at `0x18000d52d`
- `KERNEL32!GetTickCount` at `0x18000d581`

## pseudocode

```c
__int64 __fastcall NatFncObj::Call(NatFncObj *this, struct VAR *a2, unsigned int a3, struct VAR *a4, struct VAR *a5)
{
  _QWORD *Value; // rax
  __int64 *v10; // rax
  CScriptRuntime **v11; // rcx
  _QWORD *v12; // r14
  struct GcAlloc *Allocator; // rsi
  struct GcAlloc *GcAlloc; // rax
  bool v15; // zf
  __int64 v16; // rbx
  int v17; // eax
  __int64 v18; // rbx
  __int64 v19; // rcx
  _DWORD *v20; // rsi
  DWORD TickCount; // ebp
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  int v26; // ebx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v30; // rsi
  GcBlock *v31; // rax
  __int64 v32; // r9
  struct ThreadGlobals *v33; // rax
  __int16 v34; // [rsp+30h] [rbp-88h] BYREF
  __int64 v35; // [rsp+38h] [rbp-80h]
  _WORD *v36; // [rsp+48h] [rbp-70h] BYREF
  __int64 v37; // [rsp+50h] [rbp-68h]
  __int64 v38; // [rsp+58h] [rbp-60h]
  __int16 *v39; // [rsp+60h] [rbp-58h] BYREF
  __int64 v40; // [rsp+68h] [rbp-50h]
  __int64 v41; // [rsp+70h] [rbp-48h]
  _WORD v42[12]; // [rsp+78h] [rbp-40h] BYREF

  Value = TlsGetValue(g_luTls);
  if ( Value )
    Value = (_QWORD *)Value[4];
  if ( Value != *((_QWORD **)this + 9) )
    return 2147549183LL;
  if ( a2 )
    *(_WORD *)a2 = 0;
  else
    a2 = (struct VAR *)v42;
  v10 = (__int64 *)*((_QWORD *)this + 4);
  if ( v10 == NameTbl::s_varNameTblConstructed || !v10 )
  {
    v11 = (CScriptRuntime **)*((_QWORD *)this + 3);
    v12 = (_QWORD *)((char *)this + 24);
    if ( v11 )
    {
      Allocator = v11[124];
      if ( Allocator )
      {
LABEL_13:
        v16 = *((_QWORD *)Allocator + 2);
        v17 = *(_DWORD *)(v16 + 12);
        if ( (v17 & 1) != 0 && (v17 & 2) == 0 )
        {
          GcContext::ClearMark(*((GcContext **)Allocator + 2));
          *(_DWORD *)(v16 + 12) |= 2u;
        }
        if ( *((_QWORD *)Allocator + 4) )
        {
LABEL_15:
          v18 = *((_QWORD *)Allocator + 4);
          v19 = *(int *)(v18 + 8);
          if ( (int)v19 <= 0 )
          {
            *((_QWORD *)Allocator + 4) = *(_QWORD *)(v18 + 16);
          }
          else
          {
            *(_DWORD *)(v18 + 8) = v19 - 1;
            v18 += 24 * v19;
          }
          *(_WORD *)v18 = 0;
          v20 = (_DWORD *)*((_QWORD *)Allocator + 2);
          TickCount = v20[38];
          if ( !TickCount )
          {
            TickCount = GetTickCount();
            v20[38] = TickCount;
          }
          ++v20[26];
          ++v20[29];
          v22 = v20[26];
          if ( v20[2] )
            goto LABEL_22;
          if ( v22 >= v20[30] )
          {
            v20[39] |= 1u;
          }
          else
          {
            if ( v22 < dword_1800B3CE4 || GetTickCount() - TickCount <= 0x2710 )
              goto LABEL_22;
            v20[39] &= ~1u;
          }
          v20[2] = 1;
LABEL_22:
          *(_WORD *)v18 = 129;
          *(_QWORD *)(v18 + 8) = this;
          if ( *((__int64 **)this + 4) == NameTbl::s_varNameTblConstructed )
          {
            *((_QWORD *)this + 4) = v18;
          }
          else
          {
            v30 = *((_QWORD *)this + 9);
            _InterlockedIncrement((volatile signed __int32 *)v30);
            if ( (unsigned int)MUTX::Enter((MUTX *)(v30 + 56)) )
            {
              *((_QWORD *)this + 4) = v18;
              MUTX::Leave((MUTX *)(v30 + 56));
            }
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v30, 0xFFFFFFFF) == 1 && v30 )
            {
              if ( *(_BYTE *)(v30 + 97) )
                DeleteCriticalSection((LPCRITICAL_SECTION)(v30 + 56));
              operator delete((void *)v30);
            }
          }
          v34 = 128;
          v35 = v18;
          goto LABEL_25;
        }
        v31 = GcBlockFactory::PblkAlloc((GcBlockFactory *)v11);
        if ( v31 )
        {
          GcBlock::Link(v31, (struct GcBlock **)Allocator + 3);
          *((_QWORD *)Allocator + 4) = v32 + 16;
          *(_WORD *)(v32 + 16) = 138;
          *(_DWORD *)(v32 + 24) = 99;
          *(_QWORD *)(v32 + 32) = 0;
          goto LABEL_15;
        }
LABEL_45:
        v34 = 0;
        goto LABEL_25;
      }
      if ( v11[10] )
        GcAlloc = CScriptRuntime::GetGcAlloc(v11[10]);
      else
        GcAlloc = GcAlloc::GetAllocator(v11[123]);
      Allocator = GcAlloc;
      v15 = GcAlloc == 0;
    }
    else
    {
      v33 = (struct ThreadGlobals *)TlsGetValue(g_luTls);
      Allocator = GcAlloc::GetAllocator(v33);
      v15 = Allocator == 0;
    }
    if ( v15 )
      goto LABEL_45;
    goto LABEL_13;
  }
  v35 = *((_QWORD *)this + 4);
  v34 = 128;
  v12 = (_QWORD *)((char *)this + 24);
LABEL_25:
  v23 = *v12;
  v39 = &v34;
  v40 = v23;
  v41 = *(_QWORD *)(v23 + 976);
  *(_QWORD *)(v23 + 976) = &v39;
  v24 = *v12;
  v42[0] = 0;
  v36 = v42;
  v37 = v24;
  v38 = *(_QWORD *)(v24 + 976);
  *(_QWORD *)(v24 + 976) = &v36;
  v25 = *v12;
  if ( *(_DWORD *)(*v12 + 20LL) )
  {
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(v25 + 8) + 56LL))(
      *(_QWORD *)(v25 + 8),
      1,
      *((unsigned int *)this + 34));
    v26 = (*((__int64 (__fastcall **)(_QWORD, struct VAR *, struct VAR *, _QWORD, struct VAR *))this + 18))(
            *v12,
            a5,
            a2,
            a3,
            a4);
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*v12 + 8LL) + 64LL))(
      *(_QWORD *)(*v12 + 8LL),
      1,
      *((unsigned int *)this + 34));
  }
  else
  {
    v26 = (*((__int64 (__fastcall **)(__int64, struct VAR *, struct VAR *, _QWORD, struct VAR *))this + 18))(
            v25,
            a5,
            a2,
            a3,
            a4);
  }
  v27 = *(_QWORD *)(v37 + 976);
  if ( v27 )
    *(_QWORD *)(v37 + 976) = *(_QWORD *)(v27 + 16);
  v28 = *(_QWORD *)(v40 + 976);
  if ( v28 )
    *(_QWORD *)(v40 + 976) = *(_QWORD *)(v28 + 16);
  if ( v26 < 0 )
    *(_WORD *)a2 = 0;
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x18000d220  push    rdi
0x18000d222  push    r12
0x18000d224  push    r13
0x18000d226  push    r15
0x18000d228  sub     rsp, 98h
0x18000d22f  mov     rdi, rcx
0x18000d232  mov     r12, r9
0x18000d235  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18000d23b  mov     r13d, r8d
0x18000d23e  mov     r15, rdx
0x18000d241  call    cs:__imp_TlsGetValue
0x18000d247  test    rax, rax
0x18000d24a  jz      short loc_18000D250
0x18000d24c  mov     rax, [rax+20h]
0x18000d250  cmp     rax, [rdi+48h]
0x18000d254  jnz     loc_18000D479
0x18000d25a  mov     [rsp+0B8h+arg_8], rbx
0x18000d262  mov     [rsp+0B8h+var_28], r14
0x18000d26a  test    r15, r15
0x18000d26d  jz      loc_18000D549
0x18000d273  xor     eax, eax
0x18000d275  mov     [r15], ax
0x18000d279  mov     rax, [rdi+20h]
0x18000d27d  lea     rcx, ?s_varNameTblConstructed@NameTbl@@1VVAR@@A; VAR NameTbl::s_varNameTblConstructed
0x18000d284  cmp     rax, rcx
0x18000d287  jnz     loc_18000D48D
0x18000d28d  mov     rcx, [rdi+18h]
0x18000d291  lea     r14, [rdi+18h]
0x18000d295  mov     [rsp+0B8h+arg_18], rsi
0x18000d29d  test    rcx, rcx
0x18000d2a0  jz      loc_18000D5A7
0x18000d2a6  mov     rsi, [rcx+3E0h]
0x18000d2ad  test    rsi, rsi
0x18000d2b0  jnz     short loc_18000D2D7
0x18000d2b2  mov     rax, [rcx+50h]
0x18000d2b6  test    rax, rax
0x18000d2b9  jnz     loc_18000D5DF
0x18000d2bf  mov     rcx, [rcx+3D8h]; struct ThreadGlobals *
0x18000d2c6  call    ?GetAllocator@GcAlloc@@SAPEAV1@PEAVThreadGlobals@@@Z; GcAlloc::GetAllocator(ThreadGlobals *)
0x18000d2cb  mov     rsi, rax
0x18000d2ce  test    rax, rax
0x18000d2d1  jz      loc_18000D514
0x18000d2d7  mov     rbx, [rsi+10h]
0x18000d2db  mov     eax, [rbx+0Ch]
0x18000d2de  test    al, 1
0x18000d2e0  jnz     loc_18000D5C6
0x18000d2e6  cmp     qword ptr [rsi+20h], 0
0x18000d2eb  jz      loc_18000D507
0x18000d2f1  mov     rbx, [rsi+20h]
0x18000d2f5  mov     [rsp+0B8h+arg_10], rbp
0x18000d2fd  movsxd  rcx, dword ptr [rbx+8]
0x18000d301  test    ecx, ecx
0x18000d303  jle     loc_18000D520
0x18000d309  lea     eax, [rcx-1]
0x18000d30c  lea     rcx, [rcx+rcx*2]
0x18000d310  mov     [rbx+8], eax
0x18000d313  lea     rbx, [rbx+rcx*8]
0x18000d317  xor     eax, eax
0x18000d319  mov     [rbx], ax
0x18000d31c  mov     rsi, [rsi+10h]
0x18000d320  mov     ebp, [rsi+98h]
0x18000d326  test    ebp, ebp
0x18000d328  jz      loc_18000D581
0x18000d32e  inc     dword ptr [rsi+68h]
0x18000d331  inc     dword ptr [rsi+74h]
0x18000d334  cmp     dword ptr [rsi+8], 0
0x18000d338  mov     eax, [rsi+68h]
0x18000d33b  jnz     short loc_18000D352
0x18000d33d  cmp     eax, [rsi+78h]
0x18000d340  jge     loc_18000D594
0x18000d346  cmp     eax, cs:dword_1800B3CE4
0x18000d34c  jge     loc_18000D52D
0x18000d352  lea     rax, ?s_varNameTblConstructed@NameTbl@@1VVAR@@A; VAR NameTbl::s_varNameTblConstructed
0x18000d359  mov     word ptr [rbx], 81h
0x18000d35e  mov     [rbx+8], rdi
0x18000d362  cmp     [rdi+20h], rax
0x18000d366  jnz     loc_18000D4AE
0x18000d36c  mov     [rdi+20h], rbx
0x18000d370  mov     rbp, [rsp+0B8h+arg_10]
0x18000d378  mov     ecx, 80h
0x18000d37d  mov     [rsp+0B8h+var_88], cx
0x18000d382  mov     [rsp+0B8h+var_80], rbx
0x18000d387  mov     rsi, [rsp+0B8h+arg_18]
0x18000d38f  mov     rcx, [r14]
0x18000d392  lea     rax, [rsp+0B8h+var_88]
0x18000d397  mov     [rsp+0B8h+var_58], rax
0x18000d39c  mov     [rsp+0B8h+var_50], rcx
0x18000d3a1  mov     rax, [rcx+3D0h]
0x18000d3a8  mov     [rsp+0B8h+var_48], rax
0x18000d3ad  lea     rax, [rsp+0B8h+var_58]
0x18000d3b2  mov     [rcx+3D0h], rax
0x18000d3b9  xor     eax, eax
0x18000d3bb  mov     rcx, [r14]
0x18000d3be  mov     [rsp+0B8h+var_40], ax
0x18000d3c3  lea     rax, [rsp+0B8h+var_40]
0x18000d3c8  mov     [rsp+0B8h+var_70], rax
0x18000d3cd  mov     [rsp+0B8h+var_68], rcx
0x18000d3d2  mov     rax, [rcx+3D0h]
0x18000d3d9  mov     [rsp+0B8h+var_60], rax
0x18000d3de  lea     rax, [rsp+0B8h+var_70]
0x18000d3e3  mov     [rcx+3D0h], rax
0x18000d3ea  mov     rcx, [r14]
0x18000d3ed  cmp     dword ptr [rcx+14h], 0
0x18000d3f1  jnz     loc_18000D5EC
0x18000d3f7  mov     rdx, [rsp+0B8h+arg_20]
0x18000d3ff  mov     r9d, r13d
0x18000d402  mov     rax, [rdi+90h]
0x18000d409  mov     r8, r15
0x18000d40c  mov     [rsp+0B8h+var_98], r12
0x18000d411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d416  mov     ebx, eax
0x18000d418  mov     rcx, [rsp+0B8h+var_68]
0x18000d41d  mov     r14, [rsp+0B8h+var_28]
0x18000d425  mov     rax, [rcx+3D0h]
0x18000d42c  test    rax, rax
0x18000d42f  jz      short loc_18000D43C
0x18000d431  mov     rax, [rax+10h]
0x18000d435  mov     [rcx+3D0h], rax
0x18000d43c  mov     rcx, [rsp+0B8h+var_50]
0x18000d441  mov     rax, [rcx+3D0h]
0x18000d448  test    rax, rax
0x18000d44b  jz      short loc_18000D458
0x18000d44d  mov     rax, [rax+10h]
0x18000d451  mov     [rcx+3D0h], rax
0x18000d458  test    ebx, ebx
0x18000d45a  js      loc_18000D650
0x18000d460  mov     eax, ebx
0x18000d462  mov     rbx, [rsp+0B8h+arg_8]
0x18000d46a  add     rsp, 98h
0x18000d471  pop     r15
0x18000d473  pop     r13
0x18000d475  pop     r12
0x18000d477  pop     rdi
0x18000d478  retn
0x18000d479  mov     eax, 8000FFFFh
0x18000d47e  add     rsp, 98h
0x18000d485  pop     r15
0x18000d487  pop     r13
0x18000d489  pop     r12
0x18000d48b  pop     rdi
0x18000d48c  retn
0x18000d48d  test    rax, rax
0x18000d490  jz      loc_18000D28D
0x18000d496  mov     ecx, 80h
0x18000d49b  mov     [rsp+0B8h+var_80], rax
0x18000d4a0  mov     [rsp+0B8h+var_88], cx
0x18000d4a5  lea     r14, [rdi+18h]
0x18000d4a9  jmp     loc_18000D38F
0x18000d4ae  mov     rsi, [rdi+48h]
0x18000d4b2  lock inc dword ptr [rsi]
0x18000d4b5  lea     rcx, [rsi+38h]; this
0x18000d4b9  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x18000d4be  test    eax, eax
0x18000d4c0  jz      short loc_18000D4CF
0x18000d4c2  lea     rcx, [rsi+38h]; this
0x18000d4c6  mov     [rdi+20h], rbx
0x18000d4ca  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x18000d4cf  mov     eax, 0FFFFFFFFh
0x18000d4d4  lock xadd [rsi], eax
0x18000d4d8  cmp     eax, 1
0x18000d4db  jnz     loc_18000D370
0x18000d4e1  test    rsi, rsi
0x18000d4e4  jz      loc_18000D370
0x18000d4ea  cmp     byte ptr [rsi+61h], 0
0x18000d4ee  jz      short loc_18000D4FA
0x18000d4f0  lea     rcx, [rsi+38h]; lpCriticalSection
0x18000d4f4  call    cs:__imp_DeleteCriticalSection
0x18000d4fa  mov     rcx, rsi; Block
0x18000d4fd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d502  jmp     loc_18000D370
0x18000d507  call    ?PblkAlloc@GcBlockFactory@@QEAAPEAVGcBlock@@XZ; GcBlockFactory::PblkAlloc(void)
0x18000d50c  mov     r9, rax
0x18000d50f  test    rax, rax
0x18000d512  jnz     short loc_18000D553
0x18000d514  xor     eax, eax
0x18000d516  mov     [rsp+0B8h+var_88], ax
0x18000d51b  jmp     loc_18000D387
0x18000d520  mov     rax, [rbx+10h]
0x18000d524  mov     [rsi+20h], rax
0x18000d528  jmp     loc_18000D317
0x18000d52d  call    cs:__imp_GetTickCount
0x18000d533  sub     eax, ebp
0x18000d535  cmp     eax, 2710h
0x18000d53a  jbe     loc_18000D352
0x18000d540  and     dword ptr [rsi+9Ch], 0FFFFFFFEh
0x18000d547  jmp     short loc_18000D59B
0x18000d549  lea     r15, [rsp+0B8h+var_40]
0x18000d54e  jmp     loc_18000D279
0x18000d553  lea     rdx, [rsi+18h]; struct GcBlock **
0x18000d557  mov     rcx, r9; this
0x18000d55a  call    ?Link@GcBlock@@QEAAXPEAPEAV1@@Z; GcBlock::Link(GcBlock * *)
0x18000d55f  lea     rcx, [r9+10h]
0x18000d563  mov     [rsi+20h], rcx
0x18000d567  mov     word ptr [rcx], 8Ah
0x18000d56c  mov     dword ptr [r9+18h], 63h ; 'c'
0x18000d574  mov     qword ptr [r9+20h], 0
0x18000d57c  jmp     loc_18000D2F1
0x18000d581  call    cs:__imp_GetTickCount
0x18000d587  mov     ebp, eax
0x18000d589  mov     [rsi+98h], eax
0x18000d58f  jmp     loc_18000D32E
0x18000d594  or      dword ptr [rsi+9Ch], 1
0x18000d59b  mov     dword ptr [rsi+8], 1
0x18000d5a2  jmp     loc_18000D352
0x18000d5a7  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18000d5ad  call    cs:__imp_TlsGetValue
0x18000d5b3  mov     rcx, rax; struct ThreadGlobals *
0x18000d5b6  call    ?GetAllocator@GcAlloc@@SAPEAV1@PEAVThreadGlobals@@@Z; GcAlloc::GetAllocator(ThreadGlobals *)
0x18000d5bb  mov     rsi, rax
0x18000d5be  test    rax, rax
0x18000d5c1  jmp     loc_18000D2D1
0x18000d5c6  test    al, 2
0x18000d5c8  jnz     loc_18000D2E6
0x18000d5ce  mov     rcx, rbx; this
0x18000d5d1  call    ?ClearMark@GcContext@@QEAAXXZ; GcContext::ClearMark(void)
0x18000d5d6  or      dword ptr [rbx+0Ch], 2
0x18000d5da  jmp     loc_18000D2E6
0x18000d5df  mov     rcx, rax; this
0x18000d5e2  call    ?GetGcAlloc@CScriptRuntime@@QEAAPEAVGcAlloc@@XZ; CScriptRuntime::GetGcAlloc(void)
0x18000d5e7  jmp     loc_18000D2CB
0x18000d5ec  mov     rcx, [rcx+8]
0x18000d5f0  mov     edx, 1
0x18000d5f5  mov     r8d, [rdi+88h]
0x18000d5fc  mov     rax, [rcx]
0x18000d5ff  mov     rax, [rax+38h]
0x18000d603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d608  mov     rdx, [rsp+0B8h+arg_20]
0x18000d610  mov     r9d, r13d
0x18000d613  mov     rcx, [r14]
0x18000d616  mov     r8, r15
0x18000d619  mov     rax, [rdi+90h]
0x18000d620  mov     [rsp+0B8h+var_98], r12
0x18000d625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d62a  mov     rcx, [r14]
0x18000d62d  mov     ebx, eax
0x18000d62f  mov     edx, 1
0x18000d634  mov     rcx, [rcx+8]
0x18000d638  mov     r8, [rcx]
0x18000d63b  mov     rax, [r8+40h]
0x18000d63f  mov     r8d, [rdi+88h]
0x18000d646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d64b  jmp     loc_18000D418
0x18000d650  xor     eax, eax
0x18000d652  mov     [r15], ax
0x18000d656  jmp     loc_18000D460
```
