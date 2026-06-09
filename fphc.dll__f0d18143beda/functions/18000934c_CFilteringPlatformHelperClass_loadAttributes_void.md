# CFilteringPlatformHelperClass::loadAttributes(void)

- ea: `0x18000934c`
- end: `0x1800095a2`
- name: `?loadAttributes@CFilteringPlatformHelperClass@@AEAAJXZ`
- size: `598`
- prototype: `__int64 __fastcall(CFilteringPlatformHelperClass *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008540`

## callees

- `0x18000934c`
- `0x18001131a`

## string_xrefs

- `0x180009389`: `protocol`
- `0x18000954f`: `serviceid`

## pseudocode

```c
__int64 __fastcall CFilteringPlatformHelperClass::loadAttributes(CFilteringPlatformHelperClass *this)
{
  __int64 v1; // rbp
  unsigned int v2; // r14d
  __int64 v4; // rdi
  const wchar_t *v5; // rcx
  __int64 v6; // rbp
  __int64 v7; // rdi
  const wchar_t *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rdi
  const wchar_t *v11; // rcx
  _WORD *v12; // rcx
  _WORD *v13; // rax
  __int64 v14; // rsi
  __int64 v15; // rbp
  const wchar_t *v16; // rcx
  __int64 v17; // rbp
  __int64 v18; // rdi
  __int64 v19; // rsi
  const wchar_t *v20; // rcx
  __int64 v21; // rdi
  __int64 v22; // rdi
  __int64 v23; // rsi
  const wchar_t *v24; // rcx
  __int64 v25; // rdi

  v1 = *((_QWORD *)this + 4);
  v2 = 0;
  if ( v1 )
  {
    v4 = 0;
    if ( *((_DWORD *)this + 6) )
    {
      while ( 1 )
      {
        v5 = *(const wchar_t **)(v1 + 144 * v4);
        if ( v5 )
        {
          if ( !wcsncmp_0(v5, L"protocol", 0xFFu) )
            break;
        }
        v4 = (unsigned int)(v4 + 1);
        if ( (unsigned int)v4 >= *((_DWORD *)this + 6) )
          goto LABEL_8;
      }
      *((_BYTE *)this + 128) = *(_BYTE *)(v1 + 144 * v4 + 16);
      *((_QWORD *)this + 15) = (char *)this + 128;
    }
  }
LABEL_8:
  v6 = *((_QWORD *)this + 4);
  if ( v6 )
  {
    v7 = 0;
    if ( *((_DWORD *)this + 6) )
    {
      while ( 1 )
      {
        v8 = *(const wchar_t **)(144 * v7 + v6);
        if ( v8 )
        {
          if ( !wcsncmp_0(v8, L"localaddr", 0xFFu) )
            break;
        }
        v7 = (unsigned int)(v7 + 1);
        if ( (unsigned int)v7 >= *((_DWORD *)this + 6) )
          goto LABEL_15;
      }
      v9 = 144 * v7 + v6 + 16;
      *((_QWORD *)this + 17) = v9;
      *((_QWORD *)this + 52) = v9;
    }
LABEL_15:
    v10 = 0;
    if ( *((_DWORD *)this + 6) )
    {
      while ( 1 )
      {
        v11 = *(const wchar_t **)(144 * v10 + v6);
        if ( v11 )
        {
          if ( !wcsncmp_0(v11, L"remoteaddr", 0xFFu) )
            break;
        }
        v10 = (unsigned int)(v10 + 1);
        if ( (unsigned int)v10 >= *((_DWORD *)this + 6) )
          goto LABEL_24;
      }
      v12 = (_WORD *)*((_QWORD *)this + 52);
      v13 = (_WORD *)(144 * v10 + v6 + 16);
      *((_QWORD *)this + 18) = v13;
      if ( v12 )
      {
        if ( *v12 != *v13 )
          v2 = -2147024809;
      }
      else
      {
        *((_QWORD *)this + 52) = v13;
      }
    }
  }
LABEL_24:
  v14 = v6;
  if ( v6 )
  {
    v15 = 0;
    if ( *((_DWORD *)this + 6) )
    {
      while ( 1 )
      {
        v16 = *(const wchar_t **)(v14 + 144 * v15);
        if ( v16 )
        {
          if ( !wcsncmp_0(v16, L"userid", 0xFFu) )
            break;
        }
        v15 = (unsigned int)(v15 + 1);
        if ( (unsigned int)v15 >= *((_DWORD *)this + 6) )
          goto LABEL_32;
      }
      if ( *(_DWORD *)(v14 + 144 * v15 + 16) )
        *((_QWORD *)this + 51) = *(_QWORD *)(v14 + 144 * v15 + 24);
    }
  }
LABEL_32:
  v17 = v14;
  if ( v14 )
  {
    v18 = 0;
    if ( *((_DWORD *)this + 6) )
    {
      while ( 1 )
      {
        v19 = 18 * v18;
        v20 = *(const wchar_t **)(v17 + 144 * v18);
        if ( v20 )
        {
          if ( !wcsncmp_0(v20, L"appid", 0xFFu) )
            break;
        }
        v18 = (unsigned int)(v18 + 1);
        if ( (unsigned int)v18 >= *((_DWORD *)this + 6) )
          goto LABEL_41;
      }
      v21 = *(_QWORD *)(v17 + 144 * v18 + 16);
      if ( v21 && wcsncmp_0(*(const wchar_t **)(v17 + 8 * v19 + 16), &word_1800164D8, 1u) )
        *((_QWORD *)this + 53) = v21;
    }
  }
LABEL_41:
  if ( v17 )
  {
    v22 = 0;
    if ( *((_DWORD *)this + 6) )
    {
      while ( 1 )
      {
        v23 = 18 * v22;
        v24 = *(const wchar_t **)(v17 + 144 * v22);
        if ( v24 )
        {
          if ( !wcsncmp_0(v24, L"serviceid", 0xFFu) )
            break;
        }
        v22 = (unsigned int)(v22 + 1);
        if ( (unsigned int)v22 >= *((_DWORD *)this + 6) )
          return v2;
      }
      v25 = *(_QWORD *)(v17 + 144 * v22 + 16);
      if ( v25 && wcsncmp_0(*(const wchar_t **)(v17 + 8 * v23 + 16), &word_1800164D8, 1u) )
        *((_QWORD *)this + 54) = v25;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000934c  push    rbx
0x18000934e  push    rbp
0x18000934f  push    rsi
0x180009350  push    rdi
0x180009351  push    r13
0x180009353  push    r14
0x180009355  sub     rsp, 28h
0x180009359  mov     rbp, [rcx+20h]
0x18000935d  xor     r14d, r14d
0x180009360  mov     rbx, rcx
0x180009363  mov     r13d, 0FFh
0x180009369  test    rbp, rbp
0x18000936c  jz      short loc_1800093B3
0x18000936e  xor     edi, edi
0x180009370  cmp     [rcx+18h], edi
0x180009373  jbe     short loc_1800093B3
0x180009375  lea     rsi, [rdi+rdi*8]
0x180009379  add     rsi, rsi
0x18000937c  mov     rcx, [rbp+rsi*8+0]; String1
0x180009381  test    rcx, rcx
0x180009384  jz      short loc_180009399
0x180009386  mov     r8d, r13d; MaxCount
0x180009389  lea     rdx, aProtocol; "protocol"
0x180009390  call    wcsncmp_0
0x180009395  test    eax, eax
0x180009397  jz      short loc_1800093A2
0x180009399  inc     edi
0x18000939b  cmp     edi, [rbx+18h]
0x18000939e  jb      short loc_180009375
0x1800093a0  jmp     short loc_1800093B3
0x1800093a2  mov     al, [rbp+rsi*8+10h]
0x1800093a6  lea     rcx, [rbx+80h]
0x1800093ad  mov     [rcx], al
0x1800093af  mov     [rbx+78h], rcx
0x1800093b3  mov     rbp, [rbx+20h]
0x1800093b7  test    rbp, rbp
0x1800093ba  jz      loc_180009474
0x1800093c0  xor     edi, edi
0x1800093c2  cmp     [rbx+18h], edi
0x1800093c5  jbe     short loc_180009409
0x1800093c7  lea     rsi, [rdi+rdi*8]
0x1800093cb  shl     rsi, 4
0x1800093cf  mov     rcx, [rsi+rbp]; String1
0x1800093d3  test    rcx, rcx
0x1800093d6  jz      short loc_1800093EB
0x1800093d8  mov     r8d, r13d; MaxCount
0x1800093db  lea     rdx, aLocaladdr; "localaddr"
0x1800093e2  call    wcsncmp_0
0x1800093e7  test    eax, eax
0x1800093e9  jz      short loc_1800093F4
0x1800093eb  inc     edi
0x1800093ed  cmp     edi, [rbx+18h]
0x1800093f0  jb      short loc_1800093C7
0x1800093f2  jmp     short loc_180009409
0x1800093f4  lea     rax, [rbp+10h]
0x1800093f8  add     rax, rsi
0x1800093fb  mov     [rbx+88h], rax
0x180009402  mov     [rbx+1A0h], rax
0x180009409  test    rbp, rbp
0x18000940c  jz      short loc_180009474
0x18000940e  xor     edi, edi
0x180009410  cmp     [rbx+18h], edi
0x180009413  jbe     short loc_180009474
0x180009415  lea     rsi, [rdi+rdi*8]
0x180009419  shl     rsi, 4
0x18000941d  mov     rcx, [rsi+rbp]; String1
0x180009421  test    rcx, rcx
0x180009424  jz      short loc_180009439
0x180009426  mov     r8d, r13d; MaxCount
0x180009429  lea     rdx, aRemoteaddr; "remoteaddr"
0x180009430  call    wcsncmp_0
0x180009435  test    eax, eax
0x180009437  jz      short loc_180009442
0x180009439  inc     edi
0x18000943b  cmp     edi, [rbx+18h]
0x18000943e  jb      short loc_180009415
0x180009440  jmp     short loc_180009474
0x180009442  mov     rcx, [rbx+1A0h]
0x180009449  lea     rax, [rbp+10h]
0x18000944d  add     rax, rsi
0x180009450  mov     [rbx+90h], rax
0x180009457  test    rcx, rcx
0x18000945a  jnz     short loc_180009465
0x18000945c  mov     [rbx+1A0h], rax
0x180009463  jmp     short loc_180009474
0x180009465  movzx   eax, word ptr [rax]
0x180009468  mov     edx, 80070057h
0x18000946d  cmp     [rcx], ax
0x180009470  cmovnz  r14d, edx
0x180009474  mov     rsi, rbp
0x180009477  test    rbp, rbp
0x18000947a  jz      short loc_1800094C9
0x18000947c  xor     ebp, ebp
0x18000947e  cmp     [rbx+18h], ebp
0x180009481  jbe     short loc_1800094C9
0x180009483  lea     rdi, ds:0[rbp*8]
0x18000948b  add     rdi, rbp
0x18000948e  add     rdi, rdi
0x180009491  mov     rcx, [rsi+rdi*8]; String1
0x180009495  test    rcx, rcx
0x180009498  jz      short loc_1800094AD
0x18000949a  mov     r8d, r13d; MaxCount
0x18000949d  lea     rdx, aUserid; "userid"
0x1800094a4  call    wcsncmp_0
0x1800094a9  test    eax, eax
0x1800094ab  jz      short loc_1800094B6
0x1800094ad  inc     ebp
0x1800094af  cmp     ebp, [rbx+18h]
0x1800094b2  jb      short loc_180009483
0x1800094b4  jmp     short loc_1800094C9
0x1800094b6  cmp     dword ptr [rsi+rdi*8+10h], 0
0x1800094bb  jz      short loc_1800094C9
0x1800094bd  mov     rax, [rsi+rdi*8+18h]
0x1800094c2  mov     [rbx+198h], rax
0x1800094c9  mov     rbp, rsi
0x1800094cc  test    rsi, rsi
0x1800094cf  jz      short loc_18000952F
0x1800094d1  xor     edi, edi
0x1800094d3  cmp     [rbx+18h], edi
0x1800094d6  jbe     short loc_18000952F
0x1800094d8  lea     rsi, [rdi+rdi*8]
0x1800094dc  add     rsi, rsi
0x1800094df  mov     rcx, [rbp+rsi*8+0]; String1
0x1800094e4  test    rcx, rcx
0x1800094e7  jz      short loc_1800094FC
0x1800094e9  mov     r8d, r13d; MaxCount
0x1800094ec  lea     rdx, aAppid; "appid"
0x1800094f3  call    wcsncmp_0
0x1800094f8  test    eax, eax
0x1800094fa  jz      short loc_180009505
0x1800094fc  inc     edi
0x1800094fe  cmp     edi, [rbx+18h]
0x180009501  jb      short loc_1800094D8
0x180009503  jmp     short loc_18000952F
0x180009505  mov     rdi, [rbp+rsi*8+10h]
0x18000950a  test    rdi, rdi
0x18000950d  jz      short loc_18000952F
0x18000950f  mov     r8d, 1; MaxCount
0x180009515  lea     rdx, word_1800164D8; String2
0x18000951c  mov     rcx, rdi; String1
0x18000951f  call    wcsncmp_0
0x180009524  test    eax, eax
0x180009526  jz      short loc_18000952F
0x180009528  mov     [rbx+1A8h], rdi
0x18000952f  test    rbp, rbp
0x180009532  jz      short loc_180009592
0x180009534  xor     edi, edi
0x180009536  cmp     [rbx+18h], edi
0x180009539  jbe     short loc_180009592
0x18000953b  lea     rsi, [rdi+rdi*8]
0x18000953f  add     rsi, rsi
0x180009542  mov     rcx, [rbp+rsi*8+0]; String1
0x180009547  test    rcx, rcx
0x18000954a  jz      short loc_18000955F
0x18000954c  mov     r8d, r13d; MaxCount
0x18000954f  lea     rdx, aServiceid; "serviceid"
0x180009556  call    wcsncmp_0
0x18000955b  test    eax, eax
0x18000955d  jz      short loc_180009568
0x18000955f  inc     edi
0x180009561  cmp     edi, [rbx+18h]
0x180009564  jb      short loc_18000953B
0x180009566  jmp     short loc_180009592
0x180009568  mov     rdi, [rbp+rsi*8+10h]
0x18000956d  test    rdi, rdi
0x180009570  jz      short loc_180009592
0x180009572  mov     r8d, 1; MaxCount
0x180009578  lea     rdx, word_1800164D8; String2
0x18000957f  mov     rcx, rdi; String1
0x180009582  call    wcsncmp_0
0x180009587  test    eax, eax
0x180009589  jz      short loc_180009592
0x18000958b  mov     [rbx+1B0h], rdi
0x180009592  mov     eax, r14d
0x180009595  add     rsp, 28h
0x180009599  pop     r14
0x18000959b  pop     r13
0x18000959d  pop     rdi
0x18000959e  pop     rsi
0x18000959f  pop     rbp
0x1800095a0  pop     rbx
0x1800095a1  retn
```
