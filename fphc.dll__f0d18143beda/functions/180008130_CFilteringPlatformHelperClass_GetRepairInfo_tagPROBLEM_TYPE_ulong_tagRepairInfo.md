# CFilteringPlatformHelperClass::GetRepairInfo(tagPROBLEM_TYPE,ulong *,tagRepairInfo * *)

- ea: `0x180008130`
- end: `0x180008324`
- name: `?GetRepairInfo@CFilteringPlatformHelperClass@@UEAAJW4tagPROBLEM_TYPE@@PEAKPEAPEAUtagRepairInfo@@@Z`
- size: `500`
- prototype: `int(CFilteringPlatformHelperClass *__hidden this, enum tagPROBLEM_TYPE, unsigned int *, struct tagRepairInfo **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180008130`
- `0x180008490`
- `0x18000a208`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800082c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800082d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800082eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800082fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800082c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800082d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800082eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800082fb`

## pseudocode

```c
__int64 __fastcall CFilteringPlatformHelperClass::GetRepairInfo(
        CFilteringPlatformHelperClass *this,
        enum tagPROBLEM_TYPE a2,
        unsigned int *a3,
        struct tagRepairInfo **a4)
{
  int StringWithAlloc; // ebx
  int v8; // edx
  UINT v9; // esi
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // edx
  int v15; // edx
  struct _GUID v16; // xmm0
  int v17; // edx
  int v18; // edx
  int v19; // edx
  int v20; // edx
  int v21; // edx
  int v22; // edx
  union tagUiInfo::$B6D4BC3794FD71ECD2A2FEA439E7CE55 *p_pwzNull; // rdx
  struct tagRepairInfo *v24; // rdi
  unsigned int v25; // r15d
  unsigned int v26; // esi
  __int64 v27; // r14
  LPWSTR pwzNull; // rcx
  unsigned int v30; // [rsp+20h] [rbp-38h]
  int v31; // [rsp+38h] [rbp-20h]
  struct _GUID v32; // [rsp+40h] [rbp-18h] BYREF

  StringWithAlloc = 0;
  *a3 = 0;
  *a4 = 0;
  if ( a2 != PT_LOW_HEALTH )
    goto LABEL_35;
  v8 = *((_DWORD *)this + 118);
  v9 = 0;
  if ( v8 > 8 )
  {
    v17 = v8 - 9;
    if ( !v17 )
    {
      v16 = (struct _GUID)ID_WFP_REPAIR_AUTH_FAILURE_PRESHARED_KEY;
      goto LABEL_32;
    }
    v18 = v17 - 1;
    if ( !v18 )
    {
      v16 = (struct _GUID)ID_WFP_REPAIR_CLASSIFY_DROP;
      v9 = 2160;
      *((_BYTE *)this + 465) = 1;
      goto LABEL_32;
    }
    v19 = v18 - 1;
    if ( !v19 )
    {
      v16 = (struct _GUID)ID_WFP_REPAIR_MUTIPLE_AUTH_FAILED;
      goto LABEL_32;
    }
    v20 = v19 - 1;
    if ( !v20 )
    {
      v16 = (struct _GUID)ID_WFP_REPAIR_AUTHZ_FAILURE_SMART_CARD;
      goto LABEL_32;
    }
    v21 = v20 - 1;
    if ( !v21 )
    {
      v16 = (struct _GUID)ID_WFP_REPAIR_AUTHZ_FAILURE_SMART_CARD_AND_CERT_MAP;
      goto LABEL_32;
    }
    v22 = v21 - 1;
    if ( !v22 )
    {
      v16 = (struct _GUID)ID_WFP_REPAIR_AUTHZ_FAILURE_AUTH_ASSURANCE;
      goto LABEL_32;
    }
    if ( v22 == 2 )
    {
      v16 = (struct _GUID)ID_WFP_REPAIR_IPSEC_GENERIC_FAILURE;
      goto LABEL_32;
    }
LABEL_24:
    StringWithAlloc = -2147467263;
    goto LABEL_35;
  }
  if ( v8 == 8 )
  {
    v16 = (struct _GUID)ID_WFP_REPAIR_AUTH_FAILURE_KERB_ERROR;
    goto LABEL_32;
  }
  if ( v8 )
  {
    v10 = v8 - 1;
    if ( !v10 || (v11 = v10 - 1) == 0 || (v12 = v11 - 1) == 0 || (v13 = v12 - 1) == 0 )
    {
      v16 = (struct _GUID)ID_WFP_REPAIR_POLICY_MISMATCH;
      goto LABEL_32;
    }
    v14 = v13 - 1;
    if ( !v14 )
    {
      v16 = (struct _GUID)ID_WFP_REPAIR_POLICY_MISMATCH_CRED_FAILURE;
      goto LABEL_32;
    }
    v15 = v14 - 1;
    if ( !v15 )
    {
      v16 = (struct _GUID)ID_WFP_REPAIR_AUTH_FAILURE_CERT_EXPIRED;
      goto LABEL_32;
    }
    if ( v15 == 1 )
    {
      v16 = (struct _GUID)ID_WFP_REPAIR_AUTH_FAILURE_CERT_ERROR;
LABEL_32:
      v32 = v16;
      StringWithAlloc = BuildRepairInfos(
                          0xCu,
                          (const struct tagRepairInfoMap *)&CFilteringPlatformHelperClass::m_repairInfos,
                          PT_LOW_HEALTH,
                          &v32,
                          v30,
                          a3,
                          a4,
                          v31);
      if ( StringWithAlloc >= 0 )
      {
        if ( !*((_BYTE *)this + 465) )
          return (unsigned int)StringWithAlloc;
        p_pwzNull = (union tagUiInfo::$B6D4BC3794FD71ECD2A2FEA439E7CE55 *)&(*a4)->UiInfo.pwzNull;
        (*a4)->UiInfo.type = UIT_HELP_PANE;
        p_pwzNull->pwzNull = 0;
        StringWithAlloc = LoadStringWithAlloc(v9, &p_pwzNull->pwzNull, 0x1000u);
        if ( StringWithAlloc >= 0 )
          return (unsigned int)StringWithAlloc;
      }
      goto LABEL_35;
    }
    goto LABEL_24;
  }
LABEL_35:
  v24 = *a4;
  if ( *a4 )
  {
    v25 = *a3;
    if ( *a3 )
    {
      v26 = 0;
      do
      {
        v27 = v26;
        CoTaskMemFree(v24[v27].pwszClassName);
        CoTaskMemFree(v24[v27].pwszDescription);
        if ( v24[v27].UiInfo.type == UIT_HELP_PANE )
        {
          pwzNull = v24[v27].UiInfo.pwzNull;
          if ( pwzNull )
            CoTaskMemFree(pwzNull);
        }
        ++v26;
      }
      while ( v26 < v25 );
      CoTaskMemFree(v24);
    }
  }
  *a3 = 0;
  *a4 = 0;
  return (unsigned int)StringWithAlloc;
}

```

## disassembly

```asm
0x180008130  push    rbp
0x180008132  push    rbx
0x180008133  push    rsi
0x180008134  push    rdi
0x180008135  push    r12
0x180008137  push    r13
0x180008139  push    r14
0x18000813b  push    r15
0x18000813d  mov     rbp, rsp
0x180008140  sub     rsp, 58h
0x180008144  xor     ebx, ebx
0x180008146  mov     r12, r9
0x180008149  mov     [r8], ebx
0x18000814c  mov     r13, r8
0x18000814f  mov     [r9], rbx
0x180008152  mov     rdi, rcx
0x180008155  cmp     edx, 1
0x180008158  jnz     loc_1800082A9
0x18000815e  mov     edx, [rcx+1D8h]
0x180008164  xor     esi, esi
0x180008166  cmp     edx, 8
0x180008169  jg      short loc_1800081CE
0x18000816b  jz      short loc_1800081C5
0x18000816d  test    edx, edx
0x18000816f  jz      loc_1800082A9
0x180008175  sub     edx, 1
0x180008178  jz      short loc_1800081BC
0x18000817a  sub     edx, 1
0x18000817d  jz      short loc_1800081BC
0x18000817f  sub     edx, 1
0x180008182  jz      short loc_1800081BC
0x180008184  sub     edx, 1
0x180008187  jz      short loc_1800081BC
0x180008189  sub     edx, 1
0x18000818c  jz      short loc_1800081B0
0x18000818e  sub     edx, 1
0x180008191  jz      short loc_1800081A4
0x180008193  cmp     edx, 1
0x180008196  jnz     short loc_1800081F1
0x180008198  movups  xmm0, cs:ID_WFP_REPAIR_AUTH_FAILURE_CERT_ERROR
0x18000819f  jmp     loc_180008244
0x1800081a4  movups  xmm0, cs:ID_WFP_REPAIR_AUTH_FAILURE_CERT_EXPIRED
0x1800081ab  jmp     loc_180008244
0x1800081b0  movups  xmm0, cs:ID_WFP_REPAIR_POLICY_MISMATCH_CRED_FAILURE
0x1800081b7  jmp     loc_180008244
0x1800081bc  movups  xmm0, cs:ID_WFP_REPAIR_POLICY_MISMATCH
0x1800081c3  jmp     short loc_180008244
0x1800081c5  movups  xmm0, cs:ID_WFP_REPAIR_AUTH_FAILURE_KERB_ERROR
0x1800081cc  jmp     short loc_180008244
0x1800081ce  sub     edx, 9
0x1800081d1  jz      short loc_18000823D
0x1800081d3  sub     edx, 1
0x1800081d6  jz      short loc_180008228
0x1800081d8  sub     edx, 1
0x1800081db  jz      short loc_18000821F
0x1800081dd  sub     edx, 1
0x1800081e0  jz      short loc_180008216
0x1800081e2  sub     edx, 1
0x1800081e5  jz      short loc_18000820D
0x1800081e7  sub     edx, 1
0x1800081ea  jz      short loc_180008204
0x1800081ec  cmp     edx, 2
0x1800081ef  jz      short loc_1800081FB
0x1800081f1  mov     ebx, 80004001h
0x1800081f6  jmp     loc_1800082A9
0x1800081fb  movups  xmm0, cs:ID_WFP_REPAIR_IPSEC_GENERIC_FAILURE
0x180008202  jmp     short loc_180008244
0x180008204  movups  xmm0, cs:ID_WFP_REPAIR_AUTHZ_FAILURE_AUTH_ASSURANCE
0x18000820b  jmp     short loc_180008244
0x18000820d  movups  xmm0, cs:ID_WFP_REPAIR_AUTHZ_FAILURE_SMART_CARD_AND_CERT_MAP
0x180008214  jmp     short loc_180008244
0x180008216  movups  xmm0, cs:ID_WFP_REPAIR_AUTHZ_FAILURE_SMART_CARD
0x18000821d  jmp     short loc_180008244
0x18000821f  movups  xmm0, cs:ID_WFP_REPAIR_MUTIPLE_AUTH_FAILED
0x180008226  jmp     short loc_180008244
0x180008228  movups  xmm0, cs:ID_WFP_REPAIR_CLASSIFY_DROP
0x18000822f  mov     esi, 870h
0x180008234  mov     byte ptr [rcx+1D1h], 1
0x18000823b  jmp     short loc_180008244
0x18000823d  movups  xmm0, cs:ID_WFP_REPAIR_AUTH_FAILURE_PRESHARED_KEY
0x180008244  mov     r8d, 1; enum tagPROBLEM_TYPE
0x18000824a  mov     [rsp+58h+var_28], r12; struct tagRepairInfo **
0x18000824f  lea     r9, [rbp+var_18]; struct _GUID *
0x180008253  mov     [rsp+58h+var_30], r13; unsigned int *
0x180008258  lea     rdx, ?m_repairInfos@CFilteringPlatformHelperClass@@0QBUtagRepairInfoMap@@B; struct tagRepairInfoMap *
0x18000825f  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x180008264  lea     ecx, [r8+0Bh]; unsigned int
0x180008268  call    ?BuildRepairInfos@@YAJKPEBUtagRepairInfoMap@@W4tagPROBLEM_TYPE@@PEAU_GUID@@KPEAKPEAPEAUtagRepairInfo@@H@Z; BuildRepairInfos(ulong,tagRepairInfoMap const *,tagPROBLEM_TYPE,_GUID *,ulong,ulong *,tagRepairInfo * *,int)
0x18000826d  mov     ebx, eax
0x18000826f  test    eax, eax
0x180008271  js      short loc_1800082A9
0x180008273  cmp     byte ptr [rdi+1D1h], 0
0x18000827a  jz      loc_180008311
0x180008280  mov     rax, [r12]
0x180008284  mov     r8d, 1000h; unsigned int
0x18000828a  mov     ecx, esi; uID
0x18000828c  lea     rdx, [rax+40h]; unsigned __int16 **
0x180008290  mov     dword ptr [rax+38h], 3
0x180008297  mov     qword ptr [rdx], 0
0x18000829e  call    ?LoadStringWithAlloc@@YAJIPEAPEAGI@Z; LoadStringWithAlloc(uint,ushort * *,uint)
0x1800082a3  mov     ebx, eax
0x1800082a5  test    eax, eax
0x1800082a7  jns     short loc_180008311
0x1800082a9  mov     rdi, [r12]
0x1800082ad  test    rdi, rdi
0x1800082b0  jz      short loc_180008301
0x1800082b2  mov     r15d, [r13+0]
0x1800082b6  test    r15d, r15d
0x1800082b9  jz      short loc_180008301
0x1800082bb  xor     esi, esi
0x1800082bd  mov     eax, esi
0x1800082bf  imul    r14, rax, 70h ; 'p'
0x1800082c3  mov     rcx, [r14+rdi+10h]; pv
0x1800082c8  call    cs:__imp_CoTaskMemFree
0x1800082ce  mov     rcx, [r14+rdi+18h]; pv
0x1800082d3  call    cs:__imp_CoTaskMemFree
0x1800082d9  cmp     dword ptr [r14+rdi+38h], 3
0x1800082df  jnz     short loc_1800082F1
0x1800082e1  mov     rcx, [r14+rdi+40h]; pv
0x1800082e6  test    rcx, rcx
0x1800082e9  jz      short loc_1800082F1
0x1800082eb  call    cs:__imp_CoTaskMemFree
0x1800082f1  inc     esi
0x1800082f3  cmp     esi, r15d
0x1800082f6  jb      short loc_1800082BD
0x1800082f8  mov     rcx, rdi; pv
0x1800082fb  call    cs:__imp_CoTaskMemFree
0x180008301  mov     dword ptr [r13+0], 0
0x180008309  mov     qword ptr [r12], 0
0x180008311  mov     eax, ebx
0x180008313  add     rsp, 58h
0x180008317  pop     r15
0x180008319  pop     r14
0x18000831b  pop     r13
0x18000831d  pop     r12
0x18000831f  pop     rdi
0x180008320  pop     rsi
0x180008321  pop     rbx
0x180008322  pop     rbp
0x180008323  retn
```
