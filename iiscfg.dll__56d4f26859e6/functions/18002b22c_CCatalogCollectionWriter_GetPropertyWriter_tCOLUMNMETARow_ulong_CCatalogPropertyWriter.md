# CCatalogCollectionWriter::GetPropertyWriter(tCOLUMNMETARow *,ulong *,CCatalogPropertyWriter * *)

- ea: `0x18002b22c`
- end: `0x18002b3a2`
- name: `?GetPropertyWriter@CCatalogCollectionWriter@@QEAAJPEAUtCOLUMNMETARow@@PEAKPEAPEAVCCatalogPropertyWriter@@@Z`
- size: `374`
- prototype: `__int64 __fastcall(CCatalogCollectionWriter *__hidden this, struct tCOLUMNMETARow *, unsigned int *, struct CCatalogPropertyWriter **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180023e00`

## callees

- `0x18002b22c`
- `0x18002b3a8`
- `0x18002e0ca`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18002b263`
- `ole32!CoTaskMemAlloc` at `0x18002b263`

## pseudocode

```c
__int64 __fastcall CCatalogCollectionWriter::GetPropertyWriter(
        CCatalogCollectionWriter *this,
        struct tCOLUMNMETARow *a2,
        unsigned int *a3,
        struct CCatalogPropertyWriter **a4)
{
  __int64 result; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rdx

  if ( *((_DWORD *)this + 39) != *((_DWORD *)this + 38)
    || (result = CCatalogCollectionWriter::ReAllocate(this), (int)result >= 0) )
  {
    v9 = CoTaskMemAlloc(0xF8u);
    v10 = v9;
    if ( v9 )
    {
      *v9 = 0;
      v9[28] = 0;
      v9[29] = 0;
      v9[30] = 0;
      memset_0(v9 + 1, 0, 0x90u);
    }
    else
    {
      v10 = 0;
    }
    *(_QWORD *)(*((_QWORD *)this + 18) + 8LL * *((unsigned int *)this + 39)) = v10;
    v11 = *((unsigned int *)this + 39);
    *((_DWORD *)this + 39) = v11 + 1;
    v12 = *(_QWORD *)(*((_QWORD *)this + 18) + 8 * v11);
    if ( v12 )
    {
      *(_QWORD *)v12 = *(_QWORD *)this;
      *(_QWORD *)(v12 + 224) = (char *)this + 8;
      *(_OWORD *)(v12 + 8) = *(_OWORD *)a2;
      *(_OWORD *)(v12 + 24) = *((_OWORD *)a2 + 1);
      *(_OWORD *)(v12 + 40) = *((_OWORD *)a2 + 2);
      *(_OWORD *)(v12 + 56) = *((_OWORD *)a2 + 3);
      *(_OWORD *)(v12 + 72) = *((_OWORD *)a2 + 4);
      *(_OWORD *)(v12 + 88) = *((_OWORD *)a2 + 5);
      *(_OWORD *)(v12 + 104) = *((_OWORD *)a2 + 6);
      *(_OWORD *)(v12 + 120) = *((_OWORD *)a2 + 7);
      *(_OWORD *)(v12 + 136) = *((_OWORD *)a2 + 8);
      *(_OWORD *)(v12 + 152) = *(_OWORD *)a3;
      *(_OWORD *)(v12 + 168) = *((_OWORD *)a3 + 1);
      *(_OWORD *)(v12 + 184) = *((_OWORD *)a3 + 2);
      *(_OWORD *)(v12 + 200) = *((_OWORD *)a3 + 3);
      *(_QWORD *)(v12 + 216) = *((_QWORD *)a3 + 8);
      result = 0;
      *a4 = *(struct CCatalogPropertyWriter **)(*((_QWORD *)this + 18) + 8LL
                                                                       * (unsigned int)(*((_DWORD *)this + 39) - 1));
    }
    else
    {
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002b22c  push    rbx
0x18002b22e  push    rbp
0x18002b22f  push    rsi
0x18002b230  push    rdi
0x18002b231  push    r14
0x18002b233  sub     rsp, 20h
0x18002b237  mov     eax, [rcx+98h]
0x18002b23d  mov     r14, r9
0x18002b240  mov     rbp, r8
0x18002b243  mov     rsi, rdx
0x18002b246  mov     rdi, rcx
0x18002b249  cmp     [rcx+9Ch], eax
0x18002b24f  jnz     short loc_18002B25E
0x18002b251  call    ?ReAllocate@CCatalogCollectionWriter@@AEAAJXZ; CCatalogCollectionWriter::ReAllocate(void)
0x18002b256  test    eax, eax
0x18002b258  js      loc_18002B397
0x18002b25e  mov     ecx, 0F8h; cb
0x18002b263  call    cs:__imp_CoTaskMemAlloc
0x18002b269  mov     rbx, rax
0x18002b26c  test    rax, rax
0x18002b26f  jz      short loc_18002B2AC
0x18002b271  lea     rcx, [rax+8]; void *
0x18002b275  mov     qword ptr [rax], 0
0x18002b27c  xor     edx, edx; Val
0x18002b27e  mov     qword ptr [rax+0E0h], 0
0x18002b289  mov     r8d, 90h; Size
0x18002b28f  mov     qword ptr [rax+0E8h], 0
0x18002b29a  mov     qword ptr [rax+0F0h], 0
0x18002b2a5  call    memset_0
0x18002b2aa  jmp     short loc_18002B2AE
0x18002b2ac  xor     ebx, ebx
0x18002b2ae  mov     ecx, [rdi+9Ch]
0x18002b2b4  mov     rax, [rdi+90h]
0x18002b2bb  mov     [rax+rcx*8], rbx
0x18002b2bf  mov     ecx, [rdi+9Ch]
0x18002b2c5  lea     eax, [rcx+1]
0x18002b2c8  mov     [rdi+9Ch], eax
0x18002b2ce  mov     rax, [rdi+90h]
0x18002b2d5  mov     rdx, [rax+rcx*8]
0x18002b2d9  test    rdx, rdx
0x18002b2dc  jnz     short loc_18002B2E8
0x18002b2de  mov     eax, 8007000Eh
0x18002b2e3  jmp     loc_18002B397
0x18002b2e8  mov     rax, [rdi]
0x18002b2eb  mov     [rdx], rax
0x18002b2ee  lea     rax, [rdi+8]
0x18002b2f2  mov     [rdx+0E0h], rax
0x18002b2f9  movups  xmm0, xmmword ptr [rsi]
0x18002b2fc  movups  xmmword ptr [rdx+8], xmm0
0x18002b300  movups  xmm1, xmmword ptr [rsi+10h]
0x18002b304  movups  xmmword ptr [rdx+18h], xmm1
0x18002b308  movups  xmm0, xmmword ptr [rsi+20h]
0x18002b30c  movups  xmmword ptr [rdx+28h], xmm0
0x18002b310  movups  xmm1, xmmword ptr [rsi+30h]
0x18002b314  movups  xmmword ptr [rdx+38h], xmm1
0x18002b318  movups  xmm0, xmmword ptr [rsi+40h]
0x18002b31c  movups  xmmword ptr [rdx+48h], xmm0
0x18002b320  movups  xmm1, xmmword ptr [rsi+50h]
0x18002b324  movups  xmmword ptr [rdx+58h], xmm1
0x18002b328  movups  xmm0, xmmword ptr [rsi+60h]
0x18002b32c  movups  xmmword ptr [rdx+68h], xmm0
0x18002b330  movups  xmm1, xmmword ptr [rsi+70h]
0x18002b334  movups  xmmword ptr [rdx+78h], xmm1
0x18002b338  movups  xmm0, xmmword ptr [rsi+80h]
0x18002b33f  movups  xmmword ptr [rdx+88h], xmm0
0x18002b346  movups  xmm0, xmmword ptr [rbp+0]
0x18002b34a  movups  xmmword ptr [rdx+98h], xmm0
0x18002b351  movups  xmm1, xmmword ptr [rbp+10h]
0x18002b355  movups  xmmword ptr [rdx+0A8h], xmm1
0x18002b35c  movups  xmm0, xmmword ptr [rbp+20h]
0x18002b360  movups  xmmword ptr [rdx+0B8h], xmm0
0x18002b367  movups  xmm1, xmmword ptr [rbp+30h]
0x18002b36b  movups  xmmword ptr [rdx+0C8h], xmm1
0x18002b372  movsd   xmm0, qword ptr [rbp+40h]
0x18002b377  movsd   qword ptr [rdx+0D8h], xmm0
0x18002b37f  mov     ecx, [rdi+9Ch]
0x18002b385  mov     rax, [rdi+90h]
0x18002b38c  dec     ecx
0x18002b38e  mov     rcx, [rax+rcx*8]
0x18002b392  xor     eax, eax
0x18002b394  mov     [r14], rcx
0x18002b397  add     rsp, 20h
0x18002b39b  pop     r14
0x18002b39d  pop     rdi
0x18002b39e  pop     rsi
0x18002b39f  pop     rbp
0x18002b3a0  pop     rbx
0x18002b3a1  retn
```
