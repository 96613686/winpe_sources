# OneXHlpCreateDefaultProfile

- ea: `0x18002ec50`
- end: `0x18002edcf`
- name: `OneXHlpCreateDefaultProfile`
- size: `383`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18002aa58`
- `0x18002c450`

## callees

- `0x180014e20`
- `0x180018550`
- `0x180020aea`
- `0x18002ec50`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x18002ec97`
- `MobileNetworking!AllocateMemory` at `0x18002ec97`

## string_xrefs

- `0x18002ec87`: `OneXHlpCreateDefaultProfile`

## pseudocode

```c
__int64 __fastcall OneXHlpCreateDefaultProfile(void **a1, _DWORD *a2, unsigned int a3, char a4)
{
  unsigned int AlignedSize; // ecx
  void *v9; // rdx
  __int64 v10; // rbx
  __int128 v12; // [rsp+20h] [rbp-18h] BYREF
  void *v13; // [rsp+70h] [rbp+38h] BYREF

  v13 = 0;
  *a1 = 0;
  *a2 = 0;
  AlignedSize = AllocateMemory(104, &v13, "OneXHlpCreateDefaultProfile", 556);
  if ( !AlignedSize )
  {
    memset_0(v13, 0, 0x68u);
    *(_DWORD *)v13 = 1;
    *((_DWORD *)v13 + 1) = 104;
    AlignedSize = GetAlignedSize(32, (char *)v13 + 60);
    if ( !AlignedSize )
    {
      AlignedSize = GetAlignedSize(68, (char *)v13 + 64);
      if ( !AlignedSize )
      {
        v9 = v13;
        if ( v13 )
        {
          v10 = -1;
          if ( (char *)v13 + 72 >= v13 )
            v10 = (__int64)v13 + 72;
          AlignedSize = (char *)v13 + 72 < v13 ? 0x216 : 0;
          if ( (char *)v13 + 72 >= v13 )
          {
            *(_BYTE *)(v10 + 4) = a4;
            *(_QWORD *)(v10 + 12) = 0;
            *(_DWORD *)(v10 + 8) = 0;
            *(_DWORD *)v10 = 0;
            *((_DWORD *)v13 + 6) = -1;
            *((_DWORD *)v13 + 7) = -1;
            *((_DWORD *)v13 + 8) = -1;
            *((_DWORD *)v13 + 9) = -1;
            *((_DWORD *)v13 + 10) = -1;
            *((_DWORD *)v13 + 4) = 3;
            v12 = *(_OWORD *)(v10 + 4);
            AlignedSize = OneXIsValidEapTypeAndFlags(&v12, v9, a3);
            if ( !AlignedSize )
            {
              *(_DWORD *)(v10 + 20) &= ~1u;
              *(_DWORD *)(v10 + 24) = 0;
              AlignedSize = GetAlignedSize(32, v10 + 28);
              if ( !AlignedSize )
              {
                *a1 = v13;
                *a2 = 104;
              }
            }
          }
        }
        else
        {
          return 87;
        }
      }
    }
  }
  return AlignedSize;
}

```

## disassembly

```asm
0x18002ec50  push    rbp
0x18002ec52  push    rbx
0x18002ec53  push    rsi
0x18002ec54  push    rdi
0x18002ec55  push    r14
0x18002ec57  push    r15
0x18002ec59  mov     rbp, rsp
0x18002ec5c  sub     rsp, 38h
0x18002ec60  mov     r14b, r9b
0x18002ec63  mov     [rbp+arg_0], 0
0x18002ec6b  mov     r15d, r8d
0x18002ec6e  mov     qword ptr [rcx], 0
0x18002ec75  mov     rdi, rdx
0x18002ec78  mov     dword ptr [rdx], 0
0x18002ec7e  mov     rsi, rcx
0x18002ec81  mov     r9d, 22Ch
0x18002ec87  lea     r8, aOnexhlpcreated; "OneXHlpCreateDefaultProfile"
0x18002ec8e  lea     rdx, [rbp+arg_0]
0x18002ec92  mov     ecx, 68h ; 'h'
0x18002ec97  call    cs:__imp_AllocateMemory
0x18002ec9d  mov     ecx, eax
0x18002ec9f  test    eax, eax
0x18002eca1  jnz     loc_18002EDC0
0x18002eca7  mov     rcx, [rbp+arg_0]; void *
0x18002ecab  lea     r8d, [rax+68h]; Size
0x18002ecaf  xor     edx, edx; Val
0x18002ecb1  call    memset_0
0x18002ecb6  mov     rax, [rbp+arg_0]
0x18002ecba  mov     ecx, 20h ; ' '
0x18002ecbf  mov     dword ptr [rax], 1
0x18002ecc5  mov     rax, [rbp+arg_0]
0x18002ecc9  mov     dword ptr [rax+4], 68h ; 'h'
0x18002ecd0  mov     rdx, [rbp+arg_0]
0x18002ecd4  add     rdx, 3Ch ; '<'
0x18002ecd8  call    GetAlignedSize
0x18002ecdd  mov     ecx, eax
0x18002ecdf  test    eax, eax
0x18002ece1  jnz     loc_18002EDC0
0x18002ece7  mov     rdx, [rbp+arg_0]
0x18002eceb  lea     ecx, [rax+44h]
0x18002ecee  add     rdx, 40h ; '@'
0x18002ecf2  call    GetAlignedSize
0x18002ecf7  mov     ecx, eax
0x18002ecf9  test    eax, eax
0x18002ecfb  jnz     loc_18002EDC0
0x18002ed01  mov     rdx, [rbp+arg_0]
0x18002ed05  test    rdx, rdx
0x18002ed08  jz      loc_18002EDBB
0x18002ed0e  lea     rax, [rdx+48h]
0x18002ed12  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002ed16  cmp     rax, rdx
0x18002ed19  cmovnb  rbx, rax
0x18002ed1d  sbb     ecx, ecx
0x18002ed1f  and     ecx, 216h
0x18002ed25  cmp     rax, rdx
0x18002ed28  jb      loc_18002EDC0
0x18002ed2e  mov     [rbx+4], r14b
0x18002ed32  or      ecx, 0FFFFFFFFh
0x18002ed35  mov     qword ptr [rbx+0Ch], 0
0x18002ed3d  mov     r8d, r15d
0x18002ed40  mov     dword ptr [rbx+8], 0
0x18002ed47  mov     dword ptr [rbx], 0
0x18002ed4d  mov     rax, [rbp+arg_0]
0x18002ed51  mov     [rax+18h], ecx
0x18002ed54  mov     rax, [rbp+arg_0]
0x18002ed58  mov     [rax+1Ch], ecx
0x18002ed5b  mov     rax, [rbp+arg_0]
0x18002ed5f  mov     [rax+20h], ecx
0x18002ed62  mov     rax, [rbp+arg_0]
0x18002ed66  mov     [rax+24h], ecx
0x18002ed69  mov     rax, [rbp+arg_0]
0x18002ed6d  mov     [rax+28h], ecx
0x18002ed70  lea     rcx, [rbp+var_18]
0x18002ed74  mov     rax, [rbp+arg_0]
0x18002ed78  mov     dword ptr [rax+10h], 3
0x18002ed7f  movups  xmm0, xmmword ptr [rbx+4]
0x18002ed83  movdqu  [rbp+var_18], xmm0
0x18002ed88  call    OneXIsValidEapTypeAndFlags
0x18002ed8d  mov     ecx, eax
0x18002ed8f  test    eax, eax
0x18002ed91  jnz     short loc_18002EDC0
0x18002ed93  and     dword ptr [rbx+14h], 0FFFFFFFEh
0x18002ed97  lea     rdx, [rbx+1Ch]
0x18002ed9b  lea     ecx, [rax+20h]
0x18002ed9e  mov     [rbx+18h], eax
0x18002eda1  call    GetAlignedSize
0x18002eda6  mov     ecx, eax
0x18002eda8  test    eax, eax
0x18002edaa  jnz     short loc_18002EDC0
0x18002edac  mov     rax, [rbp+arg_0]
0x18002edb0  mov     [rsi], rax
0x18002edb3  mov     dword ptr [rdi], 68h ; 'h'
0x18002edb9  jmp     short loc_18002EDC0
0x18002edbb  mov     ecx, 57h ; 'W'
0x18002edc0  mov     eax, ecx
0x18002edc2  add     rsp, 38h
0x18002edc6  pop     r15
0x18002edc8  pop     r14
0x18002edca  pop     rdi
0x18002edcb  pop     rsi
0x18002edcc  pop     rbx
0x18002edcd  pop     rbp
0x18002edce  retn
```
