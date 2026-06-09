# CCustomDataTable::InitFrom(CCustomDataTable const &)

- ea: `0x180038e4c`
- end: `0x18003901b`
- name: `?InitFrom@CCustomDataTable@@QEAAXAEBV1@@Z`
- size: `463`
- prototype: `void __fastcall(CCustomDataTable *__hidden this, const struct CCustomDataTable *)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180035410`
- `0x180037470`
- `0x180039810`

## callees

- `0x180001e60`
- `0x180038e4c`
- `0x1800396f8`
- `0x180039720`
- `0x180053a48`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038e8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038f4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038e8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038f4e`

## pseudocode

```c
void __fastcall CCustomDataTable::InitFrom(CCustomDataTable *this, const struct CCustomDataTable *a2)
{
  __int64 v3; // rcx
  int v5; // esi
  __int64 v6; // rax
  unsigned __int64 v7; // r14
  unsigned __int16 *v8; // rax
  int v9; // eax
  unsigned __int64 v10; // rcx
  LPVOID v11; // rax
  int i; // r8d
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rcx

  *((_DWORD *)this + 54) = 0;
  v3 = *((_QWORD *)a2 + 14);
  v5 = -2147024882;
  if ( v3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(v3 + 2 * v6) );
    v7 = v6 + 1;
    v8 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v6 + 1));
    *((_QWORD *)this + 14) = v8;
    if ( v8 )
      v9 = StringCchCopyW(v8, v7, *((const unsigned __int16 **)a2 + 14));
    else
      v9 = -2147024882;
    *((_DWORD *)this + 54) = v9;
    if ( v9 < 0 )
      return;
  }
  else
  {
    *((_QWORD *)this + 14) = 0;
  }
  *((_QWORD *)this + 15) = *((_QWORD *)a2 + 15);
  *((_DWORD *)this + 32) = *((_DWORD *)a2 + 32);
  v10 = *((unsigned int *)a2 + 35);
  *((_DWORD *)this + 35) = v10;
  *((_DWORD *)this + 34) = *((_DWORD *)a2 + 34);
  *((_DWORD *)this + 36) = *((_DWORD *)a2 + 36);
  *((_DWORD *)this + 26) = *((_DWORD *)a2 + 26);
  *((_DWORD *)this + 38) = *((_DWORD *)a2 + 38);
  *((_DWORD *)this + 37) = *((_DWORD *)a2 + 37);
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_DWORD *)this + 47) = *((_DWORD *)a2 + 47);
  if ( !*((_QWORD *)a2 + 24) )
  {
    *((_QWORD *)this + 24) = 0;
LABEL_19:
    if ( (unsigned int)CCustomDataTable::UsingLowerTable(this) )
    {
      v17 = *((_QWORD *)a2 + 25);
      if ( v17 )
      {
        (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v17 + 88LL))(v17, (char *)this + 200);
        *((_DWORD *)this + 54) = 0;
      }
    }
    if ( (unsigned int)CCustomDataTable::UsingStdCache(this) )
      *((_DWORD *)this + 54) = CSimpleDataTableCursor::InternalCloneCursor(
                                 (CCustomDataTable *)((char *)this + 40),
                                 (struct CSimpleDataTableCursor *)(((unsigned __int64)a2 + 40) & -(__int64)(a2 != 0)));
    return;
  }
  v11 = CoTaskMemAlloc(saturated_mul(v10, 0xCu));
  *((_QWORD *)this + 24) = v11;
  if ( v11 )
  {
    for ( i = 0; i < *((_DWORD *)this + 35); *(_DWORD *)(v13 + 4 * v15 + 8) = *(_DWORD *)(v16 + 4 * v15 + 8) )
    {
      v13 = *((_QWORD *)this + 24);
      v14 = i++;
      v15 = 3 * v14;
      v16 = *((_QWORD *)a2 + 24);
      *(_QWORD *)(v13 + 4 * v15) = *(_QWORD *)(v16 + 4 * v15);
    }
    v5 = *((_DWORD *)this + 54);
  }
  else
  {
    *((_DWORD *)this + 54) = -2147024882;
  }
  if ( v5 >= 0 )
    goto LABEL_19;
}

```

## disassembly

```asm
0x180038e4c  push    rbx
0x180038e4e  push    rbp
0x180038e4f  push    rsi
0x180038e50  push    rdi
0x180038e51  push    r14
0x180038e53  push    r15
0x180038e55  sub     rsp, 28h
0x180038e59  xor     ebp, ebp
0x180038e5b  mov     rbx, rcx
0x180038e5e  mov     [rcx+0D8h], ebp
0x180038e64  or      r15, 0FFFFFFFFFFFFFFFFh
0x180038e68  mov     rcx, [rdx+70h]
0x180038e6c  mov     rdi, rdx
0x180038e6f  mov     esi, 8007000Eh
0x180038e74  test    rcx, rcx
0x180038e77  jz      short loc_180038EBF
0x180038e79  mov     rax, r15
0x180038e7c  inc     rax
0x180038e7f  cmp     [rcx+rax*2], bp
0x180038e83  jnz     short loc_180038E7C
0x180038e85  lea     r14, [rax+1]
0x180038e89  lea     rcx, [r14+r14]; cb
0x180038e8d  call    cs:__imp_CoTaskMemAlloc
0x180038e93  mov     [rbx+70h], rax
0x180038e97  test    rax, rax
0x180038e9a  jz      short loc_180038EAD
0x180038e9c  mov     r8, [rdi+70h]; unsigned __int16 *
0x180038ea0  mov     rdx, r14; unsigned __int64
0x180038ea3  mov     rcx, rax; unsigned __int16 *
0x180038ea6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180038eab  jmp     short loc_180038EAF
0x180038ead  mov     eax, esi
0x180038eaf  mov     [rbx+0D8h], eax
0x180038eb5  test    eax, eax
0x180038eb7  js      loc_18003900E
0x180038ebd  jmp     short loc_180038EC3
0x180038ebf  mov     [rbx+70h], rbp
0x180038ec3  mov     rax, [rdi+78h]
0x180038ec7  lea     r14, [rbx+0C8h]
0x180038ece  mov     [rbx+78h], rax
0x180038ed2  mov     eax, [rdi+80h]
0x180038ed8  mov     [rbx+80h], eax
0x180038ede  mov     ecx, [rdi+8Ch]
0x180038ee4  mov     [rbx+8Ch], ecx
0x180038eea  mov     eax, [rdi+88h]
0x180038ef0  mov     [rbx+88h], eax
0x180038ef6  mov     eax, [rdi+90h]
0x180038efc  mov     [rbx+90h], eax
0x180038f02  mov     eax, [rdi+68h]
0x180038f05  mov     [rbx+68h], eax
0x180038f08  mov     eax, [rdi+98h]
0x180038f0e  mov     [rbx+98h], eax
0x180038f14  mov     eax, [rdi+94h]
0x180038f1a  mov     [rbx+94h], eax
0x180038f20  mov     [r14], rbp
0x180038f23  mov     [rbx+0D0h], rbp
0x180038f2a  mov     eax, [rdi+0BCh]
0x180038f30  mov     [rbx+0BCh], eax
0x180038f36  cmp     [rdi+0C0h], rbp
0x180038f3d  jz      short loc_180038FB2
0x180038f3f  mov     eax, 0Ch
0x180038f44  mul     rcx
0x180038f47  cmovb   rax, r15
0x180038f4b  mov     rcx, rax; cb
0x180038f4e  call    cs:__imp_CoTaskMemAlloc
0x180038f54  mov     [rbx+0C0h], rax
0x180038f5b  test    rax, rax
0x180038f5e  jz      short loc_180038FA6
0x180038f60  mov     r8d, ebp
0x180038f63  cmp     [rbx+8Ch], ebp
0x180038f69  jle     short loc_180038F9E
0x180038f6b  mov     rcx, [rbx+0C0h]
0x180038f72  movsxd  rax, r8d
0x180038f75  inc     r8d
0x180038f78  lea     rdx, [rax+rax*2]
0x180038f7c  mov     rax, [rdi+0C0h]
0x180038f83  movsd   xmm0, qword ptr [rax+rdx*4]
0x180038f88  movsd   qword ptr [rcx+rdx*4], xmm0
0x180038f8d  mov     eax, [rax+rdx*4+8]
0x180038f91  mov     [rcx+rdx*4+8], eax
0x180038f95  cmp     r8d, [rbx+8Ch]
0x180038f9c  jl      short loc_180038F6B
0x180038f9e  mov     esi, [rbx+0D8h]
0x180038fa4  jmp     short loc_180038FAC
0x180038fa6  mov     [rbx+0D8h], esi
0x180038fac  test    esi, esi
0x180038fae  js      short loc_18003900E
0x180038fb0  jmp     short loc_180038FB9
0x180038fb2  mov     [rbx+0C0h], rbp
0x180038fb9  mov     rcx, rbx; this
0x180038fbc  call    ?UsingLowerTable@CCustomDataTable@@QEAAHXZ; CCustomDataTable::UsingLowerTable(void)
0x180038fc1  test    eax, eax
0x180038fc3  jz      short loc_180038FE6
0x180038fc5  mov     rcx, [rdi+0C8h]
0x180038fcc  test    rcx, rcx
0x180038fcf  jz      short loc_180038FE6
0x180038fd1  mov     rax, [rcx]
0x180038fd4  mov     rdx, r14
0x180038fd7  mov     rax, [rax+58h]
0x180038fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038fe0  mov     [rbx+0D8h], ebp
0x180038fe6  mov     rcx, rbx; this
0x180038fe9  call    ?UsingStdCache@CCustomDataTable@@QEAAHXZ; CCustomDataTable::UsingStdCache(void)
0x180038fee  test    eax, eax
0x180038ff0  jz      short loc_18003900E
0x180038ff2  lea     rax, [rdi+28h]
0x180038ff6  neg     rdi
0x180038ff9  lea     rcx, [rbx+28h]; this
0x180038ffd  sbb     rdx, rdx
0x180039000  and     rdx, rax; struct CSimpleDataTableCursor *
0x180039003  call    ?InternalCloneCursor@CSimpleDataTableCursor@@QEAAJPEAV1@@Z; CSimpleDataTableCursor::InternalCloneCursor(CSimpleDataTableCursor *)
0x180039008  mov     [rbx+0D8h], eax
0x18003900e  add     rsp, 28h
0x180039012  pop     r15
0x180039014  pop     r14
0x180039016  pop     rdi
0x180039017  pop     rsi
0x180039018  pop     rbp
0x180039019  pop     rbx
0x18003901a  retn
```
