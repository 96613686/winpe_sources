# PpRegStateReadCreateClassCreationSettings

- ea: `0x14000a134`
- end: `0x14000a298`
- name: `PpRegStateReadCreateClassCreationSettings`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400091b0`

## callees

- `0x140002350`
- `0x140009db8`
- `0x140009f4c`
- `0x14000a134`
- `0x14000a628`
- `0x14000a828`
- `0x14000aa0c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000a1c0`
- `ntoskrnl!ZwClose` at `0x14000a279`
- `ntoskrnl!ZwClose` at `0x14000a1c0`
- `ntoskrnl!ZwClose` at `0x14000a279`

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
0x14000a134  mov     [rsp-8+arg_0], rbx
0x14000a139  mov     [rsp-8+arg_8], rdi
0x14000a13e  push    rbp
0x14000a13f  mov     rbp, rsp
0x14000a142  sub     rsp, 40h
0x14000a146  mov     rdi, r8
0x14000a149  mov     qword ptr [r8], 0
0x14000a150  mov     qword ptr [r8+8], 0
0x14000a158  lea     rax, [rbp+Handle]
0x14000a15c  mov     qword ptr [r8+10h], 0
0x14000a164  lea     r9, [rbp+arg_10]
0x14000a168  mov     r8d, 1
0x14000a16e  mov     [rsp+40h+var_20], rax
0x14000a173  mov     rbx, rdx
0x14000a176  mov     [rbp+arg_10], 0
0x14000a17d  mov     [rbp+Handle], 0
0x14000a185  mov     qword ptr [rbp+DestinationString.Length], 0
0x14000a18d  call    PiRegStateOpenClassKey
0x14000a192  test    eax, eax
0x14000a194  js      loc_14000A287
0x14000a19a  cmp     [rbp+arg_10], 2
0x14000a19e  jnz     short loc_14000A1FA
0x14000a1a0  mov     rcx, [rbp+Handle]
0x14000a1a4  lea     r9, [rbp+DestinationString]
0x14000a1a8  mov     r8d, 20019h
0x14000a1ae  lea     rdx, aProperties; "Properties"
0x14000a1b5  call    CmRegUtilOpenExistingWstrKey
0x14000a1ba  mov     rcx, [rbp+Handle]; Handle
0x14000a1be  mov     ebx, eax
0x14000a1c0  call    cs:__imp_ZwClose
0x14000a1c7  nop     dword ptr [rax+rax+00h]
0x14000a1cc  test    ebx, ebx
0x14000a1ce  js      short loc_14000A1E7
0x14000a1d0  mov     rcx, qword ptr [rbp+DestinationString.Length]; KeyHandle
0x14000a1d4  mov     rdx, rdi
0x14000a1d7  call    PiRegStateReadStackCreationSettingsFromKey
0x14000a1dc  mov     rcx, qword ptr [rbp+DestinationString.Length]
0x14000a1e0  mov     ebx, eax
0x14000a1e2  jmp     loc_14000A279
0x14000a1e7  cmp     ebx, 0C0000034h
0x14000a1ed  jnz     loc_14000A285
0x14000a1f3  xor     ebx, ebx
0x14000a1f5  jmp     loc_14000A285
0x14000a1fa  mov     r10, [rbx+30h]
0x14000a1fe  mov     rdi, [rbp+Handle]
0x14000a202  add     r10, 18h
0x14000a206  jnz     short loc_14000A20F
0x14000a208  mov     ebx, 0C000009Ah
0x14000a20d  jmp     short loc_14000A276
0x14000a20f  xorps   xmm0, xmm0
0x14000a212  lea     rdx, aClass; "Class"
0x14000a219  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000a21d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000a221  call    WdmlibRtlInitUnicodeStringEx
0x14000a226  mov     ebx, eax
0x14000a228  test    eax, eax
0x14000a22a  js      short loc_14000A276
0x14000a22c  mov     r8, r10
0x14000a22f  lea     rdx, [rbp+DestinationString]; ValueName
0x14000a233  mov     rcx, rdi; KeyHandle
0x14000a236  call    CmRegUtilUcValueSetUcString
0x14000a23b  mov     ebx, eax
0x14000a23d  test    eax, eax
0x14000a23f  js      short loc_14000A276
0x14000a241  lea     r8, [rbp+arg_10]
0x14000a245  mov     [rbp+arg_10], 31h ; '1'
0x14000a24c  lea     rdx, aNodisplayclass; "NoDisplayClass"
0x14000a253  mov     rcx, rdi
0x14000a256  call    CmRegUtilWstrValueSetWstrString
0x14000a25b  mov     ebx, eax
0x14000a25d  test    eax, eax
0x14000a25f  js      short loc_14000A276
0x14000a261  lea     r8, [rbp+arg_10]
0x14000a265  mov     rcx, rdi
0x14000a268  lea     rdx, aNouseclass; "NoUseClass"
0x14000a26f  call    CmRegUtilWstrValueSetWstrString
0x14000a274  mov     ebx, eax
0x14000a276  mov     rcx, rdi; Handle
0x14000a279  call    cs:__imp_ZwClose
0x14000a280  nop     dword ptr [rax+rax+00h]
0x14000a285  mov     eax, ebx
0x14000a287  mov     rbx, [rsp+40h+arg_0]
0x14000a28c  mov     rdi, [rsp+40h+arg_8]
0x14000a291  add     rsp, 40h
0x14000a295  pop     rbp
0x14000a296  retn
```
