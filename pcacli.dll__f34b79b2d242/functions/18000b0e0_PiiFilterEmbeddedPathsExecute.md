# PiiFilterEmbeddedPathsExecute

- ea: `0x18000b0e0`
- end: `0x18000b505`
- name: `PiiFilterEmbeddedPathsExecute`
- size: `1061`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180003560`

## callees

- `0x180006880`
- `0x180006e50`
- `0x180007010`
- `0x180007668`
- `0x18000824a`
- `0x180008660`
- `0x180008e54`
- `0x18000b068`
- `0x18000b0e0`

## import_xrefs

- `msvcrt!wcschr` at `0x18000b3a5`
- `msvcrt!wcschr` at `0x18000b4a5`
- `msvcrt!wcschr` at `0x18000b3a5`
- `msvcrt!wcschr` at `0x18000b4a5`
- `msvcrt!iswspace` at `0x18000b3fe`
- `msvcrt!iswspace` at `0x18000b459`
- `msvcrt!iswspace` at `0x18000b3fe`
- `msvcrt!iswspace` at `0x18000b459`
- `ntdll!RtlAllocateHeap` at `0x18000b11e`
- `ntdll!RtlAllocateHeap` at `0x18000b150`
- `ntdll!RtlAllocateHeap` at `0x18000b11e`
- `ntdll!RtlAllocateHeap` at `0x18000b150`

## pseudocode

```c
__int64 __fastcall PiiFilterEmbeddedPathsExecute(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        _QWORD *a3,
        const unsigned __int16 *a4)
{
  unsigned __int16 *v7; // r13
  int v8; // edi
  unsigned __int16 *v9; // rsi
  unsigned __int64 v10; // rdx
  unsigned int v11; // ebp
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // rcx
  const unsigned __int16 **v14; // rdx
  RtlNameValueArray *v15; // r9
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rcx
  const unsigned __int16 *v18; // r15
  const unsigned __int16 *Value; // r12
  __int64 v20; // r15
  wchar_t *v21; // rcx
  __int64 v22; // rcx
  const unsigned __int16 *v23; // r8
  unsigned int v24; // r11d
  const wchar_t *v25; // rcx
  wchar_t v26; // dx
  unsigned __int16 *v27; // rdi
  wchar_t *v28; // rax
  wchar_t *v29; // rbx
  wint_t *v30; // rdi
  int v31; // ebp
  int v32; // eax
  char *v33; // rdi
  unsigned __int64 v34; // rcx
  unsigned __int64 v36; // [rsp+68h] [rbp+10h] BYREF
  unsigned __int16 *Heap; // [rsp+70h] [rbp+18h]

  v36 = a2;
  Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x800u);
  v7 = Heap;
  if ( Heap )
  {
    v9 = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x800u);
    if ( v9 )
    {
      v8 = RtlStringCchCopyW(a1, 0x400u, a4);
      if ( v8 >= 0 )
      {
        v10 = a3[2];
        if ( v10 + a3[8] )
        {
          v11 = 0;
          while ( 1 )
          {
            v12 = v11;
            if ( v11 >= v10 )
            {
              v15 = (RtlNameValueArray *)(a3 + 6);
              v16 = v11 - v10;
              v14 = 0;
              if ( v16 < a3[8] )
              {
                v17 = a3[7];
                v36 = 0;
                if ( (int)ULongLongMult(v17, v16, &v36) < 0
                  || (v14 = (const unsigned __int16 **)(a3[11] + v36), (unsigned __int64)v14 < a3[11]) )
                {
                  v14 = 0;
                }
              }
              v12 = v11 - a3[2];
            }
            else
            {
              v13 = a3[1];
              v36 = 0;
              if ( (int)ULongLongMult(v13, v11, &v36) < 0
                || (v14 = (const unsigned __int16 **)(a3[5] + v36), (unsigned __int64)v14 < a3[5]) )
              {
                v14 = 0;
              }
              v15 = (RtlNameValueArray *)a3;
            }
            v18 = *v14;
            Value = RtlNameValueArray::GetValue(v15, v12);
            v8 = RtlStringCchCopyW(v9, 0x400u, a1);
            if ( v8 < 0 )
              break;
            AslStringUpper(v9);
            v8 = RtlStringCchCopyW(v7, 0x400u, v18);
            if ( v8 < 0 )
              break;
            v20 = -1;
            do
              ++v20;
            while ( v7[v20] );
            if ( v20 && (AslStringUpper(v7), (v21 = wcsstr_0(v9, v7)) != 0) )
            {
              v22 = v21 - v9;
              a1[v22] = 0;
              v23 = &a1[v22 + v20];
              if ( v23 >= a1 + 1024 )
                break;
              v8 = RtlStringCchCopyW(v9, 0x400u, v23);
              if ( v8 < 0 )
                break;
              v8 = RtlStringCchCatW(a1, v24, Value);
              if ( v8 < 0 )
                break;
              v8 = RtlStringCchCatW(a1, 0x400u, v9);
              if ( v8 < 0 )
                break;
            }
            else
            {
              ++v11;
            }
            v10 = a3[2];
            if ( v11 >= v10 + a3[8] )
              goto LABEL_30;
          }
        }
        else
        {
LABEL_30:
          v8 = RtlStringCchCopyW(v9, 0x400u, a1);
          if ( v8 >= 0 )
          {
            AslStringUpper(v9);
            v25 = v9;
            while ( 1 )
            {
              v28 = wcsstr_0(v25, L"\\USERS\\");
              if ( !v28 )
                break;
              v25 = v28 + 7;
              v26 = v28[7];
              if ( v26 )
              {
                v27 = &a1[v25 - v9];
                do
                {
                  if ( v26 == 92 )
                    break;
                  if ( v27 >= a1 + 1024 )
                    break;
                  ++v25;
                  *v27++ = 120;
                  v26 = *v25;
                }
                while ( *v25 );
              }
            }
            v29 = wcschr(a1, 0x40u);
            if ( v29 )
            {
              do
              {
                if ( !*v29 )
                  break;
                v30 = v29 - 1;
                LODWORD(v36) = 0;
                v31 = 0;
                while ( *++v29 && !(unsigned int)PiipIsInvalidEmailCharacter(*v29, 0, (int *)&v36) )
                {
                  if ( *v29 == 46 )
                    v31 = 1;
                }
                if ( iswspace(*v29) || !*v29 || (v32 = 0, *v29 == 62) )
                  v32 = 1;
                if ( v31 && v32 )
                {
                  --v29;
                  LODWORD(v36) = 0;
                  while ( v30 >= a1 )
                  {
                    if ( (unsigned int)PiipIsInvalidEmailCharacter(*v30, 1, (int *)&v36) )
                    {
                      if ( *v30 != 60 && !iswspace(*v30) )
                        goto LABEL_64;
                      break;
                    }
                    --v30;
                  }
                  if ( !(_DWORD)v36 )
                  {
                    v33 = (char *)(v30 + 1);
                    v34 = (unsigned __int64)((char *)v29 - v33 + 2) >> 1;
                    if ( v33 > (char *)v29 )
                      v34 = 0;
                    if ( v34 )
                    {
                      while ( v34 )
                      {
                        *(_WORD *)v33 = 35;
                        v33 += 2;
                        --v34;
                      }
                    }
                  }
                }
LABEL_64:
                v29 = wcschr(v29, 0x40u);
              }
              while ( v29 );
              v7 = Heap;
            }
            v8 = 0;
          }
        }
      }
    }
    else
    {
      v8 = -1073741801;
    }
    AslFree(NtCurrentPeb()->ProcessHeap, v7);
    if ( v9 )
      AslFree(NtCurrentPeb()->ProcessHeap, v9);
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000b0e0  mov     [rsp+arg_0], rbx
0x18000b0e5  mov     [rsp+arg_8], rdx
0x18000b0ea  push    rbp
0x18000b0eb  push    rsi
0x18000b0ec  push    rdi
0x18000b0ed  push    r12
0x18000b0ef  push    r13
0x18000b0f1  push    r14
0x18000b0f3  push    r15
0x18000b0f5  sub     rsp, 20h
0x18000b0f9  mov     r14, rcx
0x18000b0fc  mov     rbx, r8
0x18000b0ff  mov     rcx, gs:60h
0x18000b108  mov     esi, 800h
0x18000b10d  mov     ebp, 8
0x18000b112  mov     r8d, esi; Size
0x18000b115  mov     edx, ebp; Flags
0x18000b117  mov     rdi, r9
0x18000b11a  mov     rcx, [rcx+30h]; HeapHandle
0x18000b11e  call    cs:__imp_RtlAllocateHeap
0x18000b124  xor     r15d, r15d
0x18000b127  mov     [rsp+58h+arg_10], rax
0x18000b12c  mov     r13, rax
0x18000b12f  test    rax, rax
0x18000b132  jnz     short loc_18000B13E
0x18000b134  mov     edi, 0C0000017h
0x18000b139  jmp     loc_18000B4EE
0x18000b13e  mov     rcx, gs:60h
0x18000b147  mov     r8, rsi; Size
0x18000b14a  mov     edx, ebp; Flags
0x18000b14c  mov     rcx, [rcx+30h]; HeapHandle
0x18000b150  call    cs:__imp_RtlAllocateHeap
0x18000b156  mov     rsi, rax
0x18000b159  test    rax, rax
0x18000b15c  jnz     short loc_18000B168
0x18000b15e  mov     edi, 0C0000017h
0x18000b163  jmp     loc_18000B4BF
0x18000b168  mov     r8, rdi; unsigned __int16 *
0x18000b16b  mov     edx, 400h; unsigned __int64
0x18000b170  mov     rcx, r14; unsigned __int16 *
0x18000b173  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b178  mov     edi, eax
0x18000b17a  test    eax, eax
0x18000b17c  js      loc_18000B4BF
0x18000b182  mov     rdx, [rbx+10h]
0x18000b186  mov     rcx, [rbx+40h]
0x18000b18a  add     rcx, rdx
0x18000b18d  jz      loc_18000B323
0x18000b193  mov     ebp, r15d
0x18000b196  mov     edi, ebp
0x18000b198  cmp     rdi, rdx
0x18000b19b  jnb     short loc_18000B1CD
0x18000b19d  mov     rcx, [rbx+8]; unsigned __int64
0x18000b1a1  lea     r8, [rsp+58h+arg_8]; unsigned __int64 *
0x18000b1a6  mov     edx, edi; unsigned __int64
0x18000b1a8  mov     [rsp+58h+arg_8], r15
0x18000b1ad  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000b1b2  test    eax, eax
0x18000b1b4  js      short loc_18000B1C5
0x18000b1b6  mov     rdx, [rsp+58h+arg_8]
0x18000b1bb  add     rdx, [rbx+28h]
0x18000b1bf  cmp     rdx, [rbx+28h]
0x18000b1c3  jnb     short loc_18000B1C8
0x18000b1c5  mov     rdx, r15
0x18000b1c8  mov     r9, rbx
0x18000b1cb  jmp     short loc_18000B210
0x18000b1cd  mov     rax, rdi
0x18000b1d0  lea     r9, [rbx+30h]
0x18000b1d4  sub     rax, rdx
0x18000b1d7  mov     rdx, r15
0x18000b1da  cmp     rax, [r9+10h]
0x18000b1de  jnb     short loc_18000B20C
0x18000b1e0  mov     rcx, [rbx+38h]; unsigned __int64
0x18000b1e4  lea     r8, [rsp+58h+arg_8]; unsigned __int64 *
0x18000b1e9  mov     rdx, rax; unsigned __int64
0x18000b1ec  mov     [rsp+58h+arg_8], r15
0x18000b1f1  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000b1f6  test    eax, eax
0x18000b1f8  js      short loc_18000B209
0x18000b1fa  mov     rdx, [rsp+58h+arg_8]
0x18000b1ff  add     rdx, [rbx+58h]
0x18000b203  cmp     rdx, [rbx+58h]
0x18000b207  jnb     short loc_18000B20C
0x18000b209  mov     rdx, r15
0x18000b20c  sub     rdi, [rbx+10h]
0x18000b210  mov     r15, [rdx]
0x18000b213  mov     rcx, r9; this
0x18000b216  mov     rdx, rdi; unsigned __int64
0x18000b219  call    ?GetValue@RtlNameValueArray@@QEBAPEBG_K@Z; RtlNameValueArray::GetValue(unsigned __int64)
0x18000b21e  mov     r8, r14; unsigned __int16 *
0x18000b221  mov     edx, 400h; unsigned __int64
0x18000b226  mov     rcx, rsi; unsigned __int16 *
0x18000b229  mov     r12, rax
0x18000b22c  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b231  mov     edi, eax
0x18000b233  test    eax, eax
0x18000b235  js      loc_18000B4BF
0x18000b23b  mov     rcx, rsi
0x18000b23e  call    AslStringUpper
0x18000b243  mov     r8, r15; unsigned __int16 *
0x18000b246  mov     edx, 400h; unsigned __int64
0x18000b24b  mov     rcx, r13; unsigned __int16 *
0x18000b24e  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b253  mov     edi, eax
0x18000b255  test    eax, eax
0x18000b257  js      loc_18000B4BF
0x18000b25d  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000b261  xor     eax, eax
0x18000b263  inc     r15
0x18000b266  cmp     [r13+r15*2+0], ax
0x18000b26c  jnz     short loc_18000B263
0x18000b26e  test    r15, r15
0x18000b271  jnz     short loc_18000B27D
0x18000b273  inc     ebp
0x18000b275  xor     r15d, r15d
0x18000b278  jmp     loc_18000B30D
0x18000b27d  mov     rcx, r13
0x18000b280  call    AslStringUpper
0x18000b285  mov     rdx, r13; SubStr
0x18000b288  mov     rcx, rsi; Str
0x18000b28b  call    wcsstr_0
0x18000b290  mov     rcx, rax
0x18000b293  xor     eax, eax
0x18000b295  test    rcx, rcx
0x18000b298  jz      short loc_18000B273
0x18000b29a  sub     rcx, rsi
0x18000b29d  sar     rcx, 1
0x18000b2a0  mov     [r14+rcx*2], ax
0x18000b2a5  lea     rax, [rcx+r15]
0x18000b2a9  lea     r8, [r14+rax*2]; unsigned __int16 *
0x18000b2ad  lea     rax, [r14+800h]
0x18000b2b4  cmp     r8, rax
0x18000b2b7  jnb     loc_18000B4BF
0x18000b2bd  mov     r11d, 400h
0x18000b2c3  mov     rcx, rsi; unsigned __int16 *
0x18000b2c6  mov     edx, r11d; unsigned __int64
0x18000b2c9  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b2ce  xor     r15d, r15d
0x18000b2d1  mov     edi, eax
0x18000b2d3  test    eax, eax
0x18000b2d5  js      loc_18000B4BF
0x18000b2db  mov     r8, r12; unsigned __int16 *
0x18000b2de  mov     edx, r11d; unsigned __int64
0x18000b2e1  mov     rcx, r14; unsigned __int16 *
0x18000b2e4  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b2e9  mov     edi, eax
0x18000b2eb  test    eax, eax
0x18000b2ed  js      loc_18000B4BF
0x18000b2f3  mov     r8, rsi; unsigned __int16 *
0x18000b2f6  mov     edx, 400h; unsigned __int64
0x18000b2fb  mov     rcx, r14; unsigned __int16 *
0x18000b2fe  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b303  mov     edi, eax
0x18000b305  test    eax, eax
0x18000b307  js      loc_18000B4BF
0x18000b30d  mov     rdx, [rbx+10h]
0x18000b311  mov     rcx, [rbx+40h]
0x18000b315  add     rcx, rdx
0x18000b318  mov     eax, ebp
0x18000b31a  cmp     rax, rcx
0x18000b31d  jb      loc_18000B196
0x18000b323  mov     r8, r14; unsigned __int16 *
0x18000b326  mov     edx, 400h; unsigned __int64
0x18000b32b  mov     rcx, rsi; unsigned __int16 *
0x18000b32e  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b333  mov     edi, eax
0x18000b335  test    eax, eax
0x18000b337  js      loc_18000B4BF
0x18000b33d  mov     rcx, rsi
0x18000b340  call    AslStringUpper
0x18000b345  mov     rcx, rsi
0x18000b348  jmp     short loc_18000B38A
0x18000b34a  lea     rcx, [rax+0Eh]
0x18000b34e  movzx   edx, word ptr [rcx]
0x18000b351  test    dx, dx
0x18000b354  jz      short loc_18000B38A
0x18000b356  mov     rax, rcx
0x18000b359  sub     rax, rsi
0x18000b35c  sar     rax, 1
0x18000b35f  lea     rdi, [r14+rax*2]
0x18000b363  cmp     dx, 5Ch ; '\'
0x18000b367  jz      short loc_18000B38A
0x18000b369  lea     rax, [r14+800h]
0x18000b370  cmp     rdi, rax
0x18000b373  jnb     short loc_18000B38A
0x18000b375  add     rcx, 2; Str
0x18000b379  mov     word ptr [rdi], 78h ; 'x'
0x18000b37e  add     rdi, 2
0x18000b382  movzx   edx, word ptr [rcx]
0x18000b385  test    dx, dx
0x18000b388  jnz     short loc_18000B363
0x18000b38a  lea     rdx, aUsers; "\\USERS\\"
0x18000b391  call    wcsstr_0
0x18000b396  test    rax, rax
0x18000b399  jnz     short loc_18000B34A
0x18000b39b  lea     r12d, [rax+40h]
0x18000b39f  mov     rcx, r14; Str
0x18000b3a2  mov     edx, r12d; Ch
0x18000b3a5  call    cs:__imp_wcschr
0x18000b3ab  mov     rbx, rax
0x18000b3ae  test    rax, rax
0x18000b3b1  jz      loc_18000B4BC
0x18000b3b7  lea     r13d, [r12-3Fh]
0x18000b3bc  cmp     [rbx], r15w
0x18000b3c0  jz      loc_18000B4B7
0x18000b3c6  lea     rdi, [rbx-2]
0x18000b3ca  mov     dword ptr [rsp+58h+arg_8], r15d
0x18000b3cf  mov     ebp, r15d
0x18000b3d2  jmp     short loc_18000B3EF
0x18000b3d4  lea     r8, [rsp+58h+arg_8]; int *
0x18000b3d9  xor     edx, edx; int
0x18000b3db  movzx   ecx, ax; unsigned __int16
0x18000b3de  call    ?PiipIsInvalidEmailCharacter@@YAHGHAEAH@Z; PiipIsInvalidEmailCharacter(ushort,int,int &)
0x18000b3e3  test    eax, eax
0x18000b3e5  jnz     short loc_18000B3FB
0x18000b3e7  cmp     word ptr [rbx], 2Eh ; '.'
0x18000b3eb  cmovz   ebp, r13d
0x18000b3ef  add     rbx, 2
0x18000b3f3  movzx   eax, word ptr [rbx]
0x18000b3f6  test    ax, ax
0x18000b3f9  jnz     short loc_18000B3D4
0x18000b3fb  movzx   ecx, word ptr [rbx]; C
0x18000b3fe  call    cs:__imp_iswspace
0x18000b404  test    eax, eax
0x18000b406  jnz     short loc_18000B417
0x18000b408  cmp     [rbx], r15w
0x18000b40c  jz      short loc_18000B417
0x18000b40e  cmp     word ptr [rbx], 3Eh ; '>'
0x18000b412  mov     eax, r15d
0x18000b415  jnz     short loc_18000B41C
0x18000b417  mov     eax, 1
0x18000b41c  test    ebp, ebp
0x18000b41e  jz      short loc_18000B499
0x18000b420  test    eax, eax
0x18000b422  jz      short loc_18000B499
0x18000b424  sub     rbx, 2
0x18000b428  mov     dword ptr [rsp+58h+arg_8], r15d
0x18000b42d  jmp     short loc_18000B449
0x18000b42f  movzx   ecx, word ptr [rdi]; unsigned __int16
0x18000b432  lea     r8, [rsp+58h+arg_8]; int *
0x18000b437  mov     edx, 1; int
0x18000b43c  call    ?PiipIsInvalidEmailCharacter@@YAHGHAEAH@Z; PiipIsInvalidEmailCharacter(ushort,int,int &)
0x18000b441  test    eax, eax
0x18000b443  jnz     short loc_18000B450
0x18000b445  sub     rdi, 2
0x18000b449  cmp     rdi, r14
0x18000b44c  jnb     short loc_18000B42F
0x18000b44e  jmp     short loc_18000B463
0x18000b450  cmp     word ptr [rdi], 3Ch ; '<'
0x18000b454  jz      short loc_18000B463
0x18000b456  movzx   ecx, word ptr [rdi]; C
0x18000b459  call    cs:__imp_iswspace
0x18000b45f  test    eax, eax
0x18000b461  jz      short loc_18000B499
0x18000b463  mov     r13d, 1
0x18000b469  cmp     dword ptr [rsp+58h+arg_8], r15d
0x18000b46e  jnz     short loc_18000B49F
0x18000b470  add     rdi, 2
0x18000b474  mov     rcx, rbx
0x18000b477  sub     rcx, rdi
0x18000b47a  add     rcx, 2
0x18000b47e  shr     rcx, 1
0x18000b481  cmp     rdi, rbx
0x18000b484  cmova   rcx, r15
0x18000b488  cmp     rcx, r13
0x18000b48b  jb      short loc_18000B49F
0x18000b48d  lea     eax, [r13+22h]
0x18000b491  movzx   eax, ax
0x18000b494  rep stosw
0x18000b497  jmp     short loc_18000B49F
0x18000b499  mov     r13d, 1
0x18000b49f  mov     edx, r12d; Ch
0x18000b4a2  mov     rcx, rbx; Str
0x18000b4a5  call    cs:__imp_wcschr
0x18000b4ab  mov     rbx, rax
0x18000b4ae  test    rax, rax
0x18000b4b1  jnz     loc_18000B3BC
0x18000b4b7  mov     r13, [rsp+58h+arg_10]
0x18000b4bc  mov     edi, r15d
0x18000b4bf  mov     rcx, gs:60h
0x18000b4c8  mov     rdx, r13
0x18000b4cb  mov     rcx, [rcx+30h]
0x18000b4cf  call    AslFree
0x18000b4d4  test    rsi, rsi
0x18000b4d7  jz      short loc_18000B4EE
0x18000b4d9  mov     rcx, gs:60h
0x18000b4e2  mov     rdx, rsi
0x18000b4e5  mov     rcx, [rcx+30h]
0x18000b4e9  call    AslFree
0x18000b4ee  mov     rbx, [rsp+58h+arg_0]
0x18000b4f3  mov     eax, edi
0x18000b4f5  add     rsp, 20h
0x18000b4f9  pop     r15
0x18000b4fb  pop     r14
0x18000b4fd  pop     r13
0x18000b4ff  pop     r12
0x18000b501  pop     rdi
0x18000b502  pop     rsi
0x18000b503  pop     rbp
0x18000b504  retn
  ... truncated ...
```
