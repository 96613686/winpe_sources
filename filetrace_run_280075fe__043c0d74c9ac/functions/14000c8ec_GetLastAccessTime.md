# GetLastAccessTime

- ea: `0x14000c8ec`
- end: `0x14000c98a`
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
- `0x14000c8ec`

## import_xrefs

- `FLTMGR!FltQueryInformationFile` at `0x14000c95a`
- `FLTMGR!FltQueryInformationFile` at `0x14000c95a`

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
0x14000c8ec  push    rbx
0x14000c8ee  sub     rsp, 60h
0x14000c8f2  mov     rax, cs:WmiRegistrationContext.DeviceExtension
0x14000c8f9  xor     rax, rsp
0x14000c8fc  mov     [rsp+68h+var_10], rax
0x14000c901  xor     eax, eax
0x14000c903  xorps   xmm0, xmm0
0x14000c906  mov     [rsp+68h+var_18], rax
0x14000c90b  mov     rbx, r8
0x14000c90e  mov     r10, rdx
0x14000c911  movups  [rsp+68h+FileInformation], xmm0
0x14000c916  movups  [rsp+68h+var_28], xmm0
0x14000c91b  test    r8, r8
0x14000c91e  jnz     short loc_14000C927
0x14000c920  mov     eax, 0C000000Dh
0x14000c925  jmp     short loc_14000C976
0x14000c927  mov     rax, [rcx+10h]
0x14000c92b  xor     edx, edx
0x14000c92d  mov     r8, [rax+8]
0x14000c931  test    r8, r8
0x14000c934  jz      short loc_14000C974
0x14000c936  cmp     [r8+18h], rdx
0x14000c93a  jz      short loc_14000C974
0x14000c93c  mov     rcx, [r10+18h]; Instance
0x14000c940  lea     r9d, [rdx+28h]; Length
0x14000c944  mov     [rsp+68h+LengthReturned], rdx; LengthReturned
0x14000c949  lea     r8, [rsp+68h+FileInformation]; FileInformation
0x14000c94e  mov     rdx, [r10+20h]; FileObject
0x14000c952  mov     [rsp+68h+FileInformationClass], 4; FileInformationClass
0x14000c95a  call    cs:__imp_FltQueryInformationFile
0x14000c961  nop     dword ptr [rax+rax+00h]
0x14000c966  mov     edx, eax
0x14000c968  test    eax, eax
0x14000c96a  js      short loc_14000C974
0x14000c96c  mov     rcx, qword ptr [rsp+68h+FileInformation+8]
0x14000c971  mov     [rbx], rcx
0x14000c974  mov     eax, edx
0x14000c976  mov     rcx, [rsp+68h+var_10]
0x14000c97b  xor     rcx, rsp; StackCookie
0x14000c97e  call    __security_check_cookie
0x14000c983  add     rsp, 60h
0x14000c987  pop     rbx
0x14000c988  retn
```
