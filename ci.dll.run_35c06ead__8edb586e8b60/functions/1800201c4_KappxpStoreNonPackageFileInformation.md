# KappxpStoreNonPackageFileInformation

- ea: `0x1800201c4`
- end: `0x1800203d8`
- name: `KappxpStoreNonPackageFileInformation`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001fc50`

## callees

- `0x1800201c4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180020243`
- `ntoskrnl!ExAllocatePool2` at `0x180020243`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800203ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800203ad`
- `ntoskrnl!ZwClose` at `0x180020399`
- `ntoskrnl!ZwClose` at `0x180020399`
- `ntoskrnl!ZwSetValueKey` at `0x18002035a`
- `ntoskrnl!ZwSetValueKey` at `0x180020387`
- `ntoskrnl!ZwSetValueKey` at `0x18002035a`
- `ntoskrnl!ZwSetValueKey` at `0x180020387`
- `ntoskrnl!ZwOpenKey` at `0x180020326`
- `ntoskrnl!ZwOpenKey` at `0x180020326`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18002028b`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18002028b`

## string_xrefs

- `0x18002026d`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\AppModel\StateChange`
- `0x180020278`: `TargetNtPath`

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
0x1800201c4  mov     [rsp-8+arg_0], rbx
0x1800201c9  mov     [rsp-8+arg_8], rsi
0x1800201ce  push    rbp
0x1800201cf  push    rdi
0x1800201d0  push    r12
0x1800201d2  push    r14
0x1800201d4  push    r15
0x1800201d6  lea     rbp, [rsp-37h]
0x1800201db  sub     rsp, 0B0h
0x1800201e2  xorps   xmm0, xmm0
0x1800201e5  mov     qword ptr [rbp+57h+ValueName.Length], 160014h
0x1800201ed  xor     eax, eax
0x1800201ef  mov     qword ptr [rbp+57h+var_68.Length], 160014h
0x1800201f7  lea     rax, aBinaryname; "BinaryName"
0x1800201fe  mov     r14d, r8d
0x180020201  mov     [rbp+57h+ValueName.Buffer], rax
0x180020205  mov     r15, rdx
0x180020208  lea     rax, aBinaryhash; "BinaryHash"
0x18002020f  mov     rsi, rcx
0x180020212  xor     r12d, r12d
0x180020215  mov     [rbp+57h+var_68.Buffer], rax
0x180020219  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18002021d  mov     ebx, 20Ah
0x180020222  mov     [rbp+57h+KeyHandle], r12
0x180020226  mov     r8d, 58707041h
0x18002022c  mov     [rbp+57h+arg_18], r12d
0x180020230  mov     edx, ebx
0x180020232  mov     ecx, 100h
0x180020237  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18002023b  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18002023f  movups  [rbp+57h+var_88], xmm0
0x180020243  call    cs:__imp_ExAllocatePool2
0x18002024a  nop     dword ptr [rax+rax+00h]
0x18002024f  mov     rdi, rax
0x180020252  test    rax, rax
0x180020255  jnz     short loc_180020261
0x180020257  mov     eax, 0C0000017h
0x18002025c  jmp     loc_1800203BB
0x180020261  lea     rax, [rbp+57h+arg_18]
0x180020265  xor     r9d, r9d
0x180020268  mov     [rsp+0D0h+var_A0], rax
0x18002026d  lea     r8, aRegistryMachin_20; "\\Registry\\Machine\\Software\\Microsof"...
0x180020274  mov     [rsp+0D0h+DataSize], ebx
0x180020278  lea     rdx, aTargetntpath; "TargetNtPath"
0x18002027f  lea     rcx, aAppxstatechang; "AppxStateChange"
0x180020286  mov     [rsp+0D0h+Data], rdi
0x18002028b  call    cs:__imp_RtlGetPersistedStateLocation
0x180020292  nop     dword ptr [rax+rax+00h]
0x180020297  mov     ebx, eax
0x180020299  test    eax, eax
0x18002029b  js      loc_1800203A5
0x1800202a1  xorps   xmm0, xmm0
0x1800202a4  mov     ecx, 7FFFh
0x1800202a9  movups  [rbp+57h+var_88], xmm0
0x1800202ad  mov     rax, rdi
0x1800202b0  mov     edx, 2
0x1800202b5  cmp     [rax], r12w
0x1800202b9  jz      short loc_1800202C4
0x1800202bb  add     rax, rdx
0x1800202be  sub     rcx, 1
0x1800202c2  jnz     short loc_1800202B5
0x1800202c4  mov     rax, rcx
0x1800202c7  neg     rax
0x1800202ca  sbb     ebx, ebx
0x1800202cc  not     ebx
0x1800202ce  and     ebx, 0C000000Dh
0x1800202d4  test    rcx, rcx
0x1800202d7  jz      loc_1800203A5
0x1800202dd  add     cx, cx
0x1800202e0  mov     qword ptr [rbp+57h+var_88+8], rdi
0x1800202e4  mov     eax, 0FFFEh
0x1800202e9  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800202f0  sub     ax, cx
0x1800202f3  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x1800202f7  mov     word ptr [rbp+57h+var_88], ax
0x1800202fb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800202ff  add     ax, dx
0x180020302  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180020309  mov     word ptr [rbp+57h+var_88+2], ax
0x18002030d  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180020311  lea     rax, [rbp+57h+var_88]
0x180020315  xorps   xmm0, xmm0
0x180020318  mov     edx, 20006h; DesiredAccess
0x18002031d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180020321  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180020326  call    cs:__imp_ZwOpenKey
0x18002032d  nop     dword ptr [rax+rax+00h]
0x180020332  mov     ebx, eax
0x180020334  test    eax, eax
0x180020336  js      short loc_1800203A5
0x180020338  movzx   eax, word ptr [rsi+2]
0x18002033c  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180020340  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180020344  mov     r9d, 1; Type
0x18002034a  mov     [rsp+0D0h+DataSize], eax; DataSize
0x18002034e  xor     r8d, r8d; TitleIndex
0x180020351  mov     rax, [rsi+8]
0x180020355  mov     [rsp+0D0h+Data], rax; Data
0x18002035a  call    cs:__imp_ZwSetValueKey
0x180020361  nop     dword ptr [rax+rax+00h]
0x180020366  mov     ebx, eax
0x180020368  test    eax, eax
0x18002036a  js      short loc_180020395
0x18002036c  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180020370  lea     rdx, [rbp+57h+var_68]; ValueName
0x180020374  mov     [rsp+0D0h+DataSize], r14d; DataSize
0x180020379  mov     r9d, 3; Type
0x18002037f  xor     r8d, r8d; TitleIndex
0x180020382  mov     [rsp+0D0h+Data], r15; Data
0x180020387  call    cs:__imp_ZwSetValueKey
0x18002038e  nop     dword ptr [rax+rax+00h]
0x180020393  mov     ebx, eax
0x180020395  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180020399  call    cs:__imp_ZwClose
0x1800203a0  nop     dword ptr [rax+rax+00h]
0x1800203a5  mov     edx, 58707041h; Tag
0x1800203aa  mov     rcx, rdi; P
0x1800203ad  call    cs:__imp_ExFreePoolWithTag
0x1800203b4  nop     dword ptr [rax+rax+00h]
0x1800203b9  mov     eax, ebx
0x1800203bb  lea     r11, [rsp+0D0h+var_20]
0x1800203c3  mov     rbx, [r11+30h]
0x1800203c7  mov     rsi, [r11+38h]
0x1800203cb  mov     rsp, r11
0x1800203ce  pop     r15
0x1800203d0  pop     r14
0x1800203d2  pop     r12
0x1800203d4  pop     rdi
0x1800203d5  pop     rbp
0x1800203d6  retn
```
