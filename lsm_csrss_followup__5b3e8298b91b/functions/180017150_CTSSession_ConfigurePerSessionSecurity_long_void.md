# CTSSession::ConfigurePerSessionSecurity(long,void *)

- ea: `0x180017150`
- end: `0x1800173a9`
- name: `?ConfigurePerSessionSecurity@CTSSession@@CAJJPEAX@Z`
- size: `601`
- prototype: `static int(int, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006b480`

## callees

- `0x1800074c0`
- `0x180017150`
- `0x180018200`
- `0x180018a20`
- `0x18004b460`
- `0x18004b830`
- `0x18004b890`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x18001725c`
- `ntdll!NtQueryValueKey` at `0x18001725c`
- `ntdll!NtOpenKey` at `0x18001721d`
- `ntdll!NtOpenKey` at `0x18001721d`
- `ntdll!NtClose` at `0x18001727e`
- `ntdll!NtClose` at `0x18001727e`
- `ntdll!RtlInitUnicodeString` at `0x1800171e0`
- `ntdll!RtlInitUnicodeString` at `0x180017233`
- `ntdll!RtlInitUnicodeString` at `0x1800171e0`
- `ntdll!RtlInitUnicodeString` at `0x180017233`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180017183`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180017183`

## string_xrefs

- `0x1800171b6`: `\Registry\Machine\System\CurrentControlSet\Control\Session Manager`
- `0x1800172af`: `CTSSession::ConfigurePerSessionSecurity`
- `0x180017364`: `CTSSession::ConfigurePerSessionSecurity`
- `0x180017343`: `StringCchPrintf DD_PATH failed: 0x%x in %s`
- `0x18001735d`: `AddAccessToDirectory( user ) failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSSession::ConfigurePerSessionSecurity(unsigned int a1, void *a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  __int64 v6; // rcx
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rax
  unsigned __int16 *v9; // rsi
  int v10; // eax
  __int64 v11; // rdx
  const struct std::nothrow_t *v12; // rdx
  int v13; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+80h] [rbp-80h] BYREF
  int v20; // [rsp+84h] [rbp-7Ch]
  int v21; // [rsp+8Ch] [rbp-74h]
  unsigned __int16 v22[264]; // [rsp+C0h] [rbp-40h] BYREF

  if ( (unsigned int)WTSGetServiceSessionId() == a1 )
    return 0;
  if ( !dword_1800DD884 )
  {
    KeyHandle = 0;
    ResultLength = 0;
    dword_1800DD884 = 1;
    DestinationString = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    RtlInitUnicodeString(
      &DestinationString,
      L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Session Manager");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"ProtectionMode");
      if ( NtQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             KeyValueInformation,
             0x40u,
             &ResultLength) >= 0
        && v20 == 4
        && v21 )
      {
        dword_1800DD880 = v21;
      }
      NtClose(KeyHandle);
    }
  }
  if ( (dword_1800DD880 & 3) == 0 )
  {
    return 0;
  }
  else
  {
    v5 = StringCchPrintfW(v22, 0x104u, L"%d", a1);
    v4 = v5;
    if ( v5 >= 0 )
    {
      v6 = -1;
      do
        ++v6;
      while ( v22[v6] );
      v7 = v6 + 23;
      v8 = 2 * (v6 + 23);
      if ( !is_mul_ok(v6 + 23, 2u) )
        v8 = -1;
      v9 = (unsigned __int16 *)operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
      if ( v9 )
      {
        v10 = StringCchPrintfW(v9, v7, L"%s%s%s", L"\\Sessions\\", v22, L"\\DosDevices");
        v4 = v10;
        if ( v10 >= 0 )
        {
          v13 = CUtils::AddAccessToDirectory(v9, v11, a2);
          v4 = v13;
          if ( v13 < 0 )
            _DbgPrintMessage(
              8,
              "AddAccessToDirectory( user ) failed: 0x%x in %s",
              (unsigned int)v13,
              "CTSSession::ConfigurePerSessionSecurity");
        }
        else
        {
          _DbgPrintMessage(
            8,
            "StringCchPrintf DD_PATH failed: 0x%x in %s",
            (unsigned int)v10,
            "CTSSession::ConfigurePerSessionSecurity");
        }
        operator delete(v9, v12);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      _DbgPrintMessage(8, "StringCchPrintf SessionId failed: 0x%x in %s", v5, "CTSSession::ConfigurePerSessionSecurity");
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180017150  mov     [rsp-8+arg_10], rbx
0x180017155  mov     [rsp-8+arg_18], rsi
0x18001715a  push    rbp
0x18001715b  push    rdi
0x18001715c  push    r14
0x18001715e  lea     rbp, [rsp-1E0h]
0x180017166  sub     rsp, 2E0h
0x18001716d  mov     rax, cs:__security_cookie
0x180017174  xor     rax, rsp
0x180017177  mov     [rbp+1F0h+var_20], rax
0x18001717e  mov     r14, rdx
0x180017181  mov     ebx, ecx
0x180017183  call    cs:__imp_WTSGetServiceSessionId
0x180017189  xor     edi, edi
0x18001718b  cmp     eax, ebx
0x18001718d  jnz     short loc_180017196
0x18001718f  mov     ebx, edi
0x180017191  jmp     loc_180017380
0x180017196  cmp     cs:dword_1800DD884, edi
0x18001719c  mov     esi, 2
0x1800171a1  jnz     loc_180017284
0x1800171a7  xorps   xmm1, xmm1
0x1800171aa  mov     [rsp+2F0h+KeyHandle], rdi
0x1800171af  xorps   xmm0, xmm0
0x1800171b2  mov     [rsp+2F0h+var_2C0], edi
0x1800171b6  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800171bd  mov     cs:dword_1800DD884, 1
0x1800171c7  lea     rcx, [rsp+2F0h+DestinationString]; DestinationString
0x1800171cc  movups  xmmword ptr [rsp+2F0h+DestinationString.Length], xmm0
0x1800171d1  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.Length], xmm1
0x1800171d6  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.ObjectName], xmm1
0x1800171db  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800171e0  call    cs:__imp_RtlInitUnicodeString
0x1800171e6  lea     rax, [rsp+2F0h+DestinationString]
0x1800171eb  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x1800171f3  xorps   xmm0, xmm0
0x1800171f6  mov     [rsp+2F0h+ObjectAttributes.ObjectName], rax
0x1800171fb  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x180017200  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], rdi
0x180017205  mov     edx, 20019h; DesiredAccess
0x18001720a  mov     [rsp+2F0h+ObjectAttributes.Attributes], 40h ; '@'
0x180017212  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x180017217  movdqu  xmmword ptr [rsp+2F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001721d  call    cs:__imp_NtOpenKey
0x180017223  test    eax, eax
0x180017225  js      short loc_180017284
0x180017227  lea     rdx, aProtectionmode; "ProtectionMode"
0x18001722e  lea     rcx, [rsp+2F0h+DestinationString]; DestinationString
0x180017233  call    cs:__imp_RtlInitUnicodeString
0x180017239  mov     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x18001723e  lea     rax, [rsp+2F0h+var_2C0]
0x180017243  mov     [rsp+2F0h+ResultLength], rax; ResultLength
0x180017248  lea     r9, [rbp+1F0h+KeyValueInformation]; KeyValueInformation
0x18001724c  mov     r8d, esi; KeyValueInformationClass
0x18001724f  mov     [rsp+2F0h+Length], 40h ; '@'; Length
0x180017257  lea     rdx, [rsp+2F0h+DestinationString]; ValueName
0x18001725c  call    cs:__imp_NtQueryValueKey
0x180017262  test    eax, eax
0x180017264  js      short loc_180017279
0x180017266  cmp     [rbp+1F0h+var_26C], 4
0x18001726a  jnz     short loc_180017279
0x18001726c  mov     eax, [rbp+1F0h+var_264]
0x18001726f  test    eax, eax
0x180017271  jz      short loc_180017279
0x180017273  mov     cs:dword_1800DD880, eax
0x180017279  mov     rcx, [rsp+2F0h+KeyHandle]; Handle
0x18001727e  call    cs:__imp_NtClose
0x180017284  test    byte ptr cs:dword_1800DD880, 3
0x18001728b  jz      loc_18001718F
0x180017291  mov     r9d, ebx
0x180017294  lea     r8, aD; "%d"
0x18001729b  mov     edx, 104h; unsigned __int64
0x1800172a0  lea     rcx, [rbp+1F0h+var_230]; unsigned __int16 *
0x1800172a4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800172a9  mov     ebx, eax
0x1800172ab  test    eax, eax
0x1800172ad  jns     short loc_1800172CF
0x1800172af  lea     r9, aCtssessionConf; "CTSSession::ConfigurePerSessionSecurity"
0x1800172b6  mov     r8d, eax
0x1800172b9  lea     rdx, aStringcchprint_0; "StringCchPrintf SessionId failed: 0x%x "...
0x1800172c0  mov     ecx, 8; int
0x1800172c5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800172ca  jmp     loc_180017380
0x1800172cf  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800172d3  lea     rdx, [rbp+1F0h+var_230]
0x1800172d7  mov     rcx, r8
0x1800172da  inc     rcx
0x1800172dd  cmp     [rdx+rcx*2], di
0x1800172e1  jnz     short loc_1800172DA
0x1800172e3  lea     rbx, [rcx+17h]
0x1800172e7  mov     rax, rsi
0x1800172ea  mul     rbx
0x1800172ed  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800172f4  cmovb   rax, r8
0x1800172f8  mov     rcx, rax; unsigned __int64
0x1800172fb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180017300  mov     rsi, rax
0x180017303  test    rax, rax
0x180017306  jnz     short loc_18001730F
0x180017308  mov     ebx, 8007000Eh
0x18001730d  jmp     short loc_180017380
0x18001730f  lea     rax, aDosdevices; "\\DosDevices"
0x180017316  mov     rdx, rbx; unsigned __int64
0x180017319  mov     [rsp+2F0h+ResultLength], rax
0x18001731e  lea     r9, aSessions; "\\Sessions\\"
0x180017325  lea     rax, [rbp+1F0h+var_230]
0x180017329  mov     rcx, rsi; unsigned __int16 *
0x18001732c  lea     r8, aSSS; "%s%s%s"
0x180017333  mov     qword ptr [rsp+2F0h+Length], rax
0x180017338  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001733d  mov     ebx, eax
0x18001733f  test    eax, eax
0x180017341  jns     short loc_18001734C
0x180017343  lea     rdx, aStringcchprint_1; "StringCchPrintf DD_PATH failed: 0x%x in"...
0x18001734a  jmp     short loc_180017364
0x18001734c  mov     r8, r14; void *
0x18001734f  mov     rcx, rsi; SourceString
0x180017352  call    ?AddAccessToDirectory@CUtils@@SAJPEBGKPEAX@Z; CUtils::AddAccessToDirectory(ushort const *,ulong,void *)
0x180017357  mov     ebx, eax
0x180017359  test    eax, eax
0x18001735b  jns     short loc_180017378
0x18001735d  lea     rdx, aAddaccesstodir; "AddAccessToDirectory( user ) failed: 0x"...
0x180017364  lea     r9, aCtssessionConf; "CTSSession::ConfigurePerSessionSecurity"
0x18001736b  mov     r8d, eax
0x18001736e  mov     ecx, 8; int
0x180017373  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180017378  mov     rcx, rsi; void *
0x18001737b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017380  mov     eax, ebx
0x180017382  mov     rcx, [rbp+1F0h+var_20]
0x180017389  xor     rcx, rsp; StackCookie
0x18001738c  call    __security_check_cookie
0x180017391  lea     r11, [rsp+2F0h+var_10]
0x180017399  mov     rbx, [r11+30h]
0x18001739d  mov     rsi, [r11+38h]
0x1800173a1  mov     rsp, r11
0x1800173a4  pop     r14
0x1800173a6  pop     rdi
0x1800173a7  pop     rbp
0x1800173a8  retn
```
