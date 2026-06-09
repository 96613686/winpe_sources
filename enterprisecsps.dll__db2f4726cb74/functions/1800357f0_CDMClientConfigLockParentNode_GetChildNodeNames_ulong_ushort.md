# CDMClientConfigLockParentNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x1800357f0`
- end: `0x1800359a7`
- name: `?GetChildNodeNames@CDMClientConfigLockParentNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `439`
- prototype: `__int64 __fastcall(CDMClientConfigLockParentNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180009cc4`
- `0x180015e90`
- `0x1800357f0`
- `0x180038514`
- `0x1800397e0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180035901`
- `OLEAUT32!__imp_SysAllocString` at `0x180035901`
- `OLEAUT32!__imp_SysFreeString` at `0x18003593b`
- `OLEAUT32!__imp_SysFreeString` at `0x18003593b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035958`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035958`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800358b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800358b6`

## string_xrefs

- `0x180035975`: `CDMClientConfigLockParentNode::GetChildNodeNames`

## pseudocode

```c
__int64 __fastcall CDMClientConfigLockParentNode::GetChildNodeNames(
        CDMClientConfigLockParentNode *this,
        unsigned int *a2,
        unsigned __int16 ***a3)
{
  unsigned int *v4; // r15
  int v6; // r9d
  int v7; // ebx
  unsigned int v8; // edi
  __int64 i; // rcx
  unsigned int v10; // eax
  size_t v11; // rsi
  unsigned __int16 **v12; // rax
  unsigned __int16 **v13; // r14
  __int64 v14; // rsi
  int j; // ebp
  const OLECHAR *v16; // rcx
  BSTR v17; // rax
  __int64 k; // rsi
  OLECHAR *v19; // rcx
  SIZE_T cb; // [rsp+98h] [rbp+20h] BYREF

  v4 = a2;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigLock_DMClientCSP>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ConfigLock_DMClientCSP>::GetImpl'::`2'::impl,
    a2);
  if ( !v4 || !a3 )
    return 2147942487LL;
  if ( *((_DWORD *)this + 11) == 70 )
  {
    v8 = 0;
    *a3 = 0;
    LODWORD(cb) = 0;
    *v4 = 0;
    for ( i = 0; i != 3; ++i )
    {
      v10 = v8 + 1;
      if ( !(&c_rgConfigLockNodes)[i] )
        v10 = v8;
      v8 = v10;
    }
    v7 = ULongLongToULong(8LL * v10, (unsigned int *)&cb);
    if ( v7 >= 0 )
    {
      v11 = (unsigned int)cb;
      v12 = (unsigned __int16 **)CoTaskMemAlloc((unsigned int)cb);
      v13 = v12;
      if ( v12 )
      {
        memset_0(v12, 0, v11);
        v14 = 0;
        for ( j = 0; j < 3; ++j )
        {
          if ( (unsigned int)v14 >= v8 )
            goto LABEL_24;
          v16 = (const OLECHAR *)(&c_rgConfigLockNodes)[j];
          if ( v16 )
          {
            v17 = SysAllocString(v16);
            v13[v14] = v17;
            if ( !v17 )
            {
              v7 = -2147024882;
              goto LABEL_25;
            }
            v14 = (unsigned int)(v14 + 1);
          }
        }
        if ( (_DWORD)v14 == v8 )
        {
          *v4 = v14;
          v6 = (int)v13;
          *a3 = v13;
          goto LABEL_32;
        }
LABEL_24:
        v7 = -2147418113;
LABEL_25:
        for ( k = 0; (unsigned int)k < v8; k = (unsigned int)(k + 1) )
        {
          v19 = v13[k];
          if ( v19 )
          {
            SysFreeString(v19);
            v13[k] = 0;
          }
        }
        CoTaskMemFree(v13);
        v6 = 0;
      }
      else
      {
        v7 = -2147024882;
      }
    }
  }
  else if ( *((_DWORD *)this + 11) == 71 || (unsigned int)(*((_DWORD *)this + 11) - 72) < 2 )
  {
    v7 = -2046820335;
  }
  else
  {
    v7 = -2147418113;
  }
LABEL_32:
  DmClientLogging::Write(L"CDMClientConfigLockParentNode::GetChildNodeNames", *((_DWORD *)this + 11), v7, v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800357f0  push    rbx
0x1800357f2  push    rbp
0x1800357f3  push    rsi
0x1800357f4  push    rdi
0x1800357f5  push    r12
0x1800357f7  push    r13
0x1800357f9  push    r14
0x1800357fb  push    r15
0x1800357fd  sub     rsp, 38h
0x180035801  mov     r12, r8
0x180035804  mov     r15, rdx
0x180035807  mov     r13, rcx
0x18003580a  mov     dl, 1
0x18003580c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ConfigLock_DMClientCSP@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ConfigLock_DMClientCSP@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigLock_DMClientCSP> `wil::Feature<__WilFeatureTraits_Feature_ConfigLock_DMClientCSP>::GetImpl(void)'::`2'::impl
0x180035813  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ConfigLock_DMClientCSP@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigLock_DMClientCSP>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180035818  test    r15, r15
0x18003581b  jz      loc_180035990
0x180035821  test    r12, r12
0x180035824  jz      loc_180035990
0x18003582a  mov     ecx, [r13+2Ch]
0x18003582e  sub     ecx, 46h ; 'F'
0x180035831  jz      short loc_180035856
0x180035833  sub     ecx, 1
0x180035836  jz      short loc_18003584C
0x180035838  sub     ecx, 1
0x18003583b  jz      short loc_18003584C
0x18003583d  cmp     ecx, 1
0x180035840  jz      short loc_18003584C
0x180035842  mov     ebx, 8000FFFFh
0x180035847  jmp     loc_180035971
0x18003584c  mov     ebx, 86000011h
0x180035851  jmp     loc_180035971
0x180035856  xor     edi, edi
0x180035858  mov     qword ptr [r12], 0
0x180035860  xor     r9d, r9d
0x180035863  mov     dword ptr [rsp+78h+cb], edi
0x18003586a  mov     [r15], edi
0x18003586d  lea     rdx, ?c_rgConfigLockNodes@@3PAPEBGA; ushort const * near * c_rgConfigLockNodes
0x180035874  mov     qword ptr [rsp+78h+var_58], r9
0x180035879  xor     ecx, ecx
0x18003587b  cmp     [rdx+rcx*8], r9
0x18003587f  lea     eax, [rdi+1]
0x180035882  cmovz   eax, edi
0x180035885  inc     rcx
0x180035888  mov     edi, eax
0x18003588a  cmp     rcx, 3
0x18003588e  jnz     short loc_18003587B
0x180035890  mov     ecx, edi
0x180035892  lea     rdx, [rsp+78h+cb]; unsigned int *
0x18003589a  shl     rcx, 3; unsigned __int64
0x18003589e  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800358a3  mov     ebx, eax
0x1800358a5  test    eax, eax
0x1800358a7  js      loc_180035969
0x1800358ad  mov     esi, dword ptr [rsp+78h+cb]
0x1800358b4  mov     ecx, esi; cb
0x1800358b6  call    cs:__imp_CoTaskMemAlloc
0x1800358bd  nop     dword ptr [rax+rax+00h]
0x1800358c2  mov     r14, rax
0x1800358c5  test    rax, rax
0x1800358c8  jnz     short loc_1800358D4
0x1800358ca  mov     ebx, 8007000Eh
0x1800358cf  jmp     loc_180035971
0x1800358d4  mov     r8, rsi; Size
0x1800358d7  xor     edx, edx; Val
0x1800358d9  mov     rcx, r14; void *
0x1800358dc  call    memset_0
0x1800358e1  xor     esi, esi
0x1800358e3  xor     ebp, ebp
0x1800358e5  cmp     ebp, 3
0x1800358e8  jge     short loc_180035923
0x1800358ea  cmp     esi, edi
0x1800358ec  jnb     short loc_180035927
0x1800358ee  movsxd  rax, ebp
0x1800358f1  lea     rcx, ?c_rgConfigLockNodes@@3PAPEBGA; ushort const * near * c_rgConfigLockNodes
0x1800358f8  mov     rcx, [rcx+rax*8]; psz
0x1800358fc  test    rcx, rcx
0x1800358ff  jz      short loc_180035918
0x180035901  call    cs:__imp_SysAllocString
0x180035908  nop     dword ptr [rax+rax+00h]
0x18003590d  mov     [r14+rsi*8], rax
0x180035911  test    rax, rax
0x180035914  jz      short loc_18003591C
0x180035916  inc     esi
0x180035918  inc     ebp
0x18003591a  jmp     short loc_1800358E5
0x18003591c  mov     ebx, 8007000Eh
0x180035921  jmp     short loc_18003592C
0x180035923  cmp     esi, edi
0x180035925  jz      short loc_180035988
0x180035927  mov     ebx, 8000FFFFh
0x18003592c  xor     esi, esi
0x18003592e  test    edi, edi
0x180035930  jz      short loc_180035955
0x180035932  mov     rcx, [r14+rsi*8]; bstrString
0x180035936  test    rcx, rcx
0x180035939  jz      short loc_18003594F
0x18003593b  call    cs:__imp_SysFreeString
0x180035942  nop     dword ptr [rax+rax+00h]
0x180035947  mov     qword ptr [r14+rsi*8], 0
0x18003594f  inc     esi
0x180035951  cmp     esi, edi
0x180035953  jb      short loc_180035932
0x180035955  mov     rcx, r14; pv
0x180035958  call    cs:__imp_CoTaskMemFree
0x18003595f  nop     dword ptr [rax+rax+00h]
0x180035964  mov     r9, qword ptr [rsp+78h+var_58]; int
0x180035969  test    ebx, ebx
0x18003596b  js      short loc_180035971
0x18003596d  mov     [r12], r9
0x180035971  mov     edx, [r13+2Ch]; unsigned int
0x180035975  lea     rcx, aCdmclientconfi_0; "CDMClientConfigLockParentNode::GetChild"...
0x18003597c  mov     r8d, ebx; int
0x18003597f  call    ?Write@DmClientLogging@@SAXPEBGKJH@Z; DmClientLogging::Write(ushort const *,ulong,long,int)
0x180035984  mov     eax, ebx
0x180035986  jmp     short loc_180035995
0x180035988  mov     [r15], esi
0x18003598b  mov     r9, r14
0x18003598e  jmp     short loc_18003596D
0x180035990  mov     eax, 80070057h
0x180035995  add     rsp, 38h
0x180035999  pop     r15
0x18003599b  pop     r14
0x18003599d  pop     r13
0x18003599f  pop     r12
0x1800359a1  pop     rdi
0x1800359a2  pop     rsi
0x1800359a3  pop     rbp
0x1800359a4  pop     rbx
0x1800359a5  retn
```
