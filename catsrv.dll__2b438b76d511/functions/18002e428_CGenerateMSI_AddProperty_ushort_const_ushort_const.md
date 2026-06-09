# CGenerateMSI::_AddProperty(ushort const *,ushort const *)

- ea: `0x18002e428`
- end: `0x18002e529`
- name: `?_AddProperty@CGenerateMSI@@QEAAJPEBG0@Z`
- size: `257`
- prototype: `__int64 __fastcall(CGenerateMSI *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18002cae0`
- `0x18002d600`

## callees

- `0x18002e428`

## import_xrefs

- `msi!__imp_MsiCloseHandle` at `0x18002e483`
- `msi!__imp_MsiCloseHandle` at `0x18002e48f`
- `msi!__imp_MsiCloseHandle` at `0x18002e4e7`
- `msi!__imp_MsiCloseHandle` at `0x18002e50c`
- `msi!__imp_MsiCloseHandle` at `0x18002e483`
- `msi!__imp_MsiCloseHandle` at `0x18002e48f`
- `msi!__imp_MsiCloseHandle` at `0x18002e4e7`
- `msi!__imp_MsiCloseHandle` at `0x18002e50c`
- `msi!__imp_MsiCreateRecord` at `0x18002e447`
- `msi!__imp_MsiCreateRecord` at `0x18002e447`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x18002e4c5`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x18002e4c5`
- `msi!__imp_MsiRecordSetStringW` at `0x18002e464`
- `msi!__imp_MsiRecordSetStringW` at `0x18002e4aa`
- `msi!__imp_MsiRecordSetStringW` at `0x18002e464`
- `msi!__imp_MsiRecordSetStringW` at `0x18002e4aa`
- `msi!__imp_MsiViewExecute` at `0x18002e4d7`
- `msi!__imp_MsiViewExecute` at `0x18002e4d7`

## pseudocode

```c
__int64 __fastcall CGenerateMSI::_AddProperty(
        CGenerateMSI *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  MSIHANDLE Record; // eax
  MSIHANDLE v7; // edi
  unsigned int v8; // ebx
  signed int v9; // eax
  bool v10; // cc
  signed int v12; // eax
  MSIHANDLE hAny; // [rsp+68h] [rbp+20h] BYREF

  hAny = 0;
  Record = MsiCreateRecord(2u);
  v7 = Record;
  if ( !Record )
  {
    v8 = -2147024882;
    goto LABEL_6;
  }
  v9 = MsiRecordSetStringW(Record, 1u, a2);
  v8 = v9;
  v10 = v9 <= 0;
  if ( v9 )
    goto LABEL_4;
  v9 = MsiRecordSetStringW(v7, 2u, a3);
  v8 = v9;
  v10 = v9 <= 0;
  if ( v9
    || (v9 = MsiDatabaseOpenViewW(
               *((_DWORD *)this + 16),
               L"INSERT INTO Property (Property, Value) VALUES (?, ?)",
               &hAny),
        v8 = v9,
        v10 = v9 <= 0,
        v9)
    || (v9 = MsiViewExecute(hAny, v7), v8 = v9, v10 = v9 <= 0, v9) )
  {
LABEL_4:
    if ( v10 )
      goto LABEL_6;
    goto LABEL_5;
  }
  v12 = MsiCloseHandle(hAny);
  hAny = 0;
  v8 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v8 = (unsigned __int16)v12 | 0x80070000;
    goto LABEL_9;
  }
  v8 = 0;
  v9 = MsiCloseHandle(v7);
  v7 = 0;
  if ( v9 )
  {
    if ( v9 <= 0 )
    {
      v8 = v9;
      goto LABEL_6;
    }
LABEL_5:
    v8 = (unsigned __int16)v9 | 0x80070000;
  }
LABEL_6:
  if ( hAny )
    MsiCloseHandle(hAny);
  if ( v7 )
LABEL_9:
    MsiCloseHandle(v7);
  return v8;
}

```

## disassembly

```asm
0x18002e428  push    rbx
0x18002e42a  push    rbp
0x18002e42b  push    rsi
0x18002e42c  push    rdi
0x18002e42d  sub     rsp, 28h
0x18002e431  mov     rsi, rcx
0x18002e434  mov     [rsp+48h+hAny], 0
0x18002e43c  mov     ecx, 2; cParams
0x18002e441  mov     rbp, r8
0x18002e444  mov     rbx, rdx
0x18002e447  call    cs:__imp_MsiCreateRecord
0x18002e44d  mov     edi, eax
0x18002e44f  test    eax, eax
0x18002e451  jnz     short loc_18002E45A
0x18002e453  mov     ebx, 8007000Eh
0x18002e458  jmp     short loc_18002E47B
0x18002e45a  mov     r8, rbx; szValue
0x18002e45d  mov     edx, 1; iField
0x18002e462  mov     ecx, edi; hRecord
0x18002e464  call    cs:__imp_MsiRecordSetStringW
0x18002e46a  mov     ebx, eax
0x18002e46c  test    eax, eax
0x18002e46e  jz      short loc_18002E4A0
0x18002e470  jle     short loc_18002E47B
0x18002e472  movzx   ebx, ax
0x18002e475  or      ebx, 80070000h
0x18002e47b  mov     ecx, [rsp+48h+hAny]; hAny
0x18002e47f  test    ecx, ecx
0x18002e481  jz      short loc_18002E489
0x18002e483  call    cs:__imp_MsiCloseHandle
0x18002e489  test    edi, edi
0x18002e48b  jz      short loc_18002E495
0x18002e48d  mov     ecx, edi; hAny
0x18002e48f  call    cs:__imp_MsiCloseHandle
0x18002e495  mov     eax, ebx
0x18002e497  add     rsp, 28h
0x18002e49b  pop     rdi
0x18002e49c  pop     rsi
0x18002e49d  pop     rbp
0x18002e49e  pop     rbx
0x18002e49f  retn
0x18002e4a0  mov     r8, rbp; szValue
0x18002e4a3  mov     edx, 2; iField
0x18002e4a8  mov     ecx, edi; hRecord
0x18002e4aa  call    cs:__imp_MsiRecordSetStringW
0x18002e4b0  mov     ebx, eax
0x18002e4b2  test    eax, eax
0x18002e4b4  jnz     short loc_18002E470
0x18002e4b6  mov     ecx, [rsi+40h]; hDatabase
0x18002e4b9  lea     r8, [rsp+48h+hAny]; phView
0x18002e4be  lea     rdx, aInsertIntoProp_2; "INSERT INTO Property (Property, Value) "...
0x18002e4c5  call    cs:__imp_MsiDatabaseOpenViewW
0x18002e4cb  mov     ebx, eax
0x18002e4cd  test    eax, eax
0x18002e4cf  jnz     short loc_18002E470
0x18002e4d1  mov     ecx, [rsp+48h+hAny]; hView
0x18002e4d5  mov     edx, edi; hRecord
0x18002e4d7  call    cs:__imp_MsiViewExecute
0x18002e4dd  mov     ebx, eax
0x18002e4df  test    eax, eax
0x18002e4e1  jnz     short loc_18002E470
0x18002e4e3  mov     ecx, [rsp+48h+hAny]; hAny
0x18002e4e7  call    cs:__imp_MsiCloseHandle
0x18002e4ed  mov     [rsp+48h+hAny], 0
0x18002e4f5  mov     ebx, eax
0x18002e4f7  test    eax, eax
0x18002e4f9  jz      short loc_18002E508
0x18002e4fb  jle     short loc_18002E48D
0x18002e4fd  movzx   ebx, ax
0x18002e500  or      ebx, 80070000h
0x18002e506  jmp     short loc_18002E48D
0x18002e508  mov     ecx, edi; hAny
0x18002e50a  xor     ebx, ebx
0x18002e50c  call    cs:__imp_MsiCloseHandle
0x18002e512  xor     edi, edi
0x18002e514  test    eax, eax
0x18002e516  jz      loc_18002E47B
0x18002e51c  jg      loc_18002E472
0x18002e522  mov     ebx, eax
0x18002e524  jmp     loc_18002E47B
```
