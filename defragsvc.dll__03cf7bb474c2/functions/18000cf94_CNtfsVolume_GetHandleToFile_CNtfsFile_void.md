# CNtfsVolume::_GetHandleToFile(CNtfsFile *,void * *)

- ea: `0x18000cf94`
- end: `0x18000d3e1`
- name: `?_GetHandleToFile@CNtfsVolume@@AEAAJPEAVCNtfsFile@@PEAPEAX@Z`
- size: `1101`
- prototype: `__int64 __fastcall(CNtfsVolume *__hidden this, struct CNtfsFile *, void **)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003d84`
- `0x18000cd50`

## callees

- `0x180006400`
- `0x18000cae8`
- `0x18000cf94`
- `0x18000d3e8`
- `0x18000e218`
- `0x180010bc0`
- `0x1800157fc`
- `0x180019228`
- `0x1800192b4`
- `0x180046494`
- `0x18004a92c`
- `0x180067af2`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d15c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d16a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d15c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d16a`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x18000cff8`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x18000cff8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d1c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d1c3`

## pseudocode

```c
__int64 __fastcall CNtfsVolume::_GetHandleToFile(CNtfsVolume *this, struct CNtfsFile *a2, void **a3)
{
  void **v3; // r14
  struct CNtfsFile *v4; // rsi
  int ThreadContextRetail; // eax
  CSxGlobalTracer **v7; // rdx
  CSxGlobalTracer *v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rdi
  __int16 v11; // ax
  int HandleToFile; // r12d
  __int16 v14; // ax
  __int64 v15; // r9
  void *v16; // rax
  __int64 v17; // rdx
  void *v18; // rax
  __int64 v19; // r13
  int v20; // r15d
  char *v21; // r14
  CNtfsVolume *v22; // rcx
  void *v23; // [rsp+20h] [rbp-60h] BYREF
  void *Src; // [rsp+28h] [rbp-58h]
  LPVOID pv; // [rsp+30h] [rbp-50h] BYREF
  __int64 v26; // [rsp+38h] [rbp-48h]
  int v27; // [rsp+40h] [rbp-40h] BYREF
  __int64 v28; // [rsp+44h] [rbp-3Ch]
  __int16 v29; // [rsp+4Ch] [rbp-34h]
  const char *v30; // [rsp+50h] [rbp-30h]
  __int128 v31; // [rsp+58h] [rbp-28h] BYREF
  __int64 v32; // [rsp+68h] [rbp-18h]
  int v33; // [rsp+70h] [rbp-10h]
  void *v36; // [rsp+D8h] [rbp+58h] BYREF

  v3 = a3;
  v4 = a2;
  v27 = 0;
  v28 = 575;
  v29 = 1;
  v30 = "CNtfsVolume::_GetHandleToFile";
  v31 = 0;
  v32 = 0;
  v33 = 0;
  ThreadContextRetail = SxTracerGetThreadContextRetail((char *)&v31 + 8);
  v7 = &WPP_GLOBAL_Control;
  if ( ThreadContextRetail >= 0 )
  {
    *(_QWORD *)&v31 = *(_QWORD *)(*((_QWORD *)&v31 + 1) + 32LL);
    *(_QWORD *)(*((_QWORD *)&v31 + 1) + 32LL) = &v27;
LABEL_3:
    v8 = WPP_GLOBAL_Control;
    goto LABEL_4;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids,
      (unsigned int)ThreadContextRetail);
    v7 = &WPP_GLOBAL_Control;
    goto LABEL_3;
  }
LABEL_4:
  if ( v29 )
  {
    if ( v29 == 1 )
    {
      if ( v8 == (CSxGlobalTracer *)&WPP_GLOBAL_Control || (*((_DWORD *)v8 + 7) & 0x20000000) == 0 )
        goto LABEL_8;
      v17 = 12;
LABEL_33:
      WPP_SF_s(*((_QWORD *)v8 + 2), v17, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids, v30);
      goto LABEL_8;
    }
    if ( v8 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x20000) != 0 )
    {
      v17 = 13;
      goto LABEL_33;
    }
  }
  else if ( v8 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x8000000) != 0 )
  {
    v17 = 11;
    goto LABEL_33;
  }
LABEL_8:
  v9 = -1;
  v10 = -1;
  v36 = (void *)-1LL;
  v23 = (void *)-1LL;
  pv = (LPVOID)&qword_18006F470;
  v26 = 0;
  v11 = 581;
  if ( !v4 || (LOWORD(v28) = 581, v11 = 582, !v3) )
  {
    HandleToFile = -2147024809;
    v27 = -2147024809;
    goto LABEL_10;
  }
  v27 = 0;
  LOWORD(v28) = 582;
  *v3 = (void *)-1LL;
  if ( (unsigned __int16)(*((_WORD *)v4 + 16) - 1) <= 0xFu )
  {
    v18 = (void *)*((_QWORD *)this + 6);
    Src = v18;
    if ( v18 )
    {
      v19 = -1;
      do
        ++v19;
      while ( *((_WORD *)v18 + v19) );
      HandleToFile = 0;
      if ( (_DWORD)v19 )
      {
        HandleToFile = CBsString::ExtendBuffer((CBsString *)&pv, (int)v19 + 1);
        if ( HandleToFile >= 0 )
        {
          v20 = v26;
          v21 = (char *)pv + 2 * (unsigned int)v26;
          memcpy_0(v21, Src, 2LL * (unsigned int)v19);
          *(_WORD *)&v21[2 * (unsigned int)v19] = 0;
          LODWORD(v26) = v19 + v20;
          v4 = a2;
          v3 = a3;
        }
      }
      v27 = HandleToFile;
      if ( HandleToFile >= 0 )
      {
        LOWORD(v28) = 592;
        HandleToFile = CBsString::Trailing((CBsString *)&pv, (unsigned __int16)v7);
        v27 = HandleToFile;
        v11 = 593;
        if ( HandleToFile >= 0 )
        {
          LOWORD(v28) = 593;
          HandleToFile = CBsString::Append((CBsString *)&pv, off_18006D5B0[*((unsigned __int16 *)v4 + 16) - 1]);
          v27 = HandleToFile;
          v11 = 594;
          if ( HandleToFile >= 0 )
          {
            LOWORD(v28) = 594;
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_4f8c356de1ed38d999e93e3ab0e0aef2_Traceguids, pv);
            }
            HandleToFile = CNtfsVolume::_GetHandleToFile(v22, (unsigned __int16 *)pv, &v36);
            v27 = HandleToFile;
            v14 = 598;
            if ( HandleToFile >= 0 )
            {
              LOWORD(v28) = 598;
              goto LABEL_22;
            }
            goto LABEL_24;
          }
        }
LABEL_10:
        WORD1(v28) = v11;
        goto LABEL_11;
      }
    }
    else
    {
      HandleToFile = -2147024809;
      v27 = -2147024809;
    }
    v11 = 592;
    goto LABEL_10;
  }
  HandleToFile = FsOpenFileByFileID(*((_QWORD *)this + 5), *((_QWORD *)v4 + 2), &v36);
  v27 = HandleToFile;
  v14 = 606;
  if ( HandleToFile < 0 )
  {
LABEL_24:
    WORD1(v28) = v14;
    v10 = (__int64)v36;
    goto LABEL_11;
  }
  LOWORD(v28) = 606;
  v15 = *((_QWORD *)v4 + 3);
  if ( !v15 )
  {
LABEL_22:
    v16 = v36;
    v10 = -1;
LABEL_23:
    *v3 = v16;
    goto LABEL_11;
  }
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_4f8c356de1ed38d999e93e3ab0e0aef2_Traceguids, v15);
  v10 = (__int64)v36;
  HandleToFile = FsOpenAlternateStream(v36, *((const unsigned __int16 **)v4 + 3), &v23);
  v27 = HandleToFile;
  if ( HandleToFile >= 0 )
  {
    LOWORD(v28) = 614;
    v16 = v23;
    goto LABEL_23;
  }
  WORD1(v28) = 614;
  v9 = (__int64)v23;
LABEL_11:
  if ( pv != &qword_18006F470 )
    CoTaskMemFree(pv);
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v9);
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v10);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v27);
  return (unsigned int)HandleToFile;
}

```

## disassembly

```asm
0x18000cf94  mov     [rsp-38h+arg_0], rbx
0x18000cf99  mov     [rsp-38h+arg_10], r8
0x18000cf9e  mov     [rsp-38h+arg_8], rdx
0x18000cfa3  push    rbp
0x18000cfa4  push    rsi
0x18000cfa5  push    rdi
0x18000cfa6  push    r12
0x18000cfa8  push    r13
0x18000cfaa  push    r14
0x18000cfac  push    r15
0x18000cfae  mov     rbp, rsp
0x18000cfb1  sub     rsp, 80h
0x18000cfb8  mov     r14, r8
0x18000cfbb  mov     rsi, rdx
0x18000cfbe  mov     r15, rcx
0x18000cfc1  xor     r13d, r13d
0x18000cfc4  mov     [rbp+var_40], r13d
0x18000cfc8  mov     [rbp+var_3C], 23Fh
0x18000cfd0  lea     r12d, [r13+1]
0x18000cfd4  mov     [rbp+var_34], r12w
0x18000cfd9  lea     rax, aCntfsvolumeGet_10; "CNtfsVolume::_GetHandleToFile"
0x18000cfe0  mov     [rbp+var_30], rax
0x18000cfe4  xorps   xmm0, xmm0
0x18000cfe7  movdqu  [rbp+var_28], xmm0
0x18000cfec  mov     [rbp+var_18], r13
0x18000cff0  mov     [rbp+var_10], r13d
0x18000cff4  lea     rcx, [rbp+var_28+8]
0x18000cff8  call    cs:__imp_SxTracerGetThreadContextRetail
0x18000cffe  lea     rbx, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x18000d005  lea     rdx, WPP_GLOBAL_Control
0x18000d00c  test    eax, eax
0x18000d00e  js      loc_18000D326
0x18000d014  mov     rcx, qword ptr [rbp+var_28+8]
0x18000d018  mov     rax, [rcx+20h]
0x18000d01c  mov     qword ptr [rbp+var_28], rax
0x18000d020  lea     rax, [rbp+var_40]
0x18000d024  mov     [rcx+20h], rax
0x18000d028  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d02f  movzx   eax, [rbp+var_34]
0x18000d033  test    ax, ax
0x18000d036  jz      loc_18000D360
0x18000d03c  cmp     ax, r12w
0x18000d040  jnz     loc_18000D1CE
0x18000d046  cmp     rcx, rdx
0x18000d049  jz      short loc_18000D058
0x18000d04b  test    dword ptr [rcx+1Ch], 20000000h
0x18000d052  jnz     loc_18000D380
0x18000d058  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000d05c  mov     rdi, rbx
0x18000d05f  mov     [rbp+arg_18], rbx
0x18000d063  mov     [rbp+var_60], rbx
0x18000d067  lea     rax, qword_18006F470
0x18000d06e  mov     [rbp+pv], rax
0x18000d072  mov     [rbp+var_48], r13
0x18000d076  mov     eax, 245h
0x18000d07b  test    rsi, rsi
0x18000d07e  jnz     short loc_18000D0E5
0x18000d080  mov     r12d, 80070057h
0x18000d086  mov     [rbp+var_40], r12d
0x18000d08a  mov     word ptr [rbp+var_3C+2], ax
0x18000d08e  mov     rcx, [rbp+pv]; pv
0x18000d092  lea     rax, qword_18006F470
0x18000d099  cmp     rcx, rax
0x18000d09c  jnz     loc_18000D1C3
0x18000d0a2  lea     rax, [rbx-1]
0x18000d0a6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d0aa  jbe     loc_18000D159
0x18000d0b0  lea     rcx, [rdi-1]
0x18000d0b4  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000d0b8  jbe     loc_18000D167
0x18000d0be  lea     rcx, [rbp+var_40]; this
0x18000d0c2  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000d0c7  mov     eax, r12d
0x18000d0ca  mov     rbx, [rsp+80h+arg_0]
0x18000d0d2  add     rsp, 80h
0x18000d0d9  pop     r15
0x18000d0db  pop     r14
0x18000d0dd  pop     r13
0x18000d0df  pop     r12
0x18000d0e1  pop     rdi
0x18000d0e2  pop     rsi
0x18000d0e3  pop     rbp
0x18000d0e4  retn
0x18000d0e5  mov     word ptr [rbp+var_3C], ax
0x18000d0e9  mov     eax, 246h
0x18000d0ee  test    r14, r14
0x18000d0f1  jz      short loc_18000D080
0x18000d0f3  mov     [rbp+var_40], r13d
0x18000d0f7  mov     word ptr [rbp+var_3C], ax
0x18000d0fb  mov     [r14], rbx
0x18000d0fe  movzx   eax, word ptr [rsi+20h]
0x18000d102  sub     ax, r12w
0x18000d106  cmp     ax, 0Fh
0x18000d10a  jbe     loc_18000D1FE
0x18000d110  lea     r8, [rbp+arg_18]
0x18000d114  mov     rdx, [rsi+10h]
0x18000d118  mov     rcx, [r15+28h]
0x18000d11c  call    ?FsOpenFileByFileID@@YAJQEAXUFILE_REFERENCE@@PEAPEAX@Z; FsOpenFileByFileID(void * const,FILE_REFERENCE,void * *)
0x18000d121  mov     r12d, eax
0x18000d124  mov     [rbp+var_40], eax
0x18000d127  test    eax, eax
0x18000d129  mov     eax, 25Eh
0x18000d12e  js      short loc_18000D14C
0x18000d130  mov     word ptr [rbp+var_3C], ax
0x18000d134  mov     r9, [rsi+18h]
0x18000d138  test    r9, r9
0x18000d13b  jnz     short loc_18000D175
0x18000d13d  mov     rax, [rbp+arg_18]
0x18000d141  mov     rdi, rbx
0x18000d144  mov     [r14], rax
0x18000d147  jmp     loc_18000D08E
0x18000d14c  mov     word ptr [rbp+var_3C+2], ax
0x18000d150  mov     rdi, [rbp+arg_18]
0x18000d154  jmp     loc_18000D08E
0x18000d159  mov     rcx, rbx; hObject
0x18000d15c  call    cs:__imp_CloseHandle
0x18000d162  jmp     loc_18000D0B0
0x18000d167  mov     rcx, rdi; hObject
0x18000d16a  call    cs:__imp_CloseHandle
0x18000d170  jmp     loc_18000D0BE
0x18000d175  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d17c  lea     rax, WPP_GLOBAL_Control
0x18000d183  cmp     rcx, rax
0x18000d186  jz      short loc_18000D192
0x18000d188  test    byte ptr [rcx+1Ch], 8
0x18000d18c  jnz     loc_18000D3C6
0x18000d192  lea     r8, [rbp+var_60]; void **
0x18000d196  mov     rdx, [rsi+18h]; unsigned __int16 *
0x18000d19a  mov     rdi, [rbp+arg_18]
0x18000d19e  mov     rcx, rdi; void *
0x18000d1a1  call    ?FsOpenAlternateStream@@YAJPEAXPEBGPEAPEAX@Z; FsOpenAlternateStream(void *,ushort const *,void * *)
0x18000d1a6  mov     r12d, eax
0x18000d1a9  mov     [rbp+var_40], eax
0x18000d1ac  test    eax, eax
0x18000d1ae  mov     eax, 266h
0x18000d1b3  js      loc_18000D319
0x18000d1b9  mov     word ptr [rbp+var_3C], ax
0x18000d1bd  mov     rax, [rbp+var_60]
0x18000d1c1  jmp     short loc_18000D144
0x18000d1c3  call    cs:__imp_CoTaskMemFree
0x18000d1c9  jmp     loc_18000D0A2
0x18000d1ce  cmp     rcx, rdx
0x18000d1d1  jz      loc_18000D058
0x18000d1d7  test    dword ptr [rcx+1Ch], 20000h
0x18000d1de  jz      loc_18000D058
0x18000d1e4  mov     edx, 0Dh
0x18000d1e9  mov     r9, [rbp+var_30]
0x18000d1ed  mov     r8, rbx
0x18000d1f0  mov     rcx, [rcx+10h]
0x18000d1f4  call    WPP_SF_s
0x18000d1f9  jmp     loc_18000D058
0x18000d1fe  mov     rax, [r15+30h]
0x18000d202  mov     [rbp+Src], rax
0x18000d206  test    rax, rax
0x18000d209  jz      loc_18000D38A
0x18000d20f  mov     r13, rbx
0x18000d212  xor     r15d, r15d
0x18000d215  inc     r13
0x18000d218  cmp     [rax+r13*2], r15w
0x18000d21d  jnz     short loc_18000D215
0x18000d21f  mov     r12d, r15d
0x18000d222  test    r13d, r13d
0x18000d225  jz      short loc_18000D273
0x18000d227  lea     edx, [r13+1]; unsigned int
0x18000d22b  lea     rcx, [rbp+pv]; this
0x18000d22f  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x18000d234  mov     r12d, eax
0x18000d237  test    eax, eax
0x18000d239  js      short loc_18000D273
0x18000d23b  mov     r15d, dword ptr [rbp+var_48]
0x18000d23f  mov     rax, [rbp+pv]
0x18000d243  lea     r14, [rax+r15*2]
0x18000d247  mov     eax, r13d
0x18000d24a  lea     rsi, [rax+rax]
0x18000d24e  mov     r8, rsi; Size
0x18000d251  mov     rdx, [rbp+Src]; Src
0x18000d255  mov     rcx, r14; void *
0x18000d258  call    memcpy_0
0x18000d25d  xor     eax, eax
0x18000d25f  mov     [rsi+r14], ax
0x18000d264  add     r15d, r13d
0x18000d267  mov     dword ptr [rbp+var_48], r15d
0x18000d26b  mov     rsi, [rbp+arg_8]
0x18000d26f  mov     r14, [rbp+arg_10]
0x18000d273  mov     [rbp+var_40], r12d
0x18000d277  test    r12d, r12d
0x18000d27a  js      loc_18000D394
0x18000d280  mov     eax, 250h
0x18000d285  mov     word ptr [rbp+var_3C], ax
0x18000d289  lea     rcx, [rbp+pv]; this
0x18000d28d  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x18000d292  mov     r12d, eax
0x18000d295  mov     [rbp+var_40], eax
0x18000d298  test    eax, eax
0x18000d29a  mov     eax, 251h
0x18000d29f  js      loc_18000D08A
0x18000d2a5  mov     word ptr [rbp+var_3C], ax
0x18000d2a9  movzx   edx, word ptr [rsi+20h]
0x18000d2ad  lea     rax, off_18006D5B0; "$Secure::$ATTRIBUTE_LIST"
0x18000d2b4  mov     rdx, [rax+rdx*8-8]; unsigned __int16 *
0x18000d2b9  lea     rcx, [rbp+pv]; this
0x18000d2bd  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18000d2c2  mov     r12d, eax
0x18000d2c5  mov     [rbp+var_40], eax
0x18000d2c8  test    eax, eax
0x18000d2ca  mov     eax, 252h
0x18000d2cf  js      loc_18000D08A
0x18000d2d5  mov     word ptr [rbp+var_3C], ax
0x18000d2d9  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18000d2e0  lea     rax, WPP_GLOBAL_Control
0x18000d2e7  cmp     rcx, rax
0x18000d2ea  jnz     loc_18000D39E
0x18000d2f0  lea     r8, [rbp+arg_18]; void **
0x18000d2f4  mov     rdx, [rbp+pv]; unsigned __int16 *
0x18000d2f8  call    ?_GetHandleToFile@CNtfsVolume@@AEAAJPEAGPEAPEAX@Z; CNtfsVolume::_GetHandleToFile(ushort *,void * *)
0x18000d2fd  mov     r12d, eax
0x18000d300  mov     [rbp+var_40], eax
0x18000d303  test    eax, eax
0x18000d305  mov     eax, 256h
0x18000d30a  js      loc_18000D14C
0x18000d310  mov     word ptr [rbp+var_3C], ax
0x18000d314  jmp     loc_18000D13D
0x18000d319  mov     word ptr [rbp+var_3C+2], ax
0x18000d31d  mov     rbx, [rbp+var_60]
0x18000d321  jmp     loc_18000D08E
0x18000d326  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d32d  cmp     rcx, rdx
0x18000d330  jz      loc_18000D02F
0x18000d336  test    [rcx+1Ch], r12b
0x18000d33a  jz      loc_18000D02F
0x18000d340  mov     edx, 0Ah
0x18000d345  mov     r9d, eax
0x18000d348  mov     r8, rbx
0x18000d34b  mov     rcx, [rcx+10h]
0x18000d34f  call    WPP_SF_d
0x18000d354  lea     rdx, WPP_GLOBAL_Control
0x18000d35b  jmp     loc_18000D028
0x18000d360  cmp     rcx, rdx
0x18000d363  jz      loc_18000D058
0x18000d369  test    dword ptr [rcx+1Ch], 8000000h
0x18000d370  jz      loc_18000D058
0x18000d376  mov     edx, 0Bh
0x18000d37b  jmp     loc_18000D1E9
0x18000d380  mov     edx, 0Ch
0x18000d385  jmp     loc_18000D1E9
0x18000d38a  mov     r12d, 80070057h
0x18000d390  mov     [rbp+var_40], r12d
0x18000d394  mov     eax, 250h
0x18000d399  jmp     loc_18000D08A
0x18000d39e  test    byte ptr [rcx+1Ch], 8
0x18000d3a2  jz      loc_18000D2F0
0x18000d3a8  mov     edx, 13h
0x18000d3ad  mov     r9, [rbp+pv]
0x18000d3b1  lea     r8, WPP_4f8c356de1ed38d999e93e3ab0e0aef2_Traceguids
0x18000d3b8  mov     rcx, [rcx+10h]
0x18000d3bc  call    WPP_SF_S
0x18000d3c1  jmp     loc_18000D2F0
0x18000d3c6  mov     edx, 14h
0x18000d3cb  lea     r8, WPP_4f8c356de1ed38d999e93e3ab0e0aef2_Traceguids
0x18000d3d2  mov     rcx, [rcx+10h]
0x18000d3d6  call    WPP_SF_S
0x18000d3db  jmp     loc_18000D192
```
