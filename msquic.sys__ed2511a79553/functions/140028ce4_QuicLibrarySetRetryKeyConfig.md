# QuicLibrarySetRetryKeyConfig

- ea: `0x140028ce4`
- end: `0x140028ed7`
- name: `QuicLibrarySetRetryKeyConfig`
- size: `499`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x140028728`
- `0x140028b3c`
- `0x14003f350`

## callees

- `0x140028040`
- `0x140028ce4`
- `0x14003c8e0`
- `0x14003cb00`
- `0x14003ead8`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140028d3a`
- `ntoskrnl!_snprintf_s` at `0x140028db1`
- `ntoskrnl!_snprintf_s` at `0x140028e48`
- `ntoskrnl!_snprintf_s` at `0x140028e8b`
- `ntoskrnl!_snprintf_s` at `0x140028d3a`
- `ntoskrnl!_snprintf_s` at `0x140028db1`
- `ntoskrnl!_snprintf_s` at `0x140028e48`
- `ntoskrnl!_snprintf_s` at `0x140028e8b`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140028e11`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140028e11`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140028dc9`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140028dc9`

## string_xrefs

- `0x140028e29`: `[ lib] Stateless Retry Key updated. Algorithm: %d, RotationMs: %u`

## pseudocode

```c
__int64 __fastcall QuicLibrarySetRetryKeyConfig(_DWORD *a1)
{
  __int64 v2; // rcx
  unsigned int v3; // ecx
  unsigned __int16 v4; // ax
  int v5; // ecx
  size_t v6; // rsi
  KIRQL v7; // al
  UCHAR *v8; // rdx
  KIRQL v9; // bp
  __int64 v10; // rcx
  int v12; // [rsp+20h] [rbp-A8h]
  unsigned int v13; // [rsp+20h] [rbp-A8h]
  char DstBuf[128]; // [rsp+30h] [rbp-98h] BYREF

  if ( !*((_QWORD *)a1 + 2) )
  {
    if ( (byte_14005C48E & 0x10) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[ lib] Invalid retry key secret: NULL.");
LABEL_18:
      McTemplateU0s_EtwWriteTransfer(v2, QuicLogError, DstBuf);
      return 3221225485LL;
    }
    return 3221225485LL;
  }
  v3 = *a1;
  if ( v3 > 1 )
  {
    if ( (byte_14005C48E & 0x10) != 0 )
    {
      v13 = v3;
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[ lib] Invalid retry key algorithm: %d.", v13);
      goto LABEL_18;
    }
    return 3221225485LL;
  }
  if ( !a1[1] )
  {
    if ( (byte_14005C48E & 0x10) != 0 )
    {
      v12 = 0;
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[ lib] Invalid retry key rotation ms: %u.", v12);
      goto LABEL_18;
    }
    return 3221225485LL;
  }
  v4 = CxPlatKeyLength();
  v5 = a1[2];
  v6 = v4;
  if ( v5 != v4 )
  {
    if ( (byte_14005C48E & 0x10) != 0 )
    {
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "[ lib] Invalid retry key secret length: %u. Expected %u.",
        v5,
        v4);
      goto LABEL_18;
    }
    return 3221225485LL;
  }
  v7 = ExAcquireSpinLockExclusive(&dword_14005C5C8);
  v8 = (UCHAR *)*((_QWORD *)a1 + 2);
  v9 = v7;
  if ( v8 != &pbSecret )
  {
    memmove(&pbSecret, v8, v6);
    cbSecret = v6;
  }
  dword_14005C5F0 = *a1;
  dword_14005C5F4 = a1[1];
  ExReleaseSpinLockExclusive(&dword_14005C5C8, v9);
  if ( (byte_14005C48E & 0x40) != 0 )
  {
    _snprintf_s(
      DstBuf,
      0x80u,
      0xFFFFFFFFFFFFFFFFuLL,
      "[ lib] Stateless Retry Key updated. Algorithm: %d, RotationMs: %u",
      *a1,
      a1[1]);
    McTemplateU0s_EtwWriteTransfer(v10, QuicLogInfo, DstBuf);
  }
  return 0;
}

```

## disassembly

```asm
0x140028ce4  mov     [rsp+arg_8], rbx
0x140028ce9  mov     [rsp+arg_10], rbp
0x140028cee  mov     [rsp+arg_18], rsi
0x140028cf3  push    rdi
0x140028cf4  sub     rsp, 0C0h
0x140028cfb  mov     rax, cs:__security_cookie
0x140028d02  xor     rax, rsp
0x140028d05  mov     [rsp+0C8h+var_18], rax
0x140028d0d  xor     edx, edx
0x140028d0f  mov     rbx, rcx
0x140028d12  cmp     [rcx+10h], rdx
0x140028d16  jnz     short loc_140028D4B
0x140028d18  test    cs:byte_14005C48E, 10h
0x140028d1f  jz      loc_140028EA8
0x140028d25  lea     r9, aLibInvalidRetr_1; "[ lib] Invalid retry key secret: NULL."
0x140028d2c  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140028d30  mov     edx, 80h; SizeInBytes
0x140028d35  lea     rcx, [rsp+0C8h+DstBuf]; DstBuf
0x140028d3a  call    cs:__imp__snprintf_s
0x140028d41  nop     dword ptr [rax+rax+00h]
0x140028d46  jmp     loc_140028E97
0x140028d4b  mov     ecx, [rcx]
0x140028d4d  cmp     ecx, 1
0x140028d50  ja      loc_140028E69
0x140028d56  cmp     [rbx+4], edx
0x140028d59  jnz     short loc_140028D78
0x140028d5b  test    cs:byte_14005C48E, 10h
0x140028d62  jz      loc_140028EA8
0x140028d68  mov     [rsp+0C8h+var_A8], edx
0x140028d6c  lea     r9, aLibInvalidRetr_2; "[ lib] Invalid retry key rotation ms: %"...
0x140028d73  jmp     loc_140028E7D
0x140028d78  call    CxPlatKeyLength
0x140028d7d  mov     ecx, [rbx+8]
0x140028d80  movzx   esi, ax
0x140028d83  cmp     ecx, esi
0x140028d85  jz      short loc_140028DC2
0x140028d87  test    cs:byte_14005C48E, 10h
0x140028d8e  jz      loc_140028EA8
0x140028d94  mov     [rsp+0C8h+var_A0], esi
0x140028d98  lea     r9, aLibInvalidRetr; "[ lib] Invalid retry key secret length:"...
0x140028d9f  mov     [rsp+0C8h+var_A8], ecx
0x140028da3  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140028da7  lea     rcx, [rsp+0C8h+DstBuf]; DstBuf
0x140028dac  mov     edx, 80h; SizeInBytes
0x140028db1  call    cs:__imp__snprintf_s
0x140028db8  nop     dword ptr [rax+rax+00h]
0x140028dbd  jmp     loc_140028E97
0x140028dc2  lea     rcx, dword_14005C5C8; SpinLock
0x140028dc9  call    cs:__imp_ExAcquireSpinLockExclusive
0x140028dd0  nop     dword ptr [rax+rax+00h]
0x140028dd5  mov     rdx, [rbx+10h]; Src
0x140028dd9  lea     rcx, pbSecret; void *
0x140028de0  mov     bpl, al
0x140028de3  cmp     rdx, rcx
0x140028de6  jz      short loc_140028DF6
0x140028de8  mov     r8, rsi; Size
0x140028deb  call    memmove
0x140028df0  mov     cs:cbSecret, esi
0x140028df6  mov     edx, [rbx]
0x140028df8  lea     rcx, dword_14005C5C8; SpinLock
0x140028dff  mov     cs:dword_14005C5F0, edx
0x140028e05  mov     dl, bpl; OldIrql
0x140028e08  mov     eax, [rbx+4]
0x140028e0b  mov     cs:dword_14005C5F4, eax
0x140028e11  call    cs:__imp_ExReleaseSpinLockExclusive
0x140028e18  nop     dword ptr [rax+rax+00h]
0x140028e1d  test    cs:byte_14005C48E, 40h
0x140028e24  jz      short loc_140028E65
0x140028e26  mov     eax, [rbx+4]
0x140028e29  lea     r9, aLibStatelessRe; "[ lib] Stateless Retry Key updated. Alg"...
0x140028e30  mov     [rsp+0C8h+var_A0], eax
0x140028e34  lea     rcx, [rsp+0C8h+DstBuf]; DstBuf
0x140028e39  mov     eax, [rbx]
0x140028e3b  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140028e3f  mov     edx, 80h; SizeInBytes
0x140028e44  mov     [rsp+0C8h+var_A8], eax
0x140028e48  call    cs:__imp__snprintf_s
0x140028e4f  nop     dword ptr [rax+rax+00h]
0x140028e54  lea     r8, [rsp+0C8h+DstBuf]
0x140028e59  lea     rdx, QuicLogInfo
0x140028e60  call    McTemplateU0s_EtwWriteTransfer
0x140028e65  xor     eax, eax
0x140028e67  jmp     short loc_140028EAD
0x140028e69  test    cs:byte_14005C48E, 10h
0x140028e70  jz      short loc_140028EA8
0x140028e72  mov     [rsp+0C8h+var_A8], ecx
0x140028e76  lea     r9, aLibInvalidRetr_0; "[ lib] Invalid retry key algorithm: %d."
0x140028e7d  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140028e81  lea     rcx, [rsp+0C8h+DstBuf]; DstBuf
0x140028e86  mov     edx, 80h; SizeInBytes
0x140028e8b  call    cs:__imp__snprintf_s
0x140028e92  nop     dword ptr [rax+rax+00h]
0x140028e97  lea     r8, [rsp+0C8h+DstBuf]
0x140028e9c  lea     rdx, QuicLogError
0x140028ea3  call    McTemplateU0s_EtwWriteTransfer
0x140028ea8  mov     eax, 0C000000Dh
0x140028ead  mov     rcx, [rsp+0C8h+var_18]
0x140028eb5  xor     rcx, rsp; StackCookie
0x140028eb8  call    __security_check_cookie
0x140028ebd  lea     r11, [rsp+0C8h+var_8]
0x140028ec5  mov     rbx, [r11+18h]
0x140028ec9  mov     rbp, [r11+20h]
0x140028ecd  mov     rsi, [r11+28h]
0x140028ed1  mov     rsp, r11
0x140028ed4  pop     rdi
0x140028ed5  retn
```
