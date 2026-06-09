# PpRegStateUpdateStackCreationSettings

- ea: `0x140151120`
- end: `0x140151294`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140150030`

## callees

- `0x140078840`
- `0x140150c38`
- `0x140151120`
- `0x140151448`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140151204`
- `ntoskrnl!ZwClose` at `0x140151275`
- `ntoskrnl!ZwClose` at `0x140151204`
- `ntoskrnl!ZwClose` at `0x140151275`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140151218`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140151218`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401511ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401511ae`
- `ntoskrnl!ZwSetValueKey` at `0x140151263`
- `ntoskrnl!ZwSetValueKey` at `0x140151263`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14015118e`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14015118e`

## string_xrefs

- `0x140151228`: `Security`

## pseudocode

```c
__int64 __fastcall PpRegStateUpdateStackCreationSettings(int a1, __int64 a2)
{
  __int64 result; // rax
  int v4; // r8d
  __int64 v5; // r9
  __int64 *v6; // rbx
  NTSTATUS WstrKey; // ebx
  ULONG DataSize; // r9d
  void *Data; // r10
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
0x140151120  mov     [rsp-8+arg_0], rbx
0x140151125  mov     [rsp-8+arg_8], rdi
0x14015112a  push    rbp
0x14015112b  mov     rbp, rsp
0x14015112e  sub     rsp, 60h
0x140151132  lea     rax, [rbp+Handle]
0x140151136  mov     [rbp+P], 0
0x14015113e  xor     r9d, r9d
0x140151141  mov     [rsp+60h+Data], rax
0x140151146  xor     r8d, r8d
0x140151149  mov     [rbp+KeyHandle], 0
0x140151151  mov     rdi, rdx
0x140151154  mov     [rbp+Handle], 0
0x14015115c  call    PiRegStateOpenClassKey
0x140151161  test    eax, eax
0x140151163  js      loc_140151283
0x140151169  cmp     cs:PiRegStateDiscriptor, 0
0x140151170  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x140151177  jnz     short loc_1401511C6
0x140151179  xor     edx, edx
0x14015117b  lea     rax, [rbp+P]
0x14015117f  mov     r9b, 1
0x140151182  mov     [rsp+60h+Data], rax
0x140151187  mov     rcx, rbx
0x14015118a  lea     r8d, [rdx+1]
0x14015118e  call    cs:__imp_SeCaptureSecurityDescriptor
0x140151195  nop     dword ptr [rax+rax+00h]
0x14015119a  test    eax, eax
0x14015119c  js      short loc_1401511BC
0x14015119e  mov     rcx, [rbp+P]; P
0x1401511a2  xor     edx, edx; Tag
0x1401511a4  mov     cs:PiRegStateDiscriptor, 1
0x1401511ae  call    cs:__imp_ExFreePoolWithTag
0x1401511b5  nop     dword ptr [rax+rax+00h]
0x1401511ba  jmp     short loc_1401511C6
0x1401511bc  mov     cs:PiRegStateDiscriptor, 2
0x1401511c6  mov     rcx, [rbp+Handle]
0x1401511ca  lea     rdx, aProperties_0; "Properties"
0x1401511d1  xor     eax, eax
0x1401511d3  cmp     cs:PiRegStateDiscriptor, 1
0x1401511da  cmovnz  rbx, rax
0x1401511de  lea     rax, [rbp+KeyHandle]
0x1401511e2  mov     [rsp+60h+var_30], rax
0x1401511e7  mov     qword ptr [rsp+60h+DataSize], 0
0x1401511f0  mov     [rsp+60h+Data], rbx
0x1401511f5  mov     [rbp+P], rbx
0x1401511f9  call    CmRegUtilCreateWstrKey
0x1401511fe  mov     rcx, [rbp+Handle]; Handle
0x140151202  mov     ebx, eax
0x140151204  call    cs:__imp_ZwClose
0x14015120b  nop     dword ptr [rax+rax+00h]
0x140151210  test    ebx, ebx
0x140151212  js      short loc_140151281
0x140151214  mov     rcx, [rdi+8]; SecurityDescriptor
0x140151218  call    cs:__imp_RtlLengthSecurityDescriptor
0x14015121f  nop     dword ptr [rax+rax+00h]
0x140151224  mov     r10, [rdi+8]
0x140151228  lea     rdx, aSecurity; "Security"
0x14015122f  xorps   xmm0, xmm0
0x140151232  lea     rcx, [rbp+DestinationString]; DestinationString
0x140151236  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14015123a  mov     r9d, eax
0x14015123d  call    WdmlibRtlInitUnicodeStringEx
0x140151242  mov     ebx, eax
0x140151244  test    eax, eax
0x140151246  js      short loc_140151271
0x140151248  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14015124c  lea     rdx, [rbp+DestinationString]; ValueName
0x140151250  mov     [rsp+60h+DataSize], r9d; DataSize
0x140151255  xor     r8d, r8d; TitleIndex
0x140151258  mov     r9d, 3; Type
0x14015125e  mov     [rsp+60h+Data], r10; Data
0x140151263  call    cs:__imp_ZwSetValueKey
0x14015126a  nop     dword ptr [rax+rax+00h]
0x14015126f  mov     ebx, eax
0x140151271  mov     rcx, [rbp+KeyHandle]; Handle
0x140151275  call    cs:__imp_ZwClose
0x14015127c  nop     dword ptr [rax+rax+00h]
0x140151281  mov     eax, ebx
0x140151283  mov     rbx, [rsp+60h+arg_0]
0x140151288  mov     rdi, [rsp+60h+arg_8]
0x14015128d  add     rsp, 60h
0x140151291  pop     rbp
0x140151292  retn
```
