# PpRegStateReadCreateClassCreationSettings

- ea: `0x1400102e4`
- end: `0x140010448`
- name: `PpRegStateReadCreateClassCreationSettings`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14000f350`

## callees

- `0x140001208`
- `0x14000ff68`
- `0x1400100fc`
- `0x1400102e4`
- `0x1400106a0`
- `0x1400108a0`
- `0x140010a84`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140010370`
- `ntoskrnl!ZwClose` at `0x140010429`
- `ntoskrnl!ZwClose` at `0x140010370`
- `ntoskrnl!ZwClose` at `0x140010429`

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
0x1400102e4  mov     [rsp-8+arg_0], rbx
0x1400102e9  mov     [rsp-8+arg_8], rdi
0x1400102ee  push    rbp
0x1400102ef  mov     rbp, rsp
0x1400102f2  sub     rsp, 40h
0x1400102f6  mov     rdi, r8
0x1400102f9  mov     qword ptr [r8], 0
0x140010300  mov     qword ptr [r8+8], 0
0x140010308  lea     rax, [rbp+Handle]
0x14001030c  mov     qword ptr [r8+10h], 0
0x140010314  lea     r9, [rbp+arg_10]
0x140010318  mov     r8d, 1
0x14001031e  mov     [rsp+40h+var_20], rax
0x140010323  mov     rbx, rdx
0x140010326  mov     [rbp+arg_10], 0
0x14001032d  mov     [rbp+Handle], 0
0x140010335  mov     qword ptr [rbp+DestinationString.Length], 0
0x14001033d  call    PiRegStateOpenClassKey
0x140010342  test    eax, eax
0x140010344  js      loc_140010437
0x14001034a  cmp     [rbp+arg_10], 2
0x14001034e  jnz     short loc_1400103AA
0x140010350  mov     rcx, [rbp+Handle]
0x140010354  lea     r9, [rbp+DestinationString]
0x140010358  mov     r8d, 20019h
0x14001035e  lea     rdx, aProperties; "Properties"
0x140010365  call    CmRegUtilOpenExistingWstrKey
0x14001036a  mov     rcx, [rbp+Handle]; Handle
0x14001036e  mov     ebx, eax
0x140010370  call    cs:__imp_ZwClose
0x140010377  nop     dword ptr [rax+rax+00h]
0x14001037c  test    ebx, ebx
0x14001037e  js      short loc_140010397
0x140010380  mov     rcx, qword ptr [rbp+DestinationString.Length]; KeyHandle
0x140010384  mov     rdx, rdi
0x140010387  call    PiRegStateReadStackCreationSettingsFromKey
0x14001038c  mov     rcx, qword ptr [rbp+DestinationString.Length]
0x140010390  mov     ebx, eax
0x140010392  jmp     loc_140010429
0x140010397  cmp     ebx, 0C0000034h
0x14001039d  jnz     loc_140010435
0x1400103a3  xor     ebx, ebx
0x1400103a5  jmp     loc_140010435
0x1400103aa  mov     r10, [rbx+30h]
0x1400103ae  mov     rdi, [rbp+Handle]
0x1400103b2  add     r10, 18h
0x1400103b6  jnz     short loc_1400103BF
0x1400103b8  mov     ebx, 0C000009Ah
0x1400103bd  jmp     short loc_140010426
0x1400103bf  xorps   xmm0, xmm0
0x1400103c2  lea     rdx, aClass; "Class"
0x1400103c9  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400103cd  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400103d1  call    WdmlibRtlInitUnicodeStringEx
0x1400103d6  mov     ebx, eax
0x1400103d8  test    eax, eax
0x1400103da  js      short loc_140010426
0x1400103dc  mov     r8, r10
0x1400103df  lea     rdx, [rbp+DestinationString]; ValueName
0x1400103e3  mov     rcx, rdi; KeyHandle
0x1400103e6  call    CmRegUtilUcValueSetUcString
0x1400103eb  mov     ebx, eax
0x1400103ed  test    eax, eax
0x1400103ef  js      short loc_140010426
0x1400103f1  lea     r8, [rbp+arg_10]
0x1400103f5  mov     [rbp+arg_10], 31h ; '1'
0x1400103fc  lea     rdx, aNodisplayclass; "NoDisplayClass"
0x140010403  mov     rcx, rdi
0x140010406  call    CmRegUtilWstrValueSetWstrString
0x14001040b  mov     ebx, eax
0x14001040d  test    eax, eax
0x14001040f  js      short loc_140010426
0x140010411  lea     r8, [rbp+arg_10]
0x140010415  mov     rcx, rdi
0x140010418  lea     rdx, aNouseclass; "NoUseClass"
0x14001041f  call    CmRegUtilWstrValueSetWstrString
0x140010424  mov     ebx, eax
0x140010426  mov     rcx, rdi; Handle
0x140010429  call    cs:__imp_ZwClose
0x140010430  nop     dword ptr [rax+rax+00h]
0x140010435  mov     eax, ebx
0x140010437  mov     rbx, [rsp+40h+arg_0]
0x14001043c  mov     rdi, [rsp+40h+arg_8]
0x140010441  add     rsp, 40h
0x140010445  pop     rbp
0x140010446  retn
```
