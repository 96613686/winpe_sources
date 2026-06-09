# LipsTunnelPolicyCreate

- ea: `0x180049dec`
- end: `0x180049f1f`
- name: `LipsTunnelPolicyCreate`
- size: `307`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180049560`

## callees

- `0x18000c4d0`
- `0x18000e510`
- `0x180049dec`
- `0x18004c148`
- `0x18004c6b4`

## string_xrefs

- `0x180049e7f`: `LipsTunnelPolicyCreate`

## pseudocode

```c
__int64 __fastcall LipsTunnelPolicyCreate(__int64 a1, __int64 a2, __int64 a3)
{
  int v5; // ebp
  __int64 v6; // rdx
  __int64 v7; // r10
  unsigned int v8; // esi
  __int64 v10; // rax
  __int64 v11; // rcx
  __int128 v12; // xmm1

  if ( (*(_BYTE *)(*(_QWORD *)(a1 + 264) + 32LL) & 0x44) != 0 )
    return 13;
  v5 = *(_DWORD *)(a1 + 236);
  LipsIpsecSetTimeoutFlags(*(_QWORD *)(a1 + 264), a2, a3);
  if ( gcUdpEncapsulation == 1 )
  {
    *(_DWORD *)v6 |= 0x10u;
  }
  else if ( gcUdpEncapsulation == 2 )
  {
    *(_DWORD *)v6 |= 0x20u;
  }
  v8 = LipsIpsecPolicyProposalsCreate(
         *(_QWORD *)(v7 + 48),
         *(_DWORD *)(v7 + 40),
         (_QWORD *)(v6 + 8),
         (unsigned int *)(v6 + 4));
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_4259805821ae3eb6062dce0997567f8e_Traceguids, v8);
    return LipsReportError(v8, (int)"LipsTunnelPolicyCreate");
  }
  else
  {
    *(_DWORD *)(a2 + 52) = gcSaIdleTime;
    *(_DWORD *)(a2 + 56) = 60;
    if ( *(_DWORD *)(a1 + 84) )
    {
      *(_DWORD *)(a2 + 16) = 1;
      if ( v5 == 8 )
      {
        *(_OWORD *)(a2 + 20) = *(_OWORD *)(a1 + 296);
        v12 = *(_OWORD *)(a1 + 168);
      }
      else
      {
        *(_OWORD *)(a2 + 20) = *(_OWORD *)(a1 + 168);
        v12 = *(_OWORD *)(a1 + 296);
      }
      *(_OWORD *)(a2 + 36) = v12;
    }
    else
    {
      *(_DWORD *)(a2 + 16) = 0;
      v10 = 296;
      v11 = 168;
      if ( v5 != 8 )
      {
        v10 = 168;
        v11 = 296;
      }
      *(_DWORD *)(a2 + 20) = _byteswap_ulong(*(_DWORD *)(v10 + a1));
      *(_DWORD *)(a2 + 36) = _byteswap_ulong(*(_DWORD *)(v11 + a1));
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180049dec  push    rbx
0x180049dee  push    rbp
0x180049def  push    rsi
0x180049df0  push    rdi
0x180049df1  sub     rsp, 28h
0x180049df5  mov     r10, [rcx+108h]
0x180049dfc  mov     rbx, rdx
0x180049dff  mov     rdi, rcx
0x180049e02  test    byte ptr [r10+20h], 44h
0x180049e07  jnz     loc_180049F11
0x180049e0d  mov     ebp, [rcx+0ECh]
0x180049e13  mov     rcx, r10
0x180049e16  call    LipsIpsecSetTimeoutFlags
0x180049e1b  mov     eax, cs:gcUdpEncapsulation
0x180049e21  cmp     eax, 1
0x180049e24  jnz     short loc_180049E2B
0x180049e26  or      dword ptr [rdx], 10h
0x180049e29  jmp     short loc_180049E33
0x180049e2b  cmp     eax, 2
0x180049e2e  jnz     short loc_180049E33
0x180049e30  or      dword ptr [rdx], 20h
0x180049e33  mov     rcx, [r10+30h]
0x180049e37  lea     r9, [rdx+4]
0x180049e3b  lea     r8, [rdx+8]
0x180049e3f  mov     edx, [r10+28h]
0x180049e43  call    LipsIpsecPolicyProposalsCreate
0x180049e48  mov     esi, eax
0x180049e4a  test    eax, eax
0x180049e4c  jz      short loc_180049E92
0x180049e4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180049e55  lea     rax, WPP_GLOBAL_Control
0x180049e5c  cmp     rcx, rax
0x180049e5f  jz      short loc_180049E7F
0x180049e61  test    byte ptr [rcx+1Ch], 10h
0x180049e65  jz      short loc_180049E7F
0x180049e67  mov     rcx, [rcx+10h]
0x180049e6b  lea     r8, WPP_4259805821ae3eb6062dce0997567f8e_Traceguids
0x180049e72  mov     edx, 14h
0x180049e77  mov     r9d, esi
0x180049e7a  call    WPP_SF_d
0x180049e7f  lea     rdx, aLipstunnelpoli; "LipsTunnelPolicyCreate"
0x180049e86  mov     ecx, esi
0x180049e88  call    LipsReportError
0x180049e8d  jmp     loc_180049F16
0x180049e92  mov     eax, cs:gcSaIdleTime
0x180049e98  mov     [rbx+34h], eax
0x180049e9b  mov     dword ptr [rbx+38h], 3Ch ; '<'
0x180049ea2  cmp     dword ptr [rdi+54h], 0
0x180049ea6  jnz     short loc_180049ED4
0x180049ea8  mov     dword ptr [rbx+10h], 0
0x180049eaf  mov     edx, 128h
0x180049eb4  cmp     ebp, 8
0x180049eb7  mov     eax, edx
0x180049eb9  lea     ecx, [rdx-80h]
0x180049ebc  cmovnz  eax, ecx
0x180049ebf  cmovnz  ecx, edx
0x180049ec2  mov     eax, [rax+rdi]
0x180049ec5  bswap   eax
0x180049ec7  mov     [rbx+14h], eax
0x180049eca  mov     eax, [rcx+rdi]
0x180049ecd  bswap   eax
0x180049ecf  mov     [rbx+24h], eax
0x180049ed2  jmp     short loc_180049F0D
0x180049ed4  mov     dword ptr [rbx+10h], 1
0x180049edb  cmp     ebp, 8
0x180049ede  jnz     short loc_180049EF5
0x180049ee0  movups  xmm0, xmmword ptr [rdi+128h]
0x180049ee7  movdqu  xmmword ptr [rbx+14h], xmm0
0x180049eec  movups  xmm1, xmmword ptr [rdi+0A8h]
0x180049ef3  jmp     short loc_180049F08
0x180049ef5  movups  xmm0, xmmword ptr [rdi+0A8h]
0x180049efc  movdqu  xmmword ptr [rbx+14h], xmm0
0x180049f01  movups  xmm1, xmmword ptr [rdi+128h]
0x180049f08  movdqu  xmmword ptr [rbx+24h], xmm1
0x180049f0d  xor     eax, eax
0x180049f0f  jmp     short loc_180049F16
0x180049f11  mov     eax, 0Dh
0x180049f16  add     rsp, 28h
0x180049f1a  pop     rdi
0x180049f1b  pop     rsi
0x180049f1c  pop     rbp
0x180049f1d  pop     rbx
0x180049f1e  retn
```
