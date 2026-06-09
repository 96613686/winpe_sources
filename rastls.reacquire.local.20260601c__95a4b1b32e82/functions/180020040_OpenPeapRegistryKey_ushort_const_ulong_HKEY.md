# OpenPeapRegistryKey(ushort const *,ulong,HKEY__ * *)

- ea: `0x180020040`
- end: `0x180020134`
- name: `?OpenPeapRegistryKey@@YAKPEBGKPEAPEAUHKEY__@@@Z`
- size: `244`
- prototype: `unsigned int(const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180005f80`
- `0x18005c4f0`

## callees

- `0x180011cc8`
- `0x180020040`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002011a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002011a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800200cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800200cc`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x180020069`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x180020069`

## string_xrefs

- `0x1800200b7`: `System\CurrentControlSet\Services\Rasman\PPP\EAP\25`
- `0x1800200f5`: `System\CurrentControlSet\Services\Rasman\PPP\EAP\25`

## pseudocode

```c
__int64 __fastcall OpenPeapRegistryKey(const unsigned __int16 *a1, __int64 a2, HKEY *a3)
{
  unsigned int v4; // edi
  unsigned int v6; // ebx
  HKEY phkResult; // [rsp+40h] [rbp+8h] BYREF

  phkResult = 0;
  v4 = RegConnectRegistryW(0, HKEY_LOCAL_MACHINE, &phkResult);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)&WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids,
        (unsigned int)L"NULL",
        v4);
    return v4;
  }
  else
  {
    v6 = RegOpenKeyExW(phkResult, L"System\\CurrentControlSet\\Services\\Rasman\\PPP\\EAP\\25", 0, 0x20019u, a3);
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)&WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids,
          (unsigned int)L"System\\CurrentControlSet\\Services\\Rasman\\PPP\\EAP\\25",
          v6);
    }
    else
    {
      v6 = 0;
    }
    RegCloseKey(phkResult);
    return v6;
  }
}

```

## disassembly

```asm
0x180020040  mov     [rsp+arg_8], rbx
0x180020045  mov     [rsp+phkResult], rcx
0x18002004a  push    rdi
0x18002004b  sub     rsp, 30h
0x18002004f  mov     rbx, r8
0x180020052  mov     [rsp+38h+phkResult], 0
0x18002005b  lea     r8, [rsp+38h+phkResult]; phkResult
0x180020060  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180020067  xor     ecx, ecx; lpMachineName
0x180020069  call    cs:__imp_RegConnectRegistryW
0x180020070  nop     dword ptr [rax+rax+00h]
0x180020075  mov     edi, eax
0x180020077  test    eax, eax
0x180020079  jz      short loc_1800200B2
0x18002007b  mov     rcx, cs:WPP_GLOBAL_Control
0x180020082  lea     rax, WPP_GLOBAL_Control
0x180020089  cmp     rcx, rax
0x18002008c  jz      short loc_1800200AE
0x18002008e  mov     rcx, [rcx+10h]
0x180020092  lea     r9, aNull_0; "NULL"
0x180020099  mov     edx, 0Ch
0x18002009e  mov     dword ptr [rsp+38h+var_18], edi
0x1800200a2  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x1800200a9  call    WPP_SF_Sd
0x1800200ae  mov     eax, edi
0x1800200b0  jmp     short loc_180020128
0x1800200b2  mov     rcx, [rsp+38h+phkResult]; hKey
0x1800200b7  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Ra"...
0x1800200be  mov     r9d, 20019h; samDesired
0x1800200c4  mov     [rsp+38h+var_18], rbx; phkResult
0x1800200c9  xor     r8d, r8d; ulOptions
0x1800200cc  call    cs:__imp_RegOpenKeyExW
0x1800200d3  nop     dword ptr [rax+rax+00h]
0x1800200d8  mov     ebx, eax
0x1800200da  test    eax, eax
0x1800200dc  jz      short loc_180020113
0x1800200de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800200e5  lea     rax, WPP_GLOBAL_Control
0x1800200ec  cmp     rcx, rax
0x1800200ef  jz      short loc_180020115
0x1800200f1  mov     rcx, [rcx+10h]
0x1800200f5  lea     r9, SubKey; "System\\CurrentControlSet\\Services\\Ra"...
0x1800200fc  mov     edx, 0Dh
0x180020101  mov     dword ptr [rsp+38h+var_18], ebx
0x180020105  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18002010c  call    WPP_SF_Sd
0x180020111  jmp     short loc_180020115
0x180020113  xor     ebx, ebx
0x180020115  mov     rcx, [rsp+38h+phkResult]; hKey
0x18002011a  call    cs:__imp_RegCloseKey
0x180020121  nop     dword ptr [rax+rax+00h]
0x180020126  mov     eax, ebx
0x180020128  mov     rbx, [rsp+38h+arg_8]
0x18002012d  add     rsp, 30h
0x180020131  pop     rdi
0x180020132  retn
```
