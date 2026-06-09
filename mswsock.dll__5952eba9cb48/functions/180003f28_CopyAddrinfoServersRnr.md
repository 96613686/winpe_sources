# CopyAddrinfoServersRnr

- ea: `0x180003f28`
- end: `0x1800040e4`
- name: `CopyAddrinfoServersRnr`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180003ce0`

## callees

- `0x180003f28`
- `0x180018990`
- `0x180029a14`
- `0x18002a98c`
- `0x180037195`

## import_xrefs

- `DNSAPI!DnsApiFree` at `0x1800040c0`
- `DNSAPI!DnsApiFree` at `0x1800040c0`
- `DNSAPI!DnsApiAllocZero` at `0x180003fa9`
- `DNSAPI!DnsApiAllocZero` at `0x180004046`
- `DNSAPI!DnsApiAllocZero` at `0x180003fa9`
- `DNSAPI!DnsApiAllocZero` at `0x180004046`
- `DNSAPI!DnsStringCopyAllocateEx` at `0x180004029`
- `DNSAPI!DnsStringCopyAllocateEx` at `0x180004029`

## pseudocode

```c
__int64 __fastcall CopyAddrinfoServersRnr(unsigned int a1, __int64 a2, unsigned int *a3, __int64 *a4)
{
  unsigned int v8; // ebx
  __int64 v9; // r15
  __int64 v10; // rax
  __int64 v11; // rdi
  int v12; // eax
  void *v13; // rcx
  __int64 v14; // rax
  void *v15; // rax
  void *v16; // r13
  unsigned int v18; // [rsp+60h] [rbp+8h] BYREF
  int v19; // [rsp+68h] [rbp+10h]
  __int64 v20; // [rsp+70h] [rbp+18h] BYREF

  v18 = a1;
  v20 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a3 )
    *a3 = 0;
  if ( (a1 == 0) == (a2 == 0) && a4 && a3 )
  {
    v8 = 0;
    if ( a1 )
    {
      v20 = DnsApiAllocZero(40 * a1);
      v9 = v20;
      if ( v20 )
      {
        v10 = 0;
        v19 = 0;
        while ( 1 )
        {
          v11 = 5 * v10;
          *(_DWORD *)(v9 + 40 * v10) = *(_DWORD *)(a2 + 40 * v10);
          if ( *(_DWORD *)(a2 + 40 * v10) == 2 || *(_DWORD *)(a2 + 40 * v10) == 3 )
          {
            if ( *(_QWORD *)(a2 + 40 * v10 + 32) )
            {
              v12 = (Feature_5977_1413__private_featureState & 0x10) != 0
                  ? Feature_5977_1413__private_featureState & 1
                  : Feature_5977_1413__private_IsEnabledDeviceUsageNoInline();
              v13 = *(void **)(a2 + 8 * v11 + 32);
              v14 = v12 ? SaBlob_StringCopyAllocW(v13) : DnsStringCopyAllocateEx(v13, 0, 1);
              *(_QWORD *)(v9 + 8 * v11 + 32) = v14;
              if ( !v14 )
                break;
            }
          }
          v15 = (void *)DnsApiAllocZero(*(unsigned int *)(a2 + 8 * v11 + 16));
          v16 = v15;
          if ( !v15 )
            break;
          memcpy_0(v15, *(const void **)(a2 + 8 * v11 + 24), *(unsigned int *)(a2 + 8 * v11 + 16));
          *(_QWORD *)(v9 + 8 * v11 + 24) = v16;
          *(_DWORD *)(v9 + 8 * v11 + 16) = *(_DWORD *)(a2 + 8 * v11 + 16);
          *(_QWORD *)(v9 + 8 * v11 + 8) = *(_QWORD *)(a2 + 8 * v11 + 8);
          v10 = (unsigned int)(v19 + 1);
          v19 = v10;
          if ( (unsigned int)v10 >= a1 )
          {
            *a4 = v9;
            v20 = 0;
            *a3 = a1;
            goto LABEL_26;
          }
        }
      }
      v8 = 8;
    }
  }
  else
  {
    v8 = 10022;
  }
LABEL_26:
  FreeAddrinfoServersRnr(&v18, &v20);
  DnsApiFree(0);
  return v8;
}

```

## disassembly

```asm
0x180003f28  mov     [rsp+arg_18], rbx
0x180003f2d  mov     [rsp+arg_0], ecx
0x180003f31  push    rbp
0x180003f32  push    rsi
0x180003f33  push    rdi
0x180003f34  push    r12
0x180003f36  push    r13
0x180003f38  push    r14
0x180003f3a  push    r15
0x180003f3c  sub     rsp, 20h
0x180003f40  mov     [rsp+58h+arg_10], 0
0x180003f49  mov     r12, r9
0x180003f4c  mov     rbp, r8
0x180003f4f  mov     rsi, rdx
0x180003f52  mov     r14d, ecx
0x180003f55  test    r9, r9
0x180003f58  jz      short loc_180003F61
0x180003f5a  mov     qword ptr [r9], 0
0x180003f61  test    rbp, rbp
0x180003f64  jz      short loc_180003F6D
0x180003f66  mov     dword ptr [r8], 0
0x180003f6d  xor     ecx, ecx
0x180003f6f  test    r14d, r14d
0x180003f72  setz    cl
0x180003f75  xor     eax, eax
0x180003f77  test    rsi, rsi
0x180003f7a  setz    al
0x180003f7d  cmp     ecx, eax
0x180003f7f  jnz     loc_1800040AA
0x180003f85  test    r12, r12
0x180003f88  jz      loc_1800040AA
0x180003f8e  test    rbp, rbp
0x180003f91  jz      loc_1800040AA
0x180003f97  xor     ebx, ebx
0x180003f99  test    r14d, r14d
0x180003f9c  jz      loc_1800040AF
0x180003fa2  lea     ecx, [r14+r14*4]
0x180003fa6  shl     ecx, 3
0x180003fa9  call    cs:__imp_DnsApiAllocZero
0x180003fb0  nop     dword ptr [rax+rax+00h]
0x180003fb5  mov     [rsp+58h+arg_10], rax
0x180003fba  mov     r15, rax
0x180003fbd  test    rax, rax
0x180003fc0  jnz     short loc_180003FCC
0x180003fc2  mov     ebx, 8
0x180003fc7  jmp     loc_1800040AF
0x180003fcc  xor     eax, eax
0x180003fce  mov     [rsp+58h+arg_8], eax
0x180003fd2  test    r14d, r14d
0x180003fd5  jz      loc_18000409B
0x180003fdb  lea     rdi, [rax+rax*4]
0x180003fdf  mov     eax, [rsi+rdi*8]
0x180003fe2  mov     [r15+rdi*8], eax
0x180003fe6  mov     ecx, [rsi+rdi*8]
0x180003fe9  sub     ecx, 2
0x180003fec  jz      short loc_180003FF3
0x180003fee  cmp     ecx, 1
0x180003ff1  jnz     short loc_180004042
0x180003ff3  cmp     [rsi+rdi*8+20h], rbx
0x180003ff8  jz      short loc_180004042
0x180003ffa  mov     eax, cs:Feature_5977_1413__private_featureState
0x180004000  test    al, 10h
0x180004002  jz      short loc_180004009
0x180004004  and     eax, 1
0x180004007  jmp     short loc_18000400E
0x180004009  call    Feature_5977_1413__private_IsEnabledDeviceUsageNoInline
0x18000400e  mov     rcx, [rsi+rdi*8+20h]; Src
0x180004013  test    eax, eax
0x180004015  jz      short loc_18000401E
0x180004017  call    SaBlob_StringCopyAllocW
0x18000401c  jmp     short loc_180004035
0x18000401e  mov     r9d, 1
0x180004024  xor     edx, edx
0x180004026  mov     r8d, r9d
0x180004029  call    cs:__imp_DnsStringCopyAllocateEx
0x180004030  nop     dword ptr [rax+rax+00h]
0x180004035  mov     [r15+rdi*8+20h], rax
0x18000403a  mov     rcx, rax
0x18000403d  test    rax, rax
0x180004040  jz      short loc_180003FC2
0x180004042  mov     ecx, [rsi+rdi*8+10h]
0x180004046  call    cs:__imp_DnsApiAllocZero
0x18000404d  nop     dword ptr [rax+rax+00h]
0x180004052  mov     r13, rax
0x180004055  test    rax, rax
0x180004058  jz      loc_180003FC2
0x18000405e  mov     r8d, [rsi+rdi*8+10h]; Size
0x180004063  mov     rcx, rax; void *
0x180004066  mov     rdx, [rsi+rdi*8+18h]; Src
0x18000406b  call    memcpy_0
0x180004070  mov     [r15+rdi*8+18h], r13
0x180004075  mov     eax, [rsi+rdi*8+10h]
0x180004079  mov     [r15+rdi*8+10h], eax
0x18000407e  mov     rax, [rsi+rdi*8+8]
0x180004083  mov     [r15+rdi*8+8], rax
0x180004088  mov     eax, [rsp+58h+arg_8]
0x18000408c  inc     eax
0x18000408e  mov     [rsp+58h+arg_8], eax
0x180004092  cmp     eax, r14d
0x180004095  jb      loc_180003FDB
0x18000409b  mov     [r12], r15
0x18000409f  mov     [rsp+58h+arg_10], rbx
0x1800040a4  mov     [rbp+0], r14d
0x1800040a8  jmp     short loc_1800040AF
0x1800040aa  mov     ebx, 2726h
0x1800040af  lea     rdx, [rsp+58h+arg_10]
0x1800040b4  lea     rcx, [rsp+58h+arg_0]
0x1800040b9  call    FreeAddrinfoServersRnr
0x1800040be  xor     ecx, ecx
0x1800040c0  call    cs:__imp_DnsApiFree
0x1800040c7  nop     dword ptr [rax+rax+00h]
0x1800040cc  mov     eax, ebx
0x1800040ce  mov     rbx, [rsp+58h+arg_18]
0x1800040d3  add     rsp, 20h
0x1800040d7  pop     r15
0x1800040d9  pop     r14
0x1800040db  pop     r13
0x1800040dd  pop     r12
0x1800040df  pop     rdi
0x1800040e0  pop     rsi
0x1800040e1  pop     rbp
0x1800040e2  retn
```
