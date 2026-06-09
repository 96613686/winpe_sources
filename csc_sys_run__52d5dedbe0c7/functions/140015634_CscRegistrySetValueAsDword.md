# CscRegistrySetValueAsDword

- ea: `0x140015634`
- end: `0x1400157d8`
- name: `CscRegistrySetValueAsDword`
- size: `420`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14004d1cc`
- `0x14004dcac`
- `0x140090740`

## callees

- `0x140015634`
- `0x140018ee4`
- `0x1400190ec`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140015762`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015762`
- `ntoskrnl!ZwClose` at `0x140015777`
- `ntoskrnl!ZwClose` at `0x140015777`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400156cd`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400156cd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400156b6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400156b6`
- `ntoskrnl!ZwCreateKey` at `0x140015729`
- `ntoskrnl!ZwCreateKey` at `0x140015729`

## string_xrefs

- `0x1400156c2`: `\Registry\Machine\System\CurrentControlSet\Services\CSC\Parameters`

## pseudocode

```c
__int64 __fastcall CscRegistrySetValueAsDword(int a1, unsigned int a2)
{
  NTSTATUS v3; // ebx
  int v4; // edi
  __int64 v5; // rsi
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-9h] BYREF
  void *KeyHandle; // [rsp+D0h] [rbp+77h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  if ( a1 >= 19 )
  {
    v3 = -1073741585;
    v4 = 1356;
  }
  else if ( byte_14003A0C0[0] )
  {
    v5 = 9LL * a1;
    if ( *(_DWORD *)&byte_14003A0C0[72 * a1 + 140] == 4 )
    {
      ExAcquireResourceExclusiveLite(&Resource, 1u);
      RtlInitUnicodeString(
        &DestinationString,
        L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\CSC\\Parameters");
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v3 = ZwCreateKey(&KeyHandle, 0x20006u, &ObjectAttributes, 0, 0, 0, 0);
      if ( v3 >= 0 )
      {
        v4 = 0;
        v3 = CscRegistrypWriteULong(KeyHandle, &qword_14003A138[v5], a2);
      }
      else
      {
        v4 = 1397;
      }
      ExReleaseResourceLite(&Resource);
      if ( KeyHandle )
        ZwClose(KeyHandle);
    }
    else
    {
      v3 = -1073740768;
      v4 = 1369;
    }
  }
  else
  {
    v3 = -1073740768;
    v4 = 1362;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      21,
      WPP_d79ea00412a8325f3b090053ac99afd3_Traceguids,
      (unsigned int)v3,
      v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140015634  push    rbp
0x140015636  push    rbx
0x140015637  push    rsi
0x140015638  push    rdi
0x140015639  push    r12
0x14001563b  push    r14
0x14001563d  lea     rbp, [rsp-2Fh]
0x140015642  sub     rsp, 88h
0x140015649  xorps   xmm0, xmm0
0x14001564c  xor     eax, eax
0x14001564e  mov     [rbp+57h+KeyHandle], rax
0x140015652  mov     r14d, edx
0x140015655  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140015659  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14001565d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140015661  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140015665  cmp     ecx, 13h
0x140015668  jge     loc_140015785
0x14001566e  cmp     cs:byte_14003A0C0, al
0x140015674  jnz     short loc_140015685
0x140015676  mov     ebx, 0C0000420h
0x14001567b  mov     edi, 552h
0x140015680  jmp     loc_14001578F
0x140015685  movsxd  rax, ecx
0x140015688  lea     r12, byte_14003A0C0
0x14001568f  lea     rsi, [rax+rax*8]
0x140015693  cmp     dword ptr [r12+rsi*8+8Ch], 4
0x14001569c  jz      short loc_1400156AD
0x14001569e  mov     ebx, 0C0000420h
0x1400156a3  mov     edi, 559h
0x1400156a8  jmp     loc_14001578F
0x1400156ad  mov     dl, 1; Wait
0x1400156af  lea     rcx, Resource; Resource
0x1400156b6  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400156bd  nop     dword ptr [rax+rax+00h]
0x1400156c2  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400156c9  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400156cd  call    cs:__imp_RtlInitUnicodeString
0x1400156d4  nop     dword ptr [rax+rax+00h]
0x1400156d9  lea     rax, [rbp+57h+DestinationString]
0x1400156dd  mov     [rsp+0B0h+Disposition], 0; Disposition
0x1400156e6  xorps   xmm0, xmm0
0x1400156e9  mov     [rsp+0B0h+CreateOptions], 0; CreateOptions
0x1400156f1  xor     r9d, r9d; TitleIndex
0x1400156f4  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400156f8  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400156fc  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140015703  mov     edx, 20006h; DesiredAccess
0x140015708  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140015710  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140015714  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14001571b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140015720  mov     [rsp+0B0h+Class], 0; Class
0x140015729  call    cs:__imp_ZwCreateKey
0x140015730  nop     dword ptr [rax+rax+00h]
0x140015735  mov     ebx, eax
0x140015737  test    eax, eax
0x140015739  jns     short loc_140015742
0x14001573b  mov     edi, 575h
0x140015740  jmp     short loc_14001575B
0x140015742  mov     rcx, [rbp+57h+KeyHandle]
0x140015746  lea     rdx, [r12+78h]
0x14001574b  lea     rdx, [rdx+rsi*8]
0x14001574f  xor     edi, edi
0x140015751  mov     r8d, r14d
0x140015754  call    CscRegistrypWriteULong
0x140015759  mov     ebx, eax
0x14001575b  lea     rcx, Resource; Resource
0x140015762  call    cs:__imp_ExReleaseResourceLite
0x140015769  nop     dword ptr [rax+rax+00h]
0x14001576e  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140015772  test    rcx, rcx
0x140015775  jz      short loc_14001578F
0x140015777  call    cs:__imp_ZwClose
0x14001577e  nop     dword ptr [rax+rax+00h]
0x140015783  jmp     short loc_14001578F
0x140015785  mov     ebx, 0C00000EFh
0x14001578a  mov     edi, 54Ch
0x14001578f  mov     rcx, cs:WPP_GLOBAL_Control
0x140015796  lea     rax, WPP_GLOBAL_Control
0x14001579d  cmp     rcx, rax
0x1400157a0  jz      short loc_1400157C5
0x1400157a2  mov     eax, [rcx+2Ch]
0x1400157a5  test    al, 20h
0x1400157a7  jz      short loc_1400157C5
0x1400157a9  mov     rcx, [rcx+18h]
0x1400157ad  lea     r8, WPP_d79ea00412a8325f3b090053ac99afd3_Traceguids
0x1400157b4  mov     edx, 15h
0x1400157b9  mov     dword ptr [rsp+0B0h+Class], edi
0x1400157bd  mov     r9d, ebx
0x1400157c0  call    WPP_SF_Dd
0x1400157c5  mov     eax, ebx
0x1400157c7  add     rsp, 88h
0x1400157ce  pop     r14
0x1400157d0  pop     r12
0x1400157d2  pop     rdi
0x1400157d3  pop     rsi
0x1400157d4  pop     rbx
0x1400157d5  pop     rbp
0x1400157d6  retn
```
