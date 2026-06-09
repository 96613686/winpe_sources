# _CmSetDeviceRegPropWorker

- ea: `0x18006e7f8`
- end: `0x18006ea14`
- name: `_CmSetDeviceRegPropWorker`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006e694`

## callees

- `0x18001ef4c`
- `0x180021c38`
- `0x180067444`
- `0x18006ab38`
- `0x18006abdc`
- `0x18006d4c4`
- `0x18006e058`
- `0x18006e7f8`
- `0x18006f098`
- `0x18006f164`

## import_xrefs

- `ntdll!NtClose` at `0x18006e9fd`
- `ntdll!NtClose` at `0x18006e9fd`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18006e8c5`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18006e8c5`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18006e8b8`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18006e8b8`

## pseudocode

```c
__int64 __fastcall CmSetDeviceRegPropWorker(
        __int64 a1,
        const WCHAR *a2,
        void *a3,
        unsigned int a4,
        unsigned int a5,
        _DWORD *a6,
        ULONG SecurityDescriptorLength,
        __int16 a8)
{
  int v11; // r12d
  int v12; // ebx
  _DWORD *v13; // rbp
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  HANDLE v19; // rdx
  int v20; // eax
  int v21; // r9d
  int v22; // eax
  HANDLE Handle[9]; // [rsp+40h] [rbp-48h] BYREF

  Handle[0] = 0;
  v11 = a1;
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
  if ( a4 - 1 > 0x24 || !(unsigned __int8)CmDevicePropertyRead(a1, a4) )
    goto LABEL_47;
  if ( !(unsigned __int8)CmDevicePropertyWrite(v14, a4) )
    return (unsigned int)-1073741790;
  v15 = MapCmDevicePropertyToRegType(a4);
  if ( !v15 )
    return (unsigned int)-1073741264;
  if ( a5 != v15 )
    return (unsigned int)-1073741811;
  if ( a4 == 8 )
  {
    if ( SecurityDescriptorLength <= 0x40 )
      goto LABEL_27;
    return (unsigned int)-1073741811;
  }
  if ( a4 != 11 )
  {
    if ( a4 == 24
      && SecurityDescriptorLength
      && (!RtlValidRelativeSecurityDescriptor(v13, SecurityDescriptorLength, 0)
       || RtlLengthSecurityDescriptor(v13) != SecurityDescriptorLength) )
    {
      v12 = -1073741811;
      goto LABEL_48;
    }
    goto LABEL_27;
  }
  if ( !SecurityDescriptorLength )
    goto LABEL_27;
  if ( !v13 || SecurityDescriptorLength != 4 )
    return (unsigned int)-1073741811;
  if ( *v13 && (unsigned __int8)CmIsRootDevice(a2) )
  {
    v12 = -1073741808;
    goto LABEL_48;
  }
LABEL_27:
  v12 = 0;
  if ( !a3 )
  {
    v12 = CmOpenDeviceRegKey(v11, (_DWORD)a2, 16, 0, 33554434, 0, (__int64)Handle, 0);
    if ( v12 < 0 )
      goto LABEL_48;
  }
  if ( a4 == 8 )
  {
LABEL_38:
    v21 = (int)Handle[0];
    if ( a3 )
      v21 = (int)a3;
    CmRaisePropertyChangeEvent(v11, (_DWORD)a2, 1, v21, a4);
    goto LABEL_48;
  }
  v17 = MapCmDevicePropertyToRegValue(v16, a4);
  if ( !v17 )
  {
LABEL_47:
    v12 = -1073741264;
    goto LABEL_48;
  }
  v19 = Handle[0];
  if ( SecurityDescriptorLength )
  {
    if ( a3 )
      v19 = a3;
    v22 = PnpCtxRegSetValue(v18, v19, v17, a5, v13, SecurityDescriptorLength);
    if ( v22 == -1073741444 )
    {
      v12 = -1073741810;
      goto LABEL_48;
    }
    if ( v22 < 0 )
    {
      v12 = v22;
      goto LABEL_48;
    }
  }
  else
  {
    if ( a3 )
      v19 = a3;
    v20 = PnpCtxRegDeleteValue(v18, v19, v17);
    v12 = v20;
    if ( v20 == -1073741772 || v20 == -1073741444 )
      v12 = -1073741275;
  }
  if ( v12 >= 0 )
    goto LABEL_38;
LABEL_48:
  if ( Handle[0] )
    NtClose(Handle[0]);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18006e7f8  push    rbx
0x18006e7fa  push    rbp
0x18006e7fb  push    rsi
0x18006e7fc  push    rdi
0x18006e7fd  push    r12
0x18006e7ff  push    r14
0x18006e801  push    r15
0x18006e803  sub     rsp, 50h
0x18006e807  movzx   eax, [rsp+88h+arg_38]
0x18006e80f  mov     edi, r9d
0x18006e812  mov     [rsp+88h+Handle], 0
0x18006e81b  mov     r14, r8
0x18006e81e  mov     r15, rdx
0x18006e821  mov     r12, rcx
0x18006e824  test    eax, eax
0x18006e826  jz      short loc_18006E832
0x18006e828  mov     ebx, 0C000000Dh
0x18006e82d  jmp     loc_18006EA03
0x18006e832  mov     esi, [rsp+88h+SecurityDescriptorLength]
0x18006e839  test    esi, esi
0x18006e83b  jnz     short loc_18006E841
0x18006e83d  xor     ebp, ebp
0x18006e83f  jmp     short loc_18006E84E
0x18006e841  mov     rbp, [rsp+88h+arg_28]
0x18006e849  test    rbp, rbp
0x18006e84c  jz      short loc_18006E828
0x18006e84e  lea     eax, [r9-1]
0x18006e852  cmp     eax, 24h ; '$'
0x18006e855  ja      loc_18006E9EE
0x18006e85b  mov     edx, edi
0x18006e85d  call    _CmDevicePropertyRead
0x18006e862  test    al, al
0x18006e864  jz      loc_18006E9EE
0x18006e86a  mov     edx, edi
0x18006e86c  call    _CmDevicePropertyWrite
0x18006e871  test    al, al
0x18006e873  jnz     short loc_18006E87F
0x18006e875  mov     ebx, 0C0000022h
0x18006e87a  jmp     loc_18006EA03
0x18006e87f  mov     ecx, edi
0x18006e881  call    _MapCmDevicePropertyToRegType
0x18006e886  test    eax, eax
0x18006e888  jnz     short loc_18006E894
0x18006e88a  mov     ebx, 0C0000230h
0x18006e88f  jmp     loc_18006EA03
0x18006e894  cmp     [rsp+88h+arg_20], eax
0x18006e89b  jnz     short loc_18006E828
0x18006e89d  cmp     edi, 8
0x18006e8a0  jz      short loc_18006E90B
0x18006e8a2  cmp     edi, 0Bh
0x18006e8a5  jz      short loc_18006E8D9
0x18006e8a7  cmp     edi, 18h
0x18006e8aa  jnz     short loc_18006E914
0x18006e8ac  test    esi, esi
0x18006e8ae  jz      short loc_18006E914
0x18006e8b0  xor     r8d, r8d; RequiredInformation
0x18006e8b3  mov     edx, esi; SecurityDescriptorLength
0x18006e8b5  mov     rcx, rbp; SecurityDescriptorInput
0x18006e8b8  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x18006e8be  test    al, al
0x18006e8c0  jz      short loc_18006E8CF
0x18006e8c2  mov     rcx, rbp; SecurityDescriptor
0x18006e8c5  call    cs:__imp_RtlLengthSecurityDescriptor
0x18006e8cb  cmp     eax, esi
0x18006e8cd  jz      short loc_18006E914
0x18006e8cf  mov     ebx, 0C000000Dh
0x18006e8d4  jmp     loc_18006E9F3
0x18006e8d9  test    esi, esi
0x18006e8db  jz      short loc_18006E914
0x18006e8dd  test    rbp, rbp
0x18006e8e0  jz      loc_18006E828
0x18006e8e6  cmp     esi, 4
0x18006e8e9  jnz     loc_18006E828
0x18006e8ef  cmp     dword ptr [rbp+0], 0
0x18006e8f3  jz      short loc_18006E914
0x18006e8f5  mov     rcx, r15; SourceString
0x18006e8f8  call    _CmIsRootDevice
0x18006e8fd  test    al, al
0x18006e8ff  jz      short loc_18006E914
0x18006e901  mov     ebx, 0C0000010h
0x18006e906  jmp     loc_18006E9F3
0x18006e90b  cmp     esi, 40h ; '@'
0x18006e90e  ja      loc_18006E828
0x18006e914  xor     ebx, ebx
0x18006e916  test    r14, r14
0x18006e919  jnz     short loc_18006E952
0x18006e91b  mov     [rsp+88h+var_50], rbx
0x18006e920  lea     rax, [rsp+88h+Handle]
0x18006e925  mov     [rsp+88h+var_58], rax
0x18006e92a  lea     r8d, [rbx+10h]
0x18006e92e  mov     byte ptr [rsp+88h+var_60], bl
0x18006e932  xor     r9d, r9d
0x18006e935  mov     rdx, r15
0x18006e938  mov     dword ptr [rsp+88h+var_68], 2000002h
0x18006e940  mov     rcx, r12
0x18006e943  call    _CmOpenDeviceRegKey
0x18006e948  mov     ebx, eax
0x18006e94a  test    eax, eax
0x18006e94c  js      loc_18006E9F3
0x18006e952  cmp     edi, 8
0x18006e955  jz      short loc_18006E998
0x18006e957  mov     edx, edi
0x18006e959  call    _MapCmDevicePropertyToRegValue
0x18006e95e  test    rax, rax
0x18006e961  jz      loc_18006E9EE
0x18006e967  mov     rdx, [rsp+88h+Handle]
0x18006e96c  mov     r8, rax
0x18006e96f  test    esi, esi
0x18006e971  jnz     short loc_18006E9BB
0x18006e973  test    r14, r14
0x18006e976  cmovnz  rdx, r14
0x18006e97a  call    _PnpCtxRegDeleteValue
0x18006e97f  mov     ebx, eax
0x18006e981  cmp     eax, 0C0000034h
0x18006e986  jz      short loc_18006E98F
0x18006e988  cmp     eax, 0C000017Ch
0x18006e98d  jnz     short loc_18006E994
0x18006e98f  mov     ebx, 0C0000225h
0x18006e994  test    ebx, ebx
0x18006e996  js      short loc_18006E9F3
0x18006e998  mov     r9, [rsp+88h+Handle]
0x18006e99d  test    r14, r14
0x18006e9a0  mov     r8d, 1
0x18006e9a6  mov     dword ptr [rsp+88h+var_68], edi
0x18006e9aa  cmovnz  r9, r14
0x18006e9ae  mov     rdx, r15
0x18006e9b1  mov     rcx, r12
0x18006e9b4  call    _CmRaisePropertyChangeEvent
0x18006e9b9  jmp     short loc_18006E9F3
0x18006e9bb  mov     r9d, [rsp+88h+arg_20]
0x18006e9c3  test    r14, r14
0x18006e9c6  mov     [rsp+88h+var_60], esi
0x18006e9ca  cmovnz  rdx, r14
0x18006e9ce  mov     [rsp+88h+var_68], rbp
0x18006e9d3  call    _PnpCtxRegSetValue
0x18006e9d8  cmp     eax, 0C000017Ch
0x18006e9dd  jnz     short loc_18006E9E6
0x18006e9df  mov     ebx, 0C000000Eh
0x18006e9e4  jmp     short loc_18006E9F3
0x18006e9e6  test    eax, eax
0x18006e9e8  jns     short loc_18006E994
0x18006e9ea  mov     ebx, eax
0x18006e9ec  jmp     short loc_18006E9F3
0x18006e9ee  mov     ebx, 0C0000230h
0x18006e9f3  mov     rcx, [rsp+88h+Handle]; Handle
0x18006e9f8  test    rcx, rcx
0x18006e9fb  jz      short loc_18006EA03
0x18006e9fd  call    cs:__imp_NtClose
0x18006ea03  mov     eax, ebx
0x18006ea05  add     rsp, 50h
0x18006ea09  pop     r15
0x18006ea0b  pop     r14
0x18006ea0d  pop     r12
0x18006ea0f  pop     rdi
0x18006ea10  pop     rsi
0x18006ea11  pop     rbp
0x18006ea12  pop     rbx
0x18006ea13  retn
```
