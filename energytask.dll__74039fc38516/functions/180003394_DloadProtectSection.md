# DloadProtectSection

- ea: `0x180003394`
- end: `0x18000346f`
- name: `DloadProtectSection`
- size: `219`
- prototype: `void __fastcall(DWORD flNewProtect, PDWORD lpflOldProtect)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003480`

## callees

- `0x1800032d4`
- `0x180003394`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18000345e`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18000345e`

## pseudocode

```c
void __fastcall DloadProtectSection(DWORD flNewProtect, PDWORD lpflOldProtect)
{
  __int64 v4; // r9
  unsigned int v5; // r10d
  int *v6; // rcx
  unsigned int v7; // r9d
  __int64 v8; // rdx
  unsigned __int64 v9; // r8
  char *v10; // rdi
  bool v11; // sf
  SIZE_T v12; // rbx

  if ( *(_DWORD *)&byte_180000040[(int)off_18000003C + 68] <= 0xDu )
    goto LABEL_7;
  v4 = *(unsigned int *)&byte_180000040[(int)off_18000003C + 176];
  if ( !(_DWORD)v4 )
    goto LABEL_7;
  v5 = *(_DWORD *)((char *)&word_18000000C + v4);
  v6 = (int *)((char *)&_ImageBase
             + (int)off_18000003C
             + *(unsigned __int16 *)((char *)&word_180000014 + (int)off_18000003C)
             + 24);
  v7 = 0;
  if ( !*(__int16 *)((char *)&word_180000006 + (int)off_18000003C) )
    goto LABEL_7;
  while ( 1 )
  {
    v8 = (unsigned int)v6[3];
    if ( v5 >= (unsigned int)v8 )
    {
      v9 = (unsigned int)v6[2];
      if ( v5 < (int)v9 + (int)v8 )
        break;
    }
    ++v7;
    v6 += 10;
    if ( v7 >= *(unsigned __int16 *)((char *)&word_180000006 + (int)off_18000003C) )
      goto LABEL_7;
  }
  v10 = (char *)&_ImageBase + v8;
  if ( (WCHAR *)((char *)&_ImageBase + v8) )
  {
    if ( DloadSectionCommitPermanent )
    {
      v12 = (unsigned int)v6[2];
    }
    else
    {
      v11 = v6[9] < 0;
      DloadSectionCommitPermanent = 1;
      if ( !v11 )
        __fastfail(0x19u);
      v12 = v9;
      DloadMakePermanentImageCommit((unsigned __int64)v10, v9);
    }
    if ( !VirtualProtect(v10, v12, flNewProtect, lpflOldProtect) )
      __fastfail(0x19u);
  }
  else
  {
LABEL_7:
    *lpflOldProtect = 4;
  }
}

```

## disassembly

```asm
0x180003394  push    rbx
0x180003396  push    rbp
0x180003397  push    rsi
0x180003398  push    rdi
0x180003399  sub     rsp, 28h
0x18000339d  movsxd  r8, cs:off_18000003C
0x1800033a4  lea     rbx, __ImageBase
0x1800033ab  add     r8, rbx
0x1800033ae  mov     rsi, rdx
0x1800033b1  mov     ebp, ecx
0x1800033b3  cmp     dword ptr [r8+84h], 0Dh
0x1800033bb  jbe     short loc_180003408
0x1800033bd  mov     r9d, [r8+0F0h]
0x1800033c4  test    r9d, r9d
0x1800033c7  jz      short loc_180003408
0x1800033c9  movzx   ecx, word ptr [r8+14h]
0x1800033ce  mov     r10d, [r9+rbx+0Ch]
0x1800033d3  add     rcx, 18h
0x1800033d7  movzx   r11d, word ptr [r8+6]
0x1800033dc  add     rcx, r8
0x1800033df  xor     r9d, r9d
0x1800033e2  test    r11d, r11d
0x1800033e5  jz      short loc_180003408
0x1800033e7  mov     edx, [rcx+0Ch]
0x1800033ea  cmp     r10d, edx
0x1800033ed  jb      short loc_1800033FC
0x1800033ef  mov     r8d, [rcx+8]
0x1800033f3  lea     eax, [r8+rdx]
0x1800033f7  cmp     r10d, eax
0x1800033fa  jb      short loc_180003417
0x1800033fc  inc     r9d
0x1800033ff  add     rcx, 28h ; '('
0x180003403  cmp     r9d, r11d
0x180003406  jb      short loc_1800033E7
0x180003408  mov     dword ptr [rsi], 4
0x18000340e  add     rsp, 28h
0x180003412  pop     rdi
0x180003413  pop     rsi
0x180003414  pop     rbp
0x180003415  pop     rbx
0x180003416  retn
0x180003417  mov     rdi, rdx
0x18000341a  add     rdi, rbx
0x18000341d  jz      short loc_180003408
0x18000341f  cmp     cs:DloadSectionCommitPermanent, 0
0x180003426  jnz     short loc_18000344F
0x180003428  cmp     dword ptr [rcx+24h], 0
0x18000342c  mov     cs:DloadSectionCommitPermanent, 1
0x180003436  jl      short loc_18000343F
0x180003438  mov     ecx, 19h
0x18000343d  int     29h; Win8: RtlFailFast(ecx)
0x18000343f  mov     rdx, r8
0x180003442  mov     rcx, rdi
0x180003445  mov     rbx, r8
0x180003448  call    DloadMakePermanentImageCommit
0x18000344d  jmp     short loc_180003452
0x18000344f  mov     rbx, r8
0x180003452  mov     r9, rsi; lpflOldProtect
0x180003455  mov     r8d, ebp; flNewProtect
0x180003458  mov     rdx, rbx; dwSize
0x18000345b  mov     rcx, rdi; lpAddress
0x18000345e  call    cs:__imp_VirtualProtect
0x180003464  test    eax, eax
0x180003466  jnz     short loc_18000340E
0x180003468  lea     ecx, [rax+19h]
0x18000346b  int     29h; Win8: RtlFailFast(ecx)
0x18000346d  jmp     short loc_18000340E
```
