# NatFncObj::Call(VAR *,int,VAR *,VAR *,ulong)

- ea: `0x18000a3e0`
- end: `0x18000a83b`
- name: `?Call@NatFncObj@@UEAAJPEAVVAR@@H00K@Z`
- size: `1115`
- prototype: `__int64 __fastcall(NatFncObj *__hidden this, struct VAR *, int, struct VAR *, struct VAR *, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x180005ce8`
- `0x18000a3e0`
- `0x18000abf8`
- `0x18000c860`
- `0x18000c8c0`
- `0x180014cd0`
- `0x18003c414`
- `0x180053048`
- `0x1800585c4`
- `0x180098010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000a6bc`
- `KERNEL32!DeleteCriticalSection` at `0x18000a6bc`
- `KERNEL32!TlsGetValue` at `0x18000a401`
- `KERNEL32!TlsGetValue` at `0x18000a787`
- `KERNEL32!TlsGetValue` at `0x18000a401`
- `KERNEL32!TlsGetValue` at `0x18000a787`
- `KERNEL32!GetTickCount` at `0x18000a6fb`
- `KERNEL32!GetTickCount` at `0x18000a755`
- `KERNEL32!GetTickCount` at `0x18000a6fb`
- `KERNEL32!GetTickCount` at `0x18000a755`

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
            if ( v22 < dword_1800B5CE4 || GetTickCount() - TickCount <= 0x2710 )
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
0x18000a3e0  push    rdi
0x18000a3e2  push    r12
0x18000a3e4  push    r13
0x18000a3e6  push    r15
0x18000a3e8  sub     rsp, 98h
0x18000a3ef  mov     rdi, rcx
0x18000a3f2  mov     r12, r9
0x18000a3f5  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18000a3fb  mov     r13d, r8d
0x18000a3fe  mov     r15, rdx
0x18000a401  call    cs:__imp_TlsGetValue
0x18000a408  nop     dword ptr [rax+rax+00h]
0x18000a40d  test    rax, rax
0x18000a410  jz      short loc_18000A416
0x18000a412  mov     rax, [rax+20h]
0x18000a416  cmp     rax, [rdi+48h]
0x18000a41a  jnz     loc_18000A640
0x18000a420  mov     [rsp+0B8h+arg_8], rbx
0x18000a428  mov     [rsp+0B8h+var_28], r14
0x18000a430  test    r15, r15
0x18000a433  jz      loc_18000A71D
0x18000a439  xor     eax, eax
0x18000a43b  mov     [r15], ax
0x18000a43f  mov     rax, [rdi+20h]
0x18000a443  lea     rcx, ?s_varNameTblConstructed@NameTbl@@1VVAR@@A; VAR NameTbl::s_varNameTblConstructed
0x18000a44a  cmp     rax, rcx
0x18000a44d  jnz     loc_18000A655
0x18000a453  mov     rcx, [rdi+18h]
0x18000a457  lea     r14, [rdi+18h]
0x18000a45b  mov     [rsp+0B8h+arg_18], rsi
0x18000a463  test    rcx, rcx
0x18000a466  jz      loc_18000A781
0x18000a46c  mov     rsi, [rcx+3E0h]
0x18000a473  test    rsi, rsi
0x18000a476  jnz     short loc_18000A49D
0x18000a478  mov     rax, [rcx+50h]
0x18000a47c  test    rax, rax
0x18000a47f  jnz     loc_18000A7BF
0x18000a485  mov     rcx, [rcx+3D8h]; struct ThreadGlobals *
0x18000a48c  call    ?GetAllocator@GcAlloc@@SAPEAV1@PEAVThreadGlobals@@@Z; GcAlloc::GetAllocator(ThreadGlobals *)
0x18000a491  mov     rsi, rax
0x18000a494  test    rax, rax
0x18000a497  jz      loc_18000A6E2
0x18000a49d  mov     rbx, [rsi+10h]
0x18000a4a1  mov     eax, [rbx+0Ch]
0x18000a4a4  test    al, 1
0x18000a4a6  jnz     loc_18000A7A6
0x18000a4ac  cmp     qword ptr [rsi+20h], 0
0x18000a4b1  jz      loc_18000A6D5
0x18000a4b7  mov     rbx, [rsi+20h]
0x18000a4bb  mov     [rsp+0B8h+arg_10], rbp
0x18000a4c3  movsxd  rcx, dword ptr [rbx+8]
0x18000a4c7  test    ecx, ecx
0x18000a4c9  jle     loc_18000A6EE
0x18000a4cf  lea     eax, [rcx-1]
0x18000a4d2  lea     rcx, [rcx+rcx*2]
0x18000a4d6  mov     [rbx+8], eax
0x18000a4d9  lea     rbx, [rbx+rcx*8]
0x18000a4dd  xor     eax, eax
0x18000a4df  mov     [rbx], ax
0x18000a4e2  mov     rsi, [rsi+10h]
0x18000a4e6  mov     ebp, [rsi+98h]
0x18000a4ec  test    ebp, ebp
0x18000a4ee  jz      loc_18000A755
0x18000a4f4  inc     dword ptr [rsi+68h]
0x18000a4f7  inc     dword ptr [rsi+74h]
0x18000a4fa  cmp     dword ptr [rsi+8], 0
0x18000a4fe  mov     eax, [rsi+68h]
0x18000a501  jnz     short loc_18000A518
0x18000a503  cmp     eax, [rsi+78h]
0x18000a506  jge     loc_18000A76E
0x18000a50c  cmp     eax, cs:dword_1800B5CE4
0x18000a512  jge     loc_18000A6FB
0x18000a518  lea     rax, ?s_varNameTblConstructed@NameTbl@@1VVAR@@A; VAR NameTbl::s_varNameTblConstructed
0x18000a51f  mov     word ptr [rbx], 81h
0x18000a524  mov     [rbx+8], rdi
0x18000a528  cmp     [rdi+20h], rax
0x18000a52c  jnz     loc_18000A676
0x18000a532  mov     [rdi+20h], rbx
0x18000a536  mov     rbp, [rsp+0B8h+arg_10]
0x18000a53e  mov     ecx, 80h
0x18000a543  mov     [rsp+0B8h+var_88], cx
0x18000a548  mov     [rsp+0B8h+var_80], rbx
0x18000a54d  mov     rsi, [rsp+0B8h+arg_18]
0x18000a555  mov     rcx, [r14]
0x18000a558  lea     rax, [rsp+0B8h+var_88]
0x18000a55d  mov     [rsp+0B8h+var_58], rax
0x18000a562  mov     [rsp+0B8h+var_50], rcx
0x18000a567  mov     rax, [rcx+3D0h]
0x18000a56e  mov     [rsp+0B8h+var_48], rax
0x18000a573  lea     rax, [rsp+0B8h+var_58]
0x18000a578  mov     [rcx+3D0h], rax
0x18000a57f  xor     eax, eax
0x18000a581  mov     rcx, [r14]
0x18000a584  mov     [rsp+0B8h+var_40], ax
0x18000a589  lea     rax, [rsp+0B8h+var_40]
0x18000a58e  mov     [rsp+0B8h+var_70], rax
0x18000a593  mov     [rsp+0B8h+var_68], rcx
0x18000a598  mov     rax, [rcx+3D0h]
0x18000a59f  mov     [rsp+0B8h+var_60], rax
0x18000a5a4  lea     rax, [rsp+0B8h+var_70]
0x18000a5a9  mov     [rcx+3D0h], rax
0x18000a5b0  mov     rcx, [r14]
0x18000a5b3  cmp     dword ptr [rcx+14h], 0
0x18000a5b7  jnz     loc_18000A7CC
0x18000a5bd  mov     rdx, [rsp+0B8h+arg_20]
0x18000a5c5  mov     r9d, r13d
0x18000a5c8  mov     rax, [rdi+90h]
0x18000a5cf  mov     r8, r15
0x18000a5d2  mov     [rsp+0B8h+var_98], r12
0x18000a5d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5dc  mov     ebx, eax
0x18000a5de  mov     rcx, [rsp+0B8h+var_68]
0x18000a5e3  mov     r14, [rsp+0B8h+var_28]
0x18000a5eb  mov     rax, [rcx+3D0h]
0x18000a5f2  test    rax, rax
0x18000a5f5  jz      short loc_18000A602
0x18000a5f7  mov     rax, [rax+10h]
0x18000a5fb  mov     [rcx+3D0h], rax
0x18000a602  mov     rcx, [rsp+0B8h+var_50]
0x18000a607  mov     rax, [rcx+3D0h]
0x18000a60e  test    rax, rax
0x18000a611  jz      short loc_18000A61E
0x18000a613  mov     rax, [rax+10h]
0x18000a617  mov     [rcx+3D0h], rax
0x18000a61e  test    ebx, ebx
0x18000a620  js      loc_18000A830
0x18000a626  mov     eax, ebx
0x18000a628  mov     rbx, [rsp+0B8h+arg_8]
0x18000a630  add     rsp, 98h
0x18000a637  pop     r15
0x18000a639  pop     r13
0x18000a63b  pop     r12
0x18000a63d  pop     rdi
0x18000a63e  retn
0x18000a640  mov     eax, 8000FFFFh
0x18000a645  add     rsp, 98h
0x18000a64c  pop     r15
0x18000a64e  pop     r13
0x18000a650  pop     r12
0x18000a652  pop     rdi
0x18000a653  retn
0x18000a655  test    rax, rax
0x18000a658  jz      loc_18000A453
0x18000a65e  mov     ecx, 80h
0x18000a663  mov     [rsp+0B8h+var_80], rax
0x18000a668  mov     [rsp+0B8h+var_88], cx
0x18000a66d  lea     r14, [rdi+18h]
0x18000a671  jmp     loc_18000A555
0x18000a676  mov     rsi, [rdi+48h]
0x18000a67a  lock inc dword ptr [rsi]
0x18000a67d  lea     rcx, [rsi+38h]; this
0x18000a681  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x18000a686  test    eax, eax
0x18000a688  jz      short loc_18000A697
0x18000a68a  lea     rcx, [rsi+38h]; this
0x18000a68e  mov     [rdi+20h], rbx
0x18000a692  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x18000a697  mov     eax, 0FFFFFFFFh
0x18000a69c  lock xadd [rsi], eax
0x18000a6a0  cmp     eax, 1
0x18000a6a3  jnz     loc_18000A536
0x18000a6a9  test    rsi, rsi
0x18000a6ac  jz      loc_18000A536
0x18000a6b2  cmp     byte ptr [rsi+61h], 0
0x18000a6b6  jz      short loc_18000A6C8
0x18000a6b8  lea     rcx, [rsi+38h]; lpCriticalSection
0x18000a6bc  call    cs:__imp_DeleteCriticalSection
0x18000a6c3  nop     dword ptr [rax+rax+00h]
0x18000a6c8  mov     rcx, rsi; Block
0x18000a6cb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a6d0  jmp     loc_18000A536
0x18000a6d5  call    ?PblkAlloc@GcBlockFactory@@QEAAPEAVGcBlock@@XZ; GcBlockFactory::PblkAlloc(void)
0x18000a6da  mov     r9, rax
0x18000a6dd  test    rax, rax
0x18000a6e0  jnz     short loc_18000A727
0x18000a6e2  xor     eax, eax
0x18000a6e4  mov     [rsp+0B8h+var_88], ax
0x18000a6e9  jmp     loc_18000A54D
0x18000a6ee  mov     rax, [rbx+10h]
0x18000a6f2  mov     [rsi+20h], rax
0x18000a6f6  jmp     loc_18000A4DD
0x18000a6fb  call    cs:__imp_GetTickCount
0x18000a702  nop     dword ptr [rax+rax+00h]
0x18000a707  sub     eax, ebp
0x18000a709  cmp     eax, 2710h
0x18000a70e  jbe     loc_18000A518
0x18000a714  and     dword ptr [rsi+9Ch], 0FFFFFFFEh
0x18000a71b  jmp     short loc_18000A775
0x18000a71d  lea     r15, [rsp+0B8h+var_40]
0x18000a722  jmp     loc_18000A43F
0x18000a727  lea     rdx, [rsi+18h]; struct GcBlock **
0x18000a72b  mov     rcx, r9; this
0x18000a72e  call    ?Link@GcBlock@@QEAAXPEAPEAV1@@Z; GcBlock::Link(GcBlock * *)
0x18000a733  lea     rcx, [r9+10h]
0x18000a737  mov     [rsi+20h], rcx
0x18000a73b  mov     word ptr [rcx], 8Ah
0x18000a740  mov     dword ptr [r9+18h], 63h ; 'c'
0x18000a748  mov     qword ptr [r9+20h], 0
0x18000a750  jmp     loc_18000A4B7
0x18000a755  call    cs:__imp_GetTickCount
0x18000a75c  nop     dword ptr [rax+rax+00h]
0x18000a761  mov     ebp, eax
0x18000a763  mov     [rsi+98h], eax
0x18000a769  jmp     loc_18000A4F4
0x18000a76e  or      dword ptr [rsi+9Ch], 1
0x18000a775  mov     dword ptr [rsi+8], 1
0x18000a77c  jmp     loc_18000A518
0x18000a781  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18000a787  call    cs:__imp_TlsGetValue
0x18000a78e  nop     dword ptr [rax+rax+00h]
0x18000a793  mov     rcx, rax; struct ThreadGlobals *
0x18000a796  call    ?GetAllocator@GcAlloc@@SAPEAV1@PEAVThreadGlobals@@@Z; GcAlloc::GetAllocator(ThreadGlobals *)
0x18000a79b  mov     rsi, rax
0x18000a79e  test    rax, rax
0x18000a7a1  jmp     loc_18000A497
0x18000a7a6  test    al, 2
0x18000a7a8  jnz     loc_18000A4AC
0x18000a7ae  mov     rcx, rbx; this
0x18000a7b1  call    ?ClearMark@GcContext@@QEAAXXZ; GcContext::ClearMark(void)
0x18000a7b6  or      dword ptr [rbx+0Ch], 2
0x18000a7ba  jmp     loc_18000A4AC
0x18000a7bf  mov     rcx, rax; this
0x18000a7c2  call    ?GetGcAlloc@CScriptRuntime@@QEAAPEAVGcAlloc@@XZ; CScriptRuntime::GetGcAlloc(void)
0x18000a7c7  jmp     loc_18000A491
0x18000a7cc  mov     rcx, [rcx+8]
0x18000a7d0  mov     edx, 1
0x18000a7d5  mov     r8d, [rdi+88h]
0x18000a7dc  mov     rax, [rcx]
0x18000a7df  mov     rax, [rax+38h]
0x18000a7e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7e8  mov     rdx, [rsp+0B8h+arg_20]
0x18000a7f0  mov     r9d, r13d
0x18000a7f3  mov     rcx, [r14]
0x18000a7f6  mov     r8, r15
0x18000a7f9  mov     rax, [rdi+90h]
0x18000a800  mov     [rsp+0B8h+var_98], r12
0x18000a805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a80a  mov     rcx, [r14]
0x18000a80d  mov     ebx, eax
0x18000a80f  mov     edx, 1
0x18000a814  mov     rcx, [rcx+8]
0x18000a818  mov     r8, [rcx]
0x18000a81b  mov     rax, [r8+40h]
0x18000a81f  mov     r8d, [rdi+88h]
0x18000a826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a82b  jmp     loc_18000A5DE
0x18000a830  xor     eax, eax
0x18000a832  mov     [r15], ax
0x18000a836  jmp     loc_18000A626
```
