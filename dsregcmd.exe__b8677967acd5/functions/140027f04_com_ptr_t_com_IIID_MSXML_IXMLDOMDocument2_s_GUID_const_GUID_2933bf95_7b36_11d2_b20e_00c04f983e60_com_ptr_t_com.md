# _com_ptr_t<_com_IIID<MSXML::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::_com_ptr_t<_com_IIID<MSXML::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>(_GUID const &,IUnknown *,ulong)

- ea: `0x140027f04`
- end: `0x140027fdd`
- name: `??0?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEAA@AEBU_GUID@@PEAUIUnknown@@K@Z`
- size: `217`
- prototype: `LPVOID *__fastcall(LPVOID *ppv, IID *rclsid, IUnknown *, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140028040`

## callees

- `0x140027f04`
- `0x14002c070`
- `0x140030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140027f45`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140027fa0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140027f45`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140027fa0`
- `OLE32!OleRun` at `0x140027f56`
- `OLE32!OleRun` at `0x140027f56`

## pseudocode

```c
// Hidden C++ exception states: #wind=57
LPVOID *__fastcall _com_ptr_t<_com_IIID<MSXML::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::_com_ptr_t<_com_IIID<MSXML::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>(
        LPVOID *ppv,
        IID *rclsid,
        IUnknown *a3,
        char a4)
{
  HRESULT Instance; // ebx
  LPUNKNOWN pUnknown; // [rsp+50h] [rbp+18h] BYREF

  pUnknown = a3;
  *ppv = 0;
  if ( (a4 & 0x14) != 0 )
  {
    pUnknown = 0;
    Instance = CoCreateInstance(rclsid, 0, a4, &GUID_00000000_0000_0000_c000_000000000046, (LPVOID *)&pUnknown);
    if ( Instance < 0 )
    {
LABEL_8:
      *ppv = 0;
      goto LABEL_9;
    }
    Instance = OleRun(pUnknown);
    if ( Instance >= 0 )
      Instance = ((__int64 (__fastcall *)(LPUNKNOWN, GUID *, LPVOID *))pUnknown->lpVtbl->QueryInterface)(
                   pUnknown,
                   &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                   ppv);
    ((void (__fastcall *)(LPUNKNOWN))pUnknown->lpVtbl->Release)(pUnknown);
  }
  else
  {
    Instance = CoCreateInstance(rclsid, 0, a4, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, ppv);
  }
  if ( Instance < 0 )
    goto LABEL_8;
LABEL_9:
  if ( (int)(Instance + 0x80000000) >= 0 && Instance != -2147467262 )
    _com_issue_error(Instance);
  return ppv;
}

```

## disassembly

```asm
0x140027f04  mov     r11, rsp
0x140027f07  mov     [r11+8], rbx
0x140027f0b  mov     [r11+18h], r8
0x140027f0f  push    rdi
0x140027f10  sub     rsp, 30h
0x140027f14  mov     eax, r9d
0x140027f17  mov     r10, rdx
0x140027f1a  mov     rdi, rcx
0x140027f1d  mov     qword ptr [rcx], 0
0x140027f24  mov     r8d, eax; dwClsContext
0x140027f27  xor     edx, edx; pUnkOuter
0x140027f29  test    r9b, 14h
0x140027f2d  jz      short loc_140027F91
0x140027f2f  mov     [r11+18h], rdx
0x140027f33  lea     rcx, [r11+18h]
0x140027f37  mov     [r11-18h], rcx
0x140027f3b  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x140027f42  mov     rcx, r10; rclsid
0x140027f45  call    cs:__imp_CoCreateInstance
0x140027f4b  mov     ebx, eax
0x140027f4d  test    eax, eax
0x140027f4f  js      short loc_140027FAC
0x140027f51  mov     rcx, [rsp+38h+pUnknown]; pUnknown
0x140027f56  call    cs:__imp_OleRun
0x140027f5c  mov     ebx, eax
0x140027f5e  test    eax, eax
0x140027f60  js      short loc_140027F7E
0x140027f62  mov     rcx, [rsp+38h+pUnknown]
0x140027f67  mov     rax, [rcx]
0x140027f6a  mov     r8, rdi
0x140027f6d  lea     rdx, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x140027f74  mov     rax, [rax]
0x140027f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027f7c  mov     ebx, eax
0x140027f7e  mov     rcx, [rsp+38h+pUnknown]
0x140027f83  mov     rax, [rcx]
0x140027f86  mov     rax, [rax+10h]
0x140027f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027f8f  jmp     short loc_140027FA8
0x140027f91  mov     [rsp+38h+ppv], rdi; ppv
0x140027f96  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x140027f9d  mov     rcx, r10; rclsid
0x140027fa0  call    cs:__imp_CoCreateInstance
0x140027fa6  mov     ebx, eax
0x140027fa8  test    ebx, ebx
0x140027faa  jns     short loc_140027FB3
0x140027fac  mov     qword ptr [rdi], 0
0x140027fb3  mov     ecx, 80000000h
0x140027fb8  lea     eax, [rbx+rcx]
0x140027fbb  test    ecx, eax
0x140027fbd  jnz     short loc_140027FC7
0x140027fbf  cmp     ebx, 80004002h
0x140027fc5  jnz     short loc_140027FD5
0x140027fc7  mov     rax, rdi
0x140027fca  mov     rbx, [rsp+38h+arg_0]
0x140027fcf  add     rsp, 30h
0x140027fd3  pop     rdi
0x140027fd4  retn
0x140027fd5  mov     ecx, ebx; int
0x140027fd7  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
