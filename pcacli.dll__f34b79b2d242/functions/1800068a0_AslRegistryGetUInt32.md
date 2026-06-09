# AslRegistryGetUInt32

- ea: `0x1800068a0`
- end: `0x1800069d7`
- name: `AslRegistryGetUInt32`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180004bf0`

## callees

- `0x1800068a0`
- `0x180007738`
- `0x18000c030`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x1800068d1`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800068d1`
- `ntdll!ZwQueryValueKey` at `0x180006959`
- `ntdll!ZwQueryValueKey` at `0x180006959`

## string_xrefs

- `0x1800068ee`: `AslRegistryGetUInt32`
- `0x180006987`: `AslRegistryGetUInt32_UStr`
- `0x1800069bf`: `AslRegistryGetUInt32_UStr`

## pseudocode

```c
__int64 __fastcall AslRegistryGetUInt32(_DWORD *a1, void *a2)
{
  NTSTATUS inited; // eax
  unsigned int v5; // ebx
  NTSTATUS v7; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-50h] BYREF
  __int128 KeyValueInformation; // [rsp+48h] [rbp-40h] BYREF
  int v11; // [rsp+58h] [rbp-30h]

  DestinationString = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, L"LogFlags");
  v5 = inited;
  if ( inited >= 0 )
  {
    v11 = 0;
    ResultLength = 0;
    *a1 = 0;
    KeyValueInformation = 0;
    v7 = ZwQueryValueKey(a2, &DestinationString, KeyValuePartialInformation, &KeyValueInformation, 0x14u, &ResultLength);
    v5 = v7;
    if ( v7 >= 0 )
    {
      if ( *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
      {
        v5 = 0;
        *a1 = HIDWORD(KeyValueInformation);
      }
      else
      {
        AslLogCallPrintf(1, "AslRegistryGetUInt32_UStr", 1098, "Invalid value type");
        return (unsigned int)-1073741788;
      }
    }
    else if ( v7 != -1073741772 )
    {
      AslLogCallPrintf(1, "AslRegistryGetUInt32_UStr", 1091, "Failed to query key value [%x]", v7);
    }
  }
  else
  {
    AslLogCallPrintf(1, "AslRegistryGetUInt32", 1148, "RtlInitUnicodeStringEx failed [%x]", inited);
  }
  return v5;
}

```

## disassembly

```asm
0x1800068a0  push    rbx
0x1800068a2  push    rsi
0x1800068a3  push    rdi
0x1800068a4  sub     rsp, 70h
0x1800068a8  mov     rax, cs:__security_cookie
0x1800068af  xor     rax, rsp
0x1800068b2  mov     [rsp+88h+var_28], rax
0x1800068b7  mov     rsi, rdx
0x1800068ba  mov     rdi, rcx
0x1800068bd  xorps   xmm0, xmm0
0x1800068c0  lea     rdx, aLogflags; "LogFlags"
0x1800068c7  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x1800068cc  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x1800068d1  call    cs:__imp_RtlInitUnicodeStringEx
0x1800068d7  mov     ebx, eax
0x1800068d9  test    eax, eax
0x1800068db  jns     short loc_180006916
0x1800068dd  lea     r9, aRtlinitunicode; "RtlInitUnicodeStringEx failed [%x]"
0x1800068e4  mov     [rsp+88h+Length], eax
0x1800068e8  mov     r8d, 47Ch
0x1800068ee  lea     rdx, aAslregistryget_2; "AslRegistryGetUInt32"
0x1800068f5  mov     ecx, 1
0x1800068fa  call    AslLogCallPrintf
0x1800068ff  mov     eax, ebx
0x180006901  mov     rcx, [rsp+88h+var_28]
0x180006906  xor     rcx, rsp; StackCookie
0x180006909  call    __security_check_cookie
0x18000690e  add     rsp, 70h
0x180006912  pop     rdi
0x180006913  pop     rsi
0x180006914  pop     rbx
0x180006915  retn
0x180006916  xor     eax, eax
0x180006918  mov     [rsp+88h+arg_10], rbp
0x180006920  mov     [rsp+88h+var_30], eax
0x180006924  lea     r9, [rsp+88h+KeyValueInformation]; KeyValueInformation
0x180006929  lea     rax, [rsp+88h+var_58]
0x18000692e  xorps   xmm0, xmm0
0x180006931  xor     ebp, ebp
0x180006933  mov     [rsp+88h+ResultLength], rax; ResultLength
0x180006938  mov     r8d, 2; KeyValueInformationClass
0x18000693e  mov     [rsp+88h+Length], 14h; Length
0x180006946  lea     rdx, [rsp+88h+DestinationString]; ValueName
0x18000694b  mov     [rsp+88h+var_58], ebp
0x18000694f  mov     rcx, rsi; KeyHandle
0x180006952  mov     [rdi], ebp
0x180006954  movups  [rsp+88h+KeyValueInformation], xmm0
0x180006959  call    cs:__imp_ZwQueryValueKey
0x18000695f  mov     ebx, eax
0x180006961  test    eax, eax
0x180006963  jns     short loc_18000699A
0x180006965  cmp     eax, 0C0000034h
0x18000696a  jnz     short loc_180006976
0x18000696c  mov     rbp, [rsp+88h+arg_10]
0x180006974  jmp     short loc_1800068FF
0x180006976  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x18000697d  mov     [rsp+88h+Length], eax
0x180006981  mov     r8d, 443h
0x180006987  lea     rdx, aAslregistryget_0; "AslRegistryGetUInt32_UStr"
0x18000698e  mov     ecx, 1
0x180006993  call    AslLogCallPrintf
0x180006998  jmp     short loc_18000696C
0x18000699a  cmp     dword ptr [rsp+88h+KeyValueInformation+4], 4
0x18000699f  jnz     short loc_1800069B2
0x1800069a1  cmp     dword ptr [rsp+88h+KeyValueInformation+8], 4
0x1800069a6  jnz     short loc_1800069B2
0x1800069a8  mov     eax, dword ptr [rsp+88h+KeyValueInformation+0Ch]
0x1800069ac  mov     ebx, ebp
0x1800069ae  mov     [rdi], eax
0x1800069b0  jmp     short loc_18000696C
0x1800069b2  lea     r9, aInvalidValueTy; "Invalid value type"
0x1800069b9  mov     r8d, 44Ah
0x1800069bf  lea     rdx, aAslregistryget_0; "AslRegistryGetUInt32_UStr"
0x1800069c6  mov     ecx, 1
0x1800069cb  call    AslLogCallPrintf
0x1800069d0  mov     ebx, 0C0000024h
0x1800069d5  jmp     short loc_18000696C
```
