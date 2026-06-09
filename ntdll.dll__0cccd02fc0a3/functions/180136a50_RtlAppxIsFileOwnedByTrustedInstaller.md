# RtlAppxIsFileOwnedByTrustedInstaller

- ea: `0x180136a50`
- end: `0x180136bc8`
- name: `RtlAppxIsFileOwnedByTrustedInstaller`
- size: `376`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x18002b3e0`
- `0x1800c6200`
- `0x1800dc340`
- `0x180136a50`
- `0x180160fc0`

## string_xrefs

- `0x180136a66`: `TrustedInstaller`

## pseudocode

```c
__int64 __fastcall RtlAppxIsFileOwnedByTrustedInstaller(__int64 a1, _BYTE *a2)
{
  int SecurityObject; // ebx
  __int64 Heap_0; // rsi
  __int64 v7; // rax
  __int64 v8; // rdi
  __int64 v9; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v10[3]; // [rsp+38h] [rbp-18h] BYREF
  char v11; // [rsp+88h] [rbp+38h] BYREF
  unsigned int v12; // [rsp+90h] [rbp+40h]
  unsigned int v13; // [rsp+98h] [rbp+48h] BYREF

  v9 = 0;
  v10[1] = L"TrustedInstaller";
  v12 = 0;
  v10[0] = 2228256;
  v13 = 0;
  if ( !a2 )
    return 3221225485LL;
  SecurityObject = NtQuerySecurityObject(a1, 1, 0);
  if ( SecurityObject == -1073741789 )
  {
    Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, v12);
    if ( Heap_0 )
    {
      SecurityObject = NtQuerySecurityObject(a1, 1, Heap_0);
      if ( SecurityObject >= 0 )
      {
        SecurityObject = RtlGetOwnerSecurityDescriptor(Heap_0, &v9, &v11);
        if ( SecurityObject >= 0 )
        {
          if ( v9 )
          {
            SecurityObject = RtlCreateServiceSid(v10, 0, &v13);
            if ( SecurityObject == -1073741789 )
            {
              v7 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, v13);
              v8 = v7;
              if ( v7 )
              {
                SecurityObject = RtlCreateServiceSid(v10, v7, &v13);
                if ( SecurityObject >= 0 )
                  *a2 = RtlEqualSid(v9, v8);
                RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v8);
              }
            }
          }
        }
      }
      RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, Heap_0);
    }
  }
  return (unsigned int)SecurityObject;
}

```

## disassembly

```asm
0x180136a50  push    rbp
0x180136a52  push    rbx
0x180136a53  push    rsi
0x180136a54  push    rdi
0x180136a55  push    r15
0x180136a57  mov     rbp, rsp
0x180136a5a  sub     rsp, 50h
0x180136a5e  mov     [rbp+var_20], 0
0x180136a66  lea     rax, aTrustedinstall; "TrustedInstaller"
0x180136a6d  mov     [rbp+var_10], rax
0x180136a71  mov     r15, rdx
0x180136a74  mov     [rbp+arg_10], 0
0x180136a7b  mov     rdi, rcx
0x180136a7e  mov     [rbp+var_18], 220020h
0x180136a86  mov     [rbp+arg_18], 0
0x180136a8d  test    rdx, rdx
0x180136a90  jnz     short loc_180136A9C
0x180136a92  mov     eax, 0C000000Dh
0x180136a97  jmp     loc_180136BBC
0x180136a9c  xor     r9d, r9d
0x180136a9f  lea     rax, [rbp+arg_10]
0x180136aa3  xor     r8d, r8d
0x180136aa6  mov     [rsp+50h+var_30], rax
0x180136aab  lea     edx, [r9+1]
0x180136aaf  call    NtQuerySecurityObject
0x180136ab4  mov     ebx, eax
0x180136ab6  cmp     eax, 0C0000023h
0x180136abb  jnz     loc_180136BBA
0x180136ac1  mov     rcx, gs:60h
0x180136aca  mov     edx, 8
0x180136acf  mov     r8d, [rbp+arg_10]
0x180136ad3  mov     rcx, [rcx+30h]
0x180136ad7  call    RtlAllocateHeap_0
0x180136adc  mov     rsi, rax
0x180136adf  test    rax, rax
0x180136ae2  jz      loc_180136BBA
0x180136ae8  mov     r9d, [rbp+arg_10]
0x180136aec  lea     rax, [rbp+arg_10]
0x180136af0  mov     r8, rsi
0x180136af3  mov     [rsp+50h+var_30], rax
0x180136af8  mov     edx, 1
0x180136afd  mov     rcx, rdi
0x180136b00  call    NtQuerySecurityObject
0x180136b05  mov     ebx, eax
0x180136b07  test    eax, eax
0x180136b09  js      loc_180136BA3
0x180136b0f  lea     r8, [rbp+arg_8]
0x180136b13  mov     rcx, rsi
0x180136b16  lea     rdx, [rbp+var_20]
0x180136b1a  call    RtlGetOwnerSecurityDescriptor
0x180136b1f  mov     ebx, eax
0x180136b21  test    eax, eax
0x180136b23  js      short loc_180136BA3
0x180136b25  cmp     [rbp+var_20], 0
0x180136b2a  jz      short loc_180136BA3
0x180136b2c  lea     r8, [rbp+arg_18]
0x180136b30  xor     edx, edx
0x180136b32  lea     rcx, [rbp+var_18]
0x180136b36  call    RtlCreateServiceSid
0x180136b3b  mov     ebx, eax
0x180136b3d  cmp     eax, 0C0000023h
0x180136b42  jnz     short loc_180136BA3
0x180136b44  mov     rcx, gs:60h
0x180136b4d  mov     edx, 8
0x180136b52  mov     r8d, [rbp+arg_18]
0x180136b56  mov     rcx, [rcx+30h]
0x180136b5a  call    RtlAllocateHeap_0
0x180136b5f  mov     rdi, rax
0x180136b62  test    rax, rax
0x180136b65  jz      short loc_180136BA3
0x180136b67  lea     r8, [rbp+arg_18]
0x180136b6b  mov     rdx, rax
0x180136b6e  lea     rcx, [rbp+var_18]
0x180136b72  call    RtlCreateServiceSid
0x180136b77  mov     ebx, eax
0x180136b79  test    eax, eax
0x180136b7b  js      short loc_180136B8C
0x180136b7d  mov     rcx, [rbp+var_20]
0x180136b81  mov     rdx, rdi
0x180136b84  call    RtlEqualSid
0x180136b89  mov     [r15], al
0x180136b8c  mov     rcx, gs:60h
0x180136b95  mov     r8, rdi
0x180136b98  xor     edx, edx
0x180136b9a  mov     rcx, [rcx+30h]
0x180136b9e  call    RtlFreeHeap_0
0x180136ba3  mov     rcx, gs:60h
0x180136bac  mov     r8, rsi
0x180136baf  xor     edx, edx
0x180136bb1  mov     rcx, [rcx+30h]
0x180136bb5  call    RtlFreeHeap_0
0x180136bba  mov     eax, ebx
0x180136bbc  add     rsp, 50h
0x180136bc0  pop     r15
0x180136bc2  pop     rdi
0x180136bc3  pop     rsi
0x180136bc4  pop     rbx
0x180136bc5  pop     rbp
0x180136bc6  retn
```
