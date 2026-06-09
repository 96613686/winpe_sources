# DataStoreServer::GetAttributeDictionarySchema(int &,ushort * &)

- ea: `0x180007fb4`
- end: `0x1800081b1`
- name: `?GetAttributeDictionarySchema@DataStoreServer@@QEAAJAEAHAEAPEAG@Z`
- size: `509`
- prototype: `__int64 __fastcall(DataStoreServer *__hidden this, int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006c10`

## callees

- `0x1800020b1`
- `0x180007150`
- `0x1800071ac`
- `0x1800076dc`
- `0x180007fb4`
- `0x180008ce4`
- `0x1800093cc`
- `0x18000d990`
- `0x18000db68`
- `0x180010010`

## import_xrefs

- `KERNEL32!TryEnterCriticalSection` at `0x180008046`
- `KERNEL32!TryEnterCriticalSection` at `0x180008046`
- `KERNEL32!SwitchToThread` at `0x18000803d`
- `KERNEL32!SwitchToThread` at `0x18000803d`
- `KERNEL32!EnterCriticalSection` at `0x180008055`
- `KERNEL32!EnterCriticalSection` at `0x180008055`
- `KERNEL32!LeaveCriticalSection` at `0x18000818a`
- `KERNEL32!LeaveCriticalSection` at `0x18000818a`
- `ole32!CoTaskMemAlloc` at `0x18000811e`
- `ole32!CoTaskMemAlloc` at `0x18000811e`
- `OLEAUT32!__imp_SysStringLen` at `0x180008101`
- `OLEAUT32!__imp_SysStringLen` at `0x180008101`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DataStoreServer::GetAttributeDictionarySchema(
        DataStoreServer *this,
        UINT *a2,
        unsigned __int16 **a3)
{
  struct _RTL_CRITICAL_SECTION *v7; // rsi
  int v8; // edi
  _QWORD *v9; // rdi
  __int64 v10; // rcx
  int v11; // ebx
  OLECHAR ***v12; // rax
  OLECHAR *v13; // rcx
  UINT v14; // eax
  unsigned __int16 *v15; // rax
  _QWORD *v16; // rdx
  char v17; // [rsp+50h] [rbp+8h] BYREF

  if ( *((_BYTE *)this + 48) )
  {
    v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
    v8 = 0;
    while ( !TryEnterCriticalSection(v7) )
    {
      if ( ++v8 >= 100 )
      {
        EnterCriticalSection(v7);
        break;
      }
      SwitchToThread();
    }
    v9 = (_QWORD *)((char *)this + 2168);
    v10 = *((_QWORD *)this + 271);
    if ( v10 )
    {
      v11 = 0;
    }
    else
    {
      v11 = DataStoreServer::Load(0, (const OLECHAR *)this + 547, (LPVOID *)this + 271);
      if ( v11 < 0 || (v10 = *v9) == 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WppDbgPrint("Load() failed:%!hresult! for GetAttributeDictionarySchema");
          WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids);
        }
        goto LABEL_31;
      }
    }
    v12 = (OLECHAR ***)MSXML2::IXMLDOMNode::Getxml(v10, &v17);
    if ( *v12 && (v13 = **v12) != 0 )
      v14 = SysStringLen(v13);
    else
      v14 = 0;
    *a2 = v14;
    _bstr_t::~_bstr_t((_bstr_t *)&v17);
    v15 = (unsigned __int16 *)CoTaskMemAlloc(2LL * (int)*a2);
    *a3 = v15;
    if ( !v15 )
    {
      v11 = -2147024882;
      goto LABEL_32;
    }
    if ( !*v9 )
      _com_issue_error(-2147467261);
    v16 = *(_QWORD **)MSXML2::IXMLDOMNode::Getxml(*v9, &v17);
    if ( v16 )
      v16 = (_QWORD *)*v16;
    memcpy_0(*a3, v16, 2LL * (int)*a2);
    _bstr_t::~_bstr_t((_bstr_t *)&v17);
LABEL_31:
    if ( v11 >= 0 )
    {
LABEL_34:
      LeaveCriticalSection(v7);
      return (unsigned int)v11;
    }
LABEL_32:
    if ( *v9 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 16LL))(*v9);
      *v9 = 0;
    }
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint("DataStoreServer::GetAttributeDictionarySchema()Error: DataStoreServer() is not initialized");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, "NPSDS");
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180007fb4  mov     [rsp+arg_8], rbx
0x180007fb9  mov     [rsp+arg_10], rsi
0x180007fbe  push    rdi
0x180007fbf  push    r14
0x180007fc1  push    r15
0x180007fc3  sub     rsp, 30h
0x180007fc7  mov     r15, r8
0x180007fca  mov     r14, rdx
0x180007fcd  mov     rbx, rcx
0x180007fd0  cmp     byte ptr [rcx+30h], 0
0x180007fd4  jnz     short loc_18000802E
0x180007fd6  lea     rcx, WPP_GLOBAL_Control
0x180007fdd  mov     rax, cs:WPP_GLOBAL_Control
0x180007fe4  cmp     rax, rcx
0x180007fe7  jz      short loc_180008024
0x180007fe9  cmp     byte ptr [rax+19h], 2
0x180007fed  jb      short loc_180008024
0x180007fef  test    byte ptr [rax+1Ch], 10h
0x180007ff3  jz      short loc_180008024
0x180007ff5  lea     rcx, aDatastoreserve_18; "DataStoreServer::GetAttributeDictionary"...
0x180007ffc  call    WppDbgPrint
0x180008001  mov     edx, 11h
0x180008006  lea     r9, aNpsds; "NPSDS"
0x18000800d  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x180008014  mov     rcx, cs:WPP_GLOBAL_Control
0x18000801b  mov     rcx, [rcx+10h]
0x18000801f  call    WPP_SF_s
0x180008024  mov     eax, 80004005h
0x180008029  jmp     loc_180008192
0x18000802e  lea     rsi, [rcx+8]
0x180008032  xor     edi, edi
0x180008034  jmp     short loc_180008043
0x180008036  inc     edi
0x180008038  cmp     edi, 64h ; 'd'
0x18000803b  jge     short loc_180008052
0x18000803d  call    cs:__imp_SwitchToThread
0x180008043  mov     rcx, rsi; lpCriticalSection
0x180008046  call    cs:__imp_TryEnterCriticalSection
0x18000804c  test    eax, eax
0x18000804e  jz      short loc_180008036
0x180008050  jmp     short loc_18000805B
0x180008052  mov     rcx, rsi; lpCriticalSection
0x180008055  call    cs:__imp_EnterCriticalSection
0x18000805b  lea     rdi, [rbx+878h]
0x180008062  mov     rcx, [rdi]
0x180008065  test    rcx, rcx
0x180008068  jnz     short loc_1800080E5
0x18000806a  lea     rdx, [rbx+446h]
0x180008071  mov     r8, rdi
0x180008074  call    ?Load@DataStoreServer@@AEAAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; DataStoreServer::Load(ushort const *,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)
0x180008079  mov     ebx, eax
0x18000807b  test    eax, eax
0x18000807d  js      short loc_180008087
0x18000807f  mov     rcx, [rdi]
0x180008082  test    rcx, rcx
0x180008085  jnz     short loc_1800080E7
0x180008087  lea     rcx, WPP_GLOBAL_Control
0x18000808e  mov     rax, cs:WPP_GLOBAL_Control
0x180008095  cmp     rax, rcx
0x180008098  jz      loc_180008168
0x18000809e  cmp     byte ptr [rax+19h], 2
0x1800080a2  jb      loc_180008168
0x1800080a8  test    byte ptr [rax+1Ch], 10h
0x1800080ac  jz      loc_180008168
0x1800080b2  mov     edx, ebx
0x1800080b4  lea     rcx, aLoadFailedHres_4; "Load() failed:%!hresult! for GetAttribu"...
0x1800080bb  call    WppDbgPrint
0x1800080c0  mov     edx, 12h
0x1800080c5  mov     [rsp+48h+var_28], ebx
0x1800080c9  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x1800080d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080d7  mov     rcx, [rcx+10h]
0x1800080db  call    WPP_SF_sd
0x1800080e0  jmp     loc_180008168
0x1800080e5  xor     ebx, ebx
0x1800080e7  lea     rdx, [rsp+48h+arg_0]
0x1800080ec  call    ?Getxml@IXMLDOMNode@MSXML2@@QEAA?AV_bstr_t@@XZ; MSXML2::IXMLDOMNode::Getxml(void)
0x1800080f1  mov     rcx, [rax]
0x1800080f4  test    rcx, rcx
0x1800080f7  jz      short loc_180008109
0x1800080f9  mov     rcx, [rcx]; pbstr
0x1800080fc  test    rcx, rcx
0x1800080ff  jz      short loc_180008109
0x180008101  call    cs:__imp_SysStringLen
0x180008107  jmp     short loc_18000810B
0x180008109  xor     eax, eax
0x18000810b  mov     [r14], eax
0x18000810e  lea     rcx, [rsp+48h+arg_0]; this
0x180008113  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180008118  movsxd  rcx, dword ptr [r14]
0x18000811b  add     rcx, rcx; cb
0x18000811e  call    cs:__imp_CoTaskMemAlloc
0x180008124  mov     [r15], rax
0x180008127  test    rax, rax
0x18000812a  jnz     short loc_180008133
0x18000812c  mov     ebx, 8007000Eh
0x180008131  jmp     short loc_18000816C
0x180008133  mov     rcx, [rdi]
0x180008136  test    rcx, rcx
0x180008139  jz      short loc_1800081A6
0x18000813b  lea     rdx, [rsp+48h+arg_0]
0x180008140  call    ?Getxml@IXMLDOMNode@MSXML2@@QEAA?AV_bstr_t@@XZ; MSXML2::IXMLDOMNode::Getxml(void)
0x180008145  mov     rdx, [rax]
0x180008148  test    rdx, rdx
0x18000814b  jz      short loc_180008150
0x18000814d  mov     rdx, [rdx]; Src
0x180008150  movsxd  r8, dword ptr [r14]
0x180008153  add     r8, r8; Size
0x180008156  mov     rcx, [r15]; void *
0x180008159  call    memcpy_0
0x18000815e  lea     rcx, [rsp+48h+arg_0]; this
0x180008163  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180008168  test    ebx, ebx
0x18000816a  jns     short loc_180008187
0x18000816c  mov     rcx, [rdi]
0x18000816f  test    rcx, rcx
0x180008172  jz      short loc_180008187
0x180008174  mov     rax, [rcx]
0x180008177  mov     rax, [rax+10h]
0x18000817b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008180  mov     qword ptr [rdi], 0
0x180008187  mov     rcx, rsi; lpCriticalSection
0x18000818a  call    cs:__imp_LeaveCriticalSection
0x180008190  mov     eax, ebx
0x180008192  mov     rbx, [rsp+48h+arg_8]
0x180008197  mov     rsi, [rsp+48h+arg_10]
0x18000819c  add     rsp, 30h
0x1800081a0  pop     r15
0x1800081a2  pop     r14
0x1800081a4  pop     rdi
0x1800081a5  retn
0x1800081a6  mov     ecx, 80004003h; int
0x1800081ab  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
