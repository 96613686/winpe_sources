# CMarshaledInterface::CMarshalStream::~CMarshalStream(void)

- ea: `0x1400028f0`
- end: `0x1400029bb`
- name: `??1CMarshalStream@CMarshaledInterface@@UEAA@XZ`
- size: `203`
- prototype: `void __fastcall(CMarshaledInterface::CMarshalStream *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002ad0`

## callees

- `0x1400028f0`
- `0x140006010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000290a`
- `KERNEL32!GetCurrentThreadId` at `0x14000290a`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x140002919`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x140002919`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x14000294f`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x14000294f`

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
0x1400028f0  push    rbx
0x1400028f2  sub     rsp, 20h
0x1400028f6  cmp     qword ptr [rcx+10h], 0
0x1400028fb  lea     rax, ??_7CMarshalStream@CMarshaledInterface@@6B@; const CMarshaledInterface::CMarshalStream::`vftable'
0x140002902  mov     [rcx], rax
0x140002905  mov     rbx, rcx
0x140002908  jz      short loc_140002974
0x14000290a  call    cs:__imp_GetCurrentThreadId
0x140002910  mov     rcx, [rbx+10h]; pStm
0x140002914  cmp     [rbx+28h], eax
0x140002917  jnz     short loc_140002932
0x140002919  call    cs:__imp_CoReleaseMarshalData
0x14000291f  mov     rcx, [rbx+10h]
0x140002923  test    rcx, rcx
0x140002926  jz      short loc_140002974
0x140002928  mov     qword ptr [rbx+10h], 0
0x140002930  jmp     short loc_140002968
0x140002932  lea     r8, [rsp+28h+ppv]; ppv
0x140002937  mov     [rsp+28h+ppv], 0
0x140002940  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; iid
0x140002947  mov     qword ptr [rbx+10h], 0
0x14000294f  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x140002955  mov     rcx, [rsp+28h+ppv]
0x14000295a  test    rcx, rcx
0x14000295d  jz      short loc_140002974
0x14000295f  mov     [rsp+28h+ppv], 0
0x140002968  mov     rax, [rcx]
0x14000296b  mov     rax, [rax+10h]
0x14000296f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002974  mov     rcx, [rbx+20h]
0x140002978  test    rcx, rcx
0x14000297b  jz      short loc_140002991
0x14000297d  mov     qword ptr [rbx+20h], 0
0x140002985  mov     rax, [rcx]
0x140002988  mov     rax, [rax+10h]
0x14000298c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002991  mov     rcx, [rbx+10h]
0x140002995  test    rcx, rcx
0x140002998  jz      short loc_1400029AE
0x14000299a  mov     qword ptr [rbx+10h], 0
0x1400029a2  mov     rax, [rcx]
0x1400029a5  mov     rax, [rax+10h]
0x1400029a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400029ae  mov     dword ptr [rbx+0Ch], 0C0000001h
0x1400029b5  add     rsp, 20h
0x1400029b9  pop     rbx
0x1400029ba  retn
```
