# RtlpGetUserOrMachineUILanguage4NLS

- ea: `0x18010fd00`
- end: `0x18010feef`
- name: `RtlpGetUserOrMachineUILanguage4NLS`
- size: `495`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180009d60`
- `0x18000a070`
- `0x18010fc0c`

## callees

- `0x180011c70`
- `0x1800c4700`
- `0x1800d7b80`
- `0x1800da250`
- `0x18010fd00`
- `0x18015ecc0`

## string_xrefs

- `0x18010fd78`: `Control Panel\Desktop\MuiCached`
- `0x18010fde5`: `\Registry\Machine\System\CurrentControlSet\Control\MUI\Settings`

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
0x18010fd00  mov     [rsp-18h+arg_0], rbx
0x18010fd05  mov     [rsp-18h+arg_8], rsi
0x18010fd0a  push    rbp
0x18010fd0b  push    rdi
0x18010fd0c  push    r14
0x18010fd0e  mov     rbp, rsp
0x18010fd11  sub     rsp, 60h
0x18010fd15  mov     rsi, r8
0x18010fd18  mov     [rbp+var_20], 0
0x18010fd20  mov     edi, ecx
0x18010fd22  mov     [rbp+Handle], 0
0x18010fd2a  xorps   xmm0, xmm0
0x18010fd2d  mov     [rbp+var_30], 7
0x18010fd34  lea     r8, [rbp+var_20]
0x18010fd38  mov     [rbp+arg_18], 0
0x18010fd3f  mov     ecx, 2000000h
0x18010fd44  mov     r14, rdx
0x18010fd47  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18010fd4b  call    OpenGlobalizationUserSettingsKey
0x18010fd50  mov     ebx, eax
0x18010fd52  test    eax, eax
0x18010fd54  js      loc_18010FEB3
0x18010fd5a  lea     rcx, [rbp+DestinationString]; DestinationString
0x18010fd5e  cmp     edi, 1
0x18010fd61  jnz     short loc_18010FD78
0x18010fd63  lea     rdx, aControlPanelDe_2; "Control Panel\\Desktop"
0x18010fd6a  call    RtlInitUnicodeString
0x18010fd6f  mov     rdx, [rbp+var_20]
0x18010fd73  jmp     loc_18010FDFF
0x18010fd78  lea     rdx, aControlPanelDe; "Control Panel\\Desktop\\MuiCached"
0x18010fd7f  call    RtlInitUnicodeString
0x18010fd84  mov     rdx, [rbp+var_20]
0x18010fd88  lea     r9, [rbp+Handle]
0x18010fd8c  mov     r8d, 20019h
0x18010fd92  lea     rcx, [rbp+DestinationString]
0x18010fd96  call    LdrpOpenKey
0x18010fd9b  mov     ebx, eax
0x18010fd9d  test    eax, eax
0x18010fd9f  js      short loc_18010FDD4
0x18010fda1  lea     rdx, aMachinepreferr; "MachinePreferredUILanguages"
0x18010fda8  lea     rcx, [rbp+DestinationString]; DestinationString
0x18010fdac  call    RtlInitUnicodeString
0x18010fdb1  mov     rcx, [rbp+Handle]
0x18010fdb5  lea     rax, [rbp+arg_18]
0x18010fdb9  xor     r9d, r9d
0x18010fdbc  mov     [rsp+60h+var_40], rax
0x18010fdc1  lea     r8, [rbp+var_30]
0x18010fdc5  lea     rdx, [rbp+DestinationString]
0x18010fdc9  call    LdrpQueryValueKey
0x18010fdce  mov     ebx, eax
0x18010fdd0  test    eax, eax
0x18010fdd2  jns     short loc_18010FE4B
0x18010fdd4  cmp     ebx, 80000005h
0x18010fdda  jz      short loc_18010FE4B
0x18010fddc  mov     rcx, [rbp+Handle]; Handle
0x18010fde0  call    NtClose
0x18010fde5  lea     rdx, aRegistryMachin_8; "\\Registry\\Machine\\System\\CurrentCon"...
0x18010fdec  mov     [rbp+Handle], 0
0x18010fdf4  lea     rcx, [rbp+DestinationString]; DestinationString
0x18010fdf8  call    RtlInitUnicodeString
0x18010fdfd  xor     edx, edx
0x18010fdff  lea     r9, [rbp+Handle]
0x18010fe03  mov     r8d, 20019h
0x18010fe09  lea     rcx, [rbp+DestinationString]
0x18010fe0d  call    LdrpOpenKey
0x18010fe12  mov     ebx, eax
0x18010fe14  test    eax, eax
0x18010fe16  js      loc_18010FEB3
0x18010fe1c  lea     rdx, aPreferreduilan; "PreferredUILanguages"
0x18010fe23  lea     rcx, [rbp+DestinationString]; DestinationString
0x18010fe27  call    RtlInitUnicodeString
0x18010fe2c  mov     rcx, [rbp+Handle]
0x18010fe30  lea     rax, [rbp+arg_18]
0x18010fe34  xor     r9d, r9d
0x18010fe37  mov     [rsp+60h+var_40], rax
0x18010fe3c  lea     r8, [rbp+var_30]
0x18010fe40  lea     rdx, [rbp+DestinationString]
0x18010fe44  call    LdrpQueryValueKey
0x18010fe49  mov     ebx, eax
0x18010fe4b  cmp     ebx, 0C0000034h
0x18010fe51  jz      short loc_18010FEB3
0x18010fe53  mov     eax, [rbp+arg_18]
0x18010fe56  test    eax, eax
0x18010fe58  jz      short loc_18010FEB3
0x18010fe5a  cmp     ebx, 80000005h
0x18010fe60  jnz     short loc_18010FEAE
0x18010fe62  inc     eax
0x18010fe64  mov     edi, eax
0x18010fe66  shr     edi, 1
0x18010fe68  test    r14, r14
0x18010fe6b  jnz     short loc_18010FE76
0x18010fe6d  xor     ebx, ebx
0x18010fe6f  mov     eax, edi
0x18010fe71  mov     [rsi], rax
0x18010fe74  jmp     short loc_18010FEB3
0x18010fe76  shr     rax, 1
0x18010fe79  cmp     [rsi], rax
0x18010fe7c  jnb     short loc_18010FE85
0x18010fe7e  mov     ebx, 0C0000023h
0x18010fe83  jmp     short loc_18010FE6F
0x18010fe85  mov     rcx, [rbp+Handle]
0x18010fe89  lea     rax, [rbp+arg_18]
0x18010fe8d  mov     r9, r14
0x18010fe90  mov     [rsp+60h+var_40], rax
0x18010fe95  lea     r8, [rbp+var_30]
0x18010fe99  lea     rdx, [rbp+DestinationString]
0x18010fe9d  call    LdrpQueryValueKey
0x18010fea2  mov     ebx, eax
0x18010fea4  test    eax, eax
0x18010fea6  js      short loc_18010FEB3
0x18010fea8  cmp     [rbp+var_30], 7
0x18010feac  jz      short loc_18010FE6F
0x18010feae  mov     ebx, 0C0000034h
0x18010feb3  mov     rcx, [rbp+var_20]; Handle
0x18010feb7  test    rcx, rcx
0x18010feba  jz      short loc_18010FEC9
0x18010febc  call    NtClose
0x18010fec1  mov     [rbp+var_20], 0
0x18010fec9  mov     rcx, [rbp+Handle]; Handle
0x18010fecd  test    rcx, rcx
0x18010fed0  jz      short loc_18010FED7
0x18010fed2  call    NtClose
0x18010fed7  lea     r11, [rsp+60h+var_s0]
0x18010fedc  mov     eax, ebx
0x18010fede  mov     rbx, [r11+20h]
0x18010fee2  mov     rsi, [r11+28h]
0x18010fee6  mov     rsp, r11
0x18010fee9  pop     r14
0x18010feeb  pop     rdi
0x18010feec  pop     rbp
0x18010feed  retn
```
