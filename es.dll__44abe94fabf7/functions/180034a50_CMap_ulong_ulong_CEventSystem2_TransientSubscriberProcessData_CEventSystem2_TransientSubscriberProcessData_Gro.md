# CMap<ulong,ulong,CEventSystem2::TransientSubscriberProcessData *,CEventSystem2::TransientSubscriberProcessData *>::GrowHashTable(void)

- ea: `0x180034a50`
- end: `0x180034afb`
- name: `?GrowHashTable@?$CMap@KKPEAUTransientSubscriberProcessData@CEventSystem2@@PEAU12@@@IEAAXXZ`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b214`

## callees

- `0x1800097ac`
- `0x180034a50`
- `0x1800434c6`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034a7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034a7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034ae6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034ae6`

## pseudocode

```c
void __fastcall CMap<unsigned long,unsigned long,CEventSystem2::TransientSubscriberProcessData *,CEventSystem2::TransientSubscriberProcessData *>::GrowHashTable(
        __int64 a1)
{
  unsigned __int64 v2; // rsi
  _QWORD *v3; // rax
  _QWORD *v4; // rdi
  __int64 i; // r9
  __int64 v6; // r8
  __int64 v7; // rdx
  _QWORD *v8; // rcx

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
        v8 = *(_QWORD **)a1;
        if ( !*(_QWORD *)(*(_QWORD *)a1 + 8 * i) )
          break;
        v6 = v8[i];
        v8[i] = *(_QWORD *)v6;
        v7 = (*(_DWORD *)(v6 + 12) >> 4) % (unsigned int)v2;
        *(_DWORD *)(v6 + 8) = (*(_DWORD *)(v6 + 12) >> 4) % (unsigned int)v2;
        *(_QWORD *)v6 = v4[v7];
        v4[v7] = v6;
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
0x180034a50  push    rbx
0x180034a52  push    rbp
0x180034a53  push    rsi
0x180034a54  push    rdi
0x180034a55  sub     rsp, 28h
0x180034a59  mov     edx, [rcx+8]
0x180034a5c  mov     rbx, rcx
0x180034a5f  add     edx, edx
0x180034a61  call    ?RoundUpToPrime@?$CMap@VCString@@PEBGPEAVRegRow@@PEAV2@@@IEBAII@Z; CMap<CString,ushort const *,RegRow *,RegRow *>::RoundUpToPrime(uint)
0x180034a66  mov     esi, eax
0x180034a68  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180034a6f  mov     eax, 8
0x180034a74  mul     rsi
0x180034a77  cmovb   rax, rcx
0x180034a7b  mov     rcx, rax; cb
0x180034a7e  call    cs:__imp_CoTaskMemAlloc
0x180034a84  mov     rdi, rax
0x180034a87  test    rax, rax
0x180034a8a  jz      short loc_180034AF2
0x180034a8c  lea     r8, ds:0[rsi*8]; Size
0x180034a94  xor     edx, edx; Val
0x180034a96  mov     rcx, rax; void *
0x180034a99  call    memset_0
0x180034a9e  xor     r9d, r9d
0x180034aa1  cmp     [rbx+8], r9d
0x180034aa5  jbe     short loc_180034AE3
0x180034aa7  jmp     short loc_180034AD0
0x180034aa9  mov     r8, [rcx+r9*8]
0x180034aad  xor     edx, edx
0x180034aaf  mov     rax, [r8]
0x180034ab2  mov     [rcx+r9*8], rax
0x180034ab6  mov     eax, [r8+0Ch]
0x180034aba  shr     eax, 4
0x180034abd  div     esi
0x180034abf  mov     ecx, edx
0x180034ac1  mov     [r8+8], ecx
0x180034ac5  mov     rax, [rdi+rdx*8]
0x180034ac9  mov     [r8], rax
0x180034acc  mov     [rdi+rdx*8], r8
0x180034ad0  mov     rcx, [rbx]
0x180034ad3  cmp     qword ptr [rcx+r9*8], 0
0x180034ad8  jnz     short loc_180034AA9
0x180034ada  inc     r9d
0x180034add  cmp     r9d, [rbx+8]
0x180034ae1  jb      short loc_180034AD0
0x180034ae3  mov     rcx, [rbx]; pv
0x180034ae6  call    cs:__imp_CoTaskMemFree
0x180034aec  mov     [rbx], rdi
0x180034aef  mov     [rbx+8], esi
0x180034af2  add     rsp, 28h
0x180034af6  pop     rdi
0x180034af7  pop     rsi
0x180034af8  pop     rbp
0x180034af9  pop     rbx
0x180034afa  retn
```
