# MupiReadProviderInfoFromRegistry

- ea: `0x1400138d4`
- end: `0x140013b2e`
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
- `0x1400138d4`
- `0x140013c54`
- `0x140013d38`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400139b0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400139c7`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400139b0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400139c7`
- `ntoskrnl!ExAllocatePool2` at `0x140013931`
- `ntoskrnl!ExAllocatePool2` at `0x140013931`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013a1b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013ac6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013ae3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013b11`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013a1b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013ac6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013ae3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013b11`
- `ntoskrnl!ZwClose` at `0x140013afb`
- `ntoskrnl!ZwClose` at `0x140013afb`
- `ntoskrnl!ZwOpenKey` at `0x140013a02`
- `ntoskrnl!ZwOpenKey` at `0x140013a02`

## string_xrefs

- `0x140013949`: `\Registry\Machine\System\CurrentControlSet\Services\`
- `0x140013ab1`: `TriggerStartCompleteNotification`

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
0x1400138d4  push    rbp
0x1400138d6  push    rbx
0x1400138d7  push    rsi
0x1400138d8  push    rdi
0x1400138d9  push    r14
0x1400138db  push    r15
0x1400138dd  mov     rbp, rsp
0x1400138e0  sub     rsp, 68h
0x1400138e4  xorps   xmm0, xmm0
0x1400138e7  xor     r15d, r15d
0x1400138ea  xor     eax, eax
0x1400138ec  mov     [rbp+KeyHandle], r15
0x1400138f0  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400138f4  mov     rdi, rdx
0x1400138f7  mov     rsi, rcx
0x1400138fa  movups  xmmword ptr [rcx], xmm0
0x1400138fd  or      rax, 0FFFFFFFFFFFFFFFFh
0x140013901  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140013905  movups  xmmword ptr [rcx+10h], xmm0
0x140013909  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14001390d  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x140013911  inc     rax
0x140013914  cmp     [rdx+rax*2], r15w
0x140013919  jnz     short loc_140013911
0x14001391b  lea     r14d, ds:8Ch[rax*2]
0x140013923  mov     ecx, 102h
0x140013928  mov     edx, r14d
0x14001392b  mov     r8d, 2070754Dh
0x140013931  call    cs:__imp_ExAllocatePool2
0x140013938  nop     dword ptr [rax+rax+00h]
0x14001393d  mov     rbx, rax
0x140013940  test    rax, rax
0x140013943  jz      loc_140013AF2
0x140013949  movaps  xmm0, xmmword ptr cs:aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140013950  lea     rcx, [rbp+Destination]; Destination
0x140013954  mov     [rbp+Destination.Buffer], rax
0x140013958  mov     rdx, rdi; Source
0x14001395b  mov     [rbp+Destination.MaximumLength], r14w
0x140013960  mov     eax, 68h ; 'h'
0x140013965  mov     [rbp+Destination.Length], ax
0x140013969  movups  xmmword ptr [rbx], xmm0
0x14001396c  movaps  xmm1, xmmword ptr cs:aRegistryMachin+10h; "y\\Machine\\System\\CurrentControlSet\\"...
0x140013973  movups  xmmword ptr [rbx+10h], xmm1
0x140013977  movaps  xmm0, xmmword ptr cs:aRegistryMachin+20h; "e\\System\\CurrentControlSet\\Services"...
0x14001397e  movups  xmmword ptr [rbx+20h], xmm0
0x140013982  movaps  xmm1, xmmword ptr cs:aRegistryMachin+30h; "\\CurrentControlSet\\Services\\"
0x140013989  movups  xmmword ptr [rbx+30h], xmm1
0x14001398d  movaps  xmm0, xmmword ptr cs:aRegistryMachin+40h; "ControlSet\\Services\\"
0x140013994  movups  xmmword ptr [rbx+40h], xmm0
0x140013998  movaps  xmm1, xmmword ptr cs:aRegistryMachin+50h; "et\\Services\\"
0x14001399f  movups  xmmword ptr [rbx+50h], xmm1
0x1400139a3  movsd   xmm0, qword ptr cs:aRegistryMachin+60h; "ces\\"
0x1400139ab  movsd   qword ptr [rbx+60h], xmm0
0x1400139b0  call    cs:__imp_RtlAppendUnicodeToString
0x1400139b7  nop     dword ptr [rax+rax+00h]
0x1400139bc  lea     rdx, Source; "\\NetworkProvider"
0x1400139c3  lea     rcx, [rbp+Destination]; Destination
0x1400139c7  call    cs:__imp_RtlAppendUnicodeToString
0x1400139ce  nop     dword ptr [rax+rax+00h]
0x1400139d3  lea     rax, [rbp+Destination]
0x1400139d7  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400139de  xorps   xmm0, xmm0
0x1400139e1  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400139e5  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400139e9  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x1400139ed  mov     edx, 1; DesiredAccess
0x1400139f2  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400139f9  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400139fd  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140013a02  call    cs:__imp_ZwOpenKey
0x140013a09  nop     dword ptr [rax+rax+00h]
0x140013a0e  test    eax, eax
0x140013a10  js      loc_140013AF2
0x140013a16  xor     edx, edx; Tag
0x140013a18  mov     rcx, rbx; P
0x140013a1b  call    cs:__imp_ExFreePoolWithTag
0x140013a22  nop     dword ptr [rax+rax+00h]
0x140013a27  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140013a2b  lea     rdx, aDevicename; "DeviceName"
0x140013a32  call    MupiReadRegistryValue
0x140013a37  mov     rdi, rax
0x140013a3a  test    rax, rax
0x140013a3d  jz      loc_140013AEF
0x140013a43  cmp     dword ptr [rax+4], 1
0x140013a47  jnz     loc_140013ADE
0x140013a4d  mov     eax, [rax+0Ch]
0x140013a50  test    al, 1
0x140013a52  jnz     loc_140013ADE
0x140013a58  mov     edx, [rdi+8]
0x140013a5b  mov     r8d, eax; Size
0x140013a5e  add     rdx, rdi; Src
0x140013a61  mov     rcx, rdi; void *
0x140013a64  mov     ebx, eax
0x140013a66  call    memmove
0x140013a6b  shr     rbx, 1
0x140013a6e  lea     rdx, aTriggerstartpr; "TriggerStartPrefix"
0x140013a75  mov     [rdi+rbx*2], r15w
0x140013a7a  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140013a7e  call    MupiReadRegistryValue
0x140013a83  mov     r14, rax
0x140013a86  test    rax, rax
0x140013a89  jz      short loc_140013AD5
0x140013a8b  cmp     dword ptr [rax+4], 7
0x140013a8f  jnz     short loc_140013AC1
0x140013a91  mov     rcx, [rbp+KeyHandle]
0x140013a95  lea     r8, [rsi+10h]
0x140013a99  lea     rdx, aTriggerstartno; "TriggerStartNotification"
0x140013aa0  call    MupiReadRegistryWnfStateName
0x140013aa5  test    al, al
0x140013aa7  jz      short loc_140013AC1
0x140013aa9  mov     rcx, [rbp+KeyHandle]
0x140013aad  lea     r8, [rsi+18h]
0x140013ab1  lea     rdx, aTriggerstartco; "TriggerStartCompleteNotification"
0x140013ab8  call    MupiReadRegistryWnfStateName
0x140013abd  test    al, al
0x140013abf  jnz     short loc_140013AD5
0x140013ac1  xor     edx, edx; Tag
0x140013ac3  mov     rcx, r14; P
0x140013ac6  call    cs:__imp_ExFreePoolWithTag
0x140013acd  nop     dword ptr [rax+rax+00h]
0x140013ad2  mov     r14, r15
0x140013ad5  mov     [rsi], rdi
0x140013ad8  mov     [rsi+8], r14
0x140013adc  jmp     short loc_140013AEF
0x140013ade  xor     edx, edx; Tag
0x140013ae0  mov     rcx, rdi; P
0x140013ae3  call    cs:__imp_ExFreePoolWithTag
0x140013aea  nop     dword ptr [rax+rax+00h]
0x140013aef  mov     rbx, r15
0x140013af2  mov     rcx, [rbp+KeyHandle]; Handle
0x140013af6  test    rcx, rcx
0x140013af9  jz      short loc_140013B07
0x140013afb  call    cs:__imp_ZwClose
0x140013b02  nop     dword ptr [rax+rax+00h]
0x140013b07  test    rbx, rbx
0x140013b0a  jz      short loc_140013B1D
0x140013b0c  xor     edx, edx; Tag
0x140013b0e  mov     rcx, rbx; P
0x140013b11  call    cs:__imp_ExFreePoolWithTag
0x140013b18  nop     dword ptr [rax+rax+00h]
0x140013b1d  mov     rax, rsi
0x140013b20  add     rsp, 68h
0x140013b24  pop     r15
0x140013b26  pop     r14
0x140013b28  pop     rdi
0x140013b29  pop     rsi
0x140013b2a  pop     rbx
0x140013b2b  pop     rbp
0x140013b2c  retn
```
