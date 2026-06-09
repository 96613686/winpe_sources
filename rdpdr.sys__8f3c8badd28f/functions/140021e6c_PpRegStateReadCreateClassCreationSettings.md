# PpRegStateReadCreateClassCreationSettings

- ea: `0x140021e6c`
- end: `0x140021fd0`
- name: `PpRegStateReadCreateClassCreationSettings`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140020f00`

## callees

- `0x140005d08`
- `0x140021af0`
- `0x140021c84`
- `0x140021e6c`
- `0x140022360`
- `0x140022560`
- `0x140022744`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140021ef8`
- `ntoskrnl!ZwClose` at `0x140021fb1`
- `ntoskrnl!ZwClose` at `0x140021ef8`
- `ntoskrnl!ZwClose` at `0x140021fb1`

## pseudocode

```c
NTSTATUS __fastcall PpRegStateReadCreateClassCreationSettings(unsigned int *a1, __int64 a2, _QWORD *a3)
{
  NTSTATUS result; // eax
  int inited; // ebx
  int StackCreationSettingsFromKey; // eax
  void *v8; // rcx
  HANDLE v9; // rdi
  unsigned __int16 *v10; // r10
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  int v12; // [rsp+60h] [rbp+20h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp+28h] BYREF

  *a3 = 0;
  a3[1] = 0;
  a3[2] = 0;
  v12 = 0;
  Handle = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  result = PiRegStateOpenClassKey(a1, a2, 1, &v12, &Handle);
  if ( result >= 0 )
  {
    if ( v12 == 2 )
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
          inited = CmRegUtilUcValueSetUcString(v9, &DestinationString, v10);
          if ( inited >= 0 )
          {
            v12 = 49;
            inited = CmRegUtilWstrValueSetWstrString(v9, L"NoDisplayClass", &v12);
            if ( inited >= 0 )
              inited = CmRegUtilWstrValueSetWstrString(v9, L"NoUseClass", &v12);
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
0x140021e6c  mov     [rsp-8+arg_0], rbx
0x140021e71  mov     [rsp-8+arg_8], rdi
0x140021e76  push    rbp
0x140021e77  mov     rbp, rsp
0x140021e7a  sub     rsp, 40h
0x140021e7e  mov     rdi, r8
0x140021e81  mov     qword ptr [r8], 0
0x140021e88  mov     qword ptr [r8+8], 0
0x140021e90  lea     rax, [rbp+Handle]
0x140021e94  mov     qword ptr [r8+10h], 0
0x140021e9c  lea     r9, [rbp+arg_10]
0x140021ea0  mov     r8d, 1
0x140021ea6  mov     [rsp+40h+var_20], rax
0x140021eab  mov     rbx, rdx
0x140021eae  mov     [rbp+arg_10], 0
0x140021eb5  mov     [rbp+Handle], 0
0x140021ebd  mov     qword ptr [rbp+DestinationString.Length], 0
0x140021ec5  call    PiRegStateOpenClassKey
0x140021eca  test    eax, eax
0x140021ecc  js      loc_140021FBF
0x140021ed2  cmp     [rbp+arg_10], 2
0x140021ed6  jnz     short loc_140021F32
0x140021ed8  mov     rcx, [rbp+Handle]
0x140021edc  lea     r9, [rbp+DestinationString]
0x140021ee0  mov     r8d, 20019h
0x140021ee6  lea     rdx, aProperties; "Properties"
0x140021eed  call    CmRegUtilOpenExistingWstrKey
0x140021ef2  mov     rcx, [rbp+Handle]; Handle
0x140021ef6  mov     ebx, eax
0x140021ef8  call    cs:__imp_ZwClose
0x140021eff  nop     dword ptr [rax+rax+00h]
0x140021f04  test    ebx, ebx
0x140021f06  js      short loc_140021F1F
0x140021f08  mov     rcx, qword ptr [rbp+DestinationString.Length]; KeyHandle
0x140021f0c  mov     rdx, rdi
0x140021f0f  call    PiRegStateReadStackCreationSettingsFromKey
0x140021f14  mov     rcx, qword ptr [rbp+DestinationString.Length]
0x140021f18  mov     ebx, eax
0x140021f1a  jmp     loc_140021FB1
0x140021f1f  cmp     ebx, 0C0000034h
0x140021f25  jnz     loc_140021FBD
0x140021f2b  xor     ebx, ebx
0x140021f2d  jmp     loc_140021FBD
0x140021f32  mov     r10, [rbx+30h]
0x140021f36  mov     rdi, [rbp+Handle]
0x140021f3a  add     r10, 18h
0x140021f3e  jnz     short loc_140021F47
0x140021f40  mov     ebx, 0C000009Ah
0x140021f45  jmp     short loc_140021FAE
0x140021f47  xorps   xmm0, xmm0
0x140021f4a  lea     rdx, aClass; "Class"
0x140021f51  lea     rcx, [rbp+DestinationString]; DestinationString
0x140021f55  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140021f59  call    WdmlibRtlInitUnicodeStringEx
0x140021f5e  mov     ebx, eax
0x140021f60  test    eax, eax
0x140021f62  js      short loc_140021FAE
0x140021f64  mov     r8, r10
0x140021f67  lea     rdx, [rbp+DestinationString]; ValueName
0x140021f6b  mov     rcx, rdi; KeyHandle
0x140021f6e  call    CmRegUtilUcValueSetUcString
0x140021f73  mov     ebx, eax
0x140021f75  test    eax, eax
0x140021f77  js      short loc_140021FAE
0x140021f79  lea     r8, [rbp+arg_10]
0x140021f7d  mov     [rbp+arg_10], 31h ; '1'
0x140021f84  lea     rdx, aNodisplayclass; "NoDisplayClass"
0x140021f8b  mov     rcx, rdi
0x140021f8e  call    CmRegUtilWstrValueSetWstrString
0x140021f93  mov     ebx, eax
0x140021f95  test    eax, eax
0x140021f97  js      short loc_140021FAE
0x140021f99  lea     r8, [rbp+arg_10]
0x140021f9d  mov     rcx, rdi
0x140021fa0  lea     rdx, aNouseclass; "NoUseClass"
0x140021fa7  call    CmRegUtilWstrValueSetWstrString
0x140021fac  mov     ebx, eax
0x140021fae  mov     rcx, rdi; Handle
0x140021fb1  call    cs:__imp_ZwClose
0x140021fb8  nop     dword ptr [rax+rax+00h]
0x140021fbd  mov     eax, ebx
0x140021fbf  mov     rbx, [rsp+40h+arg_0]
0x140021fc4  mov     rdi, [rsp+40h+arg_8]
0x140021fc9  add     rsp, 40h
0x140021fcd  pop     rbp
0x140021fce  retn
```
