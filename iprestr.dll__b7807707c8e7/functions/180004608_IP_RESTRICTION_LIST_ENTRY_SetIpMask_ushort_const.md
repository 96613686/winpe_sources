# IP_RESTRICTION_LIST_ENTRY::SetIpMask(ushort const *)

- ea: `0x180004608`
- end: `0x180004745`
- name: `?SetIpMask@IP_RESTRICTION_LIST_ENTRY@@QEAAJPEBG@Z`
- size: `317`
- prototype: `__int64 __fastcall(IP_RESTRICTION_LIST_ENTRY *__hidden this, IP_RESTRICTION_LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800034fc`

## callees

- `0x180003ce8`
- `0x180004608`
- `0x18000474c`

## import_xrefs

- `WS2_32!FreeAddrInfoW` at `0x180004655`
- `WS2_32!FreeAddrInfoW` at `0x180004655`

## pseudocode

```c
__int64 __fastcall IP_RESTRICTION_LIST_ENTRY::SetIpMask(IP_RESTRICTION_LIST_ENTRY *this, IP_RESTRICTION_LIST_ENTRY *a2)
{
  unsigned __int16 v2; // ax
  IP_RESTRICTION_LIST_ENTRY *v4; // rcx
  int v5; // eax
  struct addrinfoW *v6; // r8
  unsigned int v7; // edi
  int AddrInfoHelper; // eax
  struct sockaddr *ai_addr; // rax
  BOOL v11; // ecx
  int v12; // eax
  __int64 v13; // rdx
  __int128 v14; // xmm1
  PADDRINFOW pAddrInfo; // [rsp+58h] [rbp+10h] BYREF

  v2 = *(_WORD *)a2;
  pAddrInfo = 0;
  if ( !v2 )
  {
LABEL_5:
    v5 = IP_RESTRICTION_LIST_ENTRY::SetPrefixIpMask(this, (const unsigned __int16 *)a2);
    v6 = pAddrInfo;
    v7 = v5;
    goto LABEL_6;
  }
  v4 = a2;
  while ( (unsigned __int16)(v2 - 48) <= 9u )
  {
    v4 = (IP_RESTRICTION_LIST_ENTRY *)((char *)v4 + 2);
    v2 = *(_WORD *)v4;
    if ( !*(_WORD *)v4 )
      goto LABEL_5;
  }
  AddrInfoHelper = IP_RESTRICTION_LIST_ENTRY::GetAddrInfoHelper(v4, (const unsigned __int16 *)a2, &pAddrInfo);
  v6 = pAddrInfo;
  v7 = AddrInfoHelper;
  if ( AddrInfoHelper >= 0 )
  {
    ai_addr = pAddrInfo->ai_addr;
    if ( ai_addr->sa_family == 2 )
    {
      v11 = 1;
      *((struct sockaddr *)this + 2) = *ai_addr;
      v12 = *((_DWORD *)this + 9);
      if ( v12 == -1 )
        *((_DWORD *)this + 15) = 1;
      *((_DWORD *)this + 2) &= v12;
    }
    else
    {
      if ( ai_addr->sa_family != 23 )
      {
        v7 = -2147024809;
        goto LABEL_6;
      }
      v11 = 1;
      v13 = 0;
      *((struct sockaddr *)this + 2) = *ai_addr;
      v14 = *(_OWORD *)&ai_addr->sa_data[10];
      *((_DWORD *)this + 15) = 1;
      *(_OWORD *)((char *)this + 44) = v14;
      do
      {
        if ( *((_WORD *)this + v13 + 20) != 0xFFFF )
          *((_DWORD *)this + 15) = 0;
        *((_WORD *)this + v13 + 6) &= *((_WORD *)this + v13 + 20);
        ++v13;
      }
      while ( v13 != 8 );
    }
    if ( !*((_DWORD *)this + 15) )
    {
      if ( *((_WORD *)this + 16) == 23 )
      {
        if ( *((_WORD *)this + 20)
          || *((_WORD *)this + 21)
          || *((_WORD *)this + 22)
          || *((_WORD *)this + 23)
          || *((_WORD *)this + 24)
          || *((_WORD *)this + 25)
          || *((_WORD *)this + 26)
          || *((_WORD *)this + 27) )
        {
          v11 = 0;
        }
      }
      else
      {
        v11 = *((_DWORD *)this + 9) == 0;
      }
      *((_DWORD *)this + 15) = v11;
    }
    v7 = 0;
  }
LABEL_6:
  if ( v6 )
    FreeAddrInfoW(v6);
  return v7;
}

```

## disassembly

```asm
0x180004608  push    rbx
0x18000460a  push    rbp
0x18000460b  push    rsi
0x18000460c  push    rdi
0x18000460d  sub     rsp, 28h
0x180004611  movzx   eax, word ptr [rdx]
0x180004614  xor     esi, esi
0x180004616  mov     [rsp+48h+pAddrInfo], rsi
0x18000461b  mov     rbx, rcx
0x18000461e  test    ax, ax
0x180004621  jz      short loc_18000463E
0x180004623  mov     rcx, rdx; this
0x180004626  lea     ebp, [rsi+2]
0x180004629  sub     ax, 30h ; '0'
0x18000462d  cmp     ax, 9
0x180004631  ja      short loc_180004666
0x180004633  add     rcx, rbp
0x180004636  movzx   eax, word ptr [rcx]
0x180004639  test    ax, ax
0x18000463c  jnz     short loc_180004629
0x18000463e  mov     rcx, rbx; this
0x180004641  call    ?SetPrefixIpMask@IP_RESTRICTION_LIST_ENTRY@@AEAAJPEBG@Z; IP_RESTRICTION_LIST_ENTRY::SetPrefixIpMask(ushort const *)
0x180004646  mov     r8, [rsp+48h+pAddrInfo]
0x18000464b  mov     edi, eax
0x18000464d  test    r8, r8
0x180004650  jz      short loc_18000465B
0x180004652  mov     rcx, r8; pAddrInfo
0x180004655  call    cs:__imp_FreeAddrInfoW
0x18000465b  mov     eax, edi
0x18000465d  add     rsp, 28h
0x180004661  pop     rdi
0x180004662  pop     rsi
0x180004663  pop     rbp
0x180004664  pop     rbx
0x180004665  retn
0x180004666  lea     r8, [rsp+48h+pAddrInfo]; struct addrinfoW **
0x18000466b  call    ?GetAddrInfoHelper@IP_RESTRICTION_LIST_ENTRY@@AEAAJPEBGPEAPEAUaddrinfoW@@@Z; IP_RESTRICTION_LIST_ENTRY::GetAddrInfoHelper(ushort const *,addrinfoW * *)
0x180004670  mov     r8, [rsp+48h+pAddrInfo]
0x180004675  mov     edi, eax
0x180004677  test    eax, eax
0x180004679  js      short loc_18000464D
0x18000467b  mov     rax, [r8+20h]
0x18000467f  cmp     [rax], bp
0x180004682  jnz     short loc_1800046A1
0x180004684  movups  xmm0, xmmword ptr [rax]
0x180004687  mov     ecx, 1
0x18000468c  movdqu  xmmword ptr [rbx+20h], xmm0
0x180004691  mov     eax, [rbx+24h]
0x180004694  cmp     eax, 0FFFFFFFFh
0x180004697  jnz     short loc_18000469C
0x180004699  mov     [rbx+3Ch], ecx
0x18000469c  and     [rbx+8], eax
0x18000469f  jmp     short loc_1800046E7
0x1800046a1  cmp     word ptr [rax], 17h
0x1800046a5  jnz     loc_18000473B
0x1800046ab  movups  xmm0, xmmword ptr [rax]
0x1800046ae  mov     ecx, 1
0x1800046b3  mov     rdx, rsi
0x1800046b6  movups  xmmword ptr [rbx+20h], xmm0
0x1800046ba  movups  xmm1, xmmword ptr [rax+0Ch]
0x1800046be  mov     [rbx+3Ch], ecx
0x1800046c1  movups  xmmword ptr [rbx+2Ch], xmm1
0x1800046c5  mov     eax, 0FFFFh
0x1800046ca  cmp     [rbx+rdx*2+28h], ax
0x1800046cf  jz      short loc_1800046D4
0x1800046d1  mov     [rbx+3Ch], esi
0x1800046d4  movzx   eax, word ptr [rbx+rdx*2+28h]
0x1800046d9  and     [rbx+rdx*2+0Ch], ax
0x1800046de  add     rdx, rcx
0x1800046e1  cmp     rdx, 8
0x1800046e5  jnz     short loc_1800046C5
0x1800046e7  cmp     [rbx+3Ch], esi
0x1800046ea  jnz     short loc_180004734
0x1800046ec  cmp     word ptr [rbx+20h], 17h
0x1800046f1  jnz     short loc_180004727
0x1800046f3  cmp     [rbx+28h], si
0x1800046f7  jnz     short loc_180004723
0x1800046f9  cmp     [rbx+2Ah], si
0x1800046fd  jnz     short loc_180004723
0x1800046ff  cmp     [rbx+2Ch], si
0x180004703  jnz     short loc_180004723
0x180004705  cmp     [rbx+2Eh], si
0x180004709  jnz     short loc_180004723
0x18000470b  cmp     [rbx+30h], si
0x18000470f  jnz     short loc_180004723
0x180004711  cmp     [rbx+32h], si
0x180004715  jnz     short loc_180004723
0x180004717  cmp     [rbx+34h], si
0x18000471b  jnz     short loc_180004723
0x18000471d  cmp     [rbx+36h], si
0x180004721  jz      short loc_180004731
0x180004723  mov     ecx, esi
0x180004725  jmp     short loc_180004731
0x180004727  cmp     [rbx+24h], esi
0x18000472a  mov     eax, esi
0x18000472c  setz    al
0x18000472f  mov     ecx, eax
0x180004731  mov     [rbx+3Ch], ecx
0x180004734  mov     edi, esi
0x180004736  jmp     loc_18000464D
0x18000473b  mov     edi, 80070057h
0x180004740  jmp     loc_18000464D
```
