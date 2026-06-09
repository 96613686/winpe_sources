# META_SCRIPT_MAP_TABLE::CalculateScriptMapEntry(ushort const *,char const *,ulong,ulong *,MULTISZ *)

- ea: `0x18000d8a0`
- end: `0x18000dace`
- name: `?CalculateScriptMapEntry@META_SCRIPT_MAP_TABLE@@QEAAPEAVMETA_SCRIPT_MAP_ENTRY@@PEBGPEBDKPEAKPEAVMULTISZ@@@Z`
- size: `558`
- prototype: `struct META_SCRIPT_MAP_ENTRY *(META_SCRIPT_MAP_TABLE *__hidden this, const unsigned __int16 *, const char *, unsigned int, unsigned int *, struct MULTISZ *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c980`

## callees

- `0x18000d8a0`
- `0x18000dae0`
- `0x1800343be`
- `0x180035010`

## import_xrefs

- `iisutil!?FindString@MULTISZ@@QEAAHPEBG@Z` at `0x18000da49`
- `iisutil!?FindString@MULTISZ@@QEAAHPEBG@Z` at `0x18000da49`

## string_xrefs

- `0x18000da8d`: `*.DLL`

## pseudocode

```c
struct META_SCRIPT_MAP_ENTRY *__fastcall META_SCRIPT_MAP_TABLE::CalculateScriptMapEntry(
        META_SCRIPT_MAP_TABLE *this,
        wchar_t *a2,
        const char *a3,
        char a4,
        unsigned int *a5,
        struct MULTISZ *a6)
{
  __int64 v9; // rbp
  META_SCRIPT_MAP_TABLE *v10; // rax
  char *v11; // r12
  char *v12; // rsi
  const unsigned __int16 *v13; // rbx
  _WORD *v14; // rax
  unsigned __int8 *v15; // rax
  __int64 v16; // rdx
  const char *v17; // r8
  unsigned __int8 *v18; // r9
  unsigned __int8 v19; // cl
  unsigned __int8 *v20; // rax
  int v21; // ecx
  __int64 v22; // rax
  const unsigned __int16 *v23; // rax
  const unsigned __int16 *matched; // rax
  char *v25; // rax
  __int64 v26; // rbx
  const wchar_t *v28; // rdi

  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  v10 = (META_SCRIPT_MAP_TABLE *)*((_QWORD *)this + 1);
  v11 = (char *)this + 8;
  if ( v10 == (META_SCRIPT_MAP_TABLE *)((char *)this + 8) )
    v12 = 0;
  else
    v12 = (char *)v10 - 8;
  while ( 1 )
  {
    if ( !v12 )
      return 0;
    v13 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(char *, _QWORD))(*(_QWORD *)v12 + 24LL))(v12, 0);
    if ( !*v13 )
      v13 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v12 + 80LL))(v12);
    v14 = (_WORD *)(**(__int64 (__fastcall ***)(char *))v12)(v12);
    if ( *v14 != 42 || v14[1] != 46 || v14[2] || !a6 || !MULTISZ::FindString(a6, v13) )
      break;
LABEL_22:
    v25 = (char *)*((_QWORD *)v12 + 1);
    if ( v25 == v11 )
      v12 = 0;
    else
      v12 = v25 - 8;
  }
  v15 = (unsigned __int8 *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v12 + 8LL))(v12);
  v18 = v15;
  v19 = *v15;
  if ( *v15 != 42 && v15[1] )
  {
    while ( v19 )
    {
      v20 = v18;
      v17 = (const char *)(a3 - (const char *)v18);
      do
      {
        v21 = (unsigned __int8)v17[(_QWORD)v20];
        v16 = (unsigned int)*v20 - v21;
        if ( (_DWORD)v16 )
          break;
        ++v20;
      }
      while ( v21 );
      if ( !(_DWORD)v16 )
        goto LABEL_21;
      v22 = -1;
      do
        ++v22;
      while ( v18[v22] );
      v18 += v22 + 1;
      v19 = *v18;
    }
    goto LABEL_22;
  }
LABEL_21:
  v23 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(char *, __int64, const char *, unsigned __int8 *))v12)(
                                    v12,
                                    v16,
                                    v17,
                                    v18);
  matched = MatchPathInUrl(a2, v9, v23);
  if ( !matched )
    goto LABEL_22;
  v26 = matched - a2;
  if ( (*(unsigned int (__fastcall **)(char *))(*(_QWORD *)v12 + 48LL))(v12) == 4
    && (a4 & 4) == 0
    && !*(_WORD *)(*(__int64 (__fastcall **)(char *, _QWORD))(*(_QWORD *)v12 + 24LL))(v12, 0) )
  {
    v28 = (const wchar_t *)(**(__int64 (__fastcall ***)(char *))v12)(v12);
    if ( !wcscmp_0(L"*.DLL", v28) || !wcscmp_0(L"*.EXE", v28) )
      goto LABEL_22;
  }
  if ( a5 )
    *a5 = v26;
  return (struct META_SCRIPT_MAP_ENTRY *)v12;
}

```

## disassembly

```asm
0x18000d8a0  mov     [rsp+arg_10], rbp
0x18000d8a5  push    rsi
0x18000d8a6  push    r12
0x18000d8a8  push    r13
0x18000d8aa  push    r14
0x18000d8ac  push    r15
0x18000d8ae  sub     rsp, 20h
0x18000d8b2  mov     r13d, r9d
0x18000d8b5  mov     r14, r8
0x18000d8b8  mov     r15, rdx
0x18000d8bb  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x18000d8c2  inc     rbp
0x18000d8c5  cmp     word ptr [rdx+rbp*2], 0
0x18000d8ca  jnz     short loc_18000D8C2
0x18000d8cc  mov     rax, [rcx+8]
0x18000d8d0  lea     r12, [rcx+8]
0x18000d8d4  cmp     rax, r12
0x18000d8d7  jz      loc_18000DA58
0x18000d8dd  lea     rsi, [rax-8]
0x18000d8e1  mov     [rsp+48h+arg_0], rbx
0x18000d8e6  mov     [rsp+48h+arg_8], rdi
0x18000d8eb  nop     dword ptr [rax+rax+00h]
0x18000d8f0  test    rsi, rsi
0x18000d8f3  jz      loc_18000DAC7
0x18000d8f9  mov     rax, [rsi]
0x18000d8fc  xor     edx, edx
0x18000d8fe  mov     rcx, rsi
0x18000d901  mov     rax, [rax+18h]
0x18000d905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d90a  mov     rbx, rax
0x18000d90d  cmp     word ptr [rax], 0
0x18000d911  jnz     short loc_18000D925
0x18000d913  mov     rax, [rsi]
0x18000d916  mov     rcx, rsi
0x18000d919  mov     rax, [rax+50h]
0x18000d91d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d922  mov     rbx, rax
0x18000d925  mov     rax, [rsi]
0x18000d928  mov     rcx, rsi
0x18000d92b  mov     rax, [rax]
0x18000d92e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d933  cmp     word ptr [rax], 2Ah ; '*'
0x18000d937  jnz     short loc_18000D94B
0x18000d939  cmp     word ptr [rax+2], 2Eh ; '.'
0x18000d93e  jnz     short loc_18000D94B
0x18000d940  cmp     word ptr [rax+4], 0
0x18000d945  jz      loc_18000DA35
0x18000d94b  mov     rax, [rsi]
0x18000d94e  mov     rcx, rsi
0x18000d951  mov     rax, [rax+8]
0x18000d955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d95a  mov     r9, rax
0x18000d95d  movzx   ecx, byte ptr [rax]
0x18000d960  cmp     cl, 2Ah ; '*'
0x18000d963  jz      short loc_18000D9B6
0x18000d965  cmp     byte ptr [rax+1], 0
0x18000d969  jz      short loc_18000D9B6
0x18000d96b  nop     dword ptr [rax+rax+00h]
0x18000d970  test    cl, cl
0x18000d972  jz      short loc_18000D9D9
0x18000d974  mov     r8, r14
0x18000d977  mov     rax, r9
0x18000d97a  sub     r8, r9
0x18000d97d  nop     dword ptr [rax]
0x18000d980  movzx   edx, byte ptr [rax]
0x18000d983  movzx   ecx, byte ptr [rax+r8]
0x18000d988  sub     edx, ecx
0x18000d98a  jnz     short loc_18000D993
0x18000d98c  inc     rax
0x18000d98f  test    ecx, ecx
0x18000d991  jnz     short loc_18000D980
0x18000d993  test    edx, edx
0x18000d995  jz      short loc_18000D9B6
0x18000d997  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000d99e  xchg    ax, ax
0x18000d9a0  inc     rax
0x18000d9a3  cmp     byte ptr [r9+rax], 0
0x18000d9a8  jnz     short loc_18000D9A0
0x18000d9aa  inc     r9
0x18000d9ad  add     r9, rax
0x18000d9b0  movzx   ecx, byte ptr [r9]
0x18000d9b4  jmp     short loc_18000D970
0x18000d9b6  mov     rax, [rsi]
0x18000d9b9  mov     rcx, rsi
0x18000d9bc  mov     rax, [rax]
0x18000d9bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9c4  mov     r8, rax; unsigned __int16 *
0x18000d9c7  mov     edx, ebp; unsigned int
0x18000d9c9  mov     rcx, r15; String1
0x18000d9cc  call    ?MatchPathInUrl@@YAPEBGPEBGK0@Z; MatchPathInUrl(ushort const *,ulong,ushort const *)
0x18000d9d1  mov     rbx, rax
0x18000d9d4  test    rax, rax
0x18000d9d7  jnz     short loc_18000D9EF
0x18000d9d9  mov     rax, [rsi+8]
0x18000d9dd  cmp     rax, r12
0x18000d9e0  jz      loc_18000DAC0
0x18000d9e6  lea     rsi, [rax-8]
0x18000d9ea  jmp     loc_18000D8F0
0x18000d9ef  mov     rax, [rsi]
0x18000d9f2  sub     rbx, r15
0x18000d9f5  mov     rcx, rsi
0x18000d9f8  sar     rbx, 1
0x18000d9fb  mov     rax, [rax+30h]
0x18000d9ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da04  cmp     eax, 4
0x18000da07  jz      short loc_18000DA5F
0x18000da09  mov     rcx, [rsp+48h+arg_20]
0x18000da0e  test    rcx, rcx
0x18000da11  jz      short loc_18000DA15
0x18000da13  mov     [rcx], ebx
0x18000da15  mov     rax, rsi
0x18000da18  mov     rdi, [rsp+48h+arg_8]
0x18000da1d  mov     rbx, [rsp+48h+arg_0]
0x18000da22  mov     rbp, [rsp+48h+arg_10]
0x18000da27  add     rsp, 20h
0x18000da2b  pop     r15
0x18000da2d  pop     r14
0x18000da2f  pop     r13
0x18000da31  pop     r12
0x18000da33  pop     rsi
0x18000da34  retn
0x18000da35  cmp     [rsp+48h+arg_28], 0
0x18000da3b  jz      loc_18000D94B
0x18000da41  mov     rcx, [rsp+48h+arg_28]
0x18000da46  mov     rdx, rbx
0x18000da49  call    cs:__imp_?FindString@MULTISZ@@QEAAHPEBG@Z; MULTISZ::FindString(ushort const *)
0x18000da4f  test    eax, eax
0x18000da51  jnz     short loc_18000D9D9
0x18000da53  jmp     loc_18000D94B
0x18000da58  xor     esi, esi
0x18000da5a  jmp     loc_18000D8E1
0x18000da5f  test    r13b, 4
0x18000da63  jnz     short loc_18000DA09
0x18000da65  mov     rax, [rsi]
0x18000da68  xor     edx, edx
0x18000da6a  mov     rcx, rsi
0x18000da6d  mov     rax, [rax+18h]
0x18000da71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da76  cmp     word ptr [rax], 0
0x18000da7a  jnz     short loc_18000DA09
0x18000da7c  mov     rax, [rsi]
0x18000da7f  mov     rcx, rsi
0x18000da82  mov     rax, [rax]
0x18000da85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da8a  mov     rdx, rax; String2
0x18000da8d  lea     rcx, aDll; "*.DLL"
0x18000da94  mov     rdi, rax
0x18000da97  call    wcscmp_0
0x18000da9c  test    eax, eax
0x18000da9e  jz      loc_18000D9D9
0x18000daa4  mov     rdx, rdi; String2
0x18000daa7  lea     rcx, aExe; "*.EXE"
0x18000daae  call    wcscmp_0
0x18000dab3  test    eax, eax
0x18000dab5  jnz     loc_18000DA09
0x18000dabb  jmp     loc_18000D9D9
0x18000dac0  xor     esi, esi
0x18000dac2  jmp     loc_18000D8F0
0x18000dac7  xor     eax, eax
0x18000dac9  jmp     loc_18000DA18
```
