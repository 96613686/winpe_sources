# LdrpGetModuleName

- ea: `0x1800789f0`
- end: `0x180078c27`
- name: `LdrpGetModuleName`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800f84e0`

## callees

- `0x180023340`
- `0x180077e50`
- `0x1800789f0`
- `0x180078c30`
- `0x180078fa0`
- `0x180128940`
- `0x180162810`
- `0x18016f020`

## string_xrefs

- `0x180078b8b`: `\system32`

## pseudocode

```c
NTSTATUS __fastcall LdrpGetModuleName(__int64 *a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v5; // rcx
  unsigned __int16 v6; // bx
  bool v7; // cf
  __int64 v10; // rdx
  __int64 (__fastcall *v11)(__int64, __int64, wchar_t *, _QWORD, _QWORD *); // rax
  NTSTATUS result; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  char *v16; // rax
  __int16 v17; // dx
  const wchar_t *NtSystemRoot; // rax
  __int64 v19; // rcx
  size_t v20; // rdi
  __int64 v21; // rcx
  _WORD v22[8]; // [rsp+30h] [rbp-D0h] BYREF
  UNICODE_STRING SourceString; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v24[2]; // [rsp+50h] [rbp-B0h] BYREF
  STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t String1[264]; // [rsp+70h] [rbp-90h] BYREF

  v5 = *a1;
  v6 = 512;
  v7 = *(_WORD *)a2 < 0x200u;
  *(_DWORD *)(&DestinationString.MaximumLength + 1) = 0;
  if ( v7 )
    v6 = *(_WORD *)a2;
  v10 = *(_QWORD *)(a2 + 8);
  v11 = (__int64 (__fastcall *)(__int64, __int64, wchar_t *, _QWORD, _QWORD *))a1[1];
  *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
  v22[0] = 0;
  v24[0] = 0;
  result = v11(v5, v10, String1, v6, v24);
  if ( result >= 0 )
  {
    if ( v24[0] == v6 )
    {
      String1[256] = 0;
      if ( !a4 )
        goto LABEL_6;
      NtSystemRoot = (const wchar_t *)RtlGetNtSystemRoot(v14, v13, v15);
      v19 = -1;
      do
        ++v19;
      while ( NtSystemRoot[v19] );
      if ( !v19 )
        return -1073741595;
      v20 = v19 - 1;
      if ( NtSystemRoot[v19 - 1] != 92 )
        v20 = v19;
      if ( wcsnicmp(String1, NtSystemRoot, v20) || wcsnicmp(&String1[v20], L"\\system32", 9u) )
        goto LABEL_6;
      if ( v20 + 16 >= 0x101 )
        return -1073741595;
      v21 = *a1;
      if ( !*a1 )
        v21 = -1;
      if ( (int)RtlWow64GetProcessMachines(v21, v22, 0) >= 0
        && (SourceString.Buffer = String1,
            SourceString.MaximumLength = v6,
            SourceString.Length = v6,
            HIDWORD(v24[0]) = *(_DWORD *)(&SourceString.MaximumLength + 1),
            LOWORD(v24[0]) = v6 - 2 * v20,
            WORD1(v24[0]) = v24[0],
            v24[1] = &String1[v20],
            (int)RtlReplaceSystemDirectoryInPath(v24, 1, v22[0], 0) >= 0) )
      {
LABEL_6:
        SourceString.MaximumLength = v6;
        SourceString.Buffer = String1;
        SourceString.Length = v6;
        DestinationString.Buffer = (char *)(a3 + 40);
        *(_DWORD *)&DestinationString.Length = 0x1000000;
        result = RtlUnicodeStringToAnsiString(&DestinationString, &SourceString, 0);
        if ( result >= 0 )
        {
          v16 = &DestinationString.Buffer[DestinationString.Length];
          do
          {
            v17 = (__int16)v16;
            if ( v16 <= DestinationString.Buffer )
              break;
            --v16;
          }
          while ( *v16 != 92 );
          *(_WORD *)(a3 + 38) = v17 - LOWORD(DestinationString.Buffer);
          return 0;
        }
      }
      else
      {
        return -1073741595;
      }
    }
    else
    {
      return -2147483635;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800789f0  push    rbp
0x1800789f2  push    rbx
0x1800789f3  push    rsi
0x1800789f4  push    rdi
0x1800789f5  push    r12
0x1800789f7  push    r14
0x1800789f9  push    r15
0x1800789fb  lea     rbp, [rsp-190h]
0x180078a03  sub     rsp, 290h
0x180078a0a  mov     rax, cs:__security_cookie
0x180078a11  xor     rax, rsp
0x180078a14  mov     [rbp+1C0h+var_40], rax
0x180078a1b  xor     r12d, r12d
0x180078a1e  lea     rax, [rsp+2C0h+var_270]
0x180078a23  mov     r15, rcx
0x180078a26  mov     [rsp+2C0h+var_2A0], rax
0x180078a2b  mov     rcx, [rcx]
0x180078a2e  mov     ebx, 200h
0x180078a33  cmp     [rdx], bx
0x180078a36  mov     r14d, r9d
0x180078a39  mov     rsi, r8
0x180078a3c  mov     dword ptr [rsp+2C0h+DestinationString+4], r12d
0x180078a41  cmovb   bx, [rdx]
0x180078a45  lea     r8, [rsp+2C0h+String1]
0x180078a4a  mov     rdx, [rdx+8]
0x180078a4e  mov     rax, [r15+8]
0x180078a52  movzx   edi, bx
0x180078a55  mov     r9d, edi
0x180078a58  mov     dword ptr [rsp+2C0h+SourceString+4], r12d
0x180078a5d  mov     [rsp+2C0h+var_290], r12w
0x180078a63  mov     qword ptr [rsp+2C0h+var_270], r12
0x180078a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078a6d  test    eax, eax
0x180078a6f  js      loc_180078B02
0x180078a75  cmp     qword ptr [rsp+2C0h+var_270], rdi
0x180078a7a  jnz     loc_180078B24
0x180078a80  mov     [rsp+2C0h+arg_18], r13
0x180078a88  mov     [rbp+1C0h+var_50], r12w
0x180078a90  test    r14d, r14d
0x180078a93  jnz     loc_180078B2B
0x180078a99  lea     rax, [rsp+2C0h+String1]
0x180078a9e  mov     [rsp+2C0h+SourceString.MaximumLength], bx
0x180078aa3  mov     [rsp+2C0h+SourceString.Buffer], rax
0x180078aa8  lea     rdx, [rsp+2C0h+SourceString]; SourceString
0x180078aad  lea     rax, [rsi+28h]
0x180078ab1  mov     [rsp+2C0h+SourceString.Length], bx
0x180078ab6  xor     r8d, r8d; AllocateDestinationString
0x180078ab9  mov     [rsp+2C0h+DestinationString.Buffer], rax
0x180078abe  lea     rcx, [rsp+2C0h+DestinationString]; DestinationString
0x180078ac3  mov     dword ptr [rsp+2C0h+DestinationString.Length], 1000000h
0x180078acb  call    RtlUnicodeStringToAnsiString
0x180078ad0  test    eax, eax
0x180078ad2  js      short loc_180078AFA
0x180078ad4  movzx   eax, [rsp+2C0h+DestinationString.Length]
0x180078ad9  mov     rcx, [rsp+2C0h+DestinationString.Buffer]
0x180078ade  add     rax, rcx
0x180078ae1  movzx   edx, ax
0x180078ae4  cmp     rax, rcx
0x180078ae7  jbe     short loc_180078AF1
0x180078ae9  dec     rax
0x180078aec  cmp     byte ptr [rax], 5Ch ; '\'
0x180078aef  jnz     short loc_180078AE1
0x180078af1  sub     dx, cx
0x180078af4  mov     [rsi+26h], dx
0x180078af8  xor     eax, eax
0x180078afa  mov     r13, [rsp+2C0h+arg_18]
0x180078b02  mov     rcx, [rbp+1C0h+var_40]
0x180078b09  xor     rcx, rsp; StackCookie
0x180078b0c  call    __security_check_cookie
0x180078b11  add     rsp, 290h
0x180078b18  pop     r15
0x180078b1a  pop     r14
0x180078b1c  pop     r12
0x180078b1e  pop     rdi
0x180078b1f  pop     rsi
0x180078b20  pop     rbx
0x180078b21  pop     rbp
0x180078b22  retn
0x180078b24  mov     eax, 8000000Dh
0x180078b29  jmp     short loc_180078B02
0x180078b2b  call    RtlGetNtSystemRoot
0x180078b30  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180078b37  mov     rcx, r13
0x180078b3a  nop     word ptr [rax+rax+00h]
0x180078b40  inc     rcx
0x180078b43  cmp     [rax+rcx*2], r12w
0x180078b48  jnz     short loc_180078B40
0x180078b4a  test    rcx, rcx
0x180078b4d  jz      loc_180078C1D
0x180078b53  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x180078b59  lea     rdi, [rcx-1]
0x180078b5d  mov     rdx, rax; String2
0x180078b60  cmovnz  rdi, rcx
0x180078b64  lea     rcx, [rsp+2C0h+String1]; String1
0x180078b69  mov     r8, rdi; MaxCount
0x180078b6c  call    _wcsnicmp
0x180078b71  test    eax, eax
0x180078b73  jnz     loc_180078A99
0x180078b79  lea     r14, [rsp+2C0h+String1]
0x180078b7e  mov     r8d, 9; MaxCount
0x180078b84  lea     r14, [r14+rdi*2]
0x180078b88  mov     rcx, r14; String1
0x180078b8b  lea     rdx, aSystem32_1; "\\system32"
0x180078b92  call    _wcsnicmp
0x180078b97  test    eax, eax
0x180078b99  jnz     loc_180078A99
0x180078b9f  lea     rax, [rdi+10h]
0x180078ba3  cmp     rax, 101h
0x180078ba9  jnb     short loc_180078C1D
0x180078bab  mov     rcx, [r15]
0x180078bae  lea     rdx, [rsp+2C0h+var_290]
0x180078bb3  test    rcx, rcx
0x180078bb6  cmovz   rcx, r13
0x180078bba  xor     r8d, r8d
0x180078bbd  call    RtlWow64GetProcessMachines
0x180078bc2  test    eax, eax
0x180078bc4  js      short loc_180078C1D
0x180078bc6  movzx   r8d, [rsp+2C0h+var_290]
0x180078bcc  lea     rax, [rsp+2C0h+String1]
0x180078bd1  mov     [rsp+2C0h+SourceString.Buffer], rax
0x180078bd6  lea     rcx, [rsp+2C0h+var_270]
0x180078bdb  movzx   eax, bx
0x180078bde  mov     [rsp+2C0h+SourceString.MaximumLength], bx
0x180078be3  mov     [rsp+2C0h+SourceString.Length], bx
0x180078be8  add     di, di
0x180078beb  movaps  xmm0, xmmword ptr [rsp+2C0h+SourceString.Length]
0x180078bf0  sub     ax, di
0x180078bf3  movdqa  [rsp+2C0h+var_270], xmm0
0x180078bf9  mov     edx, 1
0x180078bfe  xor     r9d, r9d
0x180078c01  mov     word ptr [rsp+2C0h+var_270], ax
0x180078c06  mov     word ptr [rsp+2C0h+var_270+2], ax
0x180078c0b  mov     qword ptr [rsp+2C0h+var_270+8], r14
0x180078c10  call    RtlReplaceSystemDirectoryInPath
0x180078c15  test    eax, eax
0x180078c17  jns     loc_180078A99
0x180078c1d  mov     eax, 0C00000E5h
0x180078c22  jmp     loc_180078AFA
```
