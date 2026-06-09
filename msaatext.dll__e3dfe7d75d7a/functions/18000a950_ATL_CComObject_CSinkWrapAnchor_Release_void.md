# ATL::CComObject<CSinkWrapAnchor>::Release(void)

- ea: `0x18000a950`
- end: `0x18000a9d3`
- name: `?Release@?$CComObject@VCSinkWrapAnchor@@@ATL@@UEAAKXZ`
- size: `131`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000a9e0`
- `0x18000a9f0`

## callees

- `0x180005894`
- `0x18000a950`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a9b9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a9b9`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CSinkWrapAnchor>::Release(_DWORD *a1)
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
        *(_QWORD *)a1 = &ATL::CComObject<CSinkWrapAnchor>::`vftable'{for `ITextStoreAnchorSink'};
        *((_QWORD *)a1 + 1) = &ATL::CComObject<CSinkWrapAnchor>::`vftable'{for `ITextStoreAnchorServices'};
        *((_QWORD *)a1 + 2) = &ATL::CComObject<CSinkWrapAnchor>::`vftable'{for `IServiceProvider'};
        _InterlockedDecrement(&dword_180024B28);
        CSinkWrapBase<DocTraitsAnchor>::~CSinkWrapBase<DocTraitsAnchor>();
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
0x18000a950  mov     [rsp+arg_0], rbx
0x18000a955  push    rdi
0x18000a956  sub     rsp, 20h
0x18000a95a  mov     edi, [rcx+18h]
0x18000a95d  mov     rbx, rcx
0x18000a960  cmp     edi, 7FFFFFFFh
0x18000a966  jnz     short loc_18000A96F
0x18000a968  mov     edi, 7FFFFFFEh
0x18000a96d  jmp     short loc_18000A9C6
0x18000a96f  sub     edi, 1
0x18000a972  mov     [rcx+18h], edi
0x18000a975  jnz     short loc_18000A9C6
0x18000a977  lock inc cs:dword_180024B28
0x18000a97e  test    rbx, rbx
0x18000a981  jz      short loc_18000A9BF
0x18000a983  lea     rax, ??_7?$CComObject@VCSinkWrapAnchor@@@ATL@@6BITextStoreAnchorSink@@@; const ATL::CComObject<CSinkWrapAnchor>::`vftable'{for `ITextStoreAnchorSink'}
0x18000a98a  mov     dword ptr [rcx+18h], 1
0x18000a991  mov     [rcx], rax
0x18000a994  lea     rax, ??_7?$CComObject@VCSinkWrapAnchor@@@ATL@@6BITextStoreAnchorServices@@@; const ATL::CComObject<CSinkWrapAnchor>::`vftable'{for `ITextStoreAnchorServices'}
0x18000a99b  mov     [rcx+8], rax
0x18000a99f  lea     rax, ??_7?$CComObject@VCSinkWrapAnchor@@@ATL@@6BIServiceProvider@@@; const ATL::CComObject<CSinkWrapAnchor>::`vftable'{for `IServiceProvider'}
0x18000a9a6  mov     [rcx+10h], rax
0x18000a9aa  lock dec cs:dword_180024B28
0x18000a9b1  call    ??1?$CSinkWrapBase@VDocTraitsAnchor@@@@QEAA@XZ; CSinkWrapBase<DocTraitsAnchor>::~CSinkWrapBase<DocTraitsAnchor>(void)
0x18000a9b6  mov     rcx, rbx
0x18000a9b9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a9bf  lock dec cs:dword_180024B28
0x18000a9c6  mov     rbx, [rsp+28h+arg_0]
0x18000a9cb  mov     eax, edi
0x18000a9cd  add     rsp, 20h
0x18000a9d1  pop     rdi
0x18000a9d2  retn
```
