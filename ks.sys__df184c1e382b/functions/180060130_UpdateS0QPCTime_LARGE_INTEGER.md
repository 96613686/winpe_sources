# UpdateS0QPCTime(_LARGE_INTEGER)

- ea: `0x180060130`
- end: `0x180060276`
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

- `0x180060130`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x180060216`
- `ntoskrnl!ZwCreateKey` at `0x180060216`
- `ntoskrnl!ZwClose` at `0x180060258`
- `ntoskrnl!ZwClose` at `0x180060258`
- `ntoskrnl!ZwSetValueKey` at `0x180060248`
- `ntoskrnl!ZwSetValueKey` at `0x180060248`

## string_xrefs

- `0x180060149`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\DeviceClasses\{3c0d501a-140b-11d1-b40f-00a0c9223196}\PSTS`

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
0x180060130  mov     [rsp-8+arg_10], rbx
0x180060135  mov     [rsp-8+Data], rcx
0x18006013a  push    rbp
0x18006013b  lea     rbp, [rsp-57h]
0x180060140  sub     rsp, 90h
0x180060147  xor     ebx, ebx
0x180060149  lea     r10, aRegistryMachin_6; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x180060150  xorps   xmm0, xmm0
0x180060153  mov     [rbp+57h+KeyHandle], rbx
0x180060157  mov     edx, 7FFFh
0x18006015c  mov     dword ptr [rbp+57h+ObjectAttributes+4], ebx
0x18006015f  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], ebx
0x180060162  mov     r8d, edx
0x180060165  lea     r9d, [rbx+2]
0x180060169  mov     rax, r10
0x18006016c  movups  [rbp+57h+var_50], xmm0
0x180060170  mov     ecx, 0FFFEh
0x180060175  cmp     [rax], bx
0x180060178  jz      short loc_180060185
0x18006017a  add     rax, r9
0x18006017d  sub     r8, 1
0x180060181  jnz     short loc_180060170
0x180060183  jmp     short loc_18006019F
0x180060185  add     r8w, r8w
0x180060189  mov     qword ptr [rbp+57h+var_50+8], r10
0x18006018d  mov     eax, ecx
0x18006018f  sub     ax, r8w
0x180060193  mov     word ptr [rbp+57h+var_50], ax
0x180060197  add     ax, r9w
0x18006019b  mov     word ptr [rbp+57h+var_50+2], ax
0x18006019f  xorps   xmm0, xmm0
0x1800601a2  lea     r8, aLasts0time; "LastS0Time"
0x1800601a9  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x1800601ad  mov     rax, r8
0x1800601b0  cmp     [rax], bx
0x1800601b3  jz      short loc_1800601C0
0x1800601b5  add     rax, r9
0x1800601b8  sub     rdx, 1
0x1800601bc  jnz     short loc_1800601B0
0x1800601be  jmp     short loc_1800601D6
0x1800601c0  add     dx, dx
0x1800601c3  mov     [rbp+57h+ValueName.Buffer], r8
0x1800601c7  sub     cx, dx
0x1800601ca  mov     [rbp+57h+ValueName.Length], cx
0x1800601ce  add     cx, r9w
0x1800601d2  mov     [rbp+57h+ValueName.MaximumLength], cx
0x1800601d6  lea     rax, [rbp+57h+var_50]
0x1800601da  mov     [rsp+90h+Disposition], rbx; Disposition
0x1800601df  xorps   xmm0, xmm0
0x1800601e2  mov     [rsp+90h+CreateOptions], ebx; CreateOptions
0x1800601e6  xor     r9d, r9d; TitleIndex
0x1800601e9  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800601ed  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800601f1  mov     [rsp+90h+Class], rbx; Class
0x1800601f6  mov     edx, 0F003Fh; DesiredAccess
0x1800601fb  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180060202  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180060206  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x18006020a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006020f  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180060216  call    cs:__imp_ZwCreateKey
0x18006021d  nop     dword ptr [rax+rax+00h]
0x180060222  test    eax, eax
0x180060224  js      short loc_180060264
0x180060226  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18006022a  lea     rax, [rbp+57h+Data]
0x18006022e  mov     [rsp+90h+CreateOptions], 8; DataSize
0x180060236  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18006023a  mov     r9d, 3; Type
0x180060240  mov     [rsp+90h+Class], rax; Data
0x180060245  xor     r8d, r8d; TitleIndex
0x180060248  call    cs:__imp_ZwSetValueKey
0x18006024f  nop     dword ptr [rax+rax+00h]
0x180060254  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180060258  call    cs:__imp_ZwClose
0x18006025f  nop     dword ptr [rax+rax+00h]
0x180060264  mov     rbx, [rsp+90h+arg_10]
0x18006026c  add     rsp, 90h
0x180060273  pop     rbp
0x180060274  retn
```
