# Dhcpv6AppendParamRequestList

- ea: `0x180027e20`
- end: `0x180027ff7`
- name: `Dhcpv6AppendParamRequestList`
- size: `471`
- prototype: `__int64 __fastcall(__int64, _QWORD **, __int64, int, _QWORD *, _DWORD *, unsigned __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180013b6c`
- `0x180017ffc`

## callees

- `0x180002cac`
- `0x180019ad0`
- `0x18001a3ee`
- `0x180027e20`
- `0x1800338c0`

## import_xrefs

- `DNSAPI!DnsQueryConfigDword` at `0x180027ed3`
- `DNSAPI!DnsQueryConfigDword` at `0x180027ed3`

## pseudocode

```c
__int64 __fastcall Dhcpv6AppendParamRequestList(
        __int64 a1,
        _QWORD **a2,
        __int64 a3,
        int a4,
        _QWORD *a5,
        _DWORD *a6,
        unsigned __int64 a7)
{
  char v11; // al
  unsigned int v12; // ebx
  __int64 v13; // rax
  _QWORD *v14; // r10
  _QWORD *v15; // rdx
  __int64 i; // r9
  __int64 v17; // r11
  __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned int appended; // eax
  unsigned int v21; // ebx
  int *Src; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v24; // [rsp+48h] [rbp-B8h]
  int v25; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v26; // [rsp+54h] [rbp-ACh]
  __int16 v27[101]; // [rsp+56h] [rbp-AAh] BYREF

  memset_0(v27, 0, 0xC2u);
  v25 = 1507345;
  v26 = 24;
  v11 = *(_BYTE *)(a1 + 668);
  if ( v11 == 11 )
  {
    v27[0] = 32;
    v12 = 4;
  }
  else
  {
    v12 = 3;
    if ( (v11 == 1 || v11 == 3 || v11 == 5 || v11 == 6)
      && (unsigned int)DnsQueryConfigDword(65552, *(_QWORD *)(a1 + 56)) )
    {
      v12 = 4;
      v27[0] = 39;
    }
  }
  if ( dword_180042678 )
  {
    v13 = v12++;
    *((_WORD *)&v25 + v13) = 144;
  }
  v14 = *a2;
  while ( v14 != a2 )
  {
    v15 = v14;
    v14 = (_QWORD *)*v14;
    if ( !*((_DWORD *)v15 + 5)
      && (!*((_DWORD *)v15 + 8) || *((_DWORD *)v15 + 8) == a4 && v15[3] == a3)
      && *((_WORD *)v15 + 8) == 6 )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)v15 + 14); i = (unsigned int)(i + 2) )
      {
        if ( v12 >= 0x64 )
          break;
        v17 = v15[6];
        if ( v12 )
        {
          v18 = 0;
          while ( *(_WORD *)(v17 + i) != *((_WORD *)&v25 + v18) )
          {
            v18 = (unsigned int)(v18 + 1);
            if ( (unsigned int)v18 >= v12 )
              goto LABEL_23;
          }
        }
        else
        {
LABEL_23:
          v19 = v12++;
          *((_WORD *)&v25 + v19) = *(_WORD *)(v17 + i);
        }
      }
    }
  }
  Src = &v25;
  v24 = v12;
  appended = Dhcpv6AppendOption(&Src, 0xCu, 6u, a6, a5, a7);
  v21 = appended;
  if ( appended && (xmmword_1800423E0 & 2) != 0 )
    WPP_SF_D(1025, 33, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids, appended);
  return v21;
}

```

## disassembly

```asm
0x180027e20  push    rbp
0x180027e22  push    rbx
0x180027e23  push    rsi
0x180027e24  push    rdi
0x180027e25  push    r12
0x180027e27  push    r13
0x180027e29  push    r14
0x180027e2b  push    r15
0x180027e2d  lea     rbp, [rsp-38h]
0x180027e32  sub     rsp, 138h
0x180027e39  mov     rax, cs:__security_cookie
0x180027e40  xor     rax, rsp
0x180027e43  mov     [rbp+70h+var_50], rax
0x180027e47  mov     rax, [rbp+70h+arg_28]
0x180027e4e  mov     r15, r8
0x180027e51  mov     r13, [rbp+70h+arg_20]
0x180027e58  mov     r14, rdx
0x180027e5b  mov     [rsp+170h+var_138], rax
0x180027e60  mov     rdi, rcx
0x180027e63  mov     rax, [rbp+70h+arg_30]
0x180027e6a  lea     rcx, [rsp+170h+var_11A]; void *
0x180027e6f  xor     edx, edx; Val
0x180027e71  mov     [rsp+170h+var_140], rax
0x180027e76  mov     r8d, 0C2h; Size
0x180027e7c  mov     r12d, r9d
0x180027e7f  call    memset_0
0x180027e84  mov     eax, 18h
0x180027e89  mov     [rsp+170h+var_120], 170011h
0x180027e91  mov     [rsp+170h+var_11C], ax
0x180027e96  mov     esi, 6
0x180027e9b  mov     al, [rdi+29Ch]
0x180027ea1  cmp     al, 0Bh
0x180027ea3  jnz     short loc_180027EB2
0x180027ea5  lea     eax, [rsi+1Ah]
0x180027ea8  mov     [rsp+170h+var_11A], ax
0x180027ead  lea     ebx, [rsi-2]
0x180027eb0  jmp     short loc_180027EF1
0x180027eb2  mov     ecx, 3
0x180027eb7  mov     ebx, ecx
0x180027eb9  cmp     al, 1
0x180027ebb  jz      short loc_180027ECA
0x180027ebd  cmp     al, cl
0x180027ebf  jz      short loc_180027ECA
0x180027ec1  cmp     al, 5
0x180027ec3  jz      short loc_180027ECA
0x180027ec5  cmp     al, sil
0x180027ec8  jnz     short loc_180027EF1
0x180027eca  mov     rdx, [rdi+38h]
0x180027ece  mov     ecx, 10010h
0x180027ed3  call    cs:__imp_DnsQueryConfigDword
0x180027eda  nop     dword ptr [rax+rax+00h]
0x180027edf  test    eax, eax
0x180027ee1  jz      short loc_180027EF1
0x180027ee3  mov     eax, ebx
0x180027ee5  mov     ecx, 27h ; '''
0x180027eea  inc     ebx
0x180027eec  mov     word ptr [rsp+rax*2+170h+var_120], cx
0x180027ef1  cmp     cs:dword_180042678, 0
0x180027ef8  jz      short loc_180027F08
0x180027efa  mov     eax, ebx
0x180027efc  mov     ecx, 90h
0x180027f01  inc     ebx
0x180027f03  mov     word ptr [rsp+rax*2+170h+var_120], cx
0x180027f08  mov     r10, [r14]
0x180027f0b  jmp     short loc_180027F73
0x180027f0d  lea     rdx, [r10]
0x180027f10  mov     r10, [r10]
0x180027f13  cmp     dword ptr [rdx+14h], 0
0x180027f17  jnz     short loc_180027F73
0x180027f19  cmp     dword ptr [rdx+20h], 0
0x180027f1d  jz      short loc_180027F2B
0x180027f1f  cmp     [rdx+20h], r12d
0x180027f23  jnz     short loc_180027F73
0x180027f25  cmp     [rdx+18h], r15
0x180027f29  jnz     short loc_180027F73
0x180027f2b  cmp     si, [rdx+10h]
0x180027f2f  jnz     short loc_180027F73
0x180027f31  xor     r9d, r9d
0x180027f34  cmp     [rdx+38h], r9d
0x180027f38  jbe     short loc_180027F73
0x180027f3a  cmp     ebx, 64h ; 'd'
0x180027f3d  jnb     short loc_180027F73
0x180027f3f  mov     r11, [rdx+30h]
0x180027f43  test    ebx, ebx
0x180027f45  jz      short loc_180027F5B
0x180027f47  movzx   edi, word ptr [r11+r9]
0x180027f4c  xor     ecx, ecx
0x180027f4e  cmp     di, word ptr [rsp+rcx*2+170h+var_120]
0x180027f53  jz      short loc_180027F69
0x180027f55  inc     ecx
0x180027f57  cmp     ecx, ebx
0x180027f59  jb      short loc_180027F4E
0x180027f5b  movzx   eax, word ptr [r11+r9]
0x180027f60  mov     ecx, ebx
0x180027f62  inc     ebx
0x180027f64  mov     word ptr [rsp+rcx*2+170h+var_120], ax
0x180027f69  add     r9d, 2
0x180027f6d  cmp     r9d, [rdx+38h]
0x180027f71  jb      short loc_180027F3A
0x180027f73  cmp     r10, r14
0x180027f76  jnz     short loc_180027F0D
0x180027f78  mov     r9, [rsp+170h+var_138]
0x180027f7d  lea     rax, [rsp+170h+var_120]
0x180027f82  mov     [rsp+170h+Src], rax
0x180027f87  lea     rcx, [rsp+170h+Src]; Src
0x180027f8c  mov     rax, [rsp+170h+var_140]
0x180027f91  mov     r8d, esi
0x180027f94  mov     [rsp+170h+var_148], rax; __int64
0x180027f99  mov     edx, 0Ch
0x180027f9e  mov     [rsp+170h+var_150], r13; __int64
0x180027fa3  mov     [rsp+170h+var_128], ebx
0x180027fa7  call    Dhcpv6AppendOption
0x180027fac  mov     ebx, eax
0x180027fae  test    eax, eax
0x180027fb0  jz      short loc_180027FD4
0x180027fb2  test    byte ptr cs:xmmword_1800423E0, 2
0x180027fb9  jz      short loc_180027FD4
0x180027fbb  mov     edx, 21h ; '!'
0x180027fc0  lea     r8, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids
0x180027fc7  mov     ecx, 401h
0x180027fcc  mov     r9d, eax
0x180027fcf  call    WPP_SF_D
0x180027fd4  mov     eax, ebx
0x180027fd6  mov     rcx, [rbp+70h+var_50]
0x180027fda  xor     rcx, rsp; StackCookie
0x180027fdd  call    __security_check_cookie
0x180027fe2  add     rsp, 138h
0x180027fe9  pop     r15
0x180027feb  pop     r14
0x180027fed  pop     r13
0x180027fef  pop     r12
0x180027ff1  pop     rdi
0x180027ff2  pop     rsi
0x180027ff3  pop     rbx
0x180027ff4  pop     rbp
0x180027ff5  retn
```
