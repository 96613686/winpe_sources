# RtlpSetMachineUILanguagesImmediate

- ea: `0x18014276c`
- end: `0x1801428d9`
- name: `RtlpSetMachineUILanguagesImmediate`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1801428e0`

## callees

- `0x180011c70`
- `0x1800c0420`
- `0x180141960`
- `0x18014276c`
- `0x18015e4b0`
- `0x18015eec0`

## string_xrefs

- `0x180142823`: `Control Panel\Desktop\MuiCached`
- `0x180142799`: `\Registry\Machine\System\CurrentControlSet\Control\MUI\Settings`

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
0x18014276c  push    rbp
0x18014276e  push    rbx
0x18014276f  push    rdi
0x180142770  mov     rbp, rsp
0x180142773  sub     rsp, 40h
0x180142777  mov     rdi, rcx
0x18014277a  mov     [rbp+Handle], 0
0x180142782  xorps   xmm0, xmm0
0x180142785  mov     [rbp+arg_10], 0
0x18014278d  lea     rcx, [rbp+DestinationString]; DestinationString
0x180142791  mov     [rbp+arg_18], 0
0x180142799  lea     rdx, aRegistryMachin_8; "\\Registry\\Machine\\System\\CurrentCon"...
0x1801427a0  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1801427a4  call    RtlInitUnicodeString
0x1801427a9  lea     rax, [rbp+Handle]
0x1801427ad  mov     r9d, 0F003Fh
0x1801427b3  xor     r8d, r8d
0x1801427b6  mov     [rsp+40h+var_20], rax
0x1801427bb  xor     edx, edx
0x1801427bd  lea     rcx, [rbp+DestinationString]
0x1801427c1  call    LdrpCreateKey
0x1801427c6  mov     ebx, eax
0x1801427c8  test    eax, eax
0x1801427ca  js      loc_180142894
0x1801427d0  lea     rdx, aPreferreduilan; "PreferredUILanguages"
0x1801427d7  lea     rcx, [rbp+DestinationString]; DestinationString
0x1801427db  call    RtlInitUnicodeString
0x1801427e0  movzx   eax, word ptr [rdi+2]
0x1801427e4  lea     rdx, [rbp+DestinationString]
0x1801427e8  mov     rcx, [rbp+Handle]
0x1801427ec  mov     r9d, 7
0x1801427f2  mov     [rsp+40h+var_18], eax
0x1801427f6  xor     r8d, r8d
0x1801427f9  mov     rax, [rdi+8]
0x1801427fd  mov     [rsp+40h+var_20], rax
0x180142802  call    ZwSetValueKey
0x180142807  mov     ebx, eax
0x180142809  test    eax, eax
0x18014280b  js      loc_180142894
0x180142811  lea     r8, [rbp+arg_18]
0x180142815  mov     ecx, 2000000h
0x18014281a  call    OpenGlobalizationUserSettingsKey
0x18014281f  test    eax, eax
0x180142821  js      short loc_180142894
0x180142823  lea     rdx, aControlPanelDe; "Control Panel\\Desktop\\MuiCached"
0x18014282a  lea     rcx, [rbp+DestinationString]; DestinationString
0x18014282e  call    RtlInitUnicodeString
0x180142833  mov     rdx, [rbp+arg_18]
0x180142837  lea     rax, [rbp+arg_10]
0x18014283b  mov     r9d, 0F003Fh
0x180142841  mov     [rsp+40h+var_20], rax
0x180142846  mov     r8d, 1
0x18014284c  lea     rcx, [rbp+DestinationString]
0x180142850  call    LdrpCreateKey
0x180142855  mov     ebx, eax
0x180142857  test    eax, eax
0x180142859  js      short loc_180142894
0x18014285b  lea     rdx, aMachinepreferr; "MachinePreferredUILanguages"
0x180142862  lea     rcx, [rbp+DestinationString]; DestinationString
0x180142866  call    RtlInitUnicodeString
0x18014286b  movzx   eax, word ptr [rdi+2]
0x18014286f  lea     rdx, [rbp+DestinationString]
0x180142873  mov     rcx, [rbp+arg_10]
0x180142877  mov     r9d, 7
0x18014287d  mov     [rsp+40h+var_18], eax
0x180142881  xor     r8d, r8d
0x180142884  mov     rax, [rdi+8]
0x180142888  mov     [rsp+40h+var_20], rax
0x18014288d  call    ZwSetValueKey
0x180142892  mov     ebx, eax
0x180142894  mov     rcx, [rbp+Handle]; Handle
0x180142898  test    rcx, rcx
0x18014289b  jz      short loc_1801428AA
0x18014289d  call    NtClose
0x1801428a2  mov     [rbp+Handle], 0
0x1801428aa  mov     rcx, [rbp+arg_10]; Handle
0x1801428ae  test    rcx, rcx
0x1801428b1  jz      short loc_1801428C0
0x1801428b3  call    NtClose
0x1801428b8  mov     [rbp+arg_10], 0
0x1801428c0  mov     rcx, [rbp+arg_18]; Handle
0x1801428c4  test    rcx, rcx
0x1801428c7  jz      short loc_1801428CE
0x1801428c9  call    NtClose
0x1801428ce  mov     eax, ebx
0x1801428d0  add     rsp, 40h
0x1801428d4  pop     rdi
0x1801428d5  pop     rbx
0x1801428d6  pop     rbp
0x1801428d7  retn
```
