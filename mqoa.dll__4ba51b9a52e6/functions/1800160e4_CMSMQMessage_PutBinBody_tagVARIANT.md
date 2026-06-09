# CMSMQMessage::PutBinBody(tagVARIANT)

- ea: `0x1800160e4`
- end: `0x180016559`
- name: `?PutBinBody@CMSMQMessage@@IEAAJUtagVARIANT@@@Z`
- size: `1141`
- prototype: `__int64 __fastcall(CMSMQMessage *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180019600`

## callees

- `0x18000cb34`
- `0x18001415c`
- `0x180014210`
- `0x180015258`
- `0x1800160e4`
- `0x180017bc8`
- `0x180026fbc`
- `0x18002737e`
- `0x1800273b0`
- `0x180029010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800164a3`
- `KERNEL32!GetLastError` at `0x1800164a3`
- `KERNEL32!GlobalAlloc` at `0x18001628f`
- `KERNEL32!GlobalAlloc` at `0x180016341`
- `KERNEL32!GlobalAlloc` at `0x18001628f`
- `KERNEL32!GlobalAlloc` at `0x180016341`
- `KERNEL32!GlobalLock` at `0x18001635e`
- `KERNEL32!GlobalLock` at `0x1800163bf`
- `KERNEL32!GlobalLock` at `0x180016480`
- `KERNEL32!GlobalLock` at `0x18001635e`
- `KERNEL32!GlobalLock` at `0x1800163bf`
- `KERNEL32!GlobalLock` at `0x180016480`
- `KERNEL32!GlobalFree` at `0x180016156`
- `KERNEL32!GlobalFree` at `0x180016156`
- `KERNEL32!GlobalUnlock` at `0x1800163a4`
- `KERNEL32!GlobalUnlock` at `0x180016405`
- `KERNEL32!GlobalUnlock` at `0x180016499`
- `KERNEL32!GlobalUnlock` at `0x1800163a4`
- `KERNEL32!GlobalUnlock` at `0x180016405`
- `KERNEL32!GlobalUnlock` at `0x180016499`
- `ole32!OleSave` at `0x1800162ed`
- `ole32!OleSave` at `0x1800162ed`
- `ole32!StgCreateDocfileOnILockBytes` at `0x1800162d2`
- `ole32!StgCreateDocfileOnILockBytes` at `0x1800162d2`
- `ole32!OleSaveToStream` at `0x180016243`
- `ole32!OleSaveToStream` at `0x180016243`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180016442`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180016442`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180016464`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180016464`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMSMQMessage::PutBinBody(CMSMQMessage *this, struct tagVARIANT *a2)
{
  VARTYPE vt; // bx
  SAFEARRAY *parray; // r14
  int v5; // r15d
  void *v6; // rcx
  HRESULT PersistInfo; // edi
  SAFEARRAY *v8; // rcx
  unsigned int v10; // ebx
  unsigned __int64 v11; // rcx
  const struct _GUID *v12; // rdx
  HGLOBAL v13; // rax
  HGLOBAL v14; // rax
  LPVOID v15; // r8
  LPVOID v16; // r8
  void *v17; // rcx
  LPVOID v18; // rax
  void *v19; // rcx
  int v20; // [rsp+30h] [rbp-79h] BYREF
  ILockBytes *plkbyt; // [rsp+38h] [rbp-71h] BYREF
  LPPERSISTSTREAM pPStm; // [rsp+40h] [rbp-69h] BYREF
  SAFEARRAY *v23; // [rsp+48h] [rbp-61h] BYREF
  IStorage *ppstgOpen; // [rsp+50h] [rbp-59h] BYREF
  LPSTREAM pStm; // [rsp+58h] [rbp-51h] BYREF
  void *ppvData; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v27[16]; // [rsp+70h] [rbp-39h] BYREF
  unsigned int dwBytes; // [rsp+80h] [rbp-29h]
  int dwBytes_4; // [rsp+84h] [rbp-25h]

  vt = a2->vt;
  parray = a2->parray;
  ppvData = 0;
  pPStm = 0;
  v23 = 0;
  v5 = 0;
  v20 = 0;
  ppstgOpen = 0;
  memset_0(v27, 0, 0x50u);
  v6 = (void *)*((_QWORD *)this + 30);
  plkbyt = 0;
  pStm = 0;
  if ( v6 )
  {
    GlobalFree(v6);
    *((_QWORD *)this + 30) = 0;
  }
  *((_QWORD *)this + 28) = 0;
  *((_WORD *)this + 116) = 8209;
  *((_DWORD *)this + 62) = 0;
  if ( vt != 9 )
  {
    if ( vt != 13 )
    {
      PersistInfo = 0;
      goto LABEL_14;
    }
    if ( parray )
    {
      v8 = parray;
      goto LABEL_12;
    }
    return 2147942487LL;
  }
  if ( !parray )
    return 2147942487LL;
  PersistInfo = (**(__int64 (__fastcall ***)(SAFEARRAY *, GUID *, SAFEARRAY **))&parray->cDims)(
                  parray,
                  &IID_IUnknown,
                  &v23);
  if ( PersistInfo < 0 )
    goto LABEL_50;
  v8 = v23;
LABEL_12:
  PersistInfo = GetPersistInfo(v8, &v20, &pPStm);
  if ( PersistInfo >= 0 )
  {
    v5 = v20;
LABEL_14:
    v10 = 0;
    if ( v5 )
    {
      v11 = (unsigned int)(v5 - 1);
      if ( v5 == 1 )
        goto LABEL_18;
      v11 = (unsigned int)(v5 - 2);
      if ( v5 == 2 )
      {
        PersistInfo = CMyLockBytes::CreateInstance((const struct _GUID *)v11, (void **)&plkbyt);
        if ( PersistInfo < 0 )
          goto LABEL_50;
        PersistInfo = StgCreateDocfileOnILockBytes(plkbyt, 0x1012u, 0, &ppstgOpen);
        if ( PersistInfo < 0 )
          goto LABEL_50;
        PersistInfo = OleSave((LPPERSISTSTORAGE)pPStm, ppstgOpen, 0);
        if ( PersistInfo < 0 )
          goto LABEL_50;
        PersistInfo = ((__int64 (__fastcall *)(ILockBytes *, _BYTE *, __int64))plkbyt->lpVtbl->Stat)(plkbyt, v27, 1);
        if ( PersistInfo < 0 )
          goto LABEL_50;
        v10 = dwBytes;
        if ( !dwBytes_4 )
        {
          v14 = GlobalAlloc(0x22u, dwBytes);
          *((_QWORD *)this + 30) = v14;
          if ( !v14 )
            goto LABEL_24;
          if ( v10 )
          {
            v15 = GlobalLock(v14);
            if ( !v15 )
              goto LABEL_24;
            v20 = 0;
            PersistInfo = ((__int64 (__fastcall *)(ILockBytes *, _QWORD, LPVOID, _QWORD, int *))plkbyt->lpVtbl->ReadAt)(
                            plkbyt,
                            0,
                            v15,
                            v10,
                            &v20);
            if ( PersistInfo < 0 )
              goto LABEL_50;
            GlobalUnlock(*((HGLOBAL *)this + 30));
          }
          *((_WORD *)this + 116) = 69;
LABEL_47:
          v17 = (void *)*((_QWORD *)this + 30);
          *((_DWORD *)this + 62) = v10;
          v18 = GlobalLock(v17);
          v19 = (void *)*((_QWORD *)this + 30);
          *((_QWORD *)this + 28) = v18;
          if ( v19 && !GlobalUnlock(v19) )
            GetLastError();
          goto LABEL_50;
        }
        goto LABEL_30;
      }
      if ( v5 == 3 )
      {
LABEL_18:
        PersistInfo = CMyLockBytes::CreateInstance((const struct _GUID *)v11, (void **)&plkbyt);
        if ( PersistInfo < 0 )
          goto LABEL_50;
        PersistInfo = CMyStream::CreateInstance(plkbyt, v12, (void **)&pStm);
        if ( PersistInfo < 0 )
          goto LABEL_50;
        PersistInfo = OleSaveToStream(pPStm, pStm);
        if ( PersistInfo < 0 )
          goto LABEL_50;
        PersistInfo = ((__int64 (__fastcall *)(ILockBytes *, _BYTE *, __int64))plkbyt->lpVtbl->Stat)(plkbyt, v27, 1);
        if ( PersistInfo < 0 )
          goto LABEL_50;
        v10 = dwBytes;
        if ( !dwBytes_4 )
        {
          v13 = GlobalAlloc(0x22u, dwBytes);
          *((_QWORD *)this + 30) = v13;
          if ( !v13 )
          {
LABEL_24:
            PersistInfo = -2147024882;
            goto LABEL_50;
          }
          if ( v10 )
          {
            v16 = GlobalLock(v13);
            if ( !v16 )
              goto LABEL_24;
            v20 = 0;
            PersistInfo = ((__int64 (__fastcall *)(ILockBytes *, _QWORD, LPVOID, _QWORD, int *))plkbyt->lpVtbl->ReadAt)(
                            plkbyt,
                            0,
                            v16,
                            v10,
                            &v20);
            if ( PersistInfo < 0 )
              goto LABEL_50;
            GlobalUnlock(*((HGLOBAL *)this + 30));
          }
          *((_WORD *)this + 116) = 68;
          goto LABEL_46;
        }
LABEL_30:
        PersistInfo = -2147024809;
        goto LABEL_50;
      }
    }
    else
    {
      if ( !parray )
        goto LABEL_50;
      v10 = SafeArraySize3(parray->cDims, parray->cbElements, parray->rgsabound);
      if ( v10 == -1 )
        goto LABEL_24;
      PersistInfo = SafeArrayAccessData(parray, &ppvData);
      if ( PersistInfo < 0 )
        goto LABEL_50;
      PersistInfo = CMSMQMessage::UpdateBodyBuffer(this, v10, ppvData, 0x2011u);
      SafeArrayUnaccessData(parray);
      if ( PersistInfo < 0 )
        goto LABEL_50;
    }
LABEL_46:
    if ( !v5 )
      goto LABEL_50;
    goto LABEL_47;
  }
LABEL_50:
  if ( v23 )
  {
    (*(void (__fastcall **)(SAFEARRAY *))(*(_QWORD *)&v23->cDims + 16LL))(v23);
    v23 = 0;
  }
  if ( pPStm )
  {
    ((void (__fastcall *)(LPPERSISTSTREAM))pPStm->lpVtbl->Release)(pPStm);
    pPStm = 0;
  }
  if ( ppstgOpen )
  {
    ((void (__fastcall *)(IStorage *))ppstgOpen->lpVtbl->Release)(ppstgOpen);
    ppstgOpen = 0;
  }
  if ( plkbyt )
  {
    ((void (__fastcall *)(ILockBytes *))plkbyt->lpVtbl->Release)(plkbyt);
    plkbyt = 0;
  }
  if ( pStm )
  {
    ((void (__fastcall *)(LPSTREAM))pStm->lpVtbl->Release)(pStm);
    pStm = 0;
  }
  return CreateErrorHelper((unsigned int)PersistInfo, 1);
}

```

## disassembly

```asm
0x1800160e4  mov     [rsp-8+arg_10], rbx
0x1800160e9  push    rbp
0x1800160ea  push    rsi
0x1800160eb  push    rdi
0x1800160ec  push    r12
0x1800160ee  push    r13
0x1800160f0  push    r14
0x1800160f2  push    r15
0x1800160f4  lea     rbp, [rsp-27h]
0x1800160f9  sub     rsp, 0D0h
0x180016100  mov     rax, cs:__security_cookie
0x180016107  xor     rax, rsp
0x18001610a  mov     [rbp+57h+var_40], rax
0x18001610e  movzx   ebx, word ptr [rdx]
0x180016111  xor     r12d, r12d
0x180016114  mov     r14, [rdx+8]
0x180016118  mov     rsi, rcx
0x18001611b  xor     edx, edx; Val
0x18001611d  mov     [rbp+57h+ppvData], r12
0x180016121  lea     rcx, [rbp+57h+var_90]; void *
0x180016125  mov     [rbp+57h+pPStm], r12
0x180016129  lea     r8d, [r12+50h]; Size
0x18001612e  mov     [rbp+57h+var_B8], r12
0x180016132  mov     r15d, r12d
0x180016135  mov     [rbp+57h+var_D0], r12d
0x180016139  mov     [rbp+57h+ppstgOpen], r12
0x18001613d  call    memset_0
0x180016142  mov     rcx, [rsi+0F0h]; hMem
0x180016149  mov     [rbp+57h+plkbyt], r12
0x18001614d  mov     [rbp+57h+pStm], r12
0x180016151  test    rcx, rcx
0x180016154  jz      short loc_180016163
0x180016156  call    cs:__imp_GlobalFree
0x18001615c  mov     [rsi+0F0h], r12
0x180016163  mov     [rsi+0E0h], r12
0x18001616a  mov     r13d, 2011h
0x180016170  mov     [rsi+0E8h], r13w
0x180016178  mov     [rsi+0F8h], r12d
0x18001617f  cmp     bx, 9
0x180016183  jz      short loc_18001619A
0x180016185  cmp     bx, 0Dh
0x180016189  jz      short loc_180016190
0x18001618b  mov     edi, r12d
0x18001618e  jmp     short loc_1800161EB
0x180016190  test    r14, r14
0x180016193  jz      short loc_18001619F
0x180016195  mov     rcx, r14
0x180016198  jmp     short loc_1800161D0
0x18001619a  test    r14, r14
0x18001619d  jnz     short loc_1800161A9
0x18001619f  mov     eax, 80070057h
0x1800161a4  jmp     loc_180016532
0x1800161a9  mov     rax, [r14]
0x1800161ac  lea     r8, [rbp+57h+var_B8]
0x1800161b0  lea     rdx, IID_IUnknown
0x1800161b7  mov     rcx, r14
0x1800161ba  mov     rax, [rax]
0x1800161bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161c2  mov     edi, eax
0x1800161c4  test    eax, eax
0x1800161c6  js      loc_1800164A9
0x1800161cc  mov     rcx, [rbp+57h+var_B8]
0x1800161d0  lea     r8, [rbp+57h+pPStm]
0x1800161d4  lea     rdx, [rbp+57h+var_D0]
0x1800161d8  call    GetPersistInfo
0x1800161dd  mov     edi, eax
0x1800161df  test    eax, eax
0x1800161e1  js      loc_1800164A9
0x1800161e7  mov     r15d, [rbp+57h+var_D0]
0x1800161eb  mov     ebx, r12d
0x1800161ee  mov     ecx, r15d
0x1800161f1  test    r15d, r15d
0x1800161f4  jz      loc_180016416
0x1800161fa  sub     ecx, 1
0x1800161fd  jz      short loc_180016211
0x1800161ff  sub     ecx, 1; struct _GUID *
0x180016202  jz      loc_1800162AF
0x180016208  cmp     ecx, 1
0x18001620b  jnz     loc_18001646E
0x180016211  lea     rdx, [rbp+57h+plkbyt]; void **
0x180016215  call    ?CreateInstance@CMyLockBytes@@SAJAEBU_GUID@@PEAPEAX@Z; CMyLockBytes::CreateInstance(_GUID const &,void * *)
0x18001621a  mov     edi, eax
0x18001621c  test    eax, eax
0x18001621e  js      loc_1800164A9
0x180016224  mov     rcx, [rbp+57h+plkbyt]; struct ILockBytes *
0x180016228  lea     r8, [rbp+57h+pStm]; void **
0x18001622c  call    ?CreateInstance@CMyStream@@SAJPEAUILockBytes@@AEBU_GUID@@PEAPEAX@Z; CMyStream::CreateInstance(ILockBytes *,_GUID const &,void * *)
0x180016231  mov     edi, eax
0x180016233  test    eax, eax
0x180016235  js      loc_1800164A9
0x18001623b  mov     rdx, [rbp+57h+pStm]; pStm
0x18001623f  mov     rcx, [rbp+57h+pPStm]; pPStm
0x180016243  call    cs:__imp_OleSaveToStream
0x180016249  mov     edi, eax
0x18001624b  test    eax, eax
0x18001624d  js      loc_1800164A9
0x180016253  mov     rcx, [rbp+57h+plkbyt]
0x180016257  lea     rdx, [rbp+57h+var_90]
0x18001625b  mov     r8d, 1
0x180016261  mov     rax, [rcx]
0x180016264  mov     rax, [rax+48h]
0x180016268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001626d  mov     edi, eax
0x18001626f  test    eax, eax
0x180016271  js      loc_1800164A9
0x180016277  mov     rbx, [rbp+57h+dwBytes]
0x18001627b  mov     rax, rbx
0x18001627e  shr     rax, 20h
0x180016282  test    eax, eax
0x180016284  jnz     loc_180016330
0x18001628a  mov     edx, ebx; dwBytes
0x18001628c  lea     ecx, [rax+22h]; uFlags
0x18001628f  call    cs:__imp_GlobalAlloc
0x180016295  mov     [rsi+0F0h], rax
0x18001629c  test    rax, rax
0x18001629f  jnz     loc_1800163B8
0x1800162a5  mov     edi, 8007000Eh
0x1800162aa  jmp     loc_1800164A9
0x1800162af  lea     rdx, [rbp+57h+plkbyt]; void **
0x1800162b3  call    ?CreateInstance@CMyLockBytes@@SAJAEBU_GUID@@PEAPEAX@Z; CMyLockBytes::CreateInstance(_GUID const &,void * *)
0x1800162b8  mov     edi, eax
0x1800162ba  test    eax, eax
0x1800162bc  js      loc_1800164A9
0x1800162c2  mov     rcx, [rbp+57h+plkbyt]; plkbyt
0x1800162c6  lea     r9, [rbp+57h+ppstgOpen]; ppstgOpen
0x1800162ca  xor     r8d, r8d; reserved
0x1800162cd  mov     edx, 1012h; grfMode
0x1800162d2  call    cs:__imp_StgCreateDocfileOnILockBytes
0x1800162d8  mov     edi, eax
0x1800162da  test    eax, eax
0x1800162dc  js      loc_1800164A9
0x1800162e2  mov     rdx, [rbp+57h+ppstgOpen]; pStg
0x1800162e6  xor     r8d, r8d; fSameAsLoad
0x1800162e9  mov     rcx, [rbp+57h+pPStm]; pPS
0x1800162ed  call    cs:__imp_OleSave
0x1800162f3  mov     edi, eax
0x1800162f5  test    eax, eax
0x1800162f7  js      loc_1800164A9
0x1800162fd  mov     rcx, [rbp+57h+plkbyt]
0x180016301  lea     rdx, [rbp+57h+var_90]
0x180016305  mov     r8d, 1
0x18001630b  mov     rax, [rcx]
0x18001630e  mov     rax, [rax+48h]
0x180016312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016317  mov     edi, eax
0x180016319  test    eax, eax
0x18001631b  js      loc_1800164A9
0x180016321  mov     rbx, [rbp+57h+dwBytes]
0x180016325  mov     rax, rbx
0x180016328  shr     rax, 20h
0x18001632c  test    eax, eax
0x18001632e  jz      short loc_18001633A
0x180016330  mov     edi, 80070057h
0x180016335  jmp     loc_1800164A9
0x18001633a  mov     edx, ebx; dwBytes
0x18001633c  mov     ecx, 22h ; '"'; uFlags
0x180016341  call    cs:__imp_GlobalAlloc
0x180016347  mov     [rsi+0F0h], rax
0x18001634e  test    rax, rax
0x180016351  jz      loc_1800162A5
0x180016357  test    ebx, ebx
0x180016359  jz      short loc_1800163AA
0x18001635b  mov     rcx, rax; hMem
0x18001635e  call    cs:__imp_GlobalLock
0x180016364  mov     r8, rax
0x180016367  test    rax, rax
0x18001636a  jz      loc_1800162A5
0x180016370  mov     rcx, [rbp+57h+plkbyt]
0x180016374  lea     r9, [rbp+57h+var_D0]
0x180016378  mov     [rbp+57h+var_D0], r12d
0x18001637c  mov     rdx, r12
0x18001637f  mov     [rsp+100h+var_E0], r9
0x180016384  mov     r9d, ebx
0x180016387  mov     rax, [rcx]
0x18001638a  mov     rax, [rax+18h]
0x18001638e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016393  mov     edi, eax
0x180016395  test    eax, eax
0x180016397  js      loc_1800164A9
0x18001639d  mov     rcx, [rsi+0F0h]; hMem
0x1800163a4  call    cs:__imp_GlobalUnlock
0x1800163aa  mov     word ptr [rsi+0E8h], 45h ; 'E'
0x1800163b3  jmp     loc_180016473
0x1800163b8  test    ebx, ebx
0x1800163ba  jz      short loc_18001640B
0x1800163bc  mov     rcx, rax; hMem
0x1800163bf  call    cs:__imp_GlobalLock
0x1800163c5  mov     r8, rax
0x1800163c8  test    rax, rax
0x1800163cb  jz      loc_1800162A5
0x1800163d1  mov     rcx, [rbp+57h+plkbyt]
0x1800163d5  lea     r9, [rbp+57h+var_D0]
0x1800163d9  mov     [rbp+57h+var_D0], r12d
0x1800163dd  mov     rdx, r12
0x1800163e0  mov     [rsp+100h+var_E0], r9
0x1800163e5  mov     r9d, ebx
0x1800163e8  mov     rax, [rcx]
0x1800163eb  mov     rax, [rax+18h]
0x1800163ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163f4  mov     edi, eax
0x1800163f6  test    eax, eax
0x1800163f8  js      loc_1800164A9
0x1800163fe  mov     rcx, [rsi+0F0h]; hMem
0x180016405  call    cs:__imp_GlobalUnlock
0x18001640b  mov     word ptr [rsi+0E8h], 44h ; 'D'
0x180016414  jmp     short loc_18001646E
0x180016416  test    r14, r14
0x180016419  jz      loc_1800164A9
0x18001641f  mov     edx, [r14+4]; unsigned int
0x180016423  lea     r8, [r14+18h]; struct tagSAFEARRAYBOUND *
0x180016427  movzx   ecx, word ptr [r14]; unsigned __int16
0x18001642b  call    ?SafeArraySize3@@YAKGKPEAUtagSAFEARRAYBOUND@@@Z; SafeArraySize3(ushort,ulong,tagSAFEARRAYBOUND *)
0x180016430  mov     ebx, eax
0x180016432  cmp     eax, 0FFFFFFFFh
0x180016435  jz      loc_1800162A5
0x18001643b  lea     rdx, [rbp+57h+ppvData]; ppvData
0x18001643f  mov     rcx, r14; psa
0x180016442  call    cs:__imp_SafeArrayAccessData
0x180016448  mov     edi, eax
0x18001644a  test    eax, eax
0x18001644c  js      short loc_1800164A9
0x18001644e  mov     r8, [rbp+57h+ppvData]; void *
0x180016452  mov     r9d, r13d; unsigned __int16
0x180016455  mov     edx, ebx; unsigned int
0x180016457  mov     rcx, rsi; this
0x18001645a  call    ?UpdateBodyBuffer@CMSMQMessage@@IEAAJKPEAXG@Z; CMSMQMessage::UpdateBodyBuffer(ulong,void *,ushort)
0x18001645f  mov     rcx, r14; psa
0x180016462  mov     edi, eax
0x180016464  call    cs:__imp_SafeArrayUnaccessData
0x18001646a  test    edi, edi
0x18001646c  js      short loc_1800164A9
0x18001646e  test    r15d, r15d
0x180016471  jz      short loc_1800164A9
0x180016473  mov     rcx, [rsi+0F0h]; hMem
0x18001647a  mov     [rsi+0F8h], ebx
0x180016480  call    cs:__imp_GlobalLock
0x180016486  mov     rcx, [rsi+0F0h]; hMem
0x18001648d  mov     [rsi+0E0h], rax
0x180016494  test    rcx, rcx
0x180016497  jz      short loc_1800164A9
0x180016499  call    cs:__imp_GlobalUnlock
0x18001649f  test    eax, eax
0x1800164a1  jnz     short loc_1800164A9
0x1800164a3  call    cs:__imp_GetLastError
0x1800164a9  mov     rcx, [rbp+57h+var_B8]
0x1800164ad  test    rcx, rcx
0x1800164b0  jz      short loc_1800164C2
0x1800164b2  mov     rax, [rcx]
0x1800164b5  mov     rax, [rax+10h]
0x1800164b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164be  mov     [rbp+57h+var_B8], r12
0x1800164c2  mov     rcx, [rbp+57h+pPStm]
0x1800164c6  test    rcx, rcx
0x1800164c9  jz      short loc_1800164DB
0x1800164cb  mov     rax, [rcx]
0x1800164ce  mov     rax, [rax+10h]
0x1800164d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164d7  mov     [rbp+57h+pPStm], r12
0x1800164db  mov     rcx, [rbp+57h+ppstgOpen]
0x1800164df  test    rcx, rcx
0x1800164e2  jz      short loc_1800164F4
0x1800164e4  mov     rax, [rcx]
0x1800164e7  mov     rax, [rax+10h]
0x1800164eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164f0  mov     [rbp+57h+ppstgOpen], r12
0x1800164f4  mov     rcx, [rbp+57h+plkbyt]
0x1800164f8  test    rcx, rcx
0x1800164fb  jz      short loc_18001650D
0x1800164fd  mov     rax, [rcx]
0x180016500  mov     rax, [rax+10h]
0x180016504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016509  mov     [rbp+57h+plkbyt], r12
0x18001650d  mov     rcx, [rbp+57h+pStm]
0x180016511  test    rcx, rcx
0x180016514  jz      short loc_180016526
0x180016516  mov     rax, [rcx]
0x180016519  mov     rax, [rax+10h]
0x18001651d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016522  mov     [rbp+57h+pStm], r12
0x180016526  mov     edx, 1
0x18001652b  mov     ecx, edi
0x18001652d  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x180016532  mov     rcx, [rbp+57h+var_40]
0x180016536  xor     rcx, rsp; StackCookie
0x180016539  call    __security_check_cookie
0x18001653e  mov     rbx, [rsp+100h+arg_10]
0x180016546  add     rsp, 0D0h
0x18001654d  pop     r15
0x18001654f  pop     r14
0x180016551  pop     r13
0x180016553  pop     r12
0x180016555  pop     rdi
0x180016556  pop     rsi
0x180016557  pop     rbp
0x180016558  retn
```
