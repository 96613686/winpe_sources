# ORDeleteKey

- ea: `0x140024310`
- end: `0x1400244e0`
- name: `ORDeleteKey`
- size: `464`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140021aac`

## callees

- `0x140024310`
- `0x140024888`
- `0x140026fa8`
- `0x140027044`
- `0x14002cd04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140024364`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140024364`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400244b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400244b3`

## pseudocode

```c
__int64 __fastcall ORDeleteKey(__int64 a1, __int64 a2)
{
  __int64 v4; // rsi
  unsigned int v5; // ebx
  __int64 *v6; // rbx
  __int64 v7; // rax
  _QWORD *v8; // rbp
  __int64 v9; // rax
  __int64 *v10; // rcx
  __int64 v11; // rax
  __int64 **v12; // r8
  __int64 v13; // rax
  __int64 **v14; // rcx
  _OWORD v16[3]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v17; // [rsp+60h] [rbp+8h] BYREF

  v17 = 0;
  v16[0] = 0;
  if ( *(_WORD *)(a1 + 28) != 29806 )
    return 6;
  v4 = *(_QWORD *)(a1 + 16);
  if ( *(_DWORD *)v4 != -1092567328 )
    return 6;
  EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 136));
  if ( *(_WORD *)(a1 + 30) )
    goto LABEL_23;
  if ( a2 )
  {
    v5 = ORInitUnicodeStringEx(v16, a2);
    if ( v5 )
      goto LABEL_24;
  }
  v5 = ORParseSubKey(v16, a1, 0, &v17);
  if ( v5 )
    goto LABEL_24;
  v6 = (__int64 *)v17;
  if ( *(_QWORD *)(v4 + 56) != v17 )
  {
    v7 = *(_QWORD *)(v17 + 80);
    if ( (*(_BYTE *)(v17 + 88) & 1) != 0 )
    {
      if ( !v7 )
      {
LABEL_14:
        *(_WORD *)(v17 + 30) = 1;
        ++v6[21];
        v8 = (_QWORD *)v6[9];
        --*(_DWORD *)(v8[5] + 20LL);
        v9 = v8[5];
        if ( !*(_DWORD *)(v9 + 20) )
          *(_DWORD *)(v9 + 28) = -1;
        RtlRbRemoveNode(v8 + 10, v6 + 6);
        ++v8[21];
        --*(_DWORD *)(*(_QWORD *)(v6[12] + 16) + 12LL);
        v10 = (__int64 *)v6[12];
        if ( !*(_DWORD *)(v10[2] + 12) )
        {
          v11 = *v10;
          v17 = v6[12];
          if ( *(__int64 **)(v11 + 8) != v10 || (v12 = (__int64 **)v10[1], *v12 != v10) )
LABEL_21:
            __fastfail(3u);
          *v12 = (__int64 *)v11;
          *(_QWORD *)(v11 + 8) = v12;
          ORFreeOrNop(*(_QWORD *)(a1 + 16), v10 + 2);
          ORFreeOrNop(*(_QWORD *)(a1 + 16), &v17);
        }
        v13 = v6[2] + 96;
        v14 = *(__int64 ***)(v6[2] + 104);
        if ( *v14 != (__int64 *)v13 )
          goto LABEL_21;
        *v6 = v13;
        v6[1] = (__int64)v14;
        *v14 = v6;
        *(_QWORD *)(v13 + 8) = v6;
        *(_DWORD *)(v4 + 180) = 1;
LABEL_23:
        v5 = 0;
        goto LABEL_24;
      }
      v7 ^= v17 + 80;
    }
    if ( v7 )
    {
      v5 = 1020;
      goto LABEL_24;
    }
    goto LABEL_14;
  }
  v5 = 87;
LABEL_24:
  LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 136));
  return v5;
}

```

## disassembly

```asm
0x140024310  mov     rax, rsp
0x140024313  mov     [rax+10h], rbx
0x140024317  mov     [rax+18h], rbp
0x14002431b  push    rsi
0x14002431c  push    rdi
0x14002431d  push    r12
0x14002431f  push    r14
0x140024321  push    r15
0x140024323  sub     rsp, 30h
0x140024327  xor     r15d, r15d
0x14002432a  xorps   xmm0, xmm0
0x14002432d  mov     [rax+8], r15
0x140024331  mov     rbx, rdx
0x140024334  movups  xmmword ptr [rax-38h], xmm0
0x140024338  mov     eax, 746Eh
0x14002433d  mov     rdi, rcx
0x140024340  cmp     [rcx+1Ch], ax
0x140024344  jnz     loc_1400244C1
0x14002434a  mov     rsi, [rcx+10h]
0x14002434e  cmp     dword ptr [rsi], 0BEE0BEE0h
0x140024354  jnz     loc_1400244C1
0x14002435a  lea     r14, [rsi+88h]
0x140024361  mov     rcx, r14; lpCriticalSection
0x140024364  call    cs:__imp_EnterCriticalSection
0x14002436b  nop     dword ptr [rax+rax+00h]
0x140024370  cmp     [rdi+1Eh], r15w
0x140024375  jnz     loc_1400244AD
0x14002437b  test    rbx, rbx
0x14002437e  jz      short loc_140024397
0x140024380  mov     rdx, rbx
0x140024383  lea     rcx, [rsp+58h+var_38]
0x140024388  call    ORInitUnicodeStringEx
0x14002438d  mov     ebx, eax
0x14002438f  test    eax, eax
0x140024391  jnz     loc_1400244B0
0x140024397  lea     r9, [rsp+58h+arg_0]
0x14002439c  xor     r8d, r8d
0x14002439f  mov     rdx, rdi
0x1400243a2  lea     rcx, [rsp+58h+var_38]
0x1400243a7  call    ORParseSubKey
0x1400243ac  mov     ebx, eax
0x1400243ae  test    eax, eax
0x1400243b0  jnz     loc_1400244B0
0x1400243b6  mov     rbx, [rsp+58h+arg_0]
0x1400243bb  cmp     [rsi+38h], rbx
0x1400243bf  jnz     short loc_1400243C9
0x1400243c1  lea     ebx, [rax+57h]
0x1400243c4  jmp     loc_1400244B0
0x1400243c9  lea     rcx, [rbx+50h]
0x1400243cd  mov     r12d, 1
0x1400243d3  mov     rax, [rcx]
0x1400243d6  test    [rcx+8], r12b
0x1400243da  jz      short loc_1400243E4
0x1400243dc  test    rax, rax
0x1400243df  jz      short loc_1400243F3
0x1400243e1  xor     rax, rcx
0x1400243e4  test    rax, rax
0x1400243e7  jz      short loc_1400243F3
0x1400243e9  mov     ebx, 3FCh
0x1400243ee  jmp     loc_1400244B0
0x1400243f3  mov     [rbx+1Eh], r12w
0x1400243f8  add     [rbx+0A8h], r12
0x1400243ff  mov     rbp, [rbx+48h]
0x140024403  mov     rax, [rbp+28h]
0x140024407  dec     dword ptr [rax+14h]
0x14002440a  mov     rax, [rbp+28h]
0x14002440e  cmp     [rax+14h], r15d
0x140024412  jnz     short loc_14002441B
0x140024414  mov     dword ptr [rax+1Ch], 0FFFFFFFFh
0x14002441b  lea     rdx, [rbx+30h]
0x14002441f  lea     rcx, [rbp+50h]
0x140024423  call    RtlRbRemoveNode
0x140024428  add     [rbp+0A8h], r12
0x14002442f  mov     rax, [rbx+60h]
0x140024433  mov     rcx, [rax+10h]
0x140024437  dec     dword ptr [rcx+0Ch]
0x14002443a  mov     rcx, [rbx+60h]
0x14002443e  lea     rdx, [rcx+10h]
0x140024442  mov     rax, [rdx]
0x140024445  cmp     [rax+0Ch], r15d
0x140024449  jnz     short loc_140024480
0x14002444b  mov     rax, [rcx]
0x14002444e  mov     [rsp+58h+arg_0], rcx
0x140024453  cmp     [rax+8], rcx
0x140024457  jnz     short loc_140024491
0x140024459  mov     r8, [rcx+8]
0x14002445d  cmp     [r8], rcx
0x140024460  jnz     short loc_140024491
0x140024462  mov     [r8], rax
0x140024465  mov     [rax+8], r8
0x140024469  mov     rcx, [rdi+10h]
0x14002446d  call    ORFreeOrNop
0x140024472  mov     rcx, [rdi+10h]
0x140024476  lea     rdx, [rsp+58h+arg_0]
0x14002447b  call    ORFreeOrNop
0x140024480  mov     rax, [rbx+10h]
0x140024484  add     rax, 60h ; '`'
0x140024488  mov     rcx, [rax+8]
0x14002448c  cmp     [rcx], rax
0x14002448f  jz      short loc_140024498
0x140024491  mov     ecx, 3
0x140024496  int     29h; Win8: RtlFailFast(ecx)
0x140024498  mov     [rbx], rax
0x14002449b  mov     [rbx+8], rcx
0x14002449f  mov     [rcx], rbx
0x1400244a2  mov     [rax+8], rbx
0x1400244a6  mov     [rsi+0B4h], r12d
0x1400244ad  mov     ebx, r15d
0x1400244b0  mov     rcx, r14; lpCriticalSection
0x1400244b3  call    cs:__imp_LeaveCriticalSection
0x1400244ba  nop     dword ptr [rax+rax+00h]
0x1400244bf  jmp     short loc_1400244C6
0x1400244c1  mov     ebx, 6
0x1400244c6  mov     rbp, [rsp+58h+arg_10]
0x1400244cb  mov     eax, ebx
0x1400244cd  mov     rbx, [rsp+58h+arg_8]
0x1400244d2  add     rsp, 30h
0x1400244d6  pop     r15
0x1400244d8  pop     r14
0x1400244da  pop     r12
0x1400244dc  pop     rdi
0x1400244dd  pop     rsi
0x1400244de  retn
```
