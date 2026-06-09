# FindOrRemoveCommandSwitch(ushort *,ulong,ushort const *,bool)

- ea: `0x14000566c`
- end: `0x140005708`
- name: `?FindOrRemoveCommandSwitch@@YA_NPEAGKPEBG_N@Z`
- size: `156`
- prototype: `bool(unsigned __int16 *, unsigned int, const unsigned __int16 *, bool)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400014e4`
- `0x140003394`
- `0x140004128`
- `0x140005710`

## callees

- `0x140004d68`
- `0x140005634`
- `0x14000566c`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l1-1-0!StrStrIW` at `0x14000568f`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrStrIW` at `0x14000568f`

## pseudocode

```c
char __fastcall FindOrRemoveCommandSwitch(unsigned __int16 *a1, int a2, const unsigned __int16 *a3, char a4)
{
  char v5; // si
  unsigned __int16 *v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // rcx
  const unsigned __int16 *v12; // r8
  unsigned int v13; // ebp

  v5 = 0;
  v9 = StrStrIW(a1, a3);
  if ( v9 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a3[v10] );
    v11 = (int)wil::safe_cast_failfast<int,unsigned __int64,0>();
    v12 = &v9[v11];
    if ( (*v12 & 0xFFDF) == 0 && (v9 == a1 || *(v9 - 1) == 32) )
    {
      v5 = 1;
      if ( a4 )
      {
        while ( *v12 == 32 )
        {
          ++v12;
          LODWORD(v11) = v11 + 1;
        }
        v13 = a2 - v11;
        StringCchCopyW(v9, v13, v12);
        a1[v13] = 0;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x14000566c  push    rbx
0x14000566e  push    rbp
0x14000566f  push    rsi
0x140005670  push    rdi
0x140005671  push    r12
0x140005673  push    r14
0x140005675  push    r15
0x140005677  sub     rsp, 20h
0x14000567b  mov     ebp, edx
0x14000567d  xor     r12d, r12d
0x140005680  mov     rdx, r8; pszSrch
0x140005683  mov     sil, r12b
0x140005686  mov     r15b, r9b
0x140005689  mov     rbx, r8
0x14000568c  mov     r14, rcx
0x14000568f  call    cs:__imp_StrStrIW
0x140005695  mov     rdi, rax
0x140005698  test    rax, rax
0x14000569b  jz      short loc_1400056F6
0x14000569d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400056a1  inc     rcx
0x1400056a4  cmp     [rbx+rcx*2], r12w
0x1400056a9  jnz     short loc_1400056A1
0x1400056ab  call    ??$safe_cast_failfast@H_K$0A@@wil@@YAH_K@Z; wil::safe_cast_failfast<int,unsigned __int64,0>(unsigned __int64)
0x1400056b0  movsxd  rcx, eax
0x1400056b3  mov     eax, 0FFDFh
0x1400056b8  lea     r8, [rdi+rcx*2]
0x1400056bc  test    [r8], ax
0x1400056c0  jnz     short loc_1400056F6
0x1400056c2  cmp     rdi, r14
0x1400056c5  jz      short loc_1400056CE
0x1400056c7  cmp     word ptr [rdi-2], 20h ; ' '
0x1400056cc  jnz     short loc_1400056F6
0x1400056ce  mov     sil, 1
0x1400056d1  test    r15b, r15b
0x1400056d4  jz      short loc_1400056F6
0x1400056d6  jmp     short loc_1400056DE
0x1400056d8  add     r8, 2; unsigned __int16 *
0x1400056dc  inc     ecx
0x1400056de  cmp     word ptr [r8], 20h ; ' '
0x1400056e3  jz      short loc_1400056D8
0x1400056e5  sub     ebp, ecx
0x1400056e7  mov     rcx, rdi; unsigned __int16 *
0x1400056ea  mov     edx, ebp; unsigned __int64
0x1400056ec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400056f1  mov     [r14+rbp*2], r12w
0x1400056f6  mov     al, sil
0x1400056f9  add     rsp, 20h
0x1400056fd  pop     r15
0x1400056ff  pop     r14
0x140005701  pop     r12
0x140005703  pop     rdi
0x140005704  pop     rsi
0x140005705  pop     rbp
0x140005706  pop     rbx
0x140005707  retn
```
