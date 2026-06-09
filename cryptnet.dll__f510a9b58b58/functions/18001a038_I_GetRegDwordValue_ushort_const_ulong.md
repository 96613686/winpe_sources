# I_GetRegDwordValue(ushort const *,ulong *)

- ea: `0x18001a038`
- end: `0x18001a09e`
- name: `?I_GetRegDwordValue@@YAKPEBGPEAK@Z`
- size: `102`
- prototype: `unsigned int __fastcall(LPCWSTR lpValueName, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001a250`

## callees

- `0x18001a038`
- `0x18001a0a4`

## string_xrefs

- `0x18001a076`: `Software\Microsoft\Cryptography\OID\EncodingType 0\CertDllCreateCertificateChainEngine\Config`
- `0x18001a057`: `Software\Policies\Microsoft\SystemCertificates\ChainEngine\Config`

## pseudocode

```c
unsigned int __fastcall I_GetRegDwordValue(LPCWSTR lpValueName, unsigned int *a2)
{
  unsigned int result; // eax

  *a2 = 0;
  result = ReadRegDwordValue(
             L"Software\\Policies\\Microsoft\\SystemCertificates\\ChainEngine\\Config",
             lpValueName,
             0,
             a2);
  if ( result )
  {
    if ( result != 2 )
      return result;
    result = ReadRegDwordValue(
               L"Software\\Microsoft\\Cryptography\\OID\\EncodingType 0\\CertDllCreateCertificateChainEngine\\Config",
               lpValueName,
               1,
               a2);
    if ( result )
    {
      if ( result != 2 )
        return result;
      *a2 = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001a038  mov     [rsp+arg_0], rbx
0x18001a03d  push    rdi
0x18001a03e  sub     rsp, 20h
0x18001a042  mov     rbx, rdx
0x18001a045  mov     dword ptr [rdx], 0
0x18001a04b  mov     r9, rdx; unsigned int *
0x18001a04e  mov     rdi, rcx
0x18001a051  mov     rdx, rcx; lpValueName
0x18001a054  xor     r8d, r8d; int
0x18001a057  lea     rcx, aSoftwarePolici; "Software\\Policies\\Microsoft\\SystemCe"...
0x18001a05e  call    ?ReadRegDwordValue@@YAKPEBG0HPEAK@Z; ReadRegDwordValue(ushort const *,ushort const *,int,ulong *)
0x18001a063  test    eax, eax
0x18001a065  jz      short loc_18001A091
0x18001a067  cmp     eax, 2
0x18001a06a  jnz     short loc_18001A093
0x18001a06c  mov     r9, rbx; unsigned int *
0x18001a06f  lea     r8d, [rax-1]; int
0x18001a073  mov     rdx, rdi; lpValueName
0x18001a076  lea     rcx, SubKey; "Software\\Microsoft\\Cryptography\\OID"...
0x18001a07d  call    ?ReadRegDwordValue@@YAKPEBG0HPEAK@Z; ReadRegDwordValue(ushort const *,ushort const *,int,ulong *)
0x18001a082  test    eax, eax
0x18001a084  jz      short loc_18001A091
0x18001a086  cmp     eax, 2
0x18001a089  jnz     short loc_18001A093
0x18001a08b  mov     dword ptr [rbx], 0
0x18001a091  xor     eax, eax
0x18001a093  mov     rbx, [rsp+28h+arg_0]
0x18001a098  add     rsp, 20h
0x18001a09c  pop     rdi
0x18001a09d  retn
```
