# MfgInitSystem

- ea: `0x140c52768`
- end: `0x140c52ade`
- name: `MfgInitSystem`
- size: `886`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140c52ae4`

## callees

- `0x1403887e8`
- `0x1404033d0`
- `0x14042bfd0`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406dd620`
- `0x1406dd780`
- `0x1406ddfe0`
- `0x1406def60`
- `0x1406df940`
- `0x140bb1410`
- `0x140c52768`

## string_xrefs

- `0x140c52855`: `System\CurrentControlSet\Control\ManufacturingMode\`
- `0x140c52861`: `\registry\machine\`
- `0x140c52a3b`: `\registry\machine\`

## pseudocode

```c
__int64 __fastcall MfgInitSystem(__int64 a1)
{
  NTSTATUS inited; // ebx
  __int64 v2; // rdi
  unsigned __int16 v3; // ax
  void *Pool2; // rax
  __int64 v5; // rax
  HANDLE v7; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE Handle; // [rsp+80h] [rbp-80h] BYREF
  UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  UNICODE_STRING ValueName; // [rsp+98h] [rbp-68h] BYREF
  WCHAR pszDest[256]; // [rsp+B0h] [rbp-50h] BYREF

  Handle = 0;
  ExpManufacturingInformation = 0;
  qword_140EED050 = 0;
  inited = 0;
  v2 = *(_QWORD *)(a1 + 240);
  v7 = 0;
  DestinationString = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  ValueName = 0;
  v3 = *(_WORD *)(v2 + 2840);
  if ( !v3 )
    return (unsigned int)inited;
  if ( v3 >= 0x80u )
    return (unsigned int)-1073741811;
  DWORD2(ExpManufacturingInformation) = *(_DWORD *)(v2 + 2840);
  Pool2 = (void *)ExAllocatePool2(256, WORD5(ExpManufacturingInformation), 1348953677);
  qword_140EED050 = Pool2;
  if ( Pool2 )
  {
    inited = RtlStringCbCopyW(
               (NTSTRSAFE_PWSTR)Pool2,
               WORD5(ExpManufacturingInformation),
               *(NTSTRSAFE_PCWSTR *)(v2 + 2848));
    if ( inited < 0 )
      goto LABEL_21;
    inited = RtlStringCbPrintfW(
               pszDest,
               0x200u,
               L"%s%s",
               L"\\registry\\machine\\",
               L"System\\CurrentControlSet\\Control\\ManufacturingMode\\");
    if ( inited < 0 )
      goto LABEL_21;
    inited = RtlInitUnicodeStringEx(&DestinationString, pszDest);
    if ( inited < 0 )
      goto LABEL_21;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    inited = ZwOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
    if ( inited < 0 )
      goto LABEL_21;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = KeyHandle;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)((char *)&ExpManufacturingInformation + 8);
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    inited = ZwOpenKey(&Handle, 0xF003Fu, &ObjectAttributes);
    if ( inited < 0 )
      goto LABEL_21;
    ZwClose(Handle);
    LODWORD(ExpManufacturingInformation) = ExpManufacturingInformation | 1;
    RtlInitUnicodeStringEx(&ValueName, L"LastProfile");
    inited = ZwSetValueKey(KeyHandle, &ValueName, 0, 1u, qword_140EED050, WORD5(ExpManufacturingInformation));
    if ( inited < 0 )
      goto LABEL_21;
    inited = RtlInitUnicodeStringEx(&DestinationString, L"Current");
    if ( inited < 0 )
      goto LABEL_21;
    ObjectAttributes.RootDirectory = KeyHandle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 832;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwOpenKeyEx(&v7, 0xF003Fu, &ObjectAttributes, 8u) >= 0 )
    {
      inited = ZwDeleteKey(v7);
      if ( inited < 0 )
        goto LABEL_21;
      ZwClose(v7);
      v7 = 0;
    }
    inited = ZwCreateKey(&v7, 0xF003Fu, &ObjectAttributes, 0, 0, 3u, 0);
    if ( inited >= 0 )
    {
      inited = RtlStringCbPrintfW(
                 pszDest,
                 0x200u,
                 L"%s%s%wZ",
                 L"\\registry\\machine\\",
                 L"System\\CurrentControlSet\\Control\\ManufacturingMode\\",
                 (char *)&ExpManufacturingInformation + 8);
      if ( inited >= 0 )
      {
        v5 = -1;
        do
          ++v5;
        while ( pszDest[v5] );
        inited = ZwSetValueKey(v7, &CmSymbolicLinkValueName, 0, 6u, pszDest, 2 * v5);
      }
    }
    goto LABEL_21;
  }
  inited = -1073741670;
LABEL_21:
  if ( v7 )
    ZwClose(v7);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140c52768  push    rbp
0x140c5276a  push    rbx
0x140c5276b  push    rsi
0x140c5276c  push    rdi
0x140c5276d  push    r13
0x140c5276f  push    r15
0x140c52771  lea     rbp, [rsp-1C8h]
0x140c52779  sub     rsp, 2C8h
0x140c52780  mov     rax, cs:__security_cookie
0x140c52787  xor     rax, rsp
0x140c5278a  mov     [rbp+1F0h+var_40], rax
0x140c52791  xorps   xmm0, xmm0
0x140c52794  xor     esi, esi
0x140c52796  xor     eax, eax
0x140c52798  mov     [rbp+1F0h+Handle], rsi
0x140c5279c  movups  cs:ExpManufacturingInformation, xmm0
0x140c527a3  mov     cs:qword_140EED050, rax
0x140c527aa  mov     ebx, esi
0x140c527ac  mov     rdi, [rcx+0F0h]
0x140c527b3  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.ObjectName], xmm0
0x140c527b8  mov     [rsp+2F0h+var_2B0], rsi
0x140c527bd  movups  xmmword ptr [rbp+1F0h+DestinationString.Length], xmm0
0x140c527c1  mov     [rsp+2F0h+KeyHandle], rsi
0x140c527c6  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.Length], xmm0
0x140c527cb  movups  xmmword ptr [rsp+2F0h+ObjectAttributes+1Ch], xmm0
0x140c527d0  movups  xmmword ptr [rbp+1F0h+ValueName.Length], xmm0
0x140c527d4  movzx   eax, word ptr [rdi+0B18h]
0x140c527db  test    ax, ax
0x140c527de  jz      loc_140C52ABC
0x140c527e4  mov     ecx, 80h
0x140c527e9  cmp     ax, cx
0x140c527ec  jb      short loc_140C527F8
0x140c527ee  mov     ebx, 0C000000Dh
0x140c527f3  jmp     loc_140C52ABC
0x140c527f8  mov     word ptr cs:ExpManufacturingInformation+8, ax
0x140c527ff  mov     ecx, 100h
0x140c52804  movzx   eax, word ptr [rdi+0B1Ah]
0x140c5280b  mov     r8d, 5067664Dh
0x140c52811  mov     edx, eax
0x140c52813  mov     word ptr cs:ExpManufacturingInformation+0Ah, ax
0x140c5281a  call    ExAllocatePool2
0x140c5281f  mov     cs:qword_140EED050, rax
0x140c52826  test    rax, rax
0x140c52829  jnz     short loc_140C52835
0x140c5282b  mov     ebx, 0C000009Ah
0x140c52830  jmp     loc_140C52A9E
0x140c52835  movzx   edx, word ptr cs:ExpManufacturingInformation+0Ah; cbDest
0x140c5283c  mov     rcx, rax; pszDest
0x140c5283f  mov     r8, [rdi+0B20h]; pszSrc
0x140c52846  call    RtlStringCbCopyW
0x140c5284b  mov     ebx, eax
0x140c5284d  test    eax, eax
0x140c5284f  js      loc_140C52A9E
0x140c52855  lea     r13, aSystemCurrentc_12; "System\\CurrentControlSet\\Control\\Man"...
0x140c5285c  mov     edx, 200h; cbDest
0x140c52861  lea     r9, aRegistryMachin_111; "\\registry\\machine\\"
0x140c52868  mov     [rsp+2F0h+Data], r13
0x140c5286d  lea     r8, aSS_1; "%s%s"
0x140c52874  lea     rcx, [rbp+1F0h+pszDest]; pszDest
0x140c52878  call    RtlStringCbPrintfW
0x140c5287d  mov     ebx, eax
0x140c5287f  test    eax, eax
0x140c52881  js      loc_140C52A9E
0x140c52887  lea     rdx, [rbp+1F0h+pszDest]; SourceString
0x140c5288b  lea     rcx, [rbp+1F0h+DestinationString]; DestinationString
0x140c5288f  call    RtlInitUnicodeStringEx
0x140c52894  mov     ebx, eax
0x140c52896  test    eax, eax
0x140c52898  js      loc_140C52A9E
0x140c5289e  lea     rax, [rbp+1F0h+DestinationString]
0x140c528a2  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x140c528aa  xorps   xmm0, xmm0
0x140c528ad  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], rsi
0x140c528b2  mov     edi, 0F003Fh
0x140c528b7  mov     [rsp+2F0h+ObjectAttributes.ObjectName], rax
0x140c528bc  mov     r15d, 240h
0x140c528c2  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x140c528c7  mov     edx, edi; DesiredAccess
0x140c528c9  mov     [rsp+2F0h+ObjectAttributes.Attributes], r15d
0x140c528ce  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x140c528d3  movdqu  xmmword ptr [rsp+2F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140c528d9  call    ZwOpenKey
0x140c528de  mov     ebx, eax
0x140c528e0  test    eax, eax
0x140c528e2  js      loc_140C52A9E
0x140c528e8  mov     rax, [rsp+2F0h+KeyHandle]
0x140c528ed  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x140c528f2  mov     [rsp+2F0h+ObjectAttributes.Attributes], r15d
0x140c528f7  lea     rcx, [rbp+1F0h+Handle]; KeyHandle
0x140c528fb  xorps   xmm0, xmm0
0x140c528fe  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x140c52906  lea     r15, ExpManufacturingInformation+8
0x140c5290d  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], rax
0x140c52912  mov     edx, edi; DesiredAccess
0x140c52914  mov     [rsp+2F0h+ObjectAttributes.ObjectName], r15
0x140c52919  movdqu  xmmword ptr [rsp+2F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140c5291f  call    ZwOpenKey
0x140c52924  mov     ebx, eax
0x140c52926  test    eax, eax
0x140c52928  js      loc_140C52A9E
0x140c5292e  mov     rcx, [rbp+1F0h+Handle]; Handle
0x140c52932  call    ZwClose
0x140c52937  or      dword ptr cs:ExpManufacturingInformation, 1
0x140c5293e  lea     rdx, aLastprofile; "LastProfile"
0x140c52945  lea     rcx, [rbp+1F0h+ValueName]; DestinationString
0x140c52949  call    RtlInitUnicodeStringEx
0x140c5294e  movzx   eax, word ptr cs:ExpManufacturingInformation+0Ah
0x140c52955  lea     rdx, [rbp+1F0h+ValueName]; ValueName
0x140c52959  mov     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x140c5295e  mov     r9d, 1; Type
0x140c52964  mov     [rsp+2F0h+DataSize], eax; DataSize
0x140c52968  xor     r8d, r8d; TitleIndex
0x140c5296b  mov     rax, cs:qword_140EED050
0x140c52972  mov     [rsp+2F0h+Data], rax; Data
0x140c52977  call    ZwSetValueKey
0x140c5297c  mov     ebx, eax
0x140c5297e  test    eax, eax
0x140c52980  js      loc_140C52A9E
0x140c52986  lea     rdx, aCurrent_1; "Current"
0x140c5298d  lea     rcx, [rbp+1F0h+DestinationString]; DestinationString
0x140c52991  call    RtlInitUnicodeStringEx
0x140c52996  mov     ebx, eax
0x140c52998  test    eax, eax
0x140c5299a  js      loc_140C52A9E
0x140c529a0  mov     rax, [rsp+2F0h+KeyHandle]
0x140c529a5  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x140c529aa  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], rax
0x140c529af  lea     rcx, [rsp+2F0h+var_2B0]; KeyHandle
0x140c529b4  lea     rax, [rbp+1F0h+DestinationString]
0x140c529b8  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x140c529c0  xorps   xmm0, xmm0
0x140c529c3  mov     [rsp+2F0h+ObjectAttributes.ObjectName], rax
0x140c529c8  mov     r9d, 8; OpenOptions
0x140c529ce  mov     [rsp+2F0h+ObjectAttributes.Attributes], 340h
0x140c529d6  mov     edx, edi; DesiredAccess
0x140c529d8  movdqu  xmmword ptr [rsp+2F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140c529de  call    ZwOpenKeyEx
0x140c529e3  test    eax, eax
0x140c529e5  js      short loc_140C52A0A
0x140c529e7  mov     rcx, [rsp+2F0h+var_2B0]; KeyHandle
0x140c529ec  call    ZwDeleteKey
0x140c529f1  mov     ebx, eax
0x140c529f3  test    eax, eax
0x140c529f5  js      loc_140C52A9E
0x140c529fb  mov     rcx, [rsp+2F0h+var_2B0]; Handle
0x140c52a00  call    ZwClose
0x140c52a05  mov     [rsp+2F0h+var_2B0], rsi
0x140c52a0a  mov     [rsp+2F0h+Disposition], rsi; Disposition
0x140c52a0f  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x140c52a14  mov     [rsp+2F0h+DataSize], 3; CreateOptions
0x140c52a1c  lea     rcx, [rsp+2F0h+var_2B0]; KeyHandle
0x140c52a21  xor     r9d, r9d; TitleIndex
0x140c52a24  mov     [rsp+2F0h+Data], rsi; Class
0x140c52a29  mov     edx, edi; DesiredAccess
0x140c52a2b  call    ZwCreateKey
0x140c52a30  mov     ebx, eax
0x140c52a32  test    eax, eax
0x140c52a34  js      short loc_140C52A9E
0x140c52a36  mov     qword ptr [rsp+2F0h+DataSize], r15
0x140c52a3b  lea     r9, aRegistryMachin_111; "\\registry\\machine\\"
0x140c52a42  lea     r8, aSSWz; "%s%s%wZ"
0x140c52a49  mov     [rsp+2F0h+Data], r13
0x140c52a4e  mov     edx, 200h; cbDest
0x140c52a53  lea     rcx, [rbp+1F0h+pszDest]; pszDest
0x140c52a57  call    RtlStringCbPrintfW
0x140c52a5c  mov     ebx, eax
0x140c52a5e  test    eax, eax
0x140c52a60  js      short loc_140C52A9E
0x140c52a62  lea     rcx, [rbp+1F0h+pszDest]
0x140c52a66  or      rax, 0FFFFFFFFFFFFFFFFh
0x140c52a6a  inc     rax
0x140c52a6d  cmp     [rcx+rax*2], si
0x140c52a71  jnz     short loc_140C52A6A
0x140c52a73  mov     rcx, [rsp+2F0h+var_2B0]; KeyHandle
0x140c52a78  lea     rdx, CmSymbolicLinkValueName; ValueName
0x140c52a7f  add     eax, eax
0x140c52a81  mov     r9d, 6; Type
0x140c52a87  mov     [rsp+2F0h+DataSize], eax; DataSize
0x140c52a8b  xor     r8d, r8d; TitleIndex
0x140c52a8e  lea     rax, [rbp+1F0h+pszDest]
0x140c52a92  mov     [rsp+2F0h+Data], rax; Data
0x140c52a97  call    ZwSetValueKey
0x140c52a9c  mov     ebx, eax
0x140c52a9e  mov     rcx, [rsp+2F0h+var_2B0]; Handle
0x140c52aa3  test    rcx, rcx
0x140c52aa6  jz      short loc_140C52AAD
0x140c52aa8  call    ZwClose
0x140c52aad  mov     rcx, [rsp+2F0h+KeyHandle]; Handle
0x140c52ab2  test    rcx, rcx
0x140c52ab5  jz      short loc_140C52ABC
0x140c52ab7  call    ZwClose
0x140c52abc  mov     eax, ebx
0x140c52abe  mov     rcx, [rbp+1F0h+var_40]
0x140c52ac5  xor     rcx, rsp; StackCookie
0x140c52ac8  call    __security_check_cookie
0x140c52acd  add     rsp, 2C8h
0x140c52ad4  pop     r15
0x140c52ad6  pop     r13
0x140c52ad8  pop     rdi
0x140c52ad9  pop     rsi
0x140c52ada  pop     rbx
0x140c52adb  pop     rbp
0x140c52adc  retn
```
