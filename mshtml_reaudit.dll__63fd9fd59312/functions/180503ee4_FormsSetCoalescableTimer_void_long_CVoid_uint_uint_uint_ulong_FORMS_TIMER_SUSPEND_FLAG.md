# FormsSetCoalescableTimer(void *,long (CVoid::*)(uint),uint,uint,ulong,FORMS_TIMER_SUSPEND_FLAG)

- ea: `0x180503ee4`
- end: `0x180504386`
- name: `?FormsSetCoalescableTimer@@YAJPEAXP8CVoid@@EAAJI@ZIIKW4FORMS_TIMER_SUSPEND_FLAG@@@Z`
- size: `1186`
- prototype: ``
- caller_count: `26`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800d55a4`
- `0x1801216f0`
- `0x180375c80`
- `0x1805039f0`
- `0x180503e80`
- `0x180609874`
- `0x180682e68`
- `0x180781054`
- `0x1807a1788`
- `0x1807df93c`
- `0x18084bcf0`
- `0x180871b4c`
- `0x180880800`
- `0x1808eb680`
- `0x1809812a0`
- `0x180a63948`
- `0x180a77b84`
- `0x180aec4b0`
- `0x180d0c7c0`
- `0x180d0cc30`
- `0x180d225d0`
- `0x180d7f804`
- `0x180dd92c4`
- `0x180edad34`
- `0x180edd368`
- `0x181058954`

## callees

- `0x1801cd614`
- `0x1801cd678`
- `0x180503ee4`
- `0x18079b8d4`
- `0x1810d1010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1805042ba`
- `msvcrt!memcpy_s` at `0x1805042ba`
- `KERNEL32!GetCurrentThreadId` at `0x1805041b5`
- `KERNEL32!GetCurrentThreadId` at `0x1805042d6`
- `KERNEL32!GetCurrentThreadId` at `0x1805041b5`
- `KERNEL32!GetCurrentThreadId` at `0x1805042d6`
- `USER32!GetWindowThreadProcessId` at `0x1805041ad`
- `USER32!GetWindowThreadProcessId` at `0x1805042ce`
- `USER32!GetWindowThreadProcessId` at `0x1805041ad`
- `USER32!GetWindowThreadProcessId` at `0x1805042ce`
- `USER32!SetTimer` at `0x180504264`
- `USER32!SetTimer` at `0x180504309`
- `USER32!SetTimer` at `0x180504264`
- `USER32!SetTimer` at `0x180504309`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1805040b5`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1805040c5`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180504119`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180504129`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1805041c3`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1805042e0`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1805040b5`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1805040c5`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180504119`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180504129`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1805041c3`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1805042e0`

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
      v38 = (__int64 (__fastcall *)(HWND, UINT_PTR, _QWORD, _QWORD, _DWORD))qword_181591D28;
      v39 = *(unsigned int *)(v13 + 20);
      *(_OWORD *)(v13 + 40) = v37;
      v40 = *v36;
      if ( v38 ? v38(v40, v39, v11, 0, *(_DWORD *)(v13 + 28)) : SetTimer(v40, v39, v11, 0) )
      {
LABEL_41:
        if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
          McTemplateU0pqpq_EventWriteTransfer(
            v12,
            (unsigned int)&MSHTML_FORMSTIMER_RESET,
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
    if ( qword_181591D28 )
      v27 = ((__int64 (__fastcall *)(HWND, UINT_PTR, _QWORD, _QWORD, int))qword_181591D28)(v26, v24, v11, 0, a5);
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
    McTemplateU0pqpq_EventWriteTransfer(v33, (unsigned int)&MSHTML_FORMSTIMER_SET, a1, v31, a2, v11);
  return v17;
}

```

## disassembly

```asm
0x180503ee4  mov     rax, rsp
0x180503ee7  mov     [rax+20h], r9d
0x180503eeb  mov     [rax+18h], r8d
0x180503eef  mov     [rax+10h], rdx
0x180503ef3  mov     [rax+8], rcx
0x180503ef7  push    rbx
0x180503ef8  push    rbp
0x180503ef9  push    rsi
0x180503efa  push    rdi
0x180503efb  push    r12
0x180503efd  push    r13
0x180503eff  push    r14
0x180503f01  push    r15
0x180503f03  sub     rsp, 58h
0x180503f07  mov     rax, gs:58h
0x180503f10  xor     r13d, r13d
0x180503f13  mov     ecx, cs:_tls_index
0x180503f19  mov     r14d, r13d
0x180503f1c  mov     edx, 10h
0x180503f21  mov     r15, [rax+rcx*8]
0x180503f25  mov     [rsp+98h+var_58], r15
0x180503f2a  mov     rax, [r15+rdx]
0x180503f2e  test    rax, rax
0x180503f31  jz      short loc_180503F3A
0x180503f33  mov     r14, [rax+0E8h]
0x180503f3a  mov     [rsp+98h+var_60], r14
0x180503f3f  cmp     [r14+60h], r13
0x180503f43  jz      loc_180504183
0x180503f49  mov     rbx, r13
0x180503f4c  test    rax, rax
0x180503f4f  jz      short loc_180503F58
0x180503f51  mov     rbx, [rax+0E8h]
0x180503f58  mov     rax, [rbx+70h]
0x180503f5c  mov     r12d, 0Ah
0x180503f62  cmp     [rsp+98h+uElapse], r12d
0x180503f6a  mov     edx, [rsp+98h+arg_10]
0x180503f71  cmovnb  r12d, [rsp+98h+uElapse]
0x180503f7a  mov     ecx, [rax+4]
0x180503f7d  mov     rdi, [rax+8]
0x180503f81  mov     rax, [rsp+98h+arg_0]
0x180503f89  test    ecx, ecx
0x180503f8b  jle     short loc_180503F9E
0x180503f8d  cmp     [rdi], rax
0x180503f90  jz      loc_180504100
0x180503f96  dec     ecx
0x180503f98  add     rdi, 38h ; '8'
0x180503f9c  jmp     short loc_180503F89
0x180503f9e  mov     rbx, [r14+70h]
0x180503fa2  mov     ecx, [rbx+4]
0x180503fa5  mov     ebp, [rbx]
0x180503fa7  inc     ecx
0x180503fa9  shr     ebp, 2
0x180503fac  cmp     ecx, ebp
0x180503fae  ja      loc_1805041E0
0x180503fb4  mov     edi, r13d
0x180503fb7  mov     r11d, 10h
0x180503fbd  mov     [rsp+98h+var_68], r13d
0x180503fc2  mov     rcx, [r15+r11]
0x180503fc6  test    rcx, rcx
0x180503fc9  jz      loc_1805041D8
0x180503fcf  mov     rcx, [rcx+0E8h]
0x180503fd6  mov     r9, [rcx+70h]
0x180503fda  mov     r10d, 2002h
0x180503fe0  mov     eax, [rcx+68h]
0x180503fe3  inc     eax
0x180503fe5  mov     [rcx+68h], eax
0x180503fe8  cmp     eax, r10d
0x180503feb  jb      loc_18050436E
0x180503ff1  mov     edx, [r9+4]
0x180503ff5  mov     r8, [r9+8]
0x180503ff9  test    edx, edx
0x180503ffb  jg      loc_18050418D
0x180504001  mov     r15d, [rsp+98h+arg_28]
0x180504009  mov     ebx, [rcx+68h]
0x18050400c  mov     r13d, [rsp+98h+arg_20]
0x180504014  test    r15d, r15d
0x180504017  jz      short loc_180504034
0x180504019  mov     rax, [rsp+98h+var_58]
0x18050401e  mov     rax, [rax+r11]
0x180504022  movzx   r9d, byte ptr [rax+247h]
0x18050402a  mov     [rsp+98h+var_68], r9d
0x18050402f  test    r9d, r9d
0x180504032  jnz     short loc_180504069
0x180504034  mov     rax, cs:qword_181591D28
0x18050403b  xor     r9d, r9d; lpTimerFunc
0x18050403e  mov     rcx, [r14+60h]; hWnd
0x180504042  mov     rdx, rbx; nIDEvent
0x180504045  mov     r8d, r12d; uElapse
0x180504048  test    rax, rax
0x18050404b  jz      loc_180504264
0x180504051  mov     dword ptr [rsp+98h+var_78], r13d
0x180504056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18050405b  test    rax, rax
0x18050405e  jz      loc_180504183
0x180504064  mov     r9d, [rsp+98h+var_68]
0x180504069  mov     rcx, [r14+70h]
0x18050406d  mov     r14, [rsp+98h+arg_8]
0x180504075  movsxd  rax, dword ptr [rcx+4]
0x180504079  mov     rbp, [rcx+8]
0x18050407d  imul    rsi, rax, 38h ; '8'
0x180504081  mov     rax, [rsp+98h+arg_0]
0x180504089  mov     [rsi+rbp+14h], ebx
0x18050408d  mov     ebx, [rsp+98h+arg_10]
0x180504094  mov     [rsi+rbp+10h], ebx
0x180504098  mov     [rsi+rbp], rax
0x18050409c  mov     [rsi+rbp+8], r14
0x1805040a1  mov     [rsi+rbp+18h], r12d
0x1805040a6  mov     [rsi+rbp+24h], r15d
0x1805040ab  mov     [rsi+rbp+20h], r9d
0x1805040b0  mov     [rsi+rbp+1Ch], r13d
0x1805040b5  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1805040bb  cmp     byte ptr [rax+10h], 0
0x1805040bf  jz      loc_1805041A2
0x1805040c5  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1805040cb  mov     r15, [rsp+98h+var_60]
0x1805040d0  movups  xmm0, xmmword ptr [rax]
0x1805040d3  movdqu  xmmword ptr [rsi+rbp+28h], xmm0
0x1805040d9  mov     rax, [r15+70h]
0x1805040dd  inc     dword ptr [rax+4]
0x1805040e0  test    byte ptr cs:Microsoft_IEEnableBits+2, 10h
0x1805040e7  jnz     loc_180504314
0x1805040ed  mov     eax, edi
0x1805040ef  add     rsp, 58h
0x1805040f3  pop     r15
0x1805040f5  pop     r14
0x1805040f7  pop     r13
0x1805040f9  pop     r12
0x1805040fb  pop     rdi
0x1805040fc  pop     rsi
0x1805040fd  pop     rbp
0x1805040fe  pop     rbx
0x1805040ff  retn
0x180504100  cmp     [rdi+10h], edx
0x180504103  jnz     loc_180503F96
0x180504109  cmp     [rdi+18h], r12d
0x18050410d  jz      short loc_180504113
0x18050410f  mov     [rdi+18h], r12d
0x180504113  cmp     [rdi+20h], r13d
0x180504117  jnz     short loc_18050416E
0x180504119  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18050411f  cmp     [rax+10h], r13b
0x180504123  jz      loc_1805042C5
0x180504129  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18050412f  lea     rsi, [rbx+60h]
0x180504133  movups  xmm0, xmmword ptr [rax]
0x180504136  mov     rax, cs:qword_181591D28
0x18050413d  xor     r9d, r9d; lpTimerFunc
0x180504140  mov     edx, [rdi+14h]; nIDEvent
0x180504143  movdqu  xmmword ptr [rdi+28h], xmm0
0x180504148  mov     rcx, [rsi]; hWnd
0x18050414b  test    rax, rax
0x18050414e  jz      loc_180504306
0x180504154  mov     r8d, [rdi+1Ch]
0x180504158  mov     dword ptr [rsp+98h+var_78], r8d
0x18050415d  mov     r8d, r12d
0x180504160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180504165  test    rax, rax
0x180504168  jz      loc_180503F9E
0x18050416e  test    byte ptr cs:Microsoft_IEEnableBits+2, 10h
0x180504175  jnz     loc_180504346
0x18050417b  mov     edi, r13d
0x18050417e  jmp     loc_1805040ED
0x180504183  mov     edi, 80004005h
0x180504188  jmp     loc_1805040ED
0x18050418d  cmp     eax, [r8+14h]
0x180504191  jz      loc_180503FE0
0x180504197  dec     edx
0x180504199  add     r8, 38h ; '8'
0x18050419d  jmp     loc_180503FF9
0x1805041a2  mov     r15, [rsp+98h+var_60]
0x1805041a7  xor     edx, edx; lpdwProcessId
0x1805041a9  mov     rcx, [r15+60h]; hWnd
0x1805041ad  call    cs:__imp_GetWindowThreadProcessId
0x1805041b3  mov     ebx, eax
0x1805041b5  call    cs:__imp_GetCurrentThreadId
0x1805041bb  cmp     ebx, eax
0x1805041bd  jnz     loc_18050437A
0x1805041c3  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1805041c9  movups  xmm0, xmmword ptr [rax]
0x1805041cc  mov     ebx, [rsp+98h+arg_10]
0x1805041d3  jmp     loc_1805040D3
0x1805041d8  mov     rcx, r13
0x1805041db  jmp     loc_180503FD6
0x1805041e0  test    ecx, ecx
0x1805041e2  js      loc_1805042FC
0x1805041e8  mov     esi, 4
0x1805041ed  cmp     ecx, esi
0x1805041ef  jb      short loc_1805041F5
0x1805041f1  ja      short loc_18050426F
0x1805041f3  mov     esi, ecx
0x1805041f5  mov     eax, esi
0x1805041f7  mov     r8d, 0FFFFFFFFh
0x1805041fd  imul    rcx, rax, 38h ; '8'
0x180504201  mov     edx, ecx
0x180504203  cmp     rcx, r8
0x180504206  ja      short loc_18050425F
0x180504208  cmp     r8, rcx
0x18050420b  mov     edi, 80070216h
0x180504210  sbb     eax, eax
0x180504212  and     edi, eax
0x180504214  cmp     rcx, r8
0x180504217  ja      short loc_180504252
0x180504219  test    byte ptr [rbx], 2
0x18050421c  mov     r15, [rbx+8]
0x180504220  mov     r14d, edx
0x180504223  jnz     short loc_180504295
0x180504225  mov     r8d, r14d
0x180504228  mov     rdx, r15
0x18050422b  call    ??$HeapReAlloc@$00@MemoryProtection@@YAPEAXPEAX0_K@Z; MemoryProtection::HeapReAlloc<1>(void *,void *,unsigned __int64)
0x180504230  test    rax, rax
0x180504233  jz      short loc_180504287
0x180504235  mov     [rbx+8], rax
0x180504239  mov     edi, r13d
0x18050423c  and     dword ptr [rbx], 1
0x18050423f  lea     eax, ds:0[rsi*4]
0x180504246  or      [rbx], eax
0x180504248  mov     r14, [rsp+98h+var_60]
0x18050424d  mov     r15, [rsp+98h+var_58]
0x180504252  test    edi, edi
0x180504254  jz      loc_180503FB7
0x18050425a  jmp     loc_1805040ED
0x18050425f  mov     edx, r8d
0x180504262  jmp     short loc_180504208
0x180504264  call    cs:__imp_SetTimer
0x18050426a  jmp     loc_18050405B
0x18050426f  mov     esi, [rbx]
0x180504271  shr     esi, 3
0x180504274  add     esi, ebp
0x180504276  cmp     esi, ebp
0x180504278  jb      short loc_18050428E
0x18050427a  cmp     ecx, esi
0x18050427c  jbe     loc_1805041F5
0x180504282  jmp     loc_1805041F3
0x180504287  test    r14, r14
0x18050428a  jz      short loc_180504235
0x18050428c  jmp     short loc_1805042F2
0x18050428e  mov     edi, 80070216h
0x180504293  jmp     short loc_180504252
0x180504295  mov     rcx, cs:g_hProcessHeap
0x18050429c  mov     rdx, r14
0x18050429f  call    ??$HeapAlloc@$00@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<1>(void *,unsigned __int64)
0x1805042a4  mov     [rbx+8], rax
0x1805042a8  mov     rcx, rax; Destination
0x1805042ab  test    rax, rax
0x1805042ae  jz      short loc_1805042EE
0x1805042b0  imul    r9d, ebp, 38h ; '8'; SourceSize
0x1805042b4  mov     r8, r15; Source
0x1805042b7  mov     rdx, r14; DestinationSize
0x1805042ba  call    cs:__imp_memcpy_s
0x1805042c0  jmp     loc_18050423C
0x1805042c5  lea     rsi, [rbx+60h]
0x1805042c9  xor     edx, edx; lpdwProcessId
0x1805042cb  mov     rcx, [rsi]; hWnd
0x1805042ce  call    cs:__imp_GetWindowThreadProcessId
0x1805042d4  mov     ebx, eax
0x1805042d6  call    cs:__imp_GetCurrentThreadId
0x1805042dc  cmp     ebx, eax
0x1805042de  jnz     short loc_18050433A
0x1805042e0  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1805042e6  movups  xmm0, xmmword ptr [rax]
0x1805042e9  jmp     loc_180504136
0x1805042ee  mov     [rbx+8], r15
0x1805042f2  mov     edi, 8007000Eh
0x1805042f7  jmp     loc_180504248
0x1805042fc  mov     edi, 80070057h
0x180504301  jmp     loc_1805040ED
0x180504306  mov     r8d, r12d; uElapse
0x180504309  call    cs:__imp_SetTimer
0x18050430f  jmp     loc_180504165
0x180504314  mov     r8, [rsp+98h+arg_0]
0x18050431c  lea     rdx, MSHTML_FORMSTIMER_SET
0x180504323  mov     [rsp+98h+var_70], r12d
0x180504328  mov     r9d, ebx
0x18050432b  mov     [rsp+98h+var_78], r14
0x180504330  call    McTemplateU0pqpq_EventWriteTransfer
0x180504335  jmp     loc_1805040ED
0x18050433a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180504341  jmp     loc_180504136
0x180504346  mov     eax, [rdi+18h]
0x180504349  lea     rdx, MSHTML_FORMSTIMER_RESET
0x180504350  mov     r9d, [rdi+10h]
0x180504354  mov     r8, [rdi]
0x180504357  mov     [rsp+98h+var_70], eax
0x18050435b  mov     rax, [rdi+8]
0x18050435f  mov     [rsp+98h+var_78], rax
0x180504364  call    McTemplateU0pqpq_EventWriteTransfer
0x180504369  jmp     loc_18050417B
0x18050436e  mov     [rcx+68h], r10d
0x180504372  mov     eax, r10d
0x180504375  jmp     loc_180503FF1
0x18050437a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180504381  jmp     loc_1805041CC
```
