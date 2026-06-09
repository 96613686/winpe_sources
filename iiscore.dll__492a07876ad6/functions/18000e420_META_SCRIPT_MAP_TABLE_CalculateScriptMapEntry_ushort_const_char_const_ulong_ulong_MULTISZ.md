# META_SCRIPT_MAP_TABLE::CalculateScriptMapEntry(ushort const *,char const *,ulong,ulong *,MULTISZ *)

- ea: `0x18000e420`
- end: `0x18000e659`
- name: `?CalculateScriptMapEntry@META_SCRIPT_MAP_TABLE@@QEAAPEAVMETA_SCRIPT_MAP_ENTRY@@PEBGPEBDKPEAKPEAVMULTISZ@@@Z`
- size: `569`
- prototype: `struct META_SCRIPT_MAP_ENTRY *(META_SCRIPT_MAP_TABLE *__hidden this, const unsigned __int16 *, const char *, unsigned int, unsigned int *, struct MULTISZ *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d9a0`

## callees

- `0x18000e420`
- `0x18000e660`
- `0x18003775e`
- `0x180038010`

## import_xrefs

- `iisutil!?FindString@MULTISZ@@QEAAHPEBG@Z` at `0x18000e5ca`
- `iisutil!?FindString@MULTISZ@@QEAAHPEBG@Z` at `0x18000e5ca`

## string_xrefs

- `0x18000e618`: `*.DLL`

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
  wchar_t *matched; // rax
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
0x18000e420  mov     [rsp+arg_10], rbp
0x18000e425  push    rsi
0x18000e426  push    r12
0x18000e428  push    r13
0x18000e42a  push    r14
0x18000e42c  push    r15
0x18000e42e  sub     rsp, 20h
0x18000e432  mov     r13d, r9d
0x18000e435  mov     r14, r8
0x18000e438  mov     r15, rdx
0x18000e43b  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x18000e442  inc     rbp
0x18000e445  cmp     word ptr [rdx+rbp*2], 0
0x18000e44a  jnz     short loc_18000E442
0x18000e44c  mov     rax, [rcx+8]
0x18000e450  lea     r12, [rcx+8]
0x18000e454  cmp     rax, r12
0x18000e457  jz      loc_18000E5E3
0x18000e45d  lea     rsi, [rax-8]
0x18000e461  mov     [rsp+48h+arg_0], rbx
0x18000e466  mov     [rsp+48h+arg_8], rdi
0x18000e46b  nop     dword ptr [rax+rax+00h]
0x18000e470  test    rsi, rsi
0x18000e473  jz      loc_18000E652
0x18000e479  mov     rax, [rsi]
0x18000e47c  xor     edx, edx
0x18000e47e  mov     rcx, rsi
0x18000e481  mov     rax, [rax+18h]
0x18000e485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e48a  mov     rbx, rax
0x18000e48d  cmp     word ptr [rax], 0
0x18000e491  jnz     short loc_18000E4A5
0x18000e493  mov     rax, [rsi]
0x18000e496  mov     rcx, rsi
0x18000e499  mov     rax, [rax+50h]
0x18000e49d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4a2  mov     rbx, rax
0x18000e4a5  mov     rax, [rsi]
0x18000e4a8  mov     rcx, rsi
0x18000e4ab  mov     rax, [rax]
0x18000e4ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4b3  cmp     word ptr [rax], 2Ah ; '*'
0x18000e4b7  jnz     short loc_18000E4CB
0x18000e4b9  cmp     word ptr [rax+2], 2Eh ; '.'
0x18000e4be  jnz     short loc_18000E4CB
0x18000e4c0  cmp     word ptr [rax+4], 0
0x18000e4c5  jz      loc_18000E5B6
0x18000e4cb  mov     rax, [rsi]
0x18000e4ce  mov     rcx, rsi
0x18000e4d1  mov     rax, [rax+8]
0x18000e4d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4da  mov     r9, rax
0x18000e4dd  movzx   ecx, byte ptr [rax]
0x18000e4e0  cmp     cl, 2Ah ; '*'
0x18000e4e3  jz      short loc_18000E536
0x18000e4e5  cmp     byte ptr [rax+1], 0
0x18000e4e9  jz      short loc_18000E536
0x18000e4eb  nop     dword ptr [rax+rax+00h]
0x18000e4f0  test    cl, cl
0x18000e4f2  jz      short loc_18000E559
0x18000e4f4  mov     r8, r14
0x18000e4f7  mov     rax, r9
0x18000e4fa  sub     r8, r9
0x18000e4fd  nop     dword ptr [rax]
0x18000e500  movzx   edx, byte ptr [rax]
0x18000e503  movzx   ecx, byte ptr [rax+r8]
0x18000e508  sub     edx, ecx
0x18000e50a  jnz     short loc_18000E513
0x18000e50c  inc     rax
0x18000e50f  test    ecx, ecx
0x18000e511  jnz     short loc_18000E500
0x18000e513  test    edx, edx
0x18000e515  jz      short loc_18000E536
0x18000e517  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000e51e  xchg    ax, ax
0x18000e520  inc     rax
0x18000e523  cmp     byte ptr [r9+rax], 0
0x18000e528  jnz     short loc_18000E520
0x18000e52a  inc     r9
0x18000e52d  add     r9, rax
0x18000e530  movzx   ecx, byte ptr [r9]
0x18000e534  jmp     short loc_18000E4F0
0x18000e536  mov     rax, [rsi]
0x18000e539  mov     rcx, rsi
0x18000e53c  mov     rax, [rax]
0x18000e53f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e544  mov     r8, rax; unsigned __int16 *
0x18000e547  mov     edx, ebp; unsigned int
0x18000e549  mov     rcx, r15; String1
0x18000e54c  call    ?MatchPathInUrl@@YAPEBGPEBGK0@Z; MatchPathInUrl(ushort const *,ulong,ushort const *)
0x18000e551  mov     rbx, rax
0x18000e554  test    rax, rax
0x18000e557  jnz     short loc_18000E56F
0x18000e559  mov     rax, [rsi+8]
0x18000e55d  cmp     rax, r12
0x18000e560  jz      loc_18000E64B
0x18000e566  lea     rsi, [rax-8]
0x18000e56a  jmp     loc_18000E470
0x18000e56f  mov     rax, [rsi]
0x18000e572  sub     rbx, r15
0x18000e575  mov     rcx, rsi
0x18000e578  sar     rbx, 1
0x18000e57b  mov     rax, [rax+30h]
0x18000e57f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e584  cmp     eax, 4
0x18000e587  jz      short loc_18000E5EA
0x18000e589  mov     rcx, [rsp+48h+arg_20]
0x18000e58e  test    rcx, rcx
0x18000e591  jz      short loc_18000E595
0x18000e593  mov     [rcx], ebx
0x18000e595  mov     rax, rsi
0x18000e598  mov     rdi, [rsp+48h+arg_8]
0x18000e59d  mov     rbx, [rsp+48h+arg_0]
0x18000e5a2  mov     rbp, [rsp+48h+arg_10]
0x18000e5a7  add     rsp, 20h
0x18000e5ab  pop     r15
0x18000e5ad  pop     r14
0x18000e5af  pop     r13
0x18000e5b1  pop     r12
0x18000e5b3  pop     rsi
0x18000e5b4  retn
0x18000e5b6  cmp     [rsp+48h+arg_28], 0
0x18000e5bc  jz      loc_18000E4CB
0x18000e5c2  mov     rcx, [rsp+48h+arg_28]
0x18000e5c7  mov     rdx, rbx
0x18000e5ca  call    cs:__imp_?FindString@MULTISZ@@QEAAHPEBG@Z; MULTISZ::FindString(ushort const *)
0x18000e5d1  nop     dword ptr [rax+rax+00h]
0x18000e5d6  test    eax, eax
0x18000e5d8  jnz     loc_18000E559
0x18000e5de  jmp     loc_18000E4CB
0x18000e5e3  xor     esi, esi
0x18000e5e5  jmp     loc_18000E461
0x18000e5ea  test    r13b, 4
0x18000e5ee  jnz     short loc_18000E589
0x18000e5f0  mov     rax, [rsi]
0x18000e5f3  xor     edx, edx
0x18000e5f5  mov     rcx, rsi
0x18000e5f8  mov     rax, [rax+18h]
0x18000e5fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e601  cmp     word ptr [rax], 0
0x18000e605  jnz     short loc_18000E589
0x18000e607  mov     rax, [rsi]
0x18000e60a  mov     rcx, rsi
0x18000e60d  mov     rax, [rax]
0x18000e610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e615  mov     rdx, rax; String2
0x18000e618  lea     rcx, aDll; "*.DLL"
0x18000e61f  mov     rdi, rax
0x18000e622  call    wcscmp_0
0x18000e627  test    eax, eax
0x18000e629  jz      loc_18000E559
0x18000e62f  mov     rdx, rdi; String2
0x18000e632  lea     rcx, aExe; "*.EXE"
0x18000e639  call    wcscmp_0
0x18000e63e  test    eax, eax
0x18000e640  jnz     loc_18000E589
0x18000e646  jmp     loc_18000E559
0x18000e64b  xor     esi, esi
0x18000e64d  jmp     loc_18000E470
0x18000e652  xor     eax, eax
0x18000e654  jmp     loc_18000E598
```
