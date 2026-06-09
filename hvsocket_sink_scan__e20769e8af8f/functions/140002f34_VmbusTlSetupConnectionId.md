# VmbusTlSetupConnectionId

- ea: `0x140002f34`
- end: `0x140002ff4`
- name: `VmbusTlSetupConnectionId`
- size: `192`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14001cf60`
- `0x140024cf0`
- `0x140025610`
- `0x140026330`

## callees

- `0x140002f34`
- `0x140007034`
- `0x14000975c`
- `0x14000bfa0`
- `0x14000c0a0`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x140002f7d`
- `ntoskrnl!ExUuidCreate` at `0x140002f7d`

## pseudocode

```c
__int64 __fastcall VmbusTlSetupConnectionId(__int64 a1)
{
  NTSTATUS v2; // eax
  int v3; // ebx
  __int64 v4; // r8
  __int64 v5; // rdx
  UUID Buf1; // [rsp+20h] [rbp-28h] BYREF

  Buf1 = *(UUID *)(a1 + 464);
  if ( !memcmp(&Buf1, &HV_GUID_ZERO, 0x10u) && (v2 = ExUuidCreate(&Buf1), v3 = v2, v2 < 0) )
  {
    if ( (unsigned int)dword_140013058 > 2 )
    {
      v4 = (unsigned int)v2;
      v5 = 527;
LABEL_8:
      HvsocketTraceEndpointError("VmbusTlSetupConnectionId", v5, v4, a1);
    }
  }
  else
  {
    v3 = VmbusTlSetEndpointId(a1, &Buf1);
    if ( v3 < 0 && (unsigned int)dword_140013058 > 2 )
    {
      v4 = (unsigned int)v3;
      v5 = 535;
      goto LABEL_8;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140002f34  mov     [rsp+arg_8], rbx
0x140002f39  push    rdi
0x140002f3a  sub     rsp, 40h
0x140002f3e  mov     rax, cs:__security_cookie
0x140002f45  xor     rax, rsp
0x140002f48  mov     [rsp+48h+var_18], rax
0x140002f4d  movups  xmm0, xmmword ptr [rcx+1D0h]
0x140002f54  mov     rdi, rcx
0x140002f57  lea     rdx, HV_GUID_ZERO; Buf2
0x140002f5e  mov     r8d, 10h; Size
0x140002f64  lea     rcx, [rsp+48h+Buf1]; Buf1
0x140002f69  movdqu  [rsp+48h+Buf1], xmm0
0x140002f6f  call    memcmp
0x140002f74  test    eax, eax
0x140002f76  jnz     short loc_140002FA4
0x140002f78  lea     rcx, [rsp+48h+Buf1]; Uuid
0x140002f7d  call    cs:__imp_ExUuidCreate
0x140002f84  nop     dword ptr [rax+rax+00h]
0x140002f89  mov     ebx, eax
0x140002f8b  test    eax, eax
0x140002f8d  jns     short loc_140002FA4
0x140002f8f  mov     ecx, cs:dword_140013058
0x140002f95  cmp     ecx, 2
0x140002f98  jbe     short loc_140002FD9
0x140002f9a  mov     r8d, eax
0x140002f9d  mov     edx, 20Fh
0x140002fa2  jmp     short loc_140002FCA
0x140002fa4  lea     rdx, [rsp+48h+Buf1]
0x140002fa9  mov     rcx, rdi
0x140002fac  call    VmbusTlSetEndpointId
0x140002fb1  mov     ebx, eax
0x140002fb3  test    eax, eax
0x140002fb5  jns     short loc_140002FD9
0x140002fb7  mov     eax, cs:dword_140013058
0x140002fbd  cmp     eax, 2
0x140002fc0  jbe     short loc_140002FD9
0x140002fc2  mov     r8d, ebx
0x140002fc5  mov     edx, 217h
0x140002fca  mov     r9, rdi
0x140002fcd  lea     rcx, aVmbustlsetupco_0; "VmbusTlSetupConnectionId"
0x140002fd4  call    HvsocketTraceEndpointError
0x140002fd9  mov     eax, ebx
0x140002fdb  mov     rcx, [rsp+48h+var_18]
0x140002fe0  xor     rcx, rsp; StackCookie
0x140002fe3  call    __security_check_cookie
0x140002fe8  mov     rbx, [rsp+48h+arg_8]
0x140002fed  add     rsp, 40h
0x140002ff1  pop     rdi
0x140002ff2  retn
```
