# CmsServicingCreateStorageTransacted

- ea: `0x18000d260`
- end: `0x18000d37f`
- name: `CmsServicingCreateStorageTransacted`
- size: `287`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x180001550`
- `0x180001574`
- `0x180001944`
- `0x1800066e4`
- `0x18000cd0c`
- `0x18000d260`

## string_xrefs

- `0x18000d30c`: `onecore\base\gendrv\silos\clem\client\dll\servicingapi.cpp`
- `0x18000d34c`: `onecore\base\gendrv\silos\clem\client\dll\servicingapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsServicingCreateStorageTransacted(__int64 a1, int a2, __int64 a3, _QWORD *a4)
{
  char *v6; // rax
  int v7; // ecx
  char *v8; // rbx
  int v9; // eax
  unsigned int v10; // edi
  __int64 result; // rax
  int v12; // [rsp+20h] [rbp-29h]
  int v13; // [rsp+20h] [rbp-29h]
  int v14; // [rsp+30h] [rbp-19h] BYREF
  __int64 v15; // [rsp+38h] [rbp-11h] BYREF
  __int64 *v16; // [rsp+40h] [rbp-9h] BYREF
  int v17[2]; // [rsp+48h] [rbp-1h] BYREF
  __int64 v18; // [rsp+50h] [rbp+7h] BYREF
  __int64 v19; // [rsp+58h] [rbp+Fh] BYREF
  __int128 v20; // [rsp+60h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v14 = a2;
  v18 = a3;
  v6 = (char *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v6;
  if ( v6 )
  {
    *(_QWORD *)v6 = 0;
    v19 = a1;
    *(GUID *)(v6 + 8) = GUID_NULL;
    v15 = 0;
    v16 = &v15;
    *(_QWORD *)v17 = &v20;
    v20 = 0;
    v9 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_CLIENT_ID,_GUID *,_GUID *,void * *),void * &,enum _CMS_CLIENT_ID &,_GUID * &,_GUID *,void * *>(
           v7,
           (unsigned int)&v19,
           (unsigned int)&v14,
           (unsigned int)&v18,
           (__int64)v17,
           (__int64)&v16);
    v10 = v9;
    if ( v9 >= 0 )
    {
      *(_QWORD *)v8 = v15;
      result = 0;
      *(_OWORD *)(v8 + 8) = v20;
      *a4 = v8;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15F,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\servicingapi.cpp",
        (const char *)(unsigned int)v9,
        v13);
      operator delete(v8, (const struct std::nothrow_t *)0x18);
      return v10;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14F,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\servicingapi.cpp",
      (const char *)0x8007000ELL,
      v12);
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000d260  push    rbp
0x18000d262  push    rbx
0x18000d263  push    rsi
0x18000d264  push    rdi
0x18000d265  lea     rbp, [rsp-3Fh]
0x18000d26a  sub     rsp, 88h
0x18000d271  mov     rax, cs:__security_cookie
0x18000d278  xor     rax, rsp
0x18000d27b  mov     [rbp+57h+var_30], rax
0x18000d27f  mov     rdi, rcx
0x18000d282  mov     [rbp+57h+var_70], edx
0x18000d285  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d28c  mov     [rbp+57h+var_50], r8
0x18000d290  mov     ecx, 18h; unsigned __int64
0x18000d295  mov     rsi, r9
0x18000d298  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d29d  mov     rbx, rax
0x18000d2a0  test    rax, rax
0x18000d2a3  jz      loc_18000D348
0x18000d2a9  mov     qword ptr [rax], 0
0x18000d2b0  lea     r9, [rbp+57h+var_50]
0x18000d2b4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000d2bb  lea     r8, [rbp+57h+var_70]
0x18000d2bf  mov     [rbp+57h+var_48], rdi
0x18000d2c3  lea     rdx, [rbp+57h+var_48]
0x18000d2c7  movdqu  xmmword ptr [rax+8], xmm0
0x18000d2cc  lea     rax, [rbp+57h+var_68]
0x18000d2d0  mov     [rbp+57h+var_68], 0
0x18000d2d8  mov     [rbp+57h+var_60], rax
0x18000d2dc  xorps   xmm0, xmm0
0x18000d2df  lea     rax, [rbp+57h+var_40]
0x18000d2e3  mov     qword ptr [rbp+57h+var_58], rax
0x18000d2e7  lea     rax, [rbp+57h+var_60]
0x18000d2eb  mov     [rsp+0A0h+var_78], rax
0x18000d2f0  lea     rax, [rbp+57h+var_58]
0x18000d2f4  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x18000d2f9  movups  [rbp+57h+var_40], xmm0
0x18000d2fd  call    ??$InvokeStubFunction@P6AJPEAXW4_CMS_CLIENT_ID@@PEAU_GUID@@2PEAPEAX@ZAEAPEAXAEAW41@AEAPEAU2@PEAU2@PEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXW4_CMS_CLIENT_ID@@PEAU_GUID@@2PEAPEAX@ZAEAPEAXAEAW43@AEAPEAU4@$$QEAPEAU4@$$QEAPEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_CLIENT_ID,_GUID *,_GUID *,void * *),void * &,_CMS_CLIENT_ID &,_GUID * &,_GUID *,void * *>(long (*)(void *,_CMS_CLIENT_ID,_GUID *,_GUID *,void * *),void * &,_CMS_CLIENT_ID &,_GUID * &,_GUID * &&,void * * &&)
0x18000d302  mov     edi, eax
0x18000d304  test    eax, eax
0x18000d306  jns     short loc_18000D331
0x18000d308  mov     rcx, [rbp+5Fh]; this
0x18000d30c  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000d313  mov     r9d, eax; char *
0x18000d316  mov     edx, 15Fh; void *
0x18000d31b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d320  mov     edx, 18h; struct std::nothrow_t *
0x18000d325  mov     rcx, rbx; void *
0x18000d328  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d32d  mov     eax, edi
0x18000d32f  jmp     short loc_18000D367
0x18000d331  mov     rax, [rbp+57h+var_68]
0x18000d335  mov     [rbx], rax
0x18000d338  xor     eax, eax
0x18000d33a  movups  xmm0, [rbp+57h+var_40]
0x18000d33e  movdqu  xmmword ptr [rbx+8], xmm0
0x18000d343  mov     [rsi], rbx
0x18000d346  jmp     short loc_18000D367
0x18000d348  mov     rcx, [rbp+5Fh]; this
0x18000d34c  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000d353  mov     ebx, 8007000Eh
0x18000d358  mov     edx, 14Fh; void *
0x18000d35d  mov     r9d, ebx; char *
0x18000d360  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d365  mov     eax, ebx
0x18000d367  mov     rcx, [rbp+57h+var_30]
0x18000d36b  xor     rcx, rsp; StackCookie
0x18000d36e  call    __security_check_cookie
0x18000d373  add     rsp, 88h
0x18000d37a  pop     rdi
0x18000d37b  pop     rsi
0x18000d37c  pop     rbx
0x18000d37d  pop     rbp
0x18000d37e  retn
```
