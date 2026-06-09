# OpenRegKey

- ea: `0x18002ad10`
- end: `0x18002b035`
- name: `OpenRegKey`
- size: `805`
- prototype: `__int64 __usercall@<rax>(PHANDLE KeyHandle@<rcx>, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18002aabc`
- `0x18002ad10`
- `0x18012c3ac`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002adf9`
- `ntdll!RtlInitUnicodeString` at `0x18002adf9`
- `ntdll!NtOpenKey` at `0x18002ae41`
- `ntdll!NtOpenKey` at `0x18002ae41`
- `ntdll!NtCreateKey` at `0x18002ae7e`
- `ntdll!NtCreateKey` at `0x18002ae7e`
- `ntdll!RtlIsMultiSessionSku` at `0x18002aff2`
- `ntdll!RtlIsMultiSessionSku` at `0x18002aff2`
- `ntdll!RtlOpenCurrentUser` at `0x18002ad96`
- `ntdll!RtlOpenCurrentUser` at `0x18002adbf`
- `ntdll!RtlOpenCurrentUser` at `0x18002ad96`
- `ntdll!RtlOpenCurrentUser` at `0x18002adbf`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18002b012`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18002b012`
- `ntdll!NtClose` at `0x18002ae96`
- `ntdll!NtClose` at `0x18002afa3`
- `ntdll!NtClose` at `0x18002ae96`
- `ntdll!NtClose` at `0x18002afa3`

## pseudocode

```c
int __fastcall OpenRegKey(PHANDLE KeyHandle, WCHAR *a2, WCHAR *a3, ACCESS_MASK a4, char a5)
{
  WCHAR *v8; // rax
  HANDLE v9; // rdi
  int v10; // ecx
  int result; // eax
  __int64 v12; // rdx
  NTSTATUS v13; // ebx
  WCHAR *v14; // rcx
  WCHAR *v15; // r10
  __int64 v16; // rcx
  __int64 v17; // r9
  __int64 v18; // rcx
  WCHAR *v19; // rax
  __int64 v20; // r8
  WCHAR *v21; // r9
  WCHAR *v22; // rdx
  int v23; // ecx
  HANDLE KeyHandlea; // [rsp+40h] [rbp-C0h] BYREF
  ULONG Disposition; // [rsp+48h] [rbp-B8h] BYREF
  int v26; // [rsp+4Ch] [rbp-B4h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SourceString[512]; // [rsp+90h] [rbp-70h] BYREF

  KeyHandlea = 0;
  Disposition = 0;
  v8 = a2;
  v9 = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  if ( a2 )
  {
    if ( *a2 )
    {
      v12 = 2147483646;
      v15 = SourceString;
      v16 = 2147483646;
      v17 = 512;
      do
      {
        if ( !v16 )
          break;
        if ( !*v8 )
          break;
        *v15++ = *v8++;
        --v16;
        --v17;
      }
      while ( v17 );
      v14 = v15 - 1;
      if ( v17 )
        v14 = v15;
      *v14 = 0;
      if ( !v17 )
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
      v23 = v10 - 2;
      if ( v23 )
      {
        if ( v23 != 1 )
          return -1073741595;
        v26 = 0;
        result = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, &KeyHandlea, &v26);
      }
      else
      {
        result = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, &KeyHandlea);
      }
    }
    if ( result < 0 )
      return result;
  }
  v9 = KeyHandlea;
  v12 = 2147483646;
  SourceString[0] = 0;
LABEL_10:
  if ( a3 )
  {
    v18 = 512;
    v19 = SourceString;
    do
    {
      if ( !*v19 )
        break;
      ++v19;
      --v18;
    }
    while ( v18 );
    if ( !v18 )
      goto LABEL_40;
    v20 = v18;
    v21 = &SourceString[512 - v18];
    do
    {
      if ( !v12 )
        break;
      if ( !*a3 )
        break;
      *v21++ = *a3++;
      --v12;
      --v20;
    }
    while ( v20 );
    v22 = v21 - 1;
    if ( v20 )
      v22 = v21;
    *v22 = 0;
    if ( !v20 )
    {
LABEL_40:
      if ( v9 )
        NtClose(v9);
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
  v13 = NtOpenKey(KeyHandle, a4, &ObjectAttributes);
  if ( v13 < 0 && (a5 & 2) != 0 )
    v13 = NtCreateKey(KeyHandle, a4, &ObjectAttributes, 0, 0, 0, &Disposition);
  if ( KeyHandlea )
    NtClose(KeyHandlea);
  if ( v13 < 0 )
    *KeyHandle = 0;
  return v13;
}

```

## disassembly

```asm
0x18002ad10  mov     [rsp-8+arg_8], rbx
0x18002ad15  push    rbp
0x18002ad16  push    rsi
0x18002ad17  push    rdi
0x18002ad18  push    r14
0x18002ad1a  push    r15
0x18002ad1c  lea     rbp, [rsp-3A0h]
0x18002ad24  sub     rsp, 4A0h
0x18002ad2b  mov     rax, cs:__security_cookie
0x18002ad32  xor     rax, rsp
0x18002ad35  mov     [rbp+3C0h+var_30], rax
0x18002ad3c  xor     r15d, r15d
0x18002ad3f  xorps   xmm0, xmm0
0x18002ad42  mov     rsi, rcx
0x18002ad45  mov     [rsp+4C0h+KeyHandle], r15
0x18002ad4a  xor     ecx, ecx
0x18002ad4c  mov     [rsp+4C0h+var_478], r15d
0x18002ad51  mov     r14d, r9d
0x18002ad54  mov     rbx, r8
0x18002ad57  mov     rax, rdx
0x18002ad5a  mov     edi, r15d
0x18002ad5d  movups  xmmword ptr [rsp+4C0h+ObjectAttributes.ObjectName], xmm0
0x18002ad62  movups  xmmword ptr [rsp+4C0h+ObjectAttributes.Length], xmm0
0x18002ad67  movups  xmmword ptr [rsp+4C0h+ObjectAttributes+1Ch], xmm0
0x18002ad6c  movups  xmmword ptr [rbp+3C0h+DestinationString.Length], xmm0
0x18002ad70  test    rdx, rdx
0x18002ad73  jnz     short loc_18002ADAC
0x18002ad75  mov     ecx, cs:dword_1803A7170
0x18002ad7b  test    ecx, ecx
0x18002ad7d  jz      loc_18002AFF2
0x18002ad83  cmp     ecx, 1
0x18002ad86  jnz     loc_18002AFB4
0x18002ad8c  lea     rdx, [rsp+4C0h+KeyHandle]; KeyHandle
0x18002ad91  mov     ecx, 2000000h; DesiredAccess
0x18002ad96  call    cs:__imp_RtlOpenCurrentUser
0x18002ad9d  nop     dword ptr [rax+rax+00h]
0x18002ada2  test    eax, eax
0x18002ada4  js      loc_18002AEC7
0x18002adaa  jmp     short loc_18002ADD3
0x18002adac  cmp     [rdx], cx
0x18002adaf  jnz     loc_18002AEEE
0x18002adb5  lea     rdx, [rsp+4C0h+KeyHandle]; KeyHandle
0x18002adba  mov     ecx, 2000000h; DesiredAccess
0x18002adbf  call    cs:__imp_RtlOpenCurrentUser
0x18002adc6  nop     dword ptr [rax+rax+00h]
0x18002adcb  test    eax, eax
0x18002adcd  js      loc_18002AEC7
0x18002add3  mov     rdi, [rsp+4C0h+KeyHandle]
0x18002add8  mov     edx, 7FFFFFFEh
0x18002addd  mov     [rbp+3C0h+SourceString], r15w
0x18002ade2  mov     r8d, 200h
0x18002ade8  test    rbx, rbx
0x18002adeb  jnz     loc_18002AF28
0x18002adf1  lea     rdx, [rbp+3C0h+SourceString]; SourceString
0x18002adf5  lea     rcx, [rbp+3C0h+DestinationString]; DestinationString
0x18002adf9  call    cs:__imp_RtlInitUnicodeString
0x18002ae00  nop     dword ptr [rax+rax+00h]
0x18002ae05  mov     rax, [rsp+4C0h+KeyHandle]
0x18002ae0a  lea     r8, [rsp+4C0h+ObjectAttributes]; ObjectAttributes
0x18002ae0f  mov     [rsp+4C0h+ObjectAttributes.RootDirectory], rax
0x18002ae14  xorps   xmm0, xmm0
0x18002ae17  lea     rax, [rbp+3C0h+DestinationString]
0x18002ae1b  mov     [rsp+4C0h+ObjectAttributes.Length], 30h ; '0'
0x18002ae23  mov     edx, r14d; DesiredAccess
0x18002ae26  mov     [rsp+4C0h+ObjectAttributes.ObjectName], rax
0x18002ae2b  mov     rcx, rsi; KeyHandle
0x18002ae2e  mov     [rsp+4C0h+ObjectAttributes.Attributes], 40h ; '@'
0x18002ae36  movdqu  xmmword ptr [rsp+4C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002ae3c  mov     [rsp+4C0h+var_478], r15d
0x18002ae41  call    cs:__imp_NtOpenKey
0x18002ae48  nop     dword ptr [rax+rax+00h]
0x18002ae4d  mov     ebx, eax
0x18002ae4f  test    eax, eax
0x18002ae51  jns     short loc_18002AE8C
0x18002ae53  test    [rbp+3C0h+arg_20], 2
0x18002ae5a  jz      short loc_18002AE8C
0x18002ae5c  lea     rax, [rsp+4C0h+var_478]
0x18002ae61  xor     r9d, r9d; TitleIndex
0x18002ae64  mov     [rsp+4C0h+Disposition], rax; Disposition
0x18002ae69  lea     r8, [rsp+4C0h+ObjectAttributes]; ObjectAttributes
0x18002ae6e  mov     [rsp+4C0h+CreateOptions], r15d; CreateOptions
0x18002ae73  mov     edx, r14d; DesiredAccess
0x18002ae76  mov     rcx, rsi; KeyHandle
0x18002ae79  mov     [rsp+4C0h+Class], r15; Class
0x18002ae7e  call    cs:__imp_NtCreateKey
0x18002ae85  nop     dword ptr [rax+rax+00h]
0x18002ae8a  mov     ebx, eax
0x18002ae8c  mov     rcx, [rsp+4C0h+KeyHandle]; Handle
0x18002ae91  test    rcx, rcx
0x18002ae94  jz      short loc_18002AEA2
0x18002ae96  call    cs:__imp_NtClose
0x18002ae9d  nop     dword ptr [rax+rax+00h]
0x18002aea2  test    ebx, ebx
0x18002aea4  jns     short loc_18002AEA9
0x18002aea6  mov     [rsi], r15
0x18002aea9  mov     eax, ebx
0x18002aeab  jmp     short loc_18002AEC7
0x18002aead  test    r9, r9
0x18002aeb0  lea     rcx, [r10-2]
0x18002aeb4  cmovnz  rcx, r10
0x18002aeb8  mov     [rcx], r15w
0x18002aebc  jnz     loc_18002ADE8
0x18002aec2  mov     eax, 0C0000001h
0x18002aec7  mov     rcx, [rbp+3C0h+var_30]
0x18002aece  xor     rcx, rsp; StackCookie
0x18002aed1  call    __security_check_cookie
0x18002aed6  mov     rbx, [rsp+4C0h+arg_8]
0x18002aede  add     rsp, 4A0h
0x18002aee5  pop     r15
0x18002aee7  pop     r14
0x18002aee9  pop     rdi
0x18002aeea  pop     rsi
0x18002aeeb  pop     rbp
0x18002aeec  retn
0x18002aeee  mov     edx, 7FFFFFFEh
0x18002aef3  lea     r10, [rbp+3C0h+SourceString]
0x18002aef7  mov     r8d, 200h
0x18002aefd  mov     ecx, edx
0x18002aeff  mov     r9d, r8d
0x18002af02  test    rcx, rcx
0x18002af05  jz      short loc_18002AEAD
0x18002af07  movzx   r11d, word ptr [rax]
0x18002af0b  test    r11w, r11w
0x18002af0f  jz      short loc_18002AEAD
0x18002af11  mov     [r10], r11w
0x18002af15  add     rax, 2
0x18002af19  add     r10, 2
0x18002af1d  dec     rcx
0x18002af20  sub     r9, 1
0x18002af24  jnz     short loc_18002AF02
0x18002af26  jmp     short loc_18002AEAD
0x18002af28  mov     rcx, r8
0x18002af2b  lea     rax, [rbp+3C0h+SourceString]
0x18002af2f  nop
0x18002af30  cmp     [rax], r15w
0x18002af34  jz      short loc_18002AF40
0x18002af36  add     rax, 2
0x18002af3a  sub     rcx, 1
0x18002af3e  jnz     short loc_18002AF30
0x18002af40  mov     r9, r8
0x18002af43  sub     r9, rcx
0x18002af46  test    rcx, rcx
0x18002af49  cmovz   r9, r15
0x18002af4d  jz      short loc_18002AF97
0x18002af4f  sub     r8, r9
0x18002af52  lea     r9, [rbp+r9*2+3C0h+SourceString]
0x18002af57  jz      short loc_18002AF82
0x18002af59  nop     dword ptr [rax+00000000h]
0x18002af60  test    rdx, rdx
0x18002af63  jz      short loc_18002AF82
0x18002af65  movzx   eax, word ptr [rbx]
0x18002af68  test    ax, ax
0x18002af6b  jz      short loc_18002AF82
0x18002af6d  mov     [r9], ax
0x18002af71  add     rbx, 2
0x18002af75  add     r9, 2
0x18002af79  dec     rdx
0x18002af7c  sub     r8, 1
0x18002af80  jnz     short loc_18002AF60
0x18002af82  test    r8, r8
0x18002af85  lea     rdx, [r9-2]
0x18002af89  cmovnz  rdx, r9
0x18002af8d  mov     [rdx], r15w
0x18002af91  jnz     loc_18002ADF1
0x18002af97  test    rdi, rdi
0x18002af9a  jz      loc_18002AEC2
0x18002afa0  mov     rcx, rdi; Handle
0x18002afa3  call    cs:__imp_NtClose
0x18002afaa  nop     dword ptr [rax+rax+00h]
0x18002afaf  jmp     loc_18002AEC2
0x18002afb4  sub     ecx, 2
0x18002afb7  jnz     short loc_18002AFCD
0x18002afb9  lea     rdx, [rsp+4C0h+KeyHandle]; KeyHandle
0x18002afbe  mov     ecx, 2000000h; DesiredAccess
0x18002afc3  call    OpenGlobalizationUserSettingsKey_ForSingleUserModel
0x18002afc8  jmp     loc_18002ADA2
0x18002afcd  cmp     ecx, 1
0x18002afd0  jnz     short loc_18002B02B
0x18002afd2  lea     r9, [rsp+4C0h+var_474]
0x18002afd7  mov     [rsp+4C0h+var_474], r15d
0x18002afdc  lea     r8, [rsp+4C0h+KeyHandle]; KeyHandle
0x18002afe1  xor     edx, edx; Sid
0x18002afe3  mov     ecx, 2000000h; DesiredAccess
0x18002afe8  call    OpenGlobalizationUserSettingsKey_ForMua
0x18002afed  jmp     loc_18002ADA2
0x18002aff2  call    cs:__imp_RtlIsMultiSessionSku
0x18002aff9  nop     dword ptr [rax+rax+00h]
0x18002affe  test    al, al
0x18002b000  jz      short loc_18002B012
0x18002b002  mov     ecx, 1
0x18002b007  mov     cs:dword_1803A7170, ecx
0x18002b00d  jmp     loc_18002AD83
0x18002b012  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x18002b019  nop     dword ptr [rax+rax+00h]
0x18002b01e  test    al, al
0x18002b020  mov     ecx, r15d
0x18002b023  setnz   cl
0x18002b026  add     ecx, 2
0x18002b029  jmp     short loc_18002B007
0x18002b02b  mov     eax, 0C00000E5h
0x18002b030  jmp     loc_18002AEC7
```
