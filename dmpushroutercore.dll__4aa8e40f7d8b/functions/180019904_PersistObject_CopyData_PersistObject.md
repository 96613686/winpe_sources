# PersistObject::CopyData(PersistObject *)

- ea: `0x180019904`
- end: `0x180019cdb`
- name: `?CopyData@PersistObject@@QEAAJPEAV1@@Z`
- size: `983`
- prototype: `__int64 __fastcall(PersistObject *__hidden this, struct PersistObject *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180016c04`
- `0x180036710`
- `0x1800368f0`

## callees

- `0x1800064a2`
- `0x180017258`
- `0x180017384`
- `0x180019904`
- `0x18001abd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019989`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019a15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019a86`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019afc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019ba5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019c26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019cbb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019989`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019a15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019a86`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019afc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019ba5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019c26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019cbb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001992c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001995b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800199d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019a52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019ab8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019b2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019bda`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001992c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001995b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800199d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019a52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019ab8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019b2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019bda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019c58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019c6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019c94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019c9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019ca8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019c58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019c6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019c94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019c9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019ca8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800199b5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019b6b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800199b5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019b6b`
- `DMCmnUtils!CopyString` at `0x180019c1b`
- `DMCmnUtils!CopyString` at `0x180019c1b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PersistObject::CopyData(PersistObject *this, struct PersistObject *a2)
{
  void *v3; // rdi
  _DWORD *v4; // r12
  int v5; // ebx
  unsigned int v6; // ebp
  unsigned int v7; // edx
  unsigned int v8; // ecx
  unsigned __int64 v9; // rax
  unsigned int v10; // r8d
  unsigned int v11; // r9d
  unsigned int i; // edx
  unsigned int v13; // r14d
  __int64 v14; // r13
  __int64 v15; // rbx
  int *v16; // rdx
  __int64 v17; // rbx
  unsigned int v18; // edi
  _DWORD *v19; // rdx
  int v20; // eax
  __int64 v21; // rbx
  __int64 v22; // r14
  HLOCAL v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rcx
  int v27; // [rsp+20h] [rbp-68h]
  unsigned int v28; // [rsp+24h] [rbp-64h]
  HLOCAL hMem[2]; // [rsp+28h] [rbp-60h] BYREF
  char v30; // [rsp+38h] [rbp-50h]
  char *v31; // [rsp+40h] [rbp-48h]
  char v32; // [rsp+48h] [rbp-40h]
  int v34; // [rsp+A0h] [rbp+18h]
  unsigned int v35; // [rsp+A8h] [rbp+20h]

  v31 = (char *)this + 32;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v32 = 1;
  hMem[0] = 0;
  v3 = 0;
  v4 = 0;
  if ( !a2 )
  {
    v5 = -2147467261;
    goto LABEL_64;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
  v6 = 0;
  if ( *((_DWORD *)a2 + 4) )
  {
    v7 = 0;
    do
    {
      v8 = v6 + 1;
      if ( !*(_QWORD *)(*((_QWORD *)a2 + 1) + 8LL * v7) )
        v8 = v6;
      v6 = v8;
      ++v7;
    }
    while ( v7 < *((_DWORD *)a2 + 4) );
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
  v5 = 0;
  if ( v6 )
  {
    v9 = 4LL * v6;
    if ( v9 > 0xFFFFFFFF )
    {
      v5 = -2147024362;
      goto LABEL_64;
    }
    v4 = LocalAlloc(0x40u, (unsigned int)v9);
    if ( !v4 )
    {
      v5 = -2147024882;
      goto LABEL_64;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
    v10 = 0;
    v11 = 0;
    for ( i = 0; i < *((_DWORD *)a2 + 4); ++i )
    {
      if ( *(_QWORD *)(*((_QWORD *)a2 + 1) + 8LL * i) )
      {
        if ( v6 < ++v10 || v11 >= v6 )
        {
          v5 = -2147024774;
          goto LABEL_19;
        }
        v4[v11++] = i;
      }
    }
    v6 = v10;
LABEL_19:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
    if ( v5 >= 0 )
    {
      v27 = 0;
      v35 = 0;
      v28 = 0;
      v13 = 0;
      v34 = 0;
      if ( v6 )
      {
        while ( 1 )
        {
          v14 = v13;
          v15 = (unsigned int)v4[v13];
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
          if ( (unsigned int)v15 < *((_DWORD *)a2 + 4)
            && (_mm_lfence(), (v16 = *(int **)(*((_QWORD *)a2 + 1) + 8 * v15)) != 0) )
          {
            v5 = 0;
            v27 = *v16;
          }
          else
          {
            v5 = -2147023728;
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
          v3 = 0;
          if ( v5 < 0 )
            goto LABEL_64;
          if ( v27 == 1 )
          {
            v24 = (unsigned int)v4[v13];
            hMem[1] = (char *)a2 + 32;
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
            v30 = 1;
            if ( (unsigned int)v24 < *((_DWORD *)a2 + 4)
              && (_mm_lfence(), (v25 = *(_QWORD *)(*((_QWORD *)a2 + 1) + 8 * v24)) != 0) )
            {
              if ( *(_DWORD *)v25 == 1 )
                v5 = CopyString(*(const unsigned __int16 **)(v25 + 16), 0xFFFFFFFF, (unsigned __int16 **)hMem);
              else
                v5 = -2147024883;
            }
            else
            {
              v5 = -2147023728;
            }
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
            v30 = 0;
            v3 = 0;
            if ( v5 < 0 )
              goto LABEL_64;
            v20 = PersistObject::Set(this, (unsigned int)v4[v13], hMem[0]);
            goto LABEL_59;
          }
          if ( v27 == 3 )
            break;
          if ( v27 == 4 )
          {
            v17 = (unsigned int)v4[v13];
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
            if ( (unsigned int)v17 >= *((_DWORD *)a2 + 4)
              || (_mm_lfence(), (v19 = *(_DWORD **)(*((_QWORD *)a2 + 1) + 8 * v17)) == 0) )
            {
              v5 = -2147023728;
              goto LABEL_32;
            }
            if ( *v19 == 4 )
            {
              v5 = 0;
              v18 = v19[1];
              v35 = v18;
            }
            else
            {
              v5 = -2147024883;
LABEL_32:
              v18 = v35;
            }
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
            if ( v5 < 0 )
            {
              v3 = 0;
              goto LABEL_64;
            }
            v20 = PersistObject::Set(this, (unsigned int)v4[v13], v18);
            v3 = 0;
LABEL_59:
            v5 = v20;
            if ( v20 < 0 )
              goto LABEL_64;
          }
          LocalFree(hMem[0]);
          hMem[0] = 0;
          LocalFree(v3);
          v3 = 0;
          v34 = ++v13;
          if ( v13 >= v6 )
            goto LABEL_64;
        }
        v21 = (unsigned int)v4[v13];
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
        if ( (unsigned int)v21 < *((_DWORD *)a2 + 4) )
        {
          _mm_lfence();
          v22 = *(_QWORD *)(*((_QWORD *)a2 + 1) + 8 * v21);
          if ( v22 )
          {
            if ( *(_DWORD *)v22 == 3 )
            {
              v23 = LocalAlloc(0x40u, *(unsigned int *)(v22 + 8));
              v3 = v23;
              if ( v23 )
              {
                v5 = 0;
                memcpy_0(v23, *(const void **)(v22 + 24), *(unsigned int *)(v22 + 8));
                v28 = *(_DWORD *)(v22 + 8);
              }
              else
              {
                v5 = -2147024882;
              }
            }
            else
            {
              v5 = -2147024883;
            }
          }
          else
          {
            v5 = -2147023728;
          }
          v13 = v34;
        }
        else
        {
          v5 = -2147023728;
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
        if ( v5 < 0 )
          goto LABEL_64;
        v20 = PersistObject::Set(this, (unsigned int)v4[v14], v3, v28);
        goto LABEL_59;
      }
    }
  }
LABEL_64:
  LocalFree(v3);
  LocalFree(hMem[0]);
  LocalFree(v4);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180019904  mov     [rsp+arg_8], rbx
0x180019909  mov     [rsp+arg_0], rcx
0x18001990e  push    rbp
0x18001990f  push    rsi
0x180019910  push    rdi
0x180019911  push    r12
0x180019913  push    r13
0x180019915  push    r14
0x180019917  push    r15
0x180019919  sub     rsp, 50h
0x18001991d  mov     rsi, rdx
0x180019920  lea     rax, [rcx+20h]
0x180019924  mov     [rsp+88h+var_48], rax
0x180019929  mov     rcx, rax; lpCriticalSection
0x18001992c  call    cs:__imp_EnterCriticalSection
0x180019932  mov     [rsp+88h+var_40], 1
0x180019937  xor     r13d, r13d
0x18001993a  mov     [rsp+88h+hMem], r13
0x18001993f  mov     edi, r13d
0x180019942  mov     r12d, r13d
0x180019945  test    rsi, rsi
0x180019948  jnz     short loc_180019954
0x18001994a  mov     ebx, 80004003h
0x18001994f  jmp     loc_180019C91
0x180019954  lea     r15, [rsi+20h]
0x180019958  mov     rcx, r15; lpCriticalSection
0x18001995b  call    cs:__imp_EnterCriticalSection
0x180019961  mov     ebp, r13d
0x180019964  cmp     [rsi+10h], r13d
0x180019968  jbe     short loc_180019986
0x18001996a  mov     edx, r13d
0x18001996d  mov     r8, [rsi+8]
0x180019971  mov     eax, edx
0x180019973  lea     ecx, [rbp+1]
0x180019976  cmp     [r8+rax*8], r13
0x18001997a  cmovz   ecx, ebp
0x18001997d  mov     ebp, ecx
0x18001997f  inc     edx
0x180019981  cmp     edx, [rsi+10h]
0x180019984  jb      short loc_180019971
0x180019986  mov     rcx, r15; lpCriticalSection
0x180019989  call    cs:__imp_LeaveCriticalSection
0x18001998f  mov     ebx, r13d
0x180019992  test    ebp, ebp
0x180019994  jz      loc_180019C91
0x18001999a  mov     eax, ebp
0x18001999c  shl     rax, 2
0x1800199a0  mov     ecx, 0FFFFFFFFh
0x1800199a5  cmp     rax, rcx
0x1800199a8  ja      loc_180019C8C
0x1800199ae  mov     edx, eax; uBytes
0x1800199b0  mov     ecx, 40h ; '@'; uFlags
0x1800199b5  call    cs:__imp_LocalAlloc
0x1800199bb  mov     r12, rax
0x1800199be  test    rax, rax
0x1800199c1  jnz     short loc_1800199CD
0x1800199c3  mov     ebx, 8007000Eh
0x1800199c8  jmp     loc_180019C91
0x1800199cd  mov     rcx, r15; lpCriticalSection
0x1800199d0  call    cs:__imp_EnterCriticalSection
0x1800199d6  mov     r8d, r13d
0x1800199d9  mov     r9d, r13d
0x1800199dc  mov     edx, r13d
0x1800199df  cmp     [rsi+10h], r13d
0x1800199e3  jbe     short loc_180019A0F
0x1800199e5  mov     ecx, edx
0x1800199e7  mov     rax, [rsi+8]
0x1800199eb  cmp     [rax+rcx*8], r13
0x1800199ef  jz      short loc_180019A08
0x1800199f1  inc     r8d
0x1800199f4  cmp     ebp, r8d
0x1800199f7  jb      short loc_180019A64
0x1800199f9  cmp     r9d, ebp
0x1800199fc  jnb     short loc_180019A64
0x1800199fe  mov     eax, r9d
0x180019a01  mov     [r12+rax*4], edx
0x180019a05  inc     r9d
0x180019a08  inc     edx
0x180019a0a  cmp     edx, [rsi+10h]
0x180019a0d  jb      short loc_1800199E5
0x180019a0f  mov     ebp, r8d
0x180019a12  mov     rcx, r15; lpCriticalSection
0x180019a15  call    cs:__imp_LeaveCriticalSection
0x180019a1b  test    ebx, ebx
0x180019a1d  js      loc_180019C91
0x180019a23  mov     [rsp+88h+var_68], r13d
0x180019a28  mov     [rsp+88h+arg_18], r13d
0x180019a30  mov     [rsp+88h+var_64], r13d
0x180019a35  mov     r14d, r13d
0x180019a38  mov     [rsp+88h+arg_10], r13d
0x180019a40  test    ebp, ebp
0x180019a42  jz      loc_180019C91
0x180019a48  mov     r13d, r14d
0x180019a4b  mov     ebx, [r12+r13*4]
0x180019a4f  mov     rcx, r15; lpCriticalSection
0x180019a52  call    cs:__imp_EnterCriticalSection
0x180019a58  cmp     ebx, [rsi+10h]
0x180019a5b  jb      short loc_180019A6B
0x180019a5d  mov     ebx, 80070490h
0x180019a62  jmp     short loc_180019A83
0x180019a64  mov     ebx, 8007007Ah
0x180019a69  jmp     short loc_180019A12
0x180019a6b  lfence
0x180019a6e  mov     rax, [rsi+8]
0x180019a72  mov     rdx, [rax+rbx*8]
0x180019a76  test    rdx, rdx
0x180019a79  jz      short loc_180019A5D
0x180019a7b  xor     ebx, ebx
0x180019a7d  mov     eax, [rdx]
0x180019a7f  mov     [rsp+88h+var_68], eax
0x180019a83  mov     rcx, r15; lpCriticalSection
0x180019a86  call    cs:__imp_LeaveCriticalSection
0x180019a8c  xor     edi, edi
0x180019a8e  test    ebx, ebx
0x180019a90  js      loc_180019C91
0x180019a96  mov     eax, [rsp+88h+var_68]
0x180019a9a  sub     eax, 1
0x180019a9d  jz      loc_180019BCE
0x180019aa3  sub     eax, 2
0x180019aa6  jz      short loc_180019B25
0x180019aa8  cmp     eax, 1
0x180019aab  jnz     loc_180019C53
0x180019ab1  mov     ebx, [r12+r13*4]
0x180019ab5  mov     rcx, r15; lpCriticalSection
0x180019ab8  call    cs:__imp_EnterCriticalSection
0x180019abe  cmp     ebx, [rsi+10h]
0x180019ac1  jb      short loc_180019AD1
0x180019ac3  mov     ebx, 80070490h
0x180019ac8  mov     edi, [rsp+88h+arg_18]
0x180019acf  jmp     short loc_180019AF9
0x180019ad1  lfence
0x180019ad4  mov     rax, [rsi+8]
0x180019ad8  mov     rdx, [rax+rbx*8]
0x180019adc  test    rdx, rdx
0x180019adf  jz      short loc_180019AC3
0x180019ae1  cmp     dword ptr [rdx], 4
0x180019ae4  jz      short loc_180019AED
0x180019ae6  mov     ebx, 8007000Dh
0x180019aeb  jmp     short loc_180019AC8
0x180019aed  xor     ebx, ebx
0x180019aef  mov     edi, [rdx+4]
0x180019af2  mov     [rsp+88h+arg_18], edi
0x180019af9  mov     rcx, r15; lpCriticalSection
0x180019afc  call    cs:__imp_LeaveCriticalSection
0x180019b02  test    ebx, ebx
0x180019b04  js      loc_180019C88
0x180019b0a  mov     r8d, edi
0x180019b0d  mov     edx, [r12+r13*4]
0x180019b11  mov     rcx, [rsp+88h+arg_0]
0x180019b19  call    ?Set@PersistObject@@QEAAJW4PERSIST_OBJECT_MEMBER_ID@1@K@Z; PersistObject::Set(PersistObject::PERSIST_OBJECT_MEMBER_ID,ulong)
0x180019b1e  xor     edi, edi
0x180019b20  jmp     loc_180019C4D
0x180019b25  mov     ebx, [r12+r13*4]
0x180019b29  mov     rcx, r15; lpCriticalSection
0x180019b2c  call    cs:__imp_EnterCriticalSection
0x180019b32  cmp     ebx, [rsi+10h]
0x180019b35  jb      short loc_180019B3E
0x180019b37  mov     ebx, 80070490h
0x180019b3c  jmp     short loc_180019BA2
0x180019b3e  lfence
0x180019b41  mov     rax, [rsi+8]
0x180019b45  mov     r14, [rax+rbx*8]
0x180019b49  test    r14, r14
0x180019b4c  jnz     short loc_180019B55
0x180019b4e  mov     ebx, 80070490h
0x180019b53  jmp     short loc_180019B9A
0x180019b55  cmp     dword ptr [r14], 3
0x180019b59  jz      short loc_180019B62
0x180019b5b  mov     ebx, 8007000Dh
0x180019b60  jmp     short loc_180019B9A
0x180019b62  mov     edx, [r14+8]; uBytes
0x180019b66  mov     ecx, 40h ; '@'; uFlags
0x180019b6b  call    cs:__imp_LocalAlloc
0x180019b71  mov     rdi, rax
0x180019b74  test    rax, rax
0x180019b77  jnz     short loc_180019B80
0x180019b79  mov     ebx, 8007000Eh
0x180019b7e  jmp     short loc_180019B9A
0x180019b80  xor     ebx, ebx
0x180019b82  mov     r8d, [r14+8]; Size
0x180019b86  mov     rdx, [r14+18h]; Src
0x180019b8a  mov     rcx, rax; void *
0x180019b8d  call    memcpy_0
0x180019b92  mov     eax, [r14+8]
0x180019b96  mov     [rsp+88h+var_64], eax
0x180019b9a  mov     r14d, [rsp+88h+arg_10]
0x180019ba2  mov     rcx, r15; lpCriticalSection
0x180019ba5  call    cs:__imp_LeaveCriticalSection
0x180019bab  test    ebx, ebx
0x180019bad  js      loc_180019C91
0x180019bb3  mov     r9d, [rsp+88h+var_64]
0x180019bb8  mov     r8, rdi
0x180019bbb  mov     edx, [r12+r13*4]
0x180019bbf  mov     rcx, [rsp+88h+arg_0]
0x180019bc7  call    ?Set@PersistObject@@QEAAJW4PERSIST_OBJECT_MEMBER_ID@1@QEAEK@Z; PersistObject::Set(PersistObject::PERSIST_OBJECT_MEMBER_ID,uchar * const,ulong)
0x180019bcc  jmp     short loc_180019C4D
0x180019bce  mov     ebx, [r12+r13*4]
0x180019bd2  mov     [rsp+88h+var_58], r15
0x180019bd7  mov     rcx, r15; lpCriticalSection
0x180019bda  call    cs:__imp_EnterCriticalSection
0x180019be0  mov     [rsp+88h+var_50], 1
0x180019be5  cmp     ebx, [rsi+10h]
0x180019be8  jb      short loc_180019BF1
0x180019bea  mov     ebx, 80070490h
0x180019bef  jmp     short loc_180019C23
0x180019bf1  lfence
0x180019bf4  mov     rax, [rsi+8]
0x180019bf8  mov     rcx, [rax+rbx*8]
0x180019bfc  test    rcx, rcx
0x180019bff  jz      short loc_180019BEA
0x180019c01  cmp     dword ptr [rcx], 1
0x180019c04  jz      short loc_180019C0D
0x180019c06  mov     ebx, 8007000Dh
0x180019c0b  jmp     short loc_180019C23
0x180019c0d  lea     r8, [rsp+88h+hMem]
0x180019c12  mov     edx, 0FFFFFFFFh
0x180019c17  mov     rcx, [rcx+10h]
0x180019c1b  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180019c21  mov     ebx, eax
0x180019c23  mov     rcx, r15; lpCriticalSection
0x180019c26  call    cs:__imp_LeaveCriticalSection
0x180019c2c  mov     [rsp+88h+var_50], 0
0x180019c31  xor     edi, edi
0x180019c33  test    ebx, ebx
0x180019c35  js      short loc_180019C91
0x180019c37  mov     r8, [rsp+88h+hMem]
0x180019c3c  mov     edx, [r12+r13*4]
0x180019c40  mov     rcx, [rsp+88h+arg_0]
0x180019c48  call    ?Set@PersistObject@@QEAAJW4PERSIST_OBJECT_MEMBER_ID@1@PEBG@Z; PersistObject::Set(PersistObject::PERSIST_OBJECT_MEMBER_ID,ushort const *)
0x180019c4d  mov     ebx, eax
0x180019c4f  test    eax, eax
0x180019c51  js      short loc_180019C91
0x180019c53  mov     rcx, [rsp+88h+hMem]; hMem
0x180019c58  call    cs:__imp_LocalFree
0x180019c5e  mov     [rsp+88h+hMem], 0
0x180019c67  mov     rcx, rdi; hMem
0x180019c6a  call    cs:__imp_LocalFree
0x180019c70  xor     edi, edi
0x180019c72  inc     r14d
0x180019c75  mov     [rsp+88h+arg_10], r14d
0x180019c7d  cmp     r14d, ebp
0x180019c80  jb      loc_180019A48
0x180019c86  jmp     short loc_180019C91
0x180019c88  xor     edi, edi
0x180019c8a  jmp     short loc_180019C91
0x180019c8c  mov     ebx, 80070216h
0x180019c91  mov     rcx, rdi; hMem
0x180019c94  call    cs:__imp_LocalFree
0x180019c9a  mov     rcx, [rsp+88h+hMem]; hMem
0x180019c9f  call    cs:__imp_LocalFree
0x180019ca5  mov     rcx, r12; hMem
0x180019ca8  call    cs:__imp_LocalFree
0x180019cae  nop
0x180019caf  mov     rcx, [rsp+88h+arg_0]
0x180019cb7  add     rcx, 20h ; ' '; lpCriticalSection
0x180019cbb  call    cs:__imp_LeaveCriticalSection
0x180019cc1  mov     eax, ebx
0x180019cc3  mov     rbx, [rsp+88h+arg_8]
0x180019ccb  add     rsp, 50h
0x180019ccf  pop     r15
0x180019cd1  pop     r14
0x180019cd3  pop     r13
0x180019cd5  pop     r12
0x180019cd7  pop     rdi
0x180019cd8  pop     rsi
0x180019cd9  pop     rbp
0x180019cda  retn
```
