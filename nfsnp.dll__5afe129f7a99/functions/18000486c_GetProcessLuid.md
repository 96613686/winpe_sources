# GetProcessLuid

- ea: `0x18000486c`
- end: `0x18000490d`
- name: `GetProcessLuid`
- size: `161`
- prototype: `__int64 __fastcall(PLUID DestinationLuid)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008b28`

## callees

- `0x18000486c`
- `0x180012e70`

## import_xrefs

- `ntdll!RtlCopyLuid` at `0x1800048e0`
- `ntdll!RtlCopyLuid` at `0x1800048e0`
- `ntdll!NtQueryInformationToken` at `0x1800048c6`
- `ntdll!NtQueryInformationToken` at `0x1800048c6`

## pseudocode

```c
__int64 __fastcall GetProcessLuid(PLUID DestinationLuid)
{
  NTSTATUS v2; // ebx
  ULONG v4; // [rsp+30h] [rbp-58h] BYREF
  _LUID SourceLuid[2]; // [rsp+38h] [rbp-50h] BYREF
  __int128 v6; // [rsp+48h] [rbp-40h]
  __int128 v7; // [rsp+58h] [rbp-30h]
  __int64 v8; // [rsp+68h] [rbp-20h]

  *(_OWORD *)&SourceLuid[0].LowPart = 0;
  v4 = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v2 = NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenStatistics, SourceLuid, 0x38u, &v4);
  if ( v2 >= 0 )
    RtlCopyLuid(DestinationLuid, &SourceLuid[1]);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000486c  mov     r11, rsp
0x18000486f  mov     [r11+10h], rbx
0x180004873  push    rdi
0x180004874  sub     rsp, 80h
0x18000487b  mov     rax, cs:__security_cookie
0x180004882  xor     rax, rsp
0x180004885  mov     [rsp+88h+var_18], rax
0x18000488a  xorps   xmm0, xmm0
0x18000488d  lea     r8, [r11-50h]; TokenInformation
0x180004891  xor     eax, eax
0x180004893  mov     r9d, 38h ; '8'; TokenInformationLength
0x180004899  movups  xmmword ptr [rsp+88h+SourceLuid.LowPart], xmm0
0x18000489e  mov     [rsp+88h+var_58], eax
0x1800048a2  mov     rdi, rcx
0x1800048a5  movups  [rsp+88h+var_40], xmm0
0x1800048aa  lea     edx, [r9-2Eh]; TokenInformationClass
0x1800048ae  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x1800048b5  movups  [rsp+88h+var_30], xmm0
0x1800048ba  mov     [r11-20h], rax
0x1800048be  lea     rax, [r11-58h]
0x1800048c2  mov     [r11-68h], rax
0x1800048c6  call    cs:__imp_NtQueryInformationToken
0x1800048cd  nop     dword ptr [rax+rax+00h]
0x1800048d2  mov     ebx, eax
0x1800048d4  test    eax, eax
0x1800048d6  js      short loc_1800048EC
0x1800048d8  lea     rdx, [rsp+88h+SourceLuid.LowPart+8]; SourceLuid
0x1800048dd  mov     rcx, rdi; DestinationLuid
0x1800048e0  call    cs:__imp_RtlCopyLuid
0x1800048e7  nop     dword ptr [rax+rax+00h]
0x1800048ec  mov     eax, ebx
0x1800048ee  mov     rcx, [rsp+88h+var_18]
0x1800048f3  xor     rcx, rsp; StackCookie
0x1800048f6  call    __security_check_cookie
0x1800048fb  mov     rbx, [rsp+88h+arg_8]
0x180004903  add     rsp, 80h
0x18000490a  pop     rdi
0x18000490b  retn
```
