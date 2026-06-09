# PROTOCOL_SUPPORT_META_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *)

- ea: `0x1800016b0`
- end: `0x180001aaa`
- name: `?Initialize@PROTOCOL_SUPPORT_META_CONTEXT@@QEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `1018`
- prototype: `__int64 __fastcall(PROTOCOL_SUPPORT_META_CONTEXT *__hidden this, struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001290`

## callees

- `0x1800016b0`
- `0x180002760`
- `0x180005010`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x180001a7f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001a7f`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800018e9`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180001916`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18000310f`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180003134`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800018e9`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180001916`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18000310f`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180003134`
- `iisutil!?Append@MULTISZA@@QEAAHAEAVSTRA@@@Z` at `0x1800018ff`
- `iisutil!?Append@MULTISZA@@QEAAHAEAVSTRA@@@Z` at `0x18000192c`
- `iisutil!?Append@MULTISZA@@QEAAHAEAVSTRA@@@Z` at `0x180003121`
- `iisutil!?Append@MULTISZA@@QEAAHAEAVSTRA@@@Z` at `0x180003149`
- `iisutil!?Append@MULTISZA@@QEAAHAEAVSTRA@@@Z` at `0x1800018ff`
- `iisutil!?Append@MULTISZA@@QEAAHAEAVSTRA@@@Z` at `0x18000192c`
- `iisutil!?Append@MULTISZA@@QEAAHAEAVSTRA@@@Z` at `0x180003121`
- `iisutil!?Append@MULTISZA@@QEAAHAEAVSTRA@@@Z` at `0x180003149`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180001724`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180001724`

## string_xrefs

- `0x180001797`: `system.webServer/httpProtocol`

## pseudocode

```c
__int64 __fastcall PROTOCOL_SUPPORT_META_CONTEXT::Initialize(
        PROTOCOL_SUPPORT_META_CONTEXT *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  __int64 (__fastcall ***v6)(_QWORD); // rax
  __int64 v7; // r14
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rax
  int v9; // ebx
  unsigned int v10; // edi
  unsigned int v11; // edi
  unsigned int v13; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v15; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v16; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v17; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v18; // [rsp+68h] [rbp-98h] BYREF
  const unsigned __int16 *v19; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v20; // [rsp+78h] [rbp-88h] BYREF
  __int64 v21; // [rsp+80h] [rbp-80h] BYREF
  __int64 v22; // [rsp+88h] [rbp-78h] BYREF
  __int64 v23; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v24[56]; // [rsp+98h] [rbp-68h] BYREF
  char v25[64]; // [rsp+D0h] [rbp-30h] BYREF

  v23 = 0;
  v16 = 0;
  v18 = 0;
  v22 = 0;
  v15 = 0;
  v17 = 0;
  v21 = 0;
  v14 = 0;
  v19 = 0;
  v20 = 0;
  v13 = 0;
  STRA::STRA((STRA *)v24, v25, 0x40u);
  v6 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 160LL))(a2);
  v7 = (**v6)(v6);
  v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 56LL))(s_pGlobalInfo);
  v9 = (**v8)(v8, &IID_INativeConfigurationSystem, &v23);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v23 + 24LL))(
           v23,
           L"system.webServer/httpProtocol",
           v7,
           &v16,
           a3,
           0);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v16 + 72LL))(
             v16,
             L"allowKeepAlive",
             (char *)this + 232,
             0,
             0);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v16 + 32LL))(
               v16,
               L"customHeaders",
               &v22);
        if ( v9 >= 0 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 40LL))(v22, &v18);
          if ( v9 >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v18 + 24LL))(v18, &v13);
            if ( v9 >= 0 )
            {
              v10 = 0;
              if ( v13 )
              {
                while ( 1 )
                {
                  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v18 + 32LL))(v18, v10, &v15);
                  if ( v9 < 0 )
                    break;
                  v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v15 + 64LL))(
                         v15,
                         L"name",
                         &v19,
                         0,
                         0);
                  if ( v9 < 0 )
                    break;
                  v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v15 + 64LL))(
                         v15,
                         L"value",
                         &v20,
                         0,
                         0);
                  if ( v9 < 0 )
                    break;
                  if ( (int)STRA::CopyW((STRA *)v24, v19) < 0
                    || !MULTISZA::Append((PROTOCOL_SUPPORT_META_CONTEXT *)((char *)this + 8), (struct STRA *)v24)
                    || (int)STRA::CopyW((STRA *)v24, v20) < 0
                    || !MULTISZA::Append((PROTOCOL_SUPPORT_META_CONTEXT *)((char *)this + 64), (struct STRA *)v24) )
                  {
LABEL_46:
                    v9 = -2147024888;
                    break;
                  }
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
                  ++v10;
                  v15 = 0;
                  if ( v10 >= v13 )
                    goto LABEL_16;
                }
              }
              else
              {
LABEL_16:
                v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v16 + 32LL))(
                       v16,
                       L"redirectHeaders",
                       &v21);
                if ( v9 >= 0 )
                {
                  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 40LL))(v21, &v17);
                  if ( v9 >= 0 )
                  {
                    v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v17 + 24LL))(v17, &v13);
                    if ( v9 >= 0 )
                    {
                      v11 = 0;
                      if ( v13 )
                      {
                        while ( 1 )
                        {
                          v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v17 + 32LL))(
                                 v17,
                                 v11,
                                 &v14);
                          if ( v9 < 0 )
                            break;
                          v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v14 + 64LL))(
                                 v14,
                                 L"name",
                                 &v19,
                                 0,
                                 0);
                          if ( v9 < 0 )
                            break;
                          v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v14 + 64LL))(
                                 v14,
                                 L"value",
                                 &v20,
                                 0,
                                 0);
                          if ( v9 < 0 )
                            break;
                          if ( (int)STRA::CopyW((STRA *)v24, v19) < 0
                            || !MULTISZA::Append(
                                  (PROTOCOL_SUPPORT_META_CONTEXT *)((char *)this + 120),
                                  (struct STRA *)v24)
                            || (int)STRA::CopyW((STRA *)v24, v20) < 0
                            || !MULTISZA::Append(
                                  (PROTOCOL_SUPPORT_META_CONTEXT *)((char *)this + 176),
                                  (struct STRA *)v24) )
                          {
                            goto LABEL_46;
                          }
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
                          ++v11;
                          v14 = 0;
                          if ( v11 >= v13 )
                            goto LABEL_22;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
LABEL_22:
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  STRA::~STRA((STRA *)v24);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800016b0  mov     [rsp-8+arg_18], rbx
0x1800016b5  push    rbp
0x1800016b6  push    rsi
0x1800016b7  push    rdi
0x1800016b8  push    r14
0x1800016ba  push    r15
0x1800016bc  lea     rbp, [rsp-20h]
0x1800016c1  sub     rsp, 120h
0x1800016c8  mov     rax, cs:__security_cookie
0x1800016cf  xor     rax, rsp
0x1800016d2  mov     [rbp+40h+var_30], rax
0x1800016d6  xor     r15d, r15d
0x1800016d9  mov     rdi, r8
0x1800016dc  mov     rbx, rdx
0x1800016df  mov     [rbp+40h+var_B0], r15
0x1800016e3  mov     rsi, rcx
0x1800016e6  mov     [rsp+140h+var_E8], r15
0x1800016eb  mov     r8d, 40h ; '@'
0x1800016f1  mov     [rsp+140h+var_D8], r15
0x1800016f6  lea     rdx, [rbp+40h+var_70]
0x1800016fa  mov     [rbp+40h+var_B8], r15
0x1800016fe  lea     rcx, [rbp+40h+var_A8]
0x180001702  mov     [rsp+140h+var_F0], r15
0x180001707  mov     [rsp+140h+var_E0], r15
0x18000170c  mov     [rbp+40h+var_C0], r15
0x180001710  mov     [rsp+140h+var_F8], r15
0x180001715  mov     [rsp+140h+var_D0], r15
0x18000171a  mov     [rsp+140h+var_C8], r15
0x18000171f  mov     [rsp+140h+var_100], r15d
0x180001724  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000172a  mov     rax, [rbx]
0x18000172d  mov     rcx, rbx
0x180001730  mov     rax, [rax+0A0h]
0x180001737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000173c  mov     rdx, rax
0x18000173f  mov     rcx, [rax]
0x180001742  mov     rax, [rcx]
0x180001745  mov     rcx, rdx
0x180001748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000174d  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x180001754  mov     r14, rax
0x180001757  mov     rdx, [rcx]
0x18000175a  mov     rax, [rdx+38h]
0x18000175e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001763  mov     r9, rax
0x180001766  lea     r8, [rbp+40h+var_B0]
0x18000176a  lea     rdx, IID_INativeConfigurationSystem
0x180001771  mov     rcx, [rax]
0x180001774  mov     rax, [rcx]
0x180001777  mov     rcx, r9
0x18000177a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000177f  mov     ebx, eax
0x180001781  test    eax, eax
0x180001783  js      loc_1800019C3
0x180001789  mov     rcx, [rbp+40h+var_B0]
0x18000178d  lea     r9, [rsp+140h+var_E8]
0x180001792  mov     [rsp+140h+var_118], r15
0x180001797  lea     rdx, aSystemWebserve; "system.webServer/httpProtocol"
0x18000179e  mov     r8, r14
0x1800017a1  mov     [rsp+140h+var_120], rdi
0x1800017a6  mov     rax, [rcx]
0x1800017a9  mov     rax, [rax+18h]
0x1800017ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017b2  mov     ebx, eax
0x1800017b4  test    eax, eax
0x1800017b6  js      loc_1800019C3
0x1800017bc  mov     rcx, [rsp+140h+var_E8]
0x1800017c1  lea     r8, [rsi+0E8h]
0x1800017c8  xor     r9d, r9d
0x1800017cb  mov     [rsp+140h+var_120], r15
0x1800017d0  lea     rdx, aAllowkeepalive; "allowKeepAlive"
0x1800017d7  mov     rax, [rcx]
0x1800017da  mov     rax, [rax+48h]
0x1800017de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017e3  mov     ebx, eax
0x1800017e5  test    eax, eax
0x1800017e7  js      loc_1800019C3
0x1800017ed  mov     rcx, [rsp+140h+var_E8]
0x1800017f2  lea     r8, [rbp+40h+var_B8]
0x1800017f6  lea     rdx, aCustomheaders; "customHeaders"
0x1800017fd  mov     rax, [rcx]
0x180001800  mov     rax, [rax+20h]
0x180001804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001809  mov     ebx, eax
0x18000180b  test    eax, eax
0x18000180d  js      loc_1800019C3
0x180001813  mov     rcx, [rbp+40h+var_B8]
0x180001817  lea     rdx, [rsp+140h+var_D8]
0x18000181c  mov     rax, [rcx]
0x18000181f  mov     rax, [rax+28h]
0x180001823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001828  mov     ebx, eax
0x18000182a  test    eax, eax
0x18000182c  js      loc_1800019C3
0x180001832  mov     rcx, [rsp+140h+var_D8]
0x180001837  lea     rdx, [rsp+140h+var_100]
0x18000183c  mov     rax, [rcx]
0x18000183f  mov     rax, [rax+18h]
0x180001843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001848  mov     ebx, eax
0x18000184a  test    eax, eax
0x18000184c  js      loc_1800019C3
0x180001852  mov     edi, r15d
0x180001855  cmp     [rsp+140h+var_100], r15d
0x18000185a  jbe     loc_18000195C
0x180001860  mov     rcx, [rsp+140h+var_D8]
0x180001865  lea     r8, [rsp+140h+var_F0]
0x18000186a  mov     edx, edi
0x18000186c  mov     rax, [rcx]
0x18000186f  mov     rax, [rax+20h]
0x180001873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001878  mov     ebx, eax
0x18000187a  test    eax, eax
0x18000187c  js      loc_1800019C3
0x180001882  mov     rcx, [rsp+140h+var_F0]
0x180001887  lea     r8, [rsp+140h+var_D0]
0x18000188c  xor     r9d, r9d
0x18000188f  mov     [rsp+140h+var_120], r15
0x180001894  lea     rdx, aName; "name"
0x18000189b  mov     rax, [rcx]
0x18000189e  mov     rax, [rax+40h]
0x1800018a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018a7  mov     ebx, eax
0x1800018a9  test    eax, eax
0x1800018ab  js      loc_1800019C3
0x1800018b1  mov     rcx, [rsp+140h+var_F0]
0x1800018b6  lea     r8, [rsp+140h+var_C8]
0x1800018bb  xor     r9d, r9d
0x1800018be  mov     [rsp+140h+var_120], r15
0x1800018c3  lea     rdx, aValue; "value"
0x1800018ca  mov     rax, [rcx]
0x1800018cd  mov     rax, [rax+40h]
0x1800018d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018d6  mov     ebx, eax
0x1800018d8  test    eax, eax
0x1800018da  js      loc_1800019C3
0x1800018e0  mov     rdx, [rsp+140h+var_D0]
0x1800018e5  lea     rcx, [rbp+40h+var_A8]
0x1800018e9  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x1800018ef  test    eax, eax
0x1800018f1  js      loc_18000317A
0x1800018f7  lea     rcx, [rsi+8]
0x1800018fb  lea     rdx, [rbp+40h+var_A8]
0x1800018ff  call    cs:__imp_?Append@MULTISZA@@QEAAHAEAVSTRA@@@Z; MULTISZA::Append(STRA &)
0x180001905  test    eax, eax
0x180001907  jz      loc_18000317A
0x18000190d  mov     rdx, [rsp+140h+var_C8]
0x180001912  lea     rcx, [rbp+40h+var_A8]
0x180001916  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x18000191c  test    eax, eax
0x18000191e  js      loc_18000317A
0x180001924  lea     rcx, [rsi+40h]
0x180001928  lea     rdx, [rbp+40h+var_A8]
0x18000192c  call    cs:__imp_?Append@MULTISZA@@QEAAHAEAVSTRA@@@Z; MULTISZA::Append(STRA &)
0x180001932  test    eax, eax
0x180001934  jz      loc_18000317A
0x18000193a  mov     rcx, [rsp+140h+var_F0]
0x18000193f  mov     rax, [rcx]
0x180001942  mov     rax, [rax+10h]
0x180001946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000194b  inc     edi
0x18000194d  mov     [rsp+140h+var_F0], r15
0x180001952  cmp     edi, [rsp+140h+var_100]
0x180001956  jb      loc_180001860
0x18000195c  mov     rcx, [rsp+140h+var_E8]
0x180001961  lea     r8, [rbp+40h+var_C0]
0x180001965  lea     rdx, aRedirectheader; "redirectHeaders"
0x18000196c  mov     rax, [rcx]
0x18000196f  mov     rax, [rax+20h]
0x180001973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001978  mov     ebx, eax
0x18000197a  test    eax, eax
0x18000197c  js      short loc_1800019C3
0x18000197e  mov     rcx, [rbp+40h+var_C0]
0x180001982  lea     rdx, [rsp+140h+var_E0]
0x180001987  mov     rax, [rcx]
0x18000198a  mov     rax, [rax+28h]
0x18000198e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001993  mov     ebx, eax
0x180001995  test    eax, eax
0x180001997  js      short loc_1800019C3
0x180001999  mov     rcx, [rsp+140h+var_E0]
0x18000199e  lea     rdx, [rsp+140h+var_100]
0x1800019a3  mov     rax, [rcx]
0x1800019a6  mov     rax, [rax+18h]
0x1800019aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019af  mov     ebx, eax
0x1800019b1  test    eax, eax
0x1800019b3  js      short loc_1800019C3
0x1800019b5  mov     edi, r15d
0x1800019b8  cmp     [rsp+140h+var_100], r15d
0x1800019bd  ja      loc_180003086
0x1800019c3  mov     rcx, [rsp+140h+var_F8]
0x1800019c8  test    rcx, rcx
0x1800019cb  jnz     loc_180003184
0x1800019d1  mov     rcx, [rsp+140h+var_E0]
0x1800019d6  test    rcx, rcx
0x1800019d9  jz      short loc_1800019EC
0x1800019db  mov     rax, [rcx]
0x1800019de  mov     rax, [rax+10h]
0x1800019e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019e7  mov     [rsp+140h+var_E0], r15
0x1800019ec  mov     rcx, [rbp+40h+var_C0]
0x1800019f0  test    rcx, rcx
0x1800019f3  jz      short loc_180001A05
0x1800019f5  mov     rax, [rcx]
0x1800019f8  mov     rax, [rax+10h]
0x1800019fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a01  mov     [rbp+40h+var_C0], r15
0x180001a05  mov     rcx, [rsp+140h+var_F0]
0x180001a0a  test    rcx, rcx
0x180001a0d  jnz     loc_18000319A
0x180001a13  mov     rcx, [rsp+140h+var_D8]
0x180001a18  test    rcx, rcx
0x180001a1b  jz      short loc_180001A2E
0x180001a1d  mov     rax, [rcx]
0x180001a20  mov     rax, [rax+10h]
0x180001a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a29  mov     [rsp+140h+var_D8], r15
0x180001a2e  mov     rcx, [rbp+40h+var_B8]
0x180001a32  test    rcx, rcx
0x180001a35  jz      short loc_180001A47
0x180001a37  mov     rax, [rcx]
0x180001a3a  mov     rax, [rax+10h]
0x180001a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a43  mov     [rbp+40h+var_B8], r15
0x180001a47  mov     rcx, [rsp+140h+var_E8]
0x180001a4c  test    rcx, rcx
0x180001a4f  jz      short loc_180001A62
0x180001a51  mov     rax, [rcx]
0x180001a54  mov     rax, [rax+10h]
0x180001a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a5d  mov     [rsp+140h+var_E8], r15
0x180001a62  mov     rcx, [rbp+40h+var_B0]
0x180001a66  test    rcx, rcx
0x180001a69  jz      short loc_180001A7B
0x180001a6b  mov     rax, [rcx]
0x180001a6e  mov     rax, [rax+10h]
0x180001a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a77  mov     [rbp+40h+var_B0], r15
0x180001a7b  lea     rcx, [rbp+40h+var_A8]
0x180001a7f  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180001a85  mov     eax, ebx
0x180001a87  mov     rcx, [rbp+40h+var_30]
0x180001a8b  xor     rcx, rsp; StackCookie
0x180001a8e  call    __security_check_cookie
0x180001a93  mov     rbx, [rsp+140h+arg_18]
0x180001a9b  add     rsp, 120h
0x180001aa2  pop     r15
0x180001aa4  pop     r14
0x180001aa6  pop     rdi
0x180001aa7  pop     rsi
0x180001aa8  pop     rbp
0x180001aa9  retn
0x180003086  mov     rcx, [rsp+140h+var_E0]
0x18000308b  lea     r8, [rsp+140h+var_F8]
0x180003090  mov     edx, edi
0x180003092  mov     rax, [rcx]
0x180003095  mov     rax, [rax+20h]
0x180003099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000309e  mov     ebx, eax
0x1800030a0  test    eax, eax
0x1800030a2  js      loc_1800019C3
0x1800030a8  mov     rcx, [rsp+140h+var_F8]
0x1800030ad  lea     r8, [rsp+140h+var_D0]
0x1800030b2  xor     r9d, r9d
0x1800030b5  mov     [rsp+140h+var_120], r15
0x1800030ba  lea     rdx, aName; "name"
0x1800030c1  mov     rax, [rcx]
0x1800030c4  mov     rax, [rax+40h]
0x1800030c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030cd  mov     ebx, eax
0x1800030cf  test    eax, eax
0x1800030d1  js      loc_1800019C3
0x1800030d7  mov     rcx, [rsp+140h+var_F8]
0x1800030dc  lea     r8, [rsp+140h+var_C8]
0x1800030e1  xor     r9d, r9d
0x1800030e4  mov     [rsp+140h+var_120], r15
0x1800030e9  lea     rdx, aValue; "value"
0x1800030f0  mov     rax, [rcx]
0x1800030f3  mov     rax, [rax+40h]
0x1800030f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030fc  mov     ebx, eax
0x1800030fe  test    eax, eax
0x180003100  js      loc_1800019C3
0x180003106  mov     rdx, [rsp+140h+var_D0]
0x18000310b  lea     rcx, [rbp+40h+var_A8]
0x18000310f  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x180003115  test    eax, eax
0x180003117  js      short loc_18000317A
0x180003119  lea     rcx, [rsi+78h]
0x18000311d  lea     rdx, [rbp+40h+var_A8]
0x180003121  call    cs:__imp_?Append@MULTISZA@@QEAAHAEAVSTRA@@@Z; MULTISZA::Append(STRA &)
0x180003127  test    eax, eax
0x180003129  jz      short loc_18000317A
0x18000312b  mov     rdx, [rsp+140h+var_C8]
0x180003130  lea     rcx, [rbp+40h+var_A8]
0x180003134  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x18000313a  test    eax, eax
0x18000313c  js      short loc_18000317A
  ... truncated ...
```
