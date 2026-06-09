# CreateJobObjectW

- ea: `0x18003ad50`
- end: `0x18003adf1`
- name: `CreateJobObjectW`
- size: `161`
- prototype: `HANDLE __stdcall(LPSECURITY_ATTRIBUTES lpJobAttributes, LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180069310`

## callees

- `0x18000f920`
- `0x18003ad50`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18003adba`
- `ntdll!RtlSetLastWin32Error` at `0x18003adba`
- `ntdll!NtCreateJobObject` at `0x18003ada7`
- `ntdll!NtCreateJobObject` at `0x18003ada7`
- `ntdll!RtlInitUnicodeString` at `0x18003adde`
- `ntdll!RtlInitUnicodeString` at `0x18003adde`
- `KERNELBASE!BaseFormatObjectAttributes` at `0x18003ad90`
- `KERNELBASE!BaseFormatObjectAttributes` at `0x18003ad90`

## pseudocode

```c
HANDLE __stdcall CreateJobObjectW(LPSECURITY_ATTRIBUTES lpJobAttributes, LPCWSTR lpName)
{
  struct _UNICODE_STRING *p_DestinationString; // r8
  NTSTATUS v4; // eax
  ULONG v5; // ecx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  _OWORD v8[3]; // [rsp+30h] [rbp-30h] BYREF
  POBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp+18h] BYREF
  void *JobHandle; // [rsp+80h] [rbp+20h] BYREF

  ObjectAttributes = 0;
  JobHandle = 0;
  memset(v8, 0, 44);
  DestinationString = 0;
  if ( lpName )
  {
    RtlInitUnicodeString(&DestinationString, lpName);
    p_DestinationString = &DestinationString;
  }
  else
  {
    p_DestinationString = 0;
  }
  v4 = ((__int64 (__fastcall *)(_OWORD *, LPSECURITY_ATTRIBUTES, struct _UNICODE_STRING *, POBJECT_ATTRIBUTES *, _QWORD, PWSTR))BaseFormatObjectAttributes)(
         v8,
         lpJobAttributes,
         p_DestinationString,
         &ObjectAttributes,
         *(_QWORD *)&DestinationString.Length,
         DestinationString.Buffer);
  if ( v4 < 0 || (v4 = NtCreateJobObject(&JobHandle, 0x1F003Fu, ObjectAttributes), v4 < 0) )
  {
    BaseSetLastNTError((unsigned int)v4);
    return 0;
  }
  else
  {
    if ( v4 == 0x40000000 )
      v5 = 183;
    else
      v5 = 0;
    RtlSetLastWin32Error(v5);
    return JobHandle;
  }
}

```

## disassembly

```asm
0x18003ad50  mov     [rsp-8+arg_0], rbx
0x18003ad55  push    rbp
0x18003ad56  mov     rbp, rsp
0x18003ad59  sub     rsp, 60h
0x18003ad5d  xorps   xmm0, xmm0
0x18003ad60  xor     eax, eax
0x18003ad62  mov     [rbp+ObjectAttributes], rax
0x18003ad66  mov     rbx, rcx
0x18003ad69  mov     [rbp+JobHandle], rax
0x18003ad6d  movups  xmmword ptr [rbp+var_20], xmm0
0x18003ad71  movups  xmmword ptr [rbp+var_20+0Ch], xmm0
0x18003ad75  movups  [rbp+var_30], xmm0
0x18003ad79  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18003ad7d  test    rdx, rdx
0x18003ad80  jnz     short loc_18003ADDA
0x18003ad82  xor     r8d, r8d
0x18003ad85  lea     r9, [rbp+ObjectAttributes]
0x18003ad89  mov     rdx, rbx
0x18003ad8c  lea     rcx, [rbp+var_30]
0x18003ad90  call    cs:__imp_BaseFormatObjectAttributes
0x18003ad96  test    eax, eax
0x18003ad98  js      short loc_18003ADCF
0x18003ad9a  mov     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18003ad9e  lea     rcx, [rbp+JobHandle]; JobHandle
0x18003ada2  mov     edx, 1F003Fh; DesiredAccess
0x18003ada7  call    cs:__imp_NtCreateJobObject
0x18003adad  test    eax, eax
0x18003adaf  js      short loc_18003ADCF
0x18003adb1  cmp     eax, 40000000h
0x18003adb6  jz      short loc_18003ADEA
0x18003adb8  xor     ecx, ecx; LastError
0x18003adba  call    cs:__imp_RtlSetLastWin32Error
0x18003adc0  mov     rax, [rbp+JobHandle]
0x18003adc4  mov     rbx, [rsp+60h+arg_0]
0x18003adc9  add     rsp, 60h
0x18003adcd  pop     rbp
0x18003adce  retn
0x18003adcf  mov     ecx, eax
0x18003add1  call    BaseSetLastNTError
0x18003add6  xor     eax, eax
0x18003add8  jmp     short loc_18003ADC4
0x18003adda  lea     rcx, [rbp+DestinationString]; DestinationString
0x18003adde  call    cs:__imp_RtlInitUnicodeString
0x18003ade4  lea     r8, [rbp+DestinationString]
0x18003ade8  jmp     short loc_18003AD85
0x18003adea  mov     ecx, 0B7h
0x18003adef  jmp     short loc_18003ADBA
```
