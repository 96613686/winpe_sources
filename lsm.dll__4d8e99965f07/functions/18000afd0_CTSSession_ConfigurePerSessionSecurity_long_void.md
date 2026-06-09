# CTSSession::ConfigurePerSessionSecurity(long,void *)

- ea: `0x18000afd0`
- end: `0x18000b24e`
- name: `?ConfigurePerSessionSecurity@CTSSession@@CAJJPEAX@Z`
- size: `638`
- prototype: `static int(int, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006f300`

## callees

- `0x1800077a0`
- `0x180009644`
- `0x18000afd0`
- `0x18000c17c`
- `0x18004e850`
- `0x18004ec20`
- `0x18004ec80`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x18000b0f4`
- `ntdll!NtQueryValueKey` at `0x18000b0f4`
- `ntdll!NtOpenKey` at `0x18000b0a9`
- `ntdll!NtOpenKey` at `0x18000b0a9`
- `ntdll!NtClose` at `0x18000b11c`
- `ntdll!NtClose` at `0x18000b11c`
- `ntdll!RtlInitUnicodeString` at `0x18000b066`
- `ntdll!RtlInitUnicodeString` at `0x18000b0c5`
- `ntdll!RtlInitUnicodeString` at `0x18000b066`
- `ntdll!RtlInitUnicodeString` at `0x18000b0c5`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18000b003`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18000b003`

## string_xrefs

- `0x18000b03c`: `\Registry\Machine\System\CurrentControlSet\Control\Session Manager`
- `0x18000b153`: `CTSSession::ConfigurePerSessionSecurity`
- `0x18000b208`: `CTSSession::ConfigurePerSessionSecurity`
- `0x18000b1e7`: `StringCchPrintf DD_PATH failed: 0x%x in %s`
- `0x18000b201`: `AddAccessToDirectory( user ) failed: 0x%x in %s`

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
  if ( !dword_1800E2894 )
  {
    KeyHandle = 0;
    ResultLength = 0;
    dword_1800E2894 = 1;
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
        dword_1800E2890 = v21;
      }
      NtClose(KeyHandle);
    }
  }
  if ( (dword_1800E2890 & 3) == 0 )
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
0x18000afd0  mov     [rsp-8+arg_10], rbx
0x18000afd5  mov     [rsp-8+arg_18], rsi
0x18000afda  push    rbp
0x18000afdb  push    rdi
0x18000afdc  push    r14
0x18000afde  lea     rbp, [rsp-1E0h]
0x18000afe6  sub     rsp, 2E0h
0x18000afed  mov     rax, cs:__security_cookie
0x18000aff4  xor     rax, rsp
0x18000aff7  mov     [rbp+1F0h+var_20], rax
0x18000affe  mov     r14, rdx
0x18000b001  mov     ebx, ecx
0x18000b003  call    cs:__imp_WTSGetServiceSessionId
0x18000b00a  nop     dword ptr [rax+rax+00h]
0x18000b00f  xor     edi, edi
0x18000b011  cmp     eax, ebx
0x18000b013  jnz     short loc_18000B01C
0x18000b015  mov     ebx, edi
0x18000b017  jmp     loc_18000B224
0x18000b01c  cmp     cs:dword_1800E2894, edi
0x18000b022  mov     esi, 2
0x18000b027  jnz     loc_18000B128
0x18000b02d  xorps   xmm1, xmm1
0x18000b030  mov     [rsp+2F0h+KeyHandle], rdi
0x18000b035  xorps   xmm0, xmm0
0x18000b038  mov     [rsp+2F0h+var_2C0], edi
0x18000b03c  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x18000b043  mov     cs:dword_1800E2894, 1
0x18000b04d  lea     rcx, [rsp+2F0h+DestinationString]; DestinationString
0x18000b052  movups  xmmword ptr [rsp+2F0h+DestinationString.Length], xmm0
0x18000b057  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.Length], xmm1
0x18000b05c  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.ObjectName], xmm1
0x18000b061  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.SecurityDescriptor], xmm1
0x18000b066  call    cs:__imp_RtlInitUnicodeString
0x18000b06d  nop     dword ptr [rax+rax+00h]
0x18000b072  lea     rax, [rsp+2F0h+DestinationString]
0x18000b077  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x18000b07f  xorps   xmm0, xmm0
0x18000b082  mov     [rsp+2F0h+ObjectAttributes.ObjectName], rax
0x18000b087  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x18000b08c  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], rdi
0x18000b091  mov     edx, 20019h; DesiredAccess
0x18000b096  mov     [rsp+2F0h+ObjectAttributes.Attributes], 40h ; '@'
0x18000b09e  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x18000b0a3  movdqu  xmmword ptr [rsp+2F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000b0a9  call    cs:__imp_NtOpenKey
0x18000b0b0  nop     dword ptr [rax+rax+00h]
0x18000b0b5  test    eax, eax
0x18000b0b7  js      short loc_18000B128
0x18000b0b9  lea     rdx, aProtectionmode; "ProtectionMode"
0x18000b0c0  lea     rcx, [rsp+2F0h+DestinationString]; DestinationString
0x18000b0c5  call    cs:__imp_RtlInitUnicodeString
0x18000b0cc  nop     dword ptr [rax+rax+00h]
0x18000b0d1  mov     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x18000b0d6  lea     rax, [rsp+2F0h+var_2C0]
0x18000b0db  mov     [rsp+2F0h+ResultLength], rax; ResultLength
0x18000b0e0  lea     r9, [rbp+1F0h+KeyValueInformation]; KeyValueInformation
0x18000b0e4  mov     r8d, esi; KeyValueInformationClass
0x18000b0e7  mov     [rsp+2F0h+Length], 40h ; '@'; Length
0x18000b0ef  lea     rdx, [rsp+2F0h+DestinationString]; ValueName
0x18000b0f4  call    cs:__imp_NtQueryValueKey
0x18000b0fb  nop     dword ptr [rax+rax+00h]
0x18000b100  test    eax, eax
0x18000b102  js      short loc_18000B117
0x18000b104  cmp     [rbp+1F0h+var_26C], 4
0x18000b108  jnz     short loc_18000B117
0x18000b10a  mov     eax, [rbp+1F0h+var_264]
0x18000b10d  test    eax, eax
0x18000b10f  jz      short loc_18000B117
0x18000b111  mov     cs:dword_1800E2890, eax
0x18000b117  mov     rcx, [rsp+2F0h+KeyHandle]; Handle
0x18000b11c  call    cs:__imp_NtClose
0x18000b123  nop     dword ptr [rax+rax+00h]
0x18000b128  test    byte ptr cs:dword_1800E2890, 3
0x18000b12f  jz      loc_18000B015
0x18000b135  mov     r9d, ebx
0x18000b138  lea     r8, aD; "%d"
0x18000b13f  mov     edx, 104h; unsigned __int64
0x18000b144  lea     rcx, [rbp+1F0h+var_230]; unsigned __int16 *
0x18000b148  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b14d  mov     ebx, eax
0x18000b14f  test    eax, eax
0x18000b151  jns     short loc_18000B173
0x18000b153  lea     r9, aCtssessionConf; "CTSSession::ConfigurePerSessionSecurity"
0x18000b15a  mov     r8d, eax
0x18000b15d  lea     rdx, aStringcchprint_0; "StringCchPrintf SessionId failed: 0x%x "...
0x18000b164  mov     ecx, 8; int
0x18000b169  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b16e  jmp     loc_18000B224
0x18000b173  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000b177  lea     rdx, [rbp+1F0h+var_230]
0x18000b17b  mov     rcx, r8
0x18000b17e  inc     rcx
0x18000b181  cmp     [rdx+rcx*2], di
0x18000b185  jnz     short loc_18000B17E
0x18000b187  lea     rbx, [rcx+17h]
0x18000b18b  mov     rax, rsi
0x18000b18e  mul     rbx
0x18000b191  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b198  cmovb   rax, r8
0x18000b19c  mov     rcx, rax; unsigned __int64
0x18000b19f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000b1a4  mov     rsi, rax
0x18000b1a7  test    rax, rax
0x18000b1aa  jnz     short loc_18000B1B3
0x18000b1ac  mov     ebx, 8007000Eh
0x18000b1b1  jmp     short loc_18000B224
0x18000b1b3  lea     rax, aDosdevices; "\\DosDevices"
0x18000b1ba  mov     rdx, rbx; unsigned __int64
0x18000b1bd  mov     [rsp+2F0h+ResultLength], rax
0x18000b1c2  lea     r9, aSessions; "\\Sessions\\"
0x18000b1c9  lea     rax, [rbp+1F0h+var_230]
0x18000b1cd  mov     rcx, rsi; unsigned __int16 *
0x18000b1d0  lea     r8, aSSS; "%s%s%s"
0x18000b1d7  mov     qword ptr [rsp+2F0h+Length], rax
0x18000b1dc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b1e1  mov     ebx, eax
0x18000b1e3  test    eax, eax
0x18000b1e5  jns     short loc_18000B1F0
0x18000b1e7  lea     rdx, aStringcchprint_1; "StringCchPrintf DD_PATH failed: 0x%x in"...
0x18000b1ee  jmp     short loc_18000B208
0x18000b1f0  mov     r8, r14; void *
0x18000b1f3  mov     rcx, rsi; SourceString
0x18000b1f6  call    ?AddAccessToDirectory@CUtils@@SAJPEBGKPEAX@Z; CUtils::AddAccessToDirectory(ushort const *,ulong,void *)
0x18000b1fb  mov     ebx, eax
0x18000b1fd  test    eax, eax
0x18000b1ff  jns     short loc_18000B21C
0x18000b201  lea     rdx, aAddaccesstodir; "AddAccessToDirectory( user ) failed: 0x"...
0x18000b208  lea     r9, aCtssessionConf; "CTSSession::ConfigurePerSessionSecurity"
0x18000b20f  mov     r8d, eax
0x18000b212  mov     ecx, 8; int
0x18000b217  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b21c  mov     rcx, rsi; void *
0x18000b21f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b224  mov     eax, ebx
0x18000b226  mov     rcx, [rbp+1F0h+var_20]
0x18000b22d  xor     rcx, rsp; StackCookie
0x18000b230  call    __security_check_cookie
0x18000b235  lea     r11, [rsp+2F0h+var_10]
0x18000b23d  mov     rbx, [r11+30h]
0x18000b241  mov     rsi, [r11+38h]
0x18000b245  mov     rsp, r11
0x18000b248  pop     r14
0x18000b24a  pop     rdi
0x18000b24b  pop     rbp
0x18000b24c  retn
```
