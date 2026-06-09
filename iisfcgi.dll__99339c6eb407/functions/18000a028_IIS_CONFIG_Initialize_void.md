# IIS_CONFIG::Initialize(void)

- ea: `0x18000a028`
- end: `0x18000a8b1`
- name: `?Initialize@IIS_CONFIG@@QEAAJXZ`
- size: `2185`
- prototype: `__int64 __fastcall(IIS_CONFIG *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b088`
- `0x18000e510`

## callees

- `0x180001008`
- `0x180009a94`
- `0x18000a028`
- `0x18000a8b8`
- `0x18000edde`
- `0x18000ee10`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a10c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a10c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000a102`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000a102`
- `iisutil!?Append@MULTISZ@@QEAAHAEAVSTRU@@@Z` at `0x18000a647`
- `iisutil!?Append@MULTISZ@@QEAAHAEAVSTRU@@@Z` at `0x18000a647`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x18000a58f`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x18000a58f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000a0da`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000a0da`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a886`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a886`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18000a0e4`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18000a0e4`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000a87c`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000a87c`
- `iisutil!SAFE_snwprintf` at `0x18000a62f`
- `iisutil!SAFE_snwprintf` at `0x18000a62f`

## string_xrefs

- `0x18000a292`: `fullPath`
- `0x18000a365`: `protocol`

## pseudocode

```c
__int64 __fastcall IIS_CONFIG::Initialize(IIS_CONFIG *this)
{
  signed int LastError; // eax
  int v3; // ebx
  struct IHttpServer *v4; // rcx
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rax
  unsigned __int64 v6; // rdi
  __int64 v7; // rax
  bool v8; // cf
  size_t v9; // rax
  unsigned __int64 *v10; // rax
  _QWORD *v11; // r14
  IIS_CONFIG_RECORD *i; // r15
  unsigned int v13; // r12d
  int v14; // r15d
  int v15; // r14d
  unsigned int j; // edi
  __int64 v17; // rdi
  __int64 v18; // rcx
  unsigned int v19; // r8d
  __int64 v20; // r9
  unsigned __int16 *v21; // rdx
  unsigned __int16 v22; // ax
  unsigned __int16 v23; // cx
  unsigned int v24; // r8d
  __int64 v25; // rcx
  void (__fastcall ***v26)(_QWORD, GUID *, char *); // rcx
  __int64 v28; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v29; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v30; // [rsp+8Ch] [rbp-74h] BYREF
  __int64 v31; // [rsp+90h] [rbp-70h] BYREF
  __int64 v32; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v33; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v34; // [rsp+A4h] [rbp-5Ch] BYREF
  int v35; // [rsp+A8h] [rbp-58h] BYREF
  int v36; // [rsp+ACh] [rbp-54h] BYREF
  int v37; // [rsp+B0h] [rbp-50h] BYREF
  int v38; // [rsp+B4h] [rbp-4Ch] BYREF
  unsigned int v39; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v40; // [rsp+BCh] [rbp-44h] BYREF
  unsigned int v41; // [rsp+C0h] [rbp-40h] BYREF
  int v42; // [rsp+C4h] [rbp-3Ch] BYREF
  int v43; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v44; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v45; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v46; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v47; // [rsp+E8h] [rbp-18h] BYREF
  void (__fastcall ***v48)(_QWORD, GUID *, char *); // [rsp+F0h] [rbp-10h] BYREF
  __int64 v49; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v50; // [rsp+100h] [rbp+0h] BYREF
  const unsigned __int16 *v51; // [rsp+108h] [rbp+8h] BYREF
  const unsigned __int16 *v52; // [rsp+110h] [rbp+10h] BYREF
  const unsigned __int16 *v53; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v54[56]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v55[56]; // [rsp+158h] [rbp+58h] BYREF
  unsigned __int16 v56[64]; // [rsp+190h] [rbp+90h] BYREF

  v47 = 0;
  v46 = 0;
  v44 = 0;
  v29 = 0;
  v28 = 0;
  v53 = 0;
  v52 = 0;
  v51 = 0;
  v43 = 0;
  v42 = 0;
  v41 = 0;
  v40 = 0;
  v39 = 0;
  v38 = 0;
  v37 = 0;
  v36 = 0;
  v35 = 0;
  v45 = 0;
  v32 = 0;
  v30 = 0;
  v31 = 0;
  v50 = 0;
  v49 = 0;
  memset_0(v56, 0, sizeof(v56));
  STRU::STRU((STRU *)v55, v56, 0x40u);
  MULTISZ::MULTISZ((MULTISZ *)v54);
  v48 = 0;
  v34 = 0;
  v33 = 0;
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 1096), 0x3E8u) )
  {
    v4 = g_pGlobalInfo;
    *((_DWORD *)this + 272) = 1;
    *((_DWORD *)this + 284) = 0;
    v5 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)v4 + 56LL))(v4);
    v3 = (**v5)(v5, &IID_INativeConfigurationSystem, &v47);
    if ( v3 >= 0 )
    {
      v3 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, void (__fastcall ****)(_QWORD, GUID *, char *), _QWORD))(*(_QWORD *)v47 + 24LL))(
             v47,
             L"system.webServer/fastCgi",
             L"MACHINE/WEBROOT/APPHOST",
             &v46,
             &v48,
             0);
      if ( v3 >= 0 )
      {
        v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v46 + 40LL))(v46, &v44);
        if ( v3 >= 0 )
        {
          v3 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v44 + 24LL))(v44, &v29);
          if ( v3 >= 0 )
          {
            v6 = v29;
            *((_DWORD *)this + 264) = v29;
            v7 = 416 * v6;
            if ( !is_mul_ok(v6, 0x1A0u) )
              v7 = -1;
            v8 = __CFADD__(v7, 8);
            v9 = v7 + 8;
            if ( v8 )
              v9 = -1;
            v10 = (unsigned __int64 *)operator new(v9);
            if ( v10 )
            {
              *v10 = v6;
              v11 = v10 + 1;
              for ( i = (IIS_CONFIG_RECORD *)(v10 + 1); v6; --v6 )
              {
                IIS_CONFIG_RECORD::IIS_CONFIG_RECORD(i);
                i = (IIS_CONFIG_RECORD *)((char *)i + 416);
              }
            }
            else
            {
              v11 = 0;
            }
            *((_QWORD *)this + 133) = v11;
            if ( v11 )
            {
              v13 = 0;
              if ( v29 )
              {
                while ( 1 )
                {
                  v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v44 + 32LL))(v44, v13, &v28);
                  if ( v3 < 0 )
                    break;
                  v3 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v28 + 64LL))(
                         v28,
                         L"fullPath",
                         &v53,
                         0,
                         0);
                  if ( v3 < 0 )
                    break;
                  v3 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v28 + 64LL))(
                         v28,
                         L"arguments",
                         &v52,
                         0,
                         0);
                  if ( v3 < 0 )
                    break;
                  v3 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v28 + 64LL))(
                         v28,
                         L"monitorChangesTo",
                         &v51,
                         0,
                         0);
                  if ( v3 < 0 )
                    break;
                  v3 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v28 + 48LL))(
                         v28,
                         L"stderrMode",
                         &v33,
                         0,
                         0);
                  if ( v3 < 0 )
                    break;
                  v14 = v33;
                  if ( v33 >= 2 && v33 - 2 > 1 )
                    goto LABEL_57;
                  v3 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v28 + 48LL))(
                         v28,
                         L"protocol",
                         &v34,
                         0,
                         0);
                  if ( v3 < 0 )
                    break;
                  v15 = v34;
                  if ( v34 > 1 )
                  {
LABEL_57:
                    v3 = -2147024883;
                    break;
                  }
                  v3 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v28 + 48LL))(
                         v28,
                         L"queueLength",
                         &v43,
                         0,
                         0);
                  if ( v3 < 0 )
                    break;
                  v3 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v28 + 48LL))(
                         v28,
                         L"maxInstances",
                         &v42,
                         0,
                         0);
                  if ( v3 < 0 )
                    break;
                  v3 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v28 + 48LL))(
                         v28,
                         L"idleTimeout",
                         &v41,
                         0,
                         0);
                  if ( v3 < 0 )
                    break;
                  v3 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v28 + 48LL))(
                         v28,
                         L"activityTimeout",
                         &v40,
                         0,
                         0);
                  if ( v3 < 0 )
                    break;
                  v3 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v28 + 48LL))(
                         v28,
                         L"requestTimeout",
                         &v39,
                         0,
                         0);
                  if ( v3 < 0 )
                    break;
                  v3 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v28 + 48LL))(
                         v28,
                         L"instanceMaxRequests",
                         &v38,
                         0,
                         0);
                  if ( v3 < 0 )
                    break;
                  v3 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v28 + 48LL))(
                         v28,
                         L"signalBeforeTerminateSeconds",
                         &v37,
                         0,
                         0);
                  if ( v3 < 0 )
                    break;
                  v3 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v28 + 72LL))(
                         v28,
                         L"flushNamedPipe",
                         &v36,
                         0,
                         0);
                  if ( v3 < 0 )
                    break;
                  v3 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v28 + 48LL))(
                         v28,
                         L"rapidFailsPerMinute",
                         &v35,
                         0,
                         0);
                  if ( v3 < 0 )
                    break;
                  v3 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v28 + 32LL))(
                         v28,
                         L"environmentVariables",
                         &v45);
                  if ( v3 < 0 )
                    break;
                  v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 40LL))(v45, &v32);
                  if ( v3 < 0 )
                    break;
                  v3 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v32 + 24LL))(v32, &v30);
                  if ( v3 < 0 )
                    break;
                  MULTISZ::Reset((MULTISZ *)v54);
                  for ( j = 0; j < v30; v31 = 0 )
                  {
                    v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v32 + 32LL))(v32, j, &v31);
                    if ( v3 < 0 )
                      goto LABEL_59;
                    v3 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v31 + 64LL))(
                           v31,
                           L"name",
                           &v50,
                           0,
                           0);
                    if ( v3 < 0 )
                      goto LABEL_59;
                    v3 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v31 + 64LL))(
                           v31,
                           L"value",
                           &v49,
                           0,
                           0);
                    if ( v3 < 0 )
                      goto LABEL_59;
                    v3 = SAFE_snwprintf((struct STRU *)v55, L"%s=%s", v50, v49);
                    if ( v3 < 0 )
                      goto LABEL_59;
                    if ( !MULTISZ::Append((MULTISZ *)v54, (struct STRU *)v55) )
                      goto LABEL_58;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                    ++j;
                  }
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
                  v17 = 416LL * v13;
                  v18 = v17 + *((_QWORD *)this + 133);
                  v32 = 0;
                  v3 = IIS_CONFIG_RECORD::Initialize(
                         v18,
                         v53,
                         v52,
                         v51,
                         v14,
                         (const struct MULTISZ *)v54,
                         v15,
                         v43,
                         v42,
                         v41,
                         v40,
                         v39,
                         v38,
                         v37,
                         v36,
                         v35);
                  if ( v3 >= 0 )
                  {
                    v19 = 0;
                    v20 = v17 + *((_QWORD *)this + 133);
                    v21 = *(unsigned __int16 **)v20;
                    v22 = **(_WORD **)v20;
                    if ( *((_DWORD *)this + 262) )
                    {
                      while ( v22 )
                      {
                        ++v21;
                        v19 = v22 + 101 * v19;
                        v22 = *v21;
                      }
                    }
                    else
                    {
                      while ( v22 )
                      {
                        v23 = v22;
                        v22 = *++v21;
                        v19 = (v23 & 0xFFDF) + 101 * v19;
                      }
                    }
                    v24 = v19 % 0x83;
                    *(_QWORD *)(v20 + 8) = *((_QWORD *)this + v24);
                    v25 = v28;
                    *((_QWORD *)this + v24) = v20;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
                    ++v13;
                    v28 = 0;
                    if ( v13 < v29 )
                      continue;
                  }
                  break;
                }
              }
            }
            else
            {
LABEL_58:
              v3 = -2147024882;
            }
          }
        }
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_59:
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  if ( v44 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  if ( v46 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  if ( v47 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  v26 = v48;
  if ( v48 )
  {
    *((_DWORD *)this + 270) = v3;
    (**v26)(v26, &IID_IAppHostConfigException, (char *)this + 1072);
    ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, char *)))(*v48)[2])(v48);
    v3 = 0;
  }
  MULTISZ::~MULTISZ((MULTISZ *)v54);
  STRU::~STRU((STRU *)v55);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000a028  push    rbp
0x18000a02a  push    rbx
0x18000a02b  push    rsi
0x18000a02c  push    rdi
0x18000a02d  push    r12
0x18000a02f  push    r13
0x18000a031  push    r14
0x18000a033  push    r15
0x18000a035  lea     rbp, [rsp-128h]
0x18000a03d  sub     rsp, 228h
0x18000a044  mov     rax, cs:__security_cookie
0x18000a04b  xor     rax, rsp
0x18000a04e  mov     [rbp+160h+var_50], rax
0x18000a055  xor     r13d, r13d
0x18000a058  mov     rsi, rcx
0x18000a05b  lea     rcx, [rbp+160h+var_D0]; void *
0x18000a062  mov     [rbp+160h+var_178], r13
0x18000a066  xor     edx, edx; Val
0x18000a068  mov     [rbp+160h+var_180], r13
0x18000a06c  mov     r8d, 80h; Size
0x18000a072  mov     [rbp+160h+var_190], r13
0x18000a076  mov     [rbp+160h+var_1D8], r13d
0x18000a07a  mov     [rbp+160h+var_1E0], r13
0x18000a07e  mov     [rbp+160h+var_148], r13
0x18000a082  mov     [rbp+160h+var_150], r13
0x18000a086  mov     [rbp+160h+var_158], r13
0x18000a08a  mov     [rbp+160h+var_198], r13d
0x18000a08e  mov     [rbp+160h+var_19C], r13d
0x18000a092  mov     [rbp+160h+var_1A0], r13d
0x18000a096  mov     [rbp+160h+var_1A4], r13d
0x18000a09a  mov     [rbp+160h+var_1A8], r13d
0x18000a09e  mov     [rbp+160h+var_1AC], r13d
0x18000a0a2  mov     [rbp+160h+var_1B0], r13d
0x18000a0a6  mov     [rbp+160h+var_1B4], r13d
0x18000a0aa  mov     [rbp+160h+var_1B8], r13d
0x18000a0ae  mov     [rbp+160h+var_188], r13
0x18000a0b2  mov     [rbp+160h+var_1C8], r13
0x18000a0b6  mov     [rbp+160h+var_1D4], r13d
0x18000a0ba  mov     [rbp+160h+var_1D0], r13
0x18000a0be  mov     [rbp+160h+var_160], r13
0x18000a0c2  mov     [rbp+160h+var_168], r13
0x18000a0c6  call    memset_0
0x18000a0cb  lea     r8d, [r13+40h]
0x18000a0cf  lea     rdx, [rbp+160h+var_D0]
0x18000a0d6  lea     rcx, [rbp+160h+var_108]
0x18000a0da  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000a0e0  lea     rcx, [rbp+160h+var_140]
0x18000a0e4  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18000a0ea  lea     rcx, [rsi+448h]; lpCriticalSection
0x18000a0f1  mov     [rbp+160h+var_170], r13
0x18000a0f5  mov     edx, 3E8h; dwSpinCount
0x18000a0fa  mov     [rbp+160h+var_1BC], r13d
0x18000a0fe  mov     [rbp+160h+var_1C0], r13d
0x18000a102  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000a108  test    eax, eax
0x18000a10a  jnz     short loc_18000A12A
0x18000a10c  call    cs:__imp_GetLastError
0x18000a112  mov     ebx, eax
0x18000a114  test    eax, eax
0x18000a116  jle     loc_18000A7AA
0x18000a11c  movzx   ebx, ax
0x18000a11f  or      ebx, 80070000h
0x18000a125  jmp     loc_18000A7AA
0x18000a12a  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000a131  mov     dword ptr [rsi+440h], 1
0x18000a13b  mov     [rsi+470h], r13d
0x18000a142  mov     rax, [rcx]
0x18000a145  mov     rax, [rax+38h]
0x18000a149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a14e  mov     r9, rax
0x18000a151  lea     r8, [rbp+160h+var_178]
0x18000a155  lea     rdx, IID_INativeConfigurationSystem
0x18000a15c  mov     rcx, [rax]
0x18000a15f  mov     rax, [rcx]
0x18000a162  mov     rcx, r9
0x18000a165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a16a  mov     ebx, eax
0x18000a16c  test    eax, eax
0x18000a16e  js      loc_18000A7AA
0x18000a174  mov     rcx, [rbp+160h+var_178]
0x18000a178  lea     rdx, [rbp+160h+var_170]
0x18000a17c  mov     [rsp+260h+var_238], r13
0x18000a181  lea     r9, [rbp+160h+var_180]
0x18000a185  mov     [rsp+260h+var_240], rdx
0x18000a18a  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18000a191  lea     rdx, aSystemWebserve; "system.webServer/fastCgi"
0x18000a198  mov     rax, [rcx]
0x18000a19b  mov     rax, [rax+18h]
0x18000a19f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1a4  mov     ebx, eax
0x18000a1a6  test    eax, eax
0x18000a1a8  js      loc_18000A7AA
0x18000a1ae  mov     rcx, [rbp+160h+var_180]
0x18000a1b2  lea     rdx, [rbp+160h+var_190]
0x18000a1b6  mov     rax, [rcx]
0x18000a1b9  mov     rax, [rax+28h]
0x18000a1bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1c2  mov     ebx, eax
0x18000a1c4  test    eax, eax
0x18000a1c6  js      loc_18000A7AA
0x18000a1cc  mov     rcx, [rbp+160h+var_190]
0x18000a1d0  lea     rdx, [rbp+160h+var_1D8]
0x18000a1d4  mov     rax, [rcx]
0x18000a1d7  mov     rax, [rax+18h]
0x18000a1db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1e0  mov     ebx, eax
0x18000a1e2  test    eax, eax
0x18000a1e4  js      loc_18000A7AA
0x18000a1ea  mov     edi, [rbp+160h+var_1D8]
0x18000a1ed  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000a1f4  mov     r12d, 1A0h
0x18000a1fa  mov     [rsi+420h], edi
0x18000a200  mov     eax, r12d
0x18000a203  mul     rdi
0x18000a206  cmovb   rax, rcx
0x18000a20a  add     rax, 8
0x18000a20e  cmovb   rax, rcx
0x18000a212  mov     rcx, rax; Size
0x18000a215  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a21a  test    rax, rax
0x18000a21d  jz      short loc_18000A241
0x18000a21f  mov     [rax], rdi
0x18000a222  lea     r14, [rax+8]
0x18000a226  mov     r15, r14
0x18000a229  test    rdi, rdi
0x18000a22c  jz      short loc_18000A244
0x18000a22e  mov     rcx, r15; this
0x18000a231  call    ??0IIS_CONFIG_RECORD@@QEAA@XZ; IIS_CONFIG_RECORD::IIS_CONFIG_RECORD(void)
0x18000a236  add     r15, r12
0x18000a239  sub     rdi, 1
0x18000a23d  jnz     short loc_18000A22E
0x18000a23f  jmp     short loc_18000A244
0x18000a241  mov     r14, r13
0x18000a244  mov     [rsi+428h], r14
0x18000a24b  test    r14, r14
0x18000a24e  jz      loc_18000A7A5
0x18000a254  mov     r12d, r13d
0x18000a257  cmp     [rbp+160h+var_1D8], r13d
0x18000a25b  jbe     loc_18000A7AA
0x18000a261  mov     rcx, [rbp+160h+var_190]
0x18000a265  lea     r8, [rbp+160h+var_1E0]
0x18000a269  mov     edx, r12d
0x18000a26c  mov     rax, [rcx]
0x18000a26f  mov     rax, [rax+20h]
0x18000a273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a278  mov     ebx, eax
0x18000a27a  test    eax, eax
0x18000a27c  js      loc_18000A7AA
0x18000a282  mov     rcx, [rbp+160h+var_1E0]
0x18000a286  lea     r8, [rbp+160h+var_148]
0x18000a28a  xor     r9d, r9d
0x18000a28d  mov     [rsp+260h+var_240], r13
0x18000a292  lea     rdx, aFullpath; "fullPath"
0x18000a299  mov     rax, [rcx]
0x18000a29c  mov     rax, [rax+40h]
0x18000a2a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2a5  mov     ebx, eax
0x18000a2a7  test    eax, eax
0x18000a2a9  js      loc_18000A7AA
0x18000a2af  mov     rcx, [rbp+160h+var_1E0]
0x18000a2b3  lea     r8, [rbp+160h+var_150]
0x18000a2b7  xor     r9d, r9d
0x18000a2ba  mov     [rsp+260h+var_240], r13
0x18000a2bf  lea     rdx, aArguments; "arguments"
0x18000a2c6  mov     rax, [rcx]
0x18000a2c9  mov     rax, [rax+40h]
0x18000a2cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2d2  mov     ebx, eax
0x18000a2d4  test    eax, eax
0x18000a2d6  js      loc_18000A7AA
0x18000a2dc  mov     rcx, [rbp+160h+var_1E0]
0x18000a2e0  lea     r8, [rbp+160h+var_158]
0x18000a2e4  xor     r9d, r9d
0x18000a2e7  mov     [rsp+260h+var_240], r13
0x18000a2ec  lea     rdx, aMonitorchanges; "monitorChangesTo"
0x18000a2f3  mov     rax, [rcx]
0x18000a2f6  mov     rax, [rax+40h]
0x18000a2fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2ff  mov     ebx, eax
0x18000a301  test    eax, eax
0x18000a303  js      loc_18000A7AA
0x18000a309  mov     rcx, [rbp+160h+var_1E0]
0x18000a30d  lea     r8, [rbp+160h+var_1C0]
0x18000a311  xor     r9d, r9d
0x18000a314  mov     [rsp+260h+var_240], r13
0x18000a319  lea     rdx, aStderrmode; "stderrMode"
0x18000a320  mov     rax, [rcx]
0x18000a323  mov     rax, [rax+30h]
0x18000a327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a32c  mov     ebx, eax
0x18000a32e  test    eax, eax
0x18000a330  js      loc_18000A7AA
0x18000a336  mov     r15d, [rbp+160h+var_1C0]
0x18000a33a  mov     ecx, r15d
0x18000a33d  test    r15d, r15d
0x18000a340  jz      short loc_18000A355
0x18000a342  sub     ecx, 1
0x18000a345  jz      short loc_18000A355
0x18000a347  sub     ecx, 1
0x18000a34a  jz      short loc_18000A355
0x18000a34c  cmp     ecx, 1
0x18000a34f  jnz     loc_18000A79E
0x18000a355  mov     rcx, [rbp+160h+var_1E0]
0x18000a359  lea     r8, [rbp+160h+var_1BC]
0x18000a35d  xor     r9d, r9d
0x18000a360  mov     [rsp+260h+var_240], r13
0x18000a365  lea     rdx, aProtocol; "protocol"
0x18000a36c  mov     rax, [rcx]
0x18000a36f  mov     rax, [rax+30h]
0x18000a373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a378  mov     ebx, eax
0x18000a37a  test    eax, eax
0x18000a37c  js      loc_18000A7AA
0x18000a382  mov     r14d, [rbp+160h+var_1BC]
0x18000a386  test    r14d, r14d
0x18000a389  jz      short loc_18000A395
0x18000a38b  cmp     r14d, 1
0x18000a38f  jnz     loc_18000A79E
0x18000a395  mov     rcx, [rbp+160h+var_1E0]
0x18000a399  lea     r8, [rbp+160h+var_198]
0x18000a39d  xor     r9d, r9d
0x18000a3a0  mov     [rsp+260h+var_240], r13
0x18000a3a5  lea     rdx, aQueuelength; "queueLength"
0x18000a3ac  mov     rax, [rcx]
0x18000a3af  mov     rax, [rax+30h]
0x18000a3b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3b8  mov     ebx, eax
0x18000a3ba  test    eax, eax
0x18000a3bc  js      loc_18000A7AA
0x18000a3c2  mov     rcx, [rbp+160h+var_1E0]
0x18000a3c6  lea     r8, [rbp+160h+var_19C]
0x18000a3ca  xor     r9d, r9d
0x18000a3cd  mov     [rsp+260h+var_240], r13
0x18000a3d2  lea     rdx, aMaxinstances_0; "maxInstances"
0x18000a3d9  mov     rax, [rcx]
0x18000a3dc  mov     rax, [rax+30h]
0x18000a3e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3e5  mov     ebx, eax
0x18000a3e7  test    eax, eax
0x18000a3e9  js      loc_18000A7AA
0x18000a3ef  mov     rcx, [rbp+160h+var_1E0]
0x18000a3f3  lea     r8, [rbp+160h+var_1A0]
0x18000a3f7  xor     r9d, r9d
0x18000a3fa  mov     [rsp+260h+var_240], r13
0x18000a3ff  lea     rdx, aIdletimeout; "idleTimeout"
0x18000a406  mov     rax, [rcx]
0x18000a409  mov     rax, [rax+30h]
0x18000a40d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a412  mov     ebx, eax
0x18000a414  test    eax, eax
0x18000a416  js      loc_18000A7AA
0x18000a41c  mov     rcx, [rbp+160h+var_1E0]
0x18000a420  lea     r8, [rbp+160h+var_1A4]
0x18000a424  xor     r9d, r9d
0x18000a427  mov     [rsp+260h+var_240], r13
0x18000a42c  lea     rdx, aActivitytimeou; "activityTimeout"
0x18000a433  mov     rax, [rcx]
0x18000a436  mov     rax, [rax+30h]
0x18000a43a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a43f  mov     ebx, eax
0x18000a441  test    eax, eax
0x18000a443  js      loc_18000A7AA
0x18000a449  mov     rcx, [rbp+160h+var_1E0]
0x18000a44d  lea     r8, [rbp+160h+var_1A8]
0x18000a451  xor     r9d, r9d
0x18000a454  mov     [rsp+260h+var_240], r13
0x18000a459  lea     rdx, aRequesttimeout; "requestTimeout"
0x18000a460  mov     rax, [rcx]
0x18000a463  mov     rax, [rax+30h]
0x18000a467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a46c  mov     ebx, eax
0x18000a46e  test    eax, eax
0x18000a470  js      loc_18000A7AA
0x18000a476  mov     rcx, [rbp+160h+var_1E0]
0x18000a47a  lea     r8, [rbp+160h+var_1AC]
0x18000a47e  xor     r9d, r9d
0x18000a481  mov     [rsp+260h+var_240], r13
0x18000a486  lea     rdx, aInstancemaxreq; "instanceMaxRequests"
0x18000a48d  mov     rax, [rcx]
0x18000a490  mov     rax, [rax+30h]
0x18000a494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a499  mov     ebx, eax
0x18000a49b  test    eax, eax
0x18000a49d  js      loc_18000A7AA
0x18000a4a3  mov     rcx, [rbp+160h+var_1E0]
0x18000a4a7  lea     r8, [rbp+160h+var_1B0]
0x18000a4ab  xor     r9d, r9d
0x18000a4ae  mov     [rsp+260h+var_240], r13
0x18000a4b3  lea     rdx, aSignalbeforete; "signalBeforeTerminateSeconds"
0x18000a4ba  mov     rax, [rcx]
0x18000a4bd  mov     rax, [rax+30h]
0x18000a4c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4c6  mov     ebx, eax
0x18000a4c8  test    eax, eax
0x18000a4ca  js      loc_18000A7AA
0x18000a4d0  mov     rcx, [rbp+160h+var_1E0]
0x18000a4d4  lea     r8, [rbp+160h+var_1B4]
0x18000a4d8  xor     r9d, r9d
0x18000a4db  mov     [rsp+260h+var_240], r13
0x18000a4e0  lea     rdx, aFlushnamedpipe; "flushNamedPipe"
  ... truncated ...
```
