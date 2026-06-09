# GenAddShadowStack(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_CONTEXT *,ulong)

- ea: `0x180017314`
- end: `0x180017663`
- name: `?GenAddShadowStack@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_CONTEXT@@K@Z`
- size: `847`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _INTERNAL_PROCESS *, struct _CONTEXT *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001ad48`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x180017314`
- `0x18001f834`
- `0x18002c010`

## string_xrefs

- `0x180017617`: `Unable to add shadow stack memory region: ReadVirtual of KUSER_SHARED_DATA->XState failed 0x%08x`

## pseudocode

```c
__int64 __fastcall GenAddShadowStack(
        struct _MINIDUMP_STATE *a1,
        struct _INTERNAL_PROCESS *a2,
        unsigned __int64 a3,
        unsigned int a4)
{
  __int64 v5; // rsi
  DWORD v8; // edx
  struct _CONTEXT *v9; // rdx
  DWORD v10; // eax
  __int64 P3Home_low; // r8
  int v12; // r9d
  char *v13; // rdi
  int v14; // eax
  unsigned int v15; // esi
  __int64 v16; // r8
  unsigned int v17; // edx
  unsigned int i; // ecx
  __int64 v19; // rdx
  __int64 v20; // rsi
  int v21; // eax
  unsigned int v22; // r14d
  unsigned __int64 v24; // rcx
  int v25; // eax
  unsigned int v26; // edi
  __int64 v27; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v28; // [rsp+28h] [rbp-D8h]
  int v29; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v30; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v31; // [rsp+58h] [rbp-A8h]
  __int128 v32; // [rsp+68h] [rbp-98h]
  _BYTE v33[544]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v34; // [rsp+2A0h] [rbp+1A0h]
  _DWORD v35[77]; // [rsp+2ACh] [rbp+1ACh]

  v5 = a4;
  memset_0(v33, 0, 0x358u);
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  if ( !a3 )
    return 0;
  v8 = *(_DWORD *)(a3 + 48);
  if ( (v8 & 0x10000) != 0 )
  {
    if ( (v8 & 0x10040) != 0x10040 || (unsigned int)v5 < 0x2EC )
      return 0;
    v9 = (struct _CONTEXT *)(a3 + 716);
  }
  else
  {
    v10 = *(_DWORD *)(a3 + 48);
    if ( (v8 & 0x100000) != 0 )
    {
      if ( (v10 & 0x100080) != 1048704 && (v8 & 0x100040) != 1048640 || (unsigned int)v5 < 0x4F0 )
        return 0;
      v9 = (struct _CONTEXT *)(a3 + 1232);
    }
    else
    {
      if ( (v10 & 0x400020) != 4194336 || (v8 & 0x400000) == 0 || (unsigned int)v5 < 0x3B0 )
        return 0;
      v9 = (struct _CONTEXT *)(a3 + 912);
    }
  }
  if ( !v9 )
    return 0;
  P3Home_low = SLODWORD(v9->P3Home);
  if ( SLODWORD(v9->P1Home) > (int)P3Home_low )
    return 0;
  v12 = P3Home_low + HIDWORD(v9->P3Home);
  if ( v12 > HIDWORD(v9->P1Home) + LODWORD(v9->P1Home) )
    return 0;
  if ( (int)P3Home_low > v12 )
    return 0;
  v13 = (char *)v9 + P3Home_low;
  if ( (unsigned __int64)v9 + P3Home_low < a3 || a3 > ~v5 || (unsigned __int64)v13 >= v5 + a3 || !v13 )
    return 0;
  v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _BYTE *, int, int *))(**((_QWORD **)a1 + 2) + 232LL))(
          *((_QWORD *)a1 + 2),
          *((_QWORD *)a2 + 8),
          *((_QWORD *)a1 + 26),
          v33,
          856,
          &v29);
  v15 = v14;
  if ( v14 >= 0 && v29 == 856 )
  {
    if ( (v33[20] & 2) != 0 )
    {
      v16 = *((_QWORD *)v13 + 1);
      if ( (v16 & 0x800) != 0 )
      {
        v17 = 576;
        for ( i = 2; i < 0xB; ++i )
        {
          if ( ((1LL << i) & v16) != 0 )
          {
            if ( ((1LL << i) & v34) != 0 )
              v17 = (v17 + 63) & 0xFFFFFFC0;
            v17 += v35[i];
          }
        }
        if ( (v34 & 0x800) != 0 )
          v17 = (v17 + 63) & 0xFFFFFFC0;
        v19 = v17 - 512;
        if ( (_DWORD)v19 != -1 )
        {
          v20 = (unsigned int)v19;
          if ( (v13[v19] & 1) != 0 )
          {
            v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int128 *))(**((_QWORD **)a1 + 2) + 248LL))(
                    *((_QWORD *)a1 + 2),
                    *((_QWORD *)a2 + 8),
                    *(_QWORD *)&v13[v19 + 8],
                    &v30);
            v22 = v21;
            if ( v21 < 0 )
            {
              (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
                *((_QWORD *)a1 + 5),
                2,
                "Unable to add shadow stack memory region: QueryVirtual failed 0x%08x",
                (unsigned int)v21);
              return v22;
            }
            v24 = *(_QWORD *)&v13[v20 + 8];
            if ( v24 < (unsigned __int64)v30 || v24 > *((_QWORD *)&v31 + 1) + (_QWORD)v30 )
            {
              (*(void (__fastcall **)(_QWORD, __int64, const char *))(**((_QWORD **)a1 + 5) + 8LL))(
                *((_QWORD *)a1 + 5),
                2,
                "Unable to add shadow stack memory region: Memory range not found");
              return 2147500037LL;
            }
            v28 = *((_QWORD *)&v31 + 1) + v30 - v24;
            v27 = *(_QWORD *)&v13[v20 + 8];
            v25 = GenAddMemoryRange(a1, a2, 2);
            v26 = v25;
            if ( v25 < 0 )
            {
              (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
                *((_QWORD *)a1 + 5),
                2,
                "Unable to add shadow stack memory region: GenAddMemoryRange failed 0x%08x",
                (unsigned int)v25,
                v27,
                v28);
              return v26;
            }
          }
        }
      }
    }
    return 0;
  }
  (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
    *((_QWORD *)a1 + 5),
    2,
    "Unable to add shadow stack memory region: ReadVirtual of KUSER_SHARED_DATA->XState failed 0x%08x",
    (unsigned int)v14);
  if ( !v15 )
    return (unsigned int)-2147467259;
  return v15;
}

```

## disassembly

```asm
0x180017314  push    rbp
0x180017316  push    rbx
0x180017317  push    rsi
0x180017318  push    rdi
0x180017319  push    r13
0x18001731b  push    r14
0x18001731d  push    r15
0x18001731f  lea     rbp, [rsp-2F0h]
0x180017327  sub     rsp, 3F0h
0x18001732e  mov     rax, cs:__security_cookie
0x180017335  xor     rax, rsp
0x180017338  mov     [rbp+320h+var_40], rax
0x18001733f  mov     rbx, r8
0x180017342  mov     esi, r9d
0x180017345  mov     r13, rdx
0x180017348  mov     r15, rcx
0x18001734b  mov     r14d, 358h
0x180017351  lea     rcx, [rbp+320h+var_3A0]; void *
0x180017355  mov     r8d, r14d; Size
0x180017358  xor     edx, edx; Val
0x18001735a  call    memset_0
0x18001735f  mov     [rsp+420h+var_3E0], 0
0x180017367  xorps   xmm0, xmm0
0x18001736a  movups  [rsp+420h+var_3D8], xmm0
0x18001736f  movups  [rsp+420h+var_3C8], xmm0
0x180017374  movups  [rsp+420h+var_3B8], xmm0
0x180017379  test    rbx, rbx
0x18001737c  jz      loc_180017640
0x180017382  mov     edx, [rbx+30h]
0x180017385  bt      edx, 10h
0x180017389  jnb     short loc_1800173AF
0x18001738b  mov     eax, 10040h
0x180017390  and     edx, eax
0x180017392  cmp     edx, eax
0x180017394  jnz     loc_180017640
0x18001739a  cmp     esi, 2ECh
0x1800173a0  jb      loc_180017640
0x1800173a6  lea     rdx, [rbx+2CCh]
0x1800173ad  jmp     short loc_18001741A
0x1800173af  mov     eax, edx
0x1800173b1  bt      edx, 14h
0x1800173b5  jnb     short loc_1800173EC
0x1800173b7  mov     ecx, 100080h
0x1800173bc  and     eax, ecx
0x1800173be  cmp     eax, ecx
0x1800173c0  mov     eax, 100040h
0x1800173c5  setnz   cl
0x1800173c8  and     edx, eax
0x1800173ca  cmp     edx, eax
0x1800173cc  setnz   al
0x1800173cf  test    al, cl
0x1800173d1  jnz     loc_180017640
0x1800173d7  cmp     esi, 4F0h
0x1800173dd  jb      loc_180017640
0x1800173e3  lea     rdx, [rbx+4D0h]
0x1800173ea  jmp     short loc_18001741A
0x1800173ec  mov     ecx, 400020h
0x1800173f1  and     eax, ecx
0x1800173f3  cmp     eax, ecx
0x1800173f5  setz    cl
0x1800173f8  bt      edx, 16h
0x1800173fc  setb    al
0x1800173ff  test    al, cl
0x180017401  jz      loc_180017640
0x180017407  cmp     esi, 3B0h
0x18001740d  jb      loc_180017640
0x180017413  lea     rdx, [rbx+390h]
0x18001741a  test    rdx, rdx
0x18001741d  jz      loc_180017640
0x180017423  movsxd  r8, dword ptr [rdx+10h]
0x180017427  mov     ecx, [rdx]
0x180017429  cmp     ecx, r8d
0x18001742c  jg      loc_180017640
0x180017432  mov     r9d, [rdx+14h]
0x180017436  add     ecx, [rdx+4]
0x180017439  add     r9d, r8d
0x18001743c  cmp     r9d, ecx
0x18001743f  jg      loc_180017640
0x180017445  cmp     r8d, r9d
0x180017448  jg      loc_180017640
0x18001744e  lea     rdi, [rdx+r8]
0x180017452  cmp     rdi, rbx
0x180017455  jb      loc_180017640
0x18001745b  mov     rax, rsi
0x18001745e  not     rax
0x180017461  cmp     rbx, rax
0x180017464  ja      loc_180017640
0x18001746a  lea     rax, [rsi+rbx]
0x18001746e  cmp     rdi, rax
0x180017471  jnb     loc_180017640
0x180017477  test    rdi, rdi
0x18001747a  jz      loc_180017640
0x180017480  mov     rcx, [r15+10h]
0x180017484  lea     rdx, [rsp+420h+var_3E0]
0x180017489  mov     r8, [r15+0D0h]
0x180017490  lea     r9, [rbp+320h+var_3A0]
0x180017494  mov     [rsp+420h+var_3F8], rdx
0x180017499  mov     rdx, [r13+40h]
0x18001749d  mov     rax, [rcx]
0x1800174a0  mov     dword ptr [rsp+420h+var_400], r14d
0x1800174a5  mov     rax, [rax+0E8h]
0x1800174ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174b1  mov     esi, eax
0x1800174b3  test    eax, eax
0x1800174b5  js      loc_180017613
0x1800174bb  cmp     [rsp+420h+var_3E0], r14d
0x1800174c0  jnz     loc_180017613
0x1800174c6  mov     ebx, 2
0x1800174cb  test    [rbp+320h+var_38C], bl
0x1800174ce  jz      loc_180017640
0x1800174d4  mov     r8, [rdi+8]
0x1800174d8  bt      r8, 0Bh
0x1800174dd  jnb     loc_180017640
0x1800174e3  mov     r9, [rbp+320h+var_180]
0x1800174ea  mov     edx, 240h
0x1800174ef  mov     ecx, ebx
0x1800174f1  mov     r11d, 0FFFFFFC0h
0x1800174f7  mov     eax, 1
0x1800174fc  shl     rax, cl
0x1800174ff  test    r8, rax
0x180017502  jz      short loc_180017518
0x180017504  test    r9, rax
0x180017507  jz      short loc_18001750F
0x180017509  add     edx, 3Fh ; '?'
0x18001750c  and     edx, r11d
0x18001750f  mov     eax, ecx
0x180017511  add     edx, [rbp+rax*4+320h+var_174]
0x180017518  inc     ecx
0x18001751a  cmp     ecx, 0Bh
0x18001751d  jb      short loc_1800174F7
0x18001751f  bt      r9, 0Bh
0x180017524  jnb     short loc_18001752C
0x180017526  add     edx, 3Fh ; '?'
0x180017529  and     edx, r11d
0x18001752c  add     edx, 0FFFFFE00h
0x180017532  cmp     edx, 0FFFFFFFFh
0x180017535  jz      loc_180017640
0x18001753b  test    byte ptr [rdx+rdi], 1
0x18001753f  mov     esi, edx
0x180017541  jz      loc_180017640
0x180017547  mov     rcx, [r15+10h]
0x18001754b  lea     r9, [rsp+420h+var_3D8]
0x180017550  mov     r8, [rdx+rdi+8]
0x180017555  mov     rdx, [r13+40h]
0x180017559  mov     rax, [rcx]
0x18001755c  mov     rax, [rax+0F8h]
0x180017563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017568  mov     r14d, eax
0x18001756b  test    eax, eax
0x18001756d  jns     short loc_180017593
0x18001756f  mov     rcx, [r15+28h]
0x180017573  lea     r8, aUnableToAddSha_1; "Unable to add shadow stack memory regio"...
0x18001757a  mov     r9d, r14d
0x18001757d  mov     rdx, [rcx]
0x180017580  mov     rax, [rdx+8]
0x180017584  mov     edx, ebx
0x180017586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001758b  mov     eax, r14d
0x18001758e  jmp     loc_180017642
0x180017593  mov     rcx, [rsi+rdi+8]
0x180017598  mov     r8, qword ptr [rsp+420h+var_3D8]
0x18001759d  cmp     rcx, r8
0x1800175a0  jb      short loc_1800175F3
0x1800175a2  add     r8, qword ptr [rsp+420h+var_3C8+8]
0x1800175a7  cmp     rcx, r8
0x1800175aa  ja      short loc_1800175F3
0x1800175ac  sub     r8, rcx
0x1800175af  mov     r9d, 1
0x1800175b5  mov     [rsp+420h+var_3F8], r8
0x1800175ba  mov     rdx, r13
0x1800175bd  mov     [rsp+420h+var_400], rcx
0x1800175c2  mov     r8d, ebx
0x1800175c5  mov     rcx, r15
0x1800175c8  call    ?GenAddMemoryRange@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@W4MEMBLOCK_TYPE@@W4MEMBLOCK_FILTER_TYPE@@_K4@Z; GenAddMemoryRange(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,MEMBLOCK_TYPE,MEMBLOCK_FILTER_TYPE,unsigned __int64,unsigned __int64)
0x1800175cd  mov     edi, eax
0x1800175cf  test    eax, eax
0x1800175d1  jns     short loc_180017640
0x1800175d3  mov     rcx, [r15+28h]
0x1800175d7  lea     r8, aUnableToAddSha_0; "Unable to add shadow stack memory regio"...
0x1800175de  mov     r9d, edi
0x1800175e1  mov     rdx, [rcx]
0x1800175e4  mov     rax, [rdx+8]
0x1800175e8  mov     edx, ebx
0x1800175ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175ef  mov     eax, edi
0x1800175f1  jmp     short loc_180017642
0x1800175f3  mov     rcx, [r15+28h]
0x1800175f7  lea     r8, aUnableToAddSha_2; "Unable to add shadow stack memory regio"...
0x1800175fe  mov     edx, ebx
0x180017600  mov     rax, [rcx]
0x180017603  mov     rax, [rax+8]
0x180017607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001760c  mov     eax, 80004005h
0x180017611  jmp     short loc_180017642
0x180017613  mov     rcx, [r15+28h]
0x180017617  lea     r8, aUnableToAddSha; "Unable to add shadow stack memory regio"...
0x18001761e  mov     r9d, esi
0x180017621  mov     edx, 2
0x180017626  mov     rax, [rcx]
0x180017629  mov     rax, [rax+8]
0x18001762d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017632  mov     eax, 80004005h
0x180017637  test    esi, esi
0x180017639  cmovz   esi, eax
0x18001763c  mov     eax, esi
0x18001763e  jmp     short loc_180017642
0x180017640  xor     eax, eax
0x180017642  mov     rcx, [rbp+320h+var_40]
0x180017649  xor     rcx, rsp; StackCookie
0x18001764c  call    __security_check_cookie
0x180017651  add     rsp, 3F0h
0x180017658  pop     r15
0x18001765a  pop     r14
0x18001765c  pop     r13
0x18001765e  pop     rdi
0x18001765f  pop     rsi
0x180017660  pop     rbx
0x180017661  pop     rbp
0x180017662  retn
```
