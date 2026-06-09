# CiHvciTransferRelocationInformation

- ea: `0x1800d2050`
- end: `0x1800d22bb`
- name: `CiHvciTransferRelocationInformation`
- size: `619`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000f04c`
- `0x18000f9b0`
- `0x18002c1b0`
- `0x1800d2050`
- `0x1800d22c4`

## import_xrefs

- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800d209b`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800d209b`

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
            result = ((__int64 (__fastcall *)(_QWORD, char *, char *, _QWORD, char *, ULONG, char *, _QWORD))xmmword_18004A5C0)(
                       *(_QWORD *)(*(_QWORD *)(a1 + 3072) + 16LL),
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
                return (*((__int64 (__fastcall **)(_QWORD, char *, __int64, _QWORD))&xmmword_18004A5B0 + 1))(
                         *(_QWORD *)(*(_QWORD *)(a1 + 3072) + 16LL),
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
0x1800d2050  mov     rax, rsp
0x1800d2053  mov     [rax+10h], rbx
0x1800d2057  mov     [rax+18h], rsi
0x1800d205b  mov     [rax+8], rcx
0x1800d205f  push    rdi
0x1800d2060  push    r12
0x1800d2062  push    r13
0x1800d2064  push    r14
0x1800d2066  push    r15
0x1800d2068  sub     rsp, 90h
0x1800d206f  mov     r14d, r8d
0x1800d2072  mov     rdi, rdx
0x1800d2075  xor     r15d, r15d
0x1800d2078  mov     [rax-40h], r15
0x1800d207c  mov     [rax-64h], r15d
0x1800d2080  mov     [rax-50h], r15
0x1800d2084  mov     [rax-48h], r15
0x1800d2088  mov     [rax+20h], r15d
0x1800d208c  mov     esi, r15d
0x1800d208f  mov     r13d, r15d
0x1800d2092  mov     r8d, r14d; Size
0x1800d2095  lea     r9, [rax-50h]; NtHeader
0x1800d2099  xor     ecx, ecx; Flags
0x1800d209b  call    cs:__imp_RtlImageNtHeaderEx
0x1800d20a2  nop     dword ptr [rax+rax+00h]
0x1800d20a7  mov     [rsp+0B8h+var_68], eax
0x1800d20ab  test    eax, eax
0x1800d20ad  js      loc_1800D229D
0x1800d20b3  mov     rcx, [rsp+0B8h+var_50]
0x1800d20b8  mov     edx, [rcx+50h]
0x1800d20bb  cmp     edx, r14d
0x1800d20be  jbe     short loc_1800D20CE
0x1800d20c0  mov     eax, 0C00000F1h
0x1800d20c5  mov     [rsp+0B8h+var_68], eax
0x1800d20c9  jmp     loc_1800D229D
0x1800d20ce  test    byte ptr [rcx+16h], 1
0x1800d20d2  jz      short loc_1800D20DE
0x1800d20d4  mov     [rsp+0B8h+var_58], r15
0x1800d20d9  mov     rax, r15
0x1800d20dc  jmp     short loc_1800D2139
0x1800d20de  mov     eax, 10Bh
0x1800d20e3  cmp     [rcx+18h], ax
0x1800d20e7  jnz     short loc_1800D2111
0x1800d20e9  mov     eax, 0A8h
0x1800d20ee  cmp     [rcx+14h], ax
0x1800d20f2  jb      short loc_1800D2103
0x1800d20f4  cmp     dword ptr [rcx+74h], 5
0x1800d20f8  jbe     short loc_1800D2103
0x1800d20fa  mov     rax, [rcx+0A0h]
0x1800d2101  jmp     short loc_1800D2134
0x1800d2103  mov     eax, 0C000007Bh
0x1800d2108  mov     [rsp+0B8h+var_68], eax
0x1800d210c  jmp     loc_1800D229D
0x1800d2111  mov     eax, 0B8h
0x1800d2116  cmp     [rcx+14h], ax
0x1800d211a  jb      loc_1800D228E
0x1800d2120  cmp     dword ptr [rcx+84h], 5
0x1800d2127  jbe     loc_1800D228E
0x1800d212d  mov     rax, [rcx+0B0h]
0x1800d2134  mov     [rsp+0B8h+var_58], rax
0x1800d2139  mov     ebx, dword ptr [rsp+0B8h+var_58]
0x1800d213d  test    ebx, ebx
0x1800d213f  jz      short loc_1800D2149
0x1800d2141  shr     rax, 20h
0x1800d2145  test    eax, eax
0x1800d2147  jnz     short loc_1800D2155
0x1800d2149  mov     ebx, r15d
0x1800d214c  mov     dword ptr [rsp+0B8h+var_58], ebx
0x1800d2150  mov     dword ptr [rsp+0B8h+var_58+4], r15d
0x1800d2155  mov     ecx, dword ptr [rsp+0B8h+var_58+4]
0x1800d2159  add     ecx, ebx
0x1800d215b  cmp     ecx, ebx
0x1800d215d  jb      short loc_1800D2164
0x1800d215f  mov     eax, r15d
0x1800d2162  jmp     short loc_1800D216C
0x1800d2164  or      ecx, 0FFFFFFFFh
0x1800d2167  mov     eax, 0C0000095h
0x1800d216c  mov     [rsp+0B8h+var_68], eax
0x1800d2170  test    eax, eax
0x1800d2172  js      loc_1800D229D
0x1800d2178  cmp     ecx, edx
0x1800d217a  jbe     short loc_1800D218A
0x1800d217c  mov     eax, 0C000007Bh
0x1800d2181  mov     [rsp+0B8h+var_68], eax
0x1800d2185  jmp     loc_1800D229D
0x1800d218a  lea     r9, [rsp+0B8h+arg_18]
0x1800d2192  lea     r8, [rsp+0B8h+var_48]
0x1800d2197  mov     edx, r14d; Size
0x1800d219a  mov     rcx, rdi; BaseAddress
0x1800d219d  call    CipHvciFindImageLoadConfig
0x1800d21a2  mov     [rsp+0B8h+var_68], eax
0x1800d21a6  test    eax, eax
0x1800d21a8  js      loc_1800D229D
0x1800d21ae  lea     rax, [rsp+0B8h+var_64]
0x1800d21b3  mov     [rsp+0B8h+var_90], rax; __int64
0x1800d21b8  lea     rax, [rsp+0B8h+var_40]
0x1800d21bd  mov     [rsp+0B8h+var_98], rax; __int64
0x1800d21c2  mov     r15d, [rsp+0B8h+arg_18]
0x1800d21ca  mov     r9d, r15d
0x1800d21cd  mov     r12, [rsp+0B8h+var_48]
0x1800d21d2  mov     r8, r12
0x1800d21d5  mov     edx, r14d; Size
0x1800d21d8  mov     rcx, rdi; BaseAddress
0x1800d21db  call    CipHvciFindDynamicRelocationTable
0x1800d21e0  mov     [rsp+0B8h+var_68], eax
0x1800d21e4  test    eax, eax
0x1800d21e6  js      loc_1800D229D
0x1800d21ec  mov     r8d, r15d
0x1800d21ef  mov     rdx, r12
0x1800d21f2  mov     rcx, rdi; BaseAddress
0x1800d21f5  call    CiHvciFindHotPatchMetadataOffset
0x1800d21fa  test    eax, eax
0x1800d21fc  jz      short loc_1800D2215
0x1800d21fe  mov     esi, eax
0x1800d2200  lea     rsi, [rsi+rdi]
0x1800d2204  mov     [rsp+0B8h+var_38], rsi
0x1800d220c  mov     r13d, [rsi+4]
0x1800d2210  mov     [rsp+0B8h+var_64+4], r13d
0x1800d2215  mov     r10d, [rsp+0B8h+var_64]
0x1800d221a  mov     rdx, [rsp+0B8h+var_40]
0x1800d221f  add     rdx, rdi
0x1800d2222  mov     r9d, dword ptr [rsp+0B8h+var_58+4]
0x1800d2227  mov     r8d, ebx
0x1800d222a  add     r8, rdi
0x1800d222d  mov     rbx, [rsp+0B8h+arg_0]
0x1800d2235  mov     rcx, [rbx+0C00h]
0x1800d223c  mov     rax, qword ptr cs:xmmword_18004A5C0
0x1800d2243  mov     [rsp+0B8h+var_80], r10
0x1800d2248  mov     [rsp+0B8h+var_88], rdx
0x1800d224d  mov     dword ptr [rsp+0B8h+var_90], r15d
0x1800d2252  mov     [rsp+0B8h+var_98], r12
0x1800d2257  mov     rdx, rdi
0x1800d225a  mov     rcx, [rcx+10h]
0x1800d225e  call    _guard_dispatch_icall
0x1800d2263  test    eax, eax
0x1800d2265  js      short loc_1800D229D
0x1800d2267  test    rsi, rsi
0x1800d226a  jz      short loc_1800D229D
0x1800d226c  mov     r9d, r13d
0x1800d226f  mov     rcx, [rbx+0C00h]
0x1800d2276  mov     rax, qword ptr cs:xmmword_18004A5B0+8
0x1800d227d  mov     r8, rsi
0x1800d2280  mov     rdx, rdi
0x1800d2283  mov     rcx, [rcx+10h]
0x1800d2287  call    _guard_dispatch_icall
0x1800d228c  jmp     short loc_1800D229D
0x1800d228e  mov     eax, 0C000007Bh
0x1800d2293  mov     [rsp+0B8h+var_68], eax
0x1800d2297  jmp     short loc_1800D229D
0x1800d2299  mov     [rsp+0B8h+var_68], eax
0x1800d229d  lea     r11, [rsp+0B8h+var_28]
0x1800d22a5  mov     rbx, [r11+38h]
0x1800d22a9  mov     rsi, [r11+40h]
0x1800d22ad  mov     rsp, r11
0x1800d22b0  pop     r15
0x1800d22b2  pop     r14
0x1800d22b4  pop     r13
0x1800d22b6  pop     r12
0x1800d22b8  pop     rdi
0x1800d22b9  retn
```
