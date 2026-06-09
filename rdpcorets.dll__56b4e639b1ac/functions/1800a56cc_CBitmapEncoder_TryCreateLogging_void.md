# CBitmapEncoder::TryCreateLogging(void)

- ea: `0x1800a56cc`
- end: `0x1800a5d5b`
- name: `?TryCreateLogging@CBitmapEncoder@@AEAAXXZ`
- size: `1679`
- prototype: `void __fastcall(CBitmapEncoder *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800a4a20`

## callees

- `0x180009088`
- `0x1800091a8`
- `0x18001569c`
- `0x18002e600`
- `0x18002f8e4`
- `0x180033da0`
- `0x180034970`
- `0x180059838`
- `0x180063160`
- `0x1800a56cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x1800a590a`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x1800a5ae8`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x1800a5cb8`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x1800a590a`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x1800a5ae8`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x1800a5cb8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a5739`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a5739`

## string_xrefs

- `0x1800a57f5`: `TSMM_VIDEO_RegReadSTRING( REG_VALUE_TSMMV_SERVER_YUV_DUMP_PATH ) failed. Not using YUV logging.`
- `0x1800a57a0`: `VideoRemotingYuvDumpPath`
- `0x1800a599f`: `VideoRemotingRgbDumpPath`
- `0x1800a59da`: `TSMM_VIDEO_RegReadSTRING( REG_VALUE_TSMMV_SERVER_RGB_DUMP_PATH ) failed. Not using RGB logging.`
- `0x1800a5b6f`: `VideoRemotingH264DumpPath`
- `0x1800a5baa`: `TSMM_VIDEO_RegReadSTRING( REG_VALUE_TSMMV_SERVER_H264_DUMP_PATH ) failed. Not using H264 logging.`

## pseudocode

```c
void __fastcall CBitmapEncoder::TryCreateLogging(CBitmapEncoder *this)
{
  DWORD TickCount; // eax
  const unsigned __int16 *v3; // rdx
  HKEY v4; // rcx
  const unsigned __int16 *v5; // rdx
  HKEY v6; // rcx
  int STRING; // edi
  unsigned int v8; // eax
  unsigned int v9; // eax
  FILE *v10; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v12; // edx
  const unsigned __int16 *v13; // rdx
  HKEY v14; // rcx
  int v15; // edi
  unsigned int v16; // eax
  unsigned int v17; // eax
  FILE *v18; // rax
  unsigned int v19; // eax
  int v20; // edx
  int v21; // edi
  unsigned int v22; // eax
  unsigned int v23; // eax
  FILE *v24; // rax
  unsigned int v25; // eax
  int v26; // edx
  __int64 v27; // [rsp+28h] [rbp-D8h]
  __int64 v28; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v29[4]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v30; // [rsp+40h] [rbp-C0h]
  unsigned __int16 v31[4]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v33[8]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+68h] [rbp-98h]
  wchar_t FileName[1024]; // [rsp+70h] [rbp-90h] BYREF

  v34 = 0;
  LODWORD(v28) = 2048;
  *(_QWORD *)v29 = 0;
  LODWORD(v30) = 0;
  *(_OWORD *)v33 = 0;
  *(_QWORD *)v31 = 0;
  LODWORD(v32) = 0;
  memset_0(FileName, 0, sizeof(FileName));
  TickCount = GetTickCount();
  StringCchPrintfW(v33, 0xCu, L"%u", TickCount);
  StringCchPrintfW(v29, 6u, L"%d", *((unsigned int *)this + 42));
  StringCchPrintfW(v31, 6u, L"%d", *((unsigned int *)this + 43));
  STRING = TSMM_VIDEO_RegReadSTRING(v4, v3, L"VideoRemotingYuvDumpPath", FileName, (unsigned int *)&v28);
  if ( STRING >= 0 )
  {
    if ( STRING != 1 )
    {
      StringCchCatW(FileName, 0x400u, L"\\VOBR_YUV_");
      StringCchCatW(FileName, 0x400u, v33);
      StringCchCatW(FileName, 0x400u, L"_");
      StringCchCatW(FileName, 0x400u, v29);
      StringCchCatW(FileName, 0x400u, L"x");
      StringCchCatW(FileName, 0x400u, v31);
      StringCchCatW(FileName, 0x400u, L"_24p.YUV");
      v10 = _wfopen(FileName, L"wb");
      *((_QWORD *)this + 17) = v10;
      if ( v10 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_21;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v12 = 117;
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
        {
          goto LABEL_21;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v12 = 116;
      }
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        (unsigned int)WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)FileName);
      goto LABEL_21;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids, v9);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      114,
      (unsigned int)WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids,
      v8,
      (__int64)"TSMM_VIDEO_RegReadSTRING( REG_VALUE_TSMMV_SERVER_YUV_DUMP_PATH ) failed. Not using YUV logging.",
      STRING,
      v28,
      *(_QWORD *)v29,
      v30,
      *(_QWORD *)v31,
      v32,
      *(_QWORD *)v33,
      *(_QWORD *)&v33[4],
      v34);
  }
LABEL_21:
  v15 = TSMM_VIDEO_RegReadSTRING(v6, v5, L"VideoRemotingRgbDumpPath", FileName, (unsigned int *)&v28);
  if ( v15 >= 0 )
  {
    if ( v15 != 1 )
    {
      StringCchCatW(FileName, 0x400u, L"\\VOBR_RGB_");
      StringCchCatW(FileName, 0x400u, v33);
      StringCchCatW(FileName, 0x400u, L"_");
      StringCchCatW(FileName, 0x400u, v29);
      StringCchCatW(FileName, 0x400u, L"x");
      StringCchCatW(FileName, 0x400u, v31);
      StringCchCatW(FileName, 0x400u, L"_24p.bgra");
      v18 = _wfopen(FileName, L"wb");
      *((_QWORD *)this + 18) = v18;
      if ( v18 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_41;
        }
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 121;
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
        {
          goto LABEL_41;
        }
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 120;
      }
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v20,
        (unsigned int)WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids,
        v19,
        (__int64)FileName);
      goto LABEL_41;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids, v17);
    }
  }
  else
  {
    v14 = (HKEY)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v27) = v15;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        118,
        (unsigned int)WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids,
        v16,
        (__int64)"TSMM_VIDEO_RegReadSTRING( REG_VALUE_TSMMV_SERVER_RGB_DUMP_PATH ) failed. Not using RGB logging.",
        v27);
    }
  }
LABEL_41:
  v21 = TSMM_VIDEO_RegReadSTRING(v14, v13, L"VideoRemotingH264DumpPath", FileName, (unsigned int *)&v28);
  if ( v21 >= 0 )
  {
    if ( v21 != 1 )
    {
      StringCchCatW(FileName, 0x400u, L"\\VOBR_H264_");
      StringCchCatW(FileName, 0x400u, v33);
      StringCchCatW(FileName, 0x400u, L"_");
      StringCchCatW(FileName, 0x400u, v29);
      StringCchCatW(FileName, 0x400u, L"x");
      StringCchCatW(FileName, 0x400u, v31);
      StringCchCatW(FileName, 0x400u, L".264");
      v24 = _wfopen(FileName, L"wb");
      *((_QWORD *)this + 19) = v24;
      if ( v24 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          return;
        }
        v25 = RdpWppGetCurrentThreadActivityIdPrefix();
        v26 = 125;
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
        {
          return;
        }
        v25 = RdpWppGetCurrentThreadActivityIdPrefix();
        v26 = 124;
      }
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v26,
        (unsigned int)WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids,
        v25,
        (__int64)FileName);
      return;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v23 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids, v23);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v22 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(v27) = v21;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      122,
      (unsigned int)WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids,
      v22,
      (__int64)"TSMM_VIDEO_RegReadSTRING( REG_VALUE_TSMMV_SERVER_H264_DUMP_PATH ) failed. Not using H264 logging.",
      v27);
  }
}

```

## disassembly

```asm
0x1800a56cc  mov     [rsp-8+arg_8], rbx
0x1800a56d1  mov     [rsp-8+arg_10], rsi
0x1800a56d6  push    rbp
0x1800a56d7  push    rdi
0x1800a56d8  push    r13
0x1800a56da  push    r14
0x1800a56dc  push    r15
0x1800a56de  lea     rbp, [rsp-780h]
0x1800a56e6  sub     rsp, 880h
0x1800a56ed  mov     rax, cs:__security_cookie
0x1800a56f4  xor     rax, rsp
0x1800a56f7  mov     [rbp+7A0h+var_30], rax
0x1800a56fe  xor     eax, eax
0x1800a5700  mov     rsi, rcx
0x1800a5703  mov     r8d, 800h; Size
0x1800a5709  mov     [rsp+8A0h+var_838], rax
0x1800a570e  xorps   xmm0, xmm0
0x1800a5711  mov     dword ptr [rsp+8A0h+var_870], r8d
0x1800a5716  lea     rcx, [rsp+8A0h+FileName]; void *
0x1800a571b  mov     qword ptr [rsp+8A0h+var_868], rax
0x1800a5720  xor     edx, edx; Val
0x1800a5722  mov     dword ptr [rsp+8A0h+var_860], eax
0x1800a5726  movups  xmmword ptr [rsp+8A0h+var_848], xmm0
0x1800a572b  mov     qword ptr [rsp+8A0h+var_858], rax
0x1800a5730  mov     dword ptr [rsp+8A0h+var_850], eax
0x1800a5734  call    memset_0
0x1800a5739  call    cs:__imp_GetTickCount
0x1800a573f  lea     r8, aU; "%u"
0x1800a5746  mov     edx, 0Ch; unsigned __int64
0x1800a574b  mov     r9d, eax
0x1800a574e  lea     rcx, [rsp+8A0h+var_848]; unsigned __int16 *
0x1800a5753  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a5758  mov     r9d, [rsi+0A8h]
0x1800a575f  lea     r8, aD; "%d"
0x1800a5766  mov     ebx, 6
0x1800a576b  lea     rcx, [rsp+8A0h+var_868]; unsigned __int16 *
0x1800a5770  mov     edx, ebx; unsigned __int64
0x1800a5772  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a5777  mov     r9d, [rsi+0ACh]
0x1800a577e  lea     r8, aD; "%d"
0x1800a5785  mov     edx, ebx; unsigned __int64
0x1800a5787  lea     rcx, [rsp+8A0h+var_858]; unsigned __int16 *
0x1800a578c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a5791  lea     rax, [rsp+8A0h+var_870]
0x1800a5796  lea     r9, [rsp+8A0h+FileName]; unsigned __int16 *
0x1800a579b  mov     [rsp+8A0h+var_880], rax; unsigned int *
0x1800a57a0  lea     r8, aVideoremotingy; "VideoRemotingYuvDumpPath"
0x1800a57a7  call    ?TSMM_VIDEO_RegReadSTRING@@YAJPEAUHKEY__@@PEBG1PEAGPEAK@Z; TSMM_VIDEO_RegReadSTRING(HKEY__ *,ushort const *,ushort const *,ushort *,ulong *)
0x1800a57ac  lea     r14, WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids
0x1800a57b3  mov     edi, eax
0x1800a57b5  mov     r15d, 200h
0x1800a57bb  mov     r13d, 400h
0x1800a57c1  test    eax, eax
0x1800a57c3  jns     short loc_1800A5825
0x1800a57c5  mov     rax, cs:WPP_GLOBAL_Control
0x1800a57cc  lea     rbx, WPP_GLOBAL_Control
0x1800a57d3  cmp     rax, rbx
0x1800a57d6  jz      loc_1800A5990
0x1800a57dc  test    byte ptr [rax+1Ch], 8
0x1800a57e0  jz      loc_1800A5990
0x1800a57e6  cmp     byte ptr [rax+19h], 2
0x1800a57ea  jb      loc_1800A5990
0x1800a57f0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a57f5  lea     rcx, aTsmmVideoRegre_6; "TSMM_VIDEO_RegReadSTRING( REG_VALUE_TSM"...
0x1800a57fc  mov     dword ptr [rsp+8A0h+var_878], edi
0x1800a5800  mov     [rsp+8A0h+var_880], rcx
0x1800a5805  mov     edx, 72h ; 'r'
0x1800a580a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5811  mov     r9d, eax
0x1800a5814  mov     r8, r14
0x1800a5817  mov     rcx, [rcx+10h]
0x1800a581b  call    WPP_SF_DsD
0x1800a5820  jmp     loc_1800A5990
0x1800a5825  cmp     edi, 1
0x1800a5828  jnz     short loc_1800A5878
0x1800a582a  mov     rax, cs:WPP_GLOBAL_Control
0x1800a5831  lea     rbx, WPP_GLOBAL_Control
0x1800a5838  cmp     rax, rbx
0x1800a583b  jz      loc_1800A5990
0x1800a5841  test    [rax+1Ch], r15d
0x1800a5845  jz      loc_1800A5990
0x1800a584b  cmp     byte ptr [rax+19h], 3
0x1800a584f  jb      loc_1800A5990
0x1800a5855  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a585a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5861  lea     edx, [rdi+72h]
0x1800a5864  mov     r9d, eax
0x1800a5867  mov     r8, r14
0x1800a586a  mov     rcx, [rcx+10h]
0x1800a586e  call    WPP_SF_d
0x1800a5873  jmp     loc_1800A5990
0x1800a5878  lea     r8, aVobrYuv; "\\VOBR_YUV_"
0x1800a587f  mov     rdx, r13; unsigned __int64
0x1800a5882  lea     rcx, [rsp+8A0h+FileName]; unsigned __int16 *
0x1800a5887  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a588c  lea     r8, [rsp+8A0h+var_848]; unsigned __int16 *
0x1800a5891  mov     rdx, r13; unsigned __int64
0x1800a5894  lea     rcx, [rsp+8A0h+FileName]; unsigned __int16 *
0x1800a5899  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a589e  lea     r8, asc_180176104; "_"
0x1800a58a5  mov     rdx, r13; unsigned __int64
0x1800a58a8  lea     rcx, [rsp+8A0h+FileName]; unsigned __int16 *
0x1800a58ad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a58b2  lea     r8, [rsp+8A0h+var_868]; unsigned __int16 *
0x1800a58b7  mov     rdx, r13; unsigned __int64
0x1800a58ba  lea     rcx, [rsp+8A0h+FileName]; unsigned __int16 *
0x1800a58bf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a58c4  lea     r8, asc_180176134; "x"
0x1800a58cb  mov     rdx, r13; unsigned __int64
0x1800a58ce  lea     rcx, [rsp+8A0h+FileName]; unsigned __int16 *
0x1800a58d3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a58d8  lea     r8, [rsp+8A0h+var_858]; unsigned __int16 *
0x1800a58dd  mov     rdx, r13; unsigned __int64
0x1800a58e0  lea     rcx, [rsp+8A0h+FileName]; unsigned __int16 *
0x1800a58e5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a58ea  lea     r8, a24pYuv; "_24p.YUV"
0x1800a58f1  mov     rdx, r13; unsigned __int64
0x1800a58f4  lea     rcx, [rsp+8A0h+FileName]; unsigned __int16 *
0x1800a58f9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a58fe  lea     rdx, aWb; "wb"
0x1800a5905  lea     rcx, [rsp+8A0h+FileName]; FileName
0x1800a590a  call    cs:__imp__wfopen
0x1800a5910  mov     [rsi+88h], rax
0x1800a5917  test    rax, rax
0x1800a591a  jnz     short loc_1800A5947
0x1800a591c  mov     rax, cs:WPP_GLOBAL_Control
0x1800a5923  lea     rbx, WPP_GLOBAL_Control
0x1800a592a  cmp     rax, rbx
0x1800a592d  jz      short loc_1800A5990
0x1800a592f  test    [rax+1Ch], r15d
0x1800a5933  jz      short loc_1800A5990
0x1800a5935  cmp     byte ptr [rax+19h], 3
0x1800a5939  jb      short loc_1800A5990
0x1800a593b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a5940  mov     edx, 74h ; 't'
0x1800a5945  jmp     short loc_1800A5970
0x1800a5947  mov     rax, cs:WPP_GLOBAL_Control
0x1800a594e  lea     rbx, WPP_GLOBAL_Control
0x1800a5955  cmp     rax, rbx
0x1800a5958  jz      short loc_1800A5990
0x1800a595a  test    [rax+1Ch], r15d
0x1800a595e  jz      short loc_1800A5990
0x1800a5960  cmp     byte ptr [rax+19h], 4
0x1800a5964  jb      short loc_1800A5990
0x1800a5966  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a596b  mov     edx, 75h ; 'u'
0x1800a5970  lea     rcx, [rsp+8A0h+FileName]
0x1800a5975  mov     r9d, eax
0x1800a5978  mov     [rsp+8A0h+var_880], rcx
0x1800a597d  mov     r8, r14
0x1800a5980  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5987  mov     rcx, [rcx+10h]
0x1800a598b  call    WPP_SF_DS
0x1800a5990  lea     rax, [rsp+8A0h+var_870]
0x1800a5995  lea     r9, [rsp+8A0h+FileName]; unsigned __int16 *
0x1800a599a  mov     [rsp+8A0h+var_880], rax; unsigned int *
0x1800a599f  lea     r8, aVideoremotingr; "VideoRemotingRgbDumpPath"
0x1800a59a6  call    ?TSMM_VIDEO_RegReadSTRING@@YAJPEAUHKEY__@@PEBG1PEAGPEAK@Z; TSMM_VIDEO_RegReadSTRING(HKEY__ *,ushort const *,ushort const *,ushort *,ulong *)
0x1800a59ab  mov     edi, eax
0x1800a59ad  test    eax, eax
0x1800a59af  jns     short loc_1800A5A0A
0x1800a59b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a59b8  cmp     rcx, rbx
0x1800a59bb  jz      loc_1800A5B60
0x1800a59c1  test    byte ptr [rcx+1Ch], 8
0x1800a59c5  jz      loc_1800A5B60
0x1800a59cb  cmp     byte ptr [rcx+19h], 2
0x1800a59cf  jb      loc_1800A5B60
0x1800a59d5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a59da  lea     rcx, aTsmmVideoRegre_4; "TSMM_VIDEO_RegReadSTRING( REG_VALUE_TSM"...
0x1800a59e1  mov     dword ptr [rsp+8A0h+var_878], edi
0x1800a59e5  mov     [rsp+8A0h+var_880], rcx
0x1800a59ea  mov     edx, 76h ; 'v'
0x1800a59ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a59f6  mov     r9d, eax
0x1800a59f9  mov     r8, r14
0x1800a59fc  mov     rcx, [rcx+10h]
0x1800a5a00  call    WPP_SF_DsD
0x1800a5a05  jmp     loc_1800A5B60
0x1800a5a0a  cmp     edi, 1
0x1800a5a0d  jnz     short loc_1800A5A56
0x1800a5a0f  mov     rax, cs:WPP_GLOBAL_Control
0x1800a5a16  cmp     rax, rbx
0x1800a5a19  jz      loc_1800A5B60
0x1800a5a1f  test    [rax+1Ch], r15d
0x1800a5a23  jz      loc_1800A5B60
0x1800a5a29  cmp     byte ptr [rax+19h], 3
0x1800a5a2d  jb      loc_1800A5B60
0x1800a5a33  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a5a38  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5a3f  lea     edx, [rdi+76h]
0x1800a5a42  mov     r9d, eax
0x1800a5a45  mov     r8, r14
0x1800a5a48  mov     rcx, [rcx+10h]
0x1800a5a4c  call    WPP_SF_d
0x1800a5a51  jmp     loc_1800A5B60
0x1800a5a56  lea     r8, aVobrRgb; "\\VOBR_RGB_"
0x1800a5a5d  mov     rdx, r13; unsigned __int64
0x1800a5a60  lea     rcx, [rsp+8A0h+FileName]; unsigned __int16 *
0x1800a5a65  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a5a6a  lea     r8, [rsp+8A0h+var_848]; unsigned __int16 *
0x1800a5a6f  mov     rdx, r13; unsigned __int64
0x1800a5a72  lea     rcx, [rsp+8A0h+FileName]; unsigned __int16 *
0x1800a5a77  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a5a7c  lea     r8, asc_180176104; "_"
0x1800a5a83  mov     rdx, r13; unsigned __int64
0x1800a5a86  lea     rcx, [rsp+8A0h+FileName]; unsigned __int16 *
0x1800a5a8b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a5a90  lea     r8, [rsp+8A0h+var_868]; unsigned __int16 *
0x1800a5a95  mov     rdx, r13; unsigned __int64
0x1800a5a98  lea     rcx, [rsp+8A0h+FileName]; unsigned __int16 *
0x1800a5a9d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a5aa2  lea     r8, asc_180176134; "x"
0x1800a5aa9  mov     rdx, r13; unsigned __int64
0x1800a5aac  lea     rcx, [rsp+8A0h+FileName]; unsigned __int16 *
0x1800a5ab1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a5ab6  lea     r8, [rsp+8A0h+var_858]; unsigned __int16 *
0x1800a5abb  mov     rdx, r13; unsigned __int64
0x1800a5abe  lea     rcx, [rsp+8A0h+FileName]; unsigned __int16 *
0x1800a5ac3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a5ac8  lea     r8, a24pBgra; "_24p.bgra"
0x1800a5acf  mov     rdx, r13; unsigned __int64
0x1800a5ad2  lea     rcx, [rsp+8A0h+FileName]; unsigned __int16 *
0x1800a5ad7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a5adc  lea     rdx, aWb; "wb"
0x1800a5ae3  lea     rcx, [rsp+8A0h+FileName]; FileName
0x1800a5ae8  call    cs:__imp__wfopen
0x1800a5aee  mov     [rsi+90h], rax
0x1800a5af5  test    rax, rax
0x1800a5af8  jnz     short loc_1800A5B1E
0x1800a5afa  mov     rax, cs:WPP_GLOBAL_Control
0x1800a5b01  cmp     rax, rbx
0x1800a5b04  jz      short loc_1800A5B60
0x1800a5b06  test    [rax+1Ch], r15d
0x1800a5b0a  jz      short loc_1800A5B60
0x1800a5b0c  cmp     byte ptr [rax+19h], 3
0x1800a5b10  jb      short loc_1800A5B60
0x1800a5b12  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a5b17  mov     edx, 78h ; 'x'
0x1800a5b1c  jmp     short loc_1800A5B40
0x1800a5b1e  mov     rax, cs:WPP_GLOBAL_Control
0x1800a5b25  cmp     rax, rbx
0x1800a5b28  jz      short loc_1800A5B60
0x1800a5b2a  test    [rax+1Ch], r15d
0x1800a5b2e  jz      short loc_1800A5B60
0x1800a5b30  cmp     byte ptr [rax+19h], 4
0x1800a5b34  jb      short loc_1800A5B60
0x1800a5b36  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a5b3b  mov     edx, 79h ; 'y'
0x1800a5b40  lea     rcx, [rsp+8A0h+FileName]
0x1800a5b45  mov     r9d, eax
0x1800a5b48  mov     [rsp+8A0h+var_880], rcx
0x1800a5b4d  mov     r8, r14
0x1800a5b50  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5b57  mov     rcx, [rcx+10h]
0x1800a5b5b  call    WPP_SF_DS
0x1800a5b60  lea     rax, [rsp+8A0h+var_870]
0x1800a5b65  lea     r9, [rsp+8A0h+FileName]; unsigned __int16 *
0x1800a5b6a  mov     [rsp+8A0h+var_880], rax; unsigned int *
0x1800a5b6f  lea     r8, aVideoremotingh; "VideoRemotingH264DumpPath"
0x1800a5b76  call    ?TSMM_VIDEO_RegReadSTRING@@YAJPEAUHKEY__@@PEBG1PEAGPEAK@Z; TSMM_VIDEO_RegReadSTRING(HKEY__ *,ushort const *,ushort const *,ushort *,ulong *)
0x1800a5b7b  mov     edi, eax
0x1800a5b7d  test    eax, eax
0x1800a5b7f  jns     short loc_1800A5BDA
0x1800a5b81  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5b88  cmp     rcx, rbx
0x1800a5b8b  jz      loc_1800A5D30
0x1800a5b91  test    byte ptr [rcx+1Ch], 8
0x1800a5b95  jz      loc_1800A5D30
0x1800a5b9b  cmp     byte ptr [rcx+19h], 2
0x1800a5b9f  jb      loc_1800A5D30
0x1800a5ba5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a5baa  lea     rcx, aTsmmVideoRegre_7; "TSMM_VIDEO_RegReadSTRING( REG_VALUE_TSM"...
0x1800a5bb1  mov     dword ptr [rsp+8A0h+var_878], edi
0x1800a5bb5  mov     [rsp+8A0h+var_880], rcx
0x1800a5bba  mov     edx, 7Ah ; 'z'
0x1800a5bbf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5bc6  mov     r9d, eax
0x1800a5bc9  mov     r8, r14
0x1800a5bcc  mov     rcx, [rcx+10h]
0x1800a5bd0  call    WPP_SF_DsD
0x1800a5bd5  jmp     loc_1800A5D30
0x1800a5bda  cmp     edi, 1
0x1800a5bdd  jnz     short loc_1800A5C26
0x1800a5bdf  mov     rax, cs:WPP_GLOBAL_Control
0x1800a5be6  cmp     rax, rbx
0x1800a5be9  jz      loc_1800A5D30
0x1800a5bef  test    [rax+1Ch], r15d
0x1800a5bf3  jz      loc_1800A5D30
0x1800a5bf9  cmp     byte ptr [rax+19h], 3
0x1800a5bfd  jb      loc_1800A5D30
0x1800a5c03  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a5c08  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5c0f  lea     edx, [rdi+7Ah]
0x1800a5c12  mov     r9d, eax
0x1800a5c15  mov     r8, r14
0x1800a5c18  mov     rcx, [rcx+10h]
0x1800a5c1c  call    WPP_SF_d
0x1800a5c21  jmp     loc_1800A5D30
0x1800a5c26  lea     r8, aVobrH264; "\\VOBR_H264_"
  ... truncated ...
```
