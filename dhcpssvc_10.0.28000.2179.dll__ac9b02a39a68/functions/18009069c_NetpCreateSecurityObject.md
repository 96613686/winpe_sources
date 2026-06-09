# NetpCreateSecurityObject

- ea: `0x18009069c`
- end: `0x180090784`
- name: `NetpCreateSecurityObject`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002318`

## callees

- `0x180090328`
- `0x18009069c`

## import_xrefs

- `ntdll!NtClose` at `0x180090756`
- `ntdll!NtClose` at `0x180090756`
- `ntdll!RtlNewSecurityObject` at `0x180090743`
- `ntdll!RtlNewSecurityObject` at `0x180090743`
- `ntdll!NtOpenProcessToken` at `0x1800906ed`
- `ntdll!NtOpenProcessToken` at `0x1800906ed`
- `KERNEL32!LocalFree` at `0x180090709`
- `KERNEL32!LocalFree` at `0x18009076a`
- `KERNEL32!LocalFree` at `0x180090709`
- `KERNEL32!LocalFree` at `0x18009076a`

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
0x18009069c  mov     r11, rsp
0x18009069f  mov     [r11+8], rbx
0x1800906a3  mov     [r11+20h], r9
0x1800906a7  mov     [r11+18h], r8
0x1800906ab  push    rdi
0x1800906ac  sub     rsp, 30h
0x1800906b0  mov     r8, cs:DhcpServiceSid
0x1800906b7  lea     rax, [r11+20h]
0x1800906bb  mov     r9, r8
0x1800906be  mov     qword ptr [r11+20h], 0
0x1800906c6  mov     qword ptr [r11+18h], 0
0x1800906ce  mov     [r11-18h], rax
0x1800906d2  call    NetpCreateSecurityDescriptor
0x1800906d7  test    eax, eax
0x1800906d9  js      loc_180090778
0x1800906df  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800906e4  mov     edx, 8; DesiredAccess
0x1800906e9  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800906ed  call    cs:__imp_NtOpenProcessToken
0x1800906f4  nop     dword ptr [rax+rax+00h]
0x1800906f9  mov     ebx, eax
0x1800906fb  test    eax, eax
0x1800906fd  jns     short loc_180090719
0x1800906ff  mov     rcx, [rsp+38h+hMem]; hMem
0x180090704  test    rcx, rcx
0x180090707  jz      short loc_180090715
0x180090709  call    cs:__imp_LocalFree
0x180090710  nop     dword ptr [rax+rax+00h]
0x180090715  mov     eax, ebx
0x180090717  jmp     short loc_180090778
0x180090719  mov     rbx, [rsp+38h+hMem]
0x18009071e  lea     rax, DhcpGlobalServiceGenericInfoMapping
0x180090725  mov     [rsp+38h+GenericMapping], rax; GenericMapping
0x18009072a  lea     r8, DhcpGlobalServiceSecurityDescriptor; NewDescriptor
0x180090731  mov     rax, [rsp+38h+TokenHandle]
0x180090736  xor     r9d, r9d; IsDirectoryObject
0x180090739  mov     rdx, rbx; CreatorDescriptor
0x18009073c  mov     [rsp+38h+Token], rax; Token
0x180090741  xor     ecx, ecx; ParentDescriptor
0x180090743  call    cs:__imp_RtlNewSecurityObject
0x18009074a  nop     dword ptr [rax+rax+00h]
0x18009074f  mov     rcx, [rsp+38h+TokenHandle]; Handle
0x180090754  mov     edi, eax
0x180090756  call    cs:__imp_NtClose
0x18009075d  nop     dword ptr [rax+rax+00h]
0x180090762  test    rbx, rbx
0x180090765  jz      short loc_180090776
0x180090767  mov     rcx, rbx; hMem
0x18009076a  call    cs:__imp_LocalFree
0x180090771  nop     dword ptr [rax+rax+00h]
0x180090776  mov     eax, edi
0x180090778  mov     rbx, [rsp+38h+arg_0]
0x18009077d  add     rsp, 30h
0x180090781  pop     rdi
0x180090782  retn
```
