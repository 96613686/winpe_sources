# HAlertDataCollector::Load(void)

- ea: `0x1800f5040`
- end: `0x1800f5b58`
- name: `?Load@HAlertDataCollector@@UEAAJXZ`
- size: `2840`
- prototype: `__int64 __fastcall(HAlertDataCollector *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180012ef0`
- `0x1800c4850`
- `0x1800f5040`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800f53a2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800f53be`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800f53a2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800f53be`
- `pdh!PdhOpenQueryW` at `0x1800f5137`
- `pdh!PdhOpenQueryW` at `0x1800f5137`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800f57e2`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800f57e2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800f5b2c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800f5b2c`

## pseudocode

```c
__int64 __fastcall HAlertDataCollector::Load(HAlertDataCollector *this)
{
  ULONG v1; // r14d
  int v3; // eax
  __int64 v4; // rbx
  int *v5; // r9
  int *v6; // rax
  PDH_STATUS v7; // eax
  __int64 v8; // rbx
  void *v9; // rax
  __int64 v10; // rbx
  void *v11; // rax
  __int64 v12; // rbx
  int v13; // eax
  __int64 v14; // rbx
  int v15; // eax
  __int64 v16; // rbx
  int v17; // eax
  __int64 v18; // rbx
  int v19; // eax
  __int64 v20; // rbx
  int v21; // eax
  __int64 v22; // rbx
  int v23; // eax
  __int64 v24; // rbx
  SAFEARRAY **v25; // r13
  int v26; // eax
  __int64 v27; // rbx
  HRESULT v28; // eax
  __int64 v29; // rbx
  __int64 v30; // rbx
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // r9
  __int64 v37; // rax
  int v38; // eax
  int v39; // eax
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+70h] [rbp-90h] BYREF
  int v44; // [rsp+78h] [rbp-88h] BYREF
  int v45; // [rsp+80h] [rbp-80h] BYREF
  void *ppvData; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v47[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v48[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v49[64]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v50[64]; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int16 v51[64]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v52[64]; // [rsp+310h] [rbp+210h] BYREF
  unsigned __int16 v53[64]; // [rsp+390h] [rbp+290h] BYREF
  unsigned __int16 v54[64]; // [rsp+410h] [rbp+310h] BYREF
  unsigned __int16 v55[64]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v56[64]; // [rsp+510h] [rbp+410h] BYREF
  unsigned __int16 v57[64]; // [rsp+590h] [rbp+490h] BYREF
  unsigned __int16 v58[64]; // [rsp+610h] [rbp+510h] BYREF
  unsigned __int16 v59[64]; // [rsp+690h] [rbp+590h] BYREF
  unsigned __int16 v60[64]; // [rsp+710h] [rbp+610h] BYREF
  unsigned __int16 v61[64]; // [rsp+790h] [rbp+690h] BYREF

  v1 = 0;
  ppvData = 0;
  v3 = HDataCollector::Load(this);
  v45 = v3;
  if ( v3 < 0 )
  {
    v43 = 0;
    v44 = v3;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v47, 0x4000000000000800uLL);
      v4 = -1;
      do
        ++v4;
      while ( v47[v4] );
      v5 = &v44;
      v6 = &v43;
LABEL_119:
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v5, 4, byte_180147320, 1, v6, 4);
    }
    goto LABEL_120;
  }
  v7 = PdhOpenQueryW(0, 0, (PDH_HQUERY *)this + 31);
  v45 = v7;
  if ( v7 < 0 )
  {
    v44 = 0;
    v43 = v7;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_120;
    }
    PlaiWhoAmI(v48, 0x4000000000000800uLL);
    v8 = -1;
    do
      ++v8;
    while ( v48[v8] );
    goto LABEL_14;
  }
  v9 = PlaiAlloc(0x800u, 1, 0, byte_180147320, v41);
  *((_QWORD *)this + 35) = v9;
  if ( !v9 )
  {
    v45 = -2147024882;
    v43 = -2147024882;
    v44 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_120;
    }
    PlaiWhoAmI(v49, 0x4000000000000800uLL);
    v10 = -1;
    do
      ++v10;
    while ( v49[v10] );
    goto LABEL_14;
  }
  v11 = PlaiAlloc(0x800u, 1, 0, byte_180147320, v42);
  *((_QWORD *)this + 36) = v11;
  if ( !v11 )
  {
    v45 = -2147024882;
    v43 = -2147024882;
    v44 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_120;
    }
    PlaiWhoAmI(v50, 0x4000000000000800uLL);
    v12 = -1;
    do
      ++v12;
    while ( v50[v12] );
    goto LABEL_14;
  }
  LoadStringW(g_hInstance, 0xC9u, *((LPWSTR *)this + 35), 1024);
  LoadStringW(g_hInstance, 0xCAu, *((LPWSTR *)this + 36), 1024);
  v13 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 30) + 272LL))(
          *((_QWORD *)this + 30),
          (char *)this + 192);
  v45 = v13;
  if ( v13 < 0 )
  {
    v44 = 0;
    v43 = v13;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_120;
    }
    PlaiWhoAmI(v51, 0x4000000000000800uLL);
    v14 = -1;
    do
      ++v14;
    while ( v51[v14] );
    goto LABEL_14;
  }
  v15 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 30) + 368LL))(
          *((_QWORD *)this + 30),
          (char *)this + 232);
  v45 = v15;
  if ( v15 < 0 )
  {
    v44 = 0;
    v43 = v15;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_120;
    }
    PlaiWhoAmI(v52, 0x4000000000000800uLL);
    v16 = -1;
    do
      ++v16;
    while ( v52[v16] );
    goto LABEL_14;
  }
  v17 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 30) + 304LL))(
          *((_QWORD *)this + 30),
          (char *)this + 200);
  v45 = v17;
  if ( v17 < 0 )
  {
    v44 = 0;
    v43 = v17;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_120;
    }
    PlaiWhoAmI(v53, 0x4000000000000800uLL);
    v18 = -1;
    do
      ++v18;
    while ( v53[v18] );
    goto LABEL_14;
  }
  v19 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 30) + 320LL))(
          *((_QWORD *)this + 30),
          (char *)this + 208);
  v45 = v19;
  if ( v19 < 0 )
  {
    v44 = 0;
    v43 = v19;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_120;
    }
    PlaiWhoAmI(v54, 0x4000000000000800uLL);
    v20 = -1;
    do
      ++v20;
    while ( v54[v20] );
    goto LABEL_14;
  }
  v21 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 30) + 336LL))(
          *((_QWORD *)this + 30),
          (char *)this + 216);
  v45 = v21;
  if ( v21 < 0 )
  {
    v44 = 0;
    v43 = v21;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_120;
    }
    PlaiWhoAmI(v55, 0x4000000000000800uLL);
    v22 = -1;
    do
      ++v22;
    while ( v55[v22] );
    goto LABEL_14;
  }
  v23 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 30) + 352LL))(
          *((_QWORD *)this + 30),
          (char *)this + 224);
  v45 = v23;
  if ( v23 < 0 )
  {
    v44 = 0;
    v43 = v23;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_120;
    }
    PlaiWhoAmI(v56, 0x4000000000000800uLL);
    v24 = -1;
    do
      ++v24;
    while ( v56[v24] );
    goto LABEL_14;
  }
  v25 = (SAFEARRAY **)((char *)this + 184);
  v26 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 30) + 256LL))(
          *((_QWORD *)this + 30),
          (char *)this + 184);
  v45 = v26;
  if ( v26 < 0 )
  {
    v44 = 0;
    v43 = v26;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_120;
    }
    PlaiWhoAmI(v57, 0x4000000000000800uLL);
    v27 = -1;
    do
      ++v27;
    while ( v57[v27] );
    goto LABEL_14;
  }
  v28 = SafeArrayAccessData(*v25, &ppvData);
  v45 = v28;
  if ( v28 < 0 )
  {
    v44 = 0;
    v43 = v28;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_120;
    }
    PlaiWhoAmI(v58, 0x4000000000000800uLL);
    v29 = -1;
    do
      ++v29;
    while ( v58[v29] );
LABEL_14:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v43, 4, byte_180147320, 1, &v44, 4);
    goto LABEL_120;
  }
  v30 = -1;
  while ( v1 < (*v25)->rgsabound[0].cElements )
  {
    v31 = (*(__int64 (__fastcall **)(HAlertDataCollector *, _QWORD))(*(_QWORD *)this + 112LL))(
            this,
            *((_QWORD *)ppvData + v1));
    v32 = 0;
    v45 = v31;
    if ( v31 < 0 )
    {
      v33 = *((_QWORD *)ppvData + v1);
      if ( v33 )
      {
        v34 = -1;
        do
          ++v34;
        while ( *(_WORD *)(v33 + 2 * v34) );
        v35 = (unsigned int)(2 * v34) + 2LL;
      }
      else
      {
        v35 = 0;
      }
      v36 = *((_QWORD *)this + 7);
      if ( v36 )
      {
        v37 = -1;
        do
          ++v37;
        while ( *(_WORD *)(v36 + 2 * v37) );
        v32 = (unsigned int)(2 * v37) + 2LL;
      }
      v45 = EventingWriteEvent(&g_Eventing, &PLA_EVENTLOG_CNTRADD_FAILED, 3, v36, v32, v33, v35, &v45, 4);
      if ( v45 < 0 )
      {
        v44 = 0;
        v43 = v45;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v59, 0x4000000000000800uLL);
          do
            ++v30;
          while ( v59[v30] );
          goto LABEL_14;
        }
        goto LABEL_120;
      }
    }
    ++v1;
  }
  v38 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 30) + 288LL))(
          *((_QWORD *)this + 30),
          (char *)this + 196);
  v45 = v38;
  if ( v38 >= 0 )
  {
    v39 = (*(__int64 (__fastcall **)(HAlertDataCollector *, _QWORD))(*(_QWORD *)this + 48LL))(
            this,
            *((unsigned int *)this + 49));
    v45 = v39;
    if ( v39 < 0 )
    {
      v44 = 0;
      v43 = v39;
      if ( (_DWORD)xmmword_180169738 )
      {
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v61, 0x4000000000000800uLL);
          do
            ++v30;
          while ( v61[v30] );
          v5 = &v43;
          v6 = &v44;
          goto LABEL_119;
        }
      }
    }
  }
  else
  {
    v43 = v38;
    v44 = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v60, 0x4000000000000800uLL);
      do
        ++v30;
      while ( v60[v30] );
      goto LABEL_14;
    }
  }
LABEL_120:
  if ( ppvData )
    SafeArrayUnaccessData(*((SAFEARRAY **)this + 23));
  return (unsigned int)v45;
}

```

## disassembly

```asm
0x1800f5040  push    rbp
0x1800f5042  push    rbx
0x1800f5043  push    rsi
0x1800f5044  push    rdi
0x1800f5045  push    r12
0x1800f5047  push    r13
0x1800f5049  push    r14
0x1800f504b  push    r15
0x1800f504d  lea     rbp, [rsp-728h]
0x1800f5055  sub     rsp, 828h
0x1800f505c  mov     rax, cs:__security_cookie
0x1800f5063  xor     rax, rsp
0x1800f5066  mov     [rbp+760h+var_50], rax
0x1800f506d  xor     r14d, r14d
0x1800f5070  mov     rdi, rcx
0x1800f5073  mov     [rbp+760h+var_7E0], r14d
0x1800f5077  mov     [rbp+760h+ppvData], r14
0x1800f507b  call    ?Load@HDataCollector@@UEAAJXZ; HDataCollector::Load(void)
0x1800f5080  mov     [rbp+760h+var_7E0], eax
0x1800f5083  test    eax, eax
0x1800f5085  jns     loc_1800F512C
0x1800f508b  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800f5092  mov     [rsp+860h+var_7F0], r14d
0x1800f5097  mov     [rsp+860h+var_7E8], eax
0x1800f509b  jz      loc_1800F5B1F
0x1800f50a1  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f50ab  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f50b2  jz      loc_1800F5B1F
0x1800f50b8  mov     rax, cs:qword_180169748
0x1800f50bf  and     rax, rdx
0x1800f50c2  cmp     cs:qword_180169748, rax
0x1800f50c9  jnz     loc_1800F5B1F
0x1800f50cf  lea     rcx, [rbp+760h+var_7D0]; unsigned __int16 *
0x1800f50d3  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f50d8  lea     rax, [rbp+760h+var_7D0]
0x1800f50dc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800f50e0  inc     rbx
0x1800f50e3  cmp     [rax+rbx*2], r14w
0x1800f50e8  jnz     short loc_1800F50E0
0x1800f50ea  lea     rax, [rbp+760h+var_7D0]
0x1800f50ee  mov     esi, 4
0x1800f50f3  lea     ecx, [rbx+rbx]
0x1800f50f6  add     rcx, 2
0x1800f50fa  lea     r9, [rsp+860h+var_7E8]
0x1800f50ff  mov     [rsp+860h+var_800], rcx
0x1800f5104  mov     [rsp+860h+var_808], rax
0x1800f5109  lea     r12d, [rsi-3]
0x1800f510d  lea     rax, aHalertdatacoll; "HAlertDataCollector::Load"
0x1800f5114  mov     [rsp+860h+var_810], 1Ah
0x1800f511d  mov     [rsp+860h+var_818], rax
0x1800f5122  lea     rax, [rsp+860h+var_7F0]
0x1800f5127  jmp     loc_1800F5AE6
0x1800f512c  lea     r8, [rdi+0F8h]; phQuery
0x1800f5133  xor     edx, edx; dwUserData
0x1800f5135  xor     ecx, ecx; szDataSource
0x1800f5137  call    cs:__imp_PdhOpenQueryW
0x1800f513d  mov     [rbp+760h+var_7E0], eax
0x1800f5140  test    eax, eax
0x1800f5142  jns     loc_1800F5204
0x1800f5148  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800f514f  mov     [rsp+860h+var_7E8], r14d
0x1800f5154  mov     [rsp+860h+var_7F0], eax
0x1800f5158  jz      loc_1800F5B1F
0x1800f515e  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f5168  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f516f  jz      loc_1800F5B1F
0x1800f5175  mov     rax, cs:qword_180169748
0x1800f517c  and     rax, rdx
0x1800f517f  cmp     cs:qword_180169748, rax
0x1800f5186  jnz     loc_1800F5B1F
0x1800f518c  lea     rcx, [rbp+760h+var_750]; unsigned __int16 *
0x1800f5190  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f5195  lea     rax, [rbp+760h+var_750]
0x1800f5199  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800f519d  inc     rbx
0x1800f51a0  cmp     [rax+rbx*2], r14w
0x1800f51a5  jnz     short loc_1800F519D
0x1800f51a7  mov     esi, 4
0x1800f51ac  lea     rax, [rbp+760h+var_750]
0x1800f51b0  lea     r12d, [rsi-3]
0x1800f51b4  lea     ecx, [rbx+rbx]
0x1800f51b7  add     rcx, 2
0x1800f51bb  mov     [rsp+860h+var_800], rcx
0x1800f51c0  mov     [rsp+860h+var_808], rax
0x1800f51c5  lea     rax, aHalertdatacoll; "HAlertDataCollector::Load"
0x1800f51cc  mov     [rsp+860h+var_810], 1Ah
0x1800f51d5  mov     [rsp+860h+var_818], rax
0x1800f51da  lea     rax, [rsp+860h+var_7E8]
0x1800f51df  mov     [rsp+860h+var_820], rsi
0x1800f51e4  mov     [rsp+860h+var_828], rax
0x1800f51e9  lea     rax, byte_180147320
0x1800f51f0  mov     [rsp+860h+var_830], r12
0x1800f51f5  mov     [rsp+860h+var_838], rax
0x1800f51fa  lea     r9, [rsp+860h+var_7F0]
0x1800f51ff  jmp     loc_1800F5B01
0x1800f5204  xor     r8d, r8d; int
0x1800f5207  lea     r15, byte_180147320
0x1800f520e  mov     ebx, 800h
0x1800f5213  mov     r9, r15; char *
0x1800f5216  mov     ecx, ebx; dwBytes
0x1800f5218  lea     r12d, [r8+1]
0x1800f521c  mov     edx, r12d; int
0x1800f521f  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800f5224  mov     [rdi+118h], rax
0x1800f522b  test    rax, rax
0x1800f522e  jnz     loc_1800F52F1
0x1800f5234  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800f523b  mov     eax, 8007000Eh
0x1800f5240  mov     [rbp+760h+var_7E0], eax
0x1800f5243  mov     [rsp+860h+var_7F0], eax
0x1800f5247  mov     [rsp+860h+var_7E8], r14d
0x1800f524c  jz      loc_1800F5B1F
0x1800f5252  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f525c  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f5263  jz      loc_1800F5B1F
0x1800f5269  mov     rax, cs:qword_180169748
0x1800f5270  and     rax, rdx
0x1800f5273  cmp     cs:qword_180169748, rax
0x1800f527a  jnz     loc_1800F5B1F
0x1800f5280  lea     rcx, [rbp+760h+var_6D0]; unsigned __int16 *
0x1800f5287  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f528c  lea     rax, [rbp+760h+var_6D0]
0x1800f5293  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800f5297  inc     rbx
0x1800f529a  cmp     [rax+rbx*2], r14w
0x1800f529f  jnz     short loc_1800F5297
0x1800f52a1  lea     rax, [rbp+760h+var_6D0]
0x1800f52a8  lea     ecx, [rbx+rbx]
0x1800f52ab  mov     esi, 4
0x1800f52b0  add     rcx, 2
0x1800f52b4  mov     [rsp+860h+var_800], rcx
0x1800f52b9  mov     [rsp+860h+var_808], rax
0x1800f52be  lea     rax, aHalertdatacoll; "HAlertDataCollector::Load"
0x1800f52c5  mov     [rsp+860h+var_810], 1Ah
0x1800f52ce  mov     [rsp+860h+var_818], rax
0x1800f52d3  lea     rax, [rsp+860h+var_7E8]
0x1800f52d8  mov     [rsp+860h+var_820], rsi
0x1800f52dd  mov     [rsp+860h+var_828], rax
0x1800f52e2  mov     [rsp+860h+var_830], r12
0x1800f52e7  mov     [rsp+860h+var_838], r15
0x1800f52ec  jmp     loc_1800F51FA
0x1800f52f1  mov     r9, r15; char *
0x1800f52f4  xor     r8d, r8d; int
0x1800f52f7  mov     edx, r12d; int
0x1800f52fa  mov     rcx, rbx; dwBytes
0x1800f52fd  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800f5302  mov     [rdi+120h], rax
0x1800f5309  test    rax, rax
0x1800f530c  jnz     short loc_1800F5387
0x1800f530e  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800f5315  mov     eax, 8007000Eh
0x1800f531a  mov     [rbp+760h+var_7E0], eax
0x1800f531d  mov     [rsp+860h+var_7F0], eax
0x1800f5321  mov     [rsp+860h+var_7E8], r14d
0x1800f5326  jz      loc_1800F5B1F
0x1800f532c  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f5336  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f533d  jz      loc_1800F5B1F
0x1800f5343  mov     rax, cs:qword_180169748
0x1800f534a  and     rax, rdx
0x1800f534d  cmp     cs:qword_180169748, rax
0x1800f5354  jnz     loc_1800F5B1F
0x1800f535a  lea     rcx, [rbp+760h+var_650]; unsigned __int16 *
0x1800f5361  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f5366  lea     rax, [rbp+760h+var_650]
0x1800f536d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800f5371  inc     rbx
0x1800f5374  cmp     [rax+rbx*2], r14w
0x1800f5379  jnz     short loc_1800F5371
0x1800f537b  lea     rax, [rbp+760h+var_650]
0x1800f5382  jmp     loc_1800F52A8
0x1800f5387  mov     r8, [rdi+118h]; lpBuffer
0x1800f538e  mov     ebx, 400h
0x1800f5393  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800f539a  mov     r9d, ebx; cchBufferMax
0x1800f539d  mov     edx, 0C9h; uID
0x1800f53a2  call    cs:__imp_LoadStringW
0x1800f53a8  mov     r8, [rdi+120h]; lpBuffer
0x1800f53af  mov     r9d, ebx; cchBufferMax
0x1800f53b2  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800f53b9  mov     edx, 0CAh; uID
0x1800f53be  call    cs:__imp_LoadStringW
0x1800f53c4  mov     rcx, [rdi+0F0h]
0x1800f53cb  lea     rdx, [rdi+0C0h]
0x1800f53d2  mov     rax, [rcx]
0x1800f53d5  mov     rax, [rax+110h]
0x1800f53dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f53e1  mov     [rbp+760h+var_7E0], eax
0x1800f53e4  test    eax, eax
0x1800f53e6  jns     short loc_1800F5459
0x1800f53e8  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800f53ef  mov     [rsp+860h+var_7E8], r14d
0x1800f53f4  mov     [rsp+860h+var_7F0], eax
0x1800f53f8  jz      loc_1800F5B1F
0x1800f53fe  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f5408  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f540f  jz      loc_1800F5B1F
0x1800f5415  mov     rax, cs:qword_180169748
0x1800f541c  and     rax, rdx
0x1800f541f  cmp     cs:qword_180169748, rax
0x1800f5426  jnz     loc_1800F5B1F
0x1800f542c  lea     rcx, [rbp+760h+var_5D0]; unsigned __int16 *
0x1800f5433  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f5438  lea     rax, [rbp+760h+var_5D0]
0x1800f543f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800f5443  inc     rbx
0x1800f5446  cmp     [rax+rbx*2], r14w
0x1800f544b  jnz     short loc_1800F5443
0x1800f544d  lea     rax, [rbp+760h+var_5D0]
0x1800f5454  jmp     loc_1800F52A8
0x1800f5459  mov     rcx, [rdi+0F0h]
0x1800f5460  lea     rdx, [rdi+0E8h]
0x1800f5467  mov     rax, [rcx]
0x1800f546a  mov     rax, [rax+170h]
0x1800f5471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5476  mov     [rbp+760h+var_7E0], eax
0x1800f5479  test    eax, eax
0x1800f547b  jns     short loc_1800F54EE
0x1800f547d  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800f5484  mov     [rsp+860h+var_7E8], r14d
0x1800f5489  mov     [rsp+860h+var_7F0], eax
0x1800f548d  jz      loc_1800F5B1F
0x1800f5493  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f549d  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f54a4  jz      loc_1800F5B1F
0x1800f54aa  mov     rax, cs:qword_180169748
0x1800f54b1  and     rax, rdx
0x1800f54b4  cmp     cs:qword_180169748, rax
0x1800f54bb  jnz     loc_1800F5B1F
0x1800f54c1  lea     rcx, [rbp+760h+var_550]; unsigned __int16 *
0x1800f54c8  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f54cd  lea     rax, [rbp+760h+var_550]
0x1800f54d4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800f54d8  inc     rbx
0x1800f54db  cmp     [rax+rbx*2], r14w
0x1800f54e0  jnz     short loc_1800F54D8
0x1800f54e2  lea     rax, [rbp+760h+var_550]
0x1800f54e9  jmp     loc_1800F52A8
0x1800f54ee  mov     rcx, [rdi+0F0h]
0x1800f54f5  lea     rdx, [rdi+0C8h]
0x1800f54fc  mov     rax, [rcx]
0x1800f54ff  mov     rax, [rax+130h]
0x1800f5506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f550b  mov     [rbp+760h+var_7E0], eax
0x1800f550e  test    eax, eax
0x1800f5510  jns     short loc_1800F5583
0x1800f5512  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800f5519  mov     [rsp+860h+var_7E8], r14d
0x1800f551e  mov     [rsp+860h+var_7F0], eax
0x1800f5522  jz      loc_1800F5B1F
0x1800f5528  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f5532  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f5539  jz      loc_1800F5B1F
0x1800f553f  mov     rax, cs:qword_180169748
0x1800f5546  and     rax, rdx
0x1800f5549  cmp     cs:qword_180169748, rax
0x1800f5550  jnz     loc_1800F5B1F
0x1800f5556  lea     rcx, [rbp+760h+var_4D0]; unsigned __int16 *
0x1800f555d  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f5562  lea     rax, [rbp+760h+var_4D0]
0x1800f5569  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800f556d  inc     rbx
0x1800f5570  cmp     [rax+rbx*2], r14w
0x1800f5575  jnz     short loc_1800F556D
0x1800f5577  lea     rax, [rbp+760h+var_4D0]
0x1800f557e  jmp     loc_1800F52A8
0x1800f5583  mov     rcx, [rdi+0F0h]
0x1800f558a  lea     rdx, [rdi+0D0h]
0x1800f5591  mov     rax, [rcx]
0x1800f5594  mov     rax, [rax+140h]
0x1800f559b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f55a0  mov     [rbp+760h+var_7E0], eax
0x1800f55a3  test    eax, eax
0x1800f55a5  jns     short loc_1800F5618
0x1800f55a7  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800f55ae  mov     [rsp+860h+var_7E8], r14d
0x1800f55b3  mov     [rsp+860h+var_7F0], eax
0x1800f55b7  jz      loc_1800F5B1F
0x1800f55bd  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f55c7  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f55ce  jz      loc_1800F5B1F
0x1800f55d4  mov     rax, cs:qword_180169748
0x1800f55db  and     rax, rdx
0x1800f55de  cmp     cs:qword_180169748, rax
0x1800f55e5  jnz     loc_1800F5B1F
0x1800f55eb  lea     rcx, [rbp+760h+var_450]; unsigned __int16 *
0x1800f55f2  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f55f7  lea     rax, [rbp+760h+var_450]
0x1800f55fe  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800f5602  inc     rbx
0x1800f5605  cmp     [rax+rbx*2], r14w
0x1800f560a  jnz     short loc_1800F5602
0x1800f560c  lea     rax, [rbp+760h+var_450]
0x1800f5613  jmp     loc_1800F52A8
0x1800f5618  mov     rcx, [rdi+0F0h]
0x1800f561f  lea     rdx, [rdi+0D8h]
0x1800f5626  mov     rax, [rcx]
0x1800f5629  mov     rax, [rax+150h]
0x1800f5630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5635  mov     [rbp+760h+var_7E0], eax
  ... truncated ...
```
