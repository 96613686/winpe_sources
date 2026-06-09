# CMFFLACPropertyHandler::AddPropertyToMetadataHandler(CMFProperty *)

- ea: `0x18002a85c`
- end: `0x18002a953`
- name: `?AddPropertyToMetadataHandler@CMFFLACPropertyHandler@@AEAAJPEAVCMFProperty@@@Z`
- size: `247`
- prototype: `__int64 __fastcall(CMFFLACPropertyHandler *__hidden this, struct CMFProperty *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002c990`

## callees

- `0x180020398`
- `0x180020484`
- `0x18002a85c`
- `0x180032ab0`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a93b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a93b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a92b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a92b`

## pseudocode

```c
__int64 __fastcall CMFFLACPropertyHandler::AddPropertyToMetadataHandler(
        CMFFLACPropertyHandler *this,
        struct CMFProperty *a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  struct tagPROPVARIANT *v6; // rsi
  __int64 (__fastcall *v7)(struct CMFProperty *, __int64 *, LPVOID *, int *); // rax
  int v8; // ebx
  __int64 v9; // rdx
  PROPVARIANT pvar; // [rsp+30h] [rbp-28h] BYREF
  int v12; // [rsp+68h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+18h] BYREF

  v4 = (*(__int64 (__fastcall **)(struct CMFProperty *))(*(_QWORD *)a2 + 304LL))(a2);
  v5 = *(_QWORD *)a2;
  v6 = (struct tagPROPVARIANT *)v4;
  pv = 0;
  v12 = 0;
  v7 = *(__int64 (__fastcall **)(struct CMFProperty *, __int64 *, LPVOID *, int *))(v5 + 104);
  memset(&pvar, 0, sizeof(pvar));
  v8 = v7(a2, MF_MD_NAME, &pv, &v12);
  if ( v8 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_9;
    v9 = 42;
    goto LABEL_4;
  }
  v8 = CFLACMetadataWriter::SetProperty(
         (CMFFLACPropertyHandler *)((char *)this + 1984),
         (const unsigned __int16 *)pv,
         v6);
  if ( v8 >= 0 )
  {
    *((_DWORD *)this + 530) = 1;
  }
  else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v9 = 43;
LABEL_4:
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_36e4e3a47ce73e52b63ec011625d5c06_Traceguids, this, v8);
  }
LABEL_9:
  PropVariantClear(&pvar);
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002a85c  mov     [rsp+arg_0], rbx
0x18002a861  mov     [rsp+arg_18], rsi
0x18002a866  push    rdi
0x18002a867  sub     rsp, 50h
0x18002a86b  mov     rax, [rdx]
0x18002a86e  mov     rdi, rcx
0x18002a871  mov     rcx, rdx
0x18002a874  mov     rbx, rdx
0x18002a877  mov     rax, [rax+130h]
0x18002a87e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a883  mov     rcx, [rbx]
0x18002a886  lea     r9, [rsp+58h+arg_8]
0x18002a88b  mov     rsi, rax
0x18002a88e  lea     r8, [rsp+58h+pv]
0x18002a893  xor     eax, eax
0x18002a895  lea     rdx, MF_MD_NAME
0x18002a89c  mov     qword ptr [rsp+58h+pvar+10h], rax
0x18002a8a1  xorps   xmm0, xmm0
0x18002a8a4  mov     [rsp+58h+pv], rax
0x18002a8a9  mov     [rsp+58h+arg_8], eax
0x18002a8ad  mov     rax, [rcx+68h]
0x18002a8b1  mov     rcx, rbx
0x18002a8b4  movups  xmmword ptr [rsp+58h+pvar], xmm0
0x18002a8b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a8be  mov     ebx, eax
0x18002a8c0  test    eax, eax
0x18002a8c2  jns     short loc_18002A8F2
0x18002a8c4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002a8c9  cmp     al, 1
0x18002a8cb  jb      short loc_18002A926
0x18002a8cd  mov     edx, 2Ah ; '*'
0x18002a8d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a8d9  lea     r8, WPP_36e4e3a47ce73e52b63ec011625d5c06_Traceguids
0x18002a8e0  mov     r9, rdi
0x18002a8e3  mov     [rsp+58h+var_38], ebx
0x18002a8e7  mov     rcx, [rcx+10h]
0x18002a8eb  call    WPP_SF_qd
0x18002a8f0  jmp     short loc_18002A926
0x18002a8f2  mov     rdx, [rsp+58h+pv]; unsigned __int16 *
0x18002a8f7  lea     rcx, [rdi+7C0h]; this
0x18002a8fe  mov     r8, rsi; struct tagPROPVARIANT *
0x18002a901  call    ?SetProperty@CFLACMetadataWriter@@UEAAJPEBGPEBUtagPROPVARIANT@@@Z; CFLACMetadataWriter::SetProperty(ushort const *,tagPROPVARIANT const *)
0x18002a906  mov     ebx, eax
0x18002a908  test    eax, eax
0x18002a90a  jns     short loc_18002A91C
0x18002a90c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002a911  cmp     al, 1
0x18002a913  jb      short loc_18002A926
0x18002a915  mov     edx, 2Bh ; '+'
0x18002a91a  jmp     short loc_18002A8D2
0x18002a91c  mov     dword ptr [rdi+848h], 1
0x18002a926  lea     rcx, [rsp+58h+pvar]; pvar
0x18002a92b  call    cs:__imp_PropVariantClear
0x18002a931  mov     rcx, [rsp+58h+pv]; pv
0x18002a936  test    rcx, rcx
0x18002a939  jz      short loc_18002A941
0x18002a93b  call    cs:__imp_CoTaskMemFree
0x18002a941  mov     rsi, [rsp+58h+arg_18]
0x18002a946  mov     eax, ebx
0x18002a948  mov     rbx, [rsp+58h+arg_0]
0x18002a94d  add     rsp, 50h
0x18002a951  pop     rdi
0x18002a952  retn
```
