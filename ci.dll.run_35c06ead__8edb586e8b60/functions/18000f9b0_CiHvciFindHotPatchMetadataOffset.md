# CiHvciFindHotPatchMetadataOffset

- ea: `0x18000f9b0`
- end: `0x18000fb39`
- name: `CiHvciFindHotPatchMetadataOffset`
- size: `393`
- prototype: `__int64 __fastcall(PVOID BaseAddress)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x1800d2050`

## callees

- `0x18000f9b0`

## import_xrefs

- `ntoskrnl!RtlImageNtHeaderEx` at `0x18000f9da`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x18000f9da`

## pseudocode

```c
__int64 __fastcall CiHvciFindHotPatchMetadataOffset(char *BaseAddress, unsigned int *a2, unsigned int a3)
{
  WORD Machine; // cx
  unsigned int *v7; // r9
  unsigned int *v8; // r8
  char *v9; // r10
  __int64 SizeOfImage; // rdx
  unsigned int v11; // r9d
  unsigned int v12; // eax
  unsigned int v13; // r10d
  unsigned int v14; // edx
  unsigned int v15; // edx
  unsigned int v16; // eax
  PIMAGE_NT_HEADERS NtHeader; // [rsp+68h] [rbp+20h] BYREF

  NtHeader = 0;
  RtlImageNtHeaderEx(1u, BaseAddress, 0, &NtHeader);
  Machine = NtHeader->FileHeader.Machine;
  if ( Machine == 0x8664 || Machine == 0xAA64 )
  {
    if ( a3 <= 4 )
      return 0;
    if ( a3 != *a2 )
      return 0;
    v8 = 0;
    v7 = a2;
    if ( a3 < 0xF4 )
      return 0;
  }
  else
  {
    if ( Machine != 332 || a3 <= 4 )
      return 0;
    if ( a3 == 64 )
    {
      a3 = *a2;
    }
    else if ( a3 != *a2 )
    {
      return 0;
    }
    if ( a3 < 0x98 )
      return 0;
    v7 = 0;
    v8 = a2;
  }
  v9 = (char *)a2 + a3;
  if ( v9 < (char *)a2 )
    return 0;
  SizeOfImage = NtHeader->OptionalHeader.SizeOfImage;
  if ( a2 >= (unsigned int *)&BaseAddress[SizeOfImage] || v9 > &BaseAddress[SizeOfImage] )
    return 0;
  v11 = Machine == 0x8664 || Machine == 0xAA64 ? v7[60] : v8[37];
  if ( v11 >= 0xFFFFFFF8 || v11 == 0 || v11 + 8 > (unsigned int)SizeOfImage )
    return 0;
  switch ( *(_DWORD *)&BaseAddress[v11] )
  {
    case 1:
      v12 = 20;
      break;
    case 2:
      v12 = 24;
      break;
    case 3:
      v12 = 28;
      break;
    case 4:
      v12 = 36;
      break;
    default:
      return 0;
  }
  v13 = *(_DWORD *)&BaseAddress[v11 + 4];
  if ( v13 >= v12 )
  {
    if ( *(_DWORD *)&BaseAddress[v11 + 8] )
    {
      if ( v13 + v11 > v13 && v13 + v11 <= (unsigned int)SizeOfImage )
      {
        v14 = *(_DWORD *)&BaseAddress[v11 + 16];
        if ( v14 <= 0x3FFFFFF7 )
        {
          v15 = 4 * v14;
          v16 = v15 + *(_DWORD *)&BaseAddress[v11 + 12];
          if ( v16 > v15 && v16 <= v13 )
            return v11;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000f9b0  push    rbx
0x18000f9b2  push    rbp
0x18000f9b3  push    rsi
0x18000f9b4  push    rdi
0x18000f9b5  sub     rsp, 28h
0x18000f9b9  mov     ebx, r8d
0x18000f9bc  mov     [rsp+48h+NtHeader], 0
0x18000f9c5  xor     r8d, r8d; Size
0x18000f9c8  lea     r9, [rsp+48h+NtHeader]; NtHeader
0x18000f9cd  mov     rdi, rdx
0x18000f9d0  mov     rsi, rcx
0x18000f9d3  mov     rdx, rcx; BaseAddress
0x18000f9d6  lea     ecx, [r8+1]; Flags
0x18000f9da  call    cs:__imp_RtlImageNtHeaderEx
0x18000f9e1  nop     dword ptr [rax+rax+00h]
0x18000f9e6  mov     rdx, [rsp+48h+NtHeader]
0x18000f9eb  mov     ebp, 8664h
0x18000f9f0  mov     r11d, 0AA64h
0x18000f9f6  movzx   ecx, word ptr [rdx+4]
0x18000f9fa  cmp     cx, bp
0x18000f9fd  jz      short loc_18000FA43
0x18000f9ff  cmp     cx, r11w
0x18000fa03  jz      short loc_18000FA43
0x18000fa05  mov     eax, 14Ch
0x18000fa0a  cmp     cx, ax
0x18000fa0d  jnz     loc_18000FB2D
0x18000fa13  mov     eax, ebx
0x18000fa15  cmp     ebx, 4
0x18000fa18  jbe     loc_18000FB2D
0x18000fa1e  cmp     ebx, 40h ; '@'
0x18000fa21  jnz     short loc_18000FA27
0x18000fa23  mov     ebx, [rdi]
0x18000fa25  jmp     short loc_18000FA2F
0x18000fa27  cmp     eax, [rdi]
0x18000fa29  jnz     loc_18000FB2D
0x18000fa2f  cmp     ebx, 98h
0x18000fa35  jb      loc_18000FB2D
0x18000fa3b  xor     r9d, r9d
0x18000fa3e  mov     r8, rdi
0x18000fa41  jmp     short loc_18000FA66
0x18000fa43  cmp     ebx, 4
0x18000fa46  jbe     loc_18000FB2D
0x18000fa4c  cmp     ebx, [rdi]
0x18000fa4e  jnz     loc_18000FB2D
0x18000fa54  xor     r8d, r8d
0x18000fa57  mov     r9, rdi
0x18000fa5a  cmp     ebx, 0F4h
0x18000fa60  jb      loc_18000FB2D
0x18000fa66  mov     r10d, ebx
0x18000fa69  add     r10, rdi
0x18000fa6c  cmp     r10, rdi
0x18000fa6f  jb      loc_18000FB2D
0x18000fa75  mov     edx, [rdx+50h]
0x18000fa78  lea     rax, [rdx+rsi]
0x18000fa7c  cmp     rdi, rax
0x18000fa7f  jnb     loc_18000FB2D
0x18000fa85  cmp     r10, rax
0x18000fa88  ja      loc_18000FB2D
0x18000fa8e  cmp     cx, bp
0x18000fa91  jz      short loc_18000FAA2
0x18000fa93  cmp     cx, r11w
0x18000fa97  jz      short loc_18000FAA2
0x18000fa99  mov     r9d, [r8+94h]
0x18000faa0  jmp     short loc_18000FAA9
0x18000faa2  mov     r9d, [r9+0F0h]
0x18000faa9  lea     eax, [r9+8]
0x18000faad  cmp     eax, 8
0x18000fab0  jbe     short loc_18000FB2D
0x18000fab2  cmp     eax, edx
0x18000fab4  ja      short loc_18000FB2D
0x18000fab6  mov     r8d, r9d
0x18000fab9  mov     ecx, [r8+rsi]
0x18000fabd  sub     ecx, 1
0x18000fac0  jz      short loc_18000FAE4
0x18000fac2  sub     ecx, 1
0x18000fac5  jz      short loc_18000FADD
0x18000fac7  sub     ecx, 1
0x18000faca  jz      short loc_18000FAD6
0x18000facc  cmp     ecx, 1
0x18000facf  jnz     short loc_18000FB2D
0x18000fad1  lea     eax, [rcx+23h]
0x18000fad4  jmp     short loc_18000FAE9
0x18000fad6  mov     eax, 1Ch
0x18000fadb  jmp     short loc_18000FAE9
0x18000fadd  mov     eax, 18h
0x18000fae2  jmp     short loc_18000FAE9
0x18000fae4  mov     eax, 14h
0x18000fae9  mov     r10d, [r8+rsi+4]
0x18000faee  cmp     r10d, eax
0x18000faf1  jb      short loc_18000FB2D
0x18000faf3  cmp     dword ptr [r8+rsi+8], 0
0x18000faf9  jz      short loc_18000FB2D
0x18000fafb  lea     eax, [r10+r9]
0x18000faff  cmp     eax, r10d
0x18000fb02  jbe     short loc_18000FB2D
0x18000fb04  cmp     eax, edx
0x18000fb06  ja      short loc_18000FB2D
0x18000fb08  mov     edx, [r8+rsi+10h]
0x18000fb0d  cmp     edx, 3FFFFFF7h
0x18000fb13  ja      short loc_18000FB2D
0x18000fb15  mov     eax, [r8+rsi+0Ch]
0x18000fb1a  shl     edx, 2
0x18000fb1d  add     eax, edx
0x18000fb1f  cmp     eax, edx
0x18000fb21  jbe     short loc_18000FB2D
0x18000fb23  cmp     eax, r10d
0x18000fb26  ja      short loc_18000FB2D
0x18000fb28  mov     eax, r9d
0x18000fb2b  jmp     short loc_18000FB2F
0x18000fb2d  xor     eax, eax
0x18000fb2f  add     rsp, 28h
0x18000fb33  pop     rdi
0x18000fb34  pop     rsi
0x18000fb35  pop     rbp
0x18000fb36  pop     rbx
0x18000fb37  retn
```
