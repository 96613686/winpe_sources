# RtlpGetUserOrMachineUILanguage4NLS

- ea: `0x18010e9a0`
- end: `0x18010eb8f`
- name: `RtlpGetUserOrMachineUILanguage4NLS`
- size: `495`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180009d60`
- `0x18000a070`
- `0x18010e8ac`

## callees

- `0x180011c70`
- `0x1800c0420`
- `0x1800d38d0`
- `0x1800d97d0`
- `0x18010e9a0`
- `0x18015e4b0`

## string_xrefs

- `0x18010ea18`: `Control Panel\Desktop\MuiCached`
- `0x18010ea85`: `\Registry\Machine\System\CurrentControlSet\Control\MUI\Settings`

## pseudocode

```c
__int64 __fastcall RtlpGetUserOrMachineUILanguage4NLS(int a1, __int64 a2, unsigned __int64 *a3)
{
  int v6; // ebx
  HANDLE v7; // rdx
  unsigned __int64 v8; // rax
  unsigned int v9; // edi
  int v11; // [rsp+30h] [rbp-30h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-28h] BYREF
  HANDLE v13; // [rsp+40h] [rbp-20h] BYREF
  UNICODE_STRING DestinationString; // [rsp+48h] [rbp-18h] BYREF
  int v15; // [rsp+98h] [rbp+38h] BYREF

  v13 = 0;
  Handle = 0;
  v11 = 7;
  v15 = 0;
  DestinationString = 0;
  v6 = OpenGlobalizationUserSettingsKey(0x2000000, a2, &v13);
  if ( v6 < 0 )
    goto LABEL_21;
  if ( a1 == 1 )
  {
    RtlInitUnicodeString(&DestinationString, L"Control Panel\\Desktop");
    v7 = v13;
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, L"Control Panel\\Desktop\\MuiCached");
    v6 = LdrpOpenKey(&DestinationString, v13, 131097, &Handle);
    if ( v6 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"MachinePreferredUILanguages");
      v6 = LdrpQueryValueKey(Handle, &DestinationString, &v11, 0, &v15);
      if ( v6 >= 0 )
        goto LABEL_10;
    }
    if ( v6 == -2147483643 )
      goto LABEL_10;
    NtClose(Handle);
    Handle = 0;
    RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MUI\\Settings");
    v7 = 0;
  }
  v6 = LdrpOpenKey(&DestinationString, v7, 131097, &Handle);
  if ( v6 < 0 )
    goto LABEL_21;
  RtlInitUnicodeString(&DestinationString, L"PreferredUILanguages");
  v6 = LdrpQueryValueKey(Handle, &DestinationString, &v11, 0, &v15);
LABEL_10:
  if ( v6 != -1073741772 && v15 )
  {
    if ( v6 != -2147483643 )
    {
LABEL_20:
      v6 = -1073741772;
      goto LABEL_21;
    }
    v8 = (unsigned int)(v15 + 1);
    v9 = (unsigned int)v8 >> 1;
    if ( !a2 )
    {
      v6 = 0;
LABEL_15:
      *a3 = v9;
      goto LABEL_21;
    }
    if ( *a3 < v8 >> 1 )
    {
      v6 = -1073741789;
      goto LABEL_15;
    }
    v6 = LdrpQueryValueKey(Handle, &DestinationString, &v11, a2, &v15);
    if ( v6 >= 0 )
    {
      if ( v11 == 7 )
        goto LABEL_15;
      goto LABEL_20;
    }
  }
LABEL_21:
  if ( v13 )
  {
    NtClose(v13);
    v13 = 0;
  }
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18010e9a0  mov     [rsp-18h+arg_0], rbx
0x18010e9a5  mov     [rsp-18h+arg_8], rsi
0x18010e9aa  push    rbp
0x18010e9ab  push    rdi
0x18010e9ac  push    r14
0x18010e9ae  mov     rbp, rsp
0x18010e9b1  sub     rsp, 60h
0x18010e9b5  mov     rsi, r8
0x18010e9b8  mov     [rbp+var_20], 0
0x18010e9c0  mov     edi, ecx
0x18010e9c2  mov     [rbp+Handle], 0
0x18010e9ca  xorps   xmm0, xmm0
0x18010e9cd  mov     [rbp+var_30], 7
0x18010e9d4  lea     r8, [rbp+var_20]
0x18010e9d8  mov     [rbp+arg_18], 0
0x18010e9df  mov     ecx, 2000000h
0x18010e9e4  mov     r14, rdx
0x18010e9e7  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18010e9eb  call    OpenGlobalizationUserSettingsKey
0x18010e9f0  mov     ebx, eax
0x18010e9f2  test    eax, eax
0x18010e9f4  js      loc_18010EB53
0x18010e9fa  lea     rcx, [rbp+DestinationString]; DestinationString
0x18010e9fe  cmp     edi, 1
0x18010ea01  jnz     short loc_18010EA18
0x18010ea03  lea     rdx, aControlPanelDe_2; "Control Panel\\Desktop"
0x18010ea0a  call    RtlInitUnicodeString
0x18010ea0f  mov     rdx, [rbp+var_20]
0x18010ea13  jmp     loc_18010EA9F
0x18010ea18  lea     rdx, aControlPanelDe; "Control Panel\\Desktop\\MuiCached"
0x18010ea1f  call    RtlInitUnicodeString
0x18010ea24  mov     rdx, [rbp+var_20]
0x18010ea28  lea     r9, [rbp+Handle]
0x18010ea2c  mov     r8d, 20019h
0x18010ea32  lea     rcx, [rbp+DestinationString]
0x18010ea36  call    LdrpOpenKey
0x18010ea3b  mov     ebx, eax
0x18010ea3d  test    eax, eax
0x18010ea3f  js      short loc_18010EA74
0x18010ea41  lea     rdx, aMachinepreferr; "MachinePreferredUILanguages"
0x18010ea48  lea     rcx, [rbp+DestinationString]; DestinationString
0x18010ea4c  call    RtlInitUnicodeString
0x18010ea51  mov     rcx, [rbp+Handle]
0x18010ea55  lea     rax, [rbp+arg_18]
0x18010ea59  xor     r9d, r9d
0x18010ea5c  mov     [rsp+60h+var_40], rax
0x18010ea61  lea     r8, [rbp+var_30]
0x18010ea65  lea     rdx, [rbp+DestinationString]
0x18010ea69  call    LdrpQueryValueKey
0x18010ea6e  mov     ebx, eax
0x18010ea70  test    eax, eax
0x18010ea72  jns     short loc_18010EAEB
0x18010ea74  cmp     ebx, 80000005h
0x18010ea7a  jz      short loc_18010EAEB
0x18010ea7c  mov     rcx, [rbp+Handle]; Handle
0x18010ea80  call    NtClose
0x18010ea85  lea     rdx, aRegistryMachin_8; "\\Registry\\Machine\\System\\CurrentCon"...
0x18010ea8c  mov     [rbp+Handle], 0
0x18010ea94  lea     rcx, [rbp+DestinationString]; DestinationString
0x18010ea98  call    RtlInitUnicodeString
0x18010ea9d  xor     edx, edx
0x18010ea9f  lea     r9, [rbp+Handle]
0x18010eaa3  mov     r8d, 20019h
0x18010eaa9  lea     rcx, [rbp+DestinationString]
0x18010eaad  call    LdrpOpenKey
0x18010eab2  mov     ebx, eax
0x18010eab4  test    eax, eax
0x18010eab6  js      loc_18010EB53
0x18010eabc  lea     rdx, aPreferreduilan; "PreferredUILanguages"
0x18010eac3  lea     rcx, [rbp+DestinationString]; DestinationString
0x18010eac7  call    RtlInitUnicodeString
0x18010eacc  mov     rcx, [rbp+Handle]
0x18010ead0  lea     rax, [rbp+arg_18]
0x18010ead4  xor     r9d, r9d
0x18010ead7  mov     [rsp+60h+var_40], rax
0x18010eadc  lea     r8, [rbp+var_30]
0x18010eae0  lea     rdx, [rbp+DestinationString]
0x18010eae4  call    LdrpQueryValueKey
0x18010eae9  mov     ebx, eax
0x18010eaeb  cmp     ebx, 0C0000034h
0x18010eaf1  jz      short loc_18010EB53
0x18010eaf3  mov     eax, [rbp+arg_18]
0x18010eaf6  test    eax, eax
0x18010eaf8  jz      short loc_18010EB53
0x18010eafa  cmp     ebx, 80000005h
0x18010eb00  jnz     short loc_18010EB4E
0x18010eb02  inc     eax
0x18010eb04  mov     edi, eax
0x18010eb06  shr     edi, 1
0x18010eb08  test    r14, r14
0x18010eb0b  jnz     short loc_18010EB16
0x18010eb0d  xor     ebx, ebx
0x18010eb0f  mov     eax, edi
0x18010eb11  mov     [rsi], rax
0x18010eb14  jmp     short loc_18010EB53
0x18010eb16  shr     rax, 1
0x18010eb19  cmp     [rsi], rax
0x18010eb1c  jnb     short loc_18010EB25
0x18010eb1e  mov     ebx, 0C0000023h
0x18010eb23  jmp     short loc_18010EB0F
0x18010eb25  mov     rcx, [rbp+Handle]
0x18010eb29  lea     rax, [rbp+arg_18]
0x18010eb2d  mov     r9, r14
0x18010eb30  mov     [rsp+60h+var_40], rax
0x18010eb35  lea     r8, [rbp+var_30]
0x18010eb39  lea     rdx, [rbp+DestinationString]
0x18010eb3d  call    LdrpQueryValueKey
0x18010eb42  mov     ebx, eax
0x18010eb44  test    eax, eax
0x18010eb46  js      short loc_18010EB53
0x18010eb48  cmp     [rbp+var_30], 7
0x18010eb4c  jz      short loc_18010EB0F
0x18010eb4e  mov     ebx, 0C0000034h
0x18010eb53  mov     rcx, [rbp+var_20]; Handle
0x18010eb57  test    rcx, rcx
0x18010eb5a  jz      short loc_18010EB69
0x18010eb5c  call    NtClose
0x18010eb61  mov     [rbp+var_20], 0
0x18010eb69  mov     rcx, [rbp+Handle]; Handle
0x18010eb6d  test    rcx, rcx
0x18010eb70  jz      short loc_18010EB77
0x18010eb72  call    NtClose
0x18010eb77  lea     r11, [rsp+60h+var_s0]
0x18010eb7c  mov     eax, ebx
0x18010eb7e  mov     rbx, [r11+20h]
0x18010eb82  mov     rsi, [r11+28h]
0x18010eb86  mov     rsp, r11
0x18010eb89  pop     r14
0x18010eb8b  pop     rdi
0x18010eb8c  pop     rbp
0x18010eb8d  retn
```
