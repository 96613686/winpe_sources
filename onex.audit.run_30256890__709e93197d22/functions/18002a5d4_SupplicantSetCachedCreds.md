# SupplicantSetCachedCreds

- ea: `0x18002a5d4`
- end: `0x18002a765`
- name: `SupplicantSetCachedCreds`
- size: `401`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a550`
- `0x18001e930`
- `0x180022960`
- `0x180022c30`
- `0x1800230c0`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180010ae0`
- `0x1800214f0`
- `0x18002a5d4`

## import_xrefs

- `MobileNetworking!SetBufferAndLength` at `0x18002a6e1`
- `MobileNetworking!SetBufferAndLength` at `0x18002a6e1`
- `MobileNetworking!FreeMemory` at `0x18002a6a8`
- `MobileNetworking!FreeMemory` at `0x18002a6a8`

## string_xrefs

- `0x18002a69e`: `SupplicantSetCachedCreds`

## pseudocode

```c
__int64 __fastcall SupplicantSetCachedCreds(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v6; // ebp
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  _BYTE *v9; // rax
  int v10; // eax
  _QWORD *v11; // rcx
  int v13; // [rsp+60h] [rbp+8h] BYREF

  v6 = *(_DWORD *)(*(_QWORD *)a1 + 20LL);
  v13 = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 160, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)(a1 + 492) && *(_QWORD *)(a1 + 496) )
  {
    if ( !a2 && !a3 )
    {
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 68) & 4) != 0 )
        WPP_SF_d(v7[7], 161, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v6);
      v8 = *(unsigned int *)(a1 + 492);
      v9 = *(_BYTE **)(a1 + 496);
      if ( *(_DWORD *)(a1 + 492) )
      {
        do
        {
          *v9++ = 0;
          --v8;
        }
        while ( v8 );
      }
      FreeMemory(a1 + 496, "SupplicantSetCachedCreds", 1388);
      goto LABEL_22;
    }
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 68) & 4) != 0 )
      WPP_SF_d(v7[7], 162, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v6);
  }
  v10 = SetBufferAndLength(a1 + 496, &v13, a3, a2);
  LODWORD(a3) = v10;
  if ( !v10 )
  {
    *(_DWORD *)(a1 + 492) = v13;
    goto LABEL_22;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)a3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 163, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v6, v10);
LABEL_22:
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x800) != 0 )
    WPP_SF_D(v11[7], 164, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, (unsigned int)a3);
  return (unsigned int)a3;
}

```

## disassembly

```asm
0x18002a5d4  mov     [rsp+arg_8], rbx
0x18002a5d9  mov     [rsp+arg_10], rbp
0x18002a5de  push    rsi
0x18002a5df  push    rdi
0x18002a5e0  push    r12
0x18002a5e2  push    r13
0x18002a5e4  push    r14
0x18002a5e6  sub     rsp, 30h
0x18002a5ea  mov     rax, [rcx]
0x18002a5ed  mov     rbx, r8
0x18002a5f0  mov     r14d, edx
0x18002a5f3  mov     rdi, rcx
0x18002a5f6  mov     ebp, [rax+14h]
0x18002a5f9  mov     [rsp+58h+arg_0], 0
0x18002a601  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a608  lea     r12, WPP_GLOBAL_Control
0x18002a60f  lea     r13, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x18002a616  cmp     rcx, r12
0x18002a619  jz      short loc_18002A63C
0x18002a61b  test    dword ptr [rcx+44h], 800h
0x18002a622  jz      short loc_18002A63C
0x18002a624  mov     rcx, [rcx+38h]
0x18002a628  mov     edx, 0A0h
0x18002a62d  mov     r8, r13
0x18002a630  call    WPP_SF_
0x18002a635  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a63c  cmp     dword ptr [rdi+1ECh], 0
0x18002a643  jz      loc_18002A6CF
0x18002a649  lea     rsi, [rdi+1F0h]
0x18002a650  cmp     qword ptr [rsi], 0
0x18002a654  jz      short loc_18002A6CF
0x18002a656  test    r14d, r14d
0x18002a659  jnz     short loc_18002A6B0
0x18002a65b  test    rbx, rbx
0x18002a65e  jnz     short loc_18002A6B0
0x18002a660  cmp     rcx, r12
0x18002a663  jz      short loc_18002A67F
0x18002a665  test    byte ptr [rcx+44h], 4
0x18002a669  jz      short loc_18002A67F
0x18002a66b  mov     rcx, [rcx+38h]
0x18002a66f  mov     edx, 0A1h
0x18002a674  mov     r9d, ebp
0x18002a677  mov     r8, r13
0x18002a67a  call    WPP_SF_d
0x18002a67f  mov     edx, [rdi+1ECh]
0x18002a685  mov     rax, [rsi]
0x18002a688  test    rdx, rdx
0x18002a68b  jz      short loc_18002A698
0x18002a68d  mov     [rax], bl
0x18002a68f  inc     rax
0x18002a692  sub     rdx, 1
0x18002a696  jnz     short loc_18002A68D
0x18002a698  mov     r8d, 56Ch
0x18002a69e  lea     rdx, aSupplicantsetc; "SupplicantSetCachedCreds"
0x18002a6a5  mov     rcx, rsi
0x18002a6a8  call    cs:__imp_FreeMemory
0x18002a6ae  jmp     short loc_18002A723
0x18002a6b0  cmp     rcx, r12
0x18002a6b3  jz      short loc_18002A6CF
0x18002a6b5  test    byte ptr [rcx+44h], 4
0x18002a6b9  jz      short loc_18002A6CF
0x18002a6bb  mov     rcx, [rcx+38h]
0x18002a6bf  mov     edx, 0A2h
0x18002a6c4  mov     r9d, ebp
0x18002a6c7  mov     r8, r13
0x18002a6ca  call    WPP_SF_d
0x18002a6cf  lea     rcx, [rdi+1F0h]
0x18002a6d6  mov     r9d, r14d
0x18002a6d9  mov     r8, rbx
0x18002a6dc  lea     rdx, [rsp+58h+arg_0]
0x18002a6e1  call    cs:__imp_SetBufferAndLength
0x18002a6e7  mov     ebx, eax
0x18002a6e9  test    eax, eax
0x18002a6eb  jz      short loc_18002A719
0x18002a6ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a6f4  cmp     rcx, r12
0x18002a6f7  jz      short loc_18002A74C
0x18002a6f9  test    byte ptr [rcx+44h], 1
0x18002a6fd  jz      short loc_18002A72A
0x18002a6ff  mov     rcx, [rcx+38h]
0x18002a703  mov     edx, 0A3h
0x18002a708  mov     r9d, ebp
0x18002a70b  mov     [rsp+58h+var_38], eax
0x18002a70f  mov     r8, r13
0x18002a712  call    WPP_SF_dd
0x18002a717  jmp     short loc_18002A723
0x18002a719  mov     eax, [rsp+58h+arg_0]
0x18002a71d  mov     [rdi+1ECh], eax
0x18002a723  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a72a  cmp     rcx, r12
0x18002a72d  jz      short loc_18002A74C
0x18002a72f  test    dword ptr [rcx+44h], 800h
0x18002a736  jz      short loc_18002A74C
0x18002a738  mov     rcx, [rcx+38h]
0x18002a73c  mov     edx, 0A4h
0x18002a741  mov     r9d, ebx
0x18002a744  mov     r8, r13
0x18002a747  call    WPP_SF_D
0x18002a74c  mov     rbp, [rsp+58h+arg_10]
0x18002a751  mov     eax, ebx
0x18002a753  mov     rbx, [rsp+58h+arg_8]
0x18002a758  add     rsp, 30h
0x18002a75c  pop     r14
0x18002a75e  pop     r13
0x18002a760  pop     r12
0x18002a762  pop     rdi
0x18002a763  pop     rsi
0x18002a764  retn
```
