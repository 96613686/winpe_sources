# SecureDump_PrepareForInit

- ea: `0x1405e0eec`
- end: `0x1405e1139`
- name: `SecureDump_PrepareForInit`
- size: `589`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140c619c4`

## callees

- `0x1405e0ebc`
- `0x1405e0eec`
- `0x1405e13e0`
- `0x140bb19f0`

## string_xrefs

- `0x1405e0f14`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl`
- `0x1405e0efb`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl\EncryptionCertificates\Certificate.1`
- `0x1405e0f1f`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl\ForceDumpsDisabled`

## pseudocode

```c
void __fastcall SecureDump_PrepareForInit(__int64 a1, _BYTE *a2)
{
  unsigned int v3; // ebx
  int Registry; // eax
  int v5; // eax
  _QWORD v6[2]; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v7[2]; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v8[2]; // [rsp+50h] [rbp-10h] BYREF
  char v9; // [rsp+80h] [rbp+20h] BYREF
  PVOID P; // [rsp+90h] [rbp+30h] BYREF

  v7[0] = 13238472;
  v7[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CrashControl\\EncryptionCertificates\\Certificate.1";
  P = 0;
  v6[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CrashControl";
  v8[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CrashControl\\ForceDumpsDisabled";
  v6[0] = 8388734;
  v8[0] = 10879140;
  ForceDumpDisabled = 1;
  if ( !a2 )
    return;
  *a2 = 0;
  xmmword_140E4C3B8 = 0;
  v3 = 2;
  *(_OWORD *)&dwFlags = 0;
  Registry = SecureDump_ReadRegistry((unsigned int)v8, (unsigned int)L"GuardedHost", 4, (unsigned int)&P, (__int64)&v9);
  if ( Registry < 0 )
  {
    if ( Registry != -1073741772 )
      goto LABEL_20;
  }
  else
  {
    LODWORD(xmmword_140E4C3B8) = *(_DWORD *)P;
    ExFreePoolWithTag(P, 0);
    P = 0;
    if ( (_DWORD)xmmword_140E4C3B8 )
    {
LABEL_19:
      v3 = 0;
      goto LABEL_20;
    }
  }
  v5 = SecureDump_ReadRegistry(
         (unsigned int)v6,
         (unsigned int)L"DumpEncryptionEnabled",
         4,
         (unsigned int)&P,
         (__int64)&v9);
  if ( v5 < 0 )
  {
    if ( v5 != -1073741772 )
      goto LABEL_20;
    ForceDumpDisabled = 0;
    goto LABEL_19;
  }
  DWORD1(xmmword_140E4C3B8) = *(_DWORD *)P;
  ExFreePoolWithTag(P, 0);
  P = 0;
  if ( !DWORD1(xmmword_140E4C3B8) )
    goto LABEL_8;
  *a2 = 1;
  if ( (int)SecureDump_ReadRegistry(
              (unsigned int)v6,
              (unsigned int)L"ProvisionDumpKeyWithCertificate",
              4,
              (unsigned int)&P,
              (__int64)&v9) >= 0 )
  {
    SecureDmpLoadCertificate = *(_DWORD *)P != 0;
    ExFreePoolWithTag(P, 0);
  }
  if ( SecureDmpLoadCertificate
    || (int)SecureDump_ReadRegistry(
              (unsigned int)v7,
              (unsigned int)L"PublicKey",
              3,
              (unsigned int)&xmmword_140E4C3B8 + 8,
              (__int64)&dwFlags) >= 0
    && (int)SecureDump_ReadRegistry(
              (unsigned int)v7,
              (unsigned int)L"Thumbprint",
              1,
              (unsigned int)(&dwFlags + 2),
              (__int64)(&dwFlags + 1)) >= 0 )
  {
LABEL_8:
    ForceDumpDisabled = 0;
LABEL_9:
    SecureDmpEncryptionContext = 1;
    return;
  }
LABEL_20:
  if ( ForceDumpDisabled != 1 )
    goto LABEL_9;
  if ( *((_QWORD *)&xmmword_140E4C3B8 + 1) )
  {
    ExFreePoolWithTag(*((PVOID *)&xmmword_140E4C3B8 + 1), 0);
    *((_QWORD *)&xmmword_140E4C3B8 + 1) = 0;
  }
  if ( *((_QWORD *)&dwFlags + 1) )
  {
    ExFreePoolWithTag(*((PVOID *)&dwFlags + 1), 0);
    *((_QWORD *)&dwFlags + 1) = 0;
  }
  if ( v3 )
  {
    SecureDmpEncryptionContext = 3;
    SecureDump_LogErrorEvent(v3);
  }
}

```

## disassembly

```asm
0x1405e0eec  mov     [rsp-18h+arg_8], rbx
0x1405e0ef1  push    rbp
0x1405e0ef2  push    rsi
0x1405e0ef3  push    rdi
0x1405e0ef4  mov     rbp, rsp
0x1405e0ef7  sub     rsp, 60h
0x1405e0efb  lea     rax, aRegistryMachin_85; "\\Registry\\Machine\\System\\CurrentCon"...
0x1405e0f02  mov     [rbp+var_20], 0CA00C8h
0x1405e0f0a  mov     [rbp+var_18], rax
0x1405e0f0e  xor     esi, esi
0x1405e0f10  mov     [rbp+P], rsi
0x1405e0f14  lea     rax, aRegistryMachin_32; "\\Registry\\Machine\\System\\CurrentCon"...
0x1405e0f1b  mov     [rbp+var_28], rax
0x1405e0f1f  lea     rax, aRegistryMachin_213; "\\Registry\\Machine\\System\\CurrentCon"...
0x1405e0f26  mov     [rbp+var_8], rax
0x1405e0f2a  mov     rdi, rdx
0x1405e0f2d  mov     [rbp+var_30], 80007Eh
0x1405e0f35  mov     [rbp+var_10], 0A600A4h
0x1405e0f3d  mov     cs:ForceDumpDisabled, 1
0x1405e0f44  test    rdx, rdx
0x1405e0f47  jz      loc_1405E1013
0x1405e0f4d  xorps   xmm0, xmm0
0x1405e0f50  mov     [rdx], sil
0x1405e0f53  lea     rax, [rbp+arg_0]
0x1405e0f57  lea     rdx, aGuardedhost; "GuardedHost"
0x1405e0f5e  mov     [rsp+60h+var_40], rax
0x1405e0f63  lea     r9, [rbp+P]
0x1405e0f67  lea     r8d, [rsi+4]
0x1405e0f6b  lea     rcx, [rbp+var_10]
0x1405e0f6f  movups  cs:xmmword_140E4C3B8, xmm0
0x1405e0f76  lea     ebx, [rsi+2]
0x1405e0f79  movups  cs:dwFlags, xmm0
0x1405e0f80  call    SecureDump_ReadRegistry
0x1405e0f85  test    eax, eax
0x1405e0f87  js      short loc_1405E0FAD
0x1405e0f89  mov     rcx, [rbp+P]; P
0x1405e0f8d  xor     edx, edx; Tag
0x1405e0f8f  mov     eax, [rcx]
0x1405e0f91  mov     dword ptr cs:xmmword_140E4C3B8, eax
0x1405e0f97  call    ExFreePoolWithTag
0x1405e0f9c  cmp     dword ptr cs:xmmword_140E4C3B8, esi
0x1405e0fa2  mov     [rbp+P], rsi
0x1405e0fa6  jz      short loc_1405E0FB8
0x1405e0fa8  jmp     loc_1405E10D8
0x1405e0fad  cmp     eax, 0C0000034h
0x1405e0fb2  jnz     loc_1405E10DA
0x1405e0fb8  lea     rax, [rbp+arg_0]
0x1405e0fbc  mov     r8d, 4
0x1405e0fc2  lea     r9, [rbp+P]
0x1405e0fc6  mov     [rsp+60h+var_40], rax
0x1405e0fcb  lea     rdx, aDumpencryption; "DumpEncryptionEnabled"
0x1405e0fd2  lea     rcx, [rbp+var_30]
0x1405e0fd6  call    SecureDump_ReadRegistry
0x1405e0fdb  test    eax, eax
0x1405e0fdd  js      loc_1405E10CA
0x1405e0fe3  mov     rcx, [rbp+P]; P
0x1405e0fe7  xor     edx, edx; Tag
0x1405e0fe9  mov     eax, [rcx]
0x1405e0feb  mov     dword ptr cs:xmmword_140E4C3B8+4, eax
0x1405e0ff1  call    ExFreePoolWithTag
0x1405e0ff6  cmp     dword ptr cs:xmmword_140E4C3B8+4, esi
0x1405e0ffc  mov     [rbp+P], rsi
0x1405e1000  jnz     short loc_1405E1024
0x1405e1002  mov     cs:ForceDumpDisabled, sil
0x1405e1009  mov     cs:SecureDmpEncryptionContext, 1
0x1405e1013  mov     rbx, [rsp+60h+arg_8]
0x1405e101b  add     rsp, 60h
0x1405e101f  pop     rdi
0x1405e1020  pop     rsi
0x1405e1021  pop     rbp
0x1405e1022  retn
0x1405e1024  lea     rax, [rbp+arg_0]
0x1405e1028  mov     byte ptr [rdi], 1
0x1405e102b  lea     r9, [rbp+P]
0x1405e102f  mov     [rsp+60h+var_40], rax
0x1405e1034  mov     r8d, 4
0x1405e103a  lea     rdx, aProvisiondumpk; "ProvisionDumpKeyWithCertificate"
0x1405e1041  lea     rcx, [rbp+var_30]
0x1405e1045  call    SecureDump_ReadRegistry
0x1405e104a  test    eax, eax
0x1405e104c  js      short loc_1405E1062
0x1405e104e  mov     rcx, [rbp+P]; P
0x1405e1052  cmp     [rcx], esi
0x1405e1054  setnbe  cs:SecureDmpLoadCertificate
0x1405e105b  xor     edx, edx; Tag
0x1405e105d  call    ExFreePoolWithTag
0x1405e1062  cmp     cs:SecureDmpLoadCertificate, sil
0x1405e1069  jnz     short loc_1405E1002
0x1405e106b  lea     rax, dwFlags
0x1405e1072  mov     r8d, 3
0x1405e1078  lea     r9, xmmword_140E4C3B8+8
0x1405e107f  mov     [rsp+60h+var_40], rax
0x1405e1084  lea     rdx, aPublickey; "PublicKey"
0x1405e108b  lea     rcx, [rbp+var_20]
0x1405e108f  call    SecureDump_ReadRegistry
0x1405e1094  test    eax, eax
0x1405e1096  js      short loc_1405E10DA
0x1405e1098  lea     rax, dwFlags+4
0x1405e109f  mov     r8d, 1
0x1405e10a5  lea     r9, dwFlags+8
0x1405e10ac  mov     [rsp+60h+var_40], rax
0x1405e10b1  lea     rdx, aThumbprint; "Thumbprint"
0x1405e10b8  lea     rcx, [rbp+var_20]
0x1405e10bc  call    SecureDump_ReadRegistry
0x1405e10c1  test    eax, eax
0x1405e10c3  js      short loc_1405E10DA
0x1405e10c5  jmp     loc_1405E1002
0x1405e10ca  cmp     eax, 0C0000034h
0x1405e10cf  jnz     short loc_1405E10DA
0x1405e10d1  mov     cs:ForceDumpDisabled, sil
0x1405e10d8  mov     ebx, esi
0x1405e10da  cmp     cs:ForceDumpDisabled, 1
0x1405e10e1  jnz     loc_1405E1009
0x1405e10e7  mov     rcx, qword ptr cs:xmmword_140E4C3B8+8; P
0x1405e10ee  test    rcx, rcx
0x1405e10f1  jz      short loc_1405E1101
0x1405e10f3  xor     edx, edx; Tag
0x1405e10f5  call    ExFreePoolWithTag
0x1405e10fa  mov     qword ptr cs:xmmword_140E4C3B8+8, rsi
0x1405e1101  mov     rcx, qword ptr cs:dwFlags+8; P
0x1405e1108  test    rcx, rcx
0x1405e110b  jz      short loc_1405E111B
0x1405e110d  xor     edx, edx; Tag
0x1405e110f  call    ExFreePoolWithTag
0x1405e1114  mov     qword ptr cs:dwFlags+8, rsi
0x1405e111b  test    ebx, ebx
0x1405e111d  jz      loc_1405E1013
0x1405e1123  mov     ecx, ebx
0x1405e1125  mov     cs:SecureDmpEncryptionContext, 3
0x1405e112f  call    SecureDump_LogErrorEvent
0x1405e1134  jmp     loc_1405E1013
```
