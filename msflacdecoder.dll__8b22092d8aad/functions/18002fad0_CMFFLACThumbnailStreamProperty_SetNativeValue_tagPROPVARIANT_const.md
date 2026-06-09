# CMFFLACThumbnailStreamProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x18002fad0`
- end: `0x18002fbcc`
- name: `?SetNativeValue@CMFFLACThumbnailStreamProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `252`
- prototype: `__int64 __fastcall(PROPVARIANT *this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180016e48`
- `0x18002fad0`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002fb27`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002fb27`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002fb3f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002fb3f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002fafc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002fb10`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002fafc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002fb10`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMFFLACThumbnailStreamProperty::SetNativeValue(PROPVARIANT *this, const struct tagPROPVARIANT *a2)
{
  HRESULT v4; // ebx
  LPSTREAM v5; // rax
  int v7; // [rsp+50h] [rbp+8h] BYREF
  LPSTREAM ppstm; // [rsp+58h] [rbp+10h] BYREF

  ppstm = 0;
  v7 = 0;
  PropVariantClear(this + 4);
  if ( a2->vt == 65 )
  {
    v4 = PropVariantClear(this + 5);
    if ( v4 >= 0 )
    {
      v4 = PropVariantCopy(this + 5, a2);
      if ( v4 >= 0 )
      {
        v4 = CreateStreamOnHGlobal(0, 1, &ppstm);
        if ( v4 >= 0 )
        {
          v4 = ((__int64 (__fastcall *)(LPSTREAM, BYTE *, _QWORD, int *))ppstm->lpVtbl->Write)(
                 ppstm,
                 a2->bstrblobVal.pData,
                 a2->ulVal,
                 &v7);
          if ( v4 >= 0 )
          {
            v4 = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, 0, 0, 0);
            if ( v4 >= 0 )
            {
              this[4].vt = 66;
              v5 = ppstm;
              ppstm = 0;
              this[4].hVal.QuadPart = (LONGLONG)v5;
            }
          }
        }
      }
    }
  }
  else
  {
    v4 = -2147418113;
  }
  ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&ppstm);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002fad0  mov     rax, rsp
0x18002fad3  mov     [rax+18h], rbx
0x18002fad7  mov     [rax+20h], rbp
0x18002fadb  push    rsi
0x18002fadc  push    rdi
0x18002fadd  push    r14
0x18002fadf  sub     rsp, 30h
0x18002fae3  mov     rsi, rdx
0x18002fae6  mov     rdi, rcx
0x18002fae9  mov     qword ptr [rax+10h], 0
0x18002faf1  mov     dword ptr [rax+8], 0
0x18002faf8  add     rcx, 60h ; '`'; pvar
0x18002fafc  call    cs:__imp_PropVariantClear
0x18002fb02  cmp     word ptr [rsi], 41h ; 'A'
0x18002fb06  jnz     loc_18002FBA8
0x18002fb0c  lea     rcx, [rdi+78h]; pvar
0x18002fb10  call    cs:__imp_PropVariantClear
0x18002fb16  mov     ebx, eax
0x18002fb18  test    eax, eax
0x18002fb1a  js      loc_18002FBAD
0x18002fb20  mov     rdx, rsi; pvarSrc
0x18002fb23  lea     rcx, [rdi+78h]; pvarDest
0x18002fb27  call    cs:__imp_PropVariantCopy
0x18002fb2d  mov     ebx, eax
0x18002fb2f  test    eax, eax
0x18002fb31  js      short loc_18002FBAD
0x18002fb33  lea     r8, [rsp+48h+ppstm]; ppstm
0x18002fb38  mov     edx, 1; fDeleteOnRelease
0x18002fb3d  xor     ecx, ecx; hGlobal
0x18002fb3f  call    cs:__imp_CreateStreamOnHGlobal
0x18002fb45  mov     ebx, eax
0x18002fb47  test    eax, eax
0x18002fb49  js      short loc_18002FBAD
0x18002fb4b  mov     rcx, [rsp+48h+ppstm]
0x18002fb50  mov     rax, [rcx]
0x18002fb53  lea     r9, [rsp+48h+arg_0]
0x18002fb58  mov     r8d, [rsi+8]
0x18002fb5c  mov     rdx, [rsi+10h]
0x18002fb60  mov     rax, [rax+20h]
0x18002fb64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb69  mov     ebx, eax
0x18002fb6b  test    eax, eax
0x18002fb6d  js      short loc_18002FBAD
0x18002fb6f  mov     rcx, [rsp+48h+ppstm]
0x18002fb74  xor     edx, edx
0x18002fb76  mov     rax, [rcx]
0x18002fb79  xor     r9d, r9d
0x18002fb7c  xor     r8d, r8d
0x18002fb7f  mov     rax, [rax+28h]
0x18002fb83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb88  mov     ebx, eax
0x18002fb8a  test    eax, eax
0x18002fb8c  js      short loc_18002FBAD
0x18002fb8e  mov     word ptr [rdi+60h], 42h ; 'B'
0x18002fb94  mov     rax, [rsp+48h+ppstm]
0x18002fb99  mov     [rsp+48h+ppstm], 0
0x18002fba2  mov     [rdi+68h], rax
0x18002fba6  jmp     short loc_18002FBAD
0x18002fba8  mov     ebx, 8000FFFFh
0x18002fbad  lea     rcx, [rsp+48h+ppstm]
0x18002fbb2  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x18002fbb7  mov     eax, ebx
0x18002fbb9  mov     rbx, [rsp+48h+arg_10]
0x18002fbbe  mov     rbp, [rsp+48h+arg_18]
0x18002fbc3  add     rsp, 30h
0x18002fbc7  pop     r14
0x18002fbc9  pop     rdi
0x18002fbca  pop     rsi
0x18002fbcb  retn
```
