# CPaintBeat::UpdateWMTimer(void)

- ea: `0x1803e9bbc`
- end: `0x1803ea1c4`
- name: `?UpdateWMTimer@CPaintBeat@@AEAAXXZ`
- size: `1544`
- prototype: `void __fastcall(CPaintBeat *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1803e94b8`
- `0x1803eaa60`

## callees

- `0x18006ad94`
- `0x1803e9bbc`
- `0x1803eab10`
- `0x1807a7ab4`
- `0x1810f650a`
- `0x181104010`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1803e9d22`
- `KERNEL32!QueryPerformanceCounter` at `0x1803e9d22`
- `KERNEL32!QueryPerformanceFrequency` at `0x1803ea130`
- `KERNEL32!QueryPerformanceFrequency` at `0x1803ea130`
- `KERNEL32!GetCurrentThreadId` at `0x1803ea064`
- `KERNEL32!GetCurrentThreadId` at `0x1803ea0d8`
- `KERNEL32!GetCurrentThreadId` at `0x1803ea064`
- `KERNEL32!GetCurrentThreadId` at `0x1803ea0d8`
- `USER32!GetWindowThreadProcessId` at `0x1803ea056`
- `USER32!GetWindowThreadProcessId` at `0x1803ea0ca`
- `USER32!GetWindowThreadProcessId` at `0x1803ea056`
- `USER32!GetWindowThreadProcessId` at `0x1803ea0ca`
- `USER32!SetTimer` at `0x1803ea0b0`
- `USER32!SetTimer` at `0x1803ea118`
- `USER32!SetTimer` at `0x1803ea0b0`
- `USER32!SetTimer` at `0x1803ea118`
- `USER32!KillTimer` at `0x1803e9ce8`
- `USER32!KillTimer` at `0x1803e9ce8`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1803e9f2a`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1803e9f40`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1803e9fa5`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1803e9fbb`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1803ea0ec`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1803e9f2a`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1803e9f40`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1803e9fa5`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1803e9fbb`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1803ea0ec`

## pseudocode

```c
void __fastcall CPaintBeat::UpdateWMTimer(CPaintBeat *this)
{
  int v1; // r12d
  __int64 **v3; // rcx
  __int64 *v4; // rbx
  __int64 *i; // rax
  unsigned __int64 v6; // r14
  __int64 v7; // rbp
  __int64 v8; // rbp
  __int64 v9; // rbx
  int v10; // eax
  int v11; // esi
  __int64 v12; // rbx
  UINT_PTR v13; // rbx
  __int64 v14; // r9
  int v15; // ecx
  __int64 v16; // rsi
  LARGE_INTEGER v17; // r9
  LARGE_INTEGER v18; // r8
  unsigned __int64 v19; // r8
  UINT v20; // ebp
  __int64 v21; // r13
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v23; // rbx
  __int64 v24; // rax
  __int64 v25; // r14
  UINT v26; // r15d
  __int64 v27; // rax
  int v28; // ecx
  __int64 j; // rsi
  CImplAry *v30; // rcx
  int v31; // r8d
  __int64 v32; // r10
  __int64 v33; // rcx
  __int64 v34; // r9
  unsigned int v35; // eax
  int v36; // edx
  __int64 v37; // r8
  unsigned int v38; // ebx
  __int64 v39; // rax
  int v40; // r15d
  HWND v41; // rcx
  UINT_PTR v42; // rax
  __int64 v43; // rcx
  __int64 v44; // r14
  __int64 v45; // rsi
  int v46; // ecx
  GUID v47; // xmm0
  HWND *v48; // r14
  __int128 v49; // xmm0
  __int64 (__fastcall *v50)(HWND, UINT_PTR, _QWORD, _QWORD, _DWORD); // rax
  UINT_PTR v51; // rdx
  HWND v52; // rcx
  DWORD v54; // ebx
  DWORD WindowThreadProcessId; // ebx
  LARGE_INTEGER PerformanceCount; // [rsp+80h] [rbp+8h] BYREF
  __int64 v57; // [rsp+88h] [rbp+10h]
  __int64 v58; // [rsp+90h] [rbp+18h]
  unsigned __int64 v59; // [rsp+98h] [rbp+20h]

  v1 = 0;
  v3 = (__int64 **)((char *)this + 288);
  v4 = 0;
  for ( i = *v3; i != (__int64 *)v3; i = (__int64 *)*i )
  {
    if ( !*((_BYTE *)i + 44) )
    {
      v4 = i;
      break;
    }
  }
  if ( v4 )
  {
    v6 = v4[7];
    v59 = v6;
    if ( *((_BYTE *)this + 101) && *((_QWORD *)this + 10) <= v6 )
      return;
    v16 = *((_QWORD *)this + 1);
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    v17 = CQPCTick::s_qpcFrequency;
    if ( CQPCTick::s_qpcFrequency.QuadPart
      || (QueryPerformanceFrequency(&CQPCTick::s_qpcFrequency),
          v17 = CQPCTick::s_qpcFrequency,
          CQPCTick::s_qpcFrequency.QuadPart) )
    {
      v18 = PerformanceCount;
      if ( PerformanceCount.QuadPart && v17.QuadPart && v17.QuadPart != 1000 )
        v18.QuadPart = 1000 * (PerformanceCount.QuadPart % (unsigned __int64)v17.QuadPart) / v17.QuadPart
                     + 1000 * (PerformanceCount.QuadPart / (unsigned __int64)v17.QuadPart);
    }
    else
    {
      v18.QuadPart = 0;
    }
    v19 = v18.QuadPart - *(_QWORD *)(v16 + 536);
    v20 = 0;
    if ( v4[7] > v19 )
    {
      v20 = -1;
      if ( v6 - v19 < 0xFFFFFFFF )
        v20 = v6 - v19;
    }
    v21 = 0;
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    v23 = 16;
    v57 = 16;
    v58 = ThreadLocalStoragePointer[(unsigned int)tls_index];
    v24 = *(_QWORD *)(v58 + 16);
    if ( v24 )
      v21 = *(_QWORD *)(v24 + 232);
    if ( *(_QWORD *)(v21 + 96) )
    {
      v25 = 0;
      if ( v24 )
        v25 = *(_QWORD *)(v24 + 232);
      v26 = v20;
      if ( v20 < 0xA )
        v26 = 10;
      v27 = *(_QWORD *)(v25 + 112);
      v28 = *(_DWORD *)(v27 + 4);
      for ( j = *(_QWORD *)(v27 + 8); ; j += 56 )
      {
        if ( v28 <= 0 )
          goto LABEL_45;
        if ( *(CPaintBeat **)j == this && *(_DWORD *)(j + 16) == 206 )
          break;
        --v28;
      }
      if ( *(_DWORD *)(j + 24) != v26 )
        *(_DWORD *)(j + 24) = v26;
      if ( *(_DWORD *)(j + 32) )
        goto LABEL_74;
      if ( *((_BYTE *)GlobalThreadState() + 16) )
      {
        v48 = (HWND *)(v25 + 96);
        v49 = *(_OWORD *)GlobalThreadState();
      }
      else
      {
        v48 = (HWND *)(v25 + 96);
        WindowThreadProcessId = GetWindowThreadProcessId(*v48, 0);
        v49 = WindowThreadProcessId == GetCurrentThreadId() ? *(_OWORD *)GlobalThreadState() : *(_OWORD *)&GUID_NULL;
        v23 = v57;
      }
      v50 = (__int64 (__fastcall *)(HWND, UINT_PTR, _QWORD, _QWORD, _DWORD))qword_1815C4E28;
      v51 = *(unsigned int *)(j + 20);
      *(_OWORD *)(j + 40) = v49;
      v52 = *v48;
      if ( v50 ? v50(v52, v51, v26, 0, *(_DWORD *)(j + 28)) : SetTimer(v52, v51, v26, 0) )
      {
LABEL_74:
        if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
          McTemplateU0pqpq_EventWriteTransfer(
            v28,
            (unsigned int)MSHTML_FORMSTIMER_RESET,
            *(_QWORD *)j,
            *(_DWORD *)(j + 16),
            *(_QWORD *)(j + 8),
            *(_DWORD *)(j + 24));
LABEL_64:
        *((_QWORD *)this + 10) = v59;
        *((_BYTE *)this + 101) = 1;
        return;
      }
LABEL_45:
      v30 = *(CImplAry **)(v21 + 112);
      v31 = *((_DWORD *)v30 + 1) + 1;
      if ( (unsigned int)v31 > *(_DWORD *)v30 >> 2 )
      {
        if ( v31 < 0 )
          goto LABEL_89;
        v1 = CImplAry::EnsureSizeWorker(v30, 0x38u, v31);
        if ( v1 )
          goto LABEL_63;
      }
      v32 = v58;
      v33 = *(_QWORD *)(v58 + v23);
      if ( v33 )
        v33 = *(_QWORD *)(v33 + 232);
      v34 = *(_QWORD *)(v33 + 112);
LABEL_49:
      v35 = *(_DWORD *)(v33 + 104) + 1;
      *(_DWORD *)(v33 + 104) = v35;
      if ( v35 < 0x2002 )
      {
        *(_DWORD *)(v33 + 104) = 8194;
        v35 = 8194;
      }
      v36 = *(_DWORD *)(v34 + 4);
      v37 = *(_QWORD *)(v34 + 8);
      while ( v36 > 0 )
      {
        if ( v35 == *(_DWORD *)(v37 + 20) )
          goto LABEL_49;
        --v36;
        v37 += 56;
      }
      v38 = *(_DWORD *)(v33 + 104);
      if ( v20 < 0xA )
        v20 = 10;
      v39 = *(_QWORD *)(v32 + v57);
      v40 = *(unsigned __int8 *)(v39 + 583);
      if ( *(_BYTE *)(v39 + 583)
        || ((v41 = *(HWND *)(v21 + 96), !qword_1815C4E28)
          ? (v42 = SetTimer(v41, v38, v20, 0))
          : (v42 = ((__int64 (__fastcall *)(HWND, _QWORD, _QWORD))qword_1815C4E28)(v41, v38, v20)),
            v42) )
      {
        v43 = *(_QWORD *)(v21 + 112);
        v44 = *(_QWORD *)(v43 + 8);
        v45 = 56LL * *(int *)(v43 + 4);
        *(_QWORD *)(v45 + v44) = this;
        *(_QWORD *)(v45 + v44 + 8) = CPaintBeat::OnWMTimer;
        *(_DWORD *)(v45 + v44 + 20) = v38;
        *(_DWORD *)(v45 + v44 + 16) = 206;
        *(_DWORD *)(v45 + v44 + 24) = v20;
        *(_DWORD *)(v45 + v44 + 36) = 1;
        *(_DWORD *)(v45 + v44 + 32) = v40;
        *(_DWORD *)(v45 + v44 + 28) = 0;
        if ( *((_BYTE *)GlobalThreadState() + 16)
          || (v54 = GetWindowThreadProcessId(*(HWND *)(v21 + 96), 0), v54 == GetCurrentThreadId()) )
        {
          v47 = *(GUID *)GlobalThreadState();
        }
        else
        {
          v47 = GUID_NULL;
        }
        *(GUID *)(v45 + v44 + 40) = v47;
        ++*(_DWORD *)(*(_QWORD *)(v21 + 112) + 4LL);
        if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
          McTemplateU0pqpq_EventWriteTransfer(
            v46,
            (unsigned int)MSHTML_FORMSTIMER_SET,
            (_DWORD)this,
            206,
            (char)CPaintBeat::OnWMTimer,
            v20);
LABEL_63:
        if ( v1 < 0 )
          goto LABEL_89;
        goto LABEL_64;
      }
    }
LABEL_89:
    CPaintBeat::StopWMTimer(this);
    return;
  }
  if ( *((_BYTE *)this + 101) )
  {
    v7 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 16LL);
    if ( v7 )
    {
      v8 = *(_QWORD *)(v7 + 232);
      if ( v8 )
      {
        v9 = *(_QWORD *)(v8 + 112);
        if ( v9 )
        {
          v10 = *(_DWORD *)(v9 + 4);
          v11 = 0;
          v12 = *(_QWORD *)(v9 + 8);
          while ( v10 > 0 )
          {
            if ( *(CPaintBeat **)v12 == this && *(_DWORD *)(v12 + 16) == 206 )
            {
              if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
                McTemplateU0pqpq_EventWriteTransfer(
                  206,
                  (unsigned int)MSHTML_FORMSTIMER_KILL,
                  *(_QWORD *)v12,
                  206,
                  *(_QWORD *)(v12 + 8),
                  *(_DWORD *)(v12 + 24));
              v13 = *(unsigned int *)(v12 + 20);
              if ( v11 >= 0 )
              {
                v14 = *(_QWORD *)(v8 + 112);
                v15 = *(_DWORD *)(v14 + 4);
                if ( v11 < v15 )
                {
                  *(_DWORD *)(v14 + 4) = v15 - 1;
                  if ( v11 < (unsigned int)(v15 - 1) )
                    memmove_0(
                      (void *)(*(_QWORD *)(v14 + 8) + 56LL * v11),
                      (const void *)(*(_QWORD *)(v14 + 8) + 56LL * (v11 + 1)),
                      56LL * (unsigned int)(v15 - v11 - 1));
                }
              }
              KillTimer(*(HWND *)(v8 + 96), v13);
              break;
            }
            --v10;
            ++v11;
            v12 += 56;
          }
        }
      }
    }
    *((_BYTE *)this + 101) = 0;
    *((_QWORD *)this + 10) = 0;
  }
}

```

## disassembly

```asm
0x1803e9bbc  push    rbx
0x1803e9bbe  push    rbp
0x1803e9bbf  push    rsi
0x1803e9bc0  push    rdi
0x1803e9bc1  push    r12
0x1803e9bc3  push    r13
0x1803e9bc5  push    r14
0x1803e9bc7  push    r15
0x1803e9bc9  sub     rsp, 38h
0x1803e9bcd  xor     r12d, r12d
0x1803e9bd0  mov     rdi, rcx
0x1803e9bd3  add     rcx, 120h
0x1803e9bda  mov     ebx, r12d
0x1803e9bdd  mov     rax, [rcx]
0x1803e9be0  cmp     rax, rcx
0x1803e9be3  jz      short loc_1803E9BF2
0x1803e9be5  cmp     [rax+2Ch], r12b
0x1803e9be9  jnz     loc_1803EA089
0x1803e9bef  mov     rbx, rax
0x1803e9bf2  test    rbx, rbx
0x1803e9bf5  jz      short loc_1803E9C29
0x1803e9bf7  mov     r14, [rbx+38h]
0x1803e9bfb  mov     [rsp+78h+arg_18], r14
0x1803e9c03  cmp     [rdi+65h], r12b
0x1803e9c07  jz      loc_1803E9D0E
0x1803e9c0d  cmp     [rdi+50h], r14
0x1803e9c11  ja      loc_1803E9D0E
0x1803e9c17  add     rsp, 38h
0x1803e9c1b  pop     r15
0x1803e9c1d  pop     r14
0x1803e9c1f  pop     r13
0x1803e9c21  pop     r12
0x1803e9c23  pop     rdi
0x1803e9c24  pop     rsi
0x1803e9c25  pop     rbp
0x1803e9c26  pop     rbx
0x1803e9c27  retn
0x1803e9c29  cmp     [rdi+65h], r12b
0x1803e9c2d  jz      short loc_1803E9C17
0x1803e9c2f  mov     edx, cs:_tls_index
0x1803e9c35  mov     rax, gs:58h
0x1803e9c3e  mov     r8d, 10h
0x1803e9c44  mov     rax, [rax+rdx*8]
0x1803e9c48  mov     rbp, [r8+rax]
0x1803e9c4c  test    rbp, rbp
0x1803e9c4f  jz      loc_1803E9CF4
0x1803e9c55  mov     rbp, [rbp+0E8h]
0x1803e9c5c  test    rbp, rbp
0x1803e9c5f  jz      loc_1803E9CF4
0x1803e9c65  mov     rbx, [rbp+70h]
0x1803e9c69  test    rbx, rbx
0x1803e9c6c  jz      loc_1803E9CF4
0x1803e9c72  mov     eax, [rbx+4]
0x1803e9c75  mov     esi, r12d
0x1803e9c78  mov     rbx, [rbx+8]
0x1803e9c7c  mov     ecx, 0CEh
0x1803e9c81  test    eax, eax
0x1803e9c83  jle     short loc_1803E9CF4
0x1803e9c85  cmp     [rbx], rdi
0x1803e9c88  jnz     short loc_1803E9D01
0x1803e9c8a  cmp     [rbx+10h], ecx
0x1803e9c8d  jnz     short loc_1803E9D01
0x1803e9c8f  test    byte ptr cs:Microsoft_IEEnableBits+2, 10h
0x1803e9c96  jnz     loc_1803EA154
0x1803e9c9c  mov     ebx, [rbx+14h]
0x1803e9c9f  test    esi, esi
0x1803e9ca1  js      short loc_1803E9CE1
0x1803e9ca3  mov     r9, [rbp+70h]
0x1803e9ca7  mov     ecx, [r9+4]
0x1803e9cab  cmp     esi, ecx
0x1803e9cad  jge     short loc_1803E9CE1
0x1803e9caf  lea     eax, [rcx-1]
0x1803e9cb2  mov     [r9+4], eax
0x1803e9cb6  cmp     esi, eax
0x1803e9cb8  jnb     short loc_1803E9CE1
0x1803e9cba  sub     ecx, esi
0x1803e9cbc  lea     eax, [rcx-1]
0x1803e9cbf  imul    r8, rax, 38h ; '8'; Size
0x1803e9cc3  lea     eax, [rsi+1]
0x1803e9cc6  movsxd  rdx, eax
0x1803e9cc9  movsxd  rax, esi
0x1803e9ccc  imul    rcx, rax, 38h ; '8'
0x1803e9cd0  imul    rdx, 38h ; '8'
0x1803e9cd4  add     rcx, [r9+8]; void *
0x1803e9cd8  add     rdx, [r9+8]; Src
0x1803e9cdc  call    memmove_0
0x1803e9ce1  mov     rcx, [rbp+60h]; hWnd
0x1803e9ce5  mov     rdx, rbx; uIDEvent
0x1803e9ce8  call    cs:__imp_KillTimer
0x1803e9cef  nop     dword ptr [rax+rax+00h]
0x1803e9cf4  mov     [rdi+65h], r12b
0x1803e9cf8  mov     [rdi+50h], r12
0x1803e9cfc  jmp     loc_1803E9C17
0x1803e9d01  dec     eax
0x1803e9d03  inc     esi
0x1803e9d05  add     rbx, 38h ; '8'
0x1803e9d09  jmp     loc_1803E9C81
0x1803e9d0e  mov     rsi, [rdi+8]
0x1803e9d12  lea     rcx, [rsp+78h+PerformanceCount]; lpPerformanceCount
0x1803e9d1a  mov     qword ptr [rsp+78h+PerformanceCount], r12
0x1803e9d22  call    cs:__imp_QueryPerformanceCounter
0x1803e9d29  nop     dword ptr [rax+rax+00h]
0x1803e9d2e  mov     r9, qword ptr cs:?s_qpcFrequency@CQPCTick@@0_KA; unsigned __int64 CQPCTick::s_qpcFrequency ...
0x1803e9d35  test    r9, r9
0x1803e9d38  jz      loc_1803EA129
0x1803e9d3e  mov     r8, qword ptr [rsp+78h+PerformanceCount]
0x1803e9d46  test    r8, r8
0x1803e9d49  jz      short loc_1803E9D81
0x1803e9d4b  test    r9, r9
0x1803e9d4e  jz      short loc_1803E9D81
0x1803e9d50  cmp     r9, 3E8h
0x1803e9d57  jz      short loc_1803E9D81
0x1803e9d59  xor     edx, edx
0x1803e9d5b  mov     rax, r8
0x1803e9d5e  div     r9
0x1803e9d61  xor     edx, edx
0x1803e9d63  mov     rcx, rax
0x1803e9d66  imul    rax, r9
0x1803e9d6a  sub     r8, rax
0x1803e9d6d  imul    rax, r8, 3E8h
0x1803e9d74  imul    r8, rcx, 3E8h
0x1803e9d7b  div     r9
0x1803e9d7e  add     r8, rax
0x1803e9d81  sub     r8, [rsi+218h]
0x1803e9d88  mov     ebp, r12d
0x1803e9d8b  cmp     [rbx+38h], r8
0x1803e9d8f  jbe     short loc_1803E9DA5
0x1803e9d91  mov     rax, r14
0x1803e9d94  mov     ebp, 0FFFFFFFFh
0x1803e9d99  sub     rax, r8
0x1803e9d9c  cmp     rax, rbp
0x1803e9d9f  jb      loc_1803EA1A5
0x1803e9da5  mov     ecx, cs:_tls_index
0x1803e9dab  mov     r13, r12
0x1803e9dae  mov     rax, gs:58h
0x1803e9db7  mov     r8d, 10h
0x1803e9dbd  mov     ebx, r8d
0x1803e9dc0  mov     [rsp+78h+arg_8], rbx
0x1803e9dc8  mov     rax, [rax+rcx*8]
0x1803e9dcc  mov     [rsp+78h+arg_10], rax
0x1803e9dd4  mov     rax, [rax+r8]
0x1803e9dd8  test    rax, rax
0x1803e9ddb  jz      short loc_1803E9DE4
0x1803e9ddd  mov     r13, [rax+0E8h]
0x1803e9de4  cmp     [r13+60h], r12
0x1803e9de8  jz      loc_1803EA108
0x1803e9dee  mov     r14, r12
0x1803e9df1  test    rax, rax
0x1803e9df4  jz      short loc_1803E9DFD
0x1803e9df6  mov     r14, [rax+0E8h]
0x1803e9dfd  mov     eax, 0Ah
0x1803e9e02  mov     r15d, ebp
0x1803e9e05  cmp     ebp, eax
0x1803e9e07  cmovb   r15d, eax
0x1803e9e0b  mov     rax, [r14+70h]
0x1803e9e0f  mov     ecx, [rax+4]
0x1803e9e12  mov     rsi, [rax+8]
0x1803e9e16  test    ecx, ecx
0x1803e9e18  jle     short loc_1803E9E2B
0x1803e9e1a  cmp     [rsi], rdi
0x1803e9e1d  jz      loc_1803E9F88
0x1803e9e23  dec     ecx
0x1803e9e25  add     rsi, 38h ; '8'
0x1803e9e29  jmp     short loc_1803E9E16
0x1803e9e2b  mov     rcx, [r13+70h]; this
0x1803e9e2f  mov     r8d, [rcx+4]
0x1803e9e33  mov     eax, [rcx]
0x1803e9e35  inc     r8d; int
0x1803e9e38  shr     eax, 2
0x1803e9e3b  cmp     r8d, eax
0x1803e9e3e  ja      loc_1803EA091
0x1803e9e44  mov     r10, [rsp+78h+arg_10]
0x1803e9e4c  mov     rcx, [r10+rbx]
0x1803e9e50  test    rcx, rcx
0x1803e9e53  jz      loc_1803EA084
0x1803e9e59  mov     rcx, [rcx+0E8h]
0x1803e9e60  mov     r9, [rcx+70h]
0x1803e9e64  mov     r11d, 2002h
0x1803e9e6a  mov     eax, [rcx+68h]
0x1803e9e6d  inc     eax
0x1803e9e6f  mov     [rcx+68h], eax
0x1803e9e72  cmp     eax, r11d
0x1803e9e75  jb      loc_1803EA1B8
0x1803e9e7b  mov     edx, [r9+4]
0x1803e9e7f  mov     r8, [r9+8]
0x1803e9e83  test    edx, edx
0x1803e9e85  jg      loc_1803EA03B
0x1803e9e8b  mov     ebx, [rcx+68h]
0x1803e9e8e  mov     eax, 0Ah
0x1803e9e93  cmp     ebp, eax
0x1803e9e95  cmovb   ebp, eax
0x1803e9e98  mov     rax, [rsp+78h+arg_8]
0x1803e9ea0  mov     rax, [r10+rax]
0x1803e9ea4  movzx   r15d, byte ptr [rax+247h]
0x1803e9eac  test    r15d, r15d
0x1803e9eaf  jnz     short loc_1803E9EE0
0x1803e9eb1  mov     rax, cs:qword_1815C4E28
0x1803e9eb8  xor     r9d, r9d; lpTimerFunc
0x1803e9ebb  mov     rcx, [r13+60h]; hWnd
0x1803e9ebf  mov     edx, ebx; nIDEvent
0x1803e9ec1  mov     r8d, ebp; uElapse
0x1803e9ec4  test    rax, rax
0x1803e9ec7  jz      loc_1803EA0B0
0x1803e9ecd  mov     dword ptr [rsp+78h+var_58], r9d
0x1803e9ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803e9ed7  test    rax, rax
0x1803e9eda  jz      loc_1803EA108
0x1803e9ee0  mov     rcx, [r13+70h]
0x1803e9ee4  movsxd  rax, dword ptr [rcx+4]
0x1803e9ee8  mov     r14, [rcx+8]
0x1803e9eec  imul    rsi, rax, 38h ; '8'
0x1803e9ef0  lea     rax, ?OnWMTimer@CPaintBeat@@AEAAJI@Z; CPaintBeat::OnWMTimer(uint)
0x1803e9ef7  mov     [rsi+r14], rdi
0x1803e9efb  mov     [rsi+r14+8], rax
0x1803e9f00  mov     [rsi+r14+14h], ebx
0x1803e9f05  mov     dword ptr [rsi+r14+10h], 0CEh
0x1803e9f0e  mov     [rsi+r14+18h], ebp
0x1803e9f13  mov     dword ptr [rsi+r14+24h], 1
0x1803e9f1c  mov     [rsi+r14+20h], r15d
0x1803e9f21  mov     dword ptr [rsi+r14+1Ch], 0
0x1803e9f2a  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1803e9f31  nop     dword ptr [rax+rax+00h]
0x1803e9f36  cmp     byte ptr [rax+10h], 0
0x1803e9f3a  jz      loc_1803EA050
0x1803e9f40  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1803e9f47  nop     dword ptr [rax+rax+00h]
0x1803e9f4c  movups  xmm0, xmmword ptr [rax]
0x1803e9f4f  movdqu  xmmword ptr [rsi+r14+28h], xmm0
0x1803e9f56  mov     rax, [r13+70h]
0x1803e9f5a  inc     dword ptr [rax+4]
0x1803e9f5d  test    byte ptr cs:Microsoft_IEEnableBits+2, 10h
0x1803e9f64  jnz     loc_1803EA17B
0x1803e9f6a  test    r12d, r12d
0x1803e9f6d  js      loc_1803EA108
0x1803e9f73  mov     rax, [rsp+78h+arg_18]
0x1803e9f7b  mov     [rdi+50h], rax
0x1803e9f7f  mov     byte ptr [rdi+65h], 1
0x1803e9f83  jmp     loc_1803E9C17
0x1803e9f88  cmp     dword ptr [rsi+10h], 0CEh
0x1803e9f8f  jnz     loc_1803E9E23
0x1803e9f95  cmp     [rsi+18h], r15d
0x1803e9f99  jz      short loc_1803E9F9F
0x1803e9f9b  mov     [rsi+18h], r15d
0x1803e9f9f  cmp     [rsi+20h], r12d
0x1803e9fa3  jnz     short loc_1803EA006
0x1803e9fa5  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1803e9fac  nop     dword ptr [rax+rax+00h]
0x1803e9fb1  cmp     [rax+10h], r12b
0x1803e9fb5  jz      loc_1803EA0C1
0x1803e9fbb  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1803e9fc2  nop     dword ptr [rax+rax+00h]
0x1803e9fc7  add     r14, 60h ; '`'
0x1803e9fcb  movups  xmm0, xmmword ptr [rax]
0x1803e9fce  mov     rax, cs:qword_1815C4E28
0x1803e9fd5  mov     r8d, r15d; uElapse
0x1803e9fd8  mov     edx, [rsi+14h]; nIDEvent
0x1803e9fdb  movdqu  xmmword ptr [rsi+28h], xmm0
0x1803e9fe0  mov     rcx, [r14]; hWnd
0x1803e9fe3  test    rax, rax
0x1803e9fe6  jz      loc_1803EA115
0x1803e9fec  mov     r9d, [rsi+1Ch]
0x1803e9ff0  mov     dword ptr [rsp+78h+var_58], r9d
0x1803e9ff5  xor     r9d, r9d
0x1803e9ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803e9ffd  test    rax, rax
0x1803ea000  jz      loc_1803E9E2B
0x1803ea006  test    byte ptr cs:Microsoft_IEEnableBits+2, 10h
0x1803ea00d  jz      loc_1803E9F73
0x1803ea013  mov     eax, [rsi+18h]
0x1803ea016  lea     rdx, MSHTML_FORMSTIMER_RESET
0x1803ea01d  mov     r9d, [rsi+10h]
0x1803ea021  mov     r8, [rsi]
0x1803ea024  mov     [rsp+78h+var_50], eax
0x1803ea028  mov     rax, [rsi+8]
0x1803ea02c  mov     [rsp+78h+var_58], rax
0x1803ea031  call    McTemplateU0pqpq_EventWriteTransfer
0x1803ea036  jmp     loc_1803E9F73
0x1803ea03b  cmp     eax, [r8+14h]
0x1803ea03f  jz      loc_1803E9E6A
0x1803ea045  dec     edx
0x1803ea047  add     r8, 38h ; '8'
0x1803ea04b  jmp     loc_1803E9E83
0x1803ea050  mov     rcx, [r13+60h]; hWnd
0x1803ea054  xor     edx, edx; lpdwProcessId
0x1803ea056  call    cs:__imp_GetWindowThreadProcessId
0x1803ea05d  nop     dword ptr [rax+rax+00h]
0x1803ea062  mov     ebx, eax
0x1803ea064  call    cs:__imp_GetCurrentThreadId
0x1803ea06b  nop     dword ptr [rax+rax+00h]
0x1803ea070  cmp     ebx, eax
0x1803ea072  jz      loc_1803E9F40
0x1803ea078  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1803ea07f  jmp     loc_1803E9F4F
0x1803ea084  jmp     loc_1803E9E60
0x1803ea089  mov     rax, [rax]
0x1803ea08c  jmp     loc_1803E9BE0
0x1803ea091  test    r8d, r8d
0x1803ea094  js      short loc_1803EA108
0x1803ea096  mov     edx, 38h ; '8'; unsigned __int64
0x1803ea09b  call    ?EnsureSizeWorker@CImplAry@@AEAAJ_KJ@Z; CImplAry::EnsureSizeWorker(unsigned __int64,long)
  ... truncated ...
```
