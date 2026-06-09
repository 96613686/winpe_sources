# AllocateObjectBuffer

- ea: `0x180003b10`
- end: `0x180003c5d`
- name: `AllocateObjectBuffer`
- size: `333`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800020c0`
- `0x180002f90`
- `0x1800352f0`
- `0x1800395a0`

## callees

- `0x180003b10`
- `0x180003c70`
- `0x18000743c`
- `0x1800082b0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180003b85`
- `ntoskrnl!ExAllocatePool2` at `0x180003b85`
- `ntoskrnl!SkIsSecureKernel` at `0x180003bd8`
- `ntoskrnl!SkIsSecureKernel` at `0x180003bd8`
- `ntoskrnl!SkAllocatePool` at `0x180003c24`
- `ntoskrnl!SkAllocatePool` at `0x180003c24`

## string_xrefs

- `0x180003bf9`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180003c3b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall AllocateObjectBuffer(void *a1, __int64 *a2, unsigned int *a3)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  NTSTATUS Property; // ebx
  __int64 v8; // rbx
  int v9; // eax
  __int64 Pool; // rax
  ULONG v12[14]; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v13; // [rsp+98h] [rbp+20h] BYREF

  v13 = 0;
  v12[0] = 0;
  Property = BCryptGetProperty(a1, L"ObjectLength", (PUCHAR)&v13, 4u, v12, 0);
  if ( Property < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v5,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        (unsigned int)"Status",
        Property,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        227);
    return (unsigned int)Property;
  }
  else
  {
    v8 = v13;
    if ( !v13 )
      v8 = 8;
    LOBYTE(v9) = g_TrustedEnvironment;
    if ( !g_TrustedEnvironment )
    {
      v9 = ((int)SkIsSecureKernel(v6, v5) >> 31) + 2;
      g_TrustedEnvironment = v9;
    }
    if ( (v9 & 2) != 0 )
      Pool = SkAllocatePool(512, v8, 1650945603);
    else
      Pool = ExAllocatePool2(64, v8, 1650945603);
    if ( Pool )
    {
      *a2 = Pool;
      *a3 = v13;
      return 0;
    }
    else
    {
      DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 1003);
      return 3221225495LL;
    }
  }
}

```

## disassembly

```asm
0x180003b10  mov     r11, rsp
0x180003b13  push    rbx
0x180003b14  push    rbp
0x180003b15  push    rsi
0x180003b16  push    rdi
0x180003b17  sub     rsp, 58h
0x180003b1b  xor     ebp, ebp
0x180003b1d  lea     rax, [r11-38h]
0x180003b21  mov     rdi, r8
0x180003b24  mov     [rsp+78h+dwFlags], ebp; dwFlags
0x180003b28  mov     rsi, rdx
0x180003b2b  mov     [r11-58h], rax
0x180003b2f  mov     r9d, 4; cbOutput
0x180003b35  mov     [r11+20h], ebp
0x180003b39  lea     r8, [r11+20h]; pbOutput
0x180003b3d  mov     [rsp+78h+var_38], ebp
0x180003b41  lea     rdx, aObjectlength; "ObjectLength"
0x180003b48  call    BCryptGetProperty
0x180003b4d  mov     ebx, eax
0x180003b4f  test    eax, eax
0x180003b51  js      short loc_180003BB2
0x180003b53  mov     ebx, [rsp+78h+arg_18]
0x180003b5a  mov     eax, 8
0x180003b5f  test    rbx, rbx
0x180003b62  cmovz   ebx, eax
0x180003b65  mov     eax, cs:g_TrustedEnvironment
0x180003b6b  test    eax, eax
0x180003b6d  jz      short loc_180003BD8
0x180003b6f  mov     r8d, 62676E43h
0x180003b75  mov     rdx, rbx
0x180003b78  test    al, 2
0x180003b7a  jnz     loc_180003C1F
0x180003b80  mov     ecx, 40h ; '@'
0x180003b85  call    cs:__imp_ExAllocatePool2
0x180003b8c  nop     dword ptr [rax+rax+00h]
0x180003b91  test    rax, rax
0x180003b94  jz      loc_180003C35
0x180003b9a  mov     [rsi], rax
0x180003b9d  mov     eax, [rsp+78h+arg_18]
0x180003ba4  mov     [rdi], eax
0x180003ba6  mov     eax, ebp
0x180003ba8  add     rsp, 58h
0x180003bac  pop     rdi
0x180003bad  pop     rsi
0x180003bae  pop     rbp
0x180003baf  pop     rbx
0x180003bb0  retn
0x180003bb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180003bb9  lea     rax, WPP_GLOBAL_Control
0x180003bc0  cmp     rcx, rax
0x180003bc3  jz      short loc_180003BCC
0x180003bc5  mov     eax, [rcx+2Ch]
0x180003bc8  test    al, 1
0x180003bca  jnz     short loc_180003BF5
0x180003bcc  mov     eax, ebx
0x180003bce  add     rsp, 58h
0x180003bd2  pop     rdi
0x180003bd3  pop     rsi
0x180003bd4  pop     rbp
0x180003bd5  pop     rbx
0x180003bd6  retn
0x180003bd8  call    cs:__imp_SkIsSecureKernel
0x180003bdf  nop     dword ptr [rax+rax+00h]
0x180003be4  sar     eax, 1Fh
0x180003be7  add     eax, 2
0x180003bea  mov     cs:g_TrustedEnvironment, eax
0x180003bf0  jmp     loc_180003B6F
0x180003bf5  mov     rcx, [rcx+18h]
0x180003bf9  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003c00  mov     [rsp+78h+var_48], 3E3h
0x180003c08  lea     r9, aStatus; "Status"
0x180003c0f  mov     qword ptr [rsp+78h+dwFlags], r8
0x180003c14  mov     [rsp+78h+var_58], ebx
0x180003c18  call    WPP_SF_sDsd
0x180003c1d  jmp     short loc_180003BCC
0x180003c1f  mov     ecx, 200h
0x180003c24  call    cs:__imp_SkAllocatePool
0x180003c2b  nop     dword ptr [rax+rax+00h]
0x180003c30  jmp     loc_180003B91
0x180003c35  mov     r9d, 3EBh
0x180003c3b  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003c42  lea     rdx, aStatus; "Status"
0x180003c49  mov     ecx, 0C0000017h
0x180003c4e  call    DebugTraceError
0x180003c53  mov     eax, 0C0000017h
0x180003c58  jmp     loc_180003BA8
```
