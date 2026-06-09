# DEFDOC_META_STORED_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *)

- ea: `0x180002f2c`
- end: `0x180003204`
- name: `?Initialize@DEFDOC_META_STORED_CONTEXT@@AEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `728`
- prototype: `__int64 __fastcall(DEFDOC_META_STORED_CONTEXT *__hidden this, struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002e18`

## callees

- `0x180002f2c`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003160`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003160`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180003107`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180003107`

## pseudocode

```c
__int64 __fastcall DEFDOC_META_STORED_CONTEXT::Initialize(
        DEFDOC_META_STORED_CONTEXT *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v6)(struct IHttpContext *); // rax
  __int64 (__fastcall ***v7)(_QWORD); // rax
  __int64 v8; // r14
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rax
  signed int v10; // ebx
  __int64 v11; // rax
  unsigned int v13; // edi
  signed int LastError; // eax
  __int64 v15; // [rsp+40h] [rbp-30h] BYREF
  __int64 v16; // [rsp+48h] [rbp-28h] BYREF
  __int64 v17; // [rsp+50h] [rbp-20h] BYREF
  __int64 v18; // [rsp+58h] [rbp-18h] BYREF
  const unsigned __int16 *v19; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v20; // [rsp+A8h] [rbp+38h] BYREF
  __int64 *v21; // [rsp+B8h] [rbp+48h] BYREF

  v3 = *(_QWORD *)a2;
  v18 = 0;
  v21 = 0;
  v15 = 0;
  v6 = *(__int64 (__fastcall **)(struct IHttpContext *))(v3 + 160);
  v16 = 0;
  v17 = 0;
  v19 = 0;
  v20 = 0;
  v7 = (__int64 (__fastcall ***)(_QWORD))v6(a2);
  v8 = (**v7)(v7);
  v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
  v10 = (**v9)(v9, &IID_INativeConfigurationSystem, &v18);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 **, struct INativeSectionException **, _QWORD))(*(_QWORD *)v18 + 24LL))(
            v18,
            L"system.webServer/defaultDocument",
            v8,
            &v21,
            a3,
            0);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, char *, _QWORD, _QWORD))(*v21 + 72))(
              v21,
              L"enabled",
              (char *)this + 8,
              0,
              0);
      if ( v10 >= 0 )
      {
        v11 = *v21;
        if ( !*((_DWORD *)this + 2) )
        {
LABEL_5:
          (*(void (**)(void))(v11 + 16))();
          v21 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          return 0;
        }
        v10 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64 *))(v11 + 32))(v21, L"files", &v17);
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 40LL))(v17, &v15);
          if ( v10 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v15 + 24LL))(v15, &v20);
            if ( v10 >= 0 )
            {
              v13 = 0;
              if ( !v20 )
              {
LABEL_14:
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
                v15 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
                v17 = 0;
                v11 = *v21;
                goto LABEL_5;
              }
              while ( 1 )
              {
                v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 32LL))(v15, v13, &v16);
                if ( v10 < 0 )
                  break;
                v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v16 + 64LL))(
                        v16,
                        L"value",
                        &v19,
                        0,
                        0);
                if ( v10 < 0 )
                  break;
                if ( !MULTISZ::Append((DEFDOC_META_STORED_CONTEXT *)((char *)this + 16), v19) )
                {
                  LastError = GetLastError();
                  v10 = LastError;
                  if ( LastError > 0 )
                    v10 = (unsigned __int16)LastError | 0x80070000;
                  break;
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
                ++v13;
                v16 = 0;
                if ( v13 >= v20 )
                  goto LABEL_14;
              }
            }
          }
        }
      }
    }
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
    v21 = 0;
  }
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180002f2c  mov     [rsp-28h+arg_0], rbx
0x180002f31  push    rbp
0x180002f32  push    rsi
0x180002f33  push    rdi
0x180002f34  push    r14
0x180002f36  push    r15
0x180002f38  mov     rbp, rsp
0x180002f3b  sub     rsp, 70h
0x180002f3f  mov     rax, [rdx]
0x180002f42  xor     r15d, r15d
0x180002f45  mov     rsi, rcx
0x180002f48  mov     [rbp+var_18], r15
0x180002f4c  mov     rcx, rdx
0x180002f4f  mov     [rbp+arg_18], r15
0x180002f53  mov     rdi, r8
0x180002f56  mov     [rbp+var_30], r15
0x180002f5a  mov     rax, [rax+0A0h]
0x180002f61  mov     [rbp+var_28], r15
0x180002f65  mov     [rbp+var_20], r15
0x180002f69  mov     [rbp+var_10], r15
0x180002f6d  mov     [rbp+arg_8], r15d
0x180002f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f76  mov     rdx, rax
0x180002f79  mov     rcx, [rax]
0x180002f7c  mov     rax, [rcx]
0x180002f7f  mov     rcx, rdx
0x180002f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f87  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180002f8e  mov     r14, rax
0x180002f91  mov     rdx, [rcx]
0x180002f94  mov     rax, [rdx+38h]
0x180002f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f9d  mov     r9, rax
0x180002fa0  lea     r8, [rbp+var_18]
0x180002fa4  lea     rdx, IID_INativeConfigurationSystem
0x180002fab  mov     rcx, [rax]
0x180002fae  mov     rax, [rcx]
0x180002fb1  mov     rcx, r9
0x180002fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fb9  mov     ebx, eax
0x180002fbb  test    eax, eax
0x180002fbd  js      loc_180003175
0x180002fc3  mov     rcx, [rbp+var_18]
0x180002fc7  lea     r9, [rbp+arg_18]
0x180002fcb  mov     [rsp+70h+var_48], r15
0x180002fd0  lea     rdx, aSystemWebserve; "system.webServer/defaultDocument"
0x180002fd7  mov     r8, r14
0x180002fda  mov     [rsp+70h+var_50], rdi
0x180002fdf  mov     rax, [rcx]
0x180002fe2  mov     rax, [rax+18h]
0x180002fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002feb  mov     ebx, eax
0x180002fed  test    eax, eax
0x180002fef  js      loc_180003175
0x180002ff5  mov     rcx, [rbp+arg_18]
0x180002ff9  lea     r8, [rsi+8]
0x180002ffd  xor     r9d, r9d
0x180003000  mov     [rsp+70h+var_50], r15
0x180003005  lea     rdx, aEnabled; "enabled"
0x18000300c  mov     rax, [rcx]
0x18000300f  mov     rax, [rax+48h]
0x180003013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003018  mov     ebx, eax
0x18000301a  test    eax, eax
0x18000301c  js      loc_180003175
0x180003022  mov     rcx, [rbp+arg_18]
0x180003026  mov     rax, [rcx]
0x180003029  cmp     [rsi+8], r15d
0x18000302d  jnz     short loc_180003053
0x18000302f  mov     rax, [rax+10h]
0x180003033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003038  mov     rcx, [rbp+var_18]
0x18000303c  mov     [rbp+arg_18], r15
0x180003040  mov     rax, [rcx]
0x180003043  mov     rax, [rax+10h]
0x180003047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000304c  xor     eax, eax
0x18000304e  jmp     loc_1800031F0
0x180003053  mov     rax, [rax+20h]
0x180003057  lea     r8, [rbp+var_20]
0x18000305b  lea     rdx, aFiles; "files"
0x180003062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003067  mov     ebx, eax
0x180003069  test    eax, eax
0x18000306b  js      loc_180003175
0x180003071  mov     rcx, [rbp+var_20]
0x180003075  lea     rdx, [rbp+var_30]
0x180003079  mov     rax, [rcx]
0x18000307c  mov     rax, [rax+28h]
0x180003080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003085  mov     ebx, eax
0x180003087  test    eax, eax
0x180003089  js      loc_180003175
0x18000308f  mov     rcx, [rbp+var_30]
0x180003093  lea     rdx, [rbp+arg_8]
0x180003097  mov     rax, [rcx]
0x18000309a  mov     rax, [rax+18h]
0x18000309e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030a3  mov     ebx, eax
0x1800030a5  test    eax, eax
0x1800030a7  js      loc_180003175
0x1800030ad  mov     edi, r15d
0x1800030b0  cmp     [rbp+arg_8], r15d
0x1800030b4  jbe     short loc_18000312C
0x1800030b6  mov     rcx, [rbp+var_30]
0x1800030ba  lea     r8, [rbp+var_28]
0x1800030be  mov     edx, edi
0x1800030c0  mov     rax, [rcx]
0x1800030c3  mov     rax, [rax+20h]
0x1800030c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030cc  mov     ebx, eax
0x1800030ce  test    eax, eax
0x1800030d0  js      loc_180003175
0x1800030d6  mov     rcx, [rbp+var_28]
0x1800030da  lea     r8, [rbp+var_10]
0x1800030de  xor     r9d, r9d
0x1800030e1  mov     [rsp+70h+var_50], r15
0x1800030e6  lea     rdx, aValue; "value"
0x1800030ed  mov     rax, [rcx]
0x1800030f0  mov     rax, [rax+40h]
0x1800030f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030f9  mov     ebx, eax
0x1800030fb  test    eax, eax
0x1800030fd  js      short loc_180003175
0x1800030ff  mov     rdx, [rbp+var_10]
0x180003103  lea     rcx, [rsi+10h]
0x180003107  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x18000310d  test    eax, eax
0x18000310f  jz      short loc_180003160
0x180003111  mov     rcx, [rbp+var_28]
0x180003115  mov     rax, [rcx]
0x180003118  mov     rax, [rax+10h]
0x18000311c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003121  inc     edi
0x180003123  mov     [rbp+var_28], r15
0x180003127  cmp     edi, [rbp+arg_8]
0x18000312a  jb      short loc_1800030B6
0x18000312c  mov     rcx, [rbp+var_30]
0x180003130  mov     rax, [rcx]
0x180003133  mov     rax, [rax+10h]
0x180003137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000313c  mov     rcx, [rbp+var_20]
0x180003140  mov     [rbp+var_30], r15
0x180003144  mov     rax, [rcx]
0x180003147  mov     rax, [rax+10h]
0x18000314b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003150  mov     rcx, [rbp+arg_18]
0x180003154  mov     [rbp+var_20], r15
0x180003158  mov     rax, [rcx]
0x18000315b  jmp     loc_18000302F
0x180003160  call    cs:__imp_GetLastError
0x180003166  mov     ebx, eax
0x180003168  test    eax, eax
0x18000316a  jle     short loc_180003175
0x18000316c  movzx   ebx, ax
0x18000316f  or      ebx, 80070000h
0x180003175  mov     rcx, [rbp+var_28]
0x180003179  test    rcx, rcx
0x18000317c  jz      short loc_18000318E
0x18000317e  mov     rax, [rcx]
0x180003181  mov     rax, [rax+10h]
0x180003185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000318a  mov     [rbp+var_28], r15
0x18000318e  mov     rcx, [rbp+var_30]
0x180003192  test    rcx, rcx
0x180003195  jz      short loc_1800031A7
0x180003197  mov     rax, [rcx]
0x18000319a  mov     rax, [rax+10h]
0x18000319e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031a3  mov     [rbp+var_30], r15
0x1800031a7  mov     rcx, [rbp+var_20]
0x1800031ab  test    rcx, rcx
0x1800031ae  jz      short loc_1800031C0
0x1800031b0  mov     rax, [rcx]
0x1800031b3  mov     rax, [rax+10h]
0x1800031b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031bc  mov     [rbp+var_20], r15
0x1800031c0  mov     rcx, [rbp+arg_18]
0x1800031c4  test    rcx, rcx
0x1800031c7  jz      short loc_1800031D9
0x1800031c9  mov     rax, [rcx]
0x1800031cc  mov     rax, [rax+10h]
0x1800031d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031d5  mov     [rbp+arg_18], r15
0x1800031d9  mov     rcx, [rbp+var_18]
0x1800031dd  test    rcx, rcx
0x1800031e0  jz      short loc_1800031EE
0x1800031e2  mov     rax, [rcx]
0x1800031e5  mov     rax, [rax+10h]
0x1800031e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031ee  mov     eax, ebx
0x1800031f0  mov     rbx, [rsp+70h+arg_0]
0x1800031f8  add     rsp, 70h
0x1800031fc  pop     r15
0x1800031fe  pop     r14
0x180003200  pop     rdi
0x180003201  pop     rsi
0x180003202  pop     rbp
0x180003203  retn
```
