# OneXHlpCreateDefaultProfile

- ea: `0x180031b28`
- end: `0x180031c96`
- name: `OneXHlpCreateDefaultProfile`
- size: `366`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180031318`

## callees

- `0x180003114`
- `0x180030fd8`
- `0x180031b28`
- `0x180031c9c`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x180031b65`
- `MobileNetworking!AllocateMemory` at `0x180031b65`

## string_xrefs

- `0x180031b55`: `OneXHlpCreateDefaultProfile`

## pseudocode

```c
__int64 __fastcall OneXHlpCreateDefaultProfile(void **a1, _DWORD *a2)
{
  unsigned int AlignedSize; // ecx
  __int64 v5; // r8
  __int64 v6; // r8
  __int64 v7; // rbx
  __int64 v8; // r8
  __int128 v10; // [rsp+20h] [rbp-18h] BYREF
  void *v11; // [rsp+60h] [rbp+28h] BYREF

  *a1 = 0;
  *a2 = 0;
  v11 = 0;
  AlignedSize = AllocateMemory(104, &v11, "OneXHlpCreateDefaultProfile", 556);
  if ( !AlignedSize )
  {
    memset_0(v11, 0, 0x68u);
    *(_DWORD *)v11 = 1;
    *((_DWORD *)v11 + 1) = 104;
    AlignedSize = GetAlignedSize(32, (char *)v11 + 60, v5);
    if ( !AlignedSize )
    {
      AlignedSize = GetAlignedSize(68, (char *)v11 + 64, v6);
      if ( !AlignedSize )
      {
        if ( v11 )
        {
          v7 = -1;
          if ( (char *)v11 + 72 >= v11 )
            v7 = (__int64)v11 + 72;
          AlignedSize = (char *)v11 + 72 < v11 ? 0x216 : 0;
          if ( (char *)v11 + 72 >= v11 )
          {
            *(_BYTE *)(v7 + 4) = 25;
            *(_QWORD *)(v7 + 12) = 0;
            *(_DWORD *)(v7 + 8) = 0;
            *(_DWORD *)v7 = 0;
            *((_DWORD *)v11 + 6) = -1;
            *((_DWORD *)v11 + 7) = -1;
            *((_DWORD *)v11 + 8) = -1;
            *((_DWORD *)v11 + 9) = -1;
            *((_DWORD *)v11 + 10) = -1;
            *((_DWORD *)v11 + 4) = 3;
            v10 = *(_OWORD *)(v7 + 4);
            AlignedSize = OneXIsValidEapTypeAndFlags(&v10);
            if ( !AlignedSize )
            {
              *(_DWORD *)(v7 + 20) &= ~1u;
              *(_DWORD *)(v7 + 24) = 0;
              AlignedSize = GetAlignedSize(32, v7 + 28, v8);
              if ( !AlignedSize )
              {
                *a1 = v11;
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
0x180031b28  push    rbp
0x180031b2a  push    rbx
0x180031b2b  push    rsi
0x180031b2c  push    rdi
0x180031b2d  mov     rbp, rsp
0x180031b30  sub     rsp, 38h
0x180031b34  mov     qword ptr [rcx], 0
0x180031b3b  mov     rdi, rdx
0x180031b3e  mov     dword ptr [rdx], 0
0x180031b44  mov     rsi, rcx
0x180031b47  mov     [rbp+arg_0], 0
0x180031b4f  mov     r9d, 22Ch
0x180031b55  lea     r8, aOnexhlpcreated; "OneXHlpCreateDefaultProfile"
0x180031b5c  lea     rdx, [rbp+arg_0]
0x180031b60  mov     ecx, 68h ; 'h'
0x180031b65  call    cs:__imp_AllocateMemory
0x180031b6b  mov     ecx, eax
0x180031b6d  test    eax, eax
0x180031b6f  jnz     loc_180031C8B
0x180031b75  mov     rcx, [rbp+arg_0]; void *
0x180031b79  lea     r8d, [rax+68h]; Size
0x180031b7d  xor     edx, edx; Val
0x180031b7f  call    memset_0
0x180031b84  mov     rax, [rbp+arg_0]
0x180031b88  mov     ecx, 20h ; ' '
0x180031b8d  mov     dword ptr [rax], 1
0x180031b93  mov     rax, [rbp+arg_0]
0x180031b97  mov     dword ptr [rax+4], 68h ; 'h'
0x180031b9e  mov     rdx, [rbp+arg_0]
0x180031ba2  add     rdx, 3Ch ; '<'
0x180031ba6  call    GetAlignedSize
0x180031bab  mov     ecx, eax
0x180031bad  test    eax, eax
0x180031baf  jnz     loc_180031C8B
0x180031bb5  mov     rdx, [rbp+arg_0]
0x180031bb9  lea     ecx, [rax+44h]
0x180031bbc  add     rdx, 40h ; '@'
0x180031bc0  call    GetAlignedSize
0x180031bc5  mov     ecx, eax
0x180031bc7  test    eax, eax
0x180031bc9  jnz     loc_180031C8B
0x180031bcf  mov     rdx, [rbp+arg_0]
0x180031bd3  test    rdx, rdx
0x180031bd6  jz      loc_180031C86
0x180031bdc  lea     rax, [rdx+48h]
0x180031be0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180031be4  cmp     rax, rdx
0x180031be7  cmovnb  rbx, rax
0x180031beb  sbb     ecx, ecx
0x180031bed  and     ecx, 216h
0x180031bf3  cmp     rax, rdx
0x180031bf6  jb      loc_180031C8B
0x180031bfc  mov     byte ptr [rbx+4], 19h
0x180031c00  or      ecx, 0FFFFFFFFh
0x180031c03  mov     qword ptr [rbx+0Ch], 0
0x180031c0b  mov     dword ptr [rbx+8], 0
0x180031c12  mov     dword ptr [rbx], 0
0x180031c18  mov     rax, [rbp+arg_0]
0x180031c1c  mov     [rax+18h], ecx
0x180031c1f  mov     rax, [rbp+arg_0]
0x180031c23  mov     [rax+1Ch], ecx
0x180031c26  mov     rax, [rbp+arg_0]
0x180031c2a  mov     [rax+20h], ecx
0x180031c2d  mov     rax, [rbp+arg_0]
0x180031c31  mov     [rax+24h], ecx
0x180031c34  mov     rax, [rbp+arg_0]
0x180031c38  mov     [rax+28h], ecx
0x180031c3b  lea     rcx, [rbp+var_18]
0x180031c3f  mov     rax, [rbp+arg_0]
0x180031c43  mov     dword ptr [rax+10h], 3
0x180031c4a  movups  xmm0, xmmword ptr [rbx+4]
0x180031c4e  movdqu  [rbp+var_18], xmm0
0x180031c53  call    OneXIsValidEapTypeAndFlags
0x180031c58  mov     ecx, eax
0x180031c5a  test    eax, eax
0x180031c5c  jnz     short loc_180031C8B
0x180031c5e  and     dword ptr [rbx+14h], 0FFFFFFFEh
0x180031c62  lea     rdx, [rbx+1Ch]
0x180031c66  lea     ecx, [rax+20h]
0x180031c69  mov     [rbx+18h], eax
0x180031c6c  call    GetAlignedSize
0x180031c71  mov     ecx, eax
0x180031c73  test    eax, eax
0x180031c75  jnz     short loc_180031C8B
0x180031c77  mov     rax, [rbp+arg_0]
0x180031c7b  mov     [rsi], rax
0x180031c7e  mov     dword ptr [rdi], 68h ; 'h'
0x180031c84  jmp     short loc_180031C8B
0x180031c86  mov     ecx, 57h ; 'W'
0x180031c8b  mov     eax, ecx
0x180031c8d  add     rsp, 38h
0x180031c91  pop     rdi
0x180031c92  pop     rsi
0x180031c93  pop     rbx
0x180031c94  pop     rbp
0x180031c95  retn
```
