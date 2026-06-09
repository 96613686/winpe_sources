# RnrCtx_Create

- ea: `0x180003ce0`
- end: `0x180003f21`
- name: `RnrCtx_Create`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002d00`

## callees

- `0x180003ce0`
- `0x180003f28`
- `0x180038104`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003e67`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003e67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003e2e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003e2e`
- `DNSAPI!DnsApiFree` at `0x180003d8d`
- `DNSAPI!DnsApiFree` at `0x180003ee8`
- `DNSAPI!DnsApiFree` at `0x180003efc`
- `DNSAPI!DnsApiFree` at `0x180003d8d`
- `DNSAPI!DnsApiFree` at `0x180003ee8`
- `DNSAPI!DnsApiFree` at `0x180003efc`
- `DNSAPI!DnsApiAllocZero` at `0x180003d68`
- `DNSAPI!DnsApiAllocZero` at `0x180003d68`

## pseudocode

```c
__int64 __fastcall RnrCtx_Create(__int64 a1, _WORD *a2, unsigned int a3, __int64 a4)
{
  __int64 v5; // r14
  int v8; // eax
  unsigned int v9; // r12d
  unsigned int v10; // edi
  __int64 v11; // rax
  __int64 v13; // rax
  __int64 v14; // rsi
  unsigned __int64 v16; // rdx
  __int64 v17; // rcx
  _WORD *v18; // r8
  _WORD *v19; // rcx
  _QWORD *v20; // rax
  unsigned int v21; // r15d
  __int64 v22; // rdi
  __int64 v23; // rbx
  __int64 v24[7]; // [rsp+20h] [rbp-38h] BYREF
  unsigned int v25; // [rsp+60h] [rbp+8h] BYREF
  int v26; // [rsp+64h] [rbp+Ch]

  v26 = HIDWORD(a1);
  v5 = 0;
  v24[0] = 0;
  v25 = 0;
  if ( (xmmword_180063D60 & 2) != 0 )
  {
    WPP_SF_(1025, 10, WPP_1bf4e907990e34109b4356408ced46e7_Traceguids);
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_(1025, 11, WPP_1bf4e907990e34109b4356408ced46e7_Traceguids);
  }
  v8 = CopyAddrinfoServersRnr(a3, a4, &v25, v24);
  v9 = v25;
  if ( v8 )
    goto LABEL_8;
  v10 = 0;
  if ( a2 )
  {
    v11 = -1;
    while ( a2[++v11] != 0 )
      ;
    v10 = 2 * v11 + 2;
  }
  v13 = DnsApiAllocZero(v10 + 192);
  v5 = v13;
  if ( v13 )
  {
    *(_QWORD *)(v13 + 16) = v13;
    v14 = 0;
    *(_DWORD *)(v13 + 36) = 2;
    *(_DWORD *)(v13 + 32) = -1430532899;
    *(_DWORD *)(v13 + 40) = -1;
    *(_DWORD *)(v13 + 144) = v9;
    *(_QWORD *)(v13 + 152) = v24[0];
    if ( a2 )
    {
      v16 = (unsigned __int64)v10 >> 1;
      if ( v16 )
      {
        v17 = 2147483646;
        v18 = (_WORD *)(v13 + 184);
        do
        {
          if ( !v17 )
            break;
          if ( !*a2 )
            break;
          *v18++ = *a2++;
          --v17;
          --v16;
        }
        while ( v16 );
        v19 = v18 - 1;
        if ( v16 )
          v19 = v18;
        *v19 = 0;
      }
    }
    EnterCriticalSection(&g_RnrLock);
    v20 = ListAnchor;
    if ( *((_UNKNOWN ***)ListAnchor + 1) != &ListAnchor )
      __fastfail(3u);
    *(_QWORD *)(v5 + 8) = &ListAnchor;
    *(_QWORD *)v5 = v20;
    v20[1] = v5;
    ListAnchor = (_UNKNOWN *)v5;
    LeaveCriticalSection(&g_RnrLock);
  }
  else
  {
LABEL_8:
    v14 = v24[0];
  }
  if ( v14 )
  {
    v21 = 0;
    if ( v9 )
    {
      v22 = 0;
      do
      {
        v23 = v14 + 40 * v22;
        if ( *(_DWORD *)v23 == 2 || *(_DWORD *)(v14 + 40 * v22) == 3 )
        {
          DnsApiFree(*(_QWORD *)(v23 + 32));
          *(_QWORD *)(v23 + 32) = 0;
        }
        DnsApiFree(*(_QWORD *)(v23 + 24));
        ++v21;
        *(_QWORD *)(v23 + 24) = 0;
        ++v22;
      }
      while ( v21 < v9 );
    }
  }
  DnsApiFree(v14);
  return v5;
}

```

## disassembly

```asm
0x180003ce0  mov     [rsp+arg_10], rbx
0x180003ce5  mov     [rsp+arg_0], rcx
0x180003cea  push    rsi
0x180003ceb  push    rdi
0x180003cec  push    r12
0x180003cee  push    r13
0x180003cf0  push    r14
0x180003cf2  sub     rsp, 30h
0x180003cf6  xor     r13d, r13d
0x180003cf9  mov     rdi, r9
0x180003cfc  mov     r14d, r13d
0x180003cff  mov     [rsp+58h+var_38], r13
0x180003d04  mov     dword ptr [rsp+58h+arg_0], r13d
0x180003d09  mov     esi, r8d
0x180003d0c  mov     rbx, rdx
0x180003d0f  movzx   eax, byte ptr cs:xmmword_180063D60
0x180003d16  test    al, 2
0x180003d18  jnz     loc_180003E78
0x180003d1e  lea     r9, [rsp+58h+var_38]
0x180003d23  mov     rdx, rdi
0x180003d26  lea     r8, [rsp+58h+arg_0]
0x180003d2b  mov     ecx, esi
0x180003d2d  call    CopyAddrinfoServersRnr
0x180003d32  mov     r12d, dword ptr [rsp+58h+arg_0]
0x180003d37  test    eax, eax
0x180003d39  jnz     short loc_180003D7C
0x180003d3b  mov     edi, r13d
0x180003d3e  test    rbx, rbx
0x180003d41  jz      short loc_180003D62
0x180003d43  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003d4a  nop     word ptr [rax+rax+00h]
0x180003d50  cmp     [rbx+rax*2+2], di
0x180003d55  lea     rax, [rax+1]
0x180003d59  jnz     short loc_180003D50
0x180003d5b  lea     edi, ds:2[rax*2]
0x180003d62  lea     ecx, [rdi+0C0h]
0x180003d68  call    cs:__imp_DnsApiAllocZero
0x180003d6f  nop     dword ptr [rax+rax+00h]
0x180003d74  mov     r14, rax
0x180003d77  test    rax, rax
0x180003d7a  jnz     short loc_180003DAF
0x180003d7c  mov     rsi, [rsp+58h+var_38]
0x180003d81  test    rsi, rsi
0x180003d84  jnz     loc_180003EBF
0x180003d8a  mov     rcx, rsi
0x180003d8d  call    cs:__imp_DnsApiFree
0x180003d94  nop     dword ptr [rax+rax+00h]
0x180003d99  mov     rbx, [rsp+58h+arg_10]
0x180003d9e  mov     rax, r14
0x180003da1  add     rsp, 30h
0x180003da5  pop     r14
0x180003da7  pop     r13
0x180003da9  pop     r12
0x180003dab  pop     rdi
0x180003dac  pop     rsi
0x180003dad  retn
0x180003daf  mov     [rax+10h], r14
0x180003db3  mov     rsi, r13
0x180003db6  mov     dword ptr [rax+24h], 2
0x180003dbd  mov     dword ptr [rax+20h], 0AABBCCDDh
0x180003dc4  mov     dword ptr [rax+28h], 0FFFFFFFFh
0x180003dcb  mov     [rax+90h], r12d
0x180003dd2  mov     rax, [rsp+58h+var_38]
0x180003dd7  mov     [r14+98h], rax
0x180003dde  test    rbx, rbx
0x180003de1  jz      short loc_180003E27
0x180003de3  mov     edx, edi
0x180003de5  shr     rdx, 1
0x180003de8  jz      short loc_180003E27
0x180003dea  mov     ecx, 7FFFFFFEh
0x180003def  lea     r8, [r14+0B8h]
0x180003df6  test    rcx, rcx
0x180003df9  jz      short loc_180003E18
0x180003dfb  movzx   eax, word ptr [rbx]
0x180003dfe  test    ax, ax
0x180003e01  jz      short loc_180003E18
0x180003e03  mov     [r8], ax
0x180003e07  add     rbx, 2
0x180003e0b  add     r8, 2
0x180003e0f  dec     rcx
0x180003e12  sub     rdx, 1
0x180003e16  jnz     short loc_180003DF6
0x180003e18  test    rdx, rdx
0x180003e1b  lea     rcx, [r8-2]
0x180003e1f  cmovnz  rcx, r8
0x180003e23  mov     [rcx], r13w
0x180003e27  lea     rcx, g_RnrLock; lpCriticalSection
0x180003e2e  call    cs:__imp_EnterCriticalSection
0x180003e35  nop     dword ptr [rax+rax+00h]
0x180003e3a  mov     rax, cs:ListAnchor
0x180003e41  lea     rcx, ListAnchor
0x180003e48  cmp     [rax+8], rcx
0x180003e4c  jnz     short loc_180003EB8
0x180003e4e  mov     [r14+8], rcx
0x180003e52  lea     rcx, g_RnrLock; lpCriticalSection
0x180003e59  mov     [r14], rax
0x180003e5c  mov     [rax+8], r14
0x180003e60  mov     cs:ListAnchor, r14
0x180003e67  call    cs:__imp_LeaveCriticalSection
0x180003e6e  nop     dword ptr [rax+rax+00h]
0x180003e73  jmp     loc_180003D81
0x180003e78  mov     edx, 0Ah
0x180003e7d  lea     r8, WPP_1bf4e907990e34109b4356408ced46e7_Traceguids
0x180003e84  mov     ecx, 401h
0x180003e89  call    WPP_SF_
0x180003e8e  movzx   eax, byte ptr cs:xmmword_180063D60
0x180003e95  test    al, 2
0x180003e97  jz      loc_180003D1E
0x180003e9d  mov     edx, 0Bh
0x180003ea2  lea     r8, WPP_1bf4e907990e34109b4356408ced46e7_Traceguids
0x180003ea9  mov     ecx, 401h
0x180003eae  call    WPP_SF_
0x180003eb3  jmp     loc_180003D1E
0x180003eb8  mov     ecx, 3
0x180003ebd  int     29h; Win8: RtlFailFast(ecx)
0x180003ebf  mov     [rsp+58h+arg_8], r15
0x180003ec4  mov     r15d, r13d
0x180003ec7  test    r12d, r12d
0x180003eca  jz      short loc_180003F17
0x180003ecc  mov     rdi, r13
0x180003ecf  lea     rax, [rdi+rdi*4]
0x180003ed3  mov     ecx, [rsi+rax*8]
0x180003ed6  lea     rbx, [rsi+rax*8]
0x180003eda  sub     ecx, 2
0x180003edd  jz      short loc_180003EE4
0x180003edf  cmp     ecx, 1
0x180003ee2  jnz     short loc_180003EF8
0x180003ee4  mov     rcx, [rbx+20h]
0x180003ee8  call    cs:__imp_DnsApiFree
0x180003eef  nop     dword ptr [rax+rax+00h]
0x180003ef4  mov     [rbx+20h], r13
0x180003ef8  mov     rcx, [rbx+18h]
0x180003efc  call    cs:__imp_DnsApiFree
0x180003f03  nop     dword ptr [rax+rax+00h]
0x180003f08  inc     r15d
0x180003f0b  mov     [rbx+18h], r13
0x180003f0f  inc     rdi
0x180003f12  cmp     r15d, r12d
0x180003f15  jb      short loc_180003ECF
0x180003f17  mov     r15, [rsp+58h+arg_8]
0x180003f1c  jmp     loc_180003D8A
```
