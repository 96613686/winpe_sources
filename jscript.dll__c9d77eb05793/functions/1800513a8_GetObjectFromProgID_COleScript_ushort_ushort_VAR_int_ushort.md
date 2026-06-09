# GetObjectFromProgID(COleScript *,ushort *,ushort *,VAR *,int,ushort *)

- ea: `0x1800513a8`
- end: `0x180051812`
- name: `?GetObjectFromProgID@@YAJPEAVCOleScript@@PEAG1PEAVVAR@@H1@Z`
- size: `1130`
- prototype: `__int64 __usercall@<rax>(struct COleScript *this@<rcx>, LPCOLESTR lpszProgID@<rdx>, BSTR pbstr@<r8>, struct VAR *@<r9>, int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180031f24`
- `0x18005b430`

## callees

- `0x18004c72c`
- `0x18004ea20`
- `0x180050b20`
- `0x1800513a8`
- `0x180073a98`
- `0x1800772ac`
- `0x180077344`
- `0x180077410`
- `0x1800869dc`
- `0x180091b28`
- `0x1800942d0`
- `0x180096010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180051596`
- `msvcrt!_wcsicmp` at `0x180051596`
- `OLEAUT32!__imp_SysStringLen` at `0x1800514b2`
- `OLEAUT32!__imp_SysStringLen` at `0x1800514b2`
- `OLEAUT32!__imp_GetActiveObject` at `0x1800514e2`
- `OLEAUT32!__imp_GetActiveObject` at `0x1800514e2`
- `KERNEL32!GetComputerNameA` at `0x180051550`
- `KERNEL32!GetComputerNameA` at `0x180051550`
- `KERNEL32!MultiByteToWideChar` at `0x180051577`
- `KERNEL32!MultiByteToWideChar` at `0x180051577`
- `ole32!CoGetClassObject` at `0x1800515e1`
- `ole32!CoGetClassObject` at `0x1800515e1`
- `ole32!CLSIDFromProgID` at `0x180051428`
- `ole32!CLSIDFromProgID` at `0x180051428`
- `ole32!CLSIDFromProgIDEx` at `0x180051417`
- `ole32!CLSIDFromProgIDEx` at `0x180051417`

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
0x1800513a8  push    rbp
0x1800513aa  push    rbx
0x1800513ab  push    rsi
0x1800513ac  push    rdi
0x1800513ad  push    r12
0x1800513af  push    r13
0x1800513b1  push    r14
0x1800513b3  push    r15
0x1800513b5  lea     rbp, [rsp-0Fh]
0x1800513ba  sub     rsp, 0D8h
0x1800513c1  mov     rax, cs:__security_cookie
0x1800513c8  xor     rax, rsp
0x1800513cb  mov     [rbp+47h+var_50], rax
0x1800513cf  mov     rsi, [rbp+47h+String2]
0x1800513d3  xor     r15d, r15d
0x1800513d6  mov     [rbp+47h+var_B8], r9
0x1800513da  mov     r13, r8
0x1800513dd  mov     rbx, rdx
0x1800513e0  mov     rdi, rcx
0x1800513e3  test    rdx, rdx
0x1800513e6  jz      loc_1800517ED
0x1800513ec  mov     eax, [rdx-4]
0x1800513ef  shr     eax, 1
0x1800513f1  dec     eax
0x1800513f3  cmp     eax, 0F7h
0x1800513f8  ja      loc_1800517ED
0x1800513fe  xorps   xmm0, xmm0
0x180051401  xor     edx, edx; struct _GUID *
0x180051403  movups  xmmword ptr [rbp+47h+clsid.Data1], xmm0
0x180051407  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x18005140c  test    eax, eax
0x18005140e  jnz     short loc_180051421
0x180051410  lea     rdx, [rbp+47h+clsid]; lpclsid
0x180051414  mov     rcx, rbx; lpszProgID
0x180051417  call    cs:__imp_CLSIDFromProgIDEx
0x18005141d  test    eax, eax
0x18005141f  jns     short loc_180051436
0x180051421  lea     rdx, [rbp+47h+clsid]; lpclsid
0x180051425  mov     rcx, rbx; lpszProgID
0x180051428  call    cs:__imp_CLSIDFromProgID
0x18005142e  test    eax, eax
0x180051430  js      loc_1800517F2
0x180051436  lea     rdx, [rbp+47h+var_C0]; struct IActiveScriptSiteWldp **
0x18005143a  mov     [rbp+47h+var_C0], r15
0x18005143e  mov     rcx, rdi; this
0x180051441  call    ?GetActiveScriptSiteWldp@COleScript@@QEAAJPEAPEAVIActiveScriptSiteWldp@@@Z; COleScript::GetActiveScriptSiteWldp(IActiveScriptSiteWldp * *)
0x180051446  test    eax, eax
0x180051448  js      short loc_180051499
0x18005144a  mov     rcx, [rbp+47h+var_C0]
0x18005144e  lea     r8, [rsp+110h+nSize]
0x180051453  mov     [rsp+110h+nSize], r15d
0x180051458  lea     rdx, [rbp+47h+clsid]
0x18005145c  mov     rax, [rcx]
0x18005145f  mov     rax, [rax+20h]
0x180051463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051468  mov     ebx, eax
0x18005146a  test    eax, eax
0x18005146c  js      short loc_18005147B
0x18005146e  cmp     [rsp+110h+nSize], r15d
0x180051473  mov     eax, 800A01ADh
0x180051478  cmovz   ebx, eax
0x18005147b  mov     rdx, [rbp+47h+var_C0]
0x18005147f  mov     rcx, [rdx]
0x180051482  mov     rax, [rcx+10h]
0x180051486  mov     rcx, rdx
0x180051489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005148e  test    ebx, ebx
0x180051490  jns     short loc_180051499
0x180051492  mov     eax, ebx
0x180051494  jmp     loc_1800517F2
0x180051499  lea     rcx, [rbp+47h+clsid]
0x18005149d  call    IsProhibitedUnsafeExtension
0x1800514a2  test    eax, eax
0x1800514a4  jnz     loc_18005171D
0x1800514aa  mov     rcx, r13; pbstr
0x1800514ad  mov     [rsp+110h+ppunk], r15
0x1800514b2  call    cs:__imp_SysStringLen
0x1800514b8  mov     r14d, eax
0x1800514bb  test    eax, eax
0x1800514bd  jnz     short loc_1800514F5
0x1800514bf  cmp     [rbp+47h+arg_20], r15d
0x1800514c3  jz      short loc_1800514F5
0x1800514c5  xor     edx, edx; struct _GUID *
0x1800514c7  mov     rcx, rdi; this
0x1800514ca  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x1800514cf  test    eax, eax
0x1800514d1  jnz     loc_18005171D
0x1800514d7  lea     r8, [rsp+110h+ppunk]; ppunk
0x1800514dc  xor     edx, edx; pvReserved
0x1800514de  lea     rcx, [rbp+47h+clsid]; rclsid
0x1800514e2  call    cs:__imp_GetActiveObject
0x1800514e8  test    eax, eax
0x1800514ea  jns     loc_1800517BB
0x1800514f0  jmp     loc_1800517F2
0x1800514f5  test    r14d, r14d
0x1800514f8  lea     rdx, [rbp+47h+clsid]; struct _GUID *
0x1800514fc  mov     r12d, r15d
0x1800514ff  mov     rcx, rdi; this
0x180051502  setnz   r12b
0x180051506  call    ?CanCreateObject@COleScript@@QEAAHAEBU_GUID@@@Z; COleScript::CanCreateObject(_GUID const &)
0x18005150b  test    eax, eax
0x18005150d  jz      loc_18005171D
0x180051513  xor     edx, edx; struct _GUID *
0x180051515  mov     [rbp+47h+var_B0], r15
0x180051519  mov     rcx, rdi; this
0x18005151c  mov     [rbp+47h+var_A8], rsi
0x180051520  mov     ebx, 15h
0x180051525  mov     [rbp+47h+var_A0], r15
0x180051529  mov     [rbp+47h+var_98], r15
0x18005152d  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x180051532  test    rsi, rsi
0x180051535  jz      short loc_1800515AB
0x180051537  test    eax, eax
0x180051539  jnz     loc_18005171D
0x18005153f  lea     rdx, [rsp+110h+nSize]; nSize
0x180051544  mov     [rsp+110h+nSize], 10h
0x18005154c  lea     rcx, [rbp+47h+Buffer]; lpBuffer
0x180051550  call    cs:__imp_GetComputerNameA
0x180051556  test    eax, eax
0x180051558  jz      short loc_1800515A0
0x18005155a  lea     rax, [rbp+47h+WideCharStr]
0x18005155e  mov     [rsp+110h+cchWideChar], 10h; cchWideChar
0x180051566  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18005156a  mov     [rsp+110h+lpWideCharStr], rax; lpWideCharStr
0x18005156f  lea     r8, [rbp+47h+Buffer]; lpMultiByteStr
0x180051573  xor     edx, edx; dwFlags
0x180051575  xor     ecx, ecx; CodePage
0x180051577  call    cs:__imp_MultiByteToWideChar
0x18005157d  test    eax, eax
0x18005157f  jz      short loc_1800515A0
0x180051581  lea     eax, [rbx+47h]
0x180051584  jmp     short loc_18005158A
0x180051586  add     rsi, 2
0x18005158a  cmp     ax, [rsi]
0x18005158d  jz      short loc_180051586
0x18005158f  mov     rdx, rsi; String2
0x180051592  lea     rcx, [rbp+47h+WideCharStr]; String1
0x180051596  call    cs:__imp__wcsicmp
0x18005159c  test    eax, eax
0x18005159e  jz      short loc_1800515B5
0x1800515a0  lea     r15, [rbp+47h+var_B0]
0x1800515a4  mov     ebx, 10h
0x1800515a9  jmp     short loc_1800515B5
0x1800515ab  test    eax, eax
0x1800515ad  mov     ecx, 5
0x1800515b2  cmovnz  ebx, ecx
0x1800515b5  lea     rax, [rsp+110h+ppv]
0x1800515ba  mov     [rsp+110h+ppv], 0
0x1800515c3  lea     r9, IID_IClassFactory; riid
0x1800515ca  mov     [rsp+110h+lpWideCharStr], rax; ppv
0x1800515cf  mov     r8, r15; pvReserved
0x1800515d2  mov     [rsp+110h+var_C8], 0
0x1800515db  mov     edx, ebx; dwClsContext
0x1800515dd  lea     rcx, [rbp+47h+clsid]; rclsid
0x1800515e1  call    cs:__imp_CoGetClassObject
0x1800515e7  test    eax, eax
0x1800515e9  js      loc_1800517F2
0x1800515ef  mov     rcx, [rsp+110h+ppv]
0x1800515f4  lea     r8, [rsp+110h+var_C8]
0x1800515f9  lea     rdx, IID_IClassFactory3
0x180051600  mov     rax, [rcx]
0x180051603  mov     rax, [rax]
0x180051606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005160b  mov     rcx, [rsp+110h+ppv]
0x180051610  test    eax, eax
0x180051612  mov     rax, [rcx]
0x180051615  js      loc_1800516B9
0x18005161b  mov     rax, [rax+10h]
0x18005161f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051624  mov     rdx, [rdi+2A0h]; struct CSession *
0x18005162b  lea     rcx, [rsp+110h+nSize]; struct SiteService **
0x180051630  mov     qword ptr [rsp+110h+nSize], 0
0x180051639  call    ?Create@SiteService@@SAJPEAPEAV1@PEAVCSession@@@Z; SiteService::Create(SiteService * *,CSession *)
0x18005163e  mov     rsi, qword ptr [rsp+110h+nSize]
0x180051643  mov     ebx, eax
0x180051645  test    eax, eax
0x180051647  js      short loc_180051692
0x180051649  mov     rcx, [rsp+110h+var_C8]
0x18005164e  lea     rdx, [rsp+110h+ppunk]
0x180051653  mov     [rsp+110h+lpWideCharStr], rdx
0x180051658  lea     r9, IID_IUnknown
0x18005165f  xor     r8d, r8d
0x180051662  mov     rdx, rsi
0x180051665  mov     rax, [rcx]
0x180051668  mov     rax, [rax+28h]
0x18005166c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051671  mov     ebx, eax
0x180051673  test    eax, eax
0x180051675  js      short loc_180051692
0x180051677  mov     rcx, [rsp+110h+var_C8]
0x18005167c  mov     rax, [rcx]
0x18005167f  mov     rax, [rax+10h]
0x180051683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051688  mov     rcx, rsi; this
0x18005168b  call    ?Release@SiteService@@UEAAKXZ; SiteService::Release(void)
0x180051690  jmp     short loc_1800516F1
0x180051692  mov     rcx, [rsp+110h+var_C8]
0x180051697  mov     rax, [rcx]
0x18005169a  mov     rax, [rax+10h]
0x18005169e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800516a3  test    rsi, rsi
0x1800516a6  jz      loc_180051492
0x1800516ac  mov     rcx, rsi; this
0x1800516af  call    ?Release@SiteService@@UEAAKXZ; SiteService::Release(void)
0x1800516b4  jmp     loc_180051492
0x1800516b9  mov     rax, [rax+18h]
0x1800516bd  lea     r9, [rsp+110h+ppunk]
0x1800516c2  lea     r8, IID_IUnknown
0x1800516c9  xor     edx, edx
0x1800516cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800516d0  mov     rcx, [rsp+110h+ppv]
0x1800516d5  mov     ebx, eax
0x1800516d7  test    eax, eax
0x1800516d9  mov     rax, [rcx]
0x1800516dc  mov     rax, [rax+10h]
0x1800516e0  jns     short loc_1800516EC
0x1800516e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800516e7  jmp     loc_180051492
0x1800516ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800516f1  mov     r8, [rsp+110h+ppunk]; struct IUnknown *
0x1800516f6  lea     rdx, [rbp+47h+clsid]; struct _GUID *
0x1800516fa  mov     r9d, r12d; int
0x1800516fd  mov     rcx, rdi; this
0x180051700  call    ?CanObjectRun@COleScript@@QEAAHAEBU_GUID@@PEAUIUnknown@@H@Z; COleScript::CanObjectRun(_GUID const &,IUnknown *,int)
0x180051705  test    eax, eax
0x180051707  jnz     short loc_180051727
0x180051709  mov     rdx, [rsp+110h+ppunk]
0x18005170e  mov     rcx, [rdx]
0x180051711  mov     rax, [rcx+10h]
0x180051715  mov     rcx, rdx
0x180051718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005171d  mov     eax, 800A01ADh
0x180051722  jmp     loc_1800517F2
0x180051727  test    r14d, r14d
0x18005172a  jz      loc_1800517B7
0x180051730  mov     rcx, [rsp+110h+ppunk]
0x180051735  lea     r8, [rsp+110h+nSize]
0x18005173a  mov     qword ptr [rsp+110h+nSize], 0
0x180051743  lea     rdx, IID_IPersistFile
0x18005174a  mov     rax, [rcx]
0x18005174d  mov     rax, [rax]
0x180051750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051755  test    eax, eax
0x180051757  js      loc_1800517E6
0x18005175d  mov     rdx, r13; unsigned __int16 *
0x180051760  mov     rcx, rdi; this
0x180051763  call    ?CanObjectPersistFromURL@COleScript@@QEAAHPEAG@Z; COleScript::CanObjectPersistFromURL(ushort *)
0x180051768  mov     rcx, qword ptr [rsp+110h+nSize]
0x18005176d  test    eax, eax
0x18005176f  mov     rax, [rcx]
0x180051772  jnz     short loc_18005178B
0x180051774  mov     rax, [rax+10h]
0x180051778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005177d  mov     rcx, [rsp+110h+ppunk]
0x180051782  mov     rax, [rcx]
0x180051785  mov     rax, [rax+10h]
0x180051789  jmp     short loc_180051718
0x18005178b  mov     rax, [rax+28h]
0x18005178f  xor     r8d, r8d
0x180051792  mov     rdx, r13
0x180051795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005179a  mov     rcx, qword ptr [rsp+110h+nSize]
0x18005179f  mov     ebx, eax
0x1800517a1  mov     rax, [rcx]
0x1800517a4  mov     rax, [rax+10h]
0x1800517a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800517ad  cmp     ebx, 1
0x1800517b0  jnz     short loc_1800517B7
0x1800517b2  mov     ebx, 800A01ADh
0x1800517b7  test    ebx, ebx
0x1800517b9  js      short loc_1800517D5
0x1800517bb  mov     r9, [rbp+47h+var_B8]; struct VAR *
0x1800517bf  mov     rdx, rdi; struct COleScript *
0x1800517c2  mov     r8, [rsp+110h+ppunk]; struct IUnknown *
0x1800517c7  mov     rcx, [rdi+2A0h]; struct CSession *
0x1800517ce  call    ?PrepareObject@@YAJPEAVCSession@@PEAVCOleScript@@PEAUIUnknown@@PEAVVAR@@@Z; PrepareObject(CSession *,COleScript *,IUnknown *,VAR *)
0x1800517d3  mov     ebx, eax
0x1800517d5  mov     rcx, [rsp+110h+ppunk]
0x1800517da  mov     rax, [rcx]
0x1800517dd  mov     rax, [rax+10h]
0x1800517e1  jmp     loc_1800516E2
0x1800517e6  mov     ebx, 800A01B0h
0x1800517eb  jmp     short loc_1800517D5
0x1800517ed  mov     eax, 800A0005h
0x1800517f2  mov     rcx, [rbp+47h+var_50]
0x1800517f6  xor     rcx, rsp; StackCookie
0x1800517f9  call    __security_check_cookie
0x1800517fe  add     rsp, 0D8h
0x180051805  pop     r15
0x180051807  pop     r14
0x180051809  pop     r13
0x18005180b  pop     r12
0x18005180d  pop     rdi
0x18005180e  pop     rsi
0x18005180f  pop     rbx
0x180051810  pop     rbp
0x180051811  retn
```
