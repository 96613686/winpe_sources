# RtlAppxIsFileOwnedByTrustedInstaller

- ea: `0x180137540`
- end: `0x1801376b8`
- name: `RtlAppxIsFileOwnedByTrustedInstaller`
- size: `376`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x180037cc0`
- `0x1800c9cd0`
- `0x1800dcdc0`
- `0x180137540`
- `0x1801617d0`

## string_xrefs

- `0x180137556`: `TrustedInstaller`

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
0x180137540  push    rbp
0x180137542  push    rbx
0x180137543  push    rsi
0x180137544  push    rdi
0x180137545  push    r15
0x180137547  mov     rbp, rsp
0x18013754a  sub     rsp, 50h
0x18013754e  mov     [rbp+var_20], 0
0x180137556  lea     rax, aTrustedinstall; "TrustedInstaller"
0x18013755d  mov     [rbp+var_10], rax
0x180137561  mov     r15, rdx
0x180137564  mov     [rbp+arg_10], 0
0x18013756b  mov     rdi, rcx
0x18013756e  mov     [rbp+var_18], 220020h
0x180137576  mov     [rbp+arg_18], 0
0x18013757d  test    rdx, rdx
0x180137580  jnz     short loc_18013758C
0x180137582  mov     eax, 0C000000Dh
0x180137587  jmp     loc_1801376AC
0x18013758c  xor     r9d, r9d
0x18013758f  lea     rax, [rbp+arg_10]
0x180137593  xor     r8d, r8d
0x180137596  mov     [rsp+50h+var_30], rax
0x18013759b  lea     edx, [r9+1]
0x18013759f  call    NtQuerySecurityObject
0x1801375a4  mov     ebx, eax
0x1801375a6  cmp     eax, 0C0000023h
0x1801375ab  jnz     loc_1801376AA
0x1801375b1  mov     rcx, gs:60h
0x1801375ba  mov     edx, 8
0x1801375bf  mov     r8d, [rbp+arg_10]
0x1801375c3  mov     rcx, [rcx+30h]
0x1801375c7  call    RtlAllocateHeap_0
0x1801375cc  mov     rsi, rax
0x1801375cf  test    rax, rax
0x1801375d2  jz      loc_1801376AA
0x1801375d8  mov     r9d, [rbp+arg_10]
0x1801375dc  lea     rax, [rbp+arg_10]
0x1801375e0  mov     r8, rsi
0x1801375e3  mov     [rsp+50h+var_30], rax
0x1801375e8  mov     edx, 1
0x1801375ed  mov     rcx, rdi
0x1801375f0  call    NtQuerySecurityObject
0x1801375f5  mov     ebx, eax
0x1801375f7  test    eax, eax
0x1801375f9  js      loc_180137693
0x1801375ff  lea     r8, [rbp+arg_8]
0x180137603  mov     rcx, rsi
0x180137606  lea     rdx, [rbp+var_20]
0x18013760a  call    RtlGetOwnerSecurityDescriptor
0x18013760f  mov     ebx, eax
0x180137611  test    eax, eax
0x180137613  js      short loc_180137693
0x180137615  cmp     [rbp+var_20], 0
0x18013761a  jz      short loc_180137693
0x18013761c  lea     r8, [rbp+arg_18]
0x180137620  xor     edx, edx
0x180137622  lea     rcx, [rbp+var_18]
0x180137626  call    RtlCreateServiceSid
0x18013762b  mov     ebx, eax
0x18013762d  cmp     eax, 0C0000023h
0x180137632  jnz     short loc_180137693
0x180137634  mov     rcx, gs:60h
0x18013763d  mov     edx, 8
0x180137642  mov     r8d, [rbp+arg_18]
0x180137646  mov     rcx, [rcx+30h]
0x18013764a  call    RtlAllocateHeap_0
0x18013764f  mov     rdi, rax
0x180137652  test    rax, rax
0x180137655  jz      short loc_180137693
0x180137657  lea     r8, [rbp+arg_18]
0x18013765b  mov     rdx, rax
0x18013765e  lea     rcx, [rbp+var_18]
0x180137662  call    RtlCreateServiceSid
0x180137667  mov     ebx, eax
0x180137669  test    eax, eax
0x18013766b  js      short loc_18013767C
0x18013766d  mov     rcx, [rbp+var_20]
0x180137671  mov     rdx, rdi
0x180137674  call    RtlEqualSid
0x180137679  mov     [r15], al
0x18013767c  mov     rcx, gs:60h
0x180137685  mov     r8, rdi
0x180137688  xor     edx, edx
0x18013768a  mov     rcx, [rcx+30h]
0x18013768e  call    RtlFreeHeap_0
0x180137693  mov     rcx, gs:60h
0x18013769c  mov     r8, rsi
0x18013769f  xor     edx, edx
0x1801376a1  mov     rcx, [rcx+30h]
0x1801376a5  call    RtlFreeHeap_0
0x1801376aa  mov     eax, ebx
0x1801376ac  add     rsp, 50h
0x1801376b0  pop     r15
0x1801376b2  pop     rdi
0x1801376b3  pop     rsi
0x1801376b4  pop     rbx
0x1801376b5  pop     rbp
0x1801376b6  retn
```
