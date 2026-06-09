# CMarshaledInterface::CMarshalStream::~CMarshalStream(void)

- ea: `0x1800070cc`
- end: `0x180007167`
- name: `??1CMarshalStream@CMarshaledInterface@@UEAA@XZ`
- size: `155`
- prototype: `void __fastcall(CMarshaledInterface::CMarshalStream *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007370`

## callees

- `0x180005904`
- `0x1800070cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800070ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800070ed`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180007134`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180007134`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800070fb`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800070fb`

## pseudocode

```c
void __fastcall CMarshaledInterface::CMarshalStream::~CMarshalStream(CMarshaledInterface::CMarshalStream *this)
{
  LPSTREAM *v1; // rbx
  bool v3; // zf
  IStream *v4; // rcx
  LPVOID ppv; // [rsp+30h] [rbp+8h] BYREF

  v1 = (LPSTREAM *)((char *)this + 16);
  v3 = *((_QWORD *)this + 2) == 0;
  *(_QWORD *)this = &CMarshaledInterface::CMarshalStream::`vftable';
  if ( !v3 )
  {
    if ( *((_DWORD *)this + 10) == GetCurrentThreadId() )
    {
      CoReleaseMarshalData(*v1);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v1);
    }
    else
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
      v4 = *v1;
      *v1 = 0;
      CoGetInterfaceAndReleaseStream(v4, &GUID_00000000_0000_0000_c000_000000000046, &ppv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 32);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v1);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x1800070cc  mov     [rsp+arg_8], rbx
0x1800070d1  push    rdi
0x1800070d2  sub     rsp, 20h
0x1800070d6  lea     rbx, [rcx+10h]
0x1800070da  mov     rdi, rcx
0x1800070dd  cmp     qword ptr [rbx], 0
0x1800070e1  lea     rax, ??_7CMarshalStream@CMarshaledInterface@@6B@; const CMarshaledInterface::CMarshalStream::`vftable'
0x1800070e8  mov     [rcx], rax
0x1800070eb  jz      short loc_180007144
0x1800070ed  call    cs:__imp_GetCurrentThreadId
0x1800070f3  cmp     [rdi+28h], eax
0x1800070f6  jnz     short loc_18000710B
0x1800070f8  mov     rcx, [rbx]; pStm
0x1800070fb  call    cs:__imp_CoReleaseMarshalData
0x180007101  mov     rcx, rbx
0x180007104  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007109  jmp     short loc_180007144
0x18000710b  lea     rcx, [rsp+28h+ppv]
0x180007110  mov     [rsp+28h+ppv], 0
0x180007119  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000711e  mov     rcx, [rbx]; pStm
0x180007121  lea     r8, [rsp+28h+ppv]; ppv
0x180007126  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; iid
0x18000712d  mov     qword ptr [rbx], 0
0x180007134  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x18000713a  lea     rcx, [rsp+28h+ppv]
0x18000713f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007144  lea     rcx, [rdi+20h]
0x180007148  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000714d  mov     rcx, rbx
0x180007150  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007155  mov     rbx, [rsp+28h+arg_8]
0x18000715a  mov     dword ptr [rdi+0Ch], 0C0000001h
0x180007161  add     rsp, 20h
0x180007165  pop     rdi
0x180007166  retn
```
