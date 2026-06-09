# CPersistStreamInit::FreeFetchedData(CRowInfo &,tagDBBINDING *,ulong)

- ea: `0x18001b654`
- end: `0x18001b761`
- name: `?FreeFetchedData@CPersistStreamInit@@AEAAXAEAVCRowInfo@@PEAUtagDBBINDING@@K@Z`
- size: `269`
- prototype: `void __fastcall(CPersistStreamInit *__hidden this, struct CRowInfo *, struct tagDBBINDING *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001db24`
- `0x18001ee64`

## callees

- `0x18001b654`
- `0x180031010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001b6e7`
- `ole32!CoTaskMemFree` at `0x18001b6e7`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b6a8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b6a8`
- `OLEAUT32!__imp_VariantClear` at `0x18001b73d`
- `OLEAUT32!__imp_VariantClear` at `0x18001b73d`

## pseudocode

```c
void __fastcall CPersistStreamInit::FreeFetchedData(
        CPersistStreamInit *this,
        struct CRowInfo *a2,
        struct tagDBBINDING *a3,
        unsigned int a4)
{
  unsigned int i; // edi
  __int64 v8; // rdx
  __int16 v9; // cx
  OLECHAR *v10; // rcx
  void *v11; // rcx
  DBBYTEOFFSET v12; // rcx
  DBBYTEOFFSET obValue; // rax
  __int64 v14; // rcx
  VARIANTARG *v15; // rcx

  if ( a4 )
  {
    for ( i = 0; i < a4; ++i )
    {
      v8 = *((_QWORD *)a2 + 11);
      if ( (*(_DWORD *)(v8 + a3->obStatus) & 0xFFFFFFFB) == 0 )
      {
        v9 = a3->wType & 0xBFFF;
        if ( v9 == 8 )
        {
          v10 = *(OLECHAR **)(v8 + a3->obValue);
          if ( v10 )
          {
            SysFreeString(v10);
            goto LABEL_15;
          }
        }
        else if ( (a3->wType & 0x4000) == 0 || a3->dwMemOwner || (unsigned __int16)(v9 - 128) > 2u )
        {
          if ( v9 != 13 )
          {
            if ( v9 == 12 )
            {
              v15 = (VARIANTARG *)(v8 + a3->obValue);
              if ( v15 )
                VariantClear(v15);
            }
            goto LABEL_20;
          }
          v14 = *(_QWORD *)(v8 + a3->obValue);
          if ( v14 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
LABEL_15:
            v12 = *((_QWORD *)a2 + 11);
            obValue = a3->obValue;
LABEL_16:
            *(_QWORD *)(v12 + obValue) = 0;
          }
        }
        else
        {
          v11 = *(void **)(v8 + a3->obValue);
          if ( v11 )
          {
            CoTaskMemFree(v11);
            v12 = a3->obValue;
            obValue = *((_QWORD *)a2 + 11);
            goto LABEL_16;
          }
        }
      }
LABEL_20:
      ++a3;
    }
  }
}

```

## disassembly

```asm
0x18001b654  test    r9d, r9d
0x18001b657  jz      locret_18001B75F
0x18001b65d  push    rbx
0x18001b65e  push    rbp
0x18001b65f  push    rsi
0x18001b660  push    rdi
0x18001b661  sub     rsp, 28h
0x18001b665  mov     ebp, r9d
0x18001b668  mov     rbx, r8
0x18001b66b  mov     rsi, rdx
0x18001b66e  xor     edi, edi
0x18001b670  mov     rdx, [rsi+58h]
0x18001b674  mov     rax, [rbx+18h]
0x18001b678  test    dword ptr [rdx+rax], 0FFFFFFFBh
0x18001b67f  jnz     loc_18001B749
0x18001b685  movzx   ecx, word ptr [rbx+54h]
0x18001b689  mov     eax, 0BFFFh
0x18001b68e  and     cx, ax
0x18001b691  cmp     cx, 8
0x18001b695  jnz     short loc_18001B6B6
0x18001b697  mov     rax, [rbx+8]
0x18001b69b  mov     rcx, [rdx+rax]; bstrString
0x18001b69f  test    rcx, rcx
0x18001b6a2  jz      loc_18001B749
0x18001b6a8  call    cs:__imp_SysFreeString
0x18001b6af  nop     dword ptr [rax+rax+00h]
0x18001b6b4  jmp     short loc_18001B71C
0x18001b6b6  mov     eax, 4000h
0x18001b6bb  test    [rbx+54h], ax
0x18001b6bf  jz      short loc_18001B6FD
0x18001b6c1  cmp     dword ptr [rbx+3Ch], 0
0x18001b6c5  jnz     short loc_18001B6FD
0x18001b6c7  mov     r8d, 80h
0x18001b6cd  movzx   eax, cx
0x18001b6d0  sub     ax, r8w
0x18001b6d4  cmp     ax, 2
0x18001b6d8  ja      short loc_18001B6FD
0x18001b6da  mov     rax, [rbx+8]
0x18001b6de  mov     rcx, [rdx+rax]; pv
0x18001b6e2  test    rcx, rcx
0x18001b6e5  jz      short loc_18001B749
0x18001b6e7  call    cs:__imp_CoTaskMemFree
0x18001b6ee  nop     dword ptr [rax+rax+00h]
0x18001b6f3  mov     rcx, [rbx+8]
0x18001b6f7  mov     rax, [rsi+58h]
0x18001b6fb  jmp     short loc_18001B724
0x18001b6fd  cmp     cx, 0Dh
0x18001b701  jnz     short loc_18001B72E
0x18001b703  mov     rax, [rbx+8]
0x18001b707  mov     rcx, [rdx+rax]
0x18001b70b  test    rcx, rcx
0x18001b70e  jz      short loc_18001B749
0x18001b710  mov     rax, [rcx]
0x18001b713  mov     rax, [rax+10h]
0x18001b717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b71c  mov     rcx, [rsi+58h]
0x18001b720  mov     rax, [rbx+8]
0x18001b724  mov     qword ptr [rcx+rax], 0
0x18001b72c  jmp     short loc_18001B749
0x18001b72e  cmp     cx, 0Ch
0x18001b732  jnz     short loc_18001B749
0x18001b734  mov     rcx, [rbx+8]
0x18001b738  add     rcx, rdx; pvarg
0x18001b73b  jz      short loc_18001B749
0x18001b73d  call    cs:__imp_VariantClear
0x18001b744  nop     dword ptr [rax+rax+00h]
0x18001b749  inc     edi
0x18001b74b  add     rbx, 58h ; 'X'
0x18001b74f  cmp     edi, ebp
0x18001b751  jb      loc_18001B670
0x18001b757  add     rsp, 28h
0x18001b75b  pop     rdi
0x18001b75c  pop     rsi
0x18001b75d  pop     rbp
0x18001b75e  pop     rbx
0x18001b75f  retn
```
