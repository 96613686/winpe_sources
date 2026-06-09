# CTimeEnumTypeList::~CTimeEnumTypeList(void)

- ea: `0x18004b12c`
- end: `0x18004b1da`
- name: `??1CTimeEnumTypeList@@EEAA@XZ`
- size: `174`
- prototype: `void __fastcall(CTimeEnumTypeList *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004b0f0`

## callees

- `0x18001c4fc`
- `0x18004b12c`
- `0x18004b1e0`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004b1c2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004b1c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b19e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b1ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b1b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b19e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b1ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b1b8`

## pseudocode

```c
void __fastcall CTimeEnumTypeList::~CTimeEnumTypeList(CTimeEnumTypeList *this)
{
  __int64 v2; // rcx
  __int64 i; // rdi

  *(_QWORD *)this = &CTimeEnumTypeList::`vftable';
  SafeRelease<IShellFolder2>((char *)this + 88);
  v2 = *((_QWORD *)this + 12);
  *((_QWORD *)this + 12) = 0;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  if ( *((_QWORD *)this + 17) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 32); i = (unsigned int)(i + 1) )
      SafeRelease<IShellFolder2>(*((_QWORD *)this + 17) + 8 * i);
    CoTaskMemFree(*((LPVOID *)this + 17));
  }
  CoTaskMemFree(*((LPVOID *)this + 18));
  CoTaskMemFree(*((LPVOID *)this + 19));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  CSchemaObject<IPropertyEnumTypeList,CTimeEnumTypeList,TIME_ENUM_TYPE_DATA>::~CSchemaObject<IPropertyEnumTypeList,CTimeEnumTypeList,TIME_ENUM_TYPE_DATA>(this);
}

```

## disassembly

```asm
0x18004b12c  mov     [rsp+arg_0], rbx
0x18004b131  push    rdi
0x18004b132  sub     rsp, 20h
0x18004b136  mov     rbx, rcx
0x18004b139  lea     rax, ??_7CTimeEnumTypeList@@6B@; const CTimeEnumTypeList::`vftable'
0x18004b140  mov     [rcx], rax
0x18004b143  add     rcx, 58h ; 'X'
0x18004b147  call    ??$SafeRelease@UIShellFolder2@@@@YAXPEAPEAUIShellFolder2@@@Z; SafeRelease<IShellFolder2>(IShellFolder2 * *)
0x18004b14c  mov     rcx, [rbx+60h]
0x18004b150  mov     qword ptr [rbx+60h], 0
0x18004b158  test    rcx, rcx
0x18004b15b  jz      short loc_18004B169
0x18004b15d  mov     rax, [rcx]
0x18004b160  mov     rax, [rax+10h]
0x18004b164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b169  cmp     qword ptr [rbx+88h], 0
0x18004b171  jz      short loc_18004B1A4
0x18004b173  xor     edi, edi
0x18004b175  cmp     [rbx+80h], edi
0x18004b17b  jbe     short loc_18004B197
0x18004b17d  mov     rax, [rbx+88h]
0x18004b184  lea     rcx, [rax+rdi*8]
0x18004b188  call    ??$SafeRelease@UIShellFolder2@@@@YAXPEAPEAUIShellFolder2@@@Z; SafeRelease<IShellFolder2>(IShellFolder2 * *)
0x18004b18d  inc     edi
0x18004b18f  cmp     edi, [rbx+80h]
0x18004b195  jb      short loc_18004B17D
0x18004b197  mov     rcx, [rbx+88h]; pv
0x18004b19e  call    cs:__imp_CoTaskMemFree
0x18004b1a4  mov     rcx, [rbx+90h]; pv
0x18004b1ab  call    cs:__imp_CoTaskMemFree
0x18004b1b1  mov     rcx, [rbx+98h]; pv
0x18004b1b8  call    cs:__imp_CoTaskMemFree
0x18004b1be  lea     rcx, [rbx+18h]; lpCriticalSection
0x18004b1c2  call    cs:__imp_DeleteCriticalSection
0x18004b1c8  mov     rcx, rbx
0x18004b1cb  mov     rbx, [rsp+28h+arg_0]
0x18004b1d0  add     rsp, 20h
0x18004b1d4  pop     rdi
0x18004b1d5  jmp     ??1?$CSchemaObject@UIPropertyEnumTypeList@@VCTimeEnumTypeList@@UTIME_ENUM_TYPE_DATA@@@@MEAA@XZ; CSchemaObject<IPropertyEnumTypeList,CTimeEnumTypeList,TIME_ENUM_TYPE_DATA>::~CSchemaObject<IPropertyEnumTypeList,CTimeEnumTypeList,TIME_ENUM_TYPE_DATA>(void)
```
