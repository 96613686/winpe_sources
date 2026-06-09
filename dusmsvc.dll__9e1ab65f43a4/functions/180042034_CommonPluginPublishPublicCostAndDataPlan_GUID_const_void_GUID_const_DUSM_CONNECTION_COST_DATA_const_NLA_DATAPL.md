# CommonPluginPublishPublicCostAndDataPlan(_GUID const *,void *,_GUID const &,_DUSM_CONNECTION_COST_DATA const &,_NLA_DATAPLAN_STATUS const &)

- ea: `0x180042034`
- end: `0x1800422cc`
- name: `?CommonPluginPublishPublicCostAndDataPlan@@YAXPEBU_GUID@@PEAXAEBU1@AEBU_DUSM_CONNECTION_COST_DATA@@AEBU_NLA_DATAPLAN_STATUS@@@Z`
- size: `664`
- prototype: `void(const struct _GUID *, void *, const struct _GUID *, const struct _DUSM_CONNECTION_COST_DATA *, const struct _NLA_DATAPLAN_STATUS *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003050c`

## callees

- `0x180001234`
- `0x1800021e4`
- `0x18000758c`
- `0x180007c90`
- `0x180008704`
- `0x180013444`
- `0x180042034`
- `0x18004349c`
- `0x180043788`
- `0x1800438ec`
- `0x1800439f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004208e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004208e`

## pseudocode

```c
void __fastcall CommonPluginPublishPublicCostAndDataPlan(
        const struct _GUID *a1,
        _QWORD *a2,
        const struct _GUID *a3,
        const struct _DUSM_CONNECTION_COST_DATA *a4,
        const struct _NLA_DATAPLAN_STATUS *a5)
{
  __int64 v9; // rdx
  __int64 v10; // rcx
  _DWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // ebx
  _DWORD *v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  char *v18; // rdx
  __int64 v19; // rax
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int64 v22; // rdx
  __int64 v23; // rcx
  int v24; // edi
  __int64 v25; // rdx
  __int64 v26; // rcx
  _DWORD *v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  int v30; // [rsp+60h] [rbp-A0h] BYREF
  int v31; // [rsp+64h] [rbp-9Ch] BYREF
  int v32; // [rsp+68h] [rbp-98h] BYREF
  int v33; // [rsp+6Ch] [rbp-94h] BYREF
  int v34; // [rsp+70h] [rbp-90h] BYREF
  __int64 v35; // [rsp+78h] [rbp-88h] BYREF
  __int64 v36; // [rsp+80h] [rbp-80h] BYREF
  const struct _GUID *v37; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v38; // [rsp+90h] [rbp-70h] BYREF
  _DWORD v39[2]; // [rsp+98h] [rbp-68h] BYREF
  __int128 *v40; // [rsp+A0h] [rbp-60h]
  _DWORD v41[2]; // [rsp+A8h] [rbp-58h] BYREF
  int *v42; // [rsp+B0h] [rbp-50h]
  _DWORD v43[2]; // [rsp+B8h] [rbp-48h] BYREF
  OLECHAR *v44; // [rsp+C0h] [rbp-40h]
  int v45; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v46; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v47; // [rsp+E0h] [rbp-20h]
  __int64 v48; // [rsp+F0h] [rbp-10h]
  OLECHAR sz[40]; // [rsp+100h] [rbp+0h] BYREF

  v45 = *(_DWORD *)a4;
  memset_0(sz, 0, sizeof(sz));
  if ( !StringFromGUID2(a3, sz, 40) )
  {
    v11 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v10, v9) + 8);
    if ( *v11 > 5u )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (int)v11,
        (int)byte_18005C4E9);
    return;
  }
  v38 = 0;
  if ( !a2 )
  {
    v14 = NlaplgRegister((__int64)a1, &v38);
    if ( v14 )
    {
      v15 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v13, v12) + 8);
      if ( *v15 <= 5u )
        goto LABEL_21;
      v18 = byte_18005C49B;
      goto LABEL_8;
    }
    a2 = v38;
  }
  v43[0] = 5;
  v44 = sz;
  v19 = -1;
  do
    ++v19;
  while ( sz[v19] );
  v20 = *(_OWORD *)a5;
  v21 = *((_OWORD *)a5 + 1);
  v43[1] = 2 * v19 + 2;
  v41[0] = 33;
  v42 = &v45;
  v41[1] = 4;
  v40 = &v46;
  v46 = v20;
  v39[0] = 34;
  *(_QWORD *)&v20 = *((_QWORD *)a5 + 4);
  v47 = v21;
  v39[1] = 40;
  v48 = v20;
  v24 = NlaplgAddRow(a2, 3u, v43, v41, v39);
  if ( v24 )
  {
    v15 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v23, v22) + 8);
    if ( *v15 > 5u )
    {
      v30 = v24;
      v18 = byte_18005C403;
      goto LABEL_9;
    }
  }
  else
  {
    v14 = NlaplgCommit(a2);
    if ( !v14 )
    {
      v27 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v26, v25) + 8);
      if ( *v27 > 5u )
      {
        v35 = *(_QWORD *)((char *)&v46 + 4);
        v30 = v46;
        v36 = *((_QWORD *)&v47 + 1);
        v31 = v48;
        v32 = HIDWORD(v46);
        v33 = *((_DWORD *)a4 + 1);
        v34 = *(_DWORD *)a4;
        v37 = a3;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          (int)v27,
          (int)&word_18005C2DE,
          v28,
          v29,
          (__int64 *)&v37,
          (__int64)&v34,
          (__int64)&v33,
          (__int64)&v32,
          (__int64)&v31,
          (__int64)&v36,
          (__int64)&v30,
          (__int64)&v35);
      }
      goto LABEL_21;
    }
    v15 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v26, v25) + 8);
    if ( *v15 > 5u )
    {
      v18 = &byte_18005C44F;
LABEL_8:
      v30 = v14;
LABEL_9:
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (int)v15,
        (int)v18,
        v16,
        v17,
        (__int64)&v30);
    }
  }
LABEL_21:
  if ( v38 )
    NlaplgUnregister();
}

```

## disassembly

```asm
0x180042034  push    rbp
0x180042036  push    rbx
0x180042037  push    rsi
0x180042038  push    rdi
0x180042039  push    r12
0x18004203b  push    r14
0x18004203d  push    r15
0x18004203f  lea     rbp, [rsp-60h]
0x180042044  sub     rsp, 160h
0x18004204b  mov     rax, cs:__security_cookie
0x180042052  xor     rax, rsp
0x180042055  mov     [rbp+90h+var_40], rax
0x180042059  mov     eax, [r9]
0x18004205c  mov     rbx, rdx
0x18004205f  mov     r14, [rbp+90h+arg_20]
0x180042066  xor     edx, edx; Val
0x180042068  mov     r15, r8
0x18004206b  mov     [rbp+90h+var_C8], eax
0x18004206e  mov     rdi, rcx
0x180042071  mov     rsi, r9
0x180042074  lea     rcx, [rbp+90h+sz]; void *
0x180042078  lea     r8d, [rdx+50h]; Size
0x18004207c  call    memset_0
0x180042081  mov     r8d, 28h ; '('; cchMax
0x180042087  lea     rdx, [rbp+90h+sz]; lpsz
0x18004208b  mov     rcx, r15; rguid
0x18004208e  call    cs:__imp_StringFromGUID2
0x180042094  xor     r12d, r12d
0x180042097  test    eax, eax
0x180042099  jnz     short loc_1800420C0
0x18004209b  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x1800420a0  mov     rcx, [rax+8]
0x1800420a4  mov     eax, [rcx]
0x1800420a6  cmp     eax, 5
0x1800420a9  jbe     loc_1800422AE
0x1800420af  lea     rdx, byte_18005C4E9
0x1800420b6  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800420bb  jmp     loc_1800422AE
0x1800420c0  mov     [rbp+90h+var_100], r12
0x1800420c4  test    rbx, rbx
0x1800420c7  jnz     short loc_180042112
0x1800420c9  lea     rdx, [rbp+90h+var_100]
0x1800420cd  mov     rcx, rdi; int
0x1800420d0  call    NlaplgRegister
0x1800420d5  mov     ebx, eax
0x1800420d7  test    eax, eax
0x1800420d9  jz      short loc_18004210E
0x1800420db  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x1800420e0  mov     rcx, [rax+8]
0x1800420e4  mov     edx, [rcx]
0x1800420e6  cmp     edx, 5
0x1800420e9  jbe     loc_1800422A0
0x1800420ef  lea     rdx, byte_18005C49B
0x1800420f6  mov     [rsp+190h+var_130], ebx
0x1800420fa  lea     rax, [rsp+190h+var_130]
0x1800420ff  mov     [rsp+190h+var_170], rax
0x180042104  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180042109  jmp     loc_1800422A0
0x18004210e  mov     rbx, [rbp+90h+var_100]
0x180042112  lea     rax, [rbp+90h+sz]
0x180042116  mov     [rbp+90h+var_D8], 5
0x18004211d  mov     [rbp+90h+var_D0], rax
0x180042121  lea     rcx, [rbp+90h+sz]
0x180042125  or      rax, 0FFFFFFFFFFFFFFFFh
0x180042129  inc     rax
0x18004212c  cmp     [rcx+rax*2], r12w
0x180042131  jnz     short loc_180042129
0x180042133  movups  xmm0, xmmword ptr [r14]
0x180042137  lea     eax, ds:2[rax*2]
0x18004213e  mov     edx, 3
0x180042143  movups  xmm1, xmmword ptr [r14+10h]
0x180042148  mov     [rbp+90h+var_D4], eax
0x18004214b  lea     r9, [rbp+90h+var_E8]
0x18004214f  lea     rax, [rbp+90h+var_C8]
0x180042153  mov     [rbp+90h+var_E8], 21h ; '!'
0x18004215a  mov     [rbp+90h+var_E0], rax
0x18004215e  lea     r8, [rbp+90h+var_D8]
0x180042162  lea     rax, [rbp+90h+var_C0]
0x180042166  mov     [rbp+90h+var_E4], 4
0x18004216d  mov     [rbp+90h+var_F0], rax
0x180042171  mov     rcx, rbx
0x180042174  movups  [rbp+90h+var_C0], xmm0
0x180042178  lea     rax, [rbp+90h+var_F8]
0x18004217c  mov     [rbp+90h+var_F8], 22h ; '"'
0x180042183  movsd   xmm0, qword ptr [r14+20h]
0x180042189  mov     [rsp+190h+var_170], rax
0x18004218e  movups  [rbp+90h+var_B0], xmm1
0x180042192  mov     [rbp+90h+var_F4], 28h ; '('
0x180042199  movsd   [rbp+90h+var_A0], xmm0
0x18004219e  call    NlaplgAddRow
0x1800421a3  mov     edi, eax
0x1800421a5  test    eax, eax
0x1800421a7  jz      short loc_1800421CD
0x1800421a9  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x1800421ae  mov     rcx, [rax+8]
0x1800421b2  mov     edx, [rcx]
0x1800421b4  cmp     edx, 5
0x1800421b7  jbe     loc_1800422A0
0x1800421bd  mov     [rsp+190h+var_130], edi
0x1800421c1  lea     rdx, byte_18005C403
0x1800421c8  jmp     loc_1800420FA
0x1800421cd  mov     rcx, rbx
0x1800421d0  call    NlaplgCommit
0x1800421d5  mov     ebx, eax
0x1800421d7  test    eax, eax
0x1800421d9  jz      short loc_1800421FB
0x1800421db  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x1800421e0  mov     rcx, [rax+8]
0x1800421e4  mov     edx, [rcx]
0x1800421e6  cmp     edx, 5
0x1800421e9  jbe     loc_1800422A0
0x1800421ef  lea     rdx, byte_18005C44F
0x1800421f6  jmp     loc_1800420F6
0x1800421fb  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180042200  mov     rcx, [rax+8]
0x180042204  mov     eax, [rcx]
0x180042206  cmp     eax, 5
0x180042209  jbe     loc_1800422A0
0x18004220f  mov     rax, qword ptr [rbp+90h+var_C0+4]
0x180042213  lea     rdx, word_18005C2DE
0x18004221a  mov     [rsp+190h+var_118], rax
0x18004221f  mov     eax, dword ptr [rbp+90h+var_C0]
0x180042222  mov     [rsp+190h+var_130], eax
0x180042226  mov     rax, qword ptr [rbp+90h+var_B0+8]
0x18004222a  mov     [rbp+90h+var_110], rax
0x18004222e  mov     eax, dword ptr [rbp+90h+var_A0]
0x180042231  mov     [rsp+190h+var_12C], eax
0x180042235  mov     eax, dword ptr [rbp+90h+var_C0+0Ch]
0x180042238  mov     [rsp+190h+var_128], eax
0x18004223c  mov     eax, [rsi+4]
0x18004223f  mov     [rsp+190h+var_124], eax
0x180042243  mov     eax, [rsi]
0x180042245  mov     [rsp+190h+var_120], eax
0x180042249  lea     rax, [rsp+190h+var_118]
0x18004224e  mov     [rsp+190h+var_138], rax
0x180042253  lea     rax, [rsp+190h+var_130]
0x180042258  mov     [rsp+190h+var_140], rax
0x18004225d  lea     rax, [rbp+90h+var_110]
0x180042261  mov     [rsp+190h+var_148], rax
0x180042266  lea     rax, [rsp+190h+var_12C]
0x18004226b  mov     [rsp+190h+var_150], rax
0x180042270  lea     rax, [rsp+190h+var_128]
0x180042275  mov     [rsp+190h+var_158], rax
0x18004227a  lea     rax, [rsp+190h+var_124]
0x18004227f  mov     [rsp+190h+var_160], rax
0x180042284  lea     rax, [rsp+190h+var_120]
0x180042289  mov     [rsp+190h+var_168], rax
0x18004228e  lea     rax, [rbp+90h+var_108]
0x180042292  mov     [rsp+190h+var_170], rax
0x180042297  mov     [rbp+90h+var_108], r15
0x18004229b  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U?$_tlgWrapperByVal@$07@@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@444AEBU?$_tlgWrapperByVal@$07@@45@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800422a0  mov     rcx, [rbp+90h+var_100]
0x1800422a4  test    rcx, rcx
0x1800422a7  jz      short loc_1800422AE
0x1800422a9  call    NlaplgUnregister
0x1800422ae  mov     rcx, [rbp+90h+var_40]
0x1800422b2  xor     rcx, rsp; StackCookie
0x1800422b5  call    __security_check_cookie
0x1800422ba  add     rsp, 160h
0x1800422c1  pop     r15
0x1800422c3  pop     r14
0x1800422c5  pop     r12
0x1800422c7  pop     rdi
0x1800422c8  pop     rsi
0x1800422c9  pop     rbx
0x1800422ca  pop     rbp
0x1800422cb  retn
```
