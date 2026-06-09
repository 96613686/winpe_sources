# PpRegStateReadCreateClassCreationSettings

- ea: `0x140018734`
- end: `0x140018898`
- name: `PpRegStateReadCreateClassCreationSettings`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400177c0`

## callees

- `0x140007e0c`
- `0x1400183b8`
- `0x14001854c`
- `0x140018734`
- `0x140018bf0`
- `0x140018df0`
- `0x140018fd4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400187c0`
- `ntoskrnl!ZwClose` at `0x140018879`
- `ntoskrnl!ZwClose` at `0x1400187c0`
- `ntoskrnl!ZwClose` at `0x140018879`

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
0x140018734  mov     [rsp-8+arg_0], rbx
0x140018739  mov     [rsp-8+arg_8], rdi
0x14001873e  push    rbp
0x14001873f  mov     rbp, rsp
0x140018742  sub     rsp, 40h
0x140018746  mov     rdi, r8
0x140018749  mov     qword ptr [r8], 0
0x140018750  mov     qword ptr [r8+8], 0
0x140018758  lea     rax, [rbp+Handle]
0x14001875c  mov     qword ptr [r8+10h], 0
0x140018764  lea     r9, [rbp+arg_10]
0x140018768  mov     r8d, 1
0x14001876e  mov     [rsp+40h+var_20], rax
0x140018773  mov     rbx, rdx
0x140018776  mov     [rbp+arg_10], 0
0x14001877d  mov     [rbp+Handle], 0
0x140018785  mov     qword ptr [rbp+DestinationString.Length], 0
0x14001878d  call    PiRegStateOpenClassKey
0x140018792  test    eax, eax
0x140018794  js      loc_140018887
0x14001879a  cmp     [rbp+arg_10], 2
0x14001879e  jnz     short loc_1400187FA
0x1400187a0  mov     rcx, [rbp+Handle]
0x1400187a4  lea     r9, [rbp+DestinationString]
0x1400187a8  mov     r8d, 20019h
0x1400187ae  lea     rdx, aProperties; "Properties"
0x1400187b5  call    CmRegUtilOpenExistingWstrKey
0x1400187ba  mov     rcx, [rbp+Handle]; Handle
0x1400187be  mov     ebx, eax
0x1400187c0  call    cs:__imp_ZwClose
0x1400187c7  nop     dword ptr [rax+rax+00h]
0x1400187cc  test    ebx, ebx
0x1400187ce  js      short loc_1400187E7
0x1400187d0  mov     rcx, qword ptr [rbp+DestinationString.Length]; KeyHandle
0x1400187d4  mov     rdx, rdi
0x1400187d7  call    PiRegStateReadStackCreationSettingsFromKey
0x1400187dc  mov     rcx, qword ptr [rbp+DestinationString.Length]
0x1400187e0  mov     ebx, eax
0x1400187e2  jmp     loc_140018879
0x1400187e7  cmp     ebx, 0C0000034h
0x1400187ed  jnz     loc_140018885
0x1400187f3  xor     ebx, ebx
0x1400187f5  jmp     loc_140018885
0x1400187fa  mov     r10, [rbx+30h]
0x1400187fe  mov     rdi, [rbp+Handle]
0x140018802  add     r10, 18h
0x140018806  jnz     short loc_14001880F
0x140018808  mov     ebx, 0C000009Ah
0x14001880d  jmp     short loc_140018876
0x14001880f  xorps   xmm0, xmm0
0x140018812  lea     rdx, aClass; "Class"
0x140018819  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001881d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140018821  call    WdmlibRtlInitUnicodeStringEx
0x140018826  mov     ebx, eax
0x140018828  test    eax, eax
0x14001882a  js      short loc_140018876
0x14001882c  mov     r8, r10
0x14001882f  lea     rdx, [rbp+DestinationString]; ValueName
0x140018833  mov     rcx, rdi; KeyHandle
0x140018836  call    CmRegUtilUcValueSetUcString
0x14001883b  mov     ebx, eax
0x14001883d  test    eax, eax
0x14001883f  js      short loc_140018876
0x140018841  lea     r8, [rbp+arg_10]
0x140018845  mov     [rbp+arg_10], 31h ; '1'
0x14001884c  lea     rdx, aNodisplayclass; "NoDisplayClass"
0x140018853  mov     rcx, rdi
0x140018856  call    CmRegUtilWstrValueSetWstrString
0x14001885b  mov     ebx, eax
0x14001885d  test    eax, eax
0x14001885f  js      short loc_140018876
0x140018861  lea     r8, [rbp+arg_10]
0x140018865  mov     rcx, rdi
0x140018868  lea     rdx, aNouseclass; "NoUseClass"
0x14001886f  call    CmRegUtilWstrValueSetWstrString
0x140018874  mov     ebx, eax
0x140018876  mov     rcx, rdi; Handle
0x140018879  call    cs:__imp_ZwClose
0x140018880  nop     dword ptr [rax+rax+00h]
0x140018885  mov     eax, ebx
0x140018887  mov     rbx, [rsp+40h+arg_0]
0x14001888c  mov     rdi, [rsp+40h+arg_8]
0x140018891  add     rsp, 40h
0x140018895  pop     rbp
0x140018896  retn
```
