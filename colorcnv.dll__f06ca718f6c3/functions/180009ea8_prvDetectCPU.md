# prvDetectCPU

- ea: `0x180009ea8`
- end: `0x180009fb8`
- name: `prvDetectCPU`
- size: `272`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180009bf8`
- `0x180009e68`
- `0x180009fc0`
- `0x180029014`

## callees

- `0x180009ea8`
- `0x18000a2b4`
- `0x18000ab30`
- `0x18000ba60`

## pseudocode

```c
__int64 __fastcall prvDetectCPU(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  unsigned int v7; // [rsp+20h] [rbp-20h] BYREF
  int v8; // [rsp+24h] [rbp-1Ch]
  int v9; // [rsp+28h] [rbp-18h]
  int v10; // [rsp+2Ch] [rbp-14h]

  if ( !dword_18003AAC4 )
  {
    prvDetectCPURegKey(a1, a2);
    CPUID_ECX_Clearedasm(&v7, 0);
    dword_18003AAB8 = v7;
    dword_18003AAAC = v8;
    dword_18003AAE0 = v9;
    dword_18003AABC = v10;
    CPUID_ECX_Clearedasm(&v7, 1);
    *(_DWORD *)byte_18003AAB0 = v8;
    dword_18003AAEC = v9;
    dword_18003AAC0 = v10;
    _RAX = 7;
    __asm { cpuid }
    dword_18003AAD0 = result;
    dword_18003AAD4 = _RBX;
    dword_18003AAD8 = _RCX;
    dword_18003AADC = _RDX;
    if ( dword_18003AAAC == 1752462657 && dword_18003AABC == 1769238117 && dword_18003AAE0 == 1145913699 )
    {
      result = CPUID_ECX_Clearedasm(&v7, 0x80000000LL);
      if ( v7 >= 0x80000001 )
        result = CPUID_ECX_Clearedasm(&v7, 2147483649LL);
    }
    dword_18003AAC4 = 1;
  }
  return result;
}

```

## disassembly

```asm
0x180009ea8  mov     [rsp-8+arg_0], rbx
0x180009ead  push    rbp
0x180009eae  mov     rbp, rsp
0x180009eb1  sub     rsp, 40h
0x180009eb5  mov     rax, cs:__security_cookie
0x180009ebc  xor     rax, rsp
0x180009ebf  mov     [rbp+var_10], rax
0x180009ec3  cmp     cs:dword_18003AAC4, 0
0x180009eca  jnz     loc_180009FA1
0x180009ed0  call    prvDetectCPURegKey
0x180009ed5  xor     edx, edx
0x180009ed7  lea     rcx, [rbp+var_20]
0x180009edb  call    CPUID_ECX_Clearedasm
0x180009ee0  mov     eax, [rbp+var_20]
0x180009ee3  lea     rcx, [rbp+var_20]
0x180009ee7  mov     cs:dword_18003AAB8, eax
0x180009eed  mov     edx, 1
0x180009ef2  mov     eax, [rbp+var_1C]
0x180009ef5  mov     cs:dword_18003AAAC, eax
0x180009efb  mov     eax, [rbp+var_18]
0x180009efe  mov     cs:dword_18003AAE0, eax
0x180009f04  mov     eax, [rbp+var_14]
0x180009f07  mov     cs:dword_18003AABC, eax
0x180009f0d  call    CPUID_ECX_Clearedasm
0x180009f12  mov     eax, [rbp+var_1C]
0x180009f15  xor     ecx, ecx
0x180009f17  cmp     cs:dword_18003AAAC, 68747541h
0x180009f21  mov     dword ptr cs:byte_18003AAB0, eax
0x180009f27  mov     eax, [rbp+var_18]
0x180009f2a  mov     cs:dword_18003AAEC, eax
0x180009f30  mov     eax, [rbp+var_14]
0x180009f33  mov     cs:dword_18003AAC0, eax
0x180009f39  mov     eax, 7
0x180009f3e  cpuid
0x180009f40  mov     cs:dword_18003AAD0, eax
0x180009f46  mov     cs:dword_18003AAD4, ebx
0x180009f4c  mov     cs:dword_18003AAD8, ecx
0x180009f52  mov     cs:dword_18003AADC, edx
0x180009f58  jnz     short loc_180009F97
0x180009f5a  cmp     cs:dword_18003AABC, 69746E65h
0x180009f64  jnz     short loc_180009F97
0x180009f66  cmp     cs:dword_18003AAE0, 444D4163h
0x180009f70  jnz     short loc_180009F97
0x180009f72  mov     edx, 80000000h
0x180009f77  lea     rcx, [rbp+var_20]
0x180009f7b  call    CPUID_ECX_Clearedasm
0x180009f80  cmp     [rbp+var_20], 80000001h
0x180009f87  jb      short loc_180009F97
0x180009f89  mov     edx, 80000001h
0x180009f8e  lea     rcx, [rbp+var_20]
0x180009f92  call    CPUID_ECX_Clearedasm
0x180009f97  mov     cs:dword_18003AAC4, 1
0x180009fa1  mov     rcx, [rbp+var_10]
0x180009fa5  xor     rcx, rsp; StackCookie
0x180009fa8  call    __security_check_cookie
0x180009fad  mov     rbx, [rsp+40h+arg_0]
0x180009fb2  add     rsp, 40h
0x180009fb6  pop     rbp
0x180009fb7  retn
```
