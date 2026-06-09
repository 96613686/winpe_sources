# CLangTagStack::Pop(HtmlTokenType)

- ea: `0x180006914`
- end: `0x180006a08`
- name: `?Pop@CLangTagStack@@QEAAHW4HtmlTokenType@@@Z`
- size: `244`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180006a10`
- `0x180008690`

## callees

- `0x180006914`
- `0x180014544`

## pseudocode

```c
__int64 __fastcall CLangTagStack::Pop(__int64 a1, int a2)
{
  int v3; // ecx
  __int64 v5; // r9
  __int64 v6; // rax
  __int64 v7; // rcx
  _DWORD *v8; // rsi
  unsigned int v9; // esi
  unsigned int v10; // edi
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v15; // r9
  _DWORD *v16; // rdx

  v3 = *(_DWORD *)(a1 + 16);
  if ( !v3 )
    return 0;
  v5 = *(_QWORD *)(a1 + 8);
  v6 = (unsigned int)(v3 - 1);
  v7 = v6;
  v8 = *(_DWORD **)(v5 + 8 * v6);
  if ( a2 == *v8 )
  {
    v9 = v8[2];
    *(_DWORD *)(a1 + 16) = v6;
    operator delete(*(void **)(v5 + 8 * v6));
    v10 = *(_DWORD *)(a1 + 16);
  }
  else
  {
    v10 = 0;
    v9 = 0;
    while ( (int)v7 >= 0 )
    {
      v16 = *(_DWORD **)(v5 + 8 * v7);
      if ( a2 == *v16 && !v16[1] )
      {
        v9 = v16[2];
        v10 = v7;
        v16[1] = 1;
        break;
      }
      v7 = (unsigned int)(v7 - 1);
    }
  }
  while ( 1 )
  {
    LODWORD(v11) = *(_DWORD *)(a1 + 16);
    if ( !(_DWORD)v11 )
      break;
    v12 = *(_QWORD *)(a1 + 8);
    v13 = (unsigned int)(v11 - 1);
    if ( !*(_DWORD *)(*(_QWORD *)(v12 + 8 * v13) + 4LL) )
      break;
    *(_DWORD *)(a1 + 16) = v13;
    operator delete(*(void **)(v12 + 8LL * (unsigned int)(v11 - 1)));
  }
  if ( *(_DWORD *)a1 != v10 )
    return 0;
  if ( v10 <= (unsigned int)v11 )
    LODWORD(v11) = v10;
  while ( (_DWORD)v11 )
  {
    v11 = (unsigned int)(v11 - 1);
    v15 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v11);
    if ( *(_DWORD *)(v15 + 8) && !*(_DWORD *)(v15 + 4) )
    {
      *(_DWORD *)a1 = v11;
      return v9;
    }
  }
  *(_DWORD *)a1 = -1;
  return v9;
}

```

## disassembly

```asm
0x180006914  mov     [rsp+arg_0], rbx
0x180006919  mov     [rsp+arg_8], rsi
0x18000691e  push    rdi
0x18000691f  sub     rsp, 20h
0x180006923  mov     rbx, rcx
0x180006926  mov     r10d, 1
0x18000692c  mov     ecx, [rcx+10h]
0x18000692f  mov     r8d, edx
0x180006932  cmp     ecx, r10d
0x180006935  jb      short loc_180006983
0x180006937  mov     r9, [rbx+8]
0x18000693b  mov     eax, ecx
0x18000693d  sub     eax, r10d
0x180006940  dec     ecx
0x180006942  mov     rsi, [r9+rax*8]
0x180006946  cmp     edx, [rsi]
0x180006948  jnz     short loc_1800069C9
0x18000694a  mov     esi, [rsi+8]
0x18000694d  lea     edx, [r10+0Fh]
0x180006951  mov     [rbx+10h], ecx
0x180006954  mov     rcx, [r9+rcx*8]; Block
0x180006958  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000695d  mov     edi, [rbx+10h]
0x180006960  mov     r8d, [rbx+10h]
0x180006964  test    r8d, r8d
0x180006967  jz      short loc_18000697F
0x180006969  mov     rax, [rbx+8]
0x18000696d  mov     edx, r8d
0x180006970  dec     edx
0x180006972  mov     r9d, edx
0x180006975  mov     rcx, [rax+rdx*8]
0x180006979  cmp     dword ptr [rcx+4], 0
0x18000697d  jnz     short loc_1800069F2
0x18000697f  cmp     [rbx], edi
0x180006981  jz      short loc_180006995
0x180006983  xor     eax, eax
0x180006985  mov     rbx, [rsp+28h+arg_0]
0x18000698a  mov     rsi, [rsp+28h+arg_8]
0x18000698f  add     rsp, 20h
0x180006993  pop     rdi
0x180006994  retn
0x180006995  cmp     edi, r8d
0x180006998  cmovbe  r8d, edi
0x18000699c  test    r8d, r8d
0x18000699f  jz      short loc_1800069C1
0x1800069a1  mov     rcx, [rbx+8]
0x1800069a5  dec     r8d
0x1800069a8  mov     r9, [rcx+r8*8]
0x1800069ac  cmp     dword ptr [r9+8], 0
0x1800069b1  jz      short loc_18000699C
0x1800069b3  cmp     dword ptr [r9+4], 0
0x1800069b8  jnz     short loc_18000699C
0x1800069ba  mov     [rbx], r8d
0x1800069bd  mov     eax, esi
0x1800069bf  jmp     short loc_180006985
0x1800069c1  mov     dword ptr [rbx], 0FFFFFFFFh
0x1800069c7  jmp     short loc_1800069BD
0x1800069c9  xor     edi, edi
0x1800069cb  xor     esi, esi
0x1800069cd  test    ecx, ecx
0x1800069cf  js      short loc_180006960
0x1800069d1  mov     rdx, [r9+rcx*8]
0x1800069d5  cmp     r8d, [rdx]
0x1800069d8  jz      short loc_1800069DF
0x1800069da  sub     ecx, r10d
0x1800069dd  jmp     short loc_1800069CD
0x1800069df  cmp     [rdx+4], esi
0x1800069e2  jnz     short loc_1800069DA
0x1800069e4  mov     esi, [rdx+8]
0x1800069e7  mov     edi, ecx
0x1800069e9  mov     [rdx+4], r10d
0x1800069ed  jmp     loc_180006960
0x1800069f2  mov     [rbx+10h], edx
0x1800069f5  mov     edx, 10h
0x1800069fa  mov     rcx, [rax+r9*8]; Block
0x1800069fe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006a03  jmp     loc_180006960
```
