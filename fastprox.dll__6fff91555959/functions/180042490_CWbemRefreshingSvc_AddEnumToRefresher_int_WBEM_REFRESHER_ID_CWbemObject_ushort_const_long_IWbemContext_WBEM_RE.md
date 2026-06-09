# CWbemRefreshingSvc::AddEnumToRefresher_(int,_WBEM_REFRESHER_ID *,CWbemObject *,ushort const *,long,IWbemContext *,_WBEM_REFRESH_INFO *)

- ea: `0x180042490`
- end: `0x180042752`
- name: `?AddEnumToRefresher_@CWbemRefreshingSvc@@IEAAJHPEAU_WBEM_REFRESHER_ID@@PEAVCWbemObject@@PEBGJPEAUIWbemContext@@PEAU_WBEM_REFRESH_INFO@@@Z`
- size: `706`
- prototype: `__int64 __fastcall(CWbemRefreshingSvc *this, int, struct _WBEM_REFRESHER_ID *, struct CWbemObject *, OLECHAR *psz, int, struct IWbemContext *, struct _WBEM_REFRESH_INFO *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180042010`

## callees

- `0x180037120`
- `0x180042490`
- `0x180042760`
- `0x18008a3c0`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800425b7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800425b7`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180042537`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180042537`
- `wbemcomn!GetMemLogObject` at `0x18004266b`
- `wbemcomn!GetMemLogObject` at `0x180042681`
- `wbemcomn!GetMemLogObject` at `0x1800426b1`
- `wbemcomn!GetMemLogObject` at `0x18004266b`
- `wbemcomn!GetMemLogObject` at `0x180042681`
- `wbemcomn!GetMemLogObject` at `0x1800426b1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042676`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042691`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800426c1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042676`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042691`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800426c1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800424c2`
- `OLEAUT32!__imp_SysAllocString` at `0x1800424c2`
- `OLEAUT32!__imp_SysFreeString` at `0x180042613`
- `OLEAUT32!__imp_SysFreeString` at `0x180042613`

## pseudocode

```c
__int64 __fastcall CWbemRefreshingSvc::AddEnumToRefresher_(
        CWbemRefreshingSvc *this,
        int a2,
        struct _WBEM_REFRESHER_ID *a3,
        struct CWbemObject *a4,
        OLECHAR *psz,
        int a6,
        struct IWbemContext *a7,
        struct _WBEM_REFRESH_INFO *a8)
{
  BSTR v10; // rax
  OLECHAR *v11; // r15
  __int64 v12; // rbx
  HRESULT RefrMgr; // esi
  struct _IWbemRefresherMgr *v14; // rdi
  CMemoryLog *v16; // rax
  CMemoryLog *v17; // rax
  CMemoryLog *MemLogObject; // rax
  struct _IWbemRefresherMgr *v19; // [rsp+78h] [rbp-29h] BYREF
  __int64 v20; // [rsp+80h] [rbp-21h] BYREF
  struct _IWbemRefresherMgr *v21; // [rsp+88h] [rbp-19h]
  __int64 v22; // [rsp+90h] [rbp-11h]
  BSTR v23; // [rsp+98h] [rbp-9h]

  v10 = SysAllocString(psz);
  v11 = v10;
  if ( v10 )
  {
    v23 = v10;
    v20 = 0;
    if ( (*(int (__fastcall **)(_QWORD, BSTR, _QWORD, _QWORD, __int64 *, _QWORD))(**((_QWORD **)this + 4) + 48LL))(
           *((_QWORD *)this + 4),
           v10,
           0,
           0,
           &v20,
           0) < 0 )
    {
      MemLogObject = GetMemLogObject();
      RefrMgr = -2147217392;
      CMemoryLog::Write(MemLogObject, -2147217392);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_ccade184005d30f1287a0c391cfeefa4_Traceguids, 2147749904LL);
      }
    }
    else
    {
      v12 = v20;
      v22 = v20;
      v19 = 0;
      RefrMgr = CWbemRefreshingSvc::GetRefrMgr(this, &v19);
      v14 = v19;
      v21 = v19;
      if ( RefrMgr < 0 )
        goto LABEL_20;
      RefrMgr = CoImpersonateClient();
      if ( (int)(RefrMgr + 0x80000000) >= 0 && RefrMgr != -2147467262 )
        goto LABEL_20;
      RefrMgr = (*(__int64 (__fastcall **)(struct _IWbemRefresherMgr *, _QWORD, _QWORD, _QWORD, __int64, struct _WBEM_REFRESHER_ID *, struct CWbemObject *, OLECHAR *, int, struct IWbemContext *, struct _IWbemRefresherMgr *, struct _WBEM_REFRESH_INFO *))(*(_QWORD *)v19 + 32LL))(
                  v19,
                  *((_QWORD *)this + 4),
                  *((_QWORD *)this + 5),
                  *((_QWORD *)this + 6),
                  v20,
                  a3,
                  a4,
                  psz,
                  a6,
                  a7,
                  v19,
                  a8);
      if ( RefrMgr >= 0 && !a2 )
        RefrMgr = CWbemRefreshingSvc::ResetRefreshInfo(this, a8);
      CoRevertToSelf();
      if ( RefrMgr < 0 )
      {
LABEL_20:
        v16 = GetMemLogObject();
        CMemoryLog::Write(v16, RefrMgr);
      }
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          47,
          WPP_ccade184005d30f1287a0c391cfeefa4_Traceguids,
          (unsigned int)RefrMgr);
      }
      if ( v14 )
        (*(void (__fastcall **)(struct _IWbemRefresherMgr *))(*(_QWORD *)v14 + 16LL))(v14);
      v21 = 0;
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      v22 = 0;
    }
    SysFreeString(v11);
    return (unsigned int)RefrMgr;
  }
  else
  {
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_ccade184005d30f1287a0c391cfeefa4_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
}

```

## disassembly

```asm
0x180042490  mov     rax, rsp
0x180042493  mov     [rax+8], rbx
0x180042497  mov     [rax+20h], r9
0x18004249b  mov     [rax+18h], r8
0x18004249f  push    rbp
0x1800424a0  push    rsi
0x1800424a1  push    rdi
0x1800424a2  push    r12
0x1800424a4  push    r13
0x1800424a6  push    r14
0x1800424a8  push    r15
0x1800424aa  lea     rbp, [rax-3Fh]
0x1800424ae  sub     rsp, 0A0h
0x1800424b5  mov     r13d, edx
0x1800424b8  mov     r14, rcx
0x1800424bb  mov     r12, [rbp+37h+psz]
0x1800424bf  mov     rcx, r12; psz
0x1800424c2  call    cs:__imp_SysAllocString
0x1800424c8  mov     r15, rax
0x1800424cb  xor     edi, edi
0x1800424cd  test    rax, rax
0x1800424d0  jz      loc_180042681
0x1800424d6  mov     [rbp+37h+var_40], rax
0x1800424da  mov     [rbp+37h+var_58], rdi
0x1800424de  mov     rcx, [r14+20h]
0x1800424e2  mov     rax, [rcx]
0x1800424e5  mov     [rsp+0D0h+var_A8], rdi
0x1800424ea  lea     rdx, [rbp+37h+var_58]
0x1800424ee  mov     [rsp+0D0h+var_B0], rdx
0x1800424f3  xor     r9d, r9d
0x1800424f6  xor     r8d, r8d
0x1800424f9  mov     rdx, r15
0x1800424fc  mov     rax, [rax+30h]
0x180042500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042505  test    eax, eax
0x180042507  js      loc_1800426B1
0x18004250d  mov     rbx, [rbp+37h+var_58]
0x180042511  mov     [rbp+37h+var_48], rbx
0x180042515  mov     [rbp+37h+var_60], rdi
0x180042519  lea     rdx, [rbp+37h+var_60]; struct _IWbemRefresherMgr **
0x18004251d  mov     rcx, r14; this
0x180042520  call    ?GetRefrMgr@CWbemRefreshingSvc@@IEAAJPEAPEAU_IWbemRefresherMgr@@@Z; CWbemRefreshingSvc::GetRefrMgr(_IWbemRefresherMgr * *)
0x180042525  mov     esi, eax
0x180042527  mov     rdi, [rbp+37h+var_60]
0x18004252b  mov     [rbp+37h+var_50], rdi
0x18004252f  test    eax, eax
0x180042531  js      loc_18004266B
0x180042537  call    cs:__imp_CoImpersonateClient
0x18004253d  mov     esi, eax
0x18004253f  mov     ecx, 80000000h
0x180042544  add     eax, ecx
0x180042546  test    ecx, eax
0x180042548  jz      loc_18004265F
0x18004254e  mov     rcx, [rbp+37h+var_60]
0x180042552  mov     rax, [rcx]
0x180042555  mov     rdx, [rbp+37h+arg_38]
0x180042559  mov     [rsp+58h], rdx
0x18004255e  mov     [rsp+0D0h+var_80], rcx
0x180042563  mov     rdx, [rbp+37h+arg_30]
0x180042567  mov     [rsp+0D0h+var_88], rdx
0x18004256c  mov     edx, [rbp+37h+arg_28]
0x18004256f  mov     dword ptr [rsp+0D0h+var_90], edx
0x180042573  mov     qword ptr [rsp+0D0h+var_98], r12
0x180042578  mov     rdx, [rbp+37h+arg_18]
0x18004257c  mov     [rsp+0D0h+var_A0], rdx
0x180042581  mov     rdx, [rbp+37h+arg_10]
0x180042585  mov     [rsp+0D0h+var_A8], rdx
0x18004258a  mov     r8, [rbp+37h+var_58]
0x18004258e  mov     [rsp+0D0h+var_B0], r8
0x180042593  mov     r9, [r14+30h]
0x180042597  mov     r8, [r14+28h]
0x18004259b  mov     rdx, [r14+20h]
0x18004259f  mov     rax, [rax+20h]
0x1800425a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800425a8  mov     esi, eax
0x1800425aa  test    eax, eax
0x1800425ac  js      short loc_1800425B7
0x1800425ae  test    r13d, r13d
0x1800425b1  jz      loc_18004273E
0x1800425b7  call    cs:__imp_CoRevertToSelf
0x1800425bd  test    esi, esi
0x1800425bf  js      loc_18004266B
0x1800425c5  lea     rax, WPP_GLOBAL_Control
0x1800425cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800425d3  cmp     rcx, rax
0x1800425d6  jnz     short loc_180042636
0x1800425d8  test    rdi, rdi
0x1800425db  jz      short loc_1800425EC
0x1800425dd  mov     rax, [rdi]
0x1800425e0  mov     rcx, rdi
0x1800425e3  mov     rax, [rax+10h]
0x1800425e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800425ec  mov     [rbp+37h+var_50], 0
0x1800425f4  test    rbx, rbx
0x1800425f7  jz      short loc_180042608
0x1800425f9  mov     rax, [rbx]
0x1800425fc  mov     rcx, rbx
0x1800425ff  mov     rax, [rax+10h]
0x180042603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042608  mov     [rbp+37h+var_48], 0
0x180042610  mov     rcx, r15; bstrString
0x180042613  call    cs:__imp_SysFreeString
0x180042619  mov     eax, esi
0x18004261b  mov     rbx, [rsp+0D0h+arg_0]
0x180042623  add     rsp, 0A0h
0x18004262a  pop     r15
0x18004262c  pop     r14
0x18004262e  pop     r13
0x180042630  pop     r12
0x180042632  pop     rdi
0x180042633  pop     rsi
0x180042634  pop     rbp
0x180042635  retn
0x180042636  test    byte ptr [rcx+1Ch], 1
0x18004263a  jz      short loc_1800425D8
0x18004263c  cmp     byte ptr [rcx+19h], 2
0x180042640  jb      short loc_1800425D8
0x180042642  mov     edx, 2Fh ; '/'
0x180042647  mov     r9d, esi
0x18004264a  lea     r8, WPP_ccade184005d30f1287a0c391cfeefa4_Traceguids
0x180042651  mov     rcx, [rcx+10h]
0x180042655  call    WPP_SF_d
0x18004265a  jmp     loc_1800425D8
0x18004265f  cmp     esi, 80004002h
0x180042665  jz      loc_18004254E
0x18004266b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180042671  mov     edx, esi
0x180042673  mov     rcx, rax
0x180042676  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004267c  jmp     loc_1800425C5
0x180042681  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180042687  mov     ebx, 80041006h
0x18004268c  mov     edx, ebx
0x18004268e  mov     rcx, rax
0x180042691  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180042697  lea     rax, WPP_GLOBAL_Control
0x18004269e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800426a5  cmp     rcx, rax
0x1800426a8  jnz     short loc_180042712
0x1800426aa  mov     eax, ebx
0x1800426ac  jmp     loc_18004261B
0x1800426b1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800426b7  mov     esi, 80041010h
0x1800426bc  mov     edx, esi
0x1800426be  mov     rcx, rax
0x1800426c1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800426c7  lea     rax, WPP_GLOBAL_Control
0x1800426ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800426d5  cmp     rcx, rax
0x1800426d8  jz      loc_180042610
0x1800426de  test    byte ptr [rcx+1Ch], 1
0x1800426e2  jz      loc_180042610
0x1800426e8  cmp     byte ptr [rcx+19h], 2
0x1800426ec  jb      loc_180042610
0x1800426f2  mov     edx, 2Eh ; '.'
0x1800426f7  mov     r9d, 80041010h
0x1800426fd  lea     r8, WPP_ccade184005d30f1287a0c391cfeefa4_Traceguids
0x180042704  mov     rcx, [rcx+10h]
0x180042708  call    WPP_SF_d
0x18004270d  jmp     loc_180042610
0x180042712  test    byte ptr [rcx+1Ch], 1
0x180042716  jz      short loc_1800426AA
0x180042718  cmp     byte ptr [rcx+19h], 2
0x18004271c  jb      short loc_1800426AA
0x18004271e  mov     edx, 2Dh ; '-'
0x180042723  mov     r9d, 80041006h
0x180042729  lea     r8, WPP_ccade184005d30f1287a0c391cfeefa4_Traceguids
0x180042730  mov     rcx, [rcx+10h]
0x180042734  call    WPP_SF_d
0x180042739  jmp     loc_1800426AA
0x18004273e  mov     rdx, [rbp+37h+arg_38]; struct _WBEM_REFRESH_INFO *
0x180042742  mov     rcx, r14; this
0x180042745  call    ?ResetRefreshInfo@CWbemRefreshingSvc@@IEAAJPEAU_WBEM_REFRESH_INFO@@@Z; CWbemRefreshingSvc::ResetRefreshInfo(_WBEM_REFRESH_INFO *)
0x18004274a  mov     esi, eax
0x18004274c  jmp     loc_1800425B7
```
