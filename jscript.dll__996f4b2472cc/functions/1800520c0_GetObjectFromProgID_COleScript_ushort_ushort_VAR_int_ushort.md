# GetObjectFromProgID(COleScript *,ushort *,ushort *,VAR *,int,ushort *)

- ea: `0x1800520c0`
- end: `0x18005255f`
- name: `?GetObjectFromProgID@@YAJPEAVCOleScript@@PEAG1PEAVVAR@@H1@Z`
- size: `1183`
- prototype: `HRESULT __fastcall(struct CSession **this, const OLECHAR *lpszProgID, BSTR pbstr, struct VAR *, int, unsigned __int16 *String2)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004b744`
- `0x18005c568`

## callees

- `0x18004d3ec`
- `0x18004f750`
- `0x1800519b4`
- `0x1800520c0`
- `0x180074f64`
- `0x180078854`
- `0x1800788ec`
- `0x1800789d4`
- `0x1800887e8`
- `0x180093d50`
- `0x1800966e0`
- `0x180098010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800522d6`
- `msvcrt!_wcsicmp` at `0x1800522d6`
- `OLEAUT32!__imp_SysStringLen` at `0x1800521d6`
- `OLEAUT32!__imp_SysStringLen` at `0x1800521d6`
- `OLEAUT32!__imp_GetActiveObject` at `0x18005220c`
- `OLEAUT32!__imp_GetActiveObject` at `0x18005220c`
- `KERNEL32!GetComputerNameA` at `0x180052284`
- `KERNEL32!GetComputerNameA` at `0x180052284`
- `KERNEL32!MultiByteToWideChar` at `0x1800522b1`
- `KERNEL32!MultiByteToWideChar` at `0x1800522b1`
- `ole32!CoGetClassObject` at `0x180052327`
- `ole32!CoGetClassObject` at `0x180052327`
- `ole32!CLSIDFromProgID` at `0x180052146`
- `ole32!CLSIDFromProgID` at `0x180052146`
- `ole32!CLSIDFromProgIDEx` at `0x18005212f`
- `ole32!CLSIDFromProgIDEx` at `0x18005212f`

## pseudocode

```c
HRESULT __fastcall GetObjectFromProgID(
        struct CSession **this,
        const OLECHAR *lpszProgID,
        BSTR pbstr,
        struct VAR *a4,
        int a5,
        unsigned __int16 *String2)
{
  unsigned __int16 *v6; // rsi
  _QWORD *v7; // r15
  HRESULT result; // eax
  int v12; // ebx
  UINT v13; // eax
  UINT v14; // r14d
  BOOL v15; // r12d
  DWORD v16; // ebx
  int v17; // eax
  bool v18; // sf
  __int64 v19; // rax
  struct CSession *v20; // rdx
  int v21; // eax
  SiteService *v22; // rsi
  void (*Release)(void); // rax
  bool v24; // zf
  __int64 v25; // rax
  DWORD nSize[2]; // [rsp+30h] [rbp-99h] BYREF
  IUnknown *ppunk; // [rsp+38h] [rbp-91h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-89h] BYREF
  __int64 v29; // [rsp+48h] [rbp-81h] BYREF
  struct IActiveScriptSiteWldp *v30; // [rsp+50h] [rbp-79h] BYREF
  struct VAR *v31; // [rsp+58h] [rbp-71h]
  _QWORD v32[4]; // [rsp+60h] [rbp-69h] BYREF
  CLSID clsid; // [rsp+80h] [rbp-49h] BYREF
  CHAR Buffer[16]; // [rsp+90h] [rbp-39h] BYREF
  WCHAR WideCharStr[16]; // [rsp+A0h] [rbp-29h] BYREF

  v6 = String2;
  v7 = 0;
  v31 = a4;
  if ( !lpszProgID || (unsigned int)((*((_DWORD *)lpszProgID - 1) >> 1) - 1) > 0xF7 )
    return -2146828283;
  clsid = 0;
  if ( !(unsigned int)COleScript::InSafeMode((COleScript *)this, 0) && CLSIDFromProgIDEx(lpszProgID, &clsid) >= 0
    || (result = CLSIDFromProgID(lpszProgID, &clsid), result >= 0) )
  {
    v30 = 0;
    if ( (int)COleScript::GetActiveScriptSiteWldp((COleScript *)this, &v30) >= 0 )
    {
      nSize[0] = 0;
      v12 = (*(__int64 (__fastcall **)(struct IActiveScriptSiteWldp *, CLSID *, DWORD *))(*(_QWORD *)v30 + 32LL))(
              v30,
              &clsid,
              nSize);
      if ( v12 >= 0 && !nSize[0] )
        v12 = -2146827859;
      (*(void (__fastcall **)(struct IActiveScriptSiteWldp *))(*(_QWORD *)v30 + 16LL))(v30);
      if ( v12 < 0 )
        return v12;
    }
    if ( (unsigned int)IsProhibitedUnsafeExtension(&clsid) )
      return -2146827859;
    ppunk = 0;
    v13 = SysStringLen(pbstr);
    v14 = v13;
    if ( v13 || !a5 )
    {
      v15 = v13 != 0;
      if ( (unsigned int)COleScript::CanCreateObject((COleScript *)this, &clsid) )
      {
        v32[0] = 0;
        v32[1] = String2;
        v16 = 21;
        v32[2] = 0;
        v32[3] = 0;
        v17 = COleScript::InSafeMode((COleScript *)this, 0);
        if ( String2 )
        {
          if ( v17 )
            return -2146827859;
          nSize[0] = 16;
          if ( !GetComputerNameA(Buffer, nSize) || !MultiByteToWideChar(0, 0, Buffer, -1, WideCharStr, 16) )
            goto LABEL_27;
          while ( *v6 == 92 )
            ++v6;
          if ( _wcsicmp(WideCharStr, v6) )
          {
LABEL_27:
            v7 = v32;
            v16 = 16;
          }
        }
        else if ( v17 )
        {
          v16 = 5;
        }
        ppv = 0;
        v29 = 0;
        result = CoGetClassObject(&clsid, v16, v7, &IID_IClassFactory, &ppv);
        if ( result < 0 )
          return result;
        v18 = (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IClassFactory3, &v29) < 0;
        v19 = *(_QWORD *)ppv;
        if ( v18 )
        {
          v12 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, IUnknown **))(v19 + 24))(
                  ppv,
                  0,
                  &IID_IUnknown,
                  &ppunk);
          Release = *(void (**)(void))(*(_QWORD *)ppv + 16LL);
          if ( v12 < 0 )
          {
LABEL_38:
            Release();
            return v12;
          }
          Release();
        }
        else
        {
          (*(void (**)(void))(v19 + 16))();
          v20 = this[84];
          *(_QWORD *)nSize = 0;
          v21 = SiteService::Create((struct SiteService **)nSize, v20);
          v22 = *(SiteService **)nSize;
          v12 = v21;
          if ( v21 < 0
            || (v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, GUID *, IUnknown **))(*(_QWORD *)v29 + 40LL))(
                        v29,
                        *(_QWORD *)nSize,
                        0,
                        &IID_IUnknown,
                        &ppunk),
                v12 < 0) )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
            if ( v22 )
              SiteService::Release(v22);
            return v12;
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          SiteService::Release(v22);
        }
        if ( (unsigned int)COleScript::CanObjectRun((COleScript *)this, &clsid, ppunk, v15) )
        {
          if ( v14 )
          {
            *(_QWORD *)nSize = 0;
            if ( ((__int64 (__fastcall *)(IUnknown *, GUID *, DWORD *))ppunk->lpVtbl->QueryInterface)(
                   ppunk,
                   &IID_IPersistFile,
                   nSize) < 0 )
            {
              v12 = -2146827856;
              goto LABEL_51;
            }
            v24 = (unsigned int)COleScript::CanObjectPersistFromURL((COleScript *)this, pbstr) == 0;
            v25 = **(_QWORD **)nSize;
            if ( v24 )
            {
              (*(void (**)(void))(v25 + 16))();
              ((void (__fastcall *)(IUnknown *))ppunk->lpVtbl->Release)(ppunk);
              return -2146827859;
            }
            v12 = (*(__int64 (__fastcall **)(_QWORD, BSTR, _QWORD))(v25 + 40))(*(_QWORD *)nSize, pbstr, 0);
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)nSize + 16LL))(*(_QWORD *)nSize);
            if ( v12 == 1 )
              v12 = -2146827859;
          }
          if ( v12 < 0 )
          {
LABEL_51:
            Release = (void (*)(void))ppunk->lpVtbl->Release;
            goto LABEL_38;
          }
LABEL_50:
          v12 = PrepareObject(this[84], (struct COleScript *)this, ppunk, v31);
          goto LABEL_51;
        }
        ((void (__fastcall *)(IUnknown *))ppunk->lpVtbl->Release)(ppunk);
      }
    }
    else if ( !(unsigned int)COleScript::InSafeMode((COleScript *)this, 0) )
    {
      result = GetActiveObject(&clsid, 0, &ppunk);
      if ( result < 0 )
        return result;
      goto LABEL_50;
    }
    return -2146827859;
  }
  return result;
}

```

## disassembly

```asm
0x1800520c0  push    rbp
0x1800520c2  push    rbx
0x1800520c3  push    rsi
0x1800520c4  push    rdi
0x1800520c5  push    r12
0x1800520c7  push    r13
0x1800520c9  push    r14
0x1800520cb  push    r15
0x1800520cd  lea     rbp, [rsp-0Fh]
0x1800520d2  sub     rsp, 0D8h
0x1800520d9  mov     rax, cs:__security_cookie
0x1800520e0  xor     rax, rsp
0x1800520e3  mov     [rbp+47h+var_50], rax
0x1800520e7  mov     rsi, [rbp+47h+String2]
0x1800520eb  xor     r15d, r15d
0x1800520ee  mov     [rbp+47h+var_B8], r9
0x1800520f2  mov     r13, r8
0x1800520f5  mov     rbx, rdx
0x1800520f8  mov     rdi, rcx
0x1800520fb  test    rdx, rdx
0x1800520fe  jz      loc_180052539
0x180052104  mov     eax, [rdx-4]
0x180052107  shr     eax, 1
0x180052109  dec     eax
0x18005210b  cmp     eax, 0F7h
0x180052110  ja      loc_180052539
0x180052116  xorps   xmm0, xmm0
0x180052119  xor     edx, edx; struct _GUID *
0x18005211b  movups  xmmword ptr [rbp+47h+clsid.Data1], xmm0
0x18005211f  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x180052124  test    eax, eax
0x180052126  jnz     short loc_18005213F
0x180052128  lea     rdx, [rbp+47h+clsid]; lpclsid
0x18005212c  mov     rcx, rbx; lpszProgID
0x18005212f  call    cs:__imp_CLSIDFromProgIDEx
0x180052136  nop     dword ptr [rax+rax+00h]
0x18005213b  test    eax, eax
0x18005213d  jns     short loc_18005215A
0x18005213f  lea     rdx, [rbp+47h+clsid]; lpclsid
0x180052143  mov     rcx, rbx; lpszProgID
0x180052146  call    cs:__imp_CLSIDFromProgID
0x18005214d  nop     dword ptr [rax+rax+00h]
0x180052152  test    eax, eax
0x180052154  js      loc_18005253E
0x18005215a  lea     rdx, [rbp+47h+var_C0]; struct IActiveScriptSiteWldp **
0x18005215e  mov     [rbp+47h+var_C0], r15
0x180052162  mov     rcx, rdi; this
0x180052165  call    ?GetActiveScriptSiteWldp@COleScript@@QEAAJPEAPEAVIActiveScriptSiteWldp@@@Z; COleScript::GetActiveScriptSiteWldp(IActiveScriptSiteWldp * *)
0x18005216a  test    eax, eax
0x18005216c  js      short loc_1800521BD
0x18005216e  mov     rcx, [rbp+47h+var_C0]
0x180052172  lea     r8, [rsp+110h+nSize]
0x180052177  mov     [rsp+110h+nSize], r15d
0x18005217c  lea     rdx, [rbp+47h+clsid]
0x180052180  mov     rax, [rcx]
0x180052183  mov     rax, [rax+20h]
0x180052187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005218c  mov     ebx, eax
0x18005218e  test    eax, eax
0x180052190  js      short loc_18005219F
0x180052192  cmp     [rsp+110h+nSize], r15d
0x180052197  mov     eax, 800A01ADh
0x18005219c  cmovz   ebx, eax
0x18005219f  mov     rdx, [rbp+47h+var_C0]
0x1800521a3  mov     rcx, [rdx]
0x1800521a6  mov     rax, [rcx+10h]
0x1800521aa  mov     rcx, rdx
0x1800521ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800521b2  test    ebx, ebx
0x1800521b4  jns     short loc_1800521BD
0x1800521b6  mov     eax, ebx
0x1800521b8  jmp     loc_18005253E
0x1800521bd  lea     rcx, [rbp+47h+clsid]
0x1800521c1  call    IsProhibitedUnsafeExtension
0x1800521c6  test    eax, eax
0x1800521c8  jnz     loc_180052469
0x1800521ce  mov     rcx, r13; pbstr
0x1800521d1  mov     [rsp+110h+ppunk], r15
0x1800521d6  call    cs:__imp_SysStringLen
0x1800521dd  nop     dword ptr [rax+rax+00h]
0x1800521e2  mov     r14d, eax
0x1800521e5  test    eax, eax
0x1800521e7  jnz     short loc_180052225
0x1800521e9  cmp     [rbp+47h+arg_20], r15d
0x1800521ed  jz      short loc_180052225
0x1800521ef  xor     edx, edx; struct _GUID *
0x1800521f1  mov     rcx, rdi; this
0x1800521f4  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x1800521f9  test    eax, eax
0x1800521fb  jnz     loc_180052469
0x180052201  lea     r8, [rsp+110h+ppunk]; ppunk
0x180052206  xor     edx, edx; pvReserved
0x180052208  lea     rcx, [rbp+47h+clsid]; rclsid
0x18005220c  call    cs:__imp_GetActiveObject
0x180052213  nop     dword ptr [rax+rax+00h]
0x180052218  test    eax, eax
0x18005221a  jns     loc_180052507
0x180052220  jmp     loc_18005253E
0x180052225  test    r14d, r14d
0x180052228  lea     rdx, [rbp+47h+clsid]; struct _GUID *
0x18005222c  mov     r12d, r15d
0x18005222f  mov     rcx, rdi; this
0x180052232  setnz   r12b
0x180052236  call    ?CanCreateObject@COleScript@@QEAAHAEBU_GUID@@@Z; COleScript::CanCreateObject(_GUID const &)
0x18005223b  test    eax, eax
0x18005223d  jz      loc_180052469
0x180052243  xor     edx, edx; struct _GUID *
0x180052245  mov     [rbp+47h+var_B0], r15
0x180052249  mov     rcx, rdi; this
0x18005224c  mov     [rbp+47h+var_A8], rsi
0x180052250  mov     ebx, 15h
0x180052255  mov     [rbp+47h+var_A0], r15
0x180052259  mov     [rbp+47h+var_98], r15
0x18005225d  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x180052262  test    rsi, rsi
0x180052265  jz      loc_1800522F1
0x18005226b  test    eax, eax
0x18005226d  jnz     loc_180052469
0x180052273  lea     rdx, [rsp+110h+nSize]; nSize
0x180052278  mov     [rsp+110h+nSize], 10h
0x180052280  lea     rcx, [rbp+47h+Buffer]; lpBuffer
0x180052284  call    cs:__imp_GetComputerNameA
0x18005228b  nop     dword ptr [rax+rax+00h]
0x180052290  test    eax, eax
0x180052292  jz      short loc_1800522E6
0x180052294  lea     rax, [rbp+47h+WideCharStr]
0x180052298  mov     [rsp+110h+cchWideChar], 10h; cchWideChar
0x1800522a0  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800522a4  mov     [rsp+110h+lpWideCharStr], rax; lpWideCharStr
0x1800522a9  lea     r8, [rbp+47h+Buffer]; lpMultiByteStr
0x1800522ad  xor     edx, edx; dwFlags
0x1800522af  xor     ecx, ecx; CodePage
0x1800522b1  call    cs:__imp_MultiByteToWideChar
0x1800522b8  nop     dword ptr [rax+rax+00h]
0x1800522bd  test    eax, eax
0x1800522bf  jz      short loc_1800522E6
0x1800522c1  lea     eax, [rbx+47h]
0x1800522c4  jmp     short loc_1800522CA
0x1800522c6  add     rsi, 2
0x1800522ca  cmp     ax, [rsi]
0x1800522cd  jz      short loc_1800522C6
0x1800522cf  mov     rdx, rsi; String2
0x1800522d2  lea     rcx, [rbp+47h+WideCharStr]; String1
0x1800522d6  call    cs:__imp__wcsicmp
0x1800522dd  nop     dword ptr [rax+rax+00h]
0x1800522e2  test    eax, eax
0x1800522e4  jz      short loc_1800522FB
0x1800522e6  lea     r15, [rbp+47h+var_B0]
0x1800522ea  mov     ebx, 10h
0x1800522ef  jmp     short loc_1800522FB
0x1800522f1  test    eax, eax
0x1800522f3  mov     ecx, 5
0x1800522f8  cmovnz  ebx, ecx
0x1800522fb  lea     rax, [rsp+110h+ppv]
0x180052300  mov     [rsp+110h+ppv], 0
0x180052309  lea     r9, IID_IClassFactory; riid
0x180052310  mov     [rsp+110h+lpWideCharStr], rax; ppv
0x180052315  mov     r8, r15; pvReserved
0x180052318  mov     [rsp+110h+var_C8], 0
0x180052321  mov     edx, ebx; dwClsContext
0x180052323  lea     rcx, [rbp+47h+clsid]; rclsid
0x180052327  call    cs:__imp_CoGetClassObject
0x18005232e  nop     dword ptr [rax+rax+00h]
0x180052333  test    eax, eax
0x180052335  js      loc_18005253E
0x18005233b  mov     rcx, [rsp+110h+ppv]
0x180052340  lea     r8, [rsp+110h+var_C8]
0x180052345  lea     rdx, IID_IClassFactory3
0x18005234c  mov     rax, [rcx]
0x18005234f  mov     rax, [rax]
0x180052352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052357  mov     rcx, [rsp+110h+ppv]
0x18005235c  test    eax, eax
0x18005235e  mov     rax, [rcx]
0x180052361  js      loc_180052405
0x180052367  mov     rax, [rax+10h]
0x18005236b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052370  mov     rdx, [rdi+2A0h]; struct CSession *
0x180052377  lea     rcx, [rsp+110h+nSize]; struct SiteService **
0x18005237c  mov     qword ptr [rsp+110h+nSize], 0
0x180052385  call    ?Create@SiteService@@SAJPEAPEAV1@PEAVCSession@@@Z; SiteService::Create(SiteService * *,CSession *)
0x18005238a  mov     rsi, qword ptr [rsp+110h+nSize]
0x18005238f  mov     ebx, eax
0x180052391  test    eax, eax
0x180052393  js      short loc_1800523DE
0x180052395  mov     rcx, [rsp+110h+var_C8]
0x18005239a  lea     rdx, [rsp+110h+ppunk]
0x18005239f  mov     [rsp+110h+lpWideCharStr], rdx
0x1800523a4  lea     r9, IID_IUnknown
0x1800523ab  xor     r8d, r8d
0x1800523ae  mov     rdx, rsi
0x1800523b1  mov     rax, [rcx]
0x1800523b4  mov     rax, [rax+28h]
0x1800523b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800523bd  mov     ebx, eax
0x1800523bf  test    eax, eax
0x1800523c1  js      short loc_1800523DE
0x1800523c3  mov     rcx, [rsp+110h+var_C8]
0x1800523c8  mov     rax, [rcx]
0x1800523cb  mov     rax, [rax+10h]
0x1800523cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800523d4  mov     rcx, rsi; this
0x1800523d7  call    ?Release@SiteService@@UEAAKXZ; SiteService::Release(void)
0x1800523dc  jmp     short loc_18005243D
0x1800523de  mov     rcx, [rsp+110h+var_C8]
0x1800523e3  mov     rax, [rcx]
0x1800523e6  mov     rax, [rax+10h]
0x1800523ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800523ef  test    rsi, rsi
0x1800523f2  jz      loc_1800521B6
0x1800523f8  mov     rcx, rsi; this
0x1800523fb  call    ?Release@SiteService@@UEAAKXZ; SiteService::Release(void)
0x180052400  jmp     loc_1800521B6
0x180052405  mov     rax, [rax+18h]
0x180052409  lea     r9, [rsp+110h+ppunk]
0x18005240e  lea     r8, IID_IUnknown
0x180052415  xor     edx, edx
0x180052417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005241c  mov     rcx, [rsp+110h+ppv]
0x180052421  mov     ebx, eax
0x180052423  test    eax, eax
0x180052425  mov     rax, [rcx]
0x180052428  mov     rax, [rax+10h]
0x18005242c  jns     short loc_180052438
0x18005242e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052433  jmp     loc_1800521B6
0x180052438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005243d  mov     r8, [rsp+110h+ppunk]; struct IUnknown *
0x180052442  lea     rdx, [rbp+47h+clsid]; struct _GUID *
0x180052446  mov     r9d, r12d; int
0x180052449  mov     rcx, rdi; this
0x18005244c  call    ?CanObjectRun@COleScript@@QEAAHAEBU_GUID@@PEAUIUnknown@@H@Z; COleScript::CanObjectRun(_GUID const &,IUnknown *,int)
0x180052451  test    eax, eax
0x180052453  jnz     short loc_180052473
0x180052455  mov     rdx, [rsp+110h+ppunk]
0x18005245a  mov     rcx, [rdx]
0x18005245d  mov     rax, [rcx+10h]
0x180052461  mov     rcx, rdx
0x180052464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052469  mov     eax, 800A01ADh
0x18005246e  jmp     loc_18005253E
0x180052473  test    r14d, r14d
0x180052476  jz      loc_180052503
0x18005247c  mov     rcx, [rsp+110h+ppunk]
0x180052481  lea     r8, [rsp+110h+nSize]
0x180052486  mov     qword ptr [rsp+110h+nSize], 0
0x18005248f  lea     rdx, IID_IPersistFile
0x180052496  mov     rax, [rcx]
0x180052499  mov     rax, [rax]
0x18005249c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800524a1  test    eax, eax
0x1800524a3  js      loc_180052532
0x1800524a9  mov     rdx, r13; unsigned __int16 *
0x1800524ac  mov     rcx, rdi; this
0x1800524af  call    ?CanObjectPersistFromURL@COleScript@@QEAAHPEAG@Z; COleScript::CanObjectPersistFromURL(ushort *)
0x1800524b4  mov     rcx, qword ptr [rsp+110h+nSize]
0x1800524b9  test    eax, eax
0x1800524bb  mov     rax, [rcx]
0x1800524be  jnz     short loc_1800524D7
0x1800524c0  mov     rax, [rax+10h]
0x1800524c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800524c9  mov     rcx, [rsp+110h+ppunk]
0x1800524ce  mov     rax, [rcx]
0x1800524d1  mov     rax, [rax+10h]
0x1800524d5  jmp     short loc_180052464
0x1800524d7  mov     rax, [rax+28h]
0x1800524db  xor     r8d, r8d
0x1800524de  mov     rdx, r13
0x1800524e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800524e6  mov     rcx, qword ptr [rsp+110h+nSize]
0x1800524eb  mov     ebx, eax
0x1800524ed  mov     rax, [rcx]
0x1800524f0  mov     rax, [rax+10h]
0x1800524f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800524f9  cmp     ebx, 1
0x1800524fc  jnz     short loc_180052503
0x1800524fe  mov     ebx, 800A01ADh
0x180052503  test    ebx, ebx
0x180052505  js      short loc_180052521
0x180052507  mov     r9, [rbp+47h+var_B8]; struct VAR *
0x18005250b  mov     rdx, rdi; struct COleScript *
0x18005250e  mov     r8, [rsp+110h+ppunk]; struct IUnknown *
0x180052513  mov     rcx, [rdi+2A0h]; struct CSession *
0x18005251a  call    ?PrepareObject@@YAJPEAVCSession@@PEAVCOleScript@@PEAUIUnknown@@PEAVVAR@@@Z; PrepareObject(CSession *,COleScript *,IUnknown *,VAR *)
0x18005251f  mov     ebx, eax
0x180052521  mov     rcx, [rsp+110h+ppunk]
0x180052526  mov     rax, [rcx]
0x180052529  mov     rax, [rax+10h]
0x18005252d  jmp     loc_18005242E
0x180052532  mov     ebx, 800A01B0h
0x180052537  jmp     short loc_180052521
0x180052539  mov     eax, 800A0005h
0x18005253e  mov     rcx, [rbp+47h+var_50]
0x180052542  xor     rcx, rsp; StackCookie
0x180052545  call    __security_check_cookie
0x18005254a  add     rsp, 0D8h
0x180052551  pop     r15
0x180052553  pop     r14
0x180052555  pop     r13
0x180052557  pop     r12
  ... truncated ...
```
