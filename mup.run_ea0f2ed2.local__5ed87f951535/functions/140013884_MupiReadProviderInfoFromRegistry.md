# MupiReadProviderInfoFromRegistry

- ea: `0x140013884`
- end: `0x140013ade`
- name: `MupiReadProviderInfoFromRegistry`
- size: `602`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14000f2a0`

## callees

- `0x1400056c0`
- `0x140013884`
- `0x140013c04`
- `0x140013ce8`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x140013960`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140013977`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140013960`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140013977`
- `ntoskrnl!ExAllocatePool2` at `0x1400138e1`
- `ntoskrnl!ExAllocatePool2` at `0x1400138e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400139cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013a76`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013a93`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013ac1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400139cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013a76`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013a93`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013ac1`
- `ntoskrnl!ZwClose` at `0x140013aab`
- `ntoskrnl!ZwClose` at `0x140013aab`
- `ntoskrnl!ZwOpenKey` at `0x1400139b2`
- `ntoskrnl!ZwOpenKey` at `0x1400139b2`

## string_xrefs

- `0x1400138f9`: `\Registry\Machine\System\CurrentControlSet\Services\`
- `0x140013a61`: `TriggerStartCompleteNotification`

## pseudocode

```c
__int64 __fastcall MupiReadProviderInfoFromRegistry(__int64 a1, const WCHAR *a2)
{
  __int64 v4; // rax
  USHORT v5; // r14
  __int64 Pool2; // rax
  void *v7; // rbx
  __int64 RegistryValue; // rax
  unsigned int *v9; // rdi
  unsigned int v10; // eax
  unsigned __int64 v11; // rbx
  __int64 v12; // rax
  void *v13; // r14
  struct _UNICODE_STRING Destination; // [rsp+20h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-38h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp+38h] BYREF

  KeyHandle = 0;
  *(_OWORD *)&ObjectAttributes.ObjectName = 0;
  *(_OWORD *)a1 = 0;
  v4 = -1;
  *(_OWORD *)(&ObjectAttributes.Attributes + 1) = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_OWORD *)&ObjectAttributes.Length = 0;
  Destination = 0;
  do
    ++v4;
  while ( a2[v4] );
  v5 = 2 * v4 + 140;
  Pool2 = ExAllocatePool2(258, (unsigned int)(2 * v4 + 140), 544240973);
  v7 = (void *)Pool2;
  if ( Pool2 )
  {
    Destination.Buffer = (PWSTR)Pool2;
    Destination.MaximumLength = v5;
    Destination.Length = 104;
    *(_OWORD *)Pool2 = *(_OWORD *)L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\";
    *(_OWORD *)(Pool2 + 16) = *(_OWORD *)L"y\\Machine\\System\\CurrentControlSet\\Services\\";
    *(_OWORD *)(Pool2 + 32) = *(_OWORD *)L"e\\System\\CurrentControlSet\\Services\\";
    *(_OWORD *)(Pool2 + 48) = *(_OWORD *)L"\\CurrentControlSet\\Services\\";
    *(_OWORD *)(Pool2 + 64) = *(_OWORD *)L"ControlSet\\Services\\";
    *(_OWORD *)(Pool2 + 80) = *(_OWORD *)L"et\\Services\\";
    *(_QWORD *)(Pool2 + 96) = *(_QWORD *)L"ces\\";
    RtlAppendUnicodeToString(&Destination, a2);
    RtlAppendUnicodeToString(&Destination, L"\\NetworkProvider");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &Destination;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes) >= 0 )
    {
      ExFreePoolWithTag(v7, 0);
      RegistryValue = MupiReadRegistryValue(KeyHandle);
      v9 = (unsigned int *)RegistryValue;
      if ( RegistryValue )
      {
        if ( *(_DWORD *)(RegistryValue + 4) != 1 || (v10 = *(_DWORD *)(RegistryValue + 12), (v10 & 1) != 0) )
        {
          ExFreePoolWithTag(v9, 0);
        }
        else
        {
          v11 = v10;
          memmove(v9, (char *)v9 + v9[2], v10);
          *((_WORD *)v9 + (v11 >> 1)) = 0;
          v12 = MupiReadRegistryValue(KeyHandle);
          v13 = (void *)v12;
          if ( v12
            && (*(_DWORD *)(v12 + 4) != 7
             || !(unsigned __int8)MupiReadRegistryWnfStateName(KeyHandle, L"TriggerStartNotification", a1 + 16)
             || !(unsigned __int8)MupiReadRegistryWnfStateName(KeyHandle, L"TriggerStartCompleteNotification", a1 + 24)) )
          {
            ExFreePoolWithTag(v13, 0);
            v13 = 0;
          }
          *(_QWORD *)a1 = v9;
          *(_QWORD *)(a1 + 8) = v13;
        }
      }
      v7 = 0;
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  return a1;
}

```

## disassembly

```asm
0x140013884  push    rbp
0x140013886  push    rbx
0x140013887  push    rsi
0x140013888  push    rdi
0x140013889  push    r14
0x14001388b  push    r15
0x14001388d  mov     rbp, rsp
0x140013890  sub     rsp, 68h
0x140013894  xorps   xmm0, xmm0
0x140013897  xor     r15d, r15d
0x14001389a  xor     eax, eax
0x14001389c  mov     [rbp+KeyHandle], r15
0x1400138a0  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400138a4  mov     rdi, rdx
0x1400138a7  mov     rsi, rcx
0x1400138aa  movups  xmmword ptr [rcx], xmm0
0x1400138ad  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400138b1  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1400138b5  movups  xmmword ptr [rcx+10h], xmm0
0x1400138b9  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400138bd  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x1400138c1  inc     rax
0x1400138c4  cmp     [rdx+rax*2], r15w
0x1400138c9  jnz     short loc_1400138C1
0x1400138cb  lea     r14d, ds:8Ch[rax*2]
0x1400138d3  mov     ecx, 102h
0x1400138d8  mov     edx, r14d
0x1400138db  mov     r8d, 2070754Dh
0x1400138e1  call    cs:__imp_ExAllocatePool2
0x1400138e8  nop     dword ptr [rax+rax+00h]
0x1400138ed  mov     rbx, rax
0x1400138f0  test    rax, rax
0x1400138f3  jz      loc_140013AA2
0x1400138f9  movaps  xmm0, xmmword ptr cs:aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140013900  lea     rcx, [rbp+Destination]; Destination
0x140013904  mov     [rbp+Destination.Buffer], rax
0x140013908  mov     rdx, rdi; Source
0x14001390b  mov     [rbp+Destination.MaximumLength], r14w
0x140013910  mov     eax, 68h ; 'h'
0x140013915  mov     [rbp+Destination.Length], ax
0x140013919  movups  xmmword ptr [rbx], xmm0
0x14001391c  movaps  xmm1, xmmword ptr cs:aRegistryMachin+10h; "y\\Machine\\System\\CurrentControlSet\\"...
0x140013923  movups  xmmword ptr [rbx+10h], xmm1
0x140013927  movaps  xmm0, xmmword ptr cs:aRegistryMachin+20h; "e\\System\\CurrentControlSet\\Services"...
0x14001392e  movups  xmmword ptr [rbx+20h], xmm0
0x140013932  movaps  xmm1, xmmword ptr cs:aRegistryMachin+30h; "\\CurrentControlSet\\Services\\"
0x140013939  movups  xmmword ptr [rbx+30h], xmm1
0x14001393d  movaps  xmm0, xmmword ptr cs:aRegistryMachin+40h; "ControlSet\\Services\\"
0x140013944  movups  xmmword ptr [rbx+40h], xmm0
0x140013948  movaps  xmm1, xmmword ptr cs:aRegistryMachin+50h; "et\\Services\\"
0x14001394f  movups  xmmword ptr [rbx+50h], xmm1
0x140013953  movsd   xmm0, qword ptr cs:aRegistryMachin+60h; "ces\\"
0x14001395b  movsd   qword ptr [rbx+60h], xmm0
0x140013960  call    cs:__imp_RtlAppendUnicodeToString
0x140013967  nop     dword ptr [rax+rax+00h]
0x14001396c  lea     rdx, Source; "\\NetworkProvider"
0x140013973  lea     rcx, [rbp+Destination]; Destination
0x140013977  call    cs:__imp_RtlAppendUnicodeToString
0x14001397e  nop     dword ptr [rax+rax+00h]
0x140013983  lea     rax, [rbp+Destination]
0x140013987  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14001398e  xorps   xmm0, xmm0
0x140013991  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140013995  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140013999  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x14001399d  mov     edx, 1; DesiredAccess
0x1400139a2  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400139a9  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400139ad  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400139b2  call    cs:__imp_ZwOpenKey
0x1400139b9  nop     dword ptr [rax+rax+00h]
0x1400139be  test    eax, eax
0x1400139c0  js      loc_140013AA2
0x1400139c6  xor     edx, edx; Tag
0x1400139c8  mov     rcx, rbx; P
0x1400139cb  call    cs:__imp_ExFreePoolWithTag
0x1400139d2  nop     dword ptr [rax+rax+00h]
0x1400139d7  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400139db  lea     rdx, aDevicename; "DeviceName"
0x1400139e2  call    MupiReadRegistryValue
0x1400139e7  mov     rdi, rax
0x1400139ea  test    rax, rax
0x1400139ed  jz      loc_140013A9F
0x1400139f3  cmp     dword ptr [rax+4], 1
0x1400139f7  jnz     loc_140013A8E
0x1400139fd  mov     eax, [rax+0Ch]
0x140013a00  test    al, 1
0x140013a02  jnz     loc_140013A8E
0x140013a08  mov     edx, [rdi+8]
0x140013a0b  mov     r8d, eax; Size
0x140013a0e  add     rdx, rdi; Src
0x140013a11  mov     rcx, rdi; void *
0x140013a14  mov     ebx, eax
0x140013a16  call    memmove
0x140013a1b  shr     rbx, 1
0x140013a1e  lea     rdx, aTriggerstartpr; "TriggerStartPrefix"
0x140013a25  mov     [rdi+rbx*2], r15w
0x140013a2a  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140013a2e  call    MupiReadRegistryValue
0x140013a33  mov     r14, rax
0x140013a36  test    rax, rax
0x140013a39  jz      short loc_140013A85
0x140013a3b  cmp     dword ptr [rax+4], 7
0x140013a3f  jnz     short loc_140013A71
0x140013a41  mov     rcx, [rbp+KeyHandle]
0x140013a45  lea     r8, [rsi+10h]
0x140013a49  lea     rdx, aTriggerstartno; "TriggerStartNotification"
0x140013a50  call    MupiReadRegistryWnfStateName
0x140013a55  test    al, al
0x140013a57  jz      short loc_140013A71
0x140013a59  mov     rcx, [rbp+KeyHandle]
0x140013a5d  lea     r8, [rsi+18h]
0x140013a61  lea     rdx, aTriggerstartco; "TriggerStartCompleteNotification"
0x140013a68  call    MupiReadRegistryWnfStateName
0x140013a6d  test    al, al
0x140013a6f  jnz     short loc_140013A85
0x140013a71  xor     edx, edx; Tag
0x140013a73  mov     rcx, r14; P
0x140013a76  call    cs:__imp_ExFreePoolWithTag
0x140013a7d  nop     dword ptr [rax+rax+00h]
0x140013a82  mov     r14, r15
0x140013a85  mov     [rsi], rdi
0x140013a88  mov     [rsi+8], r14
0x140013a8c  jmp     short loc_140013A9F
0x140013a8e  xor     edx, edx; Tag
0x140013a90  mov     rcx, rdi; P
0x140013a93  call    cs:__imp_ExFreePoolWithTag
0x140013a9a  nop     dword ptr [rax+rax+00h]
0x140013a9f  mov     rbx, r15
0x140013aa2  mov     rcx, [rbp+KeyHandle]; Handle
0x140013aa6  test    rcx, rcx
0x140013aa9  jz      short loc_140013AB7
0x140013aab  call    cs:__imp_ZwClose
0x140013ab2  nop     dword ptr [rax+rax+00h]
0x140013ab7  test    rbx, rbx
0x140013aba  jz      short loc_140013ACD
0x140013abc  xor     edx, edx; Tag
0x140013abe  mov     rcx, rbx; P
0x140013ac1  call    cs:__imp_ExFreePoolWithTag
0x140013ac8  nop     dword ptr [rax+rax+00h]
0x140013acd  mov     rax, rsi
0x140013ad0  add     rsp, 68h
0x140013ad4  pop     r15
0x140013ad6  pop     r14
0x140013ad8  pop     rdi
0x140013ad9  pop     rsi
0x140013ada  pop     rbx
0x140013adb  pop     rbp
0x140013adc  retn
```
