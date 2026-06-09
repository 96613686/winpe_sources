# AddInterfaceToProtocol

- ea: `0x1800150c8`
- end: `0x1800154b7`
- name: `AddInterfaceToProtocol`
- size: `1007`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180014e28`
- `0x180027dc0`
- `0x1800292bc`

## callees

- `0x180011790`
- `0x1800150c8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800153de`
- `KERNEL32!HeapFree` at `0x1800153de`
- `KERNEL32!HeapAlloc` at `0x180015144`
- `KERNEL32!HeapAlloc` at `0x180015144`

## string_xrefs

- `0x18001516a`: `AddInterfaceToProtocol: memory allocated for interface %ws of type %d at Address %X`
- `0x1800151fd`: `AddInterfaceToProtocol: Error allocating %d bytes to add %ws to %ws`
- `0x18001527f`: `AddInterfaceToProtocol: Adding %ws to %ws`
- `0x18001535d`: `AddInterfaceToProtocol: Error %d adding %ws to %ws`

## pseudocode

```c
__int64 __fastcall AddInterfaceToProtocol(__int64 a1, __int64 a2, __int64 a3, int a4, int a5, int a6)
{
  _QWORD *v10; // rax
  char v11; // cl
  _QWORD *v12; // rdi
  __int64 v13; // r9
  __int64 v14; // r8
  __int128 *v15; // r9
  __int64 v16; // r9
  __int128 *v17; // r9
  __int64 v19; // r9
  __int64 v20; // r8
  __int128 *v21; // r9
  unsigned int v22; // eax
  unsigned int v23; // r14d
  __int64 v24; // r9
  __int128 *v25; // r9
  _QWORD *v26; // rcx
  __int64 v27; // r8
  __int128 *v28; // r9
  int v29; // [rsp+20h] [rbp-8C8h]
  int v30; // [rsp+28h] [rbp-8C0h]
  __int128 v31; // [rsp+60h] [rbp-888h] BYREF
  int v32; // [rsp+70h] [rbp-878h] BYREF
  __int128 v33; // [rsp+74h] [rbp-874h]
  __int128 v34; // [rsp+84h] [rbp-864h]
  int v35; // [rsp+94h] [rbp-854h]
  int v36; // [rsp+A0h] [rbp-848h] BYREF
  _BYTE v37[2044]; // [rsp+A4h] [rbp-844h] BYREF

  v36 = 0;
  memset_0(v37, 0, sizeof(v37));
  v32 = 0;
  v35 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v10 = HeapAlloc(IPRouterHeap, 0, 0x20u);
  v11 = Microsoft_Windows_RRASEnableBits;
  v12 = v10;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v13 = *(unsigned int *)(a1 + 516);
    v14 = *(_QWORD *)(a1 + 72);
    LOWORD(v36) = 0;
    LOWORD(v32) = 0;
    FormatRRASErrorString(
      &v36,
      L"AddInterfaceToProtocol: memory allocated for interface %ws of type %d at Address %X",
      v14,
      v13,
      v10);
    v11 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v15 = &v31;
      if ( a1 != -688 )
        LODWORD(v15) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v36,
        (_DWORD)v15,
        *(_QWORD *)(a1 + 72),
        (__int64)&v32);
      v11 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( v12 )
  {
    if ( v11 < 0 )
    {
      v19 = *(_QWORD *)(a2 + 32);
      v20 = *(_QWORD *)(a1 + 72);
      LOWORD(v36) = 0;
      LOWORD(v32) = 0;
      FormatRRASErrorString(&v36, L"AddInterfaceToProtocol: Adding %ws to %ws", v20, v19);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v21 = &v31;
        if ( a1 != -688 )
          LODWORD(v21) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v36,
          (_DWORD)v21,
          *(_QWORD *)(a1 + 72),
          (__int64)&v32);
      }
    }
    LOWORD(v30) = *(_WORD *)(a1 + 158);
    LOWORD(v29) = *(_WORD *)(a1 + 156);
    v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int, int, __int64, int, int, int))(a2 + 128))(
            *(_QWORD *)(a1 + 72),
            *(unsigned int *)(a1 + 16),
            *(unsigned int *)(a1 + 148),
            *(unsigned int *)(a1 + 152),
            v29,
            v30,
            a3,
            a4,
            a5,
            a6);
    v23 = v22;
    if ( v22 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v24 = *(_QWORD *)(a1 + 72);
        LOWORD(v36) = 0;
        LOWORD(v32) = 0;
        FormatRRASErrorString(
          &v36,
          L"AddInterfaceToProtocol: Error %d adding %ws to %ws",
          v22,
          v24,
          *(_QWORD *)(a2 + 32));
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v25 = &v31;
          if ( a1 != -688 )
            LODWORD(v25) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v36,
            (_DWORD)v25,
            *(_QWORD *)(a1 + 72),
            (__int64)&v32);
        }
      }
      HeapFree(IPRouterHeap, 0, v12);
    }
    else
    {
      v12[3] = a2;
      *((_DWORD *)v12 + 4) = a3 == 0;
      v26 = *(_QWORD **)(a1 + 64);
      if ( *v26 != a1 + 56 )
        __fastfail(3u);
      *v12 = a1 + 56;
      v12[1] = v26;
      *v26 = v12;
      *(_QWORD *)(a1 + 64) = v12;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v27 = *(unsigned int *)(a1 + 144);
        LOWORD(v36) = 0;
        LOWORD(v32) = 0;
        FormatRRASErrorString(&v36, L"Router Interface Type is %d", v27);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v28 = &v31;
          if ( a1 != -688 )
            LODWORD(v28) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v36,
            (_DWORD)v28,
            *(_QWORD *)(a1 + 72),
            (__int64)&v32);
        }
      }
    }
    return v23;
  }
  else
  {
    if ( (v11 & 0x40) != 0 )
    {
      v16 = *(_QWORD *)(a1 + 72);
      LOWORD(v36) = 0;
      LOWORD(v32) = 0;
      FormatRRASErrorString(
        &v36,
        L"AddInterfaceToProtocol: Error allocating %d bytes to add %ws to %ws",
        32,
        v16,
        *(_QWORD *)(a2 + 32));
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v17 = &v31;
        if ( a1 != -688 )
          LODWORD(v17) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v36,
          (_DWORD)v17,
          *(_QWORD *)(a1 + 72),
          (__int64)&v32);
      }
    }
    return 8;
  }
}

```

## disassembly

```asm
0x1800150c8  push    rbx
0x1800150ca  push    rsi
0x1800150cb  push    rdi
0x1800150cc  push    r13
0x1800150ce  push    r14
0x1800150d0  push    r15
0x1800150d2  sub     rsp, 8B8h
0x1800150d9  mov     rax, cs:__security_cookie
0x1800150e0  xor     rax, rsp
0x1800150e3  mov     [rsp+8E8h+var_48], rax
0x1800150eb  mov     r15, r8
0x1800150ee  mov     rsi, rdx
0x1800150f1  mov     rbx, rcx
0x1800150f4  xor     eax, eax
0x1800150f6  xor     edx, edx; Val
0x1800150f8  mov     [rsp+8E8h+var_848], eax
0x1800150ff  mov     r8d, 7FCh; Size
0x180015105  lea     rcx, [rsp+8E8h+var_844]; void *
0x18001510d  mov     r14d, r9d
0x180015110  call    memset_0
0x180015115  mov     rcx, cs:IPRouterHeap; hHeap
0x18001511c  xor     eax, eax
0x18001511e  xorps   xmm0, xmm0
0x180015121  mov     [rsp+8E8h+var_878], eax
0x180015125  xor     edx, edx; dwFlags
0x180015127  mov     [rsp+8E8h+var_854], eax
0x18001512e  movups  [rsp+8E8h+var_874], xmm0
0x180015133  lea     r8d, [rax+20h]; dwBytes
0x180015137  movups  [rsp+8E8h+var_864], xmm0
0x18001513f  movups  [rsp+8E8h+var_888], xmm0
0x180015144  call    cs:__imp_HeapAlloc
0x18001514a  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180015151  lea     r13, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180015158  mov     rdi, rax
0x18001515b  test    cl, cl
0x18001515d  jns     loc_1800151E5
0x180015163  mov     r9d, [rbx+204h]
0x18001516a  lea     rdx, aAddinterfaceto_0; "AddInterfaceToProtocol: memory allocate"...
0x180015171  mov     r8, [rbx+48h]
0x180015175  xor     ecx, ecx
0x180015177  mov     word ptr [rsp+8E8h+var_848], cx
0x18001517f  mov     word ptr [rsp+8E8h+var_878], cx
0x180015184  lea     rcx, [rsp+8E8h+var_848]
0x18001518c  mov     [rsp+8E8h+var_8C8], rax
0x180015191  call    FormatRRASErrorString
0x180015196  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18001519d  test    cl, cl
0x18001519f  jns     short loc_1800151E5
0x1800151a1  lea     rax, [rbx+2B0h]
0x1800151a8  mov     rcx, r13
0x1800151ab  test    rax, rax
0x1800151ae  lea     r9, [rsp+8E8h+var_888]
0x1800151b3  lea     r8, [rsp+8E8h+var_848]
0x1800151bb  cmovnz  r9, rax
0x1800151bf  lea     rdx, RasRtrmgrParamTraceInfo
0x1800151c6  lea     rax, [rsp+8E8h+var_878]
0x1800151cb  mov     [rsp+8E8h+var_8C0], rax
0x1800151d0  mov     rax, [rbx+48h]
0x1800151d4  mov     [rsp+8E8h+var_8C8], rax
0x1800151d9  call    McTemplateU0zjzz_EventWriteTransfer
0x1800151de  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x1800151e5  test    rdi, rdi
0x1800151e8  jnz     loc_180015277
0x1800151ee  test    cl, 40h
0x1800151f1  jz      short loc_18001526D
0x1800151f3  mov     r9, [rbx+48h]
0x1800151f7  lea     r8d, [rdi+20h]
0x1800151fb  xor     eax, eax
0x1800151fd  lea     rdx, aAddinterfaceto_11; "AddInterfaceToProtocol: Error allocatin"...
0x180015204  mov     word ptr [rsp+8E8h+var_848], ax
0x18001520c  lea     rcx, [rsp+8E8h+var_848]
0x180015214  mov     word ptr [rsp+8E8h+var_878], ax
0x180015219  mov     rax, [rsi+20h]
0x18001521d  mov     [rsp+8E8h+var_8C8], rax
0x180015222  call    FormatRRASErrorString
0x180015227  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001522e  jz      short loc_18001526D
0x180015230  lea     rax, [rbx+2B0h]
0x180015237  mov     rcx, r13
0x18001523a  test    rax, rax
0x18001523d  lea     r9, [rsp+8E8h+var_888]
0x180015242  lea     r8, [rsp+8E8h+var_848]
0x18001524a  cmovnz  r9, rax
0x18001524e  lea     rdx, RasRtrMgrParamTraceError
0x180015255  lea     rax, [rsp+8E8h+var_878]
0x18001525a  mov     [rsp+8E8h+var_8C0], rax
0x18001525f  mov     rax, [rbx+48h]
0x180015263  mov     [rsp+8E8h+var_8C8], rax
0x180015268  call    McTemplateU0zjzz_EventWriteTransfer
0x18001526d  mov     eax, 8
0x180015272  jmp     loc_180015496
0x180015277  test    cl, cl
0x180015279  jns     short loc_1800152EC
0x18001527b  mov     r9, [rsi+20h]
0x18001527f  lea     rdx, aAddinterfaceto_9; "AddInterfaceToProtocol: Adding %ws to %"...
0x180015286  mov     r8, [rbx+48h]
0x18001528a  lea     rcx, [rsp+8E8h+var_848]
0x180015292  xor     eax, eax
0x180015294  mov     word ptr [rsp+8E8h+var_848], ax
0x18001529c  mov     word ptr [rsp+8E8h+var_878], ax
0x1800152a1  call    FormatRRASErrorString
0x1800152a6  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800152ad  jge     short loc_1800152EC
0x1800152af  lea     rax, [rbx+2B0h]
0x1800152b6  mov     rcx, r13
0x1800152b9  test    rax, rax
0x1800152bc  lea     r9, [rsp+8E8h+var_888]
0x1800152c1  lea     r8, [rsp+8E8h+var_848]
0x1800152c9  cmovnz  r9, rax
0x1800152cd  lea     rdx, RasRtrmgrParamTraceInfo
0x1800152d4  lea     rax, [rsp+8E8h+var_878]
0x1800152d9  mov     [rsp+8E8h+var_8C0], rax
0x1800152de  mov     rax, [rbx+48h]
0x1800152e2  mov     [rsp+8E8h+var_8C8], rax
0x1800152e7  call    McTemplateU0zjzz_EventWriteTransfer
0x1800152ec  mov     ecx, [rsp+8E8h+arg_28]
0x1800152f3  mov     r9d, [rbx+98h]
0x1800152fa  mov     r8d, [rbx+94h]
0x180015301  mov     edx, [rbx+10h]
0x180015304  mov     rax, [rsi+80h]
0x18001530b  mov     [rsp+8E8h+var_8A0], ecx
0x18001530f  mov     ecx, [rsp+8E8h+arg_20]
0x180015316  mov     [rsp+8E8h+var_8A8], ecx
0x18001531a  movzx   ecx, word ptr [rbx+9Eh]
0x180015321  mov     [rsp+8E8h+var_8B0], r14d
0x180015326  mov     [rsp+8E8h+var_8B8], r15
0x18001532b  mov     word ptr [rsp+8E8h+var_8C0], cx
0x180015330  movzx   ecx, word ptr [rbx+9Ch]
0x180015337  mov     word ptr [rsp+8E8h+var_8C8], cx
0x18001533c  mov     rcx, [rbx+48h]
0x180015340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015345  mov     r14d, eax
0x180015348  test    eax, eax
0x18001534a  jz      loc_1800153E9
0x180015350  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180015357  jz      short loc_1800153D2
0x180015359  mov     r9, [rbx+48h]
0x18001535d  lea     rdx, aAddinterfaceto_8; "AddInterfaceToProtocol: Error %d adding"...
0x180015364  xor     ecx, ecx
0x180015366  mov     r8d, eax
0x180015369  mov     word ptr [rsp+8E8h+var_848], cx
0x180015371  mov     word ptr [rsp+8E8h+var_878], cx
0x180015376  mov     rcx, [rsi+20h]
0x18001537a  mov     [rsp+8E8h+var_8C8], rcx
0x18001537f  lea     rcx, [rsp+8E8h+var_848]
0x180015387  call    FormatRRASErrorString
0x18001538c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180015393  jz      short loc_1800153D2
0x180015395  lea     rax, [rbx+2B0h]
0x18001539c  mov     rcx, r13
0x18001539f  test    rax, rax
0x1800153a2  lea     r9, [rsp+8E8h+var_888]
0x1800153a7  lea     r8, [rsp+8E8h+var_848]
0x1800153af  cmovnz  r9, rax
0x1800153b3  lea     rdx, RasRtrMgrParamTraceError
0x1800153ba  lea     rax, [rsp+8E8h+var_878]
0x1800153bf  mov     [rsp+8E8h+var_8C0], rax
0x1800153c4  mov     rax, [rbx+48h]
0x1800153c8  mov     [rsp+8E8h+var_8C8], rax
0x1800153cd  call    McTemplateU0zjzz_EventWriteTransfer
0x1800153d2  mov     rcx, cs:IPRouterHeap; hHeap
0x1800153d9  mov     r8, rdi; lpMem
0x1800153dc  xor     edx, edx; dwFlags
0x1800153de  call    cs:__imp_HeapFree
0x1800153e4  jmp     loc_180015493
0x1800153e9  xor     eax, eax
0x1800153eb  mov     [rdi+18h], rsi
0x1800153ef  test    r15, r15
0x1800153f2  setz    al
0x1800153f5  mov     [rdi+10h], eax
0x1800153f8  lea     rax, [rbx+38h]
0x1800153fc  mov     rcx, [rax+8]
0x180015400  cmp     [rcx], rax
0x180015403  jz      short loc_18001540C
0x180015405  mov     ecx, 3
0x18001540a  int     29h; Win8: RtlFailFast(ecx)
0x18001540c  mov     [rdi], rax
0x18001540f  mov     [rdi+8], rcx
0x180015413  mov     [rcx], rdi
0x180015416  mov     [rax+8], rdi
0x18001541a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180015421  jge     short loc_180015493
0x180015423  mov     r8d, [rbx+90h]
0x18001542a  lea     rdx, aRouterInterfac; "Router Interface Type is %d"
0x180015431  xor     eax, eax
0x180015433  lea     rcx, [rsp+8E8h+var_848]
0x18001543b  mov     word ptr [rsp+8E8h+var_848], ax
0x180015443  mov     word ptr [rsp+8E8h+var_878], ax
0x180015448  call    FormatRRASErrorString
0x18001544d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180015454  jge     short loc_180015493
0x180015456  lea     rax, [rbx+2B0h]
0x18001545d  mov     rcx, r13
0x180015460  test    rax, rax
0x180015463  lea     r9, [rsp+8E8h+var_888]
0x180015468  lea     r8, [rsp+8E8h+var_848]
0x180015470  cmovnz  r9, rax
0x180015474  lea     rdx, RasRtrmgrParamTraceInfo
0x18001547b  lea     rax, [rsp+8E8h+var_878]
0x180015480  mov     [rsp+8E8h+var_8C0], rax
0x180015485  mov     rax, [rbx+48h]
0x180015489  mov     [rsp+8E8h+var_8C8], rax
0x18001548e  call    McTemplateU0zjzz_EventWriteTransfer
0x180015493  mov     eax, r14d
0x180015496  mov     rcx, [rsp+8E8h+var_48]
0x18001549e  xor     rcx, rsp; StackCookie
0x1800154a1  call    __security_check_cookie
0x1800154a6  add     rsp, 8B8h
0x1800154ad  pop     r15
0x1800154af  pop     r14
0x1800154b1  pop     r13
0x1800154b3  pop     rdi
0x1800154b4  pop     rsi
0x1800154b5  pop     rbx
0x1800154b6  retn
```
