# tson::input_archive::search(void)

- ea: `0x180019310`
- end: `0x18001940e`
- name: `?search@input_archive@tson@@AEAA_NXZ`
- size: `254`
- prototype: `bool __fastcall(tson::input_archive *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000651c`
- `0x1800177e4`
- `0x180017904`
- `0x180017a34`
- `0x180019c60`

## callees

- `0x180019310`
- `0x180021ff0`

## pseudocode

```c
char __fastcall tson::input_archive::search(tson::input_archive *this)
{
  const char *v1; // r9
  __int64 v3; // rax
  char *v4; // rax
  __int64 v5; // rcx
  unsigned __int8 *v6; // rax
  unsigned __int8 v7; // al
  _BYTE *v8; // rdx
  _BYTE *v9; // r8
  unsigned __int64 v11; // rax

  v1 = (const char *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  *((_BYTE *)this + 25) = 0;
  v3 = *((_QWORD *)this + 17);
  if ( v3 )
  {
    v4 = (char *)this + 4 * v3 + 32;
  }
  else
  {
    *((_BYTE *)this + 32) = 1;
    v4 = (char *)this + 36;
  }
  if ( *(_DWORD *)v4 == 1 )
    return 1;
  v5 = *(_QWORD *)this;
  v6 = *(unsigned __int8 **)(v5 + 8);
  if ( (unsigned __int64)v6 >= *(_QWORD *)(v5 + 16) )
    v7 = 0;
  else
    v7 = *v6;
  if ( v7 != 6 )
  {
    if ( (unsigned int)v7 - 7 >= 2 )
    {
      if ( !v1 )
      {
        v1 = "-";
        *((_BYTE *)this + 24) = 1;
      }
      v8 = *(_BYTE **)(v5 + 8);
      v9 = &v8[*((unsigned __int8 *)this + 24) + 2];
      if ( (unsigned __int64)v9 > *(_QWORD *)(v5 + 16) )
      {
        *(_BYTE *)(v5 + 24) = 1;
      }
      else
      {
        *(_QWORD *)(v5 + 8) = v9;
        if ( v8 )
        {
          if ( *v8 != 5 && *((int *)this + 2) >= 0 )
            *((_DWORD *)this + 2) = -2147023267;
          if ( (v8[1] != *((_BYTE *)this + 24) || memcmp_0(v1, v8 + 2, *((unsigned __int8 *)this + 24)))
            && *((int *)this + 2) >= 0 )
          {
            *((_DWORD *)this + 2) = -2147023092;
          }
        }
      }
      return 1;
    }
    *((_BYTE *)this + 25) = 1;
  }
  v11 = *(_QWORD *)(v5 + 8);
  if ( v11 >= *(_QWORD *)(v5 + 16) )
    *(_BYTE *)(v5 + 24) = 1;
  else
    *(_QWORD *)(v5 + 8) = v11 + 1;
  return 0;
}

```

## disassembly

```asm
0x180019310  push    rbx
0x180019312  sub     rsp, 20h
0x180019316  mov     r9, [rcx+10h]
0x18001931a  mov     rbx, rcx
0x18001931d  and     qword ptr [rcx+10h], 0
0x180019322  mov     byte ptr [rcx+19h], 0
0x180019326  mov     rax, [rcx+88h]
0x18001932d  test    rax, rax
0x180019330  jz      short loc_18001933C
0x180019332  add     rax, 8
0x180019336  lea     rax, [rcx+rax*4]
0x18001933a  jmp     short loc_180019344
0x18001933c  mov     byte ptr [rcx+20h], 1
0x180019340  lea     rax, [rcx+24h]
0x180019344  cmp     dword ptr [rax], 1
0x180019347  jz      loc_1800193E0
0x18001934d  mov     rcx, [rcx]
0x180019350  mov     rax, [rcx+8]
0x180019354  cmp     rax, [rcx+10h]
0x180019358  jnb     short loc_18001935E
0x18001935a  mov     al, [rax]
0x18001935c  jmp     short loc_180019360
0x18001935e  xor     al, al
0x180019360  movzx   edx, al
0x180019363  sub     edx, 6
0x180019366  jz      loc_1800193F3
0x18001936c  sub     edx, 1
0x18001936f  jz      short loc_1800193EF
0x180019371  cmp     edx, 1
0x180019374  jz      short loc_1800193EF
0x180019376  test    r9, r9
0x180019379  jnz     short loc_180019386
0x18001937b  lea     r9, asc_180026544; "-"
0x180019382  mov     byte ptr [rbx+18h], 1
0x180019386  movzx   r8d, byte ptr [rbx+18h]
0x18001938b  mov     rdx, [rcx+8]
0x18001938f  add     r8, 2
0x180019393  add     r8, rdx
0x180019396  cmp     r8, [rcx+10h]
0x18001939a  ja      short loc_1800193E9
0x18001939c  mov     [rcx+8], r8
0x1800193a0  test    rdx, rdx
0x1800193a3  jz      short loc_1800193E0
0x1800193a5  cmp     byte ptr [rdx], 5
0x1800193a8  jz      short loc_1800193B7
0x1800193aa  cmp     dword ptr [rbx+8], 0
0x1800193ae  jl      short loc_1800193B7
0x1800193b0  mov     dword ptr [rbx+8], 8007065Dh
0x1800193b7  movzx   eax, byte ptr [rbx+18h]
0x1800193bb  cmp     [rdx+1], al
0x1800193be  jnz     short loc_1800193D3
0x1800193c0  mov     r8d, eax; Size
0x1800193c3  add     rdx, 2; Buf2
0x1800193c7  mov     rcx, r9; Buf1
0x1800193ca  call    memcmp_0
0x1800193cf  test    eax, eax
0x1800193d1  jz      short loc_1800193E0
0x1800193d3  cmp     dword ptr [rbx+8], 0
0x1800193d7  jl      short loc_1800193E0
0x1800193d9  mov     dword ptr [rbx+8], 8007070Ch
0x1800193e0  mov     al, 1
0x1800193e2  add     rsp, 20h
0x1800193e6  pop     rbx
0x1800193e7  retn
0x1800193e9  mov     byte ptr [rcx+18h], 1
0x1800193ed  jmp     short loc_1800193E0
0x1800193ef  mov     byte ptr [rbx+19h], 1
0x1800193f3  mov     rax, [rcx+8]
0x1800193f7  cmp     rax, [rcx+10h]
0x1800193fb  jnb     short loc_180019406
0x1800193fd  inc     rax
0x180019400  mov     [rcx+8], rax
0x180019404  jmp     short loc_18001940A
0x180019406  mov     byte ptr [rcx+18h], 1
0x18001940a  xor     al, al
0x18001940c  jmp     short loc_1800193E2
```
