# CiHvciTransferRelocationInformation

- ea: `0x1800d0b80`
- end: `0x1800d0deb`
- name: `CiHvciTransferRelocationInformation`
- size: `619`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000f03c`
- `0x18000f9a0`
- `0x18002bfd0`
- `0x1800d0b80`
- `0x1800d0df4`

## import_xrefs

- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800d0bcb`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800d0bcb`

## pseudocode

```c
NTSTATUS __fastcall CiHvciTransferRelocationInformation(__int64 a1, char *a2, DWORD a3)
{
  __int64 v5; // rsi
  unsigned int v6; // r13d
  NTSTATUS result; // eax
  DWORD SizeOfImage; // edx
  IMAGE_DATA_DIRECTORY v9; // rax
  unsigned int VirtualAddress; // ebx
  unsigned int v11; // ecx
  ULONG v12; // r15d
  char *v13; // r12
  int HotPatchMetadataOffset; // eax
  _DWORD v15[3]; // [rsp+54h] [rbp-64h] BYREF
  IMAGE_DATA_DIRECTORY v16; // [rsp+60h] [rbp-58h]
  PIMAGE_NT_HEADERS v17; // [rsp+68h] [rbp-50h] BYREF
  char *v18; // [rsp+70h] [rbp-48h] BYREF
  __int64 v19[3]; // [rsp+78h] [rbp-40h] BYREF
  ULONG v21; // [rsp+D8h] [rbp+20h] BYREF

  v19[0] = 0;
  v15[0] = 0;
  v17 = 0;
  v18 = 0;
  v21 = 0;
  v5 = 0;
  v6 = 0;
  result = RtlImageNtHeaderEx(0, a2, a3, &v17);
  if ( result >= 0 )
  {
    SizeOfImage = v17->OptionalHeader.SizeOfImage;
    if ( SizeOfImage > a3 )
      return -1073741583;
    if ( (v17->FileHeader.Characteristics & 1) != 0 )
    {
      v16 = 0;
      v9.Size = 0;
    }
    else
    {
      if ( v17->OptionalHeader.Magic == 267 )
      {
        if ( v17->FileHeader.SizeOfOptionalHeader < 0xA8u || HIDWORD(v17->OptionalHeader.SizeOfHeapReserve) <= 5 )
          return -1073741701;
        v9 = v17->OptionalHeader.DataDirectory[3];
      }
      else
      {
        if ( v17->FileHeader.SizeOfOptionalHeader < 0xB8u || v17->OptionalHeader.NumberOfRvaAndSizes <= 5 )
          return -1073741701;
        v9 = v17->OptionalHeader.DataDirectory[5];
      }
      v16 = v9;
    }
    VirtualAddress = v16.VirtualAddress;
    if ( !v16.VirtualAddress || !v9.Size )
    {
      VirtualAddress = 0;
      v16 = 0;
    }
    v11 = VirtualAddress + v16.Size;
    if ( VirtualAddress + v16.Size < VirtualAddress )
    {
      v11 = -1;
      result = -1073741675;
    }
    else
    {
      result = 0;
    }
    if ( result >= 0 )
    {
      if ( v11 <= SizeOfImage )
      {
        result = CipHvciFindImageLoadConfig(a2, a3, &v18, &v21);
        if ( result >= 0 )
        {
          v12 = v21;
          v13 = v18;
          result = CipHvciFindDynamicRelocationTable(a2, a3, (__int64)v19, (__int64)v15);
          if ( result >= 0 )
          {
            HotPatchMetadataOffset = CiHvciFindHotPatchMetadataOffset(a2);
            if ( HotPatchMetadataOffset )
            {
              v5 = (__int64)&a2[HotPatchMetadataOffset];
              v19[1] = v5;
              v6 = *(_DWORD *)(v5 + 4);
              v15[1] = v6;
            }
            result = ((__int64 (__fastcall *)(_QWORD, char *, char *, _QWORD, char *, ULONG, char *, _QWORD))xmmword_1800495C0)(
                       *(_QWORD *)(*(_QWORD *)(a1 + 3056) + 16LL),
                       a2,
                       &a2[VirtualAddress],
                       v16.Size,
                       v13,
                       v12,
                       &a2[v19[0]],
                       v15[0]);
            if ( result >= 0 )
            {
              if ( v5 )
                return (*((__int64 (__fastcall **)(_QWORD, char *, __int64, _QWORD))&xmmword_1800495B0 + 1))(
                         *(_QWORD *)(*(_QWORD *)(a1 + 3056) + 16LL),
                         a2,
                         v5,
                         v6);
            }
          }
        }
      }
      else
      {
        return -1073741701;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800d0b80  mov     rax, rsp
0x1800d0b83  mov     [rax+10h], rbx
0x1800d0b87  mov     [rax+18h], rsi
0x1800d0b8b  mov     [rax+8], rcx
0x1800d0b8f  push    rdi
0x1800d0b90  push    r12
0x1800d0b92  push    r13
0x1800d0b94  push    r14
0x1800d0b96  push    r15
0x1800d0b98  sub     rsp, 90h
0x1800d0b9f  mov     r14d, r8d
0x1800d0ba2  mov     rdi, rdx
0x1800d0ba5  xor     r15d, r15d
0x1800d0ba8  mov     [rax-40h], r15
0x1800d0bac  mov     [rax-64h], r15d
0x1800d0bb0  mov     [rax-50h], r15
0x1800d0bb4  mov     [rax-48h], r15
0x1800d0bb8  mov     [rax+20h], r15d
0x1800d0bbc  mov     esi, r15d
0x1800d0bbf  mov     r13d, r15d
0x1800d0bc2  mov     r8d, r14d; Size
0x1800d0bc5  lea     r9, [rax-50h]; NtHeader
0x1800d0bc9  xor     ecx, ecx; Flags
0x1800d0bcb  call    cs:__imp_RtlImageNtHeaderEx
0x1800d0bd2  nop     dword ptr [rax+rax+00h]
0x1800d0bd7  mov     [rsp+0B8h+var_68], eax
0x1800d0bdb  test    eax, eax
0x1800d0bdd  js      loc_1800D0DCD
0x1800d0be3  mov     rcx, [rsp+0B8h+var_50]
0x1800d0be8  mov     edx, [rcx+50h]
0x1800d0beb  cmp     edx, r14d
0x1800d0bee  jbe     short loc_1800D0BFE
0x1800d0bf0  mov     eax, 0C00000F1h
0x1800d0bf5  mov     [rsp+0B8h+var_68], eax
0x1800d0bf9  jmp     loc_1800D0DCD
0x1800d0bfe  test    byte ptr [rcx+16h], 1
0x1800d0c02  jz      short loc_1800D0C0E
0x1800d0c04  mov     [rsp+0B8h+var_58], r15
0x1800d0c09  mov     rax, r15
0x1800d0c0c  jmp     short loc_1800D0C69
0x1800d0c0e  mov     eax, 10Bh
0x1800d0c13  cmp     [rcx+18h], ax
0x1800d0c17  jnz     short loc_1800D0C41
0x1800d0c19  mov     eax, 0A8h
0x1800d0c1e  cmp     [rcx+14h], ax
0x1800d0c22  jb      short loc_1800D0C33
0x1800d0c24  cmp     dword ptr [rcx+74h], 5
0x1800d0c28  jbe     short loc_1800D0C33
0x1800d0c2a  mov     rax, [rcx+0A0h]
0x1800d0c31  jmp     short loc_1800D0C64
0x1800d0c33  mov     eax, 0C000007Bh
0x1800d0c38  mov     [rsp+0B8h+var_68], eax
0x1800d0c3c  jmp     loc_1800D0DCD
0x1800d0c41  mov     eax, 0B8h
0x1800d0c46  cmp     [rcx+14h], ax
0x1800d0c4a  jb      loc_1800D0DBE
0x1800d0c50  cmp     dword ptr [rcx+84h], 5
0x1800d0c57  jbe     loc_1800D0DBE
0x1800d0c5d  mov     rax, [rcx+0B0h]
0x1800d0c64  mov     [rsp+0B8h+var_58], rax
0x1800d0c69  mov     ebx, dword ptr [rsp+0B8h+var_58]
0x1800d0c6d  test    ebx, ebx
0x1800d0c6f  jz      short loc_1800D0C79
0x1800d0c71  shr     rax, 20h
0x1800d0c75  test    eax, eax
0x1800d0c77  jnz     short loc_1800D0C85
0x1800d0c79  mov     ebx, r15d
0x1800d0c7c  mov     dword ptr [rsp+0B8h+var_58], ebx
0x1800d0c80  mov     dword ptr [rsp+0B8h+var_58+4], r15d
0x1800d0c85  mov     ecx, dword ptr [rsp+0B8h+var_58+4]
0x1800d0c89  add     ecx, ebx
0x1800d0c8b  cmp     ecx, ebx
0x1800d0c8d  jb      short loc_1800D0C94
0x1800d0c8f  mov     eax, r15d
0x1800d0c92  jmp     short loc_1800D0C9C
0x1800d0c94  or      ecx, 0FFFFFFFFh
0x1800d0c97  mov     eax, 0C0000095h
0x1800d0c9c  mov     [rsp+0B8h+var_68], eax
0x1800d0ca0  test    eax, eax
0x1800d0ca2  js      loc_1800D0DCD
0x1800d0ca8  cmp     ecx, edx
0x1800d0caa  jbe     short loc_1800D0CBA
0x1800d0cac  mov     eax, 0C000007Bh
0x1800d0cb1  mov     [rsp+0B8h+var_68], eax
0x1800d0cb5  jmp     loc_1800D0DCD
0x1800d0cba  lea     r9, [rsp+0B8h+arg_18]
0x1800d0cc2  lea     r8, [rsp+0B8h+var_48]
0x1800d0cc7  mov     edx, r14d; Size
0x1800d0cca  mov     rcx, rdi; BaseAddress
0x1800d0ccd  call    CipHvciFindImageLoadConfig
0x1800d0cd2  mov     [rsp+0B8h+var_68], eax
0x1800d0cd6  test    eax, eax
0x1800d0cd8  js      loc_1800D0DCD
0x1800d0cde  lea     rax, [rsp+0B8h+var_64]
0x1800d0ce3  mov     [rsp+0B8h+var_90], rax; __int64
0x1800d0ce8  lea     rax, [rsp+0B8h+var_40]
0x1800d0ced  mov     [rsp+0B8h+var_98], rax; __int64
0x1800d0cf2  mov     r15d, [rsp+0B8h+arg_18]
0x1800d0cfa  mov     r9d, r15d
0x1800d0cfd  mov     r12, [rsp+0B8h+var_48]
0x1800d0d02  mov     r8, r12
0x1800d0d05  mov     edx, r14d; Size
0x1800d0d08  mov     rcx, rdi; BaseAddress
0x1800d0d0b  call    CipHvciFindDynamicRelocationTable
0x1800d0d10  mov     [rsp+0B8h+var_68], eax
0x1800d0d14  test    eax, eax
0x1800d0d16  js      loc_1800D0DCD
0x1800d0d1c  mov     r8d, r15d
0x1800d0d1f  mov     rdx, r12
0x1800d0d22  mov     rcx, rdi; BaseAddress
0x1800d0d25  call    CiHvciFindHotPatchMetadataOffset
0x1800d0d2a  test    eax, eax
0x1800d0d2c  jz      short loc_1800D0D45
0x1800d0d2e  mov     esi, eax
0x1800d0d30  lea     rsi, [rsi+rdi]
0x1800d0d34  mov     [rsp+0B8h+var_38], rsi
0x1800d0d3c  mov     r13d, [rsi+4]
0x1800d0d40  mov     [rsp+0B8h+var_64+4], r13d
0x1800d0d45  mov     r10d, [rsp+0B8h+var_64]
0x1800d0d4a  mov     rdx, [rsp+0B8h+var_40]
0x1800d0d4f  add     rdx, rdi
0x1800d0d52  mov     r9d, dword ptr [rsp+0B8h+var_58+4]
0x1800d0d57  mov     r8d, ebx
0x1800d0d5a  add     r8, rdi
0x1800d0d5d  mov     rbx, [rsp+0B8h+arg_0]
0x1800d0d65  mov     rcx, [rbx+0BF0h]
0x1800d0d6c  mov     rax, qword ptr cs:xmmword_1800495C0
0x1800d0d73  mov     [rsp+0B8h+var_80], r10
0x1800d0d78  mov     [rsp+0B8h+var_88], rdx
0x1800d0d7d  mov     dword ptr [rsp+0B8h+var_90], r15d
0x1800d0d82  mov     [rsp+0B8h+var_98], r12
0x1800d0d87  mov     rdx, rdi
0x1800d0d8a  mov     rcx, [rcx+10h]
0x1800d0d8e  call    _guard_dispatch_icall
0x1800d0d93  test    eax, eax
0x1800d0d95  js      short loc_1800D0DCD
0x1800d0d97  test    rsi, rsi
0x1800d0d9a  jz      short loc_1800D0DCD
0x1800d0d9c  mov     r9d, r13d
0x1800d0d9f  mov     rcx, [rbx+0BF0h]
0x1800d0da6  mov     rax, qword ptr cs:xmmword_1800495B0+8
0x1800d0dad  mov     r8, rsi
0x1800d0db0  mov     rdx, rdi
0x1800d0db3  mov     rcx, [rcx+10h]
0x1800d0db7  call    _guard_dispatch_icall
0x1800d0dbc  jmp     short loc_1800D0DCD
0x1800d0dbe  mov     eax, 0C000007Bh
0x1800d0dc3  mov     [rsp+0B8h+var_68], eax
0x1800d0dc7  jmp     short loc_1800D0DCD
0x1800d0dc9  mov     [rsp+0B8h+var_68], eax
0x1800d0dcd  lea     r11, [rsp+0B8h+var_28]
0x1800d0dd5  mov     rbx, [r11+38h]
0x1800d0dd9  mov     rsi, [r11+40h]
0x1800d0ddd  mov     rsp, r11
0x1800d0de0  pop     r15
0x1800d0de2  pop     r14
0x1800d0de4  pop     r13
0x1800d0de6  pop     r12
0x1800d0de8  pop     rdi
0x1800d0de9  retn
```
