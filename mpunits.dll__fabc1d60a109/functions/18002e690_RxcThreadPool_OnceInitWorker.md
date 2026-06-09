# RxcThreadPool_OnceInitWorker

- ea: `0x18002e690`
- end: `0x18002e983`
- name: `RxcThreadPool_OnceInitWorker`
- size: `755`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000175c`
- `0x180008c40`
- `0x18002e690`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18002e7a8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18002e7a8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002e774`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002e774`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002e78b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002e78b`

## string_xrefs

- `0x18002e6bc`: `admin\wmi\winomi\mp\rxc\rxc.schedulers.threadpool.c`
- `0x18002e860`: `admin\wmi\winomi\mp\rxc\rxc.schedulers.threadpool.c`
- `0x18002e6e4`: `RxcThreadPool_OnceInitWorker`
- `0x18002e881`: `RxcThreadPool_OnceInitWorker - success`
- `0x18002e7d4`: `RxcThreadPool_OnceInitWorker - failure`

## pseudocode

```c
__int64 __fastcall RxcThreadPool_OnceInitWorker(__int64 a1, _QWORD *a2)
{
  __int64 (__fastcall **v2)(); // rbx
  __int64 v3; // rdi
  _OWORD *v5; // rax
  __int64 (__fastcall **v6)(); // rcx
  __int64 v7; // rdx
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  struct _TP_POOL *Threadpool; // rax
  _OWORD *v18; // rax
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  _OWORD *v29; // rcx
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int64 v39; // [rsp+30h] [rbp-D0h] BYREF
  const char *v40; // [rsp+38h] [rbp-C8h]
  int v41; // [rsp+40h] [rbp-C0h]
  int v42; // [rsp+44h] [rbp-BCh]
  _BYTE v43[352]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = NITS_STUB;
  v3 = 2;
  if ( NITS_PRESENCE_STUB == 1 )
  {
    v5 = v43;
    v6 = NITS_STUB;
    v7 = 2;
    do
    {
      v8 = *((_OWORD *)v6 + 1);
      *v5 = *(_OWORD *)v6;
      v9 = *((_OWORD *)v6 + 2);
      v5[1] = v8;
      v10 = *((_OWORD *)v6 + 3);
      v5[2] = v9;
      v11 = *((_OWORD *)v6 + 4);
      v5[3] = v10;
      v12 = *((_OWORD *)v6 + 5);
      v5[4] = v11;
      v13 = *((_OWORD *)v6 + 6);
      v5[5] = v12;
      v14 = *((_OWORD *)v6 + 7);
      v6 += 16;
      v5[6] = v13;
      v5[7] = v14;
      v5 += 8;
      --v7;
    }
    while ( v7 );
    v15 = *((_OWORD *)v6 + 1);
    *v5 = *(_OWORD *)v6;
    v16 = *((_OWORD *)v6 + 2);
    v5[1] = v15;
    v5[2] = v16;
  }
  else
  {
    v39 = 0;
    v40 = "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedulers.threadpool.c";
    v41 = 535;
    v42 = -1;
    ((void (__fastcall *)(const wchar_t *, __int64 *, _QWORD))BufferPostNotificationTrapMethod)(
      L"RxcThreadPool_OnceInitWorker",
      &v39,
      0);
  }
  Threadpool = CreateThreadpool(0);
  ptpp = Threadpool;
  if ( !Threadpool )
  {
LABEL_9:
    if ( NITS_PRESENCE_STUB == 1 )
    {
      v29 = v43;
      do
      {
        v30 = *((_OWORD *)v2 + 1);
        *v29 = *(_OWORD *)v2;
        v31 = *((_OWORD *)v2 + 2);
        v29[1] = v30;
        v32 = *((_OWORD *)v2 + 3);
        v29[2] = v31;
        v33 = *((_OWORD *)v2 + 4);
        v29[3] = v32;
        v34 = *((_OWORD *)v2 + 5);
        v29[4] = v33;
        v35 = *((_OWORD *)v2 + 6);
        v29[5] = v34;
        v36 = *((_OWORD *)v2 + 7);
        v2 += 16;
        v29[6] = v35;
        v29[7] = v36;
        v29 += 8;
        --v3;
      }
      while ( v3 );
      v37 = *((_OWORD *)v2 + 1);
      *v29 = *(_OWORD *)v2;
      v38 = *((_OWORD *)v2 + 2);
      v29[1] = v37;
      v29[2] = v38;
    }
    else
    {
      v39 = 0;
      v40 = "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedulers.threadpool.c";
      v41 = 571;
      v42 = -1;
      ((void (__fastcall *)(const wchar_t *, __int64 *, _QWORD))BufferPostNotificationTrapMethod)(
        L"RxcThreadPool_OnceInitWorker - failure",
        &v39,
        0);
    }
    return 0xFFFFFFFFLL;
  }
  SetThreadpoolThreadMinimum(Threadpool, 0);
  if ( atexit(RxcThreadPool_OnceInitCleanup) )
  {
    CloseThreadpool(ptpp);
    goto LABEL_9;
  }
  Cache_Construct(
    (unsigned int)&stru_18008E6B0,
    32,
    56,
    (unsigned int)RxcThreadPool_ImmediateItem_ObjectConstructor,
    (__int64)RxcThreadPool_ImmediateItem_ObjectDestructor);
  Cache_Construct(
    (unsigned int)&stru_18008E6F0,
    32,
    104,
    (unsigned int)RxcThreadPool_PostponedItem_ObjectConstructor,
    (__int64)RxcThreadPool_PostponedItem_ObjectDestructor);
  *a2 = &ptpp;
  if ( NITS_PRESENCE_STUB == 1 )
  {
    v18 = v43;
    do
    {
      v19 = *((_OWORD *)v2 + 1);
      *v18 = *(_OWORD *)v2;
      v20 = *((_OWORD *)v2 + 2);
      v18[1] = v19;
      v21 = *((_OWORD *)v2 + 3);
      v18[2] = v20;
      v22 = *((_OWORD *)v2 + 4);
      v18[3] = v21;
      v23 = *((_OWORD *)v2 + 5);
      v18[4] = v22;
      v24 = *((_OWORD *)v2 + 6);
      v18[5] = v23;
      v25 = *((_OWORD *)v2 + 7);
      v2 += 16;
      v18[6] = v24;
      v18[7] = v25;
      v18 += 8;
      --v3;
    }
    while ( v3 );
    v26 = *((_OWORD *)v2 + 1);
    *v18 = *(_OWORD *)v2;
    v27 = *((_OWORD *)v2 + 2);
    v18[1] = v26;
    v18[2] = v27;
  }
  else
  {
    v39 = 0;
    v40 = "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedulers.threadpool.c";
    v41 = 567;
    v42 = -1;
    ((void (__fastcall *)(const wchar_t *, __int64 *, _QWORD))BufferPostNotificationTrapMethod)(
      L"RxcThreadPool_OnceInitWorker - success",
      &v39,
      0);
  }
  return 0;
}

```

## disassembly

```asm
0x18002e690  push    rbp
0x18002e692  push    rbx
0x18002e693  push    rsi
0x18002e694  push    rdi
0x18002e695  push    r13
0x18002e697  push    r14
0x18002e699  lea     rbp, [rsp-88h]
0x18002e6a1  sub     rsp, 188h
0x18002e6a8  cmp     cs:NITS_PRESENCE_STUB, 1
0x18002e6b0  lea     rbx, NITS_STUB
0x18002e6b7  mov     edi, 2
0x18002e6bc  lea     r14, aAdminWmiWinomi_3; "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedu"...
0x18002e6c3  mov     rsi, rdx
0x18002e6c6  lea     r13d, [rdi+7Eh]
0x18002e6ca  jz      short loc_18002E707
0x18002e6cc  mov     rax, cs:off_180047A70
0x18002e6d3  lea     rdx, [rsp+1B0h+var_180]
0x18002e6d8  xor     r8d, r8d
0x18002e6db  mov     [rsp+1B0h+var_180], 0
0x18002e6e4  lea     rcx, aRxcthreadpoolO_1; "RxcThreadPool_OnceInitWorker"
0x18002e6eb  mov     [rsp+1B0h+var_178], r14
0x18002e6f0  mov     [rsp+1B0h+var_170], 217h
0x18002e6f8  mov     [rsp+1B0h+var_16C], 0FFFFFFFFh
0x18002e700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e705  jmp     short loc_18002E772
0x18002e707  lea     rax, [rsp+1B0h+var_160]
0x18002e70c  mov     rcx, rbx
0x18002e70f  mov     rdx, rdi
0x18002e712  movups  xmm0, xmmword ptr [rcx]
0x18002e715  movups  xmm1, xmmword ptr [rcx+10h]
0x18002e719  movups  xmmword ptr [rax], xmm0
0x18002e71c  movups  xmm0, xmmword ptr [rcx+20h]
0x18002e720  movups  xmmword ptr [rax+10h], xmm1
0x18002e724  movups  xmm1, xmmword ptr [rcx+30h]
0x18002e728  movups  xmmword ptr [rax+20h], xmm0
0x18002e72c  movups  xmm0, xmmword ptr [rcx+40h]
0x18002e730  movups  xmmword ptr [rax+30h], xmm1
0x18002e734  movups  xmm1, xmmword ptr [rcx+50h]
0x18002e738  movups  xmmword ptr [rax+40h], xmm0
0x18002e73c  movups  xmm0, xmmword ptr [rcx+60h]
0x18002e740  movups  xmmword ptr [rax+50h], xmm1
0x18002e744  movups  xmm1, xmmword ptr [rcx+70h]
0x18002e748  add     rcx, r13
0x18002e74b  movups  xmmword ptr [rax+60h], xmm0
0x18002e74f  movups  xmmword ptr [rax+70h], xmm1
0x18002e753  add     rax, r13
0x18002e756  sub     rdx, 1
0x18002e75a  jnz     short loc_18002E712
0x18002e75c  movups  xmm0, xmmword ptr [rcx]
0x18002e75f  movups  xmm1, xmmword ptr [rcx+10h]
0x18002e763  movups  xmmword ptr [rax], xmm0
0x18002e766  movups  xmm0, xmmword ptr [rcx+20h]
0x18002e76a  movups  xmmword ptr [rax+10h], xmm1
0x18002e76e  movups  xmmword ptr [rax+20h], xmm0
0x18002e772  xor     ecx, ecx; reserved
0x18002e774  call    cs:__imp_CreateThreadpool
0x18002e77a  mov     cs:ptpp, rax
0x18002e781  test    rax, rax
0x18002e784  jz      short loc_18002E7AE
0x18002e786  xor     edx, edx; cthrdMic
0x18002e788  mov     rcx, rax; ptpp
0x18002e78b  call    cs:__imp_SetThreadpoolThreadMinimum
0x18002e791  lea     rcx, RxcThreadPool_OnceInitCleanup; void (__cdecl *)()
0x18002e798  call    atexit
0x18002e79d  test    eax, eax
0x18002e79f  jz      short loc_18002E7FA
0x18002e7a1  mov     rcx, cs:ptpp; ptpp
0x18002e7a8  call    cs:__imp_CloseThreadpool
0x18002e7ae  cmp     cs:NITS_PRESENCE_STUB, 1
0x18002e7b6  jz      loc_18002E90B
0x18002e7bc  mov     rax, cs:off_180047A70
0x18002e7c3  lea     rdx, [rsp+1B0h+var_180]
0x18002e7c8  xor     r8d, r8d
0x18002e7cb  mov     [rsp+1B0h+var_180], 0
0x18002e7d4  lea     rcx, aRxcthreadpoolO_0; "RxcThreadPool_OnceInitWorker - failure"
0x18002e7db  mov     [rsp+1B0h+var_178], r14
0x18002e7e0  mov     [rsp+1B0h+var_170], 23Bh
0x18002e7e8  mov     [rsp+1B0h+var_16C], 0FFFFFFFFh
0x18002e7f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7f5  jmp     loc_18002E970
0x18002e7fa  mov     r14d, 20h ; ' '
0x18002e800  lea     rax, RxcThreadPool_ImmediateItem_ObjectDestructor
0x18002e807  mov     edx, r14d
0x18002e80a  mov     [rsp+1B0h+var_190], rax
0x18002e80f  lea     r9, RxcThreadPool_ImmediateItem_ObjectConstructor
0x18002e816  lea     rcx, stru_18008E6B0
0x18002e81d  lea     r8d, [r14+18h]
0x18002e821  call    Cache_Construct
0x18002e826  lea     rax, RxcThreadPool_PostponedItem_ObjectDestructor
0x18002e82d  mov     edx, r14d
0x18002e830  lea     r9, RxcThreadPool_PostponedItem_ObjectConstructor
0x18002e837  mov     [rsp+1B0h+var_190], rax
0x18002e83c  lea     r8d, [r14+48h]
0x18002e840  lea     rcx, stru_18008E6F0
0x18002e847  call    Cache_Construct
0x18002e84c  lea     rax, ptpp
0x18002e853  mov     [rsi], rax
0x18002e856  cmp     cs:NITS_PRESENCE_STUB, 1
0x18002e85e  jz      short loc_18002E8A2
0x18002e860  lea     rax, aAdminWmiWinomi_3; "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedu"...
0x18002e867  mov     [rsp+1B0h+var_180], 0
0x18002e870  mov     [rsp+1B0h+var_178], rax
0x18002e875  lea     rdx, [rsp+1B0h+var_180]
0x18002e87a  mov     rax, cs:off_180047A70
0x18002e881  lea     rcx, aRxcthreadpoolO; "RxcThreadPool_OnceInitWorker - success"
0x18002e888  xor     r8d, r8d
0x18002e88b  mov     [rsp+1B0h+var_170], 237h
0x18002e893  mov     [rsp+1B0h+var_16C], 0FFFFFFFFh
0x18002e89b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8a0  jmp     short loc_18002E907
0x18002e8a2  lea     rax, [rsp+1B0h+var_160]
0x18002e8a7  movups  xmm0, xmmword ptr [rbx]
0x18002e8aa  movups  xmm1, xmmword ptr [rbx+10h]
0x18002e8ae  movups  xmmword ptr [rax], xmm0
0x18002e8b1  movups  xmm0, xmmword ptr [rbx+20h]
0x18002e8b5  movups  xmmword ptr [rax+10h], xmm1
0x18002e8b9  movups  xmm1, xmmword ptr [rbx+30h]
0x18002e8bd  movups  xmmword ptr [rax+20h], xmm0
0x18002e8c1  movups  xmm0, xmmword ptr [rbx+40h]
0x18002e8c5  movups  xmmword ptr [rax+30h], xmm1
0x18002e8c9  movups  xmm1, xmmword ptr [rbx+50h]
0x18002e8cd  movups  xmmword ptr [rax+40h], xmm0
0x18002e8d1  movups  xmm0, xmmword ptr [rbx+60h]
0x18002e8d5  movups  xmmword ptr [rax+50h], xmm1
0x18002e8d9  movups  xmm1, xmmword ptr [rbx+70h]
0x18002e8dd  add     rbx, r13
0x18002e8e0  movups  xmmword ptr [rax+60h], xmm0
0x18002e8e4  movups  xmmword ptr [rax+70h], xmm1
0x18002e8e8  add     rax, r13
0x18002e8eb  sub     rdi, 1
0x18002e8ef  jnz     short loc_18002E8A7
0x18002e8f1  movups  xmm0, xmmword ptr [rbx]
0x18002e8f4  movups  xmm1, xmmword ptr [rbx+10h]
0x18002e8f8  movups  xmmword ptr [rax], xmm0
0x18002e8fb  movups  xmm0, xmmword ptr [rbx+20h]
0x18002e8ff  movups  xmmword ptr [rax+10h], xmm1
0x18002e903  movups  xmmword ptr [rax+20h], xmm0
0x18002e907  xor     eax, eax
0x18002e909  jmp     short loc_18002E973
0x18002e90b  lea     rcx, [rsp+1B0h+var_160]
0x18002e910  movups  xmm0, xmmword ptr [rbx]
0x18002e913  movups  xmm1, xmmword ptr [rbx+10h]
0x18002e917  movups  xmmword ptr [rcx], xmm0
0x18002e91a  movups  xmm0, xmmword ptr [rbx+20h]
0x18002e91e  movups  xmmword ptr [rcx+10h], xmm1
0x18002e922  movups  xmm1, xmmword ptr [rbx+30h]
0x18002e926  movups  xmmword ptr [rcx+20h], xmm0
0x18002e92a  movups  xmm0, xmmword ptr [rbx+40h]
0x18002e92e  movups  xmmword ptr [rcx+30h], xmm1
0x18002e932  movups  xmm1, xmmword ptr [rbx+50h]
0x18002e936  movups  xmmword ptr [rcx+40h], xmm0
0x18002e93a  movups  xmm0, xmmword ptr [rbx+60h]
0x18002e93e  movups  xmmword ptr [rcx+50h], xmm1
0x18002e942  movups  xmm1, xmmword ptr [rbx+70h]
0x18002e946  add     rbx, r13
0x18002e949  movups  xmmword ptr [rcx+60h], xmm0
0x18002e94d  movups  xmmword ptr [rcx+70h], xmm1
0x18002e951  add     rcx, r13
0x18002e954  sub     rdi, 1
0x18002e958  jnz     short loc_18002E910
0x18002e95a  movups  xmm0, xmmword ptr [rbx]
0x18002e95d  movups  xmm1, xmmword ptr [rbx+10h]
0x18002e961  movups  xmmword ptr [rcx], xmm0
0x18002e964  movups  xmm0, xmmword ptr [rbx+20h]
0x18002e968  movups  xmmword ptr [rcx+10h], xmm1
0x18002e96c  movups  xmmword ptr [rcx+20h], xmm0
0x18002e970  or      eax, 0FFFFFFFFh
0x18002e973  add     rsp, 188h
0x18002e97a  pop     r14
0x18002e97c  pop     r13
0x18002e97e  pop     rdi
0x18002e97f  pop     rsi
0x18002e980  pop     rbx
0x18002e981  pop     rbp
0x18002e982  retn
```
