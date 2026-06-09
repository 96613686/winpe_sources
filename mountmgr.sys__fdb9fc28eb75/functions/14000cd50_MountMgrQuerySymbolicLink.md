# MountMgrQuerySymbolicLink

- ea: `0x14000cd50`
- end: `0x14000ce7e`
- name: `MountMgrQuerySymbolicLink`
- size: `302`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000e340`
- `0x14000ecbc`

## callees

- `0x140001ae0`
- `0x14000cd50`

## import_xrefs

- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x14000cded`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x14000cded`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x14000cd98`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x14000cd98`
- `ntoskrnl!ZwClose` at `0x14000ce2f`
- `ntoskrnl!ZwClose` at `0x14000ce2f`

## pseudocode

```c
__int64 __fastcall MountMgrQuerySymbolicLink(struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2)
{
  NTSTATUS v3; // eax
  __int64 v4; // r8
  int v5; // ebx
  NTSTATUS SymbolicLinkObject; // eax
  __int64 v7; // r8
  unsigned int Length; // ecx
  PWSTR Buffer; // rdx
  unsigned __int64 v10; // rcx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  void *LinkHandle; // [rsp+60h] [rbp+10h] BYREF

  ObjectAttributes.ObjectName = a1;
  LinkHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = ZwOpenSymbolicLinkObject(&LinkHandle, 0x80000000, &ObjectAttributes);
  v5 = v3;
  if ( v3 >= 0 )
  {
    SymbolicLinkObject = ZwQuerySymbolicLinkObject(LinkHandle, a2, 0);
    v5 = SymbolicLinkObject;
    if ( SymbolicLinkObject < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 254, v7, (unsigned int)SymbolicLinkObject);
    }
    ZwClose(LinkHandle);
    if ( v5 >= 0 )
    {
      Length = a2->Length;
      if ( Length > 2 )
      {
        Buffer = a2->Buffer;
        if ( Buffer[((unsigned __int64)a2->Length >> 1) - 1] == 92 )
        {
          v10 = (unsigned __int16)(Length - 2);
          a2->Length = v10;
          Buffer[v10 >> 1] = 0;
        }
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 253, v4, (unsigned int)v3);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000cd50  mov     [rsp-8+arg_8], rbx
0x14000cd55  mov     [rsp-8+arg_10], rdi
0x14000cd5a  push    rbp
0x14000cd5b  mov     rbp, rsp
0x14000cd5e  sub     rsp, 50h
0x14000cd62  xor     eax, eax
0x14000cd64  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x14000cd68  mov     rdi, rdx
0x14000cd6b  mov     [rbp+LinkHandle], rax
0x14000cd6f  xorps   xmm0, xmm0
0x14000cd72  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x14000cd76  mov     edx, 80000000h; DesiredAccess
0x14000cd7b  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000cd83  lea     rcx, [rbp+LinkHandle]; LinkHandle
0x14000cd87  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14000cd8f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000cd93  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000cd98  call    cs:__imp_ZwOpenSymbolicLinkObject
0x14000cd9f  nop     dword ptr [rax+rax+00h]
0x14000cda4  mov     ebx, eax
0x14000cda6  test    eax, eax
0x14000cda8  jns     short loc_14000CDE3
0x14000cdaa  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cdb1  lea     rdx, WPP_GLOBAL_Control
0x14000cdb8  cmp     rcx, rdx
0x14000cdbb  jz      loc_14000CE6B
0x14000cdc1  mov     edx, [rcx+2Ch]
0x14000cdc4  test    dl, 1
0x14000cdc7  jz      loc_14000CE6B
0x14000cdcd  mov     rcx, [rcx+18h]
0x14000cdd1  mov     edx, 0FDh
0x14000cdd6  mov     r9d, eax
0x14000cdd9  call    WPP_SF_L
0x14000cdde  jmp     loc_14000CE6B
0x14000cde3  mov     rcx, [rbp+LinkHandle]; LinkHandle
0x14000cde7  xor     r8d, r8d; ReturnedLength
0x14000cdea  mov     rdx, rdi; LinkTarget
0x14000cded  call    cs:__imp_ZwQuerySymbolicLinkObject
0x14000cdf4  nop     dword ptr [rax+rax+00h]
0x14000cdf9  mov     ebx, eax
0x14000cdfb  test    eax, eax
0x14000cdfd  jns     short loc_14000CE2B
0x14000cdff  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ce06  lea     rdx, WPP_GLOBAL_Control
0x14000ce0d  cmp     rcx, rdx
0x14000ce10  jz      short loc_14000CE2B
0x14000ce12  mov     edx, [rcx+2Ch]
0x14000ce15  test    dl, 1
0x14000ce18  jz      short loc_14000CE2B
0x14000ce1a  mov     rcx, [rcx+18h]
0x14000ce1e  mov     edx, 0FEh
0x14000ce23  mov     r9d, eax
0x14000ce26  call    WPP_SF_L
0x14000ce2b  mov     rcx, [rbp+LinkHandle]; Handle
0x14000ce2f  call    cs:__imp_ZwClose
0x14000ce36  nop     dword ptr [rax+rax+00h]
0x14000ce3b  test    ebx, ebx
0x14000ce3d  js      short loc_14000CE6B
0x14000ce3f  movzx   ecx, word ptr [rdi]
0x14000ce42  cmp     ecx, 2
0x14000ce45  jbe     short loc_14000CE6B
0x14000ce47  mov     rdx, [rdi+8]
0x14000ce4b  mov     eax, ecx
0x14000ce4d  shr     rax, 1
0x14000ce50  cmp     word ptr [rdx+rax*2-2], 5Ch ; '\'
0x14000ce56  jnz     short loc_14000CE6B
0x14000ce58  sub     cx, 2
0x14000ce5c  movzx   ecx, cx
0x14000ce5f  mov     [rdi], cx
0x14000ce62  shr     rcx, 1
0x14000ce65  xor     eax, eax
0x14000ce67  mov     [rdx+rcx*2], ax
0x14000ce6b  mov     rdi, [rsp+50h+arg_10]
0x14000ce70  mov     eax, ebx
0x14000ce72  mov     rbx, [rsp+50h+arg_8]
0x14000ce77  add     rsp, 50h
0x14000ce7b  pop     rbp
0x14000ce7c  retn
```
