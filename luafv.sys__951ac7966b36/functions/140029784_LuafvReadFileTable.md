# LuafvReadFileTable

- ea: `0x140029784`
- end: `0x140029a1a`
- name: `LuafvReadFileTable`
- size: `662`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x140028714`

## callees

- `0x140006380`
- `0x140014b1c`
- `0x14001dd90`
- `0x1400280d4`
- `0x140028364`
- `0x140028c84`
- `0x140028d54`
- `0x140029784`
- `0x140029a20`
- `0x140029b30`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400298b9`
- `ntoskrnl!ZwClose` at `0x140029955`
- `ntoskrnl!ZwClose` at `0x1400299c1`
- `ntoskrnl!ZwClose` at `0x1400298b9`
- `ntoskrnl!ZwClose` at `0x140029955`
- `ntoskrnl!ZwClose` at `0x1400299c1`

## pseudocode

```c
__int64 __fastcall LuafvReadFileTable(HANDLE KeyHandle)
{
  __int64 i; // rdx
  __int64 v3; // rax
  __int64 v4; // rdx
  __int64 v5; // r8
  int Buffer; // edi
  unsigned int v7; // esi
  __int64 *v8; // rbx
  __int64 v9; // rbx
  _QWORD *v10; // rax
  __int64 v11; // rcx
  _QWORD *v12; // rdx
  _QWORD *v13; // rsi
  _QWORD *v14; // rax
  void *v15; // rcx
  __int64 v16; // rcx
  _QWORD *v17; // rdx
  _QWORD *v18; // rsi
  unsigned int j; // ebx
  __int64 v20; // rcx
  _QWORD v22[11]; // [rsp+20h] [rbp-58h] BYREF

  for ( i = 0; i != 7; ++i )
  {
    v3 = i;
    *((_QWORD *)&StaticEntryRoots[v3] + 1) = 0;
  }
  memset(v22, 0, 0x48u);
  v22[1] = v22;
  v22[0] = v22;
  v22[8] = &PushLock;
  Buffer = GrowQueryBuffer(0x200u, v4, v5);
  if ( Buffer < 0 )
    goto LABEL_27;
  Buffer = BuildExcludedExtensionsList(KeyHandle);
  if ( Buffer < 0 )
    goto LABEL_27;
  Buffer = GetStaticEntryRoots();
  if ( Buffer < 0 )
    goto LABEL_27;
  v7 = 0;
  v8 = &StaticEntries;
  while ( v7 < 0xFB )
  {
    if ( !byte_14000F11E || *((_BYTE *)v8 + 20) )
    {
      Buffer = CreateStaticEntry((__int64)v8);
      if ( Buffer < 0 )
        goto LABEL_27;
    }
    ++v7;
    v8 += 3;
  }
  if ( LuafvOpenKey(KeyHandle, (struct _UNICODE_STRING *)&LuafvFileListKeyName, (void **)&v22[5]) < 0 )
  {
    v22[5] = 0;
    Buffer = 0;
    goto LABEL_46;
  }
  Buffer = EnumerateKey(v22);
  if ( Buffer < 0 )
    goto LABEL_27;
  if ( (_QWORD *)v22[0] != v22 )
  {
    v9 = v22[0] - 16LL;
    while ( 1 )
    {
      Buffer = ProcessKey(v9);
      if ( Buffer < 0 )
        break;
      v10 = *(_QWORD **)v9;
      if ( *(_QWORD *)v9 == v9 )
      {
        while ( 1 )
        {
          ZwClose(*(HANDLE *)(v9 + 40));
          if ( !*(_QWORD *)(v9 + 32) )
            goto LABEL_43;
          v11 = *(_QWORD *)(v9 + 16);
          if ( *(_QWORD *)(v11 + 8) != v9 + 16 || (v12 = *(_QWORD **)(v9 + 24), *v12 != v9 + 16) )
LABEL_42:
            __fastfail(3u);
          *v12 = v11;
          *(_QWORD *)(v11 + 8) = v12;
          v13 = *(_QWORD **)(v9 + 32);
          LuafvFreePool(v9);
          v10 = (_QWORD *)*v13;
          if ( (_QWORD *)*v13 != v13 )
            break;
          v9 = (__int64)v13;
          if ( !v13 )
            goto LABEL_44;
        }
      }
      v9 = (__int64)(v10 - 2);
      if ( v10 == (_QWORD *)16 )
        goto LABEL_44;
    }
LABEL_27:
    if ( (_QWORD *)v22[0] != v22 )
    {
      v9 = v22[0] - 16LL;
      while ( 1 )
      {
        v14 = *(_QWORD **)v9;
        if ( *(_QWORD *)v9 == v9 )
          break;
        v9 = (__int64)(v14 - 2);
        if ( v14 == (_QWORD *)16 )
          goto LABEL_44;
      }
      while ( 1 )
      {
        v15 = *(void **)(v9 + 40);
        if ( v15 )
          ZwClose(v15);
        if ( !*(_QWORD *)(v9 + 32) )
          break;
        v16 = *(_QWORD *)(v9 + 16);
        if ( *(_QWORD *)(v16 + 8) != v9 + 16 )
          goto LABEL_42;
        v17 = *(_QWORD **)(v9 + 24);
        if ( *v17 != v9 + 16 )
          goto LABEL_42;
        *v17 = v16;
        *(_QWORD *)(v16 + 8) = v17;
        v18 = *(_QWORD **)(v9 + 32);
        LuafvFreePool(v9);
        if ( (_QWORD *)*v18 == v18 )
          v9 = (__int64)v18;
        else
          v9 = *v18 - 16LL;
        if ( !v9 )
          goto LABEL_44;
      }
LABEL_43:
      *(_QWORD *)(v9 + 40) = 0;
    }
  }
LABEL_44:
  if ( v22[5] )
    ZwClose((HANDLE)v22[5]);
LABEL_46:
  if ( QueryBuffer )
  {
    LuafvFreePool((__int64)QueryBuffer);
    QueryBuffer = 0;
  }
  for ( j = 0; j < 7; ++j )
  {
    if ( j )
    {
      v20 = *((_QWORD *)&StaticEntryRoots[j] + 1);
      if ( v20 )
        LuafvFreePool(v20);
    }
  }
  return (unsigned int)Buffer;
}

```

## disassembly

```asm
0x140029784  push    rbp
0x140029786  push    rbx
0x140029787  push    rsi
0x140029788  push    rdi
0x140029789  push    r12
0x14002978b  push    r14
0x14002978d  mov     rbp, rsp
0x140029790  sub     rsp, 78h
0x140029794  mov     r14, rcx
0x140029797  lea     r12, StaticEntryRoots
0x14002979e  xor     edx, edx
0x1400297a0  mov     rax, rdx
0x1400297a3  inc     rdx
0x1400297a6  add     rax, rax
0x1400297a9  mov     qword ptr [r12+rax*8+8], 0
0x1400297b2  cmp     rdx, 7
0x1400297b6  jnz     short loc_1400297A0
0x1400297b8  xor     edx, edx; Val
0x1400297ba  lea     rcx, [rbp+var_58]; void *
0x1400297be  lea     r8d, [rdx+48h]; Size
0x1400297c2  call    memset
0x1400297c7  lea     rax, [rbp+var_58]
0x1400297cb  mov     ecx, 200h
0x1400297d0  mov     [rbp+var_50], rax
0x1400297d4  lea     rax, [rbp+var_58]
0x1400297d8  mov     [rbp+var_58], rax
0x1400297dc  lea     rax, PushLock
0x1400297e3  mov     [rbp+var_18], rax
0x1400297e7  call    GrowQueryBuffer
0x1400297ec  mov     edi, eax
0x1400297ee  test    eax, eax
0x1400297f0  js      loc_140029924
0x1400297f6  mov     rcx, r14; KeyHandle
0x1400297f9  call    BuildExcludedExtensionsList
0x1400297fe  mov     edi, eax
0x140029800  test    eax, eax
0x140029802  js      loc_140029924
0x140029808  call    GetStaticEntryRoots
0x14002980d  mov     edi, eax
0x14002980f  test    eax, eax
0x140029811  js      loc_140029924
0x140029817  xor     esi, esi
0x140029819  lea     rbx, StaticEntries
0x140029820  cmp     esi, 0FBh
0x140029826  jnb     short loc_140029851
0x140029828  cmp     cs:byte_14000F11E, 0
0x14002982f  jz      short loc_140029837
0x140029831  cmp     byte ptr [rbx+14h], 0
0x140029835  jz      short loc_140029849
0x140029837  mov     rcx, rbx
0x14002983a  call    CreateStaticEntry
0x14002983f  mov     edi, eax
0x140029841  test    eax, eax
0x140029843  js      loc_140029924
0x140029849  inc     esi
0x14002984b  add     rbx, 18h
0x14002984f  jmp     short loc_140029820
0x140029851  lea     r8, [rbp+Handle]
0x140029855  mov     rcx, r14
0x140029858  lea     rdx, LuafvFileListKeyName
0x14002985f  call    LuafvOpenKey
0x140029864  test    eax, eax
0x140029866  jns     short loc_140029877
0x140029868  mov     [rbp+Handle], 0
0x140029870  xor     edi, edi
0x140029872  jmp     loc_1400299CD
0x140029877  lea     rcx, [rbp+var_58]
0x14002987b  call    EnumerateKey
0x140029880  mov     edi, eax
0x140029882  test    eax, eax
0x140029884  js      loc_140029924
0x14002988a  mov     rbx, [rbp+var_58]
0x14002988e  lea     rax, [rbp+var_58]
0x140029892  cmp     rbx, rax
0x140029895  jz      loc_1400299B8
0x14002989b  add     rbx, 0FFFFFFFFFFFFFFF0h
0x14002989f  mov     rcx, rbx
0x1400298a2  call    ProcessKey
0x1400298a7  mov     edi, eax
0x1400298a9  test    eax, eax
0x1400298ab  js      short loc_140029924
0x1400298ad  mov     rax, [rbx]
0x1400298b0  cmp     rax, rbx
0x1400298b3  jnz     short loc_140029916
0x1400298b5  mov     rcx, [rbx+28h]; Handle
0x1400298b9  call    cs:__imp_ZwClose
0x1400298c0  nop     dword ptr [rax+rax+00h]
0x1400298c5  cmp     qword ptr [rbx+20h], 0
0x1400298ca  jz      loc_1400299B0
0x1400298d0  lea     rax, [rbx+10h]
0x1400298d4  mov     rcx, [rax]
0x1400298d7  cmp     [rcx+8], rax
0x1400298db  jnz     loc_1400299A9
0x1400298e1  mov     rdx, [rax+8]
0x1400298e5  cmp     [rdx], rax
0x1400298e8  jnz     loc_1400299A9
0x1400298ee  mov     [rdx], rcx
0x1400298f1  mov     [rcx+8], rdx
0x1400298f5  mov     rcx, rbx
0x1400298f8  mov     rsi, [rbx+20h]
0x1400298fc  call    LuafvFreePool
0x140029901  mov     rax, [rsi]
0x140029904  cmp     rax, rsi
0x140029907  jnz     short loc_140029916
0x140029909  mov     rbx, rsi
0x14002990c  test    rsi, rsi
0x14002990f  jnz     short loc_1400298B5
0x140029911  jmp     loc_1400299B8
0x140029916  lea     rbx, [rax-10h]
0x14002991a  test    rbx, rbx
0x14002991d  jnz     short loc_14002989F
0x14002991f  jmp     loc_1400299B8
0x140029924  mov     rbx, [rbp+var_58]
0x140029928  lea     rax, [rbp+var_58]
0x14002992c  cmp     rbx, rax
0x14002992f  jz      loc_1400299B8
0x140029935  add     rbx, 0FFFFFFFFFFFFFFF0h
0x140029939  mov     rax, [rbx]
0x14002993c  cmp     rax, rbx
0x14002993f  jz      short loc_14002994C
0x140029941  lea     rbx, [rax-10h]
0x140029945  test    rbx, rbx
0x140029948  jnz     short loc_140029939
0x14002994a  jmp     short loc_1400299B8
0x14002994c  mov     rcx, [rbx+28h]; Handle
0x140029950  test    rcx, rcx
0x140029953  jz      short loc_140029961
0x140029955  call    cs:__imp_ZwClose
0x14002995c  nop     dword ptr [rax+rax+00h]
0x140029961  cmp     qword ptr [rbx+20h], 0
0x140029966  jz      short loc_1400299B0
0x140029968  lea     rax, [rbx+10h]
0x14002996c  mov     rcx, [rax]
0x14002996f  cmp     [rcx+8], rax
0x140029973  jnz     short loc_1400299A9
0x140029975  mov     rdx, [rax+8]
0x140029979  cmp     [rdx], rax
0x14002997c  jnz     short loc_1400299A9
0x14002997e  mov     [rdx], rcx
0x140029981  mov     [rcx+8], rdx
0x140029985  mov     rcx, rbx
0x140029988  mov     rsi, [rbx+20h]
0x14002998c  call    LuafvFreePool
0x140029991  mov     rbx, [rsi]
0x140029994  cmp     rbx, rsi
0x140029997  jnz     short loc_14002999E
0x140029999  mov     rbx, rsi
0x14002999c  jmp     short loc_1400299A2
0x14002999e  add     rbx, 0FFFFFFFFFFFFFFF0h
0x1400299a2  test    rbx, rbx
0x1400299a5  jnz     short loc_14002994C
0x1400299a7  jmp     short loc_1400299B8
0x1400299a9  mov     ecx, 3
0x1400299ae  int     29h; Win8: RtlFailFast(ecx)
0x1400299b0  mov     qword ptr [rbx+28h], 0
0x1400299b8  mov     rcx, [rbp+Handle]; Handle
0x1400299bc  test    rcx, rcx
0x1400299bf  jz      short loc_1400299CD
0x1400299c1  call    cs:__imp_ZwClose
0x1400299c8  nop     dword ptr [rax+rax+00h]
0x1400299cd  mov     rcx, cs:QueryBuffer
0x1400299d4  test    rcx, rcx
0x1400299d7  jz      short loc_1400299E9
0x1400299d9  call    LuafvFreePool
0x1400299de  mov     cs:QueryBuffer, 0
0x1400299e9  xor     ebx, ebx
0x1400299eb  test    ebx, ebx
0x1400299ed  jz      short loc_140029A03
0x1400299ef  mov     eax, ebx
0x1400299f1  add     rax, rax
0x1400299f4  mov     rcx, [r12+rax*8+8]
0x1400299f9  test    rcx, rcx
0x1400299fc  jz      short loc_140029A03
0x1400299fe  call    LuafvFreePool
0x140029a03  inc     ebx
0x140029a05  cmp     ebx, 7
0x140029a08  jb      short loc_1400299EB
0x140029a0a  mov     eax, edi
0x140029a0c  add     rsp, 78h
0x140029a10  pop     r14
0x140029a12  pop     r12
0x140029a14  pop     rdi
0x140029a15  pop     rsi
0x140029a16  pop     rbx
0x140029a17  pop     rbp
0x140029a18  retn
```
