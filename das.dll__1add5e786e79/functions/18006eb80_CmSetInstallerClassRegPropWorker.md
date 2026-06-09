# _CmSetInstallerClassRegPropWorker

- ea: `0x18006eb80`
- end: `0x18006edfa`
- name: `_CmSetInstallerClassRegPropWorker`
- size: `634`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, ULONG SecurityDescriptorLength, __int16)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006ea1c`

## callees

- `0x1800037f0`
- `0x18001ef4c`
- `0x180021c38`
- `0x180067444`
- `0x180067ff4`
- `0x18006e60c`
- `0x18006eb80`
- `0x18006f024`

## import_xrefs

- `ntdll!NtClose` at `0x18006edd3`
- `ntdll!NtClose` at `0x18006ede3`
- `ntdll!NtClose` at `0x18006edd3`
- `ntdll!NtClose` at `0x18006ede3`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18006ec8e`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18006ec8e`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18006ec81`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18006ec81`

## pseudocode

```c
__int64 __fastcall CmSetInstallerClassRegPropWorker(
        int a1,
        int a2,
        void *a3,
        unsigned int a4,
        unsigned int a5,
        void *a6,
        ULONG SecurityDescriptorLength,
        __int16 a8)
{
  int v12; // ebx
  void *v13; // rbp
  int v14; // r8d
  int v15; // r9d
  int v16; // eax
  int v17; // edx
  HANDLE v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  int v21; // eax
  int v22; // r9d
  int v23; // eax
  int v25; // [rsp+28h] [rbp-60h]
  HANDLE v26; // [rsp+40h] [rbp-48h] BYREF
  HANDLE Handle[8]; // [rsp+48h] [rbp-40h] BYREF

  v26 = 0;
  Handle[0] = 0;
  if ( a8 )
    return (unsigned int)-1073741811;
  if ( SecurityDescriptorLength )
  {
    v13 = a6;
    if ( !a6 )
      return (unsigned int)-1073741811;
  }
  else
  {
    v13 = 0;
  }
  if ( a4 - 1 > 0x24 || !(unsigned __int8)CmClassPropertyRead(a4) )
    goto LABEL_54;
  if ( !(unsigned __int8)CmClassPropertyRead(a4) )
    return (unsigned int)-1073741790;
  switch ( a4 )
  {
    case 8u:
    case 0xDu:
      v16 = 1;
      break;
    case 0x12u:
    case 0x13u:
      v16 = 7;
      break;
    case 0x18u:
      v16 = 3;
      break;
    default:
      if ( a4 != 26 && a4 - 27 >= 2 )
        return (unsigned int)-1073741264;
      v16 = 4;
      break;
  }
  if ( a5 != v16 )
    return (unsigned int)-1073741811;
  if ( a4 == 8 )
  {
    if ( SecurityDescriptorLength <= 0x40 )
      goto LABEL_30;
    return (unsigned int)-1073741811;
  }
  if ( a4 != 24
    || !SecurityDescriptorLength
    || RtlValidRelativeSecurityDescriptor(v13, SecurityDescriptorLength, 0)
    && RtlLengthSecurityDescriptor(v13) == SecurityDescriptorLength )
  {
LABEL_30:
    v12 = 0;
    if ( !a3 )
    {
      v12 = CmOpenInstallerClassRegKey(a1, a2, v14, v15, 33554438, 0, (__int64)&v26, 0);
      if ( v12 < 0 )
        goto LABEL_55;
    }
    if ( a4 == 8 || a4 == 13 || a4 - 18 < 2 )
    {
      v18 = a3;
      if ( !a3 )
        v18 = v26;
    }
    else
    {
      v17 = (int)v26;
      if ( a3 )
        v17 = (int)a3;
      v12 = PnpOpenPropertiesKey(a1, v17, 0, 2, 1, v25, (__int64)Handle);
      if ( v12 < 0 )
        goto LABEL_55;
      v18 = Handle[0];
    }
    v19 = MapCmClassPropertyToRegValue(v18, a4);
    if ( v19 )
    {
      if ( SecurityDescriptorLength )
      {
        v23 = PnpCtxRegSetValue(v20, v20, v19, a5, v13, SecurityDescriptorLength);
        if ( v23 == -1073741444 )
        {
          v12 = -1073741772;
          goto LABEL_55;
        }
        if ( v23 < 0 )
        {
          v12 = v23;
          goto LABEL_55;
        }
      }
      else
      {
        v21 = PnpCtxRegDeleteValue(v20, v20, v19);
        v12 = v21;
        if ( v21 == -1073741772 || v21 == -1073741444 )
          v12 = -1073741275;
        if ( v12 < 0 )
          goto LABEL_55;
      }
      v22 = (int)v26;
      if ( a3 )
        v22 = (int)a3;
      CmRaisePropertyChangeEvent(a1, a2, 2, v22, a4);
      goto LABEL_55;
    }
LABEL_54:
    v12 = -1073741264;
    goto LABEL_55;
  }
  v12 = -1073741811;
LABEL_55:
  if ( Handle[0] )
    NtClose(Handle[0]);
  if ( v26 )
    NtClose(v26);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18006eb80  push    rbx
0x18006eb82  push    rbp
0x18006eb83  push    rsi
0x18006eb84  push    rdi
0x18006eb85  push    r12
0x18006eb87  push    r14
0x18006eb89  push    r15
0x18006eb8b  sub     rsp, 50h
0x18006eb8f  movzx   eax, [rsp+88h+arg_38]
0x18006eb97  mov     edi, r9d
0x18006eb9a  mov     [rsp+88h+var_48], 0
0x18006eba3  mov     r14, r8
0x18006eba6  mov     [rsp+88h+Handle], 0
0x18006ebaf  mov     r12, rdx
0x18006ebb2  mov     r15, rcx
0x18006ebb5  test    eax, eax
0x18006ebb7  jz      short loc_18006EBC3
0x18006ebb9  mov     ebx, 0C000000Dh
0x18006ebbe  jmp     loc_18006EDE9
0x18006ebc3  mov     esi, [rsp+88h+SecurityDescriptorLength]
0x18006ebca  test    esi, esi
0x18006ebcc  jnz     short loc_18006EBD2
0x18006ebce  xor     ebp, ebp
0x18006ebd0  jmp     short loc_18006EBDF
0x18006ebd2  mov     rbp, [rsp+88h+arg_28]
0x18006ebda  test    rbp, rbp
0x18006ebdd  jz      short loc_18006EBB9
0x18006ebdf  lea     eax, [r9-1]
0x18006ebe3  cmp     eax, 24h ; '$'
0x18006ebe6  ja      loc_18006EDC4
0x18006ebec  mov     ecx, edi
0x18006ebee  call    _CmClassPropertyRead
0x18006ebf3  test    al, al
0x18006ebf5  jz      loc_18006EDC4
0x18006ebfb  mov     ecx, edi
0x18006ebfd  call    _CmClassPropertyRead
0x18006ec02  test    al, al
0x18006ec04  jnz     short loc_18006EC10
0x18006ec06  mov     ebx, 0C0000022h
0x18006ec0b  jmp     loc_18006EDE9
0x18006ec10  mov     ecx, edi
0x18006ec12  sub     ecx, 8
0x18006ec15  jz      short loc_18006EC59
0x18006ec17  sub     ecx, 5
0x18006ec1a  jz      short loc_18006EC59
0x18006ec1c  sub     ecx, 5
0x18006ec1f  jz      short loc_18006EC52
0x18006ec21  sub     ecx, 1
0x18006ec24  jz      short loc_18006EC52
0x18006ec26  sub     ecx, 5
0x18006ec29  jz      short loc_18006EC4B
0x18006ec2b  sub     ecx, 2
0x18006ec2e  jz      short loc_18006EC44
0x18006ec30  sub     ecx, 1
0x18006ec33  jz      short loc_18006EC44
0x18006ec35  cmp     ecx, 1
0x18006ec38  jz      short loc_18006EC44
0x18006ec3a  mov     ebx, 0C0000230h
0x18006ec3f  jmp     loc_18006EDE9
0x18006ec44  mov     eax, 4
0x18006ec49  jmp     short loc_18006EC5E
0x18006ec4b  mov     eax, 3
0x18006ec50  jmp     short loc_18006EC5E
0x18006ec52  mov     eax, 7
0x18006ec57  jmp     short loc_18006EC5E
0x18006ec59  mov     eax, 1
0x18006ec5e  cmp     [rsp+88h+arg_20], eax
0x18006ec65  jnz     loc_18006EBB9
0x18006ec6b  cmp     edi, 8
0x18006ec6e  jz      short loc_18006ECA2
0x18006ec70  cmp     edi, 18h
0x18006ec73  jnz     short loc_18006ECAB
0x18006ec75  test    esi, esi
0x18006ec77  jz      short loc_18006ECAB
0x18006ec79  xor     r8d, r8d; RequiredInformation
0x18006ec7c  mov     edx, esi; SecurityDescriptorLength
0x18006ec7e  mov     rcx, rbp; SecurityDescriptorInput
0x18006ec81  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x18006ec87  test    al, al
0x18006ec89  jz      short loc_18006EC98
0x18006ec8b  mov     rcx, rbp; SecurityDescriptor
0x18006ec8e  call    cs:__imp_RtlLengthSecurityDescriptor
0x18006ec94  cmp     eax, esi
0x18006ec96  jz      short loc_18006ECAB
0x18006ec98  mov     ebx, 0C000000Dh
0x18006ec9d  jmp     loc_18006EDC9
0x18006eca2  cmp     esi, 40h ; '@'
0x18006eca5  ja      loc_18006EBB9
0x18006ecab  xor     ebx, ebx
0x18006ecad  test    r14, r14
0x18006ecb0  jnz     short loc_18006ECE2
0x18006ecb2  mov     [rsp+88h+var_50], rbx
0x18006ecb7  lea     rax, [rsp+88h+var_48]
0x18006ecbc  mov     [rsp+88h+var_58], rax
0x18006ecc1  mov     rdx, r12
0x18006ecc4  mov     byte ptr [rsp+88h+var_60], bl
0x18006ecc8  mov     rcx, r15
0x18006eccb  mov     dword ptr [rsp+88h+var_68], 2000006h
0x18006ecd3  call    _CmOpenInstallerClassRegKey
0x18006ecd8  mov     ebx, eax
0x18006ecda  test    eax, eax
0x18006ecdc  js      loc_18006EDC9
0x18006ece2  mov     eax, edi
0x18006ece4  sub     eax, 8
0x18006ece7  jz      short loc_18006ED35
0x18006ece9  sub     eax, 5
0x18006ecec  jz      short loc_18006ED35
0x18006ecee  sub     eax, 5
0x18006ecf1  jz      short loc_18006ED35
0x18006ecf3  cmp     eax, 1
0x18006ecf6  jz      short loc_18006ED35
0x18006ecf8  mov     rdx, [rsp+88h+var_48]
0x18006ecfd  lea     rax, [rsp+88h+Handle]
0x18006ed02  mov     [rsp+88h+var_58], rax
0x18006ed07  test    r14, r14
0x18006ed0a  mov     r9d, 2
0x18006ed10  mov     byte ptr [rsp+88h+var_68], 1
0x18006ed15  cmovnz  rdx, r14
0x18006ed19  mov     rcx, r15
0x18006ed1c  xor     r8d, r8d
0x18006ed1f  call    _PnpOpenPropertiesKey
0x18006ed24  mov     ebx, eax
0x18006ed26  test    eax, eax
0x18006ed28  js      loc_18006EDC9
0x18006ed2e  mov     rcx, [rsp+88h+Handle]
0x18006ed33  jmp     short loc_18006ED41
0x18006ed35  test    r14, r14
0x18006ed38  mov     rcx, r14
0x18006ed3b  cmovz   rcx, [rsp+88h+var_48]
0x18006ed41  mov     edx, edi
0x18006ed43  call    _MapCmClassPropertyToRegValue
0x18006ed48  test    rax, rax
0x18006ed4b  jz      short loc_18006EDC4
0x18006ed4d  mov     r8, rax
0x18006ed50  mov     rdx, rcx
0x18006ed53  test    esi, esi
0x18006ed55  jnz     short loc_18006ED98
0x18006ed57  call    _PnpCtxRegDeleteValue
0x18006ed5c  mov     ebx, eax
0x18006ed5e  cmp     eax, 0C0000034h
0x18006ed63  jz      short loc_18006ED6C
0x18006ed65  cmp     eax, 0C000017Ch
0x18006ed6a  jnz     short loc_18006ED71
0x18006ed6c  mov     ebx, 0C0000225h
0x18006ed71  test    ebx, ebx
0x18006ed73  js      short loc_18006EDC9
0x18006ed75  mov     r9, [rsp+88h+var_48]
0x18006ed7a  test    r14, r14
0x18006ed7d  mov     r8d, 2
0x18006ed83  mov     dword ptr [rsp+88h+var_68], edi
0x18006ed87  cmovnz  r9, r14
0x18006ed8b  mov     rdx, r12
0x18006ed8e  mov     rcx, r15
0x18006ed91  call    _CmRaisePropertyChangeEvent
0x18006ed96  jmp     short loc_18006EDC9
0x18006ed98  mov     r9d, [rsp+88h+arg_20]
0x18006eda0  mov     [rsp+88h+var_60], esi
0x18006eda4  mov     [rsp+88h+var_68], rbp
0x18006eda9  call    _PnpCtxRegSetValue
0x18006edae  cmp     eax, 0C000017Ch
0x18006edb3  jnz     short loc_18006EDBC
0x18006edb5  mov     ebx, 0C0000034h
0x18006edba  jmp     short loc_18006EDC9
0x18006edbc  test    eax, eax
0x18006edbe  jns     short loc_18006ED75
0x18006edc0  mov     ebx, eax
0x18006edc2  jmp     short loc_18006EDC9
0x18006edc4  mov     ebx, 0C0000230h
0x18006edc9  mov     rcx, [rsp+88h+Handle]; Handle
0x18006edce  test    rcx, rcx
0x18006edd1  jz      short loc_18006EDD9
0x18006edd3  call    cs:__imp_NtClose
0x18006edd9  mov     rcx, [rsp+88h+var_48]; Handle
0x18006edde  test    rcx, rcx
0x18006ede1  jz      short loc_18006EDE9
0x18006ede3  call    cs:__imp_NtClose
0x18006ede9  mov     eax, ebx
0x18006edeb  add     rsp, 50h
0x18006edef  pop     r15
0x18006edf1  pop     r14
0x18006edf3  pop     r12
0x18006edf5  pop     rdi
0x18006edf6  pop     rsi
0x18006edf7  pop     rbp
0x18006edf8  pop     rbx
0x18006edf9  retn
```
