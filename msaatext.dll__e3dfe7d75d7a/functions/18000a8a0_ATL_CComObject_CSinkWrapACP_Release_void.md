# ATL::CComObject<CSinkWrapACP>::Release(void)

- ea: `0x18000a8a0`
- end: `0x18000a923`
- name: `?Release@?$CComObject@VCSinkWrapACP@@@ATL@@UEAAKXZ`
- size: `131`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000a930`
- `0x18000a940`

## callees

- `0x1800057e4`
- `0x18000a8a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a909`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a909`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CSinkWrapACP>::Release(_DWORD *a1)
{
  int v1; // edi
  unsigned int v3; // edi

  v1 = a1[6];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[6] = v3;
    if ( !v3 )
    {
      _InterlockedIncrement(&dword_180024B28);
      if ( a1 )
      {
        a1[6] = 1;
        *(_QWORD *)a1 = &ATL::CComObject<CSinkWrapACP>::`vftable'{for `ITextStoreACPSink'};
        *((_QWORD *)a1 + 1) = &ATL::CComObject<CSinkWrapACP>::`vftable'{for `ITextStoreACPServices'};
        *((_QWORD *)a1 + 2) = &ATL::CComObject<CSinkWrapACP>::`vftable'{for `IServiceProvider'};
        _InterlockedDecrement(&dword_180024B28);
        CSinkWrapBase<DocTraitsACP>::~CSinkWrapBase<DocTraitsACP>();
        operator delete(a1);
      }
      _InterlockedDecrement(&dword_180024B28);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000a8a0  mov     [rsp+arg_0], rbx
0x18000a8a5  push    rdi
0x18000a8a6  sub     rsp, 20h
0x18000a8aa  mov     edi, [rcx+18h]
0x18000a8ad  mov     rbx, rcx
0x18000a8b0  cmp     edi, 7FFFFFFFh
0x18000a8b6  jnz     short loc_18000A8BF
0x18000a8b8  mov     edi, 7FFFFFFEh
0x18000a8bd  jmp     short loc_18000A916
0x18000a8bf  sub     edi, 1
0x18000a8c2  mov     [rcx+18h], edi
0x18000a8c5  jnz     short loc_18000A916
0x18000a8c7  lock inc cs:dword_180024B28
0x18000a8ce  test    rbx, rbx
0x18000a8d1  jz      short loc_18000A90F
0x18000a8d3  lea     rax, ??_7?$CComObject@VCSinkWrapACP@@@ATL@@6BITextStoreACPSink@@@; const ATL::CComObject<CSinkWrapACP>::`vftable'{for `ITextStoreACPSink'}
0x18000a8da  mov     dword ptr [rcx+18h], 1
0x18000a8e1  mov     [rcx], rax
0x18000a8e4  lea     rax, ??_7?$CComObject@VCSinkWrapACP@@@ATL@@6BITextStoreACPServices@@@; const ATL::CComObject<CSinkWrapACP>::`vftable'{for `ITextStoreACPServices'}
0x18000a8eb  mov     [rcx+8], rax
0x18000a8ef  lea     rax, ??_7?$CComObject@VCSinkWrapACP@@@ATL@@6BIServiceProvider@@@; const ATL::CComObject<CSinkWrapACP>::`vftable'{for `IServiceProvider'}
0x18000a8f6  mov     [rcx+10h], rax
0x18000a8fa  lock dec cs:dword_180024B28
0x18000a901  call    ??1?$CSinkWrapBase@VDocTraitsACP@@@@QEAA@XZ; CSinkWrapBase<DocTraitsACP>::~CSinkWrapBase<DocTraitsACP>(void)
0x18000a906  mov     rcx, rbx
0x18000a909  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a90f  lock dec cs:dword_180024B28
0x18000a916  mov     rbx, [rsp+28h+arg_0]
0x18000a91b  mov     eax, edi
0x18000a91d  add     rsp, 20h
0x18000a921  pop     rdi
0x18000a922  retn
```
