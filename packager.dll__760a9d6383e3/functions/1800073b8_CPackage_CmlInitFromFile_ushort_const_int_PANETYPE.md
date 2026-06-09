# CPackage::CmlInitFromFile(ushort const *,int,PANETYPE)

- ea: `0x1800073b8`
- end: `0x1800074d7`
- name: `?CmlInitFromFile@CPackage@@IEAAJPEBGHW4PANETYPE@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180004c10`
- `0x180006830`
- `0x180009144`

## callees

- `0x1800073b8`
- `0x18000a43c`
- `0x18000a6ec`
- `0x18000baa0`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CPackage::CmlInitFromFile(__int64 a1, const unsigned __int16 *a2, int a3)
{
  _DWORD *v4; // rcx
  _DWORD *v7; // rax
  unsigned int v8; // edi
  const unsigned __int16 *v9; // r8
  __int64 v10; // rcx
  _WORD *v11; // rax
  __int64 v12; // rdx
  _WORD *v13; // rcx
  struct _IC *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rcx

  v4 = *(_DWORD **)(a1 + 120);
  if ( v4 || (v7 = operator new(0x3ECu), *(_QWORD *)(a1 + 120) = v7, (v4 = v7) != 0) )
  {
    v8 = 0;
    *v4 = *(_DWORD *)(a1 + 132);
    v9 = a2;
    v10 = 2147483646;
    v11 = (_WORD *)(*(_QWORD *)(a1 + 120) + 4LL);
    *(_DWORD *)(a1 + 104) = 1;
    v12 = 500;
    do
    {
      if ( !v10 )
        break;
      if ( !*v9 )
        break;
      *v11++ = *v9++;
      --v10;
      --v12;
    }
    while ( v12 );
    v13 = v11 - 1;
    if ( v12 )
      v13 = v11;
    *v13 = 0;
    *(_DWORD *)(a1 + 152) = 1;
    if ( a3 )
    {
      CPackage::_DestroyIC((CPackage *)a1);
      v14 = CPackage::_IconCreateFromFile((CPackage *)a1, a2);
      v15 = *(_QWORD *)(a1 + 160);
      *(_QWORD *)(a1 + 96) = v14;
      if ( v15 )
        (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v15 + 48LL))(
          v15,
          (a1 + 32) & -(__int64)(a1 != 0),
          0,
          0);
      v16 = *(_QWORD *)(a1 + 200);
      if ( v16 )
        (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v16 + 32LL))(
          v16,
          *(unsigned int *)(a1 + 208),
          *(unsigned int *)(a1 + 212));
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v8;
}

```

## disassembly

```asm
0x1800073b8  push    rbx
0x1800073ba  push    rbp
0x1800073bb  push    rsi
0x1800073bc  push    rdi
0x1800073bd  push    r14
0x1800073bf  sub     rsp, 30h
0x1800073c3  mov     rbx, rcx
0x1800073c6  xor     r14d, r14d
0x1800073c9  mov     rcx, [rcx+78h]
0x1800073cd  mov     ebp, r8d
0x1800073d0  mov     rsi, rdx
0x1800073d3  test    rcx, rcx
0x1800073d6  jnz     short loc_1800073F8
0x1800073d8  mov     ecx, 3ECh; unsigned __int64
0x1800073dd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800073e2  mov     [rbx+78h], rax
0x1800073e6  mov     rcx, rax
0x1800073e9  test    rax, rax
0x1800073ec  jnz     short loc_1800073F8
0x1800073ee  mov     edi, 8007000Eh
0x1800073f3  jmp     loc_1800074CA
0x1800073f8  mov     eax, [rbx+84h]
0x1800073fe  mov     edi, r14d
0x180007401  mov     [rcx], eax
0x180007403  mov     r8, rsi
0x180007406  mov     rax, [rbx+78h]
0x18000740a  mov     ecx, 7FFFFFFEh
0x18000740f  add     rax, 4
0x180007413  mov     dword ptr [rbx+68h], 1
0x18000741a  mov     edx, 1F4h
0x18000741f  test    rcx, rcx
0x180007422  jz      short loc_180007443
0x180007424  movzx   r9d, word ptr [r8]
0x180007428  test    r9w, r9w
0x18000742c  jz      short loc_180007443
0x18000742e  mov     [rax], r9w
0x180007432  add     r8, 2
0x180007436  add     rax, 2
0x18000743a  dec     rcx
0x18000743d  sub     rdx, 1
0x180007441  jnz     short loc_18000741F
0x180007443  test    rdx, rdx
0x180007446  lea     rcx, [rax-2]
0x18000744a  cmovnz  rcx, rax
0x18000744e  mov     [rcx], r14w
0x180007452  mov     dword ptr [rbx+98h], 1
0x18000745c  test    ebp, ebp
0x18000745e  jz      short loc_1800074CA
0x180007460  mov     rcx, rbx; this
0x180007463  call    ?_DestroyIC@CPackage@@IEAAXXZ; CPackage::_DestroyIC(void)
0x180007468  mov     rdx, rsi; unsigned __int16 *
0x18000746b  mov     rcx, rbx; this
0x18000746e  call    ?_IconCreateFromFile@CPackage@@IEAAPEAU_IC@@PEBG@Z; CPackage::_IconCreateFromFile(ushort const *)
0x180007473  mov     rcx, [rbx+0A0h]
0x18000747a  mov     [rbx+60h], rax
0x18000747e  test    rcx, rcx
0x180007481  jz      short loc_1800074A5
0x180007483  mov     r9, [rcx]
0x180007486  lea     r8, [rbx+20h]
0x18000748a  mov     rax, rbx
0x18000748d  neg     rax
0x180007490  mov     rax, [r9+30h]
0x180007494  sbb     rdx, rdx
0x180007497  and     rdx, r8
0x18000749a  xor     r9d, r9d
0x18000749d  xor     r8d, r8d
0x1800074a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074a5  mov     rcx, [rbx+0C8h]
0x1800074ac  test    rcx, rcx
0x1800074af  jz      short loc_1800074CA
0x1800074b1  mov     rdx, [rcx]
0x1800074b4  mov     r8d, [rbx+0D4h]
0x1800074bb  mov     rax, [rdx+20h]
0x1800074bf  mov     edx, [rbx+0D0h]
0x1800074c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074ca  mov     eax, edi
0x1800074cc  add     rsp, 30h
0x1800074d0  pop     r14
0x1800074d2  pop     rdi
0x1800074d3  pop     rsi
0x1800074d4  pop     rbp
0x1800074d5  pop     rbx
0x1800074d6  retn
```
