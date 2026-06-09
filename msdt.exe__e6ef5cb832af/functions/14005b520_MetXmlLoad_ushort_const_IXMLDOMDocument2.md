# MetXmlLoad(ushort const *,IXMLDOMDocument2 * *)

- ea: `0x14005b520`
- end: `0x14005b6db`
- name: `?MetXmlLoad@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z`
- size: `443`
- prototype: `__int64 __fastcall(OLECHAR *psz, LPVOID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14005421c`
- `0x14005c8d8`

## callees

- `0x140020420`
- `0x14005b520`
- `0x140063010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14005b602`
- `OLEAUT32!__imp_SysAllocString` at `0x14005b602`
- `OLEAUT32!__imp_VariantInit` at `0x14005b55a`
- `OLEAUT32!__imp_VariantInit` at `0x14005b55a`
- `OLEAUT32!__imp_VariantClear` at `0x14005b6a2`
- `OLEAUT32!__imp_VariantClear` at `0x14005b6a2`
- `ole32!CoCreateInstance` at `0x14005b5bf`
- `ole32!CoCreateInstance` at `0x14005b5bf`

## string_xrefs

- `0x14005b57a`: `MetXmlLoad`

## pseudocode

```c
__int64 __fastcall MetXmlLoad(OLECHAR *psz, LPVOID *a2)
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
    v4 = 56;
LABEL_3:
    v5 = -2147024809;
    v6 = -2147024809;
LABEL_4:
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetXmlLoad", v4, v5);
    goto LABEL_19;
  }
  if ( !a2 )
  {
    v4 = 57;
    goto LABEL_3;
  }
  v5 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x15u, &IID_IXMLDOMDocument2, &ppv);
  v6 = v5;
  if ( v5 < 0 )
  {
    v4 = 68;
    goto LABEL_4;
  }
  v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
  v6 = v5;
  if ( v5 < 0 )
  {
    v4 = 71;
    goto LABEL_4;
  }
  pvarg.llVal = (LONGLONG)SysAllocString(psz);
  if ( !pvarg.llVal )
  {
    v6 = -2147024882;
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetXmlLoad", 74, -2147024882);
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
    v4 = 79;
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
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetXmlLoad", 80, -2147467259);
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
0x14005b520  mov     [rsp-18h+arg_8], rbx
0x14005b525  mov     [rsp-18h+arg_18], rsi
0x14005b52a  push    rbp
0x14005b52b  push    rdi
0x14005b52c  push    r14
0x14005b52e  mov     rbp, rsp
0x14005b531  sub     rsp, 70h
0x14005b535  xor     eax, eax
0x14005b537  mov     rsi, rcx
0x14005b53a  mov     qword ptr [rbp+pvarg+10h], rax
0x14005b53e  lea     rcx, [rbp+pvarg]; pvarg
0x14005b542  or      eax, 0FFFFFFFFh
0x14005b545  xorps   xmm0, xmm0
0x14005b548  xor     r14d, r14d
0x14005b54b  mov     [rbp+arg_0], ax
0x14005b54f  mov     rdi, rdx
0x14005b552  mov     [rbp+arg_10], r14
0x14005b556  movups  xmmword ptr [rbp+pvarg], xmm0
0x14005b55a  call    cs:__imp_VariantInit
0x14005b561  nop     dword ptr [rax+rax+00h]
0x14005b566  test    rsi, rsi
0x14005b569  jnz     short loc_14005B597
0x14005b56b  lea     r9d, [r14+38h]
0x14005b56f  mov     eax, 80070057h
0x14005b574  mov     ebx, eax
0x14005b576  mov     dword ptr [rsp+70h+ppv], eax
0x14005b57a  lea     r8, aMetxmlload; "MetXmlLoad"
0x14005b581  mov     ecx, 1; Level
0x14005b586  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x14005b58d  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14005b592  jmp     loc_14005B69E
0x14005b597  test    rdi, rdi
0x14005b59a  jnz     short loc_14005B5A2
0x14005b59c  lea     r9d, [rdi+39h]
0x14005b5a0  jmp     short loc_14005B56F
0x14005b5a2  xor     edx, edx; pUnkOuter
0x14005b5a4  lea     rax, [rbp+arg_10]
0x14005b5a8  lea     r9, IID_IXMLDOMDocument2; riid
0x14005b5af  mov     [rsp+70h+ppv], rax; ppv
0x14005b5b4  lea     rcx, CLSID_DOMDocument60; rclsid
0x14005b5bb  lea     r8d, [rdx+15h]; dwClsContext
0x14005b5bf  call    cs:__imp_CoCreateInstance
0x14005b5c6  nop     dword ptr [rax+rax+00h]
0x14005b5cb  mov     ebx, eax
0x14005b5cd  test    eax, eax
0x14005b5cf  jns     short loc_14005B5D9
0x14005b5d1  mov     r9d, 44h ; 'D'
0x14005b5d7  jmp     short loc_14005B576
0x14005b5d9  mov     rcx, [rbp+arg_10]
0x14005b5dd  xor     edx, edx
0x14005b5df  mov     rax, [rcx]
0x14005b5e2  mov     rax, [rax+1F8h]
0x14005b5e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b5ee  mov     ebx, eax
0x14005b5f0  test    eax, eax
0x14005b5f2  jns     short loc_14005B5FF
0x14005b5f4  mov     r9d, 47h ; 'G'
0x14005b5fa  jmp     loc_14005B576
0x14005b5ff  mov     rcx, rsi; psz
0x14005b602  call    cs:__imp_SysAllocString
0x14005b609  nop     dword ptr [rax+rax+00h]
0x14005b60e  mov     qword ptr [rbp+pvarg+8], rax
0x14005b612  test    rax, rax
0x14005b615  jnz     short loc_14005B629
0x14005b617  mov     ebx, 8007000Eh
0x14005b61c  lea     r9d, [rax+4Ah]
0x14005b620  mov     dword ptr [rsp+70h+ppv], ebx
0x14005b624  jmp     loc_14005B57A
0x14005b629  mov     rcx, [rbp+arg_10]
0x14005b62d  lea     r8, [rbp+arg_0]
0x14005b631  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x14005b636  lea     rdx, [rbp+var_20]
0x14005b63a  mov     eax, 8
0x14005b63f  movsd   [rbp+var_10], xmm1
0x14005b644  mov     word ptr [rbp+pvarg], ax
0x14005b648  mov     rax, [rcx]
0x14005b64b  movups  xmm0, xmmword ptr [rbp+pvarg]
0x14005b64f  mov     rax, [rax+1D0h]
0x14005b656  movaps  [rbp+var_20], xmm0
0x14005b65a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b65f  mov     ebx, eax
0x14005b661  test    eax, eax
0x14005b663  jns     short loc_14005B670
0x14005b665  mov     r9d, 4Fh ; 'O'
0x14005b66b  jmp     loc_14005B576
0x14005b670  cmp     [rbp+arg_0], r14w
0x14005b675  jnz     short loc_14005B68B
0x14005b677  mov     ebx, 80004005h
0x14005b67c  mov     r9d, 50h ; 'P'
0x14005b682  mov     dword ptr [rsp+70h+ppv], ebx
0x14005b686  jmp     loc_14005B57A
0x14005b68b  mov     rcx, [rbp+arg_10]
0x14005b68f  mov     [rdi], rcx
0x14005b692  mov     rax, [rcx]
0x14005b695  mov     rax, [rax+8]
0x14005b699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b69e  lea     rcx, [rbp+pvarg]; pvarg
0x14005b6a2  call    cs:__imp_VariantClear
0x14005b6a9  nop     dword ptr [rax+rax+00h]
0x14005b6ae  mov     rcx, [rbp+arg_10]
0x14005b6b2  test    rcx, rcx
0x14005b6b5  jz      short loc_14005B6C3
0x14005b6b7  mov     rax, [rcx]
0x14005b6ba  mov     rax, [rax+10h]
0x14005b6be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b6c3  lea     r11, [rsp+70h+var_s0]
0x14005b6c8  mov     eax, ebx
0x14005b6ca  mov     rbx, [r11+28h]
0x14005b6ce  mov     rsi, [r11+38h]
0x14005b6d2  mov     rsp, r11
0x14005b6d5  pop     r14
0x14005b6d7  pop     rdi
0x14005b6d8  pop     rbp
0x14005b6d9  retn
```
