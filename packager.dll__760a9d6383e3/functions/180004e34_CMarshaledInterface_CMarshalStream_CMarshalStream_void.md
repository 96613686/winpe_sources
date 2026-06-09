# CMarshaledInterface::CMarshalStream::~CMarshalStream(void)

- ea: `0x180004e34`
- end: `0x180004eff`
- name: `??1CMarshalStream@CMarshaledInterface@@UEAA@XZ`
- size: `203`
- prototype: `void __fastcall(CMarshaledInterface::CMarshalStream *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004f40`

## callees

- `0x180004e34`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e4e`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180004e93`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180004e93`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180004e5d`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180004e5d`

## pseudocode

```c
void __fastcall CMarshaledInterface::CMarshalStream::~CMarshalStream(CMarshaledInterface::CMarshalStream *this)
{
  bool v1; // zf
  DWORD CurrentThreadId; // eax
  IStream *v4; // rcx
  LPVOID v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  LPVOID ppv; // [rsp+30h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 2) == 0;
  *(_QWORD *)this = &CMarshaledInterface::CMarshalStream::`vftable';
  if ( !v1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = (IStream *)*((_QWORD *)this + 2);
    if ( *((_DWORD *)this + 10) == CurrentThreadId )
    {
      CoReleaseMarshalData(v4);
      v5 = (LPVOID)*((_QWORD *)this + 2);
      if ( !v5 )
        goto LABEL_8;
      *((_QWORD *)this + 2) = 0;
    }
    else
    {
      ppv = 0;
      *((_QWORD *)this + 2) = 0;
      CoGetInterfaceAndReleaseStream(v4, &GUID_00000000_0000_0000_c000_000000000046, &ppv);
      v5 = ppv;
      if ( !ppv )
        goto LABEL_8;
      ppv = 0;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
  }
LABEL_8:
  v6 = *((_QWORD *)this + 4);
  if ( v6 )
  {
    *((_QWORD *)this + 4) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  v7 = *((_QWORD *)this + 2);
  if ( v7 )
  {
    *((_QWORD *)this + 2) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x180004e34  push    rbx
0x180004e36  sub     rsp, 20h
0x180004e3a  cmp     qword ptr [rcx+10h], 0
0x180004e3f  lea     rax, ??_7CMarshalStream@CMarshaledInterface@@6B@; const CMarshaledInterface::CMarshalStream::`vftable'
0x180004e46  mov     [rcx], rax
0x180004e49  mov     rbx, rcx
0x180004e4c  jz      short loc_180004EB8
0x180004e4e  call    cs:__imp_GetCurrentThreadId
0x180004e54  mov     rcx, [rbx+10h]; pStm
0x180004e58  cmp     [rbx+28h], eax
0x180004e5b  jnz     short loc_180004E76
0x180004e5d  call    cs:__imp_CoReleaseMarshalData
0x180004e63  mov     rcx, [rbx+10h]
0x180004e67  test    rcx, rcx
0x180004e6a  jz      short loc_180004EB8
0x180004e6c  mov     qword ptr [rbx+10h], 0
0x180004e74  jmp     short loc_180004EAC
0x180004e76  lea     r8, [rsp+28h+ppv]; ppv
0x180004e7b  mov     [rsp+28h+ppv], 0
0x180004e84  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; iid
0x180004e8b  mov     qword ptr [rbx+10h], 0
0x180004e93  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180004e99  mov     rcx, [rsp+28h+ppv]
0x180004e9e  test    rcx, rcx
0x180004ea1  jz      short loc_180004EB8
0x180004ea3  mov     [rsp+28h+ppv], 0
0x180004eac  mov     rax, [rcx]
0x180004eaf  mov     rax, [rax+10h]
0x180004eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eb8  mov     rcx, [rbx+20h]
0x180004ebc  test    rcx, rcx
0x180004ebf  jz      short loc_180004ED5
0x180004ec1  mov     qword ptr [rbx+20h], 0
0x180004ec9  mov     rax, [rcx]
0x180004ecc  mov     rax, [rax+10h]
0x180004ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ed5  mov     rcx, [rbx+10h]
0x180004ed9  test    rcx, rcx
0x180004edc  jz      short loc_180004EF2
0x180004ede  mov     qword ptr [rbx+10h], 0
0x180004ee6  mov     rax, [rcx]
0x180004ee9  mov     rax, [rax+10h]
0x180004eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ef2  mov     dword ptr [rbx+0Ch], 0C0000001h
0x180004ef9  add     rsp, 20h
0x180004efd  pop     rbx
0x180004efe  retn
```
