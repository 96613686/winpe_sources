# AslpEnvResolveVars

- ea: `0x18000f39c`
- end: `0x18000f6dd`
- name: `AslpEnvResolveVars`
- size: `833`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000cd8c`

## callees

- `0x180002688`
- `0x18000e240`
- `0x18000f39c`
- `0x180013f04`
- `0x180013fc8`

## string_xrefs

- `0x18000f63f`: `RtlStringCchCopyW failed [%x]`
- `0x18000f652`: `RtlStringCchCopyW failed [%x]`
- `0x18000f6ab`: `RtlStringCchCopyW failed [%x]`
- `0x18000f666`: `ResolvedPath is NULL or zero size [%#x]`
- `0x18000f530`: `Invalid combination of Host/Current processor architectures passed to AslpEnvResolveVars Host: %x4 Current: %x4`

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
  unsigned __int64 v8; // r14
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
    v15 = qword_1800260B0[3 * v12];
    if ( a2 > v15 )
    {
      if ( !wcsnicmp_0(a1, off_1800260A0[v14], v15) )
      {
        v10 = a2 + HIDWORD(qword_1800260B0[v14]) - LODWORD(qword_1800260B0[v14]);
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
            v24 = RtlStringCchCopyW(v11, v8, (&off_1800260A8)[v14]);
            v21 = v24;
            if ( v24 < 0 )
            {
              LODWORD(v28) = v24;
              AslLogCallPrintf(1, "AslpEnvResolveVars", 1091, "RtlStringCchCopyW failed [%x]", v28);
              return v21;
            }
            v25 = RtlStringCchCatW(v11, v8, &v29[LODWORD(qword_1800260B0[v14])]);
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
            if ( word_180026020[8 * i] == v16 && word_180026022[8 * i] == a6 )
            {
              v19 = RtlStringCchCopyW(a3, v8, L"%systemroot%");
              v21 = v19;
              if ( v19 < 0 )
              {
                LODWORD(v28) = v19;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1051, "RtlStringCchCopyW failed [%x]", v28);
                return v21;
              }
              v22 = RtlStringCchCatW(a3, v8, (&off_180026028)[v20]);
              v21 = v22;
              if ( v22 < 0 )
              {
                LODWORD(v28) = v22;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1057, "RtlStringCchCatW failed [%x]", v28);
                return v21;
              }
              v23 = RtlStringCchCatW(a3, v8, &v29[LODWORD(qword_1800260B0[v14])]);
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
0x18000f39c  mov     [rsp+arg_8], rbx
0x18000f3a1  mov     [rsp+arg_10], r8
0x18000f3a6  mov     [rsp+arg_0], rcx
0x18000f3ab  push    rbp
0x18000f3ac  push    rsi
0x18000f3ad  push    rdi
0x18000f3ae  push    r12
0x18000f3b0  push    r13
0x18000f3b2  push    r14
0x18000f3b4  push    r15
0x18000f3b6  sub     rsp, 30h
0x18000f3ba  xor     ebx, ebx
0x18000f3bc  mov     r14d, r9d
0x18000f3bf  xor     r13d, r13d
0x18000f3c2  lea     r11, cs:180000000h
0x18000f3c9  xor     esi, esi
0x18000f3cb  mov     rdi, r8
0x18000f3ce  xor     r12d, r12d
0x18000f3d1  mov     ebp, edx
0x18000f3d3  test    ebx, ebx
0x18000f3d5  jnz     loc_18000F6BA
0x18000f3db  lea     r15, [r12+r12*2]
0x18000f3df  shl     r15, 3
0x18000f3e3  mov     eax, [r15+r11+260B0h]
0x18000f3eb  cmp     ebp, eax
0x18000f3ed  jbe     loc_18000F5E3
0x18000f3f3  mov     rdx, [r15+r11+260A0h]; String2
0x18000f3fb  mov     r8d, eax; MaxCount
0x18000f3fe  call    _wcsnicmp_0
0x18000f403  lea     r11, cs:180000000h
0x18000f40a  test    eax, eax
0x18000f40c  jnz     loc_18000F5DE
0x18000f412  mov     esi, [r15+r11+260B4h]
0x18000f41a  sub     esi, [r15+r11+260B0h]
0x18000f422  add     esi, ebp
0x18000f424  cmp     esi, r14d
0x18000f427  ja      loc_18000F68A
0x18000f42d  test    rdi, rdi
0x18000f430  jz      loc_18000F661
0x18000f436  test    r14d, r14d
0x18000f439  jz      loc_18000F661
0x18000f43f  test    r12, r12
0x18000f442  jnz     loc_18000F562
0x18000f448  movzx   ecx, [rsp+68h+arg_20]
0x18000f450  lea     rdx, cs:180000000h
0x18000f457  xor     edi, edi
0x18000f459  movzx   eax, [rsp+68h+arg_28]
0x18000f461  mov     r11, rdi
0x18000f464  add     r11, r11
0x18000f467  cmp     rva word_180026020[rdx+r11*8], cx
0x18000f470  jnz     loc_18000F517
0x18000f476  cmp     rva word_180026022[rdx+r11*8], ax
0x18000f47f  jnz     loc_18000F517
0x18000f485  mov     r13, [rsp+68h+arg_10]
0x18000f48d  lea     r8, aSystemroot; "%systemroot%"
0x18000f494  mov     rcx, r13
0x18000f497  mov     rdx, r14
0x18000f49a  call    RtlStringCchCopyW
0x18000f49f  mov     ebx, eax
0x18000f4a1  test    eax, eax
0x18000f4a3  js      loc_18000F63B
0x18000f4a9  lea     r8, cs:180000000h
0x18000f4b0  mov     rdx, r14; unsigned __int64
0x18000f4b3  mov     r8, rva off_180026028[r8+r11*8]; unsigned __int16 *
0x18000f4bb  mov     rcx, r13; unsigned __int16 *
0x18000f4be  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f4c3  mov     ebx, eax
0x18000f4c5  test    eax, eax
0x18000f4c7  js      loc_18000F628
0x18000f4cd  mov     rcx, [rsp+68h+arg_0]
0x18000f4d2  lea     rax, cs:180000000h
0x18000f4d9  mov     eax, [r15+rax+260B0h]
0x18000f4e1  mov     rdx, r14; unsigned __int64
0x18000f4e4  lea     r8, [rcx+rax*2]; unsigned __int16 *
0x18000f4e8  mov     rcx, r13; unsigned __int16 *
0x18000f4eb  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f4f0  mov     ebx, eax
0x18000f4f2  test    eax, eax
0x18000f4f4  js      loc_18000F615
0x18000f4fa  movzx   eax, [rsp+68h+arg_28]
0x18000f502  lea     rdx, cs:180000000h
0x18000f509  movzx   ecx, [rsp+68h+arg_20]
0x18000f511  mov     r13d, 1
0x18000f517  inc     rdi
0x18000f51a  cmp     rdi, 8
0x18000f51e  jb      loc_18000F459
0x18000f524  test    r13d, r13d
0x18000f527  jnz     loc_18000F5CA
0x18000f52d  movzx   ecx, cx
0x18000f530  lea     r9, aInvalidCombina; "Invalid combination of Host/Current pro"...
0x18000f537  movzx   eax, ax
0x18000f53a  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x18000f541  mov     [rsp+68h+var_40], eax
0x18000f545  mov     r8d, 432h
0x18000f54b  mov     dword ptr [rsp+68h+var_48], ecx
0x18000f54f  lea     ecx, [r13+1]
0x18000f553  call    AslLogCallPrintf
0x18000f558  mov     rdi, [rsp+68h+arg_10]
0x18000f560  jmp     short loc_18000F567
0x18000f562  test    r13d, r13d
0x18000f565  jnz     short loc_18000F5D9
0x18000f567  lea     rax, cs:180000000h
0x18000f56e  mov     rdx, r14
0x18000f571  mov     r8, [r15+rax+260A8h]
0x18000f579  mov     rcx, rdi
0x18000f57c  call    RtlStringCchCopyW
0x18000f581  mov     ebx, eax
0x18000f583  test    eax, eax
0x18000f585  js      loc_18000F64E
0x18000f58b  mov     rcx, [rsp+68h+arg_0]
0x18000f590  lea     rax, cs:180000000h
0x18000f597  mov     eax, [r15+rax+260B0h]
0x18000f59f  mov     rdx, r14; unsigned __int64
0x18000f5a2  lea     r8, [rcx+rax*2]; unsigned __int16 *
0x18000f5a6  mov     rcx, rdi; unsigned __int16 *
0x18000f5a9  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f5ae  mov     ebx, eax
0x18000f5b0  test    eax, eax
0x18000f5b2  jns     short loc_18000F5D2
0x18000f5b4  mov     dword ptr [rsp+68h+var_48], eax
0x18000f5b8  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x18000f5bf  mov     r8d, 449h
0x18000f5c5  jmp     loc_18000F677
0x18000f5ca  mov     rdi, [rsp+68h+arg_10]
0x18000f5d2  lea     r11, cs:180000000h
0x18000f5d9  mov     ebx, 1
0x18000f5de  mov     rcx, [rsp+68h+arg_0]
0x18000f5e3  inc     r12
0x18000f5e6  cmp     r12, 4
0x18000f5ea  jb      loc_18000F3D3
0x18000f5f0  test    ebx, ebx
0x18000f5f2  jnz     loc_18000F6BA
0x18000f5f8  cmp     ebp, r14d
0x18000f5fb  jbe     loc_18000F691
0x18000f601  mov     rax, [rsp+68h+arg_30]
0x18000f609  mov     ebx, 0C0000023h
0x18000f60e  mov     [rax], ebp
0x18000f610  jmp     loc_18000F6C6
0x18000f615  mov     dword ptr [rsp+68h+var_48], eax
0x18000f619  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x18000f620  mov     r8d, 427h
0x18000f626  jmp     short loc_18000F677
0x18000f628  mov     dword ptr [rsp+68h+var_48], eax
0x18000f62c  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x18000f633  mov     r8d, 421h
0x18000f639  jmp     short loc_18000F677
0x18000f63b  mov     dword ptr [rsp+68h+var_48], eax
0x18000f63f  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x18000f646  mov     r8d, 41Bh
0x18000f64c  jmp     short loc_18000F677
0x18000f64e  mov     dword ptr [rsp+68h+var_48], eax
0x18000f652  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x18000f659  mov     r8d, 443h
0x18000f65f  jmp     short loc_18000F677
0x18000f661  mov     ebx, 0C000000Dh
0x18000f666  lea     r9, aResolvedpathIs; "ResolvedPath is NULL or zero size [%#x]"
0x18000f66d  mov     dword ptr [rsp+68h+var_48], ebx
0x18000f671  mov     r8d, 40Bh
0x18000f677  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x18000f67e  mov     ecx, 1
0x18000f683  call    AslLogCallPrintf
0x18000f688  jmp     short loc_18000F6C6
0x18000f68a  mov     ebx, 0C0000023h
0x18000f68f  jmp     short loc_18000F6BC
0x18000f691  mov     r8, rcx
0x18000f694  mov     rdx, r14
0x18000f697  mov     rcx, rdi
0x18000f69a  mov     esi, ebp
0x18000f69c  call    RtlStringCchCopyW
0x18000f6a1  mov     ebx, eax
0x18000f6a3  test    eax, eax
0x18000f6a5  jns     short loc_18000F6BA
0x18000f6a7  mov     dword ptr [rsp+68h+var_48], eax
0x18000f6ab  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x18000f6b2  mov     r8d, 469h
0x18000f6b8  jmp     short loc_18000F677
0x18000f6ba  xor     ebx, ebx
0x18000f6bc  mov     rax, [rsp+68h+arg_30]
0x18000f6c4  mov     [rax], esi
0x18000f6c6  mov     eax, ebx
0x18000f6c8  mov     rbx, [rsp+68h+arg_8]
0x18000f6cd  add     rsp, 30h
0x18000f6d1  pop     r15
0x18000f6d3  pop     r14
0x18000f6d5  pop     r13
0x18000f6d7  pop     r12
0x18000f6d9  pop     rdi
0x18000f6da  pop     rsi
0x18000f6db  pop     rbp
0x18000f6dc  retn
```
