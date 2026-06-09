# CiHvciFindHotPatchMetadataOffset

- ea: `0x18000f9a0`
- end: `0x18000fb29`
- name: `CiHvciFindHotPatchMetadataOffset`
- size: `393`
- prototype: `__int64 __fastcall(PVOID BaseAddress)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x1800d0b80`

## callees

- `0x18000f9a0`

## import_xrefs

- `ntoskrnl!RtlImageNtHeaderEx` at `0x18000f9ca`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x18000f9ca`

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
0x18000f9a0  push    rbx
0x18000f9a2  push    rbp
0x18000f9a3  push    rsi
0x18000f9a4  push    rdi
0x18000f9a5  sub     rsp, 28h
0x18000f9a9  mov     ebx, r8d
0x18000f9ac  mov     [rsp+48h+NtHeader], 0
0x18000f9b5  xor     r8d, r8d; Size
0x18000f9b8  lea     r9, [rsp+48h+NtHeader]; NtHeader
0x18000f9bd  mov     rdi, rdx
0x18000f9c0  mov     rsi, rcx
0x18000f9c3  mov     rdx, rcx; BaseAddress
0x18000f9c6  lea     ecx, [r8+1]; Flags
0x18000f9ca  call    cs:__imp_RtlImageNtHeaderEx
0x18000f9d1  nop     dword ptr [rax+rax+00h]
0x18000f9d6  mov     rdx, [rsp+48h+NtHeader]
0x18000f9db  mov     ebp, 8664h
0x18000f9e0  mov     r11d, 0AA64h
0x18000f9e6  movzx   ecx, word ptr [rdx+4]
0x18000f9ea  cmp     cx, bp
0x18000f9ed  jz      short loc_18000FA33
0x18000f9ef  cmp     cx, r11w
0x18000f9f3  jz      short loc_18000FA33
0x18000f9f5  mov     eax, 14Ch
0x18000f9fa  cmp     cx, ax
0x18000f9fd  jnz     loc_18000FB1D
0x18000fa03  mov     eax, ebx
0x18000fa05  cmp     ebx, 4
0x18000fa08  jbe     loc_18000FB1D
0x18000fa0e  cmp     ebx, 40h ; '@'
0x18000fa11  jnz     short loc_18000FA17
0x18000fa13  mov     ebx, [rdi]
0x18000fa15  jmp     short loc_18000FA1F
0x18000fa17  cmp     eax, [rdi]
0x18000fa19  jnz     loc_18000FB1D
0x18000fa1f  cmp     ebx, 98h
0x18000fa25  jb      loc_18000FB1D
0x18000fa2b  xor     r9d, r9d
0x18000fa2e  mov     r8, rdi
0x18000fa31  jmp     short loc_18000FA56
0x18000fa33  cmp     ebx, 4
0x18000fa36  jbe     loc_18000FB1D
0x18000fa3c  cmp     ebx, [rdi]
0x18000fa3e  jnz     loc_18000FB1D
0x18000fa44  xor     r8d, r8d
0x18000fa47  mov     r9, rdi
0x18000fa4a  cmp     ebx, 0F4h
0x18000fa50  jb      loc_18000FB1D
0x18000fa56  mov     r10d, ebx
0x18000fa59  add     r10, rdi
0x18000fa5c  cmp     r10, rdi
0x18000fa5f  jb      loc_18000FB1D
0x18000fa65  mov     edx, [rdx+50h]
0x18000fa68  lea     rax, [rdx+rsi]
0x18000fa6c  cmp     rdi, rax
0x18000fa6f  jnb     loc_18000FB1D
0x18000fa75  cmp     r10, rax
0x18000fa78  ja      loc_18000FB1D
0x18000fa7e  cmp     cx, bp
0x18000fa81  jz      short loc_18000FA92
0x18000fa83  cmp     cx, r11w
0x18000fa87  jz      short loc_18000FA92
0x18000fa89  mov     r9d, [r8+94h]
0x18000fa90  jmp     short loc_18000FA99
0x18000fa92  mov     r9d, [r9+0F0h]
0x18000fa99  lea     eax, [r9+8]
0x18000fa9d  cmp     eax, 8
0x18000faa0  jbe     short loc_18000FB1D
0x18000faa2  cmp     eax, edx
0x18000faa4  ja      short loc_18000FB1D
0x18000faa6  mov     r8d, r9d
0x18000faa9  mov     ecx, [r8+rsi]
0x18000faad  sub     ecx, 1
0x18000fab0  jz      short loc_18000FAD4
0x18000fab2  sub     ecx, 1
0x18000fab5  jz      short loc_18000FACD
0x18000fab7  sub     ecx, 1
0x18000faba  jz      short loc_18000FAC6
0x18000fabc  cmp     ecx, 1
0x18000fabf  jnz     short loc_18000FB1D
0x18000fac1  lea     eax, [rcx+23h]
0x18000fac4  jmp     short loc_18000FAD9
0x18000fac6  mov     eax, 1Ch
0x18000facb  jmp     short loc_18000FAD9
0x18000facd  mov     eax, 18h
0x18000fad2  jmp     short loc_18000FAD9
0x18000fad4  mov     eax, 14h
0x18000fad9  mov     r10d, [r8+rsi+4]
0x18000fade  cmp     r10d, eax
0x18000fae1  jb      short loc_18000FB1D
0x18000fae3  cmp     dword ptr [r8+rsi+8], 0
0x18000fae9  jz      short loc_18000FB1D
0x18000faeb  lea     eax, [r10+r9]
0x18000faef  cmp     eax, r10d
0x18000faf2  jbe     short loc_18000FB1D
0x18000faf4  cmp     eax, edx
0x18000faf6  ja      short loc_18000FB1D
0x18000faf8  mov     edx, [r8+rsi+10h]
0x18000fafd  cmp     edx, 3FFFFFF7h
0x18000fb03  ja      short loc_18000FB1D
0x18000fb05  mov     eax, [r8+rsi+0Ch]
0x18000fb0a  shl     edx, 2
0x18000fb0d  add     eax, edx
0x18000fb0f  cmp     eax, edx
0x18000fb11  jbe     short loc_18000FB1D
0x18000fb13  cmp     eax, r10d
0x18000fb16  ja      short loc_18000FB1D
0x18000fb18  mov     eax, r9d
0x18000fb1b  jmp     short loc_18000FB1F
0x18000fb1d  xor     eax, eax
0x18000fb1f  add     rsp, 28h
0x18000fb23  pop     rdi
0x18000fb24  pop     rsi
0x18000fb25  pop     rbp
0x18000fb26  pop     rbx
0x18000fb27  retn
```
