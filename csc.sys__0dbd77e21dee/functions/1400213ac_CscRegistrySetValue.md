# CscRegistrySetValue

- ea: `0x1400213ac`
- end: `0x140021582`
- name: `CscRegistrySetValue`
- size: `470`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400212e8`
- `0x1400502a8`

## callees

- `0x1400190ec`
- `0x1400213ac`
- `0x14002199c`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140021504`
- `ntoskrnl!ExReleaseResourceLite` at `0x140021504`
- `ntoskrnl!ZwClose` at `0x140021519`
- `ntoskrnl!ZwClose` at `0x140021519`
- `ntoskrnl!RtlInitUnicodeString` at `0x140021474`
- `ntoskrnl!RtlInitUnicodeString` at `0x140021474`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140021430`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140021430`
- `ntoskrnl!ZwCreateKey` at `0x1400214d0`
- `ntoskrnl!ZwCreateKey` at `0x1400214d0`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002144d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002144d`

## string_xrefs

- `0x140021469`: `\Registry\Machine\System\CurrentControlSet\Services\CSC\Parameters`

## pseudocode

```c
__int64 __fastcall CscRegistrySetValue(unsigned int a1, const UNICODE_STRING *a2)
{
  NTSTATUS v3; // ebx
  int v4; // edi
  __int64 v5; // rbx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+B0h] [rbp+30h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  if ( a1 > 0x12 )
  {
    v3 = -1073741585;
    v4 = 1456;
  }
  else if ( byte_14003A0C0[0] )
  {
    v5 = 9LL * (int)a1;
    if ( *(_DWORD *)&byte_14003A0C0[72 * a1 + 140] == 1 )
    {
      ExAcquireResourceExclusiveLite(&Resource, 1u);
      if ( RtlEqualUnicodeString(a2, (PCUNICODE_STRING)&byte_14003A0C0[8 * v5 + 160], 1u) )
      {
        v3 = 0;
        v4 = 1481;
      }
      else
      {
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
          v3 = CscRegistrypWriteParam(KeyHandle);
        }
        else
        {
          v4 = 1503;
        }
      }
      ExReleaseResourceLite(&Resource);
      if ( KeyHandle )
        ZwClose(KeyHandle);
    }
    else
    {
      v3 = -1073740768;
      v4 = 1469;
    }
  }
  else
  {
    v3 = -1073740768;
    v4 = 1462;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      22,
      WPP_d79ea00412a8325f3b090053ac99afd3_Traceguids,
      (unsigned int)v3,
      v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400213ac  mov     [rsp-18h+arg_0], rbx
0x1400213b1  mov     [rsp-18h+arg_8], rsi
0x1400213b6  push    rbp
0x1400213b7  push    rdi
0x1400213b8  push    r14
0x1400213ba  mov     rbp, rsp
0x1400213bd  sub     rsp, 80h
0x1400213c4  xorps   xmm0, xmm0
0x1400213c7  xor     eax, eax
0x1400213c9  mov     [rbp+KeyHandle], rax
0x1400213cd  mov     rsi, rdx
0x1400213d0  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400213d4  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1400213d8  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400213dc  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400213e0  cmp     ecx, 12h
0x1400213e3  ja      loc_140021527
0x1400213e9  cmp     cs:byte_14003A0C0, al
0x1400213ef  jnz     short loc_140021400
0x1400213f1  mov     ebx, 0C0000420h
0x1400213f6  mov     edi, 5B6h
0x1400213fb  jmp     loc_140021531
0x140021400  movsxd  rax, ecx
0x140021403  lea     rdi, byte_14003A0C0
0x14002140a  lea     rbx, [rax+rax*8]
0x14002140e  cmp     dword ptr [rdi+rbx*8+8Ch], 1
0x140021416  jz      short loc_140021427
0x140021418  mov     ebx, 0C0000420h
0x14002141d  mov     edi, 5BDh
0x140021422  jmp     loc_140021531
0x140021427  mov     dl, 1; Wait
0x140021429  lea     rcx, Resource; Resource
0x140021430  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140021437  nop     dword ptr [rax+rax+00h]
0x14002143c  lea     r14, [rdi+rbx*8]
0x140021440  mov     r8b, 1; CaseInSensitive
0x140021443  lea     rdx, [r14+0A0h]; String2
0x14002144a  mov     rcx, rsi; String1
0x14002144d  call    cs:__imp_RtlEqualUnicodeString
0x140021454  nop     dword ptr [rax+rax+00h]
0x140021459  test    al, al
0x14002145b  jz      short loc_140021469
0x14002145d  xor     ebx, ebx
0x14002145f  mov     edi, 5C9h
0x140021464  jmp     loc_1400214FD
0x140021469  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x140021470  lea     rcx, [rbp+DestinationString]; DestinationString
0x140021474  call    cs:__imp_RtlInitUnicodeString
0x14002147b  nop     dword ptr [rax+rax+00h]
0x140021480  lea     rax, [rbp+DestinationString]
0x140021484  mov     [rsp+80h+Disposition], 0; Disposition
0x14002148d  xorps   xmm0, xmm0
0x140021490  mov     [rsp+80h+CreateOptions], 0; CreateOptions
0x140021498  xor     r9d, r9d; TitleIndex
0x14002149b  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14002149f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400214a3  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400214aa  mov     edx, 20006h; DesiredAccess
0x1400214af  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400214b7  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400214bb  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400214c2  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400214c7  mov     [rsp+80h+Class], 0; Class
0x1400214d0  call    cs:__imp_ZwCreateKey
0x1400214d7  nop     dword ptr [rax+rax+00h]
0x1400214dc  mov     ebx, eax
0x1400214de  test    eax, eax
0x1400214e0  jns     short loc_1400214E9
0x1400214e2  mov     edi, 5DFh
0x1400214e7  jmp     short loc_1400214FD
0x1400214e9  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400214ed  lea     rdx, [r14+70h]
0x1400214f1  xor     edi, edi
0x1400214f3  mov     r8, rsi
0x1400214f6  call    CscRegistrypWriteParam
0x1400214fb  mov     ebx, eax
0x1400214fd  lea     rcx, Resource; Resource
0x140021504  call    cs:__imp_ExReleaseResourceLite
0x14002150b  nop     dword ptr [rax+rax+00h]
0x140021510  mov     rcx, [rbp+KeyHandle]; Handle
0x140021514  test    rcx, rcx
0x140021517  jz      short loc_140021531
0x140021519  call    cs:__imp_ZwClose
0x140021520  nop     dword ptr [rax+rax+00h]
0x140021525  jmp     short loc_140021531
0x140021527  mov     ebx, 0C00000EFh
0x14002152c  mov     edi, 5B0h
0x140021531  mov     rcx, cs:WPP_GLOBAL_Control
0x140021538  lea     rax, WPP_GLOBAL_Control
0x14002153f  cmp     rcx, rax
0x140021542  jz      short loc_140021567
0x140021544  mov     eax, [rcx+2Ch]
0x140021547  test    al, 20h
0x140021549  jz      short loc_140021567
0x14002154b  mov     rcx, [rcx+18h]
0x14002154f  lea     r8, WPP_d79ea00412a8325f3b090053ac99afd3_Traceguids
0x140021556  mov     edx, 16h
0x14002155b  mov     dword ptr [rsp+80h+Class], edi
0x14002155f  mov     r9d, ebx
0x140021562  call    WPP_SF_Dd
0x140021567  lea     r11, [rsp+80h+var_s0]
0x14002156f  mov     eax, ebx
0x140021571  mov     rbx, [r11+20h]
0x140021575  mov     rsi, [r11+28h]
0x140021579  mov     rsp, r11
0x14002157c  pop     r14
0x14002157e  pop     rdi
0x14002157f  pop     rbp
0x140021580  retn
```
