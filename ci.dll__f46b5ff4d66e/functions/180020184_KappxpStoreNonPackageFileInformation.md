# KappxpStoreNonPackageFileInformation

- ea: `0x180020184`
- end: `0x180020398`
- name: `KappxpStoreNonPackageFileInformation`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001fc10`

## callees

- `0x180020184`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180020203`
- `ntoskrnl!ExAllocatePool2` at `0x180020203`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002036d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002036d`
- `ntoskrnl!ZwClose` at `0x180020359`
- `ntoskrnl!ZwClose` at `0x180020359`
- `ntoskrnl!ZwSetValueKey` at `0x18002031a`
- `ntoskrnl!ZwSetValueKey` at `0x180020347`
- `ntoskrnl!ZwSetValueKey` at `0x18002031a`
- `ntoskrnl!ZwSetValueKey` at `0x180020347`
- `ntoskrnl!ZwOpenKey` at `0x1800202e6`
- `ntoskrnl!ZwOpenKey` at `0x1800202e6`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18002024b`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18002024b`

## string_xrefs

- `0x180020238`: `TargetNtPath`
- `0x18002022d`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\AppModel\StateChange`

## pseudocode

```c
__int64 __fastcall KappxpStoreNonPackageFileInformation(__int64 a1, void *a2, ULONG a3)
{
  _WORD *Pool2; // rdi
  NTSTATUS PersistedStateLocation; // ebx
  __int64 v9; // rcx
  _WORD *v10; // rax
  void *KeyHandle; // [rsp+40h] [rbp-39h] BYREF
  __int128 v12; // [rsp+48h] [rbp-31h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+58h] [rbp-21h] BYREF
  struct _UNICODE_STRING v14; // [rsp+68h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-1h] BYREF
  int v16; // [rsp+F8h] [rbp+7Fh] BYREF

  *(_QWORD *)&ValueName.Length = 1441812;
  *(_QWORD *)&v14.Length = 1441812;
  ValueName.Buffer = L"BinaryName";
  v14.Buffer = L"BinaryHash";
  KeyHandle = 0;
  v16 = 0;
  memset(&ObjectAttributes, 0, 44);
  v12 = 0;
  Pool2 = (_WORD *)ExAllocatePool2(256, 522, 1483763777);
  if ( !Pool2 )
    return 3221225495LL;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"AppxStateChange",
                             L"TargetNtPath",
                             L"\\Registry\\Machine\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel\\StateChange",
                             0,
                             Pool2,
                             522,
                             &v16);
  if ( PersistedStateLocation >= 0 )
  {
    v9 = 0x7FFF;
    v12 = 0;
    v10 = Pool2;
    do
    {
      if ( !*v10 )
        break;
      ++v10;
      --v9;
    }
    while ( v9 );
    PersistedStateLocation = v9 == 0 ? 0xC000000D : 0;
    if ( v9 )
    {
      *((_QWORD *)&v12 + 1) = Pool2;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      LOWORD(v12) = -2 - 2 * v9;
      ObjectAttributes.Attributes = 576;
      WORD1(v12) = -2 * v9;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v12;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      PersistedStateLocation = ZwOpenKey(&KeyHandle, 0x20006u, &ObjectAttributes);
      if ( PersistedStateLocation >= 0 )
      {
        PersistedStateLocation = ZwSetValueKey(
                                   KeyHandle,
                                   &ValueName,
                                   0,
                                   1u,
                                   *(PVOID *)(a1 + 8),
                                   *(unsigned __int16 *)(a1 + 2));
        if ( PersistedStateLocation >= 0 )
          PersistedStateLocation = ZwSetValueKey(KeyHandle, &v14, 0, 3u, a2, a3);
        ZwClose(KeyHandle);
      }
    }
  }
  ExFreePoolWithTag(Pool2, 0x58707041u);
  return (unsigned int)PersistedStateLocation;
}

```

## disassembly

```asm
0x180020184  mov     [rsp-8+arg_0], rbx
0x180020189  mov     [rsp-8+arg_8], rsi
0x18002018e  push    rbp
0x18002018f  push    rdi
0x180020190  push    r12
0x180020192  push    r14
0x180020194  push    r15
0x180020196  lea     rbp, [rsp-37h]
0x18002019b  sub     rsp, 0B0h
0x1800201a2  xorps   xmm0, xmm0
0x1800201a5  mov     qword ptr [rbp+57h+ValueName.Length], 160014h
0x1800201ad  xor     eax, eax
0x1800201af  mov     qword ptr [rbp+57h+var_68.Length], 160014h
0x1800201b7  lea     rax, aBinaryname; "BinaryName"
0x1800201be  mov     r14d, r8d
0x1800201c1  mov     [rbp+57h+ValueName.Buffer], rax
0x1800201c5  mov     r15, rdx
0x1800201c8  lea     rax, aBinaryhash; "BinaryHash"
0x1800201cf  mov     rsi, rcx
0x1800201d2  xor     r12d, r12d
0x1800201d5  mov     [rbp+57h+var_68.Buffer], rax
0x1800201d9  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800201dd  mov     ebx, 20Ah
0x1800201e2  mov     [rbp+57h+KeyHandle], r12
0x1800201e6  mov     r8d, 58707041h
0x1800201ec  mov     [rbp+57h+arg_18], r12d
0x1800201f0  mov     edx, ebx
0x1800201f2  mov     ecx, 100h
0x1800201f7  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800201fb  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800201ff  movups  [rbp+57h+var_88], xmm0
0x180020203  call    cs:__imp_ExAllocatePool2
0x18002020a  nop     dword ptr [rax+rax+00h]
0x18002020f  mov     rdi, rax
0x180020212  test    rax, rax
0x180020215  jnz     short loc_180020221
0x180020217  mov     eax, 0C0000017h
0x18002021c  jmp     loc_18002037B
0x180020221  lea     rax, [rbp+57h+arg_18]
0x180020225  xor     r9d, r9d
0x180020228  mov     [rsp+0D0h+var_A0], rax
0x18002022d  lea     r8, aRegistryMachin_21; "\\Registry\\Machine\\Software\\Microsof"...
0x180020234  mov     [rsp+0D0h+DataSize], ebx
0x180020238  lea     rdx, aTargetntpath; "TargetNtPath"
0x18002023f  lea     rcx, aAppxstatechang; "AppxStateChange"
0x180020246  mov     [rsp+0D0h+Data], rdi
0x18002024b  call    cs:__imp_RtlGetPersistedStateLocation
0x180020252  nop     dword ptr [rax+rax+00h]
0x180020257  mov     ebx, eax
0x180020259  test    eax, eax
0x18002025b  js      loc_180020365
0x180020261  xorps   xmm0, xmm0
0x180020264  mov     ecx, 7FFFh
0x180020269  movups  [rbp+57h+var_88], xmm0
0x18002026d  mov     rax, rdi
0x180020270  mov     edx, 2
0x180020275  cmp     [rax], r12w
0x180020279  jz      short loc_180020284
0x18002027b  add     rax, rdx
0x18002027e  sub     rcx, 1
0x180020282  jnz     short loc_180020275
0x180020284  mov     rax, rcx
0x180020287  neg     rax
0x18002028a  sbb     ebx, ebx
0x18002028c  not     ebx
0x18002028e  and     ebx, 0C000000Dh
0x180020294  test    rcx, rcx
0x180020297  jz      loc_180020365
0x18002029d  add     cx, cx
0x1800202a0  mov     qword ptr [rbp+57h+var_88+8], rdi
0x1800202a4  mov     eax, 0FFFEh
0x1800202a9  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800202b0  sub     ax, cx
0x1800202b3  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x1800202b7  mov     word ptr [rbp+57h+var_88], ax
0x1800202bb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800202bf  add     ax, dx
0x1800202c2  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800202c9  mov     word ptr [rbp+57h+var_88+2], ax
0x1800202cd  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800202d1  lea     rax, [rbp+57h+var_88]
0x1800202d5  xorps   xmm0, xmm0
0x1800202d8  mov     edx, 20006h; DesiredAccess
0x1800202dd  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800202e1  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800202e6  call    cs:__imp_ZwOpenKey
0x1800202ed  nop     dword ptr [rax+rax+00h]
0x1800202f2  mov     ebx, eax
0x1800202f4  test    eax, eax
0x1800202f6  js      short loc_180020365
0x1800202f8  movzx   eax, word ptr [rsi+2]
0x1800202fc  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180020300  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180020304  mov     r9d, 1; Type
0x18002030a  mov     [rsp+0D0h+DataSize], eax; DataSize
0x18002030e  xor     r8d, r8d; TitleIndex
0x180020311  mov     rax, [rsi+8]
0x180020315  mov     [rsp+0D0h+Data], rax; Data
0x18002031a  call    cs:__imp_ZwSetValueKey
0x180020321  nop     dword ptr [rax+rax+00h]
0x180020326  mov     ebx, eax
0x180020328  test    eax, eax
0x18002032a  js      short loc_180020355
0x18002032c  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180020330  lea     rdx, [rbp+57h+var_68]; ValueName
0x180020334  mov     [rsp+0D0h+DataSize], r14d; DataSize
0x180020339  mov     r9d, 3; Type
0x18002033f  xor     r8d, r8d; TitleIndex
0x180020342  mov     [rsp+0D0h+Data], r15; Data
0x180020347  call    cs:__imp_ZwSetValueKey
0x18002034e  nop     dword ptr [rax+rax+00h]
0x180020353  mov     ebx, eax
0x180020355  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180020359  call    cs:__imp_ZwClose
0x180020360  nop     dword ptr [rax+rax+00h]
0x180020365  mov     edx, 58707041h; Tag
0x18002036a  mov     rcx, rdi; P
0x18002036d  call    cs:__imp_ExFreePoolWithTag
0x180020374  nop     dword ptr [rax+rax+00h]
0x180020379  mov     eax, ebx
0x18002037b  lea     r11, [rsp+0D0h+var_20]
0x180020383  mov     rbx, [r11+30h]
0x180020387  mov     rsi, [r11+38h]
0x18002038b  mov     rsp, r11
0x18002038e  pop     r15
0x180020390  pop     r14
0x180020392  pop     r12
0x180020394  pop     rdi
0x180020395  pop     rbp
0x180020396  retn
```
