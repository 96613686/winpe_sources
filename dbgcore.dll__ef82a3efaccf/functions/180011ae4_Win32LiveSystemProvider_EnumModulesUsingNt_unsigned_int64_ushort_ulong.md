# Win32LiveSystemProvider::EnumModulesUsingNt(unsigned __int64 *,ushort *,ulong)

- ea: `0x180011ae4`
- end: `0x180011e02`
- name: `?EnumModulesUsingNt@Win32LiveSystemProvider@@AEAAJPEA_KPEAGK@Z`
- size: `798`
- prototype: `unsigned int __fastcall(Win32LiveSystemProvider *this, unsigned __int64 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800119d0`

## callees

- `0x18001179c`
- `0x180011ae4`
- `0x18002c010`

## import_xrefs

- `ntdll!NtQueryVirtualMemory` at `0x180011b72`
- `ntdll!NtQueryVirtualMemory` at `0x180011bb2`
- `ntdll!NtQueryVirtualMemory` at `0x180011c78`
- `ntdll!NtQueryVirtualMemory` at `0x180011d8a`
- `ntdll!NtQueryVirtualMemory` at `0x180011b72`
- `ntdll!NtQueryVirtualMemory` at `0x180011bb2`
- `ntdll!NtQueryVirtualMemory` at `0x180011c78`
- `ntdll!NtQueryVirtualMemory` at `0x180011d8a`

## pseudocode

```c
unsigned int __fastcall Win32LiveSystemProvider::EnumModulesUsingNt(
        Win32LiveSystemProvider *this,
        unsigned __int64 *a2,
        unsigned __int16 *a3,
        unsigned int a4)
{
  unsigned __int64 v4; // r13
  void *v6; // rax
  unsigned __int64 *v7; // rdi
  NTSTATUS v9; // eax
  int v10; // r15d
  _QWORD *v11; // rax
  int v12; // esi
  __int64 v13; // rcx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // r14
  NTSTATUS v16; // edi
  unsigned __int64 v17; // rdx
  unsigned __int16 *v18; // rax
  unsigned __int16 *v19; // r8
  unsigned __int64 v20; // rcx
  unsigned __int16 *v21; // rcx
  unsigned int result; // eax
  __int128 v23; // [rsp+30h] [rbp-59h] BYREF
  __int64 v24; // [rsp+40h] [rbp-49h]
  __int128 VirtualMemoryInformation; // [rsp+48h] [rbp-41h] BYREF
  __int128 v26; // [rsp+58h] [rbp-31h]
  __int128 v27; // [rsp+68h] [rbp-21h]
  __int128 v28; // [rsp+78h] [rbp-11h] BYREF
  __int128 v29; // [rsp+88h] [rbp-1h]
  __int128 v30; // [rsp+98h] [rbp+Fh]
  ULONG_PTR ResultLength; // [rsp+F0h] [rbp+67h] BYREF
  unsigned __int64 *v32; // [rsp+F8h] [rbp+6Fh]

  v32 = a2;
  v4 = a4;
  v24 = 0;
  v6 = (void *)*((_QWORD *)this + 87);
  v7 = a2;
  VirtualMemoryInformation = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v23 = 0;
  if ( (unsigned __int64)v6 >= *((_QWORD *)this + 103) )
    return 1;
  while ( 1 )
  {
    v9 = NtQueryVirtualMemory(
           *((HANDLE *)this + 82),
           v6,
           MemoryBasicVlmInformation,
           &VirtualMemoryInformation,
           0x30u,
           0);
    if ( v9 >= 0 )
      break;
    if ( v9 != -1073741503 )
      return v9 | 0x10000000;
    v9 = NtQueryVirtualMemory(*((HANDLE *)this + 82), *((PVOID *)this + 87), MemoryBasicInformation, &v28, 0x30u, 0);
    if ( v9 < 0 )
      return v9 | 0x10000000;
    *((_QWORD *)this + 87) += *((_QWORD *)&v29 + 1);
    v6 = (void *)*((_QWORD *)this + 87);
LABEL_38:
    if ( (unsigned __int64)v6 >= *((_QWORD *)this + 103) )
      return 1;
  }
  v10 = 0;
  if ( HIDWORD(VirtualMemoryInformation) == 0x1000000 )
  {
    v9 = NtQueryVirtualMemory(
           *((HANDLE *)this + 82),
           *((PVOID *)this + 87),
           MemoryWorkingSetExList|MemorySectionName,
           &v23,
           0x18u,
           0);
    if ( v9 < 0 )
      return v9 | 0x10000000;
    if ( (v24 & 2) == 0 && (v24 & 1) == 0 )
    {
      v10 = 1;
      *((_QWORD *)this + 87) = v23;
    }
  }
  if ( !*((_DWORD *)this + 205) || (v11 = (_QWORD *)*((_QWORD *)this + 98), v11 == (_QWORD *)((char *)this + 784)) )
  {
LABEL_12:
    v12 = 0;
  }
  else
  {
    while ( v11[2] != *((_QWORD *)this + 87) )
    {
      v11 = (_QWORD *)*v11;
      if ( v11 == (_QWORD *)((char *)this + 784) )
        goto LABEL_12;
    }
    v12 = 1;
  }
  if ( !v10 || v12 )
  {
LABEL_32:
    v6 = (void *)(VirtualMemoryInformation + v26);
    *((_QWORD *)this + 87) = VirtualMemoryInformation + v26;
    if ( v10 && !v12 )
      return 0;
    goto LABEL_38;
  }
  *v7 = *((_QWORD *)this + 87);
  v13 = *((_QWORD *)this + 6);
  ResultLength = 0;
  v14 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 8LL))(
                              v13,
                              (unsigned int)(2 * v4 + 14));
  v15 = v14;
  if ( !v14 )
    return -2147024882;
  v16 = NtQueryVirtualMemory(
          *((HANDLE *)this + 82),
          (PVOID)VirtualMemoryInformation,
          MemorySectionName,
          v14,
          (unsigned int)(2 * v4 + 14),
          &ResultLength);
  if ( v16 >= 0 )
  {
    v17 = v4;
    if ( (_DWORD)v4 )
    {
      if ( v4 > 0x7FFFFFFF )
      {
        *a3 = 0;
        return -2147024809;
      }
      v18 = a3;
      v19 = (unsigned __int16 *)*((_QWORD *)v15 + 1);
      v20 = (unsigned __int64)*v15 >> 1;
      do
      {
        if ( !v20 )
          break;
        if ( !*v19 )
          break;
        *v18++ = *v19++;
        --v20;
        --v17;
      }
      while ( v17 );
      v21 = v18 - 1;
      if ( v17 )
        v21 = v18;
      result = v17 == 0 ? 0x8007007A : 0;
      *v21 = 0;
    }
    else
    {
      result = -2147024809;
    }
    if ( result )
      return result;
    result = Win32LiveSystemProvider::ConvertNtPathToWin32(this, a3);
    if ( result )
      return result;
  }
  (*(void (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)this + 6) + 24LL))(*((_QWORD *)this + 6), v15);
  if ( v16 >= 0 )
  {
    v7 = v32;
    goto LABEL_32;
  }
  result = v16 | 0x10000000;
  if ( v16 == -2147483643 )
    return -2147024809;
  return result;
}

```

## disassembly

```asm
0x180011ae4  mov     [rsp-8+arg_10], rbx
0x180011ae9  mov     [rsp-8+arg_8], rdx
0x180011aee  push    rbp
0x180011aef  push    rsi
0x180011af0  push    rdi
0x180011af1  push    r12
0x180011af3  push    r13
0x180011af5  push    r14
0x180011af7  push    r15
0x180011af9  lea     rbp, [rsp-27h]
0x180011afe  sub     rsp, 0B0h
0x180011b05  xorps   xmm0, xmm0
0x180011b08  mov     r13d, r9d
0x180011b0b  xor     eax, eax
0x180011b0d  xorps   xmm1, xmm1
0x180011b10  mov     [rbp+57h+var_A0], rax
0x180011b14  mov     r12, r8
0x180011b17  mov     rax, [rcx+2B8h]
0x180011b1e  mov     rdi, rdx
0x180011b21  mov     rbx, rcx
0x180011b24  movups  [rbp+57h+VirtualMemoryInformation], xmm0
0x180011b28  movups  [rbp+57h+var_88], xmm0
0x180011b2c  movups  [rbp+57h+var_78], xmm0
0x180011b30  movups  [rbp+57h+var_68], xmm1
0x180011b34  movups  [rbp+57h+var_58], xmm1
0x180011b38  movups  [rbp+57h+var_48], xmm1
0x180011b3c  movups  [rbp+57h+var_B0], xmm0
0x180011b40  cmp     rax, [rcx+338h]
0x180011b47  jnb     loc_180011DB3
0x180011b4d  xor     r14d, r14d
0x180011b50  mov     rcx, [rbx+290h]; ProcessHandle
0x180011b57  lea     r9, [rbp+57h+VirtualMemoryInformation]; VirtualMemoryInformation
0x180011b5b  mov     [rsp+0E0h+ResultLength], r14; ResultLength
0x180011b60  mov     r8d, 3; VirtualMemoryInformationClass
0x180011b66  mov     rdx, rax; Address
0x180011b69  mov     [rsp+0E0h+Length], 30h ; '0'; Length
0x180011b72  call    cs:__imp_NtQueryVirtualMemory
0x180011b78  test    eax, eax
0x180011b7a  js      loc_180011D60
0x180011b80  cmp     dword ptr [rbp+57h+VirtualMemoryInformation+0Ch], 1000000h
0x180011b87  mov     r15d, r14d
0x180011b8a  jnz     short loc_180011BDD
0x180011b8c  mov     rdx, [rbx+2B8h]; Address
0x180011b93  lea     r9, [rbp+57h+var_B0]; VirtualMemoryInformation
0x180011b97  mov     rcx, [rbx+290h]; ProcessHandle
0x180011b9e  mov     r8d, 6; VirtualMemoryInformationClass
0x180011ba4  mov     [rsp+0E0h+ResultLength], r14; ResultLength
0x180011ba9  mov     [rsp+0E0h+Length], 18h; Length
0x180011bb2  call    cs:__imp_NtQueryVirtualMemory
0x180011bb8  test    eax, eax
0x180011bba  js      loc_180011DD3
0x180011bc0  test    byte ptr [rbp+57h+var_A0], 2
0x180011bc4  jnz     short loc_180011BDD
0x180011bc6  test    byte ptr [rbp+57h+var_A0], 1
0x180011bca  jnz     short loc_180011BDD
0x180011bcc  mov     rax, qword ptr [rbp+57h+var_B0]
0x180011bd0  mov     r15d, 1
0x180011bd6  mov     [rbx+2B8h], rax
0x180011bdd  cmp     [rbx+334h], r14d
0x180011be4  jz      short loc_180011C0E
0x180011be6  lea     rcx, [rbx+310h]
0x180011bed  mov     rax, [rcx]
0x180011bf0  cmp     rax, rcx
0x180011bf3  jz      short loc_180011C0E
0x180011bf5  mov     rdx, [rbx+2B8h]
0x180011bfc  cmp     [rax+10h], rdx
0x180011c00  jz      loc_180011CEF
0x180011c06  mov     rax, [rax]
0x180011c09  cmp     rax, rcx
0x180011c0c  jnz     short loc_180011BFC
0x180011c0e  mov     esi, r14d
0x180011c11  test    r15d, r15d
0x180011c14  jz      loc_180011D44
0x180011c1a  test    esi, esi
0x180011c1c  jnz     loc_180011D44
0x180011c22  mov     rax, [rbx+2B8h]
0x180011c29  mov     [rdi], rax
0x180011c2c  lea     edi, ds:0Eh[r13*2]
0x180011c34  mov     rcx, [rbx+30h]
0x180011c38  mov     edx, edi
0x180011c3a  mov     [rbp+57h+arg_0], r14
0x180011c3e  mov     rax, [rcx]
0x180011c41  mov     rax, [rax+8]
0x180011c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c4a  mov     r14, rax
0x180011c4d  test    rax, rax
0x180011c50  jz      loc_180011DFB
0x180011c56  mov     rdx, qword ptr [rbp+57h+VirtualMemoryInformation]; Address
0x180011c5a  lea     rcx, [rbp+57h+arg_0]
0x180011c5e  mov     [rsp+0E0h+ResultLength], rcx; ResultLength
0x180011c63  lea     r8d, [rsi+2]; VirtualMemoryInformationClass
0x180011c67  mov     rcx, [rbx+290h]; ProcessHandle
0x180011c6e  mov     r9, r14; VirtualMemoryInformation
0x180011c71  mov     eax, edi
0x180011c73  mov     [rsp+0E0h+Length], rax; Length
0x180011c78  call    cs:__imp_NtQueryVirtualMemory
0x180011c7e  xor     r10d, r10d
0x180011c81  mov     edi, eax
0x180011c83  test    eax, eax
0x180011c85  js      loc_180011D22
0x180011c8b  mov     rdx, r13
0x180011c8e  test    r13d, r13d
0x180011c91  jz      short loc_180011CF9
0x180011c93  cmp     rdx, 7FFFFFFFh
0x180011c9a  ja      loc_180011DD9
0x180011ca0  movzx   ecx, word ptr [r14]
0x180011ca4  mov     rax, r12
0x180011ca7  mov     r8, [r14+8]
0x180011cab  shr     rcx, 1
0x180011cae  test    rcx, rcx
0x180011cb1  jz      short loc_180011CD2
0x180011cb3  movzx   r9d, word ptr [r8]
0x180011cb7  test    r9w, r9w
0x180011cbb  jz      short loc_180011CD2
0x180011cbd  mov     [rax], r9w
0x180011cc1  add     r8, 2
0x180011cc5  add     rax, 2
0x180011cc9  dec     rcx
0x180011ccc  sub     rdx, 1
0x180011cd0  jnz     short loc_180011CAE
0x180011cd2  lea     rcx, [rax-2]
0x180011cd6  test    rdx, rdx
0x180011cd9  cmovnz  rcx, rax
0x180011cdd  neg     rdx
0x180011ce0  sbb     eax, eax
0x180011ce2  not     eax
0x180011ce4  and     eax, 8007007Ah
0x180011ce9  mov     [rcx], r10w
0x180011ced  jmp     short loc_180011D07
0x180011cef  mov     esi, 1
0x180011cf4  jmp     loc_180011C11
0x180011cf9  mov     eax, 80070057h
0x180011cfe  test    r13d, r13d
0x180011d01  jnz     loc_180011DD9
0x180011d07  test    eax, eax
0x180011d09  jnz     loc_180011DB8
0x180011d0f  mov     rdx, r12; unsigned __int16 *
0x180011d12  mov     rcx, rbx; this
0x180011d15  call    ?ConvertNtPathToWin32@Win32LiveSystemProvider@@AEAAJPEAG@Z; Win32LiveSystemProvider::ConvertNtPathToWin32(ushort *)
0x180011d1a  test    eax, eax
0x180011d1c  jnz     loc_180011DB8
0x180011d22  mov     rcx, [rbx+30h]
0x180011d26  mov     rdx, r14
0x180011d29  mov     rax, [rcx]
0x180011d2c  mov     rax, [rax+18h]
0x180011d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d35  xor     r14d, r14d
0x180011d38  test    edi, edi
0x180011d3a  js      loc_180011DE5
0x180011d40  mov     rdi, [rbp+57h+arg_8]
0x180011d44  mov     rax, qword ptr [rbp+57h+var_88]
0x180011d48  add     rax, qword ptr [rbp+57h+VirtualMemoryInformation]
0x180011d4c  mov     [rbx+2B8h], rax
0x180011d53  test    r15d, r15d
0x180011d56  jz      short loc_180011DA6
0x180011d58  test    esi, esi
0x180011d5a  jnz     short loc_180011DA6
0x180011d5c  xor     eax, eax
0x180011d5e  jmp     short loc_180011DB8
0x180011d60  cmp     eax, 0C0000141h
0x180011d65  jnz     short loc_180011DD3
0x180011d67  mov     rdx, [rbx+2B8h]; Address
0x180011d6e  lea     r9, [rbp+57h+var_68]; VirtualMemoryInformation
0x180011d72  mov     rcx, [rbx+290h]; ProcessHandle
0x180011d79  xor     r8d, r8d; VirtualMemoryInformationClass
0x180011d7c  mov     [rsp+0E0h+ResultLength], r14; ResultLength
0x180011d81  mov     [rsp+0E0h+Length], 30h ; '0'; Length
0x180011d8a  call    cs:__imp_NtQueryVirtualMemory
0x180011d90  test    eax, eax
0x180011d92  js      short loc_180011DD3
0x180011d94  mov     rax, qword ptr [rbp+57h+var_58+8]
0x180011d98  add     [rbx+2B8h], rax
0x180011d9f  mov     rax, [rbx+2B8h]
0x180011da6  cmp     rax, [rbx+338h]
0x180011dad  jb      loc_180011B50
0x180011db3  mov     eax, 1
0x180011db8  mov     rbx, [rsp+0E0h+arg_10]
0x180011dc0  add     rsp, 0B0h
0x180011dc7  pop     r15
0x180011dc9  pop     r14
0x180011dcb  pop     r13
0x180011dcd  pop     r12
0x180011dcf  pop     rdi
0x180011dd0  pop     rsi
0x180011dd1  pop     rbp
0x180011dd2  retn
0x180011dd3  bts     eax, 1Ch
0x180011dd7  jmp     short loc_180011DB8
0x180011dd9  mov     [r12], r10w
0x180011dde  mov     eax, 80070057h
0x180011de3  jmp     short loc_180011DB8
0x180011de5  mov     eax, edi
0x180011de7  mov     ecx, 80070057h
0x180011dec  bts     eax, 1Ch
0x180011df0  cmp     edi, 80000005h
0x180011df6  cmovz   eax, ecx
0x180011df9  jmp     short loc_180011DB8
0x180011dfb  mov     eax, 8007000Eh
0x180011e00  jmp     short loc_180011DB8
```
