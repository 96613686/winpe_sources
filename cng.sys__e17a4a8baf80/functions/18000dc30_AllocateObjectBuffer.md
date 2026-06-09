# AllocateObjectBuffer

- ea: `0x18000dc30`
- end: `0x18000dd7d`
- name: `AllocateObjectBuffer`
- size: `333`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c1e0`
- `0x18000d0b0`
- `0x18003f360`
- `0x180043610`

## callees

- `0x18000dc30`
- `0x18000dd90`
- `0x18001155c`
- `0x1800123d0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000dca5`
- `ntoskrnl!ExAllocatePool2` at `0x18000dca5`
- `ntoskrnl!SkIsSecureKernel` at `0x18000dcf8`
- `ntoskrnl!SkIsSecureKernel` at `0x18000dcf8`
- `ntoskrnl!SkAllocatePool` at `0x18000dd44`
- `ntoskrnl!SkAllocatePool` at `0x18000dd44`

## string_xrefs

- `0x18000dd19`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000dd5b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
0x18000dc30  mov     r11, rsp
0x18000dc33  push    rbx
0x18000dc34  push    rbp
0x18000dc35  push    rsi
0x18000dc36  push    rdi
0x18000dc37  sub     rsp, 58h
0x18000dc3b  xor     ebp, ebp
0x18000dc3d  lea     rax, [r11-38h]
0x18000dc41  mov     rdi, r8
0x18000dc44  mov     [rsp+78h+dwFlags], ebp; dwFlags
0x18000dc48  mov     rsi, rdx
0x18000dc4b  mov     [r11-58h], rax
0x18000dc4f  mov     r9d, 4; cbOutput
0x18000dc55  mov     [r11+20h], ebp
0x18000dc59  lea     r8, [r11+20h]; pbOutput
0x18000dc5d  mov     [rsp+78h+var_38], ebp
0x18000dc61  lea     rdx, aObjectlength; "ObjectLength"
0x18000dc68  call    BCryptGetProperty
0x18000dc6d  mov     ebx, eax
0x18000dc6f  test    eax, eax
0x18000dc71  js      short loc_18000DCD2
0x18000dc73  mov     ebx, [rsp+78h+arg_18]
0x18000dc7a  mov     eax, 8
0x18000dc7f  test    rbx, rbx
0x18000dc82  cmovz   ebx, eax
0x18000dc85  mov     eax, cs:g_TrustedEnvironment
0x18000dc8b  test    eax, eax
0x18000dc8d  jz      short loc_18000DCF8
0x18000dc8f  mov     r8d, 62676E43h
0x18000dc95  mov     rdx, rbx
0x18000dc98  test    al, 2
0x18000dc9a  jnz     loc_18000DD3F
0x18000dca0  mov     ecx, 40h ; '@'
0x18000dca5  call    cs:__imp_ExAllocatePool2
0x18000dcac  nop     dword ptr [rax+rax+00h]
0x18000dcb1  test    rax, rax
0x18000dcb4  jz      loc_18000DD55
0x18000dcba  mov     [rsi], rax
0x18000dcbd  mov     eax, [rsp+78h+arg_18]
0x18000dcc4  mov     [rdi], eax
0x18000dcc6  mov     eax, ebp
0x18000dcc8  add     rsp, 58h
0x18000dccc  pop     rdi
0x18000dccd  pop     rsi
0x18000dcce  pop     rbp
0x18000dccf  pop     rbx
0x18000dcd0  retn
0x18000dcd2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcd9  lea     rax, WPP_GLOBAL_Control
0x18000dce0  cmp     rcx, rax
0x18000dce3  jz      short loc_18000DCEC
0x18000dce5  mov     eax, [rcx+2Ch]
0x18000dce8  test    al, 1
0x18000dcea  jnz     short loc_18000DD15
0x18000dcec  mov     eax, ebx
0x18000dcee  add     rsp, 58h
0x18000dcf2  pop     rdi
0x18000dcf3  pop     rsi
0x18000dcf4  pop     rbp
0x18000dcf5  pop     rbx
0x18000dcf6  retn
0x18000dcf8  call    cs:__imp_SkIsSecureKernel
0x18000dcff  nop     dword ptr [rax+rax+00h]
0x18000dd04  sar     eax, 1Fh
0x18000dd07  add     eax, 2
0x18000dd0a  mov     cs:g_TrustedEnvironment, eax
0x18000dd10  jmp     loc_18000DC8F
0x18000dd15  mov     rcx, [rcx+18h]
0x18000dd19  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000dd20  mov     [rsp+78h+var_48], 3E3h
0x18000dd28  lea     r9, aStatus; "Status"
0x18000dd2f  mov     qword ptr [rsp+78h+dwFlags], r8
0x18000dd34  mov     [rsp+78h+var_58], ebx
0x18000dd38  call    WPP_SF_sDsd
0x18000dd3d  jmp     short loc_18000DCEC
0x18000dd3f  mov     ecx, 200h
0x18000dd44  call    cs:__imp_SkAllocatePool
0x18000dd4b  nop     dword ptr [rax+rax+00h]
0x18000dd50  jmp     loc_18000DCB1
0x18000dd55  mov     r9d, 3EBh
0x18000dd5b  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000dd62  lea     rdx, aStatus; "Status"
0x18000dd69  mov     ecx, 0C0000017h
0x18000dd6e  call    DebugTraceError
0x18000dd73  mov     eax, 0C0000017h
0x18000dd78  jmp     loc_18000DCC8
```
