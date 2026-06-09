# CsrCaptureArguments

- ea: `0x180001c50`
- end: `0x180002037`
- name: `CsrCaptureArguments`
- size: `999`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800097f0`

## callees

- `0x180001140`
- `0x180001c50`
- `0x1800035c0`
- `0x180008d94`
- `0x18000ab55`
- `0x18000ab61`
- `0x18000ab80`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180001d32`
- `ntdll!RtlAllocateHeap` at `0x180001d32`
- `ntdll!RtlFreeHeap` at `0x180001ef8`
- `ntdll!RtlFreeHeap` at `0x180002006`
- `ntdll!RtlFreeHeap` at `0x180001ef8`
- `ntdll!RtlFreeHeap` at `0x180002006`

## pseudocode

```c
char __fastcall CsrCaptureArguments(__int64 a1, __int64 a2)
{
  __int64 v3; // r15
  unsigned int v4; // ebx
  unsigned __int64 v5; // r12
  char *Heap; // rax
  char *v7; // rdi
  size_t v9; // rdx
  HRESULT v10; // eax
  char v11; // dl
  __int64 v12; // rcx
  __int64 *v13; // r8
  __int64 v14; // rdx
  _QWORD *v15; // r9
  unsigned __int64 v16; // rdx
  unsigned int *Src; // [rsp+30h] [rbp-148h]
  unsigned int v18; // [rsp+40h] [rbp-138h]
  char pszDest[16]; // [rsp+60h] [rbp-118h] BYREF
  __int128 v20; // [rsp+70h] [rbp-108h]
  __int128 v21; // [rsp+80h] [rbp-F8h]
  __int128 v22; // [rsp+90h] [rbp-E8h]
  __int128 v23; // [rsp+A0h] [rbp-D8h]
  __int128 v24; // [rsp+B0h] [rbp-C8h]
  __int128 v25; // [rsp+C0h] [rbp-B8h]
  __int128 v26; // [rsp+D0h] [rbp-A8h]
  __int128 v27; // [rsp+E0h] [rbp-98h]
  __int128 v28; // [rsp+F0h] [rbp-88h]
  __int128 v29; // [rsp+100h] [rbp-78h]
  _BYTE v30[28]; // [rsp+110h] [rbp-68h]

  Src = *(unsigned int **)(a2 + 40);
  *(_DWORD *)(a2 + 52) = 0;
  if ( (unsigned __int64)Src < *(_QWORD *)(*(_QWORD *)(a1 + 56) + 64LL)
    || (unsigned __int64)Src > *(_QWORD *)(*(_QWORD *)(a1 + 56) + 72LL) - 32LL )
  {
    *(_DWORD *)(a2 + 52) = -1073741811;
    CsrpLogFailure("CsrCaptureArguments");
    return 0;
  }
  v18 = *Src;
  v3 = *Src;
  if ( (unsigned int *)((char *)Src + v3) >= Src
    && (unsigned __int64)Src + v18 <= *(_QWORD *)(*(_QWORD *)(a1 + 56) + 72LL) )
  {
    v4 = Src[4];
    v5 = 8LL * v4 + 32;
    if ( v18 < v5 || v4 > 0xFFFF )
    {
      *(_DWORD *)(a2 + 52) = -1073741811;
      CsrpLogModuleFailureInt("CsrCaptureArguments", -1073741811);
      return 0;
    }
    Heap = (char *)RtlAllocateHeap(CsrHeap, CsrBaseTag + 0x80000, v18);
    v7 = Heap;
    if ( !Heap )
    {
      *(_DWORD *)(a2 + 52) = -1073741801;
      return 0;
    }
    memcpy_0(Heap, Src, (unsigned int)v3);
    *(_DWORD *)v7 = v3;
    *((_DWORD *)v7 + 4) = v4;
    v13 = (__int64 *)(v7 + 32);
    while ( v4 )
    {
      v14 = *v13;
      if ( *v13 )
      {
        if ( (unsigned __int64)(v14 - 64) > 0x370
          || (v14 & 7) != 0
          || (v15 = (_QWORD *)(v14 + a2), v16 = *(_QWORD *)(v14 + a2), v16 < (unsigned __int64)Src + v5)
          || v16 > (unsigned __int64)Src + v3 - 8 )
        {
          *(_DWORD *)(a2 + 52) = -1073741811;
          CsrpLogFailure("CsrCaptureArguments");
          break;
        }
        *v15 = v16 + v7 - (char *)Src;
      }
      ++v13;
      --v4;
    }
    if ( !*(_DWORD *)(a2 + 52) )
    {
      *((_QWORD *)v7 + 1) = Src;
      *(_QWORD *)(a2 + 40) = v7;
      return 1;
    }
    RtlFreeHeap(CsrHeap, 0, v7);
    return 0;
  }
  *(_DWORD *)(a2 + 52) = -1073741811;
  memset_0(pszDest, 0, 0xCCu);
  *(_DWORD *)&v30[16] = -1073741811;
  *(_DWORD *)&v30[24] = 1401;
  v10 = StringCbCopyA(pszDest, v9, "CsrCaptureArguments");
  if ( (int)(v10 + 0x80000000) >= 0 )
  {
    v11 = pszDest[0];
    if ( v10 != -2147024774 )
      v11 = 0;
    pszDest[0] = v11;
  }
  v12 = 204LL * (_InterlockedIncrement(&dword_18000F024) % 16);
  *(_OWORD *)&CsrpBlackboxBuffer[v12 + 8] = *(_OWORD *)pszDest;
  *(_OWORD *)&CsrpBlackboxBuffer[v12 + 24] = v20;
  *(_OWORD *)&CsrpBlackboxBuffer[v12 + 40] = v21;
  *(_OWORD *)&CsrpBlackboxBuffer[v12 + 56] = v22;
  *(_OWORD *)&CsrpBlackboxBuffer[v12 + 72] = v23;
  *(_OWORD *)&CsrpBlackboxBuffer[v12 + 88] = v24;
  *(_OWORD *)&CsrpBlackboxBuffer[v12 + 104] = v25;
  *(_OWORD *)&CsrpBlackboxBuffer[v12 + 120] = v26;
  *(_OWORD *)&CsrpBlackboxBuffer[v12 + 136] = v27;
  *(_OWORD *)&CsrpBlackboxBuffer[v12 + 152] = v28;
  *(_OWORD *)&CsrpBlackboxBuffer[v12 + 168] = v29;
  *(_OWORD *)&CsrpBlackboxBuffer[v12 + 184] = *(_OWORD *)v30;
  *(_OWORD *)&CsrpBlackboxBuffer[v12 + 196] = *(_OWORD *)&v30[12];
  return 0;
}

```

## disassembly

```asm
0x180001c50  push    rbx
0x180001c52  push    rsi
0x180001c53  push    rdi
0x180001c54  push    r12
0x180001c56  push    r14
0x180001c58  push    r15
0x180001c5a  sub     rsp, 148h
0x180001c61  mov     rax, cs:__security_cookie
0x180001c68  xor     rax, rsp
0x180001c6b  mov     [rsp+178h+var_48], rax
0x180001c73  mov     r14, rdx
0x180001c76  mov     rdx, rcx
0x180001c79  mov     [rsp+178h+var_128], r14
0x180001c7e  mov     rax, [r14+28h]
0x180001c82  mov     [rsp+178h+Src], rax
0x180001c87  xor     ebx, ebx
0x180001c89  mov     [r14+34h], ebx
0x180001c8d  mov     rax, [rcx+38h]
0x180001c91  mov     rcx, [rax+40h]
0x180001c95  mov     rax, [rsp+178h+Src]
0x180001c9a  cmp     rax, rcx
0x180001c9d  jb      loc_180002014
0x180001ca3  mov     [rsp+178h+BaseAddress], rbx
0x180001ca8  mov     rax, [rdx+38h]
0x180001cac  mov     rcx, [rax+48h]
0x180001cb0  add     rcx, 0FFFFFFFFFFFFFFE0h
0x180001cb4  mov     rax, [rsp+178h+Src]
0x180001cb9  cmp     rax, rcx
0x180001cbc  ja      loc_180002014
0x180001cc2  mov     rax, [rsp+178h+Src]
0x180001cc7  mov     r15d, [rax]
0x180001cca  mov     [rsp+178h+var_138], r15d
0x180001ccf  mov     rcx, [rsp+178h+Src]
0x180001cd4  mov     rax, [rsp+178h+Src]
0x180001cd9  add     rax, r15
0x180001cdc  cmp     rax, rcx
0x180001cdf  jb      loc_180001DA1
0x180001ce5  mov     rcx, [rsp+178h+Src]
0x180001cea  add     rcx, r15
0x180001ced  mov     rax, [rdx+38h]
0x180001cf1  cmp     rcx, [rax+48h]
0x180001cf5  ja      loc_180001DA1
0x180001cfb  mov     rax, [rsp+178h+Src]
0x180001d00  mov     ebx, [rax+10h]
0x180001d03  mov     [rsp+178h+var_134], ebx
0x180001d07  lea     r12, ds:20h[rbx*8]
0x180001d0f  cmp     r15, r12
0x180001d12  jb      short loc_180001D6F
0x180001d14  cmp     ebx, 0FFFFh
0x180001d1a  ja      short loc_180001D6F
0x180001d1c  mov     edx, cs:CsrBaseTag
0x180001d22  add     edx, 80000h; Flags
0x180001d28  mov     r8d, r15d; Size
0x180001d2b  mov     rcx, cs:CsrHeap; HeapHandle
0x180001d32  call    cs:__imp_RtlAllocateHeap
0x180001d39  nop     dword ptr [rax+rax+00h]
0x180001d3e  mov     rdi, rax
0x180001d41  mov     [rsp+178h+BaseAddress], rax
0x180001d46  test    rax, rax
0x180001d49  jz      short loc_180001D60
0x180001d4b  mov     rdx, [rsp+178h+Src]; Src
0x180001d50  mov     r8d, r15d; MaxCount
0x180001d53  mov     rcx, rax; void *
0x180001d56  call    memcpy_0
0x180001d5b  jmp     loc_180001F2E
0x180001d60  mov     dword ptr [r14+34h], 0C0000017h
0x180001d68  xor     al, al
0x180001d6a  jmp     loc_180001FD1
0x180001d6f  mov     dword ptr [r14+34h], 0C000000Dh
0x180001d77  mov     [rsp+178h+var_158], 0C000000Dh; int
0x180001d7f  mov     r9d, r15d
0x180001d82  lea     r8, qword_18000C660
0x180001d89  mov     edx, 58Ch
0x180001d8e  lea     rcx, pszSrc; "CsrCaptureArguments"
0x180001d95  call    CsrpLogModuleFailureInt
0x180001d9a  xor     al, al
0x180001d9c  jmp     loc_180001FD1
0x180001da1  mov     dword ptr [r14+34h], 0C000000Dh
0x180001da9  xor     edx, edx; Val
0x180001dab  mov     r8d, 0CCh; Size
0x180001db1  lea     rcx, [rsp+178h+pszDest]; void *
0x180001db6  call    memset_0
0x180001dbb  mov     [rsp+178h+var_58], 0C000000Dh
0x180001dc6  mov     [rsp+178h+var_50], 579h
0x180001dd1  lea     r8, pszSrc; "CsrCaptureArguments"
0x180001dd8  lea     rcx, [rsp+178h+pszDest]; pszDest
0x180001ddd  call    StringCbCopyA
0x180001de2  mov     edx, 80000000h
0x180001de7  lea     ecx, [rax+rdx]
0x180001dea  test    edx, ecx
0x180001dec  jnz     short loc_180001DFF
0x180001dee  movzx   edx, [rsp+178h+pszDest]
0x180001df3  cmp     eax, 8007007Ah
0x180001df8  cmovnz  edx, ebx
0x180001dfb  mov     [rsp+178h+pszDest], dl
0x180001dff  mov     eax, 1
0x180001e04  lock xadd cs:dword_18000F024, eax
0x180001e0c  inc     eax
0x180001e0e  and     eax, 8000000Fh
0x180001e13  jge     short loc_180001E1C
0x180001e15  dec     eax
0x180001e17  or      eax, 0FFFFFFF0h
0x180001e1a  inc     eax
0x180001e1c  cdqe
0x180001e1e  imul    rcx, rax, 0CCh
0x180001e25  lea     rax, CsrpBlackboxBuffer
0x180001e2c  movaps  xmm0, xmmword ptr [rsp+178h+pszDest]
0x180001e31  movups  xmmword ptr [rcx+rax+8], xmm0
0x180001e36  movaps  xmm1, [rsp+178h+var_108]
0x180001e3b  movups  xmmword ptr [rcx+rax+18h], xmm1
0x180001e40  movaps  xmm0, [rsp+178h+var_F8]
0x180001e48  movups  xmmword ptr [rcx+rax+28h], xmm0
0x180001e4d  movaps  xmm1, [rsp+178h+var_E8]
0x180001e55  movups  xmmword ptr [rcx+rax+38h], xmm1
0x180001e5a  movaps  xmm0, [rsp+178h+var_D8]
0x180001e62  movups  xmmword ptr [rcx+rax+48h], xmm0
0x180001e67  movaps  xmm1, [rsp+178h+var_C8]
0x180001e6f  movups  xmmword ptr [rcx+rax+58h], xmm1
0x180001e74  movaps  xmm0, [rsp+178h+var_B8]
0x180001e7c  movups  xmmword ptr [rcx+rax+68h], xmm0
0x180001e81  movaps  xmm1, [rsp+178h+var_A8]
0x180001e89  movups  xmmword ptr [rcx+rax+78h], xmm1
0x180001e8e  movaps  xmm0, [rsp+178h+var_98]
0x180001e96  movups  xmmword ptr [rcx+rax+88h], xmm0
0x180001e9e  movaps  xmm1, [rsp+178h+var_88]
0x180001ea6  movups  xmmword ptr [rcx+rax+98h], xmm1
0x180001eae  movaps  xmm0, [rsp+178h+var_78]
0x180001eb6  movups  xmmword ptr [rcx+rax+0A8h], xmm0
0x180001ebe  movaps  xmm1, [rsp+178h+var_68]
0x180001ec6  movups  xmmword ptr [rcx+rax+0B8h], xmm1
0x180001ece  movups  xmm0, [rsp+178h+var_68+0Ch]
0x180001ed6  movups  xmmword ptr [rcx+rax+0C4h], xmm0
0x180001ede  xor     al, al
0x180001ee0  jmp     loc_180001FD1
0x180001ee5  mov     r8, [rsp+178h+BaseAddress]; BaseAddress
0x180001eea  test    r8, r8
0x180001eed  jz      short loc_180001F04
0x180001eef  xor     edx, edx; Flags
0x180001ef1  mov     rcx, cs:CsrHeap; HeapHandle
0x180001ef8  call    cs:__imp_RtlFreeHeap
0x180001eff  nop     dword ptr [rax+rax+00h]
0x180001f04  mov     rax, [rsp+178h+var_128]
0x180001f09  mov     dword ptr [rax+34h], 0C000000Dh
0x180001f10  mov     edx, 5ACh
0x180001f15  mov     r8d, 0C000000Dh
0x180001f1b  lea     rcx, pszSrc; "CsrCaptureArguments"
0x180001f22  call    CsrpLogFailure
0x180001f27  xor     al, al
0x180001f29  jmp     loc_180001FD1
0x180001f2e  mov     [rdi], r15d
0x180001f31  mov     [rdi+10h], ebx
0x180001f34  mov     rax, [rsp+178h+Src]
0x180001f39  mov     r10, rdi
0x180001f3c  sub     r10, rax
0x180001f3f  lea     r8, [rdi+20h]
0x180001f43  test    ebx, ebx
0x180001f45  jz      short loc_180001FBB
0x180001f47  mov     rdx, [r8]
0x180001f4a  test    rdx, rdx
0x180001f4d  jz      short loc_180001F94
0x180001f4f  lea     rax, [rdx-40h]
0x180001f53  cmp     rax, 370h
0x180001f59  ja      loc_180001FF3
0x180001f5f  test    dl, 7
0x180001f62  jnz     loc_180001FF3
0x180001f68  mov     rcx, [rsp+178h+Src]
0x180001f6d  add     rcx, r12
0x180001f70  lea     r9, [rdx+r14]
0x180001f74  mov     rdx, [r9]
0x180001f77  cmp     rdx, rcx
0x180001f7a  jb      short loc_180001F9C
0x180001f7c  mov     rcx, [rsp+178h+Src]
0x180001f81  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180001f85  add     rcx, r15
0x180001f88  cmp     rdx, rcx
0x180001f8b  ja      short loc_180001F9C
0x180001f8d  lea     rax, [rdx+r10]
0x180001f91  mov     [r9], rax
0x180001f94  add     r8, 8
0x180001f98  dec     ebx
0x180001f9a  jmp     short loc_180001F43
0x180001f9c  mov     edx, 5EEh
0x180001fa1  mov     dword ptr [r14+34h], 0C000000Dh
0x180001fa9  mov     r8d, 0C000000Dh
0x180001faf  lea     rcx, pszSrc; "CsrCaptureArguments"
0x180001fb6  call    CsrpLogFailure
0x180001fbb  cmp     dword ptr [r14+34h], 0
0x180001fc0  jnz     short loc_180001FFA
0x180001fc2  mov     rax, [rsp+178h+Src]
0x180001fc7  mov     [rdi+8], rax
0x180001fcb  mov     [r14+28h], rdi
0x180001fcf  mov     al, 1
0x180001fd1  mov     rcx, [rsp+178h+var_48]
0x180001fd9  xor     rcx, rsp; StackCookie
0x180001fdc  call    __security_check_cookie
0x180001fe1  add     rsp, 148h
0x180001fe8  pop     r15
0x180001fea  pop     r14
0x180001fec  pop     r12
0x180001fee  pop     rdi
0x180001fef  pop     rsi
0x180001ff0  pop     rbx
0x180001ff1  retn
0x180001ff3  mov     edx, 5D1h
0x180001ff8  jmp     short loc_180001FA1
0x180001ffa  mov     r8, rdi; BaseAddress
0x180001ffd  xor     edx, edx; Flags
0x180001fff  mov     rcx, cs:CsrHeap; HeapHandle
0x180002006  call    cs:__imp_RtlFreeHeap
0x18000200d  nop     dword ptr [rax+rax+00h]
0x180002012  jmp     short loc_180002033
0x180002014  mov     dword ptr [r14+34h], 0C000000Dh
0x18000201c  mov     edx, 565h
0x180002021  mov     r8d, 0C000000Dh
0x180002027  lea     rcx, pszSrc; "CsrCaptureArguments"
0x18000202e  call    CsrpLogFailure
0x180002033  xor     al, al
0x180002035  jmp     short loc_180001FD1
```
