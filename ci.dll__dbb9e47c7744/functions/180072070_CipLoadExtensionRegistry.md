# CipLoadExtensionRegistry

- ea: `0x180072070`
- end: `0x1800723be`
- name: `CipLoadExtensionRegistry`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180071c9c`

## callees

- `0x18001dff0`
- `0x18001e03c`
- `0x180072070`
- `0x1800723c4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800721ee`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800721ee`
- `ntoskrnl!ExAllocatePool2` at `0x180072123`
- `ntoskrnl!ExAllocatePool2` at `0x1800722b9`
- `ntoskrnl!ExAllocatePool2` at `0x180072123`
- `ntoskrnl!ExAllocatePool2` at `0x1800722b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072150`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072167`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007224e`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072150`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072167`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007224e`
- `ntoskrnl!ZwClose` at `0x18007217c`
- `ntoskrnl!ZwClose` at `0x18007217c`
- `ntoskrnl!ZwOpenKey` at `0x180072229`
- `ntoskrnl!ZwOpenKey` at `0x180072229`
- `ntoskrnl!ZwEnumerateKey` at `0x180072281`
- `ntoskrnl!ZwEnumerateKey` at `0x1800722ee`
- `ntoskrnl!ZwEnumerateKey` at `0x180072281`
- `ntoskrnl!ZwEnumerateKey` at `0x1800722ee`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1800720f3`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1800721c5`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1800720f3`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1800721c5`

## string_xrefs

- `0x18007209b`: `\REGISTRY\Machine\SYSTEM\CurrentControlSet\Control\CI\ExtensionPolicy`
- `0x1800721a9`: `\REGISTRY\Machine\SYSTEM\CurrentControlSet\Control\CI\ExtensionPolicy`

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
0x180072070  push    rbp
0x180072072  push    rbx
0x180072073  push    rsi
0x180072074  push    rdi
0x180072075  push    r13
0x180072077  push    r14
0x180072079  push    r15
0x18007207b  lea     rbp, [rsp-27h]
0x180072080  sub     rsp, 0B0h
0x180072087  xor     eax, eax
0x180072089  mov     [rbp+57h+arg_10], 0
0x180072090  xorps   xmm0, xmm0
0x180072093  mov     [rbp+57h+Handle], rax
0x180072097  mov     [rbp+57h+var_A0], rax
0x18007209b  lea     r8, aRegistryMachin_14; "\\REGISTRY\\Machine\\SYSTEM\\CurrentCon"...
0x1800720a2  lea     rax, [rbp+57h+var_98]
0x1800720a6  mov     [rbp+57h+arg_8], 0
0x1800720ad  mov     [rbp+57h+var_90], rax
0x1800720b1  xor     edi, edi
0x1800720b3  lea     rax, [rbp+57h+var_98]
0x1800720b7  mov     r15, rcx
0x1800720ba  mov     [rbp+57h+var_98], rax
0x1800720be  lea     rcx, aCiextpolicy; "CIExtPolicy"
0x1800720c5  lea     rax, [rbp+57h+arg_10]
0x1800720c9  xorps   xmm1, xmm1
0x1800720cc  mov     [rsp+0E0h+var_B0], rax
0x1800720d1  xor     r9d, r9d
0x1800720d4  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800720d8  mov     dword ptr [rsp+0E0h+ResultLength], edi
0x1800720dc  xor     edx, edx
0x1800720de  mov     qword ptr [rsp+0E0h+Length], rdi
0x1800720e3  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800720e7  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800720eb  movups  xmmword ptr [rbp+57h+pusResult], xmm0
0x1800720ef  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x1800720f3  call    cs:__imp_RtlGetPersistedStateLocation
0x1800720fa  nop     dword ptr [rax+rax+00h]
0x1800720ff  mov     r13d, 63734943h
0x180072105  mov     r14d, 80000005h
0x18007210b  mov     ebx, eax
0x18007210d  test    eax, eax
0x18007210f  jns     short loc_180072118
0x180072111  xor     esi, esi
0x180072113  cmp     eax, r14d
0x180072116  jnz     short loc_18007213C
0x180072118  mov     edx, [rbp+57h+arg_10]
0x18007211b  mov     r8d, r13d
0x18007211e  mov     ecx, 100h
0x180072123  call    cs:__imp_ExAllocatePool2
0x18007212a  nop     dword ptr [rax+rax+00h]
0x18007212f  mov     rsi, rax
0x180072132  test    rax, rax
0x180072135  jnz     short loc_18007219D
0x180072137  mov     ebx, 0C0000017h
0x18007213c  lea     rcx, [rbp+57h+var_98]
0x180072140  call    CipFreeExtRegistryList
0x180072145  test    rsi, rsi
0x180072148  jz      short loc_18007215C
0x18007214a  mov     edx, r13d; Tag
0x18007214d  mov     rcx, rsi; P
0x180072150  call    cs:__imp_ExFreePoolWithTag
0x180072157  nop     dword ptr [rax+rax+00h]
0x18007215c  test    rdi, rdi
0x18007215f  jz      short loc_180072173
0x180072161  mov     edx, r13d; Tag
0x180072164  mov     rcx, rdi; P
0x180072167  call    cs:__imp_ExFreePoolWithTag
0x18007216e  nop     dword ptr [rax+rax+00h]
0x180072173  mov     rcx, [rbp+57h+Handle]; Handle
0x180072177  test    rcx, rcx
0x18007217a  jz      short loc_180072188
0x18007217c  call    cs:__imp_ZwClose
0x180072183  nop     dword ptr [rax+rax+00h]
0x180072188  mov     eax, ebx
0x18007218a  add     rsp, 0B0h
0x180072191  pop     r15
0x180072193  pop     r14
0x180072195  pop     r13
0x180072197  pop     rdi
0x180072198  pop     rsi
0x180072199  pop     rbx
0x18007219a  pop     rbp
0x18007219b  retn
0x18007219d  mov     eax, [rbp+57h+arg_10]
0x1800721a0  lea     rdx, [rbp+57h+arg_10]
0x1800721a4  mov     [rsp+0E0h+var_B0], rdx
0x1800721a9  lea     r8, aRegistryMachin_14; "\\REGISTRY\\Machine\\SYSTEM\\CurrentCon"...
0x1800721b0  mov     dword ptr [rsp+0E0h+ResultLength], eax
0x1800721b4  lea     rcx, aCiextpolicy; "CIExtPolicy"
0x1800721bb  xor     edx, edx
0x1800721bd  mov     qword ptr [rsp+0E0h+Length], rsi
0x1800721c2  xor     r9d, r9d
0x1800721c5  call    cs:__imp_RtlGetPersistedStateLocation
0x1800721cc  nop     dword ptr [rax+rax+00h]
0x1800721d1  mov     ecx, 80000000h
0x1800721d6  mov     ebx, eax
0x1800721d8  add     eax, ecx
0x1800721da  test    ecx, eax
0x1800721dc  jnz     short loc_1800721E7
0x1800721de  cmp     ebx, r14d
0x1800721e1  jnz     loc_18007213C
0x1800721e7  mov     rdx, rsi; SourceString
0x1800721ea  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800721ee  call    cs:__imp_RtlInitUnicodeString
0x1800721f5  nop     dword ptr [rax+rax+00h]
0x1800721fa  lea     rax, [rbp+57h+DestinationString]
0x1800721fe  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180072205  xorps   xmm0, xmm0
0x180072208  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18007220c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180072210  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x180072214  mov     edx, 20019h; DesiredAccess
0x180072219  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180072220  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x180072224  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180072229  call    cs:__imp_ZwOpenKey
0x180072230  nop     dword ptr [rax+rax+00h]
0x180072235  test    eax, eax
0x180072237  jns     short loc_180072240
0x180072239  xor     ebx, ebx
0x18007223b  jmp     loc_18007213C
0x180072240  xor     r14d, r14d
0x180072243  test    rdi, rdi
0x180072246  jz      short loc_18007225C
0x180072248  mov     edx, r13d; Tag
0x18007224b  mov     rcx, rdi; P
0x18007224e  call    cs:__imp_ExFreePoolWithTag
0x180072255  nop     dword ptr [rax+rax+00h]
0x18007225a  xor     edi, edi
0x18007225c  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x180072260  lea     rax, [rbp+57h+arg_8]
0x180072264  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x180072269  mov     r9, rdi; KeyInformation
0x18007226c  xor     r8d, r8d; KeyInformationClass
0x18007226f  mov     [rsp+0E0h+Length], 0; Length
0x180072277  mov     edx, r14d; Index
0x18007227a  mov     [rbp+57h+arg_8], 0
0x180072281  call    cs:__imp_ZwEnumerateKey
0x180072288  nop     dword ptr [rax+rax+00h]
0x18007228d  cmp     eax, 8000001Ah
0x180072292  jz      loc_18007236C
0x180072298  cmp     eax, 80000005h
0x18007229d  jz      short loc_1800722AE
0x18007229f  cmp     eax, 0C0000023h
0x1800722a4  jz      short loc_1800722AE
0x1800722a6  test    eax, eax
0x1800722a8  js      loc_180072364
0x1800722ae  mov     edx, [rbp+57h+arg_8]
0x1800722b1  mov     r8d, r13d
0x1800722b4  mov     ecx, 100h
0x1800722b9  call    cs:__imp_ExAllocatePool2
0x1800722c0  nop     dword ptr [rax+rax+00h]
0x1800722c5  mov     rdi, rax
0x1800722c8  test    rax, rax
0x1800722cb  jz      loc_180072137
0x1800722d1  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x1800722d5  lea     rax, [rbp+57h+arg_8]
0x1800722d9  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1800722de  mov     r9, rdi; KeyInformation
0x1800722e1  mov     eax, [rbp+57h+arg_8]
0x1800722e4  xor     r8d, r8d; KeyInformationClass
0x1800722e7  mov     edx, r14d; Index
0x1800722ea  mov     [rsp+0E0h+Length], eax; Length
0x1800722ee  call    cs:__imp_ZwEnumerateKey
0x1800722f5  nop     dword ptr [rax+rax+00h]
0x1800722fa  test    eax, eax
0x1800722fc  js      short loc_180072364
0x1800722fe  mov     ecx, [rdi+0Ch]; ulOperand
0x180072301  lea     rdx, [rbp+57h+pusResult]; pusResult
0x180072305  call    RtlULongToUShort
0x18007230a  mov     ebx, eax
0x18007230c  test    eax, eax
0x18007230e  js      loc_18007213C
0x180072314  lea     rax, [rdi+10h]
0x180072318  mov     qword ptr [rbp+57h+pusResult+8], rax
0x18007231c  lea     r8, [rbp+57h+var_A0]
0x180072320  movzx   eax, [rbp+57h+pusResult]
0x180072324  lea     rdx, [rbp+57h+pusResult]; Source
0x180072328  lea     rcx, [rbp+57h+DestinationString]; SourceString
0x18007232c  mov     [rbp+57h+pusResult+2], ax
0x180072330  call    CipLoadOneExtensionConfig
0x180072335  test    eax, eax
0x180072337  js      short loc_180072364
0x180072339  mov     rcx, [rbp+57h+var_90]
0x18007233d  lea     rax, [rbp+57h+var_98]
0x180072341  cmp     [rcx], rax
0x180072344  jnz     short loc_1800723B7
0x180072346  mov     rax, [rbp+57h+var_A0]
0x18007234a  lea     rdx, [rbp+57h+var_98]
0x18007234e  mov     [rbp+57h+var_A0], 0
0x180072356  mov     [rax], rdx
0x180072359  mov     [rax+8], rcx
0x18007235d  mov     [rcx], rax
0x180072360  mov     [rbp+57h+var_90], rax
0x180072364  inc     r14d
0x180072367  jmp     loc_180072243
0x18007236c  xor     ebx, ebx
0x18007236e  mov     rax, [rbp+57h+var_98]
0x180072372  lea     rcx, [rbp+57h+var_98]
0x180072376  cmp     rax, rcx
0x180072379  jz      loc_18007213C
0x18007237f  lea     rcx, [rbp+57h+var_98]
0x180072383  cmp     [rax+8], rcx
0x180072387  jnz     short loc_1800723B7
0x180072389  mov     rcx, [rax]
0x18007238c  cmp     [rcx+8], rax
0x180072390  jnz     short loc_1800723B7
0x180072392  mov     [rbp+57h+var_98], rcx
0x180072396  lea     rdx, [rbp+57h+var_98]
0x18007239a  mov     [rcx+8], rdx
0x18007239e  mov     rcx, [r15+8]
0x1800723a2  cmp     [rcx], r15
0x1800723a5  jnz     short loc_1800723B7
0x1800723a7  mov     [rax], r15
0x1800723aa  mov     [rax+8], rcx
0x1800723ae  mov     [rcx], rax
0x1800723b1  mov     [r15+8], rax
0x1800723b5  jmp     short loc_18007236E
0x1800723b7  mov     ecx, 3
0x1800723bc  int     29h; Win8: RtlFailFast(ecx)
```
