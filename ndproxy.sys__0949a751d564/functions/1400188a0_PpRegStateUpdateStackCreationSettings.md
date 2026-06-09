# PpRegStateUpdateStackCreationSettings

- ea: `0x1400188a0`
- end: `0x140018a14`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400177c0`

## callees

- `0x140007e0c`
- `0x1400183b8`
- `0x1400188a0`
- `0x140018b1c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001892e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001892e`
- `ntoskrnl!ZwSetValueKey` at `0x1400189e3`
- `ntoskrnl!ZwSetValueKey` at `0x1400189e3`
- `ntoskrnl!ZwClose` at `0x140018984`
- `ntoskrnl!ZwClose` at `0x1400189f5`
- `ntoskrnl!ZwClose` at `0x140018984`
- `ntoskrnl!ZwClose` at `0x1400189f5`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140018998`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140018998`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14001890e`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14001890e`

## string_xrefs

- `0x1400189a8`: `Security`

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
0x1400188a0  mov     [rsp-8+arg_0], rbx
0x1400188a5  mov     [rsp-8+arg_8], rdi
0x1400188aa  push    rbp
0x1400188ab  mov     rbp, rsp
0x1400188ae  sub     rsp, 60h
0x1400188b2  lea     rax, [rbp+Handle]
0x1400188b6  mov     [rbp+P], 0
0x1400188be  xor     r9d, r9d
0x1400188c1  mov     [rsp+60h+Data], rax
0x1400188c6  xor     r8d, r8d
0x1400188c9  mov     [rbp+KeyHandle], 0
0x1400188d1  mov     rdi, rdx
0x1400188d4  mov     [rbp+Handle], 0
0x1400188dc  call    PiRegStateOpenClassKey
0x1400188e1  test    eax, eax
0x1400188e3  js      loc_140018A03
0x1400188e9  cmp     cs:PiRegStateDiscriptor, 0
0x1400188f0  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x1400188f7  jnz     short loc_140018946
0x1400188f9  xor     edx, edx
0x1400188fb  lea     rax, [rbp+P]
0x1400188ff  mov     r9b, 1
0x140018902  mov     [rsp+60h+Data], rax
0x140018907  mov     rcx, rbx
0x14001890a  lea     r8d, [rdx+1]
0x14001890e  call    cs:__imp_SeCaptureSecurityDescriptor
0x140018915  nop     dword ptr [rax+rax+00h]
0x14001891a  test    eax, eax
0x14001891c  js      short loc_14001893C
0x14001891e  mov     rcx, [rbp+P]; P
0x140018922  xor     edx, edx; Tag
0x140018924  mov     cs:PiRegStateDiscriptor, 1
0x14001892e  call    cs:__imp_ExFreePoolWithTag
0x140018935  nop     dword ptr [rax+rax+00h]
0x14001893a  jmp     short loc_140018946
0x14001893c  mov     cs:PiRegStateDiscriptor, 2
0x140018946  mov     rcx, [rbp+Handle]
0x14001894a  lea     rdx, aProperties; "Properties"
0x140018951  xor     eax, eax
0x140018953  cmp     cs:PiRegStateDiscriptor, 1
0x14001895a  cmovnz  rbx, rax
0x14001895e  lea     rax, [rbp+KeyHandle]
0x140018962  mov     [rsp+60h+var_30], rax
0x140018967  mov     qword ptr [rsp+60h+DataSize], 0
0x140018970  mov     [rsp+60h+Data], rbx
0x140018975  mov     [rbp+P], rbx
0x140018979  call    CmRegUtilCreateWstrKey
0x14001897e  mov     rcx, [rbp+Handle]; Handle
0x140018982  mov     ebx, eax
0x140018984  call    cs:__imp_ZwClose
0x14001898b  nop     dword ptr [rax+rax+00h]
0x140018990  test    ebx, ebx
0x140018992  js      short loc_140018A01
0x140018994  mov     rcx, [rdi+8]; SecurityDescriptor
0x140018998  call    cs:__imp_RtlLengthSecurityDescriptor
0x14001899f  nop     dword ptr [rax+rax+00h]
0x1400189a4  mov     r11, [rdi+8]
0x1400189a8  lea     rdx, aSecurity; "Security"
0x1400189af  xorps   xmm0, xmm0
0x1400189b2  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400189b6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400189ba  mov     r10d, eax
0x1400189bd  call    WdmlibRtlInitUnicodeStringEx
0x1400189c2  mov     ebx, eax
0x1400189c4  test    eax, eax
0x1400189c6  js      short loc_1400189F1
0x1400189c8  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400189cc  lea     rdx, [rbp+DestinationString]; ValueName
0x1400189d0  mov     [rsp+60h+DataSize], r10d; DataSize
0x1400189d5  mov     r9d, 3; Type
0x1400189db  xor     r8d, r8d; TitleIndex
0x1400189de  mov     [rsp+60h+Data], r11; Data
0x1400189e3  call    cs:__imp_ZwSetValueKey
0x1400189ea  nop     dword ptr [rax+rax+00h]
0x1400189ef  mov     ebx, eax
0x1400189f1  mov     rcx, [rbp+KeyHandle]; Handle
0x1400189f5  call    cs:__imp_ZwClose
0x1400189fc  nop     dword ptr [rax+rax+00h]
0x140018a01  mov     eax, ebx
0x140018a03  mov     rbx, [rsp+60h+arg_0]
0x140018a08  mov     rdi, [rsp+60h+arg_8]
0x140018a0d  add     rsp, 60h
0x140018a11  pop     rbp
0x140018a12  retn
```
