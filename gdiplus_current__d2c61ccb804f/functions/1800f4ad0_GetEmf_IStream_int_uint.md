# GetEmf(IStream *,int,uint)

- ea: `0x1800f4ad0`
- end: `0x1800f4bee`
- name: `?GetEmf@@YAPEAUHENHMETAFILE__@@PEAUIStream@@HI@Z`
- size: `286`
- prototype: `HENHMETAFILE __fastcall(struct IStream *, int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18008953c`
- `0x180122e74`

## callees

- `0x1800f4ad0`
- `0x1800f8870`
- `0x180124b00`
- `0x180172010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f4b37`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f4b37`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800f4b09`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800f4b09`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800f4bd1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800f4bd1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800f4b71`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800f4b71`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800f4bac`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800f4bac`
- `GDI32!SetMetaFileBitsEx` at `0x1800f4b8c`
- `GDI32!SetMetaFileBitsEx` at `0x1800f4b8c`
- `GDI32!SetEnhMetaFileBits` at `0x1800f4b9a`
- `GDI32!SetEnhMetaFileBits` at `0x1800f4b9a`

## pseudocode

```c
HENHMETAFILE __fastcall GetEmf(struct IStream *a1, int a2, unsigned int a3)
{
  SIZE_T v3; // rdi
  void *v7; // rsi
  HGLOBAL v8; // rax
  void *v9; // rbx
  const BYTE *v10; // rax
  void *v11; // rax
  __int64 v12[9]; // [rsp+20h] [rbp-48h] BYREF
  LPSTREAM ppstm; // [rsp+88h] [rbp+20h] BYREF

  v3 = a3;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HandleZeroSizedEmf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_HandleZeroSizedEmf>::GetImpl'::`2'::impl)
    && !(_DWORD)v3 )
  {
    return 0;
  }
  v7 = 0;
  v8 = GlobalAlloc(0x22u, v3);
  v9 = v8;
  if ( v8 )
  {
    ppstm = 0;
    if ( CreateStreamOnHGlobal(v8, 1, &ppstm) >= 0 && ppstm )
    {
      v12[0] = v3;
      if ( (unsigned int)CopyStream(a1, ppstm, v12) )
      {
        v10 = (const BYTE *)GlobalLock(v9);
        if ( v10 )
        {
          if ( a2 )
            v11 = SetMetaFileBitsEx(v3, v10);
          else
            v11 = SetEnhMetaFileBits(v3, v10);
          v7 = v11;
        }
        GlobalUnlock(v9);
      }
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    }
    else
    {
      GlobalFree(v9);
    }
  }
  return (HENHMETAFILE)v7;
}

```

## disassembly

```asm
0x1800f4ad0  push    rbx
0x1800f4ad2  push    rbp
0x1800f4ad3  push    rsi
0x1800f4ad4  push    rdi
0x1800f4ad5  push    r14
0x1800f4ad7  push    r15
0x1800f4ad9  sub     rsp, 38h
0x1800f4add  mov     edi, r8d
0x1800f4ae0  mov     r14d, edx
0x1800f4ae3  mov     r15, rcx
0x1800f4ae6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_HandleZeroSizedEmf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HandleZeroSizedEmf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HandleZeroSizedEmf> `wil::Feature<__WilFeatureTraits_Feature_Servicing_HandleZeroSizedEmf>::GetImpl(void)'::`2'::impl
0x1800f4aed  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HandleZeroSizedEmf@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HandleZeroSizedEmf>::__private_IsEnabled(void)
0x1800f4af2  test    al, al
0x1800f4af4  jz      short loc_1800F4B01
0x1800f4af6  test    edi, edi
0x1800f4af8  jnz     short loc_1800F4B01
0x1800f4afa  xor     eax, eax
0x1800f4afc  jmp     loc_1800F4BE0
0x1800f4b01  xor     esi, esi
0x1800f4b03  mov     rdx, rdi; dwBytes
0x1800f4b06  lea     ecx, [rsi+22h]; uFlags
0x1800f4b09  call    cs:__imp_GlobalAlloc
0x1800f4b10  nop     dword ptr [rax+rax+00h]
0x1800f4b15  mov     rbx, rax
0x1800f4b18  test    rax, rax
0x1800f4b1b  jz      loc_1800F4BDD
0x1800f4b21  lea     r8, [rsp+68h+ppstm]; ppstm
0x1800f4b29  mov     [rsp+68h+ppstm], rsi
0x1800f4b31  lea     edx, [rsi+1]; fDeleteOnRelease
0x1800f4b34  mov     rcx, rax; hGlobal
0x1800f4b37  call    cs:__imp_CreateStreamOnHGlobal
0x1800f4b3e  nop     dword ptr [rax+rax+00h]
0x1800f4b43  test    eax, eax
0x1800f4b45  js      loc_1800F4BCE
0x1800f4b4b  mov     rdx, [rsp+68h+ppstm]; struct IStream *
0x1800f4b53  test    rdx, rdx
0x1800f4b56  jz      short loc_1800F4BCE
0x1800f4b58  lea     r8, [rsp+68h+var_48]; __int64 *
0x1800f4b5d  mov     [rsp+68h+var_48], rdi
0x1800f4b62  mov     rcx, r15; struct IStream *
0x1800f4b65  call    ?CopyStream@@YAHPEAUIStream@@0AEB_J@Z; CopyStream(IStream *,IStream *,__int64 const &)
0x1800f4b6a  test    eax, eax
0x1800f4b6c  jz      short loc_1800F4BB8
0x1800f4b6e  mov     rcx, rbx; hMem
0x1800f4b71  call    cs:__imp_GlobalLock
0x1800f4b78  nop     dword ptr [rax+rax+00h]
0x1800f4b7d  test    rax, rax
0x1800f4b80  jz      short loc_1800F4BA9
0x1800f4b82  mov     rdx, rax; pb
0x1800f4b85  mov     ecx, edi; nSize
0x1800f4b87  test    r14d, r14d
0x1800f4b8a  jz      short loc_1800F4B9A
0x1800f4b8c  call    cs:__imp_SetMetaFileBitsEx
0x1800f4b93  nop     dword ptr [rax+rax+00h]
0x1800f4b98  jmp     short loc_1800F4BA6
0x1800f4b9a  call    cs:__imp_SetEnhMetaFileBits
0x1800f4ba1  nop     dword ptr [rax+rax+00h]
0x1800f4ba6  mov     rsi, rax
0x1800f4ba9  mov     rcx, rbx; hMem
0x1800f4bac  call    cs:__imp_GlobalUnlock
0x1800f4bb3  nop     dword ptr [rax+rax+00h]
0x1800f4bb8  mov     rcx, [rsp+68h+ppstm]
0x1800f4bc0  mov     rax, [rcx]
0x1800f4bc3  mov     rax, [rax+10h]
0x1800f4bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4bcc  jmp     short loc_1800F4BDD
0x1800f4bce  mov     rcx, rbx; hMem
0x1800f4bd1  call    cs:__imp_GlobalFree
0x1800f4bd8  nop     dword ptr [rax+rax+00h]
0x1800f4bdd  mov     rax, rsi
0x1800f4be0  add     rsp, 38h
0x1800f4be4  pop     r15
0x1800f4be6  pop     r14
0x1800f4be8  pop     rdi
0x1800f4be9  pop     rsi
0x1800f4bea  pop     rbp
0x1800f4beb  pop     rbx
0x1800f4bec  retn
```
