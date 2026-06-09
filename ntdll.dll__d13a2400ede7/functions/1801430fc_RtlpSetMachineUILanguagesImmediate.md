# RtlpSetMachineUILanguagesImmediate

- ea: `0x1801430fc`
- end: `0x180143269`
- name: `RtlpSetMachineUILanguagesImmediate`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180143270`

## callees

- `0x180011c70`
- `0x1800c4700`
- `0x1801422f0`
- `0x1801430fc`
- `0x18015ecc0`
- `0x18015f6d0`

## string_xrefs

- `0x1801431b3`: `Control Panel\Desktop\MuiCached`
- `0x180143129`: `\Registry\Machine\System\CurrentControlSet\Control\MUI\Settings`

## pseudocode

```c
__int64 __fastcall RtlpSetMachineUILanguagesImmediate(__int64 a1)
{
  int Key; // ebx
  __int64 v3; // rdx
  UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp+28h] BYREF
  HANDLE v7; // [rsp+70h] [rbp+30h] BYREF
  HANDLE v8; // [rsp+78h] [rbp+38h] BYREF

  Handle = 0;
  v7 = 0;
  v8 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MUI\\Settings");
  Key = LdrpCreateKey((unsigned int)&DestinationString, 0, 0, 983103, (__int64)&Handle);
  if ( Key >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"PreferredUILanguages");
    Key = ZwSetValueKey(Handle, &DestinationString, 0, 7, *(_QWORD *)(a1 + 8), *(unsigned __int16 *)(a1 + 2));
    if ( Key >= 0 && (int)OpenGlobalizationUserSettingsKey(0x2000000, v3, &v8) >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"Control Panel\\Desktop\\MuiCached");
      Key = LdrpCreateKey((unsigned int)&DestinationString, (_DWORD)v8, 1, 983103, (__int64)&v7);
      if ( Key >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, L"MachinePreferredUILanguages");
        Key = ZwSetValueKey(v7, &DestinationString, 0, 7, *(_QWORD *)(a1 + 8), *(unsigned __int16 *)(a1 + 2));
      }
    }
  }
  if ( Handle )
  {
    NtClose(Handle);
    Handle = 0;
  }
  if ( v7 )
  {
    NtClose(v7);
    v7 = 0;
  }
  if ( v8 )
    NtClose(v8);
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x1801430fc  push    rbp
0x1801430fe  push    rbx
0x1801430ff  push    rdi
0x180143100  mov     rbp, rsp
0x180143103  sub     rsp, 40h
0x180143107  mov     rdi, rcx
0x18014310a  mov     [rbp+Handle], 0
0x180143112  xorps   xmm0, xmm0
0x180143115  mov     [rbp+arg_10], 0
0x18014311d  lea     rcx, [rbp+DestinationString]; DestinationString
0x180143121  mov     [rbp+arg_18], 0
0x180143129  lea     rdx, aRegistryMachin_8; "\\Registry\\Machine\\System\\CurrentCon"...
0x180143130  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180143134  call    RtlInitUnicodeString
0x180143139  lea     rax, [rbp+Handle]
0x18014313d  mov     r9d, 0F003Fh
0x180143143  xor     r8d, r8d
0x180143146  mov     [rsp+40h+var_20], rax
0x18014314b  xor     edx, edx
0x18014314d  lea     rcx, [rbp+DestinationString]
0x180143151  call    LdrpCreateKey
0x180143156  mov     ebx, eax
0x180143158  test    eax, eax
0x18014315a  js      loc_180143224
0x180143160  lea     rdx, aPreferreduilan; "PreferredUILanguages"
0x180143167  lea     rcx, [rbp+DestinationString]; DestinationString
0x18014316b  call    RtlInitUnicodeString
0x180143170  movzx   eax, word ptr [rdi+2]
0x180143174  lea     rdx, [rbp+DestinationString]
0x180143178  mov     rcx, [rbp+Handle]
0x18014317c  mov     r9d, 7
0x180143182  mov     [rsp+40h+var_18], eax
0x180143186  xor     r8d, r8d
0x180143189  mov     rax, [rdi+8]
0x18014318d  mov     [rsp+40h+var_20], rax
0x180143192  call    ZwSetValueKey
0x180143197  mov     ebx, eax
0x180143199  test    eax, eax
0x18014319b  js      loc_180143224
0x1801431a1  lea     r8, [rbp+arg_18]
0x1801431a5  mov     ecx, 2000000h
0x1801431aa  call    OpenGlobalizationUserSettingsKey
0x1801431af  test    eax, eax
0x1801431b1  js      short loc_180143224
0x1801431b3  lea     rdx, aControlPanelDe; "Control Panel\\Desktop\\MuiCached"
0x1801431ba  lea     rcx, [rbp+DestinationString]; DestinationString
0x1801431be  call    RtlInitUnicodeString
0x1801431c3  mov     rdx, [rbp+arg_18]
0x1801431c7  lea     rax, [rbp+arg_10]
0x1801431cb  mov     r9d, 0F003Fh
0x1801431d1  mov     [rsp+40h+var_20], rax
0x1801431d6  mov     r8d, 1
0x1801431dc  lea     rcx, [rbp+DestinationString]
0x1801431e0  call    LdrpCreateKey
0x1801431e5  mov     ebx, eax
0x1801431e7  test    eax, eax
0x1801431e9  js      short loc_180143224
0x1801431eb  lea     rdx, aMachinepreferr; "MachinePreferredUILanguages"
0x1801431f2  lea     rcx, [rbp+DestinationString]; DestinationString
0x1801431f6  call    RtlInitUnicodeString
0x1801431fb  movzx   eax, word ptr [rdi+2]
0x1801431ff  lea     rdx, [rbp+DestinationString]
0x180143203  mov     rcx, [rbp+arg_10]
0x180143207  mov     r9d, 7
0x18014320d  mov     [rsp+40h+var_18], eax
0x180143211  xor     r8d, r8d
0x180143214  mov     rax, [rdi+8]
0x180143218  mov     [rsp+40h+var_20], rax
0x18014321d  call    ZwSetValueKey
0x180143222  mov     ebx, eax
0x180143224  mov     rcx, [rbp+Handle]; Handle
0x180143228  test    rcx, rcx
0x18014322b  jz      short loc_18014323A
0x18014322d  call    NtClose
0x180143232  mov     [rbp+Handle], 0
0x18014323a  mov     rcx, [rbp+arg_10]; Handle
0x18014323e  test    rcx, rcx
0x180143241  jz      short loc_180143250
0x180143243  call    NtClose
0x180143248  mov     [rbp+arg_10], 0
0x180143250  mov     rcx, [rbp+arg_18]; Handle
0x180143254  test    rcx, rcx
0x180143257  jz      short loc_18014325E
0x180143259  call    NtClose
0x18014325e  mov     eax, ebx
0x180143260  add     rsp, 40h
0x180143264  pop     rdi
0x180143265  pop     rbx
0x180143266  pop     rbp
0x180143267  retn
```
