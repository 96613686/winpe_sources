# GetLastAccessTime

- ea: `0x14000c8b8`
- end: `0x14000c956`
- name: `GetLastAccessTime`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400010b0`
- `0x140002110`

## callees

- `0x140003510`
- `0x14000c8b8`

## import_xrefs

- `FLTMGR!FltQueryInformationFile` at `0x14000c926`
- `FLTMGR!FltQueryInformationFile` at `0x14000c926`

## pseudocode

```c
__int64 __fastcall GetLastAccessTime(__int64 a1, __int64 a2, _QWORD *a3)
{
  NTSTATUS InformationFile; // edx
  __int64 v7; // r8
  _OWORD FileInformation[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v9; // [rsp+50h] [rbp-18h]

  v9 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  if ( !a3 )
    return 3221225485LL;
  InformationFile = 0;
  v7 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL);
  if ( v7 && *(_QWORD *)(v7 + 24) )
  {
    InformationFile = FltQueryInformationFile(
                        *(PFLT_INSTANCE *)(a2 + 24),
                        *(PFILE_OBJECT *)(a2 + 32),
                        FileInformation,
                        0x28u,
                        FileBasicInformation,
                        0);
    if ( InformationFile >= 0 )
      *a3 = *((_QWORD *)&FileInformation[0] + 1);
  }
  return (unsigned int)InformationFile;
}

```

## disassembly

```asm
0x14000c8b8  push    rbx
0x14000c8ba  sub     rsp, 60h
0x14000c8be  mov     rax, cs:WmiRegistrationContext.DeviceExtension
0x14000c8c5  xor     rax, rsp
0x14000c8c8  mov     [rsp+68h+var_10], rax
0x14000c8cd  xor     eax, eax
0x14000c8cf  xorps   xmm0, xmm0
0x14000c8d2  mov     [rsp+68h+var_18], rax
0x14000c8d7  mov     rbx, r8
0x14000c8da  mov     r10, rdx
0x14000c8dd  movups  [rsp+68h+FileInformation], xmm0
0x14000c8e2  movups  [rsp+68h+var_28], xmm0
0x14000c8e7  test    r8, r8
0x14000c8ea  jnz     short loc_14000C8F3
0x14000c8ec  mov     eax, 0C000000Dh
0x14000c8f1  jmp     short loc_14000C942
0x14000c8f3  mov     rax, [rcx+10h]
0x14000c8f7  xor     edx, edx
0x14000c8f9  mov     r8, [rax+8]
0x14000c8fd  test    r8, r8
0x14000c900  jz      short loc_14000C940
0x14000c902  cmp     [r8+18h], rdx
0x14000c906  jz      short loc_14000C940
0x14000c908  mov     rcx, [r10+18h]; Instance
0x14000c90c  lea     r9d, [rdx+28h]; Length
0x14000c910  mov     [rsp+68h+LengthReturned], rdx; LengthReturned
0x14000c915  lea     r8, [rsp+68h+FileInformation]; FileInformation
0x14000c91a  mov     rdx, [r10+20h]; FileObject
0x14000c91e  mov     [rsp+68h+FileInformationClass], 4; FileInformationClass
0x14000c926  call    cs:__imp_FltQueryInformationFile
0x14000c92d  nop     dword ptr [rax+rax+00h]
0x14000c932  mov     edx, eax
0x14000c934  test    eax, eax
0x14000c936  js      short loc_14000C940
0x14000c938  mov     rcx, qword ptr [rsp+68h+FileInformation+8]
0x14000c93d  mov     [rbx], rcx
0x14000c940  mov     eax, edx
0x14000c942  mov     rcx, [rsp+68h+var_10]
0x14000c947  xor     rcx, rsp; StackCookie
0x14000c94a  call    __security_check_cookie
0x14000c94f  add     rsp, 60h
0x14000c953  pop     rbx
0x14000c954  retn
```
