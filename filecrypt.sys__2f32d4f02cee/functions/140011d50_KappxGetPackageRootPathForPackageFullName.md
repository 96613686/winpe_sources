# KappxGetPackageRootPathForPackageFullName

- ea: `0x140011d50`
- end: `0x140011fd7`
- name: `KappxGetPackageRootPathForPackageFullName`
- size: `647`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140011a30`

## callees

- `0x140001110`
- `0x1400011f0`
- `0x1400012b0`
- `0x140003540`
- `0x140011d50`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x140011f27`
- `ntoskrnl!ZwQueryValueKey` at `0x140011f27`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011fc6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011fc6`
- `ntoskrnl!ExAllocatePool2` at `0x140011e0e`
- `ntoskrnl!ExAllocatePool2` at `0x140011e0e`
- `ntoskrnl!ZwOpenKey` at `0x140011eeb`
- `ntoskrnl!ZwOpenKey` at `0x140011eeb`
- `ntoskrnl!ZwClose` at `0x140011fb0`
- `ntoskrnl!ZwClose` at `0x140011fb0`

## string_xrefs

- `0x140011d91`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\Appx`

## pseudocode

```c
__int64 __fastcall KappxGetPackageRootPathForPackageFullName(STRSAFE_PCNZWCH *a1, wchar_t **a2)
{
  size_t v4; // rsi
  wchar_t *Pool2; // rax
  wchar_t *v6; // rbx
  NTSTATUS v7; // edi
  ULONG ResultLength[2]; // [rsp+38h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD v11[2]; // [rsp+48h] [rbp-C0h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+58h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES v13; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+98h] [rbp-70h] BYREF
  int v15; // [rsp+9Ch] [rbp-6Ch]
  int v16; // [rsp+A0h] [rbp-68h]
  unsigned int v17; // [rsp+A4h] [rbp-64h]

  v11[0] = 8519808;
  *(_QWORD *)&ValueName.Length = 1572886;
  KeyHandle = 0;
  v11[1] = L"\\Registry\\Machine\\Software\\Microsoft\\Windows\\CurrentVersion\\Appx";
  ResultLength[0] = 0;
  ValueName.Buffer = L"PackageRoot";
  memset(&v13, 0, 44);
  if ( !*(_WORD *)a1 )
    return 3221225524LL;
  if ( g_PackageRoot )
    goto LABEL_3;
  v13.Length = 48;
  v13.ObjectName = (PUNICODE_STRING)v11;
  v13.RootDirectory = 0;
  v13.Attributes = 576;
  v6 = 0;
  *(_OWORD *)&v13.SecurityDescriptor = 0;
  v7 = ZwOpenKey(&KeyHandle, 0x2000000u, &v13);
  if ( v7 >= 0 )
  {
    v7 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, KeyValueInformation, 0x210u, ResultLength);
    if ( v7 >= 0 )
    {
      if ( v15 != 1 || v17 < 4 || *(_WORD *)&KeyValueInformation[v16 - 2 + v17] )
      {
        v7 = -1073739509;
      }
      else
      {
        g_PackageRootLength = v17 + 10;
        v7 = RtlStringCbPrintfW(&g_PackageRoot, 0x104u, L"\\??\\%ws\\");
        if ( v7 >= 0 )
        {
LABEL_3:
          v4 = g_PackageRootLength + 2 + (unsigned int)*(unsigned __int16 *)a1;
          Pool2 = (wchar_t *)ExAllocatePool2(256, v4, 1483763777);
          v6 = Pool2;
          if ( Pool2 )
          {
            v7 = RtlStringCbCopyW(Pool2, (unsigned int)v4, &g_PackageRoot);
            if ( v7 >= 0 )
            {
              v7 = RtlStringCbCatNW(v6, v4, a1[1], *(unsigned __int16 *)a1);
              if ( v7 >= 0 )
              {
                *a2 = v6;
                v6 = 0;
              }
            }
          }
          else
          {
            v7 = -1073741801;
          }
          goto LABEL_5;
        }
        g_PackageRootLength = 0;
        g_PackageRoot = 0;
      }
    }
  }
LABEL_5:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140011d50  mov     r11, rsp
0x140011d53  push    rbp
0x140011d54  push    r12
0x140011d56  push    r14
0x140011d58  push    r15
0x140011d5a  lea     rbp, [r11-1D8h]
0x140011d61  sub     rsp, 2B8h
0x140011d68  mov     rax, cs:__security_cookie
0x140011d6f  xor     rax, rsp
0x140011d72  mov     [rbp+1D0h+var_30], rax
0x140011d79  xorps   xmm0, xmm0
0x140011d7c  mov     [rsp+2D0h+var_290], 820080h
0x140011d85  xor     r12d, r12d
0x140011d88  mov     qword ptr [rsp+2D0h+ValueName.Length], 180016h
0x140011d91  lea     rax, aRegistryMachin_3; "\\Registry\\Machine\\Software\\Microsof"...
0x140011d98  mov     [rsp+2D0h+KeyHandle], r12
0x140011d9d  mov     [rsp+2D0h+var_288], rax
0x140011da2  mov     r15, rdx
0x140011da5  lea     rax, aPackageroot; "PackageRoot"
0x140011dac  mov     [rsp+2D0h+var_2A0], r12d
0x140011db1  mov     [rsp+2D0h+ValueName.Buffer], rax
0x140011db6  mov     r14, rcx
0x140011db9  xor     eax, eax
0x140011dbb  movups  xmmword ptr [rsp+2D0h+var_270+10h], xmm0
0x140011dc0  movups  xmmword ptr [rsp+2D0h+var_270], xmm0
0x140011dc5  movups  xmmword ptr [rsp+2D0h+var_270+1Ch], xmm0
0x140011dca  cmp     [rcx], ax
0x140011dcd  jz      loc_140011EAE
0x140011dd3  cmp     cs:g_PackageRoot, ax
0x140011dda  mov     [r11+18h], rbx
0x140011dde  mov     [r11-28h], rdi
0x140011de2  jz      loc_140011EB5
0x140011de8  movzx   ecx, word ptr [r14]
0x140011dec  mov     r8d, 58707041h
0x140011df2  mov     eax, cs:g_PackageRootLength
0x140011df8  add     eax, 2
0x140011dfb  mov     [rsp+2D0h+arg_18], rsi
0x140011e03  add     ecx, eax
0x140011e05  mov     esi, ecx
0x140011e07  mov     edx, ecx
0x140011e09  mov     ecx, 100h
0x140011e0e  call    cs:__imp_ExAllocatePool2
0x140011e15  nop     dword ptr [rax+rax+00h]
0x140011e1a  mov     rbx, rax
0x140011e1d  test    rax, rax
0x140011e20  jz      loc_140011F9C
0x140011e26  lea     r8, g_PackageRoot; pszSrc
0x140011e2d  mov     edx, esi; cbDest
0x140011e2f  mov     rcx, rax; pszDest
0x140011e32  call    RtlStringCbCopyW
0x140011e37  mov     edi, eax
0x140011e39  test    eax, eax
0x140011e3b  jns     short loc_140011E8D
0x140011e3d  mov     rsi, [rsp+2D0h+arg_18]
0x140011e45  mov     rcx, [rsp+2D0h+KeyHandle]; Handle
0x140011e4a  test    rcx, rcx
0x140011e4d  jnz     loc_140011FB0
0x140011e53  test    rbx, rbx
0x140011e56  jnz     loc_140011FC1
0x140011e5c  mov     rbx, [rsp+2D0h+arg_10]
0x140011e64  mov     eax, edi
0x140011e66  mov     rdi, [rsp+2B0h]
0x140011e6e  mov     rcx, [rbp+1D0h+var_30]
0x140011e75  xor     rcx, rsp; StackCookie
0x140011e78  call    __security_check_cookie
0x140011e7d  add     rsp, 2B8h
0x140011e84  pop     r15
0x140011e86  pop     r14
0x140011e88  pop     r12
0x140011e8a  pop     rbp
0x140011e8b  retn
0x140011e8d  movzx   r9d, word ptr [r14]; cbToAppend
0x140011e91  mov     rdx, rsi; cbDest
0x140011e94  mov     r8, [r14+8]; pszSrc
0x140011e98  mov     rcx, rbx; pszDest
0x140011e9b  call    RtlStringCbCatNW
0x140011ea0  mov     edi, eax
0x140011ea2  test    eax, eax
0x140011ea4  js      short loc_140011E3D
0x140011ea6  mov     [r15], rbx
0x140011ea9  mov     rbx, r12
0x140011eac  jmp     short loc_140011E3D
0x140011eae  mov     eax, 0C0000034h
0x140011eb3  jmp     short loc_140011E6E
0x140011eb5  lea     rax, [rsp+2D0h+var_290]
0x140011eba  mov     dword ptr [rsp+2D0h+var_270], 30h ; '0'
0x140011ec2  lea     r8, [rsp+2D0h+var_270]; ObjectAttributes
0x140011ec7  mov     qword ptr [rsp+2D0h+var_270+10h], rax
0x140011ecc  mov     edx, 2000000h; DesiredAccess
0x140011ed1  mov     qword ptr [rsp+2D0h+var_270+8], r12
0x140011ed6  lea     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x140011edb  mov     dword ptr [rsp+2D0h+var_270+18h], 240h
0x140011ee3  mov     rbx, r12
0x140011ee6  movdqu  xmmword ptr [rbp+1D0h+var_270+20h], xmm0
0x140011eeb  call    cs:__imp_ZwOpenKey
0x140011ef2  nop     dword ptr [rax+rax+00h]
0x140011ef7  mov     edi, eax
0x140011ef9  test    eax, eax
0x140011efb  js      loc_140011E45
0x140011f01  mov     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x140011f06  lea     rax, [rsp+2D0h+var_2A0]
0x140011f0b  mov     [rsp+2D0h+ResultLength], rax; ResultLength
0x140011f10  lea     r9, [rbp+1D0h+KeyValueInformation]; KeyValueInformation
0x140011f14  mov     r8d, 1; KeyValueInformationClass
0x140011f1a  mov     [rsp+2D0h+Length], 210h; Length
0x140011f22  lea     rdx, [rsp+2D0h+ValueName]; ValueName
0x140011f27  call    cs:__imp_ZwQueryValueKey
0x140011f2e  nop     dword ptr [rax+rax+00h]
0x140011f33  mov     edi, eax
0x140011f35  test    eax, eax
0x140011f37  js      loc_140011E45
0x140011f3d  cmp     [rbp+1D0h+var_23C], 1
0x140011f41  jnz     short loc_140011FA6
0x140011f43  mov     ecx, [rbp+1D0h+var_234]
0x140011f46  cmp     ecx, 4
0x140011f49  jb      short loc_140011FA6
0x140011f4b  mov     eax, [rbp+1D0h+var_238]
0x140011f4e  lea     r9, [rbp+1D0h+KeyValueInformation]
0x140011f52  add     r9, rax
0x140011f55  cmp     [rcx+r9-2], bx
0x140011f5b  jnz     short loc_140011FA6
0x140011f5d  lea     eax, [rcx+0Ah]
0x140011f60  mov     edx, 104h; cbDest
0x140011f65  lea     rcx, g_PackageRoot; pszDest
0x140011f6c  mov     cs:g_PackageRootLength, eax
0x140011f72  lea     r8, aWs; "\\??\\%ws\\"
0x140011f79  call    RtlStringCbPrintfW
0x140011f7e  mov     edi, eax
0x140011f80  test    eax, eax
0x140011f82  jns     loc_140011DE8
0x140011f88  mov     cs:g_PackageRootLength, r12d
0x140011f8f  mov     cs:g_PackageRoot, r12w
0x140011f97  jmp     loc_140011E45
0x140011f9c  mov     edi, 0C0000017h
0x140011fa1  jmp     loc_140011E3D
0x140011fa6  mov     edi, 0C000090Bh
0x140011fab  jmp     loc_140011E45
0x140011fb0  call    cs:__imp_ZwClose
0x140011fb7  nop     dword ptr [rax+rax+00h]
0x140011fbc  jmp     loc_140011E53
0x140011fc1  xor     edx, edx; Tag
0x140011fc3  mov     rcx, rbx; P
0x140011fc6  call    cs:__imp_ExFreePoolWithTag
0x140011fcd  nop     dword ptr [rax+rax+00h]
0x140011fd2  jmp     loc_140011E5C
```
