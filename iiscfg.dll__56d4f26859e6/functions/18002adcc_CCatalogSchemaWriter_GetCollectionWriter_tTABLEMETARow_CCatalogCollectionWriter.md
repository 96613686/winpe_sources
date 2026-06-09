# CCatalogSchemaWriter::GetCollectionWriter(tTABLEMETARow *,CCatalogCollectionWriter * *)

- ea: `0x18002adcc`
- end: `0x18002aeb7`
- name: `?GetCollectionWriter@CCatalogSchemaWriter@@QEAAJPEAUtTABLEMETARow@@PEAPEAVCCatalogCollectionWriter@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(CCatalogSchemaWriter *__hidden this, struct tTABLEMETARow *, struct CCatalogCollectionWriter **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180023e00`

## callees

- `0x18002adcc`
- `0x18002aec0`
- `0x18002e0ca`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18002ae00`
- `ole32!CoTaskMemAlloc` at `0x18002ae00`

## pseudocode

```c
__int64 __fastcall CCatalogSchemaWriter::GetCollectionWriter(
        CCatalogSchemaWriter *this,
        struct tTABLEMETARow *a2,
        struct CCatalogCollectionWriter **a3)
{
  __int64 result; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  __int64 v9; // rcx

  *a3 = 0;
  if ( *((_DWORD *)this + 3) != *((_DWORD *)this + 2)
    || (result = CCatalogSchemaWriter::ReAllocate(this), (int)result >= 0) )
  {
    v7 = CoTaskMemAlloc(0xA0u);
    v8 = v7;
    if ( v7 )
    {
      *v7 = 0;
      v7[18] = 0;
      v7[19] = 0;
      memset_0(v7 + 1, 0, 0x88u);
      v9 = *((_QWORD *)this + 2);
      *(_OWORD *)(v8 + 1) = *(_OWORD *)a2;
      *(_OWORD *)(v8 + 3) = *((_OWORD *)a2 + 1);
      *(_OWORD *)(v8 + 5) = *((_OWORD *)a2 + 2);
      *(_OWORD *)(v8 + 7) = *((_OWORD *)a2 + 3);
      *(_OWORD *)(v8 + 9) = *((_OWORD *)a2 + 4);
      *(_OWORD *)(v8 + 11) = *((_OWORD *)a2 + 5);
      *(_OWORD *)(v8 + 13) = *((_OWORD *)a2 + 6);
      *(_OWORD *)(v8 + 15) = *((_OWORD *)a2 + 7);
      v8[17] = *((_QWORD *)a2 + 16);
      *v8 = v9;
      *(_QWORD *)(*(_QWORD *)this + 8LL * (unsigned int)(*((_DWORD *)this + 3))++) = v8;
      result = 0;
      *a3 = (struct CCatalogCollectionWriter *)v8;
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
0x18002adcc  push    rbx
0x18002adce  push    rsi
0x18002adcf  push    rdi
0x18002add0  push    r14
0x18002add2  sub     rsp, 28h
0x18002add6  mov     qword ptr [r8], 0
0x18002addd  mov     r14, r8
0x18002ade0  mov     eax, [rcx+8]
0x18002ade3  mov     rsi, rdx
0x18002ade6  mov     rdi, rcx
0x18002ade9  cmp     [rcx+0Ch], eax
0x18002adec  jnz     short loc_18002ADFB
0x18002adee  call    ?ReAllocate@CCatalogSchemaWriter@@AEAAJXZ; CCatalogSchemaWriter::ReAllocate(void)
0x18002adf3  test    eax, eax
0x18002adf5  js      loc_18002AEAD
0x18002adfb  mov     ecx, 0A0h; cb
0x18002ae00  call    cs:__imp_CoTaskMemAlloc
0x18002ae06  mov     rbx, rax
0x18002ae09  test    rax, rax
0x18002ae0c  jz      loc_18002AEA8
0x18002ae12  lea     rcx, [rax+8]; void *
0x18002ae16  mov     qword ptr [rax], 0
0x18002ae1d  xor     edx, edx; Val
0x18002ae1f  mov     qword ptr [rax+90h], 0
0x18002ae2a  mov     r8d, 88h; Size
0x18002ae30  mov     qword ptr [rax+98h], 0
0x18002ae3b  call    memset_0
0x18002ae40  movups  xmm0, xmmword ptr [rsi]
0x18002ae43  mov     rcx, [rdi+10h]
0x18002ae47  movups  xmmword ptr [rbx+8], xmm0
0x18002ae4b  movups  xmm1, xmmword ptr [rsi+10h]
0x18002ae4f  movups  xmmword ptr [rbx+18h], xmm1
0x18002ae53  movups  xmm0, xmmword ptr [rsi+20h]
0x18002ae57  movups  xmmword ptr [rbx+28h], xmm0
0x18002ae5b  movups  xmm1, xmmword ptr [rsi+30h]
0x18002ae5f  movups  xmmword ptr [rbx+38h], xmm1
0x18002ae63  movups  xmm0, xmmword ptr [rsi+40h]
0x18002ae67  movups  xmmword ptr [rbx+48h], xmm0
0x18002ae6b  movups  xmm1, xmmword ptr [rsi+50h]
0x18002ae6f  movups  xmmword ptr [rbx+58h], xmm1
0x18002ae73  movups  xmm0, xmmword ptr [rsi+60h]
0x18002ae77  movups  xmmword ptr [rbx+68h], xmm0
0x18002ae7b  movups  xmm1, xmmword ptr [rsi+70h]
0x18002ae7f  movups  xmmword ptr [rbx+78h], xmm1
0x18002ae83  mov     rax, [rsi+80h]
0x18002ae8a  mov     [rbx+88h], rax
0x18002ae91  mov     [rbx], rcx
0x18002ae94  mov     ecx, [rdi+0Ch]
0x18002ae97  mov     rax, [rdi]
0x18002ae9a  mov     [rax+rcx*8], rbx
0x18002ae9e  inc     dword ptr [rdi+0Ch]
0x18002aea1  xor     eax, eax
0x18002aea3  mov     [r14], rbx
0x18002aea6  jmp     short loc_18002AEAD
0x18002aea8  mov     eax, 8007000Eh
0x18002aead  add     rsp, 28h
0x18002aeb1  pop     r14
0x18002aeb3  pop     rdi
0x18002aeb4  pop     rsi
0x18002aeb5  pop     rbx
0x18002aeb6  retn
```
