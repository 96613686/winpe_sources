# RxcThreadPool_PostponedItem_Schedule

- ea: `0x18002ee04`
- end: `0x18002f18b`
- name: `RxcThreadPool_PostponedItem_Schedule`
- size: `903`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002f2c0`

## callees

- `0x180008d40`
- `0x18002dce4`
- `0x18002df9c`
- `0x18002ee04`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002ef5c`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002ef5c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002efb9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002efb9`

## string_xrefs

- `0x18002ee47`: `admin\wmi\winomi\mp\rxc\rxc.schedulers.threadpool.c`
- `0x18002efe8`: `admin\wmi\winomi\mp\rxc\rxc.schedulers.threadpool.c`
- `0x18002f0bc`: `admin\wmi\winomi\mp\rxc\rxc.schedulers.threadpool.c`
- `0x18002ee7d`: `RxcThreadPool_PostponedItem_Schedule`
- `0x18002f006`: `RxcThreadPool_PostponedItem_Schedule - success`
- `0x18002f0da`: `RxcThreadPool_PostponedItem_Schedule - failure`

## pseudocode

```c
__int64 __fastcall RxcThreadPool_PostponedItem_Schedule(
        __int64 a1,
        void (__fastcall *a2)(__int64),
        __int64 a3,
        __int64 a4,
        _QWORD *a5)
{
  __int64 (__fastcall **v5)(); // rbx
  __int64 v6; // rsi
  _OWORD *v11; // rax
  __int64 (__fastcall **v12)(); // rcx
  __int64 v13; // rdx
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int64 v23; // rcx
  __int64 Singleton; // rax
  __int64 Object; // rax
  __int64 v26; // rdi
  struct _TP_TIMER *v27; // rcx
  _QWORD *v28; // rax
  _OWORD *v29; // rax
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  _OWORD *v40; // rax
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  __int128 v45; // xmm1
  __int128 v46; // xmm0
  __int128 v47; // xmm1
  __int128 v48; // xmm1
  __int128 v49; // xmm0
  struct _FILETIME FileTime; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v51[312]; // [rsp+28h] [rbp-D8h] BYREF
  SYSTEMTIME SystemTime; // [rsp+160h] [rbp+60h] BYREF
  int v53; // [rsp+170h] [rbp+70h]
  int v54; // [rsp+174h] [rbp+74h]

  v5 = NITS_STUB;
  v6 = 2;
  FileTime = 0;
  if ( NITS_PRESENCE_STUB == 1 )
  {
    v11 = v51;
    v12 = NITS_STUB;
    v13 = 2;
    do
    {
      v14 = *((_OWORD *)v12 + 1);
      *v11 = *(_OWORD *)v12;
      v15 = *((_OWORD *)v12 + 2);
      v11[1] = v14;
      v16 = *((_OWORD *)v12 + 3);
      v11[2] = v15;
      v17 = *((_OWORD *)v12 + 4);
      v11[3] = v16;
      v18 = *((_OWORD *)v12 + 5);
      v11[4] = v17;
      v19 = *((_OWORD *)v12 + 6);
      v11[5] = v18;
      v20 = *((_OWORD *)v12 + 7);
      v12 += 16;
      v11[6] = v19;
      v11[7] = v20;
      v11 += 8;
      --v13;
    }
    while ( v13 );
    v21 = *((_OWORD *)v12 + 1);
    *v11 = *(_OWORD *)v12;
    v22 = *((_OWORD *)v12 + 2);
    v11[1] = v21;
    v11[2] = v22;
  }
  else
  {
    *(_QWORD *)&SystemTime.wHour = "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedulers.threadpool.c";
    *(_QWORD *)&SystemTime.wYear = 0;
    v53 = 445;
    v54 = -1;
    ((void (__fastcall *)(const wchar_t *, SYSTEMTIME *, _QWORD))BufferPostNotificationTrapMethod)(
      L"RxcThreadPool_PostponedItem_Schedule",
      &SystemTime,
      0);
  }
  SystemTime.wDayOfWeek = 0;
  SystemTime.wYear = *(_WORD *)a4;
  SystemTime.wMonth = *(_WORD *)(a4 + 4);
  SystemTime.wDay = *(_WORD *)(a4 + 8);
  SystemTime.wHour = *(_WORD *)(a4 + 12);
  SystemTime.wMinute = *(_WORD *)(a4 + 16);
  SystemTime.wSecond = *(_WORD *)(a4 + 20);
  SystemTime.wMilliseconds = *(_DWORD *)(a4 + 24) / 0x3E8u;
  if ( SystemTimeToFileTime(&SystemTime, &FileTime)
    && (Singleton = RxcThreadPool_GetSingleton(v23)) != 0
    && (Object = Cache_GetObject(Singleton + 80), (v26 = Object) != 0) )
  {
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))RxcThreadPool_BaseItem_Construct)(
      Object,
      a1,
      a2,
      a3,
      FileTime);
    v27 = *(struct _TP_TIMER **)(v26 + 48);
    *(_QWORD *)(v26 + 56) = 2;
    *(_QWORD *)(v26 + 64) = 1;
    SetThreadpoolTimer(v27, &FileTime, 0, 0);
    v28 = (_QWORD *)(v26 + 72);
    if ( a5 )
    {
      *a5 = v28;
    }
    else if ( v26 != -72 )
    {
      (*(void (__fastcall **)(_QWORD))(v26 + 96))(*v28);
    }
    if ( NITS_PRESENCE_STUB == 1 )
    {
      v29 = v51;
      do
      {
        v30 = *((_OWORD *)v5 + 1);
        *v29 = *(_OWORD *)v5;
        v31 = *((_OWORD *)v5 + 2);
        v29[1] = v30;
        v32 = *((_OWORD *)v5 + 3);
        v29[2] = v31;
        v33 = *((_OWORD *)v5 + 4);
        v29[3] = v32;
        v34 = *((_OWORD *)v5 + 5);
        v29[4] = v33;
        v35 = *((_OWORD *)v5 + 6);
        v29[5] = v34;
        v36 = *((_OWORD *)v5 + 7);
        v5 += 16;
        v29[6] = v35;
        v29[7] = v36;
        v29 += 8;
        --v6;
      }
      while ( v6 );
      v37 = *((_OWORD *)v5 + 1);
      *v29 = *(_OWORD *)v5;
      v38 = *((_OWORD *)v5 + 2);
      v29[1] = v37;
      v29[2] = v38;
    }
    else
    {
      *(_QWORD *)&SystemTime.wYear = 0;
      *(_QWORD *)&SystemTime.wHour = "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedulers.threadpool.c";
      v53 = 493;
      v54 = -1;
      ((void (__fastcall *)(const wchar_t *, SYSTEMTIME *, _QWORD))BufferPostNotificationTrapMethod)(
        L"RxcThreadPool_PostponedItem_Schedule - success",
        &SystemTime,
        0);
    }
    return 0;
  }
  else
  {
    if ( a5 )
      *a5 = 0;
    if ( a2 )
      a2(a3);
    if ( NITS_PRESENCE_STUB == 1 )
    {
      v40 = v51;
      do
      {
        v41 = *((_OWORD *)v5 + 1);
        *v40 = *(_OWORD *)v5;
        v42 = *((_OWORD *)v5 + 2);
        v40[1] = v41;
        v43 = *((_OWORD *)v5 + 3);
        v40[2] = v42;
        v44 = *((_OWORD *)v5 + 4);
        v40[3] = v43;
        v45 = *((_OWORD *)v5 + 5);
        v40[4] = v44;
        v46 = *((_OWORD *)v5 + 6);
        v40[5] = v45;
        v47 = *((_OWORD *)v5 + 7);
        v5 += 16;
        v40[6] = v46;
        v40[7] = v47;
        v40 += 8;
        --v6;
      }
      while ( v6 );
      v48 = *((_OWORD *)v5 + 1);
      *v40 = *(_OWORD *)v5;
      v49 = *((_OWORD *)v5 + 2);
      v40[1] = v48;
      v40[2] = v49;
    }
    else
    {
      *(_QWORD *)&SystemTime.wYear = 0;
      *(_QWORD *)&SystemTime.wHour = "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedulers.threadpool.c";
      v53 = 504;
      v54 = -1;
      ((void (__fastcall *)(const wchar_t *, SYSTEMTIME *, _QWORD))BufferPostNotificationTrapMethod)(
        L"RxcThreadPool_PostponedItem_Schedule - failure",
        &SystemTime,
        0);
    }
    return 27;
  }
}

```

## disassembly

```asm
0x18002ee04  push    rbp
0x18002ee06  push    rbx
0x18002ee07  push    rsi
0x18002ee08  push    rdi
0x18002ee09  push    r12
0x18002ee0b  push    r13
0x18002ee0d  push    r14
0x18002ee0f  push    r15
0x18002ee11  lea     rbp, [rsp-98h]
0x18002ee19  sub     rsp, 198h
0x18002ee20  mov     rax, cs:__security_cookie
0x18002ee27  xor     rax, rsp
0x18002ee2a  mov     [rbp+0D0h+var_50], rax
0x18002ee31  cmp     cs:NITS_PRESENCE_STUB, 1
0x18002ee39  lea     rbx, NITS_STUB
0x18002ee40  mov     r14, [rbp+0D0h+arg_20]
0x18002ee47  lea     rax, aAdminWmiWinomi_3; "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedu"...
0x18002ee4e  mov     esi, 2
0x18002ee53  mov     qword ptr [rsp+1D0h+FileTime.dwLowDateTime], 0
0x18002ee5c  mov     r12, r8
0x18002ee5f  mov     rdi, r9
0x18002ee62  mov     r15, rdx
0x18002ee65  mov     r13, rcx
0x18002ee68  lea     r8d, [rsi+7Eh]
0x18002ee6c  jz      short loc_18002EEA4
0x18002ee6e  mov     qword ptr [rbp+0D0h+SystemTime.wHour], rax
0x18002ee72  lea     rdx, [rbp+0D0h+SystemTime]
0x18002ee76  mov     rax, cs:off_180047A70
0x18002ee7d  lea     rcx, aRxcthreadpoolP_4; "RxcThreadPool_PostponedItem_Schedule"
0x18002ee84  xor     r8d, r8d
0x18002ee87  mov     qword ptr [rbp+0D0h+SystemTime.wYear], 0
0x18002ee8f  mov     [rbp+0D0h+var_60], 1BDh
0x18002ee96  mov     [rbp+0D0h+var_5C], 0FFFFFFFFh
0x18002ee9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eea2  jmp     short loc_18002EF0F
0x18002eea4  lea     rax, [rsp+1D0h+var_1A8]
0x18002eea9  mov     rcx, rbx
0x18002eeac  mov     rdx, rsi
0x18002eeaf  movups  xmm0, xmmword ptr [rcx]
0x18002eeb2  movups  xmm1, xmmword ptr [rcx+10h]
0x18002eeb6  movups  xmmword ptr [rax], xmm0
0x18002eeb9  movups  xmm0, xmmword ptr [rcx+20h]
0x18002eebd  movups  xmmword ptr [rax+10h], xmm1
0x18002eec1  movups  xmm1, xmmword ptr [rcx+30h]
0x18002eec5  movups  xmmword ptr [rax+20h], xmm0
0x18002eec9  movups  xmm0, xmmword ptr [rcx+40h]
0x18002eecd  movups  xmmword ptr [rax+30h], xmm1
0x18002eed1  movups  xmm1, xmmword ptr [rcx+50h]
0x18002eed5  movups  xmmword ptr [rax+40h], xmm0
0x18002eed9  movups  xmm0, xmmword ptr [rcx+60h]
0x18002eedd  movups  xmmword ptr [rax+50h], xmm1
0x18002eee1  movups  xmm1, xmmword ptr [rcx+70h]
0x18002eee5  add     rcx, r8
0x18002eee8  movups  xmmword ptr [rax+60h], xmm0
0x18002eeec  movups  xmmword ptr [rax+70h], xmm1
0x18002eef0  add     rax, r8
0x18002eef3  sub     rdx, 1
0x18002eef7  jnz     short loc_18002EEAF
0x18002eef9  movups  xmm0, xmmword ptr [rcx]
0x18002eefc  movups  xmm1, xmmword ptr [rcx+10h]
0x18002ef00  movups  xmmword ptr [rax], xmm0
0x18002ef03  movups  xmm0, xmmword ptr [rcx+20h]
0x18002ef07  movups  xmmword ptr [rax+10h], xmm1
0x18002ef0b  movups  xmmword ptr [rax+20h], xmm0
0x18002ef0f  xor     eax, eax
0x18002ef11  lea     rcx, [rbp+0D0h+SystemTime]; lpSystemTime
0x18002ef15  mov     [rbp+0D0h+SystemTime.wDayOfWeek], ax
0x18002ef19  movzx   eax, word ptr [rdi]
0x18002ef1c  mov     [rbp+0D0h+SystemTime.wYear], ax
0x18002ef20  movzx   eax, word ptr [rdi+4]
0x18002ef24  mov     [rbp+0D0h+SystemTime.wMonth], ax
0x18002ef28  movzx   eax, word ptr [rdi+8]
0x18002ef2c  mov     [rbp+0D0h+SystemTime.wDay], ax
0x18002ef30  movzx   eax, word ptr [rdi+0Ch]
0x18002ef34  mov     [rbp+0D0h+SystemTime.wHour], ax
0x18002ef38  movzx   eax, word ptr [rdi+10h]
0x18002ef3c  mov     [rbp+0D0h+SystemTime.wMinute], ax
0x18002ef40  movzx   eax, word ptr [rdi+14h]
0x18002ef44  mov     [rbp+0D0h+SystemTime.wSecond], ax
0x18002ef48  mov     eax, 10624DD3h
0x18002ef4d  mul     dword ptr [rdi+18h]
0x18002ef50  shr     edx, 6
0x18002ef53  mov     [rbp+0D0h+SystemTime.wMilliseconds], dx
0x18002ef57  lea     rdx, [rsp+1D0h+FileTime]; lpFileTime
0x18002ef5c  call    cs:__imp_SystemTimeToFileTime
0x18002ef62  test    eax, eax
0x18002ef64  jz      loc_18002F096
0x18002ef6a  call    RxcThreadPool_GetSingleton
0x18002ef6f  test    rax, rax
0x18002ef72  jz      loc_18002F096
0x18002ef78  lea     rcx, [rax+50h]
0x18002ef7c  call    Cache_GetObject
0x18002ef81  mov     rdi, rax
0x18002ef84  test    rax, rax
0x18002ef87  jz      loc_18002F096
0x18002ef8d  mov     r9, r12
0x18002ef90  mov     r8, r15
0x18002ef93  mov     rdx, r13
0x18002ef96  mov     rcx, rax
0x18002ef99  call    RxcThreadPool_BaseItem_Construct
0x18002ef9e  mov     rcx, [rdi+30h]; pti
0x18002efa2  lea     rdx, [rsp+1D0h+FileTime]; pftDueTime
0x18002efa7  xor     r9d, r9d; msWindowLength
0x18002efaa  mov     [rdi+38h], rsi
0x18002efae  xor     r8d, r8d; msPeriod
0x18002efb1  mov     qword ptr [rdi+40h], 1
0x18002efb9  call    cs:__imp_SetThreadpoolTimer
0x18002efbf  lea     rax, [rdi+48h]
0x18002efc3  test    r14, r14
0x18002efc6  jz      short loc_18002EFCD
0x18002efc8  mov     [r14], rax
0x18002efcb  jmp     short loc_18002EFDE
0x18002efcd  test    rax, rax
0x18002efd0  jz      short loc_18002EFDE
0x18002efd2  mov     rcx, [rax]
0x18002efd5  mov     rax, [rax+18h]
0x18002efd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efde  cmp     cs:NITS_PRESENCE_STUB, 1
0x18002efe6  jz      short loc_18002F025
0x18002efe8  lea     rax, aAdminWmiWinomi_3; "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedu"...
0x18002efef  mov     qword ptr [rbp+0D0h+SystemTime.wYear], 0
0x18002eff7  mov     qword ptr [rbp+0D0h+SystemTime.wHour], rax
0x18002effb  lea     rdx, [rbp+0D0h+SystemTime]
0x18002efff  mov     rax, cs:off_180047A70
0x18002f006  lea     rcx, aRxcthreadpoolP_2; "RxcThreadPool_PostponedItem_Schedule - "...
0x18002f00d  xor     r8d, r8d
0x18002f010  mov     [rbp+0D0h+var_60], 1EDh
0x18002f017  mov     [rbp+0D0h+var_5C], 0FFFFFFFFh
0x18002f01e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f023  jmp     short loc_18002F08F
0x18002f025  lea     rax, [rsp+1D0h+var_1A8]
0x18002f02a  mov     ecx, 80h
0x18002f02f  movups  xmm0, xmmword ptr [rbx]
0x18002f032  movups  xmm1, xmmword ptr [rbx+10h]
0x18002f036  movups  xmmword ptr [rax], xmm0
0x18002f039  movups  xmm0, xmmword ptr [rbx+20h]
0x18002f03d  movups  xmmword ptr [rax+10h], xmm1
0x18002f041  movups  xmm1, xmmword ptr [rbx+30h]
0x18002f045  movups  xmmword ptr [rax+20h], xmm0
0x18002f049  movups  xmm0, xmmword ptr [rbx+40h]
0x18002f04d  movups  xmmword ptr [rax+30h], xmm1
0x18002f051  movups  xmm1, xmmword ptr [rbx+50h]
0x18002f055  movups  xmmword ptr [rax+40h], xmm0
0x18002f059  movups  xmm0, xmmword ptr [rbx+60h]
0x18002f05d  movups  xmmword ptr [rax+50h], xmm1
0x18002f061  movups  xmm1, xmmword ptr [rbx+70h]
0x18002f065  add     rbx, rcx
0x18002f068  movups  xmmword ptr [rax+60h], xmm0
0x18002f06c  movups  xmmword ptr [rax+70h], xmm1
0x18002f070  add     rax, rcx
0x18002f073  sub     rsi, 1
0x18002f077  jnz     short loc_18002F02F
0x18002f079  movups  xmm0, xmmword ptr [rbx]
0x18002f07c  movups  xmm1, xmmword ptr [rbx+10h]
0x18002f080  movups  xmmword ptr [rax], xmm0
0x18002f083  movups  xmm0, xmmword ptr [rbx+20h]
0x18002f087  movups  xmmword ptr [rax+10h], xmm1
0x18002f08b  movups  xmmword ptr [rax+20h], xmm0
0x18002f08f  xor     eax, eax
0x18002f091  jmp     loc_18002F168
0x18002f096  test    r14, r14
0x18002f099  jz      short loc_18002F0A2
0x18002f09b  mov     qword ptr [r14], 0
0x18002f0a2  test    r15, r15
0x18002f0a5  jz      short loc_18002F0B2
0x18002f0a7  mov     rcx, r12
0x18002f0aa  mov     rax, r15
0x18002f0ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0b2  cmp     cs:NITS_PRESENCE_STUB, 1
0x18002f0ba  jz      short loc_18002F0F9
0x18002f0bc  lea     rax, aAdminWmiWinomi_3; "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedu"...
0x18002f0c3  mov     qword ptr [rbp+0D0h+SystemTime.wYear], 0
0x18002f0cb  mov     qword ptr [rbp+0D0h+SystemTime.wHour], rax
0x18002f0cf  lea     rdx, [rbp+0D0h+SystemTime]
0x18002f0d3  mov     rax, cs:off_180047A70
0x18002f0da  lea     rcx, aRxcthreadpoolP_0; "RxcThreadPool_PostponedItem_Schedule - "...
0x18002f0e1  xor     r8d, r8d
0x18002f0e4  mov     [rbp+0D0h+var_60], 1F8h
0x18002f0eb  mov     [rbp+0D0h+var_5C], 0FFFFFFFFh
0x18002f0f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0f7  jmp     short loc_18002F163
0x18002f0f9  lea     rax, [rsp+1D0h+var_1A8]
0x18002f0fe  mov     ecx, 80h
0x18002f103  movups  xmm0, xmmword ptr [rbx]
0x18002f106  movups  xmm1, xmmword ptr [rbx+10h]
0x18002f10a  movups  xmmword ptr [rax], xmm0
0x18002f10d  movups  xmm0, xmmword ptr [rbx+20h]
0x18002f111  movups  xmmword ptr [rax+10h], xmm1
0x18002f115  movups  xmm1, xmmword ptr [rbx+30h]
0x18002f119  movups  xmmword ptr [rax+20h], xmm0
0x18002f11d  movups  xmm0, xmmword ptr [rbx+40h]
0x18002f121  movups  xmmword ptr [rax+30h], xmm1
0x18002f125  movups  xmm1, xmmword ptr [rbx+50h]
0x18002f129  movups  xmmword ptr [rax+40h], xmm0
0x18002f12d  movups  xmm0, xmmword ptr [rbx+60h]
0x18002f131  movups  xmmword ptr [rax+50h], xmm1
0x18002f135  movups  xmm1, xmmword ptr [rbx+70h]
0x18002f139  add     rbx, rcx
0x18002f13c  movups  xmmword ptr [rax+60h], xmm0
0x18002f140  movups  xmmword ptr [rax+70h], xmm1
0x18002f144  add     rax, rcx
0x18002f147  sub     rsi, 1
0x18002f14b  jnz     short loc_18002F103
0x18002f14d  movups  xmm0, xmmword ptr [rbx]
0x18002f150  movups  xmm1, xmmword ptr [rbx+10h]
0x18002f154  movups  xmmword ptr [rax], xmm0
0x18002f157  movups  xmm0, xmmword ptr [rbx+20h]
0x18002f15b  movups  xmmword ptr [rax+10h], xmm1
0x18002f15f  movups  xmmword ptr [rax+20h], xmm0
0x18002f163  mov     eax, 1Bh
0x18002f168  mov     rcx, [rbp+0D0h+var_50]
0x18002f16f  xor     rcx, rsp; StackCookie
0x18002f172  call    __security_check_cookie
0x18002f177  add     rsp, 198h
0x18002f17e  pop     r15
0x18002f180  pop     r14
0x18002f182  pop     r13
0x18002f184  pop     r12
0x18002f186  pop     rdi
0x18002f187  pop     rsi
0x18002f188  pop     rbx
0x18002f189  pop     rbp
0x18002f18a  retn
```
