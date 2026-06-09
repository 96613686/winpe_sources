# Configuration::LoadSupport(IXMLDOMDocument2 *)

- ea: `0x140037b90`
- end: `0x140037e23`
- name: `?LoadSupport@Configuration@@AEAAJPEAUIXMLDOMDocument2@@@Z`
- size: `659`
- prototype: `int(Configuration *__hidden this, struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x140036690`

## callees

- `0x140020420`
- `0x140020b00`
- `0x140037b90`
- `0x14003896c`
- `0x140063010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140037c23`
- `KERNEL32!HeapFree` at `0x140037c23`
- `KERNEL32!GetProcessHeap` at `0x140037c0f`
- `KERNEL32!GetProcessHeap` at `0x140037c0f`
- `OLEAUT32!__imp_SysFreeString` at `0x140037c59`
- `OLEAUT32!__imp_SysFreeString` at `0x140037cba`
- `OLEAUT32!__imp_SysFreeString` at `0x140037e03`
- `OLEAUT32!__imp_SysFreeString` at `0x140037c59`
- `OLEAUT32!__imp_SysFreeString` at `0x140037cba`
- `OLEAUT32!__imp_SysFreeString` at `0x140037e03`

## string_xrefs

- `0x140037bc7`: `/SupportPackageConfiguration/SupportProvider`
- `0x140037be2`: `Configuration::LoadSupport`
- `0x140037c74`: `/SupportPackageConfiguration/CustomerID`
- `0x140037cd5`: `/SupportPackageConfiguration/Disconnected`
- `0x140037d26`: `/SupportPackageConfiguration/OAS`
- `0x140037d77`: `/SupportPackageConfiguration/Answers`

## pseudocode

```c
__int64 __fastcall Configuration::LoadSupport(Configuration *this, struct IXMLDOMDocument2 *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // r9d
  void *v7; // r14
  HANDLE ProcessHeap; // rax
  BSTR bstrString; // [rsp+60h] [rbp+30h] BYREF
  __int64 v11; // [rsp+70h] [rbp+40h] BYREF

  bstrString = 0;
  v11 = 0;
  *((_DWORD *)this + 66) = 1;
  v4 = Configuration::TextFromSingleNode(L"/SupportPackageConfiguration/SupportProvider", a2, &bstrString);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 1311;
LABEL_3:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Configuration::LoadSupport", v6, v4);
    goto LABEL_37;
  }
  if ( !v4 )
  {
    v7 = (void *)*((_QWORD *)this + 12);
    if ( v7 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v7);
      *((_QWORD *)this + 12) = 0;
    }
    v4 = DwzStrCpy((unsigned __int16 **)this + 12, bstrString);
    v5 = v4;
    if ( v4 < 0 )
    {
      v6 = 1316;
      goto LABEL_3;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
  }
  v4 = Configuration::TextFromSingleNode(L"/SupportPackageConfiguration/CustomerID", a2, &bstrString);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 1325;
    goto LABEL_3;
  }
  if ( !v4 )
  {
    v4 = DwzStrCpy((unsigned __int16 **)this + 14, bstrString);
    v5 = v4;
    if ( v4 < 0 )
    {
      v6 = 1328;
      goto LABEL_3;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
  }
  v4 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, const wchar_t *, __int64 *))a2->lpVtbl->selectSingleNode)(
         a2,
         L"/SupportPackageConfiguration/Disconnected",
         &v11);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 1337;
    goto LABEL_3;
  }
  if ( !v4 )
    *((_DWORD *)this + 12) = 1;
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  v4 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, const wchar_t *, __int64 *))a2->lpVtbl->selectSingleNode)(
         a2,
         L"/SupportPackageConfiguration/OAS",
         &v11);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 1348;
    goto LABEL_3;
  }
  if ( !v4 )
    *((_DWORD *)this + 21) = 1;
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  v4 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, const wchar_t *, __int64 *))a2->lpVtbl->selectSingleNode)(
         a2,
         L"/SupportPackageConfiguration/Answers",
         &v11);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 1359;
    goto LABEL_3;
  }
  if ( !v4 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v11 + 272LL))(v11, &bstrString);
    v5 = v4;
    if ( v4 < 0 )
    {
      v6 = 1362;
      goto LABEL_3;
    }
    *((_QWORD *)this + 22) = bstrString;
    bstrString = 0;
  }
  v5 = 0;
LABEL_37:
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  if ( bstrString )
    SysFreeString(bstrString);
  return v5;
}

```

## disassembly

```asm
0x140037b90  mov     [rsp-28h+arg_8], rbx
0x140037b95  push    rbp
0x140037b96  push    rsi
0x140037b97  push    rdi
0x140037b98  push    r12
0x140037b9a  push    r14
0x140037b9c  mov     rbp, rsp
0x140037b9f  sub     rsp, 30h
0x140037ba3  mov     rdi, rcx
0x140037ba6  mov     [rbp+bstrString], 0
0x140037bae  mov     r12d, 1
0x140037bb4  mov     [rbp+arg_10], 0
0x140037bbc  mov     [rcx+108h], r12d
0x140037bc3  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x140037bc7  lea     rcx, aSupportpackage_2; "/SupportPackageConfiguration/SupportPro"...
0x140037bce  mov     rsi, rdx
0x140037bd1  call    ?TextFromSingleNode@Configuration@@SAJPEBGPEAUIXMLDOMDocument2@@PEAPEAG@Z; Configuration::TextFromSingleNode(ushort const *,IXMLDOMDocument2 *,ushort * *)
0x140037bd6  mov     ebx, eax
0x140037bd8  test    eax, eax
0x140037bda  jns     short loc_140037C01
0x140037bdc  mov     r9d, 51Fh
0x140037be2  lea     r8, aConfigurationL_5; "Configuration::LoadSupport"
0x140037be9  mov     [rsp+30h+var_10], eax
0x140037bed  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140037bf4  mov     ecx, r12d; Level
0x140037bf7  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140037bfc  jmp     loc_140037DDD
0x140037c01  jnz     short loc_140037C6D
0x140037c03  lea     rbx, [rdi+60h]
0x140037c07  mov     r14, [rbx]
0x140037c0a  test    r14, r14
0x140037c0d  jz      short loc_140037C36
0x140037c0f  call    cs:__imp_GetProcessHeap
0x140037c16  nop     dword ptr [rax+rax+00h]
0x140037c1b  mov     r8, r14; lpMem
0x140037c1e  xor     edx, edx; dwFlags
0x140037c20  mov     rcx, rax; hHeap
0x140037c23  call    cs:__imp_HeapFree
0x140037c2a  nop     dword ptr [rax+rax+00h]
0x140037c2f  mov     qword ptr [rbx], 0
0x140037c36  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x140037c3a  mov     rcx, rbx; unsigned __int16 **
0x140037c3d  call    ?DwzStrCpy@@YAJPEAPEAGPEBG@Z; DwzStrCpy(ushort * *,ushort const *)
0x140037c42  mov     ebx, eax
0x140037c44  test    eax, eax
0x140037c46  jns     short loc_140037C50
0x140037c48  mov     r9d, 524h
0x140037c4e  jmp     short loc_140037BE2
0x140037c50  mov     rcx, [rbp+bstrString]; bstrString
0x140037c54  test    rcx, rcx
0x140037c57  jz      short loc_140037C6D
0x140037c59  call    cs:__imp_SysFreeString
0x140037c60  nop     dword ptr [rax+rax+00h]
0x140037c65  mov     [rbp+bstrString], 0
0x140037c6d  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x140037c71  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x140037c74  lea     rcx, aSupportpackage_3; "/SupportPackageConfiguration/CustomerID"
0x140037c7b  call    ?TextFromSingleNode@Configuration@@SAJPEBGPEAUIXMLDOMDocument2@@PEAPEAG@Z; Configuration::TextFromSingleNode(ushort const *,IXMLDOMDocument2 *,ushort * *)
0x140037c80  mov     ebx, eax
0x140037c82  test    eax, eax
0x140037c84  jns     short loc_140037C91
0x140037c86  mov     r9d, 52Dh
0x140037c8c  jmp     loc_140037BE2
0x140037c91  jnz     short loc_140037CCE
0x140037c93  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x140037c97  lea     rcx, [rdi+70h]; unsigned __int16 **
0x140037c9b  call    ?DwzStrCpy@@YAJPEAPEAGPEBG@Z; DwzStrCpy(ushort * *,ushort const *)
0x140037ca0  mov     ebx, eax
0x140037ca2  test    eax, eax
0x140037ca4  jns     short loc_140037CB1
0x140037ca6  mov     r9d, 530h
0x140037cac  jmp     loc_140037BE2
0x140037cb1  mov     rcx, [rbp+bstrString]; bstrString
0x140037cb5  test    rcx, rcx
0x140037cb8  jz      short loc_140037CCE
0x140037cba  call    cs:__imp_SysFreeString
0x140037cc1  nop     dword ptr [rax+rax+00h]
0x140037cc6  mov     [rbp+bstrString], 0
0x140037cce  mov     rax, [rsi]
0x140037cd1  lea     r8, [rbp+arg_10]
0x140037cd5  lea     rdx, aSupportpackage_0; "/SupportPackageConfiguration/Disconnect"...
0x140037cdc  mov     rcx, rsi
0x140037cdf  mov     rax, [rax+128h]
0x140037ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037ceb  mov     ebx, eax
0x140037ced  test    eax, eax
0x140037cef  jns     short loc_140037CFC
0x140037cf1  mov     r9d, 539h
0x140037cf7  jmp     loc_140037BE2
0x140037cfc  jnz     short loc_140037D02
0x140037cfe  mov     [rdi+30h], r12d
0x140037d02  mov     rcx, [rbp+arg_10]
0x140037d06  test    rcx, rcx
0x140037d09  jz      short loc_140037D1F
0x140037d0b  mov     rax, [rcx]
0x140037d0e  mov     rax, [rax+10h]
0x140037d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037d17  mov     [rbp+arg_10], 0
0x140037d1f  mov     rax, [rsi]
0x140037d22  lea     r8, [rbp+arg_10]
0x140037d26  lea     rdx, aSupportpackage_1; "/SupportPackageConfiguration/OAS"
0x140037d2d  mov     rcx, rsi
0x140037d30  mov     rax, [rax+128h]
0x140037d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037d3c  mov     ebx, eax
0x140037d3e  test    eax, eax
0x140037d40  jns     short loc_140037D4D
0x140037d42  mov     r9d, 544h
0x140037d48  jmp     loc_140037BE2
0x140037d4d  jnz     short loc_140037D53
0x140037d4f  mov     [rdi+54h], r12d
0x140037d53  mov     rcx, [rbp+arg_10]
0x140037d57  test    rcx, rcx
0x140037d5a  jz      short loc_140037D70
0x140037d5c  mov     rax, [rcx]
0x140037d5f  mov     rax, [rax+10h]
0x140037d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037d68  mov     [rbp+arg_10], 0
0x140037d70  mov     rax, [rsi]
0x140037d73  lea     r8, [rbp+arg_10]
0x140037d77  lea     rdx, aSupportpackage_4; "/SupportPackageConfiguration/Answers"
0x140037d7e  mov     rcx, rsi
0x140037d81  mov     rax, [rax+128h]
0x140037d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037d8d  mov     ebx, eax
0x140037d8f  test    eax, eax
0x140037d91  jns     short loc_140037D9E
0x140037d93  mov     r9d, 54Fh
0x140037d99  jmp     loc_140037BE2
0x140037d9e  jnz     short loc_140037DDB
0x140037da0  mov     rcx, [rbp+arg_10]
0x140037da4  lea     rdx, [rbp+bstrString]
0x140037da8  mov     rax, [rcx]
0x140037dab  mov     rax, [rax+110h]
0x140037db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037db7  mov     ebx, eax
0x140037db9  test    eax, eax
0x140037dbb  jns     short loc_140037DC8
0x140037dbd  mov     r9d, 552h
0x140037dc3  jmp     loc_140037BE2
0x140037dc8  mov     rax, [rbp+bstrString]
0x140037dcc  mov     [rdi+0B0h], rax
0x140037dd3  mov     [rbp+bstrString], 0
0x140037ddb  xor     ebx, ebx
0x140037ddd  mov     rcx, [rbp+arg_10]
0x140037de1  test    rcx, rcx
0x140037de4  jz      short loc_140037DFA
0x140037de6  mov     rax, [rcx]
0x140037de9  mov     rax, [rax+10h]
0x140037ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037df2  mov     [rbp+arg_10], 0
0x140037dfa  mov     rcx, [rbp+bstrString]; bstrString
0x140037dfe  test    rcx, rcx
0x140037e01  jz      short loc_140037E0F
0x140037e03  call    cs:__imp_SysFreeString
0x140037e0a  nop     dword ptr [rax+rax+00h]
0x140037e0f  mov     eax, ebx
0x140037e11  mov     rbx, [rsp+30h+arg_8]
0x140037e16  add     rsp, 30h
0x140037e1a  pop     r14
0x140037e1c  pop     r12
0x140037e1e  pop     rdi
0x140037e1f  pop     rsi
0x140037e20  pop     rbp
0x140037e21  retn
```
