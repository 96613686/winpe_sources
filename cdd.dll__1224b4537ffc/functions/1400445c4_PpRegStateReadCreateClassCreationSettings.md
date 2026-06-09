# PpRegStateReadCreateClassCreationSettings

- ea: `0x1400445c4`
- end: `0x140044728`
- name: `PpRegStateReadCreateClassCreationSettings`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140043640`

## callees

- `0x14003707c`
- `0x140044248`
- `0x1400443dc`
- `0x1400445c4`
- `0x140044ab8`
- `0x140044cb8`
- `0x140044e9c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140044650`
- `ntoskrnl!ZwClose` at `0x140044709`
- `ntoskrnl!ZwClose` at `0x140044650`
- `ntoskrnl!ZwClose` at `0x140044709`

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
0x1400445c4  mov     [rsp-8+arg_0], rbx
0x1400445c9  mov     [rsp-8+arg_8], rdi
0x1400445ce  push    rbp
0x1400445cf  mov     rbp, rsp
0x1400445d2  sub     rsp, 40h
0x1400445d6  mov     rdi, r8
0x1400445d9  mov     qword ptr [r8], 0
0x1400445e0  mov     qword ptr [r8+8], 0
0x1400445e8  lea     rax, [rbp+Handle]
0x1400445ec  mov     qword ptr [r8+10h], 0
0x1400445f4  lea     r9, [rbp+arg_10]
0x1400445f8  mov     r8d, 1
0x1400445fe  mov     [rsp+40h+var_20], rax
0x140044603  mov     rbx, rdx
0x140044606  mov     [rbp+arg_10], 0
0x14004460d  mov     [rbp+Handle], 0
0x140044615  mov     qword ptr [rbp+DestinationString.Length], 0
0x14004461d  call    PiRegStateOpenClassKey
0x140044622  test    eax, eax
0x140044624  js      loc_140044717
0x14004462a  cmp     [rbp+arg_10], 2
0x14004462e  jnz     short loc_14004468A
0x140044630  mov     rcx, [rbp+Handle]
0x140044634  lea     r9, [rbp+DestinationString]
0x140044638  mov     r8d, 20019h
0x14004463e  lea     rdx, aProperties; "Properties"
0x140044645  call    CmRegUtilOpenExistingWstrKey
0x14004464a  mov     rcx, [rbp+Handle]; Handle
0x14004464e  mov     ebx, eax
0x140044650  call    cs:__imp_ZwClose
0x140044657  nop     dword ptr [rax+rax+00h]
0x14004465c  test    ebx, ebx
0x14004465e  js      short loc_140044677
0x140044660  mov     rcx, qword ptr [rbp+DestinationString.Length]; KeyHandle
0x140044664  mov     rdx, rdi
0x140044667  call    PiRegStateReadStackCreationSettingsFromKey
0x14004466c  mov     rcx, qword ptr [rbp+DestinationString.Length]
0x140044670  mov     ebx, eax
0x140044672  jmp     loc_140044709
0x140044677  cmp     ebx, 0C0000034h
0x14004467d  jnz     loc_140044715
0x140044683  xor     ebx, ebx
0x140044685  jmp     loc_140044715
0x14004468a  mov     r10, [rbx+30h]
0x14004468e  mov     rdi, [rbp+Handle]
0x140044692  add     r10, 18h
0x140044696  jnz     short loc_14004469F
0x140044698  mov     ebx, 0C000009Ah
0x14004469d  jmp     short loc_140044706
0x14004469f  xorps   xmm0, xmm0
0x1400446a2  lea     rdx, aClass; "Class"
0x1400446a9  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400446ad  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400446b1  call    WdmlibRtlInitUnicodeStringEx
0x1400446b6  mov     ebx, eax
0x1400446b8  test    eax, eax
0x1400446ba  js      short loc_140044706
0x1400446bc  mov     r8, r10
0x1400446bf  lea     rdx, [rbp+DestinationString]; ValueName
0x1400446c3  mov     rcx, rdi; KeyHandle
0x1400446c6  call    CmRegUtilUcValueSetUcString
0x1400446cb  mov     ebx, eax
0x1400446cd  test    eax, eax
0x1400446cf  js      short loc_140044706
0x1400446d1  lea     r8, [rbp+arg_10]
0x1400446d5  mov     [rbp+arg_10], 31h ; '1'
0x1400446dc  lea     rdx, aNodisplayclass; "NoDisplayClass"
0x1400446e3  mov     rcx, rdi
0x1400446e6  call    CmRegUtilWstrValueSetWstrString
0x1400446eb  mov     ebx, eax
0x1400446ed  test    eax, eax
0x1400446ef  js      short loc_140044706
0x1400446f1  lea     r8, [rbp+arg_10]
0x1400446f5  mov     rcx, rdi
0x1400446f8  lea     rdx, aNouseclass; "NoUseClass"
0x1400446ff  call    CmRegUtilWstrValueSetWstrString
0x140044704  mov     ebx, eax
0x140044706  mov     rcx, rdi; Handle
0x140044709  call    cs:__imp_ZwClose
0x140044710  nop     dword ptr [rax+rax+00h]
0x140044715  mov     eax, ebx
0x140044717  mov     rbx, [rsp+40h+arg_0]
0x14004471c  mov     rdi, [rsp+40h+arg_8]
0x140044721  add     rsp, 40h
0x140044725  pop     rbp
0x140044726  retn
```
