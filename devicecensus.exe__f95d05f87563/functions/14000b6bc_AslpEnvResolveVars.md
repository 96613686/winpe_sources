# AslpEnvResolveVars

- ea: `0x14000b6bc`
- end: `0x14000b9fe`
- name: `AslpEnvResolveVars`
- size: `834`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int, unsigned __int16 *, unsigned int, unsigned __int16, unsigned __int16, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000b1f0`

## callees

- `0x140004998`
- `0x140007074`
- `0x14000800c`
- `0x14000b6bc`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x14000b71e`
- `msvcrt!_wcsnicmp` at `0x14000b71e`

## string_xrefs

- `0x14000b960`: `RtlStringCchCopyW failed [%x]`
- `0x14000b973`: `RtlStringCchCopyW failed [%x]`
- `0x14000b9cc`: `RtlStringCchCopyW failed [%x]`
- `0x14000b987`: `ResolvedPath is NULL or zero size [%#x]`
- `0x14000b851`: `Invalid combination of Host/Current processor architectures passed to AslpEnvResolveVars Host: %x4 Current: %x4`

## pseudocode

```c
__int64 __fastcall AslpEnvResolveVars(
        const wchar_t *a1,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 a5,
        unsigned __int16 a6,
        unsigned int *a7)
{
  int v7; // ebx
  __int64 v8; // r14
  int v9; // r13d
  unsigned int v10; // esi
  unsigned __int16 *v11; // rdi
  __int64 v12; // r12
  __int64 v14; // r15
  unsigned int v15; // eax
  unsigned __int16 v16; // cx
  unsigned __int64 i; // rdi
  unsigned __int16 v18; // ax
  int v19; // eax
  __int64 v20; // r11
  unsigned int v21; // ebx
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 v28; // [rsp+20h] [rbp-48h]
  const wchar_t *v29; // [rsp+70h] [rbp+8h]

  v29 = a1;
  v7 = 0;
  v8 = a4;
  v9 = 0;
  v10 = 0;
  v11 = a3;
  v12 = 0;
  while ( !v7 )
  {
    v14 = 3 * v12;
    v15 = qword_14001C0D0[3 * v12];
    if ( a2 > v15 )
    {
      if ( !_wcsnicmp(a1, off_14001C0C0[v14], v15) )
      {
        v10 = a2 + HIDWORD(qword_14001C0D0[v14]) - LODWORD(qword_14001C0D0[v14]);
        if ( v10 > (unsigned int)v8 )
        {
          v21 = -1073741789;
          goto LABEL_39;
        }
        if ( !v11 || !(_DWORD)v8 )
        {
          v21 = -1073741811;
          LODWORD(v28) = -1073741811;
          AslLogCallPrintf(1, "AslpEnvResolveVars", 1035, "ResolvedPath is NULL or zero size [%#x]", v28);
          return v21;
        }
        if ( v12 )
        {
          if ( !v9 )
          {
LABEL_20:
            v24 = RtlStringCchCopyW(v11, v8, (&off_14001C0C8)[v14]);
            v21 = v24;
            if ( v24 < 0 )
            {
              LODWORD(v28) = v24;
              AslLogCallPrintf(1, "AslpEnvResolveVars", 1091, "RtlStringCchCopyW failed [%x]", v28);
              return v21;
            }
            v25 = RtlStringCchCatW(v11, v8, (unsigned __int16 *)&v29[LODWORD(qword_14001C0D0[v14])]);
            v21 = v25;
            if ( v25 < 0 )
            {
              LODWORD(v28) = v25;
              AslLogCallPrintf(1, "AslpEnvResolveVars", 1097, "RtlStringCchCatW failed [%x]", v28);
              return v21;
            }
          }
        }
        else
        {
          v16 = a5;
          for ( i = 0; i < 8; ++i )
          {
            v18 = a6;
            if ( word_14001C040[8 * i] == v16 && word_14001C042[8 * i] == a6 )
            {
              v19 = RtlStringCchCopyW(a3, v8, L"%systemroot%");
              v21 = v19;
              if ( v19 < 0 )
              {
                LODWORD(v28) = v19;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1051, "RtlStringCchCopyW failed [%x]", v28);
                return v21;
              }
              v22 = RtlStringCchCatW(a3, v8, (&off_14001C048)[v20]);
              v21 = v22;
              if ( v22 < 0 )
              {
                LODWORD(v28) = v22;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1057, "RtlStringCchCatW failed [%x]", v28);
                return v21;
              }
              v23 = RtlStringCchCatW(a3, v8, (unsigned __int16 *)&v29[LODWORD(qword_14001C0D0[v14])]);
              v21 = v23;
              if ( v23 < 0 )
              {
                LODWORD(v28) = v23;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1063, "RtlStringCchCatW failed [%x]", v28);
                return v21;
              }
              v18 = a6;
              v16 = a5;
              v9 = 1;
            }
          }
          if ( !v9 )
          {
            AslLogCallPrintf(
              1,
              "AslpEnvResolveVars",
              1074,
              "Invalid combination of Host/Current processor architectures passed to AslpEnvResolveVars Host: %x4 Current: %x4",
              v16,
              v18);
            v11 = a3;
            goto LABEL_20;
          }
          v11 = a3;
        }
        v7 = 1;
      }
      a1 = v29;
    }
    if ( (unsigned __int64)++v12 >= 4 )
    {
      if ( !v7 )
      {
        if ( a2 > (unsigned int)v8 )
        {
          v21 = -1073741789;
          *a7 = a2;
          return v21;
        }
        v10 = a2;
        v26 = RtlStringCchCopyW(v11, v8, a1);
        v21 = v26;
        if ( v26 < 0 )
        {
          LODWORD(v28) = v26;
          AslLogCallPrintf(1, "AslpEnvResolveVars", 1129, "RtlStringCchCopyW failed [%x]", v28);
          return v21;
        }
      }
      break;
    }
  }
  v21 = 0;
LABEL_39:
  *a7 = v10;
  return v21;
}

```

## disassembly

```asm
0x14000b6bc  mov     [rsp+arg_8], rbx
0x14000b6c1  mov     [rsp+arg_10], r8
0x14000b6c6  mov     [rsp+arg_0], rcx
0x14000b6cb  push    rbp
0x14000b6cc  push    rsi
0x14000b6cd  push    rdi
0x14000b6ce  push    r12
0x14000b6d0  push    r13
0x14000b6d2  push    r14
0x14000b6d4  push    r15
0x14000b6d6  sub     rsp, 30h
0x14000b6da  xor     ebx, ebx
0x14000b6dc  mov     r14d, r9d
0x14000b6df  xor     r13d, r13d
0x14000b6e2  lea     r11, __ImageBase
0x14000b6e9  xor     esi, esi
0x14000b6eb  mov     rdi, r8
0x14000b6ee  xor     r12d, r12d
0x14000b6f1  mov     ebp, edx
0x14000b6f3  test    ebx, ebx
0x14000b6f5  jnz     loc_14000B9DB
0x14000b6fb  lea     r15, [r12+r12*2]
0x14000b6ff  shl     r15, 3
0x14000b703  mov     eax, [r15+r11+1C0D0h]
0x14000b70b  cmp     ebp, eax
0x14000b70d  jbe     loc_14000B904
0x14000b713  mov     rdx, [r15+r11+1C0C0h]; String2
0x14000b71b  mov     r8d, eax; MaxCount
0x14000b71e  call    cs:__imp__wcsnicmp
0x14000b724  lea     r11, __ImageBase
0x14000b72b  test    eax, eax
0x14000b72d  jnz     loc_14000B8FF
0x14000b733  mov     esi, [r15+r11+1C0D4h]
0x14000b73b  sub     esi, [r15+r11+1C0D0h]
0x14000b743  add     esi, ebp
0x14000b745  cmp     esi, r14d
0x14000b748  ja      loc_14000B9AB
0x14000b74e  test    rdi, rdi
0x14000b751  jz      loc_14000B982
0x14000b757  test    r14d, r14d
0x14000b75a  jz      loc_14000B982
0x14000b760  test    r12, r12
0x14000b763  jnz     loc_14000B883
0x14000b769  movzx   ecx, [rsp+68h+arg_20]
0x14000b771  lea     rdx, __ImageBase
0x14000b778  xor     edi, edi
0x14000b77a  movzx   eax, [rsp+68h+arg_28]
0x14000b782  mov     r11, rdi
0x14000b785  add     r11, r11
0x14000b788  cmp     rva word_14001C040[rdx+r11*8], cx
0x14000b791  jnz     loc_14000B838
0x14000b797  cmp     rva word_14001C042[rdx+r11*8], ax
0x14000b7a0  jnz     loc_14000B838
0x14000b7a6  mov     r13, [rsp+68h+arg_10]
0x14000b7ae  lea     r8, aSystemroot; "%systemroot%"
0x14000b7b5  mov     rcx, r13
0x14000b7b8  mov     rdx, r14
0x14000b7bb  call    RtlStringCchCopyW
0x14000b7c0  mov     ebx, eax
0x14000b7c2  test    eax, eax
0x14000b7c4  js      loc_14000B95C
0x14000b7ca  lea     r8, __ImageBase
0x14000b7d1  mov     rdx, r14; unsigned __int64
0x14000b7d4  mov     r8, rva off_14001C048[r8+r11*8]; unsigned __int16 *
0x14000b7dc  mov     rcx, r13; unsigned __int16 *
0x14000b7df  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b7e4  mov     ebx, eax
0x14000b7e6  test    eax, eax
0x14000b7e8  js      loc_14000B949
0x14000b7ee  mov     rcx, [rsp+68h+arg_0]
0x14000b7f3  lea     rax, __ImageBase
0x14000b7fa  mov     eax, [r15+rax+1C0D0h]
0x14000b802  mov     rdx, r14; unsigned __int64
0x14000b805  lea     r8, [rcx+rax*2]; unsigned __int16 *
0x14000b809  mov     rcx, r13; unsigned __int16 *
0x14000b80c  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b811  mov     ebx, eax
0x14000b813  test    eax, eax
0x14000b815  js      loc_14000B936
0x14000b81b  movzx   eax, [rsp+68h+arg_28]
0x14000b823  lea     rdx, __ImageBase
0x14000b82a  movzx   ecx, [rsp+68h+arg_20]
0x14000b832  mov     r13d, 1
0x14000b838  inc     rdi
0x14000b83b  cmp     rdi, 8
0x14000b83f  jb      loc_14000B77A
0x14000b845  test    r13d, r13d
0x14000b848  jnz     loc_14000B8EB
0x14000b84e  movzx   ecx, cx
0x14000b851  lea     r9, aInvalidCombina; "Invalid combination of Host/Current pro"...
0x14000b858  movzx   eax, ax
0x14000b85b  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x14000b862  mov     [rsp+68h+var_40], eax
0x14000b866  mov     r8d, 432h
0x14000b86c  mov     dword ptr [rsp+68h+var_48], ecx
0x14000b870  lea     ecx, [r13+1]
0x14000b874  call    AslLogCallPrintf
0x14000b879  mov     rdi, [rsp+68h+arg_10]
0x14000b881  jmp     short loc_14000B888
0x14000b883  test    r13d, r13d
0x14000b886  jnz     short loc_14000B8FA
0x14000b888  lea     rax, __ImageBase
0x14000b88f  mov     rdx, r14
0x14000b892  mov     r8, [r15+rax+1C0C8h]
0x14000b89a  mov     rcx, rdi
0x14000b89d  call    RtlStringCchCopyW
0x14000b8a2  mov     ebx, eax
0x14000b8a4  test    eax, eax
0x14000b8a6  js      loc_14000B96F
0x14000b8ac  mov     rcx, [rsp+68h+arg_0]
0x14000b8b1  lea     rax, __ImageBase
0x14000b8b8  mov     eax, [r15+rax+1C0D0h]
0x14000b8c0  mov     rdx, r14; unsigned __int64
0x14000b8c3  lea     r8, [rcx+rax*2]; unsigned __int16 *
0x14000b8c7  mov     rcx, rdi; unsigned __int16 *
0x14000b8ca  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b8cf  mov     ebx, eax
0x14000b8d1  test    eax, eax
0x14000b8d3  jns     short loc_14000B8F3
0x14000b8d5  mov     dword ptr [rsp+68h+var_48], eax
0x14000b8d9  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x14000b8e0  mov     r8d, 449h
0x14000b8e6  jmp     loc_14000B998
0x14000b8eb  mov     rdi, [rsp+68h+arg_10]
0x14000b8f3  lea     r11, __ImageBase
0x14000b8fa  mov     ebx, 1
0x14000b8ff  mov     rcx, [rsp+68h+arg_0]
0x14000b904  inc     r12
0x14000b907  cmp     r12, 4
0x14000b90b  jb      loc_14000B6F3
0x14000b911  test    ebx, ebx
0x14000b913  jnz     loc_14000B9DB
0x14000b919  cmp     ebp, r14d
0x14000b91c  jbe     loc_14000B9B2
0x14000b922  mov     rax, [rsp+68h+arg_30]
0x14000b92a  mov     ebx, 0C0000023h
0x14000b92f  mov     [rax], ebp
0x14000b931  jmp     loc_14000B9E7
0x14000b936  mov     dword ptr [rsp+68h+var_48], eax
0x14000b93a  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x14000b941  mov     r8d, 427h
0x14000b947  jmp     short loc_14000B998
0x14000b949  mov     dword ptr [rsp+68h+var_48], eax
0x14000b94d  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x14000b954  mov     r8d, 421h
0x14000b95a  jmp     short loc_14000B998
0x14000b95c  mov     dword ptr [rsp+68h+var_48], eax
0x14000b960  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x14000b967  mov     r8d, 41Bh
0x14000b96d  jmp     short loc_14000B998
0x14000b96f  mov     dword ptr [rsp+68h+var_48], eax
0x14000b973  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x14000b97a  mov     r8d, 443h
0x14000b980  jmp     short loc_14000B998
0x14000b982  mov     ebx, 0C000000Dh
0x14000b987  lea     r9, aResolvedpathIs; "ResolvedPath is NULL or zero size [%#x]"
0x14000b98e  mov     dword ptr [rsp+68h+var_48], ebx
0x14000b992  mov     r8d, 40Bh
0x14000b998  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x14000b99f  mov     ecx, 1
0x14000b9a4  call    AslLogCallPrintf
0x14000b9a9  jmp     short loc_14000B9E7
0x14000b9ab  mov     ebx, 0C0000023h
0x14000b9b0  jmp     short loc_14000B9DD
0x14000b9b2  mov     r8, rcx
0x14000b9b5  mov     rdx, r14
0x14000b9b8  mov     rcx, rdi
0x14000b9bb  mov     esi, ebp
0x14000b9bd  call    RtlStringCchCopyW
0x14000b9c2  mov     ebx, eax
0x14000b9c4  test    eax, eax
0x14000b9c6  jns     short loc_14000B9DB
0x14000b9c8  mov     dword ptr [rsp+68h+var_48], eax
0x14000b9cc  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x14000b9d3  mov     r8d, 469h
0x14000b9d9  jmp     short loc_14000B998
0x14000b9db  xor     ebx, ebx
0x14000b9dd  mov     rax, [rsp+68h+arg_30]
0x14000b9e5  mov     [rax], esi
0x14000b9e7  mov     eax, ebx
0x14000b9e9  mov     rbx, [rsp+68h+arg_8]
0x14000b9ee  add     rsp, 30h
0x14000b9f2  pop     r15
0x14000b9f4  pop     r14
0x14000b9f6  pop     r13
0x14000b9f8  pop     r12
0x14000b9fa  pop     rdi
0x14000b9fb  pop     rsi
0x14000b9fc  pop     rbp
0x14000b9fd  retn
```
