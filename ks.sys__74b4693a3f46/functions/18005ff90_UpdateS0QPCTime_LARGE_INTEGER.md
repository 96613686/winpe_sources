# UpdateS0QPCTime(_LARGE_INTEGER)

- ea: `0x18005ff90`
- end: `0x1800600d6`
- name: `?UpdateS0QPCTime@@YAXT_LARGE_INTEGER@@@Z`
- size: `326`
- prototype: `void __fastcall(union _LARGE_INTEGER)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180045a40`
- `0x180045d5c`

## callees

- `0x18005ff90`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x180060076`
- `ntoskrnl!ZwCreateKey` at `0x180060076`
- `ntoskrnl!ZwClose` at `0x1800600b8`
- `ntoskrnl!ZwClose` at `0x1800600b8`
- `ntoskrnl!ZwSetValueKey` at `0x1800600a8`
- `ntoskrnl!ZwSetValueKey` at `0x1800600a8`

## string_xrefs

- `0x18005ffa9`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\DeviceClasses\{3c0d501a-140b-11d1-b40f-00a0c9223196}\PSTS`

## pseudocode

```c
void __fastcall UpdateS0QPCTime(union _LARGE_INTEGER a1)
{
  __int64 v1; // rdx
  __int64 v2; // r8
  const wchar_t *v3; // rax
  __int16 v4; // r8
  const wchar_t *v5; // rax
  __int16 v6; // dx
  __int128 v7; // [rsp+40h] [rbp+7h] BYREF
  UNICODE_STRING ValueName; // [rsp+50h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+27h] BYREF
  union _LARGE_INTEGER Data; // [rsp+A0h] [rbp+67h] BYREF
  void *KeyHandle; // [rsp+A8h] [rbp+6Fh] BYREF

  Data = a1;
  KeyHandle = 0;
  v1 = 0x7FFF;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  v2 = 0x7FFF;
  v3 = L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\DeviceClasses\\{3c0d501a-140b-11d1-b40f-00a0c9223196}\\PSTS";
  v7 = 0;
  while ( *v3 )
  {
    ++v3;
    if ( !--v2 )
      goto LABEL_6;
  }
  v4 = 2 * v2;
  *((_QWORD *)&v7 + 1) = L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\DeviceClasses\\{3c0d501a-140b-11d1-b40"
                          "f-00a0c9223196}\\PSTS";
  LOWORD(v7) = -2 - v4;
  WORD1(v7) = -v4;
LABEL_6:
  ValueName = 0;
  v5 = L"LastS0Time";
  while ( *v5 )
  {
    ++v5;
    if ( !--v1 )
      goto LABEL_11;
  }
  v6 = 2 * v1;
  ValueName.Buffer = L"LastS0Time";
  ValueName.Length = -2 - v6;
  ValueName.MaximumLength = -v6;
LABEL_11:
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v7;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.Attributes = 576;
  if ( ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, 0) >= 0 )
  {
    ZwSetValueKey(KeyHandle, &ValueName, 0, 3u, &Data, 8u);
    ZwClose(KeyHandle);
  }
}

```

## disassembly

```asm
0x18005ff90  mov     [rsp-8+arg_10], rbx
0x18005ff95  mov     [rsp-8+Data], rcx
0x18005ff9a  push    rbp
0x18005ff9b  lea     rbp, [rsp-57h]
0x18005ffa0  sub     rsp, 90h
0x18005ffa7  xor     ebx, ebx
0x18005ffa9  lea     r10, aRegistryMachin_6; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x18005ffb0  xorps   xmm0, xmm0
0x18005ffb3  mov     [rbp+57h+KeyHandle], rbx
0x18005ffb7  mov     edx, 7FFFh
0x18005ffbc  mov     dword ptr [rbp+57h+ObjectAttributes+4], ebx
0x18005ffbf  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], ebx
0x18005ffc2  mov     r8d, edx
0x18005ffc5  lea     r9d, [rbx+2]
0x18005ffc9  mov     rax, r10
0x18005ffcc  movups  [rbp+57h+var_50], xmm0
0x18005ffd0  mov     ecx, 0FFFEh
0x18005ffd5  cmp     [rax], bx
0x18005ffd8  jz      short loc_18005FFE5
0x18005ffda  add     rax, r9
0x18005ffdd  sub     r8, 1
0x18005ffe1  jnz     short loc_18005FFD0
0x18005ffe3  jmp     short loc_18005FFFF
0x18005ffe5  add     r8w, r8w
0x18005ffe9  mov     qword ptr [rbp+57h+var_50+8], r10
0x18005ffed  mov     eax, ecx
0x18005ffef  sub     ax, r8w
0x18005fff3  mov     word ptr [rbp+57h+var_50], ax
0x18005fff7  add     ax, r9w
0x18005fffb  mov     word ptr [rbp+57h+var_50+2], ax
0x18005ffff  xorps   xmm0, xmm0
0x180060002  lea     r8, aLasts0time; "LastS0Time"
0x180060009  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x18006000d  mov     rax, r8
0x180060010  cmp     [rax], bx
0x180060013  jz      short loc_180060020
0x180060015  add     rax, r9
0x180060018  sub     rdx, 1
0x18006001c  jnz     short loc_180060010
0x18006001e  jmp     short loc_180060036
0x180060020  add     dx, dx
0x180060023  mov     [rbp+57h+ValueName.Buffer], r8
0x180060027  sub     cx, dx
0x18006002a  mov     [rbp+57h+ValueName.Length], cx
0x18006002e  add     cx, r9w
0x180060032  mov     [rbp+57h+ValueName.MaximumLength], cx
0x180060036  lea     rax, [rbp+57h+var_50]
0x18006003a  mov     [rsp+90h+Disposition], rbx; Disposition
0x18006003f  xorps   xmm0, xmm0
0x180060042  mov     [rsp+90h+CreateOptions], ebx; CreateOptions
0x180060046  xor     r9d, r9d; TitleIndex
0x180060049  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18006004d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180060051  mov     [rsp+90h+Class], rbx; Class
0x180060056  mov     edx, 0F003Fh; DesiredAccess
0x18006005b  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180060062  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180060066  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x18006006a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006006f  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180060076  call    cs:__imp_ZwCreateKey
0x18006007d  nop     dword ptr [rax+rax+00h]
0x180060082  test    eax, eax
0x180060084  js      short loc_1800600C4
0x180060086  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18006008a  lea     rax, [rbp+57h+Data]
0x18006008e  mov     [rsp+90h+CreateOptions], 8; DataSize
0x180060096  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18006009a  mov     r9d, 3; Type
0x1800600a0  mov     [rsp+90h+Class], rax; Data
0x1800600a5  xor     r8d, r8d; TitleIndex
0x1800600a8  call    cs:__imp_ZwSetValueKey
0x1800600af  nop     dword ptr [rax+rax+00h]
0x1800600b4  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800600b8  call    cs:__imp_ZwClose
0x1800600bf  nop     dword ptr [rax+rax+00h]
0x1800600c4  mov     rbx, [rsp+90h+arg_10]
0x1800600cc  add     rsp, 90h
0x1800600d3  pop     rbp
0x1800600d4  retn
```
