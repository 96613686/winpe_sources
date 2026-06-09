# ndisNblTrackerRegisterBlameParameters

- ea: `0x1400a4010`
- end: `0x1400a423c`
- name: `ndisNblTrackerRegisterBlameParameters`
- size: `556`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1400a4244`

## callees

- `0x14001cf60`
- `0x140088a60`
- `0x140091354`
- `0x1400a4010`
- `0x1400eb380`
- `0x1400eb7c0`
- `0x1401411a4`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a420b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a420b`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1400a40e5`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1400a40e5`
- `ntoskrnl!IoQueryFullDriverPath` at `0x1400a4186`
- `ntoskrnl!IoQueryFullDriverPath` at `0x1400a4186`
- `ntoskrnl!RtlInitAnsiString` at `0x1400a411d`
- `ntoskrnl!RtlInitAnsiString` at `0x1400a411d`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1400a4136`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1400a4136`

## pseudocode

```c
void __fastcall ndisNblTrackerRegisterBlameParameters(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  struct _UNICODE_STRING *p_UnicodeString; // rdx
  __int64 v6; // rax
  __int64 v7; // r8
  __int64 v8; // rbx
  NTSTATUS v9; // eax
  int v10; // edx
  int v11; // r9d
  __int64 v12; // rcx
  __int64 v13; // r9
  __int64 v14; // rax
  _BYTE v15[8]; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+38h] [rbp-C8h] BYREF
  struct _STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD SystemInformation[42]; // [rsp+60h] [rbp-A0h] BYREF
  char v19; // [rsp+1B0h] [rbp+B0h] BYREF

  if ( a2[6] )
  {
    p_UnicodeString = (struct _UNICODE_STRING *)a2[6];
LABEL_3:
    LOBYTE(a4) = 1;
    v6 = Rtl::DuplicateUnicodeString(v15, p_UnicodeString, 1802781774, a4);
    wistd::unique_ptr<_UNICODE_STRING,KFreePool<_UNICODE_STRING>>::operator=(a1 + 40, v6);
    wistd::unique_ptr<_UNICODE_STRING,KFreePool<_UNICODE_STRING>>::reset(v15, 0);
    return;
  }
  v7 = a2[4];
  if ( v7 || a2[5] )
  {
    v12 = a2[5];
    UnicodeString = 0;
    if ( !v12 )
      v12 = *(_QWORD *)(v7 + 8);
    v9 = IoQueryFullDriverPath(v12, &UnicodeString);
    if ( v9 < 0 )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return;
      v11 = 15;
      goto LABEL_19;
    }
    LOBYTE(v13) = 1;
    v14 = Rtl::DuplicateUnicodeString(v15, &UnicodeString, 1802781774, v13);
    wistd::unique_ptr<_UNICODE_STRING,KFreePool<_UNICODE_STRING>>::operator=(a1 + 40, v14);
    wistd::unique_ptr<_UNICODE_STRING,KFreePool<_UNICODE_STRING>>::reset(v15, 0);
    RtlFreeUnicodeString(&UnicodeString);
  }
  else
  {
    v8 = a2[3];
    if ( !v8 )
      return;
    *(_QWORD *)&UnicodeString.Length = 0x2000000;
    UnicodeString.Buffer = (wchar_t *)&v19;
    DestinationString = 0;
    memset(&SystemInformation[1], 0, 0x140u);
    SystemInformation[0] = v8;
    v9 = ZwQuerySystemInformation(SystemSingleModuleInformation, SystemInformation, 0x148u, 0);
    if ( v9 < 0 )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return;
      v11 = 16;
      goto LABEL_19;
    }
    RtlInitAnsiString(&DestinationString, (PCSZ)&SystemInformation[7]);
    v9 = RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 0);
    if ( v9 >= 0 )
    {
      p_UnicodeString = &UnicodeString;
      goto LABEL_3;
    }
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v11 = 17;
LABEL_19:
      LOBYTE(v10) = 3;
      WPP_RECORDER_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v10,
        1,
        v11,
        (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
        v9);
    }
  }
}

```

## disassembly

```asm
0x1400a4010  mov     [rsp-8+arg_10], rbx
0x1400a4015  mov     [rsp-8+arg_18], rdi
0x1400a401a  push    rbp
0x1400a401b  lea     rbp, [rsp-2C0h]
0x1400a4023  sub     rsp, 3C0h
0x1400a402a  mov     rax, cs:__security_cookie
0x1400a4031  xor     rax, rsp
0x1400a4034  mov     [rbp+2C0h+var_10], rax
0x1400a403b  mov     rax, [rdx+30h]
0x1400a403f  mov     rdi, rcx
0x1400a4042  test    rax, rax
0x1400a4045  jz      short loc_1400A407A
0x1400a4047  mov     rdx, rax
0x1400a404a  mov     r8d, 6B74444Eh
0x1400a4050  lea     rcx, [rsp+3C0h+var_390]
0x1400a4055  mov     r9b, 1
0x1400a4058  call    ?DuplicateUnicodeString@Rtl@@YA?AV?$unique_ptr@U_UNICODE_STRING@@U?$KFreePool@U_UNICODE_STRING@@@@@wistd@@AEBU_UNICODE_STRING@@K_N@Z; Rtl::DuplicateUnicodeString(_UNICODE_STRING const &,ulong,bool)
0x1400a405d  mov     rdx, rax
0x1400a4060  lea     rcx, [rdi+28h]
0x1400a4064  call    ??4?$unique_ptr@U_UNICODE_STRING@@U?$KFreePool@U_UNICODE_STRING@@@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<_UNICODE_STRING,KFreePool<_UNICODE_STRING>>::operator=(wistd::unique_ptr<_UNICODE_STRING,KFreePool<_UNICODE_STRING>> &&)
0x1400a4069  xor     edx, edx
0x1400a406b  lea     rcx, [rsp+3C0h+var_390]
0x1400a4070  call    ?reset@?$unique_ptr@U_UNICODE_STRING@@U?$KFreePool@U_UNICODE_STRING@@@@@wistd@@QEAAXPEAU_UNICODE_STRING@@@Z; wistd::unique_ptr<_UNICODE_STRING,KFreePool<_UNICODE_STRING>>::reset(_UNICODE_STRING *)
0x1400a4075  jmp     loc_1400A4217
0x1400a407a  mov     r8, [rdx+20h]
0x1400a407e  test    r8, r8
0x1400a4081  jnz     loc_1400A416C
0x1400a4087  cmp     [rdx+28h], r8
0x1400a408b  jnz     loc_1400A416C
0x1400a4091  mov     rbx, [rdx+18h]
0x1400a4095  test    rbx, rbx
0x1400a4098  jz      loc_1400A4217
0x1400a409e  xorps   xmm0, xmm0
0x1400a40a1  mov     qword ptr [rsp+3C0h+UnicodeString.Length], 2000000h
0x1400a40aa  lea     rax, [rbp+2C0h+var_210]
0x1400a40b1  xor     edx, edx; Val
0x1400a40b3  mov     r8d, 140h; Size
0x1400a40b9  mov     [rsp+3C0h+UnicodeString.Buffer], rax
0x1400a40be  lea     rcx, [rsp+3C0h+var_358]; void *
0x1400a40c3  movups  xmmword ptr [rsp+3C0h+DestinationString.Length], xmm0
0x1400a40c8  call    memset
0x1400a40cd  xor     r9d, r9d; ReturnLength
0x1400a40d0  mov     [rsp+3C0h+SystemInformation], rbx
0x1400a40d5  mov     r8d, 148h; SystemInformationLength
0x1400a40db  lea     rdx, [rsp+3C0h+SystemInformation]; SystemInformation
0x1400a40e0  mov     ecx, 0A7h; SystemInformationClass
0x1400a40e5  call    cs:__imp_ZwQuerySystemInformation
0x1400a40ec  nop     dword ptr [rax+rax+00h]
0x1400a40f1  test    eax, eax
0x1400a40f3  jns     short loc_1400A4114
0x1400a40f5  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400a40fc  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400a4103  jz      loc_1400A4217
0x1400a4109  mov     r9d, 10h
0x1400a410f  jmp     loc_1400A41AC
0x1400a4114  lea     rdx, [rbp+2C0h+SourceString]; SourceString
0x1400a4118  lea     rcx, [rsp+3C0h+DestinationString]; DestinationString
0x1400a411d  call    cs:__imp_RtlInitAnsiString
0x1400a4124  nop     dword ptr [rax+rax+00h]
0x1400a4129  xor     r8d, r8d; AllocateDestinationString
0x1400a412c  lea     rdx, [rsp+3C0h+DestinationString]; SourceString
0x1400a4131  lea     rcx, [rsp+3C0h+UnicodeString]; DestinationString
0x1400a4136  call    cs:__imp_RtlAnsiStringToUnicodeString
0x1400a413d  nop     dword ptr [rax+rax+00h]
0x1400a4142  test    eax, eax
0x1400a4144  jns     short loc_1400A4162
0x1400a4146  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400a414d  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400a4154  jz      loc_1400A4217
0x1400a415a  mov     r9d, 11h
0x1400a4160  jmp     short loc_1400A41AC
0x1400a4162  lea     rdx, [rsp+3C0h+UnicodeString]
0x1400a4167  jmp     loc_1400A404A
0x1400a416c  mov     rcx, [rdx+28h]
0x1400a4170  xorps   xmm0, xmm0
0x1400a4173  movups  xmmword ptr [rsp+3C0h+UnicodeString.Length], xmm0
0x1400a4178  test    rcx, rcx
0x1400a417b  jnz     short loc_1400A4181
0x1400a417d  mov     rcx, [r8+8]
0x1400a4181  lea     rdx, [rsp+3C0h+UnicodeString]
0x1400a4186  call    cs:__imp_IoQueryFullDriverPath
0x1400a418d  nop     dword ptr [rax+rax+00h]
0x1400a4192  test    eax, eax
0x1400a4194  jns     short loc_1400A41D6
0x1400a4196  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400a419d  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400a41a4  jz      short loc_1400A4217
0x1400a41a6  mov     r9d, 0Fh; int
0x1400a41ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a41b3  mov     r8d, 1; int
0x1400a41b9  mov     dword ptr [rsp+3C0h+var_398], eax; char
0x1400a41bd  mov     dl, 3; int
0x1400a41bf  lea     rax, WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids
0x1400a41c6  mov     [rsp+3C0h+var_3A0], rax; struct _GUID *
0x1400a41cb  mov     rcx, [rcx+40h]; int
0x1400a41cf  call    WPP_RECORDER_SF_d
0x1400a41d4  jmp     short loc_1400A4217
0x1400a41d6  mov     r9b, 1
0x1400a41d9  lea     rdx, [rsp+3C0h+UnicodeString]
0x1400a41de  mov     r8d, 6B74444Eh
0x1400a41e4  lea     rcx, [rsp+3C0h+var_390]
0x1400a41e9  call    ?DuplicateUnicodeString@Rtl@@YA?AV?$unique_ptr@U_UNICODE_STRING@@U?$KFreePool@U_UNICODE_STRING@@@@@wistd@@AEBU_UNICODE_STRING@@K_N@Z; Rtl::DuplicateUnicodeString(_UNICODE_STRING const &,ulong,bool)
0x1400a41ee  mov     rdx, rax
0x1400a41f1  lea     rcx, [rdi+28h]
0x1400a41f5  call    ??4?$unique_ptr@U_UNICODE_STRING@@U?$KFreePool@U_UNICODE_STRING@@@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<_UNICODE_STRING,KFreePool<_UNICODE_STRING>>::operator=(wistd::unique_ptr<_UNICODE_STRING,KFreePool<_UNICODE_STRING>> &&)
0x1400a41fa  xor     edx, edx
0x1400a41fc  lea     rcx, [rsp+3C0h+var_390]
0x1400a4201  call    ?reset@?$unique_ptr@U_UNICODE_STRING@@U?$KFreePool@U_UNICODE_STRING@@@@@wistd@@QEAAXPEAU_UNICODE_STRING@@@Z; wistd::unique_ptr<_UNICODE_STRING,KFreePool<_UNICODE_STRING>>::reset(_UNICODE_STRING *)
0x1400a4206  lea     rcx, [rsp+3C0h+UnicodeString]; UnicodeString
0x1400a420b  call    cs:__imp_RtlFreeUnicodeString
0x1400a4212  nop     dword ptr [rax+rax+00h]
0x1400a4217  mov     rcx, [rbp+2C0h+var_10]
0x1400a421e  xor     rcx, rsp; StackCookie
0x1400a4221  call    __security_check_cookie
0x1400a4226  lea     r11, [rsp+3C0h+var_s0]
0x1400a422e  mov     rbx, [r11+20h]
0x1400a4232  mov     rdi, [r11+28h]
0x1400a4236  mov     rsp, r11
0x1400a4239  pop     rbp
0x1400a423a  retn
```
