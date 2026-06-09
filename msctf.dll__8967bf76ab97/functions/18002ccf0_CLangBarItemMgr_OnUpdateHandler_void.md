# CLangBarItemMgr::OnUpdateHandler(void)

- ea: `0x18002ccf0`
- end: `0x18002d522`
- name: `?OnUpdateHandler@CLangBarItemMgr@@QEAAJXZ`
- size: `2098`
- prototype: `__int64 __fastcall(CLangBarItemMgr *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update`

## callers

- `0x18002cc80`

## callees

- `0x18000b5e4`
- `0x18000f170`
- `0x1800139a4`
- `0x18002ccf0`
- `0x18002d528`
- `0x18002d834`
- `0x18002d958`
- `0x18002da10`
- `0x18002db70`
- `0x180082e90`
- `0x180089830`
- `0x180089de0`
- `0x1800b1c40`
- `0x180106a60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d2fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d417`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d2fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d417`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d42a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d42a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002cdf8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ce1c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ce40`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ce64`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ce88`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ceab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002cece`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002cef1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002cf14`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d2bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002cdf8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ce1c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ce40`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ce64`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ce88`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ceab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002cece`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002cef1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002cf14`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d2bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d34e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d392`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d3e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d3f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d403`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d34e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d392`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d3e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d3f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d403`
- `USER32!KillTimer` at `0x18002cd31`
- `USER32!KillTimer` at `0x18002cd31`
- `USER32!NotifyWinEvent` at `0x18002d4f9`
- `USER32!NotifyWinEvent` at `0x18002d4f9`

## pseudocode

```c
__int64 __fastcall CLangBarItemMgr::OnUpdateHandler(CLangBarItemMgr *this)
{
  UINT_PTR v1; // rdx
  bool v3; // zf
  int v4; // ebx
  unsigned int v5; // r15d
  unsigned int v6; // edx
  __int64 v7; // rcx
  int v8; // eax
  int v9; // esi
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  __int64 v19; // rdx
  int v20; // r13d
  __int64 v21; // rax
  __int64 v22; // r12
  unsigned __int16 ItemType; // ax
  unsigned int v24; // esi
  unsigned int v25; // edi
  _DWORD *v26; // rax
  struct MsgBase *v27; // rbx
  DWORD CurrentThreadId; // eax
  CCtfClientPort *v29; // rax
  CCtfClientPort *v30; // rdi
  HWND v31; // rdx
  DWORD v32; // ebx
  LPVOID Value; // rax
  __int64 v34; // r9
  CLangBarMgr *v35; // rcx
  struct CCtfClientPort *Instance; // rax
  unsigned int v38; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v39[2]; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v40; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int *v42; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 **v43; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 **v44; // [rsp+78h] [rbp-88h] BYREF
  HICON *v45; // [rsp+80h] [rbp-80h] BYREF
  struct tagSIZE *v46; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL v47; // [rsp+90h] [rbp-70h] BYREF
  HLOCAL v48; // [rsp+98h] [rbp-68h] BYREF
  HLOCAL v49; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int *v50; // [rsp+A8h] [rbp-58h] BYREF
  int v51; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int **v52; // [rsp+B8h] [rbp-48h]
  __int64 v53; // [rsp+C0h] [rbp-40h]
  int v54; // [rsp+C8h] [rbp-38h]
  unsigned __int16 *v55; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v56; // [rsp+D8h] [rbp-28h]
  int v57; // [rsp+E0h] [rbp-20h]
  int v58; // [rsp+E8h] [rbp-18h]
  HLOCAL *p_hMem; // [rsp+F0h] [rbp-10h]
  __int64 v60; // [rsp+F8h] [rbp-8h]
  int v61; // [rsp+100h] [rbp+0h]
  unsigned int *v62; // [rsp+108h] [rbp+8h]
  unsigned int *v63; // [rsp+110h] [rbp+10h]
  int v64; // [rsp+118h] [rbp+18h]
  int v65; // [rsp+120h] [rbp+20h]
  HLOCAL *v66; // [rsp+128h] [rbp+28h]
  __int64 v67; // [rsp+130h] [rbp+30h]
  int v68; // [rsp+138h] [rbp+38h]
  unsigned int *v69; // [rsp+140h] [rbp+40h]
  unsigned int *v70; // [rsp+148h] [rbp+48h]
  int v71; // [rsp+150h] [rbp+50h]
  int v72; // [rsp+158h] [rbp+58h]
  HLOCAL *v73; // [rsp+160h] [rbp+60h]
  __int64 v74; // [rsp+168h] [rbp+68h]
  int v75; // [rsp+170h] [rbp+70h]
  unsigned int *v76; // [rsp+178h] [rbp+78h]
  unsigned int *v77; // [rsp+180h] [rbp+80h]
  int v78; // [rsp+188h] [rbp+88h]
  int v79; // [rsp+190h] [rbp+90h]
  HLOCAL *v80; // [rsp+198h] [rbp+98h]
  __int64 v81; // [rsp+1A0h] [rbp+A0h]
  int v82; // [rsp+1A8h] [rbp+A8h]
  unsigned int *v83; // [rsp+1B0h] [rbp+B0h]
  unsigned int *v84; // [rsp+1B8h] [rbp+B8h]
  int v85; // [rsp+1C0h] [rbp+C0h]
  int v86; // [rsp+1C8h] [rbp+C8h]
  HLOCAL *v87; // [rsp+1D0h] [rbp+D0h]
  __int64 v88; // [rsp+1D8h] [rbp+D8h]
  int v89; // [rsp+1E0h] [rbp+E0h]
  unsigned int *v90; // [rsp+1E8h] [rbp+E8h]
  unsigned int *v91; // [rsp+1F0h] [rbp+F0h]
  int v92; // [rsp+1F8h] [rbp+F8h]
  int v93; // [rsp+200h] [rbp+100h]
  HLOCAL *v94; // [rsp+208h] [rbp+108h]
  __int64 v95; // [rsp+210h] [rbp+110h]
  int v96; // [rsp+218h] [rbp+118h]
  unsigned int *v97; // [rsp+220h] [rbp+120h]
  unsigned int *v98; // [rsp+228h] [rbp+128h]
  int v99; // [rsp+230h] [rbp+130h]
  int v100; // [rsp+238h] [rbp+138h]
  HLOCAL *v101; // [rsp+240h] [rbp+140h]
  __int64 v102; // [rsp+248h] [rbp+148h]
  int v103; // [rsp+250h] [rbp+150h]
  unsigned int *v104; // [rsp+258h] [rbp+158h]
  unsigned int *v105; // [rsp+260h] [rbp+160h]
  int v106; // [rsp+268h] [rbp+168h]
  int v107; // [rsp+270h] [rbp+170h]
  HLOCAL *v108; // [rsp+278h] [rbp+178h]
  __int64 v109; // [rsp+280h] [rbp+180h]
  int v110; // [rsp+288h] [rbp+188h]
  unsigned int *v111; // [rsp+290h] [rbp+190h]
  unsigned int *v112; // [rsp+298h] [rbp+198h]
  int v113; // [rsp+2A0h] [rbp+1A0h]
  int v114; // [rsp+2A8h] [rbp+1A8h]
  HLOCAL *v115; // [rsp+2B0h] [rbp+1B0h]
  __int64 v116; // [rsp+2B8h] [rbp+1B8h]
  int v117; // [rsp+2C0h] [rbp+1C0h]
  unsigned int *v118; // [rsp+2C8h] [rbp+1C8h]
  unsigned int *v119; // [rsp+2D0h] [rbp+1D0h]
  int v120; // [rsp+2D8h] [rbp+1D8h]

  v1 = *((_QWORD *)this + 13);
  if ( !v1 )
    return 1;
  KillTimer(0, v1);
  v3 = (*((_BYTE *)this + 96) & 1) == 0;
  *((_QWORD *)this + 13) = 0;
  if ( v3 )
    return 1;
  v4 = 0;
  v5 = 0;
  if ( *((int *)this + 8) > 0 )
  {
    v6 = 0;
    while ( 1 )
    {
      v7 = *(_QWORD *)(*((_QWORD *)this + 3) + 8LL * v6);
      v4 += *(_DWORD *)(v7 + 80) != 0;
      if ( !*(_QWORD *)(v7 + 32) )
        break;
      if ( *(_DWORD *)(v7 + 60) )
      {
        if ( !*(_DWORD *)(v7 + 64) )
          break;
      }
      else if ( (*(_BYTE *)(v7 + 68) & 1) != 0 )
      {
        break;
      }
      v8 = 1;
LABEL_11:
      v5 += v8;
      if ( (signed int)++v6 >= *((_DWORD *)this + 8) )
        goto LABEL_12;
    }
    v8 = 0;
    goto LABEL_11;
  }
LABEL_12:
  v9 = 1;
  if ( !v4 )
  {
    if ( v5 )
      return (unsigned int)v9;
    goto LABEL_82;
  }
  if ( !v5 )
  {
LABEL_82:
    CLangBarItemMgr::Disconnect(this);
    if ( v4 )
      goto LABEL_83;
    return (unsigned int)v9;
  }
  if ( !*((_QWORD *)this + 14) )
  {
    Instance = CCtfClientPort::CreateInstance();
    *((_QWORD *)this + 14) = Instance;
    if ( !Instance )
      return 2147500037LL;
  }
  hMem = 0;
  v10 = 104 * v5;
  v42 = 0;
  v43 = 0;
  if ( !is_mul_ok(v5, 0x68u) )
    v10 = -1;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  hMem = LocalAlloc(0x40u, v10);
  if ( !hMem )
    goto LABEL_88;
  v11 = 4 * v5;
  if ( !is_mul_ok(v5, 4u) )
    v11 = -1;
  v42 = (unsigned int *)LocalAlloc(0x40u, v11);
  if ( !v42 )
    goto LABEL_88;
  v12 = 8 * v5;
  if ( !is_mul_ok(v5, 8u) )
    v12 = -1;
  v43 = (unsigned __int16 **)LocalAlloc(0x40u, v12);
  if ( !v43 )
    goto LABEL_88;
  v13 = 8 * v5;
  if ( !is_mul_ok(v5, 8u) )
    v13 = -1;
  v44 = (unsigned __int16 **)LocalAlloc(0x40u, v13);
  if ( !v44 )
    goto LABEL_88;
  v14 = 8 * v5;
  if ( !is_mul_ok(v5, 8u) )
    v14 = -1;
  v45 = (HICON *)LocalAlloc(0x40u, v14);
  if ( !v45 )
    goto LABEL_88;
  v15 = 8 * v5;
  if ( !is_mul_ok(v5, 8u) )
    v15 = -1;
  v46 = (struct tagSIZE *)LocalAlloc(0x40u, v15);
  if ( !v46 )
    goto LABEL_88;
  v16 = 8 * v5;
  if ( !is_mul_ok(v5, 8u) )
    v16 = -1;
  v47 = LocalAlloc(0x40u, v16);
  if ( !v47 )
    goto LABEL_88;
  v17 = 8 * v5;
  if ( !is_mul_ok(v5, 8u) )
    v17 = -1;
  v48 = LocalAlloc(0x40u, v17);
  if ( !v48 )
    goto LABEL_88;
  v18 = 4 * v5;
  if ( !is_mul_ok(v5, 4u) )
    v18 = -1;
  v49 = LocalAlloc(0x40u, v18);
  if ( !v49 )
  {
LABEL_88:
    v9 = -2147024882;
    goto LABEL_64;
  }
  v19 = 0;
  v20 = 0;
  v38 = 0;
  while ( v20 < *((_DWORD *)this + 8) )
  {
    v21 = *((_QWORD *)this + 3);
    v39[0] = 0;
    v22 = *(_QWORD *)(v21 + 8LL * v20);
    if ( *(_QWORD *)(v22 + 32) )
    {
      if ( *(_DWORD *)(v22 + 60) )
      {
        if ( *(_DWORD *)(v22 + 64) )
        {
LABEL_47:
          if ( (unsigned int)CLBarItemProxy::GetUpdates(
                               (CLBarItemProxy *)v22,
                               (struct TF_LANGBARITEMINFO *)hMem + v19,
                               &v42[v19],
                               &v43[v19],
                               &v44[v19],
                               &v45[v19],
                               &v46[v19],
                               (HBITMAP *)v47 + v19,
                               (HBITMAP *)v48 + v19,
                               v39) )
          {
            v19 = v38;
          }
          else
          {
            ItemType = CLBarItemProxy::GetItemType((CLBarItemProxy *)v22);
            *((_DWORD *)v49 + v38) = v39[0] | (ItemType << 16);
            v19 = ++v38;
          }
        }
      }
      else if ( (*(_BYTE *)(v22 + 68) & 1) == 0 )
      {
        goto LABEL_47;
      }
    }
    ++v20;
    if ( (unsigned int)v19 >= v5 )
      break;
  }
  if ( (_DWORD)v19 )
  {
    *(_DWORD *)v39 = 1;
    v51 = 5;
    v50 = &v38;
    v72 = 1045;
    v52 = &v50;
    v79 = 1045;
    v55 = v39;
    v53 = 0;
    v56 = v39;
    p_hMem = &hMem;
    v62 = &v38;
    v63 = &v38;
    v66 = (HLOCAL *)&v42;
    v69 = &v38;
    v70 = &v38;
    v73 = (HLOCAL *)&v43;
    v76 = &v38;
    v77 = &v38;
    v80 = (HLOCAL *)&v44;
    v83 = &v38;
    v84 = &v38;
    v87 = (HLOCAL *)&v45;
    v90 = &v38;
    v91 = &v38;
    v94 = (HLOCAL *)&v46;
    v97 = &v38;
    v98 = &v38;
    v101 = &v47;
    v54 = 4;
    v57 = 0;
    v58 = 5;
    v60 = 0;
    v61 = 104;
    v64 = 0;
    v65 = 5;
    v67 = 0;
    v68 = 4;
    v71 = 0;
    v74 = 0;
    v75 = 8;
    v78 = 0;
    v81 = 0;
    v82 = 8;
    v85 = 0;
    v86 = 8213;
    v88 = 0;
    v89 = 8;
    v92 = 0;
    v93 = 5;
    v95 = 0;
    v96 = 8;
    v99 = 0;
    v100 = 2069;
    v102 = 0;
    v103 = 8;
    v104 = &v38;
    v107 = 2069;
    v105 = &v38;
    v110 = 8;
    v108 = &v48;
    v114 = 5;
    v111 = &v38;
    v106 = 0;
    v112 = &v38;
    v109 = 0;
    v115 = &v49;
    v118 = &v38;
    v119 = &v38;
    v113 = 0;
    v116 = 0;
    v117 = 4;
    v120 = 0;
    v40 = 0;
    if ( (int)MsgBase::CalcParamMarshalingSize(1, 0xAu, (struct tagCPROXY_PARAM *)&v51, &v40) >= 0
      && (v24 = v40, v25 = v40 + 72, v40 + 72 >= 0x48)
      && (v26 = LocalAlloc(0x40u, v25), (v27 = (struct MsgBase *)v26) != 0) )
    {
      if ( v25 > 0x200 )
      {
        v26[10] |= 0x4000000u;
        LOWORD(v25) = 72;
      }
      *((_WORD *)v26 + 1) = v25;
      *(_WORD *)v26 = v25 - 40;
      v26[14] = 10;
      v26[15] = v24;
      *((_QWORD *)v26 + 8) = v26 + 18;
      v26[10] |= 0x91000028;
      CurrentThreadId = GetCurrentThreadId();
      *((_DWORD *)v27 + 12) = 0;
      *((_DWORD *)v27 + 11) = CurrentThreadId;
      v9 = MsgBase::Marshal(v27, 0xAu, (struct tagCPROXY_PARAM *)&v51);
      if ( v9 >= 0 )
      {
        v29 = CCtfClientPort::CreateInstance();
        v30 = v29;
        if ( v29 )
        {
          v9 = CCtfClientPort::Send(v29, v27, 0);
          CCtfClientPort::Release(v30);
        }
        else
        {
          v9 = -2147467259;
        }
      }
      LocalFree(v27);
    }
    else
    {
      v9 = -2147024882;
    }
    CleanUpAutoParams(0xAu, (struct tagCPROXY_PARAM *)&v51);
    if ( v9 >= 0 )
    {
      tagSYSTHREAD::ModifyFlags(*((tagSYSTHREAD **)this + 11), 2u, 0);
      v31 = *(HWND *)(*((_QWORD *)this + 11) + 136LL);
      if ( v31 )
        NotifyWinEvent(0x7FFFFF30u, v31, 61441, 1);
    }
  }
LABEL_64:
  if ( hMem )
    LocalFree(hMem);
  if ( v42 )
    cicMemFree(v42);
  if ( v43 )
    cicMemFree(v43);
  if ( v44 )
    cicMemFree(v44);
  if ( v45 )
    cicMemFree(v45);
  if ( v46 )
    cicMemFree(v46);
  if ( v47 )
    LocalFree(v47);
  if ( v48 )
    LocalFree(v48);
  if ( v49 )
    LocalFree(v49);
LABEL_83:
  v32 = GetCurrentThreadId();
  if ( g_dwTLSIndex != -1 )
  {
    Value = TlsGetValue(g_dwTLSIndex);
    if ( Value )
    {
      v35 = (CLangBarMgr *)*((_QWORD *)Value + 5);
      if ( v35 )
        CLangBarMgr::OnLanguageBarEvent(v35, 4, v32, v34);
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002ccf0  push    rbp
0x18002ccf2  push    rbx
0x18002ccf3  push    rsi
0x18002ccf4  push    rdi
0x18002ccf5  push    r12
0x18002ccf7  push    r13
0x18002ccf9  push    r14
0x18002ccfb  push    r15
0x18002ccfd  lea     rbp, [rsp-1F8h]
0x18002cd05  sub     rsp, 2F8h
0x18002cd0c  mov     rax, cs:__security_cookie
0x18002cd13  xor     rax, rsp
0x18002cd16  mov     [rbp+230h+var_50], rax
0x18002cd1d  mov     rdx, [rcx+68h]; uIDEvent
0x18002cd21  xor     edi, edi
0x18002cd23  mov     r14, rcx
0x18002cd26  test    rdx, rdx
0x18002cd29  jz      loc_18002D490
0x18002cd2f  xor     ecx, ecx; hWnd
0x18002cd31  call    cs:__imp_KillTimer
0x18002cd37  test    byte ptr [r14+60h], 1
0x18002cd3c  mov     [r14+68h], rdi
0x18002cd40  jz      loc_18002D490
0x18002cd46  mov     ebx, edi
0x18002cd48  mov     r15d, edi
0x18002cd4b  cmp     [r14+20h], edi
0x18002cd4f  jle     short loc_18002CD91
0x18002cd51  mov     r8, [r14+18h]
0x18002cd55  mov     edx, edi
0x18002cd57  mov     eax, edx
0x18002cd59  mov     rcx, [r8+rax*8]
0x18002cd5d  mov     eax, edi
0x18002cd5f  cmp     [rcx+50h], edi
0x18002cd62  setnz   al
0x18002cd65  add     ebx, eax
0x18002cd67  cmp     [rcx+20h], rdi
0x18002cd6b  jz      short loc_18002CD84
0x18002cd6d  cmp     [rcx+3Ch], edi
0x18002cd70  jnz     short loc_18002CD7F
0x18002cd72  test    byte ptr [rcx+44h], 1
0x18002cd76  jnz     short loc_18002CD84
0x18002cd78  mov     eax, 1
0x18002cd7d  jmp     short loc_18002CD86
0x18002cd7f  cmp     [rcx+40h], edi
0x18002cd82  jnz     short loc_18002CD78
0x18002cd84  mov     eax, edi
0x18002cd86  add     r15d, eax
0x18002cd89  inc     edx
0x18002cd8b  cmp     edx, [r14+20h]
0x18002cd8f  jl      short loc_18002CD57
0x18002cd91  mov     esi, 1
0x18002cd96  test    ebx, ebx
0x18002cd98  jz      loc_18002D4A1
0x18002cd9e  test    r15d, r15d
0x18002cda1  jz      loc_18002D40B
0x18002cda7  cmp     [r14+70h], rdi
0x18002cdab  jz      loc_18002D4AB
0x18002cdb1  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18002cdb8  mov     ebx, r15d
0x18002cdbb  mov     eax, 68h ; 'h'
0x18002cdc0  mov     [rsp+330h+hMem], rdi
0x18002cdc5  mul     rbx
0x18002cdc8  lea     r12d, [r13+41h]
0x18002cdcc  mov     [rsp+330h+var_2C8], rdi
0x18002cdd1  mov     ecx, r12d; uFlags
0x18002cdd4  mov     [rsp+330h+var_2C0], rdi
0x18002cdd9  cmovb   rax, r13
0x18002cddd  mov     [rsp+330h+var_2B8], rdi
0x18002cde2  mov     edx, eax; uBytes
0x18002cde4  mov     [rbp+230h+var_2B0], rdi
0x18002cde8  mov     [rbp+230h+var_2A8], rdi
0x18002cdec  mov     [rbp+230h+var_2A0], rdi
0x18002cdf0  mov     [rbp+230h+var_298], rdi
0x18002cdf4  mov     [rbp+230h+var_290], rdi
0x18002cdf8  call    cs:__imp_LocalAlloc
0x18002cdfe  mov     [rsp+330h+hMem], rax
0x18002ce03  test    rax, rax
0x18002ce06  jz      loc_18002D463
0x18002ce0c  lea     eax, [r13+5]
0x18002ce10  mov     ecx, r12d; uFlags
0x18002ce13  mul     rbx
0x18002ce16  cmovb   rax, r13
0x18002ce1a  mov     edx, eax; uBytes
0x18002ce1c  call    cs:__imp_LocalAlloc
0x18002ce22  mov     [rsp+330h+var_2C8], rax
0x18002ce27  test    rax, rax
0x18002ce2a  jz      loc_18002D463
0x18002ce30  lea     eax, [r13+9]
0x18002ce34  mov     ecx, r12d; uFlags
0x18002ce37  mul     rbx
0x18002ce3a  cmovb   rax, r13
0x18002ce3e  mov     edx, eax; uBytes
0x18002ce40  call    cs:__imp_LocalAlloc
0x18002ce46  mov     [rsp+330h+var_2C0], rax
0x18002ce4b  test    rax, rax
0x18002ce4e  jz      loc_18002D463
0x18002ce54  lea     eax, [r13+9]
0x18002ce58  mov     ecx, r12d; uFlags
0x18002ce5b  mul     rbx
0x18002ce5e  cmovb   rax, r13
0x18002ce62  mov     edx, eax; uBytes
0x18002ce64  call    cs:__imp_LocalAlloc
0x18002ce6a  mov     [rsp+330h+var_2B8], rax
0x18002ce6f  test    rax, rax
0x18002ce72  jz      loc_18002D463
0x18002ce78  lea     eax, [r13+9]
0x18002ce7c  mov     ecx, r12d; uFlags
0x18002ce7f  mul     rbx
0x18002ce82  cmovb   rax, r13
0x18002ce86  mov     edx, eax; uBytes
0x18002ce88  call    cs:__imp_LocalAlloc
0x18002ce8e  mov     [rbp+230h+var_2B0], rax
0x18002ce92  test    rax, rax
0x18002ce95  jz      loc_18002D463
0x18002ce9b  lea     eax, [r13+9]
0x18002ce9f  mov     ecx, r12d; uFlags
0x18002cea2  mul     rbx
0x18002cea5  cmovb   rax, r13
0x18002cea9  mov     edx, eax; uBytes
0x18002ceab  call    cs:__imp_LocalAlloc
0x18002ceb1  mov     [rbp+230h+var_2A8], rax
0x18002ceb5  test    rax, rax
0x18002ceb8  jz      loc_18002D463
0x18002cebe  lea     eax, [r13+9]
0x18002cec2  mov     ecx, r12d; uFlags
0x18002cec5  mul     rbx
0x18002cec8  cmovb   rax, r13
0x18002cecc  mov     edx, eax; uBytes
0x18002cece  call    cs:__imp_LocalAlloc
0x18002ced4  mov     [rbp+230h+var_2A0], rax
0x18002ced8  test    rax, rax
0x18002cedb  jz      loc_18002D463
0x18002cee1  lea     eax, [r13+9]
0x18002cee5  mov     ecx, r12d; uFlags
0x18002cee8  mul     rbx
0x18002ceeb  cmovb   rax, r13
0x18002ceef  mov     edx, eax; uBytes
0x18002cef1  call    cs:__imp_LocalAlloc
0x18002cef7  mov     [rbp+230h+var_298], rax
0x18002cefb  test    rax, rax
0x18002cefe  jz      loc_18002D463
0x18002cf04  lea     eax, [r13+5]
0x18002cf08  mov     ecx, r12d; uFlags
0x18002cf0b  mul     rbx
0x18002cf0e  cmovb   rax, r13
0x18002cf12  mov     edx, eax; uBytes
0x18002cf14  call    cs:__imp_LocalAlloc
0x18002cf1a  mov     [rbp+230h+var_290], rax
0x18002cf1e  test    rax, rax
0x18002cf21  jz      loc_18002D463
0x18002cf27  mov     edx, edi
0x18002cf29  mov     r13d, edi
0x18002cf2c  mov     [rsp+330h+var_2E0], edx
0x18002cf30  test    r15d, r15d
0x18002cf33  jz      loc_18002D388
0x18002cf39  cmp     r13d, [r14+20h]
0x18002cf3d  jge     loc_18002D030
0x18002cf43  mov     rax, [r14+18h]
0x18002cf47  movsxd  rcx, r13d
0x18002cf4a  mov     [rsp+330h+var_2DC], di
0x18002cf4f  mov     r12, [rax+rcx*8]
0x18002cf53  cmp     [r12+20h], rdi
0x18002cf58  jz      loc_18002D024
0x18002cf5e  cmp     [r12+3Ch], edi
0x18002cf63  jnz     loc_18002D019
0x18002cf69  test    [r12+44h], sil
0x18002cf6e  jnz     loc_18002D024
0x18002cf74  mov     rax, [rbp+230h+var_298]
0x18002cf78  lea     rdi, [rax+rdx*8]
0x18002cf7c  mov     rax, [rbp+230h+var_2A0]
0x18002cf80  lea     rbx, [rax+rdx*8]
0x18002cf84  mov     rax, [rbp+230h+var_2A8]
0x18002cf88  lea     r11, [rax+rdx*8]
0x18002cf8c  mov     rax, [rbp+230h+var_2B0]
0x18002cf90  lea     r10, [rax+rdx*8]
0x18002cf94  mov     rax, [rsp+330h+var_2B8]
0x18002cf99  lea     rcx, [rax+rdx*8]
0x18002cf9d  mov     rax, [rsp+330h+var_2C0]
0x18002cfa2  lea     r9, [rax+rdx*8]; unsigned __int16 **
0x18002cfa6  mov     rax, [rsp+330h+var_2C8]
0x18002cfab  lea     r8, [rax+rdx*4]; unsigned int *
0x18002cfaf  imul    rdx, 68h ; 'h'
0x18002cfb3  lea     rax, [rsp+330h+var_2DC]
0x18002cfb8  add     rdx, [rsp+330h+hMem]; struct TF_LANGBARITEMINFO *
0x18002cfbd  mov     [rsp+330h+var_2E8], rax; unsigned __int16 *
0x18002cfc2  mov     [rsp+330h+var_2F0], rdi; HBITMAP *
0x18002cfc7  mov     [rsp+330h+var_2F8], rbx; HBITMAP *
0x18002cfcc  mov     [rsp+330h+var_300], r11; struct tagSIZE *
0x18002cfd1  mov     [rsp+330h+var_308], r10; HICON *
0x18002cfd6  mov     [rsp+330h+var_310], rcx; unsigned __int16 **
0x18002cfdb  mov     rcx, r12; this
0x18002cfde  call    ?GetUpdates@CLBarItemProxy@@QEAAJPEAUTF_LANGBARITEMINFO@@PEAKPEAPEAG2PEAPEAUHICON__@@PEAUtagSIZE@@PEAPEAUHBITMAP__@@5PEAG@Z; CLBarItemProxy::GetUpdates(TF_LANGBARITEMINFO *,ulong *,ushort * *,ushort * *,HICON__ * *,tagSIZE *,HBITMAP__ * *,HBITMAP__ * *,ushort *)
0x18002cfe3  xor     edi, edi
0x18002cfe5  test    eax, eax
0x18002cfe7  jnz     loc_18002D4C7
0x18002cfed  mov     rcx, r12; this
0x18002cff0  call    ?GetItemType@CLBarItemProxy@@QEAAKXZ; CLBarItemProxy::GetItemType(void)
0x18002cff5  mov     ecx, [rsp+330h+var_2E0]
0x18002cff9  movzx   edx, ax
0x18002cffc  movzx   eax, [rsp+330h+var_2DC]
0x18002d001  shl     edx, 10h
0x18002d004  or      edx, eax
0x18002d006  mov     rax, [rbp+230h+var_290]
0x18002d00a  mov     [rax+rcx*4], edx
0x18002d00d  mov     edx, [rsp+330h+var_2E0]
0x18002d011  inc     edx
0x18002d013  mov     [rsp+330h+var_2E0], edx
0x18002d017  jmp     short loc_18002D024
0x18002d019  cmp     [r12+40h], edi
0x18002d01e  jnz     loc_18002CF74
0x18002d024  inc     r13d
0x18002d027  cmp     edx, r15d
0x18002d02a  jb      loc_18002CF39
0x18002d030  test    edx, edx
0x18002d032  jz      loc_18002D388
0x18002d038  mov     edx, 5
0x18002d03d  mov     dword ptr [rsp+330h+var_2DC], esi
0x18002d041  lea     rax, [rsp+330h+var_2E0]
0x18002d046  mov     [rbp+230h+var_280], edx
0x18002d049  mov     [rbp+230h+var_288], rax
0x18002d04d  mov     ecx, 415h
0x18002d052  lea     rax, [rbp+230h+var_288]
0x18002d056  mov     [rbp+230h+var_1D8], ecx
0x18002d059  mov     [rbp+230h+var_278], rax
0x18002d05d  lea     r8d, [rdx+3]
0x18002d061  lea     rax, [rsp+330h+var_2DC]
0x18002d066  mov     [rbp+230h+var_1A0], ecx
0x18002d06c  mov     [rbp+230h+var_260], rax
0x18002d070  mov     ecx, 815h
0x18002d075  lea     rax, [rsp+330h+var_2DC]
0x18002d07a  mov     [rbp+230h+var_270], rdi
0x18002d07e  mov     [rbp+230h+var_258], rax
0x18002d082  lea     rax, [rsp+330h+hMem]
0x18002d087  mov     [rbp+230h+var_240], rax
0x18002d08b  lea     rax, [rsp+330h+var_2E0]
0x18002d090  mov     [rbp+230h+var_228], rax
0x18002d094  lea     rax, [rsp+330h+var_2E0]
0x18002d099  mov     [rbp+230h+var_220], rax
0x18002d09d  lea     rax, [rsp+330h+var_2C8]
0x18002d0a2  mov     [rbp+230h+var_208], rax
0x18002d0a6  lea     rax, [rsp+330h+var_2E0]
0x18002d0ab  mov     [rbp+230h+var_1F0], rax
0x18002d0af  lea     rax, [rsp+330h+var_2E0]
0x18002d0b4  mov     [rbp+230h+var_1E8], rax
0x18002d0b8  lea     rax, [rsp+330h+var_2C0]
0x18002d0bd  mov     [rbp+230h+var_1D0], rax
0x18002d0c1  lea     rax, [rsp+330h+var_2E0]
0x18002d0c6  mov     [rbp+230h+var_1B8], rax
0x18002d0ca  lea     rax, [rsp+330h+var_2E0]
0x18002d0cf  mov     [rbp+230h+var_1B0], rax
0x18002d0d6  lea     rax, [rsp+330h+var_2B8]
0x18002d0db  mov     [rbp+230h+var_198], rax
0x18002d0e2  lea     rax, [rsp+330h+var_2E0]
0x18002d0e7  mov     [rbp+230h+var_180], rax
0x18002d0ee  lea     rax, [rsp+330h+var_2E0]
0x18002d0f3  mov     [rbp+230h+var_178], rax
0x18002d0fa  lea     rax, [rbp+230h+var_2B0]
0x18002d0fe  mov     [rbp+230h+var_160], rax
0x18002d105  lea     rax, [rsp+330h+var_2E0]
0x18002d10a  mov     [rbp+230h+var_148], rax
0x18002d111  lea     rax, [rsp+330h+var_2E0]
0x18002d116  mov     [rbp+230h+var_140], rax
0x18002d11d  lea     rax, [rbp+230h+var_2A8]
0x18002d121  mov     [rbp+230h+var_128], rax
0x18002d128  lea     rax, [rsp+330h+var_2E0]
0x18002d12d  mov     [rbp+230h+var_110], rax
0x18002d134  lea     rax, [rsp+330h+var_2E0]
0x18002d139  mov     [rbp+230h+var_108], rax
0x18002d140  lea     rax, [rbp+230h+var_2A0]
0x18002d144  mov     [rbp+230h+var_F0], rax
0x18002d14b  mov     [rbp+230h+var_268], 4
0x18002d152  mov     [rbp+230h+var_250], edi
0x18002d155  mov     [rbp+230h+var_248], edx
0x18002d158  mov     [rbp+230h+var_238], rdi
0x18002d15c  mov     [rbp+230h+var_230], 68h ; 'h'
0x18002d163  mov     [rbp+230h+var_218], edi
0x18002d166  mov     [rbp+230h+var_210], edx
0x18002d169  mov     [rbp+230h+var_200], rdi
0x18002d16d  mov     [rbp+230h+var_1F8], 4
0x18002d174  mov     [rbp+230h+var_1E0], edi
0x18002d177  mov     [rbp+230h+var_1C8], rdi
0x18002d17b  mov     [rbp+230h+var_1C0], r8d
0x18002d17f  mov     [rbp+230h+var_1A8], edi
0x18002d185  mov     [rbp+230h+var_190], rdi
0x18002d18c  mov     [rbp+230h+var_188], r8d
0x18002d193  mov     [rbp+230h+var_170], edi
0x18002d199  mov     [rbp+230h+var_168], 2015h
0x18002d1a3  mov     [rbp+230h+var_158], rdi
0x18002d1aa  mov     [rbp+230h+var_150], r8d
0x18002d1b1  mov     [rbp+230h+var_138], edi
0x18002d1b7  mov     [rbp+230h+var_130], edx
0x18002d1bd  mov     [rbp+230h+var_120], rdi
0x18002d1c4  mov     [rbp+230h+var_118], r8d
0x18002d1cb  mov     [rbp+230h+var_100], edi
0x18002d1d1  mov     [rbp+230h+var_F8], ecx
0x18002d1d7  mov     [rbp+230h+var_E8], rdi
0x18002d1de  lea     rax, [rsp+330h+var_2E0]
0x18002d1e3  mov     [rbp+230h+var_E0], r8d
0x18002d1ea  mov     [rbp+230h+var_D8], rax
0x18002d1f1  lea     r12d, [rdx+5]
  ... truncated ...
```
