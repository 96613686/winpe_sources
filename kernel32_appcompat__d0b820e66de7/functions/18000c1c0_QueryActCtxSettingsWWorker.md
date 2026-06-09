# QueryActCtxSettingsWWorker

- ea: `0x18000c1c0`
- end: `0x18000c35f`
- name: `QueryActCtxSettingsWWorker`
- size: `415`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c1c0`
- `0x18000ccf0`

## import_xrefs

- `ntdll!RtlQueryActivationContextApplicationSettings` at `0x18000c23f`
- `ntdll!RtlQueryActivationContextApplicationSettings` at `0x18000c23f`
- `ntdll!RtlCompareUnicodeString` at `0x18000c31a`
- `ntdll!RtlCompareUnicodeString` at `0x18000c31a`
- `ntdll!RtlInitUnicodeString` at `0x18000c2e7`
- `ntdll!RtlInitUnicodeString` at `0x18000c303`
- `ntdll!RtlInitUnicodeString` at `0x18000c2e7`
- `ntdll!RtlInitUnicodeString` at `0x18000c303`

## string_xrefs

- `0x18000c27d`: `http://schemas.microsoft.com/SMI/2005/WindowsSettings`
- `0x18000c2dc`: `http://schemas.microsoft.com/SMI/2024/WindowsSettings`
- `0x18000c2c6`: `http://schemas.microsoft.com/SMI/2019/WindowsSettings`
- `0x18000c29a`: `http://schemas.microsoft.com/SMI/2013/WindowsSettings`
- `0x18000c2d1`: `http://schemas.microsoft.com/SMI/2020/WindowsSettings`
- `0x18000c2a5`: `http://schemas.microsoft.com/SMI/2014/WindowsSettings`
- `0x18000c2b0`: `http://schemas.microsoft.com/SMI/2016/WindowsSettings`
- `0x18000c28f`: `http://schemas.microsoft.com/SMI/2011/WindowsSettings`
- `0x18000c2bb`: `http://schemas.microsoft.com/SMI/2017/WindowsSettings`

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
0x18000c1c0  mov     [rsp-8+arg_8], rdx
0x18000c1c5  push    rbp
0x18000c1c6  push    rbx
0x18000c1c7  push    rsi
0x18000c1c8  push    rdi
0x18000c1c9  push    r12
0x18000c1cb  push    r13
0x18000c1cd  push    r14
0x18000c1cf  push    r15
0x18000c1d1  lea     rbp, [rsp-7]
0x18000c1d6  sub     rsp, 0B8h
0x18000c1dd  mov     rsi, [rbp+3Fh+arg_30]
0x18000c1e1  xor     ebx, ebx
0x18000c1e3  xorps   xmm0, xmm0
0x18000c1e6  xorps   xmm1, xmm1
0x18000c1e9  mov     r13, r9
0x18000c1ec  mov     r12, r8
0x18000c1ef  mov     rax, rdx
0x18000c1f2  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x18000c1f6  movups  xmmword ptr [rbp+3Fh+String2.Length], xmm1
0x18000c1fa  test    rsi, rsi
0x18000c1fd  jz      short loc_18000C202
0x18000c1ff  mov     [rsi], rbx
0x18000c202  test    ecx, ecx
0x18000c204  jnz     loc_18000C337
0x18000c20a  test    r13, r13
0x18000c20d  jz      loc_18000C355
0x18000c213  mov     r15, [rbp+3Fh+arg_28]
0x18000c217  mov     r14, [rbp+3Fh+arg_20]
0x18000c21b  test    r15, r15
0x18000c21e  jnz     short loc_18000C271
0x18000c220  test    r12, r12
0x18000c223  jnz     short loc_18000C27D
0x18000c225  mov     [rsp+0F0h+var_C0], rsi
0x18000c22a  mov     r9, r13
0x18000c22d  mov     [rsp+0F0h+var_C8], r15
0x18000c232  mov     r8, r12
0x18000c235  mov     rdx, rax
0x18000c238  mov     [rsp+0F0h+var_D0], r14
0x18000c23d  xor     ecx, ecx
0x18000c23f  call    cs:__imp_RtlQueryActivationContextApplicationSettings
0x18000c246  nop     dword ptr [rax+rax+00h]
0x18000c24b  test    eax, eax
0x18000c24d  jns     loc_18000C341
0x18000c253  mov     ecx, eax
0x18000c255  call    BaseSetLastNTError
0x18000c25a  mov     eax, ebx
0x18000c25c  add     rsp, 0B8h
0x18000c263  pop     r15
0x18000c265  pop     r14
0x18000c267  pop     r13
0x18000c269  pop     r12
0x18000c26b  pop     rdi
0x18000c26c  pop     rsi
0x18000c26d  pop     rbx
0x18000c26e  pop     rbp
0x18000c26f  retn
0x18000c271  test    r14, r14
0x18000c274  jnz     short loc_18000C220
0x18000c276  mov     ecx, 0C000000Dh
0x18000c27b  jmp     short loc_18000C255
0x18000c27d  lea     rax, aHttpSchemasMic_6; "http://schemas.microsoft.com/SMI/2005/W"...
0x18000c284  mov     rdx, r12; SourceString
0x18000c287  mov     [rbp+3Fh+SourceString], rax
0x18000c28b  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x18000c28f  lea     rax, aHttpSchemasMic_7; "http://schemas.microsoft.com/SMI/2011/W"...
0x18000c296  mov     [rbp+3Fh+var_88], rax
0x18000c29a  lea     rax, aHttpSchemasMic_2; "http://schemas.microsoft.com/SMI/2013/W"...
0x18000c2a1  mov     [rbp+3Fh+var_80], rax
0x18000c2a5  lea     rax, aHttpSchemasMic_5; "http://schemas.microsoft.com/SMI/2014/W"...
0x18000c2ac  mov     [rbp+3Fh+var_78], rax
0x18000c2b0  lea     rax, aHttpSchemasMic_3; "http://schemas.microsoft.com/SMI/2016/W"...
0x18000c2b7  mov     [rbp+3Fh+var_70], rax
0x18000c2bb  lea     rax, aHttpSchemasMic_1; "http://schemas.microsoft.com/SMI/2017/W"...
0x18000c2c2  mov     [rbp+3Fh+var_68], rax
0x18000c2c6  lea     rax, aHttpSchemasMic; "http://schemas.microsoft.com/SMI/2019/W"...
0x18000c2cd  mov     [rbp+3Fh+var_60], rax
0x18000c2d1  lea     rax, aHttpSchemasMic_4; "http://schemas.microsoft.com/SMI/2020/W"...
0x18000c2d8  mov     [rbp+3Fh+var_58], rax
0x18000c2dc  lea     rax, aHttpSchemasMic_0; "http://schemas.microsoft.com/SMI/2024/W"...
0x18000c2e3  mov     [rbp+3Fh+var_50], rax
0x18000c2e7  call    cs:__imp_RtlInitUnicodeString
0x18000c2ee  nop     dword ptr [rax+rax+00h]
0x18000c2f3  xor     edi, edi
0x18000c2f5  cmp     edi, 9
0x18000c2f8  jnb     short loc_18000C34B
0x18000c2fa  mov     rdx, [rbp+rdi*8+3Fh+SourceString]; SourceString
0x18000c2ff  lea     rcx, [rbp+3Fh+String2]; DestinationString
0x18000c303  call    cs:__imp_RtlInitUnicodeString
0x18000c30a  nop     dword ptr [rax+rax+00h]
0x18000c30f  xor     r8d, r8d; CaseInsensitive
0x18000c312  lea     rdx, [rbp+3Fh+String2]; String2
0x18000c316  lea     rcx, [rbp+3Fh+DestinationString]; String1
0x18000c31a  call    cs:__imp_RtlCompareUnicodeString
0x18000c321  nop     dword ptr [rax+rax+00h]
0x18000c326  test    eax, eax
0x18000c328  jz      short loc_18000C32E
0x18000c32a  inc     edi
0x18000c32c  jmp     short loc_18000C2F5
0x18000c32e  mov     rax, [rbp+3Fh+arg_8]
0x18000c332  jmp     loc_18000C225
0x18000c337  mov     ecx, 0C00000EFh
0x18000c33c  jmp     loc_18000C255
0x18000c341  mov     ebx, 1
0x18000c346  jmp     loc_18000C25A
0x18000c34b  mov     ecx, 0C00000F1h
0x18000c350  jmp     loc_18000C255
0x18000c355  mov     ecx, 0C00000F2h
0x18000c35a  jmp     loc_18000C255
```
