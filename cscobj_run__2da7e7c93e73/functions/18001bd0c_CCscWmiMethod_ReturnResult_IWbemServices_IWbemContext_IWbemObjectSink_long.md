# CCscWmiMethod::_ReturnResult(IWbemServices *,IWbemContext *,IWbemObjectSink *,long)

- ea: `0x18001bd0c`
- end: `0x18001be65`
- name: `?_ReturnResult@CCscWmiMethod@@IEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@J@Z`
- size: `345`
- prototype: `__int64 __usercall@<rax>(CCscWmiMethod *__hidden this@<rcx>, struct IWbemServices *@<rdx>, struct IWbemContext *@<r8>, struct IWbemObjectSink *@<r9>, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180019140`

## callees

- `0x18000f5a4`
- `0x18000f5cc`
- `0x180019adc`
- `0x18001bd0c`
- `0x18001c208`
- `0x18002c010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18001be25`
- `OLEAUT32!__imp_VariantClear` at `0x18001be25`

## pseudocode

```c
__int64 __fastcall CCscWmiMethod::_ReturnResult(
        CCscWmiMethod *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IWbemObjectSink *a4,
        LONG a5)
{
  int v9; // ebx
  int v10; // eax
  int v11; // r8d
  struct IWbemClassObject *v13; // [rsp+30h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-40h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 54, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids);
  }
  v13 = 0;
  v9 = CCscWmiMethod::_CreateParamsObject(this, a2, a3, &v13);
  if ( v9 >= 0 )
  {
    pvarg.vt = 3;
    pvarg.lVal = a5;
    v10 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))v13->lpVtbl->Put)(
            v13,
            L"ReturnValue",
            0,
            &pvarg,
            0);
    v9 = v10;
    if ( v10 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_DSS(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 55, v11, v10, *((_QWORD *)this + 2), *((_QWORD *)this + 3));
    }
    else
    {
      v9 = ((__int64 (__fastcall *)(struct IWbemObjectSink *, __int64, struct IWbemClassObject **))a4->lpVtbl->Indicate)(
             a4,
             1,
             &v13);
    }
    ((void (__fastcall *)(struct IWbemClassObject *))v13->lpVtbl->Release)(v13);
    VariantClear(&pvarg);
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      56,
      WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
      (unsigned int)v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001bd0c  push    rbx
0x18001bd0e  push    rbp
0x18001bd0f  push    rsi
0x18001bd10  push    rdi
0x18001bd11  push    r14
0x18001bd13  sub     rsp, 50h
0x18001bd17  mov     rsi, r9
0x18001bd1a  mov     rbx, r8
0x18001bd1d  mov     rbp, rdx
0x18001bd20  mov     rdi, rcx
0x18001bd23  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd2a  lea     r14, WPP_GLOBAL_Control
0x18001bd31  cmp     rcx, r14
0x18001bd34  jz      short loc_18001BD54
0x18001bd36  test    dword ptr [rcx+1Ch], 4000000h
0x18001bd3d  jz      short loc_18001BD54
0x18001bd3f  mov     rcx, [rcx+10h]
0x18001bd43  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001bd4a  mov     edx, 36h ; '6'
0x18001bd4f  call    WPP_SF_
0x18001bd54  lea     r9, [rsp+78h+var_48]; struct IWbemClassObject **
0x18001bd59  mov     [rsp+78h+var_48], 0
0x18001bd62  mov     r8, rbx; struct IWbemContext *
0x18001bd65  mov     rdx, rbp; struct IWbemServices *
0x18001bd68  mov     rcx, rdi; this
0x18001bd6b  call    ?_CreateParamsObject@CCscWmiMethod@@IEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAPEAUIWbemClassObject@@@Z; CCscWmiMethod::_CreateParamsObject(IWbemServices *,IWbemContext *,IWbemClassObject * *)
0x18001bd70  mov     ebx, eax
0x18001bd72  test    eax, eax
0x18001bd74  js      loc_18001BE2B
0x18001bd7a  mov     rcx, [rsp+78h+var_48]
0x18001bd7f  lea     r9, [rsp+78h+pvarg]
0x18001bd84  mov     eax, 3
0x18001bd89  mov     dword ptr [rsp+78h+var_58], 0
0x18001bd91  mov     word ptr [rsp+78h+pvarg], ax
0x18001bd96  lea     rdx, aReturnvalue; "ReturnValue"
0x18001bd9d  mov     eax, [rsp+78h+arg_20]
0x18001bda4  xor     r8d, r8d
0x18001bda7  mov     dword ptr [rsp+78h+pvarg+8], eax
0x18001bdab  mov     rax, [rcx]
0x18001bdae  mov     rax, [rax+28h]
0x18001bdb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdb7  mov     ebx, eax
0x18001bdb9  test    eax, eax
0x18001bdbb  js      short loc_18001BDDA
0x18001bdbd  mov     rax, [rsi]
0x18001bdc0  lea     r8, [rsp+78h+var_48]
0x18001bdc5  mov     edx, 1
0x18001bdca  mov     rcx, rsi
0x18001bdcd  mov     rax, [rax+18h]
0x18001bdd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdd6  mov     ebx, eax
0x18001bdd8  jmp     short loc_18001BE0F
0x18001bdda  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bde1  cmp     rcx, r14
0x18001bde4  jz      short loc_18001BE0F
0x18001bde6  test    byte ptr [rcx+1Ch], 2
0x18001bdea  jz      short loc_18001BE0F
0x18001bdec  mov     rax, [rdi+18h]
0x18001bdf0  mov     edx, 37h ; '7'
0x18001bdf5  mov     rcx, [rcx+10h]
0x18001bdf9  mov     r9d, ebx
0x18001bdfc  mov     [rsp+78h+var_50], rax
0x18001be01  mov     rax, [rdi+10h]
0x18001be05  mov     [rsp+78h+var_58], rax
0x18001be0a  call    WPP_SF_DSS
0x18001be0f  mov     rcx, [rsp+78h+var_48]
0x18001be14  mov     rax, [rcx]
0x18001be17  mov     rax, [rax+10h]
0x18001be1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be20  lea     rcx, [rsp+78h+pvarg]; pvarg
0x18001be25  call    cs:__imp_VariantClear
0x18001be2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be32  cmp     rcx, r14
0x18001be35  jz      short loc_18001BE58
0x18001be37  test    dword ptr [rcx+1Ch], 4000000h
0x18001be3e  jz      short loc_18001BE58
0x18001be40  mov     rcx, [rcx+10h]
0x18001be44  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001be4b  mov     edx, 38h ; '8'
0x18001be50  mov     r9d, ebx
0x18001be53  call    WPP_SF_d
0x18001be58  mov     eax, ebx
0x18001be5a  add     rsp, 50h
0x18001be5e  pop     r14
0x18001be60  pop     rdi
0x18001be61  pop     rsi
0x18001be62  pop     rbp
0x18001be63  pop     rbx
0x18001be64  retn
```
