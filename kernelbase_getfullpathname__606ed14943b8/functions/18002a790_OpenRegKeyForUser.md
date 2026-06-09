# OpenRegKeyForUser

- ea: `0x18002a790`
- end: `0x18002aab5`
- name: `OpenRegKeyForUser`
- size: `805`
- prototype: `__int64 __usercall@<rax>(PHANDLE KeyHandle@<rcx>, char)`
- caller_count: `10`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180028360`
- `0x18002b38c`
- `0x18002b710`
- `0x1800747f0`
- `0x180078828`
- `0x1800afe64`
- `0x1800b0180`
- `0x1800b1170`
- `0x180143164`
- `0x180143670`

## callees

- `0x18002a790`
- `0x18002aabc`
- `0x18012c3ac`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002a87b`
- `ntdll!RtlInitUnicodeString` at `0x18002a87b`
- `ntdll!NtOpenKey` at `0x18002a8c3`
- `ntdll!NtOpenKey` at `0x18002a8c3`
- `ntdll!NtCreateKey` at `0x18002a900`
- `ntdll!NtCreateKey` at `0x18002a900`
- `ntdll!RtlIsMultiSessionSku` at `0x18002aa72`
- `ntdll!RtlIsMultiSessionSku` at `0x18002aa72`
- `ntdll!RtlOpenCurrentUser` at `0x18002a823`
- `ntdll!RtlOpenCurrentUser` at `0x18002a84c`
- `ntdll!RtlOpenCurrentUser` at `0x18002a823`
- `ntdll!RtlOpenCurrentUser` at `0x18002a84c`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18002aa92`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18002aa92`
- `ntdll!NtClose` at `0x18002a918`
- `ntdll!NtClose` at `0x18002aa23`
- `ntdll!NtClose` at `0x18002a918`
- `ntdll!NtClose` at `0x18002aa23`

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
    v10 = dword_1803A7170;
    if ( !dword_1803A7170 )
    {
      if ( (unsigned __int8)RtlIsMultiSessionSku() )
        v10 = 1;
      else
        v10 = ((unsigned __int8)RtlIsMultiUsersInSessionSku() != 0) + 2;
      dword_1803A7170 = v10;
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
0x18002a790  mov     [rsp-8+arg_8], rbx
0x18002a795  mov     [rsp-8+arg_10], rsi
0x18002a79a  push    rbp
0x18002a79b  push    rdi
0x18002a79c  push    r12
0x18002a79e  push    r14
0x18002a7a0  push    r15
0x18002a7a2  lea     rbp, [rsp-3A0h]
0x18002a7aa  sub     rsp, 4A0h
0x18002a7b1  mov     rax, cs:__security_cookie
0x18002a7b8  xor     rax, rsp
0x18002a7bb  mov     [rbp+3C0h+var_30], rax
0x18002a7c2  xor     r12d, r12d
0x18002a7c5  xorps   xmm0, xmm0
0x18002a7c8  xor     eax, eax
0x18002a7ca  mov     [rsp+4C0h+KeyHandle], r12
0x18002a7cf  mov     [rsp+4C0h+var_478], r12d
0x18002a7d4  mov     r15d, r9d
0x18002a7d7  mov     rdi, r8
0x18002a7da  mov     r14, rcx
0x18002a7dd  mov     r10d, r12d
0x18002a7e0  mov     ebx, 7FFFFFFEh
0x18002a7e5  mov     esi, 200h
0x18002a7ea  movups  xmmword ptr [rsp+4C0h+ObjectAttributes.ObjectName], xmm0
0x18002a7ef  movups  xmmword ptr [rsp+4C0h+ObjectAttributes+1Ch], xmm0
0x18002a7f4  movups  xmmword ptr [rsp+4C0h+ObjectAttributes.Length], xmm0
0x18002a7f9  movups  xmmword ptr [rbp+3C0h+DestinationString.Length], xmm0
0x18002a7fd  test    rdx, rdx
0x18002a800  jnz     short loc_18002A839
0x18002a802  mov     ecx, cs:dword_1803A7170
0x18002a808  test    ecx, ecx
0x18002a80a  jz      loc_18002AA72
0x18002a810  cmp     ecx, 1
0x18002a813  jnz     loc_18002AA34
0x18002a819  lea     rdx, [rsp+4C0h+KeyHandle]; KeyHandle
0x18002a81e  mov     ecx, 2000000h; DesiredAccess
0x18002a823  call    cs:__imp_RtlOpenCurrentUser
0x18002a82a  nop     dword ptr [rax+rax+00h]
0x18002a82f  test    eax, eax
0x18002a831  js      loc_18002A949
0x18002a837  jmp     short loc_18002A860
0x18002a839  cmp     [rdx], ax
0x18002a83c  jnz     loc_18002A975
0x18002a842  lea     rdx, [rsp+4C0h+KeyHandle]; KeyHandle
0x18002a847  mov     ecx, 2000000h; DesiredAccess
0x18002a84c  call    cs:__imp_RtlOpenCurrentUser
0x18002a853  nop     dword ptr [rax+rax+00h]
0x18002a858  test    eax, eax
0x18002a85a  js      loc_18002A949
0x18002a860  mov     r10, [rsp+4C0h+KeyHandle]
0x18002a865  mov     [rbp+3C0h+SourceString], r12w
0x18002a86a  test    rdi, rdi
0x18002a86d  jnz     loc_18002A9A5
0x18002a873  lea     rdx, [rbp+3C0h+SourceString]; SourceString
0x18002a877  lea     rcx, [rbp+3C0h+DestinationString]; DestinationString
0x18002a87b  call    cs:__imp_RtlInitUnicodeString
0x18002a882  nop     dword ptr [rax+rax+00h]
0x18002a887  mov     rax, [rsp+4C0h+KeyHandle]
0x18002a88c  lea     r8, [rsp+4C0h+ObjectAttributes]; ObjectAttributes
0x18002a891  mov     [rsp+4C0h+ObjectAttributes.RootDirectory], rax
0x18002a896  xorps   xmm0, xmm0
0x18002a899  lea     rax, [rbp+3C0h+DestinationString]
0x18002a89d  mov     [rsp+4C0h+ObjectAttributes.Length], 30h ; '0'
0x18002a8a5  mov     edx, r15d; DesiredAccess
0x18002a8a8  mov     [rsp+4C0h+ObjectAttributes.ObjectName], rax
0x18002a8ad  mov     rcx, r14; KeyHandle
0x18002a8b0  mov     [rsp+4C0h+ObjectAttributes.Attributes], 40h ; '@'
0x18002a8b8  movdqu  xmmword ptr [rsp+4C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002a8be  mov     [rsp+4C0h+var_478], r12d
0x18002a8c3  call    cs:__imp_NtOpenKey
0x18002a8ca  nop     dword ptr [rax+rax+00h]
0x18002a8cf  mov     ebx, eax
0x18002a8d1  test    eax, eax
0x18002a8d3  jns     short loc_18002A90E
0x18002a8d5  test    [rbp+3C0h+arg_20], 2
0x18002a8dc  jz      short loc_18002A90E
0x18002a8de  lea     rax, [rsp+4C0h+var_478]
0x18002a8e3  xor     r9d, r9d; TitleIndex
0x18002a8e6  mov     [rsp+4C0h+Disposition], rax; Disposition
0x18002a8eb  lea     r8, [rsp+4C0h+ObjectAttributes]; ObjectAttributes
0x18002a8f0  mov     [rsp+4C0h+CreateOptions], r12d; CreateOptions
0x18002a8f5  mov     edx, r15d; DesiredAccess
0x18002a8f8  mov     rcx, r14; KeyHandle
0x18002a8fb  mov     [rsp+4C0h+Class], r12; Class
0x18002a900  call    cs:__imp_NtCreateKey
0x18002a907  nop     dword ptr [rax+rax+00h]
0x18002a90c  mov     ebx, eax
0x18002a90e  mov     rcx, [rsp+4C0h+KeyHandle]; Handle
0x18002a913  test    rcx, rcx
0x18002a916  jz      short loc_18002A924
0x18002a918  call    cs:__imp_NtClose
0x18002a91f  nop     dword ptr [rax+rax+00h]
0x18002a924  test    ebx, ebx
0x18002a926  jns     short loc_18002A92B
0x18002a928  mov     [r14], r12
0x18002a92b  mov     eax, ebx
0x18002a92d  jmp     short loc_18002A949
0x18002a92f  test    r8, r8
0x18002a932  lea     rcx, [rax-2]
0x18002a936  cmovnz  rcx, rax
0x18002a93a  mov     [rcx], r12w
0x18002a93e  jnz     loc_18002A86A
0x18002a944  mov     eax, 0C0000001h
0x18002a949  mov     rcx, [rbp+3C0h+var_30]
0x18002a950  xor     rcx, rsp; StackCookie
0x18002a953  call    __security_check_cookie
0x18002a958  lea     r11, [rsp+4C0h+var_20]
0x18002a960  mov     rbx, [r11+38h]
0x18002a964  mov     rsi, [r11+40h]
0x18002a968  mov     rsp, r11
0x18002a96b  pop     r15
0x18002a96d  pop     r14
0x18002a96f  pop     r12
0x18002a971  pop     rdi
0x18002a972  pop     rbp
0x18002a973  retn
0x18002a975  mov     rcx, rbx
0x18002a978  lea     rax, [rbp+3C0h+SourceString]
0x18002a97c  mov     r8, rsi
0x18002a97f  test    rcx, rcx
0x18002a982  jz      short loc_18002A92F
0x18002a984  movzx   r9d, word ptr [rdx]
0x18002a988  test    r9w, r9w
0x18002a98c  jz      short loc_18002A92F
0x18002a98e  mov     [rax], r9w
0x18002a992  add     rdx, 2
0x18002a996  add     rax, 2
0x18002a99a  dec     rcx
0x18002a99d  sub     r8, 1
0x18002a9a1  jnz     short loc_18002A97F
0x18002a9a3  jmp     short loc_18002A92F
0x18002a9a5  mov     rcx, rsi
0x18002a9a8  lea     rax, [rbp+3C0h+SourceString]
0x18002a9ac  nop     dword ptr [rax+00h]
0x18002a9b0  cmp     [rax], r12w
0x18002a9b4  jz      short loc_18002A9C0
0x18002a9b6  add     rax, 2
0x18002a9ba  sub     rcx, 1
0x18002a9be  jnz     short loc_18002A9B0
0x18002a9c0  mov     rdx, rsi
0x18002a9c3  sub     rdx, rcx
0x18002a9c6  test    rcx, rcx
0x18002a9c9  cmovz   rdx, r12
0x18002a9cd  jz      short loc_18002AA17
0x18002a9cf  lea     r8, [rbp+3C0h+SourceString]
0x18002a9d3  lea     r8, [r8+rdx*2]
0x18002a9d7  sub     rsi, rdx
0x18002a9da  jz      short loc_18002AA02
0x18002a9dc  nop     dword ptr [rax+00h]
0x18002a9e0  test    rbx, rbx
0x18002a9e3  jz      short loc_18002AA02
0x18002a9e5  movzx   eax, word ptr [rdi]
0x18002a9e8  test    ax, ax
0x18002a9eb  jz      short loc_18002AA02
0x18002a9ed  mov     [r8], ax
0x18002a9f1  add     rdi, 2
0x18002a9f5  add     r8, 2
0x18002a9f9  dec     rbx
0x18002a9fc  sub     rsi, 1
0x18002aa00  jnz     short loc_18002A9E0
0x18002aa02  test    rsi, rsi
0x18002aa05  lea     rdx, [r8-2]
0x18002aa09  cmovnz  rdx, r8
0x18002aa0d  mov     [rdx], r12w
0x18002aa11  jnz     loc_18002A873
0x18002aa17  test    r10, r10
0x18002aa1a  jz      loc_18002A944
0x18002aa20  mov     rcx, r10; Handle
0x18002aa23  call    cs:__imp_NtClose
0x18002aa2a  nop     dword ptr [rax+rax+00h]
0x18002aa2f  jmp     loc_18002A944
0x18002aa34  sub     ecx, 2
0x18002aa37  jnz     short loc_18002AA4D
0x18002aa39  lea     rdx, [rsp+4C0h+KeyHandle]; KeyHandle
0x18002aa3e  mov     ecx, 2000000h; DesiredAccess
0x18002aa43  call    OpenGlobalizationUserSettingsKey_ForSingleUserModel
0x18002aa48  jmp     loc_18002A82F
0x18002aa4d  cmp     ecx, 1
0x18002aa50  jnz     short loc_18002AAAB
0x18002aa52  lea     r9, [rsp+4C0h+var_474]
0x18002aa57  mov     [rsp+4C0h+var_474], r12d
0x18002aa5c  lea     r8, [rsp+4C0h+KeyHandle]; KeyHandle
0x18002aa61  xor     edx, edx; Sid
0x18002aa63  mov     ecx, 2000000h; DesiredAccess
0x18002aa68  call    OpenGlobalizationUserSettingsKey_ForMua
0x18002aa6d  jmp     loc_18002A82F
0x18002aa72  call    cs:__imp_RtlIsMultiSessionSku
0x18002aa79  nop     dword ptr [rax+rax+00h]
0x18002aa7e  test    al, al
0x18002aa80  jz      short loc_18002AA92
0x18002aa82  mov     ecx, 1
0x18002aa87  mov     cs:dword_1803A7170, ecx
0x18002aa8d  jmp     loc_18002A810
0x18002aa92  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x18002aa99  nop     dword ptr [rax+rax+00h]
0x18002aa9e  test    al, al
0x18002aaa0  mov     ecx, r12d
0x18002aaa3  setnz   cl
0x18002aaa6  add     ecx, 2
0x18002aaa9  jmp     short loc_18002AA87
0x18002aaab  mov     eax, 0C00000E5h
0x18002aab0  jmp     loc_18002A949
```
