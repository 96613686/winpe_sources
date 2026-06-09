# _CmSetInstallerClassMappedPropertyFromRegProp

- ea: `0x180078e30`
- end: `0x180079018`
- name: `_CmSetInstallerClassMappedPropertyFromRegProp`
- size: `488`
- prototype: `__int64 __fastcall(int, int, int, int, int, LPCWSTR StringSecurityDescriptor, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180078b9c`

## callees

- `0x18006ea1c`
- `0x180078e30`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x180078f9f`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180078f9f`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180078fb1`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180078fb1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180078f8c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180078f8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078fc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079007`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078fc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079007`

## pseudocode

```c
__int64 __fastcall CmSetInstallerClassMappedPropertyFromRegProp(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        LPCWSTR StringSecurityDescriptor,
        unsigned int a7)
{
  int v7; // ebx
  __int64 v8; // r10
  int v11; // edx
  DEVPROPKEY **v12; // rax
  DEVPROPKEY *v13; // r8
  __int64 v14; // rcx
  unsigned int v15; // ebx
  int v16; // r9d
  int v17; // r8d
  LPCWSTR v19; // rax
  int v20; // ecx
  ULONG v21; // ebx
  PSECURITY_DESCRIPTOR v22; // rax
  int v24; // [rsp+40h] [rbp-38h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-30h] BYREF

  v7 = *(_DWORD *)(a4 + 16);
  v8 = 0;
  v24 = 0;
  SecurityDescriptor = 0;
  v11 = 1;
  do
  {
    v12 = &CmClassRegPropMap + 3 * v8;
    v13 = *v12;
    if ( v7 == (*v12)->pid )
    {
      v14 = *(_QWORD *)a4 - *(_QWORD *)&v13->fmtid.Data1;
      if ( *(_QWORD *)a4 == *(_QWORD *)&v13->fmtid.Data1 )
        v14 = *(_QWORD *)(a4 + 8) - *(_QWORD *)v13->fmtid.Data4;
      if ( !v14 )
        break;
    }
    v12 = 0;
    v8 = (unsigned int)(v8 + 1);
  }
  while ( (unsigned int)v8 < 9 );
  if ( !v12 )
    return (unsigned int)-1073741264;
  if ( a5 != *((_DWORD *)v12 + 2) )
  {
    if ( a5 == 25 )
    {
      if ( *((_DWORD *)v12 + 2) != 18 )
        return (unsigned int)-1073741811;
    }
    else if ( a5 >= 2 )
    {
      return (unsigned int)-1073741811;
    }
  }
  v16 = *((_DWORD *)v12 + 3);
  if ( v16 != 25 )
  {
    v17 = *((_DWORD *)v12 + 4);
    if ( v16 == 27 )
    {
      v19 = StringSecurityDescriptor;
      if ( StringSecurityDescriptor )
      {
        if ( !a7 )
          return (unsigned int)-1073741811;
        if ( *(_BYTE *)StringSecurityDescriptor != 0xFF )
        {
          if ( *(_BYTE *)StringSecurityDescriptor )
            return (unsigned int)-1073741811;
          v11 = 0;
        }
        v24 = v11;
        v19 = (LPCWSTR)&v24;
        v20 = 4;
      }
      else
      {
        v20 = 0;
      }
      return (unsigned int)CmSetInstallerClassRegProp(a1, a2, v17, (__int64)v19, v20);
    }
    else
    {
      return (unsigned int)CmSetInstallerClassRegProp(
                             a1,
                             a2,
                             v17,
                             (__int64)StringSecurityDescriptor,
                             StringSecurityDescriptor != 0 ? a7 : 0);
    }
  }
  if ( StringSecurityDescriptor )
  {
    if ( a7 < 2
      || !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
    {
      return (unsigned int)-1073741811;
    }
    v21 = RtlLengthSecurityDescriptor(SecurityDescriptor);
    if ( !RtlValidRelativeSecurityDescriptor(SecurityDescriptor, v21, 0) )
    {
      LocalFree(SecurityDescriptor);
      return (unsigned int)-1073741811;
    }
    v22 = SecurityDescriptor;
  }
  else
  {
    v22 = 0;
    v21 = 0;
  }
  v15 = CmSetInstallerClassRegProp(a1, a2, 3, (__int64)v22, v21);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v15;
}

```

## disassembly

```asm
0x180078e30  push    rbx
0x180078e32  push    rbp
0x180078e33  push    rsi
0x180078e34  push    rdi
0x180078e35  sub     rsp, 58h
0x180078e39  mov     ebx, [r9+10h]
0x180078e3d  xor     r10d, r10d
0x180078e40  mov     rsi, rdx
0x180078e43  mov     [rsp+78h+var_38], 0
0x180078e4b  mov     r11, r9
0x180078e4e  mov     [rsp+78h+SecurityDescriptor], 0
0x180078e57  mov     rdi, r8
0x180078e5a  mov     rbp, rcx
0x180078e5d  lea     edx, [r10+1]; StringSDRevision
0x180078e61  lea     r9, [r10+r10*2]
0x180078e65  lea     rax, _CmClassRegPropMap
0x180078e6c  lea     rax, [rax+r9*8]
0x180078e70  mov     r8, [rax]
0x180078e73  cmp     ebx, [r8+10h]
0x180078e77  jnz     short loc_180078E8E
0x180078e79  mov     rcx, [r11]
0x180078e7c  sub     rcx, [r8]
0x180078e7f  jnz     short loc_180078E89
0x180078e81  mov     rcx, [r11+8]
0x180078e85  sub     rcx, [r8+8]
0x180078e89  test    rcx, rcx
0x180078e8c  jz      short loc_180078E99
0x180078e8e  xor     eax, eax
0x180078e90  add     r10d, edx
0x180078e93  cmp     r10d, 9
0x180078e97  jb      short loc_180078E61
0x180078e99  test    rax, rax
0x180078e9c  jnz     short loc_180078EA8
0x180078e9e  mov     ebx, 0C0000230h
0x180078ea3  jmp     loc_18007900D
0x180078ea8  mov     ecx, [rsp+78h+arg_20]
0x180078eaf  cmp     ecx, [rax+8]
0x180078eb2  jz      short loc_180078ECE
0x180078eb4  cmp     ecx, 19h
0x180078eb7  jnz     short loc_180078EC9
0x180078eb9  cmp     dword ptr [rax+8], 12h
0x180078ebd  jz      short loc_180078ECE
0x180078ebf  mov     ebx, 0C000000Dh
0x180078ec4  jmp     loc_18007900D
0x180078ec9  cmp     ecx, 2
0x180078ecc  jnb     short loc_180078EBF
0x180078ece  mov     r9d, [rax+0Ch]
0x180078ed2  cmp     r9d, 19h
0x180078ed6  jz      loc_180078F69
0x180078edc  mov     r8d, [rax+10h]
0x180078ee0  cmp     r9d, 1Bh
0x180078ee4  jz      short loc_180078F20
0x180078ee6  mov     rdx, [rsp+78h+StringSecurityDescriptor]
0x180078eee  mov     rax, rdx
0x180078ef1  neg     rax
0x180078ef4  sbb     ecx, ecx
0x180078ef6  and     ecx, [rsp+78h+arg_30]
0x180078efd  mov     [rsp+78h+var_48], ecx
0x180078f01  mov     [rsp+78h+var_50], rdx
0x180078f06  mov     [rsp+78h+var_58], r8d
0x180078f0b  mov     rdx, rsi
0x180078f0e  mov     r8, rdi
0x180078f11  mov     rcx, rbp
0x180078f14  call    _CmSetInstallerClassRegProp
0x180078f19  mov     ebx, eax
0x180078f1b  jmp     loc_18007900D
0x180078f20  mov     rax, [rsp+78h+StringSecurityDescriptor]
0x180078f28  test    rax, rax
0x180078f2b  jz      short loc_180078F56
0x180078f2d  cmp     [rsp+78h+arg_30], edx
0x180078f34  jb      short loc_180078EBF
0x180078f36  mov     al, [rax]
0x180078f38  cmp     al, 0FFh
0x180078f3a  jz      short loc_180078F46
0x180078f3c  test    al, al
0x180078f3e  jnz     loc_180078EBF
0x180078f44  xor     edx, edx
0x180078f46  mov     [rsp+78h+var_38], edx
0x180078f4a  lea     rax, [rsp+78h+var_38]
0x180078f4f  mov     ecx, 4
0x180078f54  jmp     short loc_180078F58
0x180078f56  xor     ecx, ecx
0x180078f58  mov     [rsp+78h+var_48], ecx
0x180078f5c  mov     r9d, 1Bh
0x180078f62  mov     [rsp+78h+var_50], rax
0x180078f67  jmp     short loc_180078F06
0x180078f69  mov     rcx, [rsp+78h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180078f71  test    rcx, rcx
0x180078f74  jz      short loc_180078FD2
0x180078f76  cmp     [rsp+78h+arg_30], 2
0x180078f7e  jb      loc_180078EBF
0x180078f84  xor     r9d, r9d; SecurityDescriptorSize
0x180078f87  lea     r8, [rsp+78h+SecurityDescriptor]; SecurityDescriptor
0x180078f8c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180078f92  test    eax, eax
0x180078f94  jz      loc_180078EBF
0x180078f9a  mov     rcx, [rsp+78h+SecurityDescriptor]; SecurityDescriptor
0x180078f9f  call    cs:__imp_RtlLengthSecurityDescriptor
0x180078fa5  mov     rcx, [rsp+78h+SecurityDescriptor]; SecurityDescriptorInput
0x180078faa  xor     r8d, r8d; RequiredInformation
0x180078fad  mov     edx, eax; SecurityDescriptorLength
0x180078faf  mov     ebx, eax
0x180078fb1  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x180078fb7  test    al, al
0x180078fb9  jnz     short loc_180078FCB
0x180078fbb  mov     rcx, [rsp+78h+SecurityDescriptor]; hMem
0x180078fc0  call    cs:__imp_LocalFree
0x180078fc6  jmp     loc_180078EBF
0x180078fcb  mov     rax, [rsp+78h+SecurityDescriptor]
0x180078fd0  jmp     short loc_180078FD6
0x180078fd2  xor     eax, eax
0x180078fd4  xor     ebx, ebx
0x180078fd6  mov     [rsp+78h+var_48], ebx
0x180078fda  mov     r9d, 18h
0x180078fe0  mov     [rsp+78h+var_50], rax
0x180078fe5  mov     r8, rdi
0x180078fe8  mov     rdx, rsi
0x180078feb  mov     [rsp+78h+var_58], 3
0x180078ff3  mov     rcx, rbp
0x180078ff6  call    _CmSetInstallerClassRegProp
0x180078ffb  mov     rcx, [rsp+78h+SecurityDescriptor]; hMem
0x180079000  mov     ebx, eax
0x180079002  test    rcx, rcx
0x180079005  jz      short loc_18007900D
0x180079007  call    cs:__imp_LocalFree
0x18007900d  mov     eax, ebx
0x18007900f  add     rsp, 58h
0x180079013  pop     rdi
0x180079014  pop     rsi
0x180079015  pop     rbp
0x180079016  pop     rbx
0x180079017  retn
```
