# CDMClientConfigRefreshNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x1800359b0`
- end: `0x180035b62`
- name: `?GetChildNodeNames@CDMClientConfigRefreshNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `434`
- prototype: `__int64 __fastcall(CDMClientConfigRefreshNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180009cc4`
- `0x180015e90`
- `0x1800359b0`
- `0x1800385a4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180035ad4`
- `OLEAUT32!__imp_SysAllocString` at `0x180035ad4`
- `OLEAUT32!__imp_SysFreeString` at `0x180035b0f`
- `OLEAUT32!__imp_SysFreeString` at `0x180035b0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035b2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035b2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035a8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035a8d`

## pseudocode

```c
__int64 __fastcall CDMClientConfigRefreshNode::GetChildNodeNames(
        CDMClientConfigRefreshNode *this,
        unsigned int *a2,
        unsigned __int16 ***a3)
{
  unsigned int *v4; // r12
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ebx
  unsigned int v10; // edi
  __int64 v11; // rcx
  unsigned int v12; // eax
  size_t v13; // rbp
  unsigned __int16 **v14; // rax
  unsigned __int16 **v15; // rsi
  __int64 v16; // rbp
  int i; // r14d
  const OLECHAR *v18; // rcx
  BSTR v19; // rax
  __int64 j; // rbp
  OLECHAR *v21; // rcx
  OLECHAR *psz[9]; // [rsp+20h] [rbp-48h]
  SIZE_T cb; // [rsp+88h] [rbp+20h] BYREF

  v4 = a2;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigRefresh>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ConfigRefresh>::GetImpl'::`2'::impl,
    a2);
  v6 = *((_DWORD *)this + 11);
  psz[0] = (OLECHAR *)L"Enabled";
  psz[1] = (OLECHAR *)L"Cadence";
  psz[2] = (OLECHAR *)L"PausePeriod";
  v7 = v6 - 90;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 && (unsigned int)(v8 - 1) >= 2 )
      return (unsigned int)-2147418113;
    else
      return (unsigned int)-2046820335;
  }
  else if ( v4 && a3 )
  {
    v10 = 0;
    *v4 = 0;
    v11 = 0;
    *a3 = 0;
    LODWORD(cb) = 0;
    do
    {
      v12 = v10 + 1;
      if ( !psz[v11] )
        v12 = v10;
      ++v11;
      v10 = v12;
    }
    while ( v11 != 3 );
    v9 = ULongLongToULong(8LL * v12, (unsigned int *)&cb);
    if ( v9 >= 0 )
    {
      v13 = (unsigned int)cb;
      v14 = (unsigned __int16 **)CoTaskMemAlloc((unsigned int)cb);
      v15 = v14;
      if ( v14 )
      {
        memset_0(v14, 0, v13);
        v16 = 0;
        for ( i = 0; i < 3; ++i )
        {
          if ( (unsigned int)v16 >= v10 )
            goto LABEL_24;
          v18 = psz[i];
          if ( v18 )
          {
            v19 = SysAllocString(v18);
            v15[v16] = v19;
            if ( !v19 )
            {
              v9 = -2147024882;
              goto LABEL_25;
            }
            v16 = (unsigned int)(v16 + 1);
          }
        }
        if ( (_DWORD)v16 == v10 )
        {
          *v4 = v16;
          *a3 = v15;
          return (unsigned int)v9;
        }
LABEL_24:
        v9 = -2147418113;
LABEL_25:
        for ( j = 0; (unsigned int)j < v10; j = (unsigned int)(j + 1) )
        {
          v21 = v15[j];
          if ( v21 )
          {
            SysFreeString(v21);
            v15[j] = 0;
          }
        }
        CoTaskMemFree(v15);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800359b0  mov     [rsp+arg_0], rbx
0x1800359b5  mov     [rsp+arg_8], rbp
0x1800359ba  push    rsi
0x1800359bb  push    rdi
0x1800359bc  push    r12
0x1800359be  push    r14
0x1800359c0  push    r15
0x1800359c2  sub     rsp, 40h
0x1800359c6  mov     r15, r8
0x1800359c9  mov     r12, rdx
0x1800359cc  mov     rbx, rcx
0x1800359cf  mov     dl, 1
0x1800359d1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ConfigRefresh@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ConfigRefresh@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigRefresh> `wil::Feature<__WilFeatureTraits_Feature_ConfigRefresh>::GetImpl(void)'::`2'::impl
0x1800359d8  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ConfigRefresh@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigRefresh>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800359dd  mov     ecx, [rbx+2Ch]
0x1800359e0  lea     rax, aEnabled; "Enabled"
0x1800359e7  mov     [rsp+68h+psz], rax
0x1800359ec  lea     rax, aCadence; "Cadence"
0x1800359f3  mov     [rsp+68h+var_40], rax
0x1800359f8  lea     rax, aPauseperiod; "PausePeriod"
0x1800359ff  mov     [rsp+68h+var_38], rax
0x180035a04  sub     ecx, 5Ah ; 'Z'
0x180035a07  jz      short loc_180035A2C
0x180035a09  sub     ecx, 1
0x180035a0c  jz      short loc_180035A22
0x180035a0e  sub     ecx, 1
0x180035a11  jz      short loc_180035A22
0x180035a13  cmp     ecx, 1
0x180035a16  jz      short loc_180035A22
0x180035a18  mov     ebx, 8000FFFFh
0x180035a1d  jmp     loc_180035B48
0x180035a22  mov     ebx, 86000011h
0x180035a27  jmp     loc_180035B48
0x180035a2c  test    r12, r12
0x180035a2f  jz      loc_180035B43
0x180035a35  test    r15, r15
0x180035a38  jz      loc_180035B43
0x180035a3e  xor     edi, edi
0x180035a40  mov     [r12], edi
0x180035a44  xor     ecx, ecx
0x180035a46  mov     [r15], rdi
0x180035a49  mov     dword ptr [rsp+68h+cb], edi
0x180035a50  cmp     [rsp+rcx*8+68h+psz], 0
0x180035a56  lea     eax, [rdi+1]
0x180035a59  cmovz   eax, edi
0x180035a5c  inc     rcx
0x180035a5f  mov     edi, eax
0x180035a61  cmp     rcx, 3
0x180035a65  jnz     short loc_180035A50
0x180035a67  mov     ecx, edi
0x180035a69  lea     rdx, [rsp+68h+cb]; unsigned int *
0x180035a71  shl     rcx, 3; unsigned __int64
0x180035a75  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180035a7a  mov     ebx, eax
0x180035a7c  test    eax, eax
0x180035a7e  js      loc_180035B48
0x180035a84  mov     ebp, dword ptr [rsp+68h+cb]
0x180035a8b  mov     ecx, ebp; cb
0x180035a8d  call    cs:__imp_CoTaskMemAlloc
0x180035a94  nop     dword ptr [rax+rax+00h]
0x180035a99  mov     rsi, rax
0x180035a9c  test    rax, rax
0x180035a9f  jnz     short loc_180035AAB
0x180035aa1  mov     ebx, 8007000Eh
0x180035aa6  jmp     loc_180035B48
0x180035aab  mov     r8, rbp; Size
0x180035aae  xor     edx, edx; Val
0x180035ab0  mov     rcx, rsi; void *
0x180035ab3  call    memset_0
0x180035ab8  xor     ebp, ebp
0x180035aba  xor     r14d, r14d
0x180035abd  cmp     r14d, 3
0x180035ac1  jge     short loc_180035AF7
0x180035ac3  cmp     ebp, edi
0x180035ac5  jnb     short loc_180035AFB
0x180035ac7  movsxd  rax, r14d
0x180035aca  mov     rcx, [rsp+rax*8+68h+psz]; psz
0x180035acf  test    rcx, rcx
0x180035ad2  jz      short loc_180035AEB
0x180035ad4  call    cs:__imp_SysAllocString
0x180035adb  nop     dword ptr [rax+rax+00h]
0x180035ae0  mov     [rsi+rbp*8], rax
0x180035ae4  test    rax, rax
0x180035ae7  jz      short loc_180035AF0
0x180035ae9  inc     ebp
0x180035aeb  inc     r14d
0x180035aee  jmp     short loc_180035ABD
0x180035af0  mov     ebx, 8007000Eh
0x180035af5  jmp     short loc_180035B00
0x180035af7  cmp     ebp, edi
0x180035af9  jz      short loc_180035B3A
0x180035afb  mov     ebx, 8000FFFFh
0x180035b00  xor     ebp, ebp
0x180035b02  test    edi, edi
0x180035b04  jz      short loc_180035B29
0x180035b06  mov     rcx, [rsi+rbp*8]; bstrString
0x180035b0a  test    rcx, rcx
0x180035b0d  jz      short loc_180035B23
0x180035b0f  call    cs:__imp_SysFreeString
0x180035b16  nop     dword ptr [rax+rax+00h]
0x180035b1b  mov     qword ptr [rsi+rbp*8], 0
0x180035b23  inc     ebp
0x180035b25  cmp     ebp, edi
0x180035b27  jb      short loc_180035B06
0x180035b29  mov     rcx, rsi; pv
0x180035b2c  call    cs:__imp_CoTaskMemFree
0x180035b33  nop     dword ptr [rax+rax+00h]
0x180035b38  jmp     short loc_180035B48
0x180035b3a  mov     [r12], ebp
0x180035b3e  mov     [r15], rsi
0x180035b41  jmp     short loc_180035B48
0x180035b43  mov     ebx, 80070057h
0x180035b48  mov     rbp, [rsp+68h+arg_8]
0x180035b4d  mov     eax, ebx
0x180035b4f  mov     rbx, [rsp+68h+arg_0]
0x180035b54  add     rsp, 40h
0x180035b58  pop     r15
0x180035b5a  pop     r14
0x180035b5c  pop     r12
0x180035b5e  pop     rdi
0x180035b5f  pop     rsi
0x180035b60  retn
```
