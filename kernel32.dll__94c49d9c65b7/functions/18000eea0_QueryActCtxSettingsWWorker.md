# QueryActCtxSettingsWWorker

- ea: `0x18000eea0`
- end: `0x18000f026`
- name: `QueryActCtxSettingsWWorker`
- size: `390`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000eea0`
- `0x18000f920`

## import_xrefs

- `ntdll!RtlQueryActivationContextApplicationSettings` at `0x18000ef1f`
- `ntdll!RtlQueryActivationContextApplicationSettings` at `0x18000ef1f`
- `ntdll!RtlCompareUnicodeString` at `0x18000efe7`
- `ntdll!RtlCompareUnicodeString` at `0x18000efe7`
- `ntdll!RtlInitUnicodeString` at `0x18000efc0`
- `ntdll!RtlInitUnicodeString` at `0x18000efd6`
- `ntdll!RtlInitUnicodeString` at `0x18000efc0`
- `ntdll!RtlInitUnicodeString` at `0x18000efd6`

## string_xrefs

- `0x18000ef56`: `http://schemas.microsoft.com/SMI/2005/WindowsSettings`
- `0x18000efb5`: `http://schemas.microsoft.com/SMI/2024/WindowsSettings`
- `0x18000ef9f`: `http://schemas.microsoft.com/SMI/2019/WindowsSettings`
- `0x18000ef73`: `http://schemas.microsoft.com/SMI/2013/WindowsSettings`
- `0x18000efaa`: `http://schemas.microsoft.com/SMI/2020/WindowsSettings`
- `0x18000ef7e`: `http://schemas.microsoft.com/SMI/2014/WindowsSettings`
- `0x18000ef89`: `http://schemas.microsoft.com/SMI/2016/WindowsSettings`
- `0x18000ef68`: `http://schemas.microsoft.com/SMI/2011/WindowsSettings`
- `0x18000ef94`: `http://schemas.microsoft.com/SMI/2017/WindowsSettings`

## pseudocode

```c
__int64 __fastcall QueryActCtxSettingsWWorker(
        int a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7)
{
  unsigned int v7; // ebx
  __int64 v10; // rax
  int ActivationContextApplicationSettings; // eax
  __int64 v12; // rcx
  __int64 i; // rdi
  UNICODE_STRING String2; // [rsp+40h] [rbp-71h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-61h] BYREF
  PCWSTR SourceString[18]; // [rsp+60h] [rbp-51h]

  v7 = 0;
  v10 = a2;
  DestinationString = 0;
  String2 = 0;
  if ( a7 )
    *a7 = 0;
  if ( a1 )
  {
    v12 = 3221225711LL;
  }
  else if ( a4 )
  {
    if ( !a6 || a5 )
    {
      if ( a3 )
      {
        SourceString[0] = L"http://schemas.microsoft.com/SMI/2005/WindowsSettings";
        SourceString[1] = L"http://schemas.microsoft.com/SMI/2011/WindowsSettings";
        SourceString[2] = L"http://schemas.microsoft.com/SMI/2013/WindowsSettings";
        SourceString[3] = L"http://schemas.microsoft.com/SMI/2014/WindowsSettings";
        SourceString[4] = L"http://schemas.microsoft.com/SMI/2016/WindowsSettings";
        SourceString[5] = L"http://schemas.microsoft.com/SMI/2017/WindowsSettings";
        SourceString[6] = L"http://schemas.microsoft.com/SMI/2019/WindowsSettings";
        SourceString[7] = L"http://schemas.microsoft.com/SMI/2020/WindowsSettings";
        SourceString[8] = L"http://schemas.microsoft.com/SMI/2024/WindowsSettings";
        RtlInitUnicodeString(&DestinationString, a3);
        for ( i = 0; (unsigned int)i < 9; i = (unsigned int)(i + 1) )
        {
          RtlInitUnicodeString(&String2, SourceString[i]);
          if ( !RtlCompareUnicodeString(&DestinationString, &String2, 0) )
          {
            v10 = a2;
            goto LABEL_7;
          }
        }
        v12 = 3221225713LL;
      }
      else
      {
LABEL_7:
        ActivationContextApplicationSettings = RtlQueryActivationContextApplicationSettings(0, v10, a3, a4, a5, a6, a7);
        if ( ActivationContextApplicationSettings >= 0 )
          return 1;
        v12 = (unsigned int)ActivationContextApplicationSettings;
      }
    }
    else
    {
      v12 = 3221225485LL;
    }
  }
  else
  {
    v12 = 3221225714LL;
  }
  BaseSetLastNTError(v12);
  return v7;
}

```

## disassembly

```asm
0x18000eea0  mov     [rsp-8+arg_8], rdx
0x18000eea5  push    rbp
0x18000eea6  push    rbx
0x18000eea7  push    rsi
0x18000eea8  push    rdi
0x18000eea9  push    r12
0x18000eeab  push    r13
0x18000eead  push    r14
0x18000eeaf  push    r15
0x18000eeb1  lea     rbp, [rsp-7]
0x18000eeb6  sub     rsp, 0B8h
0x18000eebd  mov     rsi, [rbp+3Fh+arg_30]
0x18000eec1  xor     ebx, ebx
0x18000eec3  xorps   xmm0, xmm0
0x18000eec6  xorps   xmm1, xmm1
0x18000eec9  mov     r13, r9
0x18000eecc  mov     r12, r8
0x18000eecf  mov     rax, rdx
0x18000eed2  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x18000eed6  movups  xmmword ptr [rbp+3Fh+String2.Length], xmm1
0x18000eeda  test    rsi, rsi
0x18000eedd  jz      short loc_18000EEE2
0x18000eedf  mov     [rsi], rbx
0x18000eee2  test    ecx, ecx
0x18000eee4  jnz     loc_18000EFFE
0x18000eeea  test    r13, r13
0x18000eeed  jz      loc_18000F01C
0x18000eef3  mov     r15, [rbp+3Fh+arg_28]
0x18000eef7  mov     r14, [rbp+3Fh+arg_20]
0x18000eefb  test    r15, r15
0x18000eefe  jnz     short loc_18000EF4A
0x18000ef00  test    r12, r12
0x18000ef03  jnz     short loc_18000EF56
0x18000ef05  mov     [rsp+0F0h+var_C0], rsi
0x18000ef0a  mov     r9, r13
0x18000ef0d  mov     [rsp+0F0h+var_C8], r15
0x18000ef12  mov     r8, r12
0x18000ef15  mov     rdx, rax
0x18000ef18  mov     [rsp+0F0h+var_D0], r14
0x18000ef1d  xor     ecx, ecx
0x18000ef1f  call    cs:__imp_RtlQueryActivationContextApplicationSettings
0x18000ef25  test    eax, eax
0x18000ef27  jns     loc_18000F008
0x18000ef2d  mov     ecx, eax
0x18000ef2f  call    BaseSetLastNTError
0x18000ef34  mov     eax, ebx
0x18000ef36  add     rsp, 0B8h
0x18000ef3d  pop     r15
0x18000ef3f  pop     r14
0x18000ef41  pop     r13
0x18000ef43  pop     r12
0x18000ef45  pop     rdi
0x18000ef46  pop     rsi
0x18000ef47  pop     rbx
0x18000ef48  pop     rbp
0x18000ef49  retn
0x18000ef4a  test    r14, r14
0x18000ef4d  jnz     short loc_18000EF00
0x18000ef4f  mov     ecx, 0C000000Dh
0x18000ef54  jmp     short loc_18000EF2F
0x18000ef56  lea     rax, aHttpSchemasMic_6; "http://schemas.microsoft.com/SMI/2005/W"...
0x18000ef5d  mov     rdx, r12; SourceString
0x18000ef60  mov     [rbp+3Fh+SourceString], rax
0x18000ef64  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x18000ef68  lea     rax, aHttpSchemasMic_7; "http://schemas.microsoft.com/SMI/2011/W"...
0x18000ef6f  mov     [rbp+3Fh+var_88], rax
0x18000ef73  lea     rax, aHttpSchemasMic_2; "http://schemas.microsoft.com/SMI/2013/W"...
0x18000ef7a  mov     [rbp+3Fh+var_80], rax
0x18000ef7e  lea     rax, aHttpSchemasMic_5; "http://schemas.microsoft.com/SMI/2014/W"...
0x18000ef85  mov     [rbp+3Fh+var_78], rax
0x18000ef89  lea     rax, aHttpSchemasMic_3; "http://schemas.microsoft.com/SMI/2016/W"...
0x18000ef90  mov     [rbp+3Fh+var_70], rax
0x18000ef94  lea     rax, aHttpSchemasMic_1; "http://schemas.microsoft.com/SMI/2017/W"...
0x18000ef9b  mov     [rbp+3Fh+var_68], rax
0x18000ef9f  lea     rax, aHttpSchemasMic; "http://schemas.microsoft.com/SMI/2019/W"...
0x18000efa6  mov     [rbp+3Fh+var_60], rax
0x18000efaa  lea     rax, aHttpSchemasMic_4; "http://schemas.microsoft.com/SMI/2020/W"...
0x18000efb1  mov     [rbp+3Fh+var_58], rax
0x18000efb5  lea     rax, aHttpSchemasMic_0; "http://schemas.microsoft.com/SMI/2024/W"...
0x18000efbc  mov     [rbp+3Fh+var_50], rax
0x18000efc0  call    cs:__imp_RtlInitUnicodeString
0x18000efc6  xor     edi, edi
0x18000efc8  cmp     edi, 9
0x18000efcb  jnb     short loc_18000F012
0x18000efcd  mov     rdx, [rbp+rdi*8+3Fh+SourceString]; SourceString
0x18000efd2  lea     rcx, [rbp+3Fh+String2]; DestinationString
0x18000efd6  call    cs:__imp_RtlInitUnicodeString
0x18000efdc  xor     r8d, r8d; CaseInsensitive
0x18000efdf  lea     rdx, [rbp+3Fh+String2]; String2
0x18000efe3  lea     rcx, [rbp+3Fh+DestinationString]; String1
0x18000efe7  call    cs:__imp_RtlCompareUnicodeString
0x18000efed  test    eax, eax
0x18000efef  jz      short loc_18000EFF5
0x18000eff1  inc     edi
0x18000eff3  jmp     short loc_18000EFC8
0x18000eff5  mov     rax, [rbp+3Fh+arg_8]
0x18000eff9  jmp     loc_18000EF05
0x18000effe  mov     ecx, 0C00000EFh
0x18000f003  jmp     loc_18000EF2F
0x18000f008  mov     ebx, 1
0x18000f00d  jmp     loc_18000EF34
0x18000f012  mov     ecx, 0C00000F1h
0x18000f017  jmp     loc_18000EF2F
0x18000f01c  mov     ecx, 0C00000F2h
0x18000f021  jmp     loc_18000EF2F
```
