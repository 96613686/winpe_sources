# CWbemRefreshingSvc::AddObjectToRefresher_(int,_WBEM_REFRESHER_ID *,CWbemObject *,long,IWbemContext *,_WBEM_REFRESH_INFO *)

- ea: `0x180041c80`
- end: `0x180041ff2`
- name: `?AddObjectToRefresher_@CWbemRefreshingSvc@@IEAAJHPEAU_WBEM_REFRESHER_ID@@PEAVCWbemObject@@JPEAUIWbemContext@@PEAU_WBEM_REFRESH_INFO@@@Z`
- size: `882`
- prototype: `__int64 __fastcall(CWbemRefreshingSvc *this, int, struct _WBEM_REFRESHER_ID *, struct CWbemObject *, int, struct IWbemContext *, struct _WBEM_REFRESH_INFO *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180041360`
- `0x180089960`

## callees

- `0x180037120`
- `0x18004132c`
- `0x180041c80`
- `0x180042760`
- `0x18008a3c0`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180041f3b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180041f3b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180041eb6`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180041eb6`
- `wbemcomn!GetMemLogObject` at `0x180041cbc`
- `wbemcomn!GetMemLogObject` at `0x180041d3c`
- `wbemcomn!GetMemLogObject` at `0x180041d9b`
- `wbemcomn!GetMemLogObject` at `0x180041e2e`
- `wbemcomn!GetMemLogObject` at `0x180041f48`
- `wbemcomn!GetMemLogObject` at `0x180041cbc`
- `wbemcomn!GetMemLogObject` at `0x180041d3c`
- `wbemcomn!GetMemLogObject` at `0x180041d9b`
- `wbemcomn!GetMemLogObject` at `0x180041e2e`
- `wbemcomn!GetMemLogObject` at `0x180041f48`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180041d84`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180041d84`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180041d16`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180041d16`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180041ccc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180041d47`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180041dab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180041e3e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180041f53`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180041ccc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180041d47`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180041dab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180041e3e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180041f53`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180041fcf`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180041fcf`
- `OLEAUT32!__imp_SysAllocString` at `0x180041d8d`
- `OLEAUT32!__imp_SysAllocString` at `0x180041d8d`
- `OLEAUT32!__imp_SysFreeString` at `0x180041fc4`
- `OLEAUT32!__imp_SysFreeString` at `0x180041fc4`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWbemRefreshingSvc::AddObjectToRefresher_(
        CWbemRefreshingSvc *this,
        int a2,
        struct _WBEM_REFRESHER_ID *a3,
        struct CWbemObject *a4,
        int a5,
        struct IWbemContext *a6,
        struct _WBEM_REFRESH_INFO *a7)
{
  CMemoryLog *v9; // rax
  HRESULT RefrMgr; // esi
  CMemoryLog *v12; // rax
  CWbemRefreshingSvc *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  const OLECHAR *LPWSTR; // rax
  OLECHAR *v17; // rax
  OLECHAR *v18; // r12
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  __int64 v21; // rbx
  struct _IWbemRefresherMgr *v22; // rdi
  struct _WBEM_REFRESH_INFO *v23; // r13
  CMemoryLog *MemLogObject; // rax
  __int64 v25; // [rsp+68h] [rbp-31h] BYREF
  OLECHAR *v26; // [rsp+70h] [rbp-29h] BYREF
  struct _IWbemRefresherMgr *v27; // [rsp+78h] [rbp-21h]
  __int64 v28; // [rsp+80h] [rbp-19h]
  _BYTE v29[80]; // [rsp+88h] [rbp-11h] BYREF
  struct _IWbemRefresherMgr *v32; // [rsp+100h] [rbp+67h] BYREF

  if ( (**((_BYTE **)a4 + 9) & 3) == 2 )
  {
    CVar::CVar((CVar *)v29);
    RefrMgr = (*(__int64 (__fastcall **)(struct CWbemObject *, _BYTE *))(*(_QWORD *)a4 + 1096LL))(a4, v29);
    if ( RefrMgr >= 0 )
    {
      LPWSTR = CVar::GetLPWSTR((CVar *)v29);
      v17 = SysAllocString(LPWSTR);
      v18 = v17;
      if ( v17 )
      {
        v26 = v17;
        v25 = 0;
        if ( (*(int (__fastcall **)(_QWORD, OLECHAR *, _QWORD, _QWORD, __int64 *, _QWORD))(**((_QWORD **)this + 4) + 48LL))(
               *((_QWORD *)this + 4),
               v17,
               0,
               0,
               &v25,
               0) >= 0 )
        {
          v21 = v25;
          v28 = v25;
          v32 = 0;
          RefrMgr = CWbemRefreshingSvc::GetRefrMgr(this, &v32);
          v22 = v32;
          v27 = v32;
          if ( RefrMgr < 0 )
            goto LABEL_31;
          RefrMgr = CoImpersonateClient();
          if ( (int)(RefrMgr + 0x80000000) >= 0 && RefrMgr != -2147467262 )
            goto LABEL_31;
          v23 = a7;
          RefrMgr = (*(__int64 (__fastcall **)(struct _IWbemRefresherMgr *, _QWORD, _QWORD, _QWORD, __int64, struct _WBEM_REFRESHER_ID *, struct CWbemObject *, int, struct IWbemContext *, struct _IWbemRefresherMgr *, struct _WBEM_REFRESH_INFO *))(*(_QWORD *)v32 + 24LL))(
                      v32,
                      *((_QWORD *)this + 4),
                      *((_QWORD *)this + 5),
                      *((_QWORD *)this + 6),
                      v25,
                      a3,
                      a4,
                      a5,
                      a6,
                      v32,
                      a7);
          if ( RefrMgr >= 0 && !a2 )
            RefrMgr = CWbemRefreshingSvc::ResetRefreshInfo(this, v23);
          CoRevertToSelf();
          if ( RefrMgr < 0 )
          {
LABEL_31:
            MemLogObject = GetMemLogObject();
            CMemoryLog::Write(MemLogObject, RefrMgr);
          }
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              34,
              WPP_ccade184005d30f1287a0c391cfeefa4_Traceguids,
              (unsigned int)RefrMgr);
          }
          if ( v22 )
            (*(void (__fastcall **)(struct _IWbemRefresherMgr *))(*(_QWORD *)v22 + 16LL))(v22);
          v27 = 0;
          if ( v21 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          v28 = 0;
          SysFreeString(v18);
        }
        else
        {
          v20 = GetMemLogObject();
          RefrMgr = -2147217392;
          CMemoryLog::Write(v20, -2147217392);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              33,
              WPP_ccade184005d30f1287a0c391cfeefa4_Traceguids,
              2147749904LL);
          }
          CSysFreeMe::~CSysFreeMe(&v26);
        }
        goto LABEL_41;
      }
      v19 = GetMemLogObject();
      RefrMgr = -2147217402;
      CMemoryLog::Write(v19, -2147217402);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_41:
        CVar::~CVar((CVar *)v29);
        return (unsigned int)RefrMgr;
      }
      v14 = 32;
      v15 = 2147749894LL;
    }
    else
    {
      v12 = GetMemLogObject();
      CMemoryLog::Write(v12, RefrMgr);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_41;
      }
      v14 = 31;
      v15 = (unsigned int)RefrMgr;
    }
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_ccade184005d30f1287a0c391cfeefa4_Traceguids, v15);
    goto LABEL_41;
  }
  v9 = GetMemLogObject();
  CMemoryLog::Write(v9, -2147217400);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_ccade184005d30f1287a0c391cfeefa4_Traceguids, 2147749896LL);
  }
  return 2147749896LL;
}

```

## disassembly

```asm
0x180041c80  mov     rax, rsp
0x180041c83  mov     [rax+8], rbx
0x180041c87  mov     [rax+18h], r8
0x180041c8b  mov     [rax+10h], edx
0x180041c8e  push    rbp
0x180041c8f  push    rsi
0x180041c90  push    rdi
0x180041c91  push    r12
0x180041c93  push    r13
0x180041c95  push    r14
0x180041c97  push    r15
0x180041c99  lea     rbp, [rax-47h]
0x180041c9d  sub     rsp, 0A0h
0x180041ca4  mov     r15, r9
0x180041ca7  mov     r14, rcx
0x180041caa  mov     rax, [r9+48h]
0x180041cae  mov     r10b, [rax]
0x180041cb1  and     r10b, 3
0x180041cb5  mov     bl, 2
0x180041cb7  cmp     r10b, bl
0x180041cba  jz      short loc_180041D12
0x180041cbc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180041cc2  mov     edi, 80041008h
0x180041cc7  mov     edx, edi
0x180041cc9  mov     rcx, rax
0x180041ccc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180041cd2  lea     rax, WPP_GLOBAL_Control
0x180041cd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180041ce0  cmp     rcx, rax
0x180041ce3  jz      short loc_180041D0B
0x180041ce5  test    byte ptr [rcx+1Ch], 1
0x180041ce9  jz      short loc_180041D0B
0x180041ceb  cmp     [rcx+19h], bl
0x180041cee  jb      short loc_180041D0B
0x180041cf0  mov     edx, 1Eh
0x180041cf5  mov     r9d, 80041008h
0x180041cfb  lea     r8, WPP_ccade184005d30f1287a0c391cfeefa4_Traceguids
0x180041d02  mov     rcx, [rcx+10h]
0x180041d06  call    WPP_SF_d
0x180041d0b  mov     eax, edi
0x180041d0d  jmp     loc_180041FD7
0x180041d12  lea     rcx, [rbp+3Fh+var_50]
0x180041d16  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180041d1c  nop
0x180041d1d  mov     rax, [r15]
0x180041d20  lea     rdx, [rbp+3Fh+var_50]
0x180041d24  mov     rcx, r15
0x180041d27  mov     rax, [rax+448h]
0x180041d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d33  mov     esi, eax
0x180041d35  xor     r13d, r13d
0x180041d38  test    eax, eax
0x180041d3a  jns     short loc_180041D80
0x180041d3c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180041d42  mov     edx, esi
0x180041d44  mov     rcx, rax
0x180041d47  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180041d4d  lea     rax, WPP_GLOBAL_Control
0x180041d54  mov     rcx, cs:WPP_GLOBAL_Control
0x180041d5b  cmp     rcx, rax
0x180041d5e  jz      loc_180041FCB
0x180041d64  test    byte ptr [rcx+1Ch], 1
0x180041d68  jz      loc_180041FCB
0x180041d6e  cmp     [rcx+19h], bl
0x180041d71  jb      loc_180041FCB
0x180041d77  lea     edx, [r13+1Fh]
0x180041d7b  mov     r9d, esi
0x180041d7e  jmp     short loc_180041DE6
0x180041d80  lea     rcx, [rbp+3Fh+var_50]
0x180041d84  call    cs:__imp_?GetLPWSTR@CVar@@QEAAPEAGXZ; CVar::GetLPWSTR(void)
0x180041d8a  mov     rcx, rax; psz
0x180041d8d  call    cs:__imp_SysAllocString
0x180041d93  mov     r12, rax
0x180041d96  test    rax, rax
0x180041d99  jnz     short loc_180041DFB
0x180041d9b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180041da1  mov     esi, 80041006h
0x180041da6  mov     edx, esi
0x180041da8  mov     rcx, rax
0x180041dab  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180041db1  lea     rax, WPP_GLOBAL_Control
0x180041db8  mov     rcx, cs:WPP_GLOBAL_Control
0x180041dbf  cmp     rcx, rax
0x180041dc2  jz      loc_180041FCB
0x180041dc8  test    byte ptr [rcx+1Ch], 1
0x180041dcc  jz      loc_180041FCB
0x180041dd2  cmp     [rcx+19h], bl
0x180041dd5  jb      loc_180041FCB
0x180041ddb  lea     edx, [r12+20h]
0x180041de0  mov     r9d, 80041006h
0x180041de6  lea     r8, WPP_ccade184005d30f1287a0c391cfeefa4_Traceguids
0x180041ded  mov     rcx, [rcx+10h]
0x180041df1  call    WPP_SF_d
0x180041df6  jmp     loc_180041FCB
0x180041dfb  mov     [rbp+3Fh+var_68], r12
0x180041dff  mov     [rbp+3Fh+var_70], r13
0x180041e03  mov     rcx, [r14+20h]
0x180041e07  mov     rax, [rcx]
0x180041e0a  mov     [rsp+0D0h+var_A8], r13
0x180041e0f  lea     rdx, [rbp+3Fh+var_70]
0x180041e13  mov     [rsp+0D0h+var_B0], rdx
0x180041e18  xor     r9d, r9d
0x180041e1b  xor     r8d, r8d
0x180041e1e  mov     rdx, r12
0x180041e21  mov     rax, [rax+30h]
0x180041e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e2a  test    eax, eax
0x180041e2c  jns     short loc_180041E8C
0x180041e2e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180041e34  mov     esi, 80041010h
0x180041e39  mov     edx, esi
0x180041e3b  mov     rcx, rax
0x180041e3e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180041e44  lea     rax, WPP_GLOBAL_Control
0x180041e4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180041e52  cmp     rcx, rax
0x180041e55  jz      short loc_180041E7E
0x180041e57  test    byte ptr [rcx+1Ch], 1
0x180041e5b  jz      short loc_180041E7E
0x180041e5d  cmp     [rcx+19h], bl
0x180041e60  jb      short loc_180041E7E
0x180041e62  mov     edx, 21h ; '!'
0x180041e67  mov     r9d, 80041010h
0x180041e6d  lea     r8, WPP_ccade184005d30f1287a0c391cfeefa4_Traceguids
0x180041e74  mov     rcx, [rcx+10h]
0x180041e78  call    WPP_SF_d
0x180041e7d  nop
0x180041e7e  lea     rcx, [rbp+3Fh+var_68]; this
0x180041e82  call    ??1CSysFreeMe@@QEAA@XZ; CSysFreeMe::~CSysFreeMe(void)
0x180041e87  jmp     loc_180041FCB
0x180041e8c  mov     rbx, [rbp+3Fh+var_70]
0x180041e90  mov     [rbp+3Fh+var_58], rbx
0x180041e94  mov     [rbp+3Fh+arg_18], r13
0x180041e98  lea     rdx, [rbp+3Fh+arg_18]; struct _IWbemRefresherMgr **
0x180041e9c  mov     rcx, r14; this
0x180041e9f  call    ?GetRefrMgr@CWbemRefreshingSvc@@IEAAJPEAPEAU_IWbemRefresherMgr@@@Z; CWbemRefreshingSvc::GetRefrMgr(_IWbemRefresherMgr * *)
0x180041ea4  mov     esi, eax
0x180041ea6  mov     rdi, [rbp+3Fh+arg_18]
0x180041eaa  mov     [rbp+3Fh+var_60], rdi
0x180041eae  test    eax, eax
0x180041eb0  js      loc_180041F48
0x180041eb6  call    cs:__imp_CoImpersonateClient
0x180041ebc  mov     esi, eax
0x180041ebe  mov     ecx, 80000000h
0x180041ec3  add     eax, ecx
0x180041ec5  test    ecx, eax
0x180041ec7  jnz     short loc_180041ED1
0x180041ec9  cmp     esi, 80004002h
0x180041ecf  jnz     short loc_180041F48
0x180041ed1  mov     rcx, [rbp+3Fh+arg_18]
0x180041ed5  mov     rax, [rcx]
0x180041ed8  mov     r13, [rbp+3Fh+arg_30]
0x180041edc  mov     [rsp+50h], r13
0x180041ee1  mov     [rsp+0D0h+var_88], rcx
0x180041ee6  mov     rdx, [rbp+3Fh+arg_28]
0x180041eea  mov     [rsp+0D0h+var_90], rdx
0x180041eef  mov     edx, [rbp+3Fh+arg_20]
0x180041ef2  mov     dword ptr [rsp+0D0h+var_98], edx
0x180041ef6  mov     qword ptr [rsp+0D0h+var_A0], r15
0x180041efb  mov     rdx, [rbp+3Fh+arg_10]
0x180041eff  mov     [rsp+0D0h+var_A8], rdx
0x180041f04  mov     r8, [rbp+3Fh+var_70]
0x180041f08  mov     [rsp+0D0h+var_B0], r8
0x180041f0d  mov     r9, [r14+30h]
0x180041f11  mov     r8, [r14+28h]
0x180041f15  mov     rdx, [r14+20h]
0x180041f19  mov     rax, [rax+18h]
0x180041f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f22  mov     esi, eax
0x180041f24  test    eax, eax
0x180041f26  js      short loc_180041F3B
0x180041f28  cmp     [rbp+3Fh+arg_8], 0
0x180041f2c  jnz     short loc_180041F3B
0x180041f2e  mov     rdx, r13; struct _WBEM_REFRESH_INFO *
0x180041f31  mov     rcx, r14; this
0x180041f34  call    ?ResetRefreshInfo@CWbemRefreshingSvc@@IEAAJPEAU_WBEM_REFRESH_INFO@@@Z; CWbemRefreshingSvc::ResetRefreshInfo(_WBEM_REFRESH_INFO *)
0x180041f39  mov     esi, eax
0x180041f3b  call    cs:__imp_CoRevertToSelf
0x180041f41  xor     r13d, r13d
0x180041f44  test    esi, esi
0x180041f46  jns     short loc_180041F59
0x180041f48  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180041f4e  mov     edx, esi
0x180041f50  mov     rcx, rax
0x180041f53  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180041f59  lea     rax, WPP_GLOBAL_Control
0x180041f60  mov     rcx, cs:WPP_GLOBAL_Control
0x180041f67  cmp     rcx, rax
0x180041f6a  jz      short loc_180041F91
0x180041f6c  test    byte ptr [rcx+1Ch], 1
0x180041f70  jz      short loc_180041F91
0x180041f72  cmp     byte ptr [rcx+19h], 2
0x180041f76  jb      short loc_180041F91
0x180041f78  mov     edx, 22h ; '"'
0x180041f7d  mov     r9d, esi
0x180041f80  lea     r8, WPP_ccade184005d30f1287a0c391cfeefa4_Traceguids
0x180041f87  mov     rcx, [rcx+10h]
0x180041f8b  call    WPP_SF_d
0x180041f90  nop
0x180041f91  test    rdi, rdi
0x180041f94  jz      short loc_180041FA5
0x180041f96  mov     rax, [rdi]
0x180041f99  mov     rcx, rdi
0x180041f9c  mov     rax, [rax+10h]
0x180041fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041fa5  mov     [rbp+3Fh+var_60], r13
0x180041fa9  test    rbx, rbx
0x180041fac  jz      short loc_180041FBD
0x180041fae  mov     rax, [rbx]
0x180041fb1  mov     rcx, rbx
0x180041fb4  mov     rax, [rax+10h]
0x180041fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041fbd  mov     [rbp+3Fh+var_58], r13
0x180041fc1  mov     rcx, r12; bstrString
0x180041fc4  call    cs:__imp_SysFreeString
0x180041fca  nop
0x180041fcb  lea     rcx, [rbp+3Fh+var_50]
0x180041fcf  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180041fd5  mov     eax, esi
0x180041fd7  mov     rbx, [rsp+0D0h+arg_0]
0x180041fdf  add     rsp, 0A0h
0x180041fe6  pop     r15
0x180041fe8  pop     r14
0x180041fea  pop     r13
0x180041fec  pop     r12
0x180041fee  pop     rdi
0x180041fef  pop     rsi
0x180041ff0  pop     rbp
0x180041ff1  retn
```
