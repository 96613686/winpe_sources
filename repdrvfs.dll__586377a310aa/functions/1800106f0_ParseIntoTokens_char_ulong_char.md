# ParseIntoTokens(char *,ulong *,char * * *)

- ea: `0x1800106f0`
- end: `0x1800109c8`
- name: `?ParseIntoTokens@@YAKPEADPEAKPEAPEAPEAD@Z`
- size: `728`
- prototype: `unsigned int __fastcall(char *, unsigned int *, char ***)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800109d0`

## callees

- `0x1800012b8`
- `0x18000fcf0`
- `0x1800106f0`
- `0x180010fa0`
- `0x18002b7b6`
- `0x1800443df`
- `0x180044420`

## import_xrefs

- `wbemcomn!?GetArenaHeap@CWin32DefaultArena@@SAPEAXXZ` at `0x180010768`
- `wbemcomn!?GetArenaHeap@CWin32DefaultArena@@SAPEAXXZ` at `0x1800107e6`
- `wbemcomn!?GetArenaHeap@CWin32DefaultArena@@SAPEAXXZ` at `0x180010768`
- `wbemcomn!?GetArenaHeap@CWin32DefaultArena@@SAPEAXXZ` at `0x1800107e6`
- `wbemcomn!GetMemLogObject` at `0x1800108fa`
- `wbemcomn!GetMemLogObject` at `0x180010970`
- `wbemcomn!GetMemLogObject` at `0x1800108fa`
- `wbemcomn!GetMemLogObject` at `0x180010970`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180010906`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001097e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180010906`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001097e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001077d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800107f5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001077d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800107f5`

## pseudocode

```c
__int64 __fastcall ParseIntoTokens(char *a1, unsigned int *a2, char ***a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rax
  bool v9; // zf
  unsigned int v10; // ebx
  void *ArenaHeap; // rax
  unsigned int v12; // r14d
  unsigned __int8 *v13; // rax
  __int64 v14; // rdx
  unsigned __int8 *v15; // rbx
  unsigned __int8 *v16; // rcx
  __int64 v17; // rbp
  unsigned __int8 v18; // al
  __int64 v19; // rax
  SIZE_T v20; // rsi
  void *v21; // rax
  _BYTE *v22; // rax
  _BYTE *v23; // r9
  __int64 v24; // rax
  unsigned __int8 *v25; // r8
  _BYTE *v26; // rcx
  char **v27; // rax
  char **v28; // rsi
  __int64 v30; // rdi
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v32; // rax
  _QWORD Src[32]; // [rsp+20h] [rbp-148h] BYREF

  memset_0(Src, 0, sizeof(Src));
  v8 = -1;
  do
    v9 = a1[++v8] == 0;
  while ( !v9 );
  if ( a1 && *a1 )
  {
    _InterlockedIncrement(&g_lAllocs);
    v10 = v8 + 1;
    ArenaHeap = (void *)CWin32DefaultArena::GetArenaHeap(v7, v6);
    v12 = 8;
    v13 = (unsigned __int8 *)HeapAlloc(ArenaHeap, 8u, v10);
    v15 = v13;
    if ( v13 )
    {
      v16 = v13;
      v17 = 0;
      while ( 1 )
      {
        v18 = *a1;
        *v16 = *a1;
        if ( v18 == 92 || !v18 )
        {
          *v16 = 0;
          v19 = -1;
          do
            v9 = v15[++v19] == 0;
          while ( !v9 );
          v20 = v19 + 1;
          _InterlockedIncrement(&g_lAllocs);
          v21 = (void *)CWin32DefaultArena::GetArenaHeap(v16, v14);
          v22 = HeapAlloc(v21, 8u, v20);
          v23 = v22;
          if ( !v22 )
            goto LABEL_28;
          if ( (_DWORD)v17 == 32 )
          {
            _BtrMemFree(v22);
            v30 = 0;
            v12 = 13;
            goto LABEL_36;
          }
          if ( v20 )
          {
            if ( v20 <= 0x7FFFFFFF )
            {
              v24 = 2147483646;
              v25 = v15;
              v26 = v23;
              do
              {
                if ( !v24 )
                  break;
                v14 = *v25;
                if ( !(_BYTE)v14 )
                  break;
                *v26 = v14;
                ++v25;
                ++v26;
                --v24;
                --v20;
              }
              while ( v20 );
              v22 = v26 - 1;
              if ( v20 )
                v22 = v26;
            }
            *v22 = 0;
          }
          Src[v17] = v23;
          v16 = v15 - 1;
          v17 = (unsigned int)(v17 + 1);
        }
        if ( !*a1 )
          break;
        ++v16;
        ++a1;
      }
      v27 = (char **)_BtrMemAlloc(8LL * (unsigned int)v17);
      v28 = v27;
      if ( v27 )
      {
        memcpy_0(v27, Src, 8LL * (unsigned int)v17);
        *a2 = v17;
        *a3 = v28;
        _BtrMemFree(v15);
        return 0;
      }
LABEL_28:
      v30 = 0;
      if ( !(_DWORD)v17 )
        goto LABEL_29;
      do
      {
LABEL_36:
        _BtrMemFree((void *)Src[v30]);
        v30 = (unsigned int)(v30 + 1);
      }
      while ( (unsigned int)v30 < (unsigned int)v17 );
LABEL_29:
      *a2 = 0;
      _BtrMemFree(v15);
      return v12;
    }
    else
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, 8);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 8);
      }
      return 8;
    }
  }
  else
  {
    v32 = GetMemLogObject();
    CMemoryLog::Write(v32, 87);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 87);
    }
    return 87;
  }
}

```

## disassembly

```asm
0x1800106f0  push    rdi
0x1800106f2  push    r12
0x1800106f4  push    r15
0x1800106f6  sub     rsp, 150h
0x1800106fd  mov     rax, cs:__security_cookie
0x180010704  xor     rax, rsp
0x180010707  mov     [rsp+168h+var_48], rax
0x18001070f  mov     r12, r8
0x180010712  mov     r15, rdx
0x180010715  mov     rdi, rcx
0x180010718  xor     edx, edx; Val
0x18001071a  mov     r8d, 100h; Size
0x180010720  lea     rcx, [rsp+168h+Src]; void *
0x180010725  call    memset_0
0x18001072a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180010731  cmp     byte ptr [rdi+rax+1], 0
0x180010736  lea     rax, [rax+1]
0x18001073a  jnz     short loc_180010731
0x18001073c  test    rdi, rdi
0x18001073f  jz      loc_180010970
0x180010745  cmp     byte ptr [rdi], 0
0x180010748  jz      loc_180010970
0x18001074e  mov     [rsp+168h+var_20], rbx
0x180010756  mov     [rsp+168h+var_38], r14
0x18001075e  lock inc cs:?g_lAllocs@@3JA; long g_lAllocs
0x180010765  lea     ebx, [rax+1]
0x180010768  call    cs:__imp_?GetArenaHeap@CWin32DefaultArena@@SAPEAXXZ; CWin32DefaultArena::GetArenaHeap(void)
0x18001076e  mov     r14d, 8
0x180010774  mov     r8d, ebx; dwBytes
0x180010777  mov     rcx, rax; hHeap
0x18001077a  mov     edx, r14d; dwFlags
0x18001077d  call    cs:__imp_HeapAlloc
0x180010783  mov     rbx, rax
0x180010786  test    rax, rax
0x180010789  jz      loc_1800108FA
0x18001078f  mov     [rsp+168h+var_28], rbp
0x180010797  mov     rcx, rax
0x18001079a  mov     [rsp+168h+var_30], rsi
0x1800107a2  xor     ebp, ebp
0x1800107a4  movzx   eax, byte ptr [rdi]
0x1800107a7  mov     [rcx], al
0x1800107a9  cmp     al, 5Ch ; '\'
0x1800107ab  jz      short loc_1800107C2
0x1800107ad  test    al, al
0x1800107af  jz      short loc_1800107C2
0x1800107b1  cmp     byte ptr [rdi], 0
0x1800107b4  jz      loc_18001086C
0x1800107ba  inc     rcx
0x1800107bd  inc     rdi
0x1800107c0  jmp     short loc_1800107A4
0x1800107c2  mov     byte ptr [rcx], 0
0x1800107c5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800107cc  nop     dword ptr [rax+00h]
0x1800107d0  cmp     byte ptr [rbx+rax+1], 0
0x1800107d5  lea     rax, [rax+1]
0x1800107d9  jnz     short loc_1800107D0
0x1800107db  lea     rsi, [rax+1]
0x1800107df  lock inc cs:?g_lAllocs@@3JA; long g_lAllocs
0x1800107e6  call    cs:__imp_?GetArenaHeap@CWin32DefaultArena@@SAPEAXXZ; CWin32DefaultArena::GetArenaHeap(void)
0x1800107ec  mov     r8, rsi; dwBytes
0x1800107ef  mov     edx, r14d; dwFlags
0x1800107f2  mov     rcx, rax; hHeap
0x1800107f5  call    cs:__imp_HeapAlloc
0x1800107fb  mov     r9, rax
0x1800107fe  test    rax, rax
0x180010801  jz      loc_1800108E0
0x180010807  cmp     ebp, 20h ; ' '
0x18001080a  jz      loc_18001094B
0x180010810  test    rsi, rsi
0x180010813  jz      short loc_18001085C
0x180010815  cmp     rsi, 7FFFFFFFh
0x18001081c  ja      short loc_180010859
0x18001081e  mov     eax, 7FFFFFFEh
0x180010823  mov     r8, rbx
0x180010826  mov     rcx, r9
0x180010829  nop     dword ptr [rax+00000000h]
0x180010830  test    rax, rax
0x180010833  jz      short loc_18001084E
0x180010835  movzx   edx, byte ptr [r8]
0x180010839  test    dl, dl
0x18001083b  jz      short loc_18001084E
0x18001083d  mov     [rcx], dl
0x18001083f  inc     r8
0x180010842  inc     rcx
0x180010845  dec     rax
0x180010848  sub     rsi, 1
0x18001084c  jnz     short loc_180010830
0x18001084e  test    rsi, rsi
0x180010851  lea     rax, [rcx-1]
0x180010855  cmovnz  rax, rcx
0x180010859  mov     byte ptr [rax], 0
0x18001085c  mov     [rsp+rbp*8+168h+Src], r9
0x180010861  lea     rcx, [rbx-1]
0x180010865  inc     ebp
0x180010867  jmp     loc_1800107B1
0x18001086c  mov     edi, ebp
0x18001086e  shl     rdi, 3
0x180010872  mov     rcx, rdi; unsigned __int64
0x180010875  call    ?_BtrMemAlloc@@YAPEAX_K@Z; _BtrMemAlloc(unsigned __int64)
0x18001087a  mov     rsi, rax
0x18001087d  test    rax, rax
0x180010880  jz      short loc_1800108E0
0x180010882  mov     r8, rdi; Size
0x180010885  lea     rdx, [rsp+168h+Src]; Src
0x18001088a  mov     rcx, rax; void *
0x18001088d  call    memcpy_0
0x180010892  mov     [r15], ebp
0x180010895  mov     rcx, rbx; void *
0x180010898  mov     [r12], rsi
0x18001089c  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x1800108a1  xor     eax, eax
0x1800108a3  mov     rsi, [rsp+168h+var_30]
0x1800108ab  mov     rbp, [rsp+168h+var_28]
0x1800108b3  mov     rbx, [rsp+168h+var_20]
0x1800108bb  mov     r14, [rsp+168h+var_38]
0x1800108c3  mov     rcx, [rsp+168h+var_48]
0x1800108cb  xor     rcx, rsp; StackCookie
0x1800108ce  call    __security_check_cookie
0x1800108d3  add     rsp, 150h
0x1800108da  pop     r15
0x1800108dc  pop     r12
0x1800108de  pop     rdi
0x1800108df  retn
0x1800108e0  xor     edi, edi
0x1800108e2  test    ebp, ebp
0x1800108e4  jnz     short loc_18001095B
0x1800108e6  mov     rcx, rbx; void *
0x1800108e9  mov     dword ptr [r15], 0
0x1800108f0  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x1800108f5  mov     eax, r14d
0x1800108f8  jmp     short loc_1800108A3
0x1800108fa  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180010900  mov     rcx, rax
0x180010903  mov     edx, r14d
0x180010906  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001090c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010913  lea     rax, WPP_GLOBAL_Control
0x18001091a  cmp     rcx, rax
0x18001091d  jz      short loc_180010943
0x18001091f  test    byte ptr [rcx+1Ch], 1
0x180010923  jz      short loc_180010943
0x180010925  cmp     byte ptr [rcx+19h], 2
0x180010929  jb      short loc_180010943
0x18001092b  mov     rcx, [rcx+10h]
0x18001092f  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x180010936  mov     edx, 4Eh ; 'N'
0x18001093b  mov     r9d, r14d
0x18001093e  call    WPP_SF_d
0x180010943  mov     eax, r14d
0x180010946  jmp     loc_1800108B3
0x18001094b  mov     rcx, r9; void *
0x18001094e  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x180010953  xor     edi, edi
0x180010955  mov     r14d, 0Dh
0x18001095b  mov     rcx, [rsp+rdi*8+168h+Src]; void *
0x180010960  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x180010965  inc     edi
0x180010967  cmp     edi, ebp
0x180010969  jb      short loc_18001095B
0x18001096b  jmp     loc_1800108E6
0x180010970  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180010976  mov     rcx, rax
0x180010979  mov     edx, 57h ; 'W'
0x18001097e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180010984  mov     rcx, cs:WPP_GLOBAL_Control
0x18001098b  lea     rax, WPP_GLOBAL_Control
0x180010992  cmp     rcx, rax
0x180010995  jz      short loc_1800109BE
0x180010997  test    byte ptr [rcx+1Ch], 1
0x18001099b  jz      short loc_1800109BE
0x18001099d  cmp     byte ptr [rcx+19h], 2
0x1800109a1  jb      short loc_1800109BE
0x1800109a3  mov     rcx, [rcx+10h]
0x1800109a7  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x1800109ae  mov     edx, 4Dh ; 'M'
0x1800109b3  mov     r9d, 57h ; 'W'
0x1800109b9  call    WPP_SF_d
0x1800109be  mov     eax, 57h ; 'W'
0x1800109c3  jmp     loc_1800108C3
```
