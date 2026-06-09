# CCfgArray<TMetabase_XMLtable::TLocation>::InsertAt(TMetabase_XMLtable::TLocation const &,ulong)

- ea: `0x18000bf74`
- end: `0x18000c000`
- name: `?InsertAt@?$CCfgArray@VTLocation@TMetabase_XMLtable@@@@QEAAJAEBVTLocation@TMetabase_XMLtable@@K@Z`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180006310`

## callees

- `0x180005ba4`
- `0x18000654c`
- `0x18000bf74`

## pseudocode

```c
__int64 __fastcall CCfgArray<TMetabase_XMLtable::TLocation>::InsertAt(__int64 a1, __int64 a2, unsigned int a3)
{
  int v3; // eax
  unsigned int v4; // esi
  __int64 v6; // rbp
  unsigned int v8; // edx
  __int64 result; // rax
  unsigned int v10; // r9d
  __int64 v11; // rbx

  v3 = *(_DWORD *)(a1 + 8);
  v4 = 0;
  v6 = a3;
  if ( *(_DWORD *)(a1 + 12) != v3 )
    goto LABEL_5;
  v8 = 1;
  if ( v3 )
    v8 = 2 * v3;
  result = CCfgArray<TMetabase_XMLtable::TLocation>::AllocNewSize(a1, v8);
  v4 = result;
  if ( (int)result >= 0 )
  {
LABEL_5:
    v10 = *(_DWORD *)(a1 + 12);
    if ( v10 > (unsigned int)v6 )
    {
      do
      {
        v11 = v10 - 1;
        TMetabase_XMLtable::TLocation::operator=(*(_QWORD *)a1 + 24LL * v10, *(_QWORD *)a1 + 24 * v11);
        v10 = v11;
      }
      while ( (unsigned int)v11 > (unsigned int)v6 );
    }
    TMetabase_XMLtable::TLocation::operator=(*(_QWORD *)a1 + 24 * v6, a2);
    ++*(_DWORD *)(a1 + 12);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x18000bf74  push    rbx
0x18000bf76  push    rbp
0x18000bf77  push    rsi
0x18000bf78  push    rdi
0x18000bf79  push    r14
0x18000bf7b  sub     rsp, 20h
0x18000bf7f  mov     eax, [rcx+8]
0x18000bf82  xor     esi, esi
0x18000bf84  mov     r14, rdx
0x18000bf87  mov     ebp, r8d
0x18000bf8a  mov     rdi, rcx
0x18000bf8d  cmp     [rcx+0Ch], eax
0x18000bf90  jnz     short loc_18000BFA7
0x18000bf92  lea     edx, [rsi+1]
0x18000bf95  test    eax, eax
0x18000bf97  jz      short loc_18000BF9C
0x18000bf99  lea     edx, [rax+rax]
0x18000bf9c  call    ?AllocNewSize@?$CCfgArray@VTLocation@TMetabase_XMLtable@@@@AEAAJK@Z; CCfgArray<TMetabase_XMLtable::TLocation>::AllocNewSize(ulong)
0x18000bfa1  mov     esi, eax
0x18000bfa3  test    eax, eax
0x18000bfa5  js      short loc_18000BFF5
0x18000bfa7  mov     r9d, [rdi+0Ch]
0x18000bfab  cmp     r9d, ebp
0x18000bfae  jbe     short loc_18000BFD6
0x18000bfb0  mov     r8, [rdi]
0x18000bfb3  lea     ebx, [r9-1]
0x18000bfb7  mov     eax, r9d
0x18000bfba  lea     rcx, [rbx+rbx*2]
0x18000bfbe  lea     rdx, [r8+rcx*8]
0x18000bfc2  lea     rcx, [rax+rax*2]
0x18000bfc6  lea     rcx, [r8+rcx*8]
0x18000bfca  call    ??4TLocation@TMetabase_XMLtable@@QEAAAEAV01@AEBV01@@Z; TMetabase_XMLtable::TLocation::operator=(TMetabase_XMLtable::TLocation const &)
0x18000bfcf  mov     r9d, ebx
0x18000bfd2  cmp     ebx, ebp
0x18000bfd4  ja      short loc_18000BFB0
0x18000bfd6  mov     rax, [rdi]
0x18000bfd9  lea     rcx, ds:0[rbp*2]
0x18000bfe1  add     rcx, rbp
0x18000bfe4  mov     rdx, r14
0x18000bfe7  lea     rcx, [rax+rcx*8]
0x18000bfeb  call    ??4TLocation@TMetabase_XMLtable@@QEAAAEAV01@AEBV01@@Z; TMetabase_XMLtable::TLocation::operator=(TMetabase_XMLtable::TLocation const &)
0x18000bff0  inc     dword ptr [rdi+0Ch]
0x18000bff3  mov     eax, esi
0x18000bff5  add     rsp, 20h
0x18000bff9  pop     r14
0x18000bffb  pop     rdi
0x18000bffc  pop     rsi
0x18000bffd  pop     rbp
0x18000bffe  pop     rbx
0x18000bfff  retn
```
