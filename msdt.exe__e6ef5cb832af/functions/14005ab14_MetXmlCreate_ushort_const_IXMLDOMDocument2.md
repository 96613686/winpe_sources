# MetXmlCreate(ushort const *,IXMLDOMDocument2 * *)

- ea: `0x14005ab14`
- end: `0x14005aca6`
- name: `?MetXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z`
- size: `402`
- prototype: `__int64 __fastcall(OLECHAR *psz, LPVOID *)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140054de0`
- `0x1400591ac`
- `0x140059278`
- `0x14005ca60`

## callees

- `0x140020420`
- `0x14005ab14`
- `0x140063010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14005abdd`
- `OLEAUT32!__imp_SysAllocString` at `0x14005abdd`
- `OLEAUT32!__imp_SysFreeString` at `0x14005ac84`
- `OLEAUT32!__imp_SysFreeString` at `0x14005ac84`
- `ole32!CoCreateInstance` at `0x14005ab99`
- `ole32!CoCreateInstance` at `0x14005ab99`

## string_xrefs

- `0x14005ab51`: `MetXmlCreate`

## pseudocode

```c
__int64 __fastcall MetXmlCreate(OLECHAR *psz, LPVOID *a2)
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
    v5 = 127;
LABEL_3:
    v6 = -2147024809;
    v7 = -2147024809;
LABEL_4:
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetXmlCreate", v5, v6);
    goto LABEL_19;
  }
  if ( !a2 )
  {
    v5 = 128;
    goto LABEL_3;
  }
  v6 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x15u, &IID_IXMLDOMDocument2, &ppv);
  v7 = v6;
  if ( v6 < 0 )
  {
    v5 = 136;
    goto LABEL_4;
  }
  v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
  v7 = v6;
  if ( v6 < 0 )
  {
    v5 = 139;
    goto LABEL_4;
  }
  v8 = SysAllocString(psz);
  v4 = v8;
  if ( !v8 )
  {
    v7 = -2147024882;
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetXmlCreate", 142, -2147024882);
    goto LABEL_19;
  }
  v6 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int16 *))(*(_QWORD *)ppv + 520LL))(ppv, v8, &v11);
  v7 = v6;
  if ( v6 < 0 )
  {
    v5 = 145;
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
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetXmlCreate", 146, -2147467259);
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
0x14005ab14  mov     [rsp+arg_8], rbx
0x14005ab19  mov     [rsp+arg_18], rbp
0x14005ab1e  push    rsi
0x14005ab1f  push    rdi
0x14005ab20  push    r14
0x14005ab22  sub     rsp, 30h
0x14005ab26  xor     ebp, ebp
0x14005ab28  or      eax, 0FFFFFFFFh
0x14005ab2b  mov     [rsp+48h+arg_0], ax
0x14005ab30  mov     r14, rdx
0x14005ab33  mov     [rsp+48h+arg_10], rbp
0x14005ab38  mov     rsi, rcx
0x14005ab3b  mov     edi, ebp
0x14005ab3d  test    rcx, rcx
0x14005ab40  jnz     short loc_14005AB6E
0x14005ab42  lea     r9d, [rcx+7Fh]
0x14005ab46  mov     eax, 80070057h
0x14005ab4b  mov     ebx, eax
0x14005ab4d  mov     dword ptr [rsp+48h+ppv], eax
0x14005ab51  lea     r8, aMetxmlcreate; "MetXmlCreate"
0x14005ab58  mov     ecx, 1; Level
0x14005ab5d  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x14005ab64  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14005ab69  jmp     loc_14005AC61
0x14005ab6e  test    r14, r14
0x14005ab71  jnz     short loc_14005AB7B
0x14005ab73  mov     r9d, 80h
0x14005ab79  jmp     short loc_14005AB46
0x14005ab7b  xor     edx, edx; pUnkOuter
0x14005ab7d  lea     rax, [rsp+48h+arg_10]
0x14005ab82  lea     r9, IID_IXMLDOMDocument2; riid
0x14005ab89  mov     [rsp+48h+ppv], rax; ppv
0x14005ab8e  lea     rcx, CLSID_DOMDocument60; rclsid
0x14005ab95  lea     r8d, [rdx+15h]; dwClsContext
0x14005ab99  call    cs:__imp_CoCreateInstance
0x14005aba0  nop     dword ptr [rax+rax+00h]
0x14005aba5  mov     ebx, eax
0x14005aba7  test    eax, eax
0x14005aba9  jns     short loc_14005ABB3
0x14005abab  mov     r9d, 88h
0x14005abb1  jmp     short loc_14005AB4D
0x14005abb3  mov     rcx, [rsp+48h+arg_10]
0x14005abb8  xor     edx, edx
0x14005abba  mov     rax, [rcx]
0x14005abbd  mov     rax, [rax+1F8h]
0x14005abc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005abc9  mov     ebx, eax
0x14005abcb  test    eax, eax
0x14005abcd  jns     short loc_14005ABDA
0x14005abcf  mov     r9d, 8Bh
0x14005abd5  jmp     loc_14005AB4D
0x14005abda  mov     rcx, rsi; psz
0x14005abdd  call    cs:__imp_SysAllocString
0x14005abe4  nop     dword ptr [rax+rax+00h]
0x14005abe9  mov     rdi, rax
0x14005abec  test    rax, rax
0x14005abef  jnz     short loc_14005AC05
0x14005abf1  mov     ebx, 8007000Eh
0x14005abf6  mov     r9d, 8Eh
0x14005abfc  mov     dword ptr [rsp+48h+ppv], ebx
0x14005ac00  jmp     loc_14005AB51
0x14005ac05  mov     rcx, [rsp+48h+arg_10]
0x14005ac0a  lea     r8, [rsp+48h+arg_0]
0x14005ac0f  mov     rdx, rdi
0x14005ac12  mov     rax, [rcx]
0x14005ac15  mov     rax, [rax+208h]
0x14005ac1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005ac21  mov     ebx, eax
0x14005ac23  test    eax, eax
0x14005ac25  jns     short loc_14005AC32
0x14005ac27  mov     r9d, 91h
0x14005ac2d  jmp     loc_14005AB4D
0x14005ac32  cmp     [rsp+48h+arg_0], bp
0x14005ac37  jnz     short loc_14005AC4D
0x14005ac39  mov     ebx, 80004005h
0x14005ac3e  mov     r9d, 92h
0x14005ac44  mov     dword ptr [rsp+48h+ppv], ebx
0x14005ac48  jmp     loc_14005AB51
0x14005ac4d  mov     rcx, [rsp+48h+arg_10]
0x14005ac52  mov     [r14], rcx
0x14005ac55  mov     rax, [rcx]
0x14005ac58  mov     rax, [rax+8]
0x14005ac5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005ac61  mov     rcx, [rsp+48h+arg_10]
0x14005ac66  test    rcx, rcx
0x14005ac69  jz      short loc_14005AC7C
0x14005ac6b  mov     rax, [rcx]
0x14005ac6e  mov     rax, [rax+10h]
0x14005ac72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005ac77  mov     [rsp+48h+arg_10], rbp
0x14005ac7c  test    rdi, rdi
0x14005ac7f  jz      short loc_14005AC90
0x14005ac81  mov     rcx, rdi; bstrString
0x14005ac84  call    cs:__imp_SysFreeString
0x14005ac8b  nop     dword ptr [rax+rax+00h]
0x14005ac90  mov     rbp, [rsp+48h+arg_18]
0x14005ac95  mov     eax, ebx
0x14005ac97  mov     rbx, [rsp+48h+arg_8]
0x14005ac9c  add     rsp, 30h
0x14005aca0  pop     r14
0x14005aca2  pop     rdi
0x14005aca3  pop     rsi
0x14005aca4  retn
```
