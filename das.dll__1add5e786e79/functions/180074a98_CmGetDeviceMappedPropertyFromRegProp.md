# _CmGetDeviceMappedPropertyFromRegProp

- ea: `0x180074a98`
- end: `0x1800750fb`
- name: `_CmGetDeviceMappedPropertyFromRegProp`
- size: `1635`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180072128`
- `0x180072330`
- `0x1800734a4`
- `0x180075104`

## callees

- `0x18001df70`
- `0x18003bc80`
- `0x180067168`
- `0x18006723c`
- `0x18006beec`
- `0x18006e058`
- `0x180071258`
- `0x180074a98`
- `0x18007d2e8`

## import_xrefs

- `ntdll!NtClose` at `0x180074f49`
- `ntdll!NtClose` at `0x180074f49`
- `ntdll!RtlGUIDFromString` at `0x1800750a9`
- `ntdll!RtlGUIDFromString` at `0x1800750a9`
- `ntdll!RtlFreeHeap` at `0x180074ce3`
- `ntdll!RtlFreeHeap` at `0x180074d34`
- `ntdll!RtlFreeHeap` at `0x180074ee8`
- `ntdll!RtlFreeHeap` at `0x180074f92`
- `ntdll!RtlFreeHeap` at `0x180074ce3`
- `ntdll!RtlFreeHeap` at `0x180074d34`
- `ntdll!RtlFreeHeap` at `0x180074ee8`
- `ntdll!RtlFreeHeap` at `0x180074f92`
- `ntdll!RtlAllocateHeap` at `0x180074c74`
- `ntdll!RtlAllocateHeap` at `0x180074e79`
- `ntdll!RtlAllocateHeap` at `0x180074c74`
- `ntdll!RtlAllocateHeap` at `0x180074e79`
- `ntdll!RtlInitUnicodeStringEx` at `0x180075091`
- `ntdll!RtlInitUnicodeStringEx` at `0x180075091`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180074f76`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180074f76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180074ff6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180074ff6`

## pseudocode

```c
__int64 __fastcall CmGetDeviceMappedPropertyFromRegProp(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5,
        GUID *a6,
        unsigned int a7,
        unsigned int *a8,
        int a9)
{
  int v9; // ebx
  GUID *v10; // r15
  int v11; // esi
  unsigned int v12; // edx
  NTSTATUS DeviceRegProp; // ebx
  unsigned int v14; // r13d
  DEVPROPKEY **v15; // r14
  DEVPROPKEY *v16; // rcx
  __int64 v17; // rax
  int v18; // eax
  NTSTATUS v19; // eax
  int v20; // r9d
  int v21; // eax
  SIZE_T v22; // rax
  GUID *v23; // rsi
  GUID *v24; // r14
  int v25; // r14d
  int v26; // eax
  __int64 Len; // r9
  PVOID Heap; // rax
  bool v29; // bl
  LPWSTR v30; // r9
  NTSTATUS v31; // eax
  int StringSecurityDescriptorLen; // [rsp+20h] [rbp-E0h]
  SIZE_T Size; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h]
  __int64 v36; // [rsp+50h] [rbp-B0h]
  int v37; // [rsp+58h] [rbp-A8h] BYREF
  ULONG v38; // [rsp+5Ch] [rbp-A4h] BYREF
  PVOID P; // [rsp+60h] [rbp-A0h]
  int v40; // [rsp+68h] [rbp-98h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+70h] [rbp-90h] BYREF
  __int64 v42; // [rsp+78h] [rbp-88h]
  __int64 v43; // [rsp+80h] [rbp-80h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  GUID Guid; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR SourceString[40]; // [rsp+B0h] [rbp-50h] BYREF

  v9 = a2;
  v10 = a6;
  v35 = a2;
  v11 = a1;
  v12 = 0;
  v42 = a3;
  v36 = a1;
  v40 = 0;
  Size = 0;
  v37 = 0;
  StringSecurityDescriptor = 0;
  v38 = 0;
  v43 = 0;
  Handle = 0;
  DestinationString = 0;
  Guid = 0;
  if ( (_WORD)a9 )
    return (unsigned int)-1073741811;
  *a5 = 0;
  *a8 = 0;
  if ( a6 )
  {
    v14 = a7;
    v10 = (GUID *)(-(__int64)(a7 != 0) & (unsigned __int64)a6);
  }
  else
  {
    v14 = 0;
  }
  do
  {
    v15 = &CmDeviceRegPropMap + 3 * v12;
    v16 = *v15;
    if ( *(_DWORD *)(a4 + 16) == (*v15)->pid )
    {
      v17 = *(_QWORD *)a4 - *(_QWORD *)&v16->fmtid.Data1;
      if ( *(_QWORD *)a4 == *(_QWORD *)&v16->fmtid.Data1 )
        v17 = *(_QWORD *)(a4 + 8) - *(_QWORD *)v16->fmtid.Data4;
      if ( !v17 )
        break;
    }
    v15 = 0;
    ++v12;
  }
  while ( v12 < 0x21 );
  if ( !v15 )
    return (unsigned int)-1073741802;
  v18 = *((_DWORD *)v15 + 3);
  LODWORD(P) = v18;
  switch ( v18 )
  {
    case 9:
      goto LABEL_67;
    case 25:
      DeviceRegProp = CmGetDeviceRegProp(v11, v9, a3, 24, (__int64)&Size + 4, 0, (__int64)&Size, a9);
      if ( DeviceRegProp == -1073741789 )
      {
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)Size);
        P = Heap;
        if ( Heap )
        {
          DeviceRegProp = CmGetDeviceRegProp(v36, v35, v42, 24, (__int64)&Size + 4, (__int64)Heap, (__int64)&Size, a9);
          if ( DeviceRegProp >= 0 )
          {
            v29 = ConvertSecurityDescriptorToStringSecurityDescriptorW(P, 1u, 0xFu, &StringSecurityDescriptor, &v38);
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
            if ( !v29 )
            {
              v11 = v36;
              v25 = v35;
              DeviceRegProp = -1073741823;
              goto LABEL_56;
            }
            DeviceRegProp = RtlUnalignedStringCchLengthW(StringSecurityDescriptor, 0x7FFFFFFF, &v43);
            if ( DeviceRegProp >= 0 )
            {
              v38 = v43 + 1;
              *a8 = 2 * (v43 + 1);
              *a5 = *((_DWORD *)v15 + 2);
              if ( v14 >= *a8 )
              {
                v31 = RtlStringCbCopyExW((_DWORD)v10, v14, (_DWORD)v30, (_DWORD)v30, StringSecurityDescriptorLen, 2048);
                v30 = StringSecurityDescriptor;
                DeviceRegProp = v31;
              }
              else
              {
                DeviceRegProp = -1073741789;
              }
            }
            LocalFree(v30);
          }
          else
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
          }
          goto LABEL_54;
        }
        return (unsigned int)-1073741801;
      }
LABEL_54:
      v11 = v36;
      goto LABEL_55;
    case 27:
      LODWORD(Size) = 4;
      DeviceRegProp = CmGetDeviceRegProp(v11, v9, a3, 27, (__int64)&Size + 4, (__int64)&v37, (__int64)&Size, a9);
      if ( DeviceRegProp < 0 )
      {
LABEL_55:
        v25 = v35;
        goto LABEL_56;
      }
      if ( HIDWORD(Size) != *((_DWORD *)v15 + 4) )
        return (unsigned int)-1073741811;
      *a8 = 1;
      *a5 = *((_DWORD *)v15 + 2);
      if ( v14 >= *a8 )
      {
        LOBYTE(v10->Data1) = -(v37 != 0);
        return (unsigned int)DeviceRegProp;
      }
      return (unsigned int)-1073741789;
    case 37:
LABEL_67:
      LODWORD(Size) = 78;
      DeviceRegProp = CmGetDeviceRegProp(
                        v11,
                        v9,
                        a3,
                        v18,
                        (__int64)&Size + 4,
                        (__int64)SourceString,
                        (__int64)&Size,
                        a9);
      if ( DeviceRegProp < 0 )
        goto LABEL_55;
      if ( HIDWORD(Size) != *((_DWORD *)v15 + 4) )
        return (unsigned int)-1073741811;
      *a8 = 16;
      *a5 = *((_DWORD *)v15 + 2);
      if ( v14 >= *a8 )
      {
        SourceString[38] = 0;
        DeviceRegProp = RtlInitUnicodeStringEx(&DestinationString, SourceString);
        if ( DeviceRegProp >= 0 )
        {
          DeviceRegProp = RtlGUIDFromString(&DestinationString, &Guid);
          if ( DeviceRegProp >= 0 )
          {
            *v10 = Guid;
            return (unsigned int)DeviceRegProp;
          }
        }
        goto LABEL_55;
      }
      return (unsigned int)-1073741789;
  }
  *a8 = v14;
  v19 = CmGetDeviceRegProp(v11, v9, a3, v18, (__int64)&Size + 4, (__int64)v10, (__int64)a8, a9);
  DeviceRegProp = v19;
  if ( v19 && v19 != -1073741789 )
    goto LABEL_54;
  if ( HIDWORD(Size) != *((_DWORD *)v15 + 4) )
    return (unsigned int)-1073741811;
  v21 = *((_DWORD *)v15 + 2);
  *a5 = v21;
  if ( v21 != 18 )
    goto LABEL_37;
  v22 = *a8;
  LODWORD(Size) = *a8;
  if ( !DeviceRegProp )
  {
    if ( v14 < 2 || !v10 )
    {
LABEL_38:
      if ( *a5 == 8210 )
      {
        Len = (unsigned int)PnpMultiSzGetLen(v10);
        if ( 2 * Len > (unsigned __int64)*a8 )
        {
          DeviceRegProp = -1073741595;
          *a8 = 0;
          return (unsigned int)DeviceRegProp;
        }
        *a8 = 2 * Len;
      }
      if ( *a5 == 18 && !*a8 )
      {
        *a8 = 0;
        *a5 = 0;
        return (unsigned int)-1073741275;
      }
      return (unsigned int)DeviceRegProp;
    }
    v23 = 0;
    v24 = v10;
    goto LABEL_32;
  }
  if ( DeviceRegProp != -1073741789 )
    goto LABEL_54;
  v23 = (GUID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v22);
  if ( !v23 )
    return (unsigned int)-1073741801;
  v25 = v35;
  v26 = CmGetDeviceRegProp(v36, v35, v42, (_DWORD)P, (__int64)&v40, (__int64)v23, (__int64)&Size, a9);
  if ( v26 >= 0 )
  {
    if ( (unsigned int)Size < 2 )
      goto LABEL_36;
    v24 = v23;
LABEL_32:
    if ( (unsigned __int8)PnpParseIndirectInfString(v24) || (unsigned __int8)PnpParseIndirectResourceString(v24) )
      *a5 = 25;
    if ( !v23 )
    {
LABEL_37:
      if ( !DeviceRegProp )
        goto LABEL_38;
      goto LABEL_54;
    }
LABEL_36:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
    goto LABEL_37;
  }
  DeviceRegProp = v26;
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
  v11 = v36;
LABEL_56:
  if ( DeviceRegProp != -1073741810 )
    return (unsigned int)DeviceRegProp;
  DeviceRegProp = CmOpenDeviceRegKey(v11, v25, 16, v20, 1, 0, (__int64)&Handle, 0);
  if ( !DeviceRegProp )
  {
    NtClose(Handle);
    return (unsigned int)-1073741275;
  }
  if ( DeviceRegProp != -1073741810 && DeviceRegProp != -1073741632 )
    return (unsigned int)-1073741823;
  return (unsigned int)DeviceRegProp;
}

```

## disassembly

```asm
0x180074a98  mov     [rsp-8+arg_18], rbx
0x180074a9d  push    rbp
0x180074a9e  push    rsi
0x180074a9f  push    rdi
0x180074aa0  push    r12
0x180074aa2  push    r13
0x180074aa4  push    r14
0x180074aa6  push    r15
0x180074aa8  lea     rbp, [rsp-10h]
0x180074aad  sub     rsp, 110h
0x180074ab4  mov     rax, cs:__security_cookie
0x180074abb  xor     rax, rsp
0x180074abe  mov     [rbp+40h+var_40], rax
0x180074ac2  mov     r10d, [rbp+40h+arg_40]
0x180074ac9  mov     rbx, rdx
0x180074acc  mov     r12, [rbp+40h+arg_20]
0x180074ad0  xorps   xmm0, xmm0
0x180074ad3  mov     r15, [rbp+40h+arg_28]
0x180074ad7  xorps   xmm1, xmm1
0x180074ada  mov     rdi, [rbp+40h+arg_38]
0x180074ae1  mov     r11, r8
0x180074ae4  mov     [rsp+140h+var_F8], rdx
0x180074ae9  mov     rsi, rcx
0x180074aec  xor     edx, edx
0x180074aee  mov     [rsp+140h+var_C8], r8
0x180074af3  mov     [rsp+140h+var_F0], rcx
0x180074af8  mov     dword ptr [rsp+140h+Size+4], edx
0x180074afc  mov     [rsp+140h+var_D8], edx
0x180074b00  mov     dword ptr [rsp+140h+Size], edx
0x180074b04  mov     [rsp+140h+var_E8], edx
0x180074b08  mov     [rsp+140h+StringSecurityDescriptor], rdx
0x180074b0d  mov     [rsp+140h+var_E4], edx
0x180074b11  mov     [rbp+40h+var_C0], rdx
0x180074b15  mov     [rbp+40h+Handle], rdx
0x180074b19  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x180074b1d  movups  xmmword ptr [rbp+40h+Guid.Data1], xmm1
0x180074b21  test    r10w, r10w
0x180074b25  jz      short loc_180074B31
0x180074b27  mov     ebx, 0C000000Dh
0x180074b2c  jmp     loc_1800750D2
0x180074b31  mov     [r12], edx
0x180074b35  mov     [rdi], edx
0x180074b37  test    r15, r15
0x180074b3a  jnz     short loc_180074B41
0x180074b3c  mov     r13d, edx
0x180074b3f  jmp     short loc_180074B53
0x180074b41  mov     r13d, [rbp+40h+arg_30]
0x180074b48  mov     eax, r13d
0x180074b4b  neg     eax
0x180074b4d  sbb     rcx, rcx
0x180074b50  and     r15, rcx
0x180074b53  mov     r8d, [r9+10h]
0x180074b57  mov     eax, edx
0x180074b59  lea     rcx, [rax+rax*2]
0x180074b5d  lea     rax, _CmDeviceRegPropMap
0x180074b64  lea     r14, [rax+rcx*8]
0x180074b68  mov     rcx, [r14]
0x180074b6b  cmp     r8d, [rcx+10h]
0x180074b6f  jnz     short loc_180074B86
0x180074b71  mov     rax, [r9]
0x180074b74  sub     rax, [rcx]
0x180074b77  jnz     short loc_180074B81
0x180074b79  mov     rax, [r9+8]
0x180074b7d  sub     rax, [rcx+8]
0x180074b81  test    rax, rax
0x180074b84  jz      short loc_180074B90
0x180074b86  xor     r14d, r14d
0x180074b89  inc     edx
0x180074b8b  cmp     edx, 21h ; '!'
0x180074b8e  jb      short loc_180074B57
0x180074b90  test    r14, r14
0x180074b93  jnz     short loc_180074B9F
0x180074b95  mov     ebx, 0C0000016h
0x180074b9a  jmp     loc_1800750D2
0x180074b9f  mov     eax, [r14+0Ch]
0x180074ba3  mov     dword ptr [rsp+140h+P], eax
0x180074ba7  cmp     eax, 9
0x180074baa  jz      loc_180075019
0x180074bb0  cmp     eax, 19h
0x180074bb3  jz      loc_180074E1D
0x180074bb9  mov     r9d, 1Bh
0x180074bbf  cmp     eax, r9d
0x180074bc2  jz      loc_180074D9F
0x180074bc8  cmp     eax, 25h ; '%'
0x180074bcb  jz      loc_180075019
0x180074bd1  mov     dword ptr [rsp+140h+var_108], r10d
0x180074bd6  lea     rcx, [rsp+140h+Size+4]
0x180074bdb  mov     [rsp+140h+var_110], rdi
0x180074be0  mov     r9d, eax
0x180074be3  mov     [rsp+140h+var_118], r15
0x180074be8  mov     r8, r11
0x180074beb  mov     [rsp+140h+StringSecurityDescriptorLen], rcx
0x180074bf0  mov     rdx, rbx
0x180074bf3  mov     rcx, rsi
0x180074bf6  mov     [rdi], r13d
0x180074bf9  call    _CmGetDeviceRegProp
0x180074bfe  mov     ebx, eax
0x180074c00  mov     esi, 0C0000023h
0x180074c05  test    eax, eax
0x180074c07  jz      short loc_180074C11
0x180074c09  cmp     eax, esi
0x180074c0b  jnz     loc_180074EEE
0x180074c11  mov     ecx, [r14+10h]
0x180074c15  cmp     dword ptr [rsp+140h+Size+4], ecx
0x180074c19  jnz     loc_180074B27
0x180074c1f  mov     eax, [r14+8]
0x180074c23  mov     [r12], eax
0x180074c27  cmp     eax, 12h
0x180074c2a  jnz     loc_180074D3A
0x180074c30  mov     eax, [rdi]
0x180074c32  mov     dword ptr [rsp+140h+Size], eax
0x180074c36  test    ebx, ebx
0x180074c38  jnz     short loc_180074C57
0x180074c3a  cmp     r13d, 2
0x180074c3e  jb      loc_180074D42
0x180074c44  test    r15, r15
0x180074c47  jz      loc_180074D42
0x180074c4d  xor     esi, esi
0x180074c4f  mov     r14, r15
0x180074c52  jmp     loc_180074CFD
0x180074c57  cmp     ebx, esi
0x180074c59  jnz     loc_180074EEE
0x180074c5f  mov     rcx, gs:60h
0x180074c68  mov     r8, rax; Size
0x180074c6b  mov     edx, 8; Flags
0x180074c70  mov     rcx, [rcx+30h]; HeapHandle
0x180074c74  call    cs:__imp_RtlAllocateHeap
0x180074c7a  mov     rsi, rax
0x180074c7d  test    rax, rax
0x180074c80  jnz     short loc_180074C8C
0x180074c82  mov     ebx, 0C0000017h
0x180074c87  jmp     loc_1800750D2
0x180074c8c  mov     ecx, [rbp+40h+arg_40]
0x180074c92  lea     rax, [rsp+140h+Size]
0x180074c97  mov     r14, [rsp+140h+var_F8]
0x180074c9c  mov     r9d, dword ptr [rsp+140h+P]
0x180074ca1  mov     rdx, r14
0x180074ca4  mov     r8, [rsp+140h+var_C8]
0x180074ca9  mov     dword ptr [rsp+140h+var_108], ecx
0x180074cad  mov     rcx, [rsp+140h+var_F0]
0x180074cb2  mov     [rsp+140h+var_110], rax
0x180074cb7  lea     rax, [rsp+140h+var_D8]
0x180074cbc  mov     [rsp+140h+var_118], rsi
0x180074cc1  mov     [rsp+140h+StringSecurityDescriptorLen], rax
0x180074cc6  call    _CmGetDeviceRegProp
0x180074ccb  test    eax, eax
0x180074ccd  jns     short loc_180074CF3
0x180074ccf  mov     rcx, gs:60h
0x180074cd8  mov     r8, rsi; P
0x180074cdb  xor     edx, edx; Flags
0x180074cdd  mov     ebx, eax
0x180074cdf  mov     rcx, [rcx+30h]; HeapHandle
0x180074ce3  call    cs:__imp_RtlFreeHeap
0x180074ce9  mov     rsi, [rsp+140h+var_F0]
0x180074cee  jmp     loc_180074EF8
0x180074cf3  cmp     dword ptr [rsp+140h+Size], 2
0x180074cf8  jb      short loc_180074D22
0x180074cfa  mov     r14, rsi
0x180074cfd  mov     rcx, r14
0x180074d00  call    _PnpParseIndirectInfString
0x180074d05  test    al, al
0x180074d07  jnz     short loc_180074D15
0x180074d09  mov     rcx, r14
0x180074d0c  call    _PnpParseIndirectResourceString
0x180074d11  test    al, al
0x180074d13  jz      short loc_180074D1D
0x180074d15  mov     dword ptr [r12], 19h
0x180074d1d  test    rsi, rsi
0x180074d20  jz      short loc_180074D3A
0x180074d22  mov     rcx, gs:60h
0x180074d2b  mov     r8, rsi; P
0x180074d2e  xor     edx, edx; Flags
0x180074d30  mov     rcx, [rcx+30h]; HeapHandle
0x180074d34  call    cs:__imp_RtlFreeHeap
0x180074d3a  test    ebx, ebx
0x180074d3c  jnz     loc_180074EEE
0x180074d42  cmp     dword ptr [r12], 2012h
0x180074d4a  jnz     short loc_180074D68
0x180074d4c  mov     rcx, r15
0x180074d4f  call    _PnpMultiSzGetLen
0x180074d54  mov     r9d, eax
0x180074d57  mov     eax, [rdi]
0x180074d59  lea     rcx, [r9+r9]
0x180074d5d  cmp     rcx, rax
0x180074d60  ja      short loc_180074D8F
0x180074d62  lea     eax, [r9+r9]
0x180074d66  mov     [rdi], eax
0x180074d68  cmp     dword ptr [r12], 12h
0x180074d6d  jnz     loc_1800750D2
0x180074d73  cmp     dword ptr [rdi], 0
0x180074d76  jnz     loc_1800750D2
0x180074d7c  mov     dword ptr [rdi], 0
0x180074d82  mov     dword ptr [r12], 0
0x180074d8a  jmp     loc_180074F4F
0x180074d8f  mov     ebx, 0C00000E5h
0x180074d94  mov     dword ptr [rdi], 0
0x180074d9a  jmp     loc_1800750D2
0x180074d9f  mov     dword ptr [rsp+140h+var_108], r10d
0x180074da4  lea     rax, [rsp+140h+Size]
0x180074da9  mov     [rsp+140h+var_110], rax
0x180074dae  mov     r8, r11
0x180074db1  lea     rax, [rsp+140h+var_E8]
0x180074db6  mov     dword ptr [rsp+140h+Size], 4
0x180074dbe  mov     [rsp+140h+var_118], rax
0x180074dc3  mov     rdx, rbx
0x180074dc6  lea     rax, [rsp+140h+Size+4]
0x180074dcb  mov     rcx, rsi
0x180074dce  mov     [rsp+140h+StringSecurityDescriptorLen], rax
0x180074dd3  call    _CmGetDeviceRegProp
0x180074dd8  mov     ebx, eax
0x180074dda  test    eax, eax
0x180074ddc  js      loc_180074EF3
0x180074de2  mov     eax, [r14+10h]
0x180074de6  cmp     dword ptr [rsp+140h+Size+4], eax
0x180074dea  jnz     loc_180074B27
0x180074df0  mov     dword ptr [rdi], 1
0x180074df6  mov     eax, [r14+8]
0x180074dfa  mov     [r12], eax
0x180074dfe  cmp     r13d, [rdi]
0x180074e01  jnb     short loc_180074E0D
0x180074e03  mov     ebx, 0C0000023h
0x180074e08  jmp     loc_1800750D2
0x180074e0d  mov     eax, [rsp+140h+var_E8]
0x180074e11  neg     eax
0x180074e13  sbb     cl, cl
0x180074e15  mov     [r15], cl
0x180074e18  jmp     loc_1800750D2
0x180074e1d  mov     dword ptr [rsp+140h+var_108], r10d
0x180074e22  lea     rax, [rsp+140h+Size]
0x180074e27  mov     [rsp+140h+var_110], rax
0x180074e2c  mov     r9d, 18h
0x180074e32  lea     rax, [rsp+140h+Size+4]
0x180074e37  mov     [rsp+140h+var_118], 0
0x180074e40  mov     r8, r11
0x180074e43  mov     [rsp+140h+StringSecurityDescriptorLen], rax
0x180074e48  mov     rdx, rbx
0x180074e4b  mov     rcx, rsi
0x180074e4e  call    _CmGetDeviceRegProp
0x180074e53  mov     esi, 0C0000023h
0x180074e58  mov     ebx, eax
0x180074e5a  cmp     eax, esi
0x180074e5c  jnz     loc_180074EEE
0x180074e62  mov     rcx, gs:60h
0x180074e6b  mov     edx, 8; Flags
0x180074e70  mov     r8d, dword ptr [rsp+140h+Size]; Size
0x180074e75  mov     rcx, [rcx+30h]; HeapHandle
0x180074e79  call    cs:__imp_RtlAllocateHeap
0x180074e7f  mov     [rsp+140h+P], rax
0x180074e84  test    rax, rax
0x180074e87  jz      loc_180074C82
0x180074e8d  mov     ecx, [rbp+40h+arg_40]
0x180074e93  mov     r9d, 18h
0x180074e99  mov     r8, [rsp+140h+var_C8]
0x180074e9e  mov     rdx, [rsp+140h+var_F8]
0x180074ea3  mov     dword ptr [rsp+140h+var_108], ecx
0x180074ea7  lea     rcx, [rsp+140h+Size]
0x180074eac  mov     [rsp+140h+var_110], rcx
0x180074eb1  mov     rcx, [rsp+140h+var_F0]
0x180074eb6  mov     [rsp+140h+var_118], rax
0x180074ebb  lea     rax, [rsp+140h+Size+4]
0x180074ec0  mov     [rsp+140h+StringSecurityDescriptorLen], rax
0x180074ec5  call    _CmGetDeviceRegProp
0x180074eca  mov     ebx, eax
0x180074ecc  test    eax, eax
0x180074ece  jns     loc_180074F59
0x180074ed4  mov     rcx, gs:60h
0x180074edd  xor     edx, edx; Flags
0x180074edf  mov     r8, [rsp+140h+P]; P
0x180074ee4  mov     rcx, [rcx+30h]; HeapHandle
0x180074ee8  call    cs:__imp_RtlFreeHeap
0x180074eee  mov     rsi, [rsp+140h+var_F0]
0x180074ef3  mov     r14, [rsp+140h+var_F8]
0x180074ef8  mov     r15d, 0C0000001h
0x180074efe  mov     edi, 0C000000Eh
0x180074f03  cmp     ebx, edi
0x180074f05  jnz     loc_1800750D2
0x180074f0b  mov     [rsp+140h+var_108], 0
0x180074f14  lea     rax, [rbp+40h+Handle]
0x180074f18  mov     [rsp+140h+var_110], rax
0x180074f1d  mov     r8d, 10h
0x180074f23  mov     byte ptr [rsp+140h+var_118], 0
0x180074f28  mov     rdx, r14
0x180074f2b  mov     rcx, rsi
0x180074f2e  mov     dword ptr [rsp+140h+StringSecurityDescriptorLen], 1
0x180074f36  call    _CmOpenDeviceRegKey
0x180074f3b  mov     ebx, eax
0x180074f3d  test    eax, eax
0x180074f3f  jnz     loc_1800750C4
0x180074f45  mov     rcx, [rbp+40h+Handle]; Handle
0x180074f49  call    cs:__imp_NtClose
0x180074f4f  mov     ebx, 0C0000225h
0x180074f54  jmp     loc_1800750D2
0x180074f59  mov     rcx, [rsp+140h+P]; SecurityDescriptor
0x180074f5e  lea     rax, [rsp+140h+var_E4]
0x180074f63  mov     edx, 1; RequestedStringSDRevision
0x180074f68  mov     [rsp+140h+StringSecurityDescriptorLen], rax; StringSecurityDescriptorLen
0x180074f6d  lea     r9, [rsp+140h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180074f72  lea     r8d, [rdx+0Eh]; SecurityInformation
0x180074f76  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180074f7c  mov     rcx, gs:60h
  ... truncated ...
```
