# KappxpStoreNonPackageFileInformation

- ea: `0x1800200f4`
- end: `0x180020308`
- name: `KappxpStoreNonPackageFileInformation`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001fb80`

## callees

- `0x1800200f4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180020173`
- `ntoskrnl!ExAllocatePool2` at `0x180020173`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800202dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800202dd`
- `ntoskrnl!ZwClose` at `0x1800202c9`
- `ntoskrnl!ZwClose` at `0x1800202c9`
- `ntoskrnl!ZwSetValueKey` at `0x18002028a`
- `ntoskrnl!ZwSetValueKey` at `0x1800202b7`
- `ntoskrnl!ZwSetValueKey` at `0x18002028a`
- `ntoskrnl!ZwSetValueKey` at `0x1800202b7`
- `ntoskrnl!ZwOpenKey` at `0x180020256`
- `ntoskrnl!ZwOpenKey` at `0x180020256`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1800201bb`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1800201bb`

## string_xrefs

- `0x18002019d`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\AppModel\StateChange`
- `0x1800201a8`: `TargetNtPath`

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
0x1800200f4  mov     [rsp-8+arg_0], rbx
0x1800200f9  mov     [rsp-8+arg_8], rsi
0x1800200fe  push    rbp
0x1800200ff  push    rdi
0x180020100  push    r12
0x180020102  push    r14
0x180020104  push    r15
0x180020106  lea     rbp, [rsp-37h]
0x18002010b  sub     rsp, 0B0h
0x180020112  xorps   xmm0, xmm0
0x180020115  mov     qword ptr [rbp+57h+ValueName.Length], 160014h
0x18002011d  xor     eax, eax
0x18002011f  mov     qword ptr [rbp+57h+var_68.Length], 160014h
0x180020127  lea     rax, aBinaryname; "BinaryName"
0x18002012e  mov     r14d, r8d
0x180020131  mov     [rbp+57h+ValueName.Buffer], rax
0x180020135  mov     r15, rdx
0x180020138  lea     rax, aBinaryhash; "BinaryHash"
0x18002013f  mov     rsi, rcx
0x180020142  xor     r12d, r12d
0x180020145  mov     [rbp+57h+var_68.Buffer], rax
0x180020149  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18002014d  mov     ebx, 20Ah
0x180020152  mov     [rbp+57h+KeyHandle], r12
0x180020156  mov     r8d, 58707041h
0x18002015c  mov     [rbp+57h+arg_18], r12d
0x180020160  mov     edx, ebx
0x180020162  mov     ecx, 100h
0x180020167  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18002016b  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18002016f  movups  [rbp+57h+var_88], xmm0
0x180020173  call    cs:__imp_ExAllocatePool2
0x18002017a  nop     dword ptr [rax+rax+00h]
0x18002017f  mov     rdi, rax
0x180020182  test    rax, rax
0x180020185  jnz     short loc_180020191
0x180020187  mov     eax, 0C0000017h
0x18002018c  jmp     loc_1800202EB
0x180020191  lea     rax, [rbp+57h+arg_18]
0x180020195  xor     r9d, r9d
0x180020198  mov     [rsp+0D0h+var_A0], rax
0x18002019d  lea     r8, aRegistryMachin_20; "\\Registry\\Machine\\Software\\Microsof"...
0x1800201a4  mov     [rsp+0D0h+DataSize], ebx
0x1800201a8  lea     rdx, aTargetntpath; "TargetNtPath"
0x1800201af  lea     rcx, aAppxstatechang; "AppxStateChange"
0x1800201b6  mov     [rsp+0D0h+Data], rdi
0x1800201bb  call    cs:__imp_RtlGetPersistedStateLocation
0x1800201c2  nop     dword ptr [rax+rax+00h]
0x1800201c7  mov     ebx, eax
0x1800201c9  test    eax, eax
0x1800201cb  js      loc_1800202D5
0x1800201d1  xorps   xmm0, xmm0
0x1800201d4  mov     ecx, 7FFFh
0x1800201d9  movups  [rbp+57h+var_88], xmm0
0x1800201dd  mov     rax, rdi
0x1800201e0  mov     edx, 2
0x1800201e5  cmp     [rax], r12w
0x1800201e9  jz      short loc_1800201F4
0x1800201eb  add     rax, rdx
0x1800201ee  sub     rcx, 1
0x1800201f2  jnz     short loc_1800201E5
0x1800201f4  mov     rax, rcx
0x1800201f7  neg     rax
0x1800201fa  sbb     ebx, ebx
0x1800201fc  not     ebx
0x1800201fe  and     ebx, 0C000000Dh
0x180020204  test    rcx, rcx
0x180020207  jz      loc_1800202D5
0x18002020d  add     cx, cx
0x180020210  mov     qword ptr [rbp+57h+var_88+8], rdi
0x180020214  mov     eax, 0FFFEh
0x180020219  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180020220  sub     ax, cx
0x180020223  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x180020227  mov     word ptr [rbp+57h+var_88], ax
0x18002022b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002022f  add     ax, dx
0x180020232  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180020239  mov     word ptr [rbp+57h+var_88+2], ax
0x18002023d  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180020241  lea     rax, [rbp+57h+var_88]
0x180020245  xorps   xmm0, xmm0
0x180020248  mov     edx, 20006h; DesiredAccess
0x18002024d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180020251  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180020256  call    cs:__imp_ZwOpenKey
0x18002025d  nop     dword ptr [rax+rax+00h]
0x180020262  mov     ebx, eax
0x180020264  test    eax, eax
0x180020266  js      short loc_1800202D5
0x180020268  movzx   eax, word ptr [rsi+2]
0x18002026c  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180020270  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180020274  mov     r9d, 1; Type
0x18002027a  mov     [rsp+0D0h+DataSize], eax; DataSize
0x18002027e  xor     r8d, r8d; TitleIndex
0x180020281  mov     rax, [rsi+8]
0x180020285  mov     [rsp+0D0h+Data], rax; Data
0x18002028a  call    cs:__imp_ZwSetValueKey
0x180020291  nop     dword ptr [rax+rax+00h]
0x180020296  mov     ebx, eax
0x180020298  test    eax, eax
0x18002029a  js      short loc_1800202C5
0x18002029c  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800202a0  lea     rdx, [rbp+57h+var_68]; ValueName
0x1800202a4  mov     [rsp+0D0h+DataSize], r14d; DataSize
0x1800202a9  mov     r9d, 3; Type
0x1800202af  xor     r8d, r8d; TitleIndex
0x1800202b2  mov     [rsp+0D0h+Data], r15; Data
0x1800202b7  call    cs:__imp_ZwSetValueKey
0x1800202be  nop     dword ptr [rax+rax+00h]
0x1800202c3  mov     ebx, eax
0x1800202c5  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800202c9  call    cs:__imp_ZwClose
0x1800202d0  nop     dword ptr [rax+rax+00h]
0x1800202d5  mov     edx, 58707041h; Tag
0x1800202da  mov     rcx, rdi; P
0x1800202dd  call    cs:__imp_ExFreePoolWithTag
0x1800202e4  nop     dword ptr [rax+rax+00h]
0x1800202e9  mov     eax, ebx
0x1800202eb  lea     r11, [rsp+0D0h+var_20]
0x1800202f3  mov     rbx, [r11+30h]
0x1800202f7  mov     rsi, [r11+38h]
0x1800202fb  mov     rsp, r11
0x1800202fe  pop     r15
0x180020300  pop     r14
0x180020302  pop     r12
0x180020304  pop     rdi
0x180020305  pop     rbp
0x180020306  retn
```
