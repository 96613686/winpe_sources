# Map<ushort *,InMemoryRegRow::MapPropertyBag *,InMemoryRegRow::HashCaseInsentitiveWSTR,InMemoryRegRow::CNonFailFastingAllocator>::grow(void)

- ea: `0x18003c000`
- end: `0x18003c0bd`
- name: `?grow@?$Map@PEAGPEAUMapPropertyBag@InMemoryRegRow@@VHashCaseInsentitiveWSTR@2@VCNonFailFastingAllocator@2@@@AEAAJXZ`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180017e18`

## callees

- `0x180017ba0`
- `0x18003c000`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c030`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c030`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c048`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c048`

## pseudocode

```c
__int64 __fastcall Map<unsigned short *,InMemoryRegRow::MapPropertyBag *,InMemoryRegRow::HashCaseInsentitiveWSTR,InMemoryRegRow::CNonFailFastingAllocator>::grow(
        __int64 a1)
{
  __int64 v2; // rcx
  unsigned int v3; // edx
  __int64 v4; // rbx
  LPVOID v5; // rsi
  int v7; // eax
  __int64 v8; // rdx
  int *i; // rbx
  int **v10; // rcx
  int **v11; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  v3 = *(_DWORD *)(a1 + 12);
  if ( v3 >= 0x11 )
  {
    do
      v2 = (unsigned int)(v2 + 1);
    while ( v3 >= *((_DWORD *)`Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::grow'::`2'::rgprime
                  + v2) );
  }
  v4 = (unsigned int)v2;
  v5 = CoTaskMemAlloc(
         8LL
       * *((unsigned int *)`Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::grow'::`2'::rgprime + v2));
  if ( !v5 )
    return 2147942414LL;
  CoTaskMemFree(*(LPVOID *)a1);
  v7 = *((_DWORD *)`Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::grow'::`2'::rgprime + v4);
  v8 = 0;
  *(_QWORD *)a1 = v5;
  for ( *(_DWORD *)(a1 + 8) = v7; (unsigned int)v8 < *(_DWORD *)(a1 + 8); v8 = (unsigned int)(v8 + 1) )
    *(_QWORD *)(*(_QWORD *)a1 + 8 * v8) = 0;
  for ( i = *(int **)(a1 + 24); i != (int *)(a1 + 24); i = *(int **)i )
  {
    if ( i[6] < 0 )
    {
      v11 = 0;
      Map<unsigned short *,InMemoryRegRow::MapPropertyBag *,InMemoryRegRow::HashCaseInsentitiveWSTR,InMemoryRegRow::CNonFailFastingAllocator>::find(
        a1,
        i + 8,
        &v11);
      v10 = v11;
      *((_QWORD *)i + 2) = *v11;
      *v10 = i;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003c000  push    rbx
0x18003c002  push    rsi
0x18003c003  push    rdi
0x18003c004  push    r14
0x18003c006  sub     rsp, 28h
0x18003c00a  mov     rdi, rcx
0x18003c00d  lea     r14, ?rgprime@?1??grow@?$Map@PEAGPEAUIDispatch@@VHashWSTR@@VCNonFailFastingAllocator@@@@AEAAJXZ@4QBIB; uint const near * const `Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::grow(void)'::`2'::rgprime
0x18003c014  xor     ecx, ecx
0x18003c016  mov     edx, [rdi+0Ch]
0x18003c019  cmp     edx, 11h
0x18003c01c  jb      short loc_18003C026
0x18003c01e  inc     ecx
0x18003c020  cmp     edx, [r14+rcx*4]
0x18003c024  jnb     short loc_18003C01E
0x18003c026  mov     ebx, ecx
0x18003c028  mov     ecx, [r14+rcx*4]
0x18003c02c  shl     rcx, 3; cb
0x18003c030  call    cs:__imp_CoTaskMemAlloc
0x18003c036  mov     rsi, rax
0x18003c039  test    rax, rax
0x18003c03c  jnz     short loc_18003C045
0x18003c03e  mov     eax, 8007000Eh
0x18003c043  jmp     short loc_18003C0B3
0x18003c045  mov     rcx, [rdi]; pv
0x18003c048  call    cs:__imp_CoTaskMemFree
0x18003c04e  mov     eax, [r14+rbx*4]
0x18003c052  xor     edx, edx
0x18003c054  mov     [rdi], rsi
0x18003c057  mov     [rdi+8], eax
0x18003c05a  test    eax, eax
0x18003c05c  jz      short loc_18003C070
0x18003c05e  mov     rax, [rdi]
0x18003c061  mov     qword ptr [rax+rdx*8], 0
0x18003c069  inc     edx
0x18003c06b  cmp     edx, [rdi+8]
0x18003c06e  jb      short loc_18003C05E
0x18003c070  lea     rsi, [rdi+18h]
0x18003c074  mov     rbx, [rsi]
0x18003c077  jmp     short loc_18003C0AC
0x18003c079  mov     eax, [rbx+18h]
0x18003c07c  test    eax, eax
0x18003c07e  jns     short loc_18003C0A9
0x18003c080  lea     rdx, [rbx+20h]
0x18003c084  mov     [rsp+48h+arg_0], 0
0x18003c08d  lea     r8, [rsp+48h+arg_0]
0x18003c092  mov     rcx, rdi
0x18003c095  call    ?find@?$Map@PEAGPEAUMapPropertyBag@InMemoryRegRow@@VHashCaseInsentitiveWSTR@2@VCNonFailFastingAllocator@2@@@AEBAHAEBQEAGPEAPEAPEAVAssoc@1@@Z; Map<ushort *,InMemoryRegRow::MapPropertyBag *,InMemoryRegRow::HashCaseInsentitiveWSTR,InMemoryRegRow::CNonFailFastingAllocator>::find(ushort * const &,Map<ushort *,InMemoryRegRow::MapPropertyBag *,InMemoryRegRow::HashCaseInsentitiveWSTR,InMemoryRegRow::CNonFailFastingAllocator>::Assoc * * *)
0x18003c09a  mov     rcx, [rsp+48h+arg_0]
0x18003c09f  mov     rax, [rcx]
0x18003c0a2  mov     [rbx+10h], rax
0x18003c0a6  mov     [rcx], rbx
0x18003c0a9  mov     rbx, [rbx]
0x18003c0ac  cmp     rbx, rsi
0x18003c0af  jnz     short loc_18003C079
0x18003c0b1  xor     eax, eax
0x18003c0b3  add     rsp, 28h
0x18003c0b7  pop     r14
0x18003c0b9  pop     rdi
0x18003c0ba  pop     rsi
0x18003c0bb  pop     rbx
0x18003c0bc  retn
```
