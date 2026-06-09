# QuicSettingsCopyVersionSettings

- ea: `0x14002c014`
- end: `0x14002c170`
- name: `QuicSettingsCopyVersionSettings`
- size: `348`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005f0c`
- `0x140025dfc`
- `0x14002d09c`

## callees

- `0x14002c014`
- `0x14003cb00`
- `0x14003ed00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002c059`
- `ntoskrnl!ExAllocatePool2` at `0x14002c059`

## pseudocode

```c
_QWORD *__fastcall QuicSettingsCopyVersionSettings(__int64 a1, char a2)
{
  unsigned __int64 v4; // rbp
  _QWORD *Pool2; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // edi
  _QWORD *v9; // rbx
  void *v11; // rcx
  unsigned int v12; // eax
  void *v13; // rcx
  unsigned int v14; // eax
  void *v15; // rcx
  unsigned int v16; // eax
  unsigned int i; // r8d
  __int64 v18; // rdx
  unsigned int j; // r8d
  __int64 v20; // rdx
  __int64 v21; // rdx

  v4 = 4 * (*(unsigned int *)(a1 + 32) + *(unsigned int *)(a1 + 28) + (unsigned __int64)*(unsigned int *)(a1 + 24)) + 40;
  Pool2 = (_QWORD *)ExAllocatePool2(66, v4, 808739665);
  v8 = 0;
  v9 = Pool2;
  if ( Pool2 )
  {
    v11 = Pool2 + 5;
    *Pool2 = Pool2 + 5;
    v12 = *(_DWORD *)(a1 + 24);
    *((_DWORD *)v9 + 6) = v12;
    memmove(v11, *(const void **)a1, 4LL * v12);
    v13 = (void *)(*v9 + 4LL * *((unsigned int *)v9 + 6));
    v9[1] = v13;
    v14 = *(_DWORD *)(a1 + 28);
    *((_DWORD *)v9 + 7) = v14;
    memmove(v13, *(const void **)(a1 + 8), 4LL * v14);
    v15 = (void *)(v9[1] + 4LL * *((unsigned int *)v9 + 7));
    v9[2] = v15;
    v16 = *(_DWORD *)(a1 + 32);
    *((_DWORD *)v9 + 8) = v16;
    memmove(v15, *(const void **)(a1 + 16), 4LL * v16);
    if ( a2 )
    {
      for ( i = 0; i < *((_DWORD *)v9 + 6); *(_DWORD *)(*v9 + 4 * v18) = _byteswap_ulong(*(_DWORD *)(*v9 + 4 * v18)) )
        v18 = i++;
      for ( j = 0; j < *((_DWORD *)v9 + 7); *(_DWORD *)(v9[1] + 4 * v20) = _byteswap_ulong(*(_DWORD *)(v9[1] + 4 * v20)) )
        v20 = j++;
      if ( *((_DWORD *)v9 + 8) )
      {
        do
        {
          v21 = v8++;
          *(_DWORD *)(v9[2] + 4 * v21) = _byteswap_ulong(*(_DWORD *)(v9[2] + 4 * v21));
        }
        while ( v8 < *((_DWORD *)v9 + 8) );
      }
    }
    return v9;
  }
  else
  {
    if ( (Microsoft_QuicEnableBits & 2) != 0 )
      McTemplateU0sx_EtwWriteTransfer(v7, v6, "VersionSettings", v4);
    return 0;
  }
}

```

## disassembly

```asm
0x14002c014  mov     rax, rsp
0x14002c017  mov     [rax+8], rbx
0x14002c01b  mov     [rax+10h], rbp
0x14002c01f  mov     [rax+18h], rsi
0x14002c023  mov     [rax+20h], rdi
0x14002c027  push    r14
0x14002c029  sub     rsp, 20h
0x14002c02d  mov     eax, [rcx+1Ch]
0x14002c030  mov     r14b, dl
0x14002c033  mov     r8d, [rcx+18h]
0x14002c037  mov     rsi, rcx
0x14002c03a  add     r8, rax
0x14002c03d  mov     eax, [rcx+20h]
0x14002c040  add     r8, rax
0x14002c043  mov     ecx, 42h ; 'B'
0x14002c048  lea     rbp, ds:28h[r8*4]
0x14002c050  mov     r8d, 30346351h
0x14002c056  mov     rdx, rbp
0x14002c059  call    cs:__imp_ExAllocatePool2
0x14002c060  nop     dword ptr [rax+rax+00h]
0x14002c065  xor     edi, edi
0x14002c067  mov     rbx, rax
0x14002c06a  test    rax, rax
0x14002c06d  jnz     short loc_14002C08E
0x14002c06f  test    cs:Microsoft_QuicEnableBits, 2
0x14002c076  jz      short loc_14002C087
0x14002c078  mov     r9, rbp
0x14002c07b  lea     r8, aVersionsetting; "VersionSettings"
0x14002c082  call    McTemplateU0sx_EtwWriteTransfer
0x14002c087  xor     eax, eax
0x14002c089  jmp     loc_14002C154
0x14002c08e  lea     rcx, [rax+28h]; void *
0x14002c092  mov     [rax], rcx
0x14002c095  mov     eax, [rsi+18h]
0x14002c098  mov     r8d, eax
0x14002c09b  mov     [rbx+18h], eax
0x14002c09e  mov     rdx, [rsi]; Src
0x14002c0a1  shl     r8, 2; Size
0x14002c0a5  call    memmove
0x14002c0aa  mov     rax, [rbx]
0x14002c0ad  mov     ecx, [rbx+18h]
0x14002c0b0  lea     rcx, [rax+rcx*4]; void *
0x14002c0b4  mov     [rbx+8], rcx
0x14002c0b8  mov     eax, [rsi+1Ch]
0x14002c0bb  mov     r8d, eax
0x14002c0be  mov     [rbx+1Ch], eax
0x14002c0c1  mov     rdx, [rsi+8]; Src
0x14002c0c5  shl     r8, 2; Size
0x14002c0c9  call    memmove
0x14002c0ce  mov     rax, [rbx+8]
0x14002c0d2  mov     ecx, [rbx+1Ch]
0x14002c0d5  lea     rcx, [rax+rcx*4]; void *
0x14002c0d9  mov     [rbx+10h], rcx
0x14002c0dd  mov     eax, [rsi+20h]
0x14002c0e0  mov     r8d, eax
0x14002c0e3  mov     [rbx+20h], eax
0x14002c0e6  mov     rdx, [rsi+10h]; Src
0x14002c0ea  shl     r8, 2; Size
0x14002c0ee  call    memmove
0x14002c0f3  test    r14b, r14b
0x14002c0f6  jz      short loc_14002C151
0x14002c0f8  mov     r8d, edi
0x14002c0fb  cmp     [rbx+18h], edi
0x14002c0fe  jbe     short loc_14002C117
0x14002c100  mov     rcx, [rbx]
0x14002c103  mov     edx, r8d
0x14002c106  inc     r8d
0x14002c109  mov     eax, [rcx+rdx*4]
0x14002c10c  bswap   eax
0x14002c10e  mov     [rcx+rdx*4], eax
0x14002c111  cmp     r8d, [rbx+18h]
0x14002c115  jb      short loc_14002C100
0x14002c117  mov     r8d, edi
0x14002c11a  cmp     [rbx+1Ch], edi
0x14002c11d  jbe     short loc_14002C137
0x14002c11f  mov     rcx, [rbx+8]
0x14002c123  mov     edx, r8d
0x14002c126  inc     r8d
0x14002c129  mov     eax, [rcx+rdx*4]
0x14002c12c  bswap   eax
0x14002c12e  mov     [rcx+rdx*4], eax
0x14002c131  cmp     r8d, [rbx+1Ch]
0x14002c135  jb      short loc_14002C11F
0x14002c137  cmp     [rbx+20h], edi
0x14002c13a  jbe     short loc_14002C151
0x14002c13c  mov     rcx, [rbx+10h]
0x14002c140  mov     edx, edi
0x14002c142  inc     edi
0x14002c144  mov     eax, [rcx+rdx*4]
0x14002c147  bswap   eax
0x14002c149  mov     [rcx+rdx*4], eax
0x14002c14c  cmp     edi, [rbx+20h]
0x14002c14f  jb      short loc_14002C13C
0x14002c151  mov     rax, rbx
0x14002c154  mov     rbx, [rsp+28h+arg_0]
0x14002c159  mov     rbp, [rsp+28h+arg_8]
0x14002c15e  mov     rsi, [rsp+28h+arg_10]
0x14002c163  mov     rdi, [rsp+28h+arg_18]
0x14002c168  add     rsp, 20h
0x14002c16c  pop     r14
0x14002c16e  retn
```
