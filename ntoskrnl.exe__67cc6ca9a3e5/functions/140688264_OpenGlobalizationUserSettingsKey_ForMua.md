# OpenGlobalizationUserSettingsKey_ForMua

- ea: `0x140688264`
- end: `0x1406884fb`
- name: `OpenGlobalizationUserSettingsKey_ForMua`
- size: `663`
- prototype: `__int64 __fastcall(__int64, __int64, HANDLE *, _DWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1404c5a90`

## callees

- `0x1403f4770`
- `0x1403f4830`
- `0x140688264`
- `0x140688504`
- `0x1406d9d70`
- `0x1406daa70`
- `0x1406daad0`
- `0x1406dacb0`
- `0x140866770`
- `0x1408eeff0`
- `0x140973560`
- `0x140bae410`
- `0x140bae8e0`

## string_xrefs

- `0x14068836e`: `TargetNtPath`
- `0x140688353`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\International`

## pseudocode

```c
__int64 __fastcall OpenGlobalizationUserSettingsKey_ForMua(__int64 a1, __int64 a2, HANDLE *a3, _DWORD *a4)
{
  void *Pool2; // r15
  __int64 v7; // rcx
  int InformationToken; // ebx
  _DWORD *v9; // rdx
  unsigned __int8 v10; // al
  int v11; // r14d
  unsigned __int16 v12; // bx
  wchar_t *v13; // rax
  wchar_t *v14; // rdi
  ULONG ReturnLength[2]; // [rsp+40h] [rbp-C0h] BYREF
  UNICODE_STRING Destination; // [rsp+48h] [rbp-B8h] BYREF
  UNICODE_STRING UnicodeString; // [rsp+58h] [rbp-A8h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Source[264]; // [rsp+A0h] [rbp-60h] BYREF

  UnicodeString = 0;
  memset(&ObjectAttributes, 0, 44);
  Pool2 = (void *)ExAllocatePool2(256, 84, 5131347);
  if ( !Pool2 )
    return (unsigned int)-1073741801;
  ReturnLength[0] = 0;
  InformationToken = ZwQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, Pool2, 0x54u, ReturnLength);
  if ( InformationToken >= 0 )
  {
    v9 = *(_DWORD **)Pool2;
    v10 = *(_BYTE *)(*(_QWORD *)Pool2 + 1LL);
    if ( v10 < 2u || (v11 = 0, v10 == 5) && v9[2] == 21 && v9[6] == 503 )
    {
      *a4 = 0;
    }
    else
    {
      InformationToken = RtlConvertSidToUnicodeString(&UnicodeString, v9, 1u);
      if ( InformationToken >= 0 )
      {
        ReturnLength[0] = 0;
        InformationToken = RtlGetPersistedStateLocation(
                             L"GlobalizationUserSettings",
                             L"TargetNtPath",
                             L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\International",
                             0,
                             Source,
                             0x208u,
                             ReturnLength);
        if ( InformationToken >= 0 )
        {
          v12 = LOWORD(ReturnLength[0]) + UnicodeString.Length + 4;
          v13 = (wchar_t *)ExAllocatePool2(256, v12, 5131347);
          v14 = v13;
          if ( v13 )
          {
            *(_QWORD *)&Destination.Length = 0;
            Destination.MaximumLength = v12;
            Destination.Buffer = v13;
            InformationToken = RtlAppendUnicodeToString(&Destination, Source);
            if ( InformationToken >= 0 )
            {
              InformationToken = RtlAppendUnicodeToString(&Destination, L"\\");
              if ( InformationToken >= 0 )
              {
                InformationToken = RtlAppendUnicodeStringToString(&Destination, &UnicodeString);
                if ( InformationToken >= 0 )
                {
                  ObjectAttributes.Length = 48;
                  ObjectAttributes.ObjectName = &Destination;
                  ObjectAttributes.RootDirectory = 0;
                  ObjectAttributes.Attributes = 576;
                  *(_QWORD *)ReturnLength = 0;
                  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                  if ( ZwOpenKey((PHANDLE)ReturnLength, 0x20019u, &ObjectAttributes) < 0 )
                  {
                    v11 = 1;
                    *a4 = 1;
                  }
                  else
                  {
                    ZwClose(*(HANDLE *)ReturnLength);
                    *a4 = 2;
                    InformationToken = ZwOpenKey(a3, 8u, &ObjectAttributes);
                  }
                }
              }
            }
            ExFreePoolWithTag(v14, 0x4E4C53u);
          }
          else
          {
            InformationToken = -1073741801;
          }
        }
        RtlFreeAnsiString(&UnicodeString);
      }
      if ( !v11 )
        goto LABEL_23;
    }
    InformationToken = OpenGlobalizationUserSettingsKey_ForSingleUserModel(v7, a3);
  }
LABEL_23:
  ExFreePoolWithTag(Pool2, 0x4E4C53u);
  return (unsigned int)InformationToken;
}

```

## disassembly

```asm
0x140688264  mov     [rsp-8+arg_0], rbx
0x140688269  mov     [rsp-8+arg_8], rsi
0x14068826e  push    rbp
0x14068826f  push    rdi
0x140688270  push    r12
0x140688272  push    r14
0x140688274  push    r15
0x140688276  lea     rbp, [rsp-1C0h]
0x14068827e  sub     rsp, 2C0h
0x140688285  mov     rax, cs:__security_cookie
0x14068828c  xor     rax, rsp
0x14068828f  mov     [rbp+1E0h+var_30], rax
0x140688296  xorps   xmm0, xmm0
0x140688299  xor     eax, eax
0x14068829b  mov     r12, r8
0x14068829e  mov     edi, 100h
0x1406882a3  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.ObjectName], xmm0
0x1406882a8  mov     r8d, 4E4C53h
0x1406882ae  mov     ecx, edi
0x1406882b0  lea     ebx, [rax+54h]
0x1406882b3  mov     rsi, r9
0x1406882b6  mov     edx, ebx
0x1406882b8  movups  xmmword ptr [rsp+2E0h+UnicodeString.Length], xmm0
0x1406882bd  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.Length], xmm0
0x1406882c2  movups  xmmword ptr [rbp+1E0h+ObjectAttributes+1Ch], xmm0
0x1406882c6  call    ExAllocatePool2
0x1406882cb  mov     r15, rax
0x1406882ce  test    rax, rax
0x1406882d1  jz      loc_1406884C8
0x1406882d7  lea     rax, [rsp+2E0h+var_2A0]
0x1406882dc  mov     [rsp+2E0h+var_2A0], 0
0x1406882e4  mov     r9d, ebx; TokenInformationLength
0x1406882e7  mov     [rsp+2E0h+ReturnLength], rax; ReturnLength
0x1406882ec  mov     r8, r15; TokenInformation
0x1406882ef  lea     edx, [rbx-53h]; TokenInformationClass
0x1406882f2  lea     rcx, [rbx-5Ah]; TokenHandle
0x1406882f6  call    ZwQueryInformationToken
0x1406882fb  mov     ebx, eax
0x1406882fd  test    eax, eax
0x1406882ff  js      loc_1406884B9
0x140688305  mov     rdx, [r15]; Sid
0x140688308  mov     al, [rdx+1]
0x14068830b  cmp     al, 2
0x14068830d  jb      loc_1406884A9
0x140688313  xor     r14d, r14d
0x140688316  cmp     al, 5
0x140688318  jnz     short loc_14068832D
0x14068831a  cmp     dword ptr [rdx+8], 15h
0x14068831e  jnz     short loc_14068832D
0x140688320  cmp     dword ptr [rdx+18h], 1F7h
0x140688327  jz      loc_1406884A9
0x14068832d  mov     r8b, 1; AllocateDestinationString
0x140688330  lea     rcx, [rsp+2E0h+UnicodeString]; UnicodeString
0x140688335  call    RtlConvertSidToUnicodeString
0x14068833a  mov     ebx, eax
0x14068833c  test    eax, eax
0x14068833e  js      loc_1406884A2
0x140688344  lea     rax, [rsp+2E0h+var_2A0]
0x140688349  mov     [rsp+2E0h+var_2A0], r14d
0x14068834e  mov     [rsp+2E0h+var_2B0], rax; __int64
0x140688353  lea     r8, aRegistryMachin_221; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x14068835a  lea     rax, [rbp+1E0h+Source]
0x14068835e  mov     [rsp+2E0h+var_2B8], 208h; int
0x140688366  xor     r9d, r9d
0x140688369  mov     [rsp+2E0h+ReturnLength], rax; void *
0x14068836e  lea     rdx, aTargetntpath_1; "TargetNtPath"
0x140688375  lea     rcx, aGlobalizationu; "GlobalizationUserSettings"
0x14068837c  call    RtlGetPersistedStateLocation
0x140688381  mov     ebx, eax
0x140688383  test    eax, eax
0x140688385  js      loc_140688498
0x14068838b  movzx   eax, [rsp+2E0h+UnicodeString.Length]
0x140688390  mov     r8d, 4E4C53h
0x140688396  add     ax, 4
0x14068839a  mov     rcx, rdi
0x14068839d  add     ax, word ptr [rsp+2E0h+var_2A0]
0x1406883a2  movzx   ebx, ax
0x1406883a5  mov     edx, ebx
0x1406883a7  call    ExAllocatePool2
0x1406883ac  mov     rdi, rax
0x1406883af  test    rax, rax
0x1406883b2  jz      loc_140688493
0x1406883b8  xorps   xmm0, xmm0
0x1406883bb  lea     rdx, [rbp+1E0h+Source]; Source
0x1406883bf  movups  xmmword ptr [rsp+2E0h+Destination.Length], xmm0
0x1406883c4  lea     rcx, [rsp+2E0h+Destination]; Destination
0x1406883c9  mov     [rsp+2E0h+Destination.MaximumLength], bx
0x1406883ce  mov     [rsp+2E0h+Destination.Buffer], rax
0x1406883d3  call    RtlAppendUnicodeToString
0x1406883d8  mov     ebx, eax
0x1406883da  test    eax, eax
0x1406883dc  js      loc_140688484
0x1406883e2  lea     rdx, pszSrc; "\\"
0x1406883e9  lea     rcx, [rsp+2E0h+Destination]; Destination
0x1406883ee  call    RtlAppendUnicodeToString
0x1406883f3  mov     ebx, eax
0x1406883f5  test    eax, eax
0x1406883f7  js      loc_140688484
0x1406883fd  lea     rdx, [rsp+2E0h+UnicodeString]; Source
0x140688402  lea     rcx, [rsp+2E0h+Destination]; Destination
0x140688407  call    RtlAppendUnicodeStringToString
0x14068840c  mov     ebx, eax
0x14068840e  test    eax, eax
0x140688410  js      short loc_140688484
0x140688412  lea     rax, [rsp+2E0h+Destination]
0x140688417  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x14068841f  xorps   xmm0, xmm0
0x140688422  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x140688427  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x14068842c  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], r14
0x140688431  mov     edx, 20019h; DesiredAccess
0x140688436  mov     [rbp+1E0h+ObjectAttributes.Attributes], 240h
0x14068843d  lea     rcx, [rsp+2E0h+var_2A0]; KeyHandle
0x140688442  mov     qword ptr [rsp+2E0h+var_2A0], r14
0x140688447  movdqu  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14068844c  call    ZwOpenKey
0x140688451  test    eax, eax
0x140688453  js      short loc_14068847B
0x140688455  mov     rcx, qword ptr [rsp+2E0h+var_2A0]; Handle
0x14068845a  call    ZwClose
0x14068845f  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x140688464  mov     dword ptr [rsi], 2
0x14068846a  mov     edx, 8; DesiredAccess
0x14068846f  mov     rcx, r12; KeyHandle
0x140688472  call    ZwOpenKey
0x140688477  mov     ebx, eax
0x140688479  jmp     short loc_140688484
0x14068847b  mov     r14d, 1
0x140688481  mov     [rsi], r14d
0x140688484  mov     edx, 4E4C53h; Tag
0x140688489  mov     rcx, rdi; P
0x14068848c  call    ExFreePoolWithTag
0x140688491  jmp     short loc_140688498
0x140688493  mov     ebx, 0C0000017h
0x140688498  lea     rcx, [rsp+2E0h+UnicodeString]; UnicodeString
0x14068849d  call    RtlFreeAnsiString
0x1406884a2  test    r14d, r14d
0x1406884a5  jz      short loc_1406884B9
0x1406884a7  jmp     short loc_1406884AF
0x1406884a9  mov     dword ptr [rsi], 0
0x1406884af  mov     rdx, r12
0x1406884b2  call    OpenGlobalizationUserSettingsKey_ForSingleUserModel
0x1406884b7  mov     ebx, eax
0x1406884b9  mov     edx, 4E4C53h; Tag
0x1406884be  mov     rcx, r15; P
0x1406884c1  call    ExFreePoolWithTag
0x1406884c6  jmp     short loc_1406884CD
0x1406884c8  mov     ebx, 0C0000017h
0x1406884cd  mov     eax, ebx
0x1406884cf  mov     rcx, [rbp+1E0h+var_30]
0x1406884d6  xor     rcx, rsp; StackCookie
0x1406884d9  call    __security_check_cookie
0x1406884de  lea     r11, [rsp+2E0h+var_20]
0x1406884e6  mov     rbx, [r11+30h]
0x1406884ea  mov     rsi, [r11+38h]
0x1406884ee  mov     rsp, r11
0x1406884f1  pop     r15
0x1406884f3  pop     r14
0x1406884f5  pop     r12
0x1406884f7  pop     rdi
0x1406884f8  pop     rbp
0x1406884f9  retn
```
