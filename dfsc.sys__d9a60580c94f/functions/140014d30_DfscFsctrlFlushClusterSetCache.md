# DfscFsctrlFlushClusterSetCache

- ea: `0x140014d30`
- end: `0x140015048`
- name: `DfscFsctrlFlushClusterSetCache`
- size: `792`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x140014910`

## callees

- `0x140001010`
- `0x1400015c0`
- `0x140002394`
- `0x140002430`
- `0x140002fcc`
- `0x140014d30`
- `0x1400199e4`
- `0x14001a79c`
- `0x14001d090`
- `0x140020d10`

## import_xrefs

- `ntoskrnl!RtlNextUnicodePrefix` at `0x140014f40`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140014fd5`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140014f40`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140014fd5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140014ffe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140014ffe`
- `ntoskrnl!ExReleaseResourceLite` at `0x140014ff2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140014ff2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140014eb2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140014eb2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140014ea0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140014ea0`

## pseudocode

```c
__int64 __fastcall DfscFsctrlFlushClusterSetCache(IRP *a1, _WORD *a2, int a3)
{
  int v3; // ebx
  _WORD *v4; // rsi
  int ContainerContextFromIrp; // edi
  struct _UNICODE_PREFIX_TABLE *ReferralCache; // rax
  __int64 v8; // rdx
  struct _UNICODE_PREFIX_TABLE *v9; // r14
  unsigned __int64 v10; // rax
  char v11; // di
  char v12; // si
  PVOID v13; // r15
  __int64 v14; // rbx
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  __int64 p_RightChild; // rdi
  __int128 v18; // [rsp+40h] [rbp-20h] BYREF
  __int128 v19; // [rsp+50h] [rbp-10h] BYREF
  PVOID P; // [rsp+A8h] [rbp+48h] BYREF
  __int64 v21; // [rsp+B8h] [rbp+58h] BYREF

  P = 0;
  v3 = a3;
  v21 = 0;
  v4 = a2;
  v18 = 0;
  if ( (a3 & 1) == 0 && (unsigned int)(a3 - 2) <= 0xFFFC && a2 && *a2 )
  {
    ContainerContextFromIrp = DfscGetContainerContextFromIrp(a1, &v21);
    if ( ContainerContextFromIrp >= 0 )
    {
      ReferralCache = (struct _UNICODE_PREFIX_TABLE *)DfscGetReferralCache(v21);
      v9 = ReferralCache;
      if ( v3 == 2 && *v4 == 42 )
      {
        DfscClusterSetCachePurge(ReferralCache);
      }
      else
      {
        *((_QWORD *)&v18 + 1) = v4;
        LOWORD(v18) = v3;
        WORD1(v18) = v3;
        if ( (unsigned __int16)v3 > 4u && *v4 == 92 && v4[1] == 92 )
        {
          LOWORD(v3) = v3 - 2;
          *((_QWORD *)&v18 + 1) = v4 + 1;
          LOWORD(v18) = v3;
          ++v4;
          WORD1(v18) = v3;
        }
        v19 = 0;
        if ( (unsigned __int16)v3 > 2u && v4[((unsigned __int64)(unsigned __int16)v3 >> 1) - 1] == 92 )
        {
          LOWORD(v3) = v3 - 2;
          LOWORD(v18) = v3;
        }
        if ( (unsigned __int16)v3 >= 4u
          && (v10 = (unsigned __int64)(unsigned __int16)v3 >> 1, v4[v10 - 2] == 92)
          && v4[v10 - 1] == 42 )
        {
          v11 = 1;
          LOWORD(v18) = v3 - 4;
        }
        else
        {
          v11 = 0;
        }
        if ( (int)DfscGetReferralFromPath(a1, 0, (IRP *)&v18, 3, v8, (__int64)&P, 0, (__int64)&v19) < 0 )
        {
          return (unsigned int)-1073741772;
        }
        else
        {
          v12 = 0;
          v13 = P;
          v14 = *((_QWORD *)P + 2);
          KeEnterCriticalRegion();
          ExAcquireResourceExclusiveLite((PERESOURCE)&v9[2].NextPrefixTree, 1u);
          if ( v11 && *(_DWORD *)(v14 + 8) != 2 )
            goto LABEL_49;
          if ( !(_WORD)v19 && (*(_BYTE *)(v14 + 12) & 1) != 0 && *(_BYTE *)(v14 + 16) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
            {
              WPP_SF_qq(
                WPP_GLOBAL_Control->AttachedDevice,
                37,
                WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids,
                v14,
                a1);
            }
            DfscRmUnlinkReferral(v14);
            DfscRmDereferenceReferral((volatile signed __int32 *)v14);
            v12 = 1;
          }
          if ( v11 )
          {
LABEL_49:
            if ( *(_DWORD *)(v14 + 8) == 1 )
            {
              UnicodePrefix = RtlNextUnicodePrefix(v9, 1u);
              if ( UnicodePrefix )
              {
                do
                {
                  p_RightChild = (__int64)&UnicodePrefix[-2].Links.RightChild;
                  if ( LODWORD(UnicodePrefix[-2].Prefix) == 2
                    && *(_BYTE *)(p_RightChild + 16)
                    && (unsigned __int8)DfscPathPrefixMatch((PCUNICODE_STRING)(v14
                                                                             + 112
                                                                             * (*(unsigned __int16 *)(v14 + 26) + 2LL))) )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
                    {
                      WPP_SF_qq(
                        WPP_GLOBAL_Control->AttachedDevice,
                        38,
                        WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids,
                        p_RightChild,
                        a1);
                    }
                    DfscRmUnlinkReferral(p_RightChild);
                    DfscRmDereferenceReferral((volatile signed __int32 *)p_RightChild);
                    v12 = 1;
                  }
                  UnicodePrefix = RtlNextUnicodePrefix(v9, 0);
                }
                while ( UnicodePrefix );
                v13 = P;
              }
            }
          }
          ExReleaseResourceLite((PERESOURCE)&v9[2].NextPrefixTree);
          KeLeaveCriticalRegion();
          DfscReferralRelease(v13);
          return v12 == 0 ? 0xC0000034 : 0;
        }
      }
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)ContainerContextFromIrp;
}

```

## disassembly

```asm
0x140014d30  mov     [rsp-38h+arg_0], rbx
0x140014d35  push    rbp
0x140014d36  push    rsi
0x140014d37  push    rdi
0x140014d38  push    r12
0x140014d3a  push    r13
0x140014d3c  push    r14
0x140014d3e  push    r15
0x140014d40  mov     rbp, rsp
0x140014d43  sub     rsp, 60h
0x140014d47  xor     r15d, r15d
0x140014d4a  xorps   xmm0, xmm0
0x140014d4d  mov     [rbp+P], r15
0x140014d51  mov     ebx, r8d
0x140014d54  mov     [rbp+arg_18], r15
0x140014d58  mov     rsi, rdx
0x140014d5b  mov     r13, rcx
0x140014d5e  movups  [rbp+var_20], xmm0
0x140014d62  test    r8b, 1
0x140014d66  jnz     loc_140015028
0x140014d6c  lea     eax, [r8-2]
0x140014d70  mov     r12d, 0FFFCh
0x140014d76  cmp     eax, r12d
0x140014d79  ja      loc_140015028
0x140014d7f  test    rdx, rdx
0x140014d82  jz      loc_140015028
0x140014d88  cmp     [rdx], r15w
0x140014d8c  jz      loc_140015028
0x140014d92  lea     rdx, [rbp+arg_18]
0x140014d96  call    DfscGetContainerContextFromIrp
0x140014d9b  mov     edi, eax
0x140014d9d  test    eax, eax
0x140014d9f  js      loc_14001502D
0x140014da5  mov     rdx, [rbp+arg_18]
0x140014da9  mov     rcx, rdx
0x140014dac  call    DfscGetReferralCache
0x140014db1  lea     r9d, [r15+2]
0x140014db5  mov     r14, rax
0x140014db8  cmp     ebx, r9d
0x140014dbb  jnz     short loc_140014DD0
0x140014dbd  cmp     word ptr [rsi], 2Ah ; '*'
0x140014dc1  jnz     short loc_140014DD0
0x140014dc3  mov     rcx, rax; PrefixTable
0x140014dc6  call    DfscClusterSetCachePurge
0x140014dcb  jmp     loc_14001502D
0x140014dd0  mov     qword ptr [rbp+var_20+8], rsi
0x140014dd4  mov     r8w, 5Ch ; '\'
0x140014dd9  mov     word ptr [rbp+var_20], bx
0x140014ddd  mov     word ptr [rbp+var_20+2], bx
0x140014de1  cmp     bx, 4
0x140014de5  jbe     short loc_140014E0A
0x140014de7  cmp     [rsi], r8w
0x140014deb  jnz     short loc_140014E0A
0x140014ded  lea     rcx, [rsi+2]
0x140014df1  cmp     [rcx], r8w
0x140014df5  jnz     short loc_140014E0A
0x140014df7  sub     bx, r9w
0x140014dfb  mov     qword ptr [rbp+var_20+8], rcx
0x140014dff  mov     word ptr [rbp+var_20], bx
0x140014e03  mov     rsi, rcx
0x140014e06  mov     word ptr [rbp+var_20+2], bx
0x140014e0a  xorps   xmm0, xmm0
0x140014e0d  movups  [rbp+var_10], xmm0
0x140014e11  cmp     bx, r9w
0x140014e15  jbe     short loc_140014E31
0x140014e17  movzx   eax, bx
0x140014e1a  shr     rax, 1
0x140014e1d  cmp     [rsi+rax*2-2], r8w
0x140014e23  jnz     short loc_140014E31
0x140014e25  mov     eax, 0FFFEh
0x140014e2a  add     bx, ax
0x140014e2d  mov     word ptr [rbp+var_20], bx
0x140014e31  cmp     bx, 4
0x140014e35  jb      short loc_140014E5A
0x140014e37  movzx   eax, bx
0x140014e3a  shr     rax, 1
0x140014e3d  cmp     [rsi+rax*2-4], r8w
0x140014e43  jnz     short loc_140014E5A
0x140014e45  cmp     word ptr [rsi+rax*2-2], 2Ah ; '*'
0x140014e4b  jnz     short loc_140014E5A
0x140014e4d  add     bx, r12w
0x140014e51  mov     dil, 1
0x140014e54  mov     word ptr [rbp+var_20], bx
0x140014e58  jmp     short loc_140014E5D
0x140014e5a  mov     dil, r15b
0x140014e5d  lea     rax, [rbp+var_10]
0x140014e61  mov     r9d, 3
0x140014e67  mov     [rsp+60h+var_28], rax
0x140014e6c  lea     r8, [rbp+var_20]
0x140014e70  lea     rax, [rbp+P]
0x140014e74  mov     [rsp+60h+var_30], r15
0x140014e79  mov     [rsp+60h+var_38], rax
0x140014e7e  mov     rcx, r13
0x140014e81  mov     [rsp+60h+var_40], rdx
0x140014e86  xor     edx, edx
0x140014e88  call    DfscGetReferralFromPath
0x140014e8d  test    eax, eax
0x140014e8f  js      loc_140015021
0x140014e95  mov     sil, r15b
0x140014e98  mov     r15, [rbp+P]
0x140014e9c  mov     rbx, [r15+10h]
0x140014ea0  call    cs:__imp_KeEnterCriticalRegion
0x140014ea7  nop     dword ptr [rax+rax+00h]
0x140014eac  mov     dl, 1; Wait
0x140014eae  lea     rcx, [r14+38h]; Resource
0x140014eb2  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140014eb9  nop     dword ptr [rax+rax+00h]
0x140014ebe  xor     ecx, ecx
0x140014ec0  lea     rdx, WPP_GLOBAL_Control
0x140014ec7  test    dil, dil
0x140014eca  jz      short loc_140014ED2
0x140014ecc  cmp     dword ptr [rbx+8], 2
0x140014ed0  jnz     short loc_140014F31
0x140014ed2  cmp     word ptr [rbp+var_10], cx
0x140014ed6  jnz     short loc_140014F28
0x140014ed8  test    byte ptr [rbx+0Ch], 1
0x140014edc  jz      short loc_140014F28
0x140014ede  cmp     [rbx+10h], cl
0x140014ee1  jz      short loc_140014F28
0x140014ee3  mov     rcx, cs:WPP_GLOBAL_Control
0x140014eea  cmp     rcx, rdx
0x140014eed  jz      short loc_140014F15
0x140014eef  test    dword ptr [rcx+2Ch], 200000h
0x140014ef6  jz      short loc_140014F15
0x140014ef8  mov     rcx, [rcx+18h]
0x140014efc  lea     r8, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids
0x140014f03  mov     edx, 25h ; '%'
0x140014f08  mov     [rsp+60h+var_40], r13
0x140014f0d  mov     r9, rbx
0x140014f10  call    WPP_SF_qq
0x140014f15  mov     rcx, rbx
0x140014f18  call    DfscRmUnlinkReferral
0x140014f1d  mov     rcx, rbx; P
0x140014f20  call    DfscRmDereferenceReferral
0x140014f25  mov     sil, 1
0x140014f28  test    dil, dil
0x140014f2b  jz      loc_140014FEE
0x140014f31  cmp     dword ptr [rbx+8], 1
0x140014f35  jnz     loc_140014FEE
0x140014f3b  mov     dl, 1; Restart
0x140014f3d  mov     rcx, r14; PrefixTable
0x140014f40  call    cs:__imp_RtlNextUnicodePrefix
0x140014f47  nop     dword ptr [rax+rax+00h]
0x140014f4c  test    rax, rax
0x140014f4f  jz      loc_140014FEE
0x140014f55  lea     r15, WPP_GLOBAL_Control
0x140014f5c  lea     rdi, [rax-48h]
0x140014f60  cmp     dword ptr [rdi+8], 2
0x140014f64  jnz     short loc_140014FD0
0x140014f66  cmp     byte ptr [rdi+10h], 0
0x140014f6a  jz      short loc_140014FD0
0x140014f6c  movzx   eax, word ptr [rbx+1Ah]
0x140014f70  lea     rdx, [rdi+90h]
0x140014f77  add     rax, 2
0x140014f7b  imul    rcx, rax, 70h ; 'p'
0x140014f7f  add     rcx, rbx; String1
0x140014f82  call    DfscPathPrefixMatch
0x140014f87  test    al, al
0x140014f89  jz      short loc_140014FD0
0x140014f8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140014f92  cmp     rcx, r15
0x140014f95  jz      short loc_140014FBD
0x140014f97  test    dword ptr [rcx+2Ch], 200000h
0x140014f9e  jz      short loc_140014FBD
0x140014fa0  mov     rcx, [rcx+18h]
0x140014fa4  lea     r8, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids
0x140014fab  mov     edx, 26h ; '&'
0x140014fb0  mov     [rsp+60h+var_40], r13
0x140014fb5  mov     r9, rdi
0x140014fb8  call    WPP_SF_qq
0x140014fbd  mov     rcx, rdi
0x140014fc0  call    DfscRmUnlinkReferral
0x140014fc5  mov     rcx, rdi; P
0x140014fc8  call    DfscRmDereferenceReferral
0x140014fcd  mov     sil, 1
0x140014fd0  xor     edx, edx; Restart
0x140014fd2  mov     rcx, r14; PrefixTable
0x140014fd5  call    cs:__imp_RtlNextUnicodePrefix
0x140014fdc  nop     dword ptr [rax+rax+00h]
0x140014fe1  test    rax, rax
0x140014fe4  jnz     loc_140014F5C
0x140014fea  mov     r15, [rbp+P]
0x140014fee  lea     rcx, [r14+38h]; Resource
0x140014ff2  call    cs:__imp_ExReleaseResourceLite
0x140014ff9  nop     dword ptr [rax+rax+00h]
0x140014ffe  call    cs:__imp_KeLeaveCriticalRegion
0x140015005  nop     dword ptr [rax+rax+00h]
0x14001500a  mov     rcx, r15; P
0x14001500d  call    DfscReferralRelease
0x140015012  neg     sil
0x140015015  sbb     edi, edi
0x140015017  not     edi
0x140015019  and     edi, 0C0000034h
0x14001501f  jmp     short loc_14001502D
0x140015021  mov     edi, 0C0000034h
0x140015026  jmp     short loc_14001502D
0x140015028  mov     edi, 0C000000Dh
0x14001502d  mov     rbx, [rsp+60h+arg_0]
0x140015035  mov     eax, edi
0x140015037  add     rsp, 60h
0x14001503b  pop     r15
0x14001503d  pop     r14
0x14001503f  pop     r13
0x140015041  pop     r12
0x140015043  pop     rdi
0x140015044  pop     rsi
0x140015045  pop     rbp
0x140015046  retn
```
