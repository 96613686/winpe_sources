# FileStream::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)

- ea: `0x180038070`
- end: `0x18003810e`
- name: `?Seek@FileStream@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z`
- size: `158`
- prototype: `__int64 __fastcall(FileStream *__hidden this, union _LARGE_INTEGER, unsigned int, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180038070`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800380d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800380d5`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800380c8`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800380c8`

## pseudocode

```c
__int64 __fastcall FileStream::Seek(HANDLE *this, union _LARGE_INTEGER a2, int a3, union _ULARGE_INTEGER *a4)
{
  int v5; // r8d
  signed int v6; // ebx
  DWORD v7; // r9d
  DWORD v8; // esi
  signed int LastError; // eax

  if ( a3 )
  {
    v5 = a3 - 1;
    if ( v5 )
    {
      if ( v5 != 1 )
        return (unsigned int)-2147287039;
      v7 = 2;
    }
    else
    {
      v7 = 1;
    }
  }
  else
  {
    v7 = 0;
  }
  if ( a2.HighPart )
  {
    return (unsigned int)-2147287015;
  }
  else
  {
    v6 = 0;
    v8 = SetFilePointer(this[1], a2.LowPart, 0, v7);
    if ( v8 != -1 )
      goto LABEL_14;
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
    {
LABEL_14:
      if ( a4 )
      {
        a4->HighPart = 0;
        a4->LowPart = v8;
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180038070  mov     [rsp+arg_0], rbx
0x180038075  mov     [rsp+arg_8], rsi
0x18003807a  push    rdi
0x18003807b  sub     rsp, 20h
0x18003807f  mov     rdi, r9
0x180038082  test    r8d, r8d
0x180038085  jz      short loc_1800380AA
0x180038087  sub     r8d, 1
0x18003808b  jz      short loc_1800380A2
0x18003808d  cmp     r8d, 1
0x180038091  jz      short loc_18003809A
0x180038093  mov     ebx, 80030001h
0x180038098  jmp     short loc_1800380FC
0x18003809a  mov     r9d, 2
0x1800380a0  jmp     short loc_1800380AD
0x1800380a2  mov     r9d, 1
0x1800380a8  jmp     short loc_1800380AD
0x1800380aa  xor     r9d, r9d; dwMoveMethod
0x1800380ad  mov     rax, rdx
0x1800380b0  shr     rax, 20h
0x1800380b4  test    eax, eax
0x1800380b6  jz      short loc_1800380BF
0x1800380b8  mov     ebx, 80030019h
0x1800380bd  jmp     short loc_1800380FC
0x1800380bf  mov     rcx, [rcx+8]; hFile
0x1800380c3  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800380c6  xor     ebx, ebx
0x1800380c8  call    cs:__imp_SetFilePointer
0x1800380ce  mov     esi, eax
0x1800380d0  cmp     eax, 0FFFFFFFFh
0x1800380d3  jnz     short loc_1800380EE
0x1800380d5  call    cs:__imp_GetLastError
0x1800380db  mov     ebx, eax
0x1800380dd  test    eax, eax
0x1800380df  jle     short loc_1800380EA
0x1800380e1  movzx   ebx, ax
0x1800380e4  or      ebx, 80070000h
0x1800380ea  test    ebx, ebx
0x1800380ec  js      short loc_1800380FC
0x1800380ee  test    rdi, rdi
0x1800380f1  jz      short loc_1800380FC
0x1800380f3  mov     dword ptr [rdi+4], 0
0x1800380fa  mov     [rdi], esi
0x1800380fc  mov     rsi, [rsp+28h+arg_8]
0x180038101  mov     eax, ebx
0x180038103  mov     rbx, [rsp+28h+arg_0]
0x180038108  add     rsp, 20h
0x18003810c  pop     rdi
0x18003810d  retn
```
