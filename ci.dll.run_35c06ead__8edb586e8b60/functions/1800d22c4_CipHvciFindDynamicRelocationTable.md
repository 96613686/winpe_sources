# CipHvciFindDynamicRelocationTable

- ea: `0x1800d22c4`
- end: `0x1800d2400`
- name: `CipHvciFindDynamicRelocationTable`
- size: `316`
- prototype: `__int64 __usercall@<rax>(PVOID BaseAddress@<rcx>, ULONGLONG Size@<rdx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d2050`

## callees

- `0x1800d22c4`

## import_xrefs

- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800d230b`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800d230b`

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
0x1800d22c4  push    rbx
0x1800d22c6  push    rsi
0x1800d22c7  push    rdi
0x1800d22c8  push    r12
0x1800d22ca  push    r13
0x1800d22cc  push    r14
0x1800d22ce  push    r15
0x1800d22d0  sub     rsp, 40h
0x1800d22d4  mov     r14d, r9d
0x1800d22d7  mov     rsi, r8
0x1800d22da  mov     rdi, rcx
0x1800d22dd  xor     r13d, r13d
0x1800d22e0  mov     [rsp+78h+NtHeader], r13
0x1800d22e5  mov     r15, [rsp+78h+arg_20]
0x1800d22ed  mov     [r15], r13
0x1800d22f0  mov     r12, [rsp+78h+arg_28]
0x1800d22f8  mov     [r12], r13d
0x1800d22fc  mov     ebx, edx
0x1800d22fe  lea     r9, [rsp+78h+NtHeader]; NtHeader
0x1800d2303  mov     r8d, edx; Size
0x1800d2306  mov     rdx, rcx; BaseAddress
0x1800d2309  xor     ecx, ecx; Flags
0x1800d230b  call    cs:__imp_RtlImageNtHeaderEx
0x1800d2312  nop     dword ptr [rax+rax+00h]
0x1800d2317  test    eax, eax
0x1800d2319  js      loc_1800D23EF
0x1800d231f  mov     eax, 20Bh
0x1800d2324  mov     rcx, [rsp+78h+NtHeader]
0x1800d2329  cmp     [rcx+18h], ax
0x1800d232d  jz      short loc_1800D2336
0x1800d232f  xor     eax, eax
0x1800d2331  jmp     loc_1800D23EF
0x1800d2336  cmp     r14d, 0E6h
0x1800d233d  jb      loc_1800D23EB
0x1800d2343  movzx   eax, word ptr [rsi+0E4h]
0x1800d234a  test    ax, ax
0x1800d234d  jz      loc_1800D23EB
0x1800d2353  lea     rdx, [rax+rax*4]
0x1800d2357  movzx   eax, word ptr [rcx+14h]
0x1800d235b  add     rax, 0FFFFFFFFFFFFFFF0h
0x1800d235f  add     rax, rcx
0x1800d2362  lea     rax, [rax+rdx*8]
0x1800d2366  cmp     rax, rdi
0x1800d2369  jb      short loc_1800D23E4
0x1800d236b  lea     rcx, [rbx+rdi]
0x1800d236f  cmp     rax, rcx
0x1800d2372  jnb     short loc_1800D23E4
0x1800d2374  lea     rdx, [rax+28h]
0x1800d2378  cmp     rdx, rdi
0x1800d237b  jb      short loc_1800D23E4
0x1800d237d  cmp     rdx, rcx
0x1800d2380  ja      short loc_1800D23E4
0x1800d2382  lfence
0x1800d2385  mov     eax, [rax+0Ch]
0x1800d2388  add     eax, [rsi+0E0h]
0x1800d238e  mov     ecx, eax
0x1800d2390  mov     [rsp+78h+var_48], rcx
0x1800d2395  cmp     rcx, rbx
0x1800d2398  jnb     short loc_1800D23DD
0x1800d239a  add     rax, 8
0x1800d239e  cmp     rax, rcx
0x1800d23a1  jb      short loc_1800D23DD
0x1800d23a3  cmp     rax, rbx
0x1800d23a6  ja      short loc_1800D23DD
0x1800d23a8  mov     [rsp+78h+var_58], 8
0x1800d23b0  mov     edx, [rcx+rdi+4]
0x1800d23b4  add     edx, 8
0x1800d23b7  mov     [rsp+78h+var_58], edx
0x1800d23bb  mov     r8d, edx
0x1800d23be  add     r8, rcx
0x1800d23c1  cmp     r8, rcx
0x1800d23c4  jb      short loc_1800D23D6
0x1800d23c6  cmp     r8, rbx
0x1800d23c9  ja      short loc_1800D23D6
0x1800d23cb  mov     [r15], rcx
0x1800d23ce  mov     [r12], edx
0x1800d23d2  xor     eax, eax
0x1800d23d4  jmp     short loc_1800D23EF
0x1800d23d6  mov     eax, 0C000007Bh
0x1800d23db  jmp     short loc_1800D23EF
0x1800d23dd  mov     eax, 0C000007Bh
0x1800d23e2  jmp     short loc_1800D23EF
0x1800d23e4  mov     eax, 0C000007Bh
0x1800d23e9  jmp     short loc_1800D23EF
0x1800d23eb  xor     eax, eax
0x1800d23ed  jmp     short $+2
0x1800d23ef  add     rsp, 40h
0x1800d23f3  pop     r15
0x1800d23f5  pop     r14
0x1800d23f7  pop     r13
0x1800d23f9  pop     r12
0x1800d23fb  pop     rdi
0x1800d23fc  pop     rsi
0x1800d23fd  pop     rbx
0x1800d23fe  retn
```
