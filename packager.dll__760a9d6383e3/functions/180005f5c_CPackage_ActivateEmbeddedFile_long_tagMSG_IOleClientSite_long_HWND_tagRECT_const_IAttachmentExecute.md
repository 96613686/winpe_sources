# CPackage::_ActivateEmbeddedFile(long,tagMSG *,IOleClientSite *,long,HWND__ *,tagRECT const *,IAttachmentExecute *)

- ea: `0x180005f5c`
- end: `0x180006425`
- name: `?_ActivateEmbeddedFile@CPackage@@IEAAJJPEAUtagMSG@@PEAUIOleClientSite@@JPEAUHWND__@@PEBUtagRECT@@PEAUIAttachmentExecute@@@Z`
- size: `1225`
- prototype: `__int64 __fastcall(CPackage *this, unsigned int, struct tagMSG *, IUnknown *, int, HWND, const struct tagRECT *, struct IAttachmentExecute *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000b328`

## callees

- `0x180001674`
- `0x180004c74`
- `0x180005f5c`
- `0x18000a718`
- `0x18000cba6`
- `0x18000cbf0`
- `0x18000e010`

## import_xrefs

- `SHELL32!__imp_SHExtCoCreateInstance` at `0x180006105`
- `SHELL32!__imp_SHExtCoCreateInstance` at `0x180006105`
- `SHLWAPI!__imp_SHCreateThread` at `0x180006349`
- `SHLWAPI!__imp_SHCreateThread` at `0x180006349`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006362`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006362`
- `ole32!OleRun` at `0x180006144`
- `ole32!OleRun` at `0x180006144`
- `ole32!GetClassFile` at `0x180006026`
- `ole32!GetClassFile` at `0x180006026`

## pseudocode

```c
__int64 __fastcall CPackage::_ActivateEmbeddedFile(
        CPackage *this,
        unsigned int a2,
        struct tagMSG *a3,
        IUnknown *a4,
        int a5,
        HWND a6,
        const struct tagRECT *a7,
        struct IAttachmentExecute *a8)
{
  __int64 v8; // rax
  const OLECHAR *v12; // rbx
  int v13; // edi
  char v14; // r14
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rdx
  __int64 *v20; // rax
  __int64 v21; // rdx
  __int64 *v22; // rbx
  __int64 v23; // rcx
  __int64 v24; // rcx
  LPUNKNOWN pUnknown; // [rsp+48h] [rbp-49h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-41h] BYREF
  IUnknown *v28; // [rsp+58h] [rbp-39h] BYREF
  HWND v29; // [rsp+60h] [rbp-31h]
  const struct tagRECT *v30; // [rsp+68h] [rbp-29h]
  CLSID pclsid; // [rsp+70h] [rbp-21h] BYREF

  v8 = *((_QWORD *)this + 14);
  v29 = a6;
  v30 = a7;
  v28 = a4;
  if ( !v8 )
    return (unsigned int)-2147467259;
  v12 = *(const OLECHAR **)(v8 + 592);
  if ( !v12 )
    return (unsigned int)-2147467259;
  v13 = 0;
  v14 = 1;
  if ( !*(_DWORD *)(v8 + 616) )
    goto LABEL_25;
  *((_DWORD *)this + 61) = 0;
  v15 = *(_QWORD *)(v8 + 608);
  if ( v15 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct tagMSG *))(*(_QWORD *)v15 + 88LL))(v15, a2, a3);
    goto LABEL_25;
  }
  pclsid = 0;
  if ( GetClassFile(v12, &pclsid) >= 0
    && memcmp_0(&pclsid, &CLSID_SOUNDREC, 0x10u)
    && memcmp_0(&pclsid, &CLSID_OLE1SOUNDREC, 0x10u)
    && memcmp_0(&pclsid, &CLSID_MPlayer, 0x10u)
    && memcmp_0(&pclsid, &CLSID_OLE1MPlayer, 0x10u)
    && memcmp_0(&pclsid, &CLSID_AVIFile, 0x10u)
    && memcmp_0(&pclsid, &CLSID_MIDFile, 0x10u) )
  {
    pUnknown = 0;
    v13 = SHExtCoCreateInstance(&pclsid, 0, 5, 0, &GUID_00000112_0000_0000_c000_000000000046, &pUnknown);
    if ( v13 < 0 )
      goto LABEL_23;
    v13 = ((__int64 (__fastcall *)(LPUNKNOWN, char *, char *))pUnknown->lpVtbl[6].AddRef)(
            pUnknown,
            (char *)this + 48,
            (char *)this + 156);
    if ( v13 >= 0 )
    {
      OleRun(pUnknown);
      hObject = 0;
      v13 = ((__int64 (__fastcall *)(LPUNKNOWN, GUID *, HANDLE *))pUnknown->lpVtbl->QueryInterface)(
              pUnknown,
              &GUID_0000010b_0000_0000_c000_000000000046,
              &hObject);
      if ( v13 >= 0 )
      {
        v13 = (*(__int64 (__fastcall **)(HANDLE, const OLECHAR *, __int64))(*(_QWORD *)hObject + 40LL))(
                hObject,
                v12,
                34);
        if ( v13 >= 0 )
        {
          v13 = ((__int64 (__fastcall *)(LPUNKNOWN, _QWORD, struct tagMSG *, IUnknown *, int, HWND, const struct tagRECT *))pUnknown->lpVtbl[3].Release)(
                  pUnknown,
                  a2,
                  a3,
                  v28,
                  a5,
                  v29,
                  v30);
          if ( v13 >= 0 )
          {
            ((void (__fastcall *)(LPUNKNOWN, _QWORD, _QWORD))pUnknown->lpVtbl[1].Release)(
              pUnknown,
              *((_QWORD *)this + 17),
              0);
            *(_QWORD *)(*((_QWORD *)this + 14) + 608LL) = pUnknown;
            pUnknown = 0;
          }
        }
        (*(void (__fastcall **)(HANDLE))(*(_QWORD *)hObject + 16LL))(hObject);
        if ( v13 >= 0 )
          goto LABEL_22;
      }
      ((void (__fastcall *)(LPUNKNOWN, _QWORD))pUnknown->lpVtbl[6].Release)(pUnknown, *((unsigned int *)this + 39));
    }
    ((void (__fastcall *)(LPUNKNOWN))pUnknown->lpVtbl->Release)(pUnknown);
LABEL_22:
    v14 = 1;
    goto LABEL_23;
  }
  v13 = -2147467259;
  *(_DWORD *)(*((_QWORD *)this + 14) + 616LL) = 0;
LABEL_23:
  if ( *((_DWORD *)this + 62) )
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 6) + 56LL))((char *)this + 48);
LABEL_25:
  v16 = *((_QWORD *)this + 14);
  if ( !*(_DWORD *)(v16 + 616) || v13 < 0 )
  {
    *(_DWORD *)(v16 + 616) = 0;
    v17 = *((_QWORD *)this + 14);
    *((_DWORD *)this + 38) = 1;
    hObject = (HANDLE)-1LL;
    *(_QWORD *)(v17 + 600) = 0;
    v13 = ((__int64 (__fastcall *)(struct IAttachmentExecute *, const OLECHAR *))a8->lpVtbl->SetLocalPath)(a8, v12);
    if ( v13 < 0 )
      return (unsigned int)v13;
    v18 = ((__int64 (__fastcall *)(struct IAttachmentExecute *, HWND, _QWORD, HANDLE *))a8->lpVtbl->Execute)(
            a8,
            v29,
            0,
            &hObject);
    if ( v18 >= 0 )
    {
      v19 = (__int64)hObject;
      v13 = 0;
      if ( !hObject )
      {
        v19 = -1;
        hObject = (HANDLE)-1LL;
      }
      *(_QWORD *)(*((_QWORD *)this + 14) + 600LL) = v19;
      v20 = (__int64 *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      v22 = v20;
      if ( v20 )
      {
        *v20 = 0;
        LODWORD(pUnknown) = 1;
        v28 = (IUnknown *)((char *)this + 8);
        if ( (int)Microsoft::WRL::Details::MakeAndInitialize<CMarshaledInterface::CMarshalStream,CMarshaledInterface::CMarshalStream,_GUID const &,IUnknown * &,enum MARSHAL_KIND &>(
                    v20,
                    v21,
                    &v28,
                    (int *)&pUnknown) < 0 )
          goto LABEL_36;
        v22[1] = (__int64)hObject;
        if ( !SHCreateThread(MainWaitOnChildThreadProc, v22, 8u, 0) )
          goto LABEL_36;
        hObject = (HANDLE)-1LL;
      }
      v22 = 0;
LABEL_36:
      if ( hObject != (HANDLE)-1LL )
        CloseHandle(hObject);
      if ( v22 )
      {
        v23 = *v22;
        if ( *v22 )
        {
          *v22 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        }
        operator delete(v22);
      }
      goto LABEL_45;
    }
    if ( (_WORD)v18 == 1223 )
    {
      v14 = 0;
      v13 = 0;
      goto LABEL_45;
    }
    return (unsigned int)-2147467259;
  }
LABEL_45:
  if ( !*((_DWORD *)this + 48) )
  {
    v24 = *((_QWORD *)this + 22);
    if ( v24 )
    {
      if ( v14 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 48LL))(v24);
        if ( *(_QWORD *)(*((_QWORD *)this + 14) + 600LL) != -1 )
          (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 22) + 56LL))(*((_QWORD *)this + 22), 1);
      }
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180005f5c  push    rbp
0x180005f5e  push    rbx
0x180005f5f  push    rsi
0x180005f60  push    rdi
0x180005f61  push    r12
0x180005f63  push    r13
0x180005f65  push    r14
0x180005f67  push    r15
0x180005f69  lea     rbp, [rsp-7]
0x180005f6e  sub     rsp, 98h
0x180005f75  mov     rax, cs:__security_cookie
0x180005f7c  xor     rax, rsp
0x180005f7f  mov     [rbp+3Fh+var_50], rax
0x180005f83  mov     rax, [rcx+70h]
0x180005f87  mov     r13, r8
0x180005f8a  mov     r8, [rbp+3Fh+arg_28]
0x180005f8e  mov     r12d, edx
0x180005f91  mov     rdx, [rbp+3Fh+arg_30]
0x180005f95  mov     rsi, rcx
0x180005f98  mov     r15, [rbp+3Fh+arg_38]
0x180005f9f  mov     [rbp+3Fh+var_70], r8
0x180005fa3  mov     [rbp+3Fh+var_68], rdx
0x180005fa7  mov     [rbp+3Fh+var_78], r9
0x180005fab  test    rax, rax
0x180005fae  jz      loc_1800063FE
0x180005fb4  mov     rbx, [rax+250h]
0x180005fbb  test    rbx, rbx
0x180005fbe  jz      loc_1800063FE
0x180005fc4  xor     edi, edi
0x180005fc6  mov     r14b, 1
0x180005fc9  mov     [rbp+3Fh+var_90], r14b
0x180005fcd  cmp     [rax+268h], edi
0x180005fd3  jz      loc_180006256
0x180005fd9  mov     [rcx+0F4h], edi
0x180005fdf  mov     rcx, [rax+260h]
0x180005fe6  test    rcx, rcx
0x180005fe9  jz      short loc_180006018
0x180005feb  mov     rax, [rcx]
0x180005fee  mov     [rsp+0D0h+var_A0], rdx
0x180005ff3  mov     edx, r12d
0x180005ff6  mov     [rsp+0D0h+var_A8], r8
0x180005ffb  mov     r8, r13
0x180005ffe  mov     r10, [rax+58h]
0x180006002  mov     eax, [rbp+3Fh+arg_20]
0x180006005  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180006009  mov     rax, r10
0x18000600c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006011  mov     edi, eax
0x180006013  jmp     loc_180006256
0x180006018  xorps   xmm0, xmm0
0x18000601b  lea     rdx, [rbp+3Fh+pclsid]; pclsid
0x18000601f  mov     rcx, rbx; szFilename
0x180006022  movups  xmmword ptr [rbp+3Fh+pclsid.Data1], xmm0
0x180006026  call    cs:__imp_GetClassFile
0x18000602c  test    eax, eax
0x18000602e  js      loc_18000638E
0x180006034  mov     edi, 10h
0x180006039  lea     rdx, CLSID_SOUNDREC; Buf2
0x180006040  mov     r8d, edi; Size
0x180006043  lea     rcx, [rbp+3Fh+pclsid]; Buf1
0x180006047  call    memcmp_0
0x18000604c  test    eax, eax
0x18000604e  jz      loc_18000638E
0x180006054  mov     r8d, edi; Size
0x180006057  lea     rdx, CLSID_OLE1SOUNDREC; Buf2
0x18000605e  lea     rcx, [rbp+3Fh+pclsid]; Buf1
0x180006062  call    memcmp_0
0x180006067  test    eax, eax
0x180006069  jz      loc_18000638E
0x18000606f  mov     r8d, edi; Size
0x180006072  lea     rdx, CLSID_MPlayer; Buf2
0x180006079  lea     rcx, [rbp+3Fh+pclsid]; Buf1
0x18000607d  call    memcmp_0
0x180006082  test    eax, eax
0x180006084  jz      loc_18000638E
0x18000608a  mov     r8d, edi; Size
0x18000608d  lea     rdx, CLSID_OLE1MPlayer; Buf2
0x180006094  lea     rcx, [rbp+3Fh+pclsid]; Buf1
0x180006098  call    memcmp_0
0x18000609d  test    eax, eax
0x18000609f  jz      loc_18000638E
0x1800060a5  mov     r8d, edi; Size
0x1800060a8  lea     rdx, CLSID_AVIFile; Buf2
0x1800060af  lea     rcx, [rbp+3Fh+pclsid]; Buf1
0x1800060b3  call    memcmp_0
0x1800060b8  test    eax, eax
0x1800060ba  jz      loc_18000638E
0x1800060c0  mov     r8d, edi; Size
0x1800060c3  lea     rdx, CLSID_MIDFile; Buf2
0x1800060ca  lea     rcx, [rbp+3Fh+pclsid]; Buf1
0x1800060ce  call    memcmp_0
0x1800060d3  test    eax, eax
0x1800060d5  jz      loc_18000638E
0x1800060db  lea     rax, [rbp+3Fh+pUnknown]
0x1800060df  mov     [rbp+3Fh+pUnknown], 0
0x1800060e7  mov     [rsp+0D0h+var_A8], rax
0x1800060ec  lea     r8d, [rdi-0Bh]
0x1800060f0  lea     rax, _GUID_00000112_0000_0000_c000_000000000046
0x1800060f7  xor     r9d, r9d
0x1800060fa  xor     edx, edx
0x1800060fc  mov     [rsp+0D0h+var_B0], rax
0x180006101  lea     rcx, [rbp+3Fh+pclsid]
0x180006105  call    cs:__imp_SHExtCoCreateInstance
0x18000610b  mov     edi, eax
0x18000610d  test    eax, eax
0x18000610f  js      loc_18000623D
0x180006115  mov     rcx, [rbp+3Fh+pUnknown]
0x180006119  lea     r14, [rsi+9Ch]
0x180006120  lea     rdx, [rsi+30h]
0x180006124  mov     r8, r14
0x180006127  mov     rax, [rcx]
0x18000612a  mov     rax, [rax+98h]
0x180006131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006136  mov     edi, eax
0x180006138  test    eax, eax
0x18000613a  js      loc_180006229
0x180006140  mov     rcx, [rbp+3Fh+pUnknown]; pUnknown
0x180006144  call    cs:__imp_OleRun
0x18000614a  mov     rcx, [rbp+3Fh+pUnknown]
0x18000614e  lea     r8, [rbp+3Fh+hObject]
0x180006152  mov     [rbp+3Fh+hObject], 0
0x18000615a  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x180006161  mov     rax, [rcx]
0x180006164  mov     rax, [rax]
0x180006167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000616c  mov     edi, eax
0x18000616e  test    eax, eax
0x180006170  js      loc_180006213
0x180006176  mov     rcx, [rbp+3Fh+hObject]
0x18000617a  mov     r8d, 22h ; '"'
0x180006180  mov     rdx, rbx
0x180006183  mov     rax, [rcx]
0x180006186  mov     rax, [rax+28h]
0x18000618a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000618f  mov     edi, eax
0x180006191  test    eax, eax
0x180006193  js      short loc_1800061FF
0x180006195  mov     rcx, [rbp+3Fh+pUnknown]
0x180006199  mov     r8, r13
0x18000619c  mov     rdx, [rbp+3Fh+var_68]
0x1800061a0  mov     r9, [rbp+3Fh+var_78]
0x1800061a4  mov     [rsp+0D0h+var_A0], rdx
0x1800061a9  mov     rdx, [rbp+3Fh+var_70]
0x1800061ad  mov     rax, [rcx]
0x1800061b0  mov     [rsp+0D0h+var_A8], rdx
0x1800061b5  mov     edx, [rbp+3Fh+arg_20]
0x1800061b8  mov     dword ptr [rsp+0D0h+var_B0], edx
0x1800061bc  mov     edx, r12d
0x1800061bf  mov     rax, [rax+58h]
0x1800061c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061c8  mov     edi, eax
0x1800061ca  test    eax, eax
0x1800061cc  js      short loc_1800061FF
0x1800061ce  mov     rcx, [rbp+3Fh+pUnknown]
0x1800061d2  xor     r8d, r8d
0x1800061d5  mov     rdx, [rsi+88h]
0x1800061dc  mov     rax, [rcx]
0x1800061df  mov     rax, [rax+28h]
0x1800061e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061e8  mov     rax, [rbp+3Fh+pUnknown]
0x1800061ec  mov     rcx, [rsi+70h]
0x1800061f0  mov     [rcx+260h], rax
0x1800061f7  mov     [rbp+3Fh+pUnknown], 0
0x1800061ff  mov     rcx, [rbp+3Fh+hObject]
0x180006203  mov     rax, [rcx]
0x180006206  mov     rax, [rax+10h]
0x18000620a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000620f  test    edi, edi
0x180006211  jns     short loc_180006239
0x180006213  mov     rcx, [rbp+3Fh+pUnknown]
0x180006217  mov     edx, [r14]
0x18000621a  mov     rax, [rcx]
0x18000621d  mov     rax, [rax+0A0h]
0x180006224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006229  mov     rcx, [rbp+3Fh+pUnknown]
0x18000622d  mov     rax, [rcx]
0x180006230  mov     rax, [rax+10h]
0x180006234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006239  mov     r14b, [rbp+3Fh+var_90]
0x18000623d  cmp     dword ptr [rsi+0F8h], 0
0x180006244  jz      short loc_180006256
0x180006246  lea     rcx, [rsi+30h]
0x18000624a  mov     rax, [rcx]
0x18000624d  mov     rax, [rax+38h]
0x180006251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006256  mov     rax, [rsi+70h]
0x18000625a  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000625e  cmp     dword ptr [rax+268h], 0
0x180006265  jz      short loc_18000626F
0x180006267  test    edi, edi
0x180006269  jns     loc_1800063B1
0x18000626f  mov     dword ptr [rax+268h], 0
0x180006279  mov     rdx, rbx
0x18000627c  mov     rax, [rsi+70h]
0x180006280  mov     rcx, r15
0x180006283  mov     dword ptr [rsi+98h], 1
0x18000628d  mov     [rbp+3Fh+hObject], r12
0x180006291  mov     qword ptr [rax+258h], 0
0x18000629c  mov     rax, [r15]
0x18000629f  mov     rax, [rax+28h]
0x1800062a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062a8  mov     edi, eax
0x1800062aa  test    eax, eax
0x1800062ac  js      loc_180006403
0x1800062b2  mov     rax, [r15]
0x1800062b5  lea     r9, [rbp+3Fh+hObject]
0x1800062b9  mov     rdx, [rbp+3Fh+var_70]
0x1800062bd  xor     r8d, r8d
0x1800062c0  mov     rcx, r15
0x1800062c3  mov     rax, [rax+60h]
0x1800062c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062cc  test    eax, eax
0x1800062ce  js      loc_1800063A6
0x1800062d4  mov     rdx, [rbp+3Fh+hObject]
0x1800062d8  xor     edi, edi
0x1800062da  test    rdx, rdx
0x1800062dd  jnz     short loc_1800062E6
0x1800062df  mov     rdx, r12
0x1800062e2  mov     [rbp+3Fh+hObject], rdx
0x1800062e6  mov     rax, [rsi+70h]
0x1800062ea  mov     ecx, 10h; unsigned __int64
0x1800062ef  mov     [rax+258h], rdx
0x1800062f6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800062fd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006302  mov     rbx, rax
0x180006305  test    rax, rax
0x180006308  jz      short loc_180006357
0x18000630a  mov     [rax], rdi
0x18000630d  lea     r9, [rbp+3Fh+pUnknown]
0x180006311  lea     rax, [rsi+8]
0x180006315  mov     dword ptr [rbp+3Fh+pUnknown], 1
0x18000631c  lea     r8, [rbp+3Fh+var_78]
0x180006320  mov     [rbp+3Fh+var_78], rax
0x180006324  mov     rcx, rbx
0x180006327  call    ??$MakeAndInitialize@VCMarshalStream@CMarshaledInterface@@V12@AEBU_GUID@@AEAPEAUIUnknown@@AEAW4MARSHAL_KIND@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCMarshalStream@CMarshaledInterface@@@WRL@Microsoft@@@012@AEBU_GUID@@AEAPEAUIUnknown@@AEAW4MARSHAL_KIND@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CMarshaledInterface::CMarshalStream,CMarshaledInterface::CMarshalStream,_GUID const &,IUnknown * &,MARSHAL_KIND &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<CMarshaledInterface::CMarshalStream>>,_GUID const &,IUnknown * &,MARSHAL_KIND &)
0x18000632c  test    eax, eax
0x18000632e  js      short loc_180006359
0x180006330  mov     rax, [rbp+3Fh+hObject]
0x180006334  lea     rcx, ?MainWaitOnChildThreadProc@@YAKPEAX@Z; pfnThreadProc
0x18000633b  xor     r9d, r9d; pfnCallback
0x18000633e  mov     [rbx+8], rax
0x180006342  mov     rdx, rbx; pData
0x180006345  lea     r8d, [r9+8]; flags
0x180006349  call    cs:__imp_SHCreateThread
0x18000634f  test    eax, eax
0x180006351  jz      short loc_180006359
0x180006353  mov     [rbp+3Fh+hObject], r12
0x180006357  xor     ebx, ebx
0x180006359  mov     rcx, [rbp+3Fh+hObject]; hObject
0x18000635d  cmp     rcx, r12
0x180006360  jz      short loc_180006368
0x180006362  call    cs:__imp_CloseHandle
0x180006368  test    rbx, rbx
0x18000636b  jz      short loc_1800063B1
0x18000636d  mov     rcx, [rbx]
0x180006370  test    rcx, rcx
0x180006373  jz      short loc_180006384
0x180006375  mov     [rbx], rdi
0x180006378  mov     rax, [rcx]
0x18000637b  mov     rax, [rax+10h]
0x18000637f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006384  mov     rcx, rbx; lpMem
0x180006387  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000638c  jmp     short loc_1800063B1
0x18000638e  mov     rax, [rsi+70h]
0x180006392  mov     edi, 80004005h
0x180006397  mov     dword ptr [rax+268h], 0
0x1800063a1  jmp     loc_18000623D
0x1800063a6  cmp     ax, 4C7h
0x1800063aa  jnz     short loc_1800063FE
0x1800063ac  xor     r14b, r14b
0x1800063af  xor     edi, edi
0x1800063b1  cmp     dword ptr [rsi+0C0h], 0
0x1800063b8  jnz     short loc_180006403
0x1800063ba  mov     rcx, [rsi+0B0h]
0x1800063c1  test    rcx, rcx
0x1800063c4  jz      short loc_180006403
0x1800063c6  test    r14b, r14b
0x1800063c9  jz      short loc_180006403
0x1800063cb  mov     rax, [rcx]
0x1800063ce  mov     rax, [rax+30h]
0x1800063d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063d7  mov     rax, [rsi+70h]
0x1800063db  cmp     [rax+258h], r12
0x1800063e2  jz      short loc_180006403
0x1800063e4  mov     rcx, [rsi+0B0h]
0x1800063eb  mov     edx, 1
0x1800063f0  mov     rax, [rcx]
0x1800063f3  mov     rax, [rax+38h]
0x1800063f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063fc  jmp     short loc_180006403
0x1800063fe  mov     edi, 80004005h
0x180006403  mov     eax, edi
0x180006405  mov     rcx, [rbp+3Fh+var_50]
0x180006409  xor     rcx, rsp; StackCookie
0x18000640c  call    __security_check_cookie
0x180006411  add     rsp, 98h
0x180006418  pop     r15
0x18000641a  pop     r14
0x18000641c  pop     r13
  ... truncated ...
```
