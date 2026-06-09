# CCscWmiEnableMethod::_Execute(IWbemServices *,IWbemContext *,IWbemObjectSink *,long,IWbemClassObject *)

- ea: `0x18001a0a0`
- end: `0x18001a298`
- name: `?_Execute@CCscWmiEnableMethod@@UEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@JPEAUIWbemClassObject@@@Z`
- size: `504`
- prototype: `__int64 __usercall@<rax>(CCscWmiEnableMethod *__hidden this@<rcx>, struct IWbemServices *@<rdx>, struct IWbemContext *@<r8>, struct IWbemObjectSink *@<r9>, int, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x18000f5a4`
- `0x18000f5cc`
- `0x180011998`
- `0x1800183b0`
- `0x1800185b4`
- `0x180019708`
- `0x180019adc`
- `0x18001a0a0`
- `0x18002c010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18001a23f`
- `OLEAUT32!__imp_VariantClear` at `0x18001a23f`

## pseudocode

```c
__int64 __fastcall CCscWmiEnableMethod::_Execute(
        CCscWmiEnableMethod *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IWbemObjectSink *a4,
        int a5,
        struct IWbemClassObject *a6)
{
  __int64 v10; // rcx
  int v11; // ebx
  SHORT v12; // di
  int v13; // eax
  int v15; // [rsp+30h] [rbp-59h] BYREF
  struct IWbemClassObject *v16; // [rsp+38h] [rbp-51h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-49h] BYREF
  struct tagVARIANT v18[4]; // [rsp+60h] [rbp-29h] BYREF

  v10 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 62, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids);
      v10 = WPP_GLOBAL_Control;
    }
    if ( (_UNKNOWN *)v10 != &WPP_GLOBAL_Control && (*(_DWORD *)(v10 + 28) & 0x4000000) != 0 )
      WPP_SF_(*(_QWORD *)(v10 + 16), 63, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids);
  }
  CCscWmiMethodParam::CCscWmiMethodParam((CCscWmiMethodParam *)v18, L"Enable");
  v11 = CCscWmiMethodParam::Query(v18, a6);
  if ( v11 >= 0 )
  {
    v15 = 0;
    v12 = -1;
    v11 = CscApi_OfflineFilesEnable(v18[0].iVal == 0xFFFF, &v15);
    if ( v11 >= 0 )
    {
      v16 = 0;
      v11 = CCscWmiMethod::_CreateParamsObject(this, a2, a3, &v16);
      if ( v11 >= 0 )
      {
        if ( !v15 )
          v12 = 0;
        pvarg.iVal = v12;
        pvarg.vt = 2;
        v11 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))v16->lpVtbl->Put)(
                v16,
                L"RebootRequired",
                0,
                &pvarg,
                0);
        if ( v11 >= 0 )
        {
          v13 = ((__int64 (__fastcall *)(struct IWbemObjectSink *, __int64, struct IWbemClassObject **))a4->lpVtbl->Indicate)(
                  a4,
                  1,
                  &v16);
          v11 = v13;
          if ( v13 < 0
            && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          {
            WPP_SF_d(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              64,
              WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
              (unsigned int)v13);
          }
        }
        ((void (__fastcall *)(struct IWbemClassObject *))v16->lpVtbl->Release)(v16);
        VariantClear(&pvarg);
      }
    }
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      65,
      WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
      (unsigned int)v11);
  }
  CCscWmiMethodParam::~CCscWmiMethodParam((CCscWmiMethodParam *)v18);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001a0a0  push    rbp
0x18001a0a2  push    rbx
0x18001a0a3  push    rsi
0x18001a0a4  push    rdi
0x18001a0a5  push    r12
0x18001a0a7  push    r14
0x18001a0a9  push    r15
0x18001a0ab  lea     rbp, [rsp-17h]
0x18001a0b0  sub     rsp, 0A0h
0x18001a0b7  mov     rsi, r9
0x18001a0ba  mov     r14, r8
0x18001a0bd  mov     r15, rdx
0x18001a0c0  mov     r12, rcx
0x18001a0c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a0ca  lea     rbx, WPP_GLOBAL_Control
0x18001a0d1  cmp     rcx, rbx
0x18001a0d4  jz      short loc_18001A11E
0x18001a0d6  test    dword ptr [rcx+1Ch], 4000000h
0x18001a0dd  jz      short loc_18001A0FB
0x18001a0df  mov     rcx, [rcx+10h]
0x18001a0e3  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001a0ea  mov     edx, 3Eh ; '>'
0x18001a0ef  call    WPP_SF_
0x18001a0f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a0fb  cmp     rcx, rbx
0x18001a0fe  jz      short loc_18001A11E
0x18001a100  test    dword ptr [rcx+1Ch], 4000000h
0x18001a107  jz      short loc_18001A11E
0x18001a109  mov     rcx, [rcx+10h]
0x18001a10d  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001a114  mov     edx, 3Fh ; '?'
0x18001a119  call    WPP_SF_
0x18001a11e  lea     rdx, CSCWMI_STR_PARAM_ENABLE; "Enable"
0x18001a125  lea     rcx, [rbp+47h+var_70]; this
0x18001a129  call    ??0CCscWmiMethodParam@@QEAA@PEBG@Z; CCscWmiMethodParam::CCscWmiMethodParam(ushort const *)
0x18001a12e  mov     rdx, [rbp+47h+arg_28]; struct IWbemClassObject *
0x18001a132  lea     rcx, [rbp+47h+var_70]; this
0x18001a136  call    ?Query@CCscWmiMethodParam@@QEAAJPEAUIWbemClassObject@@@Z; CCscWmiMethodParam::Query(IWbemClassObject *)
0x18001a13b  mov     ebx, eax
0x18001a13d  test    eax, eax
0x18001a13f  js      loc_18001A247
0x18001a145  xor     ecx, ecx
0x18001a147  mov     [rbp+47h+var_A0], 0
0x18001a14e  or      edi, 0FFFFFFFFh
0x18001a151  lea     rdx, [rbp+47h+var_A0]; int *
0x18001a155  cmp     di, [rbp+47h+var_68]
0x18001a159  setz    cl; int
0x18001a15c  call    ?CscApi_OfflineFilesEnable@@YAJHPEAH@Z; CscApi_OfflineFilesEnable(int,int *)
0x18001a161  mov     ebx, eax
0x18001a163  test    eax, eax
0x18001a165  js      loc_18001A247
0x18001a16b  lea     r9, [rbp+47h+var_98]; struct IWbemClassObject **
0x18001a16f  mov     [rbp+47h+var_98], 0
0x18001a177  mov     r8, r14; struct IWbemContext *
0x18001a17a  mov     rdx, r15; struct IWbemServices *
0x18001a17d  mov     rcx, r12; this
0x18001a180  call    ?_CreateParamsObject@CCscWmiMethod@@IEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAPEAUIWbemClassObject@@@Z; CCscWmiMethod::_CreateParamsObject(IWbemServices *,IWbemContext *,IWbemClassObject * *)
0x18001a185  mov     ebx, eax
0x18001a187  test    eax, eax
0x18001a189  js      loc_18001A247
0x18001a18f  cmp     [rbp+47h+var_A0], 0
0x18001a193  jnz     short loc_18001A19A
0x18001a195  xor     eax, eax
0x18001a197  movzx   edi, ax
0x18001a19a  mov     rcx, [rbp+47h+var_98]
0x18001a19e  lea     r9, [rbp+47h+pvarg]
0x18001a1a2  mov     word ptr [rbp+47h+pvarg+8], di
0x18001a1a6  lea     rdx, CSCWMI_STR_PARAM_REBOOTREQUIRED; "RebootRequired"
0x18001a1ad  mov     r14d, 2
0x18001a1b3  mov     [rsp+0D0h+var_B0], 0
0x18001a1bb  mov     word ptr [rbp+47h+pvarg], r14w
0x18001a1c0  xor     r8d, r8d
0x18001a1c3  mov     rax, [rcx]
0x18001a1c6  mov     rax, [rax+28h]
0x18001a1ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1cf  mov     ebx, eax
0x18001a1d1  test    eax, eax
0x18001a1d3  js      short loc_18001A224
0x18001a1d5  mov     rax, [rsi]
0x18001a1d8  lea     r8, [rbp+47h+var_98]
0x18001a1dc  lea     edx, [r14-1]
0x18001a1e0  mov     rcx, rsi
0x18001a1e3  mov     rax, [rax+18h]
0x18001a1e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1ec  mov     ebx, eax
0x18001a1ee  test    eax, eax
0x18001a1f0  jns     short loc_18001A224
0x18001a1f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a1f9  lea     rdi, WPP_GLOBAL_Control
0x18001a200  cmp     rcx, rdi
0x18001a203  jz      short loc_18001A22B
0x18001a205  test    [rcx+1Ch], r14b
0x18001a209  jz      short loc_18001A22B
0x18001a20b  mov     rcx, [rcx+10h]
0x18001a20f  lea     edx, [r14+3Eh]
0x18001a213  mov     r9d, eax
0x18001a216  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001a21d  call    WPP_SF_d
0x18001a222  jmp     short loc_18001A22B
0x18001a224  lea     rdi, WPP_GLOBAL_Control
0x18001a22b  mov     rcx, [rbp+47h+var_98]
0x18001a22f  mov     rax, [rcx]
0x18001a232  mov     rax, [rax+10h]
0x18001a236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a23b  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18001a23f  call    cs:__imp_VariantClear
0x18001a245  jmp     short loc_18001A24E
0x18001a247  lea     rdi, WPP_GLOBAL_Control
0x18001a24e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a255  cmp     rcx, rdi
0x18001a258  jz      short loc_18001A27B
0x18001a25a  test    dword ptr [rcx+1Ch], 4000000h
0x18001a261  jz      short loc_18001A27B
0x18001a263  mov     rcx, [rcx+10h]
0x18001a267  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001a26e  mov     edx, 41h ; 'A'
0x18001a273  mov     r9d, ebx
0x18001a276  call    WPP_SF_d
0x18001a27b  lea     rcx, [rbp+47h+var_70]; this
0x18001a27f  call    ??1CCscWmiMethodParam@@QEAA@XZ; CCscWmiMethodParam::~CCscWmiMethodParam(void)
0x18001a284  mov     eax, ebx
0x18001a286  add     rsp, 0A0h
0x18001a28d  pop     r15
0x18001a28f  pop     r14
0x18001a291  pop     r12
0x18001a293  pop     rdi
0x18001a294  pop     rsi
0x18001a295  pop     rbx
0x18001a296  pop     rbp
0x18001a297  retn
```
