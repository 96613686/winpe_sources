# CMap<CString,ushort const *,RefCountedPointer<RefCountedVariant>,RefCountedVariant *>::GrowHashTable(void)

- ea: `0x18003fc94`
- end: `0x18003fd41`
- name: `?GrowHashTable@?$CMap@VCString@@PEBGV?$RefCountedPointer@URefCountedVariant@@@@PEAURefCountedVariant@@@@IEAAXXZ`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d38c`

## callees

- `0x1800097ac`
- `0x180010210`
- `0x18003fc94`
- `0x1800434c6`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fcc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fcc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fd2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fd2c`

## pseudocode

```c
void __fastcall CMap<CString,unsigned short const *,RefCountedPointer<RefCountedVariant>,RefCountedVariant *>::GrowHashTable(
        __int64 a1)
{
  unsigned __int64 v2; // rsi
  _QWORD *v3; // rax
  _QWORD *v4; // rdi
  __int64 i; // r9
  __int64 v6; // r8
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  _QWORD *v10; // rcx

  v2 = (unsigned int)CMap<CString,unsigned short const *,RegRow *,RegRow *>::RoundUpToPrime(
                       a1,
                       (unsigned int)(2 * *(_DWORD *)(a1 + 8)));
  v3 = CoTaskMemAlloc(saturated_mul(v2, 8u));
  v4 = v3;
  if ( v3 )
  {
    memset_0(v3, 0, 8 * v2);
    for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 8); i = (unsigned int)(i + 1) )
    {
      while ( 1 )
      {
        v10 = *(_QWORD **)a1;
        if ( !*(_QWORD *)(*(_QWORD *)a1 + 8 * i) )
          break;
        v6 = v10[i];
        v10[i] = *(_QWORD *)v6;
        v7 = HashKey<unsigned short const *>(*(unsigned __int16 **)(v6 + 16));
        v8 = v7 % (unsigned int)v2;
        *(_DWORD *)(v9 + 8) = v7 % (unsigned int)v2;
        *(_QWORD *)v9 = v4[v8];
        v4[(unsigned int)v8] = v9;
      }
    }
    CoTaskMemFree(*(LPVOID *)a1);
    *(_QWORD *)a1 = v4;
    *(_DWORD *)(a1 + 8) = v2;
  }
}

```

## disassembly

```asm
0x18003fc94  push    rbx
0x18003fc96  push    rbp
0x18003fc97  push    rsi
0x18003fc98  push    rdi
0x18003fc99  sub     rsp, 28h
0x18003fc9d  mov     edx, [rcx+8]
0x18003fca0  mov     rbx, rcx
0x18003fca3  add     edx, edx
0x18003fca5  call    ?RoundUpToPrime@?$CMap@VCString@@PEBGPEAVRegRow@@PEAV2@@@IEBAII@Z; CMap<CString,ushort const *,RegRow *,RegRow *>::RoundUpToPrime(uint)
0x18003fcaa  mov     esi, eax
0x18003fcac  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003fcb3  mov     eax, 8
0x18003fcb8  mul     rsi
0x18003fcbb  cmovb   rax, rcx
0x18003fcbf  mov     rcx, rax; cb
0x18003fcc2  call    cs:__imp_CoTaskMemAlloc
0x18003fcc8  mov     rdi, rax
0x18003fccb  test    rax, rax
0x18003fcce  jz      short loc_18003FD38
0x18003fcd0  lea     r8, ds:0[rsi*8]; Size
0x18003fcd8  xor     edx, edx; Val
0x18003fcda  mov     rcx, rax; void *
0x18003fcdd  call    memset_0
0x18003fce2  xor     r9d, r9d
0x18003fce5  cmp     [rbx+8], r9d
0x18003fce9  jbe     short loc_18003FD29
0x18003fceb  jmp     short loc_18003FD16
0x18003fced  mov     r8, [rcx+r9*8]
0x18003fcf1  mov     rax, [r8]
0x18003fcf4  mov     [rcx+r9*8], rax
0x18003fcf8  mov     rcx, [r8+10h]
0x18003fcfc  call    ??$HashKey@PEBG@@YAIPEBG@Z; HashKey<ushort const *>(ushort const *)
0x18003fd01  xor     edx, edx
0x18003fd03  div     esi
0x18003fd05  mov     ecx, edx
0x18003fd07  mov     [r8+8], ecx
0x18003fd0b  mov     rax, [rdi+rdx*8]
0x18003fd0f  mov     [r8], rax
0x18003fd12  mov     [rdi+rdx*8], r8
0x18003fd16  mov     rcx, [rbx]
0x18003fd19  cmp     qword ptr [rcx+r9*8], 0
0x18003fd1e  jnz     short loc_18003FCED
0x18003fd20  inc     r9d
0x18003fd23  cmp     r9d, [rbx+8]
0x18003fd27  jb      short loc_18003FD16
0x18003fd29  mov     rcx, [rbx]; pv
0x18003fd2c  call    cs:__imp_CoTaskMemFree
0x18003fd32  mov     [rbx], rdi
0x18003fd35  mov     [rbx+8], esi
0x18003fd38  add     rsp, 28h
0x18003fd3c  pop     rdi
0x18003fd3d  pop     rsi
0x18003fd3e  pop     rbp
0x18003fd3f  pop     rbx
0x18003fd40  retn
```
