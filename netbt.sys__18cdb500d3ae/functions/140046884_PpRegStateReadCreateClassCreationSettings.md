# PpRegStateReadCreateClassCreationSettings

- ea: `0x140046884`
- end: `0x1400469e8`
- name: `PpRegStateReadCreateClassCreationSettings`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140045900`

## callees

- `0x140030d6c`
- `0x140046508`
- `0x14004669c`
- `0x140046884`
- `0x140046d78`
- `0x140046f78`
- `0x14004715c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140046910`
- `ntoskrnl!ZwClose` at `0x1400469c9`
- `ntoskrnl!ZwClose` at `0x140046910`
- `ntoskrnl!ZwClose` at `0x1400469c9`

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
0x140046884  mov     [rsp-8+arg_0], rbx
0x140046889  mov     [rsp-8+arg_8], rdi
0x14004688e  push    rbp
0x14004688f  mov     rbp, rsp
0x140046892  sub     rsp, 40h
0x140046896  mov     rdi, r8
0x140046899  mov     qword ptr [r8], 0
0x1400468a0  mov     qword ptr [r8+8], 0
0x1400468a8  lea     rax, [rbp+Handle]
0x1400468ac  mov     qword ptr [r8+10h], 0
0x1400468b4  lea     r9, [rbp+arg_10]
0x1400468b8  mov     r8d, 1
0x1400468be  mov     [rsp+40h+var_20], rax
0x1400468c3  mov     rbx, rdx
0x1400468c6  mov     [rbp+arg_10], 0
0x1400468cd  mov     [rbp+Handle], 0
0x1400468d5  mov     qword ptr [rbp+DestinationString.Length], 0
0x1400468dd  call    PiRegStateOpenClassKey
0x1400468e2  test    eax, eax
0x1400468e4  js      loc_1400469D7
0x1400468ea  cmp     [rbp+arg_10], 2
0x1400468ee  jnz     short loc_14004694A
0x1400468f0  mov     rcx, [rbp+Handle]
0x1400468f4  lea     r9, [rbp+DestinationString]
0x1400468f8  mov     r8d, 20019h
0x1400468fe  lea     rdx, aProperties; "Properties"
0x140046905  call    CmRegUtilOpenExistingWstrKey
0x14004690a  mov     rcx, [rbp+Handle]; Handle
0x14004690e  mov     ebx, eax
0x140046910  call    cs:__imp_ZwClose
0x140046917  nop     dword ptr [rax+rax+00h]
0x14004691c  test    ebx, ebx
0x14004691e  js      short loc_140046937
0x140046920  mov     rcx, qword ptr [rbp+DestinationString.Length]; KeyHandle
0x140046924  mov     rdx, rdi
0x140046927  call    PiRegStateReadStackCreationSettingsFromKey
0x14004692c  mov     rcx, qword ptr [rbp+DestinationString.Length]
0x140046930  mov     ebx, eax
0x140046932  jmp     loc_1400469C9
0x140046937  cmp     ebx, 0C0000034h
0x14004693d  jnz     loc_1400469D5
0x140046943  xor     ebx, ebx
0x140046945  jmp     loc_1400469D5
0x14004694a  mov     r10, [rbx+30h]
0x14004694e  mov     rdi, [rbp+Handle]
0x140046952  add     r10, 18h
0x140046956  jnz     short loc_14004695F
0x140046958  mov     ebx, 0C000009Ah
0x14004695d  jmp     short loc_1400469C6
0x14004695f  xorps   xmm0, xmm0
0x140046962  lea     rdx, aClass; "Class"
0x140046969  lea     rcx, [rbp+DestinationString]; DestinationString
0x14004696d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140046971  call    WdmlibRtlInitUnicodeStringEx
0x140046976  mov     ebx, eax
0x140046978  test    eax, eax
0x14004697a  js      short loc_1400469C6
0x14004697c  mov     r8, r10
0x14004697f  lea     rdx, [rbp+DestinationString]; ValueName
0x140046983  mov     rcx, rdi; KeyHandle
0x140046986  call    CmRegUtilUcValueSetUcString
0x14004698b  mov     ebx, eax
0x14004698d  test    eax, eax
0x14004698f  js      short loc_1400469C6
0x140046991  lea     r8, [rbp+arg_10]
0x140046995  mov     [rbp+arg_10], 31h ; '1'
0x14004699c  lea     rdx, aNodisplayclass; "NoDisplayClass"
0x1400469a3  mov     rcx, rdi
0x1400469a6  call    CmRegUtilWstrValueSetWstrString
0x1400469ab  mov     ebx, eax
0x1400469ad  test    eax, eax
0x1400469af  js      short loc_1400469C6
0x1400469b1  lea     r8, [rbp+arg_10]
0x1400469b5  mov     rcx, rdi
0x1400469b8  lea     rdx, aNouseclass; "NoUseClass"
0x1400469bf  call    CmRegUtilWstrValueSetWstrString
0x1400469c4  mov     ebx, eax
0x1400469c6  mov     rcx, rdi; Handle
0x1400469c9  call    cs:__imp_ZwClose
0x1400469d0  nop     dword ptr [rax+rax+00h]
0x1400469d5  mov     eax, ebx
0x1400469d7  mov     rbx, [rsp+40h+arg_0]
0x1400469dc  mov     rdi, [rsp+40h+arg_8]
0x1400469e1  add     rsp, 40h
0x1400469e5  pop     rbp
0x1400469e6  retn
```
