# CCscWmiTransitionOfflineMethod::_Execute(IWbemServices *,IWbemContext *,IWbemObjectSink *,long,IWbemClassObject *,IOfflineFilesCache *)

- ea: `0x18001b0a0`
- end: `0x18001b44f`
- name: `?_Execute@CCscWmiTransitionOfflineMethod@@UEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@JPEAUIWbemClassObject@@PEAUIOfflineFilesCache@@@Z`
- size: `943`
- prototype: `int(CCscWmiTransitionOfflineMethod *__hidden this, struct IWbemServices *, struct IWbemContext *, struct IWbemObjectSink *, int, struct IWbemClassObject *, struct IOfflineFilesCache *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x18000f5a4`
- `0x18000f5cc`
- `0x180014068`
- `0x1800183b0`
- `0x1800183f0`
- `0x1800185b4`
- `0x180019708`
- `0x180019adc`
- `0x18001b0a0`
- `0x18002c010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18001b38d`
- `OLEAUT32!__imp_VariantClear` at `0x18001b38d`

## string_xrefs

- `0x18001b2fd`: `OpenFiles`

## pseudocode

```c
__int64 __fastcall CCscWmiTransitionOfflineMethod::_Execute(
        CCscWmiTransitionOfflineMethod *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IWbemObjectSink *a4,
        int a5,
        struct IWbemClassObject *a6,
        struct IOfflineFilesCache *a7)
{
  int v10; // ebx
  LONGLONG llVal; // rbx
  unsigned int Lo; // r14d
  SHORT v13; // di
  BOOL v14; // esi
  __int64 v15; // rcx
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  struct IWbemClassObject *v18; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-B0h] BYREF
  struct tagVARIANT v22[2]; // [rsp+70h] [rbp-90h] BYREF
  struct tagVARIANT v23[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct tagVARIANT v24[5]; // [rsp+F0h] [rbp-10h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 100, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids);
  }
  CCscWmiMethodParam::CCscWmiMethodParam((CCscWmiMethodParam *)v24, L"Path");
  CCscWmiMethodParam::CCscWmiMethodParam((CCscWmiMethodParam *)v23, L"Flags");
  CCscWmiMethodParam::CCscWmiMethodParam((CCscWmiMethodParam *)v22, L"Force", 0);
  v10 = CCscWmiMethodParam::Query(v24, a6);
  if ( v10 >= 0 )
  {
    v10 = CCscWmiMethodParam::Query(v23, a6);
    if ( v10 >= 0 )
    {
      v10 = CCscWmiMethodParam::Query(v22, a6);
      if ( v10 >= 0 )
      {
        llVal = v24[0].llVal;
        Lo = v23[0].cyVal.Lo;
        v13 = -1;
        v14 = v22[0].iVal == 0xFFFF;
        v15 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
          {
            WPP_SF_S(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              101,
              WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
              v24[0].llVal);
            v15 = WPP_GLOBAL_Control;
          }
          if ( (_UNKNOWN *)v15 != &WPP_GLOBAL_Control )
          {
            if ( (*(_DWORD *)(v15 + 28) & 0x4000000) != 0 )
            {
              WPP_SF_d(*(_QWORD *)(v15 + 16), 102, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids, Lo);
              v15 = WPP_GLOBAL_Control;
            }
            if ( (_UNKNOWN *)v15 != &WPP_GLOBAL_Control && (*(_DWORD *)(v15 + 28) & 0x4000000) != 0 )
              WPP_SF_d(*(_QWORD *)(v15 + 16), 103, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids, v14);
          }
        }
        v20 = 0;
        v10 = ((__int64 (__fastcall *)(struct IOfflineFilesCache *, LONGLONG, _QWORD, __int64 *))a7->lpVtbl->FindItem)(
                a7,
                llVal,
                0,
                &v20);
        if ( v10 >= 0 )
        {
          v19 = 0;
          v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v20)(
                  v20,
                  &GUID_efb23a09_a867_4be8_83a6_86969a7d0856,
                  &v19);
          if ( v10 >= 0 )
          {
            v17 = 0;
            v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, BOOL, int *))(*(_QWORD *)v19 + 48LL))(
                    v19,
                    0,
                    Lo,
                    v14,
                    &v17);
            if ( v10 >= 0 )
            {
              v18 = 0;
              v10 = CCscWmiMethod::_CreateParamsObject(this, a2, a3, &v18);
              if ( v10 >= 0 )
              {
                if ( !v17 )
                  v13 = 0;
                pvarg.iVal = v13;
                pvarg.vt = 2;
                v10 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))v18->lpVtbl->Put)(
                        v18,
                        L"OpenFiles",
                        0,
                        &pvarg,
                        0);
                if ( v10 >= 0 )
                {
                  v10 = ((__int64 (__fastcall *)(struct IWbemObjectSink *, __int64, struct IWbemClassObject **))a4->lpVtbl->Indicate)(
                          a4,
                          1,
                          &v18);
                  if ( v10 < 0
                    && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
                  {
                    WPP_SF_d(
                      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                      104,
                      WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
                      (unsigned int)v10);
                  }
                }
                ((void (__fastcall *)(struct IWbemClassObject *))v18->lpVtbl->Release)(v18);
                VariantClear(&pvarg);
              }
            }
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                105,
                WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
                (unsigned int)v10);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
      }
    }
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      106,
      WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
      (unsigned int)v10);
  }
  CCscWmiMethodParam::~CCscWmiMethodParam((CCscWmiMethodParam *)v22);
  CCscWmiMethodParam::~CCscWmiMethodParam((CCscWmiMethodParam *)v23);
  CCscWmiMethodParam::~CCscWmiMethodParam((CCscWmiMethodParam *)v24);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001b0a0  mov     [rsp-8+arg_0], rcx
0x18001b0a5  push    rbp
0x18001b0a6  push    rbx
0x18001b0a7  push    rsi
0x18001b0a8  push    rdi
0x18001b0a9  push    r12
0x18001b0ab  push    r13
0x18001b0ad  push    r14
0x18001b0af  push    r15
0x18001b0b1  lea     rbp, [rsp-38h]
0x18001b0b6  sub     rsp, 138h
0x18001b0bd  mov     r15, r9
0x18001b0c0  mov     r12, r8
0x18001b0c3  mov     r13, rdx
0x18001b0c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b0cd  lea     rax, WPP_GLOBAL_Control
0x18001b0d4  cmp     rcx, rax
0x18001b0d7  jz      short loc_18001B0F7
0x18001b0d9  test    dword ptr [rcx+1Ch], 4000000h
0x18001b0e0  jz      short loc_18001B0F7
0x18001b0e2  mov     rcx, [rcx+10h]
0x18001b0e6  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001b0ed  mov     edx, 64h ; 'd'
0x18001b0f2  call    WPP_SF_
0x18001b0f7  lea     rdx, CSCWMI_STR_PARAM_PATH; "Path"
0x18001b0fe  lea     rcx, [rbp+70h+var_80]; this
0x18001b102  call    ??0CCscWmiMethodParam@@QEAA@PEBG@Z; CCscWmiMethodParam::CCscWmiMethodParam(ushort const *)
0x18001b107  lea     rdx, CSCWMI_STR_PARAM_FLAGS; "Flags"
0x18001b10e  lea     rcx, [rbp+70h+var_C0]; this
0x18001b112  call    ??0CCscWmiMethodParam@@QEAA@PEBG@Z; CCscWmiMethodParam::CCscWmiMethodParam(ushort const *)
0x18001b117  xor     r8d, r8d; __int16
0x18001b11a  lea     rdx, CSCWMI_STR_PARAM_FORCE; "Force"
0x18001b121  lea     rcx, [rsp+170h+var_100]; this
0x18001b126  call    ??0CCscWmiMethodParam@@QEAA@PEBGF@Z; CCscWmiMethodParam::CCscWmiMethodParam(ushort const *,short)
0x18001b12b  mov     rdi, [rbp+70h+arg_28]
0x18001b132  lea     rcx, [rbp+70h+var_80]; this
0x18001b136  mov     rdx, rdi; struct IWbemClassObject *
0x18001b139  call    ?Query@CCscWmiMethodParam@@QEAAJPEAUIWbemClassObject@@@Z; CCscWmiMethodParam::Query(IWbemClassObject *)
0x18001b13e  mov     ebx, eax
0x18001b140  test    eax, eax
0x18001b142  js      loc_18001B3E9
0x18001b148  mov     rdx, rdi; struct IWbemClassObject *
0x18001b14b  lea     rcx, [rbp+70h+var_C0]; this
0x18001b14f  call    ?Query@CCscWmiMethodParam@@QEAAJPEAUIWbemClassObject@@@Z; CCscWmiMethodParam::Query(IWbemClassObject *)
0x18001b154  mov     ebx, eax
0x18001b156  test    eax, eax
0x18001b158  js      loc_18001B3E9
0x18001b15e  mov     rdx, rdi; struct IWbemClassObject *
0x18001b161  lea     rcx, [rsp+170h+var_100]; this
0x18001b166  call    ?Query@CCscWmiMethodParam@@QEAAJPEAUIWbemClassObject@@@Z; CCscWmiMethodParam::Query(IWbemClassObject *)
0x18001b16b  mov     ebx, eax
0x18001b16d  test    eax, eax
0x18001b16f  js      loc_18001B3E9
0x18001b175  mov     rbx, [rbp+70h+var_78]
0x18001b179  xor     esi, esi
0x18001b17b  mov     r14d, [rbp+70h+var_B8]
0x18001b17f  or      edi, 0FFFFFFFFh
0x18001b182  cmp     di, [rsp+170h+var_F8]
0x18001b187  setz    sil
0x18001b18b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b192  lea     rax, WPP_GLOBAL_Control
0x18001b199  cmp     rcx, rax
0x18001b19c  jz      loc_18001B229
0x18001b1a2  test    dword ptr [rcx+1Ch], 4000000h
0x18001b1a9  jz      short loc_18001B1CF
0x18001b1ab  mov     rcx, [rcx+10h]
0x18001b1af  lea     edx, [rdi+66h]
0x18001b1b2  mov     r9, rbx
0x18001b1b5  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001b1bc  call    WPP_SF_S
0x18001b1c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b1c8  lea     rax, WPP_GLOBAL_Control
0x18001b1cf  cmp     rcx, rax
0x18001b1d2  jz      short loc_18001B229
0x18001b1d4  test    dword ptr [rcx+1Ch], 4000000h
0x18001b1db  jz      short loc_18001B203
0x18001b1dd  mov     rcx, [rcx+10h]
0x18001b1e1  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001b1e8  mov     edx, 66h ; 'f'
0x18001b1ed  mov     r9d, r14d
0x18001b1f0  call    WPP_SF_d
0x18001b1f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b1fc  lea     rax, WPP_GLOBAL_Control
0x18001b203  cmp     rcx, rax
0x18001b206  jz      short loc_18001B229
0x18001b208  test    dword ptr [rcx+1Ch], 4000000h
0x18001b20f  jz      short loc_18001B229
0x18001b211  mov     rcx, [rcx+10h]
0x18001b215  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001b21c  mov     edx, 67h ; 'g'
0x18001b221  mov     r9d, esi
0x18001b224  call    WPP_SF_d
0x18001b229  mov     rcx, [rbp+70h+arg_30]
0x18001b230  lea     r9, [rsp+170h+var_128]
0x18001b235  xor     r8d, r8d
0x18001b238  mov     [rsp+170h+var_128], 0
0x18001b241  mov     rdx, rbx
0x18001b244  mov     rax, [rcx]
0x18001b247  mov     rax, [rax+50h]
0x18001b24b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b250  mov     ebx, eax
0x18001b252  test    eax, eax
0x18001b254  js      loc_18001B3E9
0x18001b25a  mov     rcx, [rsp+170h+var_128]
0x18001b25f  lea     r8, [rsp+170h+var_130]
0x18001b264  mov     [rsp+170h+var_130], 0
0x18001b26d  lea     rdx, _GUID_efb23a09_a867_4be8_83a6_86969a7d0856
0x18001b274  mov     rax, [rcx]
0x18001b277  mov     rax, [rax]
0x18001b27a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b27f  mov     ebx, eax
0x18001b281  test    eax, eax
0x18001b283  js      loc_18001B3D8
0x18001b289  mov     rcx, [rsp+170h+var_130]
0x18001b28e  lea     rdx, [rsp+170h+var_140]
0x18001b293  mov     [rsp+170h+var_140], 0
0x18001b29b  mov     r9d, esi
0x18001b29e  mov     [rsp+170h+var_150], rdx
0x18001b2a3  mov     r8d, r14d
0x18001b2a6  xor     edx, edx
0x18001b2a8  mov     rax, [rcx]
0x18001b2ab  mov     rax, [rax+30h]
0x18001b2af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2b4  xor     esi, esi
0x18001b2b6  mov     ebx, eax
0x18001b2b8  test    eax, eax
0x18001b2ba  js      loc_18001B393
0x18001b2c0  mov     rcx, [rbp+70h+arg_0]; this
0x18001b2c7  lea     r9, [rsp+170h+var_138]; struct IWbemClassObject **
0x18001b2cc  mov     r8, r12; struct IWbemContext *
0x18001b2cf  mov     [rsp+170h+var_138], rsi
0x18001b2d4  mov     rdx, r13; struct IWbemServices *
0x18001b2d7  call    ?_CreateParamsObject@CCscWmiMethod@@IEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAPEAUIWbemClassObject@@@Z; CCscWmiMethod::_CreateParamsObject(IWbemServices *,IWbemContext *,IWbemClassObject * *)
0x18001b2dc  mov     ebx, eax
0x18001b2de  test    eax, eax
0x18001b2e0  js      loc_18001B393
0x18001b2e6  cmp     [rsp+170h+var_140], esi
0x18001b2ea  jnz     short loc_18001B2EE
0x18001b2ec  mov     edi, esi
0x18001b2ee  mov     rcx, [rsp+170h+var_138]
0x18001b2f3  lea     r9, [rsp+170h+pvarg]
0x18001b2f8  mov     word ptr [rsp+170h+pvarg+8], di
0x18001b2fd  lea     rdx, CSCWMI_STR_PARAM_OPENFILES; "OpenFiles"
0x18001b304  mov     r14d, 2
0x18001b30a  mov     dword ptr [rsp+170h+var_150], esi
0x18001b30e  mov     word ptr [rsp+170h+pvarg], r14w
0x18001b314  xor     r8d, r8d
0x18001b317  mov     rax, [rcx]
0x18001b31a  mov     rax, [rax+28h]
0x18001b31e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b323  mov     ebx, eax
0x18001b325  test    eax, eax
0x18001b327  js      short loc_18001B377
0x18001b329  mov     rax, [r15]
0x18001b32c  lea     r8, [rsp+170h+var_138]
0x18001b331  lea     edx, [r14-1]
0x18001b335  mov     rcx, r15
0x18001b338  mov     rax, [rax+18h]
0x18001b33c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b341  mov     ebx, eax
0x18001b343  test    eax, eax
0x18001b345  jns     short loc_18001B377
0x18001b347  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b34e  lea     rax, WPP_GLOBAL_Control
0x18001b355  cmp     rcx, rax
0x18001b358  jz      short loc_18001B377
0x18001b35a  test    [rcx+1Ch], r14b
0x18001b35e  jz      short loc_18001B377
0x18001b360  mov     rcx, [rcx+10h]
0x18001b364  lea     edx, [r14+66h]
0x18001b368  mov     r9d, ebx
0x18001b36b  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001b372  call    WPP_SF_d
0x18001b377  mov     rcx, [rsp+170h+var_138]
0x18001b37c  mov     rax, [rcx]
0x18001b37f  mov     rax, [rax+10h]
0x18001b383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b388  lea     rcx, [rsp+170h+pvarg]; pvarg
0x18001b38d  call    cs:__imp_VariantClear
0x18001b393  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b39a  lea     rax, WPP_GLOBAL_Control
0x18001b3a1  cmp     rcx, rax
0x18001b3a4  jz      short loc_18001B3C7
0x18001b3a6  test    dword ptr [rcx+1Ch], 4000000h
0x18001b3ad  jz      short loc_18001B3C7
0x18001b3af  mov     rcx, [rcx+10h]
0x18001b3b3  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001b3ba  mov     edx, 69h ; 'i'
0x18001b3bf  mov     r9d, ebx
0x18001b3c2  call    WPP_SF_d
0x18001b3c7  mov     rcx, [rsp+170h+var_130]
0x18001b3cc  mov     rax, [rcx]
0x18001b3cf  mov     rax, [rax+10h]
0x18001b3d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3d8  mov     rcx, [rsp+170h+var_128]
0x18001b3dd  mov     rax, [rcx]
0x18001b3e0  mov     rax, [rax+10h]
0x18001b3e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b3f0  lea     rax, WPP_GLOBAL_Control
0x18001b3f7  cmp     rcx, rax
0x18001b3fa  jz      short loc_18001B41D
0x18001b3fc  test    dword ptr [rcx+1Ch], 4000000h
0x18001b403  jz      short loc_18001B41D
0x18001b405  mov     rcx, [rcx+10h]
0x18001b409  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001b410  mov     edx, 6Ah ; 'j'
0x18001b415  mov     r9d, ebx
0x18001b418  call    WPP_SF_d
0x18001b41d  lea     rcx, [rsp+170h+var_100]; this
0x18001b422  call    ??1CCscWmiMethodParam@@QEAA@XZ; CCscWmiMethodParam::~CCscWmiMethodParam(void)
0x18001b427  lea     rcx, [rbp+70h+var_C0]; this
0x18001b42b  call    ??1CCscWmiMethodParam@@QEAA@XZ; CCscWmiMethodParam::~CCscWmiMethodParam(void)
0x18001b430  lea     rcx, [rbp+70h+var_80]; this
0x18001b434  call    ??1CCscWmiMethodParam@@QEAA@XZ; CCscWmiMethodParam::~CCscWmiMethodParam(void)
0x18001b439  mov     eax, ebx
0x18001b43b  add     rsp, 138h
0x18001b442  pop     r15
0x18001b444  pop     r14
0x18001b446  pop     r13
0x18001b448  pop     r12
0x18001b44a  pop     rdi
0x18001b44b  pop     rsi
0x18001b44c  pop     rbx
0x18001b44d  pop     rbp
0x18001b44e  retn
```
