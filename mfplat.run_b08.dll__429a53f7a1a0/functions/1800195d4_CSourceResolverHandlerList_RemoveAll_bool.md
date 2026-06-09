# CSourceResolverHandlerList::RemoveAll(bool)

- ea: `0x1800195d4`
- end: `0x180019747`
- name: `?RemoveAll@CSourceResolverHandlerList@@QEAAX_N@Z`
- size: `371`
- prototype: `void __fastcall(CSourceResolverHandlerList *__hidden this, bool)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800184f4`
- `0x1800189c4`
- `0x180019480`
- `0x180098378`

## callees

- `0x1800195d4`
- `0x180019750`
- `0x18001981c`
- `0x1801740b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800195eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800196bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800196e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019705`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800195eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800196bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800196e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019705`

## pseudocode

```c
void __fastcall CSourceResolverHandlerList::RemoveAll(LPVOID *this, char a2)
{
  __int64 v4; // rsi
  _QWORD *i; // r14
  __int64 v6; // rsi
  _QWORD *j; // r14
  __int64 v8; // rbp
  _QWORD *k; // rsi
  void *v10; // rax
  void *v11; // rax

  CoTaskMemFree(this[6]);
  this[6] = 0;
  *((_DWORD *)this + 14) = 0;
  CTUnkArray<IUnknown>::RemoveAll(this);
  CTUnkArray<IUnknown>::RemoveAll(this + 3);
  CTUnkArray<IUnknown>::RemoveAll(this + 8);
  v4 = 0;
  for ( i = this + 12; (unsigned int)v4 < *((_DWORD *)this + 26); v4 = (unsigned int)(v4 + 1) )
  {
    CoTaskMemFree(*(LPVOID *)(*i + 8 * v4));
    *(_QWORD *)(*i + 8 * v4) = 0;
  }
  MFDynamicArray<unsigned short *>::RemoveAllElements(this + 12);
  v6 = 0;
  for ( j = this + 14; (unsigned int)v6 < *((_DWORD *)this + 30); v6 = (unsigned int)(v6 + 1) )
  {
    CoTaskMemFree(*(LPVOID *)(*j + 8 * v6));
    *(_QWORD *)(*j + 8 * v6) = 0;
  }
  MFDynamicArray<unsigned short *>::RemoveAllElements(this + 14);
  v8 = 0;
  for ( k = this + 16; (unsigned int)v8 < *((_DWORD *)this + 34); v8 = (unsigned int)(v8 + 1) )
  {
    CoTaskMemFree(*(LPVOID *)(*k + 8 * v8));
    *(_QWORD *)(*k + 8 * v8) = 0;
  }
  MFDynamicArray<unsigned short *>::RemoveAllElements(this + 16);
  if ( a2 )
  {
    v10 = this[18];
    if ( v10 != this[19] )
      this[19] = v10;
    if ( this[21] != this[22] )
    {
      std::_Destroy_range<std::allocator<std::wstring>>();
      this[22] = this[21];
    }
    v11 = this[24];
    if ( v11 != this[25] )
      this[25] = v11;
  }
}

```

## disassembly

```asm
0x1800195d4  push    rbx
0x1800195d6  push    rbp
0x1800195d7  push    rsi
0x1800195d8  push    rdi
0x1800195d9  push    r14
0x1800195db  push    r15
0x1800195dd  sub     rsp, 28h
0x1800195e1  mov     rdi, rcx
0x1800195e4  mov     r15b, dl
0x1800195e7  mov     rcx, [rcx+30h]; pv
0x1800195eb  call    cs:__imp_CoTaskMemFree
0x1800195f1  mov     rcx, rdi
0x1800195f4  mov     qword ptr [rdi+30h], 0
0x1800195fc  mov     dword ptr [rdi+38h], 0
0x180019603  call    ?RemoveAll@?$CTUnkArray@UIUnknown@@@@QEAAXXZ; CTUnkArray<IUnknown>::RemoveAll(void)
0x180019608  lea     rcx, [rdi+18h]
0x18001960c  call    ?RemoveAll@?$CTUnkArray@UIUnknown@@@@QEAAXXZ; CTUnkArray<IUnknown>::RemoveAll(void)
0x180019611  lea     rcx, [rdi+40h]
0x180019615  call    ?RemoveAll@?$CTUnkArray@UIUnknown@@@@QEAAXXZ; CTUnkArray<IUnknown>::RemoveAll(void)
0x18001961a  xor     esi, esi
0x18001961c  lea     r14, [rdi+60h]
0x180019620  cmp     [rdi+68h], esi
0x180019623  ja      loc_1800196D9
0x180019629  mov     rcx, r14
0x18001962c  call    ?RemoveAllElements@?$MFDynamicArray@PEAG@@QEAAX_N@Z; MFDynamicArray<ushort *>::RemoveAllElements(bool)
0x180019631  xor     esi, esi
0x180019633  lea     r14, [rdi+70h]
0x180019637  cmp     [rdi+78h], esi
0x18001963a  ja      loc_1800196FE
0x180019640  mov     rcx, r14
0x180019643  call    ?RemoveAllElements@?$MFDynamicArray@PEAG@@QEAAX_N@Z; MFDynamicArray<ushort *>::RemoveAllElements(bool)
0x180019648  xor     ebp, ebp
0x18001964a  lea     rsi, [rdi+80h]
0x180019651  cmp     [rdi+88h], ebp
0x180019657  ja      short loc_1800196B5
0x180019659  mov     rcx, rsi
0x18001965c  call    ?RemoveAllElements@?$MFDynamicArray@PEAG@@QEAAX_N@Z; MFDynamicArray<ushort *>::RemoveAllElements(bool)
0x180019661  test    r15b, r15b
0x180019664  jz      short loc_1800196A8
0x180019666  mov     rax, [rdi+90h]
0x18001966d  cmp     rax, [rdi+98h]
0x180019674  jnz     loc_180019723
0x18001967a  mov     rdx, [rdi+0B0h]
0x180019681  mov     rcx, [rdi+0A8h]
0x180019688  cmp     rcx, rdx
0x18001968b  jnz     loc_18001972F
0x180019691  mov     rax, [rdi+0C0h]
0x180019698  cmp     rax, [rdi+0C8h]
0x18001969f  jz      short loc_1800196A8
0x1800196a1  mov     [rdi+0C8h], rax
0x1800196a8  add     rsp, 28h
0x1800196ac  pop     r15
0x1800196ae  pop     r14
0x1800196b0  pop     rdi
0x1800196b1  pop     rsi
0x1800196b2  pop     rbp
0x1800196b3  pop     rbx
0x1800196b4  retn
0x1800196b5  mov     rcx, [rsi]
0x1800196b8  mov     rcx, [rcx+rbp*8]; pv
0x1800196bc  call    cs:__imp_CoTaskMemFree
0x1800196c2  mov     rax, [rsi]
0x1800196c5  mov     qword ptr [rax+rbp*8], 0
0x1800196cd  inc     ebp
0x1800196cf  cmp     ebp, [rdi+88h]
0x1800196d5  jnb     short loc_180019659
0x1800196d7  jmp     short loc_1800196B5
0x1800196d9  mov     rcx, [r14]
0x1800196dc  mov     rcx, [rcx+rsi*8]; pv
0x1800196e0  call    cs:__imp_CoTaskMemFree
0x1800196e6  mov     rax, [r14]
0x1800196e9  mov     qword ptr [rax+rsi*8], 0
0x1800196f1  inc     esi
0x1800196f3  cmp     esi, [rdi+68h]
0x1800196f6  jnb     loc_180019629
0x1800196fc  jmp     short loc_1800196D9
0x1800196fe  mov     rcx, [r14]
0x180019701  mov     rcx, [rcx+rsi*8]; pv
0x180019705  call    cs:__imp_CoTaskMemFree
0x18001970b  mov     rax, [r14]
0x18001970e  mov     qword ptr [rax+rsi*8], 0
0x180019716  inc     esi
0x180019718  cmp     esi, [rdi+78h]
0x18001971b  jnb     loc_180019640
0x180019721  jmp     short loc_1800196FE
0x180019723  mov     [rdi+98h], rax
0x18001972a  jmp     loc_18001967A
0x18001972f  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180019734  mov     rax, [rdi+0A8h]
0x18001973b  mov     [rdi+0B0h], rax
0x180019742  jmp     loc_180019691
```
