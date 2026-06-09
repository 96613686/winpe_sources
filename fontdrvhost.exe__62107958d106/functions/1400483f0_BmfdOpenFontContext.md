# BmfdOpenFontContext

- ea: `0x1400483f0`
- end: `0x14004868d`
- name: `BmfdOpenFontContext`
- size: `669`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140047aa8`
- `0x14004802c`

## callees

- `0x140048348`
- `0x1400483f0`
- `0x140048a18`
- `0x14005aad8`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x14004859b`
- `KERNEL32!GlobalFree` at `0x14004859b`
- `KERNEL32!GlobalAlloc` at `0x1400484fd`
- `KERNEL32!GlobalAlloc` at `0x1400484fd`
- `KERNEL32!LeaveCriticalSection` at `0x140048592`
- `KERNEL32!LeaveCriticalSection` at `0x1400485d7`
- `KERNEL32!LeaveCriticalSection` at `0x140048592`
- `KERNEL32!LeaveCriticalSection` at `0x1400485d7`
- `KERNEL32!EnterCriticalSection` at `0x140048562`
- `KERNEL32!EnterCriticalSection` at `0x140048562`
- `KERNEL32!SetLastError` at `0x14004850e`
- `KERNEL32!SetLastError` at `0x14004850e`

## pseudocode

```c
void *__fastcall BmfdOpenFontContext(__int64 a1)
{
  __int64 v1; // rdi
  int v2; // r14d
  unsigned int v4; // eax
  __int64 v5; // rbx
  bool v6; // zf
  unsigned int v7; // esi
  int Rotate; // eax
  int v9; // edx
  int v10; // r12d
  int v11; // r13d
  __int64 v12; // rbx
  int v13; // r13d
  int v14; // edx
  int v15; // r8d
  int v16; // eax
  int v17; // ecx
  unsigned int v18; // r10d
  unsigned int v19; // r15d
  char *v20; // rax
  void *v21; // rsi
  struct _RTL_CRITICAL_SECTION *v23; // rcx
  int i; // edx
  __int64 v25; // rax
  unsigned int v26; // ecx
  ULONG pcjBuf; // [rsp+80h] [rbp+8h] BYREF
  __int64 v28; // [rsp+88h] [rbp+10h] BYREF
  PULONG ppjBuf; // [rsp+90h] [rbp+18h] BYREF
  __int64 v30; // [rsp+98h] [rbp+20h]

  v1 = *(_QWORD *)(a1 + 24);
  v2 = 0;
  v28 = 0;
  ppjBuf = 0;
  pcjBuf = 0;
  if ( !v1 )
    return 0;
  v4 = *(_DWORD *)(a1 + 4);
  if ( !v4 )
    return 0;
  if ( v4 > *(_DWORD *)(v1 + 28) )
    return 0;
  v5 = v1 + 88LL * (v4 - 1) + 40;
  v6 = (*(_DWORD *)(a1 + 12) & 0x2000) == 0;
  v30 = v5;
  if ( !v6 && (*(_BYTE *)(*(_QWORD *)(v5 + 80) + 52LL) & 0x20) != 0 )
    return 0;
  if ( (*(_DWORD *)(a1 + 12) & 0x4000) != 0 && (*(_BYTE *)(*(_QWORD *)(v5 + 80) + 52LL) & 1) != 0 )
    return 0;
  v7 = 56;
  Rotate = ulGetRotate(&v28, -1);
  v9 = *(unsigned __int16 *)(v5 + 46);
  v10 = Rotate;
  v11 = *(unsigned __int16 *)(v5 + 44);
  v12 = v28;
  v13 = HIDWORD(v28) * v11;
  v14 = v28 * v9;
  if ( v14 )
  {
    v15 = v13;
    v16 = *(_DWORD *)(a1 + 12) & 0x6000;
    if ( v16 )
    {
      if ( v16 == 0x2000 )
      {
        v17 = v14 + 1;
      }
      else
      {
        v26 = v13 + 1;
        if ( v16 == 0x4000 )
          v26 = v13 - 1;
        v17 = v14 + (v26 >> 1);
      }
    }
    else
    {
      v17 = v14;
    }
  }
  else
  {
    v17 = 1;
    v15 = 1;
  }
  v18 = (unsigned int)(v17 + 7) >> 3;
  if ( !v10 || v10 == 1800 )
  {
    v13 = v17;
    v19 = ((v15 * v18 + 3) & 0xFFFFFFFC) + 16;
  }
  else
  {
    v19 = cjGlyphDataSimulated(a1, v14, v13, 0, v10);
  }
  if ( (_DWORD)v12 != 1 || HIDWORD(v28) != 1 )
  {
    if ( v18 + 5 > 0x100 )
    {
      v7 = v18 + 61;
      v2 = 3;
    }
    else
    {
      v2 = 1;
    }
  }
  v20 = (char *)GlobalAlloc(0, v7);
  v21 = v20;
  if ( !v20 )
  {
    SetLastError(8u);
    return 0;
  }
  v23 = ghsemBMFD;
  *(_DWORD *)v20 = 252;
  *((_QWORD *)v20 + 1) = *(_QWORD *)(a1 + 24);
  *((_QWORD *)v20 + 3) = v30;
  *((_DWORD *)v20 + 8) = *(_DWORD *)(a1 + 12);
  *(_QWORD *)(v20 + 36) = v12;
  *((_DWORD *)v20 + 13) = v2;
  *((_DWORD *)v20 + 11) = v13;
  *((_DWORD *)v20 + 12) = v19;
  *((_DWORD *)v20 + 4) = v10;
  EnterCriticalSection(v23);
  if ( !*(_DWORD *)(v1 + 24) )
  {
    if ( !EngMapFontFileFD(*(_QWORD *)(v1 + 16), &ppjBuf, &pcjBuf) )
    {
      LeaveCriticalSection(ghsemBMFD);
      GlobalFree(v21);
      return 0;
    }
    for ( i = 0; i < *(_DWORD *)(v1 + 28); *(_QWORD *)(88 * v25 + v1 + 40) = (char *)ppjBuf
                                                                           + *(int *)(88 * v25 + v1 + 48) )
      v25 = i++;
  }
  ++*(_DWORD *)(v1 + 24);
  LeaveCriticalSection(ghsemBMFD);
  return v21;
}

```

## disassembly

```asm
0x1400483f0  mov     rax, rsp
0x1400483f3  push    rbx
0x1400483f4  push    rbp
0x1400483f5  push    rsi
0x1400483f6  push    rdi
0x1400483f7  push    r12
0x1400483f9  push    r13
0x1400483fb  push    r14
0x1400483fd  push    r15
0x1400483ff  sub     rsp, 38h
0x140048403  mov     rdi, [rcx+18h]
0x140048407  xor     r14d, r14d
0x14004840a  mov     [rax+10h], r14
0x14004840e  mov     rbp, rcx
0x140048411  mov     [rax+18h], r14
0x140048415  mov     [rax+8], r14d
0x140048419  test    rdi, rdi
0x14004841c  jz      loc_140048514
0x140048422  mov     eax, [rcx+4]
0x140048425  lea     r15d, [r14+1]
0x140048429  cmp     eax, r15d
0x14004842c  jb      loc_140048514
0x140048432  cmp     eax, [rdi+1Ch]
0x140048435  ja      loc_140048514
0x14004843b  lea     ecx, [rax-1]
0x14004843e  imul    rbx, rcx, 58h ; 'X'
0x140048442  add     rbx, 28h ; '('
0x140048446  add     rbx, rdi
0x140048449  test    dword ptr [rbp+0Ch], 2000h
0x140048450  mov     [rsp+78h+arg_18], rbx
0x140048458  jnz     loc_14004860A
0x14004845e  test    dword ptr [rbp+0Ch], 4000h
0x140048465  jnz     loc_14004861D
0x14004846b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14004846f  lea     rcx, [rsp+78h+arg_8]
0x140048477  mov     esi, 38h ; '8'
0x14004847c  call    ulGetRotate
0x140048481  movzx   edx, word ptr [rbx+2Eh]
0x140048485  mov     r12d, eax
0x140048488  movzx   r13d, word ptr [rbx+2Ch]
0x14004848d  mov     rbx, [rsp+78h+arg_8]
0x140048495  imul    r13d, dword ptr [rsp+78h+arg_8+4]
0x14004849e  imul    edx, ebx
0x1400484a1  test    edx, edx
0x1400484a3  jz      loc_1400485FF
0x1400484a9  mov     eax, [rbp+0Ch]
0x1400484ac  mov     r8d, r13d
0x1400484af  and     eax, 6000h
0x1400484b4  jnz     loc_140048630
0x1400484ba  mov     ecx, edx
0x1400484bc  lea     r10d, [rcx+7]
0x1400484c0  shr     r10d, 3
0x1400484c4  test    r12d, r12d
0x1400484c7  jnz     loc_140048657
0x1400484cd  mov     r15d, r10d
0x1400484d0  mov     r13d, ecx
0x1400484d3  imul    r15d, r8d
0x1400484d7  add     r15d, 3
0x1400484db  and     r15d, 0FFFFFFFCh
0x1400484df  add     r15d, 10h
0x1400484e3  cmp     ebx, 1
0x1400484e6  jnz     loc_1400485E5
0x1400484ec  cmp     dword ptr [rsp+78h+arg_8+4], ebx
0x1400484f3  jnz     loc_1400485E5
0x1400484f9  mov     edx, esi; dwBytes
0x1400484fb  xor     ecx, ecx; uFlags
0x1400484fd  call    cs:__imp_GlobalAlloc
0x140048503  mov     rsi, rax
0x140048506  test    rax, rax
0x140048509  jnz     short loc_140048527
0x14004850b  lea     ecx, [rax+8]; dwErrCode
0x14004850e  call    cs:__imp_SetLastError
0x140048514  xor     eax, eax
0x140048516  add     rsp, 38h
0x14004851a  pop     r15
0x14004851c  pop     r14
0x14004851e  pop     r13
0x140048520  pop     r12
0x140048522  pop     rdi
0x140048523  pop     rsi
0x140048524  pop     rbp
0x140048525  pop     rbx
0x140048526  retn
0x140048527  mov     rcx, cs:ghsemBMFD; lpCriticalSection
0x14004852e  mov     dword ptr [rax], 0FCh
0x140048534  mov     rax, [rbp+18h]
0x140048538  mov     [rsi+8], rax
0x14004853c  mov     rax, [rsp+78h+arg_18]
0x140048544  mov     [rsi+18h], rax
0x140048548  mov     eax, [rbp+0Ch]
0x14004854b  mov     [rsi+20h], eax
0x14004854e  mov     [rsi+24h], rbx
0x140048552  mov     [rsi+34h], r14d
0x140048556  mov     [rsi+2Ch], r13d
0x14004855a  mov     [rsi+30h], r15d
0x14004855e  mov     [rsi+10h], r12d
0x140048562  call    cs:__imp_EnterCriticalSection
0x140048568  cmp     dword ptr [rdi+18h], 0
0x14004856c  jnz     short loc_1400485CD
0x14004856e  mov     rcx, [rdi+10h]; iFile
0x140048572  lea     r8, [rsp+78h+pcjBuf]; pcjBuf
0x14004857a  lea     rdx, [rsp+78h+ppjBuf]; ppjBuf
0x140048582  call    EngMapFontFileFD
0x140048587  test    eax, eax
0x140048589  jnz     short loc_1400485A6
0x14004858b  mov     rcx, cs:ghsemBMFD; lpCriticalSection
0x140048592  call    cs:__imp_LeaveCriticalSection
0x140048598  mov     rcx, rsi; hMem
0x14004859b  call    cs:__imp_GlobalFree
0x1400485a1  jmp     loc_140048514
0x1400485a6  xor     edx, edx
0x1400485a8  cmp     [rdi+1Ch], edx
0x1400485ab  jle     short loc_1400485CD
0x1400485ad  movsxd  rax, edx
0x1400485b0  inc     edx
0x1400485b2  imul    rcx, rax, 58h ; 'X'
0x1400485b6  movsxd  rax, dword ptr [rcx+rdi+30h]
0x1400485bb  add     rax, [rsp+78h+ppjBuf]
0x1400485c3  mov     [rcx+rdi+28h], rax
0x1400485c8  cmp     edx, [rdi+1Ch]
0x1400485cb  jl      short loc_1400485AD
0x1400485cd  inc     dword ptr [rdi+18h]
0x1400485d0  mov     rcx, cs:ghsemBMFD; lpCriticalSection
0x1400485d7  call    cs:__imp_LeaveCriticalSection
0x1400485dd  mov     rax, rsi
0x1400485e0  jmp     loc_140048516
0x1400485e5  lea     eax, [r10+5]
0x1400485e9  cmp     eax, 100h
0x1400485ee  ja      loc_14004867F
0x1400485f4  mov     r14d, 1
0x1400485fa  jmp     loc_1400484F9
0x1400485ff  mov     ecx, r15d
0x140048602  mov     r8d, r15d
0x140048605  jmp     loc_1400484BC
0x14004860a  mov     rax, [rbx+50h]
0x14004860e  test    byte ptr [rax+34h], 20h
0x140048612  jnz     loc_140048514
0x140048618  jmp     loc_14004845E
0x14004861d  mov     rax, [rbx+50h]
0x140048621  test    [rax+34h], r15b
0x140048625  jnz     loc_140048514
0x14004862b  jmp     loc_14004846B
0x140048630  cmp     eax, 2000h
0x140048635  jz      short loc_14004864F
0x140048637  lea     ecx, [r13+1]
0x14004863b  cmp     eax, 4000h
0x140048640  jnz     short loc_140048646
0x140048642  lea     ecx, [r13-1]
0x140048646  shr     ecx, 1
0x140048648  add     ecx, edx
0x14004864a  jmp     loc_1400484BC
0x14004864f  lea     ecx, [rdx+1]
0x140048652  jmp     loc_1400484BC
0x140048657  cmp     r12d, 708h
0x14004865e  jz      loc_1400484CD
0x140048664  xor     r9d, r9d
0x140048667  mov     [rsp+78h+var_58], r12d
0x14004866c  mov     r8d, r13d
0x14004866f  mov     rcx, rbp
0x140048672  call    cjGlyphDataSimulated
0x140048677  mov     r15d, eax
0x14004867a  jmp     loc_1400484E3
0x14004867f  lea     esi, [rax+38h]
0x140048682  mov     r14d, 3
0x140048688  jmp     loc_1400484F9
```
