# StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180063500`
- end: `0x1800637fa`
- name: `?Open@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `762`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18006341c`

## callees

- `0x18001a140`
- `0x18002c8d0`
- `0x180063500`
- `0x1800862f0`
- `0x180086e44`
- `0x180086f7c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800636bb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180063761`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800636bb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180063761`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180063595`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180063679`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800636d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006372d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180063595`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180063679`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800636d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006372d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18006356b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18006356b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18006364f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18006364f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18006369c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18006369c`

## string_xrefs

- `0x180063795`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180063770`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800637b7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800637dc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18006370f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x180063743`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  int v24[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v25; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v26[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v27; // [rsp+238h] [rbp+138h]
  __int64 v28; // [rsp+240h] [rbp+140h]
  _BYTE *v29; // [rsp+248h] [rbp+148h]
  unsigned __int16 v30[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v31; // [rsp+258h] [rbp+158h] BYREF
  char v32; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v4 = *(_QWORD *)a1;
  *(_QWORD *)v30 = v24;
  v32 = 1;
  *(_QWORD *)v24 = 0;
  v31 = 0;
  v8 = SRCacheContext_Open(v4, L"PackageFamily\\Data", 0, &v31);
  if ( v32 )
  {
    v9 = v31;
    v10 = **(_QWORD **)v30;
    **(_QWORD **)v30 = v31;
    if ( v10 )
      SRCacheContext_Close(v10, v9);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v24[0]);
    v19 = 257;
  }
  else
  {
    if ( *(_QWORD *)v24 )
    {
      v25 = 0;
      memset_0(v26, 0, sizeof(v26));
      v27 = 0;
      v28 = 256;
      v29 = v26;
      if ( (unsigned int)o__ui64tow_s_0(a2, v30, 17) )
      {
        v8 = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x166,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)0x8000FFFFLL,
          v24[0]);
      }
      else
      {
        v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, v30);
        if ( v8 >= 0 )
        {
          *(_QWORD *)v30 = a3;
          v31 = 0;
          v32 = 1;
          v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v24, v29, 0, &v31);
          if ( v32 )
          {
            v11 = v31;
            v12 = **(_QWORD **)v30;
            **(_QWORD **)v30 = v31;
            if ( v12 )
              SRCacheContext_Close(v12, v11);
          }
          if ( v8 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1B0,
              (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
              (const char *)(unsigned int)v8,
              v24[0]);
            v22 = 262;
          }
          else
          {
            v13 = *(_QWORD *)v24;
            *a4 = *(_QWORD *)a3 != 0;
            v14 = SRCacheContext_AddToCache(v13, L"PackageFamily\\Data");
            v8 = v14;
            if ( v14 >= 0 )
            {
              v16 = v25;
              v25 = 0;
              if ( v16 )
                SRCache_Free();
              v17 = *(_QWORD *)v24;
              *(_QWORD *)v24 = 0;
              if ( v17 )
                SRCacheContext_Close(v17, v15);
              return 0;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1A6,
              (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
              (const char *)(unsigned int)v14,
              v24[0]);
            v22 = 264;
          }
          goto LABEL_24;
        }
      }
      v22 = 261;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
        (const char *)(unsigned int)v8,
        v24[0]);
      v23 = v25;
      v25 = 0;
      if ( v23 )
        SRCache_Free();
      goto LABEL_20;
    }
    v8 = -2140733422;
    v19 = 258;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v19,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
    (const char *)(unsigned int)v8,
    v24[0]);
LABEL_20:
  v21 = *(_QWORD *)v24;
  *(_QWORD *)v24 = 0;
  if ( v21 )
    SRCacheContext_Close(v21, v20);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180063500  mov     [rsp-8+arg_10], rbx
0x180063505  push    rbp
0x180063506  push    rsi
0x180063507  push    rdi
0x180063508  push    r14
0x18006350a  push    r15
0x18006350c  lea     rbp, [rsp-180h]
0x180063514  sub     rsp, 280h
0x18006351b  mov     rax, cs:__security_cookie
0x180063522  xor     rax, rsp
0x180063525  mov     [rbp+1A0h+var_28], rax
0x18006352c  mov     rcx, [rcx]
0x18006352f  lea     rax, [rsp+2A0h+var_280]
0x180063534  mov     r14, r9
0x180063537  mov     qword ptr [rbp+1A0h+var_50], rax
0x18006353e  mov     rdi, r8
0x180063541  mov     [rbp+1A0h+var_40], 1
0x180063548  mov     rsi, rdx
0x18006354b  lea     r9, [rbp+1A0h+var_48]
0x180063552  xor     r15d, r15d
0x180063555  lea     rdx, aPackagefamilyD; "PackageFamily\\Data"
0x18006355c  xor     r8d, r8d
0x18006355f  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x180063564  mov     [rbp+1A0h+var_48], r15
0x18006356b  call    cs:__imp_SRCacheContext_Open
0x180063571  mov     ebx, eax
0x180063573  cmp     [rbp+1A0h+var_40], r15b
0x18006357a  jz      short loc_18006359B
0x18006357c  mov     r8, qword ptr [rbp+1A0h+var_50]
0x180063583  mov     rdx, [rbp+1A0h+var_48]
0x18006358a  mov     rcx, [r8]
0x18006358d  mov     [r8], rdx
0x180063590  test    rcx, rcx
0x180063593  jz      short loc_18006359B
0x180063595  call    cs:__imp_SRCacheContext_Close
0x18006359b  test    ebx, ebx
0x18006359d  js      loc_180063769
0x1800635a3  cmp     qword ptr [rsp+2A0h+var_280], r15
0x1800635a8  setnz   al
0x1800635ab  test    al, al
0x1800635ad  jz      loc_1800636FE
0x1800635b3  xor     edx, edx; Val
0x1800635b5  mov     [rsp+2A0h+var_270], r15
0x1800635ba  mov     r8d, 200h; Size
0x1800635c0  lea     rcx, [rsp+2A0h+var_268]; void *
0x1800635c5  call    memset_0
0x1800635ca  mov     r9d, 10h
0x1800635d0  mov     [rbp+1A0h+var_68], r15
0x1800635d7  lea     rax, [rsp+2A0h+var_268]
0x1800635dc  mov     [rbp+1A0h+var_60], 100h
0x1800635e7  lea     rdx, [rbp+1A0h+var_50]
0x1800635ee  mov     [rbp+1A0h+var_58], rax
0x1800635f5  mov     rcx, rsi
0x1800635f8  lea     r8d, [r9+1]
0x1800635fc  call    _o__ui64tow_s_0
0x180063601  test    eax, eax
0x180063603  jnz     loc_18006378E
0x180063609  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x180063610  lea     rcx, [rsp+2A0h+var_270]; this
0x180063615  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18006361a  mov     ebx, eax
0x18006361c  test    eax, eax
0x18006361e  js      loc_180063737
0x180063624  mov     rdx, [rbp+1A0h+var_58]
0x18006362b  lea     r9, [rbp+1A0h+var_48]
0x180063632  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180063637  xor     r8d, r8d
0x18006363a  mov     qword ptr [rbp+1A0h+var_50], rdi
0x180063641  mov     [rbp+1A0h+var_48], r15
0x180063648  mov     [rbp+1A0h+var_40], 1
0x18006364f  call    cs:__imp_SRCacheContext_OpenSubContext
0x180063655  mov     ebx, eax
0x180063657  cmp     [rbp+1A0h+var_40], r15b
0x18006365e  jz      short loc_18006367F
0x180063660  mov     r8, qword ptr [rbp+1A0h+var_50]
0x180063667  mov     rdx, [rbp+1A0h+var_48]
0x18006366e  mov     rcx, [r8]
0x180063671  mov     [r8], rdx
0x180063674  test    rcx, rcx
0x180063677  jz      short loc_18006367F
0x180063679  call    cs:__imp_SRCacheContext_Close
0x18006367f  test    ebx, ebx
0x180063681  js      loc_1800637B0
0x180063687  cmp     [rdi], r15
0x18006368a  lea     rdx, aPackagefamilyD; "PackageFamily\\Data"
0x180063691  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180063696  setnz   al
0x180063699  mov     [r14], al
0x18006369c  call    cs:__imp_SRCacheContext_AddToCache
0x1800636a2  mov     ebx, eax
0x1800636a4  test    eax, eax
0x1800636a6  js      loc_1800637D5
0x1800636ac  mov     rcx, [rsp+2A0h+var_270]
0x1800636b1  mov     [rsp+2A0h+var_270], r15
0x1800636b6  test    rcx, rcx
0x1800636b9  jz      short loc_1800636C1
0x1800636bb  call    cs:__imp_SRCache_Free
0x1800636c1  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800636c6  mov     qword ptr [rsp+2A0h+var_280], r15
0x1800636cb  test    rcx, rcx
0x1800636ce  jz      short loc_1800636D6
0x1800636d0  call    cs:__imp_SRCacheContext_Close
0x1800636d6  xor     eax, eax
0x1800636d8  mov     rcx, [rbp+1A0h+var_28]
0x1800636df  xor     rcx, rsp; StackCookie
0x1800636e2  call    __security_check_cookie
0x1800636e7  mov     rbx, [rsp+2A0h+arg_10]
0x1800636ef  add     rsp, 280h
0x1800636f6  pop     r15
0x1800636f8  pop     r14
0x1800636fa  pop     rdi
0x1800636fb  pop     rsi
0x1800636fc  pop     rbp
0x1800636fd  retn
0x1800636fe  mov     ebx, 80670012h
0x180063703  mov     edx, 102h; void *
0x180063708  mov     rcx, [rbp+1A8h]; this
0x18006370f  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x180063716  mov     r9d, ebx; char *
0x180063719  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006371e  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180063723  mov     qword ptr [rsp+2A0h+var_280], r15
0x180063728  test    rcx, rcx
0x18006372b  jz      short loc_180063733
0x18006372d  call    cs:__imp_SRCacheContext_Close
0x180063733  mov     eax, ebx
0x180063735  jmp     short loc_1800636D8
0x180063737  mov     edx, 105h; void *
0x18006373c  mov     rcx, [rbp+1A8h]; this
0x180063743  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18006374a  mov     r9d, ebx; char *
0x18006374d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063752  mov     rcx, [rsp+2A0h+var_270]
0x180063757  mov     [rsp+2A0h+var_270], r15
0x18006375c  test    rcx, rcx
0x18006375f  jz      short loc_18006371E
0x180063761  call    cs:__imp_SRCache_Free
0x180063767  jmp     short loc_18006371E
0x180063769  mov     rcx, [rbp+1A8h]; this
0x180063770  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x180063777  mov     r9d, ebx; char *
0x18006377a  mov     edx, 18Ch; void *
0x18006377f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063784  mov     edx, 101h
0x180063789  jmp     loc_180063708
0x18006378e  mov     rcx, [rbp+1A8h]; this
0x180063795  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18006379c  mov     ebx, 8000FFFFh
0x1800637a1  mov     edx, 166h; void *
0x1800637a6  mov     r9d, ebx; char *
0x1800637a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800637ae  jmp     short loc_180063737
0x1800637b0  mov     rcx, [rbp+1A8h]; this
0x1800637b7  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800637be  mov     r9d, ebx; char *
0x1800637c1  mov     edx, 1B0h; void *
0x1800637c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800637cb  mov     edx, 106h
0x1800637d0  jmp     loc_18006373C
0x1800637d5  mov     rcx, [rbp+1A8h]; this
0x1800637dc  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800637e3  mov     r9d, ebx; char *
0x1800637e6  mov     edx, 1A6h; void *
0x1800637eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800637f0  mov     edx, 108h
0x1800637f5  jmp     loc_18006373C
```
