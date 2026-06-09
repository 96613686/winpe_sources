# StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x180007c94`
- end: `0x180007fea`
- name: `?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `854`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000669c`
- `0x1800082a0`
- `0x180152178`

## callees

- `0x180007c94`
- `0x18005b110`
- `0x18005b2c4`
- `0x1801369c9`
- `0x180194f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180007e0b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180007e0b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180007db9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180007db9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180007cf2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180007cf2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007d1c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007de3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007e52`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007e88`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007ef9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007f4e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007d1c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007de3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007e52`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007e88`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007ef9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007f4e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180007e6d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180007ede`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180007e6d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180007ede`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180007e2d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180007e2d`

## string_xrefs

- `0x180007ebb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x180007f30`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x180007fca`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x180007f10`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180007f66`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180007f88`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180007faa`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  int v21[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v22; // [rsp+28h] [rbp-D8h] BYREF
  int *v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  char v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v27[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+258h] [rbp+158h]
  __int64 v29; // [rsp+260h] [rbp+160h]
  _BYTE *v30; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v25 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  *(_QWORD *)v21 = 0;
  v23 = v21;
  v24 = 0;
  v6 = SRCacheContext_Open(v3, L"PackageFamily\\Index\\PackageFamilyName", 0, &v24);
  if ( v25 )
  {
    v7 = *(_QWORD *)v23;
    *(_QWORD *)v23 = v24;
    if ( v7 )
      SRCacheContext_Close(v7);
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v21[0]);
    v20 = 193;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)v6,
      v21[0]);
    goto LABEL_24;
  }
  if ( !*(_QWORD *)v21 )
  {
    v6 = -2140733422;
    v20 = 194;
    goto LABEL_33;
  }
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v28 = 0;
  v30 = v27;
  v29 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v26, a2);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v8,
      v21[0]);
  }
  else
  {
    v23 = (int *)&v22;
    v22 = 0;
    v24 = 0;
    v25 = 1;
    v6 = SRCacheContext_OpenSubContext(*(_QWORD *)v21, v30, 0, &v24);
    if ( v25 )
    {
      v9 = *(_QWORD *)v23;
      *(_QWORD *)v23 = v24;
      if ( v9 )
        SRCacheContext_Close(v9);
    }
    if ( (v6 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B0,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)v6,
        v21[0]);
      v18 = 201;
    }
    else if ( v22 && (v10 = SRCacheContext_EnumerateData(v22, 0, a3), v6 = v10, v10 < 0) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v10,
        v21[0]);
      v18 = 204;
    }
    else
    {
      v11 = SRCacheContext_AddToCache(*(_QWORD *)v21, L"PackageFamily\\Index\\PackageFamilyName");
      v6 = v11;
      if ( v11 >= 0 )
      {
        v12 = v22;
        v22 = 0;
        if ( v12 )
          SRCacheContext_Close(v12);
        v13 = v26;
        v26 = 0;
        if ( v13 )
          SRCache_Free(v13);
        v14 = *(_QWORD *)v21;
        *(_QWORD *)v21 = 0;
        if ( v14 )
          SRCacheContext_Close(v14);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v11,
        v21[0]);
      v18 = 207;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)v6,
      v21[0]);
    v19 = v22;
    v22 = 0;
    if ( v19 )
      SRCacheContext_Close(v19);
  }
  v16 = v26;
  v26 = 0;
  if ( v16 )
    SRCache_Free(v16);
LABEL_24:
  v17 = *(_QWORD *)v21;
  *(_QWORD *)v21 = 0;
  if ( v17 )
    SRCacheContext_Close(v17);
  return v6;
}

```

## disassembly

```asm
0x180007c94  push    rbp
0x180007c96  push    rbx
0x180007c97  push    rsi
0x180007c98  push    rdi
0x180007c99  push    r14
0x180007c9b  lea     rbp, [rsp-180h]
0x180007ca3  sub     rsp, 280h
0x180007caa  mov     rax, cs:__security_cookie
0x180007cb1  xor     rax, rsp
0x180007cb4  mov     [rbp+1A0h+var_30], rax
0x180007cbb  xor     r14d, r14d
0x180007cbe  mov     [rsp+2A0h+var_260], 1
0x180007cc3  mov     [r8], r14
0x180007cc6  lea     rax, [rsp+2A0h+var_280]
0x180007ccb  mov     rcx, [rcx]
0x180007cce  lea     r9, [rsp+2A0h+var_268]
0x180007cd3  mov     rdi, r8
0x180007cd6  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x180007cdb  mov     rsi, rdx
0x180007cde  mov     [rsp+2A0h+var_270], rax
0x180007ce3  xor     r8d, r8d
0x180007ce6  mov     [rsp+2A0h+var_268], r14
0x180007ceb  lea     rdx, aPackagefamilyI_0; "PackageFamily\\Index\\PackageFamilyName"
0x180007cf2  call    cs:__imp_SRCacheContext_Open
0x180007cf9  nop     dword ptr [rax+rax+00h]
0x180007cfe  mov     ebx, eax
0x180007d00  cmp     [rsp+2A0h+var_260], r14b
0x180007d05  jz      short loc_180007D28
0x180007d07  mov     r8, [rsp+2A0h+var_270]
0x180007d0c  mov     rdx, [rsp+2A0h+var_268]
0x180007d11  mov     rcx, [r8]
0x180007d14  mov     [r8], rdx
0x180007d17  test    rcx, rcx
0x180007d1a  jz      short loc_180007D28
0x180007d1c  call    cs:__imp_SRCacheContext_Close
0x180007d23  nop     dword ptr [rax+rax+00h]
0x180007d28  test    ebx, ebx
0x180007d2a  js      loc_180007FA3
0x180007d30  cmp     qword ptr [rsp+2A0h+var_280], r14
0x180007d35  setnz   al
0x180007d38  test    al, al
0x180007d3a  jz      loc_180007FDE
0x180007d40  xor     edx, edx; Val
0x180007d42  mov     [rsp+2A0h+var_250], r14
0x180007d47  mov     r8d, 200h; Size
0x180007d4d  lea     rcx, [rsp+2A0h+var_248]; void *
0x180007d52  call    memset_0
0x180007d57  lea     rax, [rsp+2A0h+var_248]
0x180007d5c  mov     [rbp+1A0h+var_48], r14
0x180007d63  mov     rdx, rsi; unsigned __int16 *
0x180007d66  mov     [rbp+1A0h+var_38], rax
0x180007d6d  lea     rcx, [rsp+2A0h+var_250]; this
0x180007d72  mov     [rbp+1A0h+var_40], 100h
0x180007d7d  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180007d82  mov     ebx, eax
0x180007d84  test    eax, eax
0x180007d86  js      loc_180007EB4
0x180007d8c  mov     rdx, [rbp+1A0h+var_38]
0x180007d93  lea     rax, [rsp+2A0h+var_278]
0x180007d98  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180007d9d  lea     r9, [rsp+2A0h+var_268]
0x180007da2  xor     r8d, r8d
0x180007da5  mov     [rsp+2A0h+var_270], rax
0x180007daa  mov     [rsp+2A0h+var_278], r14
0x180007daf  mov     [rsp+2A0h+var_268], r14
0x180007db4  mov     [rsp+2A0h+var_260], 1
0x180007db9  call    cs:__imp_SRCacheContext_OpenSubContext
0x180007dc0  nop     dword ptr [rax+rax+00h]
0x180007dc5  mov     ebx, eax
0x180007dc7  cmp     [rsp+2A0h+var_260], r14b
0x180007dcc  jz      short loc_180007DEF
0x180007dce  mov     r8, [rsp+2A0h+var_270]
0x180007dd3  mov     rdx, [rsp+2A0h+var_268]
0x180007dd8  mov     rcx, [r8]
0x180007ddb  mov     [r8], rdx
0x180007dde  test    rcx, rcx
0x180007de1  jz      short loc_180007DEF
0x180007de3  call    cs:__imp_SRCacheContext_Close
0x180007dea  nop     dword ptr [rax+rax+00h]
0x180007def  test    ebx, ebx
0x180007df1  js      loc_180007F5F
0x180007df7  mov     rcx, [rsp+2A0h+var_278]
0x180007dfc  test    rcx, rcx
0x180007dff  setnz   al
0x180007e02  test    al, al
0x180007e04  jz      short loc_180007E21
0x180007e06  mov     r8, rdi
0x180007e09  xor     edx, edx
0x180007e0b  call    cs:__imp_SRCacheContext_EnumerateData
0x180007e12  nop     dword ptr [rax+rax+00h]
0x180007e17  mov     ebx, eax
0x180007e19  test    eax, eax
0x180007e1b  js      loc_180007F81
0x180007e21  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180007e26  lea     rdx, aPackagefamilyI_0; "PackageFamily\\Index\\PackageFamilyName"
0x180007e2d  call    cs:__imp_SRCacheContext_AddToCache
0x180007e34  nop     dword ptr [rax+rax+00h]
0x180007e39  mov     ebx, eax
0x180007e3b  test    eax, eax
0x180007e3d  js      loc_180007F09
0x180007e43  mov     rcx, [rsp+2A0h+var_278]
0x180007e48  mov     [rsp+2A0h+var_278], r14
0x180007e4d  test    rcx, rcx
0x180007e50  jz      short loc_180007E5E
0x180007e52  call    cs:__imp_SRCacheContext_Close
0x180007e59  nop     dword ptr [rax+rax+00h]
0x180007e5e  mov     rcx, [rsp+2A0h+var_250]
0x180007e63  mov     [rsp+2A0h+var_250], r14
0x180007e68  test    rcx, rcx
0x180007e6b  jz      short loc_180007E79
0x180007e6d  call    cs:__imp_SRCache_Free
0x180007e74  nop     dword ptr [rax+rax+00h]
0x180007e79  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180007e7e  mov     qword ptr [rsp+2A0h+var_280], r14
0x180007e83  test    rcx, rcx
0x180007e86  jz      short loc_180007E94
0x180007e88  call    cs:__imp_SRCacheContext_Close
0x180007e8f  nop     dword ptr [rax+rax+00h]
0x180007e94  xor     eax, eax
0x180007e96  mov     rcx, [rbp+1A0h+var_30]
0x180007e9d  xor     rcx, rsp; StackCookie
0x180007ea0  call    __security_check_cookie
0x180007ea5  add     rsp, 280h
0x180007eac  pop     r14
0x180007eae  pop     rdi
0x180007eaf  pop     rsi
0x180007eb0  pop     rbx
0x180007eb1  pop     rbp
0x180007eb2  retn
0x180007eb4  mov     rcx, [rbp+1A8h]; this
0x180007ebb  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007ec2  mov     r9d, ebx; char *
0x180007ec5  mov     edx, 0C5h; void *
0x180007eca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ecf  mov     rcx, [rsp+2A0h+var_250]
0x180007ed4  mov     [rsp+2A0h+var_250], r14
0x180007ed9  test    rcx, rcx
0x180007edc  jz      short loc_180007EEA
0x180007ede  call    cs:__imp_SRCache_Free
0x180007ee5  nop     dword ptr [rax+rax+00h]
0x180007eea  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180007eef  mov     qword ptr [rsp+2A0h+var_280], r14
0x180007ef4  test    rcx, rcx
0x180007ef7  jz      short loc_180007F05
0x180007ef9  call    cs:__imp_SRCacheContext_Close
0x180007f00  nop     dword ptr [rax+rax+00h]
0x180007f05  mov     eax, ebx
0x180007f07  jmp     short loc_180007E96
0x180007f09  mov     rcx, [rbp+1A8h]; this
0x180007f10  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007f17  mov     r9d, ebx; char *
0x180007f1a  mov     edx, 1A6h; void *
0x180007f1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f24  mov     edx, 0CFh; void *
0x180007f29  mov     rcx, [rbp+1A8h]; this
0x180007f30  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007f37  mov     r9d, ebx; char *
0x180007f3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f3f  mov     rcx, [rsp+2A0h+var_278]
0x180007f44  mov     [rsp+2A0h+var_278], r14
0x180007f49  test    rcx, rcx
0x180007f4c  jz      short loc_180007ECF
0x180007f4e  call    cs:__imp_SRCacheContext_Close
0x180007f55  nop     dword ptr [rax+rax+00h]
0x180007f5a  jmp     loc_180007ECF
0x180007f5f  mov     rcx, [rbp+1A8h]; this
0x180007f66  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007f6d  mov     r9d, ebx; char *
0x180007f70  mov     edx, 1B0h; void *
0x180007f75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f7a  mov     edx, 0C9h
0x180007f7f  jmp     short loc_180007F29
0x180007f81  mov     rcx, [rbp+1A8h]; this
0x180007f88  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007f8f  mov     r9d, ebx; char *
0x180007f92  mov     edx, 2A6h; void *
0x180007f97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f9c  mov     edx, 0CCh
0x180007fa1  jmp     short loc_180007F29
0x180007fa3  mov     rcx, [rbp+1A8h]; this
0x180007faa  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007fb1  mov     r9d, ebx; char *
0x180007fb4  mov     edx, 18Ch; void *
0x180007fb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007fbe  mov     edx, 0C1h; void *
0x180007fc3  mov     rcx, [rbp+1A8h]; this
0x180007fca  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007fd1  mov     r9d, ebx; char *
0x180007fd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007fd9  jmp     loc_180007EEA
0x180007fde  mov     ebx, 80670012h
0x180007fe3  mov     edx, 0C2h
0x180007fe8  jmp     short loc_180007FC3
```
