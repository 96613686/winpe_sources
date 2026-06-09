# _CmSetDeviceMappedPropertyFromRegProp

- ea: `0x180078950`
- end: `0x180078b95`
- name: `_CmSetDeviceMappedPropertyFromRegProp`
- size: `581`
- prototype: `__int64 __fastcall(int, int, int, int, int, LPCWSTR StringSecurityDescriptor, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180078384`

## callees

- `0x18003bc80`
- `0x18006e694`
- `0x180078950`
- `0x18007ce08`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x180078ab9`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180078ab9`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180078aca`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180078aca`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180078aa7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180078aa7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078ad8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078b1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078ad8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078b1d`

## pseudocode

```c
__int64 __fastcall CmSetDeviceMappedPropertyFromRegProp(
        int a1,
        int a2,
        int a3,
        __int64 a4,
        unsigned int a5,
        LPCWSTR StringSecurityDescriptor,
        unsigned int a7)
{
  int v8; // r11d
  __int64 v9; // r8
  int v13; // edx
  DEVPROPKEY **v14; // rax
  DEVPROPKEY *v15; // r9
  __int64 v16; // rcx
  int v17; // ebx
  int v18; // edi
  int v19; // esi
  int *v20; // rax
  int v21; // ecx
  ULONG v23; // ebx
  PSECURITY_DESCRIPTOR v24; // rax
  _BYTE *v25; // rax
  int v26; // ecx
  unsigned __int64 v28; // [rsp+28h] [rbp-79h]
  int v29; // [rsp+30h] [rbp-71h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-61h] BYREF
  int v31; // [rsp+48h] [rbp-59h] BYREF
  _BYTE v32[80]; // [rsp+50h] [rbp-51h] BYREF

  v8 = *(_DWORD *)(a4 + 16);
  v9 = 0;
  v31 = 0;
  SecurityDescriptor = 0;
  v13 = 1;
  do
  {
    v14 = &CmDeviceRegPropMap + 3 * v9;
    v15 = *v14;
    if ( v8 == (*v14)->pid )
    {
      v16 = *(_QWORD *)a4 - *(_QWORD *)&v15->fmtid.Data1;
      if ( *(_QWORD *)a4 == *(_QWORD *)&v15->fmtid.Data1 )
        v16 = *(_QWORD *)(a4 + 8) - *(_QWORD *)v15->fmtid.Data4;
      if ( !v16 )
        break;
    }
    v14 = 0;
    v9 = (unsigned int)(v9 + 1);
  }
  while ( (unsigned int)v9 < 0x21 );
  if ( !v14 )
    return (unsigned int)-1073741264;
  if ( a5 != *((_DWORD *)v14 + 2) )
  {
    if ( a5 == 25 )
    {
      if ( *((_DWORD *)v14 + 2) != 18 )
        return (unsigned int)-1073741811;
    }
    else if ( a5 >= 2 )
    {
      return (unsigned int)-1073741811;
    }
  }
  v18 = *((_DWORD *)v14 + 3);
  v19 = *((_DWORD *)v14 + 4);
  if ( v18 == 9 )
    goto LABEL_36;
  if ( v18 != 25 )
  {
    if ( v18 == 27 )
    {
      if ( StringSecurityDescriptor )
      {
        if ( !a7 )
          return (unsigned int)-1073741811;
        if ( *(_BYTE *)StringSecurityDescriptor != 0xFF )
        {
          if ( *(_BYTE *)StringSecurityDescriptor )
            return (unsigned int)-1073741811;
          v13 = 0;
        }
        v31 = v13;
        v20 = &v31;
        v21 = 4;
      }
      else
      {
        v20 = 0;
        v21 = 0;
      }
      return (unsigned int)CmSetDeviceRegProp(a1, a2, a3, 27, v19, (__int64)v20, v21);
    }
    if ( v18 != 37 )
    {
      v29 = StringSecurityDescriptor != 0 ? a7 : 0;
      v28 = (unsigned __int64)StringSecurityDescriptor & -(__int64)(StringSecurityDescriptor != 0);
      return (unsigned int)CmSetDeviceRegProp(a1, a2, a3, v18, v19, v28, v29);
    }
LABEL_36:
    if ( StringSecurityDescriptor )
    {
      if ( a7 < 0x10 )
        return (unsigned int)-1073741811;
      v17 = PnpStringFromGuid(StringSecurityDescriptor, v32);
      if ( v17 < 0 )
        return (unsigned int)v17;
      v25 = v32;
      v26 = 78;
    }
    else
    {
      v25 = 0;
      v26 = 0;
    }
    v29 = v26;
    v28 = (unsigned __int64)v25;
    return (unsigned int)CmSetDeviceRegProp(a1, a2, a3, v18, v19, v28, v29);
  }
  if ( StringSecurityDescriptor )
  {
    if ( a7 < 2
      || !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
    {
      return (unsigned int)-1073741811;
    }
    v23 = RtlLengthSecurityDescriptor(SecurityDescriptor);
    if ( !RtlValidRelativeSecurityDescriptor(SecurityDescriptor, v23, 0) )
    {
      LocalFree(SecurityDescriptor);
      return (unsigned int)-1073741811;
    }
    v24 = SecurityDescriptor;
  }
  else
  {
    v24 = 0;
    v23 = 0;
  }
  v17 = CmSetDeviceRegProp(a1, a2, a3, 24, 3, (__int64)v24, v23);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180078950  push    rbp
0x180078952  push    rbx
0x180078953  push    rsi
0x180078954  push    rdi
0x180078955  push    r12
0x180078957  push    r14
0x180078959  push    r15
0x18007895b  lea     rbp, [rsp-0Fh]
0x180078960  sub     rsp, 0B0h
0x180078967  mov     rax, cs:__security_cookie
0x18007896e  xor     rax, rsp
0x180078971  mov     [rbp+3Fh+var_40], rax
0x180078975  mov     rbx, [rbp+3Fh+StringSecurityDescriptor]
0x180078979  mov     r12, r8
0x18007897c  mov     r11d, [r9+10h]
0x180078980  xor     r8d, r8d
0x180078983  mov     r15, rdx
0x180078986  mov     [rbp+3Fh+var_98], 0
0x18007898d  mov     r10, r9
0x180078990  mov     [rbp+3Fh+SecurityDescriptor], 0
0x180078998  mov     r14, rcx
0x18007899b  lea     edx, [r8+1]; StringSDRevision
0x18007899f  lea     rcx, [r8+r8*2]
0x1800789a3  lea     rax, _CmDeviceRegPropMap
0x1800789aa  lea     rax, [rax+rcx*8]
0x1800789ae  mov     r9, [rax]
0x1800789b1  cmp     r11d, [r9+10h]
0x1800789b5  jnz     short loc_1800789CC
0x1800789b7  mov     rcx, [r10]
0x1800789ba  sub     rcx, [r9]
0x1800789bd  jnz     short loc_1800789C7
0x1800789bf  mov     rcx, [r10+8]
0x1800789c3  sub     rcx, [r9+8]
0x1800789c7  test    rcx, rcx
0x1800789ca  jz      short loc_1800789D7
0x1800789cc  xor     eax, eax
0x1800789ce  add     r8d, edx
0x1800789d1  cmp     r8d, 21h ; '!'
0x1800789d5  jb      short loc_18007899F
0x1800789d7  test    rax, rax
0x1800789da  jnz     short loc_1800789E6
0x1800789dc  mov     ebx, 0C0000230h
0x1800789e1  jmp     loc_180078B75
0x1800789e6  mov     ecx, [rbp+3Fh+arg_20]
0x1800789e9  cmp     ecx, [rax+8]
0x1800789ec  jz      short loc_180078A08
0x1800789ee  cmp     ecx, 19h
0x1800789f1  jnz     short loc_180078A03
0x1800789f3  cmp     dword ptr [rax+8], 12h
0x1800789f7  jz      short loc_180078A08
0x1800789f9  mov     ebx, 0C000000Dh
0x1800789fe  jmp     loc_180078B75
0x180078a03  cmp     ecx, 2
0x180078a06  jnb     short loc_1800789F9
0x180078a08  mov     edi, [rax+0Ch]
0x180078a0b  mov     esi, [rax+10h]
0x180078a0e  cmp     edi, 9
0x180078a11  jz      loc_180078B25
0x180078a17  cmp     edi, 19h
0x180078a1a  jz      short loc_180078A8E
0x180078a1c  mov     r9d, 1Bh
0x180078a22  cmp     edi, r9d
0x180078a25  jz      short loc_180078A58
0x180078a27  cmp     edi, 25h ; '%'
0x180078a2a  jz      loc_180078B25
0x180078a30  mov     rax, rbx
0x180078a33  neg     rax
0x180078a36  mov     rax, rbx
0x180078a39  sbb     r11d, r11d
0x180078a3c  and     r11d, [rbp+3Fh+arg_30]
0x180078a40  neg     rax
0x180078a43  mov     [rsp+0E0h+var_B0], r11d
0x180078a48  sbb     r10, r10
0x180078a4b  and     r10, rbx
0x180078a4e  mov     [rsp+0E0h+var_B8], r10
0x180078a53  jmp     loc_180078B5E
0x180078a58  test    rbx, rbx
0x180078a5b  jz      short loc_180078A7C
0x180078a5d  cmp     [rbp+3Fh+arg_30], edx
0x180078a60  jb      short loc_1800789F9
0x180078a62  mov     al, [rbx]
0x180078a64  cmp     al, 0FFh
0x180078a66  jz      short loc_180078A6E
0x180078a68  test    al, al
0x180078a6a  jnz     short loc_1800789F9
0x180078a6c  xor     edx, edx
0x180078a6e  mov     [rbp+3Fh+var_98], edx
0x180078a71  lea     rax, [rbp+3Fh+var_98]
0x180078a75  mov     ecx, 4
0x180078a7a  jmp     short loc_180078A80
0x180078a7c  xor     eax, eax
0x180078a7e  xor     ecx, ecx
0x180078a80  mov     [rsp+0E0h+var_B0], ecx
0x180078a84  mov     [rsp+0E0h+var_B8], rax
0x180078a89  jmp     loc_180078B61
0x180078a8e  test    rbx, rbx
0x180078a91  jz      short loc_180078AE9
0x180078a93  cmp     [rbp+3Fh+arg_30], 2
0x180078a97  jb      loc_1800789F9
0x180078a9d  xor     r9d, r9d; SecurityDescriptorSize
0x180078aa0  lea     r8, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x180078aa4  mov     rcx, rbx; StringSecurityDescriptor
0x180078aa7  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180078aad  test    eax, eax
0x180078aaf  jz      loc_1800789F9
0x180078ab5  mov     rcx, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x180078ab9  call    cs:__imp_RtlLengthSecurityDescriptor
0x180078abf  mov     rcx, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptorInput
0x180078ac3  xor     r8d, r8d; RequiredInformation
0x180078ac6  mov     edx, eax; SecurityDescriptorLength
0x180078ac8  mov     ebx, eax
0x180078aca  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x180078ad0  test    al, al
0x180078ad2  jnz     short loc_180078AE3
0x180078ad4  mov     rcx, [rbp+3Fh+SecurityDescriptor]; hMem
0x180078ad8  call    cs:__imp_LocalFree
0x180078ade  jmp     loc_1800789F9
0x180078ae3  mov     rax, [rbp+3Fh+SecurityDescriptor]
0x180078ae7  jmp     short loc_180078AED
0x180078ae9  xor     eax, eax
0x180078aeb  xor     ebx, ebx
0x180078aed  mov     [rsp+0E0h+var_B0], ebx
0x180078af1  mov     r9d, 18h
0x180078af7  mov     [rsp+0E0h+var_B8], rax
0x180078afc  mov     r8, r12
0x180078aff  mov     rdx, r15
0x180078b02  mov     [rsp+0E0h+var_C0], 3
0x180078b0a  mov     rcx, r14
0x180078b0d  call    _CmSetDeviceRegProp
0x180078b12  mov     rcx, [rbp+3Fh+SecurityDescriptor]; hMem
0x180078b16  mov     ebx, eax
0x180078b18  test    rcx, rcx
0x180078b1b  jz      short loc_180078B75
0x180078b1d  call    cs:__imp_LocalFree
0x180078b23  jmp     short loc_180078B75
0x180078b25  test    rbx, rbx
0x180078b28  jz      short loc_180078B51
0x180078b2a  cmp     [rbp+3Fh+arg_30], 10h
0x180078b2e  jb      loc_1800789F9
0x180078b34  lea     rdx, [rbp+3Fh+var_90]
0x180078b38  mov     rcx, rbx
0x180078b3b  call    _PnpStringFromGuid
0x180078b40  mov     ebx, eax
0x180078b42  test    eax, eax
0x180078b44  js      short loc_180078B75
0x180078b46  lea     rax, [rbp+3Fh+var_90]
0x180078b4a  mov     ecx, 4Eh ; 'N'
0x180078b4f  jmp     short loc_180078B55
0x180078b51  xor     eax, eax
0x180078b53  xor     ecx, ecx
0x180078b55  mov     [rsp+0E0h+var_B0], ecx
0x180078b59  mov     [rsp+0E0h+var_B8], rax
0x180078b5e  mov     r9d, edi
0x180078b61  mov     r8, r12
0x180078b64  mov     [rsp+0E0h+var_C0], esi
0x180078b68  mov     rdx, r15
0x180078b6b  mov     rcx, r14
0x180078b6e  call    _CmSetDeviceRegProp
0x180078b73  mov     ebx, eax
0x180078b75  mov     eax, ebx
0x180078b77  mov     rcx, [rbp+3Fh+var_40]
0x180078b7b  xor     rcx, rsp; StackCookie
0x180078b7e  call    __security_check_cookie
0x180078b83  add     rsp, 0B0h
0x180078b8a  pop     r15
0x180078b8c  pop     r14
0x180078b8e  pop     r12
0x180078b90  pop     rdi
0x180078b91  pop     rsi
0x180078b92  pop     rbx
0x180078b93  pop     rbp
0x180078b94  retn
```
