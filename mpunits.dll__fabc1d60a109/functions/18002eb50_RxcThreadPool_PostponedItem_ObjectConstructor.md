# RxcThreadPool_PostponedItem_ObjectConstructor

- ea: `0x18002eb50`
- end: `0x18002ede7`
- name: `RxcThreadPool_PostponedItem_ObjectConstructor`
- size: `663`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002df9c`
- `0x18002eb50`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002ec45`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002ec45`

## string_xrefs

- `0x18002eb79`: `admin\wmi\winomi\mp\rxc\rxc.schedulers.threadpool.c`
- `0x18002eba1`: `RxcThreadPool_PostponedItem_ObjectConstructor`
- `0x18002ed4d`: `RxcThreadPool_PostponedItem_ObjectConstructor - success`
- `0x18002ec73`: `RxcThreadPool_PostponedItem_ObjectConstructor - failure`

## pseudocode

```c
__int64 __fastcall RxcThreadPool_PostponedItem_ObjectConstructor(_QWORD *pv)
{
  __int64 (__fastcall **v1)(); // rbx
  __int64 v2; // rsi
  __int64 (__fastcall **v4)(); // rcx
  _OWORD *v5; // rax
  __int64 v6; // rdx
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  PTP_TIMER ThreadpoolTimer; // rax
  _OWORD *v17; // rcx
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  _OWORD *v28; // rax
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int64 v38; // [rsp+20h] [rbp-E0h] BYREF
  const char *v39; // [rsp+28h] [rbp-D8h]
  int v40; // [rsp+30h] [rbp-D0h]
  int v41; // [rsp+34h] [rbp-CCh]
  _BYTE v42[352]; // [rsp+40h] [rbp-C0h] BYREF

  v1 = NITS_STUB;
  v2 = 2;
  if ( NITS_PRESENCE_STUB == 1 )
  {
    v5 = v42;
    v4 = NITS_STUB;
    v6 = 2;
    do
    {
      v7 = *((_OWORD *)v4 + 1);
      *v5 = *(_OWORD *)v4;
      v8 = *((_OWORD *)v4 + 2);
      v5[1] = v7;
      v9 = *((_OWORD *)v4 + 3);
      v5[2] = v8;
      v10 = *((_OWORD *)v4 + 4);
      v5[3] = v9;
      v11 = *((_OWORD *)v4 + 5);
      v5[4] = v10;
      v12 = *((_OWORD *)v4 + 6);
      v5[5] = v11;
      v13 = *((_OWORD *)v4 + 7);
      v4 += 16;
      v5[6] = v12;
      v5[7] = v13;
      v5 += 8;
      --v6;
    }
    while ( v6 );
    v14 = *((_OWORD *)v4 + 1);
    *v5 = *(_OWORD *)v4;
    v15 = *((_OWORD *)v4 + 2);
    v5[1] = v14;
    v5[2] = v15;
  }
  else
  {
    v38 = 0;
    v39 = "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedulers.threadpool.c";
    v40 = 397;
    v41 = -1;
    ((void (__fastcall *)(const wchar_t *, __int64 *, _QWORD))BufferPostNotificationTrapMethod)(
      L"RxcThreadPool_PostponedItem_ObjectConstructor",
      &v38,
      0);
  }
  pv[5] = RxcThreadPool_GetSingleton(v4);
  ThreadpoolTimer = CreateThreadpoolTimer(RxcThreadPool_PostponedItem_Worker, pv, 0);
  pv[6] = ThreadpoolTimer;
  if ( ThreadpoolTimer )
  {
    pv[9] = pv;
    pv[11] = RxcThreadPool_PostponedItem_Disposable_AddRef;
    pv[12] = RxcThreadPool_PostponedItem_Disposable_Release;
    pv[10] = RxcThreadPool_PostponedItem_Disposable_Dispose;
    if ( NITS_PRESENCE_STUB == 1 )
    {
      v28 = v42;
      do
      {
        v29 = *((_OWORD *)v1 + 1);
        *v28 = *(_OWORD *)v1;
        v30 = *((_OWORD *)v1 + 2);
        v28[1] = v29;
        v31 = *((_OWORD *)v1 + 3);
        v28[2] = v30;
        v32 = *((_OWORD *)v1 + 4);
        v28[3] = v31;
        v33 = *((_OWORD *)v1 + 5);
        v28[4] = v32;
        v34 = *((_OWORD *)v1 + 6);
        v28[5] = v33;
        v35 = *((_OWORD *)v1 + 7);
        v1 += 16;
        v28[6] = v34;
        v28[7] = v35;
        v28 += 8;
        --v2;
      }
      while ( v2 );
      v36 = *((_OWORD *)v1 + 1);
      *v28 = *(_OWORD *)v1;
      v37 = *((_OWORD *)v1 + 2);
      v28[1] = v36;
      v28[2] = v37;
    }
    else
    {
      v38 = 0;
      v39 = "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedulers.threadpool.c";
      v40 = 419;
      v41 = -1;
      ((void (__fastcall *)(const wchar_t *, __int64 *, _QWORD))BufferPostNotificationTrapMethod)(
        L"RxcThreadPool_PostponedItem_ObjectConstructor - success",
        &v38,
        0);
    }
    return 0;
  }
  else
  {
    if ( NITS_PRESENCE_STUB == 1 )
    {
      v17 = v42;
      do
      {
        v18 = *((_OWORD *)v1 + 1);
        *v17 = *(_OWORD *)v1;
        v19 = *((_OWORD *)v1 + 2);
        v17[1] = v18;
        v20 = *((_OWORD *)v1 + 3);
        v17[2] = v19;
        v21 = *((_OWORD *)v1 + 4);
        v17[3] = v20;
        v22 = *((_OWORD *)v1 + 5);
        v17[4] = v21;
        v23 = *((_OWORD *)v1 + 6);
        v17[5] = v22;
        v24 = *((_OWORD *)v1 + 7);
        v1 += 16;
        v17[6] = v23;
        v17[7] = v24;
        v17 += 8;
        --v2;
      }
      while ( v2 );
      v25 = *((_OWORD *)v1 + 1);
      *v17 = *(_OWORD *)v1;
      v26 = *((_OWORD *)v1 + 2);
      v17[1] = v25;
      v17[2] = v26;
    }
    else
    {
      v38 = 0;
      v39 = "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedulers.threadpool.c";
      v40 = 423;
      v41 = -1;
      ((void (__fastcall *)(const wchar_t *, __int64 *, _QWORD))BufferPostNotificationTrapMethod)(
        L"RxcThreadPool_PostponedItem_ObjectConstructor - failure",
        &v38,
        0);
    }
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x18002eb50  push    rbp
0x18002eb52  push    rbx
0x18002eb53  push    rsi
0x18002eb54  push    rdi
0x18002eb55  push    r13
0x18002eb57  push    r15
0x18002eb59  lea     rbp, [rsp-78h]
0x18002eb5e  sub     rsp, 178h
0x18002eb65  cmp     cs:NITS_PRESENCE_STUB, 1
0x18002eb6d  lea     rbx, NITS_STUB
0x18002eb74  mov     esi, 2
0x18002eb79  lea     r13, aAdminWmiWinomi_3; "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedu"...
0x18002eb80  mov     rdi, rcx
0x18002eb83  lea     r15d, [rsi+7Eh]
0x18002eb87  jz      short loc_18002EBC4
0x18002eb89  mov     rax, cs:off_180047A70
0x18002eb90  lea     rdx, [rsp+1A0h+var_180]
0x18002eb95  xor     r8d, r8d
0x18002eb98  mov     [rsp+1A0h+var_180], 0
0x18002eba1  lea     rcx, aRxcthreadpoolP; "RxcThreadPool_PostponedItem_ObjectConst"...
0x18002eba8  mov     [rsp+1A0h+var_178], r13
0x18002ebad  mov     [rsp+1A0h+var_170], 18Dh
0x18002ebb5  mov     [rsp+1A0h+var_16C], 0FFFFFFFFh
0x18002ebbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebc2  jmp     short loc_18002EC2F
0x18002ebc4  lea     rax, [rsp+1A0h+var_160]
0x18002ebc9  mov     rcx, rbx
0x18002ebcc  mov     rdx, rsi
0x18002ebcf  movups  xmm0, xmmword ptr [rcx]
0x18002ebd2  movups  xmm1, xmmword ptr [rcx+10h]
0x18002ebd6  movups  xmmword ptr [rax], xmm0
0x18002ebd9  movups  xmm0, xmmword ptr [rcx+20h]
0x18002ebdd  movups  xmmword ptr [rax+10h], xmm1
0x18002ebe1  movups  xmm1, xmmword ptr [rcx+30h]
0x18002ebe5  movups  xmmword ptr [rax+20h], xmm0
0x18002ebe9  movups  xmm0, xmmword ptr [rcx+40h]
0x18002ebed  movups  xmmword ptr [rax+30h], xmm1
0x18002ebf1  movups  xmm1, xmmword ptr [rcx+50h]
0x18002ebf5  movups  xmmword ptr [rax+40h], xmm0
0x18002ebf9  movups  xmm0, xmmword ptr [rcx+60h]
0x18002ebfd  movups  xmmword ptr [rax+50h], xmm1
0x18002ec01  movups  xmm1, xmmword ptr [rcx+70h]
0x18002ec05  add     rcx, r15
0x18002ec08  movups  xmmword ptr [rax+60h], xmm0
0x18002ec0c  movups  xmmword ptr [rax+70h], xmm1
0x18002ec10  add     rax, r15
0x18002ec13  sub     rdx, 1
0x18002ec17  jnz     short loc_18002EBCF
0x18002ec19  movups  xmm0, xmmword ptr [rcx]
0x18002ec1c  movups  xmm1, xmmword ptr [rcx+10h]
0x18002ec20  movups  xmmword ptr [rax], xmm0
0x18002ec23  movups  xmm0, xmmword ptr [rcx+20h]
0x18002ec27  movups  xmmword ptr [rax+10h], xmm1
0x18002ec2b  movups  xmmword ptr [rax+20h], xmm0
0x18002ec2f  call    RxcThreadPool_GetSingleton
0x18002ec34  xor     r8d, r8d; pcbe
0x18002ec37  mov     [rdi+28h], rax
0x18002ec3b  mov     rdx, rdi; pv
0x18002ec3e  lea     rcx, RxcThreadPool_PostponedItem_Worker; pfnti
0x18002ec45  call    cs:__imp_CreateThreadpoolTimer
0x18002ec4b  mov     [rdi+30h], rax
0x18002ec4f  test    rax, rax
0x18002ec52  jnz     loc_18002ED06
0x18002ec58  cmp     cs:NITS_PRESENCE_STUB, 1
0x18002ec60  jz      short loc_18002EC99
0x18002ec62  mov     [rsp+1A0h+var_180], rax
0x18002ec67  lea     rdx, [rsp+1A0h+var_180]
0x18002ec6c  mov     rax, cs:off_180047A70
0x18002ec73  lea     rcx, aRxcthreadpoolP_5; "RxcThreadPool_PostponedItem_ObjectConst"...
0x18002ec7a  xor     r8d, r8d
0x18002ec7d  mov     [rsp+1A0h+var_178], r13
0x18002ec82  mov     [rsp+1A0h+var_170], 1A7h
0x18002ec8a  mov     [rsp+1A0h+var_16C], 0FFFFFFFFh
0x18002ec92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec97  jmp     short loc_18002ECFE
0x18002ec99  lea     rcx, [rsp+1A0h+var_160]
0x18002ec9e  movups  xmm0, xmmword ptr [rbx]
0x18002eca1  movups  xmm1, xmmword ptr [rbx+10h]
0x18002eca5  movups  xmmword ptr [rcx], xmm0
0x18002eca8  movups  xmm0, xmmword ptr [rbx+20h]
0x18002ecac  movups  xmmword ptr [rcx+10h], xmm1
0x18002ecb0  movups  xmm1, xmmword ptr [rbx+30h]
0x18002ecb4  movups  xmmword ptr [rcx+20h], xmm0
0x18002ecb8  movups  xmm0, xmmword ptr [rbx+40h]
0x18002ecbc  movups  xmmword ptr [rcx+30h], xmm1
0x18002ecc0  movups  xmm1, xmmword ptr [rbx+50h]
0x18002ecc4  movups  xmmword ptr [rcx+40h], xmm0
0x18002ecc8  movups  xmm0, xmmword ptr [rbx+60h]
0x18002eccc  movups  xmmword ptr [rcx+50h], xmm1
0x18002ecd0  movups  xmm1, xmmword ptr [rbx+70h]
0x18002ecd4  add     rbx, r15
0x18002ecd7  movups  xmmword ptr [rcx+60h], xmm0
0x18002ecdb  movups  xmmword ptr [rcx+70h], xmm1
0x18002ecdf  add     rcx, r15
0x18002ece2  sub     rsi, 1
0x18002ece6  jnz     short loc_18002EC9E
0x18002ece8  movups  xmm0, xmmword ptr [rbx]
0x18002eceb  movups  xmm1, xmmword ptr [rbx+10h]
0x18002ecef  movups  xmmword ptr [rcx], xmm0
0x18002ecf2  movups  xmm0, xmmword ptr [rbx+20h]
0x18002ecf6  movups  xmmword ptr [rcx+10h], xmm1
0x18002ecfa  movups  xmmword ptr [rcx+20h], xmm0
0x18002ecfe  or      eax, 0FFFFFFFFh
0x18002ed01  jmp     loc_18002EDD7
0x18002ed06  lea     rax, RxcThreadPool_PostponedItem_Disposable_AddRef
0x18002ed0d  mov     [rdi+48h], rdi
0x18002ed11  mov     [rdi+58h], rax
0x18002ed15  lea     rax, RxcThreadPool_PostponedItem_Disposable_Release
0x18002ed1c  mov     [rdi+60h], rax
0x18002ed20  lea     rax, RxcThreadPool_PostponedItem_Disposable_Dispose
0x18002ed27  mov     [rdi+50h], rax
0x18002ed2b  cmp     cs:NITS_PRESENCE_STUB, 1
0x18002ed33  jz      short loc_18002ED70
0x18002ed35  mov     rax, cs:off_180047A70
0x18002ed3c  lea     rdx, [rsp+1A0h+var_180]
0x18002ed41  xor     r8d, r8d
0x18002ed44  mov     [rsp+1A0h+var_180], 0
0x18002ed4d  lea     rcx, aRxcthreadpoolP_3; "RxcThreadPool_PostponedItem_ObjectConst"...
0x18002ed54  mov     [rsp+1A0h+var_178], r13
0x18002ed59  mov     [rsp+1A0h+var_170], 1A3h
0x18002ed61  mov     [rsp+1A0h+var_16C], 0FFFFFFFFh
0x18002ed69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed6e  jmp     short loc_18002EDD5
0x18002ed70  lea     rax, [rsp+1A0h+var_160]
0x18002ed75  movups  xmm0, xmmword ptr [rbx]
0x18002ed78  movups  xmm1, xmmword ptr [rbx+10h]
0x18002ed7c  movups  xmmword ptr [rax], xmm0
0x18002ed7f  movups  xmm0, xmmword ptr [rbx+20h]
0x18002ed83  movups  xmmword ptr [rax+10h], xmm1
0x18002ed87  movups  xmm1, xmmword ptr [rbx+30h]
0x18002ed8b  movups  xmmword ptr [rax+20h], xmm0
0x18002ed8f  movups  xmm0, xmmword ptr [rbx+40h]
0x18002ed93  movups  xmmword ptr [rax+30h], xmm1
0x18002ed97  movups  xmm1, xmmword ptr [rbx+50h]
0x18002ed9b  movups  xmmword ptr [rax+40h], xmm0
0x18002ed9f  movups  xmm0, xmmword ptr [rbx+60h]
0x18002eda3  movups  xmmword ptr [rax+50h], xmm1
0x18002eda7  movups  xmm1, xmmword ptr [rbx+70h]
0x18002edab  add     rbx, r15
0x18002edae  movups  xmmword ptr [rax+60h], xmm0
0x18002edb2  movups  xmmword ptr [rax+70h], xmm1
0x18002edb6  add     rax, r15
0x18002edb9  sub     rsi, 1
0x18002edbd  jnz     short loc_18002ED75
0x18002edbf  movups  xmm0, xmmword ptr [rbx]
0x18002edc2  movups  xmm1, xmmword ptr [rbx+10h]
0x18002edc6  movups  xmmword ptr [rax], xmm0
0x18002edc9  movups  xmm0, xmmword ptr [rbx+20h]
0x18002edcd  movups  xmmword ptr [rax+10h], xmm1
0x18002edd1  movups  xmmword ptr [rax+20h], xmm0
0x18002edd5  xor     eax, eax
0x18002edd7  add     rsp, 178h
0x18002edde  pop     r15
0x18002ede0  pop     r13
0x18002ede2  pop     rdi
0x18002ede3  pop     rsi
0x18002ede4  pop     rbx
0x18002ede5  pop     rbp
0x18002ede6  retn
```
