# CHostObj::GetObjectA(ushort *,ushort *,ushort *,IDispatch * *)

- ea: `0x140012360`
- end: `0x1400126cb`
- name: `?GetObjectA@CHostObj@@UEAAJPEAG00PEAPEAUIDispatch@@@Z`
- size: `875`
- prototype: `__int64 __usercall@<rax>(CHostObj *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, struct IDispatch **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1400090b4`
- `0x14000ccb8`
- `0x14000d2e0`
- `0x14000dcd4`
- `0x140011bdc`
- `0x140011c00`
- `0x1400121f0`
- `0x140012360`
- `0x1400161d0`
- `0x140017010`

## import_xrefs

- `ole32!MkParseDisplayName` at `0x1400125d6`
- `ole32!MkParseDisplayName` at `0x1400125d6`
- `ole32!CreateBindCtx` at `0x140012531`
- `ole32!CreateBindCtx` at `0x140012531`

## string_xrefs

- `0x1400123c3`: `WScript.CreateObject`
- `0x140012686`: `WScript.CreateObject`

## pseudocode

```c
__int64 __fastcall CHostObj::GetObjectA(
        CHost **this,
        unsigned __int64 a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        struct IDispatch **a5)
{
  __int64 result; // rax
  HRESULT v10; // edi
  int v11; // ebx
  __int64 v12; // rdx
  struct IMoniker *v13; // rcx
  _WORD *i; // rax
  HRESULT v15; // eax
  int v16; // eax
  LPBC ppbc; // [rsp+30h] [rbp-D0h] BYREF
  LPMONIKER ppmk; // [rsp+38h] [rbp-C8h] BYREF
  struct IDispatch *v19; // [rsp+40h] [rbp-C0h] BYREF
  ULONG pchEaten; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v21; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID v22; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR szUserName[264]; // [rsp+70h] [rbp-90h] BYREF

  if ( !a5 )
    return 2147500035LL;
  if ( (unsigned int)CHost::WldpIsEnforcementOn(this[16]) )
  {
    Signal_Exception(&IID_IHost, L"WScript.CreateObject", 0xC1Fu, a3);
    return 2147942405LL;
  }
  if ( a2 )
    a2 &= -(__int64)(*(_WORD *)a2 != 0);
  if ( a4 )
    a4 &= -(__int64)(*(_WORD *)a4 != 0);
  if ( a3 )
    a3 &= -(__int64)(*(_WORD *)a3 != 0);
  v19 = 0;
  v22 = 0;
  if ( a3 )
  {
    ppbc = 0;
    result = CHostObj::CreateObjectHelper((CHostObj *)this, (unsigned __int16 *)a3, &v22, (LPVOID *)&ppbc);
    if ( (int)result < 0 )
      return result;
    if ( a2 )
    {
      ppmk = 0;
      v10 = ((__int64 (__fastcall *)(LPBC, GUID *, LPMONIKER *))ppbc->lpVtbl->QueryInterface)(
              ppbc,
              &IID_IPersistFile,
              &ppmk);
      if ( v10 < 0 )
      {
        ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
        return (unsigned int)v10;
      }
      v11 = ((__int64 (__fastcall *)(LPMONIKER, unsigned __int64, __int64))ppmk->lpVtbl->Load)(ppmk, a2, 2);
      ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
      if ( v11 < 0 )
      {
        ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
        return (unsigned int)v11;
      }
    }
    v11 = ((__int64 (__fastcall *)(LPBC, GUID *, struct IDispatch **))ppbc->lpVtbl->QueryInterface)(
            ppbc,
            &IID_IDispatch,
            &v19);
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
    goto LABEL_40;
  }
  if ( !a2 )
    return 2147942487LL;
  ppbc = 0;
  v10 = CreateBindCtx(0, &ppbc);
  if ( v10 < 0 )
  {
    COMPtr<IBindCtx>::~COMPtr<IBindCtx>(&ppbc);
    return (unsigned int)v10;
  }
  ppmk = 0;
  for ( i = (_WORD *)a2; ; ++i )
  {
    if ( !*i )
      goto LABEL_32;
    if ( *i == 58 )
      break;
  }
  if ( !i || (((unsigned __int64)i - a2) & 0xFFFFFFFFFFFFFFFEuLL) == 2 )
  {
LABEL_32:
    v21 = 0;
    v11 = FileNameToFullPathName((LPCWCH)a2, v12, szUserName, &v21);
    if ( v11 < 0 )
    {
LABEL_33:
      COMPtr<IBindCtx>::~COMPtr<IBindCtx>(&ppmk);
      COMPtr<IBindCtx>::~COMPtr<IBindCtx>(&ppbc);
      return (unsigned int)v11;
    }
    pchEaten = 0;
    v15 = MkParseDisplayName(ppbc, szUserName, &pchEaten, &ppmk);
  }
  else
  {
    v15 = CreateAMoniker(v13, (const unsigned __int16 *)a2, &ppmk);
  }
  v11 = v15;
  if ( v15 < 0 )
    goto LABEL_33;
  v16 = ((__int64 (__fastcall *)(LPMONIKER, LPBC, _QWORD, GUID *, struct IDispatch **))ppmk->lpVtbl->BindToObject)(
          ppmk,
          ppbc,
          0,
          &IID_IDispatch,
          &v19);
  v11 = v16;
  if ( v16 == -2146697211 )
  {
    v11 = -2147221014;
    goto LABEL_33;
  }
  if ( v16 < 0 )
    goto LABEL_33;
  v11 = ((__int64 (__fastcall *)(LPMONIKER, struct _GUID *))ppmk->lpVtbl->GetClassID)(ppmk, &v22);
  COMPtr<IBindCtx>::~COMPtr<IBindCtx>(&ppmk);
  COMPtr<IBindCtx>::~COMPtr<IBindCtx>(&ppbc);
LABEL_40:
  if ( v11 < 0 )
    return (unsigned int)v11;
  if ( a4 && (int)ConnectObject(&v22, v19, a4) < 0 )
  {
    ((void (__fastcall *)(struct IDispatch *))v19->lpVtbl->Release)(v19);
    Signal_Exception(&IID_IHost, L"WScript.CreateObject", 0xC1Eu);
    return 2147614729LL;
  }
  else
  {
    *a5 = v19;
    return 0;
  }
}

```

## disassembly

```asm
0x140012360  push    rbp
0x140012362  push    rbx
0x140012363  push    rsi
0x140012364  push    rdi
0x140012365  push    r12
0x140012367  push    r14
0x140012369  push    r15
0x14001236b  lea     rbp, [rsp-190h]
0x140012373  sub     rsp, 290h
0x14001237a  mov     rax, cs:__security_cookie
0x140012381  xor     rax, rsp
0x140012384  mov     [rbp+1C0h+var_40], rax
0x14001238b  mov     r15, [rbp+1C0h+arg_20]
0x140012392  xor     r12d, r12d
0x140012395  mov     rsi, r9
0x140012398  mov     rdi, r8
0x14001239b  mov     rbx, rdx
0x14001239e  mov     r14, rcx
0x1400123a1  test    r15, r15
0x1400123a4  jnz     short loc_1400123B0
0x1400123a6  mov     eax, 80004003h
0x1400123ab  jmp     loc_1400126AA
0x1400123b0  mov     rcx, [rcx+80h]; this
0x1400123b7  call    ?WldpIsEnforcementOn@CHost@@QEAAHXZ; CHost::WldpIsEnforcementOn(void)
0x1400123bc  test    eax, eax
0x1400123be  jz      short loc_1400123E6
0x1400123c0  mov     r9, rdi
0x1400123c3  lea     rdx, aWscriptCreateo; "WScript.CreateObject"
0x1400123ca  mov     r8d, 0C1Fh; unsigned int
0x1400123d0  lea     rcx, IID_IHost; struct _GUID *
0x1400123d7  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x1400123dc  mov     eax, 80070005h
0x1400123e1  jmp     loc_1400126AA
0x1400123e6  test    rbx, rbx
0x1400123e9  jz      short loc_1400123F7
0x1400123eb  movzx   eax, word ptr [rbx]
0x1400123ee  neg     ax
0x1400123f1  sbb     rcx, rcx
0x1400123f4  and     rbx, rcx
0x1400123f7  test    rsi, rsi
0x1400123fa  jz      short loc_140012408
0x1400123fc  movzx   eax, word ptr [rsi]
0x1400123ff  neg     ax
0x140012402  sbb     rcx, rcx
0x140012405  and     rsi, rcx
0x140012408  test    rdi, rdi
0x14001240b  jz      short loc_140012419
0x14001240d  movzx   eax, word ptr [rdi]
0x140012410  neg     ax
0x140012413  sbb     rdx, rdx
0x140012416  and     rdi, rdx
0x140012419  mov     [rsp+2C0h+var_280], r12
0x14001241e  xorps   xmm0, xmm0
0x140012421  movups  xmmword ptr [rsp+2C0h+var_268.Data1], xmm0
0x140012426  test    rdi, rdi
0x140012429  jz      loc_140012516
0x14001242f  lea     r9, [rsp+2C0h+ppbc]; struct IUnknown **
0x140012434  mov     [rsp+2C0h+ppbc], r12
0x140012439  lea     r8, [rsp+2C0h+var_268]; struct _GUID *
0x14001243e  mov     rdx, rdi; unsigned __int16 *
0x140012441  mov     rcx, r14; this
0x140012444  call    ?CreateObjectHelper@CHostObj@@IEAAJPEAGPEAU_GUID@@PEAPEAUIUnknown@@@Z; CHostObj::CreateObjectHelper(ushort *,_GUID *,IUnknown * *)
0x140012449  test    eax, eax
0x14001244b  js      loc_1400126AA
0x140012451  test    rbx, rbx
0x140012454  jz      loc_1400124E2
0x14001245a  mov     rcx, [rsp+2C0h+ppbc]
0x14001245f  lea     r8, [rsp+2C0h+ppmk]
0x140012464  mov     [rsp+2C0h+ppmk], r12
0x140012469  lea     rdx, IID_IPersistFile
0x140012470  mov     rax, [rcx]
0x140012473  mov     rax, [rax]
0x140012476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001247b  mov     edi, eax
0x14001247d  test    eax, eax
0x14001247f  jns     short loc_140012499
0x140012481  mov     rcx, [rsp+2C0h+ppbc]
0x140012486  mov     rdx, [rcx]
0x140012489  mov     rax, [rdx+10h]
0x14001248d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012492  mov     eax, edi
0x140012494  jmp     loc_1400126AA
0x140012499  mov     rcx, [rsp+2C0h+ppmk]
0x14001249e  mov     r8d, 2
0x1400124a4  mov     rdx, rbx
0x1400124a7  mov     rax, [rcx]
0x1400124aa  mov     rax, [rax+28h]
0x1400124ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400124b3  mov     rcx, [rsp+2C0h+ppmk]
0x1400124b8  mov     ebx, eax
0x1400124ba  mov     rdx, [rcx]
0x1400124bd  mov     rax, [rdx+10h]
0x1400124c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400124c6  test    ebx, ebx
0x1400124c8  jns     short loc_1400124E2
0x1400124ca  mov     rcx, [rsp+2C0h+ppbc]
0x1400124cf  mov     rdx, [rcx]
0x1400124d2  mov     rax, [rdx+10h]
0x1400124d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400124db  mov     eax, ebx
0x1400124dd  jmp     loc_1400126AA
0x1400124e2  mov     rcx, [rsp+2C0h+ppbc]
0x1400124e7  lea     r8, [rsp+2C0h+var_280]
0x1400124ec  lea     rdx, IID_IDispatch
0x1400124f3  mov     rax, [rcx]
0x1400124f6  mov     rax, [rax]
0x1400124f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400124fe  mov     rcx, [rsp+2C0h+ppbc]
0x140012503  mov     ebx, eax
0x140012505  mov     rdx, [rcx]
0x140012508  mov     rax, [rdx+10h]
0x14001250c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012511  jmp     loc_14001264C
0x140012516  test    rbx, rbx
0x140012519  jnz     short loc_140012525
0x14001251b  mov     eax, 80070057h
0x140012520  jmp     loc_1400126AA
0x140012525  lea     rdx, [rsp+2C0h+ppbc]; ppbc
0x14001252a  mov     [rsp+2C0h+ppbc], r12
0x14001252f  xor     ecx, ecx; reserved
0x140012531  call    cs:__imp_CreateBindCtx
0x140012537  mov     edi, eax
0x140012539  test    eax, eax
0x14001253b  jns     short loc_14001254C
0x14001253d  lea     rcx, [rsp+2C0h+ppbc]
0x140012542  call    ??1?$COMPtr@UIBindCtx@@@@QEAA@XZ; COMPtr<IBindCtx>::~COMPtr<IBindCtx>(void)
0x140012547  jmp     loc_140012492
0x14001254c  mov     [rsp+2C0h+ppmk], r12
0x140012551  mov     rax, rbx
0x140012554  cmp     [rax], r12w
0x140012558  jz      short loc_140012587
0x14001255a  cmp     word ptr [rax], 3Ah ; ':'
0x14001255e  jz      short loc_140012566
0x140012560  add     rax, 2
0x140012564  jmp     short loc_140012554
0x140012566  test    rax, rax
0x140012569  jz      short loc_140012587
0x14001256b  sub     rax, rbx
0x14001256e  and     rax, 0FFFFFFFFFFFFFFFEh
0x140012572  cmp     rax, 2
0x140012576  jz      short loc_140012587
0x140012578  lea     r8, [rsp+2C0h+ppmk]; struct IMoniker **
0x14001257d  mov     rdx, rbx; unsigned __int16 *
0x140012580  call    ?CreateAMoniker@@YAJPEAUIMoniker@@PEBGPEAPEAU1@@Z; CreateAMoniker(IMoniker *,ushort const *,IMoniker * *)
0x140012585  jmp     short loc_1400125DC
0x140012587  lea     r9, [rsp+2C0h+var_270]; unsigned __int16 **
0x14001258c  mov     [rsp+2C0h+var_270], r12
0x140012591  lea     r8, [rsp+2C0h+szUserName]; unsigned __int16 *
0x140012596  mov     rcx, rbx; lpWideCharStr
0x140012599  call    ?FileNameToFullPathName@@YAJPEBGKPEAGPEAPEAG@Z; FileNameToFullPathName(ushort const *,ulong,ushort *,ushort * *)
0x14001259e  mov     ebx, eax
0x1400125a0  test    eax, eax
0x1400125a2  jns     short loc_1400125BD
0x1400125a4  lea     rcx, [rsp+2C0h+ppmk]
0x1400125a9  call    ??1?$COMPtr@UIBindCtx@@@@QEAA@XZ; COMPtr<IBindCtx>::~COMPtr<IBindCtx>(void)
0x1400125ae  lea     rcx, [rsp+2C0h+ppbc]
0x1400125b3  call    ??1?$COMPtr@UIBindCtx@@@@QEAA@XZ; COMPtr<IBindCtx>::~COMPtr<IBindCtx>(void)
0x1400125b8  jmp     loc_1400124DB
0x1400125bd  mov     rcx, [rsp+2C0h+ppbc]; pbc
0x1400125c2  lea     r9, [rsp+2C0h+ppmk]; ppmk
0x1400125c7  lea     r8, [rsp+2C0h+pchEaten]; pchEaten
0x1400125cc  mov     [rsp+2C0h+pchEaten], r12d
0x1400125d1  lea     rdx, [rsp+2C0h+szUserName]; szUserName
0x1400125d6  call    cs:__imp_MkParseDisplayName
0x1400125dc  mov     ebx, eax
0x1400125de  test    eax, eax
0x1400125e0  js      short loc_1400125A4
0x1400125e2  mov     rcx, [rsp+2C0h+ppmk]
0x1400125e7  lea     rdx, [rsp+2C0h+var_280]
0x1400125ec  mov     [rsp+2C0h+var_2A0], rdx
0x1400125f1  lea     r9, IID_IDispatch
0x1400125f8  mov     rdx, [rsp+2C0h+ppbc]
0x1400125fd  xor     r8d, r8d
0x140012600  mov     rax, [rcx]
0x140012603  mov     rax, [rax+40h]
0x140012607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001260c  mov     ebx, eax
0x14001260e  cmp     eax, 800C0005h
0x140012613  jnz     short loc_14001261C
0x140012615  mov     ebx, 800401EAh
0x14001261a  jmp     short loc_1400125A4
0x14001261c  test    eax, eax
0x14001261e  js      short loc_1400125A4
0x140012620  mov     rcx, [rsp+2C0h+ppmk]
0x140012625  lea     rdx, [rsp+2C0h+var_268]
0x14001262a  mov     rax, [rcx]
0x14001262d  mov     rax, [rax+18h]
0x140012631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012636  lea     rcx, [rsp+2C0h+ppmk]
0x14001263b  mov     ebx, eax
0x14001263d  call    ??1?$COMPtr@UIBindCtx@@@@QEAA@XZ; COMPtr<IBindCtx>::~COMPtr<IBindCtx>(void)
0x140012642  lea     rcx, [rsp+2C0h+ppbc]
0x140012647  call    ??1?$COMPtr@UIBindCtx@@@@QEAA@XZ; COMPtr<IBindCtx>::~COMPtr<IBindCtx>(void)
0x14001264c  test    ebx, ebx
0x14001264e  js      loc_1400124DB
0x140012654  test    rsi, rsi
0x140012657  jz      short loc_1400126A0
0x140012659  mov     rdx, [rsp+2C0h+var_280]
0x14001265e  lea     rcx, [rsp+2C0h+var_268]
0x140012663  mov     r8, rsi
0x140012666  call    ConnectObject
0x14001266b  test    eax, eax
0x14001266d  jns     short loc_1400126A0
0x14001266f  mov     rcx, [rsp+2C0h+var_280]
0x140012674  mov     rax, [rcx]
0x140012677  mov     rax, [rax+10h]
0x14001267b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012680  mov     r8d, 0C1Eh; unsigned int
0x140012686  lea     rdx, aWscriptCreateo; "WScript.CreateObject"
0x14001268d  lea     rcx, IID_IHost; struct _GUID *
0x140012694  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x140012699  mov     eax, 80020009h
0x14001269e  jmp     short loc_1400126AA
0x1400126a0  mov     rax, [rsp+2C0h+var_280]
0x1400126a5  mov     [r15], rax
0x1400126a8  xor     eax, eax
0x1400126aa  mov     rcx, [rbp+1C0h+var_40]
0x1400126b1  xor     rcx, rsp; StackCookie
0x1400126b4  call    __security_check_cookie
0x1400126b9  add     rsp, 290h
0x1400126c0  pop     r15
0x1400126c2  pop     r14
0x1400126c4  pop     r12
0x1400126c6  pop     rdi
0x1400126c7  pop     rsi
0x1400126c8  pop     rbx
0x1400126c9  pop     rbp
0x1400126ca  retn
```
