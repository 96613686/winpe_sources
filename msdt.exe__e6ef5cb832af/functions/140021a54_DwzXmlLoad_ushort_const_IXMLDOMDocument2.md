# DwzXmlLoad(ushort const *,IXMLDOMDocument2 * *)

- ea: `0x140021a54`
- end: `0x140021c15`
- name: `?DwzXmlLoad@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z`
- size: `449`
- prototype: `__int64 __fastcall(OLECHAR *psz, LPVOID *)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140029230`
- `0x140029a20`
- `0x1400362b8`
- `0x140036690`
- `0x1400433c8`
- `0x140048220`

## callees

- `0x140020420`
- `0x140021a54`
- `0x140063010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140021b3a`
- `OLEAUT32!__imp_SysAllocString` at `0x140021b3a`
- `OLEAUT32!__imp_VariantInit` at `0x140021a8e`
- `OLEAUT32!__imp_VariantInit` at `0x140021a8e`
- `OLEAUT32!__imp_VariantClear` at `0x140021bdc`
- `OLEAUT32!__imp_VariantClear` at `0x140021bdc`
- `ole32!CoCreateInstance` at `0x140021af7`
- `ole32!CoCreateInstance` at `0x140021af7`

## string_xrefs

- `0x140021ab0`: `DwzXmlLoad`

## pseudocode

```c
__int64 __fastcall DwzXmlLoad(OLECHAR *psz, LPVOID *a2)
{
  int v4; // r9d
  HRESULT v5; // eax
  unsigned int v6; // ebx
  __int64 (__fastcall *v7)(LPVOID, __int128 *, __int16 *); // rax
  LPVOID v8; // rcx
  VARIANTARG pvarg; // [rsp+30h] [rbp-40h] BYREF
  __int128 v11; // [rsp+50h] [rbp-20h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-10h]
  __int16 v13; // [rsp+90h] [rbp+20h] BYREF
  LPVOID ppv; // [rsp+A0h] [rbp+30h] BYREF

  v13 = -1;
  ppv = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !psz )
  {
    v4 = 724;
LABEL_3:
    v5 = -2147024809;
    v6 = -2147024809;
LABEL_4:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzXmlLoad", v4, v5);
    goto LABEL_19;
  }
  if ( !a2 )
  {
    v4 = 725;
    goto LABEL_3;
  }
  v5 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x15u, &IID_IXMLDOMDocument2, &ppv);
  v6 = v5;
  if ( v5 < 0 )
  {
    v4 = 736;
    goto LABEL_4;
  }
  v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
  v6 = v5;
  if ( v5 < 0 )
  {
    v4 = 739;
    goto LABEL_4;
  }
  pvarg.llVal = (LONGLONG)SysAllocString(psz);
  if ( !pvarg.llVal )
  {
    v6 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzXmlLoad", 742, -2147024882);
    goto LABEL_19;
  }
  pRecInfo = pvarg.pRecInfo;
  pvarg.vt = 8;
  v7 = *(__int64 (__fastcall **)(LPVOID, __int128 *, __int16 *))(*(_QWORD *)ppv + 464LL);
  v11 = *(_OWORD *)&pvarg.vt;
  v5 = v7(ppv, &v11, &v13);
  v6 = v5;
  if ( v5 < 0 )
  {
    v4 = 747;
    goto LABEL_4;
  }
  if ( v13 )
  {
    v8 = ppv;
    *a2 = ppv;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 8LL))(v8);
  }
  else
  {
    v6 = -2147467259;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzXmlLoad", 748, -2147467259);
  }
LABEL_19:
  VariantClear(&pvarg);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v6;
}

```

## disassembly

```asm
0x140021a54  mov     [rsp-18h+arg_8], rbx
0x140021a59  mov     [rsp-18h+arg_18], rsi
0x140021a5e  push    rbp
0x140021a5f  push    rdi
0x140021a60  push    r14
0x140021a62  mov     rbp, rsp
0x140021a65  sub     rsp, 70h
0x140021a69  xor     eax, eax
0x140021a6b  mov     rsi, rcx
0x140021a6e  mov     qword ptr [rbp+pvarg+10h], rax
0x140021a72  lea     rcx, [rbp+pvarg]; pvarg
0x140021a76  or      eax, 0FFFFFFFFh
0x140021a79  xorps   xmm0, xmm0
0x140021a7c  xor     r14d, r14d
0x140021a7f  mov     [rbp+arg_0], ax
0x140021a83  mov     rdi, rdx
0x140021a86  mov     [rbp+arg_10], r14
0x140021a8a  movups  xmmword ptr [rbp+pvarg], xmm0
0x140021a8e  call    cs:__imp_VariantInit
0x140021a95  nop     dword ptr [rax+rax+00h]
0x140021a9a  test    rsi, rsi
0x140021a9d  jnz     short loc_140021ACD
0x140021a9f  mov     r9d, 2D4h
0x140021aa5  mov     eax, 80070057h
0x140021aaa  mov     ebx, eax
0x140021aac  mov     dword ptr [rsp+70h+ppv], eax
0x140021ab0  lea     r8, aDwzxmlload; "DwzXmlLoad"
0x140021ab7  mov     ecx, 1; Level
0x140021abc  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140021ac3  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140021ac8  jmp     loc_140021BD8
0x140021acd  test    rdi, rdi
0x140021ad0  jnz     short loc_140021ADA
0x140021ad2  mov     r9d, 2D5h
0x140021ad8  jmp     short loc_140021AA5
0x140021ada  xor     edx, edx; pUnkOuter
0x140021adc  lea     rax, [rbp+arg_10]
0x140021ae0  lea     r9, IID_IXMLDOMDocument2; riid
0x140021ae7  mov     [rsp+70h+ppv], rax; ppv
0x140021aec  lea     rcx, CLSID_DOMDocument60; rclsid
0x140021af3  lea     r8d, [rdx+15h]; dwClsContext
0x140021af7  call    cs:__imp_CoCreateInstance
0x140021afe  nop     dword ptr [rax+rax+00h]
0x140021b03  mov     ebx, eax
0x140021b05  test    eax, eax
0x140021b07  jns     short loc_140021B11
0x140021b09  mov     r9d, 2E0h
0x140021b0f  jmp     short loc_140021AAC
0x140021b11  mov     rcx, [rbp+arg_10]
0x140021b15  xor     edx, edx
0x140021b17  mov     rax, [rcx]
0x140021b1a  mov     rax, [rax+1F8h]
0x140021b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021b26  mov     ebx, eax
0x140021b28  test    eax, eax
0x140021b2a  jns     short loc_140021B37
0x140021b2c  mov     r9d, 2E3h
0x140021b32  jmp     loc_140021AAC
0x140021b37  mov     rcx, rsi; psz
0x140021b3a  call    cs:__imp_SysAllocString
0x140021b41  nop     dword ptr [rax+rax+00h]
0x140021b46  mov     qword ptr [rbp+pvarg+8], rax
0x140021b4a  test    rax, rax
0x140021b4d  jnz     short loc_140021B63
0x140021b4f  mov     ebx, 8007000Eh
0x140021b54  mov     r9d, 2E6h
0x140021b5a  mov     dword ptr [rsp+70h+ppv], ebx
0x140021b5e  jmp     loc_140021AB0
0x140021b63  mov     rcx, [rbp+arg_10]
0x140021b67  lea     r8, [rbp+arg_0]
0x140021b6b  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x140021b70  lea     rdx, [rbp+var_20]
0x140021b74  mov     eax, 8
0x140021b79  movsd   [rbp+var_10], xmm1
0x140021b7e  mov     word ptr [rbp+pvarg], ax
0x140021b82  mov     rax, [rcx]
0x140021b85  movups  xmm0, xmmword ptr [rbp+pvarg]
0x140021b89  mov     rax, [rax+1D0h]
0x140021b90  movaps  [rbp+var_20], xmm0
0x140021b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021b99  mov     ebx, eax
0x140021b9b  test    eax, eax
0x140021b9d  jns     short loc_140021BAA
0x140021b9f  mov     r9d, 2EBh
0x140021ba5  jmp     loc_140021AAC
0x140021baa  cmp     [rbp+arg_0], r14w
0x140021baf  jnz     short loc_140021BC5
0x140021bb1  mov     ebx, 80004005h
0x140021bb6  mov     r9d, 2ECh
0x140021bbc  mov     dword ptr [rsp+70h+ppv], ebx
0x140021bc0  jmp     loc_140021AB0
0x140021bc5  mov     rcx, [rbp+arg_10]
0x140021bc9  mov     [rdi], rcx
0x140021bcc  mov     rax, [rcx]
0x140021bcf  mov     rax, [rax+8]
0x140021bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021bd8  lea     rcx, [rbp+pvarg]; pvarg
0x140021bdc  call    cs:__imp_VariantClear
0x140021be3  nop     dword ptr [rax+rax+00h]
0x140021be8  mov     rcx, [rbp+arg_10]
0x140021bec  test    rcx, rcx
0x140021bef  jz      short loc_140021BFD
0x140021bf1  mov     rax, [rcx]
0x140021bf4  mov     rax, [rax+10h]
0x140021bf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021bfd  lea     r11, [rsp+70h+var_s0]
0x140021c02  mov     eax, ebx
0x140021c04  mov     rbx, [r11+28h]
0x140021c08  mov     rsi, [r11+38h]
0x140021c0c  mov     rsp, r11
0x140021c0f  pop     r14
0x140021c11  pop     rdi
0x140021c12  pop     rbp
0x140021c13  retn
```
