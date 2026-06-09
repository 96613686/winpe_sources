# NetpCreateSecurityObject

- ea: `0x1800904f8`
- end: `0x1800905da`
- name: `NetpCreateSecurityObject`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002324`

## callees

- `0x180090198`
- `0x1800904f8`

## import_xrefs

- `ntdll!NtClose` at `0x1800905ac`
- `ntdll!NtClose` at `0x1800905ac`
- `ntdll!RtlNewSecurityObject` at `0x180090599`
- `ntdll!RtlNewSecurityObject` at `0x180090599`
- `ntdll!NtOpenProcessToken` at `0x180090543`
- `ntdll!NtOpenProcessToken` at `0x180090543`
- `KERNEL32!LocalFree` at `0x18009055f`
- `KERNEL32!LocalFree` at `0x1800905c0`
- `KERNEL32!LocalFree` at `0x18009055f`
- `KERNEL32!LocalFree` at `0x1800905c0`

## pseudocode

```c
__int64 __fastcall NetpCreateSecurityObject(__int64 a1, unsigned int a2)
{
  __int64 result; // rax
  NTSTATUS v3; // ebx
  HLOCAL v4; // rbx
  unsigned int v5; // edi
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp+20h] BYREF

  hMem = 0;
  TokenHandle = 0;
  result = NetpCreateSecurityDescriptor(a1, a2, DhcpServiceSid, DhcpServiceSid, (struct _ACL **)&hMem);
  if ( (int)result >= 0 )
  {
    v3 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
    if ( v3 >= 0 )
    {
      v4 = hMem;
      v5 = RtlNewSecurityObject(
             0,
             hMem,
             &DhcpGlobalServiceSecurityDescriptor,
             0,
             TokenHandle,
             &DhcpGlobalServiceGenericInfoMapping);
      NtClose(TokenHandle);
      if ( v4 )
        LocalFree(v4);
      return v5;
    }
    else
    {
      if ( hMem )
        LocalFree(hMem);
      return (unsigned int)v3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800904f8  mov     r11, rsp
0x1800904fb  mov     [r11+8], rbx
0x1800904ff  mov     [r11+20h], r9
0x180090503  mov     [r11+18h], r8
0x180090507  push    rdi
0x180090508  sub     rsp, 30h
0x18009050c  mov     r8, cs:DhcpServiceSid
0x180090513  lea     rax, [r11+20h]
0x180090517  and     qword ptr [r11+20h], 0
0x18009051c  mov     r9, r8
0x18009051f  and     qword ptr [r11+18h], 0
0x180090524  mov     [r11-18h], rax
0x180090528  call    NetpCreateSecurityDescriptor
0x18009052d  test    eax, eax
0x18009052f  js      loc_1800905CE
0x180090535  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18009053a  mov     edx, 8; DesiredAccess
0x18009053f  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180090543  call    cs:__imp_NtOpenProcessToken
0x18009054a  nop     dword ptr [rax+rax+00h]
0x18009054f  mov     ebx, eax
0x180090551  test    eax, eax
0x180090553  jns     short loc_18009056F
0x180090555  mov     rcx, [rsp+38h+hMem]; hMem
0x18009055a  test    rcx, rcx
0x18009055d  jz      short loc_18009056B
0x18009055f  call    cs:__imp_LocalFree
0x180090566  nop     dword ptr [rax+rax+00h]
0x18009056b  mov     eax, ebx
0x18009056d  jmp     short loc_1800905CE
0x18009056f  mov     rbx, [rsp+38h+hMem]
0x180090574  lea     rax, DhcpGlobalServiceGenericInfoMapping
0x18009057b  mov     [rsp+38h+GenericMapping], rax; GenericMapping
0x180090580  lea     r8, DhcpGlobalServiceSecurityDescriptor; NewDescriptor
0x180090587  mov     rax, [rsp+38h+TokenHandle]
0x18009058c  xor     r9d, r9d; IsDirectoryObject
0x18009058f  mov     rdx, rbx; CreatorDescriptor
0x180090592  mov     [rsp+38h+Token], rax; Token
0x180090597  xor     ecx, ecx; ParentDescriptor
0x180090599  call    cs:__imp_RtlNewSecurityObject
0x1800905a0  nop     dword ptr [rax+rax+00h]
0x1800905a5  mov     rcx, [rsp+38h+TokenHandle]; Handle
0x1800905aa  mov     edi, eax
0x1800905ac  call    cs:__imp_NtClose
0x1800905b3  nop     dword ptr [rax+rax+00h]
0x1800905b8  test    rbx, rbx
0x1800905bb  jz      short loc_1800905CC
0x1800905bd  mov     rcx, rbx; hMem
0x1800905c0  call    cs:__imp_LocalFree
0x1800905c7  nop     dword ptr [rax+rax+00h]
0x1800905cc  mov     eax, edi
0x1800905ce  mov     rbx, [rsp+38h+arg_0]
0x1800905d3  add     rsp, 30h
0x1800905d7  pop     rdi
0x1800905d8  retn
```
