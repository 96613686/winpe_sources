# I_CreateProtectionDescriptor

- ea: `0x18000962c`
- end: `0x180009824`
- name: `I_CreateProtectionDescriptor`
- size: `504`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800058b0`
- `0x180015490`

## callees

- `0x1800079cc`
- `0x180007ae0`
- `0x180008cfc`
- `0x1800090e0`
- `0x18000962c`
- `0x180009cd0`
- `0x180009ecc`
- `0x18000d02c`
- `0x18000e120`
- `0x18001f15d`

## string_xrefs

- `0x1800096c2`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x18000979a`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x1800097dd`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x1800097f8`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`

## pseudocode

```c
__int64 __fastcall I_CreateProtectionDescriptor(const wchar_t *Src, __int64 a2, unsigned int a3, int a4, __int64 *a5)
{
  int v8; // edx
  unsigned int v9; // edi
  size_t v10; // rdi
  __int64 v11; // rdi
  __int64 v12; // rax
  int v13; // edx
  __int64 v14; // rbx
  __int64 v16; // rcx
  unsigned int v17; // eax
  unsigned int v18; // eax
  __int64 v19; // [rsp+88h] [rbp+10h] BYREF

  v19 = 0;
  if ( a2 )
  {
    v18 = CNG_DuplicateDescriptor(a2, &v19, 1);
    v9 = v18;
    if ( v18 )
    {
      DebugTraceError(
        v18,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
        165);
      goto LABEL_11;
    }
  }
  else
  {
    v9 = CNG_DescriptorStringToDescriptor(Src, &v19);
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v8,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
          (unsigned int)"Status",
          v9,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
          152);
      goto LABEL_11;
    }
  }
  v10 = 0;
  if ( Src )
  {
    v11 = -1;
    do
      ++v11;
    while ( Src[v11] );
    v10 = 2 * v11 + 2;
  }
  v12 = SafeAllocaAllocateFromHeap(v10 + 40);
  v14 = v12;
  if ( v12 )
  {
    *(_QWORD *)(v12 + 8) = 0;
    *(_QWORD *)(v12 + 16) = 0;
    *(_QWORD *)(v12 + 24) = 0;
    *(_QWORD *)(v12 + 32) = 0;
    *(_DWORD *)v12 = 40;
    *(_DWORD *)(v12 + 4) = a4;
    if ( v10 )
    {
      *(_QWORD *)(v12 + 16) = v12 + 40;
      memcpy_0((void *)(v12 + 40), Src, v10);
    }
    v16 = v19;
    *(_QWORD *)(v14 + 8) = v19;
    v19 = 0;
    v17 = CNG_OpenProtectionDescriptor(v16, a3);
    v9 = v17;
    if ( v17 )
    {
      DebugTraceError(
        v17,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
        213);
      NCryptCloseProtectionDescriptor(v14);
      return v9;
    }
    v9 = 0;
    *a5 = v14;
  }
  else
  {
    v9 = -2146893810;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
        (unsigned int)"Status",
        14,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
        184);
  }
LABEL_11:
  if ( v19 )
    CNG_FreeProtectionDescriptor();
  return v9;
}

```

## disassembly

```asm
0x18000962c  mov     r11, rsp
0x18000962f  push    rbx
0x180009630  push    rbp
0x180009631  push    rsi
0x180009632  push    rdi
0x180009633  push    r14
0x180009635  push    r15
0x180009637  sub     rsp, 48h
0x18000963b  xor     r15d, r15d
0x18000963e  mov     rax, rdx
0x180009641  test    rdx, rdx
0x180009644  mov     [r11+10h], r15
0x180009648  lea     rdx, [r11+10h]
0x18000964c  mov     ebp, r9d
0x18000964f  mov     r14d, r8d
0x180009652  mov     rsi, rcx
0x180009655  mov     ebx, r15d
0x180009658  jnz     loc_18000977C
0x18000965e  call    CNG_DescriptorStringToDescriptor
0x180009663  mov     edi, eax
0x180009665  test    eax, eax
0x180009667  jnz     loc_1800097B4
0x18000966d  mov     rdi, r15
0x180009670  test    rsi, rsi
0x180009673  jz      short loc_18000968B
0x180009675  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180009679  inc     rdi
0x18000967c  cmp     [rsi+rdi*2], r15w
0x180009681  jnz     short loc_180009679
0x180009683  lea     rdi, ds:2[rdi*2]
0x18000968b  lea     rcx, [rdi+28h]
0x18000968f  call    SafeAllocaAllocateFromHeap
0x180009694  mov     rbx, rax
0x180009697  test    rax, rax
0x18000969a  jnz     short loc_18000970F
0x18000969c  mov     edi, 8009000Eh
0x1800096a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800096a8  lea     rax, WPP_GLOBAL_Control
0x1800096af  cmp     rcx, rax
0x1800096b2  jz      short loc_1800096E6
0x1800096b4  test    byte ptr [rcx+1Ch], 1
0x1800096b8  jz      short loc_1800096E6
0x1800096ba  mov     [rsp+78h+var_48], 0B8h
0x1800096c2  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800096c9  mov     [rsp+78h+var_50], r8
0x1800096ce  mov     [rsp+78h+var_58], 8009000Eh
0x1800096d6  mov     rcx, [rcx+10h]
0x1800096da  lea     r9, aStatus; "Status"
0x1800096e1  call    WPP_SF_sDsd
0x1800096e6  mov     rcx, [rsp+78h+arg_8]
0x1800096ee  test    rcx, rcx
0x1800096f1  jnz     loc_18000981A
0x1800096f7  test    rbx, rbx
0x1800096fa  jnz     loc_18000980D
0x180009700  mov     eax, edi
0x180009702  add     rsp, 48h
0x180009706  pop     r15
0x180009708  pop     r14
0x18000970a  pop     rdi
0x18000970b  pop     rsi
0x18000970c  pop     rbp
0x18000970d  pop     rbx
0x18000970e  retn
0x18000970f  mov     [rax+8], r15
0x180009713  mov     [rax+10h], r15
0x180009717  mov     [rax+18h], r15
0x18000971b  mov     [rax+20h], r15
0x18000971f  mov     dword ptr [rax], 28h ; '('
0x180009725  mov     [rax+4], ebp
0x180009728  test    rdi, rdi
0x18000972b  jz      short loc_180009740
0x18000972d  lea     rcx, [rax+28h]; void *
0x180009731  mov     r8, rdi; Size
0x180009734  mov     rdx, rsi; Src
0x180009737  mov     [rax+10h], rcx
0x18000973b  call    memcpy_0
0x180009740  mov     rcx, [rsp+78h+arg_8]
0x180009748  mov     edx, r14d
0x18000974b  mov     [rbx+8], rcx
0x18000974f  mov     [rsp+78h+arg_8], r15
0x180009757  call    CNG_OpenProtectionDescriptor
0x18000975c  mov     edi, eax
0x18000975e  test    eax, eax
0x180009760  jnz     loc_1800097F2
0x180009766  mov     rax, [rsp+78h+arg_20]
0x18000976e  mov     edi, r15d
0x180009771  mov     [rax], rbx
0x180009774  mov     rbx, r15
0x180009777  jmp     loc_1800096E6
0x18000977c  mov     r8d, 1
0x180009782  mov     rcx, rax
0x180009785  call    CNG_DuplicateDescriptor
0x18000978a  mov     edi, eax
0x18000978c  test    eax, eax
0x18000978e  jz      loc_18000966D
0x180009794  mov     r9d, 0A5h
0x18000979a  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800097a1  lea     rdx, aStatus; "Status"
0x1800097a8  mov     ecx, eax
0x1800097aa  call    DebugTraceError
0x1800097af  jmp     loc_1800096E6
0x1800097b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097bb  lea     rax, WPP_GLOBAL_Control
0x1800097c2  cmp     rcx, rax
0x1800097c5  jz      loc_1800096E6
0x1800097cb  test    byte ptr [rcx+1Ch], 1
0x1800097cf  jz      loc_1800096E6
0x1800097d5  mov     [rsp+78h+var_48], 98h
0x1800097dd  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800097e4  mov     [rsp+78h+var_50], r8
0x1800097e9  mov     [rsp+78h+var_58], edi
0x1800097ed  jmp     loc_1800096D6
0x1800097f2  mov     r9d, 0D5h
0x1800097f8  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800097ff  lea     rdx, aStatus; "Status"
0x180009806  mov     ecx, eax
0x180009808  call    DebugTraceError
0x18000980d  mov     rcx, rbx
0x180009810  call    NCryptCloseProtectionDescriptor
0x180009815  jmp     loc_180009700
0x18000981a  call    CNG_FreeProtectionDescriptor
0x18000981f  jmp     loc_1800096F7
```
