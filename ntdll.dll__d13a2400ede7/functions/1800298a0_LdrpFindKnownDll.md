# LdrpFindKnownDll

- ea: `0x1800298a0`
- end: `0x180029a56`
- name: `LdrpFindKnownDll`
- size: `438`
- prototype: `__int64 __fastcall(char ArgList)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800295d0`

## callees

- `0x18001eb80`
- `0x1800298a0`
- `0x18002a530`
- `0x18002a5b0`
- `0x180036fa0`
- `0x1800773d0`
- `0x18015ecc0`
- `0x18015f1c0`

## string_xrefs

- `0x1800298b8`: `DLL name: %wZ\n`
- `0x1800298cd`: `LdrpFindKnownDll`
- `0x180029911`: `LdrpFindKnownDll`
- `0x180029992`: `LdrpFindKnownDll`
- `0x1800299c0`: `LdrpFindKnownDll`

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
0x1800298a0  push    rbx
0x1800298a2  push    rbp
0x1800298a3  push    rsi
0x1800298a4  push    rdi
0x1800298a5  push    r14
0x1800298a7  sub     rsp, 60h
0x1800298ab  xorps   xmm0, xmm0
0x1800298ae  mov     qword ptr [rsp+88h+ArgList], rcx; ArgList
0x1800298b3  xor     eax, eax
0x1800298b5  mov     rsi, r9
0x1800298b8  lea     rax, aDllNameWz; "DLL name: %wZ\n"
0x1800298bf  mov     rbp, r8
0x1800298c2  mov     r14, rdx
0x1800298c5  mov     [rsp+88h+Format], rax; Format
0x1800298ca  mov     rdi, rcx
0x1800298cd  lea     r8, aLdrpfindknownd; "LdrpFindKnownDll"
0x1800298d4  movups  [rsp+88h+var_48], xmm0
0x1800298d9  mov     r9d, 3; int
0x1800298df  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x1800298e6  mov     edx, 743h; int
0x1800298eb  movups  [rsp+88h+var_58], xmm0
0x1800298f0  movups  [rsp+88h+var_48+0Ch], xmm0
0x1800298f5  call    LdrpLogInternal
0x1800298fa  lea     rax, aWz_0; "%wZ\n"
0x180029901  mov     qword ptr [rsp+88h+ArgList], rdi; ArgList
0x180029906  mov     r9d, 5; int
0x18002990c  mov     [rsp+88h+Format], rax; Format
0x180029911  lea     r8, aLdrpfindknownd; "LdrpFindKnownDll"
0x180029918  mov     edx, 744h; int
0x18002991d  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x180029924  call    LdrpLogInternal
0x180029929  mov     rax, cs:LdrpKnownDllDirectoryHandle
0x180029930  test    rax, rax
0x180029933  jz      short loc_180029977
0x180029935  xorps   xmm0, xmm0
0x180029938  mov     dword ptr [rsp+88h+var_58], 30h ; '0'
0x180029940  lea     r8, [rsp+88h+var_58]
0x180029945  mov     qword ptr [rsp+88h+var_58+8], rax
0x18002994a  mov     edx, 0Dh
0x18002994f  mov     dword ptr [rsp+88h+var_48+8], 40h ; '@'
0x180029957  mov     rcx, rsi
0x18002995a  mov     qword ptr [rsp+88h+var_48], rdi
0x18002995f  movdqu  [rsp+88h+var_38], xmm0
0x180029965  call    NtOpenSection
0x18002996a  mov     ebx, eax
0x18002996c  test    eax, eax
0x18002996e  jns     short loc_1800299E6
0x180029970  cmp     eax, 0C0000034h
0x180029975  jnz     short loc_18002997C
0x180029977  mov     ebx, 0C0000135h
0x18002997c  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x180029983  mov     dword ptr [rsp+88h+ArgList], ebx; ArgList
0x180029987  mov     r9d, 4; int
0x18002998d  mov     [rsp+88h+Format], rax; Format
0x180029992  lea     r8, aLdrpfindknownd; "LdrpFindKnownDll"
0x180029999  mov     edx, 78Ah; int
0x18002999e  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x1800299a5  call    LdrpLogInternal
0x1800299aa  lea     rax, asc_180175AB4; "%x\n"
0x1800299b1  mov     dword ptr [rsp+88h+ArgList], ebx; ArgList
0x1800299b5  mov     r9d, 6; int
0x1800299bb  mov     [rsp+88h+Format], rax; Format
0x1800299c0  lea     r8, aLdrpfindknownd; "LdrpFindKnownDll"
0x1800299c7  mov     edx, 78Bh; int
0x1800299cc  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x1800299d3  call    LdrpLogInternal
0x1800299d8  mov     eax, ebx
0x1800299da  add     rsp, 60h
0x1800299de  pop     r14
0x1800299e0  pop     rdi
0x1800299e1  pop     rsi
0x1800299e2  pop     rbp
0x1800299e3  pop     rbx
0x1800299e4  retn
0x1800299e6  movzx   ecx, word ptr [rdi]
0x1800299e9  movzx   edx, cs:LdrpKnownDllPath
0x1800299f0  add     edx, 2
0x1800299f3  add     edx, ecx
0x1800299f5  mov     rcx, rbp
0x1800299f8  call    LdrpAllocateUnicodeString
0x1800299fd  mov     ebx, eax
0x1800299ff  test    eax, eax
0x180029a01  js      short loc_180029A49
0x180029a03  lea     rdx, LdrpKnownDllPath
0x180029a0a  mov     rcx, rbp
0x180029a0d  call    RtlAppendUnicodeStringToString
0x180029a12  lea     rdx, asc_180178554; "\\"
0x180029a19  mov     rcx, rbp
0x180029a1c  call    RtlAppendUnicodeToString
0x180029a21  movzx   ecx, word ptr [rbp+0]
0x180029a25  mov     rdx, rdi
0x180029a28  mov     rbx, [rbp+8]
0x180029a2c  add     rbx, rcx
0x180029a2f  mov     rcx, rbp
0x180029a32  call    RtlAppendUnicodeStringToString
0x180029a37  mov     rdx, rbx
0x180029a3a  mov     rcx, r14
0x180029a3d  call    RtlInitUnicodeStringEx
0x180029a42  xor     ebx, ebx
0x180029a44  jmp     loc_18002997C
0x180029a49  mov     rcx, [rsi]; Handle
0x180029a4c  call    NtClose
0x180029a51  jmp     loc_18002997C
```
