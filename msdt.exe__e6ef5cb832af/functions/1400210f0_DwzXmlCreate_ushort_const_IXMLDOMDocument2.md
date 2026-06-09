# DwzXmlCreate(ushort const *,IXMLDOMDocument2 * *)

- ea: `0x1400210f0`
- end: `0x140021284`
- name: `?DwzXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z`
- size: `404`
- prototype: `__int64 __fastcall(OLECHAR *psz, LPVOID *)`
- caller_count: `8`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000f1a0`
- `0x140026f84`
- `0x1400342cc`
- `0x1400343f8`
- `0x140043024`
- `0x14004b8dc`
- `0x14004e654`
- `0x14004f5cc`

## callees

- `0x140020420`
- `0x1400210f0`
- `0x140063010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1400211bb`
- `OLEAUT32!__imp_SysAllocString` at `0x1400211bb`
- `OLEAUT32!__imp_SysFreeString` at `0x140021262`
- `OLEAUT32!__imp_SysFreeString` at `0x140021262`
- `ole32!CoCreateInstance` at `0x140021177`
- `ole32!CoCreateInstance` at `0x140021177`

## string_xrefs

- `0x14002112f`: `DwzXmlCreate`

## pseudocode

```c
__int64 __fastcall DwzXmlCreate(OLECHAR *psz, LPVOID *a2)
{
  OLECHAR *v4; // rdi
  int v5; // r9d
  HRESULT v6; // eax
  unsigned int v7; // ebx
  BSTR v8; // rax
  LPVOID v9; // rcx
  __int16 v11; // [rsp+50h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+18h] BYREF

  v11 = -1;
  ppv = 0;
  v4 = 0;
  if ( !psz )
  {
    v5 = 657;
LABEL_3:
    v6 = -2147024809;
    v7 = -2147024809;
LABEL_4:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzXmlCreate", v5, v6);
    goto LABEL_19;
  }
  if ( !a2 )
  {
    v5 = 658;
    goto LABEL_3;
  }
  v6 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x15u, &IID_IXMLDOMDocument2, &ppv);
  v7 = v6;
  if ( v6 < 0 )
  {
    v5 = 666;
    goto LABEL_4;
  }
  v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
  v7 = v6;
  if ( v6 < 0 )
  {
    v5 = 669;
    goto LABEL_4;
  }
  v8 = SysAllocString(psz);
  v4 = v8;
  if ( !v8 )
  {
    v7 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzXmlCreate", 672, -2147024882);
    goto LABEL_19;
  }
  v6 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int16 *))(*(_QWORD *)ppv + 520LL))(ppv, v8, &v11);
  v7 = v6;
  if ( v6 < 0 )
  {
    v5 = 675;
    goto LABEL_4;
  }
  if ( v11 )
  {
    v9 = ppv;
    *a2 = ppv;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 8LL))(v9);
  }
  else
  {
    v7 = -2147467259;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzXmlCreate", 676, -2147467259);
  }
LABEL_19:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v4 )
    SysFreeString(v4);
  return v7;
}

```

## disassembly

```asm
0x1400210f0  mov     [rsp+arg_8], rbx
0x1400210f5  mov     [rsp+arg_18], rbp
0x1400210fa  push    rsi
0x1400210fb  push    rdi
0x1400210fc  push    r14
0x1400210fe  sub     rsp, 30h
0x140021102  xor     ebp, ebp
0x140021104  or      eax, 0FFFFFFFFh
0x140021107  mov     [rsp+48h+arg_0], ax
0x14002110c  mov     r14, rdx
0x14002110f  mov     [rsp+48h+arg_10], rbp
0x140021114  mov     rsi, rcx
0x140021117  mov     edi, ebp
0x140021119  test    rcx, rcx
0x14002111c  jnz     short loc_14002114C
0x14002111e  mov     r9d, 291h
0x140021124  mov     eax, 80070057h
0x140021129  mov     ebx, eax
0x14002112b  mov     dword ptr [rsp+48h+ppv], eax
0x14002112f  lea     r8, aDwzxmlcreate; "DwzXmlCreate"
0x140021136  mov     ecx, 1; Level
0x14002113b  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140021142  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140021147  jmp     loc_14002123F
0x14002114c  test    r14, r14
0x14002114f  jnz     short loc_140021159
0x140021151  mov     r9d, 292h
0x140021157  jmp     short loc_140021124
0x140021159  xor     edx, edx; pUnkOuter
0x14002115b  lea     rax, [rsp+48h+arg_10]
0x140021160  lea     r9, IID_IXMLDOMDocument2; riid
0x140021167  mov     [rsp+48h+ppv], rax; ppv
0x14002116c  lea     rcx, CLSID_DOMDocument60; rclsid
0x140021173  lea     r8d, [rdx+15h]; dwClsContext
0x140021177  call    cs:__imp_CoCreateInstance
0x14002117e  nop     dword ptr [rax+rax+00h]
0x140021183  mov     ebx, eax
0x140021185  test    eax, eax
0x140021187  jns     short loc_140021191
0x140021189  mov     r9d, 29Ah
0x14002118f  jmp     short loc_14002112B
0x140021191  mov     rcx, [rsp+48h+arg_10]
0x140021196  xor     edx, edx
0x140021198  mov     rax, [rcx]
0x14002119b  mov     rax, [rax+1F8h]
0x1400211a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400211a7  mov     ebx, eax
0x1400211a9  test    eax, eax
0x1400211ab  jns     short loc_1400211B8
0x1400211ad  mov     r9d, 29Dh
0x1400211b3  jmp     loc_14002112B
0x1400211b8  mov     rcx, rsi; psz
0x1400211bb  call    cs:__imp_SysAllocString
0x1400211c2  nop     dword ptr [rax+rax+00h]
0x1400211c7  mov     rdi, rax
0x1400211ca  test    rax, rax
0x1400211cd  jnz     short loc_1400211E3
0x1400211cf  mov     ebx, 8007000Eh
0x1400211d4  mov     r9d, 2A0h
0x1400211da  mov     dword ptr [rsp+48h+ppv], ebx
0x1400211de  jmp     loc_14002112F
0x1400211e3  mov     rcx, [rsp+48h+arg_10]
0x1400211e8  lea     r8, [rsp+48h+arg_0]
0x1400211ed  mov     rdx, rdi
0x1400211f0  mov     rax, [rcx]
0x1400211f3  mov     rax, [rax+208h]
0x1400211fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400211ff  mov     ebx, eax
0x140021201  test    eax, eax
0x140021203  jns     short loc_140021210
0x140021205  mov     r9d, 2A3h
0x14002120b  jmp     loc_14002112B
0x140021210  cmp     [rsp+48h+arg_0], bp
0x140021215  jnz     short loc_14002122B
0x140021217  mov     ebx, 80004005h
0x14002121c  mov     r9d, 2A4h
0x140021222  mov     dword ptr [rsp+48h+ppv], ebx
0x140021226  jmp     loc_14002112F
0x14002122b  mov     rcx, [rsp+48h+arg_10]
0x140021230  mov     [r14], rcx
0x140021233  mov     rax, [rcx]
0x140021236  mov     rax, [rax+8]
0x14002123a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002123f  mov     rcx, [rsp+48h+arg_10]
0x140021244  test    rcx, rcx
0x140021247  jz      short loc_14002125A
0x140021249  mov     rax, [rcx]
0x14002124c  mov     rax, [rax+10h]
0x140021250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021255  mov     [rsp+48h+arg_10], rbp
0x14002125a  test    rdi, rdi
0x14002125d  jz      short loc_14002126E
0x14002125f  mov     rcx, rdi; bstrString
0x140021262  call    cs:__imp_SysFreeString
0x140021269  nop     dword ptr [rax+rax+00h]
0x14002126e  mov     rbp, [rsp+48h+arg_18]
0x140021273  mov     eax, ebx
0x140021275  mov     rbx, [rsp+48h+arg_8]
0x14002127a  add     rsp, 30h
0x14002127e  pop     r14
0x140021280  pop     rdi
0x140021281  pop     rsi
0x140021282  retn
```
