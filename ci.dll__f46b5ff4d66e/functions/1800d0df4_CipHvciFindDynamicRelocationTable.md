# CipHvciFindDynamicRelocationTable

- ea: `0x1800d0df4`
- end: `0x1800d0f30`
- name: `CipHvciFindDynamicRelocationTable`
- size: `316`
- prototype: `__int64 __usercall@<rax>(PVOID BaseAddress@<rcx>, ULONGLONG Size@<rdx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d0b80`

## callees

- `0x1800d0df4`

## import_xrefs

- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800d0e3b`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800d0e3b`

## pseudocode

```c
NTSTATUS __fastcall CipHvciFindDynamicRelocationTable(
        char *BaseAddress,
        ULONGLONG Size,
        __int64 a3,
        unsigned int a4,
        unsigned __int64 *a5,
        unsigned int *a6)
{
  unsigned __int64 v9; // rbx
  NTSTATUS result; // eax
  __int64 v11; // rax
  char *v12; // rax
  __int64 v13; // rax
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rax
  unsigned int v16; // edx
  unsigned __int64 v17; // r8
  PIMAGE_NT_HEADERS NtHeader[10]; // [rsp+28h] [rbp-50h] BYREF

  NtHeader[0] = 0;
  *a5 = 0;
  *a6 = 0;
  v9 = (unsigned int)Size;
  result = RtlImageNtHeaderEx(0, BaseAddress, (unsigned int)Size, NtHeader);
  if ( result >= 0 )
  {
    if ( NtHeader[0]->OptionalHeader.Magic == 523 )
    {
      if ( a4 >= 0xE6 && (v11 = *(unsigned __int16 *)(a3 + 228), (_WORD)v11) )
      {
        v12 = (char *)NtHeader[0] + 40 * v11 + NtHeader[0]->FileHeader.SizeOfOptionalHeader - 16;
        if ( v12 < BaseAddress || v12 >= &BaseAddress[v9] || v12 + 40 < BaseAddress || v12 + 40 > &BaseAddress[v9] )
        {
          return -1073741701;
        }
        else
        {
          _mm_lfence();
          v13 = (unsigned int)(*(_DWORD *)(a3 + 224) + *((_DWORD *)v12 + 3));
          v14 = (unsigned int)v13;
          NtHeader[1] = (PIMAGE_NT_HEADERS)(unsigned int)v13;
          if ( (unsigned int)v13 >= v9 )
            return -1073741701;
          v15 = v13 + 8;
          if ( v15 < v14 || v15 > v9 )
          {
            return -1073741701;
          }
          else
          {
            v16 = *(_DWORD *)&BaseAddress[v14 + 4] + 8;
            v17 = v14 + v16;
            if ( v17 < v14 || v17 > v9 )
            {
              return -1073741701;
            }
            else
            {
              *a5 = v14;
              *a6 = v16;
              return 0;
            }
          }
        }
      }
      else
      {
        return 0;
      }
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800d0df4  push    rbx
0x1800d0df6  push    rsi
0x1800d0df7  push    rdi
0x1800d0df8  push    r12
0x1800d0dfa  push    r13
0x1800d0dfc  push    r14
0x1800d0dfe  push    r15
0x1800d0e00  sub     rsp, 40h
0x1800d0e04  mov     r14d, r9d
0x1800d0e07  mov     rsi, r8
0x1800d0e0a  mov     rdi, rcx
0x1800d0e0d  xor     r13d, r13d
0x1800d0e10  mov     [rsp+78h+NtHeader], r13
0x1800d0e15  mov     r15, [rsp+78h+arg_20]
0x1800d0e1d  mov     [r15], r13
0x1800d0e20  mov     r12, [rsp+78h+arg_28]
0x1800d0e28  mov     [r12], r13d
0x1800d0e2c  mov     ebx, edx
0x1800d0e2e  lea     r9, [rsp+78h+NtHeader]; NtHeader
0x1800d0e33  mov     r8d, edx; Size
0x1800d0e36  mov     rdx, rcx; BaseAddress
0x1800d0e39  xor     ecx, ecx; Flags
0x1800d0e3b  call    cs:__imp_RtlImageNtHeaderEx
0x1800d0e42  nop     dword ptr [rax+rax+00h]
0x1800d0e47  test    eax, eax
0x1800d0e49  js      loc_1800D0F1F
0x1800d0e4f  mov     eax, 20Bh
0x1800d0e54  mov     rcx, [rsp+78h+NtHeader]
0x1800d0e59  cmp     [rcx+18h], ax
0x1800d0e5d  jz      short loc_1800D0E66
0x1800d0e5f  xor     eax, eax
0x1800d0e61  jmp     loc_1800D0F1F
0x1800d0e66  cmp     r14d, 0E6h
0x1800d0e6d  jb      loc_1800D0F1B
0x1800d0e73  movzx   eax, word ptr [rsi+0E4h]
0x1800d0e7a  test    ax, ax
0x1800d0e7d  jz      loc_1800D0F1B
0x1800d0e83  lea     rdx, [rax+rax*4]
0x1800d0e87  movzx   eax, word ptr [rcx+14h]
0x1800d0e8b  add     rax, 0FFFFFFFFFFFFFFF0h
0x1800d0e8f  add     rax, rcx
0x1800d0e92  lea     rax, [rax+rdx*8]
0x1800d0e96  cmp     rax, rdi
0x1800d0e99  jb      short loc_1800D0F14
0x1800d0e9b  lea     rcx, [rbx+rdi]
0x1800d0e9f  cmp     rax, rcx
0x1800d0ea2  jnb     short loc_1800D0F14
0x1800d0ea4  lea     rdx, [rax+28h]
0x1800d0ea8  cmp     rdx, rdi
0x1800d0eab  jb      short loc_1800D0F14
0x1800d0ead  cmp     rdx, rcx
0x1800d0eb0  ja      short loc_1800D0F14
0x1800d0eb2  lfence
0x1800d0eb5  mov     eax, [rax+0Ch]
0x1800d0eb8  add     eax, [rsi+0E0h]
0x1800d0ebe  mov     ecx, eax
0x1800d0ec0  mov     [rsp+78h+var_48], rcx
0x1800d0ec5  cmp     rcx, rbx
0x1800d0ec8  jnb     short loc_1800D0F0D
0x1800d0eca  add     rax, 8
0x1800d0ece  cmp     rax, rcx
0x1800d0ed1  jb      short loc_1800D0F0D
0x1800d0ed3  cmp     rax, rbx
0x1800d0ed6  ja      short loc_1800D0F0D
0x1800d0ed8  mov     [rsp+78h+var_58], 8
0x1800d0ee0  mov     edx, [rcx+rdi+4]
0x1800d0ee4  add     edx, 8
0x1800d0ee7  mov     [rsp+78h+var_58], edx
0x1800d0eeb  mov     r8d, edx
0x1800d0eee  add     r8, rcx
0x1800d0ef1  cmp     r8, rcx
0x1800d0ef4  jb      short loc_1800D0F06
0x1800d0ef6  cmp     r8, rbx
0x1800d0ef9  ja      short loc_1800D0F06
0x1800d0efb  mov     [r15], rcx
0x1800d0efe  mov     [r12], edx
0x1800d0f02  xor     eax, eax
0x1800d0f04  jmp     short loc_1800D0F1F
0x1800d0f06  mov     eax, 0C000007Bh
0x1800d0f0b  jmp     short loc_1800D0F1F
0x1800d0f0d  mov     eax, 0C000007Bh
0x1800d0f12  jmp     short loc_1800D0F1F
0x1800d0f14  mov     eax, 0C000007Bh
0x1800d0f19  jmp     short loc_1800D0F1F
0x1800d0f1b  xor     eax, eax
0x1800d0f1d  jmp     short $+2
0x1800d0f1f  add     rsp, 40h
0x1800d0f23  pop     r15
0x1800d0f25  pop     r14
0x1800d0f27  pop     r13
0x1800d0f29  pop     r12
0x1800d0f2b  pop     rdi
0x1800d0f2c  pop     rsi
0x1800d0f2d  pop     rbx
0x1800d0f2e  retn
```
