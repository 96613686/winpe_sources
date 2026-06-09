# getservent

- ea: `0x180001ad4`
- end: `0x180001e4b`
- name: `getservent`
- size: `887`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800018b0`
- `0x180001998`

## callees

- `0x180001ad4`
- `0x180036ccc`
- `0x180038634`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_atoi` at `0x180001c15`
- `api-ms-win-crt-private-l1-1-0!_o_atoi` at `0x180001c15`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001ae3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001b08`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001b25`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001b85`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001c29`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001c55`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001c72`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001c8f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001cef`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001d19`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001d7a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001d90`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001dd9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001dfd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001e23`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001ae3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001b08`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001b25`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001b85`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001c29`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001c55`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001c72`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001c8f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001cef`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001d19`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001d7a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001d90`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001dd9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001dfd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001e23`
- `WS2_32!__imp_htons` at `0x180001c3c`
- `WS2_32!__imp_htons` at `0x180001c3c`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180001dc0`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180001dc0`

## pseudocode

```c
__int64 getservent()
{
  void *v0; // rbx
  _QWORD *Value; // rax
  __int64 v2; // rdx
  char *v3; // rax
  char *v4; // rbx
  char v5; // cl
  const char *i; // rdx
  DWORD v7; // ecx
  const char *j; // rax
  const char *k; // rcx
  char v10; // al
  const char *v11; // rsi
  const char *m; // rdx
  _BYTE *v13; // rsi
  u_short v14; // di
  __int64 v15; // rbx
  u_short v16; // ax
  DWORD v17; // ecx
  char **v18; // rdi
  const char *n; // rax
  char *v20; // rbx
  char v21; // al
  DWORD v22; // ecx
  const char *ii; // rax
  const CHAR *v25; // rdi
  __int64 v26; // rbx
  HANDLE FileA; // rax
  DWORD v28; // ecx
  _QWORD *v29; // rax
  __int64 v30; // rcx

  if ( *(_QWORD *)(*((_QWORD *)TlsGetValue(MSAFD_SockTlsSlot) + 9) + 272LL)
    || (v25 = (const CHAR *)*((_QWORD *)TlsGetValue(MSAFD_SockTlsSlot) + 9),
        v26 = *((_QWORD *)TlsGetValue(MSAFD_SockTlsSlot) + 9),
        FileA = CreateFileA(v25, 0x80000000, 1u, 0, 3u, 0, 0),
        v28 = MSAFD_SockTlsSlot,
        *(_QWORD *)(v26 + 272) = FileA,
        *(_QWORD *)(*((_QWORD *)TlsGetValue(v28) + 9) + 272LL) != -1) )
  {
    while ( 1 )
    {
      v0 = *(void **)(*((_QWORD *)TlsGetValue(MSAFD_SockTlsSlot) + 9) + 272LL);
      Value = TlsGetValue(MSAFD_SockTlsSlot);
      v3 = hgets((char *)(Value[9] + 280LL), v2, v0);
      v4 = v3;
      if ( !v3 )
        break;
      v5 = *v3;
      if ( *v3 != 35 )
      {
LABEL_4:
        if ( v5 )
        {
          for ( i = "#\n"; ; ++i )
          {
            if ( !*i )
            {
              v5 = *++v3;
              goto LABEL_4;
            }
            if ( *i == v5 )
              break;
          }
          if ( v3 )
          {
            v7 = MSAFD_SockTlsSlot;
            *v3 = 0;
            *(_QWORD *)(*((_QWORD *)TlsGetValue(v7) + 9) + 800LL) = v4;
LABEL_12:
            if ( *v4 )
            {
              for ( j = " \t"; ; ++j )
              {
                if ( !*j )
                {
                  ++v4;
                  goto LABEL_12;
                }
                if ( *j == *v4 )
                  break;
              }
              if ( v4 )
              {
                *v4 = 0;
                for ( k = v4 + 1; ; ++k )
                {
                  v10 = *k;
                  if ( *k != 32 && v10 != 9 )
                    break;
                }
                v11 = k;
LABEL_24:
                if ( v10 )
                {
                  for ( m = ",/"; ; ++m )
                  {
                    if ( !*m )
                    {
                      v10 = *++v11;
                      goto LABEL_24;
                    }
                    if ( *m == v10 )
                      break;
                  }
                  if ( v11 )
                  {
                    *v11 = 0;
                    v13 = v11 + 1;
                    v14 = atoi(k);
                    v15 = *((_QWORD *)TlsGetValue(MSAFD_SockTlsSlot) + 9);
                    v16 = htons(v14);
                    v17 = MSAFD_SockTlsSlot;
                    *(_WORD *)(v15 + 824) = v16;
                    *(_QWORD *)(*((_QWORD *)TlsGetValue(v17) + 9) + 816LL) = v13;
                    v18 = (char **)(*((_QWORD *)TlsGetValue(MSAFD_SockTlsSlot) + 9) + 832LL);
                    *(_QWORD *)(*((_QWORD *)TlsGetValue(MSAFD_SockTlsSlot) + 9) + 808LL) = v18;
LABEL_32:
                    if ( *v13 )
                    {
                      for ( n = " \t"; ; ++n )
                      {
                        if ( !*n )
                        {
                          ++v13;
                          goto LABEL_32;
                        }
                        if ( *n == *v13 )
                          break;
                      }
                      if ( v13 )
                      {
                        *v13 = 0;
                        v20 = v13 + 1;
                        while ( v20 )
                        {
                          v21 = *v20;
                          if ( !*v20 )
                            break;
                          if ( v21 == 32 || v21 == 9 )
                          {
                            ++v20;
                          }
                          else
                          {
                            if ( (unsigned __int64)v18 < *((_QWORD *)TlsGetValue(MSAFD_SockTlsSlot) + 9) + 1104LL )
                              *v18++ = v20;
LABEL_48:
                            if ( !*v20 )
                              goto LABEL_56;
                            for ( ii = " \t"; ; ++ii )
                            {
                              if ( !*ii )
                              {
                                ++v20;
                                goto LABEL_48;
                              }
                              if ( *ii == *v20 )
                                break;
                            }
                            if ( v20 )
                              *v20++ = 0;
                            else
LABEL_56:
                              v20 = 0;
                          }
                        }
                      }
                    }
                    v22 = MSAFD_SockTlsSlot;
                    *v18 = 0;
                    return *((_QWORD *)TlsGetValue(v22) + 9) + 800LL;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    *(_QWORD *)(*((_QWORD *)TlsGetValue(MSAFD_SockTlsSlot) + 9) + 272LL) = 0;
    if ( (xmmword_180063D60 & 2) != 0 )
    {
      v29 = TlsGetValue(MSAFD_SockTlsSlot);
      WPP_SF_s(v30, 10, WPP_140e359e2f3630e34e43524af0f82847_Traceguids, v29[9]);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180001ad4  push    rbx
0x180001ad6  push    rbp
0x180001ad7  push    rsi
0x180001ad8  push    rdi
0x180001ad9  sub     rsp, 48h
0x180001add  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180001ae3  call    cs:__imp_TlsGetValue
0x180001aea  nop     dword ptr [rax+rax+00h]
0x180001aef  xor     ebp, ebp
0x180001af1  mov     rcx, [rax+48h]
0x180001af5  cmp     [rcx+110h], rbp
0x180001afc  jz      loc_180001D74
0x180001b02  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180001b08  call    cs:__imp_TlsGetValue
0x180001b0f  nop     dword ptr [rax+rax+00h]
0x180001b14  mov     rcx, [rax+48h]
0x180001b18  mov     rbx, [rcx+110h]
0x180001b1f  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180001b25  call    cs:__imp_TlsGetValue
0x180001b2c  nop     dword ptr [rax+rax+00h]
0x180001b31  mov     r8, rbx
0x180001b34  mov     rcx, [rax+48h]
0x180001b38  add     rcx, 118h; lpBuffer
0x180001b3f  call    hgets
0x180001b44  mov     rbx, rax
0x180001b47  test    rax, rax
0x180001b4a  jz      loc_180001E44
0x180001b50  mov     cl, [rax]
0x180001b52  cmp     cl, 23h ; '#'
0x180001b55  jz      short loc_180001B02
0x180001b57  test    cl, cl
0x180001b59  jz      short loc_180001B02
0x180001b5b  lea     rdx, asc_180055148; "#\n"
0x180001b62  cmp     [rdx], bpl
0x180001b65  jz      short loc_180001B70
0x180001b67  cmp     [rdx], cl
0x180001b69  jz      short loc_180001B77
0x180001b6b  inc     rdx
0x180001b6e  jmp     short loc_180001B62
0x180001b70  inc     rax
0x180001b73  mov     cl, [rax]
0x180001b75  jmp     short loc_180001B57
0x180001b77  test    rax, rax
0x180001b7a  jz      short loc_180001B02
0x180001b7c  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180001b82  mov     [rax], bpl
0x180001b85  call    cs:__imp_TlsGetValue
0x180001b8c  nop     dword ptr [rax+rax+00h]
0x180001b91  mov     rcx, [rax+48h]
0x180001b95  mov     [rcx+320h], rbx
0x180001b9c  mov     cl, [rbx]
0x180001b9e  test    cl, cl
0x180001ba0  jz      loc_180001B02
0x180001ba6  lea     rax, asc_180055144; " \t"
0x180001bad  cmp     [rax], bpl
0x180001bb0  jz      short loc_180001BBB
0x180001bb2  cmp     [rax], cl
0x180001bb4  jz      short loc_180001BC0
0x180001bb6  inc     rax
0x180001bb9  jmp     short loc_180001BAD
0x180001bbb  inc     rbx
0x180001bbe  jmp     short loc_180001B9C
0x180001bc0  test    rbx, rbx
0x180001bc3  jz      loc_180001B02
0x180001bc9  mov     [rbx], bpl
0x180001bcc  lea     rcx, [rbx+1]; String
0x180001bd0  mov     al, [rcx]
0x180001bd2  cmp     al, 20h ; ' '
0x180001bd4  jnz     short loc_180001BDB
0x180001bd6  inc     rcx
0x180001bd9  jmp     short loc_180001BD0
0x180001bdb  cmp     al, 9
0x180001bdd  jz      short loc_180001BD6
0x180001bdf  mov     rsi, rcx
0x180001be2  test    al, al
0x180001be4  jz      loc_180001B02
0x180001bea  lea     rdx, asc_18005514C; ",/"
0x180001bf1  cmp     [rdx], bpl
0x180001bf4  jz      short loc_180001BFF
0x180001bf6  cmp     [rdx], al
0x180001bf8  jz      short loc_180001C06
0x180001bfa  inc     rdx
0x180001bfd  jmp     short loc_180001BF1
0x180001bff  inc     rsi
0x180001c02  mov     al, [rsi]
0x180001c04  jmp     short loc_180001BE2
0x180001c06  test    rsi, rsi
0x180001c09  jz      loc_180001B02
0x180001c0f  mov     [rsi], bpl
0x180001c12  inc     rsi
0x180001c15  call    cs:__imp_atoi
0x180001c1c  nop     dword ptr [rax+rax+00h]
0x180001c21  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180001c27  mov     edi, eax
0x180001c29  call    cs:__imp_TlsGetValue
0x180001c30  nop     dword ptr [rax+rax+00h]
0x180001c35  movzx   ecx, di; hostshort
0x180001c38  mov     rbx, [rax+48h]
0x180001c3c  call    cs:__imp_htons
0x180001c43  nop     dword ptr [rax+rax+00h]
0x180001c48  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180001c4e  mov     [rbx+338h], ax
0x180001c55  call    cs:__imp_TlsGetValue
0x180001c5c  nop     dword ptr [rax+rax+00h]
0x180001c61  mov     rcx, [rax+48h]
0x180001c65  mov     [rcx+330h], rsi
0x180001c6c  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180001c72  call    cs:__imp_TlsGetValue
0x180001c79  nop     dword ptr [rax+rax+00h]
0x180001c7e  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180001c84  mov     rdi, [rax+48h]
0x180001c88  add     rdi, 340h
0x180001c8f  call    cs:__imp_TlsGetValue
0x180001c96  nop     dword ptr [rax+rax+00h]
0x180001c9b  mov     rcx, [rax+48h]
0x180001c9f  mov     [rcx+328h], rdi
0x180001ca6  mov     cl, [rsi]
0x180001ca8  test    cl, cl
0x180001caa  jz      short loc_180001CE6
0x180001cac  lea     rax, asc_180055144; " \t"
0x180001cb3  cmp     [rax], bpl
0x180001cb6  jz      short loc_180001CC1
0x180001cb8  cmp     [rax], cl
0x180001cba  jz      short loc_180001CC6
0x180001cbc  inc     rax
0x180001cbf  jmp     short loc_180001CB3
0x180001cc1  inc     rsi
0x180001cc4  jmp     short loc_180001CA6
0x180001cc6  test    rsi, rsi
0x180001cc9  jz      short loc_180001CE6
0x180001ccb  mov     [rsi], bpl
0x180001cce  lea     rbx, [rsi+1]
0x180001cd2  test    rbx, rbx
0x180001cd5  jz      short loc_180001CE6
0x180001cd7  mov     al, [rbx]
0x180001cd9  test    al, al
0x180001cdb  jz      short loc_180001CE6
0x180001cdd  cmp     al, 20h ; ' '
0x180001cdf  jnz     short loc_180001D0F
0x180001ce1  inc     rbx
0x180001ce4  jmp     short loc_180001CD2
0x180001ce6  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180001cec  mov     [rdi], rbp
0x180001cef  call    cs:__imp_TlsGetValue
0x180001cf6  nop     dword ptr [rax+rax+00h]
0x180001cfb  mov     rax, [rax+48h]
0x180001cff  add     rax, 320h
0x180001d05  add     rsp, 48h
0x180001d09  pop     rdi
0x180001d0a  pop     rsi
0x180001d0b  pop     rbp
0x180001d0c  pop     rbx
0x180001d0d  retn
0x180001d0f  cmp     al, 9
0x180001d11  jz      short loc_180001CE1
0x180001d13  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180001d19  call    cs:__imp_TlsGetValue
0x180001d20  nop     dword ptr [rax+rax+00h]
0x180001d25  mov     rcx, [rax+48h]
0x180001d29  add     rcx, 450h
0x180001d30  cmp     rdi, rcx
0x180001d33  jnb     short loc_180001D3C
0x180001d35  mov     [rdi], rbx
0x180001d38  add     rdi, 8
0x180001d3c  mov     cl, [rbx]
0x180001d3e  test    cl, cl
0x180001d40  jz      short loc_180001D6C
0x180001d42  lea     rax, asc_180055144; " \t"
0x180001d49  cmp     [rax], bpl
0x180001d4c  jz      short loc_180001D57
0x180001d4e  cmp     [rax], cl
0x180001d50  jz      short loc_180001D5C
0x180001d52  inc     rax
0x180001d55  jmp     short loc_180001D49
0x180001d57  inc     rbx
0x180001d5a  jmp     short loc_180001D3C
0x180001d5c  test    rbx, rbx
0x180001d5f  jz      short loc_180001D6C
0x180001d61  mov     [rbx], bpl
0x180001d64  inc     rbx
0x180001d67  jmp     loc_180001CD2
0x180001d6c  mov     rbx, rbp
0x180001d6f  jmp     loc_180001CD2
0x180001d74  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180001d7a  call    cs:__imp_TlsGetValue
0x180001d81  nop     dword ptr [rax+rax+00h]
0x180001d86  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180001d8c  mov     rdi, [rax+48h]
0x180001d90  call    cs:__imp_TlsGetValue
0x180001d97  nop     dword ptr [rax+rax+00h]
0x180001d9c  xor     r9d, r9d; lpSecurityAttributes
0x180001d9f  mov     [rsp+68h+hTemplateFile], rbp; hTemplateFile
0x180001da4  mov     [rsp+68h+dwFlagsAndAttributes], ebp; dwFlagsAndAttributes
0x180001da8  mov     edx, 80000000h; dwDesiredAccess
0x180001dad  mov     rcx, rdi; lpFileName
0x180001db0  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180001db8  mov     rbx, [rax+48h]
0x180001dbc  lea     r8d, [r9+1]; dwShareMode
0x180001dc0  call    cs:__imp_CreateFileA
0x180001dc7  nop     dword ptr [rax+rax+00h]
0x180001dcc  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180001dd2  mov     [rbx+110h], rax
0x180001dd9  call    cs:__imp_TlsGetValue
0x180001de0  nop     dword ptr [rax+rax+00h]
0x180001de5  mov     rcx, [rax+48h]
0x180001de9  cmp     qword ptr [rcx+110h], 0FFFFFFFFFFFFFFFFh
0x180001df1  jnz     loc_180001B02
0x180001df7  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180001dfd  call    cs:__imp_TlsGetValue
0x180001e04  nop     dword ptr [rax+rax+00h]
0x180001e09  mov     rcx, [rax+48h]
0x180001e0d  mov     [rcx+110h], rbp
0x180001e14  test    byte ptr cs:xmmword_180063D60, 2
0x180001e1b  jz      short loc_180001E44
0x180001e1d  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180001e23  call    cs:__imp_TlsGetValue
0x180001e2a  nop     dword ptr [rax+rax+00h]
0x180001e2f  mov     edx, 0Ah
0x180001e34  lea     r8, WPP_140e359e2f3630e34e43524af0f82847_Traceguids
0x180001e3b  mov     r9, [rax+48h]
0x180001e3f  call    WPP_SF_s
0x180001e44  xor     eax, eax
0x180001e46  jmp     loc_180001D05
```
