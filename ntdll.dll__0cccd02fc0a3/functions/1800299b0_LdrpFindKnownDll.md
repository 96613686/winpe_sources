# LdrpFindKnownDll

- ea: `0x1800299b0`
- end: `0x180029b66`
- name: `LdrpFindKnownDll`
- size: `438`
- prototype: `__int64 __fastcall(char ArgList)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800296e0`

## callees

- `0x18001eb80`
- `0x1800299b0`
- `0x18002ad90`
- `0x18002aec0`
- `0x18002b2a0`
- `0x18005a9f0`
- `0x18015e4b0`
- `0x18015e9b0`

## string_xrefs

- `0x1800299c8`: `DLL name: %wZ\n`
- `0x1800299dd`: `LdrpFindKnownDll`
- `0x180029a21`: `LdrpFindKnownDll`
- `0x180029aa2`: `LdrpFindKnownDll`
- `0x180029ad0`: `LdrpFindKnownDll`

## pseudocode

```c
__int64 __fastcall LdrpFindKnownDll(unsigned __int16 *ArgList, __int64 a2, unsigned __int16 *a3, HANDLE *a4)
{
  int v8; // eax
  int UnicodeString; // ebx
  __int64 v11; // rbx
  _BYTE v12[48]; // [rsp+30h] [rbp-58h] BYREF

  memset(v12, 0, 44);
  LdrpLogInternal((int)"minkernel\\ldr\\ldrmap.c", 1859, (int)"LdrpFindKnownDll", 3, "DLL name: %wZ\n", (char)ArgList);
  LdrpLogInternal((int)"minkernel\\ldr\\ldrmap.c", 1860, (int)"LdrpFindKnownDll", 5, "%wZ\n", (char)ArgList);
  if ( !LdrpKnownDllDirectoryHandle )
    goto LABEL_4;
  *(_DWORD *)v12 = 48;
  *(_QWORD *)&v12[8] = LdrpKnownDllDirectoryHandle;
  *(_DWORD *)&v12[24] = 64;
  *(_QWORD *)&v12[16] = ArgList;
  *(_OWORD *)&v12[32] = 0;
  v8 = NtOpenSection(a4, 13, v12);
  UnicodeString = v8;
  if ( v8 >= 0 )
  {
    UnicodeString = LdrpAllocateUnicodeString(a3, *ArgList + (unsigned int)(unsigned __int16)LdrpKnownDllPath + 2);
    if ( UnicodeString < 0 )
    {
      NtClose(*a4);
    }
    else
    {
      RtlAppendUnicodeStringToString(a3, &LdrpKnownDllPath);
      RtlAppendUnicodeToString(a3, L"\\");
      v11 = *a3 + *((_QWORD *)a3 + 1);
      RtlAppendUnicodeStringToString(a3, ArgList);
      RtlInitUnicodeStringEx(a2, v11);
      UnicodeString = 0;
    }
  }
  else if ( v8 == -1073741772 )
  {
LABEL_4:
    UnicodeString = -1073741515;
  }
  LdrpLogInternal((int)"minkernel\\ldr\\ldrmap.c", 1930, (int)"LdrpFindKnownDll", 4, "Status: 0x%08lx\n", UnicodeString);
  LdrpLogInternal((int)"minkernel\\ldr\\ldrmap.c", 1931, (int)"LdrpFindKnownDll", 6, "%x\n", UnicodeString);
  return (unsigned int)UnicodeString;
}

```

## disassembly

```asm
0x1800299b0  push    rbx
0x1800299b2  push    rbp
0x1800299b3  push    rsi
0x1800299b4  push    rdi
0x1800299b5  push    r14
0x1800299b7  sub     rsp, 60h
0x1800299bb  xorps   xmm0, xmm0
0x1800299be  mov     qword ptr [rsp+88h+ArgList], rcx; ArgList
0x1800299c3  xor     eax, eax
0x1800299c5  mov     rsi, r9
0x1800299c8  lea     rax, aDllNameWz; "DLL name: %wZ\n"
0x1800299cf  mov     rbp, r8
0x1800299d2  mov     r14, rdx
0x1800299d5  mov     [rsp+88h+Format], rax; Format
0x1800299da  mov     rdi, rcx
0x1800299dd  lea     r8, aLdrpfindknownd; "LdrpFindKnownDll"
0x1800299e4  movups  [rsp+88h+var_48], xmm0
0x1800299e9  mov     r9d, 3; int
0x1800299ef  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x1800299f6  mov     edx, 743h; int
0x1800299fb  movups  [rsp+88h+var_58], xmm0
0x180029a00  movups  [rsp+88h+var_48+0Ch], xmm0
0x180029a05  call    LdrpLogInternal
0x180029a0a  lea     rax, aWz_0; "%wZ\n"
0x180029a11  mov     qword ptr [rsp+88h+ArgList], rdi; ArgList
0x180029a16  mov     r9d, 5; int
0x180029a1c  mov     [rsp+88h+Format], rax; Format
0x180029a21  lea     r8, aLdrpfindknownd; "LdrpFindKnownDll"
0x180029a28  mov     edx, 744h; int
0x180029a2d  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x180029a34  call    LdrpLogInternal
0x180029a39  mov     rax, cs:LdrpKnownDllDirectoryHandle
0x180029a40  test    rax, rax
0x180029a43  jz      short loc_180029A87
0x180029a45  xorps   xmm0, xmm0
0x180029a48  mov     dword ptr [rsp+88h+var_58], 30h ; '0'
0x180029a50  lea     r8, [rsp+88h+var_58]
0x180029a55  mov     qword ptr [rsp+88h+var_58+8], rax
0x180029a5a  mov     edx, 0Dh
0x180029a5f  mov     dword ptr [rsp+88h+var_48+8], 40h ; '@'
0x180029a67  mov     rcx, rsi
0x180029a6a  mov     qword ptr [rsp+88h+var_48], rdi
0x180029a6f  movdqu  [rsp+88h+var_38], xmm0
0x180029a75  call    NtOpenSection
0x180029a7a  mov     ebx, eax
0x180029a7c  test    eax, eax
0x180029a7e  jns     short loc_180029AF6
0x180029a80  cmp     eax, 0C0000034h
0x180029a85  jnz     short loc_180029A8C
0x180029a87  mov     ebx, 0C0000135h
0x180029a8c  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x180029a93  mov     dword ptr [rsp+88h+ArgList], ebx; ArgList
0x180029a97  mov     r9d, 4; int
0x180029a9d  mov     [rsp+88h+Format], rax; Format
0x180029aa2  lea     r8, aLdrpfindknownd; "LdrpFindKnownDll"
0x180029aa9  mov     edx, 78Ah; int
0x180029aae  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x180029ab5  call    LdrpLogInternal
0x180029aba  lea     rax, asc_180175AB4; "%x\n"
0x180029ac1  mov     dword ptr [rsp+88h+ArgList], ebx; ArgList
0x180029ac5  mov     r9d, 6; int
0x180029acb  mov     [rsp+88h+Format], rax; Format
0x180029ad0  lea     r8, aLdrpfindknownd; "LdrpFindKnownDll"
0x180029ad7  mov     edx, 78Bh; int
0x180029adc  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x180029ae3  call    LdrpLogInternal
0x180029ae8  mov     eax, ebx
0x180029aea  add     rsp, 60h
0x180029aee  pop     r14
0x180029af0  pop     rdi
0x180029af1  pop     rsi
0x180029af2  pop     rbp
0x180029af3  pop     rbx
0x180029af4  retn
0x180029af6  movzx   ecx, word ptr [rdi]
0x180029af9  movzx   edx, cs:LdrpKnownDllPath
0x180029b00  add     edx, 2
0x180029b03  add     edx, ecx
0x180029b05  mov     rcx, rbp
0x180029b08  call    LdrpAllocateUnicodeString
0x180029b0d  mov     ebx, eax
0x180029b0f  test    eax, eax
0x180029b11  js      short loc_180029B59
0x180029b13  lea     rdx, LdrpKnownDllPath
0x180029b1a  mov     rcx, rbp
0x180029b1d  call    RtlAppendUnicodeStringToString
0x180029b22  lea     rdx, asc_180177BA4; "\\"
0x180029b29  mov     rcx, rbp
0x180029b2c  call    RtlAppendUnicodeToString
0x180029b31  movzx   ecx, word ptr [rbp+0]
0x180029b35  mov     rdx, rdi
0x180029b38  mov     rbx, [rbp+8]
0x180029b3c  add     rbx, rcx
0x180029b3f  mov     rcx, rbp
0x180029b42  call    RtlAppendUnicodeStringToString
0x180029b47  mov     rdx, rbx
0x180029b4a  mov     rcx, r14
0x180029b4d  call    RtlInitUnicodeStringEx
0x180029b52  xor     ebx, ebx
0x180029b54  jmp     loc_180029A8C
0x180029b59  mov     rcx, [rsi]; Handle
0x180029b5c  call    NtClose
0x180029b61  jmp     loc_180029A8C
```
