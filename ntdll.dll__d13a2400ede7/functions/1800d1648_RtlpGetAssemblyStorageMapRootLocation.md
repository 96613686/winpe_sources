# RtlpGetAssemblyStorageMapRootLocation

- ea: `0x1800d1648`
- end: `0x1800d1839`
- name: `RtlpGetAssemblyStorageMapRootLocation`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800d0c40`

## callees

- `0x18001a080`
- `0x180021fd0`
- `0x1800d1648`
- `0x18015ecc0`
- `0x18015ed20`
- `0x18015edc0`
- `0x180162810`
- `0x180164280`
- `0x18016f030`

## string_xrefs

- `0x1800d170f`: `SXS: Unable to open storage root subkey %wZ; Status = 0x%08lx\n`

## pseudocode

```c
__int64 __fastcall RtlpGetAssemblyStorageMapRootLocation(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  const char *v8; // r8
  unsigned int v9; // ecx
  __int64 Atom; // rax
  __int64 v12; // [rsp+20h] [rbp-E0h]
  __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
  int v14; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v16; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v17; // [rsp+58h] [rbp-A8h]
  __int128 v18; // [rsp+68h] [rbp-98h]
  _BYTE v19[4]; // [rsp+80h] [rbp-80h] BYREF
  int v20; // [rsp+84h] [rbp-7Ch]
  unsigned int Size; // [rsp+88h] [rbp-78h]
  size_t Size_4; // [rsp+8Ch] [rbp-74h] BYREF

  v13 = a2;
  Handle = 0;
  v14 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  memset_thunk_772440563353939046(v19, 0, 0x218u);
  if ( a1 && a2 && a3 )
  {
    LODWORD(v16) = 48;
    *(_QWORD *)&v17 = &v13;
    *((_QWORD *)&v16 + 1) = a1;
    DWORD2(v17) = 64;
    v18 = 0;
    v6 = NtOpenKey(&Handle, 1, &v16);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = "SXS: Unable to open storage root subkey %wZ; Status = 0x%08lx\n";
LABEL_6:
      LODWORD(v12) = v6;
      DbgPrintEx(51, 0, v8, &v13, v12);
      goto LABEL_22;
    }
    v6 = NtQueryValueKey(Handle, &qword_180171AF0, 2, v19, 536, &v14);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = "SXS: Unabel to query location from storage root subkey %wZ; Status = 0x%08lx\n";
      goto LABEL_6;
    }
    if ( v20 != 1 )
    {
      DbgPrintEx(51, 0, "SXS: Assembly storage root location value type is not REG_SZ\n");
LABEL_11:
      v7 = -1073741766;
      goto LABEL_22;
    }
    v9 = Size;
    if ( (Size & 1) != 0 )
    {
      DbgPrintEx(51, 0, "SXS: Assembly storage root location value has non-even size\n");
      goto LABEL_11;
    }
    if ( Size > *(unsigned __int16 *)(a3 + 2) )
    {
      if ( Size > 0xFFFE )
      {
        DbgPrintEx(51, 0, "SXS: Assembly storage root location for %wZ does not fit in a UNICODE STRING\n", &v13);
        v7 = -1073741562;
        goto LABEL_22;
      }
      *(_WORD *)(a3 + 2) = Size;
      Atom = RtlpAllocateAtom((unsigned __int16)v9);
      *(_QWORD *)(a3 + 8) = Atom;
      if ( !Atom )
      {
        v7 = -1073741801;
        goto LABEL_22;
      }
      v9 = Size;
    }
    memmove(*(void **)(a3 + 8), &Size_4, v9);
    v7 = 0;
    *(_WORD *)a3 = Size;
  }
  else
  {
    v7 = -1073741811;
  }
LABEL_22:
  if ( Handle )
    NtClose(Handle);
  return v7;
}

```

## disassembly

```asm
0x1800d1648  mov     [rsp-8+arg_18], rbx
0x1800d164d  push    rbp
0x1800d164e  push    rsi
0x1800d164f  push    rdi
0x1800d1650  lea     rbp, [rsp-1B0h]
0x1800d1658  sub     rsp, 2B0h
0x1800d165f  mov     rax, cs:__security_cookie
0x1800d1666  xor     rax, rsp
0x1800d1669  mov     [rbp+1C0h+var_20], rax
0x1800d1670  xorps   xmm0, xmm0
0x1800d1673  mov     [rsp+2C0h+var_290], rdx
0x1800d1678  mov     rdi, r8
0x1800d167b  mov     [rsp+2C0h+Handle], 0
0x1800d1684  mov     rbx, rdx
0x1800d1687  mov     [rsp+2C0h+var_288], 0
0x1800d168f  mov     rsi, rcx
0x1800d1692  xor     edx, edx; Val
0x1800d1694  mov     r8d, 218h; Size
0x1800d169a  lea     rcx, [rbp+1C0h+var_240]; void *
0x1800d169e  movups  [rsp+2C0h+var_278], xmm0
0x1800d16a3  movups  [rsp+2C0h+var_268], xmm0
0x1800d16a8  movups  [rsp+2C0h+var_258], xmm0
0x1800d16ad  call    memset$thunk$772440563353939046
0x1800d16b2  test    rsi, rsi
0x1800d16b5  jz      loc_1800D1800
0x1800d16bb  test    rbx, rbx
0x1800d16be  jz      loc_1800D1800
0x1800d16c4  test    rdi, rdi
0x1800d16c7  jz      loc_1800D1800
0x1800d16cd  lea     rax, [rsp+2C0h+var_290]
0x1800d16d2  mov     dword ptr [rsp+2C0h+var_278], 30h ; '0'
0x1800d16da  xorps   xmm0, xmm0
0x1800d16dd  mov     qword ptr [rsp+2C0h+var_268], rax
0x1800d16e2  lea     r8, [rsp+2C0h+var_278]
0x1800d16e7  mov     qword ptr [rsp+2C0h+var_278+8], rsi
0x1800d16ec  mov     edx, 1
0x1800d16f1  mov     dword ptr [rsp+2C0h+var_268+8], 40h ; '@'
0x1800d16f9  lea     rcx, [rsp+2C0h+Handle]
0x1800d16fe  movdqu  [rsp+2C0h+var_258], xmm0
0x1800d1704  call    NtOpenKey
0x1800d1709  mov     ebx, eax
0x1800d170b  test    eax, eax
0x1800d170d  jns     short loc_1800D172E
0x1800d170f  lea     r8, aSxsUnableToOpe; "SXS: Unable to open storage root subkey"...
0x1800d1716  xor     edx, edx
0x1800d1718  mov     dword ptr [rsp+2C0h+var_2A0], eax
0x1800d171c  lea     r9, [rsp+2C0h+var_290]
0x1800d1721  lea     ecx, [rdx+33h]
0x1800d1724  call    DbgPrintEx
0x1800d1729  jmp     loc_1800D1805
0x1800d172e  mov     rcx, [rsp+2C0h+Handle]
0x1800d1733  lea     rax, [rsp+2C0h+var_288]
0x1800d1738  mov     [rsp+2C0h+var_298], rax
0x1800d173d  lea     r9, [rbp+1C0h+var_240]
0x1800d1741  mov     r8d, 2
0x1800d1747  mov     dword ptr [rsp+2C0h+var_2A0], 218h
0x1800d174f  lea     rdx, qword_180171AF0
0x1800d1756  call    NtQueryValueKey
0x1800d175b  mov     ebx, eax
0x1800d175d  test    eax, eax
0x1800d175f  jns     short loc_1800D176A
0x1800d1761  lea     r8, aSxsUnabelToQue; "SXS: Unabel to query location from stor"...
0x1800d1768  jmp     short loc_1800D1716
0x1800d176a  cmp     [rbp+1C0h+var_23C], 1
0x1800d176e  jz      short loc_1800D1788
0x1800d1770  lea     r8, aSxsAssemblySto_2; "SXS: Assembly storage root location val"...
0x1800d1777  xor     edx, edx
0x1800d1779  lea     ecx, [rdx+33h]
0x1800d177c  call    DbgPrintEx
0x1800d1781  mov     ebx, 0C000003Ah
0x1800d1786  jmp     short loc_1800D1805
0x1800d1788  mov     ecx, dword ptr [rbp+1C0h+Size]
0x1800d178b  test    cl, 1
0x1800d178e  jz      short loc_1800D1799
0x1800d1790  lea     r8, aSxsAssemblySto_1; "SXS: Assembly storage root location val"...
0x1800d1797  jmp     short loc_1800D1777
0x1800d1799  movzx   eax, word ptr [rdi+2]
0x1800d179d  cmp     ecx, eax
0x1800d179f  jbe     short loc_1800D17E5
0x1800d17a1  cmp     ecx, 0FFFEh
0x1800d17a7  jbe     short loc_1800D17C6
0x1800d17a9  xor     edx, edx
0x1800d17ab  lea     r9, [rsp+2C0h+var_290]
0x1800d17b0  lea     r8, aSxsAssemblySto_0; "SXS: Assembly storage root location for"...
0x1800d17b7  lea     ecx, [rdx+33h]
0x1800d17ba  call    DbgPrintEx
0x1800d17bf  mov     ebx, 0C0000106h
0x1800d17c4  jmp     short loc_1800D1805
0x1800d17c6  movzx   ecx, cx
0x1800d17c9  mov     [rdi+2], cx
0x1800d17cd  call    RtlpAllocateAtom
0x1800d17d2  mov     [rdi+8], rax
0x1800d17d6  test    rax, rax
0x1800d17d9  jnz     short loc_1800D17E2
0x1800d17db  mov     ebx, 0C0000017h
0x1800d17e0  jmp     short loc_1800D1805
0x1800d17e2  mov     ecx, dword ptr [rbp+1C0h+Size]
0x1800d17e5  mov     r8d, ecx; Size
0x1800d17e8  lea     rdx, [rbp+1C0h+Size+4]; Src
0x1800d17ec  mov     rcx, [rdi+8]; void *
0x1800d17f0  call    memmove
0x1800d17f5  movzx   eax, word ptr [rbp+1C0h+Size]
0x1800d17f9  xor     ebx, ebx
0x1800d17fb  mov     [rdi], ax
0x1800d17fe  jmp     short loc_1800D1805
0x1800d1800  mov     ebx, 0C000000Dh
0x1800d1805  mov     rcx, [rsp+2C0h+Handle]; Handle
0x1800d180a  test    rcx, rcx
0x1800d180d  jz      short loc_1800D1814
0x1800d180f  call    NtClose
0x1800d1814  mov     eax, ebx
0x1800d1816  mov     rcx, [rbp+1C0h+var_20]
0x1800d181d  xor     rcx, rsp; StackCookie
0x1800d1820  call    __security_check_cookie
0x1800d1825  mov     rbx, [rsp+2C0h+arg_18]
0x1800d182d  add     rsp, 2B0h
0x1800d1834  pop     rdi
0x1800d1835  pop     rsi
0x1800d1836  pop     rbp
0x1800d1837  retn
```
