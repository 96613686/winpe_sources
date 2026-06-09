# CLanAdvancedPage::IsAdapterDHCPEnabled(IHNetConnection *)

- ea: `0x18002ca9c`
- end: `0x18002cba9`
- name: `?IsAdapterDHCPEnabled@CLanAdvancedPage@@AEAAHPEAUIHNetConnection@@@Z`
- size: `269`
- prototype: `__int64 __fastcall(CLanAdvancedPage *__hidden this, struct IHNetConnection *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18002f0d8`

## callees

- `0x1800166dc`
- `0x180019344`
- `0x18001e1e0`
- `0x18001eb7c`
- `0x18002bb58`
- `0x18002ca9c`
- `0x1800303d8`
- `0x180040f04`
- `0x180065010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002cb7a`
- `ole32!CoTaskMemFree` at `0x18002cb7a`
- `ole32!StringFromGUID2` at `0x18002cafb`
- `ole32!StringFromGUID2` at `0x18002cafb`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CLanAdvancedPage::IsAdapterDHCPEnabled(CLanAdvancedPage *this, struct IHNetConnection *a2)
{
  unsigned int v2; // ebx
  GUID *rguid; // [rsp+20h] [rbp-E0h] BYREF
  __int16 v5; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 v6; // [rsp+32h] [rbp-CEh]
  int v7; // [rsp+34h] [rbp-CCh]
  _BYTE v8[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v9[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v10[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v11[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v12[32]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v13[32]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v14[5]; // [rsp+F8h] [rbp-8h] BYREF
  OLECHAR sz[40]; // [rsp+120h] [rbp+20h] BYREF

  v2 = 0;
  rguid = 0;
  if ( (*(int (__fastcall **)(struct IHNetConnection *, GUID **))(*(_QWORD *)a2 + 32LL))(a2, &rguid) >= 0 )
  {
    memset_0(sz, 0, 0x4Eu);
    StringFromGUID2(rguid, sz, 39);
    v5 = 0;
    v6 = 0;
    v7 = 0;
    std::wstring::wstring((__int64)v8);
    std::wstring::wstring((__int64)v9);
    std::wstring::wstring((__int64)v10);
    std::wstring::wstring((__int64)v11);
    std::wstring::wstring((__int64)v12);
    std::wstring::wstring((__int64)v13);
    std::vector<CPConFoldPidl<ConFoldPidl_v3>>::vector<CPConFoldPidl<ConFoldPidl_v3>>(v14);
    CIPv4Transition::StartWinsock((CIPv4Transition *)&v5);
    CIPv4Transition::LoadAdapterByAdapterName((CIPv4Transition *)&v5, sz);
    v2 = v6;
    CoTaskMemFree(rguid);
    CIPv4Transition::~CIPv4Transition((CIPv4Transition *)&v5);
  }
  return v2;
}

```

## disassembly

```asm
0x18002ca9c  mov     [rsp-8+arg_0], rbx
0x18002caa1  push    rbp
0x18002caa2  lea     rbp, [rsp-80h]
0x18002caa7  sub     rsp, 180h
0x18002caae  mov     rax, cs:__security_cookie
0x18002cab5  xor     rax, rsp
0x18002cab8  mov     [rbp+80h+var_10], rax
0x18002cabc  mov     rcx, rdx
0x18002cabf  xor     ebx, ebx
0x18002cac1  mov     [rsp+180h+rguid], rbx
0x18002cac6  mov     rax, [rdx]
0x18002cac9  lea     rdx, [rsp+180h+rguid]
0x18002cace  mov     rax, [rax+20h]
0x18002cad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cad7  test    eax, eax
0x18002cad9  js      loc_18002CB8A
0x18002cadf  xor     edx, edx; Val
0x18002cae1  lea     r8d, [rbx+4Eh]; Size
0x18002cae5  lea     rcx, [rbp+80h+sz]; void *
0x18002cae9  call    memset_0
0x18002caee  lea     r8d, [rbx+27h]; cchMax
0x18002caf2  lea     rdx, [rbp+80h+sz]; lpsz
0x18002caf6  mov     rcx, [rsp+180h+rguid]; rguid
0x18002cafb  call    cs:__imp_StringFromGUID2
0x18002cb01  mov     [rsp+180h+var_150], bx
0x18002cb06  mov     [rsp+180h+var_14E], bl
0x18002cb0a  mov     [rsp+180h+var_14C], ebx
0x18002cb0e  lea     rcx, [rsp+180h+var_148]
0x18002cb13  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002cb18  nop
0x18002cb19  lea     rcx, [rsp+180h+var_128]
0x18002cb1e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002cb23  nop
0x18002cb24  lea     rcx, [rsp+180h+var_108]
0x18002cb29  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002cb2e  nop
0x18002cb2f  lea     rcx, [rbp+80h+var_E8]
0x18002cb33  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002cb38  nop
0x18002cb39  lea     rcx, [rbp+80h+var_C8]
0x18002cb3d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002cb42  nop
0x18002cb43  lea     rcx, [rbp+80h+var_A8]
0x18002cb47  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002cb4c  nop
0x18002cb4d  lea     rcx, [rbp+80h+var_88]
0x18002cb51  call    ??0?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@QEAA@XZ; std::vector<CPConFoldPidl<ConFoldPidl_v3>>::vector<CPConFoldPidl<ConFoldPidl_v3>>(void)
0x18002cb56  nop
0x18002cb57  lea     rcx, [rsp+180h+var_150]; this
0x18002cb5c  call    ?StartWinsock@CIPv4Transition@@QEAAXXZ; CIPv4Transition::StartWinsock(void)
0x18002cb61  lea     rdx, [rbp+80h+sz]; unsigned __int16 *
0x18002cb65  lea     rcx, [rsp+180h+var_150]; this
0x18002cb6a  call    ?LoadAdapterByAdapterName@CIPv4Transition@@QEAA_NQEAG@Z; CIPv4Transition::LoadAdapterByAdapterName(ushort * const)
0x18002cb6f  nop
0x18002cb70  movzx   ebx, [rsp+180h+var_14E]
0x18002cb75  mov     rcx, [rsp+180h+rguid]; pv
0x18002cb7a  call    cs:__imp_CoTaskMemFree
0x18002cb80  lea     rcx, [rsp+180h+var_150]; this
0x18002cb85  call    ??1CIPv4Transition@@QEAA@XZ; CIPv4Transition::~CIPv4Transition(void)
0x18002cb8a  mov     eax, ebx
0x18002cb8c  mov     rcx, [rbp+80h+var_10]
0x18002cb90  xor     rcx, rsp; StackCookie
0x18002cb93  call    __security_check_cookie
0x18002cb98  mov     rbx, [rsp+180h+arg_0]
0x18002cba0  add     rsp, 180h
0x18002cba7  pop     rbp
0x18002cba8  retn
```
