# TextLogUpdateFileOffsets

- ea: `0x180005a5c`
- end: `0x180005b0f`
- name: `TextLogUpdateFileOffsets`
- size: `179`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180004d34`
- `0x18000512c`

## callees

- `0x180004e0c`
- `0x180005a5c`
- `0x180005b18`

## pseudocode

```c
__int64 __fastcall TextLogUpdateFileOffsets(__int64 a1, unsigned int a2, int a3)
{
  __int64 v5; // rsi
  unsigned int v6; // r14d
  unsigned int i; // edx
  __int128 v9; // [rsp+20h] [rbp-20h] BYREF
  int v10; // [rsp+30h] [rbp-10h]

  v10 = 0;
  v5 = a1;
  v9 = 0;
  if ( a3 )
  {
    *(_DWORD *)(a1 + 40) += a3;
    v6 = 0;
    for ( i = 0; (unsigned int)TextLogEnumerateOpenSections(a1, i, (__int64)&v9); i = v6 )
    {
      if ( a3 <= 0 )
      {
        if ( DWORD2(v9) > a2 )
        {
          if ( DWORD2(v9) <= a2 - a3 )
            DWORD2(v9) = a2;
          else
            DWORD2(v9) += a3;
        }
        if ( HIDWORD(v9) > a2 )
        {
          if ( HIDWORD(v9) <= a2 - a3 )
            HIDWORD(v9) = a2;
          else
            HIDWORD(v9) += a3;
        }
      }
      else
      {
        if ( DWORD2(v9) >= a2 )
          DWORD2(v9) += a3;
        if ( HIDWORD(v9) >= a2 )
          HIDWORD(v9) += a3;
      }
      TextLogUpdateSectionTag(v5, &v9, v6++);
      a1 = v5;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180005a5c  push    rbp
0x180005a5e  push    rbx
0x180005a5f  push    rsi
0x180005a60  push    rdi
0x180005a61  push    r14
0x180005a63  mov     rbp, rsp
0x180005a66  sub     rsp, 40h
0x180005a6a  xor     eax, eax
0x180005a6c  xorps   xmm0, xmm0
0x180005a6f  mov     [rbp+var_10], eax
0x180005a72  mov     ebx, r8d
0x180005a75  mov     edi, edx
0x180005a77  mov     rsi, rcx
0x180005a7a  movups  [rbp+var_20], xmm0
0x180005a7e  test    r8d, r8d
0x180005a81  jz      short loc_180005B02
0x180005a83  add     [rcx+28h], ebx
0x180005a86  xor     r14d, r14d
0x180005a89  xor     edx, edx
0x180005a8b  jmp     short loc_180005AF5
0x180005a8d  test    ebx, ebx
0x180005a8f  jle     short loc_180005AAB
0x180005a91  mov     eax, dword ptr [rbp+var_20+8]
0x180005a94  cmp     eax, edi
0x180005a96  jb      short loc_180005A9D
0x180005a98  add     eax, ebx
0x180005a9a  mov     dword ptr [rbp+var_20+8], eax
0x180005a9d  mov     eax, dword ptr [rbp+var_20+0Ch]
0x180005aa0  cmp     eax, edi
0x180005aa2  jb      short loc_180005ADD
0x180005aa4  add     eax, ebx
0x180005aa6  mov     dword ptr [rbp+var_20+0Ch], eax
0x180005aa9  jmp     short loc_180005ADD
0x180005aab  mov     ecx, dword ptr [rbp+var_20+8]
0x180005aae  cmp     ecx, edi
0x180005ab0  jbe     short loc_180005AC4
0x180005ab2  mov     eax, edi
0x180005ab4  sub     eax, ebx
0x180005ab6  cmp     ecx, eax
0x180005ab8  jbe     short loc_180005AC1
0x180005aba  add     ecx, ebx
0x180005abc  mov     dword ptr [rbp+var_20+8], ecx
0x180005abf  jmp     short loc_180005AC4
0x180005ac1  mov     dword ptr [rbp+var_20+8], edi
0x180005ac4  mov     ecx, dword ptr [rbp+var_20+0Ch]
0x180005ac7  cmp     ecx, edi
0x180005ac9  jbe     short loc_180005ADD
0x180005acb  mov     eax, edi
0x180005acd  sub     eax, ebx
0x180005acf  cmp     ecx, eax
0x180005ad1  jbe     short loc_180005ADA
0x180005ad3  add     ecx, ebx
0x180005ad5  mov     dword ptr [rbp+var_20+0Ch], ecx
0x180005ad8  jmp     short loc_180005ADD
0x180005ada  mov     dword ptr [rbp+var_20+0Ch], edi
0x180005add  mov     r8d, r14d
0x180005ae0  lea     rdx, [rbp+var_20]
0x180005ae4  mov     rcx, rsi
0x180005ae7  call    TextLogUpdateSectionTag
0x180005aec  inc     r14d
0x180005aef  mov     rcx, rsi
0x180005af2  mov     edx, r14d
0x180005af5  lea     r8, [rbp+var_20]
0x180005af9  call    TextLogEnumerateOpenSections
0x180005afe  test    eax, eax
0x180005b00  jnz     short loc_180005A8D
0x180005b02  xor     eax, eax
0x180005b04  add     rsp, 40h
0x180005b08  pop     r14
0x180005b0a  pop     rdi
0x180005b0b  pop     rsi
0x180005b0c  pop     rbx
0x180005b0d  pop     rbp
0x180005b0e  retn
```
