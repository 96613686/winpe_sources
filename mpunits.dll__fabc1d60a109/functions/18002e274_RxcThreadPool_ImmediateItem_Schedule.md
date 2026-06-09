# RxcThreadPool_ImmediateItem_Schedule

- ea: `0x18002e274`
- end: `0x18002e532`
- name: `RxcThreadPool_ImmediateItem_Schedule`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002f390`

## callees

- `0x180008d40`
- `0x18002dce4`
- `0x18002df9c`
- `0x18002e274`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002e392`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002e392`

## string_xrefs

- `0x18002e29f`: `admin\wmi\winomi\mp\rxc\rxc.schedulers.threadpool.c`
- `0x18002e3a2`: `admin\wmi\winomi\mp\rxc\rxc.schedulers.threadpool.c`
- `0x18002e474`: `admin\wmi\winomi\mp\rxc\rxc.schedulers.threadpool.c`
- `0x18002e2c5`: `RxcThreadPool_ImmediateItem_Schedule`
- `0x18002e3c3`: `RxcThreadPool_ImmediateItem_Schedule - success`
- `0x18002e495`: `RxcThreadPool_ImmediateItem_Schedule - failure`

## pseudocode

```c
__int64 __fastcall RxcThreadPool_ImmediateItem_Schedule(__int64 a1, void (__fastcall *a2)(__int64), __int64 a3)
{
  __int64 (__fastcall **v3)(); // rbx
  __int64 v4; // rdi
  __int64 (__fastcall **v8)(); // rcx
  _OWORD *v9; // rax
  __int64 v10; // rdx
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int64 Singleton; // rax
  __int64 Object; // rax
  __int64 v22; // rsi
  _OWORD *v23; // rax
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  _OWORD *v34; // rax
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  __int64 v44; // [rsp+20h] [rbp-E0h] BYREF
  const char *v45; // [rsp+28h] [rbp-D8h]
  int v46; // [rsp+30h] [rbp-D0h]
  int v47; // [rsp+34h] [rbp-CCh]
  _BYTE v48[352]; // [rsp+40h] [rbp-C0h] BYREF

  v3 = NITS_STUB;
  v4 = 2;
  if ( NITS_PRESENCE_STUB == 1 )
  {
    v9 = v48;
    v8 = NITS_STUB;
    v10 = 2;
    do
    {
      v11 = *((_OWORD *)v8 + 1);
      *v9 = *(_OWORD *)v8;
      v12 = *((_OWORD *)v8 + 2);
      v9[1] = v11;
      v13 = *((_OWORD *)v8 + 3);
      v9[2] = v12;
      v14 = *((_OWORD *)v8 + 4);
      v9[3] = v13;
      v15 = *((_OWORD *)v8 + 5);
      v9[4] = v14;
      v16 = *((_OWORD *)v8 + 6);
      v9[5] = v15;
      v17 = *((_OWORD *)v8 + 7);
      v8 += 16;
      v9[6] = v16;
      v9[7] = v17;
      v9 += 8;
      --v10;
    }
    while ( v10 );
    v18 = *((_OWORD *)v8 + 1);
    *v9 = *(_OWORD *)v8;
    v19 = *((_OWORD *)v8 + 2);
    v9[1] = v18;
    v9[2] = v19;
  }
  else
  {
    v45 = "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedulers.threadpool.c";
    v44 = 0;
    v46 = 261;
    v47 = -1;
    ((void (__fastcall *)(const wchar_t *, __int64 *, _QWORD))BufferPostNotificationTrapMethod)(
      L"RxcThreadPool_ImmediateItem_Schedule",
      &v44,
      0);
  }
  Singleton = RxcThreadPool_GetSingleton(v8);
  if ( Singleton && (Object = Cache_GetObject(Singleton + 16), (v22 = Object) != 0) )
  {
    RxcThreadPool_BaseItem_Construct(Object, a1, a2, a3, v44);
    SubmitThreadpoolWork(*(PTP_WORK *)(v22 + 48));
    if ( NITS_PRESENCE_STUB == 1 )
    {
      v23 = v48;
      do
      {
        v24 = *((_OWORD *)v3 + 1);
        *v23 = *(_OWORD *)v3;
        v25 = *((_OWORD *)v3 + 2);
        v23[1] = v24;
        v26 = *((_OWORD *)v3 + 3);
        v23[2] = v25;
        v27 = *((_OWORD *)v3 + 4);
        v23[3] = v26;
        v28 = *((_OWORD *)v3 + 5);
        v23[4] = v27;
        v29 = *((_OWORD *)v3 + 6);
        v23[5] = v28;
        v30 = *((_OWORD *)v3 + 7);
        v3 += 16;
        v23[6] = v29;
        v23[7] = v30;
        v23 += 8;
        --v4;
      }
      while ( v4 );
      v31 = *((_OWORD *)v3 + 1);
      *v23 = *(_OWORD *)v3;
      v32 = *((_OWORD *)v3 + 2);
      v23[1] = v31;
      v23[2] = v32;
    }
    else
    {
      v44 = 0;
      v45 = "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedulers.threadpool.c";
      v46 = 273;
      v47 = -1;
      ((void (__fastcall *)(const wchar_t *, __int64 *, _QWORD))BufferPostNotificationTrapMethod)(
        L"RxcThreadPool_ImmediateItem_Schedule - success",
        &v44,
        0);
    }
    return 0;
  }
  else
  {
    if ( a2 )
      a2(a3);
    if ( NITS_PRESENCE_STUB == 1 )
    {
      v34 = v48;
      do
      {
        v35 = *((_OWORD *)v3 + 1);
        *v34 = *(_OWORD *)v3;
        v36 = *((_OWORD *)v3 + 2);
        v34[1] = v35;
        v37 = *((_OWORD *)v3 + 3);
        v34[2] = v36;
        v38 = *((_OWORD *)v3 + 4);
        v34[3] = v37;
        v39 = *((_OWORD *)v3 + 5);
        v34[4] = v38;
        v40 = *((_OWORD *)v3 + 6);
        v34[5] = v39;
        v41 = *((_OWORD *)v3 + 7);
        v3 += 16;
        v34[6] = v40;
        v34[7] = v41;
        v34 += 8;
        --v4;
      }
      while ( v4 );
      v42 = *((_OWORD *)v3 + 1);
      *v34 = *(_OWORD *)v3;
      v43 = *((_OWORD *)v3 + 2);
      v34[1] = v42;
      v34[2] = v43;
    }
    else
    {
      v44 = 0;
      v45 = "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedulers.threadpool.c";
      v46 = 280;
      v47 = -1;
      ((void (__fastcall *)(const wchar_t *, __int64 *, _QWORD))BufferPostNotificationTrapMethod)(
        L"RxcThreadPool_ImmediateItem_Schedule - failure",
        &v44,
        0);
    }
    return 27;
  }
}

```

## disassembly

```asm
0x18002e274  push    rbp
0x18002e276  push    rbx
0x18002e277  push    rsi
0x18002e278  push    rdi
0x18002e279  push    r12
0x18002e27b  push    r14
0x18002e27d  push    r15
0x18002e27f  lea     rbp, [rsp-70h]
0x18002e284  sub     rsp, 170h
0x18002e28b  cmp     cs:NITS_PRESENCE_STUB, 1
0x18002e293  lea     rbx, NITS_STUB
0x18002e29a  mov     edi, 2
0x18002e29f  lea     rax, aAdminWmiWinomi_3; "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedu"...
0x18002e2a6  mov     r15, r8
0x18002e2a9  mov     r14, rdx
0x18002e2ac  mov     r12, rcx
0x18002e2af  lea     esi, [rdi+7Eh]
0x18002e2b2  jz      short loc_18002E2EF
0x18002e2b4  mov     [rsp+1A0h+var_178], rax
0x18002e2b9  lea     rdx, [rsp+1A0h+var_180]
0x18002e2be  mov     rax, cs:off_180047A70
0x18002e2c5  lea     rcx, aRxcthreadpoolI_1; "RxcThreadPool_ImmediateItem_Schedule"
0x18002e2cc  xor     r8d, r8d
0x18002e2cf  mov     [rsp+1A0h+var_180], 0
0x18002e2d8  mov     [rsp+1A0h+var_170], 105h
0x18002e2e0  mov     [rsp+1A0h+var_16C], 0FFFFFFFFh
0x18002e2e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2ed  jmp     short loc_18002E35A
0x18002e2ef  lea     rax, [rsp+1A0h+var_160]
0x18002e2f4  mov     rcx, rbx
0x18002e2f7  mov     rdx, rdi
0x18002e2fa  movups  xmm0, xmmword ptr [rcx]
0x18002e2fd  movups  xmm1, xmmword ptr [rcx+10h]
0x18002e301  movups  xmmword ptr [rax], xmm0
0x18002e304  movups  xmm0, xmmword ptr [rcx+20h]
0x18002e308  movups  xmmword ptr [rax+10h], xmm1
0x18002e30c  movups  xmm1, xmmword ptr [rcx+30h]
0x18002e310  movups  xmmword ptr [rax+20h], xmm0
0x18002e314  movups  xmm0, xmmword ptr [rcx+40h]
0x18002e318  movups  xmmword ptr [rax+30h], xmm1
0x18002e31c  movups  xmm1, xmmword ptr [rcx+50h]
0x18002e320  movups  xmmword ptr [rax+40h], xmm0
0x18002e324  movups  xmm0, xmmword ptr [rcx+60h]
0x18002e328  movups  xmmword ptr [rax+50h], xmm1
0x18002e32c  movups  xmm1, xmmword ptr [rcx+70h]
0x18002e330  add     rcx, rsi
0x18002e333  movups  xmmword ptr [rax+60h], xmm0
0x18002e337  movups  xmmword ptr [rax+70h], xmm1
0x18002e33b  add     rax, rsi
0x18002e33e  sub     rdx, 1
0x18002e342  jnz     short loc_18002E2FA
0x18002e344  movups  xmm0, xmmword ptr [rcx]
0x18002e347  movups  xmm1, xmmword ptr [rcx+10h]
0x18002e34b  movups  xmmword ptr [rax], xmm0
0x18002e34e  movups  xmm0, xmmword ptr [rcx+20h]
0x18002e352  movups  xmmword ptr [rax+10h], xmm1
0x18002e356  movups  xmmword ptr [rax+20h], xmm0
0x18002e35a  call    RxcThreadPool_GetSingleton
0x18002e35f  test    rax, rax
0x18002e362  jz      loc_18002E45A
0x18002e368  lea     rcx, [rax+10h]
0x18002e36c  call    Cache_GetObject
0x18002e371  mov     rsi, rax
0x18002e374  test    rax, rax
0x18002e377  jz      loc_18002E455
0x18002e37d  mov     r9, r15
0x18002e380  mov     r8, r14
0x18002e383  mov     rdx, r12
0x18002e386  mov     rcx, rax
0x18002e389  call    RxcThreadPool_BaseItem_Construct
0x18002e38e  mov     rcx, [rsi+30h]; pwk
0x18002e392  call    cs:__imp_SubmitThreadpoolWork
0x18002e398  cmp     cs:NITS_PRESENCE_STUB, 1
0x18002e3a0  jz      short loc_18002E3E4
0x18002e3a2  lea     rax, aAdminWmiWinomi_3; "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedu"...
0x18002e3a9  mov     [rsp+1A0h+var_180], 0
0x18002e3b2  mov     [rsp+1A0h+var_178], rax
0x18002e3b7  lea     rdx, [rsp+1A0h+var_180]
0x18002e3bc  mov     rax, cs:off_180047A70
0x18002e3c3  lea     rcx, aRxcthreadpoolI_5; "RxcThreadPool_ImmediateItem_Schedule - "...
0x18002e3ca  xor     r8d, r8d
0x18002e3cd  mov     [rsp+1A0h+var_170], 111h
0x18002e3d5  mov     [rsp+1A0h+var_16C], 0FFFFFFFFh
0x18002e3dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3e2  jmp     short loc_18002E44E
0x18002e3e4  lea     rax, [rsp+1A0h+var_160]
0x18002e3e9  mov     ecx, 80h
0x18002e3ee  movups  xmm0, xmmword ptr [rbx]
0x18002e3f1  movups  xmm1, xmmword ptr [rbx+10h]
0x18002e3f5  movups  xmmword ptr [rax], xmm0
0x18002e3f8  movups  xmm0, xmmword ptr [rbx+20h]
0x18002e3fc  movups  xmmword ptr [rax+10h], xmm1
0x18002e400  movups  xmm1, xmmword ptr [rbx+30h]
0x18002e404  movups  xmmword ptr [rax+20h], xmm0
0x18002e408  movups  xmm0, xmmword ptr [rbx+40h]
0x18002e40c  movups  xmmword ptr [rax+30h], xmm1
0x18002e410  movups  xmm1, xmmword ptr [rbx+50h]
0x18002e414  movups  xmmword ptr [rax+40h], xmm0
0x18002e418  movups  xmm0, xmmword ptr [rbx+60h]
0x18002e41c  movups  xmmword ptr [rax+50h], xmm1
0x18002e420  movups  xmm1, xmmword ptr [rbx+70h]
0x18002e424  add     rbx, rcx
0x18002e427  movups  xmmword ptr [rax+60h], xmm0
0x18002e42b  movups  xmmword ptr [rax+70h], xmm1
0x18002e42f  add     rax, rcx
0x18002e432  sub     rdi, 1
0x18002e436  jnz     short loc_18002E3EE
0x18002e438  movups  xmm0, xmmword ptr [rbx]
0x18002e43b  movups  xmm1, xmmword ptr [rbx+10h]
0x18002e43f  movups  xmmword ptr [rax], xmm0
0x18002e442  movups  xmm0, xmmword ptr [rbx+20h]
0x18002e446  movups  xmmword ptr [rax+10h], xmm1
0x18002e44a  movups  xmmword ptr [rax+20h], xmm0
0x18002e44e  xor     eax, eax
0x18002e450  jmp     loc_18002E520
0x18002e455  mov     esi, 80h
0x18002e45a  test    r14, r14
0x18002e45d  jz      short loc_18002E46A
0x18002e45f  mov     rcx, r15
0x18002e462  mov     rax, r14
0x18002e465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e46a  cmp     cs:NITS_PRESENCE_STUB, 1
0x18002e472  jz      short loc_18002E4B6
0x18002e474  lea     rax, aAdminWmiWinomi_3; "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedu"...
0x18002e47b  mov     [rsp+1A0h+var_180], 0
0x18002e484  mov     [rsp+1A0h+var_178], rax
0x18002e489  lea     rdx, [rsp+1A0h+var_180]
0x18002e48e  mov     rax, cs:off_180047A70
0x18002e495  lea     rcx, aRxcthreadpoolI_0; "RxcThreadPool_ImmediateItem_Schedule - "...
0x18002e49c  xor     r8d, r8d
0x18002e49f  mov     [rsp+1A0h+var_170], 118h
0x18002e4a7  mov     [rsp+1A0h+var_16C], 0FFFFFFFFh
0x18002e4af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e4b4  jmp     short loc_18002E51B
0x18002e4b6  lea     rax, [rsp+1A0h+var_160]
0x18002e4bb  movups  xmm0, xmmword ptr [rbx]
0x18002e4be  movups  xmm1, xmmword ptr [rbx+10h]
0x18002e4c2  movups  xmmword ptr [rax], xmm0
0x18002e4c5  movups  xmm0, xmmword ptr [rbx+20h]
0x18002e4c9  movups  xmmword ptr [rax+10h], xmm1
0x18002e4cd  movups  xmm1, xmmword ptr [rbx+30h]
0x18002e4d1  movups  xmmword ptr [rax+20h], xmm0
0x18002e4d5  movups  xmm0, xmmword ptr [rbx+40h]
0x18002e4d9  movups  xmmword ptr [rax+30h], xmm1
0x18002e4dd  movups  xmm1, xmmword ptr [rbx+50h]
0x18002e4e1  movups  xmmword ptr [rax+40h], xmm0
0x18002e4e5  movups  xmm0, xmmword ptr [rbx+60h]
0x18002e4e9  movups  xmmword ptr [rax+50h], xmm1
0x18002e4ed  movups  xmm1, xmmword ptr [rbx+70h]
0x18002e4f1  add     rbx, rsi
0x18002e4f4  movups  xmmword ptr [rax+60h], xmm0
0x18002e4f8  movups  xmmword ptr [rax+70h], xmm1
0x18002e4fc  add     rax, rsi
0x18002e4ff  sub     rdi, 1
0x18002e503  jnz     short loc_18002E4BB
0x18002e505  movups  xmm0, xmmword ptr [rbx]
0x18002e508  movups  xmm1, xmmword ptr [rbx+10h]
0x18002e50c  movups  xmmword ptr [rax], xmm0
0x18002e50f  movups  xmm0, xmmword ptr [rbx+20h]
0x18002e513  movups  xmmword ptr [rax+10h], xmm1
0x18002e517  movups  xmmword ptr [rax+20h], xmm0
0x18002e51b  mov     eax, 1Bh
0x18002e520  add     rsp, 170h
0x18002e527  pop     r15
0x18002e529  pop     r14
0x18002e52b  pop     r12
0x18002e52d  pop     rdi
0x18002e52e  pop     rsi
0x18002e52f  pop     rbx
0x18002e530  pop     rbp
0x18002e531  retn
```
