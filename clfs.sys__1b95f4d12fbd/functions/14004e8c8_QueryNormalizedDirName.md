# QueryNormalizedDirName

- ea: `0x14004e8c8`
- end: `0x14004ea77`
- name: `QueryNormalizedDirName`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14004e000`

## callees

- `0x140014310`
- `0x14004e8c8`
- `0x14004ea80`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14004ea16`
- `ntoskrnl!ObfDereferenceObject` at `0x14008083e`
- `ntoskrnl!ObfDereferenceObject` at `0x14004ea16`
- `ntoskrnl!ObfDereferenceObject` at `0x14008083e`
- `ntoskrnl!ZwClose` at `0x14004ea2f`
- `ntoskrnl!ZwClose` at `0x14008085e`
- `ntoskrnl!ZwClose` at `0x14004ea2f`
- `ntoskrnl!ZwClose` at `0x14008085e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004e9af`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004e9af`
- `ntoskrnl!ZwCreateFile` at `0x14004e96a`
- `ntoskrnl!ZwCreateFile` at `0x14004e96a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ea56`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008088f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ea56`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008088f`

## pseudocode

```c
__int64 __fastcall QueryNormalizedDirName(UNICODE_STRING *a1, struct _UNICODE_STRING *a2)
{
  PVOID v3; // rsi
  NTSTATUS NormalizedObjectName; // ebx
  wchar_t *Buffer; // rcx
  struct _IO_STATUS_BLOCK v7; // [rsp+70h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES v8; // [rsp+80h] [rbp-48h] BYREF
  HANDLE Handle; // [rsp+E0h] [rbp+18h] BYREF
  PVOID Object; // [rsp+E8h] [rbp+20h] BYREF

  Handle = 0;
  v3 = 0;
  *(&v8.Length + 1) = 0;
  *(_OWORD *)&v8.ObjectName = 0;
  v7.Pointer = 0;
  v7.Information = 0;
  *a2 = 0;
  v8.Length = 48;
  v8.RootDirectory = 0;
  v8.Attributes = 576;
  v8.ObjectName = a1;
  *(_OWORD *)&v8.SecurityDescriptor = 0;
  NormalizedObjectName = ZwCreateFile(&Handle, 0x80u, &v8, &v7, 0, 0x80u, 7u, 1u, 1u, 0, 0);
  if ( NormalizedObjectName >= 0 )
  {
    Object = 0;
    NormalizedObjectName = ObReferenceObjectByHandle(Handle, 1u, 0, 0, &Object, 0);
    v3 = Object;
    if ( NormalizedObjectName >= 0 )
    {
      NormalizedObjectName = QueryNormalizedObjectName(Object, a2);
      if ( NormalizedObjectName >= 0 && a2->Buffer[((unsigned __int64)a2->Length >> 1) - 1] != 92 )
        NormalizedObjectName = RtlUnicodeStringCatString(a2, L"\\");
    }
  }
  if ( v3 )
    ObfDereferenceObject(v3);
  if ( Handle )
  {
    ZwClose(Handle);
    Handle = 0;
  }
  if ( NormalizedObjectName < 0 )
  {
    Buffer = a2->Buffer;
    if ( Buffer )
      ExFreePoolWithTag(Buffer, 0);
    *a2 = 0;
  }
  return (unsigned int)NormalizedObjectName;
}

```

## disassembly

```asm
0x14004e8c8  mov     r11, rsp
0x14004e8cb  mov     [r11+10h], rdx
0x14004e8cf  push    rbx
0x14004e8d0  push    rsi
0x14004e8d1  push    rdi
0x14004e8d2  sub     rsp, 0B0h
0x14004e8d9  mov     rdi, rdx
0x14004e8dc  mov     [rsp+0C8h+var_68], 0
0x14004e8e4  mov     qword ptr [r11+18h], 0
0x14004e8ec  xor     esi, esi
0x14004e8ee  mov     [r11-60h], rsi
0x14004e8f2  xorps   xmm0, xmm0
0x14004e8f5  movups  xmmword ptr [r11-48h], xmm0
0x14004e8fa  movups  xmmword ptr [r11-38h], xmm0
0x14004e8ff  movups  xmmword ptr [r11-28h], xmm0
0x14004e904  mov     [r11-58h], rsi
0x14004e908  xor     eax, eax
0x14004e90a  mov     [r11-50h], rax
0x14004e90e  movdqu  xmmword ptr [rdx], xmm0
0x14004e912  mov     dword ptr [r11-48h], 30h ; '0'
0x14004e91a  mov     [r11-40h], rax
0x14004e91e  mov     dword ptr [r11-30h], 240h
0x14004e926  mov     [r11-38h], rcx
0x14004e92a  movdqu  xmmword ptr [r11-28h], xmm0
0x14004e930  mov     [rsp+0C8h+EaLength], eax; EaLength
0x14004e934  mov     [r11-80h], rax
0x14004e938  mov     [rsp+0C8h+CreateOptions], 1; CreateOptions
0x14004e940  mov     [rsp+0C8h+CreateDisposition], 1; CreateDisposition
0x14004e948  mov     [rsp+0C8h+ShareAccess], 7; ShareAccess
0x14004e950  mov     edx, 80h; DesiredAccess
0x14004e955  mov     [rsp+0C8h+FileAttributes], edx; FileAttributes
0x14004e959  mov     [rsp+0C8h+AllocationSize], rax; AllocationSize
0x14004e95e  lea     r9, [r11-58h]; IoStatusBlock
0x14004e962  lea     r8, [r11-48h]; ObjectAttributes
0x14004e966  lea     rcx, [r11+18h]; FileHandle
0x14004e96a  call    cs:__imp_ZwCreateFile
0x14004e971  nop     dword ptr [rax+rax+00h]
0x14004e976  mov     ebx, eax
0x14004e978  mov     [rsp+0C8h+var_68], eax
0x14004e97c  test    eax, eax
0x14004e97e  js      loc_14004EA0E
0x14004e984  mov     [rsp+0C8h+Object], rsi
0x14004e98c  mov     qword ptr [rsp+0C8h+FileAttributes], rsi; HandleInformation
0x14004e991  lea     rax, [rsp+0C8h+Object]
0x14004e999  mov     [rsp+0C8h+AllocationSize], rax; Object
0x14004e99e  xor     r9d, r9d; AccessMode
0x14004e9a1  xor     r8d, r8d; ObjectType
0x14004e9a4  lea     edx, [rsi+1]; DesiredAccess
0x14004e9a7  mov     rcx, [rsp+0C8h+Handle]; Handle
0x14004e9af  call    cs:__imp_ObReferenceObjectByHandle
0x14004e9b6  nop     dword ptr [rax+rax+00h]
0x14004e9bb  mov     ebx, eax
0x14004e9bd  mov     rsi, [rsp+0C8h+Object]
0x14004e9c5  mov     [rsp+0C8h+var_60], rsi
0x14004e9ca  mov     [rsp+0C8h+var_68], eax
0x14004e9ce  test    eax, eax
0x14004e9d0  js      short loc_14004EA0E
0x14004e9d2  mov     rdx, rdi; Destination
0x14004e9d5  mov     rcx, rsi; Object
0x14004e9d8  call    QueryNormalizedObjectName
0x14004e9dd  mov     ebx, eax
0x14004e9df  mov     [rsp+0C8h+var_68], eax
0x14004e9e3  test    eax, eax
0x14004e9e5  js      short loc_14004EA0E
0x14004e9e7  movzx   ecx, word ptr [rdi]
0x14004e9ea  shr     rcx, 1
0x14004e9ed  mov     rax, [rdi+8]
0x14004e9f1  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14004e9f7  jz      short loc_14004EA0E
0x14004e9f9  lea     rdx, Source; "\\"
0x14004ea00  mov     rcx, rdi; struct _UNICODE_STRING *
0x14004ea03  call    ?RtlUnicodeStringCatString@@YAJPEAU_UNICODE_STRING@@PEBG@Z; RtlUnicodeStringCatString(_UNICODE_STRING *,ushort const *)
0x14004ea08  mov     ebx, eax
0x14004ea0a  mov     [rsp+0C8h+var_68], eax
0x14004ea0e  test    rsi, rsi
0x14004ea11  jz      short loc_14004EA22
0x14004ea13  mov     rcx, rsi; Object
0x14004ea16  call    cs:__imp_ObfDereferenceObject
0x14004ea1d  nop     dword ptr [rax+rax+00h]
0x14004ea22  mov     rcx, [rsp+0C8h+Handle]; Handle
0x14004ea2a  test    rcx, rcx
0x14004ea2d  jz      short loc_14004EA47
0x14004ea2f  call    cs:__imp_ZwClose
0x14004ea36  nop     dword ptr [rax+rax+00h]
0x14004ea3b  mov     [rsp+0C8h+Handle], 0
0x14004ea47  test    ebx, ebx
0x14004ea49  jns     short loc_14004EA69
0x14004ea4b  mov     rcx, [rdi+8]; P
0x14004ea4f  test    rcx, rcx
0x14004ea52  jz      short loc_14004EA62
0x14004ea54  xor     edx, edx; Tag
0x14004ea56  call    cs:__imp_ExFreePoolWithTag
0x14004ea5d  nop     dword ptr [rax+rax+00h]
0x14004ea62  xorps   xmm0, xmm0
0x14004ea65  movdqu  xmmword ptr [rdi], xmm0
0x14004ea69  mov     eax, ebx
0x14004ea6b  add     rsp, 0B0h
0x14004ea72  pop     rdi
0x14004ea73  pop     rsi
0x14004ea74  pop     rbx
0x14004ea75  retn
0x14008082b  push    rbx
0x14008082d  push    rbp
0x14008082e  sub     rsp, 68h
0x140080832  mov     rbp, rdx
0x140080835  mov     rcx, [rbp+68h]; Object
0x140080839  test    rcx, rcx
0x14008083c  jz      short loc_140080852
0x14008083e  call    cs:__imp_ObfDereferenceObject
0x140080845  nop     dword ptr [rax+rax+00h]
0x14008084a  mov     qword ptr [rbp+68h], 0
0x140080852  mov     rcx, [rbp+0E0h]; Handle
0x140080859  test    rcx, rcx
0x14008085c  jz      short loc_140080875
0x14008085e  call    cs:__imp_ZwClose
0x140080865  nop     dword ptr [rax+rax+00h]
0x14008086a  mov     qword ptr [rbp+0E0h], 0
0x140080875  cmp     dword ptr [rbp+60h], 0
0x140080879  jge     short loc_1400808A3
0x14008087b  mov     rbx, [rbp+0D8h]
0x140080882  cmp     qword ptr [rbx+8], 0
0x140080887  jz      short loc_14008089C
0x140080889  xor     edx, edx; Tag
0x14008088b  mov     rcx, [rbx+8]; P
0x14008088f  call    cs:__imp_ExFreePoolWithTag
0x140080896  nop     dword ptr [rax+rax+00h]
0x14008089b  nop
0x14008089c  xorps   xmm0, xmm0
0x14008089f  movdqu  xmmword ptr [rbx], xmm0
0x1400808a3  add     rsp, 68h
0x1400808a7  pop     rbp
0x1400808a8  pop     rbx
0x1400808a9  retn
```
