# PpRegStateUpdateStackCreationSettings

- ea: `0x140044730`
- end: `0x1400448a4`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140043640`

## callees

- `0x14003707c`
- `0x140044248`
- `0x140044730`
- `0x140044a58`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140044814`
- `ntoskrnl!ZwClose` at `0x140044885`
- `ntoskrnl!ZwClose` at `0x140044814`
- `ntoskrnl!ZwClose` at `0x140044885`
- `ntoskrnl!ZwSetValueKey` at `0x140044873`
- `ntoskrnl!ZwSetValueKey` at `0x140044873`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14004479e`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14004479e`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140044828`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140044828`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400447be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400447be`

## string_xrefs

- `0x140044838`: `Security`

## pseudocode

```c
__int64 __fastcall PpRegStateUpdateStackCreationSettings(int a1, __int64 a2)
{
  __int64 result; // rax
  int v4; // r8d
  __int64 v5; // r9
  __int64 *v6; // rbx
  NTSTATUS WstrKey; // ebx
  ULONG DataSize; // r10d
  void *Data; // r11
  HANDLE KeyHandle; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-18h] BYREF
  PVOID P; // [rsp+80h] [rbp+20h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp+28h] BYREF

  P = 0;
  KeyHandle = 0;
  Handle = 0;
  result = PiRegStateOpenClassKey(a1, a2, 0, 0, (__int64)&Handle);
  if ( (int)result >= 0 )
  {
    v6 = PiRegStateSysAllInherittedSecurityDescriptor;
    if ( !PiRegStateDiscriptor )
    {
      LOBYTE(v5) = 1;
      if ( (int)SeCaptureSecurityDescriptor(PiRegStateSysAllInherittedSecurityDescriptor, 0, 1, v5, &P) < 0 )
      {
        PiRegStateDiscriptor = 2;
      }
      else
      {
        PiRegStateDiscriptor = 1;
        ExFreePoolWithTag(P, 0);
      }
    }
    if ( PiRegStateDiscriptor != 1 )
      v6 = 0;
    P = v6;
    WstrKey = CmRegUtilCreateWstrKey(
                (_DWORD)Handle,
                (unsigned int)L"Properties",
                v4,
                v5,
                (__int64)v6,
                0,
                (__int64)&KeyHandle);
    ZwClose(Handle);
    if ( WstrKey >= 0 )
    {
      RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a2 + 8));
      DestinationString = 0;
      WstrKey = WdmlibRtlInitUnicodeStringEx(&DestinationString, L"Security");
      if ( WstrKey >= 0 )
        WstrKey = ZwSetValueKey(KeyHandle, &DestinationString, 0, 3u, Data, DataSize);
      ZwClose(KeyHandle);
    }
    return (unsigned int)WstrKey;
  }
  return result;
}

```

## disassembly

```asm
0x140044730  mov     [rsp-8+arg_0], rbx
0x140044735  mov     [rsp-8+arg_8], rdi
0x14004473a  push    rbp
0x14004473b  mov     rbp, rsp
0x14004473e  sub     rsp, 60h
0x140044742  lea     rax, [rbp+Handle]
0x140044746  mov     [rbp+P], 0
0x14004474e  xor     r9d, r9d
0x140044751  mov     [rsp+60h+Data], rax
0x140044756  xor     r8d, r8d
0x140044759  mov     [rbp+KeyHandle], 0
0x140044761  mov     rdi, rdx
0x140044764  mov     [rbp+Handle], 0
0x14004476c  call    PiRegStateOpenClassKey
0x140044771  test    eax, eax
0x140044773  js      loc_140044893
0x140044779  cmp     cs:PiRegStateDiscriptor, 0
0x140044780  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x140044787  jnz     short loc_1400447D6
0x140044789  xor     edx, edx
0x14004478b  lea     rax, [rbp+P]
0x14004478f  mov     r9b, 1
0x140044792  mov     [rsp+60h+Data], rax
0x140044797  mov     rcx, rbx
0x14004479a  lea     r8d, [rdx+1]
0x14004479e  call    cs:__imp_SeCaptureSecurityDescriptor
0x1400447a5  nop     dword ptr [rax+rax+00h]
0x1400447aa  test    eax, eax
0x1400447ac  js      short loc_1400447CC
0x1400447ae  mov     rcx, [rbp+P]; P
0x1400447b2  xor     edx, edx; Tag
0x1400447b4  mov     cs:PiRegStateDiscriptor, 1
0x1400447be  call    cs:__imp_ExFreePoolWithTag
0x1400447c5  nop     dword ptr [rax+rax+00h]
0x1400447ca  jmp     short loc_1400447D6
0x1400447cc  mov     cs:PiRegStateDiscriptor, 2
0x1400447d6  mov     rcx, [rbp+Handle]
0x1400447da  lea     rdx, aProperties; "Properties"
0x1400447e1  xor     eax, eax
0x1400447e3  cmp     cs:PiRegStateDiscriptor, 1
0x1400447ea  cmovnz  rbx, rax
0x1400447ee  lea     rax, [rbp+KeyHandle]
0x1400447f2  mov     [rsp+60h+var_30], rax
0x1400447f7  mov     qword ptr [rsp+60h+DataSize], 0
0x140044800  mov     [rsp+60h+Data], rbx
0x140044805  mov     [rbp+P], rbx
0x140044809  call    CmRegUtilCreateWstrKey
0x14004480e  mov     rcx, [rbp+Handle]; Handle
0x140044812  mov     ebx, eax
0x140044814  call    cs:__imp_ZwClose
0x14004481b  nop     dword ptr [rax+rax+00h]
0x140044820  test    ebx, ebx
0x140044822  js      short loc_140044891
0x140044824  mov     rcx, [rdi+8]; SecurityDescriptor
0x140044828  call    cs:__imp_RtlLengthSecurityDescriptor
0x14004482f  nop     dword ptr [rax+rax+00h]
0x140044834  mov     r11, [rdi+8]
0x140044838  lea     rdx, aSecurity; "Security"
0x14004483f  xorps   xmm0, xmm0
0x140044842  lea     rcx, [rbp+DestinationString]; DestinationString
0x140044846  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14004484a  mov     r10d, eax
0x14004484d  call    WdmlibRtlInitUnicodeStringEx
0x140044852  mov     ebx, eax
0x140044854  test    eax, eax
0x140044856  js      short loc_140044881
0x140044858  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14004485c  lea     rdx, [rbp+DestinationString]; ValueName
0x140044860  mov     [rsp+60h+DataSize], r10d; DataSize
0x140044865  mov     r9d, 3; Type
0x14004486b  xor     r8d, r8d; TitleIndex
0x14004486e  mov     [rsp+60h+Data], r11; Data
0x140044873  call    cs:__imp_ZwSetValueKey
0x14004487a  nop     dword ptr [rax+rax+00h]
0x14004487f  mov     ebx, eax
0x140044881  mov     rcx, [rbp+KeyHandle]; Handle
0x140044885  call    cs:__imp_ZwClose
0x14004488c  nop     dword ptr [rax+rax+00h]
0x140044891  mov     eax, ebx
0x140044893  mov     rbx, [rsp+60h+arg_0]
0x140044898  mov     rdi, [rsp+60h+arg_8]
0x14004489d  add     rsp, 60h
0x1400448a1  pop     rbp
0x1400448a2  retn
```
