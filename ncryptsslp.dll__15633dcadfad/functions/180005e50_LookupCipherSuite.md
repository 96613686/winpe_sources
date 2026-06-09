# LookupCipherSuite

- ea: `0x180005e50`
- end: `0x180005eb8`
- name: `LookupCipherSuite`
- size: `104`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800058e0`
- `0x180006720`
- `0x180011a40`
- `0x180011f10`
- `0x180013740`

## callees

- `0x180005e50`

## pseudocode

```c
__int64 __fastcall LookupCipherSuite(int a1, int a2)
{
  __int64 i; // rdx
  int v4; // r10d
  __int64 j; // rax
  _DWORD *v6; // rdx

  for ( i = 0; (unsigned int)i < 7; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned __int16)ProtocolVersionList[4 * i] == a1 )
    {
      v4 = dword_180031A24[2 * i];
      if ( v4 )
      {
        for ( j = 0; (unsigned int)j < g_dwCipherSuiteInfoTotalCount; j = (unsigned int)(j + 1) )
        {
          v6 = (_DWORD *)g_pCipherSuiteInfo[j];
          if ( v6 && v6[1] == a2 && (v4 & *v6) != 0 )
            return g_pCipherSuiteInfo[j];
        }
      }
      return 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180005e50  mov     r9d, edx
0x180005e53  lea     r11, __ImageBase
0x180005e5a  xor     edx, edx
0x180005e5c  cmp     edx, 7
0x180005e5f  jnb     short loc_180005EB5
0x180005e61  lea     r8, ds:0[rdx*8]
0x180005e69  movzx   eax, word ptr [r8+r11+31A20h]
0x180005e72  cmp     eax, ecx
0x180005e74  jz      short loc_180005E7A
0x180005e76  inc     edx
0x180005e78  jmp     short loc_180005E5C
0x180005e7a  mov     r10d, [r8+r11+31A24h]
0x180005e82  test    r10d, r10d
0x180005e85  jz      short loc_180005EB5
0x180005e87  mov     r8d, cs:g_dwCipherSuiteInfoTotalCount
0x180005e8e  xor     eax, eax
0x180005e90  cmp     eax, r8d
0x180005e93  jnb     short loc_180005EB5
0x180005e95  mov     rdx, rva g_pCipherSuiteInfo[r11+rax*8]
0x180005e9d  test    rdx, rdx
0x180005ea0  jz      short loc_180005EA8
0x180005ea2  cmp     [rdx+4], r9d
0x180005ea6  jz      short loc_180005EAC
0x180005ea8  inc     eax
0x180005eaa  jmp     short loc_180005E90
0x180005eac  test    [rdx], r10d
0x180005eaf  jz      short loc_180005EA8
0x180005eb1  mov     rax, rdx
0x180005eb4  retn
0x180005eb5  xor     eax, eax
0x180005eb7  retn
```
