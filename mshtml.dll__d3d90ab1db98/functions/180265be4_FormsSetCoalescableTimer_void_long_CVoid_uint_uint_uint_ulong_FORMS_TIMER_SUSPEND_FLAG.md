# FormsSetCoalescableTimer(void *,long (CVoid::*)(uint),uint,uint,ulong,FORMS_TIMER_SUSPEND_FLAG)

- ea: `0x180265be4`
- end: `0x1802660d9`
- name: `?FormsSetCoalescableTimer@@YAJPEAXP8CVoid@@EAAJI@ZIIKW4FORMS_TIMER_SUSPEND_FLAG@@@Z`
- size: `1269`
- prototype: ``
- caller_count: `27`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18012bd9c`
- `0x180265374`
- `0x1802716d0`
- `0x1803076d8`
- `0x1803dd3b0`
- `0x180605bb8`
- `0x18068196c`
- `0x18078c74c`
- `0x1807aaef4`
- `0x1807eb22c`
- `0x18084ef40`
- `0x180878114`
- `0x180887b78`
- `0x1808f7880`
- `0x18098f790`
- `0x1809a7e90`
- `0x180a77d48`
- `0x180a8c35c`
- `0x180b025c4`
- `0x180d2e620`
- `0x180d2eaa0`
- `0x180d44688`
- `0x180da20c8`
- `0x180dfcb24`
- `0x180f02254`
- `0x180f04900`
- `0x1810884e8`

## callees

- `0x18006b354`
- `0x18006b3c0`
- `0x180265be4`
- `0x1807a7ab4`
- `0x181104010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180265fef`
- `msvcrt!memcpy_s` at `0x180265fef`
- `KERNEL32!GetCurrentThreadId` at `0x180265ed4`
- `KERNEL32!GetCurrentThreadId` at `0x180266017`
- `KERNEL32!GetCurrentThreadId` at `0x180265ed4`
- `KERNEL32!GetCurrentThreadId` at `0x180266017`
- `USER32!GetWindowThreadProcessId` at `0x180265ec6`
- `USER32!GetWindowThreadProcessId` at `0x180266009`
- `USER32!GetWindowThreadProcessId` at `0x180265ec6`
- `USER32!GetWindowThreadProcessId` at `0x180266009`
- `USER32!SetTimer` at `0x180265f93`
- `USER32!SetTimer` at `0x180266056`
- `USER32!SetTimer` at `0x180265f93`
- `USER32!SetTimer` at `0x180266056`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180265db5`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180265dcb`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180265e26`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180265e3c`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180265ee8`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180266027`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180265db5`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180265dcb`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180265e26`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180265e3c`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180265ee8`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180266027`

## pseudocode

```c
__int64 __fastcall FormsSetCoalescableTimer(__int64 a1, __int64 a2, int a3, unsigned int a4, int a5, int a6)
{
  __int64 v6; // r14
  __int64 v7; // r15
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rax
  UINT v11; // r12d
  int v12; // ecx
  __int64 v13; // rdi
  __int64 v14; // rbx
  unsigned int v15; // ecx
  unsigned int v16; // ebp
  unsigned int v17; // edi
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // r9
  unsigned int v21; // eax
  int v22; // edx
  __int64 v23; // r8
  UINT_PTR v24; // rbx
  int v25; // r9d
  HWND v26; // rcx
  UINT_PTR v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rbp
  __int64 v30; // rsi
  int v31; // ebx
  __int64 v32; // r15
  int v33; // ecx
  GUID v34; // xmm0
  HWND *v36; // rsi
  __int128 v37; // xmm0
  __int64 (__fastcall *v38)(HWND, UINT_PTR, _QWORD, _QWORD, _DWORD); // rax
  UINT_PTR v39; // rdx
  HWND v40; // rcx
  DWORD v42; // ebx
  unsigned int v43; // esi
  unsigned __int64 v44; // rcx
  unsigned int v45; // edx
  const void *v46; // r15
  rsize_t v47; // r14
  __int64 v48; // rax
  void *v49; // rax
  DWORD WindowThreadProcessId; // ebx
  int v51; // [rsp+30h] [rbp-68h]
  __int64 v52; // [rsp+38h] [rbp-60h]
  __int64 v53; // [rsp+40h] [rbp-58h]

  v6 = 0;
  v7 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v53 = v7;
  v8 = *(_QWORD *)(v7 + 16);
  if ( v8 )
    v6 = *(_QWORD *)(v8 + 232);
  v52 = v6;
  if ( !*(_QWORD *)(v6 + 96) )
    return (unsigned int)-2147467259;
  v9 = 0;
  if ( v8 )
    v9 = *(_QWORD *)(v8 + 232);
  v10 = *(_QWORD *)(v9 + 112);
  v11 = 10;
  if ( a4 >= 0xA )
    v11 = a4;
  v12 = *(_DWORD *)(v10 + 4);
  v13 = *(_QWORD *)(v10 + 8);
  while ( v12 > 0 )
  {
    if ( *(_QWORD *)v13 == a1 && *(_DWORD *)(v13 + 16) == a3 )
    {
      if ( *(_DWORD *)(v13 + 24) != v11 )
        *(_DWORD *)(v13 + 24) = v11;
      if ( *(_DWORD *)(v13 + 32) )
        goto LABEL_41;
      if ( *((_BYTE *)GlobalThreadState() + 16) )
      {
        v36 = (HWND *)(v9 + 96);
        v37 = *(_OWORD *)GlobalThreadState();
      }
      else
      {
        v36 = (HWND *)(v9 + 96);
        WindowThreadProcessId = GetWindowThreadProcessId(*(HWND *)(v9 + 96), 0);
        v37 = WindowThreadProcessId == GetCurrentThreadId() ? *(_OWORD *)GlobalThreadState() : *(_OWORD *)&GUID_NULL;
      }
      v38 = (__int64 (__fastcall *)(HWND, UINT_PTR, _QWORD, _QWORD, _DWORD))qword_1815C4E28;
      v39 = *(unsigned int *)(v13 + 20);
      *(_OWORD *)(v13 + 40) = v37;
      v40 = *v36;
      if ( v38 ? v38(v40, v39, v11, 0, *(_DWORD *)(v13 + 28)) : SetTimer(v40, v39, v11, 0) )
      {
LABEL_41:
        if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
          McTemplateU0pqpq_EventWriteTransfer(
            v12,
            (unsigned int)MSHTML_FORMSTIMER_RESET,
            *(_QWORD *)v13,
            *(_DWORD *)(v13 + 16),
            *(_QWORD *)(v13 + 8),
            *(_DWORD *)(v13 + 24));
        return 0;
      }
      break;
    }
    --v12;
    v13 += 56;
  }
  v14 = *(_QWORD *)(v6 + 112);
  v15 = *(_DWORD *)(v14 + 4) + 1;
  v16 = *(_DWORD *)v14 >> 2;
  if ( v15 > v16 )
  {
    if ( (v15 & 0x80000000) != 0 )
      return (unsigned int)-2147024809;
    v43 = 4;
    if ( v15 >= 4 )
    {
      if ( v15 <= 4 )
        goto LABEL_54;
      v43 = v16 + (*(_DWORD *)v14 >> 3);
      if ( v43 < v16 )
      {
        v17 = -2147024362;
        goto LABEL_63;
      }
      if ( v15 > v43 )
LABEL_54:
        v43 = *(_DWORD *)(v14 + 4) + 1;
    }
    v44 = 56LL * v43;
    v45 = 56 * v43;
    if ( v44 > 0xFFFFFFFF )
      v45 = -1;
    v17 = v44 > 0xFFFFFFFF ? 0x80070216 : 0;
    if ( v44 <= 0xFFFFFFFF )
    {
      v46 = *(const void **)(v14 + 8);
      v47 = v45;
      if ( (*(_BYTE *)v14 & 2) != 0 )
      {
        v49 = (void *)MemoryProtection::HeapAlloc<1>(g_hProcessHeap, v45);
        *(_QWORD *)(v14 + 8) = v49;
        if ( !v49 )
        {
          *(_QWORD *)(v14 + 8) = v46;
LABEL_77:
          v17 = -2147024882;
          goto LABEL_62;
        }
        memcpy_s(v49, v47, v46, 56 * v16);
      }
      else
      {
        v48 = MemoryProtection::HeapReAlloc<1>(v44, *(_QWORD *)(v14 + 8), v45);
        if ( !v48 && v47 )
          goto LABEL_77;
        *(_QWORD *)(v14 + 8) = v48;
        v17 = 0;
      }
      *(_DWORD *)v14 &= 1u;
      *(_DWORD *)v14 |= 4 * v43;
LABEL_62:
      v6 = v52;
      v7 = v53;
    }
LABEL_63:
    if ( v17 )
      return v17;
    goto LABEL_14;
  }
  v17 = 0;
LABEL_14:
  v51 = 0;
  v18 = *(_QWORD *)(v7 + 16);
  if ( v18 )
    v19 = *(_QWORD *)(v18 + 232);
  else
    v19 = 0;
  v20 = *(_QWORD *)(v19 + 112);
LABEL_17:
  v21 = *(_DWORD *)(v19 + 104) + 1;
  *(_DWORD *)(v19 + 104) = v21;
  if ( v21 < 0x2002 )
  {
    *(_DWORD *)(v19 + 104) = 8194;
    v21 = 8194;
  }
  v22 = *(_DWORD *)(v20 + 4);
  v23 = *(_QWORD *)(v20 + 8);
  while ( v22 > 0 )
  {
    if ( v21 == *(_DWORD *)(v23 + 20) )
      goto LABEL_17;
    --v22;
    v23 += 56;
  }
  v24 = *(unsigned int *)(v19 + 104);
  if ( !a6
    || (v25 = *(unsigned __int8 *)(*(_QWORD *)(v53 + 16) + 583LL), v51 = v25, !*(_BYTE *)(*(_QWORD *)(v53 + 16) + 583LL)) )
  {
    v26 = *(HWND *)(v6 + 96);
    if ( qword_1815C4E28 )
      v27 = ((__int64 (__fastcall *)(HWND, UINT_PTR, _QWORD, _QWORD, int))qword_1815C4E28)(v26, v24, v11, 0, a5);
    else
      v27 = SetTimer(v26, v24, v11, 0);
    if ( !v27 )
      return (unsigned int)-2147467259;
    v25 = v51;
  }
  v28 = *(_QWORD *)(v6 + 112);
  v29 = *(_QWORD *)(v28 + 8);
  v30 = 56LL * *(int *)(v28 + 4);
  *(_DWORD *)(v30 + v29 + 20) = v24;
  v31 = a3;
  *(_DWORD *)(v30 + v29 + 16) = a3;
  *(_QWORD *)(v30 + v29) = a1;
  *(_QWORD *)(v30 + v29 + 8) = a2;
  *(_DWORD *)(v30 + v29 + 24) = v11;
  *(_DWORD *)(v30 + v29 + 36) = a6;
  *(_DWORD *)(v30 + v29 + 32) = v25;
  *(_DWORD *)(v30 + v29 + 28) = a5;
  if ( *((_BYTE *)GlobalThreadState() + 16) )
  {
    v32 = v52;
    v34 = *(GUID *)GlobalThreadState();
  }
  else
  {
    v32 = v52;
    v42 = GetWindowThreadProcessId(*(HWND *)(v52 + 96), 0);
    if ( v42 == GetCurrentThreadId() )
      v34 = *(GUID *)GlobalThreadState();
    else
      v34 = GUID_NULL;
    v31 = a3;
  }
  *(GUID *)(v30 + v29 + 40) = v34;
  ++*(_DWORD *)(*(_QWORD *)(v32 + 112) + 4LL);
  if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
    McTemplateU0pqpq_EventWriteTransfer(v33, (unsigned int)MSHTML_FORMSTIMER_SET, a1, v31, a2, v11);
  return v17;
}

```

## disassembly

```asm
0x180265be4  mov     rax, rsp
0x180265be7  mov     [rax+20h], r9d
0x180265beb  mov     [rax+18h], r8d
0x180265bef  mov     [rax+10h], rdx
0x180265bf3  mov     [rax+8], rcx
0x180265bf7  push    rbx
0x180265bf8  push    rbp
0x180265bf9  push    rsi
0x180265bfa  push    rdi
0x180265bfb  push    r12
0x180265bfd  push    r13
0x180265bff  push    r14
0x180265c01  push    r15
0x180265c03  sub     rsp, 58h
0x180265c07  mov     rax, gs:58h
0x180265c10  xor     r13d, r13d
0x180265c13  mov     ecx, cs:_tls_index
0x180265c19  mov     r14d, r13d
0x180265c1c  mov     edx, 10h
0x180265c21  mov     r15, [rax+rcx*8]
0x180265c25  mov     [rsp+98h+var_58], r15
0x180265c2a  mov     rax, [r15+rdx]
0x180265c2e  test    rax, rax
0x180265c31  jz      short loc_180265C3A
0x180265c33  mov     r14, [rax+0E8h]
0x180265c3a  mov     [rsp+98h+var_60], r14
0x180265c3f  cmp     [r14+60h], r13
0x180265c43  jz      loc_180265E9C
0x180265c49  mov     rbx, r13
0x180265c4c  test    rax, rax
0x180265c4f  jz      short loc_180265C58
0x180265c51  mov     rbx, [rax+0E8h]
0x180265c58  mov     rax, [rbx+70h]
0x180265c5c  mov     r12d, 0Ah
0x180265c62  cmp     [rsp+98h+uElapse], r12d
0x180265c6a  mov     edx, [rsp+98h+arg_10]
0x180265c71  cmovnb  r12d, [rsp+98h+uElapse]
0x180265c7a  mov     ecx, [rax+4]
0x180265c7d  mov     rdi, [rax+8]
0x180265c81  mov     rax, [rsp+98h+arg_0]
0x180265c89  test    ecx, ecx
0x180265c8b  jle     short loc_180265C9E
0x180265c8d  cmp     [rdi], rax
0x180265c90  jz      loc_180265E0D
0x180265c96  dec     ecx
0x180265c98  add     rdi, 38h ; '8'
0x180265c9c  jmp     short loc_180265C89
0x180265c9e  mov     rbx, [r14+70h]
0x180265ca2  mov     ecx, [rbx+4]
0x180265ca5  mov     ebp, [rbx]
0x180265ca7  inc     ecx
0x180265ca9  shr     ebp, 2
0x180265cac  cmp     ecx, ebp
0x180265cae  ja      loc_180265F0B
0x180265cb4  mov     edi, r13d
0x180265cb7  mov     r11d, 10h
0x180265cbd  mov     [rsp+98h+var_68], r13d
0x180265cc2  mov     rcx, [r15+r11]
0x180265cc6  test    rcx, rcx
0x180265cc9  jz      loc_180265F03
0x180265ccf  mov     rcx, [rcx+0E8h]
0x180265cd6  mov     r9, [rcx+70h]
0x180265cda  mov     r10d, 2002h
0x180265ce0  mov     eax, [rcx+68h]
0x180265ce3  inc     eax
0x180265ce5  mov     [rcx+68h], eax
0x180265ce8  cmp     eax, r10d
0x180265ceb  jb      loc_1802660C1
0x180265cf1  mov     edx, [r9+4]
0x180265cf5  mov     r8, [r9+8]
0x180265cf9  test    edx, edx
0x180265cfb  jg      loc_180265EA6
0x180265d01  mov     r15d, [rsp+98h+arg_28]
0x180265d09  mov     ebx, [rcx+68h]
0x180265d0c  mov     r13d, [rsp+98h+arg_20]
0x180265d14  test    r15d, r15d
0x180265d17  jz      short loc_180265D34
0x180265d19  mov     rax, [rsp+98h+var_58]
0x180265d1e  mov     rax, [rax+r11]
0x180265d22  movzx   r9d, byte ptr [rax+247h]
0x180265d2a  mov     [rsp+98h+var_68], r9d
0x180265d2f  test    r9d, r9d
0x180265d32  jnz     short loc_180265D69
0x180265d34  mov     rax, cs:qword_1815C4E28
0x180265d3b  xor     r9d, r9d; lpTimerFunc
0x180265d3e  mov     rcx, [r14+60h]; hWnd
0x180265d42  mov     rdx, rbx; nIDEvent
0x180265d45  mov     r8d, r12d; uElapse
0x180265d48  test    rax, rax
0x180265d4b  jz      loc_180265F93
0x180265d51  mov     dword ptr [rsp+98h+var_78], r13d
0x180265d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180265d5b  test    rax, rax
0x180265d5e  jz      loc_180265E9C
0x180265d64  mov     r9d, [rsp+98h+var_68]
0x180265d69  mov     rcx, [r14+70h]
0x180265d6d  mov     r14, [rsp+98h+arg_8]
0x180265d75  movsxd  rax, dword ptr [rcx+4]
0x180265d79  mov     rbp, [rcx+8]
0x180265d7d  imul    rsi, rax, 38h ; '8'
0x180265d81  mov     rax, [rsp+98h+arg_0]
0x180265d89  mov     [rsi+rbp+14h], ebx
0x180265d8d  mov     ebx, [rsp+98h+arg_10]
0x180265d94  mov     [rsi+rbp+10h], ebx
0x180265d98  mov     [rsi+rbp], rax
0x180265d9c  mov     [rsi+rbp+8], r14
0x180265da1  mov     [rsi+rbp+18h], r12d
0x180265da6  mov     [rsi+rbp+24h], r15d
0x180265dab  mov     [rsi+rbp+20h], r9d
0x180265db0  mov     [rsi+rbp+1Ch], r13d
0x180265db5  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180265dbc  nop     dword ptr [rax+rax+00h]
0x180265dc1  cmp     byte ptr [rax+10h], 0
0x180265dc5  jz      loc_180265EBB
0x180265dcb  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180265dd2  nop     dword ptr [rax+rax+00h]
0x180265dd7  mov     r15, [rsp+98h+var_60]
0x180265ddc  movups  xmm0, xmmword ptr [rax]
0x180265ddf  movdqu  xmmword ptr [rsi+rbp+28h], xmm0
0x180265de5  mov     rax, [r15+70h]
0x180265de9  inc     dword ptr [rax+4]
0x180265dec  test    byte ptr cs:Microsoft_IEEnableBits+2, 10h
0x180265df3  jnz     loc_180266067
0x180265df9  mov     eax, edi
0x180265dfb  add     rsp, 58h
0x180265dff  pop     r15
0x180265e01  pop     r14
0x180265e03  pop     r13
0x180265e05  pop     r12
0x180265e07  pop     rdi
0x180265e08  pop     rsi
0x180265e09  pop     rbp
0x180265e0a  pop     rbx
0x180265e0b  retn
0x180265e0d  cmp     [rdi+10h], edx
0x180265e10  jnz     loc_180265C96
0x180265e16  cmp     [rdi+18h], r12d
0x180265e1a  jz      short loc_180265E20
0x180265e1c  mov     [rdi+18h], r12d
0x180265e20  cmp     [rdi+20h], r13d
0x180265e24  jnz     short loc_180265E87
0x180265e26  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180265e2d  nop     dword ptr [rax+rax+00h]
0x180265e32  cmp     [rax+10h], r13b
0x180265e36  jz      loc_180266000
0x180265e3c  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180265e43  nop     dword ptr [rax+rax+00h]
0x180265e48  lea     rsi, [rbx+60h]
0x180265e4c  movups  xmm0, xmmword ptr [rax]
0x180265e4f  mov     rax, cs:qword_1815C4E28
0x180265e56  xor     r9d, r9d; lpTimerFunc
0x180265e59  mov     edx, [rdi+14h]; nIDEvent
0x180265e5c  movdqu  xmmword ptr [rdi+28h], xmm0
0x180265e61  mov     rcx, [rsi]; hWnd
0x180265e64  test    rax, rax
0x180265e67  jz      loc_180266053
0x180265e6d  mov     r8d, [rdi+1Ch]
0x180265e71  mov     dword ptr [rsp+98h+var_78], r8d
0x180265e76  mov     r8d, r12d
0x180265e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180265e7e  test    rax, rax
0x180265e81  jz      loc_180265C9E
0x180265e87  test    byte ptr cs:Microsoft_IEEnableBits+2, 10h
0x180265e8e  jnz     loc_180266099
0x180265e94  mov     edi, r13d
0x180265e97  jmp     loc_180265DF9
0x180265e9c  mov     edi, 80004005h
0x180265ea1  jmp     loc_180265DF9
0x180265ea6  cmp     eax, [r8+14h]
0x180265eaa  jz      loc_180265CE0
0x180265eb0  dec     edx
0x180265eb2  add     r8, 38h ; '8'
0x180265eb6  jmp     loc_180265CF9
0x180265ebb  mov     r15, [rsp+98h+var_60]
0x180265ec0  xor     edx, edx; lpdwProcessId
0x180265ec2  mov     rcx, [r15+60h]; hWnd
0x180265ec6  call    cs:__imp_GetWindowThreadProcessId
0x180265ecd  nop     dword ptr [rax+rax+00h]
0x180265ed2  mov     ebx, eax
0x180265ed4  call    cs:__imp_GetCurrentThreadId
0x180265edb  nop     dword ptr [rax+rax+00h]
0x180265ee0  cmp     ebx, eax
0x180265ee2  jnz     loc_1802660CD
0x180265ee8  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180265eef  nop     dword ptr [rax+rax+00h]
0x180265ef4  movups  xmm0, xmmword ptr [rax]
0x180265ef7  mov     ebx, [rsp+98h+arg_10]
0x180265efe  jmp     loc_180265DDF
0x180265f03  mov     rcx, r13
0x180265f06  jmp     loc_180265CD6
0x180265f0b  test    ecx, ecx
0x180265f0d  js      loc_180266049
0x180265f13  mov     esi, 4
0x180265f18  cmp     ecx, esi
0x180265f1a  jb      short loc_180265F24
0x180265f1c  ja      loc_180265FA4
0x180265f22  mov     esi, ecx
0x180265f24  mov     eax, esi
0x180265f26  mov     r8d, 0FFFFFFFFh
0x180265f2c  imul    rcx, rax, 38h ; '8'
0x180265f30  mov     edx, ecx
0x180265f32  cmp     rcx, r8
0x180265f35  ja      short loc_180265F8E
0x180265f37  cmp     r8, rcx
0x180265f3a  mov     edi, 80070216h
0x180265f3f  sbb     eax, eax
0x180265f41  and     edi, eax
0x180265f43  cmp     rcx, r8
0x180265f46  ja      short loc_180265F81
0x180265f48  test    byte ptr [rbx], 2
0x180265f4b  mov     r15, [rbx+8]
0x180265f4f  mov     r14d, edx
0x180265f52  jnz     short loc_180265FCA
0x180265f54  mov     r8d, r14d
0x180265f57  mov     rdx, r15
0x180265f5a  call    ??$HeapReAlloc@$00@MemoryProtection@@YAPEAXPEAX0_K@Z; MemoryProtection::HeapReAlloc<1>(void *,void *,unsigned __int64)
0x180265f5f  test    rax, rax
0x180265f62  jz      short loc_180265FBC
0x180265f64  mov     [rbx+8], rax
0x180265f68  mov     edi, r13d
0x180265f6b  and     dword ptr [rbx], 1
0x180265f6e  lea     eax, ds:0[rsi*4]
0x180265f75  or      [rbx], eax
0x180265f77  mov     r14, [rsp+98h+var_60]
0x180265f7c  mov     r15, [rsp+98h+var_58]
0x180265f81  test    edi, edi
0x180265f83  jz      loc_180265CB7
0x180265f89  jmp     loc_180265DF9
0x180265f8e  mov     edx, r8d
0x180265f91  jmp     short loc_180265F37
0x180265f93  call    cs:__imp_SetTimer
0x180265f9a  nop     dword ptr [rax+rax+00h]
0x180265f9f  jmp     loc_180265D5B
0x180265fa4  mov     esi, [rbx]
0x180265fa6  shr     esi, 3
0x180265fa9  add     esi, ebp
0x180265fab  cmp     esi, ebp
0x180265fad  jb      short loc_180265FC3
0x180265faf  cmp     ecx, esi
0x180265fb1  jbe     loc_180265F24
0x180265fb7  jmp     loc_180265F22
0x180265fbc  test    r14, r14
0x180265fbf  jz      short loc_180265F64
0x180265fc1  jmp     short loc_18026603F
0x180265fc3  mov     edi, 80070216h
0x180265fc8  jmp     short loc_180265F81
0x180265fca  mov     rcx, cs:g_hProcessHeap
0x180265fd1  mov     rdx, r14
0x180265fd4  call    ??$HeapAlloc@$00@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<1>(void *,unsigned __int64)
0x180265fd9  mov     [rbx+8], rax
0x180265fdd  mov     rcx, rax; Destination
0x180265fe0  test    rax, rax
0x180265fe3  jz      short loc_18026603B
0x180265fe5  imul    r9d, ebp, 38h ; '8'; SourceSize
0x180265fe9  mov     r8, r15; Source
0x180265fec  mov     rdx, r14; DestinationSize
0x180265fef  call    cs:__imp_memcpy_s
0x180265ff6  nop     dword ptr [rax+rax+00h]
0x180265ffb  jmp     loc_180265F6B
0x180266000  lea     rsi, [rbx+60h]
0x180266004  xor     edx, edx; lpdwProcessId
0x180266006  mov     rcx, [rsi]; hWnd
0x180266009  call    cs:__imp_GetWindowThreadProcessId
0x180266010  nop     dword ptr [rax+rax+00h]
0x180266015  mov     ebx, eax
0x180266017  call    cs:__imp_GetCurrentThreadId
0x18026601e  nop     dword ptr [rax+rax+00h]
0x180266023  cmp     ebx, eax
0x180266025  jnz     short loc_18026608D
0x180266027  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18026602e  nop     dword ptr [rax+rax+00h]
0x180266033  movups  xmm0, xmmword ptr [rax]
0x180266036  jmp     loc_180265E4F
0x18026603b  mov     [rbx+8], r15
0x18026603f  mov     edi, 8007000Eh
0x180266044  jmp     loc_180265F77
0x180266049  mov     edi, 80070057h
0x18026604e  jmp     loc_180265DF9
0x180266053  mov     r8d, r12d; uElapse
0x180266056  call    cs:__imp_SetTimer
0x18026605d  nop     dword ptr [rax+rax+00h]
0x180266062  jmp     loc_180265E7E
0x180266067  mov     r8, [rsp+98h+arg_0]
0x18026606f  lea     rdx, MSHTML_FORMSTIMER_SET
0x180266076  mov     [rsp+98h+var_70], r12d
0x18026607b  mov     r9d, ebx
0x18026607e  mov     [rsp+98h+var_78], r14
0x180266083  call    McTemplateU0pqpq_EventWriteTransfer
0x180266088  jmp     loc_180265DF9
0x18026608d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180266094  jmp     loc_180265E4F
0x180266099  mov     eax, [rdi+18h]
0x18026609c  lea     rdx, MSHTML_FORMSTIMER_RESET
0x1802660a3  mov     r9d, [rdi+10h]
0x1802660a7  mov     r8, [rdi]
0x1802660aa  mov     [rsp+98h+var_70], eax
0x1802660ae  mov     rax, [rdi+8]
0x1802660b2  mov     [rsp+98h+var_78], rax
0x1802660b7  call    McTemplateU0pqpq_EventWriteTransfer
0x1802660bc  jmp     loc_180265E94
  ... truncated ...
```
