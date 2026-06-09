# RtlpComputePath

- ea: `0x180099a70`
- end: `0x18009a238`
- name: `RtlpComputePath`
- size: `1992`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002b1b4`
- `0x180097dd0`
- `0x180097ee0`
- `0x180099940`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x18006ffa0`
- `0x180070490`
- `0x180099894`
- `0x180099a70`
- `0x18009a6b0`
- `0x18011edcc`
- `0x180120408`
- `0x180164280`

## pseudocode

```c
__int64 __fastcall RtlpComputePath(__int64 a1, unsigned int a2, __int64 a3, char a4)
{
  __int64 Heap_0; // r12
  __int64 v6; // rdi
  __int64 v7; // rsi
  char v8; // r15
  unsigned int v9; // ebx
  __int128 *v10; // r10
  __int64 v11; // rcx
  __int64 v12; // rax
  _WORD *v13; // r15
  unsigned int v14; // r14d
  unsigned int v15; // ebx
  int v16; // eax
  _WORD *v17; // rcx
  int v18; // r14d
  __int64 DirPath; // rax
  int v21; // eax
  int v22; // eax
  _WORD *v23; // rcx
  __int64 v24; // rdx
  unsigned __int8 v25; // [rsp+30h] [rbp-78h]
  int EnvironmentVariable; // [rsp+34h] [rbp-74h]
  __int128 *v27; // [rsp+48h] [rbp-60h]
  void *Src; // [rsp+60h] [rbp-48h]
  __int64 v29; // [rsp+B0h] [rbp+8h]
  char v30; // [rsp+C8h] [rbp+20h]

  v30 = a4;
  v29 = a1;
  Src = 0;
  Heap_0 = 0;
  v25 = 0;
  v6 = 128;
  v7 = 0;
  v8 = ((unsigned __int64)qword_1801E3500 >> 60) & 3;
  EnvironmentVariable = 0;
  v9 = 0;
  v27 = 0;
  while ( 1 )
  {
    v10 = &RtlpSystem32Dirs;
    if ( v9 >= a2 )
      break;
    v11 = *(int *)(a1 + 4LL * v9);
    if ( (_DWORD)v11 == 3 )
    {
      RtlEnterCriticalSection(&FastPebLock);
      EnvironmentVariable = RtlQueryEnvironmentVariable(0, L"PATH", 4);
      v18 = EnvironmentVariable;
      if ( EnvironmentVariable == -1073741789 )
      {
        Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, (unsigned int)(NtdllBaseTag + 1572864), 0);
        if ( !Heap_0 )
        {
          RtlLeaveCriticalSection(&FastPebLock);
          return v7;
        }
        v18 = RtlQueryEnvironmentVariable(0, L"PATH", 4);
        EnvironmentVariable = v18;
      }
      RtlLeaveCriticalSection(&FastPebLock);
      if ( v18 == -1073741568 )
      {
        a1 = v29;
        ++v9;
        a4 = v30;
        EnvironmentVariable = 0;
      }
      else
      {
        if ( v18 < 0 )
          goto LABEL_24;
        v6 += 2;
LABEL_20:
        a1 = v29;
        ++v9;
        a4 = v30;
      }
    }
    else
    {
      if ( (_DWORD)v11 == 7 )
      {
        v6 += (unsigned __int16)RtlpSystem32Dirs;
        if ( a4 )
        {
          v25 = LdrpIncludeAlternateForwarders(v11, (unsigned __int16)RtlpSystem32Dirs);
          v6 += v24 + 22;
          if ( v25 )
            v6 += v24 + 30;
        }
        if ( v8 == 1 )
          v27 = v10;
        goto LABEL_20;
      }
      switch ( (int)v11 )
      {
        case 0:
          if ( !(_WORD)LdrpDllDirectory )
            goto LABEL_20;
          a1 = v29;
          a4 = v30;
          v6 += (unsigned __int16)LdrpDllDirectory + 2LL;
          ++v9;
          break;
        case 1:
          DirPath = RtlpGetDirPath(0);
          a4 = v30;
          v6 += 2;
          a1 = v29;
          ++v9;
          Src = (void *)DirPath;
          continue;
        case 2:
          v6 += (unsigned __int16)RtlpSystemDirs;
          if ( v8 != 1 )
            goto LABEL_20;
          a1 = v29;
          ++v9;
          a4 = v30;
          v27 = &RtlpSystemDirs;
          break;
        default:
          __fastfail(0x25u);
      }
    }
  }
  if ( (unsigned __int64)(v6 - 128) > 0xFFFE )
  {
    v18 = -1073741562;
  }
  else
  {
    v12 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, v6);
    v7 = v12;
    if ( v12 )
    {
      v13 = (_WORD *)(v12 + 128);
      *(_WORD *)(v12 + 72) = a2;
      *(_QWORD *)(v12 + 88) = 0;
      *(_QWORD *)(v12 + 96) = 0;
      *(_QWORD *)(v12 + 104) = 0;
      *(_DWORD *)(v12 + 112) = v6;
      *(_QWORD *)(v12 + 120) = 0;
      if ( v27 )
      {
        *(_QWORD *)(v12 + 24) = v13;
        v22 = 7;
        if ( &RtlpSystem32Dirs != v27 )
          v22 = 2;
        *(_DWORD *)v7 = v22;
        memmove(v13, *((const void **)v27 + 1), *(unsigned __int16 *)v27);
        v14 = 1;
        v13 += (unsigned __int64)*(unsigned __int16 *)v27 >> 1;
        if ( v30 )
          v13 = (_WORD *)RtlpAddForwarderPath(v25, v13);
      }
      else
      {
        v14 = 0;
      }
      v15 = 0;
      while ( v15 < a2 )
      {
        if ( v27 && ((v21 = *(_DWORD *)(v29 + 4LL * v15), v21 == 2) || v21 == 7) )
        {
LABEL_22:
          ++v15;
        }
        else
        {
          *(_DWORD *)(v7 + 4LL * v14) = *(_DWORD *)(v29 + 4LL * v15);
          *(_QWORD *)(v7 + 8LL * v14 + 24) = v13;
          v16 = *(_DWORD *)(v29 + 4LL * v15);
          if ( v16 != 4 )
          {
            switch ( v16 )
            {
              case 0:
                if ( !(_WORD)LdrpDllDirectory )
                  goto LABEL_21;
                memmove(v13, *((const void **)&LdrpDllDirectory + 1), (unsigned __int16)LdrpDllDirectory);
                v23 = &v13[(unsigned __int64)(unsigned __int16)LdrpDllDirectory >> 1];
                v13 = v23 + 1;
                *v23 = 59;
                ++v14;
                ++v15;
                continue;
              case 1:
                memmove(v13, Src, 0);
                v17 = v13++;
                *v17 = 59;
                goto LABEL_21;
              case 2:
                memmove(v13, *((const void **)&RtlpSystemDirs + 1), (unsigned __int16)RtlpSystemDirs);
                ++v14;
                ++v15;
                v13 += (unsigned __int64)(unsigned __int16)RtlpSystemDirs >> 1;
                continue;
              case 3:
LABEL_21:
                ++v14;
                goto LABEL_22;
              default:
                __fastfail(0x25u);
            }
          }
          *(_QWORD *)(v7 + 120) = v13;
          ++v14;
          *v13 = asc_1801793F4[0];
          v13 += 2;
          ++v15;
          *(v13 - 1) = 59;
        }
      }
      v18 = EnvironmentVariable;
      *(v13 - 1) = 0;
    }
    else
    {
      v18 = -1073741801;
    }
  }
LABEL_24:
  if ( Heap_0 )
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, Heap_0);
  if ( v7 && v18 < 0 )
  {
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v7);
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180099a70  mov     rax, rsp
0x180099a73  mov     [rax+18h], rbx
0x180099a77  mov     [rax+20h], r9b
0x180099a7b  mov     [rax+10h], edx
0x180099a7e  mov     [rax+8], rcx
0x180099a82  push    rbp
0x180099a83  push    rsi
0x180099a84  push    rdi
0x180099a85  push    r12
0x180099a87  push    r13
0x180099a89  push    r14
0x180099a8b  push    r15
0x180099a8d  sub     rsp, 70h
0x180099a91  mov     r15, cs:qword_1801E3500
0x180099a98  mov     r13, r8
0x180099a9b  xor     r8d, r8d
0x180099a9e  shr     r15, 3Ch
0x180099aa2  mov     ebp, edx
0x180099aa4  mov     [rsp+0A8h+Src], r8
0x180099aa9  mov     edx, r8d
0x180099aac  mov     [rax-58h], r8
0x180099ab0  mov     [rax-70h], rdx
0x180099ab4  mov     r12d, r8d
0x180099ab7  mov     [rsp+0A8h+var_78], dl
0x180099abb  mov     edi, 80h
0x180099ac0  mov     [rsp+0A8h+var_50], r8
0x180099ac5  mov     esi, r8d
0x180099ac8  mov     [rax-68h], r8
0x180099acc  and     r15b, 3
0x180099ad0  mov     [rsp+0A8h+var_74], r8d
0x180099ad5  mov     ebx, r8d
0x180099ad8  mov     [rsp+0A8h+var_60], r8
0x180099add  lea     r10, RtlpSystem32Dirs
0x180099ae4  lea     r8, RtlpSystemDirs
0x180099aeb  lea     r11, cs:180000000h
0x180099af2  cmp     ebx, ebp
0x180099af4  jnb     short loc_180099B54
0x180099af6  mov     eax, ebx
0x180099af8  movsxd  rcx, dword ptr [rcx+rax*4]
0x180099afc  cmp     ecx, 3
0x180099aff  jz      loc_180099D8C
0x180099b05  cmp     ecx, 7
0x180099b08  jz      loc_180099C83
0x180099b0e  cmp     ecx, 8; switch 3 cases
0x180099b11  ja      def_180099B22; jumptable 0000000180099B22 default case
0x180099b17  mov     ecx, ds:(jpt_180099B22 - 180000000h)[r11+rcx*4]
0x180099b1f  add     rcx, r11
0x180099b22  jmp     rcx; switch jump
0x180099b28  movzx   eax, word ptr cs:LdrpAppPackagesPath
0x180099b2f  test    ax, ax
0x180099b32  jz      loc_180099CA6
0x180099b38  mov     rcx, [rsp+0A8h+arg_0]
0x180099b40  add     rax, 2
0x180099b44  movzx   r9d, [rsp+0A8h+arg_18]
0x180099b4d  add     rdi, rax
0x180099b50  inc     ebx
0x180099b52  jmp     short loc_180099ADD
0x180099b54  lea     rax, [rdi-80h]
0x180099b58  cmp     rax, 0FFFEh
0x180099b5e  ja      loc_18009A086
0x180099b64  mov     rcx, gs:60h
0x180099b6d  mov     r8, rdi
0x180099b70  xor     edx, edx
0x180099b72  mov     rcx, [rcx+30h]
0x180099b76  call    RtlAllocateHeap_0
0x180099b7b  mov     rsi, rax
0x180099b7e  test    rax, rax
0x180099b81  jz      loc_180099EFB
0x180099b87  mov     r14, [rsp+0A8h+var_60]
0x180099b8c  lea     r15, [rax+80h]
0x180099b93  xor     r8d, r8d
0x180099b96  mov     [rax+48h], bp
0x180099b9a  mov     [rax+58h], r8
0x180099b9e  mov     [rax+60h], r8
0x180099ba2  mov     [rax+68h], r8
0x180099ba6  mov     [rax+70h], edi
0x180099ba9  mov     [rax+78h], r8
0x180099bad  test    r14, r14
0x180099bb0  jnz     loc_18009A104
0x180099bb6  mov     r14d, r8d
0x180099bb9  mov     r13, [rsp+0A8h+arg_0]
0x180099bc1  lea     r9, LdrpUserDllDirectories
0x180099bc8  mov     ebx, r8d
0x180099bcb  mov     edi, 3Bh ; ';'
0x180099bd0  cmp     ebx, ebp
0x180099bd2  jnb     loc_180099D06
0x180099bd8  cmp     [rsp+0A8h+var_60], 0
0x180099bde  mov     edx, ebx
0x180099be0  jnz     loc_18009A091
0x180099be6  mov     eax, [r13+rdx*4+0]
0x180099beb  mov     ecx, r14d
0x180099bee  mov     [rsi+rcx*4], eax
0x180099bf1  mov     [rsi+rcx*8+18h], r15
0x180099bf6  movsxd  rax, dword ptr [r13+rdx*4+0]
0x180099bfb  cmp     eax, 4
0x180099bfe  jz      loc_180099D6B
0x180099c04  cmp     eax, 8; switch 4 cases
0x180099c07  ja      def_180099C1E; jumptable 0000000180099C1E default case
0x180099c0d  lea     rdx, cs:180000000h
0x180099c14  mov     ecx, ds:(jpt_180099C1E - 180000000h)[rdx+rax*4]
0x180099c1b  add     rcx, rdx
0x180099c1e  jmp     rcx; switch jump
0x180099c24  cmp     word ptr cs:LdrpAppPackagesPath, 0
0x180099c2c  jz      loc_180099CFC
0x180099c32  mov     [r15-2], r8w
0x180099c37  mov     rcx, r15; void *
0x180099c3a  movzx   r8d, word ptr cs:LdrpAppPackagesPath; Size
0x180099c42  mov     rdx, qword ptr cs:LdrpAppPackagesPath+8; Src
0x180099c49  call    memmove
0x180099c4e  mov     rax, cs:LdrpAppPackagesPathVersion
0x180099c55  lea     r9, LdrpUserDllDirectories
0x180099c5c  mov     [rsi+68h], r15
0x180099c60  xor     r8d, r8d
0x180099c63  mov     [rsi+60h], rax
0x180099c67  inc     r14d
0x180099c6a  movzx   eax, word ptr cs:LdrpAppPackagesPath
0x180099c71  shr     rax, 1
0x180099c74  lea     r15, [r15+rax*2]
0x180099c78  add     r15, 2
0x180099c7c  inc     ebx
0x180099c7e  jmp     loc_180099BD0
0x180099c83  movzx   edx, word ptr cs:RtlpSystem32Dirs
0x180099c8a  add     rdi, rdx
0x180099c8d  test    r9b, r9b
0x180099c90  jnz     loc_18009A1CC
0x180099c96  cmp     r15b, 1
0x180099c9a  jnz     short loc_180099CA1
0x180099c9c  mov     [rsp+0A8h+var_60], r10
0x180099ca1  mov     rdx, [rsp+0A8h+var_70]
0x180099ca6  mov     rcx, [rsp+0A8h+arg_0]
0x180099cae  inc     ebx
0x180099cb0  movzx   r9d, [rsp+0A8h+arg_18]
0x180099cb9  jmp     loc_180099ADD
0x180099cbe  mov     rdi, [rsp+0A8h+var_70]
0x180099cc3  test    rdi, rdi
0x180099cc6  jz      loc_18009A00A; jumptable 0000000180099C1E case 1
0x180099ccc  mov     rdx, [rsp+0A8h+var_50]; Src
0x180099cd1  mov     r8, rdi; Size
0x180099cd4  mov     rcx, r15; void *
0x180099cd7  call    memmove
0x180099cdc  mov     rax, rdi
0x180099cdf  shr     rax, 1
0x180099ce2  lea     r9, LdrpUserDllDirectories
0x180099ce9  lea     rcx, [r15+rax*2]
0x180099ced  mov     edi, 3Bh ; ';'
0x180099cf2  lea     r15, [rcx+2]
0x180099cf6  mov     [rcx], di
0x180099cf9  xor     r8d, r8d
0x180099cfc  inc     r14d
0x180099cff  inc     ebx
0x180099d01  jmp     loc_180099BD0
0x180099d06  mov     r14d, [rsp+0A8h+var_74]
0x180099d0b  mov     [r15-2], r8w
0x180099d10  test    r12, r12
0x180099d13  jz      short loc_180099D2C
0x180099d15  mov     rcx, gs:60h
0x180099d1e  mov     r8, r12
0x180099d21  xor     edx, edx
0x180099d23  mov     rcx, [rcx+30h]
0x180099d27  call    RtlFreeHeap_0
0x180099d2c  test    rsi, rsi
0x180099d2f  jz      short loc_180099D4F
0x180099d31  test    r14d, r14d
0x180099d34  jns     short loc_180099D4F
0x180099d36  mov     rcx, gs:60h
0x180099d3f  mov     r8, rsi
0x180099d42  xor     edx, edx
0x180099d44  mov     rcx, [rcx+30h]
0x180099d48  call    RtlFreeHeap_0
0x180099d4d  xor     esi, esi
0x180099d4f  mov     rbx, [rsp+0A8h+arg_10]
0x180099d57  mov     rax, rsi
0x180099d5a  add     rsp, 70h
0x180099d5e  pop     r15
0x180099d60  pop     r14
0x180099d62  pop     r13
0x180099d64  pop     r12
0x180099d66  pop     rdi
0x180099d67  pop     rsi
0x180099d68  pop     rbp
0x180099d69  retn
0x180099d6b  mov     [rsi+78h], r15
0x180099d6f  inc     r14d
0x180099d72  mov     eax, dword ptr cs:asc_1801793F4; "."
0x180099d78  mov     [r15], ax
0x180099d7c  add     r15, 4
0x180099d80  inc     ebx
0x180099d82  mov     [r15-2], di
0x180099d87  jmp     loc_180099BD0
0x180099d8c  lea     rcx, FastPebLock
0x180099d93  call    RtlEnterCriticalSection
0x180099d98  lea     rax, [rsp+0A8h+var_68]
0x180099d9d  xor     r9d, r9d
0x180099da0  mov     [rsp+0A8h+var_80], rax
0x180099da5  lea     rdx, aPath; "PATH"
0x180099dac  mov     r8d, 4
0x180099db2  mov     [rsp+0A8h+var_88], rsi
0x180099db7  xor     ecx, ecx
0x180099db9  call    RtlQueryEnvironmentVariable
0x180099dbe  mov     [rsp+0A8h+var_74], eax
0x180099dc2  mov     r14d, eax
0x180099dc5  cmp     eax, 0C0000023h
0x180099dca  jnz     short loc_180099E2C
0x180099dcc  mov     rcx, gs:60h
0x180099dd5  mov     edx, cs:NtdllBaseTag
0x180099ddb  mov     r14, [rsp+0A8h+var_68]
0x180099de0  add     edx, 180000h
0x180099de6  mov     rcx, [rcx+30h]
0x180099dea  lea     r8, [r14+r14]
0x180099dee  call    RtlAllocateHeap_0
0x180099df3  mov     r12, rax
0x180099df6  test    rax, rax
0x180099df9  jz      loc_18009A1BB
0x180099dff  lea     rax, [rsp+0A8h+var_68]
0x180099e04  mov     r9, r12
0x180099e07  mov     [rsp+0A8h+var_80], rax
0x180099e0c  lea     rdx, aPath; "PATH"
0x180099e13  mov     r8d, 4
0x180099e19  mov     [rsp+0A8h+var_88], r14
0x180099e1e  xor     ecx, ecx
0x180099e20  call    RtlQueryEnvironmentVariable
0x180099e25  mov     r14d, eax
0x180099e28  mov     [rsp+0A8h+var_74], eax
0x180099e2c  lea     rcx, FastPebLock
0x180099e33  call    RtlLeaveCriticalSection
0x180099e38  cmp     r14d, 0C0000100h
0x180099e3f  jz      loc_18009A026
0x180099e45  test    r14d, r14d
0x180099e48  js      loc_180099D10
0x180099e4e  mov     rax, [rsp+0A8h+var_68]
0x180099e53  lea     rdi, [rdi+rax*2]
0x180099e57  add     rdi, 2
0x180099e5b  jmp     loc_180099CA1
0x180099e60  movzx   r8d, word ptr cs:RtlpSystem32Dirs; Size
0x180099e68  mov     rcx, r15; void *
0x180099e6b  mov     rdx, qword ptr cs:RtlpSystem32Dirs+8; Src
0x180099e72  call    memmove
0x180099e77  movzx   eax, word ptr cs:RtlpSystem32Dirs
0x180099e7e  shr     rax, 1
0x180099e81  cmp     [rsp+0A8h+arg_18], 0
0x180099e89  lea     r15, [r15+rax*2]
0x180099e8d  jz      loc_18009A1A7
0x180099e93  movzx   ecx, [rsp+0A8h+var_78]
0x180099e98  mov     rdx, r15
0x180099e9b  call    RtlpAddForwarderPath
0x180099ea0  xor     r8d, r8d
0x180099ea3  lea     r9, LdrpUserDllDirectories
0x180099eaa  inc     r14d
0x180099ead  mov     r15, rax
0x180099eb0  inc     ebx
0x180099eb2  jmp     loc_180099BD0
0x180099eb7  test    r13, r13
0x180099eba  jz      short loc_180099ED3
0x180099ebc  lea     rdx, [rsp+0A8h+var_70]
0x180099ec1  mov     rcx, r13; Str
0x180099ec4  call    RtlpGetDirPath
0x180099ec9  mov     rdx, [rsp+0A8h+var_70]
0x180099ece  mov     [rsp+0A8h+var_50], rax
0x180099ed3  test    rdx, rdx
0x180099ed6  jz      loc_180099FD0; jumptable 0000000180099B22 case 1
0x180099edc  mov     rcx, [rsp+0A8h+arg_0]
0x180099ee4  add     rdi, 2
0x180099ee8  movzx   r9d, [rsp+0A8h+arg_18]
0x180099ef1  add     rdi, rdx
0x180099ef4  inc     ebx
0x180099ef6  jmp     loc_180099ADD
0x180099efb  mov     r14d, 0C0000017h
0x180099f01  jmp     loc_180099D10
0x180099f06  mov     rcx, [rsp+0A8h+arg_0]
0x180099f0e  add     rdi, 4
0x180099f12  movzx   r9d, [rsp+0A8h+arg_18]
0x180099f1b  inc     ebx
0x180099f1d  jmp     loc_180099ADD
0x180099f22  movzx   eax, word ptr cs:RtlpSystemDirs; jumptable 0000000180099B22 case 2
0x180099f29  add     rdi, rax
0x180099f2c  cmp     r15b, 1
0x180099f30  jnz     loc_180099CA6
0x180099f36  mov     rcx, [rsp+0A8h+arg_0]
0x180099f3e  inc     ebx
0x180099f40  movzx   r9d, [rsp+0A8h+arg_18]
0x180099f49  mov     [rsp+0A8h+var_60], r8
0x180099f4e  jmp     loc_180099ADD
0x180099f53  mov     rax, [rsp+0A8h+var_68]; jumptable 0000000180099C1E case 3
0x180099f58  test    rax, rax
0x180099f5b  jz      loc_180099CFC
0x180099f61  lea     rdi, [rax+rax]
0x180099f65  mov     rdx, r12; Src
0x180099f68  mov     r8, rdi; Size
0x180099f6b  mov     rcx, r15; void *
0x180099f6e  call    memmove
0x180099f73  lea     rax, [rdi+r15]
0x180099f77  xor     r8d, r8d
0x180099f7a  mov     edi, 3Bh ; ';'
0x180099f7f  lea     r15, [rax+2]
0x180099f83  inc     r14d
0x180099f86  mov     [rax], di
0x180099f89  lea     r9, LdrpUserDllDirectories
0x180099f90  inc     ebx
0x180099f92  jmp     loc_180099BD0
0x180099f97  movzx   r8d, word ptr cs:RtlpSystemDirs; jumptable 0000000180099C1E case 2
  ... truncated ...
```
