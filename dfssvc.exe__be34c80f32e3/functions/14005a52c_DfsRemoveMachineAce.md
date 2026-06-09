# DfsRemoveMachineAce

- ea: `0x14005a52c`
- end: `0x14005a6c3`
- name: `DfsRemoveMachineAce`
- size: `407`
- prototype: `__int64 __fastcall(LDAP *ld)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140032efc`

## callees

- `0x140001526`
- `0x140001532`
- `0x140059608`
- `0x14005a2b0`
- `0x14005a3c0`
- `0x14005a52c`
- `0x14005a870`

## import_xrefs

- `ntdll!RtlDnsHostNameToComputerName` at `0x14005a5e8`
- `ntdll!RtlDnsHostNameToComputerName` at `0x14005a5e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005a66d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005a682`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005a696`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005a66d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005a682`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005a696`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14005a636`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14005a636`

## pseudocode

```c
__int64 __fastcall DfsRemoveMachineAce(LDAP *ld, const WCHAR *a2, WCHAR *a3, WCHAR *a4)
{
  PSID v7; // rsi
  unsigned int ObjStringSD; // ebx
  __int64 v9; // rdi
  WCHAR *v10; // r14
  STRSAFE_LPCWSTR v11; // r8
  int v12; // eax
  HLOCAL hMem; // [rsp+20h] [rbp-40h] BYREF
  LPWSTR StringSid; // [rsp+28h] [rbp-38h] BYREF
  PSID Sid; // [rsp+30h] [rbp-30h]
  struct _UNICODE_STRING ComputerName; // [rsp+38h] [rbp-28h] BYREF
  struct _UNICODE_STRING DnsHostName; // [rsp+48h] [rbp-18h] BYREF

  Sid = 0;
  hMem = 0;
  StringSid = 0;
  v7 = 0;
  DnsHostName = 0;
  ComputerName = 0;
  ObjStringSD = DfsGetObjStringSD(ld, a3, &hMem);
  if ( !ObjStringSD )
  {
    v9 = -1;
    do
      ++v9;
    while ( a4[v9] );
    v10 = (WCHAR *)malloc_0(2LL * (unsigned int)(v9 + 2));
    if ( v10 )
    {
      ComputerName.Buffer = v10;
      DnsHostName.Length = 2 * v9;
      ComputerName.Length = 0;
      DnsHostName.MaximumLength = 2 * v9 + 2;
      ComputerName.MaximumLength = 2 * (v9 + 2);
      DnsHostName.Buffer = a4;
      RtlDnsHostNameToComputerName(&ComputerName, &DnsHostName, 0);
      ComputerName.Buffer[(unsigned __int64)ComputerName.Length >> 1] = 0;
      StringCbCatW(v10, (unsigned int)(2 * (v9 + 2)), v11);
      v12 = DfsFindSid(a2, v10);
      v7 = Sid;
      if ( v12 == 1 && ConvertSidToStringSidW(Sid, &StringSid) )
        ObjStringSD = DfsRemoveAce(ld, a3);
      else
        ObjStringSD = 4312;
      free_0(v10);
    }
    else
    {
      ObjStringSD = 14;
    }
  }
  if ( hMem )
    LocalFree(hMem);
  if ( StringSid )
    LocalFree(StringSid);
  if ( v7 )
    LocalFree(v7);
  return ObjStringSD;
}

```

## disassembly

```asm
0x14005a52c  mov     rax, rsp
0x14005a52f  mov     [rax+8], rbx
0x14005a533  mov     [rax+18h], rsi
0x14005a537  mov     [rax+20h], rdi
0x14005a53b  mov     [rax+10h], rdx
0x14005a53f  push    rbp
0x14005a540  push    r12
0x14005a542  push    r13
0x14005a544  push    r14
0x14005a546  push    r15
0x14005a548  mov     rbp, rsp
0x14005a54b  sub     rsp, 60h
0x14005a54f  xor     r14d, r14d
0x14005a552  mov     r15, r8
0x14005a555  xorps   xmm0, xmm0
0x14005a558  mov     [rbp+Sid], r14
0x14005a55c  xorps   xmm1, xmm1
0x14005a55f  mov     [rbp+hMem], r14
0x14005a563  mov     rdx, r15
0x14005a566  mov     [rbp+StringSid], r14
0x14005a56a  lea     r8, [rbp+hMem]
0x14005a56e  mov     r13, r9
0x14005a571  mov     r12, rcx
0x14005a574  mov     esi, r14d
0x14005a577  movups  xmmword ptr [rbp+DnsHostName.Length], xmm0
0x14005a57b  movups  xmmword ptr [rbp+ComputerName.Length], xmm1
0x14005a57f  call    DfsGetObjStringSD
0x14005a584  mov     ebx, eax
0x14005a586  test    eax, eax
0x14005a588  jnz     loc_14005A664
0x14005a58e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14005a592  inc     rdi
0x14005a595  cmp     [r13+rdi*2+0], r14w
0x14005a59b  jnz     short loc_14005A592
0x14005a59d  lea     ebx, [rdi+2]
0x14005a5a0  mov     ecx, ebx
0x14005a5a2  add     rcx, rcx; Size
0x14005a5a5  call    malloc_0
0x14005a5aa  mov     r14, rax
0x14005a5ad  xor     eax, eax
0x14005a5af  test    r14, r14
0x14005a5b2  jnz     short loc_14005A5BC
0x14005a5b4  lea     ebx, [rax+0Eh]
0x14005a5b7  jmp     loc_14005A664
0x14005a5bc  add     di, di
0x14005a5bf  mov     [rbp+ComputerName.Buffer], r14
0x14005a5c3  mov     [rbp+DnsHostName.Length], di
0x14005a5c7  lea     rdx, [rbp+DnsHostName]; DnsHostName
0x14005a5cb  add     di, 2
0x14005a5cf  mov     [rbp+ComputerName.Length], ax
0x14005a5d3  add     ebx, ebx
0x14005a5d5  mov     [rbp+DnsHostName.MaximumLength], di
0x14005a5d9  xor     r8d, r8d; AllocateComputerNameString
0x14005a5dc  mov     [rbp+ComputerName.MaximumLength], bx
0x14005a5e0  lea     rcx, [rbp+ComputerName]; ComputerName
0x14005a5e4  mov     [rbp+DnsHostName.Buffer], r13
0x14005a5e8  call    cs:__imp_RtlDnsHostNameToComputerName
0x14005a5ef  nop     dword ptr [rax+rax+00h]
0x14005a5f4  movzx   ecx, [rbp+ComputerName.Length]
0x14005a5f8  xor     edx, edx
0x14005a5fa  mov     rax, [rbp+ComputerName.Buffer]
0x14005a5fe  shr     rcx, 1
0x14005a601  mov     [rax+rcx*2], dx
0x14005a605  mov     rcx, r14; pszDest
0x14005a608  mov     edx, ebx; cbDest
0x14005a60a  call    StringCbCatW
0x14005a60f  mov     rcx, [rbp+lpSystemName]; lpSystemName
0x14005a613  lea     r8, [rbp+Sid]
0x14005a617  mov     rdx, r14; lpAccountName
0x14005a61a  call    DfsFindSid
0x14005a61f  mov     rsi, [rbp+Sid]
0x14005a623  cmp     eax, 1
0x14005a626  jz      short loc_14005A62F
0x14005a628  mov     ebx, 10D8h
0x14005a62d  jmp     short loc_14005A65C
0x14005a62f  lea     rdx, [rbp+StringSid]; StringSid
0x14005a633  mov     rcx, rsi; Sid
0x14005a636  call    cs:__imp_ConvertSidToStringSidW
0x14005a63d  nop     dword ptr [rax+rax+00h]
0x14005a642  cmp     eax, 1
0x14005a645  jnz     short loc_14005A628
0x14005a647  mov     r9, [rbp+StringSid]
0x14005a64b  mov     rdx, r15; dn
0x14005a64e  mov     r8, [rbp+hMem]
0x14005a652  mov     rcx, r12; ld
0x14005a655  call    DfsRemoveAce
0x14005a65a  mov     ebx, eax
0x14005a65c  mov     rcx, r14; Block
0x14005a65f  call    free_0
0x14005a664  mov     rcx, [rbp+hMem]; hMem
0x14005a668  test    rcx, rcx
0x14005a66b  jz      short loc_14005A679
0x14005a66d  call    cs:__imp_LocalFree
0x14005a674  nop     dword ptr [rax+rax+00h]
0x14005a679  mov     rcx, [rbp+StringSid]; hMem
0x14005a67d  test    rcx, rcx
0x14005a680  jz      short loc_14005A68E
0x14005a682  call    cs:__imp_LocalFree
0x14005a689  nop     dword ptr [rax+rax+00h]
0x14005a68e  test    rsi, rsi
0x14005a691  jz      short loc_14005A6A2
0x14005a693  mov     rcx, rsi; hMem
0x14005a696  call    cs:__imp_LocalFree
0x14005a69d  nop     dword ptr [rax+rax+00h]
0x14005a6a2  lea     r11, [rsp+60h+var_s0]
0x14005a6a7  mov     eax, ebx
0x14005a6a9  mov     rbx, [r11+30h]
0x14005a6ad  mov     rsi, [r11+40h]
0x14005a6b1  mov     rdi, [r11+48h]
0x14005a6b5  mov     rsp, r11
0x14005a6b8  pop     r15
0x14005a6ba  pop     r14
0x14005a6bc  pop     r13
0x14005a6be  pop     r12
0x14005a6c0  pop     rbp
0x14005a6c1  retn
```
