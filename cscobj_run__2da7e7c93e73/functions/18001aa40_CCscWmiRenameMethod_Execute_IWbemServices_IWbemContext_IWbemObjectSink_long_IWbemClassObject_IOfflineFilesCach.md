# CCscWmiRenameMethod::_Execute(IWbemServices *,IWbemContext *,IWbemObjectSink *,long,IWbemClassObject *,IOfflineFilesCache *)

- ea: `0x18001aa40`
- end: `0x18001ac25`
- name: `?_Execute@CCscWmiRenameMethod@@UEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@JPEAUIWbemClassObject@@PEAUIOfflineFilesCache@@@Z`
- size: `485`
- prototype: `__int64 __fastcall(CCscWmiRenameMethod *__hidden this, struct IWbemServices *, struct IWbemContext *, struct IWbemObjectSink *, int, struct IWbemClassObject *, struct IOfflineFilesCache *)`
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
- `0x18001aa40`
- `0x18002c010`

## string_xrefs

- `0x18001aab1`: `ReplaceIfExists`
- `0x18001aa9e`: `NewPath`
- `0x18001aa8e`: `OriginalPath`

## pseudocode

```c
__int64 __fastcall CCscWmiRenameMethod::_Execute(
        CCscWmiRenameMethod *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IWbemObjectSink *a4,
        int a5,
        struct IWbemClassObject *a6,
        struct IOfflineFilesCache *a7)
{
  int v7; // ebx
  LONGLONG llVal; // rdi
  LONGLONG v9; // rsi
  BOOL v10; // ebx
  __int64 v11; // rcx
  unsigned int v12; // eax
  __int64 v13; // rcx
  struct tagVARIANT v15[2]; // [rsp+30h] [rbp-B1h] BYREF
  struct tagVARIANT v16[2]; // [rsp+70h] [rbp-71h] BYREF
  struct tagVARIANT v17[4]; // [rsp+B0h] [rbp-31h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 90, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids);
  }
  CCscWmiMethodParam::CCscWmiMethodParam((CCscWmiMethodParam *)v17, L"OriginalPath");
  CCscWmiMethodParam::CCscWmiMethodParam((CCscWmiMethodParam *)v16, L"NewPath");
  CCscWmiMethodParam::CCscWmiMethodParam((CCscWmiMethodParam *)v15, L"ReplaceIfExists", 0);
  v7 = CCscWmiMethodParam::Query(v17, a6);
  if ( v7 < 0 )
    goto LABEL_19;
  v7 = CCscWmiMethodParam::Query(v16, a6);
  if ( v7 < 0 )
    goto LABEL_19;
  v7 = CCscWmiMethodParam::Query(v15, a6);
  if ( v7 < 0 )
    goto LABEL_19;
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
        91,
        WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
        v17[0].llVal);
      v11 = WPP_GLOBAL_Control;
    }
    if ( (_UNKNOWN *)v11 != &WPP_GLOBAL_Control )
    {
      if ( (*(_DWORD *)(v11 + 28) & 0x4000000) != 0 )
      {
        WPP_SF_S(*(_QWORD *)(v11 + 16), 92, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids, v9);
        v11 = WPP_GLOBAL_Control;
      }
      if ( (_UNKNOWN *)v11 != &WPP_GLOBAL_Control && (*(_DWORD *)(v11 + 28) & 0x4000000) != 0 )
        WPP_SF_d(*(_QWORD *)(v11 + 16), 93, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids, v10);
    }
  }
  v12 = ((__int64 (__fastcall *)(struct IOfflineFilesCache *, LONGLONG, LONGLONG, BOOL))a7->lpVtbl->RenameItem)(
          a7,
          llVal,
          v9,
          v10);
  v7 = v12;
  v13 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) == 0 )
    {
LABEL_20:
      if ( (_UNKNOWN *)v13 != &WPP_GLOBAL_Control && (*(_DWORD *)(v13 + 28) & 0x4000000) != 0 )
        WPP_SF_d(*(_QWORD *)(v13 + 16), 95, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids, (unsigned int)v7);
      goto LABEL_23;
    }
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 94, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids, v12);
LABEL_19:
    v13 = WPP_GLOBAL_Control;
    goto LABEL_20;
  }
LABEL_23:
  CCscWmiMethodParam::~CCscWmiMethodParam((CCscWmiMethodParam *)v15);
  CCscWmiMethodParam::~CCscWmiMethodParam((CCscWmiMethodParam *)v16);
  CCscWmiMethodParam::~CCscWmiMethodParam((CCscWmiMethodParam *)v17);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001aa40  push    rbp
0x18001aa42  push    rbx
0x18001aa43  push    rsi
0x18001aa44  push    rdi
0x18001aa45  push    r12
0x18001aa47  push    r14
0x18001aa49  push    r15
0x18001aa4b  lea     rbp, [rsp-0Fh]
0x18001aa50  sub     rsp, 0F0h
0x18001aa57  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa5e  lea     r12, WPP_GLOBAL_Control
0x18001aa65  lea     r15, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001aa6c  mov     r14d, 4000000h
0x18001aa72  cmp     rcx, r12
0x18001aa75  jz      short loc_18001AA8E
0x18001aa77  test    [rcx+1Ch], r14d
0x18001aa7b  jz      short loc_18001AA8E
0x18001aa7d  mov     rcx, [rcx+10h]
0x18001aa81  mov     edx, 5Ah ; 'Z'
0x18001aa86  mov     r8, r15
0x18001aa89  call    WPP_SF_
0x18001aa8e  lea     rdx, CSCWMI_STR_PARAM_ORIGINALPATH; "OriginalPath"
0x18001aa95  lea     rcx, [rbp+3Fh+var_70]; this
0x18001aa99  call    ??0CCscWmiMethodParam@@QEAA@PEBG@Z; CCscWmiMethodParam::CCscWmiMethodParam(ushort const *)
0x18001aa9e  lea     rdx, CSCWMI_STR_PARAM_NEWPATH; "NewPath"
0x18001aaa5  lea     rcx, [rbp+3Fh+var_B0]; this
0x18001aaa9  call    ??0CCscWmiMethodParam@@QEAA@PEBG@Z; CCscWmiMethodParam::CCscWmiMethodParam(ushort const *)
0x18001aaae  xor     r8d, r8d; __int16
0x18001aab1  lea     rdx, CSCWMI_STR_PARAM_REPLACEIFEXISTS; "ReplaceIfExists"
0x18001aab8  lea     rcx, [rsp+120h+var_F0]; this
0x18001aabd  call    ??0CCscWmiMethodParam@@QEAA@PEBGF@Z; CCscWmiMethodParam::CCscWmiMethodParam(ushort const *,short)
0x18001aac2  mov     rdi, [rbp+3Fh+arg_28]
0x18001aac6  lea     rcx, [rbp+3Fh+var_70]; this
0x18001aaca  mov     rdx, rdi; struct IWbemClassObject *
0x18001aacd  call    ?Query@CCscWmiMethodParam@@QEAAJPEAUIWbemClassObject@@@Z; CCscWmiMethodParam::Query(IWbemClassObject *)
0x18001aad2  mov     ebx, eax
0x18001aad4  test    eax, eax
0x18001aad6  js      loc_18001ABCF
0x18001aadc  mov     rdx, rdi; struct IWbemClassObject *
0x18001aadf  lea     rcx, [rbp+3Fh+var_B0]; this
0x18001aae3  call    ?Query@CCscWmiMethodParam@@QEAAJPEAUIWbemClassObject@@@Z; CCscWmiMethodParam::Query(IWbemClassObject *)
0x18001aae8  mov     ebx, eax
0x18001aaea  test    eax, eax
0x18001aaec  js      loc_18001ABCF
0x18001aaf2  mov     rdx, rdi; struct IWbemClassObject *
0x18001aaf5  lea     rcx, [rsp+120h+var_F0]; this
0x18001aafa  call    ?Query@CCscWmiMethodParam@@QEAAJPEAUIWbemClassObject@@@Z; CCscWmiMethodParam::Query(IWbemClassObject *)
0x18001aaff  mov     ebx, eax
0x18001ab01  test    eax, eax
0x18001ab03  js      loc_18001ABCF
0x18001ab09  mov     rdi, [rbp+3Fh+var_68]
0x18001ab0d  xor     ebx, ebx
0x18001ab0f  mov     rsi, [rbp+3Fh+var_A8]
0x18001ab13  or      eax, 0FFFFFFFFh
0x18001ab16  cmp     ax, [rsp+120h+var_E8]
0x18001ab1b  setz    bl
0x18001ab1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab25  cmp     rcx, r12
0x18001ab28  jz      short loc_18001AB8E
0x18001ab2a  test    [rcx+1Ch], r14d
0x18001ab2e  jz      short loc_18001AB49
0x18001ab30  mov     rcx, [rcx+10h]
0x18001ab34  lea     edx, [rax+5Ch]
0x18001ab37  mov     r9, rdi
0x18001ab3a  mov     r8, r15
0x18001ab3d  call    WPP_SF_S
0x18001ab42  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab49  cmp     rcx, r12
0x18001ab4c  jz      short loc_18001AB8E
0x18001ab4e  test    [rcx+1Ch], r14d
0x18001ab52  jz      short loc_18001AB6F
0x18001ab54  mov     rcx, [rcx+10h]
0x18001ab58  mov     edx, 5Ch ; '\'
0x18001ab5d  mov     r9, rsi
0x18001ab60  mov     r8, r15
0x18001ab63  call    WPP_SF_S
0x18001ab68  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab6f  cmp     rcx, r12
0x18001ab72  jz      short loc_18001AB8E
0x18001ab74  test    [rcx+1Ch], r14d
0x18001ab78  jz      short loc_18001AB8E
0x18001ab7a  mov     rcx, [rcx+10h]
0x18001ab7e  mov     edx, 5Dh ; ']'
0x18001ab83  mov     r9d, ebx
0x18001ab86  mov     r8, r15
0x18001ab89  call    WPP_SF_d
0x18001ab8e  mov     rcx, [rbp+3Fh+arg_30]
0x18001ab92  mov     r9d, ebx
0x18001ab95  mov     r8, rsi
0x18001ab98  mov     rdx, rdi
0x18001ab9b  mov     rax, [rcx]
0x18001ab9e  mov     rax, [rax+60h]
0x18001aba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aba7  mov     ebx, eax
0x18001aba9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001abb0  cmp     rcx, r12
0x18001abb3  jz      short loc_18001ABF5
0x18001abb5  test    [rcx+1Ch], r14d
0x18001abb9  jz      short loc_18001ABD6
0x18001abbb  mov     rcx, [rcx+10h]
0x18001abbf  mov     edx, 5Eh ; '^'
0x18001abc4  mov     r9d, eax
0x18001abc7  mov     r8, r15
0x18001abca  call    WPP_SF_d
0x18001abcf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001abd6  cmp     rcx, r12
0x18001abd9  jz      short loc_18001ABF5
0x18001abdb  test    [rcx+1Ch], r14d
0x18001abdf  jz      short loc_18001ABF5
0x18001abe1  mov     rcx, [rcx+10h]
0x18001abe5  mov     edx, 5Fh ; '_'
0x18001abea  mov     r9d, ebx
0x18001abed  mov     r8, r15
0x18001abf0  call    WPP_SF_d
0x18001abf5  lea     rcx, [rsp+120h+var_F0]; this
0x18001abfa  call    ??1CCscWmiMethodParam@@QEAA@XZ; CCscWmiMethodParam::~CCscWmiMethodParam(void)
0x18001abff  lea     rcx, [rbp+3Fh+var_B0]; this
0x18001ac03  call    ??1CCscWmiMethodParam@@QEAA@XZ; CCscWmiMethodParam::~CCscWmiMethodParam(void)
0x18001ac08  lea     rcx, [rbp+3Fh+var_70]; this
0x18001ac0c  call    ??1CCscWmiMethodParam@@QEAA@XZ; CCscWmiMethodParam::~CCscWmiMethodParam(void)
0x18001ac11  mov     eax, ebx
0x18001ac13  add     rsp, 0F0h
0x18001ac1a  pop     r15
0x18001ac1c  pop     r14
0x18001ac1e  pop     r12
0x18001ac20  pop     rdi
0x18001ac21  pop     rsi
0x18001ac22  pop     rbx
0x18001ac23  pop     rbp
0x18001ac24  retn
```
