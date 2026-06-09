# PpRegStateReadCreateClassCreationSettings

- ea: `0x14000e1c4`
- end: `0x14000e328`
- name: `PpRegStateReadCreateClassCreationSettings`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14000d240`

## callees

- `0x140006430`
- `0x14000de48`
- `0x14000dfdc`
- `0x14000e1c4`
- `0x14000e6b8`
- `0x14000e8b8`
- `0x14000ea9c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000e250`
- `ntoskrnl!ZwClose` at `0x14000e309`
- `ntoskrnl!ZwClose` at `0x14000e250`
- `ntoskrnl!ZwClose` at `0x14000e309`

## pseudocode

```c
NTSTATUS __fastcall PpRegStateReadCreateClassCreationSettings(unsigned int *a1, __int64 a2, _QWORD *a3)
{
  NTSTATUS result; // eax
  NTSTATUS inited; // ebx
  NTSTATUS StackCreationSettingsFromKey; // eax
  void *v8; // rcx
  HANDLE v9; // rdi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  int v11; // [rsp+60h] [rbp+20h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp+28h] BYREF

  *a3 = 0;
  a3[1] = 0;
  a3[2] = 0;
  v11 = 0;
  Handle = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  result = PiRegStateOpenClassKey(a1, a2, 1, &v11, &Handle);
  if ( result >= 0 )
  {
    if ( v11 == 2 )
    {
      inited = CmRegUtilOpenExistingWstrKey((__int64)Handle, L"Properties", 131097, (void **)&DestinationString);
      ZwClose(Handle);
      if ( inited < 0 )
      {
        if ( inited == -1073741772 )
          return 0;
        return inited;
      }
      StackCreationSettingsFromKey = PiRegStateReadStackCreationSettingsFromKey(
                                       *(HANDLE *)&DestinationString.Length,
                                       (__int64)a3);
      v8 = *(void **)&DestinationString.Length;
      inited = StackCreationSettingsFromKey;
    }
    else
    {
      v9 = Handle;
      if ( *(_QWORD *)(a2 + 48) == -24 )
      {
        inited = -1073741670;
      }
      else
      {
        DestinationString = 0;
        inited = WdmlibRtlInitUnicodeStringEx(&DestinationString, L"Class");
        if ( inited >= 0 )
        {
          inited = CmRegUtilUcValueSetUcString(v9, &DestinationString);
          if ( inited >= 0 )
          {
            v11 = 49;
            inited = CmRegUtilWstrValueSetWstrString(v9, L"NoDisplayClass", &v11);
            if ( inited >= 0 )
              inited = CmRegUtilWstrValueSetWstrString(v9, L"NoUseClass", &v11);
          }
        }
      }
      v8 = v9;
    }
    ZwClose(v8);
    return inited;
  }
  return result;
}

```

## disassembly

```asm
0x14000e1c4  mov     [rsp-8+arg_0], rbx
0x14000e1c9  mov     [rsp-8+arg_8], rdi
0x14000e1ce  push    rbp
0x14000e1cf  mov     rbp, rsp
0x14000e1d2  sub     rsp, 40h
0x14000e1d6  mov     rdi, r8
0x14000e1d9  mov     qword ptr [r8], 0
0x14000e1e0  mov     qword ptr [r8+8], 0
0x14000e1e8  lea     rax, [rbp+Handle]
0x14000e1ec  mov     qword ptr [r8+10h], 0
0x14000e1f4  lea     r9, [rbp+arg_10]
0x14000e1f8  mov     r8d, 1
0x14000e1fe  mov     [rsp+40h+var_20], rax
0x14000e203  mov     rbx, rdx
0x14000e206  mov     [rbp+arg_10], 0
0x14000e20d  mov     [rbp+Handle], 0
0x14000e215  mov     qword ptr [rbp+DestinationString.Length], 0
0x14000e21d  call    PiRegStateOpenClassKey
0x14000e222  test    eax, eax
0x14000e224  js      loc_14000E317
0x14000e22a  cmp     [rbp+arg_10], 2
0x14000e22e  jnz     short loc_14000E28A
0x14000e230  mov     rcx, [rbp+Handle]
0x14000e234  lea     r9, [rbp+DestinationString]
0x14000e238  mov     r8d, 20019h
0x14000e23e  lea     rdx, aProperties; "Properties"
0x14000e245  call    CmRegUtilOpenExistingWstrKey
0x14000e24a  mov     rcx, [rbp+Handle]; Handle
0x14000e24e  mov     ebx, eax
0x14000e250  call    cs:__imp_ZwClose
0x14000e257  nop     dword ptr [rax+rax+00h]
0x14000e25c  test    ebx, ebx
0x14000e25e  js      short loc_14000E277
0x14000e260  mov     rcx, qword ptr [rbp+DestinationString.Length]; KeyHandle
0x14000e264  mov     rdx, rdi
0x14000e267  call    PiRegStateReadStackCreationSettingsFromKey
0x14000e26c  mov     rcx, qword ptr [rbp+DestinationString.Length]
0x14000e270  mov     ebx, eax
0x14000e272  jmp     loc_14000E309
0x14000e277  cmp     ebx, 0C0000034h
0x14000e27d  jnz     loc_14000E315
0x14000e283  xor     ebx, ebx
0x14000e285  jmp     loc_14000E315
0x14000e28a  mov     r10, [rbx+30h]
0x14000e28e  mov     rdi, [rbp+Handle]
0x14000e292  add     r10, 18h
0x14000e296  jnz     short loc_14000E29F
0x14000e298  mov     ebx, 0C000009Ah
0x14000e29d  jmp     short loc_14000E306
0x14000e29f  xorps   xmm0, xmm0
0x14000e2a2  lea     rdx, aClass; "Class"
0x14000e2a9  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000e2ad  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000e2b1  call    WdmlibRtlInitUnicodeStringEx
0x14000e2b6  mov     ebx, eax
0x14000e2b8  test    eax, eax
0x14000e2ba  js      short loc_14000E306
0x14000e2bc  mov     r8, r10
0x14000e2bf  lea     rdx, [rbp+DestinationString]; ValueName
0x14000e2c3  mov     rcx, rdi; KeyHandle
0x14000e2c6  call    CmRegUtilUcValueSetUcString
0x14000e2cb  mov     ebx, eax
0x14000e2cd  test    eax, eax
0x14000e2cf  js      short loc_14000E306
0x14000e2d1  lea     r8, [rbp+arg_10]
0x14000e2d5  mov     [rbp+arg_10], 31h ; '1'
0x14000e2dc  lea     rdx, aNodisplayclass; "NoDisplayClass"
0x14000e2e3  mov     rcx, rdi
0x14000e2e6  call    CmRegUtilWstrValueSetWstrString
0x14000e2eb  mov     ebx, eax
0x14000e2ed  test    eax, eax
0x14000e2ef  js      short loc_14000E306
0x14000e2f1  lea     r8, [rbp+arg_10]
0x14000e2f5  mov     rcx, rdi
0x14000e2f8  lea     rdx, aNouseclass; "NoUseClass"
0x14000e2ff  call    CmRegUtilWstrValueSetWstrString
0x14000e304  mov     ebx, eax
0x14000e306  mov     rcx, rdi; Handle
0x14000e309  call    cs:__imp_ZwClose
0x14000e310  nop     dword ptr [rax+rax+00h]
0x14000e315  mov     eax, ebx
0x14000e317  mov     rbx, [rsp+40h+arg_0]
0x14000e31c  mov     rdi, [rsp+40h+arg_8]
0x14000e321  add     rsp, 40h
0x14000e325  pop     rbp
0x14000e326  retn
```
