# OpenRegKeyForUser

- ea: `0x180071e90`
- end: `0x180072176`
- name: `OpenRegKeyForUser`
- size: `742`
- prototype: `__int64 __usercall@<rax>(PHANDLE KeyHandle@<rcx>, char)`
- caller_count: `10`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001e794`
- `0x18006fad0`
- `0x180070c20`
- `0x1800711b0`
- `0x180073d7c`
- `0x1800a30ac`
- `0x1800a3390`
- `0x1800a4198`
- `0x180139444`
- `0x180139920`

## callees

- `0x180071e90`
- `0x18007217c`
- `0x180122e60`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180071f6f`
- `ntdll!RtlInitUnicodeString` at `0x180071f6f`
- `ntdll!NtOpenKey` at `0x180071fb1`
- `ntdll!NtOpenKey` at `0x180071fb1`
- `ntdll!NtCreateKey` at `0x180071fe8`
- `ntdll!NtCreateKey` at `0x180071fe8`
- `ntdll!RtlIsMultiSessionSku` at `0x18007213f`
- `ntdll!RtlIsMultiSessionSku` at `0x18007213f`
- `ntdll!RtlOpenCurrentUser` at `0x180071f23`
- `ntdll!RtlOpenCurrentUser` at `0x180071f46`
- `ntdll!RtlOpenCurrentUser` at `0x180071f23`
- `ntdll!RtlOpenCurrentUser` at `0x180071f46`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180072159`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180072159`
- `ntdll!NtClose` at `0x180071ffa`
- `ntdll!NtClose` at `0x1800720f6`
- `ntdll!NtClose` at `0x180071ffa`
- `ntdll!NtClose` at `0x1800720f6`

## pseudocode

```c
int __fastcall OpenRegKeyForUser(PHANDLE KeyHandle, WCHAR *a2, WCHAR *a3, ACCESS_MASK a4, char a5)
{
  HANDLE v8; // r10
  __int64 v9; // rbx
  int v10; // ecx
  int result; // eax
  NTSTATUS v12; // ebx
  WCHAR *v13; // rcx
  __int64 v14; // rcx
  WCHAR *v15; // rax
  __int64 v16; // r8
  __int64 v17; // rcx
  WCHAR *v18; // rax
  WCHAR *v19; // r8
  __int64 v20; // rsi
  WCHAR *v21; // rdx
  int v22; // ecx
  HANDLE KeyHandlea; // [rsp+40h] [rbp-C0h] BYREF
  ULONG Disposition; // [rsp+48h] [rbp-B8h] BYREF
  int v25; // [rsp+4Ch] [rbp-B4h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SourceString[512]; // [rsp+90h] [rbp-70h] BYREF

  KeyHandlea = 0;
  Disposition = 0;
  v8 = 0;
  v9 = 2147483646;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  if ( a2 )
  {
    if ( *a2 )
    {
      v14 = 2147483646;
      v15 = SourceString;
      v16 = 512;
      do
      {
        if ( !v14 )
          break;
        if ( !*a2 )
          break;
        *v15++ = *a2++;
        --v14;
        --v16;
      }
      while ( v16 );
      v13 = v15 - 1;
      if ( v16 )
        v13 = v15;
      *v13 = 0;
      if ( !v16 )
        return -1073741823;
      goto LABEL_10;
    }
    result = RtlOpenCurrentUser(0x2000000u, &KeyHandlea);
    if ( result < 0 )
      return result;
  }
  else
  {
    v10 = dword_18039F240;
    if ( !dword_18039F240 )
    {
      if ( (unsigned __int8)RtlIsMultiSessionSku() )
        v10 = 1;
      else
        v10 = ((unsigned __int8)RtlIsMultiUsersInSessionSku() != 0) + 2;
      dword_18039F240 = v10;
    }
    if ( v10 == 1 )
    {
      result = RtlOpenCurrentUser(0x2000000u, &KeyHandlea);
    }
    else
    {
      v22 = v10 - 2;
      if ( v22 )
      {
        if ( v22 != 1 )
          return -1073741595;
        v25 = 0;
        result = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, &KeyHandlea, &v25);
      }
      else
      {
        result = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, &KeyHandlea);
      }
    }
    if ( result < 0 )
      return result;
  }
  v8 = KeyHandlea;
  SourceString[0] = 0;
LABEL_10:
  if ( a3 )
  {
    v17 = 512;
    v18 = SourceString;
    do
    {
      if ( !*v18 )
        break;
      ++v18;
      --v17;
    }
    while ( v17 );
    if ( !v17 )
      goto LABEL_40;
    v19 = &SourceString[512 - v17];
    v20 = v17;
    do
    {
      if ( !v9 )
        break;
      if ( !*a3 )
        break;
      *v19++ = *a3++;
      --v9;
      --v20;
    }
    while ( v20 );
    v21 = v19 - 1;
    if ( v20 )
      v21 = v19;
    *v21 = 0;
    if ( !v20 )
    {
LABEL_40:
      if ( v8 )
        NtClose(v8);
      return -1073741823;
    }
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.RootDirectory = KeyHandlea;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Disposition = 0;
  v12 = NtOpenKey(KeyHandle, a4, &ObjectAttributes);
  if ( v12 < 0 && (a5 & 2) != 0 )
    v12 = NtCreateKey(KeyHandle, a4, &ObjectAttributes, 0, 0, 0, &Disposition);
  if ( KeyHandlea )
    NtClose(KeyHandlea);
  if ( v12 < 0 )
    *KeyHandle = 0;
  return v12;
}

```

## disassembly

```asm
0x180071e90  mov     [rsp-8+arg_8], rbx
0x180071e95  mov     [rsp-8+arg_10], rsi
0x180071e9a  push    rbp
0x180071e9b  push    rdi
0x180071e9c  push    r12
0x180071e9e  push    r14
0x180071ea0  push    r15
0x180071ea2  lea     rbp, [rsp-3A0h]
0x180071eaa  sub     rsp, 4A0h
0x180071eb1  mov     rax, cs:__security_cookie
0x180071eb8  xor     rax, rsp
0x180071ebb  mov     [rbp+3C0h+var_30], rax
0x180071ec2  xor     r12d, r12d
0x180071ec5  xorps   xmm0, xmm0
0x180071ec8  xor     eax, eax
0x180071eca  mov     [rsp+4C0h+KeyHandle], r12
0x180071ecf  mov     [rsp+4C0h+var_478], r12d
0x180071ed4  mov     r15d, r9d
0x180071ed7  mov     rdi, r8
0x180071eda  mov     r14, rcx
0x180071edd  mov     r10d, r12d
0x180071ee0  mov     ebx, 7FFFFFFEh
0x180071ee5  mov     esi, 200h
0x180071eea  movups  xmmword ptr [rsp+4C0h+ObjectAttributes.ObjectName], xmm0
0x180071eef  movups  xmmword ptr [rsp+4C0h+ObjectAttributes+1Ch], xmm0
0x180071ef4  movups  xmmword ptr [rsp+4C0h+ObjectAttributes.Length], xmm0
0x180071ef9  movups  xmmword ptr [rbp+3C0h+DestinationString.Length], xmm0
0x180071efd  test    rdx, rdx
0x180071f00  jnz     short loc_180071F33
0x180071f02  mov     ecx, cs:dword_18039F240
0x180071f08  test    ecx, ecx
0x180071f0a  jz      loc_18007213F
0x180071f10  cmp     ecx, 1
0x180071f13  jnz     loc_180072101
0x180071f19  lea     rdx, [rsp+4C0h+KeyHandle]; KeyHandle
0x180071f1e  mov     ecx, 2000000h; DesiredAccess
0x180071f23  call    cs:__imp_RtlOpenCurrentUser
0x180071f29  test    eax, eax
0x180071f2b  js      loc_180072025
0x180071f31  jmp     short loc_180071F54
0x180071f33  cmp     [rdx], ax
0x180071f36  jnz     loc_180072050
0x180071f3c  lea     rdx, [rsp+4C0h+KeyHandle]; KeyHandle
0x180071f41  mov     ecx, 2000000h; DesiredAccess
0x180071f46  call    cs:__imp_RtlOpenCurrentUser
0x180071f4c  test    eax, eax
0x180071f4e  js      loc_180072025
0x180071f54  mov     r10, [rsp+4C0h+KeyHandle]
0x180071f59  mov     [rbp+3C0h+SourceString], r12w
0x180071f5e  test    rdi, rdi
0x180071f61  jnz     loc_180072080
0x180071f67  lea     rdx, [rbp+3C0h+SourceString]; SourceString
0x180071f6b  lea     rcx, [rbp+3C0h+DestinationString]; DestinationString
0x180071f6f  call    cs:__imp_RtlInitUnicodeString
0x180071f75  mov     rax, [rsp+4C0h+KeyHandle]
0x180071f7a  lea     r8, [rsp+4C0h+ObjectAttributes]; ObjectAttributes
0x180071f7f  mov     [rsp+4C0h+ObjectAttributes.RootDirectory], rax
0x180071f84  xorps   xmm0, xmm0
0x180071f87  lea     rax, [rbp+3C0h+DestinationString]
0x180071f8b  mov     [rsp+4C0h+ObjectAttributes.Length], 30h ; '0'
0x180071f93  mov     edx, r15d; DesiredAccess
0x180071f96  mov     [rsp+4C0h+ObjectAttributes.ObjectName], rax
0x180071f9b  mov     rcx, r14; KeyHandle
0x180071f9e  mov     [rsp+4C0h+ObjectAttributes.Attributes], 40h ; '@'
0x180071fa6  movdqu  xmmword ptr [rsp+4C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180071fac  mov     [rsp+4C0h+var_478], r12d
0x180071fb1  call    cs:__imp_NtOpenKey
0x180071fb7  mov     ebx, eax
0x180071fb9  test    eax, eax
0x180071fbb  jns     short loc_180071FF0
0x180071fbd  test    [rbp+3C0h+arg_20], 2
0x180071fc4  jz      short loc_180071FF0
0x180071fc6  lea     rax, [rsp+4C0h+var_478]
0x180071fcb  xor     r9d, r9d; TitleIndex
0x180071fce  mov     [rsp+4C0h+Disposition], rax; Disposition
0x180071fd3  lea     r8, [rsp+4C0h+ObjectAttributes]; ObjectAttributes
0x180071fd8  mov     [rsp+4C0h+CreateOptions], r12d; CreateOptions
0x180071fdd  mov     edx, r15d; DesiredAccess
0x180071fe0  mov     rcx, r14; KeyHandle
0x180071fe3  mov     [rsp+4C0h+Class], r12; Class
0x180071fe8  call    cs:__imp_NtCreateKey
0x180071fee  mov     ebx, eax
0x180071ff0  mov     rcx, [rsp+4C0h+KeyHandle]; Handle
0x180071ff5  test    rcx, rcx
0x180071ff8  jz      short loc_180072000
0x180071ffa  call    cs:__imp_NtClose
0x180072000  test    ebx, ebx
0x180072002  jns     short loc_180072007
0x180072004  mov     [r14], r12
0x180072007  mov     eax, ebx
0x180072009  jmp     short loc_180072025
0x18007200b  test    r8, r8
0x18007200e  lea     rcx, [rax-2]
0x180072012  cmovnz  rcx, rax
0x180072016  mov     [rcx], r12w
0x18007201a  jnz     loc_180071F5E
0x180072020  mov     eax, 0C0000001h
0x180072025  mov     rcx, [rbp+3C0h+var_30]
0x18007202c  xor     rcx, rsp; StackCookie
0x18007202f  call    __security_check_cookie
0x180072034  lea     r11, [rsp+4C0h+var_20]
0x18007203c  mov     rbx, [r11+38h]
0x180072040  mov     rsi, [r11+40h]
0x180072044  mov     rsp, r11
0x180072047  pop     r15
0x180072049  pop     r14
0x18007204b  pop     r12
0x18007204d  pop     rdi
0x18007204e  pop     rbp
0x18007204f  retn
0x180072050  mov     rcx, rbx
0x180072053  lea     rax, [rbp+3C0h+SourceString]
0x180072057  mov     r8, rsi
0x18007205a  test    rcx, rcx
0x18007205d  jz      short loc_18007200B
0x18007205f  movzx   r9d, word ptr [rdx]
0x180072063  test    r9w, r9w
0x180072067  jz      short loc_18007200B
0x180072069  mov     [rax], r9w
0x18007206d  add     rdx, 2
0x180072071  add     rax, 2
0x180072075  dec     rcx
0x180072078  sub     r8, 1
0x18007207c  jnz     short loc_18007205A
0x18007207e  jmp     short loc_18007200B
0x180072080  mov     rcx, rsi
0x180072083  lea     rax, [rbp+3C0h+SourceString]
0x180072087  cmp     [rax], r12w
0x18007208b  jz      short loc_180072097
0x18007208d  add     rax, 2
0x180072091  sub     rcx, 1
0x180072095  jnz     short loc_180072087
0x180072097  mov     rdx, rsi
0x18007209a  sub     rdx, rcx
0x18007209d  test    rcx, rcx
0x1800720a0  cmovz   rdx, r12
0x1800720a4  jz      short loc_1800720EA
0x1800720a6  lea     r8, [rbp+3C0h+SourceString]
0x1800720aa  lea     r8, [r8+rdx*2]
0x1800720ae  sub     rsi, rdx
0x1800720b1  jz      short loc_1800720D5
0x1800720b3  test    rbx, rbx
0x1800720b6  jz      short loc_1800720D5
0x1800720b8  movzx   eax, word ptr [rdi]
0x1800720bb  test    ax, ax
0x1800720be  jz      short loc_1800720D5
0x1800720c0  mov     [r8], ax
0x1800720c4  add     rdi, 2
0x1800720c8  add     r8, 2
0x1800720cc  dec     rbx
0x1800720cf  sub     rsi, 1
0x1800720d3  jnz     short loc_1800720B3
0x1800720d5  test    rsi, rsi
0x1800720d8  lea     rdx, [r8-2]
0x1800720dc  cmovnz  rdx, r8
0x1800720e0  mov     [rdx], r12w
0x1800720e4  jnz     loc_180071F67
0x1800720ea  test    r10, r10
0x1800720ed  jz      loc_180072020
0x1800720f3  mov     rcx, r10; Handle
0x1800720f6  call    cs:__imp_NtClose
0x1800720fc  jmp     loc_180072020
0x180072101  sub     ecx, 2
0x180072104  jnz     short loc_18007211A
0x180072106  lea     rdx, [rsp+4C0h+KeyHandle]; KeyHandle
0x18007210b  mov     ecx, 2000000h; DesiredAccess
0x180072110  call    OpenGlobalizationUserSettingsKey_ForSingleUserModel
0x180072115  jmp     loc_180071F29
0x18007211a  cmp     ecx, 1
0x18007211d  jnz     short loc_18007216C
0x18007211f  lea     r9, [rsp+4C0h+var_474]
0x180072124  mov     [rsp+4C0h+var_474], r12d
0x180072129  lea     r8, [rsp+4C0h+KeyHandle]; KeyHandle
0x18007212e  xor     edx, edx; Sid
0x180072130  mov     ecx, 2000000h; DesiredAccess
0x180072135  call    OpenGlobalizationUserSettingsKey_ForMua
0x18007213a  jmp     loc_180071F29
0x18007213f  call    cs:__imp_RtlIsMultiSessionSku
0x180072145  test    al, al
0x180072147  jz      short loc_180072159
0x180072149  mov     ecx, 1
0x18007214e  mov     cs:dword_18039F240, ecx
0x180072154  jmp     loc_180071F10
0x180072159  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x18007215f  test    al, al
0x180072161  mov     ecx, r12d
0x180072164  setnz   cl
0x180072167  add     ecx, 2
0x18007216a  jmp     short loc_18007214E
0x18007216c  mov     eax, 0C00000E5h
0x180072171  jmp     loc_180072025
```
