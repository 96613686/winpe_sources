# AggregatedTokenRequest::UpdateContext(AggregatedTokenRequest::RealmInfo const &)

- ea: `0x14000b3f8`
- end: `0x14000b4eb`
- name: `?UpdateContext@AggregatedTokenRequest@@AEAAXAEBURealmInfo@1@@Z`
- size: `243`
- prototype: `void __fastcall(AggregatedTokenRequest *__hidden this, const struct AggregatedTokenRequest::RealmInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14000b4f4`

## callees

- `0x1400061dc`
- `0x14000b3f8`
- `0x14000be04`
- `0x14002c3e8`

## pseudocode

```c
void __fastcall AggregatedTokenRequest::UpdateContext(
        AggregatedTokenRequest *this,
        const struct AggregatedTokenRequest::RealmInfo *a2)
{
  __int64 v4; // rbx
  _WORD *v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  _WORD *v8; // rdx
  __int64 v9; // r8
  _WORD *v10; // rdx
  _BYTE pExceptionObject[56]; // [rsp+20h] [rbp-38h] BYREF

  if ( *(_DWORD *)a2 && (unsigned int)(*(_DWORD *)a2 - 1) > 1 )
  {
    ArgumentException::ArgumentException((ArgumentException *)pExceptionObject, -895418316);
    throw (ArgumentException *)pExceptionObject;
  }
  v4 = -1;
  *(_DWORD *)(*((_QWORD *)this + 1) + 300LL) = *(_DWORD *)a2;
  v5 = (_WORD *)*((_QWORD *)a2 + 1);
  if ( *((_DWORD *)v5 - 4) )
  {
    v6 = *((_QWORD *)this + 1);
    if ( v5 )
    {
      v7 = -1;
      do
        ++v7;
      while ( v5[v7] );
    }
    else
    {
      v7 = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString((__int64 *)(v6 + 264), v5, v7);
  }
  v8 = (_WORD *)*((_QWORD *)a2 + 2);
  if ( *((_DWORD *)v8 - 4) )
  {
    if ( v8 )
    {
      v9 = -1;
      do
        ++v9;
      while ( v8[v9] );
    }
    else
    {
      v9 = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString((__int64 *)(*((_QWORD *)this + 1) + 272LL), v8, v9);
  }
  v10 = (_WORD *)*((_QWORD *)a2 + 3);
  if ( *((_DWORD *)v10 - 4) )
  {
    if ( v10 )
    {
      do
        ++v4;
      while ( v10[v4] );
    }
    else
    {
      LODWORD(v4) = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString((__int64 *)(*((_QWORD *)this + 1) + 280LL), v10, (unsigned int)v4);
  }
}

```

## disassembly

```asm
0x14000b3f8  push    rbx
0x14000b3fa  push    rbp
0x14000b3fb  push    rsi
0x14000b3fc  push    rdi
0x14000b3fd  sub     rsp, 38h
0x14000b401  mov     r9d, [rdx]
0x14000b404  xor     ebp, ebp
0x14000b406  mov     rsi, rdx
0x14000b409  mov     rdi, rcx
0x14000b40c  mov     r8d, r9d
0x14000b40f  test    r9d, r9d
0x14000b412  jz      short loc_14000B424
0x14000b414  sub     r8d, 1
0x14000b418  jz      short loc_14000B424
0x14000b41a  cmp     r8d, 1
0x14000b41e  jnz     loc_14000B4CA
0x14000b424  mov     rax, [rcx+8]
0x14000b428  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000b42c  mov     [rax+12Ch], r9d
0x14000b433  mov     rdx, [rdx+8]
0x14000b437  cmp     [rdx-10h], ebp
0x14000b43a  jz      short loc_14000B463
0x14000b43c  mov     rcx, [rcx+8]
0x14000b440  test    rdx, rdx
0x14000b443  jnz     short loc_14000B44A
0x14000b445  mov     r8d, ebp
0x14000b448  jmp     short loc_14000B457
0x14000b44a  mov     r8, rbx
0x14000b44d  inc     r8
0x14000b450  cmp     [rdx+r8*2], bp
0x14000b455  jnz     short loc_14000B44D
0x14000b457  add     rcx, 108h
0x14000b45e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000b463  mov     rdx, [rsi+10h]
0x14000b467  cmp     [rdx-10h], ebp
0x14000b46a  jz      short loc_14000B493
0x14000b46c  mov     rcx, [rdi+8]
0x14000b470  test    rdx, rdx
0x14000b473  jnz     short loc_14000B47A
0x14000b475  mov     r8d, ebp
0x14000b478  jmp     short loc_14000B487
0x14000b47a  mov     r8, rbx
0x14000b47d  inc     r8
0x14000b480  cmp     [rdx+r8*2], bp
0x14000b485  jnz     short loc_14000B47D
0x14000b487  add     rcx, 110h
0x14000b48e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000b493  mov     rdx, [rsi+18h]
0x14000b497  cmp     [rdx-10h], ebp
0x14000b49a  jz      short loc_14000B4C1
0x14000b49c  mov     rcx, [rdi+8]
0x14000b4a0  test    rdx, rdx
0x14000b4a3  jnz     short loc_14000B4A9
0x14000b4a5  mov     ebx, ebp
0x14000b4a7  jmp     short loc_14000B4B2
0x14000b4a9  inc     rbx
0x14000b4ac  cmp     [rdx+rbx*2], bp
0x14000b4b0  jnz     short loc_14000B4A9
0x14000b4b2  add     rcx, 118h
0x14000b4b9  mov     r8d, ebx
0x14000b4bc  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000b4c1  add     rsp, 38h
0x14000b4c5  pop     rdi
0x14000b4c6  pop     rsi
0x14000b4c7  pop     rbp
0x14000b4c8  pop     rbx
0x14000b4c9  retn
0x14000b4ca  mov     edx, 0CAA10034h; unsigned int
0x14000b4cf  lea     rcx, [rsp+58h+pExceptionObject]; this
0x14000b4d4  call    ??0ArgumentException@@QEAA@K@Z; ArgumentException::ArgumentException(ulong)
0x14000b4d9  lea     rdx, _TI3?AVArgumentException@@; pThrowInfo
0x14000b4e0  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x14000b4e5  call    _CxxThrowException_0
```
