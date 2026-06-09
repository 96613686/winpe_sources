# ClasspIsMediaChangeDisabledForClass

- ea: `0x140055098`
- end: `0x1400553ed`
- name: `ClasspIsMediaChangeDisabledForClass`
- size: `853`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400543e0`

## callees

- `0x14001fbf4`
- `0x1400226bc`
- `0x140022748`
- `0x14003e430`
- `0x14003e470`
- `0x14003e940`
- `0x140055098`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400551a4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140055240`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400552dd`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400551a4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140055240`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400552dd`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140055271`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14005530e`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140055251`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400552ee`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140055251`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400552ee`
- `ntoskrnl!ZwClose` at `0x140055356`
- `ntoskrnl!ZwClose` at `0x140055367`
- `ntoskrnl!ZwClose` at `0x140055356`
- `ntoskrnl!ZwClose` at `0x140055367`
- `ntoskrnl!ZwOpenKey` at `0x14005512d`
- `ntoskrnl!ZwOpenKey` at `0x1400551e0`
- `ntoskrnl!ZwOpenKey` at `0x14005512d`
- `ntoskrnl!ZwOpenKey` at `0x1400551e0`

## string_xrefs

- `0x140055205`: `RtlQueryRegistryValuesEx`
- `0x1400552cc`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
bool __fastcall ClasspIsMediaChangeDisabledForClass(__int64 a1, struct _UNICODE_STRING *a2)
{
  void *v4; // rbx
  PVOID SystemRoutineAddress; // rax
  HANDLE v6; // rsi
  PVOID v7; // rax
  const char *v8; // rax
  unsigned int v10; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-C8h] BYREF
  void *KeyHandle; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING SystemRoutineName; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v16[22]; // [rsp+A0h] [rbp-60h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  KeyHandle = 0;
  Handle = 0;
  memset(v16, 0, 0xA8u);
  ObjectAttributes.ObjectName = a2;
  v10 = 1;
  ObjectAttributes.RootDirectory = 0;
  DestinationString = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"Parameters");
    ObjectAttributes.RootDirectory = KeyHandle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes) < 0 )
      Handle = 0;
    v4 = KeyHandle;
    v16[2] = L"Autorun";
    LODWORD(v16[1]) = 32;
    v16[3] = &v10;
    LODWORD(v16[4]) = 67108868;
    v16[5] = &v10;
    LODWORD(v16[6]) = 4;
    SystemRoutineName = 0;
    RtlInitUnicodeString(&SystemRoutineName, L"RtlQueryRegistryValuesEx");
    SystemRoutineAddress = MmGetSystemRoutineAddress(&SystemRoutineName);
    if ( !SystemRoutineAddress )
      SystemRoutineAddress = RtlQueryRegistryValues;
    ((void (__fastcall *)(__int64, void *, _QWORD *, _QWORD, _QWORD))SystemRoutineAddress)(3221225472LL, v4, v16, 0, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 85, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids, v10);
    }
    v6 = Handle;
    if ( Handle )
    {
      SystemRoutineName = 0;
      RtlInitUnicodeString(&SystemRoutineName, L"RtlQueryRegistryValuesEx");
      v7 = MmGetSystemRoutineAddress(&SystemRoutineName);
      if ( !v7 )
        v7 = RtlQueryRegistryValues;
      ((void (__fastcall *)(__int64, HANDLE, _QWORD *, _QWORD, _QWORD))v7)(3221225472LL, v6, v16, 0, 0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 86, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids, v10);
      }
      ZwClose(Handle);
    }
    ZwClose(KeyHandle);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v8 = "on";
      if ( !v10 )
        v8 = "off";
      WPP_SF_qs(
        WPP_GLOBAL_Control->AttachedDevice,
        87,
        (unsigned int)WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids,
        *(_QWORD *)(a1 + 8),
        (__int64)v8);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu)
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 84, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids, "Enabled");
  }
  return v10 == 0;
}

```

## disassembly

```asm
0x140055098  mov     [rsp-8+arg_10], rbx
0x14005509d  push    rbp
0x14005509e  push    rsi
0x14005509f  push    rdi
0x1400550a0  push    r14
0x1400550a2  push    r15
0x1400550a4  lea     rbp, [rsp-60h]
0x1400550a9  sub     rsp, 160h
0x1400550b0  mov     rax, cs:__security_cookie
0x1400550b7  xor     rax, rsp
0x1400550ba  mov     [rbp+80h+var_30], rax
0x1400550be  mov     rbx, rdx
0x1400550c1  mov     qword ptr [rsp+180h+ObjectAttributes.Length], 30h ; '0'
0x1400550ca  mov     r14, rcx
0x1400550cd  mov     qword ptr [rsp+180h+ObjectAttributes.Attributes], 240h
0x1400550d6  xor     r15d, r15d
0x1400550d9  lea     rcx, [rbp+80h+var_E0]; void *
0x1400550dd  xor     edx, edx; Val
0x1400550df  mov     [rsp+180h+KeyHandle], r15
0x1400550e4  mov     r8d, 0A8h; Size
0x1400550ea  mov     [rsp+180h+Handle], r15
0x1400550ef  call    memset
0x1400550f4  xorps   xmm0, xmm0
0x1400550f7  mov     [rsp+180h+ObjectAttributes.ObjectName], rbx
0x1400550fc  mov     ebx, 20019h
0x140055101  mov     [rsp+180h+var_150], 1
0x140055109  mov     edx, ebx; DesiredAccess
0x14005510b  mov     [rsp+180h+ObjectAttributes.RootDirectory], r15
0x140055110  lea     r8, [rsp+180h+ObjectAttributes]; ObjectAttributes
0x140055115  mov     esi, 240h
0x14005511a  lea     rcx, [rsp+180h+KeyHandle]; KeyHandle
0x14005511f  movups  xmmword ptr [rbp+80h+DestinationString.Length], xmm0
0x140055123  lea     edi, [r15+30h]
0x140055127  movdqu  xmmword ptr [rsp+180h+ObjectAttributes.SecurityDescriptor], xmm0
0x14005512d  call    cs:__imp_ZwOpenKey
0x140055134  nop     dword ptr [rax+rax+00h]
0x140055139  test    eax, eax
0x14005513b  jns     short loc_140055199
0x14005513d  mov     rcx, cs:WPP_GLOBAL_Control
0x140055144  lea     rdi, WPP_GLOBAL_Control
0x14005514b  cmp     rcx, rdi
0x14005514e  jz      loc_1400553C1
0x140055154  bt      dword ptr [rcx+2Ch], 0Ch
0x140055159  jnb     loc_1400553C1
0x14005515f  cmp     byte ptr [rcx+29h], 4
0x140055163  jb      loc_1400553C1
0x140055169  cmp     [rsp+180h+var_150], r15d
0x14005516e  lea     rax, aDisabled; "Disabled"
0x140055175  mov     rcx, [rcx+18h]
0x140055179  lea     r9, aEnabled_0; "Enabled"
0x140055180  cmovz   r9, rax
0x140055184  lea     edx, [r15+54h]
0x140055188  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x14005518f  call    WPP_SF_s
0x140055194  jmp     loc_1400553C1
0x140055199  lea     rdx, aParameters; "Parameters"
0x1400551a0  lea     rcx, [rbp+80h+DestinationString]; DestinationString
0x1400551a4  call    cs:__imp_RtlInitUnicodeString
0x1400551ab  nop     dword ptr [rax+rax+00h]
0x1400551b0  mov     rax, [rsp+180h+KeyHandle]
0x1400551b5  lea     r8, [rsp+180h+ObjectAttributes]; ObjectAttributes
0x1400551ba  mov     [rsp+180h+ObjectAttributes.RootDirectory], rax
0x1400551bf  lea     rcx, [rsp+180h+Handle]; KeyHandle
0x1400551c4  lea     rax, [rbp+80h+DestinationString]
0x1400551c8  mov     [rsp+180h+ObjectAttributes.Length], edi
0x1400551cc  xorps   xmm0, xmm0
0x1400551cf  mov     [rsp+180h+ObjectAttributes.ObjectName], rax
0x1400551d4  mov     edx, ebx; DesiredAccess
0x1400551d6  mov     [rsp+180h+ObjectAttributes.Attributes], esi
0x1400551da  movdqu  xmmword ptr [rsp+180h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400551e0  call    cs:__imp_ZwOpenKey
0x1400551e7  nop     dword ptr [rax+rax+00h]
0x1400551ec  test    eax, eax
0x1400551ee  jns     short loc_1400551F5
0x1400551f0  mov     [rsp+180h+Handle], r15
0x1400551f5  mov     rbx, [rsp+180h+KeyHandle]
0x1400551fa  lea     rax, aAutorun; "Autorun"
0x140055201  mov     [rbp+80h+var_D0], rax
0x140055205  lea     rdx, SourceString; "RtlQueryRegistryValuesEx"
0x14005520c  lea     rax, [rsp+180h+var_150]
0x140055211  mov     [rbp+80h+var_D8], 20h ; ' '
0x140055218  mov     [rbp+80h+var_C8], rax
0x14005521c  lea     rcx, [rsp+180h+SystemRoutineName]; DestinationString
0x140055221  lea     rax, [rsp+180h+var_150]
0x140055226  mov     [rbp+80h+var_C0], 4000004h
0x14005522d  xorps   xmm0, xmm0
0x140055230  mov     [rbp+80h+var_B8], rax
0x140055234  mov     [rbp+80h+var_B0], 4
0x14005523b  movups  xmmword ptr [rsp+180h+SystemRoutineName.Length], xmm0
0x140055240  call    cs:__imp_RtlInitUnicodeString
0x140055247  nop     dword ptr [rax+rax+00h]
0x14005524c  lea     rcx, [rsp+180h+SystemRoutineName]; SystemRoutineName
0x140055251  call    cs:__imp_MmGetSystemRoutineAddress
0x140055258  nop     dword ptr [rax+rax+00h]
0x14005525d  lea     r8, [rbp+80h+var_E0]
0x140055261  mov     [rsp+180h+var_160], r15
0x140055266  test    rax, rax
0x140055269  mov     rdx, rbx
0x14005526c  mov     ecx, 0C0000000h
0x140055271  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140055279  xor     r9d, r9d
0x14005527c  call    _guard_dispatch_icall
0x140055281  mov     rcx, cs:WPP_GLOBAL_Control
0x140055288  lea     rdi, WPP_GLOBAL_Control
0x14005528f  cmp     rcx, rdi
0x140055292  jz      short loc_1400552BB
0x140055294  bt      dword ptr [rcx+2Ch], 0Ch
0x140055299  jnb     short loc_1400552BB
0x14005529b  cmp     byte ptr [rcx+29h], 4
0x14005529f  jb      short loc_1400552BB
0x1400552a1  mov     r9d, [rsp+180h+var_150]
0x1400552a6  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x1400552ad  mov     rcx, [rcx+18h]
0x1400552b1  mov     edx, 55h ; 'U'
0x1400552b6  call    WPP_SF_d
0x1400552bb  mov     rsi, [rsp+180h+Handle]
0x1400552c0  test    rsi, rsi
0x1400552c3  jz      loc_140055362
0x1400552c9  xorps   xmm0, xmm0
0x1400552cc  lea     rdx, SourceString; "RtlQueryRegistryValuesEx"
0x1400552d3  lea     rcx, [rsp+180h+SystemRoutineName]; DestinationString
0x1400552d8  movups  xmmword ptr [rsp+180h+SystemRoutineName.Length], xmm0
0x1400552dd  call    cs:__imp_RtlInitUnicodeString
0x1400552e4  nop     dword ptr [rax+rax+00h]
0x1400552e9  lea     rcx, [rsp+180h+SystemRoutineName]; SystemRoutineName
0x1400552ee  call    cs:__imp_MmGetSystemRoutineAddress
0x1400552f5  nop     dword ptr [rax+rax+00h]
0x1400552fa  lea     r8, [rbp+80h+var_E0]
0x1400552fe  mov     [rsp+180h+var_160], r15
0x140055303  test    rax, rax
0x140055306  mov     rdx, rsi
0x140055309  mov     ecx, 0C0000000h
0x14005530e  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140055316  xor     r9d, r9d
0x140055319  call    _guard_dispatch_icall
0x14005531e  mov     rcx, cs:WPP_GLOBAL_Control
0x140055325  cmp     rcx, rdi
0x140055328  jz      short loc_140055351
0x14005532a  bt      dword ptr [rcx+2Ch], 0Ch
0x14005532f  jnb     short loc_140055351
0x140055331  cmp     byte ptr [rcx+29h], 4
0x140055335  jb      short loc_140055351
0x140055337  mov     r9d, [rsp+180h+var_150]
0x14005533c  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140055343  mov     rcx, [rcx+18h]
0x140055347  mov     edx, 56h ; 'V'
0x14005534c  call    WPP_SF_d
0x140055351  mov     rcx, [rsp+180h+Handle]; Handle
0x140055356  call    cs:__imp_ZwClose
0x14005535d  nop     dword ptr [rax+rax+00h]
0x140055362  mov     rcx, [rsp+180h+KeyHandle]; Handle
0x140055367  call    cs:__imp_ZwClose
0x14005536e  nop     dword ptr [rax+rax+00h]
0x140055373  mov     rcx, cs:WPP_GLOBAL_Control
0x14005537a  cmp     rcx, rdi
0x14005537d  jz      short loc_1400553C1
0x14005537f  bt      dword ptr [rcx+2Ch], 0Ch
0x140055384  jnb     short loc_1400553C1
0x140055386  cmp     byte ptr [rcx+29h], 4
0x14005538a  jb      short loc_1400553C1
0x14005538c  cmp     [rsp+180h+var_150], r15d
0x140055391  lea     rdx, aOff; "off"
0x140055398  mov     r9, [r14+8]
0x14005539c  lea     rax, aOn; "on"
0x1400553a3  mov     rcx, [rcx+18h]
0x1400553a7  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x1400553ae  cmovz   rax, rdx
0x1400553b2  mov     edx, 57h ; 'W'
0x1400553b7  mov     [rsp+180h+var_160], rax
0x1400553bc  call    WPP_SF_qs
0x1400553c1  cmp     [rsp+180h+var_150], r15d
0x1400553c6  setz    al
0x1400553c9  mov     rcx, [rbp+80h+var_30]
0x1400553cd  xor     rcx, rsp; StackCookie
0x1400553d0  call    __security_check_cookie
0x1400553d5  mov     rbx, [rsp+180h+arg_10]
0x1400553dd  add     rsp, 160h
0x1400553e4  pop     r15
0x1400553e6  pop     r14
0x1400553e8  pop     rdi
0x1400553e9  pop     rsi
0x1400553ea  pop     rbp
0x1400553eb  retn
```
