# CScrub::_GetNextResumeComponent(_UNICODE_STRING *)

- ea: `0x180027a0c`
- end: `0x180027b82`
- name: `?_GetNextResumeComponent@CScrub@@AEAA_NPEAU_UNICODE_STRING@@@Z`
- size: `374`
- prototype: `bool __fastcall(CScrub *this, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002892c`

## callees

- `0x18001fde0`
- `0x180027a0c`
- `0x18002bb08`

## pseudocode

```c
bool __fastcall CScrub::_GetNextResumeComponent(CScrub *this, struct _UNICODE_STRING *a2)
{
  __int64 v4; // rcx
  unsigned __int64 v5; // rax
  WCHAR *v6; // rcx
  WCHAR *v7; // r8
  WCHAR *i; // rdx
  __int16 v9; // r8

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DDZZ(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *(_DWORD *)(**(_QWORD **)this + 36LL),
      *(_QWORD *)(*(_QWORD *)this + 64LL),
      *((_QWORD *)this + 177) + 34464LL);
  }
  v4 = *((_QWORD *)this + 177);
  v5 = *(unsigned __int16 *)(v4 + 34464);
  if ( (_WORD)v5 )
  {
    v6 = *(WCHAR **)(v4 + 34472);
    v7 = &v6[v5 >> 1];
    while ( v6 < v7 && *v6 == 92 )
      ++v6;
    for ( i = v6; i < v7; ++i )
    {
      if ( *i == 92 )
        break;
    }
    a2->Buffer = v6;
    a2->MaximumLength = (_WORD)i - (_WORD)v6;
    v9 = (_WORD)v7 - (_WORD)i;
    a2->Length = (_WORD)i - (_WORD)v6;
    *(_WORD *)(*((_QWORD *)this + 177) + 34466LL) = v9;
    *(_WORD *)(*((_QWORD *)this + 177) + 34464LL) = v9;
    *(_QWORD *)(*((_QWORD *)this + 177) + 34472LL) = i;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZZZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        (__int64)a2,
        *((_QWORD *)this + 177) + 34464LL);
    }
    LOBYTE(v5) = *(_WORD *)(*((_QWORD *)this + 177) + 34464LL) != 0;
  }
  else
  {
    a2->Length = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180027a0c  push    rbx
0x180027a0e  push    rbp
0x180027a0f  push    rsi
0x180027a10  push    rdi
0x180027a11  sub     rsp, 48h
0x180027a15  mov     rdi, rdx
0x180027a18  mov     rbx, rcx
0x180027a1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180027a22  lea     rbp, WPP_GLOBAL_Control
0x180027a29  cmp     rcx, rbp
0x180027a2c  jz      short loc_180027A7C
0x180027a2e  test    byte ptr [rcx+1Ch], 1
0x180027a32  jz      short loc_180027A7C
0x180027a34  cmp     byte ptr [rcx+19h], 4
0x180027a38  jb      short loc_180027A7C
0x180027a3a  mov     r8, [rbx]
0x180027a3d  mov     edx, 0B8h
0x180027a42  mov     rax, [rbx+588h]
0x180027a49  mov     rcx, [rcx+10h]; LoggerHandle
0x180027a4d  add     rax, 86A0h
0x180027a53  mov     [rsp+68h+var_38], rax; __int64
0x180027a58  mov     r9, [r8]
0x180027a5b  mov     rax, [r8+40h]
0x180027a5f  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x180027a66  mov     [rsp+68h+var_40], rax; __int64
0x180027a6b  mov     eax, [r9+24h]
0x180027a6f  mov     r9d, [r9+10h]
0x180027a73  mov     dword ptr [rsp+68h+var_48], eax; char
0x180027a77  call    WPP_SF_DDZZ
0x180027a7c  mov     rcx, [rbx+588h]
0x180027a83  xor     esi, esi
0x180027a85  movzx   eax, word ptr [rcx+86A0h]
0x180027a8c  test    ax, ax
0x180027a8f  jnz     short loc_180027A99
0x180027a91  mov     [rdi], si
0x180027a94  jmp     loc_180027B79
0x180027a99  mov     rcx, [rcx+86A8h]
0x180027aa0  shr     rax, 1
0x180027aa3  lea     r8, [rcx+rax*2]
0x180027aa7  jmp     short loc_180027AB3
0x180027aa9  cmp     word ptr [rcx], 5Ch ; '\'
0x180027aad  jnz     short loc_180027AB8
0x180027aaf  add     rcx, 2
0x180027ab3  cmp     rcx, r8
0x180027ab6  jb      short loc_180027AA9
0x180027ab8  mov     rdx, rcx
0x180027abb  cmp     rcx, r8
0x180027abe  jnb     short loc_180027ACF
0x180027ac0  cmp     word ptr [rdx], 5Ch ; '\'
0x180027ac4  jz      short loc_180027ACF
0x180027ac6  add     rdx, 2
0x180027aca  cmp     rdx, r8
0x180027acd  jb      short loc_180027AC0
0x180027acf  mov     [rdi+8], rcx
0x180027ad3  movzx   eax, dx
0x180027ad6  sub     ax, cx
0x180027ad9  mov     [rdi+2], ax
0x180027add  sub     r8w, dx
0x180027ae1  mov     [rdi], ax
0x180027ae4  mov     rax, [rbx+588h]
0x180027aeb  mov     [rax+86A2h], r8w
0x180027af3  mov     rax, [rbx+588h]
0x180027afa  mov     [rax+86A0h], r8w
0x180027b02  mov     rax, [rbx+588h]
0x180027b09  mov     [rax+86A8h], rdx
0x180027b10  mov     rcx, cs:WPP_GLOBAL_Control
0x180027b17  cmp     rcx, rbp
0x180027b1a  jz      short loc_180027B68
0x180027b1c  test    byte ptr [rcx+1Ch], 1
0x180027b20  jz      short loc_180027B68
0x180027b22  cmp     byte ptr [rcx+19h], 4
0x180027b26  jb      short loc_180027B68
0x180027b28  mov     r8, [rbx]
0x180027b2b  mov     edx, 0B9h
0x180027b30  mov     rax, [rbx+588h]
0x180027b37  mov     rcx, [rcx+10h]; LoggerHandle
0x180027b3b  add     rax, 86A0h
0x180027b41  mov     [rsp+68h+var_30], rax; __int64
0x180027b46  mov     r9, [r8]
0x180027b49  mov     rax, [r8+40h]
0x180027b4d  mov     [rsp+68h+var_38], rdi; __int64
0x180027b52  mov     [rsp+68h+var_40], rax; __int64
0x180027b57  mov     eax, [r9+24h]
0x180027b5b  mov     r9d, [r9+10h]
0x180027b5f  mov     dword ptr [rsp+68h+var_48], eax; char
0x180027b63  call    WPP_SF_DDZZZ
0x180027b68  mov     rax, [rbx+588h]
0x180027b6f  cmp     [rax+86A0h], si
0x180027b76  setnbe  al
0x180027b79  add     rsp, 48h
0x180027b7d  pop     rdi
0x180027b7e  pop     rsi
0x180027b7f  pop     rbp
0x180027b80  pop     rbx
0x180027b81  retn
```
