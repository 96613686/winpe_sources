# IsCompressedVideoFormat

- ea: `0x18000d5cc`
- end: `0x18000d6e4`
- name: `IsCompressedVideoFormat`
- size: `280`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c560`

## callees

- `0x18000d5cc`

## pseudocode

```c
__int64 __fastcall IsCompressedVideoFormat(__int64 a1)
{
  unsigned int v1; // r8d
  unsigned __int64 v2; // rdx
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  bool v9; // zf

  v1 = 1;
  v2 = *(_QWORD *)(a1 + 4) - *(_QWORD *)&MFVideoFormat_Base.Data2;
  if ( !v2 )
    v2 = *(unsigned int *)(a1 + 12) - (unsigned __int64)*(unsigned int *)&MFVideoFormat_Base.Data4[4];
  if ( !v2 )
  {
    v3 = *(_DWORD *)a1;
    if ( *(_DWORD *)a1 <= 0x32315659u )
    {
      if ( v3 == 842094169 )
        return 0;
      if ( v3 <= 0x30313276 )
      {
        if ( v3 != 808530550 )
        {
          if ( v3 )
          {
            v4 = v3 - 3;
            if ( v4 )
            {
              v5 = v4 - 17;
              if ( v5 )
              {
                v6 = v5 - 2;
                if ( v6 )
                {
                  v7 = v6 - 1;
                  if ( v7 )
                  {
                    v8 = v7 - 1;
                    if ( v8 )
                    {
                      v9 = v8 == 17;
                      goto LABEL_21;
                    }
                  }
                }
              }
            }
          }
        }
        return 0;
      }
      if ( v3 == 808531030 || v3 == 808596553 || v3 == 825307737 || v3 == 825308249 || v3 == 825316942 )
        return 0;
      v9 = v3 == 842094158;
LABEL_21:
      if ( !v9 )
        return v1;
      return 0;
    }
    if ( v3 <= 0x56555949 )
    {
      if ( v3 == 1448433993
        || v3 == 844715353
        || v3 == 909193814
        || v3 == 961893977
        || v3 == 1345401945
        || v3 == 1431918169 )
      {
        return 0;
      }
      v9 = v3 == 1448433985;
      goto LABEL_21;
    }
    if ( v3 == 1498831189
      || v3 == -466162822
      || v3 == -466162821
      || v3 == -466162820
      || v3 == -466162819
      || v3 == -466162818 )
    {
      return 0;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18000d5cc  mov     rdx, [rcx+4]
0x18000d5d0  mov     r8d, 1
0x18000d5d6  sub     rdx, qword ptr cs:MFVideoFormat_Base.Data2
0x18000d5dd  jnz     short loc_18000D5EB
0x18000d5df  mov     edx, [rcx+0Ch]
0x18000d5e2  mov     eax, dword ptr cs:MFVideoFormat_Base.Data4+4
0x18000d5e8  sub     rdx, rax
0x18000d5eb  test    rdx, rdx
0x18000d5ee  jnz     loc_18000D6E0
0x18000d5f4  mov     eax, [rcx]
0x18000d5f6  mov     ecx, 32315659h
0x18000d5fb  cmp     eax, ecx
0x18000d5fd  ja      short loc_18000D67E
0x18000d5ff  jz      loc_18000D6DD
0x18000d605  mov     ecx, 30313276h
0x18000d60a  cmp     eax, ecx
0x18000d60c  ja      short loc_18000D64E
0x18000d60e  jz      loc_18000D6DD
0x18000d614  test    eax, eax
0x18000d616  jz      loc_18000D6DD
0x18000d61c  sub     eax, 3
0x18000d61f  jz      loc_18000D6DD
0x18000d625  sub     eax, 11h
0x18000d628  jz      loc_18000D6DD
0x18000d62e  sub     eax, 2
0x18000d631  jz      loc_18000D6DD
0x18000d637  sub     eax, r8d
0x18000d63a  jz      loc_18000D6DD
0x18000d640  sub     eax, r8d
0x18000d643  jz      loc_18000D6DD
0x18000d649  cmp     eax, 11h
0x18000d64c  jmp     short loc_18000D67A
0x18000d64e  cmp     eax, 30313456h
0x18000d653  jz      loc_18000D6DD
0x18000d659  cmp     eax, 30323449h
0x18000d65e  jz      short loc_18000D6DD
0x18000d660  cmp     eax, 31313259h
0x18000d665  jz      short loc_18000D6DD
0x18000d667  cmp     eax, 31313459h
0x18000d66c  jz      short loc_18000D6DD
0x18000d66e  cmp     eax, 3131564Eh
0x18000d673  jz      short loc_18000D6DD
0x18000d675  cmp     eax, 3231564Eh
0x18000d67a  jz      short loc_18000D6DD
0x18000d67c  jmp     short loc_18000D6E0
0x18000d67e  mov     ecx, 56555949h
0x18000d683  cmp     eax, ecx
0x18000d685  ja      short loc_18000D6B3
0x18000d687  jz      short loc_18000D6DD
0x18000d689  cmp     eax, 32595559h
0x18000d68e  jz      short loc_18000D6DD
0x18000d690  cmp     eax, 36313256h
0x18000d695  jz      short loc_18000D6DD
0x18000d697  cmp     eax, 39555659h
0x18000d69c  jz      short loc_18000D6DD
0x18000d69e  cmp     eax, 50313459h
0x18000d6a3  jz      short loc_18000D6DD
0x18000d6a5  cmp     eax, 55595659h
0x18000d6aa  jz      short loc_18000D6DD
0x18000d6ac  cmp     eax, 56555941h
0x18000d6b1  jmp     short loc_18000D67A
0x18000d6b3  cmp     eax, 59565955h
0x18000d6b8  jz      short loc_18000D6DD
0x18000d6ba  cmp     eax, 0E436EB7Ah
0x18000d6bf  jz      short loc_18000D6DD
0x18000d6c1  cmp     eax, 0E436EB7Bh
0x18000d6c6  jz      short loc_18000D6DD
0x18000d6c8  cmp     eax, 0E436EB7Ch
0x18000d6cd  jz      short loc_18000D6DD
0x18000d6cf  cmp     eax, 0E436EB7Dh
0x18000d6d4  jz      short loc_18000D6DD
0x18000d6d6  cmp     eax, 0E436EB7Eh
0x18000d6db  jnz     short loc_18000D6E0
0x18000d6dd  xor     r8d, r8d
0x18000d6e0  mov     eax, r8d
0x18000d6e3  retn
```
