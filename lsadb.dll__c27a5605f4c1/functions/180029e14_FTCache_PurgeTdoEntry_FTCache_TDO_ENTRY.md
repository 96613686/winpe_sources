# FTCache::PurgeTdoEntry(FTCache::TDO_ENTRY *)

- ea: `0x180029e14`
- end: `0x18002a156`
- name: `?PurgeTdoEntry@FTCache@@AEAAXPEAUTDO_ENTRY@1@@Z`
- size: `834`
- prototype: `void __fastcall(FTCache *__hidden this, struct FTCache::TDO_ENTRY *)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180025ba8`
- `0x180028510`
- `0x18002a92c`
- `0x18002ae5c`

## callees

- `0x180029e14`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029ea8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029fde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029fe7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a0cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a0d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a113`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a11c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a13d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029ea8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029fde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029fe7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a0cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a0d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a113`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a11c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a13d`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180029e98`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180029f76`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180029f9f`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180029fcd`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002a090`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002a0be`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180029e98`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180029f76`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180029f9f`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180029fcd`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002a090`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002a0be`

## pseudocode

```c
void __fastcall FTCache::PurgeTdoEntry(FTCache *this, struct FTCache::TDO_ENTRY *a2)
{
  _QWORD **v3; // rsi
  _QWORD *v5; // rbx
  __int64 v6; // rax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  _QWORD *v9; // rcx
  _QWORD *v10; // rdx
  void **v11; // rsi
  void ***v12; // rbx
  void **v13; // rax
  void **v14; // rcx
  char **v15; // rdx
  void **v16; // rax
  char **v17; // rdx
  void **v18; // rax
  char **v19; // rdx
  void **v20; // rcx
  void **v21; // rdx
  void **v22; // rdx
  void **v23; // rax
  void **v24; // rdx
  void **v25; // rsi
  void ***v26; // rbx
  void **v27; // rax
  void **v28; // rcx
  char **v29; // rdx
  void **v30; // rax
  char **v31; // rdx
  void **v32; // rcx
  void **v33; // rdx
  void **v34; // rax
  void **v35; // rdx
  void **v36; // rsi
  void ***v37; // rbx
  void **v38; // rax
  void **v39; // rcx
  void *v40; // rcx

  v3 = (_QWORD **)((char *)a2 + 24);
  while ( 1 )
  {
    v5 = *v3;
    if ( *v3 == v3 )
      break;
    v6 = *v5;
    if ( *(_QWORD **)(*v5 + 8LL) != v5
      || (v7 = (_QWORD *)v5[1], (_QWORD *)*v7 != v5)
      || (*v7 = v6, *(_QWORD *)(v6 + 8) = v7, v8 = v5[2], *(_QWORD **)(v8 + 8) != v5 + 2)
      || (v9 = (_QWORD *)v5[3], (_QWORD *)*v9 != v5 + 2) )
    {
LABEL_47:
      __fastfail(3u);
    }
    *v9 = v8;
    *(_QWORD *)(v8 + 8) = v9;
    --*(_DWORD *)(v5[8] + 16LL);
    v10 = (_QWORD *)v5[8];
    if ( (_QWORD *)v10[3] == v10 + 3 )
    {
      RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)((char *)this + 112), v10);
      --FTCache::sm_TlnKeys;
    }
    LocalFree(v5);
    --FTCache::sm_TlnEntries;
  }
  v11 = (void **)((char *)a2 + 40);
  while ( 1 )
  {
    v12 = (void ***)*v11;
    if ( *v11 == v11 )
      break;
    v13 = *v12;
    if ( (*v12)[1] != v12 )
      goto LABEL_47;
    v14 = v12[1];
    if ( *v14 != v12 )
      goto LABEL_47;
    *v14 = v13;
    v13[1] = v14;
    v15 = (char **)v12[2];
    if ( v15[1] != (char *)(v12 + 2) )
      goto LABEL_47;
    v16 = v12[3];
    if ( *v16 != v12 + 2 )
      goto LABEL_47;
    *v16 = v15;
    v15[1] = (char *)v16;
    v17 = (char **)v12[4];
    if ( v17[1] != (char *)(v12 + 4) )
      goto LABEL_47;
    v18 = v12[5];
    if ( *v18 != v12 + 4 )
      goto LABEL_47;
    *v18 = v17;
    v17[1] = (char *)v18;
    v19 = (char **)v12[6];
    if ( v19[1] != (char *)(v12 + 6) )
      goto LABEL_47;
    v20 = v12[7];
    if ( *v20 != v12 + 6 )
      goto LABEL_47;
    *v20 = v19;
    v19[1] = (char *)v20;
    --*((_DWORD *)v12[13] + 2);
    v21 = v12[13];
    if ( v21[2] == v21 + 2 )
    {
      RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)((char *)this + 216), v21);
      --FTCache::sm_SidKeys;
    }
    --*((_DWORD *)v12[14] + 4);
    v22 = v12[14];
    if ( v22[3] == v22 + 3 )
    {
      RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)((char *)this + 320), v22);
      --FTCache::sm_DnsNameKeys;
    }
    v23 = v12[15];
    if ( v23 )
    {
      --*((_DWORD *)v23 + 4);
      v24 = v12[15];
      if ( v24[3] == v24 + 3 )
      {
        RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)((char *)this + 424), v24);
        --FTCache::sm_NetbiosNameKeys;
      }
    }
    LocalFree(v12[10]);
    LocalFree(v12);
    --FTCache::sm_DomainInfoEntries;
  }
  v25 = (void **)((char *)a2 + 56);
  while ( 1 )
  {
    v26 = (void ***)*v25;
    if ( *v25 == v25 )
      break;
    v27 = *v26;
    if ( (*v26)[1] != v26 )
      goto LABEL_47;
    v28 = v26[1];
    if ( *v28 != v26 )
      goto LABEL_47;
    *v28 = v27;
    v27[1] = v28;
    v29 = (char **)v26[2];
    if ( v29[1] != (char *)(v26 + 2) )
      goto LABEL_47;
    v30 = v26[3];
    if ( *v30 != v26 + 2 )
      goto LABEL_47;
    *v30 = v29;
    v29[1] = (char *)v30;
    v31 = (char **)v26[4];
    if ( v31[1] != (char *)(v26 + 4) )
      goto LABEL_47;
    v32 = v26[5];
    if ( *v32 != v26 + 4 )
      goto LABEL_47;
    *v32 = v31;
    v31[1] = (char *)v32;
    --*((_DWORD *)v26[10] + 4);
    v33 = v26[10];
    if ( v33[3] == v33 + 3 )
    {
      RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)((char *)this + 528), v33);
      --FTCache::sm_ScannerDnsNameKeys;
    }
    v34 = v26[11];
    if ( v34 )
    {
      --*((_DWORD *)v34 + 4);
      v35 = v26[11];
      if ( v35[3] == v35 + 3 )
      {
        RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)((char *)this + 632), v35);
        --FTCache::sm_ScannerNetbiosNameKeys;
      }
    }
    LocalFree(v26[8]);
    LocalFree(v26);
    --FTCache::sm_ScannerInfoEntries;
  }
  v36 = (void **)((char *)a2 + 72);
  while ( 1 )
  {
    v37 = (void ***)*v36;
    if ( *v36 == v36 )
      break;
    v38 = *v37;
    if ( (*v37)[1] != v37 )
      goto LABEL_47;
    v39 = v37[1];
    if ( *v39 != v37 )
      goto LABEL_47;
    *v39 = v38;
    v38[1] = v39;
    LocalFree(v37[5]);
    LocalFree(v37);
    --FTCache::sm_BinaryEntries;
  }
  v40 = (void *)*((_QWORD *)a2 + 2);
  *((_DWORD *)a2 + 22) = 0;
  LocalFree(v40);
  *((_QWORD *)a2 + 2) = 0;
}

```

## disassembly

```asm
0x180029e14  push    rbx
0x180029e16  push    rbp
0x180029e17  push    rsi
0x180029e18  push    rdi
0x180029e19  push    r14
0x180029e1b  sub     rsp, 20h
0x180029e1f  mov     rdi, rdx
0x180029e22  lea     rsi, [rdx+18h]
0x180029e26  mov     rbp, rcx
0x180029e29  or      r14d, 0FFFFFFFFh
0x180029e2d  mov     rbx, [rsi]
0x180029e30  cmp     rbx, rsi
0x180029e33  jz      loc_180029EBA
0x180029e39  mov     rax, [rbx]
0x180029e3c  cmp     [rax+8], rbx
0x180029e40  jnz     loc_18002A12B
0x180029e46  mov     rcx, [rbx+8]
0x180029e4a  cmp     [rcx], rbx
0x180029e4d  jnz     loc_18002A12B
0x180029e53  mov     [rcx], rax
0x180029e56  mov     [rax+8], rcx
0x180029e5a  lea     rax, [rbx+10h]
0x180029e5e  mov     rdx, [rax]
0x180029e61  cmp     [rdx+8], rax
0x180029e65  jnz     loc_18002A12B
0x180029e6b  mov     rcx, [rbx+18h]
0x180029e6f  cmp     [rcx], rax
0x180029e72  jnz     loc_18002A12B
0x180029e78  mov     [rcx], rdx
0x180029e7b  mov     [rdx+8], rcx
0x180029e7f  mov     rax, [rbx+40h]
0x180029e83  add     [rax+10h], r14d
0x180029e87  mov     rdx, [rbx+40h]; Buffer
0x180029e8b  lea     rax, [rdx+18h]
0x180029e8f  cmp     [rax], rax
0x180029e92  jnz     short loc_180029EA5
0x180029e94  lea     rcx, [rbp+70h]; Table
0x180029e98  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180029e9e  add     cs:?sm_TlnKeys@FTCache@@0KA, r14d; ulong FTCache::sm_TlnKeys
0x180029ea5  mov     rcx, rbx; hMem
0x180029ea8  call    cs:__imp_LocalFree
0x180029eae  add     cs:?sm_TlnEntries@FTCache@@0KA, r14d; ulong FTCache::sm_TlnEntries
0x180029eb5  jmp     loc_180029E2D
0x180029eba  lea     rsi, [rdi+28h]
0x180029ebe  mov     rbx, [rsi]
0x180029ec1  cmp     rbx, rsi
0x180029ec4  jz      loc_180029FF9
0x180029eca  mov     rax, [rbx]
0x180029ecd  cmp     [rax+8], rbx
0x180029ed1  jnz     loc_18002A12B
0x180029ed7  mov     rcx, [rbx+8]
0x180029edb  cmp     [rcx], rbx
0x180029ede  jnz     loc_18002A12B
0x180029ee4  mov     [rcx], rax
0x180029ee7  mov     [rax+8], rcx
0x180029eeb  lea     rcx, [rbx+10h]
0x180029eef  mov     rdx, [rcx]
0x180029ef2  cmp     [rdx+8], rcx
0x180029ef6  jnz     loc_18002A12B
0x180029efc  mov     rax, [rbx+18h]
0x180029f00  cmp     [rax], rcx
0x180029f03  jnz     loc_18002A12B
0x180029f09  mov     [rax], rdx
0x180029f0c  lea     rcx, [rbx+20h]
0x180029f10  mov     [rdx+8], rax
0x180029f14  mov     rdx, [rcx]
0x180029f17  cmp     [rdx+8], rcx
0x180029f1b  jnz     loc_18002A12B
0x180029f21  mov     rax, [rbx+28h]
0x180029f25  cmp     [rax], rcx
0x180029f28  jnz     loc_18002A12B
0x180029f2e  mov     [rax], rdx
0x180029f31  mov     [rdx+8], rax
0x180029f35  lea     rax, [rbx+30h]
0x180029f39  mov     rdx, [rax]
0x180029f3c  cmp     [rdx+8], rax
0x180029f40  jnz     loc_18002A12B
0x180029f46  mov     rcx, [rbx+38h]
0x180029f4a  cmp     [rcx], rax
0x180029f4d  jnz     loc_18002A12B
0x180029f53  mov     [rcx], rdx
0x180029f56  mov     [rdx+8], rcx
0x180029f5a  mov     rax, [rbx+68h]
0x180029f5e  add     [rax+8], r14d
0x180029f62  mov     rdx, [rbx+68h]; Buffer
0x180029f66  lea     rax, [rdx+10h]
0x180029f6a  cmp     [rax], rax
0x180029f6d  jnz     short loc_180029F83
0x180029f6f  lea     rcx, [rbp+0D8h]; Table
0x180029f76  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180029f7c  add     cs:?sm_SidKeys@FTCache@@0KA, r14d; ulong FTCache::sm_SidKeys
0x180029f83  mov     rax, [rbx+70h]
0x180029f87  add     [rax+10h], r14d
0x180029f8b  mov     rdx, [rbx+70h]; Buffer
0x180029f8f  lea     rax, [rdx+18h]
0x180029f93  cmp     [rax], rax
0x180029f96  jnz     short loc_180029FAC
0x180029f98  lea     rcx, [rbp+140h]; Table
0x180029f9f  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180029fa5  add     cs:?sm_DnsNameKeys@FTCache@@0KA, r14d; ulong FTCache::sm_DnsNameKeys
0x180029fac  mov     rax, [rbx+78h]
0x180029fb0  test    rax, rax
0x180029fb3  jz      short loc_180029FDA
0x180029fb5  add     [rax+10h], r14d
0x180029fb9  mov     rdx, [rbx+78h]; Buffer
0x180029fbd  lea     rax, [rdx+18h]
0x180029fc1  cmp     [rax], rax
0x180029fc4  jnz     short loc_180029FDA
0x180029fc6  lea     rcx, [rbp+1A8h]; Table
0x180029fcd  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180029fd3  add     cs:?sm_NetbiosNameKeys@FTCache@@0KA, r14d; ulong FTCache::sm_NetbiosNameKeys
0x180029fda  mov     rcx, [rbx+50h]; hMem
0x180029fde  call    cs:__imp_LocalFree
0x180029fe4  mov     rcx, rbx; hMem
0x180029fe7  call    cs:__imp_LocalFree
0x180029fed  add     cs:?sm_DomainInfoEntries@FTCache@@0KA, r14d; ulong FTCache::sm_DomainInfoEntries
0x180029ff4  jmp     loc_180029EBE
0x180029ff9  lea     rsi, [rdi+38h]
0x180029ffd  mov     rbx, [rsi]
0x18002a000  cmp     rbx, rsi
0x18002a003  jz      loc_18002A0EA
0x18002a009  mov     rax, [rbx]
0x18002a00c  cmp     [rax+8], rbx
0x18002a010  jnz     loc_18002A12B
0x18002a016  mov     rcx, [rbx+8]
0x18002a01a  cmp     [rcx], rbx
0x18002a01d  jnz     loc_18002A12B
0x18002a023  mov     [rcx], rax
0x18002a026  mov     [rax+8], rcx
0x18002a02a  lea     rcx, [rbx+10h]
0x18002a02e  mov     rdx, [rcx]
0x18002a031  cmp     [rdx+8], rcx
0x18002a035  jnz     loc_18002A12B
0x18002a03b  mov     rax, [rbx+18h]
0x18002a03f  cmp     [rax], rcx
0x18002a042  jnz     loc_18002A12B
0x18002a048  mov     [rax], rdx
0x18002a04b  mov     [rdx+8], rax
0x18002a04f  lea     rax, [rbx+20h]
0x18002a053  mov     rdx, [rax]
0x18002a056  cmp     [rdx+8], rax
0x18002a05a  jnz     loc_18002A12B
0x18002a060  mov     rcx, [rbx+28h]
0x18002a064  cmp     [rcx], rax
0x18002a067  jnz     loc_18002A12B
0x18002a06d  mov     [rcx], rdx
0x18002a070  mov     [rdx+8], rcx
0x18002a074  mov     rax, [rbx+50h]
0x18002a078  add     [rax+10h], r14d
0x18002a07c  mov     rdx, [rbx+50h]; Buffer
0x18002a080  lea     rax, [rdx+18h]
0x18002a084  cmp     [rax], rax
0x18002a087  jnz     short loc_18002A09D
0x18002a089  lea     rcx, [rbp+210h]; Table
0x18002a090  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18002a096  add     cs:?sm_ScannerDnsNameKeys@FTCache@@0KA, r14d; ulong FTCache::sm_ScannerDnsNameKeys
0x18002a09d  mov     rax, [rbx+58h]
0x18002a0a1  test    rax, rax
0x18002a0a4  jz      short loc_18002A0CB
0x18002a0a6  add     [rax+10h], r14d
0x18002a0aa  mov     rdx, [rbx+58h]; Buffer
0x18002a0ae  lea     rax, [rdx+18h]
0x18002a0b2  cmp     [rax], rax
0x18002a0b5  jnz     short loc_18002A0CB
0x18002a0b7  lea     rcx, [rbp+278h]; Table
0x18002a0be  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18002a0c4  add     cs:?sm_ScannerNetbiosNameKeys@FTCache@@0KA, r14d; ulong FTCache::sm_ScannerNetbiosNameKeys
0x18002a0cb  mov     rcx, [rbx+40h]; hMem
0x18002a0cf  call    cs:__imp_LocalFree
0x18002a0d5  mov     rcx, rbx; hMem
0x18002a0d8  call    cs:__imp_LocalFree
0x18002a0de  add     cs:?sm_ScannerInfoEntries@FTCache@@0KA, r14d; ulong FTCache::sm_ScannerInfoEntries
0x18002a0e5  jmp     loc_180029FFD
0x18002a0ea  lea     rsi, [rdi+48h]
0x18002a0ee  mov     rbx, [rsi]
0x18002a0f1  cmp     rbx, rsi
0x18002a0f4  jz      short loc_18002A132
0x18002a0f6  mov     rax, [rbx]
0x18002a0f9  cmp     [rax+8], rbx
0x18002a0fd  jnz     short loc_18002A12B
0x18002a0ff  mov     rcx, [rbx+8]
0x18002a103  cmp     [rcx], rbx
0x18002a106  jnz     short loc_18002A12B
0x18002a108  mov     [rcx], rax
0x18002a10b  mov     [rax+8], rcx
0x18002a10f  mov     rcx, [rbx+28h]; hMem
0x18002a113  call    cs:__imp_LocalFree
0x18002a119  mov     rcx, rbx; hMem
0x18002a11c  call    cs:__imp_LocalFree
0x18002a122  add     cs:?sm_BinaryEntries@FTCache@@0KA, r14d; ulong FTCache::sm_BinaryEntries
0x18002a129  jmp     short loc_18002A0EE
0x18002a12b  mov     ecx, 3
0x18002a130  int     29h; Win8: RtlFailFast(ecx)
0x18002a132  mov     rcx, [rdi+10h]; hMem
0x18002a136  mov     dword ptr [rdi+58h], 0
0x18002a13d  call    cs:__imp_LocalFree
0x18002a143  mov     qword ptr [rdi+10h], 0
0x18002a14b  add     rsp, 20h
0x18002a14f  pop     r14
0x18002a151  pop     rdi
0x18002a152  pop     rsi
0x18002a153  pop     rbp
0x18002a154  pop     rbx
0x18002a155  retn
```
