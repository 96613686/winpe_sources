# sub_1800AA7FC

- ea: `0x1800aa7fc`
- end: `0x1800aad6a`
- name: `sub_1800AA7FC`
- size: `1390`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800aa270`

## callees

- `0x180006960`
- `0x18000ac80`
- `0x18000c470`
- `0x18000e400`
- `0x18002d790`
- `0x180037a98`
- `0x1800a9030`
- `0x1800aa7fc`
- `0x1800b4ad8`
- `0x1800fcf10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aacf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aacf9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800aace5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800aace5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800aad31`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800aad31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aad21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aad21`
- `MFPlat!MFPutWorkItemEx2` at `0x1800aacc6`
- `MFPlat!MFPutWorkItemEx2` at `0x1800aacc6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aa857`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aa929`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aa9d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aaa97`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aab3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aabe7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aa857`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aa929`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aa9d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aaa97`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aab3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aabe7`

## string_xrefs

- `0x1800aa811`: `CPluginForByteStreamMediaSource::OnSourceOpened`

## pseudocode

```c
__int64 __fastcall sub_1800AA7FC(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 *v5; // rcx
  int v6; // ebx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  IMFAsyncResult *v14; // r14
  __int64 *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rdx
  DWORD v19; // edi
  __int64 *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 *v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rax
  struct IMFAsyncResultVtbl *lpVtbl; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  bool v34; // sf
  int v36; // [rsp+70h] [rbp+40h] BYREF
  int v37; // [rsp+78h] [rbp+48h] BYREF
  __int64 v38; // [rsp+80h] [rbp+50h] BYREF
  IMFAsyncResult *pResult; // [rsp+88h] [rbp+58h] BYREF

  sub_180006960(&v36, "CPluginForByteStreamMediaSource::OnSourceOpened", 260);
  pResult = 0;
  v38 = 0;
  if ( !a2 )
  {
    v5 = (__int64 *)qword_18012EC10;
    v6 = -2147467261;
    if ( !qword_18012EC10 )
    {
      v7 = MFGetCallStackTracingWeakReference(0, v4);
      qword_18012EC10 = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v5 = (__int64 *)qword_18012EC10;
      }
      else
      {
        v5 = &qword_18012E0B0;
        qword_18012EC10 = (__int64)&qword_18012E0B0;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v8 = sub_18000C470(v5, v4);
      if ( *(_DWORD *)(v8 + 1996) != -2147467261 )
        sub_18000E400(v8, "CPluginForByteStreamMediaSource::OnSourceOpened", 271, 2147500035LL);
    }
    if ( (unsigned __int8)sub_1800A9030(v5, v4) )
    {
      v9 = 44;
LABEL_12:
      sub_180037A98(*((_QWORD *)RequestContext + 2), v9, qword_180110BC0, a1, v6);
      goto LABEL_84;
    }
    goto LABEL_84;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, IMFAsyncResult **))(*(_QWORD *)a2 + 24LL))(a2, &pResult);
  if ( v6 >= 0 )
  {
    v14 = pResult;
    if ( !pResult )
    {
      v15 = (__int64 *)qword_18012EC10;
      v6 = -2147024809;
      if ( !qword_18012EC10 )
      {
        v16 = MFGetCallStackTracingWeakReference(0, v10);
        qword_18012EC10 = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (__int64 *)qword_18012EC10;
        }
        else
        {
          v15 = &qword_18012E0B0;
          qword_18012EC10 = (__int64)&qword_18012E0B0;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v17 = sub_18000C470(v15, v10);
        if ( *(_DWORD *)(v17 + 1996) != -2147024809 )
          sub_18000E400(v17, "CPluginForByteStreamMediaSource::OnSourceOpened", 278, 2147942487LL);
      }
      if ( (unsigned __int8)sub_1800A9030(v15, v10) )
        sub_180037A98(*((_QWORD *)RequestContext + 2), 46, qword_180110BC0, a1, -2147024809);
      goto LABEL_84;
    }
    v6 = (*(__int64 (__fastcall **)(struct IMFAsyncResultVtbl *, __int64 *, __int64 *))pResult[15].lpVtbl->QueryInterface)(
           pResult[15].lpVtbl,
           &qword_18010F640,
           &v38);
    v19 = 1;
    if ( v6 >= 0 )
    {
      if ( v38 )
      {
        v6 = sub_1800B4AD8(v38, a2);
        if ( v6 < 0 )
        {
          v28 = (__int64 *)qword_18012EC10;
          if ( !qword_18012EC10 )
          {
            v29 = MFGetCallStackTracingWeakReference(0, v27);
            qword_18012EC10 = v29;
            if ( v29 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
            {
              v28 = (__int64 *)qword_18012EC10;
            }
            else
            {
              v28 = &qword_18012E0B0;
              qword_18012EC10 = (__int64)&qword_18012E0B0;
            }
          }
          if ( *((_BYTE *)v28 + 8) )
          {
            v30 = sub_18000C470(v28, v27);
            if ( *(_DWORD *)(v30 + 1996) != v6 )
              sub_18000E400(v30, "CPluginForByteStreamMediaSource::OnSourceOpened", 289, (unsigned int)v6);
          }
          if ( (unsigned __int8)sub_1800A9030(v28, v27) )
          {
            v23 = 49;
            goto LABEL_69;
          }
        }
      }
      else
      {
        v24 = (__int64 *)qword_18012EC10;
        v6 = -2147024809;
        if ( !qword_18012EC10 )
        {
          v25 = MFGetCallStackTracingWeakReference(0, v18);
          qword_18012EC10 = v25;
          if ( v25 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
          {
            v24 = (__int64 *)qword_18012EC10;
          }
          else
          {
            v24 = &qword_18012E0B0;
            qword_18012EC10 = (__int64)&qword_18012E0B0;
          }
        }
        if ( *((_BYTE *)v24 + 8) )
        {
          v26 = sub_18000C470(v24, v18);
          if ( *(_DWORD *)(v26 + 1996) != -2147024809 )
            sub_18000E400(v26, "CPluginForByteStreamMediaSource::OnSourceOpened", 287, 2147942487LL);
        }
        if ( (unsigned __int8)sub_1800A9030(v24, v18) )
          sub_180037A98(*((_QWORD *)RequestContext + 2), 48, qword_180110BC0, a1, -2147024809);
      }
    }
    else
    {
      v20 = (__int64 *)qword_18012EC10;
      if ( !qword_18012EC10 )
      {
        v21 = MFGetCallStackTracingWeakReference(0, v18);
        qword_18012EC10 = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (__int64 *)qword_18012EC10;
        }
        else
        {
          v20 = &qword_18012E0B0;
          qword_18012EC10 = (__int64)&qword_18012E0B0;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = sub_18000C470(v20, v18);
        if ( *(_DWORD *)(v22 + 1996) != v6 )
          sub_18000E400(v22, "CPluginForByteStreamMediaSource::OnSourceOpened", 284, (unsigned int)v6);
      }
      if ( (unsigned __int8)sub_1800A9030(v20, v18) )
      {
        v23 = 47;
LABEL_69:
        sub_180037A98(*((_QWORD *)RequestContext + 2), v23, qword_180110BC0, a1, v6);
      }
    }
    lpVtbl = v14[5].lpVtbl;
    LODWORD(v14[6].lpVtbl) = v6;
    if ( lpVtbl )
    {
      v37 = 0;
      v36 = 0;
      if ( (*((int (__fastcall **)(struct IMFAsyncResultVtbl *, int *, int *))lpVtbl->QueryInterface + 3))(
             lpVtbl,
             &v37,
             &v36) >= 0 )
        v19 = v36;
      else
        v36 = 1;
      MFPutWorkItemEx2(v19, 0, v14);
      goto LABEL_84;
    }
    if ( !v14[7].lpVtbl )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      if ( EventW )
      {
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)&v14[7], (signed __int64)EventW, 0) )
          CloseHandle(EventW);
      }
      else
      {
        LastError = GetLastError();
        v34 = LastError < 0;
        if ( LastError > 0 )
          v34 = 1;
        if ( v34 )
          goto LABEL_84;
      }
    }
    SetEvent(v14[7].lpVtbl);
    goto LABEL_84;
  }
  v11 = (__int64 *)qword_18012EC10;
  if ( !qword_18012EC10 )
  {
    v12 = MFGetCallStackTracingWeakReference(0, v10);
    qword_18012EC10 = v12;
    if ( v12 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
    {
      v11 = (__int64 *)qword_18012EC10;
    }
    else
    {
      v11 = &qword_18012E0B0;
      qword_18012EC10 = (__int64)&qword_18012E0B0;
    }
  }
  if ( *((_BYTE *)v11 + 8) )
  {
    v13 = sub_18000C470(v11, v10);
    if ( *(_DWORD *)(v13 + 1996) != v6 )
      sub_18000E400(v13, "CPluginForByteStreamMediaSource::OnSourceOpened", 276, (unsigned int)v6);
  }
  if ( (unsigned __int8)sub_1800A9030(v11, v10) )
  {
    v9 = 45;
    goto LABEL_12;
  }
LABEL_84:
  sub_18002D790(&v38);
  sub_18002D790(&pResult);
  sub_18000AC80(&v36);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800aa7fc  push    rbp
0x1800aa7fe  push    rbx
0x1800aa7ff  push    rsi
0x1800aa800  push    rdi
0x1800aa801  push    r13
0x1800aa803  push    r14
0x1800aa805  push    r15
0x1800aa807  mov     rbp, rsp
0x1800aa80a  sub     rsp, 30h
0x1800aa80e  mov     rsi, rdx
0x1800aa811  lea     r13, aCpluginforbyte_5; "CPluginForByteStreamMediaSource::OnSour"...
0x1800aa818  mov     r15, rcx
0x1800aa81b  mov     rdx, r13
0x1800aa81e  mov     r8d, 104h
0x1800aa824  lea     rcx, [rbp+arg_0]
0x1800aa828  call    sub_180006960
0x1800aa82d  mov     [rbp+pResult], 0
0x1800aa835  mov     [rbp+arg_10], 0
0x1800aa83d  test    rsi, rsi
0x1800aa840  jnz     loc_1800AA8FF
0x1800aa846  mov     rcx, cs:qword_18012EC10
0x1800aa84d  mov     ebx, 80004003h
0x1800aa852  test    rcx, rcx
0x1800aa855  jnz     short loc_1800AA89F
0x1800aa857  call    cs:MFGetCallStackTracingWeakReference
0x1800aa85e  nop     dword ptr [rax+rax+00h]
0x1800aa863  mov     cs:qword_18012EC10, rax
0x1800aa86a  mov     rcx, rax
0x1800aa86d  test    rax, rax
0x1800aa870  jz      short loc_1800AA891
0x1800aa872  mov     rax, [rax]
0x1800aa875  mov     edx, 7F0h
0x1800aa87a  mov     rax, [rax+8]
0x1800aa87e  call    cs:__guard_dispatch_icall_fptr
0x1800aa884  test    eax, eax
0x1800aa886  jz      short loc_1800AA891
0x1800aa888  mov     rcx, cs:qword_18012EC10
0x1800aa88f  jmp     short loc_1800AA89F
0x1800aa891  lea     rcx, qword_18012E0B0
0x1800aa898  mov     cs:qword_18012EC10, rcx
0x1800aa89f  cmp     byte ptr [rcx+8], 0
0x1800aa8a3  jz      short loc_1800AA8C6
0x1800aa8a5  call    sub_18000C470
0x1800aa8aa  cmp     [rax+7CCh], ebx
0x1800aa8b0  jz      short loc_1800AA8C6
0x1800aa8b2  mov     r9d, ebx
0x1800aa8b5  mov     r8d, 10Fh
0x1800aa8bb  mov     rdx, r13
0x1800aa8be  mov     rcx, rax
0x1800aa8c1  call    sub_18000E400
0x1800aa8c6  call    sub_1800A9030
0x1800aa8cb  mov     edi, 1
0x1800aa8d0  cmp     al, dil
0x1800aa8d3  jb      loc_1800AAD3D
0x1800aa8d9  lea     edx, [rdi+2Bh]
0x1800aa8dc  mov     [rsp+30h+var_10], ebx
0x1800aa8e0  mov     rcx, cs:RequestContext
0x1800aa8e7  lea     r8, qword_180110BC0
0x1800aa8ee  mov     r9, r15
0x1800aa8f1  mov     rcx, [rcx+10h]
0x1800aa8f5  call    sub_180037A98
0x1800aa8fa  jmp     loc_1800AAD3D
0x1800aa8ff  mov     rax, [rsi]
0x1800aa902  lea     rdx, [rbp+pResult]
0x1800aa906  mov     rcx, rsi
0x1800aa909  mov     rax, [rax+18h]
0x1800aa90d  call    cs:__guard_dispatch_icall_fptr
0x1800aa913  mov     ebx, eax
0x1800aa915  test    eax, eax
0x1800aa917  jns     loc_1800AA9B3
0x1800aa91d  mov     rcx, cs:qword_18012EC10
0x1800aa924  test    rcx, rcx
0x1800aa927  jnz     short loc_1800AA971
0x1800aa929  call    cs:MFGetCallStackTracingWeakReference
0x1800aa930  nop     dword ptr [rax+rax+00h]
0x1800aa935  mov     cs:qword_18012EC10, rax
0x1800aa93c  mov     rcx, rax
0x1800aa93f  test    rax, rax
0x1800aa942  jz      short loc_1800AA963
0x1800aa944  mov     rax, [rax]
0x1800aa947  mov     edx, 7F0h
0x1800aa94c  mov     rax, [rax+8]
0x1800aa950  call    cs:__guard_dispatch_icall_fptr
0x1800aa956  test    eax, eax
0x1800aa958  jz      short loc_1800AA963
0x1800aa95a  mov     rcx, cs:qword_18012EC10
0x1800aa961  jmp     short loc_1800AA971
0x1800aa963  lea     rcx, qword_18012E0B0
0x1800aa96a  mov     cs:qword_18012EC10, rcx
0x1800aa971  cmp     byte ptr [rcx+8], 0
0x1800aa975  jz      short loc_1800AA998
0x1800aa977  call    sub_18000C470
0x1800aa97c  cmp     [rax+7CCh], ebx
0x1800aa982  jz      short loc_1800AA998
0x1800aa984  mov     r9d, ebx
0x1800aa987  mov     r8d, 114h
0x1800aa98d  mov     rdx, r13
0x1800aa990  mov     rcx, rax
0x1800aa993  call    sub_18000E400
0x1800aa998  call    sub_1800A9030
0x1800aa99d  mov     edi, 1
0x1800aa9a2  cmp     al, dil
0x1800aa9a5  jb      loc_1800AAD3D
0x1800aa9ab  lea     edx, [rdi+2Ch]
0x1800aa9ae  jmp     loc_1800AA8DC
0x1800aa9b3  mov     r14, [rbp+pResult]
0x1800aa9b7  test    r14, r14
0x1800aa9ba  jnz     loc_1800AAA61
0x1800aa9c0  mov     rcx, cs:qword_18012EC10
0x1800aa9c7  mov     esi, 80070057h
0x1800aa9cc  mov     ebx, esi
0x1800aa9ce  test    rcx, rcx
0x1800aa9d1  jnz     short loc_1800AAA1B
0x1800aa9d3  call    cs:MFGetCallStackTracingWeakReference
0x1800aa9da  nop     dword ptr [rax+rax+00h]
0x1800aa9df  mov     cs:qword_18012EC10, rax
0x1800aa9e6  mov     rcx, rax
0x1800aa9e9  test    rax, rax
0x1800aa9ec  jz      short loc_1800AAA0D
0x1800aa9ee  mov     rax, [rax]
0x1800aa9f1  mov     edx, 7F0h
0x1800aa9f6  mov     rax, [rax+8]
0x1800aa9fa  call    cs:__guard_dispatch_icall_fptr
0x1800aaa00  test    eax, eax
0x1800aaa02  jz      short loc_1800AAA0D
0x1800aaa04  mov     rcx, cs:qword_18012EC10
0x1800aaa0b  jmp     short loc_1800AAA1B
0x1800aaa0d  lea     rcx, qword_18012E0B0
0x1800aaa14  mov     cs:qword_18012EC10, rcx
0x1800aaa1b  cmp     byte ptr [rcx+8], 0
0x1800aaa1f  jz      short loc_1800AAA42
0x1800aaa21  call    sub_18000C470
0x1800aaa26  cmp     [rax+7CCh], esi
0x1800aaa2c  jz      short loc_1800AAA42
0x1800aaa2e  mov     r9d, esi
0x1800aaa31  mov     r8d, 116h
0x1800aaa37  mov     rdx, r13
0x1800aaa3a  mov     rcx, rax
0x1800aaa3d  call    sub_18000E400
0x1800aaa42  call    sub_1800A9030
0x1800aaa47  mov     edi, 1
0x1800aaa4c  cmp     al, dil
0x1800aaa4f  jb      loc_1800AAD3D
0x1800aaa55  lea     edx, [rdi+2Dh]
0x1800aaa58  mov     [rsp+30h+var_10], esi
0x1800aaa5c  jmp     loc_1800AA8E0
0x1800aaa61  mov     rcx, [r14+78h]
0x1800aaa65  lea     r8, [rbp+arg_10]
0x1800aaa69  lea     rdx, qword_18010F640
0x1800aaa70  mov     rax, [rcx]
0x1800aaa73  mov     rax, [rax]
0x1800aaa76  call    cs:__guard_dispatch_icall_fptr
0x1800aaa7c  mov     ebx, eax
0x1800aaa7e  mov     edi, 1
0x1800aaa83  test    eax, eax
0x1800aaa85  jns     loc_1800AAB1E
0x1800aaa8b  mov     rcx, cs:qword_18012EC10
0x1800aaa92  test    rcx, rcx
0x1800aaa95  jnz     short loc_1800AAADF
0x1800aaa97  call    cs:MFGetCallStackTracingWeakReference
0x1800aaa9e  nop     dword ptr [rax+rax+00h]
0x1800aaaa3  mov     cs:qword_18012EC10, rax
0x1800aaaaa  mov     rcx, rax
0x1800aaaad  test    rax, rax
0x1800aaab0  jz      short loc_1800AAAD1
0x1800aaab2  mov     rax, [rax]
0x1800aaab5  mov     edx, 7F0h
0x1800aaaba  mov     rax, [rax+8]
0x1800aaabe  call    cs:__guard_dispatch_icall_fptr
0x1800aaac4  test    eax, eax
0x1800aaac6  jz      short loc_1800AAAD1
0x1800aaac8  mov     rcx, cs:qword_18012EC10
0x1800aaacf  jmp     short loc_1800AAADF
0x1800aaad1  lea     rcx, qword_18012E0B0
0x1800aaad8  mov     cs:qword_18012EC10, rcx
0x1800aaadf  cmp     byte ptr [rcx+8], 0
0x1800aaae3  jz      short loc_1800AAB06
0x1800aaae5  call    sub_18000C470
0x1800aaaea  cmp     [rax+7CCh], ebx
0x1800aaaf0  jz      short loc_1800AAB06
0x1800aaaf2  mov     r9d, ebx
0x1800aaaf5  mov     r8d, 11Ch
0x1800aaafb  mov     rdx, r13
0x1800aaafe  mov     rcx, rax
0x1800aab01  call    sub_18000E400
0x1800aab06  call    sub_1800A9030
0x1800aab0b  cmp     al, dil
0x1800aab0e  jb      loc_1800AAC83
0x1800aab14  mov     edx, 2Fh ; '/'
0x1800aab19  jmp     loc_1800AAC65
0x1800aab1e  mov     rcx, [rbp+arg_10]
0x1800aab22  test    rcx, rcx
0x1800aab25  jnz     loc_1800AABC9
0x1800aab2b  mov     rcx, cs:qword_18012EC10
0x1800aab32  mov     esi, 80070057h
0x1800aab37  mov     ebx, esi
0x1800aab39  test    rcx, rcx
0x1800aab3c  jnz     short loc_1800AAB86
0x1800aab3e  call    cs:MFGetCallStackTracingWeakReference
0x1800aab45  nop     dword ptr [rax+rax+00h]
0x1800aab4a  mov     cs:qword_18012EC10, rax
0x1800aab51  mov     rcx, rax
0x1800aab54  test    rax, rax
0x1800aab57  jz      short loc_1800AAB78
0x1800aab59  mov     rax, [rax]
0x1800aab5c  mov     edx, 7F0h
0x1800aab61  mov     rax, [rax+8]
0x1800aab65  call    cs:__guard_dispatch_icall_fptr
0x1800aab6b  test    eax, eax
0x1800aab6d  jz      short loc_1800AAB78
0x1800aab6f  mov     rcx, cs:qword_18012EC10
0x1800aab76  jmp     short loc_1800AAB86
0x1800aab78  lea     rcx, qword_18012E0B0
0x1800aab7f  mov     cs:qword_18012EC10, rcx
0x1800aab86  cmp     byte ptr [rcx+8], 0
0x1800aab8a  jz      short loc_1800AABAD
0x1800aab8c  call    sub_18000C470
0x1800aab91  cmp     [rax+7CCh], esi
0x1800aab97  jz      short loc_1800AABAD
0x1800aab99  mov     r9d, esi
0x1800aab9c  mov     r8d, 11Fh
0x1800aaba2  mov     rdx, r13
0x1800aaba5  mov     rcx, rax
0x1800aaba8  call    sub_18000E400
0x1800aabad  call    sub_1800A9030
0x1800aabb2  cmp     al, dil
0x1800aabb5  jb      loc_1800AAC83
0x1800aabbb  mov     edx, 30h ; '0'
0x1800aabc0  mov     [rsp+30h+var_10], esi
0x1800aabc4  jmp     loc_1800AAC69
0x1800aabc9  mov     rdx, rsi
0x1800aabcc  call    sub_1800B4AD8
0x1800aabd1  mov     ebx, eax
0x1800aabd3  test    eax, eax
0x1800aabd5  jns     loc_1800AAC83
0x1800aabdb  mov     rcx, cs:qword_18012EC10
0x1800aabe2  test    rcx, rcx
0x1800aabe5  jnz     short loc_1800AAC2F
0x1800aabe7  call    cs:MFGetCallStackTracingWeakReference
0x1800aabee  nop     dword ptr [rax+rax+00h]
0x1800aabf3  mov     cs:qword_18012EC10, rax
0x1800aabfa  mov     rcx, rax
0x1800aabfd  test    rax, rax
0x1800aac00  jz      short loc_1800AAC21
0x1800aac02  mov     rax, [rax]
0x1800aac05  mov     edx, 7F0h
0x1800aac0a  mov     rax, [rax+8]
0x1800aac0e  call    cs:__guard_dispatch_icall_fptr
0x1800aac14  test    eax, eax
0x1800aac16  jz      short loc_1800AAC21
0x1800aac18  mov     rcx, cs:qword_18012EC10
0x1800aac1f  jmp     short loc_1800AAC2F
0x1800aac21  lea     rcx, qword_18012E0B0
0x1800aac28  mov     cs:qword_18012EC10, rcx
0x1800aac2f  cmp     byte ptr [rcx+8], 0
0x1800aac33  jz      short loc_1800AAC56
0x1800aac35  call    sub_18000C470
0x1800aac3a  cmp     [rax+7CCh], ebx
0x1800aac40  jz      short loc_1800AAC56
0x1800aac42  mov     r9d, ebx
0x1800aac45  mov     r8d, 121h
0x1800aac4b  mov     rdx, r13
0x1800aac4e  mov     rcx, rax
0x1800aac51  call    sub_18000E400
0x1800aac56  call    sub_1800A9030
0x1800aac5b  cmp     al, dil
0x1800aac5e  jb      short loc_1800AAC83
0x1800aac60  mov     edx, 31h ; '1'
0x1800aac65  mov     [rsp+30h+var_10], ebx
0x1800aac69  mov     rcx, cs:RequestContext
0x1800aac70  lea     r8, qword_180110BC0
0x1800aac77  mov     r9, r15
0x1800aac7a  mov     rcx, [rcx+10h]
0x1800aac7e  call    sub_180037A98
0x1800aac83  mov     rcx, [r14+28h]
0x1800aac87  mov     [r14+30h], ebx
0x1800aac8b  test    rcx, rcx
0x1800aac8e  jz      short loc_1800AACD4
0x1800aac90  mov     [rbp+arg_8], 0
0x1800aac97  lea     r8, [rbp+arg_0]
0x1800aac9b  mov     [rbp+arg_0], 0
0x1800aaca2  lea     rdx, [rbp+arg_8]
0x1800aaca6  mov     rax, [rcx]
0x1800aaca9  mov     rax, [rax+18h]
0x1800aacad  call    cs:__guard_dispatch_icall_fptr
0x1800aacb3  test    eax, eax
0x1800aacb5  jns     short loc_1800AACBC
0x1800aacb7  mov     [rbp+arg_0], edi
0x1800aacba  jmp     short loc_1800AACBF
0x1800aacbc  mov     edi, [rbp+arg_0]
0x1800aacbf  mov     r8, r14; pResult
0x1800aacc2  xor     edx, edx; Priority
0x1800aacc4  mov     ecx, edi; dwQueue
0x1800aacc6  call    cs:MFPutWorkItemEx2
0x1800aaccd  nop     dword ptr [rax+rax+00h]
0x1800aacd2  jmp     short loc_1800AAD3D
0x1800aacd4  cmp     qword ptr [r14+38h], 0
0x1800aacd9  jnz     short loc_1800AAD2D
0x1800aacdb  xor     r9d, r9d; lpName
0x1800aacde  xor     r8d, r8d; bInitialState
  ... truncated ...
```
