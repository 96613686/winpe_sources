# CiHvciTransferRelocationInformation

- ea: `0x1800d2040`
- end: `0x1800d22ab`
- name: `CiHvciTransferRelocationInformation`
- size: `619`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000f03c`
- `0x18000f9a0`
- `0x18002c000`
- `0x1800d2040`
- `0x1800d22b4`

## import_xrefs

- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800d208b`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800d208b`

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
            result = ((__int64 (__fastcall *)(_QWORD, char *, char *, _QWORD, char *, ULONG, char *, _QWORD))xmmword_18004A620)(
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
                return (*((__int64 (__fastcall **)(_QWORD, char *, __int64, _QWORD))&xmmword_18004A610 + 1))(
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
0x1800d2040  mov     rax, rsp
0x1800d2043  mov     [rax+10h], rbx
0x1800d2047  mov     [rax+18h], rsi
0x1800d204b  mov     [rax+8], rcx
0x1800d204f  push    rdi
0x1800d2050  push    r12
0x1800d2052  push    r13
0x1800d2054  push    r14
0x1800d2056  push    r15
0x1800d2058  sub     rsp, 90h
0x1800d205f  mov     r14d, r8d
0x1800d2062  mov     rdi, rdx
0x1800d2065  xor     r15d, r15d
0x1800d2068  mov     [rax-40h], r15
0x1800d206c  mov     [rax-64h], r15d
0x1800d2070  mov     [rax-50h], r15
0x1800d2074  mov     [rax-48h], r15
0x1800d2078  mov     [rax+20h], r15d
0x1800d207c  mov     esi, r15d
0x1800d207f  mov     r13d, r15d
0x1800d2082  mov     r8d, r14d; Size
0x1800d2085  lea     r9, [rax-50h]; NtHeader
0x1800d2089  xor     ecx, ecx; Flags
0x1800d208b  call    cs:__imp_RtlImageNtHeaderEx
0x1800d2092  nop     dword ptr [rax+rax+00h]
0x1800d2097  mov     [rsp+0B8h+var_68], eax
0x1800d209b  test    eax, eax
0x1800d209d  js      loc_1800D228D
0x1800d20a3  mov     rcx, [rsp+0B8h+var_50]
0x1800d20a8  mov     edx, [rcx+50h]
0x1800d20ab  cmp     edx, r14d
0x1800d20ae  jbe     short loc_1800D20BE
0x1800d20b0  mov     eax, 0C00000F1h
0x1800d20b5  mov     [rsp+0B8h+var_68], eax
0x1800d20b9  jmp     loc_1800D228D
0x1800d20be  test    byte ptr [rcx+16h], 1
0x1800d20c2  jz      short loc_1800D20CE
0x1800d20c4  mov     [rsp+0B8h+var_58], r15
0x1800d20c9  mov     rax, r15
0x1800d20cc  jmp     short loc_1800D2129
0x1800d20ce  mov     eax, 10Bh
0x1800d20d3  cmp     [rcx+18h], ax
0x1800d20d7  jnz     short loc_1800D2101
0x1800d20d9  mov     eax, 0A8h
0x1800d20de  cmp     [rcx+14h], ax
0x1800d20e2  jb      short loc_1800D20F3
0x1800d20e4  cmp     dword ptr [rcx+74h], 5
0x1800d20e8  jbe     short loc_1800D20F3
0x1800d20ea  mov     rax, [rcx+0A0h]
0x1800d20f1  jmp     short loc_1800D2124
0x1800d20f3  mov     eax, 0C000007Bh
0x1800d20f8  mov     [rsp+0B8h+var_68], eax
0x1800d20fc  jmp     loc_1800D228D
0x1800d2101  mov     eax, 0B8h
0x1800d2106  cmp     [rcx+14h], ax
0x1800d210a  jb      loc_1800D227E
0x1800d2110  cmp     dword ptr [rcx+84h], 5
0x1800d2117  jbe     loc_1800D227E
0x1800d211d  mov     rax, [rcx+0B0h]
0x1800d2124  mov     [rsp+0B8h+var_58], rax
0x1800d2129  mov     ebx, dword ptr [rsp+0B8h+var_58]
0x1800d212d  test    ebx, ebx
0x1800d212f  jz      short loc_1800D2139
0x1800d2131  shr     rax, 20h
0x1800d2135  test    eax, eax
0x1800d2137  jnz     short loc_1800D2145
0x1800d2139  mov     ebx, r15d
0x1800d213c  mov     dword ptr [rsp+0B8h+var_58], ebx
0x1800d2140  mov     dword ptr [rsp+0B8h+var_58+4], r15d
0x1800d2145  mov     ecx, dword ptr [rsp+0B8h+var_58+4]
0x1800d2149  add     ecx, ebx
0x1800d214b  cmp     ecx, ebx
0x1800d214d  jb      short loc_1800D2154
0x1800d214f  mov     eax, r15d
0x1800d2152  jmp     short loc_1800D215C
0x1800d2154  or      ecx, 0FFFFFFFFh
0x1800d2157  mov     eax, 0C0000095h
0x1800d215c  mov     [rsp+0B8h+var_68], eax
0x1800d2160  test    eax, eax
0x1800d2162  js      loc_1800D228D
0x1800d2168  cmp     ecx, edx
0x1800d216a  jbe     short loc_1800D217A
0x1800d216c  mov     eax, 0C000007Bh
0x1800d2171  mov     [rsp+0B8h+var_68], eax
0x1800d2175  jmp     loc_1800D228D
0x1800d217a  lea     r9, [rsp+0B8h+arg_18]
0x1800d2182  lea     r8, [rsp+0B8h+var_48]
0x1800d2187  mov     edx, r14d; Size
0x1800d218a  mov     rcx, rdi; BaseAddress
0x1800d218d  call    CipHvciFindImageLoadConfig
0x1800d2192  mov     [rsp+0B8h+var_68], eax
0x1800d2196  test    eax, eax
0x1800d2198  js      loc_1800D228D
0x1800d219e  lea     rax, [rsp+0B8h+var_64]
0x1800d21a3  mov     [rsp+0B8h+var_90], rax; __int64
0x1800d21a8  lea     rax, [rsp+0B8h+var_40]
0x1800d21ad  mov     [rsp+0B8h+var_98], rax; __int64
0x1800d21b2  mov     r15d, [rsp+0B8h+arg_18]
0x1800d21ba  mov     r9d, r15d
0x1800d21bd  mov     r12, [rsp+0B8h+var_48]
0x1800d21c2  mov     r8, r12
0x1800d21c5  mov     edx, r14d; Size
0x1800d21c8  mov     rcx, rdi; BaseAddress
0x1800d21cb  call    CipHvciFindDynamicRelocationTable
0x1800d21d0  mov     [rsp+0B8h+var_68], eax
0x1800d21d4  test    eax, eax
0x1800d21d6  js      loc_1800D228D
0x1800d21dc  mov     r8d, r15d
0x1800d21df  mov     rdx, r12
0x1800d21e2  mov     rcx, rdi; BaseAddress
0x1800d21e5  call    CiHvciFindHotPatchMetadataOffset
0x1800d21ea  test    eax, eax
0x1800d21ec  jz      short loc_1800D2205
0x1800d21ee  mov     esi, eax
0x1800d21f0  lea     rsi, [rsi+rdi]
0x1800d21f4  mov     [rsp+0B8h+var_38], rsi
0x1800d21fc  mov     r13d, [rsi+4]
0x1800d2200  mov     [rsp+0B8h+var_64+4], r13d
0x1800d2205  mov     r10d, [rsp+0B8h+var_64]
0x1800d220a  mov     rdx, [rsp+0B8h+var_40]
0x1800d220f  add     rdx, rdi
0x1800d2212  mov     r9d, dword ptr [rsp+0B8h+var_58+4]
0x1800d2217  mov     r8d, ebx
0x1800d221a  add     r8, rdi
0x1800d221d  mov     rbx, [rsp+0B8h+arg_0]
0x1800d2225  mov     rcx, [rbx+0BF0h]
0x1800d222c  mov     rax, qword ptr cs:xmmword_18004A620
0x1800d2233  mov     [rsp+0B8h+var_80], r10
0x1800d2238  mov     [rsp+0B8h+var_88], rdx
0x1800d223d  mov     dword ptr [rsp+0B8h+var_90], r15d
0x1800d2242  mov     [rsp+0B8h+var_98], r12
0x1800d2247  mov     rdx, rdi
0x1800d224a  mov     rcx, [rcx+10h]
0x1800d224e  call    _guard_dispatch_icall
0x1800d2253  test    eax, eax
0x1800d2255  js      short loc_1800D228D
0x1800d2257  test    rsi, rsi
0x1800d225a  jz      short loc_1800D228D
0x1800d225c  mov     r9d, r13d
0x1800d225f  mov     rcx, [rbx+0BF0h]
0x1800d2266  mov     rax, qword ptr cs:xmmword_18004A610+8
0x1800d226d  mov     r8, rsi
0x1800d2270  mov     rdx, rdi
0x1800d2273  mov     rcx, [rcx+10h]
0x1800d2277  call    _guard_dispatch_icall
0x1800d227c  jmp     short loc_1800D228D
0x1800d227e  mov     eax, 0C000007Bh
0x1800d2283  mov     [rsp+0B8h+var_68], eax
0x1800d2287  jmp     short loc_1800D228D
0x1800d2289  mov     [rsp+0B8h+var_68], eax
0x1800d228d  lea     r11, [rsp+0B8h+var_28]
0x1800d2295  mov     rbx, [r11+38h]
0x1800d2299  mov     rsi, [r11+40h]
0x1800d229d  mov     rsp, r11
0x1800d22a0  pop     r15
0x1800d22a2  pop     r14
0x1800d22a4  pop     r13
0x1800d22a6  pop     r12
0x1800d22a8  pop     rdi
0x1800d22a9  retn
```
