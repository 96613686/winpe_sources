# CMapsToastTaskHandler::Worker(void)

- ea: `0x180005e60`
- end: `0x180006331`
- name: `?Worker@CMapsToastTaskHandler@@EEAAJXZ`
- size: `1233`
- prototype: `__int64 __fastcall(CMapsToastTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800015b0`
- `0x180001624`
- `0x1800020a4`
- `0x1800027e4`
- `0x18000374c`
- `0x1800038e4`
- `0x1800040f0`
- `0x1800044a8`
- `0x18000574c`
- `0x180005d40`
- `0x180005e60`
- `0x180007450`
- `0x18000954c`

## import_xrefs

- `ZTrace_Maps!ZTraceClose` at `0x1800062c9`
- `ZTrace_Maps!ZTraceClose` at `0x1800062c9`
- `ZTrace_Maps!ZTraceInit` at `0x180005f24`
- `ZTrace_Maps!ZTraceInit` at `0x180005f24`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000614f`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800062c0`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000614f`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800062c0`
- `ZTrace_Maps!ZTraceHelper` at `0x180005f6a`
- `ZTrace_Maps!ZTraceHelper` at `0x180005f6a`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180006064`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800061ce`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180006064`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800061ce`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x180006048`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x180006048`

## string_xrefs

- `0x180005f1d`: `*** starting ztrace:onecoreuap\windows\maps\moshost\notifications\mapstoasttask.cpp***`
- `0x180005f47`: `Config: %ls`
- `0x180005f5b`: `CMapsToastTaskHandler::Worker`
- `0x180006117`: `CMapsToastTaskHandler::Worker`
- `0x18000605b`: `CMapsToastTaskHandler::FormatDownloadStartAppMessage`
- `0x180006146`: `CMapsToastTaskHandler::FormatDownloadStartAppMessage`
- `0x1800061c5`: `CMapsToastTaskHandler::GetSystemSettingsAppId`

## pseudocode

```c
__int64 __fastcall CMapsToastTaskHandler::Worker(CMapsToastTaskHandler *this)
{
  unsigned int v2; // r15d
  int Resources; // eax
  int v4; // r8d
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  int AppDisplayName; // eax
  HRESULT v10; // eax
  int v11; // r8d
  int v12; // eax
  __int128 *v13; // rcx
  __int128 *v14; // rax
  __int128 *v15; // r9
  const unsigned __int16 *v16; // r8
  __int64 v17; // r8
  int v18; // r14d
  unsigned __int64 v19; // rdx
  unsigned __int16 **v20; // rdi
  __int64 v21; // rbx
  int v22; // ecx
  int RegString; // eax
  int v24; // ebx
  void *v25; // rcx
  void **v26; // rcx
  const WCHAR *v27; // rax
  const unsigned __int16 *v28; // r8
  const unsigned __int16 *v29; // rdx
  unsigned int v31; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v32; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v33; // [rsp+58h] [rbp-A8h] BYREF
  int v34; // [rsp+5Ch] [rbp-A4h] BYREF
  int v35; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v36; // [rsp+68h] [rbp-98h] BYREF
  __int128 v37; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v38[2]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v39; // [rsp+98h] [rbp-68h]
  unsigned __int64 v40; // [rsp+A0h] [rbp-60h]
  void *Block[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v42; // [rsp+B8h] [rbp-48h]
  __int128 v43; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v44; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v45; // [rsp+E0h] [rbp-20h]
  __int128 v46; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v47; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v48; // [rsp+100h] [rbp+0h]
  unsigned __int16 *v49[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v50; // [rsp+118h] [rbp+18h]
  unsigned __int64 v51; // [rsp+120h] [rbp+20h]
  __int128 v52; // [rsp+128h] [rbp+28h] BYREF
  __int64 v53; // [rsp+138h] [rbp+38h]
  unsigned __int64 v54; // [rsp+140h] [rbp+40h]
  WCHAR pszBuf[128]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 Src[1024]; // [rsp+250h] [rbp+150h] BYREF

  v2 = 0;
  v32 = 0;
  v31 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 7;
  LOWORD(v46) = 0;
  v35 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 7;
  LOWORD(v43) = 0;
  v52 = 0;
  v53 = 0;
  v54 = 7;
  LOWORD(v52) = 0;
  v34 = 0;
  v33 = 0;
  *(_OWORD *)v49 = 0;
  v50 = 0;
  v51 = 7;
  LOWORD(v49[0]) = 0;
  *(_OWORD *)v38 = 0;
  v39 = 0;
  v40 = 7;
  LOWORD(v38[0]) = 0;
  *(_OWORD *)Block = 0;
  *(_QWORD *)&v42 = 0;
  *((_QWORD *)&v42 + 1) = 7;
  LOWORD(Block[0]) = 0;
  ZTraceInit("*** starting ztrace:onecoreuap\\windows\\maps\\moshost\\notifications\\mapstoasttask.cpp***");
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 9, 1, 1) == 1 )
    goto LABEL_60;
  ZTraceHelper(3, "CMapsToastTaskHandler::Worker", 95, this, "Config: %ls", *((const wchar_t **)this + 1));
  Resources = CMapsToastTaskHandler::ParseArguments(
                this,
                *((_QWORD *)this + 1),
                &v32,
                &v31,
                &v46,
                &v35,
                &v43,
                &v52,
                &v34,
                &v33);
  if ( Resources < 0 )
  {
    v4 = 107;
LABEL_58:
    v22 = Resources;
    goto LABEL_59;
  }
  v5 = v31;
  Resources = CMapsToastTaskHandler::LoadResources(this, v32, v31, v49, v38);
  if ( Resources < 0 )
  {
    v4 = 114;
    goto LABEL_58;
  }
  if ( v5 == 111 )
  {
    v36 = 0;
    *(_QWORD *)&v37 = 0;
    *((_QWORD *)&v37 + 1) = 7;
    LOWORD(v36) = 0;
    AppDisplayName = CMapsToastTaskHandler::GetAppDisplayName(this, v33, &v36);
    if ( AppDisplayName < 0 )
    {
      v12 = ZTraceReportPropagation(AppDisplayName, "CMapsToastTaskHandler::FormatDownloadStartAppMessage", 235, this);
    }
    else
    {
      v10 = StrFormatByteSizeEx((unsigned int)(1000 * v34), 1, pszBuf, 0x80u);
      if ( v10 >= 0 )
      {
        v13 = &v52;
        if ( v54 > 7 )
          v13 = (__int128 *)v52;
        v14 = &v43;
        if ( v45 > 7 )
          v14 = (__int128 *)v43;
        v15 = &v36;
        if ( *((_QWORD *)&v37 + 1) > 7u )
          v15 = (__int128 *)v36;
        v16 = (const unsigned __int16 *)v38;
        if ( v40 > 7 )
          v16 = v38[0];
        v10 = StringCchPrintfW(Src, 0x400u, v16, v15, v14, v13, pszBuf);
        if ( v10 >= 0 )
        {
          v18 = 0;
          v19 = -1;
          do
            ++v19;
          while ( Src[v19] );
          if ( v19 > v40 )
          {
            std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
              v38,
              v19,
              v17,
              Src);
          }
          else
          {
            v20 = v38;
            if ( v40 > 7 )
              v20 = (unsigned __int16 **)v38[0];
            v39 = v19;
            v21 = 2 * v19;
            memmove_0(v20, Src, 2 * v19);
            *(_WORD *)((char *)v20 + v21) = 0;
          }
LABEL_30:
          std::wstring::~wstring(&v36);
          if ( v18 < 0 )
          {
            v4 = 124;
            v22 = v18;
LABEL_59:
            v2 = ZTraceReportPropagation(v22, "CMapsToastTaskHandler::Worker", v4, this);
            goto LABEL_60;
          }
          goto LABEL_35;
        }
        v11 = 250;
      }
      else
      {
        v11 = 241;
      }
      v12 = ZTraceReportOrigination(v10, "CMapsToastTaskHandler::FormatDownloadStartAppMessage", v11, this);
    }
    v18 = v12;
    goto LABEL_30;
  }
  if ( v5 == 113 )
  {
    Resources = CMapsToastTaskHandler::FormatDownloadErrorMessage(this, &v43, v38);
    if ( Resources < 0 )
    {
      v4 = 130;
      goto LABEL_58;
    }
  }
LABEL_35:
  v36 = 0;
  *(_QWORD *)&v37 = 0;
  *((_QWORD *)&v37 + 1) = 7;
  LOWORD(v36) = 0;
  RegString = RegUtils::GetRegString(v7, v6, v8, &v36);
  if ( RegString >= 0 )
  {
    if ( *((_QWORD *)&v42 + 1) > 7u )
    {
      if ( (unsigned __int64)(2LL * *((_QWORD *)&v42 + 1) + 2) < 0x1000 )
      {
        v25 = Block[0];
      }
      else
      {
        v25 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v25 - 8) > 0x1F )
          __fastfail(5u);
      }
      operator delete(v25);
    }
    v24 = 0;
    *(_OWORD *)Block = v36;
    v42 = v37;
    *(_QWORD *)&v37 = 0;
    *((_QWORD *)&v37 + 1) = 7;
    LOWORD(v36) = 0;
  }
  else
  {
    v24 = ZTraceReportOrigination(RegString, "CMapsToastTaskHandler::GetSystemSettingsAppId", 312, this);
  }
  std::wstring::~wstring(&v36);
  if ( v24 < 0 )
  {
    v4 = 134;
    v22 = v24;
    goto LABEL_59;
  }
  v26 = Block;
  if ( *((_QWORD *)&v42 + 1) > 7u )
    v26 = (void **)Block[0];
  if ( v47 )
  {
    v27 = (const WCHAR *)&v46;
    if ( v48 > 7 )
      v27 = (const WCHAR *)v46;
  }
  else
  {
    v27 = 0;
  }
  v28 = (const unsigned __int16 *)v38;
  if ( v40 > 7 )
    v28 = v38[0];
  v29 = (const unsigned __int16 *)v49;
  if ( v51 > 7 )
    v29 = v49[0];
  Resources = CMapsToastTaskHandler::ShowToast(this, v29, v28, v35, v27, (const unsigned __int16 *)v26);
  if ( Resources < 0 )
  {
    v4 = 142;
    goto LABEL_58;
  }
LABEL_60:
  ZTraceClose();
  std::wstring::~wstring(Block);
  std::wstring::~wstring(v38);
  std::wstring::~wstring(v49);
  std::wstring::~wstring(&v52);
  std::wstring::~wstring(&v43);
  std::wstring::~wstring(&v46);
  return v2;
}

```

## disassembly

```asm
0x180005e60  push    rbp
0x180005e62  push    rbx
0x180005e63  push    rsi
0x180005e64  push    rdi
0x180005e65  push    r12
0x180005e67  push    r13
0x180005e69  push    r14
0x180005e6b  push    r15
0x180005e6d  lea     rbp, [rsp-968h]
0x180005e75  sub     rsp, 0A68h
0x180005e7c  mov     rax, cs:__security_cookie
0x180005e83  xor     rax, rsp
0x180005e86  mov     [rbp+9A0h+var_50], rax
0x180005e8d  mov     rsi, rcx
0x180005e90  xor     r12d, r12d
0x180005e93  mov     r15d, r12d
0x180005e96  mov     [rsp+0AA0h+var_A4C], r12d
0x180005e9b  mov     [rsp+0AA0h+var_A50], r12d
0x180005ea0  xorps   xmm0, xmm0
0x180005ea3  movups  [rbp+9A0h+var_9B8], xmm0
0x180005ea7  mov     [rbp+9A0h+var_9A8], r12
0x180005eab  lea     r13d, [r12+7]
0x180005eb0  mov     [rbp+9A0h+var_9A0], r13
0x180005eb4  mov     word ptr [rbp+9A0h+var_9B8], r12w
0x180005eb9  mov     [rsp+0AA0h+var_A40], r12d
0x180005ebe  movups  [rbp+9A0h+var_9D8], xmm0
0x180005ec2  mov     [rbp+9A0h+var_9C8], r12
0x180005ec6  mov     [rbp+9A0h+var_9C0], r13
0x180005eca  mov     word ptr [rbp+9A0h+var_9D8], r12w
0x180005ecf  movups  [rbp+9A0h+var_978], xmm0
0x180005ed3  mov     [rbp+9A0h+var_968], r12
0x180005ed7  mov     [rbp+9A0h+var_960], r13
0x180005edb  mov     word ptr [rbp+9A0h+var_978], r12w
0x180005ee0  mov     [rsp+0AA0h+var_A44], r12d
0x180005ee5  mov     [rsp+0AA0h+var_A48], r12d
0x180005eea  movups  xmmword ptr [rbp+9A0h+var_998], xmm0
0x180005eee  mov     [rbp+9A0h+var_988], r12
0x180005ef2  mov     [rbp+9A0h+var_980], r13
0x180005ef6  mov     word ptr [rbp+9A0h+var_998], r12w
0x180005efb  movups  xmmword ptr [rbp+9A0h+var_A18], xmm0
0x180005eff  mov     [rbp+9A0h+var_A08], r12
0x180005f03  mov     [rbp+9A0h+var_A00], r13
0x180005f07  mov     word ptr [rbp+9A0h+var_A18], r12w
0x180005f0c  movups  xmmword ptr [rbp+9A0h+Block], xmm0
0x180005f10  mov     qword ptr [rbp+9A0h+var_9E8], r12
0x180005f14  mov     qword ptr [rbp+9A0h+var_9E8+8], r13
0x180005f18  mov     word ptr [rbp+9A0h+Block], r12w
0x180005f1d  lea     rcx, aStartingZtrace; "*** starting ztrace:onecoreuap\\windows"...
0x180005f24  call    cs:__imp_?ZTraceInit@@YAXPEBD@Z; ZTraceInit(char const *)
0x180005f2a  lea     r14d, [r12+1]
0x180005f2f  mov     eax, r14d
0x180005f32  lock cmpxchg [rsi+24h], r14d
0x180005f38  jz      loc_1800062C9
0x180005f3e  mov     rax, [rsi+8]
0x180005f42  mov     [rsp+0AA0h+var_A78], rax
0x180005f47  lea     rax, aConfigLs; "Config: %ls"
0x180005f4e  mov     [rsp+0AA0h+var_A80], rax
0x180005f53  mov     r9, rsi
0x180005f56  lea     r8d, [r12+5Fh]
0x180005f5b  lea     rdi, aCmapstoasttask_5; "CMapsToastTaskHandler::Worker"
0x180005f62  mov     rdx, rdi
0x180005f65  lea     ecx, [r12+3]
0x180005f6a  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x180005f70  lea     rax, [rsp+0AA0h+var_A48]
0x180005f75  mov     [rsp+0AA0h+var_A58], rax
0x180005f7a  lea     rax, [rsp+0AA0h+var_A44]
0x180005f7f  mov     [rsp+0AA0h+var_A60], rax
0x180005f84  lea     rax, [rbp+9A0h+var_978]
0x180005f88  mov     [rsp+0AA0h+var_A68], rax
0x180005f8d  lea     rax, [rbp+9A0h+var_9D8]
0x180005f91  mov     [rsp+0AA0h+var_A70], rax
0x180005f96  lea     rax, [rsp+0AA0h+var_A40]
0x180005f9b  mov     [rsp+0AA0h+var_A78], rax
0x180005fa0  lea     rax, [rbp+9A0h+var_9B8]
0x180005fa4  mov     [rsp+0AA0h+var_A80], rax
0x180005fa9  lea     r9, [rsp+0AA0h+var_A50]
0x180005fae  lea     r8, [rsp+0AA0h+var_A4C]
0x180005fb3  mov     rdx, [rsi+8]
0x180005fb7  mov     rcx, rsi
0x180005fba  call    ?ParseArguments@CMapsToastTaskHandler@@AEAAJPEBGPEAK1PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@12211@Z; CMapsToastTaskHandler::ParseArguments(ushort const *,ulong *,ulong *,std::wstring *,ulong *,std::wstring *,std::wstring *,ulong *,ulong *)
0x180005fbf  test    eax, eax
0x180005fc1  jns     short loc_180005FCD
0x180005fc3  lea     r8d, [r12+6Bh]
0x180005fc8  jmp     loc_1800062B8
0x180005fcd  lea     rax, [rbp+9A0h+var_A18]
0x180005fd1  mov     [rsp+0AA0h+var_A80], rax
0x180005fd6  lea     r9, [rbp+9A0h+var_998]
0x180005fda  mov     ebx, [rsp+0AA0h+var_A50]
0x180005fde  mov     r8d, ebx
0x180005fe1  mov     edx, [rsp+0AA0h+var_A4C]
0x180005fe5  mov     rcx, rsi
0x180005fe8  call    ?LoadResources@CMapsToastTaskHandler@@AEAAJKKPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; CMapsToastTaskHandler::LoadResources(ulong,ulong,std::wstring *,std::wstring *)
0x180005fed  test    eax, eax
0x180005fef  jns     short loc_180005FFC
0x180005ff1  mov     r8d, 72h ; 'r'
0x180005ff7  jmp     loc_1800062B8
0x180005ffc  cmp     ebx, 6Fh ; 'o'
0x180005fff  jnz     loc_180006175
0x180006005  xorps   xmm0, xmm0
0x180006008  movups  [rsp+0AA0h+var_A38], xmm0
0x18000600d  mov     qword ptr [rsp+0AA0h+var_A28], r12
0x180006012  mov     qword ptr [rbp+9A0h+var_A28+8], r13
0x180006016  mov     word ptr [rsp+0AA0h+var_A38], r12w
0x18000601c  lea     r8, [rsp+0AA0h+var_A38]
0x180006021  mov     edx, [rsp+0AA0h+var_A48]
0x180006025  mov     rcx, rsi
0x180006028  call    ?GetAppDisplayName@CMapsToastTaskHandler@@AEAAJKPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CMapsToastTaskHandler::GetAppDisplayName(ulong,std::wstring *)
0x18000602d  test    eax, eax
0x18000602f  js      loc_18000613D
0x180006035  imul    ecx, [rsp+0AA0h+var_A44], 3E8h; ull
0x18000603d  lea     r9d, [rbx+11h]; cchBuf
0x180006041  lea     r8, [rbp+9A0h+pszBuf]; pszBuf
0x180006045  mov     edx, r14d; flags
0x180006048  call    cs:__imp_StrFormatByteSizeEx
0x18000604e  test    eax, eax
0x180006050  jns     short loc_18000606F
0x180006052  mov     r8d, 0F1h
0x180006058  mov     r9, rsi
0x18000605b  lea     rdx, aCmapstoasttask_3; "CMapsToastTaskHandler::FormatDownloadSt"...
0x180006062  mov     ecx, eax
0x180006064  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18000606a  jmp     loc_180006155
0x18000606f  lea     rcx, [rbp+9A0h+var_978]
0x180006073  cmp     [rbp+9A0h+var_960], r13
0x180006077  cmova   rcx, qword ptr [rbp+9A0h+var_978]
0x18000607c  lea     rax, [rbp+9A0h+var_9D8]
0x180006080  cmp     [rbp+9A0h+var_9C0], r13
0x180006084  cmova   rax, qword ptr [rbp+9A0h+var_9D8]
0x180006089  lea     r9, [rsp+0AA0h+var_A38]
0x18000608e  cmp     qword ptr [rbp+9A0h+var_A28+8], r13
0x180006092  cmova   r9, qword ptr [rsp+0AA0h+var_A38]
0x180006098  lea     r8, [rbp+9A0h+var_A18]
0x18000609c  cmp     [rbp+9A0h+var_A00], r13
0x1800060a0  cmova   r8, [rbp+9A0h+var_A18]; unsigned __int16 *
0x1800060a5  lea     rdx, [rbp+9A0h+pszBuf]
0x1800060a9  mov     [rsp+0AA0h+var_A70], rdx
0x1800060ae  mov     [rsp+0AA0h+var_A78], rcx
0x1800060b3  mov     [rsp+0AA0h+var_A80], rax
0x1800060b8  mov     edx, 400h; unsigned __int64
0x1800060bd  lea     rcx, [rbp+9A0h+Src]; unsigned __int16 *
0x1800060c4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800060c9  test    eax, eax
0x1800060cb  js      short loc_180006132
0x1800060cd  mov     r14d, r12d
0x1800060d0  lea     rax, [rbp+9A0h+Src]
0x1800060d7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800060db  inc     rdx
0x1800060de  cmp     [rax+rdx*2], r12w
0x1800060e3  jnz     short loc_1800060DB
0x1800060e5  cmp     rdx, [rbp+9A0h+var_A00]
0x1800060e9  ja      short loc_180006120
0x1800060eb  lea     rdi, [rbp+9A0h+var_A18]
0x1800060ef  cmp     [rbp+9A0h+var_A00], r13
0x1800060f3  cmova   rdi, [rbp+9A0h+var_A18]
0x1800060f8  mov     [rbp+9A0h+var_A08], rdx
0x1800060fc  lea     rbx, [rdx+rdx]
0x180006100  mov     r8, rbx; Size
0x180006103  lea     rdx, [rbp+9A0h+Src]; Src
0x18000610a  mov     rcx, rdi; void *
0x18000610d  call    memmove_0
0x180006112  mov     [rdi+rbx], r12w
0x180006117  lea     rdi, aCmapstoasttask_5; "CMapsToastTaskHandler::Worker"
0x18000611e  jmp     short loc_180006158
0x180006120  lea     r9, [rbp+9A0h+Src]
0x180006127  lea     rcx, [rbp+9A0h+var_A18]
0x18000612b  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180006130  jmp     short loc_180006158
0x180006132  mov     r8d, 0FAh
0x180006138  jmp     loc_180006058
0x18000613d  mov     r9, rsi
0x180006140  mov     r8d, 0EBh
0x180006146  lea     rdx, aCmapstoasttask_3; "CMapsToastTaskHandler::FormatDownloadSt"...
0x18000614d  mov     ecx, eax
0x18000614f  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180006155  mov     r14d, eax
0x180006158  lea     rcx, [rsp+0AA0h+var_A38]
0x18000615d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006162  test    r14d, r14d
0x180006165  jns     short loc_180006197
0x180006167  mov     r8d, 7Ch ; '|'
0x18000616d  mov     ecx, r14d
0x180006170  jmp     loc_1800062BA
0x180006175  cmp     ebx, 71h ; 'q'
0x180006178  jnz     short loc_180006197
0x18000617a  lea     r8, [rbp+9A0h+var_A18]
0x18000617e  lea     rdx, [rbp+9A0h+var_9D8]
0x180006182  mov     rcx, rsi
0x180006185  call    ?FormatDownloadErrorMessage@CMapsToastTaskHandler@@AEAAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; CMapsToastTaskHandler::FormatDownloadErrorMessage(std::wstring *,std::wstring *)
0x18000618a  test    eax, eax
0x18000618c  jns     short loc_180006197
0x18000618e  lea     r8d, [rbx+11h]
0x180006192  jmp     loc_1800062B8
0x180006197  xorps   xmm0, xmm0
0x18000619a  movups  [rsp+0AA0h+var_A38], xmm0
0x18000619f  mov     qword ptr [rsp+0AA0h+var_A28], r12
0x1800061a4  mov     qword ptr [rbp+9A0h+var_A28+8], r13
0x1800061a8  mov     word ptr [rsp+0AA0h+var_A38], r12w
0x1800061ae  lea     r9, [rsp+0AA0h+var_A38]
0x1800061b3  call    ?GetRegString@RegUtils@@SAJPEBG00PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegUtils::GetRegString(ushort const *,ushort const *,ushort const *,std::wstring *)
0x1800061b8  test    eax, eax
0x1800061ba  jns     short loc_1800061D8
0x1800061bc  mov     r9, rsi
0x1800061bf  mov     r8d, 138h
0x1800061c5  lea     rdx, aCmapstoasttask_6; "CMapsToastTaskHandler::GetSystemSetting"...
0x1800061cc  mov     ecx, eax
0x1800061ce  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x1800061d4  mov     ebx, eax
0x1800061d6  jmp     short loc_180006240
0x1800061d8  mov     rdx, qword ptr [rbp+9A0h+var_9E8+8]
0x1800061dc  cmp     rdx, r13
0x1800061df  jbe     short loc_18000621C
0x1800061e1  mov     rax, [rbp+9A0h+Block]
0x1800061e5  lea     rdx, ds:2[rdx*2]
0x1800061ed  cmp     rdx, 1000h
0x1800061f4  jb      short loc_180006214
0x1800061f6  mov     rcx, [rax-8]
0x1800061fa  sub     rax, rcx
0x1800061fd  sub     rax, 8
0x180006201  cmp     rax, 1Fh
0x180006205  ja      short loc_18000620D
0x180006207  add     rdx, 27h ; '''
0x18000620b  jmp     short loc_180006217
0x18000620d  mov     ecx, 5
0x180006212  int     29h; Win8: RtlFailFast(ecx)
0x180006214  mov     rcx, rax; Block
0x180006217  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000621c  mov     ebx, r12d
0x18000621f  movups  xmm0, [rsp+0AA0h+var_A38]
0x180006224  movups  xmmword ptr [rbp+9A0h+Block], xmm0
0x180006228  movups  xmm1, [rsp+0AA0h+var_A28]
0x18000622d  movups  [rbp+9A0h+var_9E8], xmm1
0x180006231  mov     qword ptr [rsp+0AA0h+var_A28], r12
0x180006236  mov     qword ptr [rbp+9A0h+var_A28+8], r13
0x18000623a  mov     word ptr [rsp+0AA0h+var_A38], r12w
0x180006240  lea     rcx, [rsp+0AA0h+var_A38]
0x180006245  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000624a  test    ebx, ebx
0x18000624c  jns     short loc_180006258
0x18000624e  mov     r8d, 86h
0x180006254  mov     ecx, ebx
0x180006256  jmp     short loc_1800062BA
0x180006258  lea     rcx, [rbp+9A0h+Block]
0x18000625c  cmp     qword ptr [rbp+9A0h+var_9E8+8], r13
0x180006260  cmova   rcx, [rbp+9A0h+Block]
0x180006265  cmp     [rbp+9A0h+var_9A8], r12
0x180006269  jnz     short loc_180006270
0x18000626b  mov     rax, r12
0x18000626e  jmp     short loc_18000627D
0x180006270  lea     rax, [rbp+9A0h+var_9B8]
0x180006274  cmp     [rbp+9A0h+var_9A0], r13
0x180006278  cmova   rax, qword ptr [rbp+9A0h+var_9B8]
0x18000627d  lea     r8, [rbp+9A0h+var_A18]
0x180006281  cmp     [rbp+9A0h+var_A00], r13
0x180006285  cmova   r8, [rbp+9A0h+var_A18]; unsigned __int16 *
0x18000628a  lea     rdx, [rbp+9A0h+var_998]
0x18000628e  cmp     [rbp+9A0h+var_980], r13
0x180006292  cmova   rdx, [rbp+9A0h+var_998]; unsigned __int16 *
0x180006297  mov     [rsp+0AA0h+var_A78], rcx; unsigned __int16 *
0x18000629c  mov     [rsp+0AA0h+var_A80], rax; PCWSTR
0x1800062a1  mov     r9d, [rsp+0AA0h+var_A40]; int
0x1800062a6  mov     rcx, rsi; this
0x1800062a9  call    ?ShowToast@CMapsToastTaskHandler@@AEAAJPEBG0H00@Z; CMapsToastTaskHandler::ShowToast(ushort const *,ushort const *,int,ushort const *,ushort const *)
0x1800062ae  test    eax, eax
0x1800062b0  jns     short loc_1800062C9
0x1800062b2  mov     r8d, 8Eh
0x1800062b8  mov     ecx, eax
0x1800062ba  mov     r9, rsi
0x1800062bd  mov     rdx, rdi
0x1800062c0  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x1800062c6  mov     r15d, eax
0x1800062c9  call    cs:__imp_?ZTraceClose@@YAXXZ; ZTraceClose(void)
0x1800062cf  nop
0x1800062d0  lea     rcx, [rbp+9A0h+Block]
0x1800062d4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800062d9  nop
0x1800062da  lea     rcx, [rbp+9A0h+var_A18]
0x1800062de  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800062e3  nop
0x1800062e4  lea     rcx, [rbp+9A0h+var_998]
0x1800062e8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800062ed  nop
0x1800062ee  lea     rcx, [rbp+9A0h+var_978]
0x1800062f2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800062f7  nop
0x1800062f8  lea     rcx, [rbp+9A0h+var_9D8]
0x1800062fc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006301  nop
0x180006302  lea     rcx, [rbp+9A0h+var_9B8]
0x180006306  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000630b  mov     eax, r15d
0x18000630e  mov     rcx, [rbp+9A0h+var_50]
0x180006315  xor     rcx, rsp; StackCookie
0x180006318  call    __security_check_cookie
0x18000631d  add     rsp, 0A68h
0x180006324  pop     r15
0x180006326  pop     r14
0x180006328  pop     r13
0x18000632a  pop     r12
0x18000632c  pop     rdi
0x18000632d  pop     rsi
  ... truncated ...
```
