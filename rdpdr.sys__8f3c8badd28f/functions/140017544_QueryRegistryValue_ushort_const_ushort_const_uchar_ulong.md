# QueryRegistryValue(ushort const *,ushort const *,uchar *,ulong)

- ea: `0x140017544`
- end: `0x1400176b3`
- name: `?QueryRegistryValue@@YAJPEBG0PEAEK@Z`
- size: `367`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001cb3c`
- `0x14002e078`

## callees

- `0x140001e30`
- `0x140003188`
- `0x14000327c`
- `0x140017544`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400175b0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001760c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400175b0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001760c`
- `ntoskrnl!ZwOpenKey` at `0x1400175ef`
- `ntoskrnl!ZwOpenKey` at `0x1400175ef`
- `ntoskrnl!ZwQueryValueKey` at `0x140017639`
- `ntoskrnl!ZwQueryValueKey` at `0x140017639`
- `ntoskrnl!ZwClose` at `0x140017687`
- `ntoskrnl!ZwClose` at `0x140017687`

## string_xrefs

- `0x1400175a5`: `\Registry\Machine\System\CurrentControlSet\Control\Terminal Server\WinStations\RDP-Tcp`

## pseudocode

```c
__int64 __fastcall QueryRegistryValue(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned __int8 *a3)
{
  _DWORD *v5; // rdi
  NTSTATUS v6; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+90h] [rbp+20h] BYREF
  ULONG Length; // [rsp+A8h] [rbp+38h] BYREF

  KeyHandle = 0;
  Length = 28;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  v5 = operator new(0x1Cu, 0x40u);
  if ( v5 )
  {
    RtlInitUnicodeString(
      &DestinationString,
      L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Terminal Server\\WinStations\\RDP-Tcp");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v6 = ZwOpenKey(&KeyHandle, 0x80000000, &ObjectAttributes);
    if ( v6 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, a2);
      v6 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, v5, Length, &Length);
      if ( v6 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            96,
            WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids,
            (unsigned int)v6);
      }
      else
      {
        *(_DWORD *)a3 = v5[3];
      }
      ZwClose(KeyHandle);
    }
  }
  else
  {
    v6 = -1073741801;
  }
  operator delete(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140017544  mov     rax, rsp
0x140017547  mov     [rax+10h], rbx
0x14001754b  mov     [rax+18h], rsi
0x14001754f  mov     [rax+20h], r9d
0x140017553  mov     [rax+8], rcx
0x140017557  push    rbp
0x140017558  push    rdi
0x140017559  push    r14
0x14001755b  mov     rbp, rsp
0x14001755e  sub     rsp, 70h
0x140017562  xorps   xmm0, xmm0
0x140017565  mov     [rbp+KeyHandle], 0
0x14001756d  mov     ecx, 1Ch; unsigned __int64
0x140017572  mov     r14, rdx
0x140017575  mov     rsi, r8
0x140017578  mov     [rbp+arg_18], ecx
0x14001757b  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14001757f  lea     edx, [rcx+24h]; unsigned __int64
0x140017582  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140017586  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14001758a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001758e  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x140017593  mov     rdi, rax
0x140017596  test    rax, rax
0x140017599  jnz     short loc_1400175A5
0x14001759b  mov     ebx, 0C0000017h
0x1400175a0  jmp     loc_140017693
0x1400175a5  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400175ac  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400175b0  call    cs:__imp_RtlInitUnicodeString
0x1400175b7  nop     dword ptr [rax+rax+00h]
0x1400175bc  lea     rax, [rbp+DestinationString]
0x1400175c0  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400175c7  xorps   xmm0, xmm0
0x1400175ca  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400175ce  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400175d2  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400175da  mov     edx, 80000000h; DesiredAccess
0x1400175df  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400175e6  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400175ea  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400175ef  call    cs:__imp_ZwOpenKey
0x1400175f6  nop     dword ptr [rax+rax+00h]
0x1400175fb  mov     ebx, eax
0x1400175fd  test    eax, eax
0x1400175ff  js      loc_140017693
0x140017605  mov     rdx, r14; SourceString
0x140017608  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001760c  call    cs:__imp_RtlInitUnicodeString
0x140017613  nop     dword ptr [rax+rax+00h]
0x140017618  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14001761c  lea     rax, [rbp+arg_18]
0x140017620  mov     [rsp+70h+ResultLength], rax; ResultLength
0x140017625  lea     rdx, [rbp+DestinationString]; ValueName
0x140017629  mov     eax, [rbp+arg_18]
0x14001762c  mov     r9, rdi; KeyValueInformation
0x14001762f  mov     r8d, 2; KeyValueInformationClass
0x140017635  mov     [rsp+70h+Length], eax; Length
0x140017639  call    cs:__imp_ZwQueryValueKey
0x140017640  nop     dword ptr [rax+rax+00h]
0x140017645  mov     ebx, eax
0x140017647  test    eax, eax
0x140017649  js      short loc_140017652
0x14001764b  mov     eax, [rdi+0Ch]
0x14001764e  mov     [rsi], eax
0x140017650  jmp     short loc_140017683
0x140017652  mov     rcx, cs:WPP_GLOBAL_Control
0x140017659  lea     rax, WPP_GLOBAL_Control
0x140017660  cmp     rcx, rax
0x140017663  jz      short loc_140017683
0x140017665  cmp     byte ptr [rcx+29h], 4
0x140017669  jb      short loc_140017683
0x14001766b  mov     rcx, [rcx+18h]
0x14001766f  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x140017676  mov     edx, 60h ; '`'
0x14001767b  mov     r9d, ebx
0x14001767e  call    WPP_SF_d
0x140017683  mov     rcx, [rbp+KeyHandle]; Handle
0x140017687  call    cs:__imp_ZwClose
0x14001768e  nop     dword ptr [rax+rax+00h]
0x140017693  mov     rcx, rdi; void *
0x140017696  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001769b  lea     r11, [rsp+70h+var_s0]
0x1400176a0  mov     eax, ebx
0x1400176a2  mov     rbx, [r11+28h]
0x1400176a6  mov     rsi, [r11+30h]
0x1400176aa  mov     rsp, r11
0x1400176ad  pop     r14
0x1400176af  pop     rdi
0x1400176b0  pop     rbp
0x1400176b1  retn
```
