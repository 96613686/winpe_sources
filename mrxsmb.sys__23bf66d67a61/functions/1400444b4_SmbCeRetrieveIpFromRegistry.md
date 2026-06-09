# SmbCeRetrieveIpFromRegistry

- ea: `0x1400444b4`
- end: `0x1400447f4`
- name: `SmbCeRetrieveIpFromRegistry`
- size: `832`
- prototype: `__int64 __fastcall(__int64, __int64, struct in_addr *, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400447fc`

## callees

- `0x140010f94`
- `0x140026950`
- `0x14004345c`
- `0x1400444b4`
- `0x140045384`

## import_xrefs

- `ntoskrnl!RtlIpv4StringToAddressW` at `0x140044716`
- `ntoskrnl!RtlIpv4StringToAddressW` at `0x140044716`
- `ntoskrnl!ZwQueryValueKey` at `0x140044689`
- `ntoskrnl!ZwQueryValueKey` at `0x140044689`
- `ntoskrnl!ZwOpenKey` at `0x14004457e`
- `ntoskrnl!ZwOpenKey` at `0x140044612`
- `ntoskrnl!ZwOpenKey` at `0x14004457e`
- `ntoskrnl!ZwOpenKey` at `0x140044612`
- `ntoskrnl!RtlInitUnicodeString` at `0x140044547`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004465c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140044547`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004465c`
- `ntoskrnl!ExAllocatePool2` at `0x140044636`
- `ntoskrnl!ExAllocatePool2` at `0x140044636`
- `ntoskrnl!ZwClose` at `0x14004479e`
- `ntoskrnl!ZwClose` at `0x1400447b3`
- `ntoskrnl!ZwClose` at `0x14004479e`
- `ntoskrnl!ZwClose` at `0x1400447b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400447cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400447cc`

## string_xrefs

- `0x14004453c`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\Lanmanworkstation\Parameters\Routing`

## pseudocode

```c
__int64 __fastcall SmbCeRetrieveIpFromRegistry(__int64 a1, __int64 a2, struct in_addr *a3, _DWORD *a4)
{
  __int64 Pool2; // rdi
  unsigned int v8; // esi
  NTSTATUS v9; // ebx
  _WORD *v10; // rcx
  ADDRESS_FAMILY s_w1; // cx
  UCHAR v12; // al
  __int64 v13; // r8
  __int128 v15; // [rsp+30h] [rbp-89h] BYREF
  __int128 v16; // [rsp+40h] [rbp-79h] BYREF
  LPCWSTR Terminator; // [rsp+50h] [rbp-69h] BYREF
  UNICODE_STRING DestinationString; // [rsp+58h] [rbp-61h] BYREF
  UNICODE_STRING ValueName; // [rsp+68h] [rbp-51h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES v21; // [rsp+A8h] [rbp-11h] BYREF
  void *KeyHandle; // [rsp+120h] [rbp+67h] BYREF
  ULONG Length; // [rsp+128h] [rbp+6Fh] BYREF
  int v24; // [rsp+12Ch] [rbp+73h]
  HANDLE Handle; // [rsp+138h] [rbp+7Fh] BYREF

  v24 = HIDWORD(a2);
  KeyHandle = 0;
  Handle = 0;
  Pool2 = 0;
  Length = 48;
  v8 = -1073741670;
  Terminator = 0;
  *(_OWORD *)&ObjectAttributes.Length = 0;
  *a4 = 0;
  memset(&ObjectAttributes.ObjectName, 0, 32);
  memset(&v21, 0, sizeof(v21));
  DestinationString = 0;
  v15 = 0;
  ValueName = 0;
  if ( !*(_QWORD *)(a1 + 8) || !a3 )
  {
    v9 = -1073741811;
    goto LABEL_27;
  }
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Services\\Lanmanworkstation\\Parameters\\Routing");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v9 < 0 )
    goto LABEL_27;
  v10 = *(_WORD **)(a1 + 8);
  if ( *v10 == 92 )
  {
    if ( *(_WORD *)a1 <= 2u )
    {
      v9 = -1073741823;
      goto LABEL_27;
    }
    LOWORD(v15) = *(_WORD *)a1 - 2;
    WORD1(v15) = *(_WORD *)(a1 + 2) - 2;
    *((_QWORD *)&v15 + 1) = v10 + 1;
  }
  else
  {
    v15 = *(_OWORD *)a1;
  }
  v21.RootDirectory = KeyHandle;
  v21.Length = 48;
  v21.ObjectName = (PUNICODE_STRING)&v15;
  v21.Attributes = 576;
  *(_OWORD *)&v21.SecurityDescriptor = 0;
  v9 = ZwOpenKey(&Handle, 0x20019u, &v21);
  if ( v9 >= 0 )
  {
    Pool2 = ExAllocatePool2(64, Length, 1834186323);
    if ( !Pool2 )
    {
      v9 = -1073741670;
      goto LABEL_27;
    }
    RtlInitUnicodeString(&ValueName, L"LocalAddress");
    v9 = ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, (PVOID)Pool2, Length, &Length);
    if ( v9 >= 0 )
    {
      if ( *(_DWORD *)(Pool2 + 4) != 1 )
      {
        v9 = -1073741788;
        goto LABEL_15;
      }
      v9 = RtlStringCbLengthW((STRSAFE_PCNZWCH)(Pool2 + 12), *(unsigned int *)(Pool2 + 8), 0);
      if ( v9 < 0 || (v9 = RtlIpv4StringToAddressW((PCWSTR)(Pool2 + 12), 1u, &Terminator, a3 + 1), v9 < 0) )
      {
LABEL_15:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_948a51171ac53989b14c3e6a960354da_Traceguids, a1);
        }
        goto LABEL_27;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        s_w1 = a3->S_un.S_un_w.s_w1;
        v16 = (unsigned __int64)a3;
        v12 = SOCKADDR_SIZE(s_w1);
        WORD4(v16) = v12;
        WPP_SF__SOCKADDR_Z(*(_QWORD *)(v13 + 24), v12, v13, (unsigned int)&v16, a1);
      }
      a3->S_un.S_un_w.s_w1 = 2;
      *a4 = 1;
    }
  }
LABEL_27:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Handle )
    ZwClose(Handle);
  if ( Pool2 )
    ExFreePoolWithTag((PVOID)Pool2, 0x6D537653u);
  if ( v9 != -1073741670 )
    return 0;
  return v8;
}

```

## disassembly

```asm
0x1400444b4  mov     qword ptr [rsp-8+arg_8], rdx
0x1400444b9  push    rbp
0x1400444ba  push    rbx
0x1400444bb  push    rsi
0x1400444bc  push    rdi
0x1400444bd  push    r12
0x1400444bf  push    r14
0x1400444c1  push    r15
0x1400444c3  lea     rbp, [rsp-27h]
0x1400444c8  sub     rsp, 0E0h
0x1400444cf  xorps   xmm0, xmm0
0x1400444d2  mov     [rbp+57h+KeyHandle], 0
0x1400444da  xorps   xmm1, xmm1
0x1400444dd  mov     [rbp+57h+Handle], 0
0x1400444e5  xor     edi, edi
0x1400444e7  mov     ebx, 30h ; '0'
0x1400444ec  mov     r12, r9
0x1400444ef  mov     r15, r8
0x1400444f2  mov     r14, rcx
0x1400444f5  mov     [rbp+57h+arg_8], ebx
0x1400444f8  mov     esi, 0C000009Ah
0x1400444fd  mov     [rbp+57h+Terminator], rdi
0x140044501  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140044505  mov     [r9], edi
0x140044508  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14004450c  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140044510  movups  xmmword ptr [rbp+57h+var_68.Length], xmm1
0x140044514  movups  xmmword ptr [rbp+57h+var_68.ObjectName], xmm1
0x140044518  movups  xmmword ptr [rbp+57h+var_68.SecurityDescriptor], xmm1
0x14004451c  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140044520  movups  [rsp+110h+var_E0], xmm1
0x140044525  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x140044529  cmp     [rcx+8], rdi
0x14004452d  jz      loc_140044790
0x140044533  test    r8, r8
0x140044536  jz      loc_140044790
0x14004453c  lea     rdx, aRegistryMachin_4; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x140044543  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140044547  call    cs:__imp_RtlInitUnicodeString
0x14004454e  nop     dword ptr [rax+rax+00h]
0x140044553  lea     rax, [rbp+57h+DestinationString]
0x140044557  mov     [rbp+57h+ObjectAttributes.Length], ebx
0x14004455a  xorps   xmm0, xmm0
0x14004455d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140044561  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140044565  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x140044569  mov     edx, 20019h; DesiredAccess
0x14004456e  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140044575  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140044579  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14004457e  call    cs:__imp_ZwOpenKey
0x140044585  nop     dword ptr [rax+rax+00h]
0x14004458a  mov     ebx, eax
0x14004458c  test    eax, eax
0x14004458e  js      loc_140044795
0x140044594  mov     rcx, [r14+8]
0x140044598  lea     edx, [rdi+2]
0x14004459b  cmp     word ptr [rcx], 5Ch ; '\'
0x14004459f  jz      short loc_1400445AD
0x1400445a1  movaps  xmm0, xmmword ptr [r14]
0x1400445a5  movdqu  [rsp+110h+var_E0], xmm0
0x1400445ab  jmp     short loc_1400445DE
0x1400445ad  movzx   eax, word ptr [r14]
0x1400445b1  cmp     ax, dx
0x1400445b4  ja      short loc_1400445C0
0x1400445b6  mov     ebx, 0C0000001h
0x1400445bb  jmp     loc_140044795
0x1400445c0  sub     ax, dx
0x1400445c3  mov     word ptr [rsp+110h+var_E0], ax
0x1400445c8  movzx   eax, word ptr [r14+2]
0x1400445cd  sub     ax, dx
0x1400445d0  mov     word ptr [rsp+110h+var_E0+2], ax
0x1400445d5  lea     rax, [rcx+2]
0x1400445d9  mov     qword ptr [rsp+110h+var_E0+8], rax
0x1400445de  mov     rax, [rbp+57h+KeyHandle]
0x1400445e2  lea     r8, [rbp+57h+var_68]; ObjectAttributes
0x1400445e6  mov     [rbp+57h+var_68.RootDirectory], rax
0x1400445ea  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x1400445ee  lea     rax, [rsp+110h+var_E0]
0x1400445f3  mov     [rbp+57h+var_68.Length], 30h ; '0'
0x1400445fa  xorps   xmm0, xmm0
0x1400445fd  mov     [rbp+57h+var_68.ObjectName], rax
0x140044601  mov     edx, 20019h; DesiredAccess
0x140044606  mov     [rbp+57h+var_68.Attributes], 240h
0x14004460d  movdqu  xmmword ptr [rbp+57h+var_68.SecurityDescriptor], xmm0
0x140044612  call    cs:__imp_ZwOpenKey
0x140044619  nop     dword ptr [rax+rax+00h]
0x14004461e  mov     ebx, eax
0x140044620  test    eax, eax
0x140044622  js      loc_140044795
0x140044628  mov     edx, [rbp+57h+arg_8]
0x14004462b  mov     ecx, 40h ; '@'
0x140044630  mov     r8d, 6D537653h
0x140044636  call    cs:__imp_ExAllocatePool2
0x14004463d  nop     dword ptr [rax+rax+00h]
0x140044642  mov     rdi, rax
0x140044645  test    rax, rax
0x140044648  jnz     short loc_140044651
0x14004464a  mov     ebx, esi
0x14004464c  jmp     loc_140044795
0x140044651  lea     rdx, aLocaladdress; "LocalAddress"
0x140044658  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x14004465c  call    cs:__imp_RtlInitUnicodeString
0x140044663  nop     dword ptr [rax+rax+00h]
0x140044668  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14004466c  lea     rax, [rbp+57h+arg_8]
0x140044670  mov     [rsp+110h+ResultLength], rax; ResultLength
0x140044675  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140044679  mov     eax, [rbp+57h+arg_8]
0x14004467c  mov     r9, rdi; KeyValueInformation
0x14004467f  mov     r8d, 2; KeyValueInformationClass
0x140044685  mov     [rsp+110h+Length], eax; Length
0x140044689  call    cs:__imp_ZwQueryValueKey
0x140044690  nop     dword ptr [rax+rax+00h]
0x140044695  mov     ebx, eax
0x140044697  test    eax, eax
0x140044699  js      loc_140044795
0x14004469f  cmp     dword ptr [rdi+4], 1
0x1400446a3  jz      short loc_1400446F3
0x1400446a5  mov     ebx, 0C0000024h
0x1400446aa  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400446b1  lea     rax, WPP_GLOBAL_Control
0x1400446b8  cmp     rcx, rax
0x1400446bb  jz      loc_140044795
0x1400446c1  mov     eax, [rcx+2Ch]
0x1400446c4  test    al, 1
0x1400446c6  jz      loc_140044795
0x1400446cc  cmp     byte ptr [rcx+29h], 1
0x1400446d0  jb      loc_140044795
0x1400446d6  mov     rcx, [rcx+18h]
0x1400446da  lea     r8, WPP_948a51171ac53989b14c3e6a960354da_Traceguids
0x1400446e1  mov     edx, 0Ah
0x1400446e6  mov     r9, r14
0x1400446e9  call    WPP_SF_Z
0x1400446ee  jmp     loc_140044795
0x1400446f3  mov     edx, [rdi+8]; cbMax
0x1400446f6  lea     rcx, [rdi+0Ch]; psz
0x1400446fa  xor     r8d, r8d; pcbLength
0x1400446fd  call    RtlStringCbLengthW
0x140044702  mov     ebx, eax
0x140044704  test    eax, eax
0x140044706  js      short loc_1400446AA
0x140044708  lea     r9, [r15+4]; Addr
0x14004470c  mov     dl, 1; Strict
0x14004470e  lea     r8, [rbp+57h+Terminator]; Terminator
0x140044712  lea     rcx, [rdi+0Ch]; S
0x140044716  call    cs:__imp_RtlIpv4StringToAddressW
0x14004471d  nop     dword ptr [rax+rax+00h]
0x140044722  mov     ebx, eax
0x140044724  test    eax, eax
0x140044726  js      short loc_1400446AA
0x140044728  mov     r8, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004472f  lea     rax, WPP_GLOBAL_Control
0x140044736  cmp     r8, rax
0x140044739  jz      short loc_140044780
0x14004473b  mov     eax, [r8+2Ch]
0x14004473f  test    al, 40h
0x140044741  jz      short loc_140044780
0x140044743  cmp     byte ptr [r8+29h], 2
0x140044748  jb      short loc_140044780
0x14004474a  movzx   ecx, word ptr [r15]; af
0x14004474e  xorps   xmm0, xmm0
0x140044751  movups  [rbp+57h+var_D0], xmm0
0x140044755  mov     qword ptr [rbp+57h+var_D0], r15
0x140044759  call    SOCKADDR_SIZE
0x14004475e  movzx   edx, al
0x140044761  lea     r9, [rbp+57h+var_D0]
0x140044765  mov     word ptr [rbp+57h+var_D0+8], dx
0x140044769  movaps  xmm0, [rbp+57h+var_D0]
0x14004476d  movdqa  [rbp+57h+var_D0], xmm0
0x140044772  mov     rcx, [r8+18h]
0x140044776  mov     qword ptr [rsp+110h+Length], r14
0x14004477b  call    WPP_SF__SOCKADDR_Z
0x140044780  mov     word ptr [r15], 2
0x140044786  mov     dword ptr [r12], 1
0x14004478e  jmp     short loc_140044795
0x140044790  mov     ebx, 0C000000Dh
0x140044795  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140044799  test    rcx, rcx
0x14004479c  jz      short loc_1400447AA
0x14004479e  call    cs:__imp_ZwClose
0x1400447a5  nop     dword ptr [rax+rax+00h]
0x1400447aa  mov     rcx, [rbp+57h+Handle]; Handle
0x1400447ae  test    rcx, rcx
0x1400447b1  jz      short loc_1400447BF
0x1400447b3  call    cs:__imp_ZwClose
0x1400447ba  nop     dword ptr [rax+rax+00h]
0x1400447bf  test    rdi, rdi
0x1400447c2  jz      short loc_1400447D8
0x1400447c4  mov     edx, 6D537653h; Tag
0x1400447c9  mov     rcx, rdi; P
0x1400447cc  call    cs:__imp_ExFreePoolWithTag
0x1400447d3  nop     dword ptr [rax+rax+00h]
0x1400447d8  xor     ecx, ecx
0x1400447da  cmp     ebx, esi
0x1400447dc  cmovnz  esi, ecx
0x1400447df  mov     eax, esi
0x1400447e1  add     rsp, 0E0h
0x1400447e8  pop     r15
0x1400447ea  pop     r14
0x1400447ec  pop     r12
0x1400447ee  pop     rdi
0x1400447ef  pop     rsi
0x1400447f0  pop     rbx
0x1400447f1  pop     rbp
0x1400447f2  retn
```
