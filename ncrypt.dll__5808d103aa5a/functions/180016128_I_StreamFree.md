# I_StreamFree

- ea: `0x180016128`
- end: `0x180016204`
- name: `I_StreamFree`
- size: `220`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180002400`
- `0x180003460`
- `0x1800160b0`
- `0x18001d460`

## callees

- `0x180007958`
- `0x180007ae0`
- `0x180016128`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall I_StreamFree(__int64 a1, int a2, int a3)
{
  _BYTE *v4; // rax
  __int64 i; // rcx
  _DWORD *v6; // rcx
  __int64 v7; // rdi
  _BYTE *v9; // rax
  __int64 v10; // rcx

  if ( *(_DWORD *)(a1 + 36) )
  {
    if ( *(_QWORD *)(a1 + 72) )
    {
      v4 = *(_BYTE **)(a1 + 128);
      if ( v4 )
      {
        for ( i = *(unsigned int *)(a1 + 120); i; --i )
          *v4++ = 0;
      }
      v6 = *(_DWORD **)(a1 + 72);
      if ( v6 )
        NCryptMsgClose(v6, a2, a3);
    }
    v7 = a1 + 8;
  }
  else
  {
    v7 = a1 + 8;
    if ( *(_QWORD *)(a1 + 144) )
      (*(void (**)(void))(*(_QWORD *)v7 + 16LL))();
    if ( *(_QWORD *)(a1 + 136) )
    {
      v9 = *(_BYTE **)(a1 + 176);
      if ( v9 )
      {
        v10 = *(unsigned int *)(a1 + 184);
        if ( *(_DWORD *)(a1 + 184) )
        {
          do
          {
            *v9++ = 0;
            --v10;
          }
          while ( v10 );
        }
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 176));
      }
      NCryptCloseProtectionDescriptor(*(_QWORD *)(a1 + 136), a2, a3);
    }
  }
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(a1);
}

```

## disassembly

```asm
0x180016128  mov     [rsp+arg_0], rbx
0x18001612d  push    rdi
0x18001612e  sub     rsp, 20h
0x180016132  cmp     dword ptr [rcx+24h], 0
0x180016136  mov     rbx, rcx
0x180016139  jz      short loc_18001618C
0x18001613b  cmp     qword ptr [rcx+48h], 0
0x180016140  jz      short loc_18001616F
0x180016142  mov     rax, [rcx+80h]
0x180016149  test    rax, rax
0x18001614c  jz      short loc_180016162
0x18001614e  mov     ecx, [rcx+78h]
0x180016151  test    rcx, rcx
0x180016154  jz      short loc_180016162
0x180016156  mov     byte ptr [rax], 0
0x180016159  inc     rax
0x18001615c  sub     rcx, 1
0x180016160  jnz     short loc_180016156
0x180016162  mov     rcx, [rbx+48h]
0x180016166  test    rcx, rcx
0x180016169  jnz     loc_1800161FA
0x18001616f  lea     rdi, [rbx+8]
0x180016173  mov     rax, [rdi]
0x180016176  mov     rcx, rbx
0x180016179  mov     rax, [rax+10h]
0x18001617d  mov     rbx, [rsp+28h+arg_0]
0x180016182  add     rsp, 20h
0x180016186  pop     rdi
0x180016187  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18001618c  mov     rcx, [rcx+90h]
0x180016193  lea     rdi, [rbx+8]
0x180016197  test    rcx, rcx
0x18001619a  jz      short loc_1800161A8
0x18001619c  mov     rax, [rdi]
0x18001619f  mov     rax, [rax+10h]
0x1800161a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161a8  cmp     qword ptr [rbx+88h], 0
0x1800161b0  jz      short loc_180016173
0x1800161b2  mov     rax, [rbx+0B0h]
0x1800161b9  test    rax, rax
0x1800161bc  jz      short loc_1800161E9
0x1800161be  mov     ecx, [rbx+0B8h]
0x1800161c4  test    rcx, rcx
0x1800161c7  jz      short loc_1800161D5
0x1800161c9  mov     byte ptr [rax], 0
0x1800161cc  inc     rax
0x1800161cf  sub     rcx, 1
0x1800161d3  jnz     short loc_1800161C9
0x1800161d5  mov     rax, [rbx+8]
0x1800161d9  mov     rcx, [rbx+0B0h]
0x1800161e0  mov     rax, [rax+10h]
0x1800161e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161e9  mov     rcx, [rbx+88h]
0x1800161f0  call    NCryptCloseProtectionDescriptor
0x1800161f5  jmp     loc_180016173
0x1800161fa  call    NCryptMsgClose
0x1800161ff  jmp     loc_18001616F
```
