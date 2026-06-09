# RtlpGetAssemblyStorageMapRootLocation

- ea: `0x1800cff18`
- end: `0x1800d0109`
- name: `RtlpGetAssemblyStorageMapRootLocation`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800cf510`

## callees

- `0x18001a080`
- `0x180021fe0`
- `0x1800cff18`
- `0x18015e4b0`
- `0x18015e510`
- `0x18015e5b0`
- `0x180162000`
- `0x180163a80`
- `0x18016f030`

## string_xrefs

- `0x1800cffdf`: `SXS: Unable to open storage root subkey %wZ; Status = 0x%08lx\n`

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
    v6 = NtQueryValueKey(Handle, &qword_180171AE0, 2, v19, 536, &v14);
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
0x1800cff18  mov     [rsp-8+arg_18], rbx
0x1800cff1d  push    rbp
0x1800cff1e  push    rsi
0x1800cff1f  push    rdi
0x1800cff20  lea     rbp, [rsp-1B0h]
0x1800cff28  sub     rsp, 2B0h
0x1800cff2f  mov     rax, cs:__security_cookie
0x1800cff36  xor     rax, rsp
0x1800cff39  mov     [rbp+1C0h+var_20], rax
0x1800cff40  xorps   xmm0, xmm0
0x1800cff43  mov     [rsp+2C0h+var_290], rdx
0x1800cff48  mov     rdi, r8
0x1800cff4b  mov     [rsp+2C0h+Handle], 0
0x1800cff54  mov     rbx, rdx
0x1800cff57  mov     [rsp+2C0h+var_288], 0
0x1800cff5f  mov     rsi, rcx
0x1800cff62  xor     edx, edx; Val
0x1800cff64  mov     r8d, 218h; Size
0x1800cff6a  lea     rcx, [rbp+1C0h+var_240]; void *
0x1800cff6e  movups  [rsp+2C0h+var_278], xmm0
0x1800cff73  movups  [rsp+2C0h+var_268], xmm0
0x1800cff78  movups  [rsp+2C0h+var_258], xmm0
0x1800cff7d  call    memset$thunk$772440563353939046
0x1800cff82  test    rsi, rsi
0x1800cff85  jz      loc_1800D00D0
0x1800cff8b  test    rbx, rbx
0x1800cff8e  jz      loc_1800D00D0
0x1800cff94  test    rdi, rdi
0x1800cff97  jz      loc_1800D00D0
0x1800cff9d  lea     rax, [rsp+2C0h+var_290]
0x1800cffa2  mov     dword ptr [rsp+2C0h+var_278], 30h ; '0'
0x1800cffaa  xorps   xmm0, xmm0
0x1800cffad  mov     qword ptr [rsp+2C0h+var_268], rax
0x1800cffb2  lea     r8, [rsp+2C0h+var_278]
0x1800cffb7  mov     qword ptr [rsp+2C0h+var_278+8], rsi
0x1800cffbc  mov     edx, 1
0x1800cffc1  mov     dword ptr [rsp+2C0h+var_268+8], 40h ; '@'
0x1800cffc9  lea     rcx, [rsp+2C0h+Handle]
0x1800cffce  movdqu  [rsp+2C0h+var_258], xmm0
0x1800cffd4  call    NtOpenKey
0x1800cffd9  mov     ebx, eax
0x1800cffdb  test    eax, eax
0x1800cffdd  jns     short loc_1800CFFFE
0x1800cffdf  lea     r8, aSxsUnableToOpe; "SXS: Unable to open storage root subkey"...
0x1800cffe6  xor     edx, edx
0x1800cffe8  mov     dword ptr [rsp+2C0h+var_2A0], eax
0x1800cffec  lea     r9, [rsp+2C0h+var_290]
0x1800cfff1  lea     ecx, [rdx+33h]
0x1800cfff4  call    DbgPrintEx
0x1800cfff9  jmp     loc_1800D00D5
0x1800cfffe  mov     rcx, [rsp+2C0h+Handle]
0x1800d0003  lea     rax, [rsp+2C0h+var_288]
0x1800d0008  mov     [rsp+2C0h+var_298], rax
0x1800d000d  lea     r9, [rbp+1C0h+var_240]
0x1800d0011  mov     r8d, 2
0x1800d0017  mov     dword ptr [rsp+2C0h+var_2A0], 218h
0x1800d001f  lea     rdx, qword_180171AE0
0x1800d0026  call    NtQueryValueKey
0x1800d002b  mov     ebx, eax
0x1800d002d  test    eax, eax
0x1800d002f  jns     short loc_1800D003A
0x1800d0031  lea     r8, aSxsUnabelToQue; "SXS: Unabel to query location from stor"...
0x1800d0038  jmp     short loc_1800CFFE6
0x1800d003a  cmp     [rbp+1C0h+var_23C], 1
0x1800d003e  jz      short loc_1800D0058
0x1800d0040  lea     r8, aSxsAssemblySto_2; "SXS: Assembly storage root location val"...
0x1800d0047  xor     edx, edx
0x1800d0049  lea     ecx, [rdx+33h]
0x1800d004c  call    DbgPrintEx
0x1800d0051  mov     ebx, 0C000003Ah
0x1800d0056  jmp     short loc_1800D00D5
0x1800d0058  mov     ecx, dword ptr [rbp+1C0h+Size]
0x1800d005b  test    cl, 1
0x1800d005e  jz      short loc_1800D0069
0x1800d0060  lea     r8, aSxsAssemblySto_1; "SXS: Assembly storage root location val"...
0x1800d0067  jmp     short loc_1800D0047
0x1800d0069  movzx   eax, word ptr [rdi+2]
0x1800d006d  cmp     ecx, eax
0x1800d006f  jbe     short loc_1800D00B5
0x1800d0071  cmp     ecx, 0FFFEh
0x1800d0077  jbe     short loc_1800D0096
0x1800d0079  xor     edx, edx
0x1800d007b  lea     r9, [rsp+2C0h+var_290]
0x1800d0080  lea     r8, aSxsAssemblySto_0; "SXS: Assembly storage root location for"...
0x1800d0087  lea     ecx, [rdx+33h]
0x1800d008a  call    DbgPrintEx
0x1800d008f  mov     ebx, 0C0000106h
0x1800d0094  jmp     short loc_1800D00D5
0x1800d0096  movzx   ecx, cx
0x1800d0099  mov     [rdi+2], cx
0x1800d009d  call    RtlpAllocateAtom
0x1800d00a2  mov     [rdi+8], rax
0x1800d00a6  test    rax, rax
0x1800d00a9  jnz     short loc_1800D00B2
0x1800d00ab  mov     ebx, 0C0000017h
0x1800d00b0  jmp     short loc_1800D00D5
0x1800d00b2  mov     ecx, dword ptr [rbp+1C0h+Size]
0x1800d00b5  mov     r8d, ecx; Size
0x1800d00b8  lea     rdx, [rbp+1C0h+Size+4]; Src
0x1800d00bc  mov     rcx, [rdi+8]; void *
0x1800d00c0  call    memmove
0x1800d00c5  movzx   eax, word ptr [rbp+1C0h+Size]
0x1800d00c9  xor     ebx, ebx
0x1800d00cb  mov     [rdi], ax
0x1800d00ce  jmp     short loc_1800D00D5
0x1800d00d0  mov     ebx, 0C000000Dh
0x1800d00d5  mov     rcx, [rsp+2C0h+Handle]; Handle
0x1800d00da  test    rcx, rcx
0x1800d00dd  jz      short loc_1800D00E4
0x1800d00df  call    NtClose
0x1800d00e4  mov     eax, ebx
0x1800d00e6  mov     rcx, [rbp+1C0h+var_20]
0x1800d00ed  xor     rcx, rsp; StackCookie
0x1800d00f0  call    __security_check_cookie
0x1800d00f5  mov     rbx, [rsp+2C0h+arg_18]
0x1800d00fd  add     rsp, 2B0h
0x1800d0104  pop     rdi
0x1800d0105  pop     rsi
0x1800d0106  pop     rbp
0x1800d0107  retn
```
