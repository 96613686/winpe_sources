# JsonHelpersInternal::JsonReader::ReadJsonValueAlloc(JsonValue * *)

- ea: `0x180005ef4`
- end: `0x18000639a`
- name: `?ReadJsonValueAlloc@JsonReader@JsonHelpersInternal@@QEAAJPEAPEAUJsonValue@@@Z`
- size: `1190`
- prototype: `__int64 __fastcall(JsonHelpersInternal::JsonReader *__hidden this, struct JsonValue **)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180005a6c`
- `0x1800063a0`

## callees

- `0x180002eb0`
- `0x180002f54`
- `0x180002ff0`
- `0x180005794`
- `0x180005a6c`
- `0x180005ef4`
- `0x1800063a0`
- `0x180006934`
- `0x180007ae0`
- `0x1800191f0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800061bf`
- `msvcrt!_wcsicmp` at `0x180006204`
- `msvcrt!_wcsicmp` at `0x180006269`
- `msvcrt!_wcsicmp` at `0x1800061bf`
- `msvcrt!_wcsicmp` at `0x180006204`
- `msvcrt!_wcsicmp` at `0x180006269`
- `KERNEL32!HeapAlloc` at `0x180005ff6`
- `KERNEL32!HeapAlloc` at `0x180006030`
- `KERNEL32!HeapAlloc` at `0x180006116`
- `KERNEL32!HeapAlloc` at `0x1800061d8`
- `KERNEL32!HeapAlloc` at `0x18000621d`
- `KERNEL32!HeapAlloc` at `0x180006286`
- `KERNEL32!HeapAlloc` at `0x1800062cc`
- `KERNEL32!HeapAlloc` at `0x180006313`
- `KERNEL32!HeapAlloc` at `0x180005ff6`
- `KERNEL32!HeapAlloc` at `0x180006030`
- `KERNEL32!HeapAlloc` at `0x180006116`
- `KERNEL32!HeapAlloc` at `0x1800061d8`
- `KERNEL32!HeapAlloc` at `0x18000621d`
- `KERNEL32!HeapAlloc` at `0x180006286`
- `KERNEL32!HeapAlloc` at `0x1800062cc`
- `KERNEL32!HeapAlloc` at `0x180006313`
- `KERNEL32!GetProcessHeap` at `0x180005fe7`
- `KERNEL32!GetProcessHeap` at `0x180006022`
- `KERNEL32!GetProcessHeap` at `0x180006046`
- `KERNEL32!GetProcessHeap` at `0x18000605f`
- `KERNEL32!GetProcessHeap` at `0x180006107`
- `KERNEL32!GetProcessHeap` at `0x1800061c9`
- `KERNEL32!GetProcessHeap` at `0x18000620e`
- `KERNEL32!GetProcessHeap` at `0x180006277`
- `KERNEL32!GetProcessHeap` at `0x1800062bd`
- `KERNEL32!GetProcessHeap` at `0x180006304`
- `KERNEL32!GetProcessHeap` at `0x180006360`
- `KERNEL32!GetProcessHeap` at `0x180005fe7`
- `KERNEL32!GetProcessHeap` at `0x180006022`
- `KERNEL32!GetProcessHeap` at `0x180006046`
- `KERNEL32!GetProcessHeap` at `0x18000605f`
- `KERNEL32!GetProcessHeap` at `0x180006107`
- `KERNEL32!GetProcessHeap` at `0x1800061c9`
- `KERNEL32!GetProcessHeap` at `0x18000620e`
- `KERNEL32!GetProcessHeap` at `0x180006277`
- `KERNEL32!GetProcessHeap` at `0x1800062bd`
- `KERNEL32!GetProcessHeap` at `0x180006304`
- `KERNEL32!GetProcessHeap` at `0x180006360`
- `KERNEL32!HeapFree` at `0x180006054`
- `KERNEL32!HeapFree` at `0x18000606d`
- `KERNEL32!HeapFree` at `0x18000636e`
- `KERNEL32!HeapFree` at `0x180006054`
- `KERNEL32!HeapFree` at `0x18000606d`
- `KERNEL32!HeapFree` at `0x18000636e`

## pseudocode

```c
__int64 __fastcall JsonHelpersInternal::JsonReader::ReadJsonValueAlloc(
        JsonHelpersInternal::JsonReader *this,
        struct JsonValue **a2)
{
  __int64 v2; // r9
  unsigned __int16 *v3; // r12
  __int64 v6; // r8
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  int StringFromStreamAlloc; // ebx
  HANDLE v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rsi
  __int64 v18; // rax
  unsigned __int64 v19; // r15
  SIZE_T v20; // rbx
  HANDLE v21; // rax
  unsigned __int16 *v22; // rax
  unsigned __int16 *v23; // r14
  HANDLE v24; // rax
  HANDLE v25; // rax
  struct JsonValue *v26; // rdi
  __int64 v27; // rbx
  HANDLE v28; // rax
  struct JsonValue *v29; // rax
  __int64 v30; // r8
  wchar_t v31; // dx
  wchar_t v32; // dx
  wchar_t v33; // cx
  HANDLE v34; // rax
  struct JsonValue *v35; // rax
  HANDLE v36; // rax
  struct JsonValue *v37; // rax
  __int64 v38; // rcx
  __int16 v39; // dx
  HANDLE v40; // rax
  struct JsonValue *v41; // rax
  HANDLE v42; // rax
  struct JsonValue *v43; // rax
  HANDLE ProcessHeap; // rax
  struct JsonValue *v45; // rax
  HANDLE v46; // rax
  __int64 v48; // [rsp+20h] [rbp-40h] BYREF
  __int64 v49; // [rsp+28h] [rbp-38h] BYREF
  unsigned __int16 *v50; // [rsp+30h] [rbp-30h] BYREF
  double v51; // [rsp+38h] [rbp-28h] BYREF
  struct JsonValue *v52; // [rsp+40h] [rbp-20h] BYREF
  wchar_t String1[4]; // [rsp+48h] [rbp-18h] BYREF
  __int16 v54; // [rsp+50h] [rbp-10h]
  __int16 v55; // [rsp+52h] [rbp-Eh]

  v2 = *((_QWORD *)this + 1);
  v52 = 0;
  v51 = 0.0;
  v48 = 0;
  v3 = 0;
  v49 = 0;
  v50 = 0;
  while ( 1 )
  {
    v6 = *(_QWORD *)this;
    v7 = *(unsigned __int16 *)(v2 + 2LL * *(_QWORD *)this);
    if ( v7 != 9
      && *(_WORD *)(v2 + 2LL * *(_QWORD *)this) != 10
      && *(_WORD *)(v2 + 2LL * *(_QWORD *)this) != 13
      && *(_WORD *)(v2 + 2LL * *(_QWORD *)this) != 32 )
    {
      break;
    }
    *(_QWORD *)this = v6 + 1;
    if ( !(_WORD)v7 )
      *(_QWORD *)this = v6;
  }
  if ( v7 <= 0x36 )
  {
    if ( v7 == 54 )
      goto LABEL_64;
    v8 = v7 - 34;
    if ( v8 )
    {
      v9 = v8 - 11;
      if ( v9 )
      {
        v10 = v9 - 3;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            v12 = v11 - 1;
            if ( v12 )
            {
              v13 = v12 - 1;
              if ( v13 )
              {
                if ( v13 - 1 >= 2 )
                  goto LABEL_17;
              }
            }
          }
        }
      }
LABEL_64:
      StringFromStreamAlloc = JsonHelpersInternal::JsonReader::ReadJsonNumber(this, &v51);
      if ( StringFromStreamAlloc < 0 )
        goto LABEL_68;
      ProcessHeap = GetProcessHeap();
      v45 = (struct JsonValue *)HeapAlloc(ProcessHeap, 0, 0x10u);
      v26 = v45;
      if ( v45 )
      {
        *((double *)v45 + 1) = v51;
        *(_DWORD *)v45 = 1;
        goto LABEL_67;
      }
LABEL_40:
      StringFromStreamAlloc = -2147024882;
      goto LABEL_68;
    }
    StringFromStreamAlloc = JsonHelpersInternal::JsonReader::ReadStringFromStreamAlloc(
                              this,
                              (const unsigned __int16 **)&v50);
    if ( StringFromStreamAlloc < 0 )
    {
      v3 = v50;
      goto LABEL_68;
    }
    v15 = GetProcessHeap();
    v16 = HeapAlloc(v15, 0, 0x10u);
    v3 = v50;
    v17 = v16;
    if ( !v16 )
      goto LABEL_40;
    v18 = -1;
    do
      ++v18;
    while ( v50[v18] );
    v19 = v18 + 1;
    v20 = 2 * (v18 + 1);
    v21 = GetProcessHeap();
    v22 = (unsigned __int16 *)HeapAlloc(v21, 0, v20);
    v23 = v22;
    if ( !v22 )
    {
      StringFromStreamAlloc = -2147024882;
      goto LABEL_24;
    }
    StringFromStreamAlloc = StringCchCopyW(v22, v19, v3);
    if ( StringFromStreamAlloc < 0 )
    {
LABEL_24:
      v24 = GetProcessHeap();
      HeapFree(v24, 0, v17);
      if ( v23 )
      {
        v25 = GetProcessHeap();
        HeapFree(v25, 0, v23);
      }
      goto LABEL_68;
    }
    *(_DWORD *)v17 = 0;
    v26 = (struct JsonValue *)v17;
    v17[1] = v23;
LABEL_67:
    *a2 = v26;
    StringFromStreamAlloc = 0;
    v52 = 0;
    goto LABEL_68;
  }
  switch ( v7 )
  {
    case '7':
    case '8':
    case '9':
      goto LABEL_64;
    case '[':
      StringFromStreamAlloc = JsonHelpersInternal::JsonReader::ReadJsonValueListAlloc(this);
      if ( StringFromStreamAlloc < 0 )
        goto LABEL_68;
      v42 = GetProcessHeap();
      v43 = (struct JsonValue *)HeapAlloc(v42, 0, 0x10u);
      v26 = v43;
      if ( !v43 )
        goto LABEL_40;
      *(_DWORD *)v43 = 4;
      *((_QWORD *)v43 + 1) = v49;
      v49 = 0;
      goto LABEL_67;
    case 'f':
    case 'n':
    case 't':
      *(_QWORD *)this = v6 + 1;
      v30 = v6 + 1;
      String1[0] = v7;
      v31 = *(_WORD *)(v2 + 2 * v30);
      *(_QWORD *)this = v30 + 1;
      if ( v31 )
        ++v30;
      else
        *(_QWORD *)this = v30;
      String1[1] = v31;
      v32 = *(_WORD *)(v2 + 2 * v30);
      *(_QWORD *)this = v30 + 1;
      if ( v32 )
        ++v30;
      else
        *(_QWORD *)this = v30;
      String1[2] = v32;
      v33 = *(_WORD *)(v2 + 2 * v30);
      *(_QWORD *)this = v30 + 1;
      if ( !v33 )
        *(_QWORD *)this = v30;
      String1[3] = v33;
      v54 = 0;
      if ( _wcsicmp(String1, L"true") )
      {
        if ( _wcsicmp(String1, L"null") )
        {
          v38 = *(_QWORD *)this;
          v39 = *(_WORD *)(*((_QWORD *)this + 1) + 2LL * (*(_QWORD *)this)++);
          if ( !v39 )
            *(_QWORD *)this = v38;
          v54 = v39;
          v55 = 0;
          if ( _wcsicmp(String1, L"false") )
            goto LABEL_17;
          v40 = GetProcessHeap();
          v41 = (struct JsonValue *)HeapAlloc(v40, 0, 0x10u);
          v26 = v41;
          if ( !v41 )
            goto LABEL_40;
          *(_DWORD *)v41 = 2;
          *((_BYTE *)v41 + 8) = 0;
        }
        else
        {
          v36 = GetProcessHeap();
          v37 = (struct JsonValue *)HeapAlloc(v36, 0, 0x10u);
          v26 = v37;
          if ( !v37 )
            goto LABEL_40;
          *(_DWORD *)v37 = 3;
        }
      }
      else
      {
        v34 = GetProcessHeap();
        v35 = (struct JsonValue *)HeapAlloc(v34, 0, 0x10u);
        v26 = v35;
        if ( !v35 )
          goto LABEL_40;
        *(_DWORD *)v35 = 2;
        *((_BYTE *)v35 + 8) = 1;
      }
      goto LABEL_67;
  }
  if ( v7 != 123 )
  {
LABEL_17:
    StringFromStreamAlloc = -2147024883;
    goto LABEL_68;
  }
  StringFromStreamAlloc = JsonHelpersInternal::JsonReader::ReadJsonObjectAlloc(this);
  if ( StringFromStreamAlloc >= 0 )
  {
    v27 = v48;
    v28 = GetProcessHeap();
    v29 = (struct JsonValue *)HeapAlloc(v28, 0, 0x10u);
    v26 = v29;
    if ( !v29 )
      goto LABEL_40;
    *(_DWORD *)v29 = 5;
    *((_QWORD *)v29 + 1) = v27;
    v48 = 0;
    goto LABEL_67;
  }
LABEL_68:
  CleanupJsonValue(&v52);
  CleanupJsonObject(&v48);
  CleanupJsonValueList(&v49);
  if ( v3 )
  {
    v46 = GetProcessHeap();
    HeapFree(v46, 0, v3);
  }
  return (unsigned int)StringFromStreamAlloc;
}

```

## disassembly

```asm
0x180005ef4  mov     [rsp-38h+arg_10], rbx
0x180005ef9  push    rbp
0x180005efa  push    rsi
0x180005efb  push    rdi
0x180005efc  push    r12
0x180005efe  push    r13
0x180005f00  push    r14
0x180005f02  push    r15
0x180005f04  mov     rbp, rsp
0x180005f07  sub     rsp, 60h
0x180005f0b  mov     rax, cs:__security_cookie
0x180005f12  xor     rax, rsp
0x180005f15  mov     [rbp+var_8], rax
0x180005f19  mov     r9, [rcx+8]
0x180005f1d  xor     r15d, r15d
0x180005f20  xorps   xmm0, xmm0
0x180005f23  mov     [rbp+var_20], r15
0x180005f27  movsd   [rbp+var_28], xmm0
0x180005f2c  mov     edi, r15d
0x180005f2f  mov     [rbp+var_40], r15
0x180005f33  mov     r12d, r15d
0x180005f36  mov     [rbp+var_38], r15
0x180005f3a  mov     r13, rdx
0x180005f3d  mov     [rbp+var_30], r15
0x180005f41  mov     rbx, rcx
0x180005f44  mov     r8, [rbx]
0x180005f47  movzx   ecx, word ptr [r9+r8*2]
0x180005f4c  mov     edx, ecx
0x180005f4e  sub     edx, 9
0x180005f51  jz      short loc_180005F62
0x180005f53  sub     edx, 1
0x180005f56  jz      short loc_180005F62
0x180005f58  sub     edx, 3
0x180005f5b  jz      short loc_180005F62
0x180005f5d  cmp     edx, 13h
0x180005f60  jnz     short loc_180005F74
0x180005f62  lea     rax, [r8+1]
0x180005f66  mov     [rbx], rax
0x180005f69  cmp     r15w, cx
0x180005f6d  jnz     short loc_180005F44
0x180005f6f  mov     [rbx], r8
0x180005f72  jmp     short loc_180005F44
0x180005f74  cmp     ecx, 36h ; '6'
0x180005f77  ja      loc_1800060AF
0x180005f7d  jz      loc_1800062F2
0x180005f83  sub     ecx, 22h ; '"'
0x180005f86  jz      short loc_180005FD1
0x180005f88  sub     ecx, 0Bh
0x180005f8b  jz      loc_1800062F2
0x180005f91  sub     ecx, 3
0x180005f94  jz      loc_1800062F2
0x180005f9a  sub     ecx, 1
0x180005f9d  jz      loc_1800062F2
0x180005fa3  sub     ecx, 1
0x180005fa6  jz      loc_1800062F2
0x180005fac  sub     ecx, 1
0x180005faf  jz      loc_1800062F2
0x180005fb5  sub     ecx, 1
0x180005fb8  jz      loc_1800062F2
0x180005fbe  cmp     ecx, 1
0x180005fc1  jz      loc_1800062F2
0x180005fc7  mov     ebx, 8007000Dh
0x180005fcc  jmp     loc_180006340
0x180005fd1  lea     rdx, [rbp+var_30]; unsigned __int16 **
0x180005fd5  mov     rcx, rbx; this
0x180005fd8  call    ?ReadStringFromStreamAlloc@JsonReader@JsonHelpersInternal@@AEAAJPEAPEBG@Z; JsonHelpersInternal::JsonReader::ReadStringFromStreamAlloc(ushort const * *)
0x180005fdd  mov     ebx, eax
0x180005fdf  test    eax, eax
0x180005fe1  js      loc_1800060A6
0x180005fe7  call    cs:__imp_GetProcessHeap
0x180005fed  xor     edx, edx; dwFlags
0x180005fef  mov     rcx, rax; hHeap
0x180005ff2  lea     r8d, [rdx+10h]; dwBytes
0x180005ff6  call    cs:__imp_HeapAlloc
0x180005ffc  mov     r12, [rbp+var_30]
0x180006000  mov     rsi, rax
0x180006003  test    rax, rax
0x180006006  jz      loc_180006124
0x18000600c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006010  inc     rax
0x180006013  cmp     [r12+rax*2], r15w
0x180006018  jnz     short loc_180006010
0x18000601a  lea     r15, [rax+1]
0x18000601e  lea     rbx, [r15+r15]
0x180006022  call    cs:__imp_GetProcessHeap
0x180006028  mov     r8, rbx; dwBytes
0x18000602b  xor     edx, edx; dwFlags
0x18000602d  mov     rcx, rax; hHeap
0x180006030  call    cs:__imp_HeapAlloc
0x180006036  mov     r14, rax
0x180006039  test    rax, rax
0x18000603c  jnz     short loc_180006080
0x18000603e  mov     ebx, 8007000Eh
0x180006043  xor     r15d, r15d
0x180006046  call    cs:__imp_GetProcessHeap
0x18000604c  mov     r8, rsi; lpMem
0x18000604f  xor     edx, edx; dwFlags
0x180006051  mov     rcx, rax; hHeap
0x180006054  call    cs:__imp_HeapFree
0x18000605a  test    r14, r14
0x18000605d  jz      short loc_180006073
0x18000605f  call    cs:__imp_GetProcessHeap
0x180006065  mov     r8, r14; lpMem
0x180006068  xor     edx, edx; dwFlags
0x18000606a  mov     rcx, rax; hHeap
0x18000606d  call    cs:__imp_HeapFree
0x180006073  test    ebx, ebx
0x180006075  jns     loc_180006335
0x18000607b  jmp     loc_180006340
0x180006080  mov     r8, r12; unsigned __int16 *
0x180006083  mov     rdx, r15; unsigned __int64
0x180006086  mov     rcx, r14; unsigned __int16 *
0x180006089  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000608e  xor     r15d, r15d
0x180006091  mov     ebx, eax
0x180006093  test    eax, eax
0x180006095  js      short loc_180006046
0x180006097  mov     [rsi], r15d
0x18000609a  mov     rdi, rsi
0x18000609d  mov     [rsi+8], r14
0x1800060a1  jmp     loc_180006335
0x1800060a6  mov     r12, [rbp+var_30]
0x1800060aa  jmp     loc_180006340
0x1800060af  mov     edx, ecx
0x1800060b1  sub     edx, 37h ; '7'
0x1800060b4  jz      loc_1800062F2
0x1800060ba  sub     edx, 1
0x1800060bd  jz      loc_1800062F2
0x1800060c3  sub     edx, 1
0x1800060c6  jz      loc_1800062F2
0x1800060cc  sub     edx, 22h ; '"'
0x1800060cf  jz      loc_1800062A7
0x1800060d5  sub     edx, 0Bh
0x1800060d8  jz      short loc_180006141
0x1800060da  sub     edx, 8
0x1800060dd  jz      short loc_180006141
0x1800060df  sub     edx, 6
0x1800060e2  jz      short loc_180006141
0x1800060e4  cmp     edx, 7
0x1800060e7  jnz     loc_180005FC7
0x1800060ed  lea     rdx, [rbp+var_40]
0x1800060f1  mov     rcx, rbx; this
0x1800060f4  call    ?ReadJsonObjectAlloc@JsonReader@JsonHelpersInternal@@QEAAJPEAPEAV?$RtlArray@PEAUJsonKeyValuePair@@@@@Z; JsonHelpersInternal::JsonReader::ReadJsonObjectAlloc(RtlArray<JsonKeyValuePair *> * *)
0x1800060f9  mov     ebx, eax
0x1800060fb  test    eax, eax
0x1800060fd  js      loc_180006340
0x180006103  mov     rbx, [rbp+var_40]
0x180006107  call    cs:__imp_GetProcessHeap
0x18000610d  xor     edx, edx; dwFlags
0x18000610f  mov     rcx, rax; hHeap
0x180006112  lea     r8d, [rdx+10h]; dwBytes
0x180006116  call    cs:__imp_HeapAlloc
0x18000611c  mov     rdi, rax
0x18000611f  test    rax, rax
0x180006122  jnz     short loc_18000612E
0x180006124  mov     ebx, 8007000Eh
0x180006129  jmp     loc_180006340
0x18000612e  mov     dword ptr [rax], 5
0x180006134  mov     [rax+8], rbx
0x180006138  mov     [rbp+var_40], r15
0x18000613c  jmp     loc_180006335
0x180006141  lea     rdx, [r8+1]
0x180006145  mov     [rbx], rdx
0x180006148  cmp     r15w, cx
0x18000614c  jnz     short loc_180006153
0x18000614e  mov     [rbx], r8
0x180006151  jmp     short loc_180006156
0x180006153  mov     r8, rdx
0x180006156  mov     [rbp+String1], cx
0x18000615a  lea     rcx, [r8+1]
0x18000615e  movzx   edx, word ptr [r9+r8*2]
0x180006163  mov     [rbx], rcx
0x180006166  cmp     r15w, dx
0x18000616a  jnz     short loc_180006171
0x18000616c  mov     [rbx], r8
0x18000616f  jmp     short loc_180006174
0x180006171  mov     r8, rcx
0x180006174  mov     [rbp+var_16], dx
0x180006178  lea     rcx, [r8+1]
0x18000617c  movzx   edx, word ptr [r9+r8*2]
0x180006181  mov     [rbx], rcx
0x180006184  cmp     r15w, dx
0x180006188  jnz     short loc_18000618F
0x18000618a  mov     [rbx], r8
0x18000618d  jmp     short loc_180006192
0x18000618f  mov     r8, rcx
0x180006192  mov     [rbp+var_14], dx
0x180006196  lea     rax, [r8+1]
0x18000619a  movzx   ecx, word ptr [r9+r8*2]
0x18000619f  mov     [rbx], rax
0x1800061a2  cmp     r15w, cx
0x1800061a6  jnz     short loc_1800061AB
0x1800061a8  mov     [rbx], r8
0x1800061ab  mov     [rbp+var_12], cx
0x1800061af  lea     rdx, aTrue; "true"
0x1800061b6  lea     rcx, [rbp+String1]; String1
0x1800061ba  mov     [rbp+var_10], r15w
0x1800061bf  call    cs:__imp__wcsicmp
0x1800061c5  test    eax, eax
0x1800061c7  jnz     short loc_1800061F9
0x1800061c9  call    cs:__imp_GetProcessHeap
0x1800061cf  xor     edx, edx; dwFlags
0x1800061d1  mov     rcx, rax; hHeap
0x1800061d4  lea     r8d, [rdx+10h]; dwBytes
0x1800061d8  call    cs:__imp_HeapAlloc
0x1800061de  mov     rdi, rax
0x1800061e1  test    rax, rax
0x1800061e4  jz      loc_180006124
0x1800061ea  mov     dword ptr [rax], 2
0x1800061f0  mov     byte ptr [rax+8], 1
0x1800061f4  jmp     loc_180006335
0x1800061f9  lea     rdx, aNull; "null"
0x180006200  lea     rcx, [rbp+String1]; String1
0x180006204  call    cs:__imp__wcsicmp
0x18000620a  test    eax, eax
0x18000620c  jnz     short loc_18000623A
0x18000620e  call    cs:__imp_GetProcessHeap
0x180006214  xor     edx, edx; dwFlags
0x180006216  mov     rcx, rax; hHeap
0x180006219  lea     r8d, [rdx+10h]; dwBytes
0x18000621d  call    cs:__imp_HeapAlloc
0x180006223  mov     rdi, rax
0x180006226  test    rax, rax
0x180006229  jz      loc_180006124
0x18000622f  mov     dword ptr [rax], 3
0x180006235  jmp     loc_180006335
0x18000623a  mov     rcx, [rbx]
0x18000623d  mov     rax, [rbx+8]
0x180006241  movzx   edx, word ptr [rax+rcx*2]
0x180006245  lea     rax, [rcx+1]
0x180006249  mov     [rbx], rax
0x18000624c  cmp     r15w, dx
0x180006250  jnz     short loc_180006255
0x180006252  mov     [rbx], rcx
0x180006255  mov     [rbp+var_10], dx
0x180006259  lea     rcx, [rbp+String1]; String1
0x18000625d  lea     rdx, aFalse; "false"
0x180006264  mov     [rbp+var_E], r15w
0x180006269  call    cs:__imp__wcsicmp
0x18000626f  test    eax, eax
0x180006271  jnz     loc_180005FC7
0x180006277  call    cs:__imp_GetProcessHeap
0x18000627d  xor     edx, edx; dwFlags
0x18000627f  mov     rcx, rax; hHeap
0x180006282  lea     r8d, [rdx+10h]; dwBytes
0x180006286  call    cs:__imp_HeapAlloc
0x18000628c  mov     rdi, rax
0x18000628f  test    rax, rax
0x180006292  jz      loc_180006124
0x180006298  mov     dword ptr [rax], 2
0x18000629e  mov     [rax+8], r15b
0x1800062a2  jmp     loc_180006335
0x1800062a7  lea     rdx, [rbp+var_38]
0x1800062ab  mov     rcx, rbx; this
0x1800062ae  call    ?ReadJsonValueListAlloc@JsonReader@JsonHelpersInternal@@QEAAJPEAPEAV?$RtlArray@PEAUJsonValue@@@@@Z; JsonHelpersInternal::JsonReader::ReadJsonValueListAlloc(RtlArray<JsonValue *> * *)
0x1800062b3  mov     ebx, eax
0x1800062b5  test    eax, eax
0x1800062b7  js      loc_180006340
0x1800062bd  call    cs:__imp_GetProcessHeap
0x1800062c3  xor     edx, edx; dwFlags
0x1800062c5  mov     rcx, rax; hHeap
0x1800062c8  lea     r8d, [rdx+10h]; dwBytes
0x1800062cc  call    cs:__imp_HeapAlloc
0x1800062d2  mov     rdi, rax
0x1800062d5  test    rax, rax
0x1800062d8  jz      loc_180006124
0x1800062de  mov     dword ptr [rax], 4
0x1800062e4  mov     rax, [rbp+var_38]
0x1800062e8  mov     [rdi+8], rax
0x1800062ec  mov     [rbp+var_38], r15
0x1800062f0  jmp     short loc_180006335
0x1800062f2  lea     rdx, [rbp+var_28]; double *
0x1800062f6  mov     rcx, rbx; this
0x1800062f9  call    ?ReadJsonNumber@JsonReader@JsonHelpersInternal@@QEAAJPEAN@Z; JsonHelpersInternal::JsonReader::ReadJsonNumber(double *)
0x1800062fe  mov     ebx, eax
0x180006300  test    eax, eax
0x180006302  js      short loc_180006340
0x180006304  call    cs:__imp_GetProcessHeap
0x18000630a  xor     edx, edx; dwFlags
0x18000630c  mov     rcx, rax; hHeap
0x18000630f  lea     r8d, [rdx+10h]; dwBytes
0x180006313  call    cs:__imp_HeapAlloc
0x180006319  mov     rdi, rax
0x18000631c  test    rax, rax
0x18000631f  jz      loc_180006124
0x180006325  movsd   xmm0, [rbp+var_28]
0x18000632a  movsd   qword ptr [rax+8], xmm0
0x18000632f  mov     dword ptr [rax], 1
0x180006335  mov     [r13+0], rdi
0x180006339  mov     ebx, r15d
0x18000633c  mov     [rbp+var_20], r15
0x180006340  lea     rcx, [rbp+var_20]; struct JsonValue **
0x180006344  call    ?CleanupJsonValue@@YAXPEAPEAUJsonValue@@@Z; CleanupJsonValue(JsonValue * *)
0x180006349  lea     rcx, [rbp+var_40]
0x18000634d  call    ?CleanupJsonObject@@YAXPEAPEAV?$RtlArray@PEAUJsonKeyValuePair@@@@@Z; CleanupJsonObject(RtlArray<JsonKeyValuePair *> * *)
0x180006352  lea     rcx, [rbp+var_38]
0x180006356  call    ?CleanupJsonValueList@@YAXPEAPEAV?$RtlArray@PEAUJsonValue@@@@@Z; CleanupJsonValueList(RtlArray<JsonValue *> * *)
0x18000635b  test    r12, r12
0x18000635e  jz      short loc_180006374
0x180006360  call    cs:__imp_GetProcessHeap
  ... truncated ...
```
