# CCscWmiRenameExMethod::_Execute(IWbemServices *,IWbemContext *,IWbemObjectSink *,long,IWbemClassObject *,IOfflineFilesCache *)

- ea: `0x18001a800`
- end: `0x18001aa2c`
- name: `?_Execute@CCscWmiRenameExMethod@@UEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@JPEAUIWbemClassObject@@PEAUIOfflineFilesCache@@@Z`
- size: `556`
- prototype: `__int64 __fastcall(CCscWmiRenameExMethod *__hidden this, struct IWbemServices *, struct IWbemContext *, struct IWbemObjectSink *, int, struct IWbemClassObject *, struct IOfflineFilesCache *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x18000f5a4`
- `0x18000f5cc`
- `0x180014068`
- `0x1800183b0`
- `0x1800183f0`
- `0x1800185b4`
- `0x180019708`
- `0x18001a800`
- `0x18002c010`

## string_xrefs

- `0x18001a873`: `ReplaceIfExists`
- `0x18001a860`: `NewPath`
- `0x18001a850`: `OriginalPath`

## pseudocode

```c
__int64 __fastcall CCscWmiRenameExMethod::_Execute(
        CCscWmiRenameExMethod *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IWbemObjectSink *a4,
        int a5,
        struct IWbemClassObject *a6,
        struct IOfflineFilesCache *a7)
{
  int v7; // ebx
  LONGLONG llVal; // rsi
  LONGLONG v9; // r14
  BOOL v10; // edi
  __int64 v11; // rcx
  unsigned int v12; // eax
  __int64 v14; // [rsp+30h] [rbp-D0h] BYREF
  struct tagVARIANT v15[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct tagVARIANT v16[2]; // [rsp+80h] [rbp-80h] BYREF
  struct tagVARIANT v17[5]; // [rsp+C0h] [rbp-40h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 84, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids);
  }
  CCscWmiMethodParam::CCscWmiMethodParam((CCscWmiMethodParam *)v17, L"OriginalPath");
  CCscWmiMethodParam::CCscWmiMethodParam((CCscWmiMethodParam *)v16, L"NewPath");
  CCscWmiMethodParam::CCscWmiMethodParam((CCscWmiMethodParam *)v15, L"ReplaceIfExists", 0);
  v7 = CCscWmiMethodParam::Query(v17, a6);
  if ( v7 >= 0 )
  {
    v7 = CCscWmiMethodParam::Query(v16, a6);
    if ( v7 >= 0 )
    {
      v7 = CCscWmiMethodParam::Query(v15, a6);
      if ( v7 >= 0 )
      {
        llVal = v17[0].llVal;
        v9 = v16[0].llVal;
        v10 = v15[0].iVal == 0xFFFF;
        v11 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
          {
            WPP_SF_S(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              85,
              WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
              v17[0].llVal);
            v11 = WPP_GLOBAL_Control;
          }
          if ( (_UNKNOWN *)v11 != &WPP_GLOBAL_Control )
          {
            if ( (*(_DWORD *)(v11 + 28) & 0x4000000) != 0 )
            {
              WPP_SF_S(*(_QWORD *)(v11 + 16), 86, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids, v9);
              v11 = WPP_GLOBAL_Control;
            }
            if ( (_UNKNOWN *)v11 != &WPP_GLOBAL_Control && (*(_DWORD *)(v11 + 28) & 0x4000000) != 0 )
              WPP_SF_d(*(_QWORD *)(v11 + 16), 87, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids, v10);
          }
        }
        v14 = 0;
        v7 = ((__int64 (__fastcall *)(struct IOfflineFilesCache *, GUID *, __int64 *))a7->lpVtbl->QueryInterface)(
               a7,
               &GUID_8c075039_1551_4ed9_8781_56705c04d3c0,
               &v14);
        if ( v7 >= 0 )
        {
          v12 = (*(__int64 (__fastcall **)(__int64, LONGLONG, LONGLONG, BOOL))(*(_QWORD *)v14 + 160LL))(
                  v14,
                  llVal,
                  v9,
                  v10);
          v7 = v12;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
          {
            WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 88, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids, v12);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
      }
    }
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      89,
      WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
      (unsigned int)v7);
  }
  CCscWmiMethodParam::~CCscWmiMethodParam((CCscWmiMethodParam *)v15);
  CCscWmiMethodParam::~CCscWmiMethodParam((CCscWmiMethodParam *)v16);
  CCscWmiMethodParam::~CCscWmiMethodParam((CCscWmiMethodParam *)v17);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001a800  push    rbp
0x18001a802  push    rbx
0x18001a803  push    rsi
0x18001a804  push    rdi
0x18001a805  push    r12
0x18001a807  push    r13
0x18001a809  push    r14
0x18001a80b  push    r15
0x18001a80d  lea     rbp, [rsp-8]
0x18001a812  sub     rsp, 108h
0x18001a819  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a820  lea     r13, WPP_GLOBAL_Control
0x18001a827  lea     r12, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001a82e  mov     r15d, 4000000h
0x18001a834  cmp     rcx, r13
0x18001a837  jz      short loc_18001A850
0x18001a839  test    [rcx+1Ch], r15d
0x18001a83d  jz      short loc_18001A850
0x18001a83f  mov     rcx, [rcx+10h]
0x18001a843  mov     edx, 54h ; 'T'
0x18001a848  mov     r8, r12
0x18001a84b  call    WPP_SF_
0x18001a850  lea     rdx, CSCWMI_STR_PARAM_ORIGINALPATH; "OriginalPath"
0x18001a857  lea     rcx, [rbp+40h+var_80]; this
0x18001a85b  call    ??0CCscWmiMethodParam@@QEAA@PEBG@Z; CCscWmiMethodParam::CCscWmiMethodParam(ushort const *)
0x18001a860  lea     rdx, CSCWMI_STR_PARAM_NEWPATH; "NewPath"
0x18001a867  lea     rcx, [rbp+40h+var_C0]; this
0x18001a86b  call    ??0CCscWmiMethodParam@@QEAA@PEBG@Z; CCscWmiMethodParam::CCscWmiMethodParam(ushort const *)
0x18001a870  xor     r8d, r8d; __int16
0x18001a873  lea     rdx, CSCWMI_STR_PARAM_REPLACEIFEXISTS; "ReplaceIfExists"
0x18001a87a  lea     rcx, [rsp+140h+var_100]; this
0x18001a87f  call    ??0CCscWmiMethodParam@@QEAA@PEBGF@Z; CCscWmiMethodParam::CCscWmiMethodParam(ushort const *,short)
0x18001a884  mov     rdi, [rbp+40h+arg_28]
0x18001a888  lea     rcx, [rbp+40h+var_80]; this
0x18001a88c  mov     rdx, rdi; struct IWbemClassObject *
0x18001a88f  call    ?Query@CCscWmiMethodParam@@QEAAJPEAUIWbemClassObject@@@Z; CCscWmiMethodParam::Query(IWbemClassObject *)
0x18001a894  mov     ebx, eax
0x18001a896  test    eax, eax
0x18001a898  js      loc_18001A9D4
0x18001a89e  mov     rdx, rdi; struct IWbemClassObject *
0x18001a8a1  lea     rcx, [rbp+40h+var_C0]; this
0x18001a8a5  call    ?Query@CCscWmiMethodParam@@QEAAJPEAUIWbemClassObject@@@Z; CCscWmiMethodParam::Query(IWbemClassObject *)
0x18001a8aa  mov     ebx, eax
0x18001a8ac  test    eax, eax
0x18001a8ae  js      loc_18001A9D4
0x18001a8b4  mov     rdx, rdi; struct IWbemClassObject *
0x18001a8b7  lea     rcx, [rsp+140h+var_100]; this
0x18001a8bc  call    ?Query@CCscWmiMethodParam@@QEAAJPEAUIWbemClassObject@@@Z; CCscWmiMethodParam::Query(IWbemClassObject *)
0x18001a8c1  mov     ebx, eax
0x18001a8c3  test    eax, eax
0x18001a8c5  js      loc_18001A9D4
0x18001a8cb  mov     rsi, [rbp+40h+var_78]
0x18001a8cf  xor     edi, edi
0x18001a8d1  mov     r14, [rbp+40h+var_B8]
0x18001a8d5  or      eax, 0FFFFFFFFh
0x18001a8d8  cmp     ax, [rsp+140h+var_F8]
0x18001a8dd  setz    dil
0x18001a8e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a8e8  cmp     rcx, r13
0x18001a8eb  jz      short loc_18001A951
0x18001a8ed  test    [rcx+1Ch], r15d
0x18001a8f1  jz      short loc_18001A90C
0x18001a8f3  mov     rcx, [rcx+10h]
0x18001a8f7  lea     edx, [rax+56h]
0x18001a8fa  mov     r9, rsi
0x18001a8fd  mov     r8, r12
0x18001a900  call    WPP_SF_S
0x18001a905  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a90c  cmp     rcx, r13
0x18001a90f  jz      short loc_18001A951
0x18001a911  test    [rcx+1Ch], r15d
0x18001a915  jz      short loc_18001A932
0x18001a917  mov     rcx, [rcx+10h]
0x18001a91b  mov     edx, 56h ; 'V'
0x18001a920  mov     r9, r14
0x18001a923  mov     r8, r12
0x18001a926  call    WPP_SF_S
0x18001a92b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a932  cmp     rcx, r13
0x18001a935  jz      short loc_18001A951
0x18001a937  test    [rcx+1Ch], r15d
0x18001a93b  jz      short loc_18001A951
0x18001a93d  mov     rcx, [rcx+10h]
0x18001a941  mov     edx, 57h ; 'W'
0x18001a946  mov     r9d, edi
0x18001a949  mov     r8, r12
0x18001a94c  call    WPP_SF_d
0x18001a951  mov     rcx, [rbp+40h+arg_30]
0x18001a958  lea     r8, [rsp+140h+var_110]
0x18001a95d  lea     rdx, _GUID_8c075039_1551_4ed9_8781_56705c04d3c0
0x18001a964  mov     [rsp+140h+var_110], 0
0x18001a96d  mov     rax, [rcx]
0x18001a970  mov     rax, [rax]
0x18001a973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a978  mov     ebx, eax
0x18001a97a  test    eax, eax
0x18001a97c  js      short loc_18001A9D4
0x18001a97e  mov     rcx, [rsp+140h+var_110]
0x18001a983  mov     r9d, edi
0x18001a986  mov     r8, r14
0x18001a989  mov     rdx, rsi
0x18001a98c  mov     rax, [rcx]
0x18001a98f  mov     rax, [rax+0A0h]
0x18001a996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a99b  mov     ebx, eax
0x18001a99d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9a4  cmp     rcx, r13
0x18001a9a7  jz      short loc_18001A9C3
0x18001a9a9  test    [rcx+1Ch], r15d
0x18001a9ad  jz      short loc_18001A9C3
0x18001a9af  mov     rcx, [rcx+10h]
0x18001a9b3  mov     edx, 58h ; 'X'
0x18001a9b8  mov     r9d, eax
0x18001a9bb  mov     r8, r12
0x18001a9be  call    WPP_SF_d
0x18001a9c3  mov     rcx, [rsp+140h+var_110]
0x18001a9c8  mov     rax, [rcx]
0x18001a9cb  mov     rax, [rax+10h]
0x18001a9cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9db  cmp     rcx, r13
0x18001a9de  jz      short loc_18001A9FA
0x18001a9e0  test    [rcx+1Ch], r15d
0x18001a9e4  jz      short loc_18001A9FA
0x18001a9e6  mov     rcx, [rcx+10h]
0x18001a9ea  mov     edx, 59h ; 'Y'
0x18001a9ef  mov     r9d, ebx
0x18001a9f2  mov     r8, r12
0x18001a9f5  call    WPP_SF_d
0x18001a9fa  lea     rcx, [rsp+140h+var_100]; this
0x18001a9ff  call    ??1CCscWmiMethodParam@@QEAA@XZ; CCscWmiMethodParam::~CCscWmiMethodParam(void)
0x18001aa04  lea     rcx, [rbp+40h+var_C0]; this
0x18001aa08  call    ??1CCscWmiMethodParam@@QEAA@XZ; CCscWmiMethodParam::~CCscWmiMethodParam(void)
0x18001aa0d  lea     rcx, [rbp+40h+var_80]; this
0x18001aa11  call    ??1CCscWmiMethodParam@@QEAA@XZ; CCscWmiMethodParam::~CCscWmiMethodParam(void)
0x18001aa16  mov     eax, ebx
0x18001aa18  add     rsp, 108h
0x18001aa1f  pop     r15
0x18001aa21  pop     r14
0x18001aa23  pop     r13
0x18001aa25  pop     r12
0x18001aa27  pop     rdi
0x18001aa28  pop     rsi
0x18001aa29  pop     rbx
0x18001aa2a  pop     rbp
0x18001aa2b  retn
```
