# DfscReadLinkedConnectionPolicy

- ea: `0x1400187e4`
- end: `0x1400188ae`
- name: `DfscReadLinkedConnectionPolicy`
- size: `202`
- prototype: `int()`
- caller_count: `3`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140028004`
- `0x140029160`
- `0x14002a488`

## callees

- `0x140011760`
- `0x1400187e4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14001889b`
- `ntoskrnl!ZwClose` at `0x14001889b`
- `ntoskrnl!ZwOpenKey` at `0x140018842`
- `ntoskrnl!ZwOpenKey` at `0x140018842`

## string_xrefs

- `0x1400187ff`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\Policies\System`
- `0x140018856`: `EnableLinkedConnections`

## pseudocode

```c
int DfscReadLinkedConnectionPolicy()
{
  int result; // eax
  struct _UNICODE_STRING v1; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  int v3; // [rsp+70h] [rbp+10h] BYREF
  void *KeyHandle; // [rsp+78h] [rbp+18h] BYREF

  KeyHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  v3 = 0;
  v1.Buffer = L"\\Registry\\Machine\\Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System";
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &v1;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_QWORD *)&v1.Length = 9830550;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    v1.Buffer = L"EnableLinkedConnections";
    *(_DWORD *)&v1.Length = 3014702;
    if ( DfscGetUlongRegistryParameter(KeyHandle, &v1, &v3) >= 0 )
      LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject) = (v3 != 0 ? 2 : 0)
                                                  | (__int64)WPP_MAIN_CB.Queue.Wcb.DeviceObject & 0xFFFFFFF9
                                                  | 4;
    return ZwClose(KeyHandle);
  }
  return result;
}

```

## disassembly

```asm
0x1400187e4  push    rbp
0x1400187e6  mov     rbp, rsp
0x1400187e9  sub     rsp, 60h
0x1400187ed  xor     eax, eax
0x1400187ef  mov     [rbp+KeyHandle], 0
0x1400187f7  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x1400187fb  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400187ff  lea     rax, aRegistryMachin; "\\Registry\\Machine\\Software\\Microsof"...
0x140018806  mov     [rbp+arg_0], 0
0x14001880d  mov     [rbp+var_38], rax
0x140018811  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140018815  lea     rax, [rbp+var_40]
0x140018819  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140018821  xorps   xmm0, xmm0
0x140018824  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140018828  mov     edx, 20019h; DesiredAccess
0x14001882d  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x140018835  mov     [rbp+var_40], 960096h
0x14001883d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140018842  call    cs:__imp_ZwOpenKey
0x140018849  nop     dword ptr [rax+rax+00h]
0x14001884e  test    eax, eax
0x140018850  js      short loc_1400188A7
0x140018852  mov     rcx, [rbp+KeyHandle]
0x140018856  lea     rax, aEnablelinkedco; "EnableLinkedConnections"
0x14001885d  lea     r8, [rbp+arg_0]
0x140018861  mov     [rbp+var_38], rax
0x140018865  lea     rdx, [rbp+var_40]
0x140018869  mov     dword ptr [rbp+var_40], 2E002Eh
0x140018870  call    DfscGetUlongRegistryParameter
0x140018875  test    eax, eax
0x140018877  js      short loc_140018897
0x140018879  mov     edx, dword ptr cs:WPP_MAIN_CB.Queue+30h
0x14001887f  mov     eax, [rbp+arg_0]
0x140018882  or      edx, 4
0x140018885  neg     eax
0x140018887  sbb     ecx, ecx
0x140018889  and     edx, 0FFFFFFFDh
0x14001888c  and     ecx, 2
0x14001888f  or      edx, ecx
0x140018891  mov     dword ptr cs:WPP_MAIN_CB.Queue+30h, edx
0x140018897  mov     rcx, [rbp+KeyHandle]; Handle
0x14001889b  call    cs:__imp_ZwClose
0x1400188a2  nop     dword ptr [rax+rax+00h]
0x1400188a7  add     rsp, 60h
0x1400188ab  pop     rbp
0x1400188ac  retn
```
