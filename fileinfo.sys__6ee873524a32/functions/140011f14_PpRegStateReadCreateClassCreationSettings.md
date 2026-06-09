# PpRegStateReadCreateClassCreationSettings

- ea: `0x140011f14`
- end: `0x140012078`
- name: `PpRegStateReadCreateClassCreationSettings`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140010f90`

## callees

- `0x1400037b8`
- `0x140011b98`
- `0x140011d2c`
- `0x140011f14`
- `0x140012408`
- `0x140012608`
- `0x1400127ec`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140011fa0`
- `ntoskrnl!ZwClose` at `0x140012059`
- `ntoskrnl!ZwClose` at `0x140011fa0`
- `ntoskrnl!ZwClose` at `0x140012059`

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
0x140011f14  mov     [rsp-8+arg_0], rbx
0x140011f19  mov     [rsp-8+arg_8], rdi
0x140011f1e  push    rbp
0x140011f1f  mov     rbp, rsp
0x140011f22  sub     rsp, 40h
0x140011f26  mov     rdi, r8
0x140011f29  mov     qword ptr [r8], 0
0x140011f30  mov     qword ptr [r8+8], 0
0x140011f38  lea     rax, [rbp+Handle]
0x140011f3c  mov     qword ptr [r8+10h], 0
0x140011f44  lea     r9, [rbp+arg_10]
0x140011f48  mov     r8d, 1
0x140011f4e  mov     [rsp+40h+var_20], rax
0x140011f53  mov     rbx, rdx
0x140011f56  mov     [rbp+arg_10], 0
0x140011f5d  mov     [rbp+Handle], 0
0x140011f65  mov     qword ptr [rbp+DestinationString.Length], 0
0x140011f6d  call    PiRegStateOpenClassKey
0x140011f72  test    eax, eax
0x140011f74  js      loc_140012067
0x140011f7a  cmp     [rbp+arg_10], 2
0x140011f7e  jnz     short loc_140011FDA
0x140011f80  mov     rcx, [rbp+Handle]
0x140011f84  lea     r9, [rbp+DestinationString]
0x140011f88  mov     r8d, 20019h
0x140011f8e  lea     rdx, aProperties; "Properties"
0x140011f95  call    CmRegUtilOpenExistingWstrKey
0x140011f9a  mov     rcx, [rbp+Handle]; Handle
0x140011f9e  mov     ebx, eax
0x140011fa0  call    cs:__imp_ZwClose
0x140011fa7  nop     dword ptr [rax+rax+00h]
0x140011fac  test    ebx, ebx
0x140011fae  js      short loc_140011FC7
0x140011fb0  mov     rcx, qword ptr [rbp+DestinationString.Length]; KeyHandle
0x140011fb4  mov     rdx, rdi
0x140011fb7  call    PiRegStateReadStackCreationSettingsFromKey
0x140011fbc  mov     rcx, qword ptr [rbp+DestinationString.Length]
0x140011fc0  mov     ebx, eax
0x140011fc2  jmp     loc_140012059
0x140011fc7  cmp     ebx, 0C0000034h
0x140011fcd  jnz     loc_140012065
0x140011fd3  xor     ebx, ebx
0x140011fd5  jmp     loc_140012065
0x140011fda  mov     r10, [rbx+30h]
0x140011fde  mov     rdi, [rbp+Handle]
0x140011fe2  add     r10, 18h
0x140011fe6  jnz     short loc_140011FEF
0x140011fe8  mov     ebx, 0C000009Ah
0x140011fed  jmp     short loc_140012056
0x140011fef  xorps   xmm0, xmm0
0x140011ff2  lea     rdx, aClass; "Class"
0x140011ff9  lea     rcx, [rbp+DestinationString]; DestinationString
0x140011ffd  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140012001  call    WdmlibRtlInitUnicodeStringEx
0x140012006  mov     ebx, eax
0x140012008  test    eax, eax
0x14001200a  js      short loc_140012056
0x14001200c  mov     r8, r10
0x14001200f  lea     rdx, [rbp+DestinationString]; ValueName
0x140012013  mov     rcx, rdi; KeyHandle
0x140012016  call    CmRegUtilUcValueSetUcString
0x14001201b  mov     ebx, eax
0x14001201d  test    eax, eax
0x14001201f  js      short loc_140012056
0x140012021  lea     r8, [rbp+arg_10]
0x140012025  mov     [rbp+arg_10], 31h ; '1'
0x14001202c  lea     rdx, aNodisplayclass; "NoDisplayClass"
0x140012033  mov     rcx, rdi
0x140012036  call    CmRegUtilWstrValueSetWstrString
0x14001203b  mov     ebx, eax
0x14001203d  test    eax, eax
0x14001203f  js      short loc_140012056
0x140012041  lea     r8, [rbp+arg_10]
0x140012045  mov     rcx, rdi
0x140012048  lea     rdx, aNouseclass; "NoUseClass"
0x14001204f  call    CmRegUtilWstrValueSetWstrString
0x140012054  mov     ebx, eax
0x140012056  mov     rcx, rdi; Handle
0x140012059  call    cs:__imp_ZwClose
0x140012060  nop     dword ptr [rax+rax+00h]
0x140012065  mov     eax, ebx
0x140012067  mov     rbx, [rsp+40h+arg_0]
0x14001206c  mov     rdi, [rsp+40h+arg_8]
0x140012071  add     rsp, 40h
0x140012075  pop     rbp
0x140012076  retn
```
