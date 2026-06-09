# PpRegStateReadCreateClassCreationSettings

- ea: `0x140043c54`
- end: `0x140043db8`
- name: `PpRegStateReadCreateClassCreationSettings`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140042cc0`

## callees

- `0x14002811c`
- `0x1400438d8`
- `0x140043a6c`
- `0x140043c54`
- `0x140044110`
- `0x140044310`
- `0x1400444f4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140043ce0`
- `ntoskrnl!ZwClose` at `0x140043d99`
- `ntoskrnl!ZwClose` at `0x140043ce0`
- `ntoskrnl!ZwClose` at `0x140043d99`

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
  ULONG v11; // [rsp+60h] [rbp+20h] BYREF
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
0x140043c54  mov     [rsp-8+arg_0], rbx
0x140043c59  mov     [rsp-8+arg_8], rdi
0x140043c5e  push    rbp
0x140043c5f  mov     rbp, rsp
0x140043c62  sub     rsp, 40h
0x140043c66  mov     rdi, r8
0x140043c69  mov     qword ptr [r8], 0
0x140043c70  mov     qword ptr [r8+8], 0
0x140043c78  lea     rax, [rbp+Handle]
0x140043c7c  mov     qword ptr [r8+10h], 0
0x140043c84  lea     r9, [rbp+arg_10]
0x140043c88  mov     r8d, 1
0x140043c8e  mov     [rsp+40h+var_20], rax
0x140043c93  mov     rbx, rdx
0x140043c96  mov     [rbp+arg_10], 0
0x140043c9d  mov     [rbp+Handle], 0
0x140043ca5  mov     qword ptr [rbp+DestinationString.Length], 0
0x140043cad  call    PiRegStateOpenClassKey
0x140043cb2  test    eax, eax
0x140043cb4  js      loc_140043DA7
0x140043cba  cmp     [rbp+arg_10], 2
0x140043cbe  jnz     short loc_140043D1A
0x140043cc0  mov     rcx, [rbp+Handle]
0x140043cc4  lea     r9, [rbp+DestinationString]
0x140043cc8  mov     r8d, 20019h
0x140043cce  lea     rdx, aProperties; "Properties"
0x140043cd5  call    CmRegUtilOpenExistingWstrKey
0x140043cda  mov     rcx, [rbp+Handle]; Handle
0x140043cde  mov     ebx, eax
0x140043ce0  call    cs:__imp_ZwClose
0x140043ce7  nop     dword ptr [rax+rax+00h]
0x140043cec  test    ebx, ebx
0x140043cee  js      short loc_140043D07
0x140043cf0  mov     rcx, qword ptr [rbp+DestinationString.Length]; KeyHandle
0x140043cf4  mov     rdx, rdi
0x140043cf7  call    PiRegStateReadStackCreationSettingsFromKey
0x140043cfc  mov     rcx, qword ptr [rbp+DestinationString.Length]
0x140043d00  mov     ebx, eax
0x140043d02  jmp     loc_140043D99
0x140043d07  cmp     ebx, 0C0000034h
0x140043d0d  jnz     loc_140043DA5
0x140043d13  xor     ebx, ebx
0x140043d15  jmp     loc_140043DA5
0x140043d1a  mov     r10, [rbx+30h]
0x140043d1e  mov     rdi, [rbp+Handle]
0x140043d22  add     r10, 18h
0x140043d26  jnz     short loc_140043D2F
0x140043d28  mov     ebx, 0C000009Ah
0x140043d2d  jmp     short loc_140043D96
0x140043d2f  xorps   xmm0, xmm0
0x140043d32  lea     rdx, aClass; "Class"
0x140043d39  lea     rcx, [rbp+DestinationString]; DestinationString
0x140043d3d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140043d41  call    WdmlibRtlInitUnicodeStringEx
0x140043d46  mov     ebx, eax
0x140043d48  test    eax, eax
0x140043d4a  js      short loc_140043D96
0x140043d4c  mov     r8, r10
0x140043d4f  lea     rdx, [rbp+DestinationString]; ValueName
0x140043d53  mov     rcx, rdi; KeyHandle
0x140043d56  call    CmRegUtilUcValueSetUcString
0x140043d5b  mov     ebx, eax
0x140043d5d  test    eax, eax
0x140043d5f  js      short loc_140043D96
0x140043d61  lea     r8, [rbp+arg_10]
0x140043d65  mov     [rbp+arg_10], 31h ; '1'
0x140043d6c  lea     rdx, aNodisplayclass; "NoDisplayClass"
0x140043d73  mov     rcx, rdi
0x140043d76  call    CmRegUtilWstrValueSetWstrString
0x140043d7b  mov     ebx, eax
0x140043d7d  test    eax, eax
0x140043d7f  js      short loc_140043D96
0x140043d81  lea     r8, [rbp+arg_10]
0x140043d85  mov     rcx, rdi
0x140043d88  lea     rdx, aNouseclass; "NoUseClass"
0x140043d8f  call    CmRegUtilWstrValueSetWstrString
0x140043d94  mov     ebx, eax
0x140043d96  mov     rcx, rdi; Handle
0x140043d99  call    cs:__imp_ZwClose
0x140043da0  nop     dword ptr [rax+rax+00h]
0x140043da5  mov     eax, ebx
0x140043da7  mov     rbx, [rsp+40h+arg_0]
0x140043dac  mov     rdi, [rsp+40h+arg_8]
0x140043db1  add     rsp, 40h
0x140043db5  pop     rbp
0x140043db6  retn
```
