# DataObj_GetFilePropertyStore(IDataObject *,long,IPersistSerializedPropStorage *)

- ea: `0x1800164f0`
- end: `0x180016769`
- name: `?DataObj_GetFilePropertyStore@@YAJPEAUIDataObject@@JPEAUIPersistSerializedPropStorage@@@Z`
- size: `633`
- prototype: `__int64 __fastcall(struct IDataObject *, int, struct IPersistSerializedPropStorage *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180048de4`
- `0x18004f1c4`

## callees

- `0x1800164f0`
- `0x180019dc0`
- `0x18001d1dc`
- `0x1800214cc`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800166c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001671c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016747`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800166c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001671c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016747`
- `KERNEL32!GlobalSize` at `0x180016641`
- `KERNEL32!GlobalSize` at `0x180016641`
- `KERNEL32!GlobalLock` at `0x18001662a`
- `KERNEL32!GlobalLock` at `0x18001662a`
- `KERNEL32!GlobalUnlock` at `0x18001665e`
- `KERNEL32!GlobalUnlock` at `0x18001665e`
- `ole32!ReleaseStgMedium` at `0x180016669`
- `ole32!ReleaseStgMedium` at `0x18001675e`
- `ole32!ReleaseStgMedium` at `0x180016669`
- `ole32!ReleaseStgMedium` at `0x18001675e`
- `USER32!RegisterClipboardFormatW` at `0x180016596`
- `USER32!RegisterClipboardFormatW` at `0x1800165a3`
- `USER32!RegisterClipboardFormatW` at `0x1800165b0`
- `USER32!RegisterClipboardFormatW` at `0x1800165bd`
- `USER32!RegisterClipboardFormatW` at `0x1800165ca`
- `USER32!RegisterClipboardFormatW` at `0x1800165de`
- `USER32!RegisterClipboardFormatW` at `0x1800165eb`
- `USER32!RegisterClipboardFormatW` at `0x1800165ff`
- `USER32!RegisterClipboardFormatW` at `0x180016613`
- `USER32!RegisterClipboardFormatW` at `0x180016596`
- `USER32!RegisterClipboardFormatW` at `0x1800165a3`
- `USER32!RegisterClipboardFormatW` at `0x1800165b0`
- `USER32!RegisterClipboardFormatW` at `0x1800165bd`
- `USER32!RegisterClipboardFormatW` at `0x1800165ca`
- `USER32!RegisterClipboardFormatW` at `0x1800165de`
- `USER32!RegisterClipboardFormatW` at `0x1800165eb`
- `USER32!RegisterClipboardFormatW` at `0x1800165ff`
- `USER32!RegisterClipboardFormatW` at `0x180016613`

## string_xrefs

- `0x1800165b6`: `FileGroupDescriptorW`
- `0x1800165a9`: `FileGroupDescriptor`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DataObj_GetFilePropertyStore(
        struct IDataObject *a1,
        int a2,
        struct IPersistSerializedPropStorage *a3)
{
  unsigned __int16 v6; // ax
  int v7; // ebx
  unsigned int *v9; // rbp
  unsigned int v10; // ebp
  void *v11; // rcx
  int v12; // eax
  void *v13; // rbx
  int BlobWithIndex; // edi
  __int64 v15; // rdx
  unsigned int v16; // [rsp+20h] [rbp-68h]
  unsigned int v17; // [rsp+20h] [rbp-68h]
  STGMEDIUM hMem; // [rsp+30h] [rbp-58h] BYREF
  unsigned __int16 v19; // [rsp+48h] [rbp-40h] BYREF
  int v20; // [rsp+4Ah] [rbp-3Eh]
  __int16 v21; // [rsp+4Eh] [rbp-3Ah]
  __int64 v22; // [rsp+50h] [rbp-38h]
  int v23; // [rsp+58h] [rbp-30h]
  int v24; // [rsp+5Ch] [rbp-2Ch]
  __int64 v25; // [rsp+60h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  LPVOID pv; // [rsp+90h] [rbp+8h] BYREF

  if ( g_cfAsyncFlag_Storage )
  {
    v6 = g_cfFilePropertyStoreByteSize_Storage;
  }
  else
  {
    RegisterClipboardFormatW(L"UniformResourceLocator");
    RegisterClipboardFormatW(L"Shell IDList Array");
    RegisterClipboardFormatW(L"FileGroupDescriptor");
    RegisterClipboardFormatW(L"FileGroupDescriptorW");
    g_cfOFFSETS_Storage = RegisterClipboardFormatW(L"Shell Object Offsets");
    RegisterClipboardFormatW(L"EnterpriseDataProtectionId");
    g_cfAsyncFlag_Storage = RegisterClipboardFormatW(L"AsyncFlag");
    g_cfFilePropertyStore_Storage = RegisterClipboardFormatW(L"FilePropertyStore");
    v6 = RegisterClipboardFormatW(L"FilePropertyStoreByteSize");
    g_cfFilePropertyStoreByteSize_Storage = v6;
  }
  memset(&hMem, 0, sizeof(hMem));
  v19 = v6;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 1;
  v24 = a2;
  v25 = 1;
  v7 = ((__int64 (__fastcall *)(struct IDataObject *, unsigned __int16 *, STGMEDIUM *))a1->lpVtbl->GetData)(
         a1,
         &v19,
         &hMem);
  if ( v7 < 0 )
    return (unsigned int)v7;
  v9 = (unsigned int *)GlobalLock(hMem.hBitmap);
  if ( !v9 )
  {
    v7 = -2147418113;
    ReleaseStgMedium(&hMem);
    return (unsigned int)v7;
  }
  if ( GlobalSize(hMem.hBitmap) >= 4 )
  {
    v10 = *v9;
  }
  else
  {
    v10 = 0;
    v7 = -2147418113;
  }
  GlobalUnlock(hMem.hBitmap);
  ReleaseStgMedium(&hMem);
  if ( v7 < 0 )
    return (unsigned int)v7;
  pv = 0;
  v12 = CTCoAllocPolicy::Alloc(v11, 1u, v10, &pv);
  v7 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BA,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\dobjutil_storage.h",
      (const char *)(unsigned int)v12,
      v16);
    CoTaskMemFree(pv);
    return (unsigned int)v7;
  }
  v13 = pv;
  BlobWithIndex = DataObj_GetBlobWithIndex(a1, g_cfFilePropertyStore_Storage, a2, pv, v10);
  if ( BlobWithIndex < 0 )
  {
    v15 = 443;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\dobjutil_storage.h",
      (const char *)(unsigned int)BlobWithIndex,
      v17);
    CoTaskMemFree(v13);
    return (unsigned int)BlobWithIndex;
  }
  BlobWithIndex = ((__int64 (__fastcall *)(struct IPersistSerializedPropStorage *, void *, _QWORD))a3->lpVtbl->SetPropertyStorage)(
                    a3,
                    v13,
                    v10);
  if ( BlobWithIndex < 0 )
  {
    v15 = 446;
    goto LABEL_16;
  }
  CoTaskMemFree(v13);
  return 0;
}

```

## disassembly

```asm
0x1800164f0  mov     [rsp+arg_8], rbx
0x1800164f5  mov     [rsp+arg_10], rbp
0x1800164fa  push    rsi
0x1800164fb  push    rdi
0x1800164fc  push    r14
0x1800164fe  sub     rsp, 70h
0x180016502  mov     r14, r8
0x180016505  mov     esi, edx
0x180016507  mov     rdi, rcx
0x18001650a  xor     eax, eax
0x18001650c  cmp     ax, cs:?g_cfAsyncFlag_Storage@@3GA; ushort g_cfAsyncFlag_Storage
0x180016513  jz      short loc_18001658F
0x180016515  movzx   eax, cs:?g_cfFilePropertyStoreByteSize_Storage@@3GA; ushort g_cfFilePropertyStoreByteSize_Storage
0x18001651c  xorps   xmm0, xmm0
0x18001651f  xor     ecx, ecx
0x180016521  movups  xmmword ptr [rsp+88h+hMem], xmm0
0x180016526  mov     [rsp+88h+var_48], rcx
0x18001652b  mov     [rsp+88h+var_40], ax
0x180016530  xor     eax, eax
0x180016532  mov     [rsp+88h+var_3E], eax
0x180016536  mov     [rsp+88h+var_3A], ax
0x18001653b  mov     [rsp+88h+var_38], rax
0x180016540  mov     [rsp+88h+var_30], 1
0x180016548  mov     [rsp+88h+var_2C], esi
0x18001654c  mov     [rsp+88h+var_28], 1
0x180016555  mov     rax, [rdi]
0x180016558  lea     r8, [rsp+88h+hMem]
0x18001655d  lea     rdx, [rsp+88h+var_40]
0x180016562  mov     rcx, rdi
0x180016565  mov     rax, [rax+18h]
0x180016569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001656e  mov     ebx, eax
0x180016570  test    eax, eax
0x180016572  jns     loc_180016625
0x180016578  mov     eax, ebx
0x18001657a  lea     r11, [rsp+88h+var_18]
0x18001657f  mov     rbx, [r11+28h]
0x180016583  mov     rbp, [r11+30h]
0x180016587  mov     rsp, r11
0x18001658a  pop     r14
0x18001658c  pop     rdi
0x18001658d  pop     rsi
0x18001658e  retn
0x18001658f  lea     rcx, szFormat; "UniformResourceLocator"
0x180016596  call    cs:__imp_RegisterClipboardFormatW
0x18001659c  lea     rcx, aShellIdlistArr; "Shell IDList Array"
0x1800165a3  call    cs:__imp_RegisterClipboardFormatW
0x1800165a9  lea     rcx, aFilegroupdescr_0; "FileGroupDescriptor"
0x1800165b0  call    cs:__imp_RegisterClipboardFormatW
0x1800165b6  lea     rcx, aFilegroupdescr; "FileGroupDescriptorW"
0x1800165bd  call    cs:__imp_RegisterClipboardFormatW
0x1800165c3  lea     rcx, aShellObjectOff; "Shell Object Offsets"
0x1800165ca  call    cs:__imp_RegisterClipboardFormatW
0x1800165d0  mov     cs:?g_cfOFFSETS_Storage@@3GA, ax; ushort g_cfOFFSETS_Storage
0x1800165d7  lea     rcx, aEnterprisedata; "EnterpriseDataProtectionId"
0x1800165de  call    cs:__imp_RegisterClipboardFormatW
0x1800165e4  lea     rcx, aAsyncflag; "AsyncFlag"
0x1800165eb  call    cs:__imp_RegisterClipboardFormatW
0x1800165f1  mov     cs:?g_cfAsyncFlag_Storage@@3GA, ax; ushort g_cfAsyncFlag_Storage
0x1800165f8  lea     rcx, aFilepropertyst; "FilePropertyStore"
0x1800165ff  call    cs:__imp_RegisterClipboardFormatW
0x180016605  mov     cs:?g_cfFilePropertyStore_Storage@@3GA, ax; ushort g_cfFilePropertyStore_Storage
0x18001660c  lea     rcx, aFilepropertyst_0; "FilePropertyStoreByteSize"
0x180016613  call    cs:__imp_RegisterClipboardFormatW
0x180016619  mov     cs:?g_cfFilePropertyStoreByteSize_Storage@@3GA, ax; ushort g_cfFilePropertyStoreByteSize_Storage
0x180016620  jmp     loc_18001651C
0x180016625  mov     rcx, [rsp+88h+hMem+8]; hMem
0x18001662a  call    cs:__imp_GlobalLock
0x180016630  mov     rbp, rax
0x180016633  test    rax, rax
0x180016636  jz      loc_180016754
0x18001663c  mov     rcx, [rsp+88h+hMem+8]; hMem
0x180016641  call    cs:__imp_GlobalSize
0x180016647  cmp     rax, 4
0x18001664b  jnb     short loc_180016656
0x18001664d  xor     ebp, ebp
0x18001664f  mov     ebx, 8000FFFFh
0x180016654  jmp     short loc_180016659
0x180016656  mov     ebp, [rbp+0]
0x180016659  mov     rcx, [rsp+88h+hMem+8]; hMem
0x18001665e  call    cs:__imp_GlobalUnlock
0x180016664  lea     rcx, [rsp+88h+hMem]; LPSTGMEDIUM
0x180016669  call    cs:__imp_ReleaseStgMedium
0x18001666f  test    ebx, ebx
0x180016671  js      loc_180016578
0x180016677  mov     [rsp+88h+pv], 0
0x180016683  mov     r8d, ebp; unsigned __int64
0x180016686  lea     r9, [rsp+88h+pv]; void **
0x18001668e  mov     edx, 1; unsigned int
0x180016693  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180016698  mov     ebx, eax
0x18001669a  test    eax, eax
0x18001669c  jns     short loc_1800166CE
0x18001669e  mov     rcx, [rsp+88h]; this
0x1800166a6  mov     r9d, eax; char *
0x1800166a9  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1800166b0  mov     edx, 1BAh; void *
0x1800166b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800166ba  nop
0x1800166bb  mov     rcx, [rsp+88h+pv]; pv
0x1800166c3  call    cs:__imp_CoTaskMemFree
0x1800166c9  jmp     loc_180016578
0x1800166ce  movzx   edx, cs:?g_cfFilePropertyStore_Storage@@3GA; unsigned int
0x1800166d5  mov     [rsp+88h+var_68], ebp; int
0x1800166d9  mov     rbx, [rsp+88h+pv]
0x1800166e1  mov     r9, rbx; void *
0x1800166e4  mov     r8d, esi; int
0x1800166e7  mov     rcx, rdi; struct IDataObject *
0x1800166ea  call    ?DataObj_GetBlobWithIndex@@YAJPEAUIDataObject@@IJPEAXI@Z; DataObj_GetBlobWithIndex(IDataObject *,uint,long,void *,uint)
0x1800166ef  mov     edi, eax
0x1800166f1  test    eax, eax
0x1800166f3  jns     short loc_180016729
0x1800166f5  mov     edx, 1BBh
0x1800166fa  jmp     short loc_180016701
0x1800166fc  mov     edx, 1BEh; void *
0x180016701  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180016708  mov     r9d, edi; char *
0x18001670b  mov     rcx, [rsp+88h]; this
0x180016713  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016718  nop
0x180016719  mov     rcx, rbx; pv
0x18001671c  call    cs:__imp_CoTaskMemFree
0x180016722  mov     eax, edi
0x180016724  jmp     loc_18001657A
0x180016729  mov     rax, [r14]
0x18001672c  mov     r8d, ebp
0x18001672f  mov     rdx, rbx
0x180016732  mov     rcx, r14
0x180016735  mov     rax, [rax+20h]
0x180016739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001673e  mov     edi, eax
0x180016740  test    eax, eax
0x180016742  js      short loc_1800166FC
0x180016744  mov     rcx, rbx; pv
0x180016747  call    cs:__imp_CoTaskMemFree
0x18001674d  xor     eax, eax
0x18001674f  jmp     loc_18001657A
0x180016754  mov     ebx, 8000FFFFh
0x180016759  lea     rcx, [rsp+88h+hMem]; LPSTGMEDIUM
0x18001675e  call    cs:__imp_ReleaseStgMedium
0x180016764  jmp     loc_180016578
```
