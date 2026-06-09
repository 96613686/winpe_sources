# GlobalDoWork(ulong,IHttpEventProvider *)

- ea: `0x180001280`
- end: `0x180001523`
- name: `?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z`
- size: `675`
- prototype: `__int64 __fastcall(int, __int64 *)`
- caller_count: `14`
- callee_count: `3`
- tags: ``

## callers

- `0x180002200`
- `0x180002210`
- `0x180002220`
- `0x180002230`
- `0x180002240`
- `0x180002250`
- `0x180002260`
- `0x180002270`
- `0x180002280`
- `0x180002290`
- `0x1800022a0`
- `0x1800022b0`
- `0x1800022c0`
- `0x1800022d0`

## callees

- `0x180001280`
- `0x180002620`
- `0x180003010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180001365`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001516`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001365`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001516`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18000150b`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18000150b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800012e3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800012e3`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180001413`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180001413`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x1800014d8`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x1800014d8`
- `iisutil!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x1800013bb`
- `iisutil!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x1800013bb`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x1800013e0`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x1800013e0`

## string_xrefs

- `0x18000132e`: `TOKEN`

## pseudocode

```c
__int64 __fastcall GlobalDoWork(int a1, __int64 *a2)
{
  PVOID v4; // rsi
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rcx
  int v8; // r8d
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // ebx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // r15
  __int64 v20; // rdi
  __int64 v21; // rax
  __int64 (__fastcall *v22)(__int64); // rbx
  __int64 v23; // rbp
  unsigned __int16 *v24; // rax
  __int64 v25; // rbp
  int v26; // edx
  int v27; // ecx
  __int64 v28; // [rsp+20h] [rbp-E8h] BYREF
  _BYTE v29[56]; // [rsp+28h] [rbp-E0h] BYREF
  _OWORD v30[8]; // [rsp+60h] [rbp-A8h] BYREF

  memset(v30, 0, sizeof(v30));
  STRU::STRU((STRU *)v29, (unsigned __int16 *)v30, 0x40u);
  if ( a1 == 4 )
  {
    if ( g_pTokenCache )
      CLKRHashTable::Clear((CLKRHashTable *)g_pTokenCache);
  }
  else if ( a1 == 16 )
  {
    v4 = g_pTokenCache;
    if ( g_pTokenCache )
    {
      v5 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 16))(a2);
      v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
      v7 = 0;
      do
      {
        v8 = *(unsigned __int16 *)(v6 + 2 * v7++);
        v9 = aToken[v7 - 1];
        v10 = (unsigned int)(v8 - v9);
      }
      while ( !(_DWORD)v10 && v7 != 6 );
      if ( !(_DWORD)v10 )
      {
        v13 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, const wchar_t *))(*a2 + 8))(a2, v9, v10, L"TOKEN");
        if ( v13 )
        {
          v14 = v13 - 1;
          if ( !v14 )
          {
            v16 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 24))(a2);
            CLKRHashTable::InsertRecord(v4, v16, 0);
            v11 = 1;
            goto LABEL_9;
          }
          if ( v14 == 1 )
          {
            v15 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 16))(a2);
            CLKRHashTable::DeleteKey(v4, v15);
            v11 = 1;
            goto LABEL_9;
          }
        }
        else
        {
          v17 = *a2;
          v28 = 0;
          v18 = (*(__int64 (__fastcall **)(__int64 *))(v17 + 16))(a2);
          if ( !(unsigned int)CLKRHashTable::FindKey(v4, v18, &v28) )
          {
            v19 = v28;
            v20 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 16))(a2);
            v21 = (**(__int64 (__fastcall ***)(__int64))v19)(v19);
            v22 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 48LL);
            v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 48LL))(v21);
            v24 = (unsigned __int16 *)v22(v20);
            v25 = v23 - (_QWORD)v24;
            do
            {
              v26 = *(unsigned __int16 *)((char *)v24 + v25);
              v27 = *v24 - v26;
              if ( v27 )
                break;
              ++v24;
            }
            while ( v26 );
            if ( v27 )
            {
              CLKRHashTable::DeleteRecord(v4, v19);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
            }
            else
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 24LL))(v19);
              (*(void (__fastcall **)(__int64 *, __int64))(*a2 + 32))(a2, v19);
            }
            v11 = 1;
            goto LABEL_9;
          }
        }
      }
      v11 = 0;
LABEL_9:
      STRU::~STRU((STRU *)v29);
      return v11;
    }
  }
  STRU::~STRU((STRU *)v29);
  return 0;
}

```

## disassembly

```asm
0x180001280  mov     r11, rsp
0x180001283  push    rbx
0x180001284  push    rsi
0x180001285  push    r14
0x180001287  sub     rsp, 0F0h
0x18000128e  mov     rax, cs:__security_cookie
0x180001295  xor     rax, rsp
0x180001298  mov     [rsp+108h+var_28], rax
0x1800012a0  xorps   xmm0, xmm0
0x1800012a3  mov     r14, rdx
0x1800012a6  movups  [rsp+108h+var_A8], xmm0
0x1800012ab  mov     ebx, ecx
0x1800012ad  mov     r8d, 40h ; '@'
0x1800012b3  movups  [rsp+108h+var_98], xmm0
0x1800012b8  lea     rdx, [rsp+108h+var_A8]
0x1800012bd  movups  [rsp+108h+var_88], xmm0
0x1800012c5  lea     rcx, [rsp+108h+var_E0]
0x1800012ca  movups  xmmword ptr [r11-78h], xmm0
0x1800012cf  movups  xmmword ptr [r11-68h], xmm0
0x1800012d4  movups  xmmword ptr [r11-58h], xmm0
0x1800012d9  movups  xmmword ptr [r11-48h], xmm0
0x1800012de  movups  xmmword ptr [r11-38h], xmm0
0x1800012e3  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800012e9  cmp     ebx, 4
0x1800012ec  jz      loc_1800014FF
0x1800012f2  cmp     ebx, 10h
0x1800012f5  jnz     loc_180001511
0x1800012fb  mov     rsi, cs:?g_pTokenCache@@3PEAVTOKEN_CACHE@@EA; TOKEN_CACHE * g_pTokenCache
0x180001302  test    rsi, rsi
0x180001305  jz      loc_180001511
0x18000130b  mov     rax, [r14]
0x18000130e  mov     rcx, r14
0x180001311  mov     rax, [rax+10h]
0x180001315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000131a  mov     rdx, rax
0x18000131d  mov     rcx, [rax]
0x180001320  mov     rax, [rcx+8]
0x180001324  mov     rcx, rdx
0x180001327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000132c  xor     ecx, ecx
0x18000132e  lea     r9, aToken; "TOKEN"
0x180001335  nop     word ptr [rax+rax+00000000h]
0x180001340  movzx   r8d, word ptr [rax+rcx*2]
0x180001345  inc     rcx
0x180001348  movzx   edx, word ptr [r9+rcx*2-2]
0x18000134e  sub     r8d, edx
0x180001351  jnz     short loc_180001359
0x180001353  cmp     rcx, 6
0x180001357  jnz     short loc_180001340
0x180001359  test    r8d, r8d
0x18000135c  jz      short loc_180001389
0x18000135e  xor     ebx, ebx
0x180001360  lea     rcx, [rsp+108h+var_E0]
0x180001365  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000136b  mov     eax, ebx
0x18000136d  mov     rcx, [rsp+108h+var_28]
0x180001375  xor     rcx, rsp; StackCookie
0x180001378  call    __security_check_cookie
0x18000137d  add     rsp, 0F0h
0x180001384  pop     r14
0x180001386  pop     rsi
0x180001387  pop     rbx
0x180001388  retn
0x180001389  mov     rax, [r14]
0x18000138c  mov     rcx, r14
0x18000138f  mov     rax, [rax+8]
0x180001393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001398  test    eax, eax
0x18000139a  jz      short loc_1800013F0
0x18000139c  sub     eax, 1
0x18000139f  jz      short loc_1800013C8
0x1800013a1  cmp     eax, 1
0x1800013a4  jnz     short loc_18000135E
0x1800013a6  mov     rax, [r14]
0x1800013a9  mov     rcx, r14
0x1800013ac  mov     rax, [rax+10h]
0x1800013b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013b5  mov     rdx, rax
0x1800013b8  mov     rcx, rsi
0x1800013bb  call    cs:__imp_?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z; CLKRHashTable::DeleteKey(unsigned __int64)
0x1800013c1  mov     ebx, 1
0x1800013c6  jmp     short loc_180001360
0x1800013c8  mov     rax, [r14]
0x1800013cb  mov     rcx, r14
0x1800013ce  mov     rax, [rax+18h]
0x1800013d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013d7  xor     r8d, r8d
0x1800013da  mov     rdx, rax
0x1800013dd  mov     rcx, rsi
0x1800013e0  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x1800013e6  mov     ebx, 1
0x1800013eb  jmp     loc_180001360
0x1800013f0  mov     rax, [r14]
0x1800013f3  mov     rcx, r14
0x1800013f6  mov     [rsp+108h+var_E8], 0
0x1800013ff  mov     rax, [rax+10h]
0x180001403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001408  mov     rdx, rax
0x18000140b  lea     r8, [rsp+108h+var_E8]
0x180001410  mov     rcx, rsi
0x180001413  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180001419  test    eax, eax
0x18000141b  jnz     loc_18000135E
0x180001421  mov     rax, [r14]
0x180001424  mov     rcx, r14
0x180001427  mov     [rsp+108h+arg_0], rbp
0x18000142f  mov     [rsp+108h+arg_10], rdi
0x180001437  mov     [rsp+108h+arg_18], r15
0x18000143f  mov     rax, [rax+10h]
0x180001443  mov     r15, [rsp+108h+var_E8]
0x180001448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000144d  mov     rcx, [r15]
0x180001450  mov     rdi, rax
0x180001453  mov     rax, [rcx]
0x180001456  mov     rcx, r15
0x180001459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000145e  mov     rdx, rax
0x180001461  mov     rcx, [rax]
0x180001464  mov     rax, [rcx+30h]
0x180001468  mov     rcx, [rdi]
0x18000146b  mov     rbx, [rcx+30h]
0x18000146f  mov     rcx, rdx
0x180001472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001477  mov     rbp, rax
0x18000147a  mov     rcx, rdi
0x18000147d  mov     rax, rbx
0x180001480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001485  mov     rdi, [rsp+108h+arg_10]
0x18000148d  sub     rbp, rax
0x180001490  movzx   ecx, word ptr [rax]
0x180001493  movzx   edx, word ptr [rax+rbp]
0x180001497  sub     ecx, edx
0x180001499  jnz     short loc_1800014A3
0x18000149b  add     rax, 2
0x18000149f  test    edx, edx
0x1800014a1  jnz     short loc_180001490
0x1800014a3  mov     rbp, [rsp+108h+arg_0]
0x1800014ab  test    ecx, ecx
0x1800014ad  jnz     short loc_1800014D2
0x1800014af  mov     rax, [r15]
0x1800014b2  mov     rcx, r15
0x1800014b5  mov     rax, [rax+18h]
0x1800014b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014be  mov     rax, [r14]
0x1800014c1  mov     rdx, r15
0x1800014c4  mov     rcx, r14
0x1800014c7  mov     rax, [rax+20h]
0x1800014cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014d0  jmp     short loc_1800014ED
0x1800014d2  mov     rdx, r15
0x1800014d5  mov     rcx, rsi
0x1800014d8  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x1800014de  mov     rax, [r15]
0x1800014e1  mov     rcx, r15
0x1800014e4  mov     rax, [rax+10h]
0x1800014e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014ed  mov     r15, [rsp+108h+arg_18]
0x1800014f5  mov     ebx, 1
0x1800014fa  jmp     loc_180001360
0x1800014ff  mov     rcx, cs:?g_pTokenCache@@3PEAVTOKEN_CACHE@@EA; TOKEN_CACHE * g_pTokenCache
0x180001506  test    rcx, rcx
0x180001509  jz      short loc_180001511
0x18000150b  call    cs:__imp_?Clear@CLKRHashTable@@QEAAXXZ; CLKRHashTable::Clear(void)
0x180001511  lea     rcx, [rsp+108h+var_E0]
0x180001516  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000151c  xor     eax, eax
0x18000151e  jmp     loc_18000136D
```
