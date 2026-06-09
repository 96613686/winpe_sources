# PushClient::xGetMessage(void *,ushort * *,ulong *,uchar * *,ulong *,ushort * *,ushort * *,PushRouterSubmitOrigin *,ulong *,uchar * *)

- ea: `0x180018d14`
- end: `0x180019466`
- name: `?xGetMessage@PushClient@@SAJPEAXPEAPEAGPEAKPEAPEAE211PEAW4PushRouterSubmitOrigin@@23@Z`
- size: `1874`
- prototype: `__int64 __fastcall(void *, unsigned __int16 **, unsigned int *, unsigned __int8 **, unsigned int *, unsigned __int16 **, unsigned __int16 **, enum PushRouterSubmitOrigin *, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180010540`

## callees

- `0x180001464`
- `0x180001504`
- `0x1800039f0`
- `0x18000dc6c`
- `0x1800127c4`
- `0x180013528`
- `0x1800145bc`
- `0x1800184dc`
- `0x180018d14`
- `0x18001946c`
- `0x1800195c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019426`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019426`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018dcc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018dcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019430`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001943a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019430`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001943a`
- `DMCmnUtils!CopyString` at `0x18001909c`
- `DMCmnUtils!CopyString` at `0x1800191df`
- `DMCmnUtils!CopyString` at `0x18001909c`
- `DMCmnUtils!CopyString` at `0x1800191df`
- `DMCmnUtils!InvStrCmpNIW` at `0x18001904a`
- `DMCmnUtils!InvStrCmpNIW` at `0x18001918e`
- `DMCmnUtils!InvStrCmpNIW` at `0x18001904a`
- `DMCmnUtils!InvStrCmpNIW` at `0x18001918e`

## pseudocode

```c
__int64 __fastcall PushClient::xGetMessage(
        void *a1,
        unsigned __int16 **a2,
        unsigned int *a3,
        unsigned __int8 **a4,
        unsigned int *a5,
        unsigned __int16 **a6,
        unsigned __int16 **a7,
        enum PushRouterSubmitOrigin *a8,
        unsigned int *a9,
        unsigned __int8 **a10)
{
  unsigned __int16 *v11; // r13
  PushRouter *v12; // rcx
  __int64 v13; // r8
  int v14; // edi
  struct PushClient *ExistingClientByHandle; // rax
  __int64 v16; // rcx
  unsigned __int16 *v17; // r15
  int v18; // r14d
  unsigned int *v19; // r10
  enum PushRouterSubmitOrigin *v20; // r8
  unsigned __int8 **v21; // r9
  unsigned __int16 **v22; // rdx
  unsigned __int16 **v23; // rcx
  int MessageW; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  unsigned __int16 *v27; // rbx
  int v28; // r9d
  __int64 v29; // rdx
  unsigned __int16 *v30; // r12
  const unsigned __int16 *v31; // rax
  __int64 v32; // rdx
  unsigned __int16 *v33; // rax
  unsigned __int16 *v34; // rdx
  unsigned __int16 *v35; // rcx
  int v36; // r8d
  unsigned __int16 v37; // ax
  int EndOfHeader; // eax
  int v39; // eax
  const unsigned __int16 *v40; // rax
  unsigned __int64 v41; // r12
  unsigned __int16 *v42; // rax
  const unsigned __int16 *v43; // rsi
  unsigned __int16 *v44; // rcx
  int v45; // r8d
  unsigned __int16 v46; // ax
  int v47; // eax
  int v48; // eax
  unsigned int v49; // ebx
  const OLECHAR *v50; // rdx
  const OLECHAR *v51; // r8
  __int64 v52; // rax
  __int64 v53; // rcx
  int v54; // ecx
  __int64 v55; // rcx
  int v56; // ecx
  __int64 v57; // rcx
  int v58; // ecx
  unsigned __int16 *v59; // rdi
  unsigned int v60; // ebx
  unsigned int v62; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v63; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v64; // [rsp+68h] [rbp-98h] BYREF
  int v65; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned __int16 *v66; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v67; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v68; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL v70; // [rsp+90h] [rbp-70h] BYREF
  unsigned int *v71; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v72; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v73; // [rsp+A8h] [rbp-58h] BYREF
  void *v74; // [rsp+B0h] [rbp-50h]
  enum PushRouterSubmitOrigin *v75; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int8 **v76; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int8 **v77; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int *v78; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int8 *v79; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int *v80; // [rsp+E0h] [rbp-20h]
  unsigned int *v81; // [rsp+110h] [rbp+10h]
  __int64 v82; // [rsp+118h] [rbp+18h]
  unsigned int **v83; // [rsp+120h] [rbp+20h]
  __int64 v84; // [rsp+128h] [rbp+28h]
  unsigned int *v85; // [rsp+130h] [rbp+30h]
  __int64 v86; // [rsp+138h] [rbp+38h]
  const OLECHAR *v87; // [rsp+140h] [rbp+40h]
  int v88; // [rsp+148h] [rbp+48h]
  int v89; // [rsp+14Ch] [rbp+4Ch]
  const OLECHAR *v90; // [rsp+150h] [rbp+50h]
  int v91; // [rsp+158h] [rbp+58h]
  int v92; // [rsp+15Ch] [rbp+5Ch]
  unsigned __int16 *v93; // [rsp+160h] [rbp+60h]
  int v94; // [rsp+168h] [rbp+68h]
  int v95; // [rsp+16Ch] [rbp+6Ch]
  unsigned __int16 *v96; // [rsp+170h] [rbp+70h]
  int v97; // [rsp+178h] [rbp+78h]
  int v98; // [rsp+17Ch] [rbp+7Ch]

  v71 = a5;
  v80 = a9;
  v74 = a1;
  v11 = 0;
  hMem = 0;
  v70 = 0;
  v64 = 0;
  v63 = 0;
  v67 = 0;
  v68 = 0;
  v79 = 0;
  v66 = 0;
  v73 = 0;
  v62 = 0;
  v77 = a4;
  v78 = a3;
  v72 = (unsigned __int16 *)a2;
  v75 = a8;
  v76 = a10;
  v65 = 27;
  EnterCriticalSection(&g_csPushRouter);
  v14 = 2;
  if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(MDM_PUSHROUTER_Context, PushRouterPushRouterGetMessageCallReceived, v13, 1);
  *a2 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a7 )
    *a7 = 0;
  ExistingClientByHandle = PushRouter::FindExistingClientByHandle(v12, v74);
  if ( !ExistingClientByHandle )
  {
    v17 = 0;
LABEL_9:
    v18 = -2147024890;
LABEL_76:
    v49 = v65;
    if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
      McTemplateU0zzzzdd_EventWriteTransfer(
        v16,
        (unsigned int)PushRouterPushRouterGetMessageCallFailed,
        (_DWORD)hMem,
        (_DWORD)v70,
        (__int64)v11,
        (__int64)v17,
        v65,
        v18);
    if ( (unsigned int)dword_180050060 > 2 )
    {
      v50 = (const OLECHAR *)v70;
      v51 = (const OLECHAR *)hMem;
      v71 = (unsigned int *)v74;
      v52 = -1;
      v62 = v49;
      v64 = v18;
      if ( v17 )
      {
        v53 = -1;
        do
          ++v53;
        while ( v17[v53] );
        v54 = 2 * v53 + 2;
      }
      else
      {
        v17 = (unsigned __int16 *)&word_1800401D0;
        v54 = 2;
      }
      v96 = v17;
      v97 = v54;
      v98 = 0;
      if ( v11 )
      {
        v55 = -1;
        do
          ++v55;
        while ( v11[v55] );
        v56 = 2 * v55 + 2;
      }
      else
      {
        v11 = (unsigned __int16 *)&word_1800401D0;
        v56 = 2;
      }
      v93 = v11;
      v94 = v56;
      v95 = 0;
      if ( v70 )
      {
        v57 = -1;
        do
          ++v57;
        while ( *((_WORD *)v70 + v57) );
        v58 = 2 * v57 + 2;
      }
      else
      {
        v50 = &word_1800401D0;
        v58 = 2;
      }
      v90 = v50;
      v91 = v58;
      v92 = 0;
      if ( hMem )
      {
        do
          ++v52;
        while ( *((_WORD *)hMem + v52) );
        v14 = 2 * v52 + 2;
      }
      else
      {
        v51 = &word_1800401D0;
      }
      v87 = v51;
      v85 = &v62;
      v88 = v14;
      v83 = &v71;
      v89 = 0;
      v81 = &v64;
      v86 = 4;
      v84 = 8;
      v82 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_180050060, &byte_180046707, 0);
    }
    goto LABEL_104;
  }
  v17 = (unsigned __int16 *)*((_QWORD *)ExistingClientByHandle + 6);
  if ( !*((_DWORD *)ExistingClientByHandle + 10) )
    goto LABEL_9;
  v19 = &v63;
  if ( !v80 )
    v19 = 0;
  v20 = (enum PushRouterSubmitOrigin *)&v65;
  v21 = &v79;
  v22 = &v73;
  v23 = &v66;
  if ( !a10 )
    v21 = 0;
  if ( !a8 )
    v20 = 0;
  if ( !a7 )
    v22 = 0;
  if ( !a6 )
    v23 = 0;
  MessageW = PushClient::GetMessageW(
               ExistingClientByHandle,
               (unsigned __int8 **)&v68,
               &v64,
               &v67,
               &v62,
               v23,
               v22,
               v20,
               v21,
               v19);
  v27 = v67;
  v28 = 0;
  v11 = v66;
  v18 = MessageW;
  if ( MessageW >= 0 && MessageW != 5439490 )
  {
    if ( a6 )
      *a6 = v66;
    if ( a7 )
      *a7 = v73;
    if ( v75 )
      *(_DWORD *)v75 = v65;
    if ( v76 )
      *v76 = v79;
    if ( v80 )
      *v80 = v63;
    *v77 = (unsigned __int8 *)v68;
    *v78 = v64;
    v16 = (__int64)v71;
    *(_QWORD *)v72 = v27;
    *(_DWORD *)v16 = v62;
  }
  if ( v27 )
  {
    v67 = v27;
    v29 = 0x7FFFFFFF;
    v66 = v27;
    v30 = v27;
    v63 = 0;
    hMem = 0;
    v31 = L"Content-Type";
    do
    {
      if ( !*v31 )
        break;
      ++v31;
      --v29;
    }
    while ( v29 );
    v71 = (unsigned int *)((0x7FFFFFFF - v29) & -(__int64)(v29 != 0));
    if ( v29 )
    {
      v32 = 0x7FFFFFFF;
      v33 = v27;
      do
      {
        if ( !*v33 )
          break;
        ++v33;
        --v32;
      }
      while ( v32 );
      v26 = (0x7FFFFFFF - v32) & -(__int64)(v32 != 0);
      if ( v32 )
      {
        v72 = &v27[v26];
        v34 = v72;
        while ( 1 )
        {
          EndOfHeader = FindEndOfHeader((const unsigned __int16 **)&v67, v34, &v63);
          v28 = 0;
          if ( !EndOfHeader )
            break;
          v35 = v30;
          v36 = 0;
          if ( v63 )
          {
            while ( 1 )
            {
              v37 = *v35++;
              if ( v37 == 58 )
                break;
              if ( ++v36 >= v63 )
                goto LABEL_51;
            }
            v68 = v35;
            v62 = v35 - v30 - 1;
            v64 = v63 - v62;
            if ( (unsigned int)Trim((const unsigned __int16 **)&v66, &v62) )
            {
              if ( (unsigned int *)v62 == v71 && !InvStrCmpNIW(v66, L"Content-Type", (unsigned __int64)v71) )
              {
                v39 = Trim((const unsigned __int16 **)&v68, &v64);
                CopyString(v68, v39 != 0 ? v64 : 0, (unsigned __int16 **)&hMem);
                v28 = 0;
                break;
              }
            }
          }
LABEL_51:
          v30 = v67;
          v34 = v72;
          v66 = v67;
        }
      }
    }
    v66 = v27;
    v40 = L"X-Wap-Application-Id";
    v67 = v27;
    v25 = 0x7FFFFFFF;
    v63 = 0;
    v70 = 0;
    do
    {
      if ( !*v40 )
        break;
      ++v40;
      --v25;
    }
    while ( v25 );
    LODWORD(v16) = 0x7FFFFFFF - v25;
    v41 = (0x7FFFFFFF - v25) & -(__int64)(v25 != 0);
    if ( v25 )
    {
      v16 = 0x7FFFFFFF;
      v42 = v27;
      do
      {
        if ( !*v42 )
          break;
        ++v42;
        --v16;
      }
      while ( v16 );
      v25 = (0x7FFFFFFF - v16) & ((unsigned __int128)-(__int128)(unsigned __int64)v16 >> 64);
      if ( v16 )
      {
        v43 = &v27[v25];
        while ( 1 )
        {
          v47 = FindEndOfHeader((const unsigned __int16 **)&v66, v43, &v63);
          v28 = 0;
          if ( !v47 )
            break;
          v44 = v27;
          v45 = 0;
          if ( v63 )
          {
            while ( 1 )
            {
              v46 = *v44++;
              if ( v46 == 58 )
                break;
              if ( ++v45 >= v63 )
                goto LABEL_71;
            }
            v68 = v44;
            v62 = v44 - v27 - 1;
            v64 = v63 - v62;
            if ( (unsigned int)Trim((const unsigned __int16 **)&v67, &v62) )
            {
              if ( v62 == v41 && !InvStrCmpNIW(v67, L"X-Wap-Application-Id", v41) )
              {
                v48 = Trim((const unsigned __int16 **)&v68, &v64);
                CopyString(v68, v48 != 0 ? v64 : 0, (unsigned __int16 **)&v70);
                break;
              }
            }
          }
LABEL_71:
          v27 = v66;
          v67 = v66;
        }
      }
    }
  }
  if ( v18 < 0 )
    goto LABEL_76;
  if ( v18 != 5439490 )
  {
    v59 = v73;
    v60 = v65;
    if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
      McTemplateU0zzzzzdd_EventWriteTransfer(
        v16,
        v25,
        (_DWORD)hMem,
        (_DWORD)v70,
        (__int64)v11,
        (__int64)v17,
        (__int64)v73,
        v65,
        v18);
    if ( (unsigned int)dword_180050060 > 4 )
    {
      v77 = (unsigned __int8 **)v70;
      v76 = (unsigned __int8 **)hMem;
      v75 = (enum PushRouterSubmitOrigin *)v74;
      v71 = (unsigned int *)v59;
      v72 = v17;
      v78 = (unsigned int *)v11;
      v62 = v60;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v16,
        (unsigned int)word_18004668A,
        v26,
        v28,
        (__int64)&v75,
        (__int64)&v62,
        (__int64)&v76,
        (__int64)&v77,
        (__int64)&v78,
        (__int64)&v72,
        (__int64)&v71);
    }
  }
LABEL_104:
  LeaveCriticalSection(&g_csPushRouter);
  LocalFree(hMem);
  LocalFree(v70);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180018d14  push    rbp
0x180018d16  push    rbx
0x180018d17  push    rsi
0x180018d18  push    rdi
0x180018d19  push    r12
0x180018d1b  push    r13
0x180018d1d  push    r14
0x180018d1f  push    r15
0x180018d21  lea     rbp, [rsp-0A8h]
0x180018d29  sub     rsp, 1A8h
0x180018d30  mov     rax, cs:__security_cookie
0x180018d37  xor     rax, rsp
0x180018d3a  mov     [rbp+0E0h+var_50], rax
0x180018d41  mov     rax, [rbp+0E0h+arg_20]
0x180018d48  mov     r15, rdx
0x180018d4b  mov     rbx, [rbp+0E0h+arg_38]
0x180018d52  mov     r14, [rbp+0E0h+arg_48]
0x180018d59  mov     rsi, [rbp+0E0h+arg_28]
0x180018d60  mov     r12, [rbp+0E0h+arg_30]
0x180018d67  mov     [rbp+0E0h+var_148], rax
0x180018d6b  mov     rax, [rbp+0E0h+arg_40]
0x180018d72  mov     [rbp+0E0h+var_100], rax
0x180018d76  xor     eax, eax
0x180018d78  mov     [rbp+0E0h+var_130], rcx
0x180018d7c  mov     r13d, eax
0x180018d7f  lea     rcx, ?g_csPushRouter@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180018d86  mov     [rbp+0E0h+hMem], rax
0x180018d8a  mov     [rbp+0E0h+var_150], rax
0x180018d8e  mov     [rsp+1E0h+var_178], eax
0x180018d92  mov     [rsp+1E0h+var_17C], eax
0x180018d96  mov     [rsp+1E0h+var_168], rax
0x180018d9b  mov     [rbp+0E0h+var_160], rax
0x180018d9f  mov     [rbp+0E0h+var_108], rax
0x180018da3  mov     [rsp+1E0h+var_170], rax
0x180018da8  mov     [rbp+0E0h+var_138], rax
0x180018dac  mov     [rsp+1E0h+var_180], eax
0x180018db0  mov     [rbp+0E0h+var_118], r9
0x180018db4  mov     [rbp+0E0h+var_110], r8
0x180018db8  mov     [rbp+0E0h+var_140], rdx
0x180018dbc  mov     [rbp+0E0h+var_128], rbx
0x180018dc0  mov     [rbp+0E0h+var_120], r14
0x180018dc4  mov     [rsp+1E0h+var_174], 1Bh
0x180018dcc  call    cs:__imp_EnterCriticalSection
0x180018dd2  lea     edi, [r13+2]
0x180018dd6  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, dil
0x180018ddd  jz      short loc_180018E02
0x180018ddf  lea     rax, [rbp+0E0h+var_60]
0x180018de6  lea     r9d, [r13+1]
0x180018dea  mov     [rsp+1E0h+var_1C0], rax
0x180018def  lea     rdx, PushRouterPushRouterGetMessageCallReceived
0x180018df6  lea     rcx, MDM_PUSHROUTER_Context
0x180018dfd  call    McGenEventWrite_EventWriteTransfer
0x180018e02  xor     eax, eax
0x180018e04  mov     [r15], rax
0x180018e07  test    rsi, rsi
0x180018e0a  jz      short loc_180018E0F
0x180018e0c  mov     [rsi], rax
0x180018e0f  test    r12, r12
0x180018e12  jz      short loc_180018E18
0x180018e14  mov     [r12], rax
0x180018e18  mov     rdx, [rbp+0E0h+var_130]; void *
0x180018e1c  call    ?FindExistingClientByHandle@PushRouter@@QEAAPEAVPushClient@@PEAX@Z; PushRouter::FindExistingClientByHandle(void *)
0x180018e21  xor     r9d, r9d
0x180018e24  mov     r11, rax
0x180018e27  test    rax, rax
0x180018e2a  jnz     short loc_180018E3A
0x180018e2c  mov     r15d, r9d
0x180018e2f  mov     r14d, 80070006h
0x180018e35  jmp     loc_1800191EE
0x180018e3a  mov     r15, [rax+30h]
0x180018e3e  cmp     [rax+28h], r9d
0x180018e42  jz      short loc_180018E2F
0x180018e44  cmp     [rbp+0E0h+var_100], r9
0x180018e48  lea     rax, [rsp+1E0h+var_180]
0x180018e4d  lea     r10, [rsp+1E0h+var_17C]
0x180018e52  cmovz   r10, r9
0x180018e56  lea     r8, [rsp+1E0h+var_174]
0x180018e5b  mov     [rsp+1E0h+var_198], r10; unsigned int *
0x180018e60  lea     r9, [rbp+0E0h+var_108]
0x180018e64  test    r14, r14
0x180018e67  lea     rdx, [rbp+0E0h+var_138]
0x180018e6b  lea     rcx, [rsp+1E0h+var_170]
0x180018e70  cmovz   r9, r13
0x180018e74  test    rbx, rbx
0x180018e77  mov     [rsp+1E0h+var_1A0], r9; unsigned __int8 **
0x180018e7c  lea     r9, [rsp+1E0h+var_168]; unsigned __int16 **
0x180018e81  cmovz   r8, r13
0x180018e85  test    r12, r12
0x180018e88  mov     [rsp+1E0h+var_1A8], r8; enum PushRouterSubmitOrigin *
0x180018e8d  lea     r8, [rsp+1E0h+var_178]; unsigned int *
0x180018e92  cmovz   rdx, r13
0x180018e96  test    rsi, rsi
0x180018e99  mov     [rsp+1E0h+var_1B0], rdx; unsigned __int16 **
0x180018e9e  lea     rdx, [rbp+0E0h+var_160]; unsigned __int8 **
0x180018ea2  cmovz   rcx, r13
0x180018ea6  mov     [rsp+1E0h+var_1B8], rcx; unsigned __int16 **
0x180018eab  mov     rcx, r11; this
0x180018eae  mov     [rsp+1E0h+var_1C0], rax; unsigned int *
0x180018eb3  call    ?GetMessageW@PushClient@@AEAAJPEAPEAEPEAKPEAPEAG122PEAW4PushRouterSubmitOrigin@@01@Z; PushClient::GetMessageW(uchar * *,ulong *,ushort * *,ulong *,ushort * *,ushort * *,PushRouterSubmitOrigin *,uchar * *,ulong *)
0x180018eb8  mov     rbx, [rsp+1E0h+var_168]
0x180018ebd  xor     r9d, r9d
0x180018ec0  mov     r13, [rsp+1E0h+var_170]
0x180018ec5  mov     r14d, eax
0x180018ec8  test    eax, eax
0x180018eca  js      short loc_180018F3C
0x180018ecc  cmp     eax, 530002h
0x180018ed1  jz      short loc_180018F3C
0x180018ed3  test    rsi, rsi
0x180018ed6  jz      short loc_180018EDB
0x180018ed8  mov     [rsi], r13
0x180018edb  test    r12, r12
0x180018ede  jz      short loc_180018EE8
0x180018ee0  mov     rax, [rbp+0E0h+var_138]
0x180018ee4  mov     [r12], rax
0x180018ee8  mov     rax, [rbp+0E0h+var_128]
0x180018eec  test    rax, rax
0x180018eef  jz      short loc_180018EF7
0x180018ef1  mov     ecx, [rsp+1E0h+var_174]
0x180018ef5  mov     [rax], ecx
0x180018ef7  mov     rcx, [rbp+0E0h+var_120]
0x180018efb  test    rcx, rcx
0x180018efe  jz      short loc_180018F07
0x180018f00  mov     rax, [rbp+0E0h+var_108]
0x180018f04  mov     [rcx], rax
0x180018f07  mov     rcx, [rbp+0E0h+var_100]
0x180018f0b  test    rcx, rcx
0x180018f0e  jz      short loc_180018F16
0x180018f10  mov     eax, [rsp+1E0h+var_17C]
0x180018f14  mov     [rcx], eax
0x180018f16  mov     rax, [rbp+0E0h+var_160]
0x180018f1a  mov     rcx, [rbp+0E0h+var_118]
0x180018f1e  mov     [rcx], rax
0x180018f21  mov     rcx, [rbp+0E0h+var_110]
0x180018f25  mov     eax, [rsp+1E0h+var_178]
0x180018f29  mov     [rcx], eax
0x180018f2b  mov     rax, [rbp+0E0h+var_140]
0x180018f2f  mov     rcx, [rbp+0E0h+var_148]
0x180018f33  mov     [rax], rbx
0x180018f36  mov     eax, [rsp+1E0h+var_180]
0x180018f3a  mov     [rcx], eax
0x180018f3c  test    rbx, rbx
0x180018f3f  jz      loc_1800191E5
0x180018f45  mov     esi, 7FFFFFFFh
0x180018f4a  mov     [rsp+1E0h+var_168], rbx
0x180018f4f  mov     edx, esi
0x180018f51  mov     [rsp+1E0h+var_170], rbx
0x180018f56  mov     r12, rbx
0x180018f59  mov     [rsp+1E0h+var_17C], r9d
0x180018f5e  mov     [rbp+0E0h+hMem], r9
0x180018f62  lea     rax, aContentType; "Content-Type"
0x180018f69  cmp     [rax], r9w
0x180018f6d  jz      short loc_180018F78
0x180018f6f  add     rax, rdi
0x180018f72  sub     rdx, 1
0x180018f76  jnz     short loc_180018F69
0x180018f78  mov     rcx, rsi
0x180018f7b  mov     rax, rdx
0x180018f7e  sub     rcx, rdx
0x180018f81  neg     rax
0x180018f84  sbb     rax, rax
0x180018f87  and     rax, rcx
0x180018f8a  mov     [rbp+0E0h+var_148], rax
0x180018f8e  test    rdx, rdx
0x180018f91  jz      loc_1800190A5
0x180018f97  test    rbx, rbx
0x180018f9a  jz      loc_1800190A5
0x180018fa0  mov     rdx, rsi
0x180018fa3  mov     rax, rbx
0x180018fa6  cmp     [rax], r9w
0x180018faa  jz      short loc_180018FB5
0x180018fac  add     rax, rdi
0x180018faf  sub     rdx, 1
0x180018fb3  jnz     short loc_180018FA6
0x180018fb5  mov     rcx, rsi
0x180018fb8  mov     rax, rdx
0x180018fbb  sub     rcx, rdx
0x180018fbe  neg     rax
0x180018fc1  sbb     r8, r8
0x180018fc4  and     r8, rcx
0x180018fc7  test    rdx, rdx
0x180018fca  jz      loc_1800190A5
0x180018fd0  lea     rax, [rbx+r8*2]
0x180018fd4  mov     [rbp+0E0h+var_140], rax
0x180018fd8  mov     rdx, rax
0x180018fdb  jmp     loc_180019062
0x180018fe0  mov     edx, [rsp+1E0h+var_17C]
0x180018fe4  mov     rcx, r12
0x180018fe7  mov     r8d, r9d
0x180018fea  test    edx, edx
0x180018fec  jz      short loc_180019054
0x180018fee  movzx   eax, word ptr [rcx]
0x180018ff1  add     rcx, rdi
0x180018ff4  cmp     ax, 3Ah ; ':'
0x180018ff8  jz      short loc_180019004
0x180018ffa  inc     r8d
0x180018ffd  cmp     r8d, edx
0x180019000  jb      short loc_180018FEE
0x180019002  jmp     short loc_180019054
0x180019004  mov     [rbp+0E0h+var_160], rcx
0x180019008  sub     rcx, r12
0x18001900b  sar     rcx, 1
0x18001900e  lea     eax, [rcx-1]
0x180019011  sub     edx, eax
0x180019013  mov     [rsp+1E0h+var_180], eax
0x180019017  mov     [rsp+1E0h+var_178], edx
0x18001901b  lea     rcx, [rsp+1E0h+var_170]; unsigned __int16 **
0x180019020  lea     rdx, [rsp+1E0h+var_180]; unsigned int *
0x180019025  call    ?Trim@@YAHPEAPEBGPEAK@Z; Trim(ushort const * *,ulong *)
0x18001902a  test    eax, eax
0x18001902c  jz      short loc_180019054
0x18001902e  mov     eax, [rsp+1E0h+var_180]
0x180019032  mov     rcx, [rbp+0E0h+var_148]
0x180019036  cmp     rax, rcx
0x180019039  jnz     short loc_180019054
0x18001903b  mov     r8, rcx
0x18001903e  lea     rdx, aContentType; "Content-Type"
0x180019045  mov     rcx, [rsp+1E0h+var_170]
0x18001904a  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x180019050  test    eax, eax
0x180019052  jz      short loc_18001907E
0x180019054  mov     r12, [rsp+1E0h+var_168]
0x180019059  mov     rdx, [rbp+0E0h+var_140]; unsigned __int16 *
0x18001905d  mov     [rsp+1E0h+var_170], r12
0x180019062  lea     r8, [rsp+1E0h+var_17C]; unsigned int *
0x180019067  lea     rcx, [rsp+1E0h+var_168]; unsigned __int16 **
0x18001906c  call    ?FindEndOfHeader@@YAHPEAPEBGPEBGPEAK@Z; FindEndOfHeader(ushort const * *,ushort const *,ulong *)
0x180019071  xor     r9d, r9d
0x180019074  test    eax, eax
0x180019076  jnz     loc_180018FE0
0x18001907c  jmp     short loc_1800190A5
0x18001907e  lea     rdx, [rsp+1E0h+var_178]; unsigned int *
0x180019083  lea     rcx, [rbp+0E0h+var_160]; unsigned __int16 **
0x180019087  call    ?Trim@@YAHPEAPEBGPEAK@Z; Trim(ushort const * *,ulong *)
0x18001908c  mov     rcx, [rbp+0E0h+var_160]
0x180019090  lea     r8, [rbp+0E0h+hMem]
0x180019094  neg     eax
0x180019096  sbb     edx, edx
0x180019098  and     edx, [rsp+1E0h+var_178]
0x18001909c  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1800190a2  xor     r9d, r9d
0x1800190a5  mov     [rsp+1E0h+var_170], rbx
0x1800190aa  lea     rax, ?c_szAppIdHeader@@3QBGB; "X-Wap-Application-Id"
0x1800190b1  mov     [rsp+1E0h+var_168], rbx
0x1800190b6  mov     rdx, rsi
0x1800190b9  mov     [rsp+1E0h+var_17C], r9d
0x1800190be  mov     [rbp+0E0h+var_150], r9
0x1800190c2  cmp     [rax], r9w
0x1800190c6  jz      short loc_1800190D1
0x1800190c8  add     rax, rdi
0x1800190cb  sub     rdx, 1
0x1800190cf  jnz     short loc_1800190C2
0x1800190d1  mov     rcx, rsi
0x1800190d4  mov     rax, rdx
0x1800190d7  sub     rcx, rdx
0x1800190da  neg     rax
0x1800190dd  sbb     r12, r12
0x1800190e0  and     r12, rcx
0x1800190e3  test    rdx, rdx
0x1800190e6  jz      loc_1800191E5
0x1800190ec  test    rbx, rbx
0x1800190ef  jz      loc_1800191E5
0x1800190f5  mov     rcx, rsi
0x1800190f8  mov     rax, rbx
0x1800190fb  cmp     [rax], r9w
0x1800190ff  jz      short loc_18001910A
0x180019101  add     rax, rdi
0x180019104  sub     rcx, 1
0x180019108  jnz     short loc_1800190FB
0x18001910a  sub     rsi, rcx
0x18001910d  mov     rax, rcx
0x180019110  neg     rax
0x180019113  sbb     rdx, rdx
0x180019116  and     rdx, rsi
0x180019119  test    rcx, rcx
0x18001911c  jz      loc_1800191E5
0x180019122  lea     rsi, [rbx+rdx*2]
0x180019126  jmp     short loc_1800191A2
0x180019128  mov     edx, [rsp+1E0h+var_17C]
0x18001912c  mov     rcx, rbx
0x18001912f  mov     r8d, r9d
0x180019132  test    edx, edx
0x180019134  jz      short loc_180019198
0x180019136  movzx   eax, word ptr [rcx]
0x180019139  add     rcx, rdi
0x18001913c  cmp     ax, 3Ah ; ':'
0x180019140  jz      short loc_18001914C
0x180019142  inc     r8d
0x180019145  cmp     r8d, edx
0x180019148  jb      short loc_180019136
0x18001914a  jmp     short loc_180019198
0x18001914c  mov     [rbp+0E0h+var_160], rcx
0x180019150  sub     rcx, rbx
0x180019153  sar     rcx, 1
0x180019156  lea     eax, [rcx-1]
0x180019159  sub     edx, eax
0x18001915b  mov     [rsp+1E0h+var_180], eax
0x18001915f  mov     [rsp+1E0h+var_178], edx
0x180019163  lea     rcx, [rsp+1E0h+var_168]; unsigned __int16 **
0x180019168  lea     rdx, [rsp+1E0h+var_180]; unsigned int *
0x18001916d  call    ?Trim@@YAHPEAPEBGPEAK@Z; Trim(ushort const * *,ulong *)
  ... truncated ...
```
