# PmGetRegistryId(_DEVICE_EXTENSION *,_GUID *)

- ea: `0x140023394`
- end: `0x140023533`
- name: `?PmGetRegistryId@@YAJPEAU_DEVICE_EXTENSION@@PEAU_GUID@@@Z`
- size: `415`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1400261fc`

## callees

- `0x140010f20`
- `0x140011440`
- `0x140023394`
- `0x140023540`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x140023480`
- `ntoskrnl!ExUuidCreate` at `0x140023480`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14002344d`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14002344d`
- `ntoskrnl!ZwClose` at `0x140023504`
- `ntoskrnl!ZwClose` at `0x140023504`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1400234cf`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1400234cf`
- `ntoskrnl!RtlGUIDFromString` at `0x140023467`
- `ntoskrnl!RtlGUIDFromString` at `0x140023467`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400234ed`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400234ed`
- `ntoskrnl!RtlStringFromGUID` at `0x14002349a`
- `ntoskrnl!RtlStringFromGUID` at `0x14002349a`

## pseudocode

```c
__int64 __fastcall PmGetRegistryId(struct _DEVICE_EXTENSION *a1, struct _GUID *a2)
{
  NTSTATUS v3; // ebx
  int RegistryValues; // eax
  NTSTATUS v5; // eax
  PCWSTR Path; // [rsp+30h] [rbp-69h] BYREF
  UNICODE_STRING GuidString; // [rsp+38h] [rbp-61h] BYREF
  _QWORD v9[14]; // [rsp+50h] [rbp-49h] BYREF
  GUID Guid; // [rsp+C0h] [rbp+27h] BYREF

  Path = 0;
  memset(v9, 0, sizeof(v9));
  Guid = 0;
  GuidString = 0;
  *a2 = GUID_NULL;
  v3 = PmOpenDeviceParameter(a1, (void **)&Path);
  if ( v3 >= 0 )
  {
    v9[3] = &GuidString;
    v9[2] = L"DiskId";
    v9[0] = 0;
    LODWORD(v9[1]) = 292;
    LODWORD(v9[4]) = 0x1000000;
    RegistryValues = RtlQueryRegistryValuesEx(0x40000000, Path, v9, 0, 0);
    v3 = RegistryValues;
    if ( RegistryValues < 0 )
    {
      if ( RegistryValues != -1073741772 )
        goto LABEL_10;
      v3 = ExUuidCreate(&Guid);
      if ( v3 < 0 )
        goto LABEL_10;
      v3 = RtlStringFromGUID(&Guid, &GuidString);
      if ( v3 < 0 )
        goto LABEL_10;
      v5 = RtlWriteRegistryValue(0x40000000u, Path, L"DiskId", 1u, GuidString.Buffer, GuidString.MaximumLength);
    }
    else
    {
      v5 = RtlGUIDFromString(&GuidString, &Guid);
    }
    v3 = v5;
    if ( v5 >= 0 )
      *a2 = Guid;
  }
LABEL_10:
  RtlFreeUnicodeString(&GuidString);
  if ( Path )
    ZwClose((HANDLE)Path);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140023394  mov     [rsp-8+arg_10], rbx
0x140023399  push    rbp
0x14002339a  push    rsi
0x14002339b  push    r15
0x14002339d  lea     rbp, [rsp-47h]
0x1400233a2  sub     rsp, 0E0h
0x1400233a9  mov     rax, cs:__security_cookie
0x1400233b0  xor     rax, rsp
0x1400233b3  mov     [rbp+57h+var_20], rax
0x1400233b7  mov     rsi, rdx
0x1400233ba  mov     [rbp+57h+Path], 0
0x1400233c2  xor     edx, edx; Val
0x1400233c4  mov     [rbp+57h+var_A0], 0
0x1400233cc  mov     rbx, rcx
0x1400233cf  xorps   xmm0, xmm0
0x1400233d2  xorps   xmm1, xmm1
0x1400233d5  lea     rcx, [rbp+57h+var_98]; void *
0x1400233d9  movups  xmmword ptr [rbp+57h+Guid.Data1], xmm0
0x1400233dd  lea     r8d, [rdx+68h]; Size
0x1400233e1  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm1
0x1400233e5  call    memset
0x1400233ea  movups  xmm0, xmmword ptr cs:?GUID_NULL@@3U_GUID@@B.Data1; _GUID const GUID_NULL ...
0x1400233f1  lea     rdx, [rbp+57h+Path]; void **
0x1400233f5  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x1400233f8  movdqu  xmmword ptr [rsi], xmm0
0x1400233fc  call    ?PmOpenDeviceParameter@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAX@Z; PmOpenDeviceParameter(_DEVICE_EXTENSION *,void * *)
0x140023401  mov     ebx, eax
0x140023403  test    eax, eax
0x140023405  js      loc_1400234E9
0x14002340b  mov     rdx, [rbp+57h+Path]
0x14002340f  lea     rax, [rbp+57h+GuidString]
0x140023413  lea     r15, ValueName; "DiskId"
0x14002341a  mov     [rbp+57h+var_88], rax
0x14002341e  xor     r9d, r9d
0x140023421  mov     [rbp+57h+var_90], r15
0x140023425  lea     r8, [rbp+57h+var_A0]
0x140023429  mov     [rbp+57h+var_A0], 0
0x140023431  mov     ecx, 40000000h
0x140023436  mov     [rbp+57h+var_98], 124h
0x14002343d  mov     [rbp+57h+var_80], 1000000h
0x140023444  mov     [rsp+0F0h+ValueData], 0
0x14002344d  call    cs:__imp_RtlQueryRegistryValuesEx
0x140023454  nop     dword ptr [rax+rax+00h]
0x140023459  mov     ebx, eax
0x14002345b  test    eax, eax
0x14002345d  js      short loc_140023475
0x14002345f  lea     rdx, [rbp+57h+Guid]; Guid
0x140023463  lea     rcx, [rbp+57h+GuidString]; GuidString
0x140023467  call    cs:__imp_RtlGUIDFromString
0x14002346e  nop     dword ptr [rax+rax+00h]
0x140023473  jmp     short loc_1400234DB
0x140023475  cmp     eax, 0C0000034h
0x14002347a  jnz     short loc_1400234E9
0x14002347c  lea     rcx, [rbp+57h+Guid]; Uuid
0x140023480  call    cs:__imp_ExUuidCreate
0x140023487  nop     dword ptr [rax+rax+00h]
0x14002348c  mov     ebx, eax
0x14002348e  test    eax, eax
0x140023490  js      short loc_1400234E9
0x140023492  lea     rdx, [rbp+57h+GuidString]; GuidString
0x140023496  lea     rcx, [rbp+57h+Guid]; Guid
0x14002349a  call    cs:__imp_RtlStringFromGUID
0x1400234a1  nop     dword ptr [rax+rax+00h]
0x1400234a6  mov     ebx, eax
0x1400234a8  test    eax, eax
0x1400234aa  js      short loc_1400234E9
0x1400234ac  movzx   eax, [rbp+57h+GuidString.MaximumLength]
0x1400234b0  mov     r9d, 1; ValueType
0x1400234b6  mov     rdx, [rbp+57h+Path]; Path
0x1400234ba  mov     r8, r15; ValueName
0x1400234bd  mov     [rsp+0F0h+ValueLength], eax; ValueLength
0x1400234c1  mov     ecx, 40000000h; RelativeTo
0x1400234c6  mov     rax, [rbp+57h+GuidString.Buffer]
0x1400234ca  mov     [rsp+0F0h+ValueData], rax; ValueData
0x1400234cf  call    cs:__imp_RtlWriteRegistryValue
0x1400234d6  nop     dword ptr [rax+rax+00h]
0x1400234db  mov     ebx, eax
0x1400234dd  test    eax, eax
0x1400234df  js      short loc_1400234E9
0x1400234e1  movups  xmm0, xmmword ptr [rbp+57h+Guid.Data1]
0x1400234e5  movdqu  xmmword ptr [rsi], xmm0
0x1400234e9  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x1400234ed  call    cs:__imp_RtlFreeUnicodeString
0x1400234f4  nop     dword ptr [rax+rax+00h]
0x1400234f9  cmp     [rbp+57h+Path], 0
0x1400234fe  jz      short loc_140023510
0x140023500  mov     rcx, [rbp+57h+Path]; Handle
0x140023504  call    cs:__imp_ZwClose
0x14002350b  nop     dword ptr [rax+rax+00h]
0x140023510  mov     eax, ebx
0x140023512  mov     rcx, [rbp+57h+var_20]
0x140023516  xor     rcx, rsp; StackCookie
0x140023519  call    __security_check_cookie
0x14002351e  mov     rbx, [rsp+0F0h+arg_10]
0x140023526  add     rsp, 0E0h
0x14002352d  pop     r15
0x14002352f  pop     rsi
0x140023530  pop     rbp
0x140023531  retn
```
