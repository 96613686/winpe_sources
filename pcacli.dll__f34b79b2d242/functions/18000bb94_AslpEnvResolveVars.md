# AslpEnvResolveVars

- ea: `0x18000bb94`
- end: `0x18000bed5`
- name: `AslpEnvResolveVars`
- size: `833`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, __int16, __int16, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000b6dc`

## callees

- `0x180007668`
- `0x180007738`
- `0x180008256`
- `0x180008ab0`
- `0x18000bb94`

## string_xrefs

- `0x18000be37`: `RtlStringCchCopyW failed [%x]`
- `0x18000be4a`: `RtlStringCchCopyW failed [%x]`
- `0x18000bea3`: `RtlStringCchCopyW failed [%x]`
- `0x18000be5e`: `ResolvedPath is NULL or zero size [%#x]`
- `0x18000bd28`: `Invalid combination of Host/Current processor architectures passed to AslpEnvResolveVars Host: %x4 Current: %x4`

## pseudocode

```c
__int64 __fastcall AslpEnvResolveVars(
        unsigned __int16 *a1,
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
  unsigned __int16 *v29; // [rsp+70h] [rbp+8h]

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
    v15 = qword_180014110[3 * v12];
    if ( a2 > v15 )
    {
      if ( !wcsnicmp_0(a1, off_180014100[v14], v15) )
      {
        v10 = a2 + HIDWORD(qword_180014110[v14]) - LODWORD(qword_180014110[v14]);
        if ( v10 > (unsigned int)v8 )
        {
          v21 = -1073741789;
          goto LABEL_40;
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
            v24 = RtlStringCchCopyW(v11, v8, (&off_180014108)[v14]);
            v21 = v24;
            if ( v24 < 0 )
            {
              LODWORD(v28) = v24;
              AslLogCallPrintf(1, "AslpEnvResolveVars", 1091, "RtlStringCchCopyW failed [%x]", v28);
              return v21;
            }
            v25 = RtlStringCchCatW(v11, v8, &v29[LODWORD(qword_180014110[v14])]);
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
            if ( word_180014080[8 * i] == v16 && word_180014082[8 * i] == a6 )
            {
              v19 = RtlStringCchCopyW(a3, v8, L"%systemroot%");
              v21 = v19;
              if ( v19 < 0 )
              {
                LODWORD(v28) = v19;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1051, "RtlStringCchCopyW failed [%x]", v28);
                return v21;
              }
              v22 = RtlStringCchCatW(a3, v8, (&off_180014088)[v20]);
              v21 = v22;
              if ( v22 < 0 )
              {
                LODWORD(v28) = v22;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1057, "RtlStringCchCatW failed [%x]", v28);
                return v21;
              }
              v23 = RtlStringCchCatW(a3, v8, &v29[LODWORD(qword_180014110[v14])]);
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
LABEL_40:
  *a7 = v10;
  return v21;
}

```

## disassembly

```asm
0x18000bb94  mov     [rsp+arg_8], rbx
0x18000bb99  mov     [rsp+arg_10], r8
0x18000bb9e  mov     [rsp+arg_0], rcx
0x18000bba3  push    rbp
0x18000bba4  push    rsi
0x18000bba5  push    rdi
0x18000bba6  push    r12
0x18000bba8  push    r13
0x18000bbaa  push    r14
0x18000bbac  push    r15
0x18000bbae  sub     rsp, 30h
0x18000bbb2  xor     ebx, ebx
0x18000bbb4  mov     r14d, r9d
0x18000bbb7  xor     r13d, r13d
0x18000bbba  lea     r11, cs:180000000h
0x18000bbc1  xor     esi, esi
0x18000bbc3  mov     rdi, r8
0x18000bbc6  xor     r12d, r12d
0x18000bbc9  mov     ebp, edx
0x18000bbcb  test    ebx, ebx
0x18000bbcd  jnz     loc_18000BEB2
0x18000bbd3  lea     r15, [r12+r12*2]
0x18000bbd7  shl     r15, 3
0x18000bbdb  mov     eax, [r15+r11+14110h]
0x18000bbe3  cmp     ebp, eax
0x18000bbe5  jbe     loc_18000BDDB
0x18000bbeb  mov     rdx, [r15+r11+14100h]; String2
0x18000bbf3  mov     r8d, eax; MaxCount
0x18000bbf6  call    _wcsnicmp_0
0x18000bbfb  lea     r11, cs:180000000h
0x18000bc02  test    eax, eax
0x18000bc04  jnz     loc_18000BDD6
0x18000bc0a  mov     esi, [r15+r11+14114h]
0x18000bc12  sub     esi, [r15+r11+14110h]
0x18000bc1a  add     esi, ebp
0x18000bc1c  cmp     esi, r14d
0x18000bc1f  ja      loc_18000BE82
0x18000bc25  test    rdi, rdi
0x18000bc28  jz      loc_18000BE59
0x18000bc2e  test    r14d, r14d
0x18000bc31  jz      loc_18000BE59
0x18000bc37  test    r12, r12
0x18000bc3a  jnz     loc_18000BD5A
0x18000bc40  movzx   ecx, [rsp+68h+arg_20]
0x18000bc48  lea     rdx, cs:180000000h
0x18000bc4f  xor     edi, edi
0x18000bc51  movzx   eax, [rsp+68h+arg_28]
0x18000bc59  mov     r11, rdi
0x18000bc5c  add     r11, r11
0x18000bc5f  cmp     rva word_180014080[rdx+r11*8], cx
0x18000bc68  jnz     loc_18000BD0F
0x18000bc6e  cmp     rva word_180014082[rdx+r11*8], ax
0x18000bc77  jnz     loc_18000BD0F
0x18000bc7d  mov     r13, [rsp+68h+arg_10]
0x18000bc85  lea     r8, aSystemroot; "%systemroot%"
0x18000bc8c  mov     rcx, r13; unsigned __int16 *
0x18000bc8f  mov     rdx, r14; unsigned __int64
0x18000bc92  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bc97  mov     ebx, eax
0x18000bc99  test    eax, eax
0x18000bc9b  js      loc_18000BE33
0x18000bca1  lea     r8, cs:180000000h
0x18000bca8  mov     rdx, r14
0x18000bcab  mov     r8, rva off_180014088[r8+r11*8]; "\\System32" ...
0x18000bcb3  mov     rcx, r13
0x18000bcb6  call    RtlStringCchCatW
0x18000bcbb  mov     ebx, eax
0x18000bcbd  test    eax, eax
0x18000bcbf  js      loc_18000BE20
0x18000bcc5  mov     rcx, [rsp+68h+arg_0]
0x18000bcca  lea     rax, cs:180000000h
0x18000bcd1  mov     eax, [r15+rax+14110h]
0x18000bcd9  mov     rdx, r14
0x18000bcdc  lea     r8, [rcx+rax*2]
0x18000bce0  mov     rcx, r13
0x18000bce3  call    RtlStringCchCatW
0x18000bce8  mov     ebx, eax
0x18000bcea  test    eax, eax
0x18000bcec  js      loc_18000BE0D
0x18000bcf2  movzx   eax, [rsp+68h+arg_28]
0x18000bcfa  lea     rdx, cs:180000000h
0x18000bd01  movzx   ecx, [rsp+68h+arg_20]
0x18000bd09  mov     r13d, 1
0x18000bd0f  inc     rdi
0x18000bd12  cmp     rdi, 8
0x18000bd16  jb      loc_18000BC51
0x18000bd1c  test    r13d, r13d
0x18000bd1f  jnz     loc_18000BDC2
0x18000bd25  movzx   ecx, cx
0x18000bd28  lea     r9, aInvalidCombina; "Invalid combination of Host/Current pro"...
0x18000bd2f  movzx   eax, ax
0x18000bd32  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x18000bd39  mov     [rsp+68h+var_40], eax
0x18000bd3d  mov     r8d, 432h
0x18000bd43  mov     dword ptr [rsp+68h+var_48], ecx
0x18000bd47  lea     ecx, [r13+1]
0x18000bd4b  call    AslLogCallPrintf
0x18000bd50  mov     rdi, [rsp+68h+arg_10]
0x18000bd58  jmp     short loc_18000BD5F
0x18000bd5a  test    r13d, r13d
0x18000bd5d  jnz     short loc_18000BDD1
0x18000bd5f  lea     rax, cs:180000000h
0x18000bd66  mov     rdx, r14; unsigned __int64
0x18000bd69  mov     r8, [r15+rax+14108h]; unsigned __int16 *
0x18000bd71  mov     rcx, rdi; unsigned __int16 *
0x18000bd74  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bd79  mov     ebx, eax
0x18000bd7b  test    eax, eax
0x18000bd7d  js      loc_18000BE46
0x18000bd83  mov     rcx, [rsp+68h+arg_0]
0x18000bd88  lea     rax, cs:180000000h
0x18000bd8f  mov     eax, [r15+rax+14110h]
0x18000bd97  mov     rdx, r14
0x18000bd9a  lea     r8, [rcx+rax*2]
0x18000bd9e  mov     rcx, rdi
0x18000bda1  call    RtlStringCchCatW
0x18000bda6  mov     ebx, eax
0x18000bda8  test    eax, eax
0x18000bdaa  jns     short loc_18000BDCA
0x18000bdac  mov     dword ptr [rsp+68h+var_48], eax
0x18000bdb0  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x18000bdb7  mov     r8d, 449h
0x18000bdbd  jmp     loc_18000BE6F
0x18000bdc2  mov     rdi, [rsp+68h+arg_10]
0x18000bdca  lea     r11, cs:180000000h
0x18000bdd1  mov     ebx, 1
0x18000bdd6  mov     rcx, [rsp+68h+arg_0]
0x18000bddb  inc     r12
0x18000bdde  cmp     r12, 4
0x18000bde2  jb      loc_18000BBCB
0x18000bde8  test    ebx, ebx
0x18000bdea  jnz     loc_18000BEB2
0x18000bdf0  cmp     ebp, r14d
0x18000bdf3  jbe     loc_18000BE89
0x18000bdf9  mov     rax, [rsp+68h+arg_30]
0x18000be01  mov     ebx, 0C0000023h
0x18000be06  mov     [rax], ebp
0x18000be08  jmp     loc_18000BEBE
0x18000be0d  mov     dword ptr [rsp+68h+var_48], eax
0x18000be11  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x18000be18  mov     r8d, 427h
0x18000be1e  jmp     short loc_18000BE6F
0x18000be20  mov     dword ptr [rsp+68h+var_48], eax
0x18000be24  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x18000be2b  mov     r8d, 421h
0x18000be31  jmp     short loc_18000BE6F
0x18000be33  mov     dword ptr [rsp+68h+var_48], eax
0x18000be37  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x18000be3e  mov     r8d, 41Bh
0x18000be44  jmp     short loc_18000BE6F
0x18000be46  mov     dword ptr [rsp+68h+var_48], eax
0x18000be4a  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x18000be51  mov     r8d, 443h
0x18000be57  jmp     short loc_18000BE6F
0x18000be59  mov     ebx, 0C000000Dh
0x18000be5e  lea     r9, aResolvedpathIs; "ResolvedPath is NULL or zero size [%#x]"
0x18000be65  mov     dword ptr [rsp+68h+var_48], ebx
0x18000be69  mov     r8d, 40Bh
0x18000be6f  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x18000be76  mov     ecx, 1
0x18000be7b  call    AslLogCallPrintf
0x18000be80  jmp     short loc_18000BEBE
0x18000be82  mov     ebx, 0C0000023h
0x18000be87  jmp     short loc_18000BEB4
0x18000be89  mov     r8, rcx; unsigned __int16 *
0x18000be8c  mov     rdx, r14; unsigned __int64
0x18000be8f  mov     rcx, rdi; unsigned __int16 *
0x18000be92  mov     esi, ebp
0x18000be94  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000be99  mov     ebx, eax
0x18000be9b  test    eax, eax
0x18000be9d  jns     short loc_18000BEB2
0x18000be9f  mov     dword ptr [rsp+68h+var_48], eax
0x18000bea3  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x18000beaa  mov     r8d, 469h
0x18000beb0  jmp     short loc_18000BE6F
0x18000beb2  xor     ebx, ebx
0x18000beb4  mov     rax, [rsp+68h+arg_30]
0x18000bebc  mov     [rax], esi
0x18000bebe  mov     eax, ebx
0x18000bec0  mov     rbx, [rsp+68h+arg_8]
0x18000bec5  add     rsp, 30h
0x18000bec9  pop     r15
0x18000becb  pop     r14
0x18000becd  pop     r13
0x18000becf  pop     r12
0x18000bed1  pop     rdi
0x18000bed2  pop     rsi
0x18000bed3  pop     rbp
0x18000bed4  retn
```
