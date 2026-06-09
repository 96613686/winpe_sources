# CEnumFmt10::InitFromRegDb(HKEY__ *)

- ea: `0x18009d140`
- end: `0x18009d3dd`
- name: `?InitFromRegDb@CEnumFmt10@@UEAAJPEAUHKEY__@@@Z`
- size: `669`
- prototype: `HRESULT __fastcall(CEnumFmt10 *this, HKEY__ *hkey)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009ce6c`

## callees

- `0x18000e924`
- `0x18009d140`
- `0x18009d998`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009d268`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009d268`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009d16b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009d17d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009d16b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009d17d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d19b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d3a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d3b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d19b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d3a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d3b1`

## string_xrefs

- `0x18009d1c8`: `Protocol\StdFileEditing\RequestDataFormats`
- `0x18009d20f`: `Protocol\StdFileEditing\SetDataFormats`

## pseudocode

```c
__int64 __fastcall CEnumFmt10::InitFromRegDb(CEnumFmt10 *this, HKEY__ *hkey)
{
  wchar_t *v4; // r14
  wchar_t *v5; // rax
  unsigned int v6; // ebx
  wchar_t *v7; // rsi
  __int64 v8; // rdi
  unsigned __int64 v9; // r15
  wchar_t *v10; // rcx
  wchar_t v12; // cx
  wchar_t *v13; // rdx
  bool v14; // zf
  __int64 v15; // rax
  wchar_t v16; // cx
  wchar_t *v17; // rdx
  __int64 v18; // rax
  FMT *v19; // rax
  wchar_t *v20; // rdi
  int v21; // ebp
  wchar_t v22; // ax
  wchar_t *v23; // rdx
  wchar_t v24; // cx
  wchar_t *v25; // rdi
  int v26; // ebp
  wchar_t v27; // ax
  wchar_t *v28; // rdx
  wchar_t v29; // cx
  unsigned __int16 v30; // dx
  unsigned __int64 v31; // rcx
  FMT *m_rgFmt; // rax
  unsigned int cb; // [rsp+60h] [rbp+18h] BYREF

  v4 = (wchar_t *)CoTaskMemAlloc(0x400u);
  v5 = (wchar_t *)CoTaskMemAlloc(0x400u);
  v6 = 0;
  v7 = v5;
  v8 = 0;
  v9 = 0;
  if ( !v4 )
  {
    v10 = v5;
LABEL_3:
    CoTaskMemFree(v10);
    return 2147942414LL;
  }
  if ( !v5 )
  {
    v10 = v4;
    goto LABEL_3;
  }
  cb = 1024;
  if ( !wRegQueryValue(hkey, L"Protocol\\StdFileEditing\\RequestDataFormats", v4, &cb) )
  {
    v12 = *v4;
    v8 = 1;
    v13 = v4;
    while ( v12 )
    {
      v14 = v12 == 44;
      v15 = v8 + 1;
      v12 = *++v13;
      if ( !v14 )
        v15 = v8;
      v8 = v15;
    }
  }
  cb = 1024;
  if ( !wRegQueryValue(hkey, L"Protocol\\StdFileEditing\\SetDataFormats", v7, &cb) )
  {
    v16 = *v7;
    ++v8;
    v17 = v7;
    while ( v16 )
    {
      v14 = v16 == 44;
      v18 = v8 + 1;
      v16 = *++v17;
      if ( !v14 )
        v18 = v8;
      v8 = v18;
    }
  }
  if ( v8 )
  {
    v19 = (FMT *)HeapAlloc(g_hHeap, 0, 8 * v8 + 8);
    this->m_rgFmt = v19;
    if ( v19 )
    {
      v20 = v4;
      if ( *v4 )
      {
        v21 = 1;
        do
        {
          while ( 1 )
          {
            v22 = *v20;
            if ( *v20 != 32 )
              break;
            ++v20;
          }
          v23 = v20;
          if ( v22 )
          {
            v24 = *v20;
            do
            {
              v22 = v24;
              if ( v24 == 44 )
                break;
              v22 = *++v20;
              v24 = *v20;
            }
            while ( *v20 );
          }
          *v20++ = 0;
          v21 = v22 != 0 ? v21 : 0;
          this->m_rgFmt[v9].cf = String2Clipformat(v23);
          this->m_rgFmt[v9++].dw = 1;
        }
        while ( v21 );
      }
      v25 = v7;
      if ( *v7 )
      {
        v26 = 1;
        do
        {
          while ( 1 )
          {
            v27 = *v25;
            if ( *v25 != 32 )
              break;
            ++v25;
          }
          v28 = v25;
          if ( v27 )
          {
            v29 = *v25;
            do
            {
              v27 = v29;
              if ( v29 == 44 )
                break;
              v27 = *++v25;
              v29 = *v25;
            }
            while ( *v25 );
          }
          *v25++ = 0;
          v26 = v27 != 0 ? v26 : 0;
          v30 = String2Clipformat(v28);
          v31 = 0;
          m_rgFmt = this->m_rgFmt;
          while ( v31 < v9 )
          {
            if ( m_rgFmt[v31].cf == v30 )
            {
              m_rgFmt[v31].dw |= 2u;
              goto LABEL_45;
            }
            ++v31;
          }
          m_rgFmt[v9].cf = v30;
          this->m_rgFmt[v9++].dw = 2;
LABEL_45:
          ;
        }
        while ( v26 );
      }
      this->m_rgFmt[v9].cf = 0;
      this->m_cFmt = v9;
    }
    else
    {
      v6 = -2147024882;
    }
  }
  else
  {
    v6 = -2147221166;
  }
  CoTaskMemFree(v4);
  CoTaskMemFree(v7);
  return v6;
}

```

## disassembly

```asm
0x18009d140  mov     [rsp+arg_0], rbx
0x18009d145  mov     [rsp+arg_8], rbp
0x18009d14a  mov     [rsp+arg_18], rsi
0x18009d14f  push    rdi
0x18009d150  push    r12
0x18009d152  push    r13
0x18009d154  push    r14
0x18009d156  push    r15
0x18009d158  sub     rsp, 20h
0x18009d15c  mov     r13, this
0x18009d15f  mov     r12d, 400h
0x18009d165  mov     ecx, r12d; cb
0x18009d168  mov     rbp, hkey
0x18009d16b  call    cs:__imp_CoTaskMemAlloc
0x18009d172  nop     dword ptr [rax+rax+00h]
0x18009d177  mov     ecx, r12d; cb
0x18009d17a  mov     r14, rax
0x18009d17d  call    cs:__imp_CoTaskMemAlloc
0x18009d184  nop     dword ptr [rax+rax+00h]
0x18009d189  xor     ebx, ebx
0x18009d18b  mov     rsi, rax
0x18009d18e  mov     edi, ebx
0x18009d190  mov     r15d, ebx
0x18009d193  test    r14, r14
0x18009d196  jnz     short loc_18009D1B1
0x18009d198  mov     this, rax; pv
0x18009d19b  call    cs:__imp_CoTaskMemFree
0x18009d1a2  nop     dword ptr [rax+rax+00h]
0x18009d1a7  mov     eax, 8007000Eh
0x18009d1ac  jmp     loc_18009D3BF
0x18009d1b1  test    rsi, rsi
0x18009d1b4  jnz     short loc_18009D1BB
0x18009d1b6  mov     this, r14
0x18009d1b9  jmp     short loc_18009D19B
0x18009d1bb  lea     r9, [rsp+48h+cb]; lpdwSize
0x18009d1c0  mov     [rsp+48h+cb], r12d
0x18009d1c5  mov     r8, r14; lpValue
0x18009d1c8  lea     hkey, aProtocolStdfil; "Protocol\\StdFileEditing\\RequestDataFo"...
0x18009d1cf  mov     this, rbp; hKey
0x18009d1d2  call    wRegQueryValue
0x18009d1d7  test    eax, eax
0x18009d1d9  jnz     short loc_18009D202
0x18009d1db  movzx   ecx, word ptr [r14]
0x18009d1df  lea     edi, [rax+1]
0x18009d1e2  mov     hkey, r14
0x18009d1e5  jmp     short loc_18009D1FD
0x18009d1e7  cmp     cx, 2Ch ; ','
0x18009d1eb  lea     rax, [rdi+1]
0x18009d1ef  lea     hkey, [hkey+2]
0x18009d1f3  movzx   ecx, word ptr [hkey]
0x18009d1f6  cmovnz  rax, rdi
0x18009d1fa  mov     rdi, rax
0x18009d1fd  test    cx, cx
0x18009d200  jnz     short loc_18009D1E7
0x18009d202  lea     r9, [rsp+48h+cb]; lpdwSize
0x18009d207  mov     [rsp+48h+cb], r12d
0x18009d20c  mov     r8, rsi; lpValue
0x18009d20f  lea     hkey, aProtocolStdfil_3; "Protocol\\StdFileEditing\\SetDataFormat"...
0x18009d216  mov     this, rbp; hKey
0x18009d219  call    wRegQueryValue
0x18009d21e  test    eax, eax
0x18009d220  jnz     short loc_18009D248
0x18009d222  movzx   ecx, word ptr [rsi]
0x18009d225  inc     rdi
0x18009d228  mov     hkey, rsi
0x18009d22b  jmp     short loc_18009D243
0x18009d22d  cmp     cx, 2Ch ; ','
0x18009d231  lea     rax, [rdi+1]
0x18009d235  lea     hkey, [hkey+2]
0x18009d239  movzx   ecx, word ptr [hkey]
0x18009d23c  cmovnz  rax, rdi
0x18009d240  mov     rdi, rax
0x18009d243  test    cx, cx
0x18009d246  jnz     short loc_18009D22D
0x18009d248  test    rdi, rdi
0x18009d24b  jnz     short loc_18009D257
0x18009d24d  mov     ebx, 80040152h
0x18009d252  jmp     $errRtn_131
0x18009d257  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18009d25e  lea     r8, ds:8[rdi*8]; dwBytes
0x18009d266  xor     edx, edx; dwFlags
0x18009d268  call    cs:__imp_HeapAlloc
0x18009d26f  nop     dword ptr [rax+rax+00h]
0x18009d274  mov     [r13+18h], rax
0x18009d278  test    rax, rax
0x18009d27b  jnz     short loc_18009D287
0x18009d27d  mov     ebx, 8007000Eh
0x18009d282  jmp     $errRtn_131
0x18009d287  mov     rdi, r14
0x18009d28a  mov     r12w, 20h ; ' '
0x18009d28f  cmp     [r14], bx
0x18009d293  jz      short loc_18009D2FF
0x18009d295  mov     ebp, 1
0x18009d29a  jmp     short loc_18009D2A0
0x18009d29c  add     rdi, 2
0x18009d2a0  movzx   eax, word ptr [rdi]
0x18009d2a3  cmp     ax, r12w
0x18009d2a7  jz      short loc_18009D29C
0x18009d2a9  mov     hkey, rdi
0x18009d2ac  test    ax, ax
0x18009d2af  jz      short loc_18009D2CC
0x18009d2b1  movzx   ecx, ax
0x18009d2b4  movzx   eax, cx
0x18009d2b7  cmp     cx, 2Ch ; ','
0x18009d2bb  jz      short loc_18009D2CC
0x18009d2bd  add     rdi, 2
0x18009d2c1  movzx   eax, word ptr [rdi]
0x18009d2c4  movzx   ecx, ax
0x18009d2c7  test    ax, ax
0x18009d2ca  jnz     short loc_18009D2B4
0x18009d2cc  neg     ax
0x18009d2cf  mov     [rdi], bx
0x18009d2d2  mov     this, hkey; sz
0x18009d2d5  sbb     eax, eax
0x18009d2d7  add     rdi, 2
0x18009d2db  and     ebp, eax
0x18009d2dd  call    String2Clipformat
0x18009d2e2  mov     this, [r13+18h]
0x18009d2e6  mov     [this+r15*8], ax
0x18009d2eb  mov     rax, [r13+18h]
0x18009d2ef  mov     dword ptr [rax+r15*8+4], 1
0x18009d2f8  inc     r15
0x18009d2fb  test    ebp, ebp
0x18009d2fd  jnz     short loc_18009D2A0
0x18009d2ff  mov     rdi, rsi
0x18009d302  cmp     [rsi], bx
0x18009d305  jz      loc_18009D392
0x18009d30b  mov     ebp, 1
0x18009d310  jmp     short loc_18009D316
0x18009d312  add     rdi, 2
0x18009d316  movzx   eax, word ptr [rdi]
0x18009d319  cmp     ax, r12w
0x18009d31d  jz      short loc_18009D312
0x18009d31f  mov     hkey, rdi
0x18009d322  test    ax, ax
0x18009d325  jz      short loc_18009D342
0x18009d327  movzx   ecx, ax
0x18009d32a  movzx   eax, cx
0x18009d32d  cmp     cx, 2Ch ; ','
0x18009d331  jz      short loc_18009D342
0x18009d333  add     rdi, 2
0x18009d337  movzx   eax, word ptr [rdi]
0x18009d33a  movzx   ecx, ax
0x18009d33d  test    ax, ax
0x18009d340  jnz     short loc_18009D32A
0x18009d342  neg     ax
0x18009d345  mov     [rdi], bx
0x18009d348  mov     this, hkey; sz
0x18009d34b  sbb     eax, eax
0x18009d34d  add     rdi, 2
0x18009d351  and     ebp, eax
0x18009d353  call    String2Clipformat
0x18009d358  movzx   edx, ax
0x18009d35b  mov     this, rbx
0x18009d35e  mov     rax, [r13+18h]
0x18009d362  cmp     this, r15
0x18009d365  jnb     short loc_18009D379
0x18009d367  cmp     [rax+this*8], dx
0x18009d36b  jz      short loc_18009D372
0x18009d36d  inc     this
0x18009d370  jmp     short loc_18009D362
0x18009d372  or      dword ptr [rax+this*8+4], 2
0x18009d377  jmp     short loc_18009D38E
0x18009d379  mov     [rax+r15*8], dx
0x18009d37e  mov     rax, [r13+18h]
0x18009d382  mov     dword ptr [rax+r15*8+4], 2
0x18009d38b  inc     r15
0x18009d38e  test    ebp, ebp
0x18009d390  jnz     short loc_18009D316
0x18009d392  mov     this, [r13+18h]
0x18009d396  mov     [this+r15*8], bx
0x18009d39b  mov     [r13+20h], r15
0x18009d39f  mov     this, r14; pv
0x18009d3a2  call    cs:__imp_CoTaskMemFree
0x18009d3a9  nop     dword ptr [rax+rax+00h]
0x18009d3ae  mov     this, rsi; pv
0x18009d3b1  call    cs:__imp_CoTaskMemFree
0x18009d3b8  nop     dword ptr [rax+rax+00h]
0x18009d3bd  mov     eax, ebx
0x18009d3bf  mov     rbx, [rsp+48h+arg_0]
0x18009d3c4  mov     rbp, [rsp+48h+arg_8]
0x18009d3c9  mov     rsi, [rsp+48h+arg_18]
0x18009d3ce  add     rsp, 20h
0x18009d3d2  pop     r15
0x18009d3d4  pop     r14
0x18009d3d6  pop     r13
0x18009d3d8  pop     r12
0x18009d3da  pop     rdi
0x18009d3db  retn
```
