# CSearchQueryMapping::MapPKey_Kind(LeaveInfo *,CMFBaseStringT<ushort> *,CSearchQueryMapping *)

- ea: `0x18002a340`
- end: `0x18002a6b3`
- name: `?MapPKey_Kind@CSearchQueryMapping@@KAJPEAULeaveInfo@@PEAV?$CMFBaseStringT@G@@PEAV1@@Z`
- size: `883`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18001bfc0`
- `0x18001c648`
- `0x18001d41c`
- `0x18002a340`
- `0x1800333e8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a388`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a3b4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a3e0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a45f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a4d6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a551`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a5cc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a388`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a3b4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a3e0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a45f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a4d6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a551`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a5cc`

## pseudocode

```c
__int64 __fastcall CSearchQueryMapping::MapPKey_Kind(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v5; // rdi
  const wchar_t *v6; // rdx
  int v7; // [rsp+70h] [rbp+38h] BYREF

  if ( !*(_DWORD *)(a1 + 48) )
  {
    if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(a1 + 32), -1, L"video", -1) == 2
      || CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(a1 + 32), -1, L"movie", -1) == 2 )
    {
      v7 = -1;
      if ( (int)UIntPtrToLong(0x2Eu, &v7) < 0 )
        goto LABEL_41;
      result = *(unsigned int *)(a2 + 4);
      if ( (int)result < 0 )
        return result;
      v5 = v7;
      if ( (unsigned int)v7 > 0x4000000 )
        goto LABEL_41;
      if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(a2, (unsigned int)(v7 + *(_DWORD *)(a2 + 8))) < 0 )
        return *(unsigned int *)(a2 + 4);
      v6 = L"upnp:class derivedfrom \"object.item.videoItem\"";
      goto LABEL_40;
    }
    if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(a1 + 32), -1, L"music", -1) == 2 )
    {
      v7 = -1;
      if ( (int)UIntPtrToLong(0x2Eu, &v7) >= 0 )
      {
        result = *(unsigned int *)(a2 + 4);
        if ( (int)result < 0 )
          return result;
        v5 = v7;
        if ( (unsigned int)v7 <= 0x4000000 )
        {
          if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(a2, (unsigned int)(v7 + *(_DWORD *)(a2 + 8))) < 0 )
            return *(unsigned int *)(a2 + 4);
          v6 = L"upnp:class derivedfrom \"object.item.audioItem\"";
          goto LABEL_40;
        }
      }
      goto LABEL_41;
    }
    if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(a1 + 32), -1, L"picture", -1) == 2 )
    {
      v7 = -1;
      if ( (int)UIntPtrToLong(0x2Eu, &v7) >= 0 )
      {
        result = *(unsigned int *)(a2 + 4);
        if ( (int)result < 0 )
          return result;
        v5 = v7;
        if ( (unsigned int)v7 <= 0x4000000 )
        {
          if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(a2, (unsigned int)(v7 + *(_DWORD *)(a2 + 8))) < 0 )
            return *(unsigned int *)(a2 + 4);
          v6 = L"upnp:class derivedfrom \"object.item.imageItem\"";
          goto LABEL_40;
        }
      }
LABEL_41:
      result = 2147942511LL;
      *(_DWORD *)(a2 + 4) = -2147024785;
      return result;
    }
    if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(a1 + 32), -1, L"recordedtv", -1) == 2 )
    {
      v7 = -1;
      if ( (int)UIntPtrToLong(0x3Du, &v7) < 0 )
        goto LABEL_41;
      result = *(unsigned int *)(a2 + 4);
      if ( (int)result < 0 )
        return result;
      v5 = v7;
      if ( (unsigned int)v7 > 0x4000000 )
        goto LABEL_41;
      if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(a2, (unsigned int)(v7 + *(_DWORD *)(a2 + 8))) < 0 )
        return *(unsigned int *)(a2 + 4);
      v6 = L"upnp:class derivedfrom \"object.item.videoItem.videoBroadcast\"";
LABEL_40:
      memcpy_0((void *)(*(_QWORD *)(a2 + 16) + 2LL * *(int *)(a2 + 8)), v6, 2 * v5);
      CMFBaseStringT<unsigned short>::ReleaseBuffer(a2, (unsigned int)(v5 + *(_DWORD *)(a2 + 8)));
      return 0;
    }
    if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(a1 + 32), -1, L"folder", -1) == 2 )
    {
      v7 = -1;
      if ( (int)UIntPtrToLong(0x29u, &v7) < 0 )
        goto LABEL_41;
      result = *(unsigned int *)(a2 + 4);
      if ( (int)result < 0 )
        return result;
      v5 = v7;
      if ( (unsigned int)v7 > 0x4000000 )
        goto LABEL_41;
      if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(a2, (unsigned int)(v7 + *(_DWORD *)(a2 + 8))) < 0 )
        return *(unsigned int *)(a2 + 4);
      v6 = L"upnp:class derivedfrom \"object.container\"";
      goto LABEL_40;
    }
    if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(a1 + 32), -1, L"playlist", -1) == 2 )
    {
      v7 = -1;
      if ( (int)UIntPtrToLong(0x3Bu, &v7) < 0 )
        goto LABEL_41;
      result = *(unsigned int *)(a2 + 4);
      if ( (int)result < 0 )
        return result;
      v5 = v7;
      if ( (unsigned int)v7 > 0x4000000 )
        goto LABEL_41;
      if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(a2, (unsigned int)(v7 + *(_DWORD *)(a2 + 8))) < 0 )
        return *(unsigned int *)(a2 + 4);
      v6 = L"upnp:class derivedfrom \"object.container.playlistContainer\"";
      goto LABEL_40;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18002a340  push    rbp
0x18002a342  push    rbx
0x18002a343  push    rsi
0x18002a344  push    rdi
0x18002a345  push    r14
0x18002a347  push    r15
0x18002a349  mov     rbp, rsp
0x18002a34c  sub     rsp, 38h
0x18002a350  cmp     dword ptr [rcx+30h], 0
0x18002a354  mov     rbx, rdx
0x18002a357  mov     rdi, rcx
0x18002a35a  jnz     loc_18002A6A1
0x18002a360  mov     r8, [rcx+20h]; lpString1
0x18002a364  lea     rax, aVideo_0; "video"
0x18002a36b  or      esi, 0FFFFFFFFh
0x18002a36e  mov     [rsp+38h+cchCount2], esi; cchCount2
0x18002a372  mov     r9d, esi; cchCount1
0x18002a375  mov     [rsp+38h+lpString2], rax; lpString2
0x18002a37a  lea     r14d, [rsi+2]
0x18002a37e  lea     r15d, [r14+7Eh]
0x18002a382  mov     edx, r14d; dwCmpFlags
0x18002a385  mov     ecx, r15d; Locale
0x18002a388  call    cs:__imp_CompareStringW
0x18002a38e  cmp     eax, 2
0x18002a391  jz      loc_18002A62B
0x18002a397  mov     r8, [rdi+20h]; lpString1
0x18002a39b  lea     rax, aMovie; "movie"
0x18002a3a2  mov     [rsp+38h+cchCount2], esi; cchCount2
0x18002a3a6  mov     r9d, esi; cchCount1
0x18002a3a9  mov     edx, r14d; dwCmpFlags
0x18002a3ac  mov     [rsp+38h+lpString2], rax; lpString2
0x18002a3b1  mov     ecx, r15d; Locale
0x18002a3b4  call    cs:__imp_CompareStringW
0x18002a3ba  cmp     eax, 2
0x18002a3bd  jz      loc_18002A62B
0x18002a3c3  mov     r8, [rdi+20h]; lpString1
0x18002a3c7  lea     rax, aMusic; "music"
0x18002a3ce  mov     [rsp+38h+cchCount2], esi; cchCount2
0x18002a3d2  mov     r9d, esi; cchCount1
0x18002a3d5  mov     edx, r14d; dwCmpFlags
0x18002a3d8  mov     [rsp+38h+lpString2], rax; lpString2
0x18002a3dd  mov     ecx, r15d; Locale
0x18002a3e0  call    cs:__imp_CompareStringW
0x18002a3e6  cmp     eax, 2
0x18002a3e9  jnz     short loc_18002A442
0x18002a3eb  lea     rdx, [rbp+arg_0]; int *
0x18002a3ef  mov     [rbp+arg_0], esi
0x18002a3f2  lea     ecx, [rsi+2Fh]; unsigned __int64
0x18002a3f5  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x18002a3fa  test    eax, eax
0x18002a3fc  js      loc_18002A697
0x18002a402  mov     eax, [rbx+4]
0x18002a405  test    eax, eax
0x18002a407  js      loc_18002A6A6
0x18002a40d  movsxd  rdi, [rbp+arg_0]
0x18002a411  cmp     edi, 4000000h
0x18002a417  ja      loc_18002A697
0x18002a41d  mov     edx, [rbx+8]
0x18002a420  mov     rcx, rbx
0x18002a423  add     edx, edi
0x18002a425  call    ?_EnsureSpace@?$CMFBaseStringT@G@@IEAAJJ@Z; CMFBaseStringT<ushort>::_EnsureSpace(long)
0x18002a42a  test    eax, eax
0x18002a42c  jns     short loc_18002A436
0x18002a42e  mov     eax, [rbx+4]
0x18002a431  jmp     loc_18002A6A6
0x18002a436  lea     rdx, aUpnpClassDeriv_15; "upnp:class derivedfrom \"object.item.au"...
0x18002a43d  jmp     loc_18002A66F
0x18002a442  mov     r8, [rdi+20h]; lpString1
0x18002a446  lea     rax, aPicture; "picture"
0x18002a44d  mov     [rsp+38h+cchCount2], esi; cchCount2
0x18002a451  mov     r9d, esi; cchCount1
0x18002a454  mov     edx, r14d; dwCmpFlags
0x18002a457  mov     [rsp+38h+lpString2], rax; lpString2
0x18002a45c  mov     ecx, r15d; Locale
0x18002a45f  call    cs:__imp_CompareStringW
0x18002a465  cmp     eax, 2
0x18002a468  jnz     short loc_18002A4B9
0x18002a46a  lea     rdx, [rbp+arg_0]; int *
0x18002a46e  mov     [rbp+arg_0], esi
0x18002a471  lea     ecx, [rax+2Ch]; unsigned __int64
0x18002a474  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x18002a479  test    eax, eax
0x18002a47b  js      loc_18002A697
0x18002a481  mov     eax, [rbx+4]
0x18002a484  test    eax, eax
0x18002a486  js      loc_18002A6A6
0x18002a48c  movsxd  rdi, [rbp+arg_0]
0x18002a490  cmp     edi, 4000000h
0x18002a496  ja      loc_18002A697
0x18002a49c  mov     edx, [rbx+8]
0x18002a49f  mov     rcx, rbx
0x18002a4a2  add     edx, edi
0x18002a4a4  call    ?_EnsureSpace@?$CMFBaseStringT@G@@IEAAJJ@Z; CMFBaseStringT<ushort>::_EnsureSpace(long)
0x18002a4a9  test    eax, eax
0x18002a4ab  js      short loc_18002A42E
0x18002a4ad  lea     rdx, aUpnpClassDeriv_7; "upnp:class derivedfrom \"object.item.im"...
0x18002a4b4  jmp     loc_18002A66F
0x18002a4b9  mov     r8, [rdi+20h]; lpString1
0x18002a4bd  lea     rax, aRecordedtv; "recordedtv"
0x18002a4c4  mov     [rsp+38h+cchCount2], esi; cchCount2
0x18002a4c8  mov     r9d, esi; cchCount1
0x18002a4cb  mov     edx, r14d; dwCmpFlags
0x18002a4ce  mov     [rsp+38h+lpString2], rax; lpString2
0x18002a4d3  mov     ecx, r15d; Locale
0x18002a4d6  call    cs:__imp_CompareStringW
0x18002a4dc  cmp     eax, 2
0x18002a4df  jnz     short loc_18002A534
0x18002a4e1  lea     rdx, [rbp+arg_0]; int *
0x18002a4e5  mov     [rbp+arg_0], esi
0x18002a4e8  lea     ecx, [rax+3Bh]; unsigned __int64
0x18002a4eb  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x18002a4f0  test    eax, eax
0x18002a4f2  js      loc_18002A697
0x18002a4f8  mov     eax, [rbx+4]
0x18002a4fb  test    eax, eax
0x18002a4fd  js      loc_18002A6A6
0x18002a503  movsxd  rdi, [rbp+arg_0]
0x18002a507  cmp     edi, 4000000h
0x18002a50d  ja      loc_18002A697
0x18002a513  mov     edx, [rbx+8]
0x18002a516  mov     rcx, rbx
0x18002a519  add     edx, edi
0x18002a51b  call    ?_EnsureSpace@?$CMFBaseStringT@G@@IEAAJJ@Z; CMFBaseStringT<ushort>::_EnsureSpace(long)
0x18002a520  test    eax, eax
0x18002a522  js      loc_18002A42E
0x18002a528  lea     rdx, aUpnpClassDeriv_12; "upnp:class derivedfrom \"object.item.vi"...
0x18002a52f  jmp     loc_18002A66F
0x18002a534  mov     r8, [rdi+20h]; lpString1
0x18002a538  lea     rax, aFolder_0; "folder"
0x18002a53f  mov     [rsp+38h+cchCount2], esi; cchCount2
0x18002a543  mov     r9d, esi; cchCount1
0x18002a546  mov     edx, r14d; dwCmpFlags
0x18002a549  mov     [rsp+38h+lpString2], rax; lpString2
0x18002a54e  mov     ecx, r15d; Locale
0x18002a551  call    cs:__imp_CompareStringW
0x18002a557  cmp     eax, 2
0x18002a55a  jnz     short loc_18002A5AF
0x18002a55c  lea     rdx, [rbp+arg_0]; int *
0x18002a560  mov     [rbp+arg_0], esi
0x18002a563  lea     ecx, [rax+27h]; unsigned __int64
0x18002a566  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x18002a56b  test    eax, eax
0x18002a56d  js      loc_18002A697
0x18002a573  mov     eax, [rbx+4]
0x18002a576  test    eax, eax
0x18002a578  js      loc_18002A6A6
0x18002a57e  movsxd  rdi, [rbp+arg_0]
0x18002a582  cmp     edi, 4000000h
0x18002a588  ja      loc_18002A697
0x18002a58e  mov     edx, [rbx+8]
0x18002a591  mov     rcx, rbx
0x18002a594  add     edx, edi
0x18002a596  call    ?_EnsureSpace@?$CMFBaseStringT@G@@IEAAJJ@Z; CMFBaseStringT<ushort>::_EnsureSpace(long)
0x18002a59b  test    eax, eax
0x18002a59d  js      loc_18002A42E
0x18002a5a3  lea     rdx, aUpnpClassDeriv_6; "upnp:class derivedfrom \"object.contain"...
0x18002a5aa  jmp     loc_18002A66F
0x18002a5af  mov     r8, [rdi+20h]; lpString1
0x18002a5b3  lea     rax, aPlaylist; "playlist"
0x18002a5ba  mov     [rsp+38h+cchCount2], esi; cchCount2
0x18002a5be  mov     r9d, esi; cchCount1
0x18002a5c1  mov     edx, r14d; dwCmpFlags
0x18002a5c4  mov     [rsp+38h+lpString2], rax; lpString2
0x18002a5c9  mov     ecx, r15d; Locale
0x18002a5cc  call    cs:__imp_CompareStringW
0x18002a5d2  cmp     eax, 2
0x18002a5d5  jnz     loc_18002A6A1
0x18002a5db  lea     rdx, [rbp+arg_0]; int *
0x18002a5df  mov     [rbp+arg_0], esi
0x18002a5e2  lea     ecx, [rax+39h]; unsigned __int64
0x18002a5e5  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x18002a5ea  test    eax, eax
0x18002a5ec  js      loc_18002A697
0x18002a5f2  mov     eax, [rbx+4]
0x18002a5f5  test    eax, eax
0x18002a5f7  js      loc_18002A6A6
0x18002a5fd  movsxd  rdi, [rbp+arg_0]
0x18002a601  cmp     edi, 4000000h
0x18002a607  ja      loc_18002A697
0x18002a60d  mov     edx, [rbx+8]
0x18002a610  mov     rcx, rbx
0x18002a613  add     edx, edi
0x18002a615  call    ?_EnsureSpace@?$CMFBaseStringT@G@@IEAAJJ@Z; CMFBaseStringT<ushort>::_EnsureSpace(long)
0x18002a61a  test    eax, eax
0x18002a61c  js      loc_18002A42E
0x18002a622  lea     rdx, aUpnpClassDeriv_10; "upnp:class derivedfrom \"object.contain"...
0x18002a629  jmp     short loc_18002A66F
0x18002a62b  lea     rdx, [rbp+arg_0]; int *
0x18002a62f  mov     [rbp+arg_0], esi
0x18002a632  mov     ecx, 2Eh ; '.'; unsigned __int64
0x18002a637  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x18002a63c  test    eax, eax
0x18002a63e  js      short loc_18002A697
0x18002a640  mov     eax, [rbx+4]
0x18002a643  test    eax, eax
0x18002a645  js      short loc_18002A6A6
0x18002a647  movsxd  rdi, [rbp+arg_0]
0x18002a64b  cmp     edi, 4000000h
0x18002a651  ja      short loc_18002A697
0x18002a653  mov     edx, [rbx+8]
0x18002a656  mov     rcx, rbx
0x18002a659  add     edx, edi
0x18002a65b  call    ?_EnsureSpace@?$CMFBaseStringT@G@@IEAAJJ@Z; CMFBaseStringT<ushort>::_EnsureSpace(long)
0x18002a660  test    eax, eax
0x18002a662  js      loc_18002A42E
0x18002a668  lea     rdx, aUpnpClassDeriv_5; "upnp:class derivedfrom \"object.item.vi"...
0x18002a66f  movsxd  rcx, dword ptr [rbx+8]
0x18002a673  mov     r8, rdi
0x18002a676  mov     rax, [rbx+10h]
0x18002a67a  add     r8, r8; Size
0x18002a67d  lea     rcx, [rax+rcx*2]; void *
0x18002a681  call    memcpy_0
0x18002a686  mov     edx, [rbx+8]
0x18002a689  mov     rcx, rbx
0x18002a68c  add     edx, edi
0x18002a68e  call    ?ReleaseBuffer@?$CMFBaseStringT@G@@QEAAJJ@Z; CMFBaseStringT<ushort>::ReleaseBuffer(long)
0x18002a693  xor     eax, eax
0x18002a695  jmp     short loc_18002A6A6
0x18002a697  mov     eax, 8007006Fh
0x18002a69c  mov     [rbx+4], eax
0x18002a69f  jmp     short loc_18002A6A6
0x18002a6a1  mov     eax, 80070057h
0x18002a6a6  add     rsp, 38h
0x18002a6aa  pop     r15
0x18002a6ac  pop     r14
0x18002a6ae  pop     rdi
0x18002a6af  pop     rsi
0x18002a6b0  pop     rbx
0x18002a6b1  pop     rbp
0x18002a6b2  retn
```
