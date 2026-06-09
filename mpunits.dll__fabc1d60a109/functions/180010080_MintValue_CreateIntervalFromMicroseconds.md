# MintValue_CreateIntervalFromMicroseconds

- ea: `0x180010080`
- end: `0x180010189`
- name: `MintValue_CreateIntervalFromMicroseconds`
- size: `265`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010190`
- `0x180013f10`
- `0x180016d50`
- `0x1800177a4`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x180010080`
- `0x18001046c`
- `0x180012440`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800100a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800100a9`

## string_xrefs

- `0x18001009d`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall MintValue_CreateIntervalFromMicroseconds(__int64 a1, __int64 a2)
{
  HMODULE ModuleHandleA; // rax
  __int64 v5; // rax
  char v6; // bp
  int v7; // r14d
  __int16 v8; // r15
  char v9; // r12
  __int64 v10; // rbx
  __int128 v12; // [rsp+30h] [rbp-48h] BYREF

  if ( a2 >= 0 )
  {
    v5 = MintValue_CreateUninitializedHeaderObject(&v12, 12, 56, MintValue_ObjectDestructor_FreeOnly);
    v6 = *(_BYTE *)v5;
    v7 = *(_DWORD *)(v5 + 1);
    v8 = *(_WORD *)(v5 + 5);
    v9 = *(_BYTE *)(v5 + 7);
    if ( *(_BYTE *)v5 != 0xFE )
    {
      v10 = *(_QWORD *)(v5 + 8);
      *(_DWORD *)(v10 + 16) = 0;
      Interval_FromMicroseconds(a2, v10 + 20);
      *(_DWORD *)(a1 + 1) = v7;
      *(_WORD *)(a1 + 5) = v8;
      *(_BYTE *)(a1 + 7) = v9;
      *(_BYTE *)a1 = v6;
      *(_QWORD *)(a1 + 8) = v10;
      return a1;
    }
  }
  else
  {
    v12 = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    *(_QWORD *)&v12 = Intlstr_GetString_LoadString(ModuleHandleA, 2080);
    BYTE8(v12) = 0;
    MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
  }
  *(_DWORD *)(a1 + 4) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)a1 = 254;
  return a1;
}

```

## disassembly

```asm
0x180010080  push    rbx
0x180010082  push    rbp
0x180010083  push    rsi
0x180010084  push    rdi
0x180010085  push    r12
0x180010087  push    r14
0x180010089  push    r15
0x18001008b  sub     rsp, 40h
0x18001008f  mov     rsi, rdx
0x180010092  mov     rdi, rcx
0x180010095  test    rdx, rdx
0x180010098  jns     short loc_180010100
0x18001009a  xorps   xmm0, xmm0
0x18001009d  lea     rcx, ModuleName; "mpunits.dll"
0x1800100a4  movups  [rsp+78h+var_48], xmm0
0x1800100a9  call    cs:__imp_GetModuleHandleA
0x1800100af  mov     rcx, rax
0x1800100b2  mov     edx, 820h
0x1800100b7  call    _Intlstr_GetString_LoadString
0x1800100bc  mov     qword ptr [rsp+78h+var_48], rax
0x1800100c1  lea     r9, [rsp+78h+var_48]
0x1800100c6  mov     byte ptr [rsp+78h+var_48+8], 0
0x1800100cb  lea     rdx, aMi; "MI"
0x1800100d2  movaps  xmm0, [rsp+78h+var_48]
0x1800100d7  mov     r8d, 5
0x1800100dd  mov     [rsp+78h+var_50], 0; __int64
0x1800100e6  movdqa  [rsp+78h+var_48], xmm0
0x1800100ec  mov     [rsp+78h+var_58], 0; __int64
0x1800100f5  lea     ecx, [r8-1]; int
0x1800100f9  call    MI_ReportErrorDetails_ForCustomError
0x1800100fe  jmp     short loc_180010130
0x180010100  mov     edx, 0Ch
0x180010105  lea     r9, MintValue_ObjectDestructor_FreeOnly
0x18001010c  lea     rcx, [rsp+78h+var_48]
0x180010111  lea     r8d, [rdx+2Ch]
0x180010115  call    MintValue_CreateUninitializedHeaderObject
0x18001011a  mov     bpl, [rax]
0x18001011d  mov     r14d, [rax+1]
0x180010121  movzx   r15d, word ptr [rax+5]
0x180010126  mov     r12b, [rax+7]
0x18001012a  cmp     bpl, 0FEh
0x18001012e  jnz     short loc_18001014C
0x180010130  xor     edx, edx
0x180010132  xor     ecx, ecx
0x180010134  mov     eax, 0FFh
0x180010139  mov     [rdi+4], edx
0x18001013c  and     eax, 0FFFFFFFEh
0x18001013f  mov     [rdi+8], rcx
0x180010143  or      eax, 0FEh
0x180010148  mov     [rdi], eax
0x18001014a  jmp     short loc_180010177
0x18001014c  mov     rbx, [rax+8]
0x180010150  mov     rcx, rsi
0x180010153  lea     rdx, [rbx+14h]
0x180010157  mov     dword ptr [rbx+10h], 0
0x18001015e  call    Interval_FromMicroseconds
0x180010163  mov     [rdi+1], r14d
0x180010167  mov     [rdi+5], r15w
0x18001016c  mov     [rdi+7], r12b
0x180010170  mov     [rdi], bpl
0x180010173  mov     [rdi+8], rbx
0x180010177  mov     rax, rdi
0x18001017a  add     rsp, 40h
0x18001017e  pop     r15
0x180010180  pop     r14
0x180010182  pop     r12
0x180010184  pop     rdi
0x180010185  pop     rsi
0x180010186  pop     rbp
0x180010187  pop     rbx
0x180010188  retn
```
