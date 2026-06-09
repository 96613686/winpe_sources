# ScExtractDeviceStrings(_STORAGE_DEVICE_DESCRIPTOR *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x140009ba8`
- end: `0x140009c2d`
- name: `?ScExtractDeviceStrings@@YAJPEAU_STORAGE_DEVICE_DESCRIPTOR@@PEAU_UNICODE_STRING@@111@Z`
- size: `133`
- prototype: `__int64 __fastcall(struct _STORAGE_DEVICE_DESCRIPTOR *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140010920`
- `0x1400261fc`

## callees

- `0x140004878`
- `0x140009ba8`

## pseudocode

```c
__int64 __fastcall ScExtractDeviceStrings(
        struct _STORAGE_DEVICE_DESCRIPTOR *a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        struct _UNICODE_STRING *a5)
{
  unsigned int v5; // edi
  ULONG Size; // ebp
  unsigned int v8; // ebp
  __int64 v9; // rbx
  struct _UNICODE_STRING *v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  _DWORD v14[4]; // [rsp+20h] [rbp-58h]
  struct _UNICODE_STRING *v15[9]; // [rsp+30h] [rbp-48h]

  v5 = 0;
  Size = a1->Size;
  v14[0] = a1->VendorIdOffset;
  v8 = Size - 1;
  v9 = 0;
  v14[1] = a1->ProductIdOffset;
  v14[2] = a1->ProductRevisionOffset;
  v14[3] = a1->SerialNumberOffset;
  v15[3] = a5;
  v15[0] = a2;
  v15[1] = a3;
  v15[2] = a4;
  do
  {
    v10 = v15[v9];
    if ( v10 )
    {
      v11 = (unsigned int)v14[v9];
      if ( (unsigned int)v11 >= 0x24 && (unsigned int)v11 <= v8 )
      {
        v12 = ScAnsiToUnicodeString((PCSZ)a1 + v11, v10);
        if ( v12 < 0 )
          v5 = v12;
      }
    }
    ++v9;
  }
  while ( v9 != 4 );
  return v5;
}

```

## disassembly

```asm
0x140009ba8  mov     r11, rsp
0x140009bab  push    rbx
0x140009bac  push    rbp
0x140009bad  push    rsi
0x140009bae  push    rdi
0x140009baf  sub     rsp, 58h
0x140009bb3  mov     eax, [rcx+0Ch]
0x140009bb6  xor     edi, edi
0x140009bb8  mov     ebp, [rcx+4]
0x140009bbb  mov     rsi, rcx
0x140009bbe  mov     [rsp+78h+var_58], eax
0x140009bc2  dec     ebp
0x140009bc4  mov     eax, [rcx+10h]
0x140009bc7  xor     ebx, ebx
0x140009bc9  mov     [rsp+78h+var_54], eax
0x140009bcd  mov     eax, [rcx+14h]
0x140009bd0  mov     [rsp+78h+var_50], eax
0x140009bd4  mov     eax, [rcx+18h]
0x140009bd7  mov     [rsp+78h+var_4C], eax
0x140009bdb  mov     rax, [rsp+78h+arg_20]
0x140009be3  mov     [r11-30h], rax
0x140009be7  mov     [r11-48h], rdx
0x140009beb  mov     [r11-40h], r8
0x140009bef  mov     [r11-38h], r9
0x140009bf3  mov     rdx, [rsp+rbx*8+78h+var_48]; struct _UNICODE_STRING *
0x140009bf8  test    rdx, rdx
0x140009bfb  jz      short loc_140009C18
0x140009bfd  mov     eax, [rsp+rbx*4+78h+var_58]
0x140009c01  cmp     eax, 24h ; '$'
0x140009c04  jb      short loc_140009C18
0x140009c06  cmp     eax, ebp
0x140009c08  ja      short loc_140009C18
0x140009c0a  lea     rcx, [rsi+rax]; SourceString
0x140009c0e  call    ?ScAnsiToUnicodeString@@YAJPEADPEAU_UNICODE_STRING@@@Z; ScAnsiToUnicodeString(char *,_UNICODE_STRING *)
0x140009c13  test    eax, eax
0x140009c15  cmovs   edi, eax
0x140009c18  inc     rbx
0x140009c1b  cmp     rbx, 4
0x140009c1f  jnz     short loc_140009BF3
0x140009c21  mov     eax, edi
0x140009c23  add     rsp, 58h
0x140009c27  pop     rdi
0x140009c28  pop     rsi
0x140009c29  pop     rbp
0x140009c2a  pop     rbx
0x140009c2b  retn
```
