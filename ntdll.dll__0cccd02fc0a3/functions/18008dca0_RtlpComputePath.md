# RtlpComputePath

- ea: `0x18008dca0`
- end: `0x18008e478`
- name: `RtlpComputePath`
- size: `2008`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002beb4`
- `0x18008c000`
- `0x18008c110`
- `0x18008db70`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x1800535c0`
- `0x180053ab0`
- `0x18008dac4`
- `0x18008dca0`
- `0x18008e8e0`
- `0x18011e2dc`
- `0x18011f918`
- `0x180163a80`

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
          *v13 = asc_180178FEC[0];
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
0x18008dca0  mov     rax, rsp
0x18008dca3  mov     [rax+18h], rbx
0x18008dca7  mov     [rax+20h], r9b
0x18008dcab  mov     [rax+10h], edx
0x18008dcae  mov     [rax+8], rcx
0x18008dcb2  push    rbp
0x18008dcb3  push    rsi
0x18008dcb4  push    rdi
0x18008dcb5  push    r12
0x18008dcb7  push    r13
0x18008dcb9  push    r14
0x18008dcbb  push    r15
0x18008dcbd  sub     rsp, 70h
0x18008dcc1  mov     r15, cs:qword_1801E3500
0x18008dcc8  mov     r13, r8
0x18008dccb  xor     r8d, r8d
0x18008dcce  shr     r15, 3Ch
0x18008dcd2  mov     ebp, edx
0x18008dcd4  mov     [rsp+0A8h+Src], r8
0x18008dcd9  mov     edx, r8d
0x18008dcdc  mov     [rax-58h], r8
0x18008dce0  mov     [rax-70h], rdx
0x18008dce4  mov     r12d, r8d
0x18008dce7  mov     [rsp+0A8h+var_78], dl
0x18008dceb  mov     edi, 80h
0x18008dcf0  mov     [rsp+0A8h+var_50], r8
0x18008dcf5  mov     esi, r8d
0x18008dcf8  mov     [rax-68h], r8
0x18008dcfc  and     r15b, 3
0x18008dd00  mov     [rsp+0A8h+var_74], r8d
0x18008dd05  mov     ebx, r8d
0x18008dd08  mov     [rsp+0A8h+var_60], r8
0x18008dd0d  lea     r10, RtlpSystem32Dirs
0x18008dd14  lea     r8, RtlpSystemDirs
0x18008dd1b  lea     r11, cs:180000000h
0x18008dd22  cmp     ebx, ebp
0x18008dd24  jnb     short loc_18008DD84
0x18008dd26  mov     eax, ebx
0x18008dd28  movsxd  rcx, dword ptr [rcx+rax*4]
0x18008dd2c  cmp     ecx, 3
0x18008dd2f  jz      loc_18008DFBC
0x18008dd35  cmp     ecx, 7
0x18008dd38  jz      loc_18008DEB3
0x18008dd3e  cmp     ecx, 8; switch 3 cases
0x18008dd41  ja      def_18008DD52; jumptable 000000018008DD52 default case
0x18008dd47  mov     ecx, ds:(jpt_18008DD52 - 180000000h)[r11+rcx*4]
0x18008dd4f  add     rcx, r11
0x18008dd52  jmp     rcx; switch jump
0x18008dd58  movzx   eax, word ptr cs:LdrpAppPackagesPath
0x18008dd5f  test    ax, ax
0x18008dd62  jz      loc_18008DED6
0x18008dd68  mov     rcx, [rsp+0A8h+arg_0]
0x18008dd70  add     rax, 2
0x18008dd74  movzx   r9d, [rsp+0A8h+arg_18]
0x18008dd7d  add     rdi, rax
0x18008dd80  inc     ebx
0x18008dd82  jmp     short loc_18008DD0D
0x18008dd84  lea     rax, [rdi-80h]
0x18008dd88  cmp     rax, 0FFFEh
0x18008dd8e  ja      loc_18008E2B6
0x18008dd94  mov     rcx, gs:60h
0x18008dd9d  mov     r8, rdi
0x18008dda0  xor     edx, edx
0x18008dda2  mov     rcx, [rcx+30h]
0x18008dda6  call    RtlAllocateHeap_0
0x18008ddab  mov     rsi, rax
0x18008ddae  test    rax, rax
0x18008ddb1  jz      loc_18008E12B
0x18008ddb7  mov     r14, [rsp+0A8h+var_60]
0x18008ddbc  lea     r15, [rax+80h]
0x18008ddc3  xor     r8d, r8d
0x18008ddc6  mov     [rax+48h], bp
0x18008ddca  mov     [rax+58h], r8
0x18008ddce  mov     [rax+60h], r8
0x18008ddd2  mov     [rax+68h], r8
0x18008ddd6  mov     [rax+70h], edi
0x18008ddd9  mov     [rax+78h], r8
0x18008dddd  test    r14, r14
0x18008dde0  jnz     loc_18008E334
0x18008dde6  mov     r14d, r8d
0x18008dde9  mov     r13, [rsp+0A8h+arg_0]
0x18008ddf1  lea     r9, LdrpUserDllDirectories
0x18008ddf8  mov     ebx, r8d
0x18008ddfb  mov     edi, 3Bh ; ';'
0x18008de00  cmp     ebx, ebp
0x18008de02  jnb     loc_18008DF36
0x18008de08  cmp     [rsp+0A8h+var_60], 0
0x18008de0e  mov     edx, ebx
0x18008de10  jnz     loc_18008E2C1
0x18008de16  mov     eax, [r13+rdx*4+0]
0x18008de1b  mov     ecx, r14d
0x18008de1e  mov     [rsi+rcx*4], eax
0x18008de21  mov     [rsi+rcx*8+18h], r15
0x18008de26  movsxd  rax, dword ptr [r13+rdx*4+0]
0x18008de2b  cmp     eax, 4
0x18008de2e  jz      loc_18008DF9B
0x18008de34  cmp     eax, 8; switch 4 cases
0x18008de37  ja      def_18008DE4E; jumptable 000000018008DE4E default case
0x18008de3d  lea     rdx, cs:180000000h
0x18008de44  mov     ecx, ds:(jpt_18008DE4E - 180000000h)[rdx+rax*4]
0x18008de4b  add     rcx, rdx
0x18008de4e  jmp     rcx; switch jump
0x18008de54  cmp     word ptr cs:LdrpAppPackagesPath, 0
0x18008de5c  jz      loc_18008DF2C
0x18008de62  mov     [r15-2], r8w
0x18008de67  mov     rcx, r15; void *
0x18008de6a  movzx   r8d, word ptr cs:LdrpAppPackagesPath; Size
0x18008de72  mov     rdx, qword ptr cs:LdrpAppPackagesPath+8; Src
0x18008de79  call    memmove
0x18008de7e  mov     rax, cs:LdrpAppPackagesPathVersion
0x18008de85  lea     r9, LdrpUserDllDirectories
0x18008de8c  mov     [rsi+68h], r15
0x18008de90  xor     r8d, r8d
0x18008de93  mov     [rsi+60h], rax
0x18008de97  inc     r14d
0x18008de9a  movzx   eax, word ptr cs:LdrpAppPackagesPath
0x18008dea1  shr     rax, 1
0x18008dea4  lea     r15, [r15+rax*2]
0x18008dea8  add     r15, 2
0x18008deac  inc     ebx
0x18008deae  jmp     loc_18008DE00
0x18008deb3  movzx   edx, word ptr cs:RtlpSystem32Dirs
0x18008deba  add     rdi, rdx
0x18008debd  test    r9b, r9b
0x18008dec0  jnz     loc_18008E3FC
0x18008dec6  cmp     r15b, 1
0x18008deca  jnz     short loc_18008DED1
0x18008decc  mov     [rsp+0A8h+var_60], r10
0x18008ded1  mov     rdx, [rsp+0A8h+var_70]
0x18008ded6  mov     rcx, [rsp+0A8h+arg_0]
0x18008dede  inc     ebx
0x18008dee0  movzx   r9d, [rsp+0A8h+arg_18]
0x18008dee9  jmp     loc_18008DD0D
0x18008deee  mov     rdi, [rsp+0A8h+var_70]
0x18008def3  test    rdi, rdi
0x18008def6  jz      loc_18008E23A; jumptable 000000018008DE4E case 1
0x18008defc  mov     rdx, [rsp+0A8h+var_50]; Src
0x18008df01  mov     r8, rdi; Size
0x18008df04  mov     rcx, r15; void *
0x18008df07  call    memmove
0x18008df0c  mov     rax, rdi
0x18008df0f  shr     rax, 1
0x18008df12  lea     r9, LdrpUserDllDirectories
0x18008df19  lea     rcx, [r15+rax*2]
0x18008df1d  mov     edi, 3Bh ; ';'
0x18008df22  lea     r15, [rcx+2]
0x18008df26  mov     [rcx], di
0x18008df29  xor     r8d, r8d
0x18008df2c  inc     r14d
0x18008df2f  inc     ebx
0x18008df31  jmp     loc_18008DE00
0x18008df36  mov     r14d, [rsp+0A8h+var_74]
0x18008df3b  mov     [r15-2], r8w
0x18008df40  test    r12, r12
0x18008df43  jz      short loc_18008DF5C
0x18008df45  mov     rcx, gs:60h
0x18008df4e  mov     r8, r12
0x18008df51  xor     edx, edx
0x18008df53  mov     rcx, [rcx+30h]
0x18008df57  call    RtlFreeHeap_0
0x18008df5c  test    rsi, rsi
0x18008df5f  jz      short loc_18008DF7F
0x18008df61  test    r14d, r14d
0x18008df64  jns     short loc_18008DF7F
0x18008df66  mov     rcx, gs:60h
0x18008df6f  mov     r8, rsi
0x18008df72  xor     edx, edx
0x18008df74  mov     rcx, [rcx+30h]
0x18008df78  call    RtlFreeHeap_0
0x18008df7d  xor     esi, esi
0x18008df7f  mov     rbx, [rsp+0A8h+arg_10]
0x18008df87  mov     rax, rsi
0x18008df8a  add     rsp, 70h
0x18008df8e  pop     r15
0x18008df90  pop     r14
0x18008df92  pop     r13
0x18008df94  pop     r12
0x18008df96  pop     rdi
0x18008df97  pop     rsi
0x18008df98  pop     rbp
0x18008df99  retn
0x18008df9b  mov     [rsi+78h], r15
0x18008df9f  inc     r14d
0x18008dfa2  mov     eax, dword ptr cs:asc_180178FEC; "."
0x18008dfa8  mov     [r15], ax
0x18008dfac  add     r15, 4
0x18008dfb0  inc     ebx
0x18008dfb2  mov     [r15-2], di
0x18008dfb7  jmp     loc_18008DE00
0x18008dfbc  lea     rcx, FastPebLock
0x18008dfc3  call    RtlEnterCriticalSection
0x18008dfc8  lea     rax, [rsp+0A8h+var_68]
0x18008dfcd  xor     r9d, r9d
0x18008dfd0  mov     [rsp+0A8h+var_80], rax
0x18008dfd5  lea     rdx, aPath; "PATH"
0x18008dfdc  mov     r8d, 4
0x18008dfe2  mov     [rsp+0A8h+var_88], rsi
0x18008dfe7  xor     ecx, ecx
0x18008dfe9  call    RtlQueryEnvironmentVariable
0x18008dfee  mov     [rsp+0A8h+var_74], eax
0x18008dff2  mov     r14d, eax
0x18008dff5  cmp     eax, 0C0000023h
0x18008dffa  jnz     short loc_18008E05C
0x18008dffc  mov     rcx, gs:60h
0x18008e005  mov     edx, cs:NtdllBaseTag
0x18008e00b  mov     r14, [rsp+0A8h+var_68]
0x18008e010  add     edx, 180000h
0x18008e016  mov     rcx, [rcx+30h]
0x18008e01a  lea     r8, [r14+r14]
0x18008e01e  call    RtlAllocateHeap_0
0x18008e023  mov     r12, rax
0x18008e026  test    rax, rax
0x18008e029  jz      loc_18008E3EB
0x18008e02f  lea     rax, [rsp+0A8h+var_68]
0x18008e034  mov     r9, r12
0x18008e037  mov     [rsp+0A8h+var_80], rax
0x18008e03c  lea     rdx, aPath; "PATH"
0x18008e043  mov     r8d, 4
0x18008e049  mov     [rsp+0A8h+var_88], r14
0x18008e04e  xor     ecx, ecx
0x18008e050  call    RtlQueryEnvironmentVariable
0x18008e055  mov     r14d, eax
0x18008e058  mov     [rsp+0A8h+var_74], eax
0x18008e05c  lea     rcx, FastPebLock
0x18008e063  call    RtlLeaveCriticalSection
0x18008e068  cmp     r14d, 0C0000100h
0x18008e06f  jz      loc_18008E256
0x18008e075  test    r14d, r14d
0x18008e078  js      loc_18008DF40
0x18008e07e  mov     rax, [rsp+0A8h+var_68]
0x18008e083  lea     rdi, [rdi+rax*2]
0x18008e087  add     rdi, 2
0x18008e08b  jmp     loc_18008DED1
0x18008e090  movzx   r8d, word ptr cs:RtlpSystem32Dirs; Size
0x18008e098  mov     rcx, r15; void *
0x18008e09b  mov     rdx, qword ptr cs:RtlpSystem32Dirs+8; Src
0x18008e0a2  call    memmove
0x18008e0a7  movzx   eax, word ptr cs:RtlpSystem32Dirs
0x18008e0ae  shr     rax, 1
0x18008e0b1  cmp     [rsp+0A8h+arg_18], 0
0x18008e0b9  lea     r15, [r15+rax*2]
0x18008e0bd  jz      loc_18008E3D7
0x18008e0c3  movzx   ecx, [rsp+0A8h+var_78]
0x18008e0c8  mov     rdx, r15
0x18008e0cb  call    RtlpAddForwarderPath
0x18008e0d0  xor     r8d, r8d
0x18008e0d3  lea     r9, LdrpUserDllDirectories
0x18008e0da  inc     r14d
0x18008e0dd  mov     r15, rax
0x18008e0e0  inc     ebx
0x18008e0e2  jmp     loc_18008DE00
0x18008e0e7  test    r13, r13
0x18008e0ea  jz      short loc_18008E103
0x18008e0ec  lea     rdx, [rsp+0A8h+var_70]
0x18008e0f1  mov     rcx, r13; Str
0x18008e0f4  call    RtlpGetDirPath
0x18008e0f9  mov     rdx, [rsp+0A8h+var_70]
0x18008e0fe  mov     [rsp+0A8h+var_50], rax
0x18008e103  test    rdx, rdx
0x18008e106  jz      loc_18008E200; jumptable 000000018008DD52 case 1
0x18008e10c  mov     rcx, [rsp+0A8h+arg_0]
0x18008e114  add     rdi, 2
0x18008e118  movzx   r9d, [rsp+0A8h+arg_18]
0x18008e121  add     rdi, rdx
0x18008e124  inc     ebx
0x18008e126  jmp     loc_18008DD0D
0x18008e12b  mov     r14d, 0C0000017h
0x18008e131  jmp     loc_18008DF40
0x18008e136  mov     rcx, [rsp+0A8h+arg_0]
0x18008e13e  add     rdi, 4
0x18008e142  movzx   r9d, [rsp+0A8h+arg_18]
0x18008e14b  inc     ebx
0x18008e14d  jmp     loc_18008DD0D
0x18008e152  movzx   eax, word ptr cs:RtlpSystemDirs; jumptable 000000018008DD52 case 2
0x18008e159  add     rdi, rax
0x18008e15c  cmp     r15b, 1
0x18008e160  jnz     loc_18008DED6
0x18008e166  mov     rcx, [rsp+0A8h+arg_0]
0x18008e16e  inc     ebx
0x18008e170  movzx   r9d, [rsp+0A8h+arg_18]
0x18008e179  mov     [rsp+0A8h+var_60], r8
0x18008e17e  jmp     loc_18008DD0D
0x18008e183  mov     rax, [rsp+0A8h+var_68]; jumptable 000000018008DE4E case 3
0x18008e188  test    rax, rax
0x18008e18b  jz      loc_18008DF2C
0x18008e191  lea     rdi, [rax+rax]
0x18008e195  mov     rdx, r12; Src
0x18008e198  mov     r8, rdi; Size
0x18008e19b  mov     rcx, r15; void *
0x18008e19e  call    memmove
0x18008e1a3  lea     rax, [rdi+r15]
0x18008e1a7  xor     r8d, r8d
0x18008e1aa  mov     edi, 3Bh ; ';'
0x18008e1af  lea     r15, [rax+2]
0x18008e1b3  inc     r14d
0x18008e1b6  mov     [rax], di
0x18008e1b9  lea     r9, LdrpUserDllDirectories
0x18008e1c0  inc     ebx
0x18008e1c2  jmp     loc_18008DE00
0x18008e1c7  movzx   r8d, word ptr cs:RtlpSystemDirs; jumptable 000000018008DE4E case 2
  ... truncated ...
```
