# SpEnumerateSecurityPackagesW

- ea: `0x180002470`
- end: `0x1800024ae`
- name: `SpEnumerateSecurityPackagesW`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002470`
- `0x180002fdc`
- `0x18000351c`

## pseudocode

```c
int __fastcall SpEnumerateSecurityPackagesW(_DWORD *a1, _QWORD *a2)
{
  int result; // eax

  *a1 = 0;
  result = InitMaxToken();
  if ( result >= 0 )
  {
    result = CopyPkgInfo(a2);
    if ( result >= 0 )
    {
      *a1 = 1;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002470  mov     [rsp+arg_0], rbx
0x180002475  push    rdi
0x180002476  sub     rsp, 20h
0x18000247a  mov     rdi, rdx
0x18000247d  mov     dword ptr [rcx], 0
0x180002483  mov     rbx, rcx
0x180002486  call    InitMaxToken
0x18000248b  test    eax, eax
0x18000248d  js      short loc_1800024A3
0x18000248f  mov     rcx, rdi
0x180002492  call    CopyPkgInfo
0x180002497  test    eax, eax
0x180002499  js      short loc_1800024A3
0x18000249b  mov     dword ptr [rbx], 1
0x1800024a1  xor     eax, eax
0x1800024a3  mov     rbx, [rsp+28h+arg_0]
0x1800024a8  add     rsp, 20h
0x1800024ac  pop     rdi
0x1800024ad  retn
```
