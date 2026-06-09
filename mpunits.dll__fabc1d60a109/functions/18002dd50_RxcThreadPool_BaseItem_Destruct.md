# RxcThreadPool_BaseItem_Destruct

- ea: `0x18002dd50`
- end: `0x18002deef`
- name: `RxcThreadPool_BaseItem_Destruct`
- size: `415`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18002e540`
- `0x18002e9d0`
- `0x18002f1a0`

## callees

- `0x18002dd50`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002deb5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002deb5`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x18002dead`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x18002dead`

## string_xrefs

- `0x18002dd81`: `admin\wmi\winomi\mp\rxc\rxc.schedulers.threadpool.c`
- `0x18002dd9f`: `RxcThreadPool_BaseItem_Destruct`

## pseudocode

```c
__int64 __fastcall RxcThreadPool_BaseItem_Destruct(__int64 a1, struct _TP_CALLBACK_INSTANCE *a2)
{
  __int64 v4; // rdx
  char *v5; // rax
  __int64 (__fastcall **v6)(); // rcx
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  char v17; // [rsp+20h] [rbp-168h] BYREF
  __int128 v18; // [rsp+150h] [rbp-38h] BYREF
  __int128 v19; // [rsp+160h] [rbp-28h]

  if ( NITS_PRESENCE_STUB == 1 )
  {
    v4 = 2;
    v5 = &v17;
    v6 = NITS_STUB;
    do
    {
      v7 = *((_OWORD *)v6 + 1);
      *(_OWORD *)v5 = *(_OWORD *)v6;
      v8 = *((_OWORD *)v6 + 2);
      *((_OWORD *)v5 + 1) = v7;
      v9 = *((_OWORD *)v6 + 3);
      *((_OWORD *)v5 + 2) = v8;
      v10 = *((_OWORD *)v6 + 4);
      *((_OWORD *)v5 + 3) = v9;
      v11 = *((_OWORD *)v6 + 5);
      *((_OWORD *)v5 + 4) = v10;
      v12 = *((_OWORD *)v6 + 6);
      *((_OWORD *)v5 + 5) = v11;
      v13 = *((_OWORD *)v6 + 7);
      v6 += 16;
      *((_OWORD *)v5 + 6) = v12;
      *((_OWORD *)v5 + 7) = v13;
      v5 += 128;
      --v4;
    }
    while ( v4 );
    v14 = *((_OWORD *)v6 + 1);
    *(_OWORD *)v5 = *(_OWORD *)v6;
    v15 = *((_OWORD *)v6 + 2);
    *((_OWORD *)v5 + 1) = v14;
    *((_OWORD *)v5 + 2) = v15;
  }
  else
  {
    *(_QWORD *)&v18 = 0;
    *((_QWORD *)&v18 + 1) = "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedulers.threadpool.c";
    *(_QWORD *)&v19 = -4294967173LL;
    ((void (__fastcall *)(const wchar_t *, __int128 *, _QWORD))BufferPostNotificationTrapMethod)(
      L"RxcThreadPool_BaseItem_Destruct",
      &v18,
      0);
  }
  if ( *(_QWORD *)(a1 + 16) )
  {
    v18 = 0;
    v19 = 0;
    ExecutionContext_SaveThread((LPGUID)&v18);
    ExecutionContext_SetContext(*(GUID **)a1);
    (*(void (__fastcall **)(_QWORD))(a1 + 16))(*(_QWORD *)(a1 + 24));
    ExecutionContext_RestoreThread((LPGUID)&v18);
  }
  if ( a2 )
    FreeLibraryWhenCallbackReturns(a2, *(HMODULE *)(a1 + 32));
  else
    FreeLibrary(*(HMODULE *)(a1 + 32));
  return ExecutionContext_Release(*(void **)a1);
}

```

## disassembly

```asm
0x18002dd50  mov     r11, rsp
0x18002dd53  mov     [r11+18h], rbx
0x18002dd57  push    rdi
0x18002dd58  sub     rsp, 180h
0x18002dd5f  mov     rax, cs:__security_cookie
0x18002dd66  xor     rax, rsp
0x18002dd69  mov     [rsp+188h+var_18], rax
0x18002dd71  cmp     cs:NITS_PRESENCE_STUB, 1
0x18002dd79  mov     rdi, rdx
0x18002dd7c  mov     rbx, rcx
0x18002dd7f  jz      short loc_18002DDC0
0x18002dd81  lea     rax, aAdminWmiWinomi_3; "admin\\wmi\\winomi\\mp\\rxc\\rxc.schedu"...
0x18002dd88  mov     qword ptr [r11-38h], 0
0x18002dd90  mov     [r11-30h], rax
0x18002dd94  lea     rdx, [r11-38h]
0x18002dd98  mov     rax, cs:off_180047A70
0x18002dd9f  lea     rcx, aRxcthreadpoolB; "RxcThreadPool_BaseItem_Destruct"
0x18002dda6  xor     r8d, r8d
0x18002dda9  mov     dword ptr [r11-28h], 7Bh ; '{'
0x18002ddb1  mov     dword ptr [r11-24h], 0FFFFFFFFh
0x18002ddb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddbe  jmp     short loc_18002DE35
0x18002ddc0  mov     edx, 2
0x18002ddc5  lea     rax, [rsp+188h+var_168]
0x18002ddca  lea     rcx, NITS_STUB
0x18002ddd1  lea     r8d, [rdx+7Eh]
0x18002ddd5  movups  xmm0, xmmword ptr [rcx]
0x18002ddd8  movups  xmm1, xmmword ptr [rcx+10h]
0x18002dddc  movups  xmmword ptr [rax], xmm0
0x18002dddf  movups  xmm0, xmmword ptr [rcx+20h]
0x18002dde3  movups  xmmword ptr [rax+10h], xmm1
0x18002dde7  movups  xmm1, xmmword ptr [rcx+30h]
0x18002ddeb  movups  xmmword ptr [rax+20h], xmm0
0x18002ddef  movups  xmm0, xmmword ptr [rcx+40h]
0x18002ddf3  movups  xmmword ptr [rax+30h], xmm1
0x18002ddf7  movups  xmm1, xmmword ptr [rcx+50h]
0x18002ddfb  movups  xmmword ptr [rax+40h], xmm0
0x18002ddff  movups  xmm0, xmmword ptr [rcx+60h]
0x18002de03  movups  xmmword ptr [rax+50h], xmm1
0x18002de07  movups  xmm1, xmmword ptr [rcx+70h]
0x18002de0b  add     rcx, r8
0x18002de0e  movups  xmmword ptr [rax+60h], xmm0
0x18002de12  movups  xmmword ptr [rax+70h], xmm1
0x18002de16  add     rax, r8
0x18002de19  sub     rdx, 1
0x18002de1d  jnz     short loc_18002DDD5
0x18002de1f  movups  xmm0, xmmword ptr [rcx]
0x18002de22  movups  xmm1, xmmword ptr [rcx+10h]
0x18002de26  movups  xmmword ptr [rax], xmm0
0x18002de29  movups  xmm0, xmmword ptr [rcx+20h]
0x18002de2d  movups  xmmword ptr [rax+10h], xmm1
0x18002de31  movups  xmmword ptr [rax+20h], xmm0
0x18002de35  cmp     qword ptr [rbx+10h], 0
0x18002de3a  jz      short loc_18002DE9E
0x18002de3c  mov     rax, cs:off_180047C30
0x18002de43  lea     rcx, [rsp+188h+var_38]
0x18002de4b  xorps   xmm0, xmm0
0x18002de4e  movups  [rsp+188h+var_38], xmm0
0x18002de56  movups  [rsp+188h+var_28], xmm0
0x18002de5e  mov     rax, [rax]
0x18002de61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de66  mov     rax, cs:off_180047C30
0x18002de6d  mov     rcx, [rbx]
0x18002de70  mov     rax, [rax+10h]
0x18002de74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de79  mov     rcx, [rbx+18h]
0x18002de7d  mov     rax, [rbx+10h]
0x18002de81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de86  mov     rax, cs:off_180047C30
0x18002de8d  lea     rcx, [rsp+188h+var_38]
0x18002de95  mov     rax, [rax+8]
0x18002de99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de9e  mov     rcx, [rbx+20h]; hLibModule
0x18002dea2  test    rdi, rdi
0x18002dea5  jz      short loc_18002DEB5
0x18002dea7  mov     rdx, rcx; mod
0x18002deaa  mov     rcx, rdi; pci
0x18002dead  call    cs:__imp_FreeLibraryWhenCallbackReturns
0x18002deb3  jmp     short loc_18002DEBB
0x18002deb5  call    cs:__imp_FreeLibrary
0x18002debb  mov     rax, cs:off_180047C30
0x18002dec2  mov     rcx, [rbx]
0x18002dec5  mov     rax, [rax+30h]
0x18002dec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dece  mov     rcx, [rsp+188h+var_18]
0x18002ded6  xor     rcx, rsp; StackCookie
0x18002ded9  call    __security_check_cookie
0x18002dede  mov     rbx, [rsp+188h+arg_10]
0x18002dee6  add     rsp, 180h
0x18002deed  pop     rdi
0x18002deee  retn
```
