# CAdvancedSettingsWriter::QueryInterface(_GUID const &,void * *)

- ea: `0x180013210`
- end: `0x180013296`
- name: `?QueryInterface@CAdvancedSettingsWriter@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `134`
- prototype: `__int64 __fastcall(LPUNKNOWN punkOuter, IID *riid, void **ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180013210`
- `0x18001a010`

## import_xrefs

- `SHLWAPI!__imp_QISearch` at `0x180013231`
- `SHLWAPI!__imp_QISearch` at `0x180013231`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180013268`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180013268`

## pseudocode

```c
__int64 __fastcall CAdvancedSettingsWriter::QueryInterface(LPUNKNOWN punkOuter, IID *riid, void **ppv)
{
  HRESULT v6; // ebp
  __int64 v7; // r8
  LPUNKNOWN v8; // rbx

  v6 = QISearch(punkOuter, &stru_18001C5C0, riid, ppv);
  if ( v6 < 0 )
  {
    v7 = *(_QWORD *)&IID_IMarshal.Data1 - *(_QWORD *)&riid->Data1;
    if ( *(_QWORD *)&IID_IMarshal.Data1 == *(_QWORD *)&riid->Data1 )
      v7 = *(_QWORD *)IID_IMarshal.Data4 - *(_QWORD *)riid->Data4;
    if ( !v7 )
    {
      v8 = punkOuter + 2;
      if ( !punkOuter[2].lpVtbl )
        CoCreateFreeThreadedMarshaler(punkOuter, (LPUNKNOWN *)&punkOuter[2]);
      if ( v8->lpVtbl )
        return (*(unsigned int (__fastcall **)(struct IUnknownVtbl *, IID *, void **))v8->lpVtbl->QueryInterface)(
                 v8->lpVtbl,
                 riid,
                 ppv);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180013210  push    rbx
0x180013212  push    rbp
0x180013213  push    rsi
0x180013214  push    rdi
0x180013215  push    r14
0x180013217  sub     rsp, 20h
0x18001321b  mov     r14, r8
0x18001321e  mov     r9, r8; ppv
0x180013221  mov     r8, rdx; riid
0x180013224  mov     rdi, rdx
0x180013227  lea     rdx, stru_18001C5C0; pqit
0x18001322e  mov     rsi, rcx
0x180013231  call    cs:__imp_QISearch
0x180013237  mov     ebp, eax
0x180013239  test    eax, eax
0x18001323b  jns     short loc_180013289
0x18001323d  mov     r8, qword ptr cs:IID_IMarshal.Data1
0x180013244  sub     r8, [rdi]
0x180013247  jnz     short loc_180013254
0x180013249  mov     r8, qword ptr cs:IID_IMarshal.Data4
0x180013250  sub     r8, [rdi+8]
0x180013254  test    r8, r8
0x180013257  jnz     short loc_180013289
0x180013259  lea     rbx, [rsi+10h]
0x18001325d  cmp     [rbx], r8
0x180013260  jnz     short loc_18001326E
0x180013262  mov     rdx, rbx; ppunkMarshal
0x180013265  mov     rcx, rsi; punkOuter
0x180013268  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18001326e  mov     rcx, [rbx]
0x180013271  test    rcx, rcx
0x180013274  jz      short loc_180013289
0x180013276  mov     rax, [rcx]
0x180013279  mov     r8, r14
0x18001327c  mov     rdx, rdi
0x18001327f  mov     rax, [rax]
0x180013282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013287  mov     ebp, eax
0x180013289  mov     eax, ebp
0x18001328b  add     rsp, 20h
0x18001328f  pop     r14
0x180013291  pop     rdi
0x180013292  pop     rsi
0x180013293  pop     rbp
0x180013294  pop     rbx
0x180013295  retn
```
