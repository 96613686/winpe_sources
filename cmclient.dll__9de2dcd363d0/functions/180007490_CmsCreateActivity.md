# CmsCreateActivity

- ea: `0x180007490`
- end: `0x1800075fd`
- name: `CmsCreateActivity`
- size: `365`
- prototype: `__int64 __fastcall(__int64, int, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000a660`

## callees

- `0x180001550`
- `0x180001574`
- `0x180002d88`
- `0x180003dfc`
- `0x1800066e4`
- `0x180007490`

## string_xrefs

- `0x1800075ae`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x1800075d0`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsCreateActivity(__int64 a1, int a2, _QWORD *a3)
{
  __int64 v5; // rdx
  _QWORD *v6; // rax
  __int64 v7; // rcx
  _QWORD *v8; // rbx
  int v9; // eax
  unsigned int v10; // edi
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 **v15; // [rsp+20h] [rbp-50h]
  int v16; // [rsp+30h] [rbp-40h] BYREF
  _QWORD *v17; // [rsp+38h] [rbp-38h] BYREF
  __int64 v18; // [rsp+40h] [rbp-30h] BYREF
  __int64 *v19; // [rsp+48h] [rbp-28h] BYREF
  __int64 *v20; // [rsp+50h] [rbp-20h] BYREF
  __int64 v21; // [rsp+58h] [rbp-18h] BYREF
  __int64 v22; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v16 = a2;
  if ( a1 )
  {
    if ( !a2 || a2 >= 31003 )
    {
      v5 = 664;
      goto LABEL_15;
    }
    if ( !a3 )
    {
      v5 = 665;
      goto LABEL_15;
    }
    v6 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v6;
    if ( v6 )
    {
      *v6 = 0;
      v6[1] = 0;
      v6[3] = 0;
      v17 = v6;
      v6[2] = 0;
      v18 = 0;
      v22 = 0;
      v19 = &v18;
      v20 = &v22;
      v21 = *(_QWORD *)(a1 + 24);
      v15 = &v19;
      v9 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_ACTIVITY_ID,_WNF_STATE_NAME *,void * *),void *,enum _CMS_ACTIVITY_ID &,_WNF_STATE_NAME *,void * *>(
             v7,
             &v21,
             &v16,
             &v20);
      v10 = v9;
      if ( v9 >= 0 )
      {
        v13 = v18;
        *v8 = a1;
        _InterlockedIncrement((volatile signed __int32 *)(a1 + 20));
        v10 = 0;
        v8[2] = v22;
        v8[1] = v13;
        *a3 = v8;
        v17 = 0;
LABEL_13:
        wistd::unique_ptr<Container::Manager::Client::OutOfProcClientActivity,wistd::default_delete<Container::Manager::Client::OutOfProcClientActivity>>::~unique_ptr<Container::Manager::Client::OutOfProcClientActivity,wistd::default_delete<Container::Manager::Client::OutOfProcClientActivity>>(&v17);
        return v10;
      }
      v11 = (unsigned int)v9;
      v12 = 687;
    }
    else
    {
      v10 = -2147024882;
      v17 = 0;
      v11 = 2147942414LL;
      v12 = 674;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)v11,
      (int)v15);
    goto LABEL_13;
  }
  v5 = 663;
LABEL_15:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)0x80070057LL,
    (int)v15);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180007490  push    rbp
0x180007492  push    rbx
0x180007493  push    rsi
0x180007494  push    rdi
0x180007495  push    r14
0x180007497  mov     rbp, rsp
0x18000749a  sub     rsp, 70h
0x18000749e  mov     rax, cs:__security_cookie
0x1800074a5  xor     rax, rsp
0x1800074a8  mov     [rbp+var_8], rax
0x1800074ac  mov     [rbp+var_40], edx
0x1800074af  mov     r14, r8
0x1800074b2  mov     rsi, rcx
0x1800074b5  test    rcx, rcx
0x1800074b8  jnz     short loc_1800074C4
0x1800074ba  mov     edx, 297h
0x1800074bf  jmp     loc_1800075CC
0x1800074c4  test    edx, edx
0x1800074c6  jz      loc_1800075C7
0x1800074cc  cmp     edx, 791Bh
0x1800074d2  jge     loc_1800075C7
0x1800074d8  test    r14, r14
0x1800074db  jnz     short loc_1800074E7
0x1800074dd  mov     edx, 299h
0x1800074e2  jmp     loc_1800075CC
0x1800074e7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800074ee  mov     ecx, 20h ; ' '; unsigned __int64
0x1800074f3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800074f8  mov     rbx, rax
0x1800074fb  test    rax, rax
0x1800074fe  jz      loc_180007595
0x180007504  mov     qword ptr [rax], 0
0x18000750b  lea     r9, [rbp+var_20]
0x18000750f  mov     qword ptr [rax+8], 0
0x180007517  lea     r8, [rbp+var_40]
0x18000751b  mov     qword ptr [rax+18h], 0
0x180007523  lea     rdx, [rbp+var_18]
0x180007527  xor     eax, eax
0x180007529  mov     [rbp+var_38], rbx
0x18000752d  mov     [rbx+10h], rax
0x180007531  mov     [rbp+var_30], rax
0x180007535  mov     [rbp+var_10], rax
0x180007539  lea     rax, [rbp+var_30]
0x18000753d  mov     [rbp+var_28], rax
0x180007541  lea     rax, [rbp+var_10]
0x180007545  mov     [rbp+var_20], rax
0x180007549  mov     rax, [rsi+18h]
0x18000754d  mov     [rbp+var_18], rax
0x180007551  lea     rax, [rbp+var_28]
0x180007555  mov     [rsp+70h+var_50], rax
0x18000755a  call    ??$InvokeStubFunction@P6AJPEAXW4_CMS_ACTIVITY_ID@@PEAU_WNF_STATE_NAME@@PEAPEAX@ZPEAXAEAW41@PEAU2@PEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXW4_CMS_ACTIVITY_ID@@PEAU_WNF_STATE_NAME@@PEAPEAX@Z$$QEAPEAXAEAW43@$$QEAPEAU4@$$QEAPEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_ACTIVITY_ID,_WNF_STATE_NAME *,void * *),void *,_CMS_ACTIVITY_ID &,_WNF_STATE_NAME *,void * *>(long (*)(void *,_CMS_ACTIVITY_ID,_WNF_STATE_NAME *,void * *),void * &&,_CMS_ACTIVITY_ID &,_WNF_STATE_NAME * &&,void * * &&)
0x18000755f  mov     edi, eax
0x180007561  test    eax, eax
0x180007563  jns     short loc_18000756F
0x180007565  mov     r9d, eax
0x180007568  mov     edx, 2AFh
0x18000756d  jmp     short loc_1800075AA
0x18000756f  mov     rcx, [rbp+var_30]
0x180007573  mov     [rbx], rsi
0x180007576  lock inc dword ptr [rsi+14h]
0x18000757a  mov     rax, [rbp+var_10]
0x18000757e  xor     edi, edi
0x180007580  mov     [rbx+10h], rax
0x180007584  mov     [rbx+8], rcx
0x180007588  mov     [r14], rbx
0x18000758b  mov     [rbp+var_38], 0
0x180007593  jmp     short loc_1800075BA
0x180007595  mov     edi, 8007000Eh
0x18000759a  mov     [rbp+var_38], 0
0x1800075a2  mov     r9d, edi; char *
0x1800075a5  mov     edx, 2A2h; void *
0x1800075aa  mov     rcx, [rbp+28h]; this
0x1800075ae  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x1800075b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800075ba  lea     rcx, [rbp+var_38]
0x1800075be  call    ??1?$unique_ptr@VOutOfProcClientActivity@Client@Manager@Container@@U?$default_delete@VOutOfProcClientActivity@Client@Manager@Container@@@wistd@@@wistd@@QEAA@XZ; wistd::unique_ptr<Container::Manager::Client::OutOfProcClientActivity,wistd::default_delete<Container::Manager::Client::OutOfProcClientActivity>>::~unique_ptr<Container::Manager::Client::OutOfProcClientActivity,wistd::default_delete<Container::Manager::Client::OutOfProcClientActivity>>(void)
0x1800075c3  mov     eax, edi
0x1800075c5  jmp     short loc_1800075E6
0x1800075c7  mov     edx, 298h; void *
0x1800075cc  mov     rcx, [rbp+28h]; this
0x1800075d0  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x1800075d7  mov     ebx, 80070057h
0x1800075dc  mov     r9d, ebx; char *
0x1800075df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800075e4  mov     eax, ebx
0x1800075e6  mov     rcx, [rbp+var_8]
0x1800075ea  xor     rcx, rsp; StackCookie
0x1800075ed  call    __security_check_cookie
0x1800075f2  add     rsp, 70h
0x1800075f6  pop     r14
0x1800075f8  pop     rdi
0x1800075f9  pop     rsi
0x1800075fa  pop     rbx
0x1800075fb  pop     rbp
0x1800075fc  retn
```
