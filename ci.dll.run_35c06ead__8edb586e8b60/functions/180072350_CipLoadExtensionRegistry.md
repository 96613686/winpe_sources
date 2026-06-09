# CipLoadExtensionRegistry

- ea: `0x180072350`
- end: `0x18007269e`
- name: `CipLoadExtensionRegistry`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180071f7c`

## callees

- `0x18001e0c4`
- `0x18001e110`
- `0x180072350`
- `0x1800726a4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800724ce`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800724ce`
- `ntoskrnl!ExAllocatePool2` at `0x180072403`
- `ntoskrnl!ExAllocatePool2` at `0x180072599`
- `ntoskrnl!ExAllocatePool2` at `0x180072403`
- `ntoskrnl!ExAllocatePool2` at `0x180072599`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072430`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072447`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007252e`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072430`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072447`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007252e`
- `ntoskrnl!ZwClose` at `0x18007245c`
- `ntoskrnl!ZwClose` at `0x18007245c`
- `ntoskrnl!ZwOpenKey` at `0x180072509`
- `ntoskrnl!ZwOpenKey` at `0x180072509`
- `ntoskrnl!ZwEnumerateKey` at `0x180072561`
- `ntoskrnl!ZwEnumerateKey` at `0x1800725ce`
- `ntoskrnl!ZwEnumerateKey` at `0x180072561`
- `ntoskrnl!ZwEnumerateKey` at `0x1800725ce`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1800723d3`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1800724a5`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1800723d3`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1800724a5`

## string_xrefs

- `0x18007237b`: `\REGISTRY\Machine\SYSTEM\CurrentControlSet\Control\CI\ExtensionPolicy`
- `0x180072489`: `\REGISTRY\Machine\SYSTEM\CurrentControlSet\Control\CI\ExtensionPolicy`

## pseudocode

```c
__int64 __fastcall CipLoadExtensionRegistry(__int64 a1)
{
  ULONG *v1; // rdi
  int PersistedStateLocation; // eax
  NTSTATUS v4; // ebx
  WCHAR *Pool2; // rsi
  ULONG i; // r14d
  NTSTATUS v8; // eax
  ULONG *v9; // rax
  __int64 *v10; // rax
  __int64 *v11; // rcx
  __int64 **v12; // rcx
  __int64 *v13; // [rsp+48h] [rbp-41h] BYREF
  __int64 **v14; // [rsp+50h] [rbp-39h]
  USHORT pusResult[8]; // [rsp+58h] [rbp-31h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-11h] BYREF
  ULONG ResultLength; // [rsp+F8h] [rbp+6Fh] BYREF
  unsigned int v19; // [rsp+100h] [rbp+77h] BYREF
  HANDLE Handle; // [rsp+108h] [rbp+7Fh] BYREF

  v19 = 0;
  Handle = 0;
  ResultLength = 0;
  v14 = &v13;
  v1 = 0;
  v13 = (__int64 *)&v13;
  memset(&ObjectAttributes, 0, 44);
  *(_OWORD *)pusResult = 0;
  DestinationString = 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"CIExtPolicy",
                             0,
                             L"\\REGISTRY\\Machine\\SYSTEM\\CurrentControlSet\\Control\\CI\\ExtensionPolicy",
                             0,
                             0,
                             0,
                             &v19);
  v4 = PersistedStateLocation;
  if ( PersistedStateLocation >= 0 || (Pool2 = 0, PersistedStateLocation == -2147483643) )
  {
    Pool2 = (WCHAR *)ExAllocatePool2(256, v19, 1668499779);
    if ( Pool2 )
    {
      v4 = RtlGetPersistedStateLocation(
             L"CIExtPolicy",
             0,
             L"\\REGISTRY\\Machine\\SYSTEM\\CurrentControlSet\\Control\\CI\\ExtensionPolicy",
             0,
             Pool2,
             v19,
             &v19);
      if ( (int)(v4 + 0x80000000) < 0 || v4 == -2147483643 )
      {
        RtlInitUnicodeString(&DestinationString, Pool2);
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes) >= 0 )
        {
          for ( i = 0; ; ++i )
          {
            if ( v1 )
            {
              ExFreePoolWithTag(v1, 0x63734943u);
              v1 = 0;
            }
            ResultLength = 0;
            v8 = ZwEnumerateKey(Handle, i, KeyBasicInformation, v1, 0, &ResultLength);
            if ( v8 == -2147483622 )
              break;
            if ( v8 == -2147483643 || v8 == -1073741789 || v8 >= 0 )
            {
              v9 = (ULONG *)ExAllocatePool2(256, ResultLength, 1668499779);
              v1 = v9;
              if ( !v9 )
                goto LABEL_4;
              if ( ZwEnumerateKey(Handle, i, KeyBasicInformation, v9, ResultLength, &ResultLength) >= 0 )
              {
                v4 = RtlULongToUShort(v1[3], pusResult);
                if ( v4 < 0 )
                  goto LABEL_5;
                *(_QWORD *)&pusResult[4] = v1 + 4;
                pusResult[1] = pusResult[0];
                if ( (int)CipLoadOneExtensionConfig(&DestinationString, (PCUNICODE_STRING)pusResult) >= 0 )
                {
                  if ( *v14 != (__int64 *)&v13 )
LABEL_36:
                    __fastfail(3u);
                  MEMORY[0] = &v13;
                  MEMORY[8] = v14;
                  *v14 = 0;
                  v14 = 0;
                }
              }
            }
          }
          v4 = 0;
          while ( 1 )
          {
            v10 = v13;
            if ( v13 == (__int64 *)&v13 )
              break;
            if ( (__int64 **)v13[1] != &v13 )
              goto LABEL_36;
            v11 = (__int64 *)*v13;
            if ( *(__int64 **)(*v13 + 8) != v13 )
              goto LABEL_36;
            v13 = (__int64 *)*v13;
            v11[1] = (__int64)&v13;
            v12 = *(__int64 ***)(a1 + 8);
            if ( *v12 != (__int64 *)a1 )
              goto LABEL_36;
            *v10 = a1;
            v10[1] = (__int64)v12;
            *v12 = v10;
            *(_QWORD *)(a1 + 8) = v10;
          }
        }
        else
        {
          v4 = 0;
        }
      }
    }
    else
    {
LABEL_4:
      v4 = -1073741801;
    }
  }
LABEL_5:
  CipFreeExtRegistryList(&v13);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x63734943u);
  if ( v1 )
    ExFreePoolWithTag(v1, 0x63734943u);
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180072350  push    rbp
0x180072352  push    rbx
0x180072353  push    rsi
0x180072354  push    rdi
0x180072355  push    r13
0x180072357  push    r14
0x180072359  push    r15
0x18007235b  lea     rbp, [rsp-27h]
0x180072360  sub     rsp, 0B0h
0x180072367  xor     eax, eax
0x180072369  mov     [rbp+57h+arg_10], 0
0x180072370  xorps   xmm0, xmm0
0x180072373  mov     [rbp+57h+Handle], rax
0x180072377  mov     [rbp+57h+var_A0], rax
0x18007237b  lea     r8, aRegistryMachin_14; "\\REGISTRY\\Machine\\SYSTEM\\CurrentCon"...
0x180072382  lea     rax, [rbp+57h+var_98]
0x180072386  mov     [rbp+57h+arg_8], 0
0x18007238d  mov     [rbp+57h+var_90], rax
0x180072391  xor     edi, edi
0x180072393  lea     rax, [rbp+57h+var_98]
0x180072397  mov     r15, rcx
0x18007239a  mov     [rbp+57h+var_98], rax
0x18007239e  lea     rcx, aCiextpolicy; "CIExtPolicy"
0x1800723a5  lea     rax, [rbp+57h+arg_10]
0x1800723a9  xorps   xmm1, xmm1
0x1800723ac  mov     [rsp+0E0h+var_B0], rax
0x1800723b1  xor     r9d, r9d
0x1800723b4  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800723b8  mov     dword ptr [rsp+0E0h+ResultLength], edi
0x1800723bc  xor     edx, edx
0x1800723be  mov     qword ptr [rsp+0E0h+Length], rdi
0x1800723c3  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800723c7  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800723cb  movups  xmmword ptr [rbp+57h+pusResult], xmm0
0x1800723cf  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x1800723d3  call    cs:__imp_RtlGetPersistedStateLocation
0x1800723da  nop     dword ptr [rax+rax+00h]
0x1800723df  mov     r13d, 63734943h
0x1800723e5  mov     r14d, 80000005h
0x1800723eb  mov     ebx, eax
0x1800723ed  test    eax, eax
0x1800723ef  jns     short loc_1800723F8
0x1800723f1  xor     esi, esi
0x1800723f3  cmp     eax, r14d
0x1800723f6  jnz     short loc_18007241C
0x1800723f8  mov     edx, [rbp+57h+arg_10]
0x1800723fb  mov     r8d, r13d
0x1800723fe  mov     ecx, 100h
0x180072403  call    cs:__imp_ExAllocatePool2
0x18007240a  nop     dword ptr [rax+rax+00h]
0x18007240f  mov     rsi, rax
0x180072412  test    rax, rax
0x180072415  jnz     short loc_18007247D
0x180072417  mov     ebx, 0C0000017h
0x18007241c  lea     rcx, [rbp+57h+var_98]
0x180072420  call    CipFreeExtRegistryList
0x180072425  test    rsi, rsi
0x180072428  jz      short loc_18007243C
0x18007242a  mov     edx, r13d; Tag
0x18007242d  mov     rcx, rsi; P
0x180072430  call    cs:__imp_ExFreePoolWithTag
0x180072437  nop     dword ptr [rax+rax+00h]
0x18007243c  test    rdi, rdi
0x18007243f  jz      short loc_180072453
0x180072441  mov     edx, r13d; Tag
0x180072444  mov     rcx, rdi; P
0x180072447  call    cs:__imp_ExFreePoolWithTag
0x18007244e  nop     dword ptr [rax+rax+00h]
0x180072453  mov     rcx, [rbp+57h+Handle]; Handle
0x180072457  test    rcx, rcx
0x18007245a  jz      short loc_180072468
0x18007245c  call    cs:__imp_ZwClose
0x180072463  nop     dword ptr [rax+rax+00h]
0x180072468  mov     eax, ebx
0x18007246a  add     rsp, 0B0h
0x180072471  pop     r15
0x180072473  pop     r14
0x180072475  pop     r13
0x180072477  pop     rdi
0x180072478  pop     rsi
0x180072479  pop     rbx
0x18007247a  pop     rbp
0x18007247b  retn
0x18007247d  mov     eax, [rbp+57h+arg_10]
0x180072480  lea     rdx, [rbp+57h+arg_10]
0x180072484  mov     [rsp+0E0h+var_B0], rdx
0x180072489  lea     r8, aRegistryMachin_14; "\\REGISTRY\\Machine\\SYSTEM\\CurrentCon"...
0x180072490  mov     dword ptr [rsp+0E0h+ResultLength], eax
0x180072494  lea     rcx, aCiextpolicy; "CIExtPolicy"
0x18007249b  xor     edx, edx
0x18007249d  mov     qword ptr [rsp+0E0h+Length], rsi
0x1800724a2  xor     r9d, r9d
0x1800724a5  call    cs:__imp_RtlGetPersistedStateLocation
0x1800724ac  nop     dword ptr [rax+rax+00h]
0x1800724b1  mov     ecx, 80000000h
0x1800724b6  mov     ebx, eax
0x1800724b8  add     eax, ecx
0x1800724ba  test    ecx, eax
0x1800724bc  jnz     short loc_1800724C7
0x1800724be  cmp     ebx, r14d
0x1800724c1  jnz     loc_18007241C
0x1800724c7  mov     rdx, rsi; SourceString
0x1800724ca  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800724ce  call    cs:__imp_RtlInitUnicodeString
0x1800724d5  nop     dword ptr [rax+rax+00h]
0x1800724da  lea     rax, [rbp+57h+DestinationString]
0x1800724de  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800724e5  xorps   xmm0, xmm0
0x1800724e8  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800724ec  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800724f0  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x1800724f4  mov     edx, 20019h; DesiredAccess
0x1800724f9  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180072500  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x180072504  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180072509  call    cs:__imp_ZwOpenKey
0x180072510  nop     dword ptr [rax+rax+00h]
0x180072515  test    eax, eax
0x180072517  jns     short loc_180072520
0x180072519  xor     ebx, ebx
0x18007251b  jmp     loc_18007241C
0x180072520  xor     r14d, r14d
0x180072523  test    rdi, rdi
0x180072526  jz      short loc_18007253C
0x180072528  mov     edx, r13d; Tag
0x18007252b  mov     rcx, rdi; P
0x18007252e  call    cs:__imp_ExFreePoolWithTag
0x180072535  nop     dword ptr [rax+rax+00h]
0x18007253a  xor     edi, edi
0x18007253c  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x180072540  lea     rax, [rbp+57h+arg_8]
0x180072544  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x180072549  mov     r9, rdi; KeyInformation
0x18007254c  xor     r8d, r8d; KeyInformationClass
0x18007254f  mov     [rsp+0E0h+Length], 0; Length
0x180072557  mov     edx, r14d; Index
0x18007255a  mov     [rbp+57h+arg_8], 0
0x180072561  call    cs:__imp_ZwEnumerateKey
0x180072568  nop     dword ptr [rax+rax+00h]
0x18007256d  cmp     eax, 8000001Ah
0x180072572  jz      loc_18007264C
0x180072578  cmp     eax, 80000005h
0x18007257d  jz      short loc_18007258E
0x18007257f  cmp     eax, 0C0000023h
0x180072584  jz      short loc_18007258E
0x180072586  test    eax, eax
0x180072588  js      loc_180072644
0x18007258e  mov     edx, [rbp+57h+arg_8]
0x180072591  mov     r8d, r13d
0x180072594  mov     ecx, 100h
0x180072599  call    cs:__imp_ExAllocatePool2
0x1800725a0  nop     dword ptr [rax+rax+00h]
0x1800725a5  mov     rdi, rax
0x1800725a8  test    rax, rax
0x1800725ab  jz      loc_180072417
0x1800725b1  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x1800725b5  lea     rax, [rbp+57h+arg_8]
0x1800725b9  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1800725be  mov     r9, rdi; KeyInformation
0x1800725c1  mov     eax, [rbp+57h+arg_8]
0x1800725c4  xor     r8d, r8d; KeyInformationClass
0x1800725c7  mov     edx, r14d; Index
0x1800725ca  mov     [rsp+0E0h+Length], eax; Length
0x1800725ce  call    cs:__imp_ZwEnumerateKey
0x1800725d5  nop     dword ptr [rax+rax+00h]
0x1800725da  test    eax, eax
0x1800725dc  js      short loc_180072644
0x1800725de  mov     ecx, [rdi+0Ch]; ulOperand
0x1800725e1  lea     rdx, [rbp+57h+pusResult]; pusResult
0x1800725e5  call    RtlULongToUShort
0x1800725ea  mov     ebx, eax
0x1800725ec  test    eax, eax
0x1800725ee  js      loc_18007241C
0x1800725f4  lea     rax, [rdi+10h]
0x1800725f8  mov     qword ptr [rbp+57h+pusResult+8], rax
0x1800725fc  lea     r8, [rbp+57h+var_A0]
0x180072600  movzx   eax, [rbp+57h+pusResult]
0x180072604  lea     rdx, [rbp+57h+pusResult]; Source
0x180072608  lea     rcx, [rbp+57h+DestinationString]; SourceString
0x18007260c  mov     [rbp+57h+pusResult+2], ax
0x180072610  call    CipLoadOneExtensionConfig
0x180072615  test    eax, eax
0x180072617  js      short loc_180072644
0x180072619  mov     rcx, [rbp+57h+var_90]
0x18007261d  lea     rax, [rbp+57h+var_98]
0x180072621  cmp     [rcx], rax
0x180072624  jnz     short loc_180072697
0x180072626  mov     rax, [rbp+57h+var_A0]
0x18007262a  lea     rdx, [rbp+57h+var_98]
0x18007262e  mov     [rbp+57h+var_A0], 0
0x180072636  mov     [rax], rdx
0x180072639  mov     [rax+8], rcx
0x18007263d  mov     [rcx], rax
0x180072640  mov     [rbp+57h+var_90], rax
0x180072644  inc     r14d
0x180072647  jmp     loc_180072523
0x18007264c  xor     ebx, ebx
0x18007264e  mov     rax, [rbp+57h+var_98]
0x180072652  lea     rcx, [rbp+57h+var_98]
0x180072656  cmp     rax, rcx
0x180072659  jz      loc_18007241C
0x18007265f  lea     rcx, [rbp+57h+var_98]
0x180072663  cmp     [rax+8], rcx
0x180072667  jnz     short loc_180072697
0x180072669  mov     rcx, [rax]
0x18007266c  cmp     [rcx+8], rax
0x180072670  jnz     short loc_180072697
0x180072672  mov     [rbp+57h+var_98], rcx
0x180072676  lea     rdx, [rbp+57h+var_98]
0x18007267a  mov     [rcx+8], rdx
0x18007267e  mov     rcx, [r15+8]
0x180072682  cmp     [rcx], r15
0x180072685  jnz     short loc_180072697
0x180072687  mov     [rax], r15
0x18007268a  mov     [rax+8], rcx
0x18007268e  mov     [rcx], rax
0x180072691  mov     [r15+8], rax
0x180072695  jmp     short loc_18007264E
0x180072697  mov     ecx, 3
0x18007269c  int     29h; Win8: RtlFailFast(ecx)
```
