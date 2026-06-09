# JsonHelpersInternal::JsonReader::ReadJsonObjectAlloc(RtlArray<JsonKeyValuePair *> * *)

- ea: `0x180005a6c`
- end: `0x180005eec`
- name: `?ReadJsonObjectAlloc@JsonReader@JsonHelpersInternal@@QEAAJPEAPEAV?$RtlArray@PEAUJsonKeyValuePair@@@@@Z`
- size: `1152`
- prototype: `__int64 __fastcall(JsonHelpersInternal::JsonReader *this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180004ef4`
- `0x180005ef4`

## callees

- `0x180001524`
- `0x180002e34`
- `0x180002eb0`
- `0x180002f54`
- `0x180005a6c`
- `0x180005ef4`
- `0x180006934`
- `0x1800191a2`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180005dd5`
- `msvcrt!wcscpy_s` at `0x180005dd5`
- `KERNEL32!HeapAlloc` at `0x180005d08`
- `KERNEL32!HeapAlloc` at `0x180005d60`
- `KERNEL32!HeapAlloc` at `0x180005d9c`
- `KERNEL32!HeapAlloc` at `0x180005d08`
- `KERNEL32!HeapAlloc` at `0x180005d60`
- `KERNEL32!HeapAlloc` at `0x180005d9c`
- `KERNEL32!GetProcessHeap` at `0x180005ac4`
- `KERNEL32!GetProcessHeap` at `0x180005ae2`
- `KERNEL32!GetProcessHeap` at `0x180005c74`
- `KERNEL32!GetProcessHeap` at `0x180005d51`
- `KERNEL32!GetProcessHeap` at `0x180005d8e`
- `KERNEL32!GetProcessHeap` at `0x180005daa`
- `KERNEL32!GetProcessHeap` at `0x180005ac4`
- `KERNEL32!GetProcessHeap` at `0x180005ae2`
- `KERNEL32!GetProcessHeap` at `0x180005c74`
- `KERNEL32!GetProcessHeap` at `0x180005d51`
- `KERNEL32!GetProcessHeap` at `0x180005d8e`
- `KERNEL32!GetProcessHeap` at `0x180005daa`
- `KERNEL32!HeapFree` at `0x180005c82`
- `KERNEL32!HeapFree` at `0x180005db8`
- `KERNEL32!HeapFree` at `0x180005c82`
- `KERNEL32!HeapFree` at `0x180005db8`
- `KERNEL32!HeapReAlloc` at `0x180005e04`
- `KERNEL32!HeapReAlloc` at `0x180005e04`

## pseudocode

```c
__int64 __fastcall JsonHelpersInternal::JsonReader::ReadJsonObjectAlloc(
        JsonHelpersInternal::JsonReader *this,
        _QWORD *a2)
{
  _QWORD *v4; // r15
  _OWORD *v5; // rax
  _OWORD *v6; // rdi
  __int64 v7; // r9
  __int64 v8; // rdx
  __int16 v9; // r8
  __int64 v10; // rcx
  int v11; // ebx
  __int16 v12; // r8
  __int64 v13; // r9
  __int16 v14; // r8
  int StringFromStreamAlloc; // eax
  wchar_t *v16; // r12
  __int64 v17; // r9
  __int64 v18; // rdx
  __int16 v19; // r8
  HANDLE v20; // rax
  unsigned __int64 v21; // r13
  unsigned __int64 v22; // rcx
  __int64 v23; // r14
  unsigned __int64 v24; // kr00_8
  unsigned __int64 v25; // kr10_8
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // r14
  unsigned __int128 v28; // rax
  unsigned __int64 v29; // kr20_8
  size_t v30; // r15
  void *v31; // r8
  void *v32; // rcx
  void *v33; // rax
  LPVOID v34; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v36; // r14
  __int64 v37; // rax
  rsize_t v38; // r15
  SIZE_T v39; // rbx
  HANDLE v40; // rax
  wchar_t *v41; // rax
  wchar_t *v42; // rbx
  HANDLE v43; // rax
  struct JsonValue *v44; // rax
  _QWORD *v45; // rax
  __int64 v46; // r9
  __int64 v47; // r8
  __int16 v48; // dx
  _OWORD *v50; // [rsp+20h] [rbp-20h] BYREF
  struct JsonKeyValuePair *v51; // [rsp+28h] [rbp-18h] BYREF
  LPVOID lpMem; // [rsp+30h] [rbp-10h] BYREF
  struct JsonKeyValuePair *v53; // [rsp+38h] [rbp-8h] BYREF
  struct JsonValue *v55; // [rsp+90h] [rbp+50h] BYREF
  _QWORD *v56; // [rsp+98h] [rbp+58h]

  v50 = 0;
  v4 = 0;
  v56 = 0;
  v51 = 0;
  v5 = operator new(0x30u);
  v6 = v5;
  if ( !v5 )
  {
    v11 = -2147024882;
    goto LABEL_81;
  }
  *v5 = 0;
  v5[1] = 0;
  v5[2] = 0;
  GetProcessHeap();
  *v6 = 0;
  v6[1] = 0;
  v6[2] = 0;
  *(_QWORD *)v6 = GetProcessHeap();
  *((_QWORD *)v6 + 4) = 16;
  *((_QWORD *)v6 + 2) = 0;
  *((_QWORD *)v6 + 3) = 0;
  *((_QWORD *)v6 + 5) = 0;
  *((_QWORD *)v6 + 1) = 8;
  v7 = *((_QWORD *)this + 1);
  v50 = v6;
  while ( 1 )
  {
    v8 = *(_QWORD *)this;
    v9 = *(_WORD *)(v7 + 2LL * *(_QWORD *)this);
    if ( v9 != 9
      && *(_WORD *)(v7 + 2LL * *(_QWORD *)this) != 10
      && *(_WORD *)(v7 + 2LL * *(_QWORD *)this) != 13
      && *(_WORD *)(v7 + 2LL * *(_QWORD *)this) != 32 )
    {
      break;
    }
    *(_QWORD *)this = v8 + 1;
    if ( !v9 )
      *(_QWORD *)this = v8;
  }
  v10 = v8 + 1;
  *(_QWORD *)this = v8 + 1;
  if ( !v9 )
  {
    *(_QWORD *)this = v8;
LABEL_12:
    v11 = -2147024883;
    goto LABEL_81;
  }
  if ( v9 != 123 )
    goto LABEL_12;
  while ( 1 )
  {
    v12 = *(_WORD *)(v7 + 2 * v10);
    if ( v12 != 9 && *(_WORD *)(v7 + 2 * v10) != 10 && *(_WORD *)(v7 + 2 * v10) != 13 && *(_WORD *)(v7 + 2 * v10) != 32 )
      break;
    *(_QWORD *)this = v10 + 1;
    if ( v12 )
      ++v10;
    else
      *(_QWORD *)this = v10;
  }
  if ( v12 == 125 )
  {
    *a2 = v6;
    *(_QWORD *)this = v10 + 1;
    goto LABEL_22;
  }
  do
  {
    v13 = *((_QWORD *)this + 1);
    v53 = 0;
    v55 = 0;
    lpMem = 0;
    while ( 1 )
    {
      v14 = *(_WORD *)(v13 + 2 * v10);
      if ( v14 != 9
        && *(_WORD *)(v13 + 2 * v10) != 10
        && *(_WORD *)(v13 + 2 * v10) != 13
        && *(_WORD *)(v13 + 2 * v10) != 32 )
      {
        break;
      }
      *(_QWORD *)this = v10 + 1;
      if ( v14 )
        ++v10;
      else
        *(_QWORD *)this = v10;
    }
    StringFromStreamAlloc = JsonHelpersInternal::JsonReader::ReadStringFromStreamAlloc(
                              this,
                              (const unsigned __int16 **)&lpMem);
    v16 = (wchar_t *)lpMem;
    v11 = StringFromStreamAlloc;
    if ( StringFromStreamAlloc >= 0 )
    {
      v17 = *((_QWORD *)this + 1);
      while ( 1 )
      {
        v18 = *(_QWORD *)this;
        v19 = *(_WORD *)(v17 + 2LL * *(_QWORD *)this);
        if ( v19 != 9
          && *(_WORD *)(v17 + 2LL * *(_QWORD *)this) != 10
          && *(_WORD *)(v17 + 2LL * *(_QWORD *)this) != 13
          && *(_WORD *)(v17 + 2LL * *(_QWORD *)this) != 32 )
        {
          break;
        }
        *(_QWORD *)this = v18 + 1;
        if ( !v19 )
          *(_QWORD *)this = v18;
      }
      *(_QWORD *)this = v18 + 1;
      if ( !v19 )
      {
        *(_QWORD *)this = v18;
LABEL_41:
        v11 = -2147024883;
        goto LABEL_42;
      }
      if ( v19 != 58 )
        goto LABEL_41;
      v11 = JsonHelpersInternal::JsonReader::ReadJsonValueAlloc(this, &v55);
      if ( v11 >= 0 )
      {
        ProcessHeap = GetProcessHeap();
        v36 = HeapAlloc(ProcessHeap, 0, 0x10u);
        if ( v36 )
        {
          v37 = -1;
          do
            ++v37;
          while ( v16[v37] );
          v38 = v37 + 1;
          v39 = 2 * (v37 + 1);
          v40 = GetProcessHeap();
          v41 = (wchar_t *)HeapAlloc(v40, 0, v39);
          v42 = v41;
          if ( v41 )
          {
            wcscpy_s(v41, v38, v16);
            v44 = v55;
            v4 = v36;
            *v36 = v42;
            v11 = 0;
            v36[1] = v44;
            v56 = v36;
            v55 = 0;
            v51 = (struct JsonKeyValuePair *)v36;
            v53 = 0;
          }
          else
          {
            v43 = GetProcessHeap();
            HeapFree(v43, 0, v36);
            v4 = v56;
            v11 = -2147024882;
          }
        }
        else
        {
          v11 = -2147024882;
        }
      }
    }
LABEL_42:
    CleanupJsonKeyValuePair(&v53);
    CleanupJsonValue(&v55);
    if ( v16 )
    {
      v20 = GetProcessHeap();
      HeapFree(v20, 0, v16);
    }
    if ( v11 < 0 )
      goto LABEL_81;
    v21 = *((_QWORD *)v6 + 2);
    if ( v21 < *((_QWORD *)v6 + 3) )
      goto LABEL_65;
    v22 = v21 + 1;
    if ( v21 + 1 > *((_QWORD *)v6 + 3) )
    {
      v23 = *((_QWORD *)v6 + 4) - 1LL;
      if ( v23 + v22 >= v22 )
      {
        v24 = *((_QWORD *)v6 + 3);
        v25 = *((_QWORD *)v6 + 1);
        v55 = 0;
        if ( is_mul_ok(v24, v25) )
        {
          v26 = *((_QWORD *)v6 + 1);
          v27 = (v23 + v22) & ~v23;
          v55 = 0;
          v29 = v26;
          v28 = v27 * (unsigned __int128)v26;
          v30 = v28;
          if ( is_mul_ok(v27, v29) )
          {
            v31 = (void *)*((_QWORD *)v6 + 5);
            v32 = *(void **)v6;
            if ( v31 )
            {
              v34 = HeapReAlloc(v32, DWORD2(v28), v31, v28);
            }
            else
            {
              v33 = HeapAlloc(v32, DWORD2(v28), v28);
              v34 = v33;
              if ( v33 )
                memset_0(v33, 0, v30);
            }
            if ( v34 )
            {
              v4 = v56;
              *((_QWORD *)v6 + 5) = v34;
              *((_QWORD *)v6 + 3) = v27;
LABEL_65:
              v55 = 0;
              if ( is_mul_ok(*((_QWORD *)v6 + 1), v21) )
              {
                v45 = (_QWORD *)(*((_QWORD *)v6 + 5) + *((_QWORD *)v6 + 1) * v21);
                if ( (unsigned __int64)v45 >= *((_QWORD *)v6 + 5) )
                {
                  *v45 = v4;
                  ++*((_QWORD *)v6 + 2);
                }
              }
            }
          }
        }
      }
    }
    v46 = *((_QWORD *)this + 1);
    v4 = 0;
    v56 = 0;
    v51 = 0;
    while ( 1 )
    {
      v47 = *(_QWORD *)this;
      v48 = *(_WORD *)(v46 + 2LL * *(_QWORD *)this);
      if ( v48 != 9
        && *(_WORD *)(v46 + 2LL * *(_QWORD *)this) != 10
        && *(_WORD *)(v46 + 2LL * *(_QWORD *)this) != 13
        && *(_WORD *)(v46 + 2LL * *(_QWORD *)this) != 32 )
      {
        break;
      }
      *(_QWORD *)this = v47 + 1;
      if ( !v48 )
        *(_QWORD *)this = v47;
    }
    v10 = v47 + 1;
    *(_QWORD *)this = v47 + 1;
    if ( !v48 )
    {
      *(_QWORD *)this = v47;
      goto LABEL_12;
    }
  }
  while ( v48 == 44 );
  if ( v48 != 125 )
    goto LABEL_12;
  *a2 = v6;
LABEL_22:
  v50 = 0;
  v11 = 0;
LABEL_81:
  CleanupJsonObject(&v50);
  CleanupJsonKeyValuePair(&v51);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180005a6c  mov     [rsp-38h+arg_0], rbx
0x180005a71  mov     [rsp-38h+arg_8], rdx
0x180005a76  push    rbp
0x180005a77  push    rsi
0x180005a78  push    rdi
0x180005a79  push    r12
0x180005a7b  push    r13
0x180005a7d  push    r14
0x180005a7f  push    r15
0x180005a81  mov     rbp, rsp
0x180005a84  sub     rsp, 40h
0x180005a88  xor     r12d, r12d
0x180005a8b  mov     rsi, rcx
0x180005a8e  mov     rbx, rdx
0x180005a91  mov     [rbp+var_20], r12
0x180005a95  mov     r15d, r12d
0x180005a98  mov     [rbp+arg_18], r12
0x180005a9c  mov     [rbp+var_18], r12
0x180005aa0  lea     ecx, [r12+30h]; Size
0x180005aa5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005aaa  mov     rdi, rax
0x180005aad  test    rax, rax
0x180005ab0  jz      loc_180005EBB
0x180005ab6  xorps   xmm0, xmm0
0x180005ab9  movups  xmmword ptr [rax], xmm0
0x180005abc  movups  xmmword ptr [rax+10h], xmm0
0x180005ac0  movups  xmmword ptr [rax+20h], xmm0
0x180005ac4  call    cs:__imp_GetProcessHeap
0x180005aca  xorps   xmm0, xmm0
0x180005acd  lea     r13d, [r12+10h]
0x180005ad2  movups  xmmword ptr [rdi], xmm0
0x180005ad5  lea     r14d, [r12+8]
0x180005ada  movups  xmmword ptr [rdi+10h], xmm0
0x180005ade  movups  xmmword ptr [rdi+20h], xmm0
0x180005ae2  call    cs:__imp_GetProcessHeap
0x180005ae8  mov     [rdi], rax
0x180005aeb  mov     [rdi+20h], r13
0x180005aef  mov     [rdi+10h], r12
0x180005af3  mov     [rdi+18h], r12
0x180005af7  mov     [rdi+28h], r12
0x180005afb  mov     [rdi+8], r14
0x180005aff  mov     r9, [rsi+8]
0x180005b03  mov     [rbp+var_20], rdi
0x180005b07  mov     rdx, [rsi]
0x180005b0a  movzx   r8d, word ptr [r9+rdx*2]
0x180005b0f  mov     ecx, r8d
0x180005b12  sub     ecx, 9
0x180005b15  jz      short loc_180005B26
0x180005b17  sub     ecx, 1
0x180005b1a  jz      short loc_180005B26
0x180005b1c  sub     ecx, 3
0x180005b1f  jz      short loc_180005B26
0x180005b21  cmp     ecx, 13h
0x180005b24  jnz     short loc_180005B38
0x180005b26  lea     rax, [rdx+1]
0x180005b2a  mov     [rsi], rax
0x180005b2d  cmp     r12w, r8w
0x180005b31  jnz     short loc_180005B07
0x180005b33  mov     [rsi], rdx
0x180005b36  jmp     short loc_180005B07
0x180005b38  lea     rcx, [rdx+1]
0x180005b3c  mov     [rsi], rcx
0x180005b3f  cmp     r12w, r8w
0x180005b43  jnz     short loc_180005B4A
0x180005b45  mov     [rsi], rdx
0x180005b48  jmp     short loc_180005B55
0x180005b4a  mov     eax, 7Bh ; '{'
0x180005b4f  cmp     ax, r8w
0x180005b53  jz      short loc_180005B5F
0x180005b55  mov     ebx, 8007000Dh
0x180005b5a  jmp     loc_180005EC0
0x180005b5f  movzx   r8d, word ptr [r9+rcx*2]
0x180005b64  mov     edx, r8d
0x180005b67  sub     edx, 9
0x180005b6a  jz      short loc_180005B7B
0x180005b6c  sub     edx, 1
0x180005b6f  jz      short loc_180005B7B
0x180005b71  sub     edx, 3
0x180005b74  jz      short loc_180005B7B
0x180005b76  cmp     edx, 13h
0x180005b79  jnz     short loc_180005B92
0x180005b7b  lea     rdx, [rcx+1]
0x180005b7f  mov     [rsi], rdx
0x180005b82  cmp     r12w, r8w
0x180005b86  jnz     short loc_180005B8D
0x180005b88  mov     [rsi], rcx
0x180005b8b  jmp     short loc_180005B5F
0x180005b8d  mov     rcx, rdx
0x180005b90  jmp     short loc_180005B5F
0x180005b92  mov     eax, 7Dh ; '}'
0x180005b97  cmp     ax, r8w
0x180005b9b  jnz     short loc_180005BB3
0x180005b9d  lea     rax, [rcx+1]
0x180005ba1  mov     [rbx], rdi
0x180005ba4  mov     [rsi], rax
0x180005ba7  mov     [rbp+var_20], r12
0x180005bab  mov     ebx, r12d
0x180005bae  jmp     loc_180005EC0
0x180005bb3  mov     r9, [rsi+8]
0x180005bb7  mov     [rbp+var_8], r12
0x180005bbb  mov     [rbp+arg_10], r12
0x180005bbf  mov     [rbp+lpMem], r12
0x180005bc3  movzx   r8d, word ptr [r9+rcx*2]
0x180005bc8  mov     edx, r8d
0x180005bcb  sub     edx, 9
0x180005bce  jz      short loc_180005BDF
0x180005bd0  sub     edx, 1
0x180005bd3  jz      short loc_180005BDF
0x180005bd5  sub     edx, 3
0x180005bd8  jz      short loc_180005BDF
0x180005bda  cmp     edx, 13h
0x180005bdd  jnz     short loc_180005BF6
0x180005bdf  lea     rdx, [rcx+1]
0x180005be3  mov     [rsi], rdx
0x180005be6  cmp     r12w, r8w
0x180005bea  jnz     short loc_180005BF1
0x180005bec  mov     [rsi], rcx
0x180005bef  jmp     short loc_180005BC3
0x180005bf1  mov     rcx, rdx
0x180005bf4  jmp     short loc_180005BC3
0x180005bf6  lea     rdx, [rbp+lpMem]; unsigned __int16 **
0x180005bfa  mov     rcx, rsi; this
0x180005bfd  call    ?ReadStringFromStreamAlloc@JsonReader@JsonHelpersInternal@@AEAAJPEAPEBG@Z; JsonHelpersInternal::JsonReader::ReadStringFromStreamAlloc(ushort const * *)
0x180005c02  mov     r12, [rbp+lpMem]
0x180005c06  xor     r13d, r13d
0x180005c09  mov     ebx, eax
0x180005c0b  test    eax, eax
0x180005c0d  js      short loc_180005C5D
0x180005c0f  mov     r9, [rsi+8]
0x180005c13  mov     rdx, [rsi]
0x180005c16  movzx   r8d, word ptr [r9+rdx*2]
0x180005c1b  mov     ecx, r8d
0x180005c1e  sub     ecx, 9
0x180005c21  jz      short loc_180005C32
0x180005c23  sub     ecx, 1
0x180005c26  jz      short loc_180005C32
0x180005c28  sub     ecx, 3
0x180005c2b  jz      short loc_180005C32
0x180005c2d  cmp     ecx, 13h
0x180005c30  jnz     short loc_180005C44
0x180005c32  lea     rax, [rdx+1]
0x180005c36  mov     [rsi], rax
0x180005c39  cmp     r13w, r8w
0x180005c3d  jnz     short loc_180005C13
0x180005c3f  mov     [rsi], rdx
0x180005c42  jmp     short loc_180005C13
0x180005c44  lea     rax, [rdx+1]
0x180005c48  mov     [rsi], rax
0x180005c4b  cmp     r13w, r8w
0x180005c4f  jnz     loc_180005D2C
0x180005c55  mov     [rsi], rdx
0x180005c58  mov     ebx, 8007000Dh
0x180005c5d  lea     rcx, [rbp+var_8]; struct JsonKeyValuePair **
0x180005c61  call    ?CleanupJsonKeyValuePair@@YAXPEAPEAUJsonKeyValuePair@@@Z; CleanupJsonKeyValuePair(JsonKeyValuePair * *)
0x180005c66  lea     rcx, [rbp+arg_10]; struct JsonValue **
0x180005c6a  call    ?CleanupJsonValue@@YAXPEAPEAUJsonValue@@@Z; CleanupJsonValue(JsonValue * *)
0x180005c6f  test    r12, r12
0x180005c72  jz      short loc_180005C88
0x180005c74  call    cs:__imp_GetProcessHeap
0x180005c7a  mov     r8, r12; lpMem
0x180005c7d  xor     edx, edx; dwFlags
0x180005c7f  mov     rcx, rax; hHeap
0x180005c82  call    cs:__imp_HeapFree
0x180005c88  xor     r12d, r12d
0x180005c8b  test    ebx, ebx
0x180005c8d  js      loc_180005EC0
0x180005c93  mov     r13, [rdi+10h]
0x180005c97  cmp     r13, [rdi+18h]
0x180005c9b  jb      loc_180005E1E
0x180005ca1  lea     rcx, [r13+1]
0x180005ca5  cmp     rcx, [rdi+18h]
0x180005ca9  jbe     loc_180005E3F
0x180005caf  mov     r14, [rdi+20h]
0x180005cb3  dec     r14
0x180005cb6  lea     r8, [r14+rcx]
0x180005cba  cmp     r8, rcx
0x180005cbd  jb      loc_180005E3F
0x180005cc3  mov     rax, [rdi+8]
0x180005cc7  mul     qword ptr [rdi+18h]
0x180005ccb  mov     [rbp+arg_10], r12
0x180005ccf  test    rdx, rdx
0x180005cd2  jnz     loc_180005E3F
0x180005cd8  mov     rax, [rdi+8]
0x180005cdc  not     r14
0x180005cdf  and     r14, r8
0x180005ce2  mov     [rbp+arg_10], r12
0x180005ce6  mul     r14
0x180005ce9  mov     r15, rax
0x180005cec  test    rdx, rdx
0x180005cef  jnz     loc_180005E3F
0x180005cf5  mov     r8, [rdi+28h]; lpMem
0x180005cf9  mov     rcx, [rdi]; hHeap
0x180005cfc  test    r8, r8
0x180005cff  jnz     loc_180005E01
0x180005d05  mov     r8, rax; dwBytes
0x180005d08  call    cs:__imp_HeapAlloc
0x180005d0e  mov     rbx, rax
0x180005d11  test    rax, rax
0x180005d14  jz      loc_180005E0D
0x180005d1a  mov     r8, r15; Size
0x180005d1d  xor     edx, edx; Val
0x180005d1f  mov     rcx, rax; void *
0x180005d22  call    memset_0
0x180005d27  jmp     loc_180005E0D
0x180005d2c  mov     eax, 3Ah ; ':'
0x180005d31  cmp     ax, r8w
0x180005d35  jnz     loc_180005C58
0x180005d3b  lea     rdx, [rbp+arg_10]; struct JsonValue **
0x180005d3f  mov     rcx, rsi; this
0x180005d42  call    ?ReadJsonValueAlloc@JsonReader@JsonHelpersInternal@@QEAAJPEAPEAUJsonValue@@@Z; JsonHelpersInternal::JsonReader::ReadJsonValueAlloc(JsonValue * *)
0x180005d47  mov     ebx, eax
0x180005d49  test    eax, eax
0x180005d4b  js      loc_180005C5D
0x180005d51  call    cs:__imp_GetProcessHeap
0x180005d57  xor     edx, edx; dwFlags
0x180005d59  mov     rcx, rax; hHeap
0x180005d5c  lea     r8d, [rdx+10h]; dwBytes
0x180005d60  call    cs:__imp_HeapAlloc
0x180005d66  mov     r14, rax
0x180005d69  test    rax, rax
0x180005d6c  jnz     short loc_180005D78
0x180005d6e  mov     ebx, 8007000Eh
0x180005d73  jmp     loc_180005C5D
0x180005d78  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005d7c  inc     rax
0x180005d7f  cmp     [r12+rax*2], r13w
0x180005d84  jnz     short loc_180005D7C
0x180005d86  lea     r15, [rax+1]
0x180005d8a  lea     rbx, [r15+r15]
0x180005d8e  call    cs:__imp_GetProcessHeap
0x180005d94  mov     r8, rbx; dwBytes
0x180005d97  xor     edx, edx; dwFlags
0x180005d99  mov     rcx, rax; hHeap
0x180005d9c  call    cs:__imp_HeapAlloc
0x180005da2  mov     rbx, rax
0x180005da5  test    rax, rax
0x180005da8  jnz     short loc_180005DCC
0x180005daa  call    cs:__imp_GetProcessHeap
0x180005db0  mov     r8, r14; lpMem
0x180005db3  xor     edx, edx; dwFlags
0x180005db5  mov     rcx, rax; hHeap
0x180005db8  call    cs:__imp_HeapFree
0x180005dbe  mov     r15, [rbp+arg_18]
0x180005dc2  mov     ebx, 8007000Eh
0x180005dc7  jmp     loc_180005C5D
0x180005dcc  mov     r8, r12; Source
0x180005dcf  mov     rdx, r15; SizeInWords
0x180005dd2  mov     rcx, rbx; Destination
0x180005dd5  call    cs:__imp_wcscpy_s
0x180005ddb  mov     rax, [rbp+arg_10]
0x180005ddf  mov     r15, r14
0x180005de2  mov     [r14], rbx
0x180005de5  mov     ebx, r13d
0x180005de8  mov     [r14+8], rax
0x180005dec  mov     [rbp+arg_18], r14
0x180005df0  mov     [rbp+arg_10], r13
0x180005df4  mov     [rbp+var_18], r14
0x180005df8  mov     [rbp+var_8], r13
0x180005dfc  jmp     loc_180005C5D
0x180005e01  mov     r9, r15; dwBytes
0x180005e04  call    cs:__imp_HeapReAlloc
0x180005e0a  mov     rbx, rax
0x180005e0d  test    rbx, rbx
0x180005e10  jz      short loc_180005E3F
0x180005e12  mov     r15, [rbp+arg_18]
0x180005e16  mov     [rdi+28h], rbx
0x180005e1a  mov     [rdi+18h], r14
0x180005e1e  mov     rax, r13
0x180005e21  mov     [rbp+arg_10], r12
0x180005e25  mul     qword ptr [rdi+8]
0x180005e29  test    rdx, rdx
0x180005e2c  jnz     short loc_180005E3F
0x180005e2e  add     rax, [rdi+28h]
0x180005e32  cmp     rax, [rdi+28h]
0x180005e36  jb      short loc_180005E3F
0x180005e38  mov     [rax], r15
0x180005e3b  inc     qword ptr [rdi+10h]
0x180005e3f  mov     r9, [rsi+8]
0x180005e43  mov     r15, r12
0x180005e46  mov     [rbp+arg_18], r12
0x180005e4a  mov     [rbp+var_18], r12
0x180005e4e  mov     r8, [rsi]
0x180005e51  movzx   edx, word ptr [r9+r8*2]
0x180005e56  mov     ecx, edx
0x180005e58  sub     ecx, 9
0x180005e5b  jz      short loc_180005E6C
0x180005e5d  sub     ecx, 1
0x180005e60  jz      short loc_180005E6C
0x180005e62  sub     ecx, 3
0x180005e65  jz      short loc_180005E6C
0x180005e67  cmp     ecx, 13h
0x180005e6a  jnz     short loc_180005E7E
0x180005e6c  lea     rax, [r8+1]
0x180005e70  mov     [rsi], rax
0x180005e73  cmp     r12w, dx
0x180005e77  jnz     short loc_180005E4E
0x180005e79  mov     [rsi], r8
0x180005e7c  jmp     short loc_180005E4E
0x180005e7e  lea     rcx, [r8+1]
0x180005e82  mov     [rsi], rcx
  ... truncated ...
```
