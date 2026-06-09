# CComponentData::Destroy(void)

- ea: `0x180005de0`
- end: `0x180005f44`
- name: `?Destroy@CComponentData@@UEAAJXZ`
- size: `356`
- prototype: `__int64 __fastcall(CComponentData *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800018a0`
- `0x180004f68`
- `0x180005de0`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall CComponentData::Destroy(CComponentData *this)
{
  __int16 v1; // ax
  __int64 i; // rax
  __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 j; // r10
  __int64 v7; // rbx
  __int64 v8; // r10
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx

  v1 = *((_WORD *)this + 24);
  if ( (v1 & 8) != 0 )
  {
    for ( i = 0; (unsigned int)i < dword_180031E9C; i = (unsigned int)(i + 1) )
    {
      if ( *((CComponentData **)Src + i) == (CComponentData *)((char *)this - 8) )
      {
        *((_QWORD *)Src + i) = 0;
        --dword_180031E98;
        break;
      }
    }
    v1 = *((_WORD *)this + 24) & 0xFFF7;
  }
  *((_WORD *)this + 24) = v1 | 4;
  CLruCache::Clear((CLruCache *)&g_DirSearchCache);
  v4 = *((_QWORD *)this + 9);
  if ( v4 )
  {
    do
    {
      v5 = *(_QWORD *)(v4 + 8);
      (**(void (__fastcall ***)(__int64, __int64))v4)(v4, 1);
      v4 = v5;
    }
    while ( v5 );
  }
  *((_QWORD *)this + 9) = 0;
  for ( j = *((_QWORD *)this + 7); j; j = (v7 - 56) & -(__int64)(v7 != 0) )
  {
    v7 = *(_QWORD *)(j + 64);
    CDLink::UnLink((CDLink *)(j + 56));
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  v9 = *((_QWORD *)this + 143);
  *((_QWORD *)this + 7) = 0;
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)this + 143) = 0;
  }
  v10 = *((_QWORD *)this + 144);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    *((_QWORD *)this + 144) = 0;
  }
  v11 = *((_QWORD *)this + 145);
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    *((_QWORD *)this + 145) = 0;
  }
  v12 = *((_QWORD *)this + 146);
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    *((_QWORD *)this + 146) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180005de0  mov     [rsp+arg_0], rbx
0x180005de5  push    rdi
0x180005de6  sub     rsp, 20h
0x180005dea  movzx   eax, word ptr [rcx+30h]
0x180005dee  mov     rdi, rcx
0x180005df1  test    al, 8
0x180005df3  jz      short loc_180005E2E
0x180005df5  mov     rdx, cs:Src
0x180005dfc  lea     r8, [rcx-8]
0x180005e00  xor     eax, eax
0x180005e02  cmp     eax, cs:dword_180031E9C
0x180005e08  jnb     short loc_180005E22
0x180005e0a  cmp     [rdx+rax*8], r8
0x180005e0e  jz      short loc_180005E14
0x180005e10  inc     eax
0x180005e12  jmp     short loc_180005E02
0x180005e14  mov     qword ptr [rdx+rax*8], 0
0x180005e1c  dec     cs:dword_180031E98
0x180005e22  movzx   eax, word ptr [rcx+30h]
0x180005e26  mov     ecx, 0FFF7h
0x180005e2b  and     ax, cx
0x180005e2e  or      ax, 4
0x180005e32  lea     rcx, ?g_DirSearchCache@@3VCIDsCache@@A; this
0x180005e39  mov     [rdi+30h], ax
0x180005e3d  call    ?Clear@CLruCache@@UEAAXXZ; CLruCache::Clear(void)
0x180005e42  mov     rcx, [rdi+48h]
0x180005e46  test    rcx, rcx
0x180005e49  jz      short loc_180005E67
0x180005e4b  mov     rax, [rcx]
0x180005e4e  mov     edx, 1
0x180005e53  mov     rbx, [rcx+8]
0x180005e57  mov     rax, [rax]
0x180005e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e5f  mov     rcx, rbx
0x180005e62  test    rbx, rbx
0x180005e65  jnz     short loc_180005E4B
0x180005e67  mov     qword ptr [rdi+48h], 0
0x180005e6f  mov     r10, [rdi+38h]
0x180005e73  test    r10, r10
0x180005e76  jz      short loc_180005EA3
0x180005e78  mov     rbx, [r10+40h]
0x180005e7c  lea     rcx, [r10+38h]; this
0x180005e80  call    ?UnLink@CDLink@@QEAAXXZ; CDLink::UnLink(void)
0x180005e85  mov     r9, [r10]
0x180005e88  mov     rcx, r10
0x180005e8b  mov     rax, [r9+10h]
0x180005e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e94  lea     rax, [rbx-38h]
0x180005e98  neg     rbx
0x180005e9b  sbb     r10, r10
0x180005e9e  and     r10, rax
0x180005ea1  jnz     short loc_180005E78
0x180005ea3  mov     rcx, [rdi+478h]
0x180005eaa  mov     qword ptr [rdi+38h], 0
0x180005eb2  test    rcx, rcx
0x180005eb5  jz      short loc_180005ECE
0x180005eb7  mov     rax, [rcx]
0x180005eba  mov     rax, [rax+10h]
0x180005ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ec3  mov     qword ptr [rdi+478h], 0
0x180005ece  mov     rcx, [rdi+480h]
0x180005ed5  test    rcx, rcx
0x180005ed8  jz      short loc_180005EF1
0x180005eda  mov     rax, [rcx]
0x180005edd  mov     rax, [rax+10h]
0x180005ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ee6  mov     qword ptr [rdi+480h], 0
0x180005ef1  mov     rcx, [rdi+488h]
0x180005ef8  test    rcx, rcx
0x180005efb  jz      short loc_180005F14
0x180005efd  mov     rax, [rcx]
0x180005f00  mov     rax, [rax+10h]
0x180005f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f09  mov     qword ptr [rdi+488h], 0
0x180005f14  mov     rcx, [rdi+490h]
0x180005f1b  test    rcx, rcx
0x180005f1e  jz      short loc_180005F37
0x180005f20  mov     rax, [rcx]
0x180005f23  mov     rax, [rax+10h]
0x180005f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f2c  mov     qword ptr [rdi+490h], 0
0x180005f37  mov     rbx, [rsp+28h+arg_0]
0x180005f3c  xor     eax, eax
0x180005f3e  add     rsp, 20h
0x180005f42  pop     rdi
0x180005f43  retn
```
