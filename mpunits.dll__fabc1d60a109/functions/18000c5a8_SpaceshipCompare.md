# SpaceshipCompare

- ea: `0x18000c5a8`
- end: `0x18000c7da`
- name: `SpaceshipCompare`
- size: `562`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d154`
- `0x18000d288`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x18000c5a8`
- `0x18000c7e0`
- `0x18000c8b4`
- `0x18000ca8c`
- `0x18000cbc8`
- `0x18000cecc`
- `0x18000cf54`
- `0x18000d05c`
- `0x180010cc0`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000c727`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000c727`

## string_xrefs

- `0x18000c71c`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall SpaceshipCompare(__int128 *a1, __int128 *a2, __int64 a3, char a4)
{
  __int128 v7; // xmm1
  __int128 v9; // xmm1
  __int128 v10; // xmm1
  __int128 v11; // xmm1
  HMODULE ModuleHandleA; // rax
  __int64 v13; // r8
  __int128 v14; // xmm1
  __int128 v15; // [rsp+30h] [rbp-28h] BYREF
  __int128 v16; // [rsp+40h] [rbp-18h] BYREF

  if ( *(_BYTE *)a1 == 0xFF )
  {
    v15 = 0x106u;
LABEL_26:
    v16 = *a2;
    return SpaceshipCompare_NullValues(&v15, &v16);
  }
  if ( *(_BYTE *)a2 == 0xFF )
  {
    v15 = *a1;
    v16 = 0x106u;
    return SpaceshipCompare_NullValues(&v15, &v16);
  }
  if ( (*(_DWORD *)a1 & 0x100) != 0 || (*(_DWORD *)a2 & 0x100) != 0 )
  {
    v15 = *a1;
    goto LABEL_26;
  }
  if ( *(_BYTE *)a1 == 13 )
  {
    v7 = *a1;
    v16 = *a2;
    v15 = v7;
    return SpaceshipCompare_Strings(&v15, &v16);
  }
  if ( (unsigned __int8)(*(_BYTE *)a1 - 1) <= 0xAu )
  {
    LOBYTE(a3) = a4;
    return SpaceshipCompare_LhsNumber(a1, a2, a3);
  }
  if ( !*(_BYTE *)a1 )
  {
    LOBYTE(a3) = a4;
    v9 = *a1;
    v16 = *a2;
    v15 = v9;
    return SpaceshipCompare_Booleans(&v15, &v16, a3);
  }
  if ( *(_BYTE *)a1 != 12 )
    goto LABEL_30;
  if ( *(_DWORD *)(*((_QWORD *)a1 + 1) + 16LL) )
  {
    LOBYTE(a3) = a4;
    v10 = *a1;
    v16 = *a2;
    v15 = v10;
    return SpaceshipCompare_Timestamp(&v15, &v16, a3);
  }
  if ( *(_BYTE *)a1 == 12 )
  {
    if ( !*(_DWORD *)(*((_QWORD *)a1 + 1) + 16LL) )
    {
      LOBYTE(a3) = a4;
      v11 = *a1;
      v16 = *a2;
      v15 = v11;
      return SpaceshipCompare_Interval(&v15, &v16, a3);
    }
  }
  else
  {
LABEL_30:
    if ( *(_BYTE *)a1 == 15
      && ((__int64 (__fastcall *)(_QWORD))Observable_FromInstance)(*(_QWORD *)(*((_QWORD *)a1 + 1) + 24LL)) )
    {
      v15 = 0;
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      *(_QWORD *)&v15 = Intlstr_GetString_LoadString(ModuleHandleA, 2066);
      BYTE8(v15) = 0;
      v16 = v15;
      MI_ReportErrorDetails_ForCustomError(7, (int)L"MI", 0, 0);
      return 4;
    }
  }
  if ( !(unsigned __int8)MintValue_IsGuid(a1) )
    return 3;
  LOBYTE(v13) = a4;
  v14 = *a1;
  v16 = *a2;
  v15 = v14;
  return SpaceshipCompare_Guid(&v15, &v16, v13);
}

```

## disassembly

```asm
0x18000c5a8  push    rbp
0x18000c5aa  push    rsi
0x18000c5ab  push    rdi
0x18000c5ac  push    r14
0x18000c5ae  mov     rbp, rsp
0x18000c5b1  sub     rsp, 58h
0x18000c5b5  cmp     byte ptr [rcx], 0FFh
0x18000c5b8  mov     r14b, r9b
0x18000c5bb  mov     rsi, rdx
0x18000c5be  mov     rdi, rcx
0x18000c5c1  jnz     short loc_18000C5E1
0x18000c5c3  mov     qword ptr [rbp+var_28], 106h
0x18000c5cb  mov     qword ptr [rbp+var_28+8], 0
0x18000c5d3  movaps  xmm1, [rbp+var_28]
0x18000c5d7  movdqa  [rbp+var_28], xmm1
0x18000c5dc  jmp     loc_18000C7BB
0x18000c5e1  cmp     byte ptr [rdx], 0FFh
0x18000c5e4  jnz     short loc_18000C60C
0x18000c5e6  movups  xmm1, xmmword ptr [rcx]
0x18000c5e9  mov     qword ptr [rbp+var_28], 106h
0x18000c5f1  mov     qword ptr [rbp+var_28+8], 0
0x18000c5f9  movaps  xmm0, [rbp+var_28]
0x18000c5fd  movdqu  [rbp+var_28], xmm1
0x18000c602  movdqa  [rbp+var_18], xmm0
0x18000c607  jmp     loc_18000C7C3
0x18000c60c  mov     eax, 100h
0x18000c611  test    [rcx], eax
0x18000c613  jnz     loc_18000C7B3
0x18000c619  test    [rdx], eax
0x18000c61b  jnz     loc_18000C7B3
0x18000c621  cmp     byte ptr [rcx], 0Dh
0x18000c624  jnz     short loc_18000C648
0x18000c626  movups  xmm0, xmmword ptr [rdx]
0x18000c629  lea     rdx, [rbp+var_18]
0x18000c62d  movups  xmm1, xmmword ptr [rcx]
0x18000c630  lea     rcx, [rbp+var_28]
0x18000c634  movdqu  [rbp+var_18], xmm0
0x18000c639  movdqu  [rbp+var_28], xmm1
0x18000c63e  call    SpaceshipCompare_Strings
0x18000c643  jmp     loc_18000C7D0
0x18000c648  mov     al, [rcx]
0x18000c64a  dec     al
0x18000c64c  cmp     al, 0Ah
0x18000c64e  ja      short loc_18000C65D
0x18000c650  mov     r8b, r14b
0x18000c653  call    SpaceshipCompare_LhsNumber
0x18000c658  jmp     loc_18000C7D0
0x18000c65d  cmp     byte ptr [rcx], 0
0x18000c660  jnz     short loc_18000C687
0x18000c662  movups  xmm0, xmmword ptr [rdx]
0x18000c665  mov     r8b, r14b
0x18000c668  lea     rdx, [rbp+var_18]
0x18000c66c  movups  xmm1, xmmword ptr [rcx]
0x18000c66f  lea     rcx, [rbp+var_28]
0x18000c673  movdqu  [rbp+var_18], xmm0
0x18000c678  movdqu  [rbp+var_28], xmm1
0x18000c67d  call    SpaceshipCompare_Booleans
0x18000c682  jmp     loc_18000C7D0
0x18000c687  cmp     byte ptr [rcx], 0Ch
0x18000c68a  jnz     short loc_18000C6F3
0x18000c68c  mov     rax, [rcx+8]
0x18000c690  cmp     dword ptr [rax+10h], 0
0x18000c694  jz      short loc_18000C6BB
0x18000c696  movups  xmm0, xmmword ptr [rdx]
0x18000c699  mov     r8b, r14b
0x18000c69c  lea     rdx, [rbp+var_18]
0x18000c6a0  movups  xmm1, xmmword ptr [rcx]
0x18000c6a3  lea     rcx, [rbp+var_28]
0x18000c6a7  movdqu  [rbp+var_18], xmm0
0x18000c6ac  movdqu  [rbp+var_28], xmm1
0x18000c6b1  call    SpaceshipCompare_Timestamp
0x18000c6b6  jmp     loc_18000C7D0
0x18000c6bb  cmp     byte ptr [rcx], 0Ch
0x18000c6be  jnz     short loc_18000C6F3
0x18000c6c0  mov     rax, [rcx+8]
0x18000c6c4  cmp     dword ptr [rax+10h], 0
0x18000c6c8  jnz     loc_18000C77E
0x18000c6ce  movups  xmm0, xmmword ptr [rdx]
0x18000c6d1  mov     r8b, r14b
0x18000c6d4  lea     rdx, [rbp+var_18]
0x18000c6d8  movups  xmm1, xmmword ptr [rcx]
0x18000c6db  lea     rcx, [rbp+var_28]
0x18000c6df  movdqu  [rbp+var_18], xmm0
0x18000c6e4  movdqu  [rbp+var_28], xmm1
0x18000c6e9  call    SpaceshipCompare_Interval
0x18000c6ee  jmp     loc_18000C7D0
0x18000c6f3  cmp     byte ptr [rcx], 0Fh
0x18000c6f6  jnz     loc_18000C77E
0x18000c6fc  mov     rcx, [rcx+8]
0x18000c700  mov     rax, cs:off_180047B90
0x18000c707  mov     rcx, [rcx+18h]
0x18000c70b  mov     rax, [rax+8]
0x18000c70f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c714  test    rax, rax
0x18000c717  jz      short loc_18000C77E
0x18000c719  xorps   xmm0, xmm0
0x18000c71c  lea     rcx, ModuleName; "mpunits.dll"
0x18000c723  movups  [rbp+var_28], xmm0
0x18000c727  call    cs:__imp_GetModuleHandleA
0x18000c72d  mov     rcx, rax
0x18000c730  mov     edx, 812h
0x18000c735  call    _Intlstr_GetString_LoadString
0x18000c73a  mov     r8d, 0Bh
0x18000c740  mov     qword ptr [rbp+var_28], rax
0x18000c744  mov     byte ptr [rbp+var_28+8], 0
0x18000c748  lea     r9, [rbp+var_18]
0x18000c74c  movaps  xmm0, [rbp+var_28]
0x18000c750  lea     rdx, aMi; "MI"
0x18000c757  mov     [rsp+58h+var_30], 0; __int64
0x18000c760  lea     ecx, [r8-4]; int
0x18000c764  movdqa  [rbp+var_18], xmm0
0x18000c769  mov     [rsp+58h+var_38], 0; __int64
0x18000c772  call    MI_ReportErrorDetails_ForCustomError
0x18000c777  mov     eax, 4
0x18000c77c  jmp     short loc_18000C7D0
0x18000c77e  mov     rcx, rdi
0x18000c781  call    MintValue_IsGuid
0x18000c786  test    al, al
0x18000c788  jz      short loc_18000C7AC
0x18000c78a  movups  xmm0, xmmword ptr [rsi]
0x18000c78d  mov     r8b, r14b
0x18000c790  lea     rdx, [rbp+var_18]
0x18000c794  movups  xmm1, xmmword ptr [rdi]
0x18000c797  lea     rcx, [rbp+var_28]
0x18000c79b  movdqu  [rbp+var_18], xmm0
0x18000c7a0  movdqu  [rbp+var_28], xmm1
0x18000c7a5  call    SpaceshipCompare_Guid
0x18000c7aa  jmp     short loc_18000C7D0
0x18000c7ac  mov     eax, 3
0x18000c7b1  jmp     short loc_18000C7D0
0x18000c7b3  movups  xmm1, xmmword ptr [rcx]
0x18000c7b6  movdqu  [rbp+var_28], xmm1
0x18000c7bb  movups  xmm0, xmmword ptr [rdx]
0x18000c7be  movdqu  [rbp+var_18], xmm0
0x18000c7c3  lea     rdx, [rbp+var_18]
0x18000c7c7  lea     rcx, [rbp+var_28]
0x18000c7cb  call    SpaceshipCompare_NullValues
0x18000c7d0  add     rsp, 58h
0x18000c7d4  pop     r14
0x18000c7d6  pop     rdi
0x18000c7d7  pop     rsi
0x18000c7d8  pop     rbp
0x18000c7d9  retn
```
