# IP_RESTRICTION_LIST_ENTRY::SetPrefixIpMask(ushort const *)

- ea: `0x18000474c`
- end: `0x1800048b9`
- name: `?SetPrefixIpMask@IP_RESTRICTION_LIST_ENTRY@@AEAAJPEBG@Z`
- size: `365`
- prototype: `int(IP_RESTRICTION_LIST_ENTRY *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004608`

## callees

- `0x180003ce8`
- `0x18000474c`

## import_xrefs

- `msvcrt!_wtoi` at `0x18000476a`
- `msvcrt!_wtoi` at `0x18000476a`
- `WS2_32!FreeAddrInfoW` at `0x1800048a1`
- `WS2_32!FreeAddrInfoW` at `0x1800048a1`
- `WS2_32!__imp_htonl` at `0x1800047c6`
- `WS2_32!__imp_htonl` at `0x1800047c6`

## pseudocode

```c
__int64 __fastcall IP_RESTRICTION_LIST_ENTRY::SetPrefixIpMask(
        IP_RESTRICTION_LIST_ENTRY *this,
        const unsigned __int16 *a2)
{
  unsigned int v3; // eax
  IP_RESTRICTION_LIST_ENTRY *v4; // rcx
  unsigned int v5; // esi
  int AddrInfoHelper; // ebx
  u_long v7; // eax
  struct sockaddr *ai_addr; // rcx
  __int128 v9; // xmm1
  __int64 v10; // rdx
  __int64 v11; // r8
  PADDRINFOW pAddrInfo; // [rsp+40h] [rbp+18h] BYREF

  pAddrInfo = 0;
  v3 = _wtoi(a2);
  v5 = v3;
  if ( v3 > 0x80 )
    goto LABEL_20;
  if ( *((_DWORD *)this + 17) == 2 )
  {
    if ( v3 <= 0x20 )
    {
      AddrInfoHelper = IP_RESTRICTION_LIST_ENTRY::GetAddrInfoHelper(v4, L"255.255.255.255", &pAddrInfo);
      if ( AddrInfoHelper < 0 )
        goto LABEL_21;
      *((_OWORD *)this + 2) = *pAddrInfo->ai_addr;
      v7 = htonl(-1 << (32 - v5));
      *((_DWORD *)this + 9) = v7;
      if ( v5 == 32 )
        *((_DWORD *)this + 15) = 1;
      else
        *((_DWORD *)this + 2) &= v7;
      goto LABEL_8;
    }
    goto LABEL_20;
  }
  if ( *((_DWORD *)this + 17) != 23 )
  {
LABEL_20:
    AddrInfoHelper = -2147024809;
    goto LABEL_21;
  }
  AddrInfoHelper = IP_RESTRICTION_LIST_ENTRY::GetAddrInfoHelper(
                     v4,
                     L"ffff:ffff:ffff:ffff:ffff:ffff:ffff:ffff",
                     &pAddrInfo);
  if ( AddrInfoHelper >= 0 )
  {
    ai_addr = pAddrInfo->ai_addr;
    *((struct sockaddr *)this + 2) = *ai_addr;
    v9 = *(_OWORD *)&ai_addr->sa_data[10];
    *((_DWORD *)this + 15) = 0;
    *(_OWORD *)((char *)this + 44) = v9;
    if ( v5 == 128 )
    {
      LODWORD(v10) = 8;
      *((_DWORD *)this + 15) = 1;
    }
    else
    {
      v10 = v5 >> 4;
      if ( (unsigned int)v10 < 8 )
        *((_WORD *)this + v10 + 20) <<= 16 - (v5 & 0xF);
    }
    v11 = 0;
    do
    {
      if ( (unsigned int)v11 > (unsigned int)v10 )
        *((_WORD *)this + v11 + 20) = 0;
      *((_WORD *)this + v11 + 6) &= *((_WORD *)this + (unsigned int)v11 + 20);
      v11 = (unsigned int)(v11 + 1);
    }
    while ( (unsigned int)v11 < 8 );
LABEL_8:
    AddrInfoHelper = 0;
  }
LABEL_21:
  if ( pAddrInfo )
    FreeAddrInfoW(pAddrInfo);
  return (unsigned int)AddrInfoHelper;
}

```

## disassembly

```asm
0x18000474c  mov     [rsp+arg_0], rbx
0x180004751  mov     [rsp+arg_8], rsi
0x180004756  push    rdi
0x180004757  sub     rsp, 20h
0x18000475b  mov     rdi, rcx
0x18000475e  mov     [rsp+28h+pAddrInfo], 0
0x180004767  mov     rcx, rdx; String
0x18000476a  call    cs:__imp__wtoi
0x180004770  mov     esi, eax
0x180004772  cmp     eax, 80h
0x180004777  ja      loc_180004892
0x18000477d  cmp     dword ptr [rdi+44h], 2
0x180004781  jnz     short loc_1800047E7
0x180004783  cmp     eax, 20h ; ' '
0x180004786  ja      loc_180004892
0x18000478c  lea     r8, [rsp+28h+pAddrInfo]; struct addrinfoW **
0x180004791  lea     rdx, a255255255255; "255.255.255.255"
0x180004798  call    ?GetAddrInfoHelper@IP_RESTRICTION_LIST_ENTRY@@AEAAJPEBGPEAPEAUaddrinfoW@@@Z; IP_RESTRICTION_LIST_ENTRY::GetAddrInfoHelper(ushort const *,addrinfoW * *)
0x18000479d  mov     ebx, eax
0x18000479f  test    eax, eax
0x1800047a1  js      loc_180004897
0x1800047a7  mov     rax, [rsp+28h+pAddrInfo]
0x1800047ac  mov     rcx, [rax+20h]
0x1800047b0  or      eax, 0FFFFFFFFh
0x1800047b3  movups  xmm0, xmmword ptr [rcx]
0x1800047b6  mov     ecx, 20h ; ' '
0x1800047bb  sub     ecx, esi
0x1800047bd  shl     eax, cl
0x1800047bf  mov     ecx, eax; hostlong
0x1800047c1  movdqu  xmmword ptr [rdi+20h], xmm0
0x1800047c6  call    cs:__imp_htonl
0x1800047cc  mov     [rdi+24h], eax
0x1800047cf  cmp     esi, 20h ; ' '
0x1800047d2  jnz     short loc_1800047DD
0x1800047d4  mov     dword ptr [rdi+3Ch], 1
0x1800047db  jmp     short loc_1800047E0
0x1800047dd  and     [rdi+8], eax
0x1800047e0  xor     ebx, ebx
0x1800047e2  jmp     loc_180004897
0x1800047e7  cmp     dword ptr [rdi+44h], 17h
0x1800047eb  jnz     loc_180004892
0x1800047f1  lea     r8, [rsp+28h+pAddrInfo]; struct addrinfoW **
0x1800047f6  lea     rdx, aFfffFfffFfffFf; "ffff:ffff:ffff:ffff:ffff:ffff:ffff:ffff"
0x1800047fd  call    ?GetAddrInfoHelper@IP_RESTRICTION_LIST_ENTRY@@AEAAJPEBGPEAPEAUaddrinfoW@@@Z; IP_RESTRICTION_LIST_ENTRY::GetAddrInfoHelper(ushort const *,addrinfoW * *)
0x180004802  mov     ebx, eax
0x180004804  test    eax, eax
0x180004806  js      loc_180004897
0x18000480c  mov     rax, [rsp+28h+pAddrInfo]
0x180004811  mov     rcx, [rax+20h]
0x180004815  movups  xmm0, xmmword ptr [rcx]
0x180004818  movups  xmmword ptr [rdi+20h], xmm0
0x18000481c  movups  xmm1, xmmword ptr [rcx+0Ch]
0x180004820  mov     dword ptr [rdi+3Ch], 0
0x180004827  movups  xmmword ptr [rdi+2Ch], xmm1
0x18000482b  cmp     esi, 80h
0x180004831  jnz     short loc_180004841
0x180004833  shr     esi, 4
0x180004836  mov     edx, esi
0x180004838  mov     dword ptr [rdi+3Ch], 1
0x18000483f  jmp     short loc_18000485A
0x180004841  mov     edx, esi
0x180004843  shr     edx, 4
0x180004846  cmp     edx, 8
0x180004849  jnb     short loc_18000485A
0x18000484b  and     esi, 0Fh
0x18000484e  mov     ecx, 10h
0x180004853  sub     ecx, esi
0x180004855  shl     word ptr [rdi+rdx*2+28h], cl
0x18000485a  xor     r8d, r8d
0x18000485d  lea     r10d, [r8+14h]
0x180004861  mov     r9d, r8d
0x180004864  mov     rcx, r10
0x180004867  cmp     r8d, edx
0x18000486a  jbe     short loc_180004874
0x18000486c  xor     eax, eax
0x18000486e  mov     [rdi+r8*2+28h], ax
0x180004874  mov     rax, r9
0x180004877  add     rax, rcx
0x18000487a  movzx   ecx, word ptr [rdi+rax*2]
0x18000487e  and     [rdi+r8*2+0Ch], cx
0x180004884  inc     r8d
0x180004887  cmp     r8d, 8
0x18000488b  jb      short loc_180004861
0x18000488d  jmp     loc_1800047E0
0x180004892  mov     ebx, 80070057h
0x180004897  mov     rcx, [rsp+28h+pAddrInfo]; pAddrInfo
0x18000489c  test    rcx, rcx
0x18000489f  jz      short loc_1800048A7
0x1800048a1  call    cs:__imp_FreeAddrInfoW
0x1800048a7  mov     rsi, [rsp+28h+arg_8]
0x1800048ac  mov     eax, ebx
0x1800048ae  mov     rbx, [rsp+28h+arg_0]
0x1800048b3  add     rsp, 20h
0x1800048b7  pop     rdi
0x1800048b8  retn
```
