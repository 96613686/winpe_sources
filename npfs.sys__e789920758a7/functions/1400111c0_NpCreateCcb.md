# NpCreateCcb

- ea: `0x1400111c0`
- end: `0x14001139b`
- name: `NpCreateCcb`
- size: `475`
- prototype: `__int64 __fastcall(__int64, __int64, int, char, char, int, int, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140010ef4`
- `0x14001399c`

## callees

- `0x140002240`
- `0x1400111c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400111e7`
- `ntoskrnl!ExAllocatePool2` at `0x1400111e7`

## pseudocode

```c
__int64 __fastcall NpCreateCcb(__int64 a1, __int64 a2, int a3, char a4, char a5, int a6, int a7, _QWORD *a8)
{
  char *Pool2; // rax
  char *v13; // rbx
  char v14; // al
  _QWORD *v15; // rdx
  __int64 v16; // rdi
  _QWORD *v17; // rcx
  signed __int32 v18; // eax

  Pool2 = (char *)ExAllocatePool2(257, 464, 1665560654);
  v13 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  memset(Pool2, 0, 0x1D0u);
  *(_WORD *)v13 = 516;
  v14 = v13[10];
  *((_QWORD *)v13 + 5) = a1;
  *((_DWORD *)v13 + 1) = 1;
  *((_QWORD *)v13 + 7) = a2;
  v13[8] = a3;
  v13[10] = v14 ^ (v14 ^ a4) & 1 ^ (v14 ^ (v14 ^ a4) & 1 ^ (2 * a5)) & 2;
  *((_DWORD *)v13 + 25) = a6;
  *((_QWORD *)v13 + 11) = 2;
  *((_DWORD *)v13 + 24) = 0;
  *((_QWORD *)v13 + 13) = 0;
  *((_QWORD *)v13 + 10) = v13 + 72;
  *((_QWORD *)v13 + 9) = v13 + 72;
  *((_QWORD *)v13 + 14) = (unsigned __int64)(v13 + 120) | 1;
  *((_DWORD *)v13 + 49) = a7;
  *((_QWORD *)v13 + 23) = 2;
  *((_DWORD *)v13 + 48) = 0;
  *((_QWORD *)v13 + 25) = 0;
  *((_QWORD *)v13 + 22) = v13 + 168;
  *((_QWORD *)v13 + 21) = v13 + 168;
  *((_QWORD *)v13 + 26) = (unsigned __int64)(v13 + 216) | 1;
  v15 = *(_QWORD **)(a1 + 288);
  if ( *v15 != a1 + 280 )
    goto LABEL_9;
  *((_QWORD *)v13 + 3) = a1 + 280;
  *((_QWORD *)v13 + 4) = v15;
  *v15 = v13 + 24;
  *(_QWORD *)(a1 + 288) = v13 + 24;
  ++*(_DWORD *)(a1 + 120);
  ++*(_DWORD *)(a1 + 248);
  if ( a3 == 2 )
  {
    v16 = a1 + 312;
    v17 = *(_QWORD **)(v16 + 8);
    if ( *v17 == v16 )
    {
      *((_QWORD *)v13 + 36) = v16;
      *((_QWORD *)v13 + 37) = v17;
      *v17 = v13 + 288;
      *(_QWORD *)(v16 + 8) = v13 + 288;
      goto LABEL_6;
    }
LABEL_9:
    __fastfail(3u);
  }
  do
  {
LABEL_6:
    v18 = _InterlockedExchangeAdd(&NpCcbIndexGenerator, 1u);
    *((_DWORD *)v13 + 114) = v18 + 1;
  }
  while ( v18 == -1 );
  *((_QWORD *)v13 + 35) = v13 + 272;
  *((_QWORD *)v13 + 34) = v13 + 272;
  *((_QWORD *)v13 + 39) = v13 + 304;
  *((_QWORD *)v13 + 38) = v13 + 304;
  *((_QWORD *)v13 + 41) = v13 + 320;
  *((_QWORD *)v13 + 40) = v13 + 320;
  *((_QWORD *)v13 + 43) = v13 + 336;
  *((_QWORD *)v13 + 42) = v13 + 336;
  *((_OWORD *)v13 + 27) = 0;
  *((_QWORD *)v13 + 56) = 0;
  *a8 = v13;
  return 0;
}

```

## disassembly

```asm
0x1400111c0  push    rbx
0x1400111c2  push    rbp
0x1400111c3  push    rsi
0x1400111c4  push    rdi
0x1400111c5  push    r14
0x1400111c7  sub     rsp, 20h
0x1400111cb  mov     ebp, r8d
0x1400111ce  mov     r14, rdx
0x1400111d1  mov     rdi, rcx
0x1400111d4  mov     edx, 1D0h
0x1400111d9  mov     ecx, 101h
0x1400111de  mov     r8d, 6346704Eh
0x1400111e4  mov     esi, r9d
0x1400111e7  call    cs:__imp_ExAllocatePool2
0x1400111ee  nop     dword ptr [rax+rax+00h]
0x1400111f3  mov     rbx, rax
0x1400111f6  test    rax, rax
0x1400111f9  jz      loc_14001138D
0x1400111ff  xor     edx, edx; Val
0x140011201  mov     r8d, 1D0h; Size
0x140011207  mov     rcx, rax; void *
0x14001120a  call    memset
0x14001120f  mov     word ptr [rbx], 204h
0x140011214  lea     rcx, [rbx+48h]
0x140011218  mov     al, [rbx+0Ah]
0x14001121b  mov     r8d, 1
0x140011221  mov     [rbx+28h], rdi
0x140011225  xor     sil, al
0x140011228  mov     [rbx+4], r8d
0x14001122c  and     sil, r8b
0x14001122f  mov     [rbx+38h], r14
0x140011233  xor     sil, al
0x140011236  mov     al, [rsp+48h+arg_20]
0x14001123a  lea     r9d, [r8+1]
0x14001123e  mov     [rbx+8], bpl
0x140011242  add     al, al
0x140011244  xor     al, sil
0x140011247  and     al, r9b
0x14001124a  xor     al, sil
0x14001124d  mov     [rbx+0Ah], al
0x140011250  mov     eax, [rsp+48h+arg_28]
0x140011254  mov     [rcx+1Ch], eax
0x140011257  lea     rax, [rcx+30h]
0x14001125b  mov     [rcx+10h], r9
0x14001125f  or      rax, r8
0x140011262  mov     dword ptr [rcx+18h], 0
0x140011269  mov     qword ptr [rcx+20h], 0
0x140011271  mov     [rcx+8], rcx
0x140011275  mov     [rcx], rcx
0x140011278  mov     [rcx+28h], rax
0x14001127c  lea     rcx, [rbx+0A8h]
0x140011283  mov     eax, [rsp+48h+arg_30]
0x14001128a  mov     [rcx+1Ch], eax
0x14001128d  lea     rax, [rcx+30h]
0x140011291  mov     [rcx+10h], r9
0x140011295  or      rax, r8
0x140011298  mov     dword ptr [rcx+18h], 0
0x14001129f  mov     qword ptr [rcx+20h], 0
0x1400112a7  mov     [rcx+8], rcx
0x1400112ab  mov     [rcx], rcx
0x1400112ae  mov     [rcx+28h], rax
0x1400112b2  lea     rcx, [rdi+118h]
0x1400112b9  mov     rdx, [rcx+8]
0x1400112bd  cmp     [rdx], rcx
0x1400112c0  jnz     loc_140011394
0x1400112c6  lea     rax, [rbx+18h]
0x1400112ca  mov     [rax], rcx
0x1400112cd  mov     [rax+8], rdx
0x1400112d1  mov     [rdx], rax
0x1400112d4  mov     [rcx+8], rax
0x1400112d8  add     [rdi+78h], r8d
0x1400112dc  add     [rdi+0F8h], r8d
0x1400112e3  cmp     ebp, r9d
0x1400112e6  jnz     short loc_140011311
0x1400112e8  add     rdi, 138h
0x1400112ef  mov     rcx, [rdi+8]
0x1400112f3  cmp     [rcx], rdi
0x1400112f6  jnz     loc_140011394
0x1400112fc  lea     rax, [rbx+120h]
0x140011303  mov     [rax], rdi
0x140011306  mov     [rax+8], rcx
0x14001130a  mov     [rcx], rax
0x14001130d  mov     [rdi+8], rax
0x140011311  mov     eax, r8d
0x140011314  lock xadd cs:NpCcbIndexGenerator, eax
0x14001131c  add     eax, r8d
0x14001131f  mov     [rbx+1C8h], eax
0x140011325  jz      short loc_140011311
0x140011327  lea     rax, [rbx+110h]
0x14001132e  xorps   xmm0, xmm0
0x140011331  mov     [rax+8], rax
0x140011335  mov     [rax], rax
0x140011338  lea     rax, [rbx+130h]
0x14001133f  mov     [rax+8], rax
0x140011343  mov     [rax], rax
0x140011346  lea     rax, [rbx+140h]
0x14001134d  mov     [rax+8], rax
0x140011351  mov     [rax], rax
0x140011354  lea     rax, [rbx+150h]
0x14001135b  mov     [rax+8], rax
0x14001135f  mov     [rax], rax
0x140011362  mov     rax, [rsp+48h+arg_38]
0x14001136a  movups  xmmword ptr [rbx+1B0h], xmm0
0x140011371  mov     qword ptr [rbx+1C0h], 0
0x14001137c  mov     [rax], rbx
0x14001137f  xor     eax, eax
0x140011381  add     rsp, 20h
0x140011385  pop     r14
0x140011387  pop     rdi
0x140011388  pop     rsi
0x140011389  pop     rbp
0x14001138a  pop     rbx
0x14001138b  retn
0x14001138d  mov     eax, 0C000009Ah
0x140011392  jmp     short loc_140011381
0x140011394  mov     ecx, 3
0x140011399  int     29h; Win8: RtlFailFast(ecx)
```
