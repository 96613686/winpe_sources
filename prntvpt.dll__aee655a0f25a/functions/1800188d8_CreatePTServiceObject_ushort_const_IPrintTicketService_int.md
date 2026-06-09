# CreatePTServiceObject(ushort const *,IPrintTicketService * *,int *)

- ea: `0x1800188d8`
- end: `0x1800189c0`
- name: `?CreatePTServiceObject@@YAJPEBGPEAPEAUIPrintTicketService@@PEAH@Z`
- size: `232`
- prototype: `HRESULT __fastcall(const unsigned __int16 *, LPVOID *ppv, int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019300`
- `0x1800194e0`

## callees

- `0x18000e574`
- `0x18000f53c`
- `0x1800188d8`
- `0x180018b04`
- `0x180018bbc`
- `0x180023010`

## import_xrefs

- `GDI32!GdiIsUMPDSandboxingEnabled` at `0x18001890a`
- `GDI32!GdiIsUMPDSandboxingEnabled` at `0x18001890a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800189ad`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800189ad`

## pseudocode

```c
HRESULT __fastcall CreatePTServiceObject(const unsigned __int16 *a1, LPVOID *ppv, int *a3)
{
  HRESULT result; // eax
  int v7; // ebx
  __int64 (__fastcall ***v8)(_QWORD, GUID *, LPVOID *); // rax
  __int64 (__fastcall ***v9)(_QWORD, GUID *, LPVOID *); // rsi
  struct ATL::CAtlModule *v10; // rcx
  int v11; // eax
  GUID *v12; // rcx

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  if ( (unsigned int)IsSandboxingRequired()
    && ((unsigned int)GdiIsUMPDSandboxingEnabled() || !IsIppOrMpsOrVpOrPrintToPdfPrinter(a1)) )
  {
    v7 = 0;
    v11 = IsClientAppContainer();
    v12 = &GUID_b86f86af_aa5d_47c2_ab44_17ab64f907b4;
    if ( !v11 )
      v12 = &GUID_ba7c0d29_81ca_4901_b450_634e20bb8c34;
    result = CoCreateInstance(v12, 0, 4u, &IID_IPrintTicketService, ppv);
  }
  else
  {
    v7 = 1;
    v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, LPVOID *))operator new(0x28u);
    v9 = v8;
    if ( v8 )
    {
      v10 = ATL::_pAtlModule;
      *((_DWORD *)v8 + 2) = 0;
      v8[3] = 0;
      *v8 = (__int64 (__fastcall **)(_QWORD, GUID *, LPVOID *))&ATL::CComObject<CPrintTicketLocalServer>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v10 + 8LL))(v10);
      result = (**v9)(v9, &IID_IPrintTicketService, ppv);
    }
    else
    {
      result = -2147024882;
    }
  }
  *a3 = v7;
  return result;
}

```

## disassembly

```asm
0x1800188d8  push    rbx
0x1800188da  push    rsi
0x1800188db  push    rdi
0x1800188dc  push    r14
0x1800188de  sub     rsp, 38h
0x1800188e2  mov     r14, r8
0x1800188e5  mov     rdi, rdx
0x1800188e8  mov     rbx, rcx
0x1800188eb  test    rdx, rdx
0x1800188ee  jnz     short loc_1800188FA
0x1800188f0  mov     eax, 80070057h
0x1800188f5  jmp     loc_1800189B6
0x1800188fa  mov     qword ptr [rdx], 0
0x180018901  call    ?IsSandboxingRequired@@YAHXZ; IsSandboxingRequired(void)
0x180018906  test    eax, eax
0x180018908  jz      short loc_180018920
0x18001890a  call    cs:__imp_GdiIsUMPDSandboxingEnabled
0x180018910  test    eax, eax
0x180018912  jnz     short loc_180018982
0x180018914  mov     rcx, rbx; unsigned __int16 *
0x180018917  call    ?IsIppOrMpsOrVpOrPrintToPdfPrinter@@YA_NPEBG@Z; IsIppOrMpsOrVpOrPrintToPdfPrinter(ushort const *)
0x18001891c  test    al, al
0x18001891e  jz      short loc_180018982
0x180018920  mov     ebx, 1
0x180018925  lea     ecx, [rbx+27h]; Size
0x180018928  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001892d  mov     rsi, rax
0x180018930  test    rax, rax
0x180018933  jz      short loc_18001897B
0x180018935  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001893c  mov     dword ptr [rax+8], 0
0x180018943  mov     qword ptr [rax+18h], 0
0x18001894b  lea     rax, ??_7?$CComObject@VCPrintTicketLocalServer@@@ATL@@6B@; const ATL::CComObject<CPrintTicketLocalServer>::`vftable'
0x180018952  mov     [rsi], rax
0x180018955  mov     rdx, [rcx]
0x180018958  mov     rax, [rdx+8]
0x18001895c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018961  mov     rax, [rsi]
0x180018964  lea     rdx, IID_IPrintTicketService
0x18001896b  mov     r8, rdi
0x18001896e  mov     rcx, rsi
0x180018971  mov     rax, [rax]
0x180018974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018979  jmp     short loc_1800189B3
0x18001897b  mov     eax, 8007000Eh
0x180018980  jmp     short loc_1800189B3
0x180018982  xor     ebx, ebx
0x180018984  call    ?IsClientAppContainer@@YAHXZ; IsClientAppContainer(void)
0x180018989  xor     edx, edx; pUnkOuter
0x18001898b  mov     [rsp+58h+ppv], rdi; ppv
0x180018990  lea     r9, IID_IPrintTicketService; riid
0x180018997  lea     r8d, [rbx+4]; dwClsContext
0x18001899b  lea     rcx, _GUID_b86f86af_aa5d_47c2_ab44_17ab64f907b4
0x1800189a2  test    eax, eax
0x1800189a4  jnz     short loc_1800189AD
0x1800189a6  lea     rcx, _GUID_ba7c0d29_81ca_4901_b450_634e20bb8c34; rclsid
0x1800189ad  call    cs:__imp_CoCreateInstance
0x1800189b3  mov     [r14], ebx
0x1800189b6  add     rsp, 38h
0x1800189ba  pop     r14
0x1800189bc  pop     rdi
0x1800189bd  pop     rsi
0x1800189be  pop     rbx
0x1800189bf  retn
```
