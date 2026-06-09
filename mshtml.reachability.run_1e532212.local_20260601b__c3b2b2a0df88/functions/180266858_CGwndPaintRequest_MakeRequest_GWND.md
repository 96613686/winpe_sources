# CGwndPaintRequest::MakeRequest(GWND *)

- ea: `0x180266858`
- end: `0x180266f29`
- name: `?MakeRequest@CGwndPaintRequest@@QEAAJPEAVGWND@@@Z`
- size: `1745`
- prototype: `__int64 __fastcall(CGwndPaintRequest *__hidden this, struct GWND *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180473948`

## callees

- `0x18006ad94`
- `0x18011a7c4`
- `0x180266858`
- `0x180266f30`
- `0x180266fa0`
- `0x1807a7ab4`
- `0x181104010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x180266d11`
- `KERNEL32!GetTickCount64` at `0x180266d11`
- `KERNEL32!GetCurrentThreadId` at `0x180266af8`
- `KERNEL32!GetCurrentThreadId` at `0x180266dcc`
- `KERNEL32!GetCurrentThreadId` at `0x180266af8`
- `KERNEL32!GetCurrentThreadId` at `0x180266dcc`
- `USER32!GetWindowThreadProcessId` at `0x180266aea`
- `USER32!GetWindowThreadProcessId` at `0x180266dbe`
- `USER32!GetWindowThreadProcessId` at `0x180266aea`
- `USER32!GetWindowThreadProcessId` at `0x180266dbe`
- `USER32!SetTimer` at `0x180266da7`
- `USER32!SetTimer` at `0x180266e1c`
- `USER32!SetTimer` at `0x180266e31`
- `USER32!SetTimer` at `0x180266e46`
- `USER32!SetTimer` at `0x180266da7`
- `USER32!SetTimer` at `0x180266e1c`
- `USER32!SetTimer` at `0x180266e31`
- `USER32!SetTimer` at `0x180266e46`
- `USER32!RedrawWindow` at `0x180266b3b`
- `USER32!RedrawWindow` at `0x180266b3b`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1802669f4`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180266a0a`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180266cbd`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180266cd3`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1802669f4`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180266a0a`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180266cbd`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180266cd3`

## pseudocode

```c
__int64 __fastcall CGwndPaintRequest::MakeRequest(CGwndPaintRequest *this, struct GWND *a2)
{
  __int64 v2; // r13
  struct GWND *v4; // r12
  __int64 v5; // rdi
  __int64 v6; // r14
  __int64 v7; // rax
  __int64 v8; // rax
  int v9; // ecx
  __int64 i; // rbx
  CImplAry *v11; // rcx
  int v12; // r8d
  __int64 v13; // rcx
  __int64 v14; // r9
  unsigned int v15; // eax
  int v16; // edx
  __int64 v17; // r8
  __int64 v18; // rax
  unsigned int v19; // ebx
  int v20; // r15d
  __int64 v21; // r8
  HWND v22; // rcx
  __int64 v24; // rcx
  __int64 v25; // rbp
  __int64 v26; // r14
  int v27; // ecx
  GUID v28; // xmm0
  __int128 *UserInputId; // rax
  UINT_PTR v30; // rdx
  __int128 v31; // xmm0
  __int64 (__fastcall *v32)(_QWORD, UINT_PTR, __int64, _QWORD, _DWORD); // rax
  UINT_PTR v33; // rax
  DWORD WindowThreadProcessId; // ebx
  unsigned int v36; // ecx
  __int64 v37; // r14
  __int64 v38; // r15
  __int64 v39; // r15
  struct GWND *Gwnd; // rdi
  int v41; // r8d
  __int64 v42; // rcx
  int v43; // edx
  __int64 j; // rbx
  CImplAry *v45; // rcx
  int v46; // r8d
  unsigned int UniqueID; // eax
  __int64 v48; // rcx
  unsigned int v49; // ebx
  int v50; // r12d
  HWND v51; // rcx
  UINT_PTR v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rbp
  __int64 v55; // r14
  int v56; // ecx
  GUID v57; // xmm0
  __int128 *v58; // rax
  UINT_PTR v59; // rdx
  __int128 v60; // xmm0
  __int64 (__fastcall *v61)(_QWORD, UINT_PTR, __int64, _QWORD, _DWORD); // rax
  UINT_PTR v62; // rax
  DWORD v63; // ebx
  _BYTE v64[72]; // [rsp+30h] [rbp-48h] BYREF

  v2 = 0;
  if ( !*((_BYTE *)this + 16) )
  {
    LODWORD(v5) = -2147418113;
    return (unsigned int)v5;
  }
  v4 = a2;
  if ( (unsigned __int16)*((_DWORD *)a2 + 31) )
  {
    v36 = *((unsigned __int16 *)a2 + 63);
    if ( (unsigned __int16)*((_DWORD *)a2 + 31) > v36 || v36 >= *((_DWORD *)a2 + 33) )
    {
      LODWORD(v5) = 0;
      return (unsigned int)v5;
    }
  }
  v5 = 0;
  if ( *((_BYTE *)this + 17) )
    goto LABEL_47;
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v7 = *(_QWORD *)(v6 + 16);
  if ( v7 )
    v2 = *(_QWORD *)(v7 + 232);
  if ( !*(_QWORD *)(v2 + 96) )
    goto LABEL_98;
  if ( v7 )
    v5 = *(_QWORD *)(v7 + 232);
  v8 = *(_QWORD *)(v5 + 112);
  v9 = *(_DWORD *)(v8 + 4);
  for ( i = *(_QWORD *)(v8 + 8); ; i += 56 )
  {
    if ( v9 <= 0 )
      goto LABEL_13;
    if ( *(CGwndPaintRequest **)i == this && *(_DWORD *)(i + 16) == 52737 )
      break;
    --v9;
  }
  if ( *(_DWORD *)(i + 24) != 10 )
    *(_DWORD *)(i + 24) = 10;
  if ( *(_DWORD *)(i + 32)
    || ((UserInputId = (__int128 *)GetUserInputId(v64, v5),
         v30 = *(unsigned int *)(i + 20),
         v31 = *UserInputId,
         v32 = (__int64 (__fastcall *)(_QWORD, UINT_PTR, __int64, _QWORD, _DWORD))qword_1815C4E28,
         *(_OWORD *)(i + 40) = v31,
         !v32)
      ? (v33 = SetTimer(*(HWND *)(v5 + 96), v30, 0xAu, 0))
      : (v33 = v32(*(_QWORD *)(v5 + 96), v30, 10, 0, *(_DWORD *)(i + 28))),
        v33) )
  {
    if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
      McTemplateU0pqpq_EventWriteTransfer(
        v9,
        (unsigned int)MSHTML_FORMSTIMER_RESET,
        *(_QWORD *)i,
        *(_DWORD *)(i + 16),
        *(_QWORD *)(i + 8),
        *(_DWORD *)(i + 24));
    LODWORD(v5) = 0;
    goto LABEL_31;
  }
LABEL_13:
  v11 = *(CImplAry **)(v2 + 112);
  v12 = *((_DWORD *)v11 + 1) + 1;
  if ( (unsigned int)v12 <= *(_DWORD *)v11 >> 2 )
  {
    LODWORD(v5) = 0;
LABEL_15:
    v13 = *(_QWORD *)(v6 + 16);
    if ( v13 )
      v13 = *(_QWORD *)(v13 + 232);
    v14 = *(_QWORD *)(v13 + 112);
LABEL_18:
    v15 = *(_DWORD *)(v13 + 104) + 1;
    *(_DWORD *)(v13 + 104) = v15;
    if ( v15 < 0x2002 )
    {
      *(_DWORD *)(v13 + 104) = 8194;
      v15 = 8194;
    }
    v16 = *(_DWORD *)(v14 + 4);
    v17 = *(_QWORD *)(v14 + 8);
    while ( v16 > 0 )
    {
      if ( v15 == *(_DWORD *)(v17 + 20) )
        goto LABEL_18;
      --v16;
      v17 += 56;
    }
    v18 = *(_QWORD *)(v6 + 16);
    v19 = *(_DWORD *)(v13 + 104);
    v20 = *(unsigned __int8 *)(v18 + 583);
    if ( !*(_BYTE *)(v18 + 583) )
    {
      v21 = (unsigned int)(v20 + 10);
      v22 = *(HWND *)(v2 + 96);
      if ( !(qword_1815C4E28
           ? ((__int64 (__fastcall *)(HWND, _QWORD, __int64))qword_1815C4E28)(v22, v19, v21)
           : SetTimer(v22, v19, v21, 0)) )
        goto LABEL_98;
    }
    v24 = *(_QWORD *)(v2 + 112);
    v25 = *(_QWORD *)(v24 + 8);
    v26 = 56LL * *(int *)(v24 + 4);
    *(_QWORD *)(v26 + v25) = this;
    *(_QWORD *)(v26 + v25 + 8) = CGwndPaintRequest::OnWatchdogTimer;
    *(_DWORD *)(v26 + v25 + 20) = v19;
    *(_DWORD *)(v26 + v25 + 16) = 52737;
    *(_QWORD *)(v26 + v25 + 24) = 10;
    *(_DWORD *)(v26 + v25 + 36) = 1;
    *(_DWORD *)(v26 + v25 + 32) = v20;
    if ( *((_BYTE *)GlobalThreadState() + 16)
      || (WindowThreadProcessId = GetWindowThreadProcessId(*(HWND *)(v2 + 96), 0),
          WindowThreadProcessId == GetCurrentThreadId()) )
    {
      v28 = *(GUID *)GlobalThreadState();
    }
    else
    {
      v28 = GUID_NULL;
    }
    *(GUID *)(v26 + v25 + 40) = v28;
    ++*(_DWORD *)(*(_QWORD *)(v2 + 112) + 4LL);
    if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
      McTemplateU0pqpq_EventWriteTransfer(
        v27,
        (unsigned int)MSHTML_FORMSTIMER_SET,
        (_DWORD)this,
        52737,
        (char)CGwndPaintRequest::OnWatchdogTimer,
        10);
    goto LABEL_30;
  }
  if ( v12 < 0 )
    goto LABEL_93;
  LODWORD(v5) = CImplAry::EnsureSizeWorker(v11, 0x38u, v12);
  if ( !(_DWORD)v5 )
    goto LABEL_15;
LABEL_30:
  if ( (int)v5 >= 0 )
  {
LABEL_31:
    *((_BYTE *)this + 17) = 1;
LABEL_47:
    if ( *((_BYTE *)this + 18) )
    {
LABEL_48:
      RedrawWindow(*((HWND *)v4 + 12), 0, 0, 2u);
      ++*((_WORD *)v4 + 62);
      return (unsigned int)v5;
    }
    v37 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    v38 = *(_QWORD *)(v37 + 16);
    if ( v38 )
      v39 = *(_QWORD *)(v38 + 232);
    else
      v39 = 0;
    if ( !*(_QWORD *)(v39 + 96) )
      goto LABEL_98;
    Gwnd = GetGwnd();
    v42 = *((_QWORD *)Gwnd + 14);
    v43 = *(_DWORD *)(v42 + 4);
    for ( j = *(_QWORD *)(v42 + 8); ; j += 56 )
    {
      if ( v43 <= 0 )
        goto LABEL_63;
      if ( *(CGwndPaintRequest **)j == this && *(_DWORD *)(j + 16) == 52738 )
        break;
      v43 -= v41;
    }
    if ( *(_DWORD *)(j + 24) != 300 )
      *(_DWORD *)(j + 24) = 300;
    if ( *(_DWORD *)(j + 32)
      || ((v58 = (__int128 *)GetUserInputId(v64, Gwnd),
           v59 = *(unsigned int *)(j + 20),
           v60 = *v58,
           v61 = (__int64 (__fastcall *)(_QWORD, UINT_PTR, __int64, _QWORD, _DWORD))qword_1815C4E28,
           *(_OWORD *)(j + 40) = v60,
           !v61)
        ? (v62 = SetTimer(*((HWND *)Gwnd + 12), v59, 0x12Cu, 0))
        : (v62 = v61(*((_QWORD *)Gwnd + 12), v59, 300, 0, *(_DWORD *)(j + 28))),
          v62) )
    {
      if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
        McTemplateU0pqpq_EventWriteTransfer(
          v42,
          (unsigned int)MSHTML_FORMSTIMER_RESET,
          *(_QWORD *)j,
          *(_DWORD *)(j + 16),
          *(_QWORD *)(j + 8),
          *(_DWORD *)(j + 24));
      LODWORD(v5) = 0;
LABEL_75:
      *((_BYTE *)this + 18) = 1;
      *(_QWORD *)this = GetTickCount64();
      *((_QWORD *)this + 1) = 0;
      goto LABEL_48;
    }
LABEL_63:
    v45 = *(CImplAry **)(v39 + 112);
    v46 = *((_DWORD *)v45 + 1) + 1;
    if ( (unsigned int)v46 <= *(_DWORD *)v45 >> 2 )
    {
      LODWORD(v5) = 0;
      goto LABEL_65;
    }
    if ( v46 >= 0 )
    {
      LODWORD(v5) = CImplAry::EnsureSizeWorker(v45, 0x38u, v46);
      if ( (_DWORD)v5 )
        goto LABEL_74;
LABEL_65:
      UniqueID = GetUniqueID();
      v48 = *(_QWORD *)(v37 + 16);
      v49 = UniqueID;
      v50 = *(unsigned __int8 *)(v48 + 583);
      if ( *(_BYTE *)(v48 + 583)
        || ((v51 = *(HWND *)(v39 + 96), !qword_1815C4E28)
          ? (v52 = SetTimer(v51, UniqueID, 0x12Cu, 0))
          : (v52 = ((__int64 (__fastcall *)(HWND, _QWORD, __int64, _QWORD, _DWORD))qword_1815C4E28)(
                     v51,
                     UniqueID,
                     300,
                     0,
                     0)),
            v52) )
      {
        v53 = *(_QWORD *)(v39 + 112);
        v54 = *(_QWORD *)(v53 + 8);
        v55 = 56LL * *(int *)(v53 + 4);
        *(_QWORD *)(v55 + v54) = this;
        *(_QWORD *)(v55 + v54 + 8) = CGwndPaintRequest::OnStarveCheckTimer;
        *(_DWORD *)(v55 + v54 + 20) = v49;
        *(_DWORD *)(v55 + v54 + 16) = 52738;
        *(_QWORD *)(v55 + v54 + 24) = 300;
        *(_DWORD *)(v55 + v54 + 36) = 1;
        *(_DWORD *)(v55 + v54 + 32) = v50;
        if ( *((_BYTE *)GlobalThreadState() + 16)
          || (v63 = GetWindowThreadProcessId(*(HWND *)(v39 + 96), 0), v63 == GetCurrentThreadId()) )
        {
          v57 = *(GUID *)GlobalThreadState();
        }
        else
        {
          v57 = GUID_NULL;
        }
        *(GUID *)(v55 + v54 + 40) = v57;
        ++*(_DWORD *)(*(_QWORD *)(v39 + 112) + 4LL);
        if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
          McTemplateU0pqpq_EventWriteTransfer(
            v56,
            (unsigned int)MSHTML_FORMSTIMER_SET,
            (_DWORD)this,
            52738,
            (char)CGwndPaintRequest::OnStarveCheckTimer,
            44);
        v4 = a2;
LABEL_74:
        if ( (int)v5 < 0 )
          return (unsigned int)v5;
        goto LABEL_75;
      }
LABEL_98:
      LODWORD(v5) = -2147467259;
      return (unsigned int)v5;
    }
LABEL_93:
    LODWORD(v5) = -2147024809;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180266858  mov     rax, rsp
0x18026685b  mov     [rax+18h], rbx
0x18026685f  mov     [rax+10h], rdx
0x180266863  mov     [rax+8], rcx
0x180266867  push    rbp
0x180266868  push    rsi
0x180266869  push    rdi
0x18026686a  push    r12
0x18026686c  push    r13
0x18026686e  push    r14
0x180266870  push    r15
0x180266872  sub     rsp, 40h
0x180266876  xor     r13d, r13d
0x180266879  mov     rsi, rcx
0x18026687c  cmp     [rcx+10h], r13b
0x180266880  jz      loc_180266EB9
0x180266886  mov     eax, [rdx+7Ch]
0x180266889  mov     r12, rdx
0x18026688c  and     eax, 0FFFFh
0x180266891  jnz     loc_180266B6D
0x180266897  mov     edi, r13d
0x18026689a  mov     edx, 10h
0x18026689f  mov     r8d, 1
0x1802668a5  cmp     [rsi+11h], r13b
0x1802668a9  jnz     loc_180266B1D
0x1802668af  mov     rax, gs:58h
0x1802668b8  mov     ecx, cs:_tls_index
0x1802668be  mov     ebp, edx
0x1802668c0  mov     r14, [rax+rcx*8]
0x1802668c4  mov     rax, [r14+rdx]
0x1802668c8  test    rax, rax
0x1802668cb  jz      short loc_1802668D4
0x1802668cd  mov     r13, [rax+0E8h]
0x1802668d4  cmp     [r13+60h], rdi
0x1802668d8  jz      loc_180266EF7
0x1802668de  test    rax, rax
0x1802668e1  jz      short loc_1802668EA
0x1802668e3  mov     rdi, [rax+0E8h]
0x1802668ea  mov     rax, [rdi+70h]
0x1802668ee  mov     ecx, [rax+4]
0x1802668f1  mov     rbx, [rax+8]
0x1802668f5  mov     r15d, 0Ah
0x1802668fb  test    ecx, ecx
0x1802668fd  jle     short loc_180266911
0x1802668ff  cmp     [rbx], rsi
0x180266902  jz      loc_180266A4F
0x180266908  sub     ecx, r8d
0x18026690b  add     rbx, 38h ; '8'
0x18026690f  jmp     short loc_1802668F5
0x180266911  mov     rcx, [r13+70h]; this
0x180266915  mov     r8d, [rcx+4]
0x180266919  mov     eax, [rcx]
0x18026691b  inc     r8d; int
0x18026691e  shr     eax, 2
0x180266921  cmp     r8d, eax
0x180266924  ja      loc_180266B8A
0x18026692a  xor     edi, edi
0x18026692c  mov     rcx, [r14+rbp]
0x180266930  test    rcx, rcx
0x180266933  jz      loc_180266B18
0x180266939  mov     rcx, [rcx+0E8h]
0x180266940  mov     r9, [rcx+70h]
0x180266944  mov     r10d, 2002h
0x18026694a  mov     eax, [rcx+68h]
0x18026694d  inc     eax
0x18026694f  mov     [rcx+68h], eax
0x180266952  cmp     eax, r10d
0x180266955  jb      loc_180266EEB
0x18026695b  mov     edx, [r9+4]
0x18026695f  mov     r8, [r9+8]
0x180266963  test    edx, edx
0x180266965  jg      loc_180266ACF
0x18026696b  mov     rax, [r14+rbp]
0x18026696f  mov     ebx, [rcx+68h]
0x180266972  movzx   r15d, byte ptr [rax+247h]
0x18026697a  test    r15d, r15d
0x18026697d  jnz     short loc_1802669AF
0x18026697f  mov     rax, cs:qword_1815C4E28
0x180266986  lea     r8d, [r15+0Ah]; uElapse
0x18026698a  mov     rcx, [r13+60h]; hWnd
0x18026698e  xor     r9d, r9d; lpTimerFunc
0x180266991  mov     edx, ebx; nIDEvent
0x180266993  test    rax, rax
0x180266996  jz      loc_180266DA7
0x18026699c  mov     dword ptr [rsp+78h+var_58], r9d
0x1802669a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802669a6  test    rax, rax
0x1802669a9  jz      loc_180266EF7
0x1802669af  mov     rcx, [r13+70h]
0x1802669b3  movsxd  rax, dword ptr [rcx+4]
0x1802669b7  mov     rbp, [rcx+8]
0x1802669bb  imul    r14, rax, 38h ; '8'
0x1802669bf  lea     rax, ?OnWatchdogTimer@CGwndPaintRequest@@QEAAJI@Z; CGwndPaintRequest::OnWatchdogTimer(uint)
0x1802669c6  mov     [r14+rbp], rsi
0x1802669ca  mov     [r14+rbp+8], rax
0x1802669cf  mov     [r14+rbp+14h], ebx
0x1802669d4  mov     dword ptr [r14+rbp+10h], 0CE01h
0x1802669dd  mov     qword ptr [r14+rbp+18h], 0Ah
0x1802669e6  mov     dword ptr [r14+rbp+24h], 1
0x1802669ef  mov     [r14+rbp+20h], r15d
0x1802669f4  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1802669fb  nop     dword ptr [rax+rax+00h]
0x180266a00  cmp     byte ptr [rax+10h], 0
0x180266a04  jz      loc_180266AE4
0x180266a0a  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180266a11  nop     dword ptr [rax+rax+00h]
0x180266a16  movups  xmm0, xmmword ptr [rax]
0x180266a19  movdqu  xmmword ptr [r14+rbp+28h], xmm0
0x180266a20  mov     rax, [r13+70h]
0x180266a24  mov     r8d, 1
0x180266a2a  add     [rax+4], r8d
0x180266a2e  test    byte ptr cs:Microsoft_IEEnableBits+2, 10h
0x180266a35  jnz     loc_180266E57
0x180266a3b  xor     r13d, r13d
0x180266a3e  test    edi, edi
0x180266a40  js      loc_180266B52
0x180266a46  mov     [rsi+11h], r8b
0x180266a4a  jmp     loc_180266B21
0x180266a4f  cmp     dword ptr [rbx+10h], 0CE01h
0x180266a56  jnz     loc_180266908
0x180266a5c  cmp     [rbx+18h], r15d
0x180266a60  jz      short loc_180266A66
0x180266a62  mov     [rbx+18h], r15d
0x180266a66  cmp     dword ptr [rbx+20h], 0
0x180266a6a  jnz     short loc_180266AB3
0x180266a6c  mov     rdx, rdi
0x180266a6f  lea     rcx, [rsp+78h+var_48]
0x180266a74  call    _GetUserInputId
0x180266a79  mov     edx, [rbx+14h]; nIDEvent
0x180266a7c  xor     r9d, r9d; lpTimerFunc
0x180266a7f  mov     r8d, r15d; uElapse
0x180266a82  movups  xmm0, xmmword ptr [rax]
0x180266a85  mov     rax, cs:qword_1815C4E28
0x180266a8c  movdqu  xmmword ptr [rbx+28h], xmm0
0x180266a91  test    rax, rax
0x180266a94  jz      loc_180266E2D
0x180266a9a  mov     ecx, [rbx+1Ch]
0x180266a9d  mov     dword ptr [rsp+78h+var_58], ecx
0x180266aa1  mov     rcx, [rdi+60h]
0x180266aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180266aaa  test    rax, rax
0x180266aad  jz      loc_180266911
0x180266ab3  test    byte ptr cs:Microsoft_IEEnableBits+2, 10h
0x180266aba  jnz     loc_180266EC3
0x180266ac0  xor     r13d, r13d
0x180266ac3  mov     edi, r13d
0x180266ac6  lea     r8d, [r13+1]
0x180266aca  jmp     loc_180266A46
0x180266acf  cmp     eax, [r8+14h]
0x180266ad3  jz      loc_18026694A
0x180266ad9  dec     edx
0x180266adb  add     r8, 38h ; '8'
0x180266adf  jmp     loc_180266963
0x180266ae4  mov     rcx, [r13+60h]; hWnd
0x180266ae8  xor     edx, edx; lpdwProcessId
0x180266aea  call    cs:__imp_GetWindowThreadProcessId
0x180266af1  nop     dword ptr [rax+rax+00h]
0x180266af6  mov     ebx, eax
0x180266af8  call    cs:__imp_GetCurrentThreadId
0x180266aff  nop     dword ptr [rax+rax+00h]
0x180266b04  cmp     ebx, eax
0x180266b06  jz      loc_180266A0A
0x180266b0c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180266b13  jmp     loc_180266A19
0x180266b18  jmp     loc_180266940
0x180266b1d  test    edi, edi
0x180266b1f  js      short loc_180266B52
0x180266b21  cmp     [rsi+12h], r13b
0x180266b25  jz      loc_180266BAC
0x180266b2b  mov     rcx, [r12+60h]; hWnd
0x180266b30  mov     r9d, 2; flags
0x180266b36  xor     r8d, r8d; hrgnUpdate
0x180266b39  xor     edx, edx; lprcUpdate
0x180266b3b  call    cs:__imp_RedrawWindow
0x180266b42  nop     dword ptr [rax+rax+00h]
0x180266b47  mov     eax, 1
0x180266b4c  add     [r12+7Ch], ax
0x180266b52  mov     rbx, [rsp+78h+arg_10]
0x180266b5a  mov     eax, edi
0x180266b5c  add     rsp, 40h
0x180266b60  pop     r15
0x180266b62  pop     r14
0x180266b64  pop     r13
0x180266b66  pop     r12
0x180266b68  pop     rdi
0x180266b69  pop     rsi
0x180266b6a  pop     rbp
0x180266b6b  retn
0x180266b6d  movzx   ecx, word ptr [r12+7Eh]
0x180266b73  cmp     eax, ecx
0x180266b75  ja      short loc_180266B85
0x180266b77  cmp     ecx, [r12+84h]
0x180266b7f  jb      loc_180266897
0x180266b85  mov     edi, r13d
0x180266b88  jmp     short loc_180266B52
0x180266b8a  test    r8d, r8d
0x180266b8d  js      loc_180266E12
0x180266b93  mov     edx, 38h ; '8'; unsigned __int64
0x180266b98  call    ?EnsureSizeWorker@CImplAry@@AEAAJ_KJ@Z; CImplAry::EnsureSizeWorker(unsigned __int64,long)
0x180266b9d  mov     edi, eax
0x180266b9f  test    eax, eax
0x180266ba1  jz      loc_18026692C
0x180266ba7  jmp     loc_180266E80
0x180266bac  mov     ecx, cs:_tls_index
0x180266bb2  mov     rax, gs:58h
0x180266bbb  mov     edx, 10h
0x180266bc0  mov     ebp, edx
0x180266bc2  mov     r14, [rax+rcx*8]
0x180266bc6  mov     r15, [r14+rdx]
0x180266bca  test    r15, r15
0x180266bcd  jz      loc_180266DEC
0x180266bd3  mov     r15, [r15+0E8h]
0x180266bda  cmp     [r15+60h], r13
0x180266bde  jz      loc_180266EF7
0x180266be4  call    ?GetGwnd@@YAPEAVGWND@@XZ; GetGwnd(void)
0x180266be9  mov     rdi, rax
0x180266bec  mov     rcx, [rax+70h]
0x180266bf0  mov     edx, [rcx+4]
0x180266bf3  mov     rbx, [rcx+8]
0x180266bf7  mov     eax, 12Ch
0x180266bfc  test    edx, edx
0x180266bfe  jle     short loc_180266C12
0x180266c00  cmp     [rbx], rsi
0x180266c03  jz      loc_180266D2D
0x180266c09  sub     edx, r8d
0x180266c0c  add     rbx, 38h ; '8'
0x180266c10  jmp     short loc_180266BF7
0x180266c12  mov     rcx, [r15+70h]; this
0x180266c16  mov     r8d, [rcx+4]
0x180266c1a  mov     eax, [rcx]
0x180266c1c  inc     r8d; int
0x180266c1f  shr     eax, 2
0x180266c22  cmp     r8d, eax
0x180266c25  ja      loc_180266DF4
0x180266c2b  mov     edi, r13d
0x180266c2e  call    GetUniqueID
0x180266c33  mov     rcx, [r14+rbp]
0x180266c37  mov     ebx, eax
0x180266c39  movzx   r12d, byte ptr [rcx+247h]
0x180266c41  test    r12d, r12d
0x180266c44  jnz     short loc_180266C78
0x180266c46  mov     rax, cs:qword_1815C4E28
0x180266c4d  xor     r9d, r9d; lpTimerFunc
0x180266c50  mov     rcx, [r15+60h]; hWnd
0x180266c54  mov     edx, ebx; nIDEvent
0x180266c56  mov     r8d, 12Ch; uElapse
0x180266c5c  test    rax, rax
0x180266c5f  jz      loc_180266E1C
0x180266c65  mov     dword ptr [rsp+78h+var_58], r13d
0x180266c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180266c6f  test    rax, rax
0x180266c72  jz      loc_180266EF7
0x180266c78  mov     rcx, [r15+70h]
0x180266c7c  movsxd  rax, dword ptr [rcx+4]
0x180266c80  mov     rbp, [rcx+8]
0x180266c84  imul    r14, rax, 38h ; '8'
0x180266c88  lea     rax, ?OnStarveCheckTimer@CGwndPaintRequest@@QEAAJI@Z; CGwndPaintRequest::OnStarveCheckTimer(uint)
0x180266c8f  mov     [r14+rbp], rsi
0x180266c93  mov     [r14+rbp+8], rax
0x180266c98  mov     [r14+rbp+14h], ebx
0x180266c9d  mov     dword ptr [r14+rbp+10h], 0CE02h
0x180266ca6  mov     qword ptr [r14+rbp+18h], 12Ch
0x180266caf  mov     dword ptr [r14+rbp+24h], 1
0x180266cb8  mov     [r14+rbp+20h], r12d
0x180266cbd  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180266cc4  nop     dword ptr [rax+rax+00h]
0x180266cc9  cmp     [rax+10h], r13b
0x180266ccd  jz      loc_180266DB8
0x180266cd3  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180266cda  nop     dword ptr [rax+rax+00h]
0x180266cdf  movups  xmm0, xmmword ptr [rax]
0x180266ce2  movdqu  xmmword ptr [r14+rbp+28h], xmm0
0x180266ce9  mov     rax, [r15+70h]
0x180266ced  inc     dword ptr [rax+4]
0x180266cf0  test    byte ptr cs:Microsoft_IEEnableBits+2, 10h
0x180266cf7  jnz     loc_180266E8B
0x180266cfd  mov     r12, [rsp+78h+arg_8]
0x180266d05  test    edi, edi
0x180266d07  js      loc_180266B52
0x180266d0d  mov     byte ptr [rsi+12h], 1
0x180266d11  call    cs:__imp_GetTickCount64
0x180266d18  nop     dword ptr [rax+rax+00h]
0x180266d1d  mov     [rsi], rax
0x180266d20  mov     qword ptr [rsi+8], 0
0x180266d28  jmp     loc_180266B2B
0x180266d2d  cmp     dword ptr [rbx+10h], 0CE02h
0x180266d34  jnz     loc_180266C09
0x180266d3a  cmp     [rbx+18h], eax
0x180266d3d  jz      short loc_180266D42
0x180266d3f  mov     [rbx+18h], eax
0x180266d42  cmp     [rbx+20h], r13d
0x180266d46  jnz     short loc_180266D92
0x180266d48  mov     rdx, rdi
0x180266d4b  lea     rcx, [rsp+78h+var_48]
0x180266d50  call    _GetUserInputId
0x180266d55  mov     edx, [rbx+14h]; nIDEvent
0x180266d58  xor     r9d, r9d; lpTimerFunc
0x180266d5b  mov     r8d, 12Ch; uElapse
0x180266d61  movups  xmm0, xmmword ptr [rax]
0x180266d64  mov     rax, cs:qword_1815C4E28
  ... truncated ...
```
