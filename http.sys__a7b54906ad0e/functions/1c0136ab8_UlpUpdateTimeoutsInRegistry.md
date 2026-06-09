# UlpUpdateTimeoutsInRegistry

- ea: `0x1c0136ab8`
- end: `0x1c0136bf9`
- name: `UlpUpdateTimeoutsInRegistry`
- size: `321`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, registry_config, service_task, installer_update`

## callers

- `0x1c0049660`
- `0x1c0136904`

## callees

- `0x1c0136ab8`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1c0136b3d`
- `ntoskrnl!ZwOpenKey` at `0x1c0136b3d`
- `ntoskrnl!ZwDeleteValueKey` at `0x1c0136b9b`
- `ntoskrnl!ZwDeleteValueKey` at `0x1c0136b9b`
- `ntoskrnl!ZwSetValueKey` at `0x1c0136bc0`
- `ntoskrnl!ZwSetValueKey` at `0x1c0136bc0`
- `ntoskrnl!ZwClose` at `0x1c0136bd7`
- `ntoskrnl!ZwClose` at `0x1c0136bd7`

## string_xrefs

- `0x1c0136ad9`: `\Registry\Machine\System\CurrentControlSet\Services\Http\Parameters`

## pseudocode

```c
__int64 __fastcall UlpUpdateTimeoutsInRegistry(__int64 a1, int a2, int a3, char a4)
{
  NTSTATUS v6; // edi
  const wchar_t *v7; // rax
  NTSTATUS v8; // eax
  __int128 v10; // [rsp+38h] [rbp-19h]
  struct _UNICODE_STRING v11; // [rsp+38h] [rbp-19h]
  struct _UNICODE_STRING ValueName; // [rsp+48h] [rbp-9h] BYREF
  __int128 v13; // [rsp+58h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp+17h] BYREF
  void *KeyHandle; // [rsp+B8h] [rbp+67h] BYREF
  int Data; // [rsp+C8h] [rbp+77h] BYREF

  Data = a3;
  KeyHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  ObjectAttributes.RootDirectory = 0;
  ValueName = 0;
  *((_QWORD *)&v10 + 1) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Http\\Parameters";
  *(_QWORD *)&v10 = 8781958;
  v13 = v10;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v13;
  v6 = ZwOpenKey(&KeyHandle, 0x2001Fu, &ObjectAttributes);
  if ( v6 >= 0 )
  {
    if ( a2 )
    {
      if ( a2 != 1 )
      {
        v6 = -1073741811;
        goto LABEL_11;
      }
      *(_DWORD *)&v11.Length = 2228258;
      v7 = L"HeaderWaitTimeout";
    }
    else
    {
      *(_DWORD *)&v11.Length = 2752554;
      v7 = L"IdleConnectionTimeout";
    }
    *(_DWORD *)(&v11.MaximumLength + 1) = 0;
    v11.Buffer = (PWSTR)v7;
    ValueName = v11;
    if ( a4 )
      v8 = ZwDeleteValueKey(KeyHandle, &ValueName);
    else
      v8 = ZwSetValueKey(KeyHandle, &ValueName, 0, 4u, &Data, 4u);
    v6 = v8;
  }
LABEL_11:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1c0136ab8  mov     rax, rsp
0x1c0136abb  mov     [rax+10h], rbx
0x1c0136abf  mov     [rax+18h], r8d
0x1c0136ac3  mov     [rax+8], rcx
0x1c0136ac7  push    rbp
0x1c0136ac8  push    rsi
0x1c0136ac9  push    rdi
0x1c0136aca  lea     rbp, [rax-5Fh]
0x1c0136ace  sub     rsp, 90h
0x1c0136ad5  and     dword ptr [rbp+57h+var_70+4], 0
0x1c0136ad9  lea     rax, aRegistryMachin_7; "\\Registry\\Machine\\System\\CurrentCon"...
0x1c0136ae0  and     [rbp+57h+KeyHandle], 0
0x1c0136ae5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1c0136ae9  and     dword ptr [rbp+57h+ObjectAttributes+4], 0
0x1c0136aed  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1c0136af1  and     dword ptr [rbp+57h+ObjectAttributes+1Ch], 0
0x1c0136af5  xorps   xmm0, xmm0
0x1c0136af8  and     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1c0136afd  mov     ebx, edx
0x1c0136aff  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x1c0136b03  mov     qword ptr [rbp+57h+var_70+8], rax
0x1c0136b07  mov     edx, 2001Fh; DesiredAccess
0x1c0136b0c  lea     rax, [rbp+57h+var_50]
0x1c0136b10  mov     dword ptr [rbp+57h+var_70], 860086h
0x1c0136b17  movaps  xmm0, [rbp+57h+var_70]
0x1c0136b1b  mov     sil, r9b
0x1c0136b1e  movdqa  [rbp+57h+var_50], xmm0
0x1c0136b23  xorps   xmm0, xmm0
0x1c0136b26  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1c0136b2b  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1c0136b32  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1c0136b39  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1c0136b3d  call    cs:__imp_ZwOpenKey
0x1c0136b44  nop     dword ptr [rax+rax+00h]
0x1c0136b49  mov     edi, eax
0x1c0136b4b  test    eax, eax
0x1c0136b4d  js      short loc_1C0136BCE
0x1c0136b4f  test    ebx, ebx
0x1c0136b51  jz      short loc_1C0136B6F
0x1c0136b53  cmp     ebx, 1
0x1c0136b56  jz      short loc_1C0136B5F
0x1c0136b58  mov     edi, 0C000000Dh
0x1c0136b5d  jmp     short loc_1C0136BCE
0x1c0136b5f  mov     dword ptr [rbp+57h+var_70], 220022h
0x1c0136b66  lea     rax, aHeaderwaittime; "HeaderWaitTimeout"
0x1c0136b6d  jmp     short loc_1C0136B7D
0x1c0136b6f  mov     dword ptr [rbp+57h+var_70], 2A002Ah
0x1c0136b76  lea     rax, aIdleconnection; "IdleConnectionTimeout"
0x1c0136b7d  and     dword ptr [rbp+57h+var_70+4], 0
0x1c0136b81  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1c0136b85  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1c0136b89  mov     qword ptr [rbp+57h+var_70+8], rax
0x1c0136b8d  movaps  xmm0, [rbp+57h+var_70]
0x1c0136b91  movdqa  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x1c0136b96  test    sil, sil
0x1c0136b99  jz      short loc_1C0136BA9
0x1c0136b9b  call    cs:__imp_ZwDeleteValueKey
0x1c0136ba2  nop     dword ptr [rax+rax+00h]
0x1c0136ba7  jmp     short loc_1C0136BCC
0x1c0136ba9  mov     r9d, 4; Type
0x1c0136baf  lea     rax, [rbp+57h+arg_10]
0x1c0136bb3  mov     [rsp+28h], r9d; DataSize
0x1c0136bb8  xor     r8d, r8d; TitleIndex
0x1c0136bbb  mov     [rsp+0A0h+Data], rax; Data
0x1c0136bc0  call    cs:__imp_ZwSetValueKey
0x1c0136bc7  nop     dword ptr [rax+rax+00h]
0x1c0136bcc  mov     edi, eax
0x1c0136bce  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1c0136bd2  test    rcx, rcx
0x1c0136bd5  jz      short loc_1C0136BE3
0x1c0136bd7  call    cs:__imp_ZwClose
0x1c0136bde  nop     dword ptr [rax+rax+00h]
0x1c0136be3  mov     rbx, [rsp+0A0h+arg_8]
0x1c0136beb  mov     eax, edi
0x1c0136bed  add     rsp, 90h
0x1c0136bf4  pop     rdi
0x1c0136bf5  pop     rsi
0x1c0136bf6  pop     rbp
0x1c0136bf7  retn
```
