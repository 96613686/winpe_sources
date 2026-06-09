# FltpQueryCountersEnabled

- ea: `0x180019be0`
- end: `0x180019e70`
- name: `FltpQueryCountersEnabled`
- size: `656`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180069c90`

## callees

- `0x180009f20`
- `0x180019be0`
- `0x1800247a0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180019de2`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002639c`
- `ntoskrnl!ExFreePoolWithTag` at `0x180019de2`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002639c`
- `ntoskrnl!ExAllocatePool2` at `0x180019cb9`
- `ntoskrnl!ExAllocatePool2` at `0x1800263bb`
- `ntoskrnl!ExAllocatePool2` at `0x180019cb9`
- `ntoskrnl!ExAllocatePool2` at `0x1800263bb`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180019cfd`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180019cfd`
- `ntoskrnl!RtlInitUnicodeString` at `0x180019d74`
- `ntoskrnl!RtlInitUnicodeString` at `0x180019d74`
- `ntoskrnl!ZwClose` at `0x180019e10`
- `ntoskrnl!ZwClose` at `0x180019e10`
- `ntoskrnl!ZwOpenKey` at `0x180019d40`
- `ntoskrnl!ZwOpenKey` at `0x180019d40`
- `ntoskrnl!ZwQueryValueKey` at `0x180019da7`
- `ntoskrnl!ZwQueryValueKey` at `0x180019da7`

## string_xrefs

- `0x180019c44`: `\Registry\Machine\System\CurrentControlSet\Services\FltMgr\OneSettings\`

## pseudocode

```c
__int64 FltpQueryCountersEnabled()
{
  ULONG Length; // r14d
  int v1; // esi
  _DWORD *Pool2; // rbx
  NTSTATUS v3; // edi
  __int64 result; // rax
  ULONG ResultLength[2]; // [rsp+38h] [rbp-D0h] BYREF
  void *Destination; // [rsp+40h] [rbp-C8h] BYREF
  UNICODE_STRING Destination_8; // [rsp+48h] [rbp-C0h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes_8; // [rsp+58h] [rbp-B0h] BYREF
  UNICODE_STRING DestinationString; // [rsp+88h] [rbp-80h] BYREF
  WCHAR Source[72]; // [rsp+98h] [rbp-70h] BYREF
  char v11; // [rsp+128h] [rbp+20h] BYREF

  Length = 80;
  DestinationString = 0;
  memset(&ObjectAttributes_8, 0, 44);
  LOBYTE(v1) = 0;
  wcscpy(Source, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\FltMgr\\OneSettings\\");
  Destination_8 = 0;
  Destination = 0;
  ResultLength[0] = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(256, 80, 1920224582);
  if ( Pool2 )
  {
    *(_QWORD *)&Destination_8.Length = 20971520;
    Destination_8.Buffer = (wchar_t *)&v11;
    RtlAppendUnicodeToString(&Destination_8, Source);
    ObjectAttributes_8.Length = 48;
    ObjectAttributes_8.ObjectName = &Destination_8;
    ObjectAttributes_8.RootDirectory = 0;
    ObjectAttributes_8.Attributes = 576;
    *(_OWORD *)&ObjectAttributes_8.SecurityDescriptor = 0;
    v3 = ZwOpenKey(&Destination, 0x20019u, &ObjectAttributes_8);
    if ( (int)FltpDbgStatus((unsigned int)v3, "minkernel\\fs\\filtermgr\\filter\\fltioperf.c", 904, 0) >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"CountersEnabled");
      while ( 1 )
      {
        v3 = ZwQueryValueKey(Destination, &DestinationString, KeyValuePartialInformation, Pool2, Length, ResultLength);
        if ( (int)FltpDbgStatus((unsigned int)v3, "minkernel\\fs\\filtermgr\\filter\\fltioperf.c", 925, 0) >= 0 )
          break;
        if ( v3 != -1073741789 && v3 != -2147483643 )
          goto LABEL_7;
        ExFreePoolWithTag(Pool2, 0x72744D46u);
        Length = ResultLength[0];
        Pool2 = (_DWORD *)ExAllocatePool2(256, ResultLength[0], 1920224582);
        if ( !Pool2 )
        {
          v3 = -1073741670;
          goto LABEL_8;
        }
      }
      if ( Pool2[1] == 4 )
        v1 = Pool2[3];
    }
LABEL_7:
    ExFreePoolWithTag(Pool2, 0x72744D46u);
  }
  else
  {
    v3 = -1073741670;
  }
LABEL_8:
  if ( Destination )
    ZwClose(Destination);
  result = 0;
  if ( v3 >= 0 )
    return (unsigned __int8)v1;
  return result;
}

```

## disassembly

```asm
0x180019be0  mov     r11, rsp
0x180019be3  mov     [r11+20h], rsi
0x180019be7  push    rbp
0x180019be8  push    rdi
0x180019be9  push    r15
0x180019beb  lea     rbp, [r11-188h]
0x180019bf2  sub     rsp, 270h
0x180019bf9  mov     rax, cs:__security_cookie
0x180019c00  xor     rax, rsp
0x180019c03  mov     [rbp+180h+var_20], rax
0x180019c0a  xorps   xmm0, xmm0
0x180019c0d  mov     [r11+8], rbx
0x180019c11  movups  xmmword ptr [rsp+280h+ObjectAttributes+18h], xmm0
0x180019c16  xor     r15d, r15d
0x180019c19  mov     [r11+18h], r14
0x180019c1d  movups  xmmword ptr [rsp+280h+ObjectAttributes+24h], xmm0
0x180019c22  mov     r14d, 50h ; 'P'
0x180019c28  xor     eax, eax
0x180019c2a  movups  xmmword ptr [rbp+180h+DestinationString.Length], xmm0
0x180019c2e  mov     r8d, 72744D46h
0x180019c34  mov     edx, r14d
0x180019c37  movups  xmmword ptr [rsp+280h+ObjectAttributes+8], xmm0
0x180019c3c  mov     ecx, 100h
0x180019c41  mov     esi, r15d
0x180019c44  movaps  xmm0, xmmword ptr cs:aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x180019c4b  xorps   xmm1, xmm1
0x180019c4e  movaps  xmmword ptr [rbp+180h+Source], xmm0
0x180019c52  movaps  xmm0, xmmword ptr cs:aRegistryMachin_0+20h; "e\\System\\CurrentControlSet\\Services"...
0x180019c59  movups  xmmword ptr [rsp+280h+Destination.Buffer], xmm1
0x180019c5e  mov     qword ptr [rsp+280h+Destination.Length], r15
0x180019c63  movaps  xmm1, xmmword ptr cs:aRegistryMachin_0+10h; "y\\Machine\\System\\CurrentControlSet\\"...
0x180019c6a  movaps  [rbp+180h+var_1D0], xmm0
0x180019c6e  movaps  xmm0, xmmword ptr cs:aRegistryMachin_0+40h; "ControlSet\\Services\\FltMgr\\OneSettin"...
0x180019c75  movaps  [rbp+180h+var_1E0], xmm1
0x180019c79  movaps  xmm1, xmmword ptr cs:aRegistryMachin_0+30h; "\\CurrentControlSet\\Services\\FltMgr\\"...
0x180019c80  movaps  [rbp+180h+var_1B0], xmm0
0x180019c84  movaps  xmm0, xmmword ptr cs:aRegistryMachin_0+60h; "ces\\FltMgr\\OneSettings\\"
0x180019c8b  movaps  [rbp+180h+var_1C0], xmm1
0x180019c8f  movaps  xmm1, xmmword ptr cs:aRegistryMachin_0+50h; "et\\Services\\FltMgr\\OneSettings\\"
0x180019c96  movaps  [rbp+180h+var_190], xmm0
0x180019c9a  movaps  xmm0, xmmword ptr cs:aRegistryMachin_0+80h; "ttings\\"
0x180019ca1  movaps  [rbp+180h+var_1A0], xmm1
0x180019ca5  movaps  xmm1, xmmword ptr cs:aRegistryMachin_0+70h; "gr\\OneSettings\\"
0x180019cac  movaps  [rbp+180h+var_170], xmm0
0x180019cb0  mov     [rsp+280h+var_250], r15d
0x180019cb5  movaps  [rbp+180h+var_180], xmm1
0x180019cb9  call    cs:__imp_ExAllocatePool2
0x180019cc0  nop     dword ptr [rax+rax+00h]
0x180019cc5  mov     rbx, rax
0x180019cc8  test    rax, rax
0x180019ccb  jz      loc_180019E4C
0x180019cd1  xorps   xmm0, xmm0
0x180019cd4  mov     [rsp+280h+arg_8], r12
0x180019cdc  movups  xmmword ptr [rsp+280h+Destination.Buffer], xmm0
0x180019ce1  mov     eax, 140h
0x180019ce6  lea     rdx, [rbp+180h+Source]; Source
0x180019cea  mov     word ptr [rsp+280h+Destination.Buffer+2], ax
0x180019cef  lea     rcx, [rsp+280h+Destination.Buffer]; Destination
0x180019cf4  lea     rax, [rbp+180h+var_160]
0x180019cf8  mov     qword ptr [rsp+280h+ObjectAttributes], rax
0x180019cfd  call    cs:__imp_RtlAppendUnicodeToString
0x180019d04  nop     dword ptr [rax+rax+00h]
0x180019d09  lea     rax, [rsp+280h+Destination.Buffer]
0x180019d0e  mov     dword ptr [rsp+280h+ObjectAttributes+8], 30h ; '0'
0x180019d16  xorps   xmm0, xmm0
0x180019d19  mov     qword ptr [rsp+280h+ObjectAttributes+18h], rax
0x180019d1e  lea     r8, [rsp+280h+ObjectAttributes+8]; ObjectAttributes
0x180019d23  mov     qword ptr [rsp+280h+ObjectAttributes+10h], r15
0x180019d28  mov     edx, 20019h; DesiredAccess
0x180019d2d  mov     dword ptr [rsp+280h+ObjectAttributes+20h], 240h
0x180019d35  lea     rcx, [rsp+280h+Destination]; KeyHandle
0x180019d3a  movdqu  xmmword ptr [rsp+280h+ObjectAttributes+28h], xmm0
0x180019d40  call    cs:__imp_ZwOpenKey
0x180019d47  nop     dword ptr [rax+rax+00h]
0x180019d4c  mov     r8d, 388h
0x180019d52  lea     rdx, aMinkernelFsFil_8; "minkernel\\fs\\filtermgr\\filter\\fltio"...
0x180019d59  mov     ecx, eax
0x180019d5b  xor     r9d, r9d
0x180019d5e  mov     edi, eax
0x180019d60  call    FltpDbgStatus
0x180019d65  test    eax, eax
0x180019d67  js      short loc_180019DDA
0x180019d69  lea     rdx, aCountersenable; "CountersEnabled"
0x180019d70  lea     rcx, [rbp+180h+DestinationString]; DestinationString
0x180019d74  call    cs:__imp_RtlInitUnicodeString
0x180019d7b  nop     dword ptr [rax+rax+00h]
0x180019d80  mov     r12d, 39Dh
0x180019d86  mov     rcx, qword ptr [rsp+280h+Destination.Length]; KeyHandle
0x180019d8b  lea     rax, [rsp+280h+var_250]
0x180019d90  mov     [rsp+280h+ResultLength], rax; ResultLength
0x180019d95  lea     rdx, [rbp+180h+DestinationString]; ValueName
0x180019d99  mov     r9, rbx; KeyValueInformation
0x180019d9c  mov     [rsp+280h+Length], r14d; Length
0x180019da1  mov     r8d, 2; KeyValueInformationClass
0x180019da7  call    cs:__imp_ZwQueryValueKey
0x180019dae  nop     dword ptr [rax+rax+00h]
0x180019db3  xor     r9d, r9d
0x180019db6  lea     rdx, aMinkernelFsFil_8; "minkernel\\fs\\filtermgr\\filter\\fltio"...
0x180019dbd  mov     ecx, eax
0x180019dbf  mov     r8d, r12d
0x180019dc2  mov     edi, eax
0x180019dc4  call    FltpDbgStatus
0x180019dc9  test    eax, eax
0x180019dcb  js      loc_180019E53
0x180019dd1  cmp     dword ptr [rbx+4], 4
0x180019dd5  jnz     short loc_180019DDA
0x180019dd7  mov     esi, [rbx+0Ch]
0x180019dda  mov     edx, 72744D46h; Tag
0x180019ddf  mov     rcx, rbx; P
0x180019de2  call    cs:__imp_ExFreePoolWithTag
0x180019de9  nop     dword ptr [rax+rax+00h]
0x180019dee  mov     r12, [rsp+280h+arg_8]
0x180019df6  mov     rcx, qword ptr [rsp+280h+Destination.Length]; Handle
0x180019dfb  mov     r14, [rsp+280h+arg_10]
0x180019e03  mov     rbx, [rsp+280h+arg_0]
0x180019e0b  test    rcx, rcx
0x180019e0e  jz      short loc_180019E1C
0x180019e10  call    cs:__imp_ZwClose
0x180019e17  nop     dword ptr [rax+rax+00h]
0x180019e1c  test    edi, edi
0x180019e1e  movzx   ecx, sil
0x180019e22  mov     eax, r15d
0x180019e25  cmovns  eax, ecx
0x180019e28  mov     rcx, [rbp+180h+var_20]
0x180019e2f  xor     rcx, rsp; StackCookie
0x180019e32  call    __security_check_cookie
0x180019e37  mov     rsi, [rsp+280h+arg_18]
0x180019e3f  add     rsp, 270h
0x180019e46  pop     r15
0x180019e48  pop     rdi
0x180019e49  pop     rbp
0x180019e4a  retn
0x180019e4c  mov     edi, 0C000009Ah
0x180019e51  jmp     short loc_180019DF6
0x180019e53  cmp     edi, 0C0000023h
0x180019e59  jz      loc_180026394
0x180019e5f  cmp     edi, 80000005h
0x180019e65  jnz     loc_180019DDA
0x180019e6b  jmp     loc_180026394
0x180026394  mov     edx, 72744D46h; Tag
0x180026399  mov     rcx, rbx; P
0x18002639c  call    cs:__imp_ExFreePoolWithTag
0x1800263a3  nop     dword ptr [rax+rax+00h]
0x1800263a8  mov     r14d, [rsp+280h+var_250]
0x1800263ad  mov     ecx, 100h
0x1800263b2  mov     edx, r14d
0x1800263b5  mov     r8d, 72744D46h
0x1800263bb  call    cs:__imp_ExAllocatePool2
0x1800263c2  nop     dword ptr [rax+rax+00h]
0x1800263c7  mov     rbx, rax
0x1800263ca  test    rax, rax
0x1800263cd  jnz     loc_180019D86
0x1800263d3  mov     edi, 0C000009Ah
0x1800263d8  jmp     loc_180019DEE
```
