# subtract_timestamp_timestamp

- ea: `0x1800177a4`
- end: `0x1800178e5`
- name: `subtract_timestamp_timestamp`
- size: `321`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017418`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x180010080`
- `0x180012820`
- `0x1800177a4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800177f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001786b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800177f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001786b`

## string_xrefs

- `0x1800177ea`: `mpunits.dll`
- `0x180017860`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall subtract_timestamp_timestamp(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rsi
  __int64 v6; // rax
  HMODULE ModuleHandleA; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // xmm0_8
  int v11; // eax
  __int128 v13; // [rsp+30h] [rbp-18h] BYREF

  v5 = Timestamp_ToMicroseconds(*(_QWORD *)(a2 + 8) + 20LL);
  v6 = Timestamp_ToMicroseconds(*(_QWORD *)(a3 + 8) + 20LL);
  if ( v5 == 0x46120BA57B2FFFFLL )
  {
    if ( v6 == 0x46120BA57B2FFFFLL )
    {
      v13 = 0;
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      v8 = 2052;
LABEL_4:
      *(_QWORD *)&v13 = Intlstr_GetString_LoadString(ModuleHandleA, v8);
      BYTE8(v13) = 0;
      MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
      goto LABEL_11;
    }
    v6 = 0x8C79AE812C62423FuLL;
  }
  else if ( v6 == 0xFFFFFFF5F123923FuLL )
  {
    if ( v5 == 0xFFFFFFF5F123923FuLL )
    {
      v13 = 0;
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      v8 = 2053;
      goto LABEL_4;
    }
    v6 = v5 - 8639999999999000000LL;
  }
  v9 = MintValue_CreateIntervalFromMicroseconds(&v13, v5 - v6);
  if ( *(_BYTE *)v9 != 0xFE )
  {
    v10 = *(_QWORD *)(v9 + 1);
    *(_BYTE *)a1 = *(_BYTE *)v9;
    v11 = *(_DWORD *)(v9 + 9);
    *(_QWORD *)(a1 + 1) = v10;
    *(_DWORD *)(a1 + 9) = v11;
    *(_WORD *)(a1 + 13) = *(_WORD *)(v9 + 13);
    *(_BYTE *)(a1 + 15) = *(_BYTE *)(v9 + 15);
    return a1;
  }
LABEL_11:
  *(_DWORD *)(a1 + 4) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)a1 = 254;
  return a1;
}

```

## disassembly

```asm
0x1800177a4  push    rbp
0x1800177a6  push    rbx
0x1800177a7  push    rsi
0x1800177a8  push    rdi
0x1800177a9  mov     rbp, rsp
0x1800177ac  sub     rsp, 48h
0x1800177b0  mov     rdi, rcx
0x1800177b3  mov     rbx, r8
0x1800177b6  mov     rcx, [rdx+8]
0x1800177ba  add     rcx, 14h
0x1800177be  call    Timestamp_ToMicroseconds
0x1800177c3  mov     rcx, [rbx+8]
0x1800177c7  mov     rsi, rax
0x1800177ca  add     rcx, 14h
0x1800177ce  call    Timestamp_ToMicroseconds
0x1800177d3  mov     rcx, 46120BA57B2FFFFh
0x1800177dd  cmp     rsi, rcx
0x1800177e0  jnz     short loc_180017849
0x1800177e2  cmp     rax, rcx
0x1800177e5  jnz     short loc_18001783D
0x1800177e7  xorps   xmm0, xmm0
0x1800177ea  lea     rcx, ModuleName; "mpunits.dll"
0x1800177f1  movups  [rbp+var_18], xmm0
0x1800177f5  call    cs:__imp_GetModuleHandleA
0x1800177fb  mov     edx, 804h
0x180017800  mov     rcx, rax
0x180017803  call    _Intlstr_GetString_LoadString
0x180017808  mov     qword ptr [rbp+var_18], rax
0x18001780c  lea     r9, [rbp+var_18]
0x180017810  xor     eax, eax
0x180017812  lea     rdx, aMi; "MI"
0x180017819  mov     byte ptr [rbp+var_18+8], al
0x18001781c  movaps  xmm0, [rbp+var_18]
0x180017820  mov     [rsp+48h+var_20], rax; __int64
0x180017825  lea     r8d, [rax+5]
0x180017829  movdqa  [rbp+var_18], xmm0
0x18001782e  lea     ecx, [rax+4]; int
0x180017831  mov     [rsp+48h+var_28], rax; __int64
0x180017836  call    MI_ReportErrorDetails_ForCustomError
0x18001783b  jmp     short loc_18001789D
0x18001783d  mov     rax, 8C79AE812C62423Fh
0x180017847  jmp     short loc_180017885
0x180017849  mov     rcx, 0FFFFFFF5F123923Fh
0x180017853  cmp     rax, rcx
0x180017856  jnz     short loc_180017885
0x180017858  cmp     rsi, rcx
0x18001785b  jnz     short loc_180017878
0x18001785d  xorps   xmm0, xmm0
0x180017860  lea     rcx, ModuleName; "mpunits.dll"
0x180017867  movups  [rbp+var_18], xmm0
0x18001786b  call    cs:__imp_GetModuleHandleA
0x180017871  mov     edx, 805h
0x180017876  jmp     short loc_180017800
0x180017878  mov     rax, 88188DC6D4AF4240h
0x180017882  add     rax, rsi
0x180017885  sub     rsi, rax
0x180017888  lea     rcx, [rbp+var_18]
0x18001788c  mov     rdx, rsi
0x18001788f  call    MintValue_CreateIntervalFromMicroseconds
0x180017894  mov     rcx, rax
0x180017897  mov     al, [rax]
0x180017899  cmp     al, 0FEh
0x18001789b  jnz     short loc_1800178B9
0x18001789d  xor     edx, edx
0x18001789f  xor     ecx, ecx
0x1800178a1  mov     eax, 0FFh
0x1800178a6  mov     [rdi+4], edx
0x1800178a9  and     eax, 0FFFFFFFEh
0x1800178ac  mov     [rdi+8], rcx
0x1800178b0  or      eax, 0FEh
0x1800178b5  mov     [rdi], eax
0x1800178b7  jmp     short loc_1800178D9
0x1800178b9  movsd   xmm0, qword ptr [rcx+1]
0x1800178be  mov     [rdi], al
0x1800178c0  mov     eax, [rcx+9]
0x1800178c3  movsd   qword ptr [rdi+1], xmm0
0x1800178c8  mov     [rdi+9], eax
0x1800178cb  movzx   eax, word ptr [rcx+0Dh]
0x1800178cf  mov     [rdi+0Dh], ax
0x1800178d3  mov     al, [rcx+0Fh]
0x1800178d6  mov     [rdi+0Fh], al
0x1800178d9  mov     rax, rdi
0x1800178dc  add     rsp, 48h
0x1800178e0  pop     rdi
0x1800178e1  pop     rsi
0x1800178e2  pop     rbx
0x1800178e3  pop     rbp
0x1800178e4  retn
```
