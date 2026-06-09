# OpenGlobalizationUserSettingsKey_ForMua

- ea: `0x14068dc34`
- end: `0x14068decb`
- name: `OpenGlobalizationUserSettingsKey_ForMua`
- size: `663`
- prototype: `__int64 __fastcall(__int64, __int64, HANDLE *, _DWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1404d5240`

## callees

- `0x140388690`
- `0x140388750`
- `0x14068dc34`
- `0x14068ded4`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406dd620`
- `0x1406dd800`
- `0x1408557f0`
- `0x140879b80`
- `0x14094b120`
- `0x140bb1410`
- `0x140bb19f0`

## string_xrefs

- `0x14068dd3e`: `TargetNtPath`
- `0x14068dd23`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\International`

## pseudocode

```c
__int64 __fastcall OpenGlobalizationUserSettingsKey_ForMua(__int64 a1, __int64 a2, HANDLE *a3, _DWORD *a4)
{
  void *Pool2; // r15
  __int64 v7; // rcx
  NTSTATUS InformationToken; // ebx
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
                             Source,
                             520,
                             (__int64)ReturnLength);
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
0x14068dc34  mov     [rsp-8+arg_0], rbx
0x14068dc39  mov     [rsp-8+arg_8], rsi
0x14068dc3e  push    rbp
0x14068dc3f  push    rdi
0x14068dc40  push    r12
0x14068dc42  push    r14
0x14068dc44  push    r15
0x14068dc46  lea     rbp, [rsp-1C0h]
0x14068dc4e  sub     rsp, 2C0h
0x14068dc55  mov     rax, cs:__security_cookie
0x14068dc5c  xor     rax, rsp
0x14068dc5f  mov     [rbp+1E0h+var_30], rax
0x14068dc66  xorps   xmm0, xmm0
0x14068dc69  xor     eax, eax
0x14068dc6b  mov     r12, r8
0x14068dc6e  mov     edi, 100h
0x14068dc73  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.ObjectName], xmm0
0x14068dc78  mov     r8d, 4E4C53h
0x14068dc7e  mov     ecx, edi
0x14068dc80  lea     ebx, [rax+54h]
0x14068dc83  mov     rsi, r9
0x14068dc86  mov     edx, ebx
0x14068dc88  movups  xmmword ptr [rsp+2E0h+UnicodeString.Length], xmm0
0x14068dc8d  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.Length], xmm0
0x14068dc92  movups  xmmword ptr [rbp+1E0h+ObjectAttributes+1Ch], xmm0
0x14068dc96  call    ExAllocatePool2
0x14068dc9b  mov     r15, rax
0x14068dc9e  test    rax, rax
0x14068dca1  jz      loc_14068DE98
0x14068dca7  lea     rax, [rsp+2E0h+var_2A0]
0x14068dcac  mov     [rsp+2E0h+var_2A0], 0
0x14068dcb4  mov     r9d, ebx; TokenInformationLength
0x14068dcb7  mov     [rsp+2E0h+ReturnLength], rax; ReturnLength
0x14068dcbc  mov     r8, r15; TokenInformation
0x14068dcbf  lea     edx, [rbx-53h]; TokenInformationClass
0x14068dcc2  lea     rcx, [rbx-5Ah]; TokenHandle
0x14068dcc6  call    ZwQueryInformationToken
0x14068dccb  mov     ebx, eax
0x14068dccd  test    eax, eax
0x14068dccf  js      loc_14068DE89
0x14068dcd5  mov     rdx, [r15]; Sid
0x14068dcd8  mov     al, [rdx+1]
0x14068dcdb  cmp     al, 2
0x14068dcdd  jb      loc_14068DE79
0x14068dce3  xor     r14d, r14d
0x14068dce6  cmp     al, 5
0x14068dce8  jnz     short loc_14068DCFD
0x14068dcea  cmp     dword ptr [rdx+8], 15h
0x14068dcee  jnz     short loc_14068DCFD
0x14068dcf0  cmp     dword ptr [rdx+18h], 1F7h
0x14068dcf7  jz      loc_14068DE79
0x14068dcfd  mov     r8b, 1; AllocateDestinationString
0x14068dd00  lea     rcx, [rsp+2E0h+UnicodeString]; UnicodeString
0x14068dd05  call    RtlConvertSidToUnicodeString
0x14068dd0a  mov     ebx, eax
0x14068dd0c  test    eax, eax
0x14068dd0e  js      loc_14068DE72
0x14068dd14  lea     rax, [rsp+2E0h+var_2A0]
0x14068dd19  mov     [rsp+2E0h+var_2A0], r14d
0x14068dd1e  mov     [rsp+2E0h+var_2B0], rax; __int64
0x14068dd23  lea     r8, aRegistryMachin_220; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x14068dd2a  lea     rax, [rbp+1E0h+Source]
0x14068dd2e  mov     [rsp+2E0h+var_2B8], 208h; int
0x14068dd36  xor     r9d, r9d
0x14068dd39  mov     [rsp+2E0h+ReturnLength], rax; void *
0x14068dd3e  lea     rdx, aTargetntpath_1; "TargetNtPath"
0x14068dd45  lea     rcx, aGlobalizationu; "GlobalizationUserSettings"
0x14068dd4c  call    RtlGetPersistedStateLocation
0x14068dd51  mov     ebx, eax
0x14068dd53  test    eax, eax
0x14068dd55  js      loc_14068DE68
0x14068dd5b  movzx   eax, [rsp+2E0h+UnicodeString.Length]
0x14068dd60  mov     r8d, 4E4C53h
0x14068dd66  add     ax, 4
0x14068dd6a  mov     rcx, rdi
0x14068dd6d  add     ax, word ptr [rsp+2E0h+var_2A0]
0x14068dd72  movzx   ebx, ax
0x14068dd75  mov     edx, ebx
0x14068dd77  call    ExAllocatePool2
0x14068dd7c  mov     rdi, rax
0x14068dd7f  test    rax, rax
0x14068dd82  jz      loc_14068DE63
0x14068dd88  xorps   xmm0, xmm0
0x14068dd8b  lea     rdx, [rbp+1E0h+Source]; Source
0x14068dd8f  movups  xmmword ptr [rsp+2E0h+Destination.Length], xmm0
0x14068dd94  lea     rcx, [rsp+2E0h+Destination]; Destination
0x14068dd99  mov     [rsp+2E0h+Destination.MaximumLength], bx
0x14068dd9e  mov     [rsp+2E0h+Destination.Buffer], rax
0x14068dda3  call    RtlAppendUnicodeToString
0x14068dda8  mov     ebx, eax
0x14068ddaa  test    eax, eax
0x14068ddac  js      loc_14068DE54
0x14068ddb2  lea     rdx, pszSrc; "\\"
0x14068ddb9  lea     rcx, [rsp+2E0h+Destination]; Destination
0x14068ddbe  call    RtlAppendUnicodeToString
0x14068ddc3  mov     ebx, eax
0x14068ddc5  test    eax, eax
0x14068ddc7  js      loc_14068DE54
0x14068ddcd  lea     rdx, [rsp+2E0h+UnicodeString]; Source
0x14068ddd2  lea     rcx, [rsp+2E0h+Destination]; Destination
0x14068ddd7  call    RtlAppendUnicodeStringToString
0x14068dddc  mov     ebx, eax
0x14068ddde  test    eax, eax
0x14068dde0  js      short loc_14068DE54
0x14068dde2  lea     rax, [rsp+2E0h+Destination]
0x14068dde7  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x14068ddef  xorps   xmm0, xmm0
0x14068ddf2  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x14068ddf7  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x14068ddfc  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], r14
0x14068de01  mov     edx, 20019h; DesiredAccess
0x14068de06  mov     [rbp+1E0h+ObjectAttributes.Attributes], 240h
0x14068de0d  lea     rcx, [rsp+2E0h+var_2A0]; KeyHandle
0x14068de12  mov     qword ptr [rsp+2E0h+var_2A0], r14
0x14068de17  movdqu  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14068de1c  call    ZwOpenKey
0x14068de21  test    eax, eax
0x14068de23  js      short loc_14068DE4B
0x14068de25  mov     rcx, qword ptr [rsp+2E0h+var_2A0]; Handle
0x14068de2a  call    ZwClose
0x14068de2f  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x14068de34  mov     dword ptr [rsi], 2
0x14068de3a  mov     edx, 8; DesiredAccess
0x14068de3f  mov     rcx, r12; KeyHandle
0x14068de42  call    ZwOpenKey
0x14068de47  mov     ebx, eax
0x14068de49  jmp     short loc_14068DE54
0x14068de4b  mov     r14d, 1
0x14068de51  mov     [rsi], r14d
0x14068de54  mov     edx, 4E4C53h; Tag
0x14068de59  mov     rcx, rdi; P
0x14068de5c  call    ExFreePoolWithTag
0x14068de61  jmp     short loc_14068DE68
0x14068de63  mov     ebx, 0C0000017h
0x14068de68  lea     rcx, [rsp+2E0h+UnicodeString]; UnicodeString
0x14068de6d  call    RtlFreeAnsiString
0x14068de72  test    r14d, r14d
0x14068de75  jz      short loc_14068DE89
0x14068de77  jmp     short loc_14068DE7F
0x14068de79  mov     dword ptr [rsi], 0
0x14068de7f  mov     rdx, r12
0x14068de82  call    OpenGlobalizationUserSettingsKey_ForSingleUserModel
0x14068de87  mov     ebx, eax
0x14068de89  mov     edx, 4E4C53h; Tag
0x14068de8e  mov     rcx, r15; P
0x14068de91  call    ExFreePoolWithTag
0x14068de96  jmp     short loc_14068DE9D
0x14068de98  mov     ebx, 0C0000017h
0x14068de9d  mov     eax, ebx
0x14068de9f  mov     rcx, [rbp+1E0h+var_30]
0x14068dea6  xor     rcx, rsp; StackCookie
0x14068dea9  call    __security_check_cookie
0x14068deae  lea     r11, [rsp+2E0h+var_20]
0x14068deb6  mov     rbx, [r11+30h]
0x14068deba  mov     rsi, [r11+38h]
0x14068debe  mov     rsp, r11
0x14068dec1  pop     r15
0x14068dec3  pop     r14
0x14068dec5  pop     r12
0x14068dec7  pop     rdi
0x14068dec8  pop     rbp
0x14068dec9  retn
```
