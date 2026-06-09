# CIISGlobalModule::OnGlobalCacheOperation(ICacheProvider *)

- ea: `0x180001010`
- end: `0x180001276`
- name: `?OnGlobalCacheOperation@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVICacheProvider@@@Z`
- size: `614`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001010`
- `0x180002620`
- `0x180003010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x1800010d5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001269`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800010d5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001269`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001070`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001070`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180001177`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180001177`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x18000123d`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x18000123d`
- `iisutil!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x18000112a`
- `iisutil!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x18000112a`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000114d`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000114d`

## string_xrefs

- `0x1800010a9`: `TOKEN`

## pseudocode

```c
__int64 __fastcall CIISGlobalModule::OnGlobalCacheOperation(__int64 a1, __int64 *a2)
{
  PVOID v3; // rbp
  __int64 v4; // rax
  __int64 v5; // rax
  unsigned int v6; // ebx
  __int64 v7; // rcx
  int v8; // r8d
  __int64 v9; // rdx
  __int64 v10; // r8
  int v12; // eax
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // r14
  __int64 v19; // rdi
  __int64 v20; // rax
  __int64 (__fastcall *v21)(__int64); // rbx
  __int64 v22; // r15
  unsigned __int16 *v23; // rax
  __int64 v24; // r15
  int v25; // edx
  int v26; // ecx
  __int64 v27; // [rsp+20h] [rbp-E8h] BYREF
  _BYTE v28[56]; // [rsp+28h] [rbp-E0h] BYREF
  _OWORD v29[8]; // [rsp+60h] [rbp-A8h] BYREF

  memset(v29, 0, sizeof(v29));
  STRU::STRU((STRU *)v28, (unsigned __int16 *)v29, 0x40u);
  v3 = g_pTokenCache;
  if ( !g_pTokenCache )
  {
    STRU::~STRU((STRU *)v28);
    return 0;
  }
  v4 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 16))(a2);
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  v6 = 0;
  v7 = 0;
  do
  {
    v8 = *(unsigned __int16 *)(v5 + 2 * v7++);
    v9 = aToken[v7 - 1];
    v10 = (unsigned int)(v8 - v9);
  }
  while ( !(_DWORD)v10 && v7 != 6 );
  if ( !(_DWORD)v10 )
  {
    v12 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, const wchar_t *))(*a2 + 8))(a2, v9, v10, L"TOKEN");
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        if ( v13 != 1 )
          goto LABEL_6;
        v14 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 16))(a2);
        CLKRHashTable::DeleteKey(v3, v14);
      }
      else
      {
        v15 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 24))(a2);
        CLKRHashTable::InsertRecord(v3, v15, 0);
      }
    }
    else
    {
      v16 = *a2;
      v27 = 0;
      v17 = (*(__int64 (__fastcall **)(__int64 *))(v16 + 16))(a2);
      if ( (unsigned int)CLKRHashTable::FindKey(v3, v17, &v27) )
        goto LABEL_6;
      v18 = v27;
      v19 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 16))(a2);
      v20 = (**(__int64 (__fastcall ***)(__int64))v18)(v18);
      v21 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 48LL);
      v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 48LL))(v20);
      v23 = (unsigned __int16 *)v21(v19);
      v24 = v22 - (_QWORD)v23;
      do
      {
        v25 = *(unsigned __int16 *)((char *)v23 + v24);
        v26 = *v23 - v25;
        if ( v26 )
          break;
        ++v23;
      }
      while ( v25 );
      if ( v26 )
      {
        CLKRHashTable::DeleteRecord(v3, v18);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
      else
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 24LL))(v18);
        (*(void (__fastcall **)(__int64 *, __int64))(*a2 + 32))(a2, v18);
      }
    }
    v6 = 1;
  }
LABEL_6:
  STRU::~STRU((STRU *)v28);
  return v6;
}

```

## disassembly

```asm
0x180001010  mov     r11, rsp
0x180001013  push    rbx
0x180001014  push    rbp
0x180001015  push    rsi
0x180001016  sub     rsp, 0F0h
0x18000101d  mov     rax, cs:__security_cookie
0x180001024  xor     rax, rsp
0x180001027  mov     [rsp+108h+var_28], rax
0x18000102f  xorps   xmm0, xmm0
0x180001032  lea     rcx, [rsp+108h+var_E0]
0x180001037  movups  [rsp+108h+var_A8], xmm0
0x18000103c  mov     rsi, rdx
0x18000103f  mov     r8d, 40h ; '@'
0x180001045  movups  [rsp+108h+var_98], xmm0
0x18000104a  lea     rdx, [rsp+108h+var_A8]
0x18000104f  movups  [rsp+108h+var_88], xmm0
0x180001057  movups  xmmword ptr [r11-78h], xmm0
0x18000105c  movups  xmmword ptr [r11-68h], xmm0
0x180001061  movups  xmmword ptr [r11-58h], xmm0
0x180001066  movups  xmmword ptr [r11-48h], xmm0
0x18000106b  movups  xmmword ptr [r11-38h], xmm0
0x180001070  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180001076  mov     rbp, cs:?g_pTokenCache@@3PEAVTOKEN_CACHE@@EA; TOKEN_CACHE * g_pTokenCache
0x18000107d  test    rbp, rbp
0x180001080  jz      loc_180001264
0x180001086  mov     rax, [rsi]
0x180001089  mov     rcx, rsi
0x18000108c  mov     rax, [rax+10h]
0x180001090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001095  mov     rdx, rax
0x180001098  mov     rcx, [rax]
0x18000109b  mov     rax, [rcx+8]
0x18000109f  mov     rcx, rdx
0x1800010a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010a7  xor     ebx, ebx
0x1800010a9  lea     r9, aToken; "TOKEN"
0x1800010b0  mov     ecx, ebx
0x1800010b2  movzx   r8d, word ptr [rax+rcx*2]
0x1800010b7  inc     rcx
0x1800010ba  movzx   edx, word ptr [r9+rcx*2-2]
0x1800010c0  sub     r8d, edx
0x1800010c3  jnz     short loc_1800010CB
0x1800010c5  cmp     rcx, 6
0x1800010c9  jnz     short loc_1800010B2
0x1800010cb  test    r8d, r8d
0x1800010ce  jz      short loc_1800010F8
0x1800010d0  lea     rcx, [rsp+108h+var_E0]
0x1800010d5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800010db  mov     eax, ebx
0x1800010dd  mov     rcx, [rsp+108h+var_28]
0x1800010e5  xor     rcx, rsp; StackCookie
0x1800010e8  call    __security_check_cookie
0x1800010ed  add     rsp, 0F0h
0x1800010f4  pop     rsi
0x1800010f5  pop     rbp
0x1800010f6  pop     rbx
0x1800010f7  retn
0x1800010f8  mov     rax, [rsi]
0x1800010fb  mov     rcx, rsi
0x1800010fe  mov     rax, [rax+8]
0x180001102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001107  test    eax, eax
0x180001109  jz      short loc_180001158
0x18000110b  sub     eax, 1
0x18000110e  jz      short loc_180001135
0x180001110  cmp     eax, 1
0x180001113  jnz     short loc_1800010D0
0x180001115  mov     rax, [rsi]
0x180001118  mov     rcx, rsi
0x18000111b  mov     rax, [rax+10h]
0x18000111f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001124  mov     rdx, rax
0x180001127  mov     rcx, rbp
0x18000112a  call    cs:__imp_?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z; CLKRHashTable::DeleteKey(unsigned __int64)
0x180001130  jmp     loc_18000125A
0x180001135  mov     rax, [rsi]
0x180001138  mov     rcx, rsi
0x18000113b  mov     rax, [rax+18h]
0x18000113f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001144  xor     r8d, r8d
0x180001147  mov     rdx, rax
0x18000114a  mov     rcx, rbp
0x18000114d  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180001153  jmp     loc_18000125A
0x180001158  mov     rax, [rsi]
0x18000115b  mov     rcx, rsi
0x18000115e  mov     [rsp+108h+var_E8], rbx
0x180001163  mov     rax, [rax+10h]
0x180001167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000116c  mov     rdx, rax
0x18000116f  lea     r8, [rsp+108h+var_E8]
0x180001174  mov     rcx, rbp
0x180001177  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18000117d  test    eax, eax
0x18000117f  jnz     loc_1800010D0
0x180001185  mov     rax, [rsi]
0x180001188  mov     rcx, rsi
0x18000118b  mov     [rsp+108h+arg_0], rdi
0x180001193  mov     [rsp+108h+arg_10], r14
0x18000119b  mov     r14, [rsp+108h+var_E8]
0x1800011a0  mov     rax, [rax+10h]
0x1800011a4  mov     [rsp+108h+arg_18], r15
0x1800011ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011b1  mov     rcx, [r14]
0x1800011b4  mov     rdi, rax
0x1800011b7  mov     rax, [rcx]
0x1800011ba  mov     rcx, r14
0x1800011bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011c2  mov     rdx, rax
0x1800011c5  mov     rcx, [rax]
0x1800011c8  mov     rax, [rcx+30h]
0x1800011cc  mov     rcx, [rdi]
0x1800011cf  mov     rbx, [rcx+30h]
0x1800011d3  mov     rcx, rdx
0x1800011d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011db  mov     r15, rax
0x1800011de  mov     rcx, rdi
0x1800011e1  mov     rax, rbx
0x1800011e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011e9  mov     rdi, [rsp+108h+arg_0]
0x1800011f1  sub     r15, rax
0x1800011f4  movzx   ecx, word ptr [rax]
0x1800011f7  movzx   edx, word ptr [rax+r15]
0x1800011fc  sub     ecx, edx
0x1800011fe  jnz     short loc_180001208
0x180001200  add     rax, 2
0x180001204  test    edx, edx
0x180001206  jnz     short loc_1800011F4
0x180001208  mov     r15, [rsp+108h+arg_18]
0x180001210  test    ecx, ecx
0x180001212  jnz     short loc_180001237
0x180001214  mov     rax, [r14]
0x180001217  mov     rcx, r14
0x18000121a  mov     rax, [rax+18h]
0x18000121e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001223  mov     rax, [rsi]
0x180001226  mov     rdx, r14
0x180001229  mov     rcx, rsi
0x18000122c  mov     rax, [rax+20h]
0x180001230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001235  jmp     short loc_180001252
0x180001237  mov     rdx, r14
0x18000123a  mov     rcx, rbp
0x18000123d  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x180001243  mov     rax, [r14]
0x180001246  mov     rcx, r14
0x180001249  mov     rax, [rax+10h]
0x18000124d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001252  mov     r14, [rsp+108h+arg_10]
0x18000125a  mov     ebx, 1
0x18000125f  jmp     loc_1800010D0
0x180001264  lea     rcx, [rsp+108h+var_E0]
0x180001269  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000126f  xor     ebx, ebx
0x180001271  jmp     loc_1800010DB
```
