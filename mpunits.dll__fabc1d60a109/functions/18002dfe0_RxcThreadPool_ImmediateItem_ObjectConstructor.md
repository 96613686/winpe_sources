# RxcThreadPool_ImmediateItem_ObjectConstructor

- ea: `0x18002dfe0`
- end: `0x18002e252`
- name: `RxcThreadPool_ImmediateItem_ObjectConstructor`
- size: `626`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002df9c`
- `0x18002dfe0`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002e0d5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002e0d5`

## string_xrefs

- `0x18002e009`: `admin\wmi\winomi\mp\rxc\rxc.schedulers.threadpool.c`
- `0x18002e031`: `RxcThreadPool_ImmediateItem_ObjectConstructor`
- `0x18002e1b8`: `RxcThreadPool_ImmediateItem_ObjectConstructor - success`
- `0x18002e103`: `RxcThreadPool_ImmediateItem_ObjectConstructor - failure`

## pseudocode

```c
__int64 __fastcall RxcThreadPool_ImmediateItem_ObjectConstructor(_QWORD *pv)
{
  __int64 (__fastcall **v1)(); // rbx
  __int64 v2; // rdi
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
  PTP_WORK ThreadpoolWork; // rax
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
    v40 = 225;
    v41 = -1;
    ((void (__fastcall *)(const wchar_t *, __int64 *, _QWORD))BufferPostNotificationTrapMethod)(
      L"RxcThreadPool_ImmediateItem_ObjectConstructor",
      &v38,
      0);
  }
  pv[5] = RxcThreadPool_GetSingleton(v4);
  ThreadpoolWork = CreateThreadpoolWork(RxcThreadPool_ImmediateItem_Worker, pv, 0);
  pv[6] = ThreadpoolWork;
  if ( ThreadpoolWork )
  {
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
      v40 = 238;
      v41 = -1;
      ((void (__fastcall *)(const wchar_t *, __int64 *, _QWORD))BufferPostNotificationTrapMethod)(
        L"RxcThreadPool_ImmediateItem_ObjectConstructor - success",
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
      v40 = 242;
      v41 = -1;
      ((void (__fastcall *)(const wchar_t *, __int64 *, _QWORD))BufferPostNotificationTrapMethod)(
        L"RxcThreadPool_ImmediateItem_ObjectConstructor - failure",
        &v38,
        0);
    }
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x18002dfe0  push    rbp
0x18002dfe2  push    rbx
0x18002dfe3  push    rsi
0x18002dfe4  push    rdi
0x18002dfe5  push    r13
0x18002dfe7  push    r15
0x18002dfe9  lea     rbp, [rsp-78h]
0x18002dfee  sub     rsp, 178h
0x18002dff5  cmp     cs:NITS_PRESENCE_STUB, 1
0x18002dffd  lea     rbx, NITS_STUB
0x18002e004  mov     edi, 2
0x18002e009  lea     r13, aAdminWmiWinomi_3; "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedu"...
0x18002e010  mov     rsi, rcx
0x18002e013  lea     r15d, [rdi+7Eh]
0x18002e017  jz      short loc_18002E054
0x18002e019  mov     rax, cs:off_180047A70
0x18002e020  lea     rdx, [rsp+1A0h+var_180]
0x18002e025  xor     r8d, r8d
0x18002e028  mov     [rsp+1A0h+var_180], 0
0x18002e031  lea     rcx, aRxcthreadpoolI; "RxcThreadPool_ImmediateItem_ObjectConst"...
0x18002e038  mov     [rsp+1A0h+var_178], r13
0x18002e03d  mov     [rsp+1A0h+var_170], 0E1h
0x18002e045  mov     [rsp+1A0h+var_16C], 0FFFFFFFFh
0x18002e04d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e052  jmp     short loc_18002E0BF
0x18002e054  lea     rax, [rsp+1A0h+var_160]
0x18002e059  mov     rcx, rbx
0x18002e05c  mov     rdx, rdi
0x18002e05f  movups  xmm0, xmmword ptr [rcx]
0x18002e062  movups  xmm1, xmmword ptr [rcx+10h]
0x18002e066  movups  xmmword ptr [rax], xmm0
0x18002e069  movups  xmm0, xmmword ptr [rcx+20h]
0x18002e06d  movups  xmmword ptr [rax+10h], xmm1
0x18002e071  movups  xmm1, xmmword ptr [rcx+30h]
0x18002e075  movups  xmmword ptr [rax+20h], xmm0
0x18002e079  movups  xmm0, xmmword ptr [rcx+40h]
0x18002e07d  movups  xmmword ptr [rax+30h], xmm1
0x18002e081  movups  xmm1, xmmword ptr [rcx+50h]
0x18002e085  movups  xmmword ptr [rax+40h], xmm0
0x18002e089  movups  xmm0, xmmword ptr [rcx+60h]
0x18002e08d  movups  xmmword ptr [rax+50h], xmm1
0x18002e091  movups  xmm1, xmmword ptr [rcx+70h]
0x18002e095  add     rcx, r15
0x18002e098  movups  xmmword ptr [rax+60h], xmm0
0x18002e09c  movups  xmmword ptr [rax+70h], xmm1
0x18002e0a0  add     rax, r15
0x18002e0a3  sub     rdx, 1
0x18002e0a7  jnz     short loc_18002E05F
0x18002e0a9  movups  xmm0, xmmword ptr [rcx]
0x18002e0ac  movups  xmm1, xmmword ptr [rcx+10h]
0x18002e0b0  movups  xmmword ptr [rax], xmm0
0x18002e0b3  movups  xmm0, xmmword ptr [rcx+20h]
0x18002e0b7  movups  xmmword ptr [rax+10h], xmm1
0x18002e0bb  movups  xmmword ptr [rax+20h], xmm0
0x18002e0bf  call    RxcThreadPool_GetSingleton
0x18002e0c4  xor     r8d, r8d; pcbe
0x18002e0c7  mov     [rsi+28h], rax
0x18002e0cb  mov     rdx, rsi; pv
0x18002e0ce  lea     rcx, RxcThreadPool_ImmediateItem_Worker; pfnwk
0x18002e0d5  call    cs:__imp_CreateThreadpoolWork
0x18002e0db  mov     [rsi+30h], rax
0x18002e0df  test    rax, rax
0x18002e0e2  jnz     loc_18002E196
0x18002e0e8  cmp     cs:NITS_PRESENCE_STUB, 1
0x18002e0f0  jz      short loc_18002E129
0x18002e0f2  mov     [rsp+1A0h+var_180], rax
0x18002e0f7  lea     rdx, [rsp+1A0h+var_180]
0x18002e0fc  mov     rax, cs:off_180047A70
0x18002e103  lea     rcx, aRxcthreadpoolI_2; "RxcThreadPool_ImmediateItem_ObjectConst"...
0x18002e10a  xor     r8d, r8d
0x18002e10d  mov     [rsp+1A0h+var_178], r13
0x18002e112  mov     [rsp+1A0h+var_170], 0F2h
0x18002e11a  mov     [rsp+1A0h+var_16C], 0FFFFFFFFh
0x18002e122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e127  jmp     short loc_18002E18E
0x18002e129  lea     rcx, [rsp+1A0h+var_160]
0x18002e12e  movups  xmm0, xmmword ptr [rbx]
0x18002e131  movups  xmm1, xmmword ptr [rbx+10h]
0x18002e135  movups  xmmword ptr [rcx], xmm0
0x18002e138  movups  xmm0, xmmword ptr [rbx+20h]
0x18002e13c  movups  xmmword ptr [rcx+10h], xmm1
0x18002e140  movups  xmm1, xmmword ptr [rbx+30h]
0x18002e144  movups  xmmword ptr [rcx+20h], xmm0
0x18002e148  movups  xmm0, xmmword ptr [rbx+40h]
0x18002e14c  movups  xmmword ptr [rcx+30h], xmm1
0x18002e150  movups  xmm1, xmmword ptr [rbx+50h]
0x18002e154  movups  xmmword ptr [rcx+40h], xmm0
0x18002e158  movups  xmm0, xmmword ptr [rbx+60h]
0x18002e15c  movups  xmmword ptr [rcx+50h], xmm1
0x18002e160  movups  xmm1, xmmword ptr [rbx+70h]
0x18002e164  add     rbx, r15
0x18002e167  movups  xmmword ptr [rcx+60h], xmm0
0x18002e16b  movups  xmmword ptr [rcx+70h], xmm1
0x18002e16f  add     rcx, r15
0x18002e172  sub     rdi, 1
0x18002e176  jnz     short loc_18002E12E
0x18002e178  movups  xmm0, xmmword ptr [rbx]
0x18002e17b  movups  xmm1, xmmword ptr [rbx+10h]
0x18002e17f  movups  xmmword ptr [rcx], xmm0
0x18002e182  movups  xmm0, xmmword ptr [rbx+20h]
0x18002e186  movups  xmmword ptr [rcx+10h], xmm1
0x18002e18a  movups  xmmword ptr [rcx+20h], xmm0
0x18002e18e  or      eax, 0FFFFFFFFh
0x18002e191  jmp     loc_18002E242
0x18002e196  cmp     cs:NITS_PRESENCE_STUB, 1
0x18002e19e  jz      short loc_18002E1DB
0x18002e1a0  mov     rax, cs:off_180047A70
0x18002e1a7  lea     rdx, [rsp+1A0h+var_180]
0x18002e1ac  xor     r8d, r8d
0x18002e1af  mov     [rsp+1A0h+var_180], 0
0x18002e1b8  lea     rcx, aRxcthreadpoolI_4; "RxcThreadPool_ImmediateItem_ObjectConst"...
0x18002e1bf  mov     [rsp+1A0h+var_178], r13
0x18002e1c4  mov     [rsp+1A0h+var_170], 0EEh
0x18002e1cc  mov     [rsp+1A0h+var_16C], 0FFFFFFFFh
0x18002e1d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e1d9  jmp     short loc_18002E240
0x18002e1db  lea     rax, [rsp+1A0h+var_160]
0x18002e1e0  movups  xmm0, xmmword ptr [rbx]
0x18002e1e3  movups  xmm1, xmmword ptr [rbx+10h]
0x18002e1e7  movups  xmmword ptr [rax], xmm0
0x18002e1ea  movups  xmm0, xmmword ptr [rbx+20h]
0x18002e1ee  movups  xmmword ptr [rax+10h], xmm1
0x18002e1f2  movups  xmm1, xmmword ptr [rbx+30h]
0x18002e1f6  movups  xmmword ptr [rax+20h], xmm0
0x18002e1fa  movups  xmm0, xmmword ptr [rbx+40h]
0x18002e1fe  movups  xmmword ptr [rax+30h], xmm1
0x18002e202  movups  xmm1, xmmword ptr [rbx+50h]
0x18002e206  movups  xmmword ptr [rax+40h], xmm0
0x18002e20a  movups  xmm0, xmmword ptr [rbx+60h]
0x18002e20e  movups  xmmword ptr [rax+50h], xmm1
0x18002e212  movups  xmm1, xmmword ptr [rbx+70h]
0x18002e216  add     rbx, r15
0x18002e219  movups  xmmword ptr [rax+60h], xmm0
0x18002e21d  movups  xmmword ptr [rax+70h], xmm1
0x18002e221  add     rax, r15
0x18002e224  sub     rdi, 1
0x18002e228  jnz     short loc_18002E1E0
0x18002e22a  movups  xmm0, xmmword ptr [rbx]
0x18002e22d  movups  xmm1, xmmword ptr [rbx+10h]
0x18002e231  movups  xmmword ptr [rax], xmm0
0x18002e234  movups  xmm0, xmmword ptr [rbx+20h]
0x18002e238  movups  xmmword ptr [rax+10h], xmm1
0x18002e23c  movups  xmmword ptr [rax+20h], xmm0
0x18002e240  xor     eax, eax
0x18002e242  add     rsp, 178h
0x18002e249  pop     r15
0x18002e24b  pop     r13
0x18002e24d  pop     rdi
0x18002e24e  pop     rsi
0x18002e24f  pop     rbx
0x18002e250  pop     rbp
0x18002e251  retn
```
