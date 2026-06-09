# TREE_HASH_TABLE::DeletePath(ushort const *)

- ea: `0x180002fd0`
- end: `0x180003402`
- name: `?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z`
- size: `1074`
- prototype: `void __fastcall(TREE_HASH_TABLE *__hidden this, const unsigned __int16 *Src)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002da0`
- `0x180002fd0`
- `0x180003410`
- `0x1800034f0`
- `0x180003fb0`
- `0x180007e60`
- `0x18002e516`
- `0x18002e52e`
- `0x18002e560`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003124`
- `msvcrt!_wcsicmp` at `0x180003124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800030a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800031bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800030a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800031bd`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180003316`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180003316`
- `bcrypt!BCryptCreateHash` at `0x180003347`
- `bcrypt!BCryptCreateHash` at `0x180003347`
- `bcrypt!BCryptFinishHash` at `0x18000338b`
- `bcrypt!BCryptFinishHash` at `0x18000338b`
- `bcrypt!BCryptHashData` at `0x180003367`
- `bcrypt!BCryptHashData` at `0x180003367`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800033a5`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800033a5`
- `bcrypt!BCryptDestroyHash` at `0x1800033bb`
- `bcrypt!BCryptDestroyHash` at `0x1800033bb`

## pseudocode

```c
void __fastcall TREE_HASH_TABLE::DeletePath(TREE_HASH_TABLE *this, const unsigned __int16 *Src)
{
  const unsigned __int16 *v2; // r12
  unsigned __int16 v4; // ax
  int i; // ebx
  const unsigned __int16 *v6; // rcx
  unsigned int v7; // esi
  signed __int32 v8; // edx
  __int64 v9; // rdx
  __int64 v10; // rax
  struct TREE_HASH_NODE *v11; // rbx
  struct TREE_HASH_NODE **v12; // rdi
  const wchar_t *v13; // rcx
  signed __int64 v14; // r8
  int v15; // edx
  int v16; // eax
  signed __int32 v17; // edx
  UCHAR *v18; // rdi
  __int64 v19; // rax
  __int64 v21; // rbx
  unsigned int v22; // eax
  unsigned __int16 v23; // cx
  signed int LastError; // eax
  bool v25; // sf
  ULONG v26; // esi
  unsigned __int64 v27; // rdx
  NTSTATUS v28; // ebx
  unsigned int v29; // r8d
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-C0h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v32[24]; // [rsp+58h] [rbp-B0h] BYREF
  UCHAR *v33; // [rsp+78h] [rbp-90h]
  int v34; // [rsp+80h] [rbp-88h]
  __int16 v35; // [rsp+84h] [rbp-84h]
  unsigned int v36; // [rsp+88h] [rbp-80h]
  UCHAR pbOutput[16]; // [rsp+90h] [rbp-78h] BYREF
  __int128 v38; // [rsp+A0h] [rbp-68h]
  UCHAR pbInput[2]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v40[526]; // [rsp+BAh] [rbp-4Eh] BYREF

  if ( !Src )
    return;
  v2 = Src;
  if ( *((_DWORD *)this + 6) )
  {
    if ( !*((_DWORD *)this + 7) )
    {
      v4 = *Src;
      i = 0;
      if ( *Src )
      {
        v6 = Src;
        do
        {
          ++v6;
          i = v4 + 101 * i;
          v4 = *v6;
        }
        while ( *v6 );
      }
      goto LABEL_7;
    }
    memset_0(v40, 0, 0x206u);
    v34 = 520;
    v18 = pbInput;
    v36 = 0;
    *(_WORD *)pbInput = 0;
    v19 = -1;
    v33 = pbInput;
    v35 = 256;
    while ( v2[++v19] != 0 )
      ;
    v21 = (unsigned int)(2 * v19);
    if ( (unsigned __int64)(v21 + 2) > 0x208 )
    {
      if ( (unsigned __int64)(v21 + 128) > 0xFFFFFFFF )
        goto LABEL_58;
      if ( !BUFFER::Resize((BUFFER *)v32, v21 + 128) )
      {
        LastError = GetLastError();
        v25 = LastError < 0;
        if ( LastError > 0 )
          v25 = 1;
        if ( v25 )
          goto LABEL_58;
        v22 = v36;
        v18 = v33;
        goto LABEL_46;
      }
      v18 = v33;
    }
    memcpy_0(v18, v2, (unsigned int)v21);
    v22 = (unsigned int)v21 >> 1;
    v36 = v22;
    *(_WORD *)&v18[2 * v22] = 0;
LABEL_46:
    phAlgorithm = 0;
    phHash = 0;
    *(_OWORD *)pbOutput = 0;
    v38 = 0;
    if ( v18 )
    {
      v26 = 2 * v22;
      if ( 2 * v22 )
      {
        v28 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
        if ( v28 >= 0 )
        {
          v28 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
          if ( v28 >= 0 )
          {
            v28 = BCryptHashData(phHash, v18, v26, 0);
            if ( v28 >= 0 )
              v28 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
          }
        }
        if ( phAlgorithm )
          BCryptCloseAlgorithmProvider(phAlgorithm, 0);
        if ( phHash )
          BCryptDestroyHash(phHash);
        if ( v28 >= 0 )
        {
          i = HashBlob(pbOutput, v27, v29);
          BUFFER::~BUFFER((BUFFER *)v32);
          goto LABEL_7;
        }
      }
    }
LABEL_58:
    BUFFER::~BUFFER((BUFFER *)v32);
    return;
  }
  v23 = *Src;
  for ( i = 0; *Src; v23 = *Src )
  {
    ++Src;
    i = (v23 & 0xFFDF) + 101 * i;
  }
LABEL_7:
  v7 = (69069 * i + 1) & 0xFFFF0000 | ((unsigned int)(1103515245 * i + 12345) >> 16);
  if ( *((_DWORD *)this + 9)
    || (v8 = *((_DWORD *)this + 8), (_WORD)v8)
    || v8 != _InterlockedCompareExchange((volatile signed __int32 *)this + 8, (v8 + 0x10000) | 0xFFFF, v8) )
  {
    if ( (*((_DWORD *)this + 9) & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC) )
      _InterlockedIncrement((volatile signed __int32 *)this + 9);
    else
      CReaderWriterLock3::_WriteLockSpin((TREE_HASH_TABLE *)((char *)this + 32));
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)this + 9, GetCurrentThreadId() & 0xFFFFFFFC | 1);
  }
  v9 = v7 % *((_DWORD *)this + 4);
  v10 = *((_QWORD *)this + 1);
  v11 = *(struct TREE_HASH_NODE **)(v10 + 8 * v9);
  v12 = (struct TREE_HASH_NODE **)(v10 + 8LL * (unsigned int)v9);
  while ( v11 )
  {
    if ( *((_DWORD *)v11 + 12) == v7 )
    {
      v13 = (const wchar_t *)*((_QWORD *)v11 + 5);
      if ( *((_DWORD *)this + 6) )
      {
        v14 = (char *)v2 - (char *)v13;
        do
        {
          v15 = *(const wchar_t *)((char *)v13 + v14);
          v16 = *v13 - v15;
          if ( v16 )
            break;
          ++v13;
        }
        while ( v15 );
        if ( !v16 )
        {
LABEL_22:
          TREE_HASH_TABLE::DeleteNodeInternal(this, v12, v11);
          break;
        }
      }
      else if ( !_wcsicmp(v13, v2) )
      {
        goto LABEL_22;
      }
    }
    else if ( *((_DWORD *)v11 + 12) > v7 )
    {
      break;
    }
    v12 = (struct TREE_HASH_NODE **)v11;
    v11 = *(struct TREE_HASH_NODE **)v11;
  }
  if ( ((*((_BYTE *)this + 36) - 1) & 3) != 0 )
  {
    _InterlockedExchange((volatile __int32 *)this + 9, *((_DWORD *)this + 9) - 1);
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)this + 9, 0);
    while ( 1 )
    {
      v17 = *((_DWORD *)this + 8);
      if ( v17 == _InterlockedCompareExchange((volatile signed __int32 *)this + 8, (v17 - 0x10000) & 0xFFFF0000, v17) )
        break;
      _mm_pause();
    }
  }
}

```

## disassembly

```asm
0x180002fd0  test    rdx, rdx
0x180002fd3  jz      locret_180003193
0x180002fd9  mov     r11, rsp
0x180002fdc  push    rbp
0x180002fdd  push    r12
0x180002fdf  push    r15
0x180002fe1  lea     rbp, [r11-208h]
0x180002fe8  sub     rsp, 2F0h
0x180002fef  mov     rax, cs:__security_cookie
0x180002ff6  xor     rax, rsp
0x180002ff9  mov     [rbp+200h+var_40], rax
0x180003000  cmp     dword ptr [rcx+18h], 0
0x180003004  mov     r12, rdx
0x180003007  mov     [r11+18h], rbx
0x18000300b  mov     r15, rcx
0x18000300e  mov     [r11-20h], rsi
0x180003012  mov     [r11-28h], rdi
0x180003016  mov     [r11-30h], r13
0x18000301a  jz      loc_18000325A
0x180003020  cmp     dword ptr [rcx+1Ch], 0
0x180003024  jnz     loc_1800031D8
0x18000302a  movzx   eax, word ptr [rdx]
0x18000302d  xor     r13d, r13d
0x180003030  mov     ebx, r13d
0x180003033  test    ax, ax
0x180003036  jz      short loc_180003054
0x180003038  mov     rcx, rdx
0x18000303b  nop     dword ptr [rax+rax+00h]
0x180003040  imul    ebx, 65h ; 'e'
0x180003043  lea     rcx, [rcx+2]
0x180003047  movzx   eax, ax
0x18000304a  add     ebx, eax
0x18000304c  movzx   eax, word ptr [rcx]
0x18000304f  test    ax, ax
0x180003052  jnz     short loc_180003040
0x180003054  imul    esi, ebx, 41C64E6Dh
0x18000305a  imul    eax, ebx, 10DCDh
0x180003060  mov     [rsp+300h+var_30], r14
0x180003068  add     esi, 3039h
0x18000306e  inc     eax
0x180003070  shr     esi, 10h
0x180003073  and     eax, 0FFFF0000h
0x180003078  or      esi, eax
0x18000307a  mov     eax, [r15+24h]
0x18000307e  test    eax, eax
0x180003080  jnz     short loc_1800030A7
0x180003082  mov     edx, [r15+20h]
0x180003086  test    dx, dx
0x180003089  jnz     short loc_1800030A7
0x18000308b  lea     ecx, [rdx+10000h]
0x180003091  mov     eax, edx
0x180003093  or      ecx, 0FFFFh
0x180003099  lock cmpxchg [r15+20h], ecx
0x18000309f  cmp     edx, eax
0x1800030a1  jz      loc_1800031BD
0x1800030a7  call    cs:__imp_GetCurrentThreadId
0x1800030ae  nop     dword ptr [rax+rax+00h]
0x1800030b3  mov     ecx, [r15+24h]
0x1800030b7  and     eax, 0FFFFFFFCh
0x1800030ba  and     ecx, 0FFFFFFFCh
0x1800030bd  cmp     ecx, eax
0x1800030bf  jz      loc_180003250
0x1800030c5  lea     rcx, [r15+20h]; this
0x1800030c9  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x1800030ce  xor     edx, edx
0x1800030d0  mov     eax, esi
0x1800030d2  div     dword ptr [r15+10h]
0x1800030d6  mov     rax, [r15+8]
0x1800030da  mov     rbx, [rax+rdx*8]
0x1800030de  lea     rdi, [rax+rdx*8]
0x1800030e2  test    rbx, rbx
0x1800030e5  jz      short loc_180003142
0x1800030e7  cmp     [rbx+30h], esi
0x1800030ea  jnz     loc_180003195
0x1800030f0  cmp     dword ptr [r15+18h], 0
0x1800030f5  mov     rcx, [rbx+28h]; String1
0x1800030f9  jz      short loc_180003121
0x1800030fb  mov     r8, r12
0x1800030fe  sub     r8, rcx
0x180003101  movzx   eax, word ptr [rcx]
0x180003104  movzx   edx, word ptr [rcx+r8]
0x180003109  sub     eax, edx
0x18000310b  jnz     short loc_180003115
0x18000310d  add     rcx, 2
0x180003111  test    edx, edx
0x180003113  jnz     short loc_180003101
0x180003115  test    eax, eax
0x180003117  jz      short loc_180003134
0x180003119  mov     rdi, rbx
0x18000311c  mov     rbx, [rbx]
0x18000311f  jmp     short loc_1800030E2
0x180003121  mov     rdx, r12; String2
0x180003124  call    cs:__imp__wcsicmp
0x18000312b  nop     dword ptr [rax+rax+00h]
0x180003130  test    eax, eax
0x180003132  jnz     short loc_180003119
0x180003134  mov     r8, rbx; struct TREE_HASH_NODE *
0x180003137  mov     rdx, rdi; struct TREE_HASH_NODE **
0x18000313a  mov     rcx, r15; this
0x18000313d  call    ?DeleteNodeInternal@TREE_HASH_TABLE@@AEAAXPEAPEAUTREE_HASH_NODE@@PEAU2@@Z; TREE_HASH_TABLE::DeleteNodeInternal(TREE_HASH_NODE * *,TREE_HASH_NODE *)
0x180003142  mov     eax, [r15+24h]
0x180003146  dec     eax
0x180003148  test    al, 3
0x18000314a  jz      short loc_180003199
0x18000314c  xchg    eax, [r15+24h]
0x180003150  mov     r14, [rsp+300h+var_30]
0x180003158  mov     rdi, [rsp+300h+var_20]
0x180003160  mov     rsi, [rsp+2E8h]
0x180003168  mov     rbx, [rsp+300h+arg_10]
0x180003170  mov     r13, [rsp+300h+var_28]
0x180003178  mov     rcx, [rbp+200h+var_40]
0x18000317f  xor     rcx, rsp; StackCookie
0x180003182  call    __security_check_cookie
0x180003187  add     rsp, 2F0h
0x18000318e  pop     r15
0x180003190  pop     r12
0x180003192  pop     rbp
0x180003193  retn
0x180003195  jbe     short loc_180003119
0x180003197  jmp     short loc_180003142
0x180003199  xchg    r13d, [r15+24h]
0x18000319d  mov     edx, [r15+20h]
0x1800031a1  mov     eax, edx
0x1800031a3  lea     ecx, [rdx-10000h]
0x1800031a9  and     ecx, 0FFFF0000h
0x1800031af  lock cmpxchg [r15+20h], ecx
0x1800031b5  cmp     edx, eax
0x1800031b7  jz      short loc_180003150
0x1800031b9  pause
0x1800031bb  jmp     short loc_18000319D
0x1800031bd  call    cs:__imp_GetCurrentThreadId
0x1800031c4  nop     dword ptr [rax+rax+00h]
0x1800031c9  and     eax, 0FFFFFFFCh
0x1800031cc  or      eax, 1
0x1800031cf  xchg    eax, [r15+24h]
0x1800031d3  jmp     loc_1800030CE
0x1800031d8  xor     edx, edx; Val
0x1800031da  lea     rcx, [rbp+200h+var_24E]; void *
0x1800031de  mov     r8d, 206h; Size
0x1800031e4  call    memset_0
0x1800031e9  xor     r13d, r13d
0x1800031ec  mov     [rsp+300h+var_288], 208h
0x1800031f4  lea     rdi, [rbp+200h+pbInput]
0x1800031f8  mov     [rbp+200h+var_280], r13d
0x1800031fc  mov     word ptr [rbp+200h+pbInput], r13w
0x180003201  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003208  mov     qword ptr [rsp+300h+var_290], rdi
0x18000320d  mov     [rsp+300h+var_284], 100h
0x180003214  cmp     [r12+rax*2+2], r13w
0x18000321a  lea     rax, [rax+1]
0x18000321e  jnz     short loc_180003214
0x180003220  lea     ebx, [rax+rax]
0x180003223  lea     rax, [rbx+2]
0x180003227  mov     esi, ebx
0x180003229  cmp     rax, 208h
0x18000322f  ja      short loc_18000328C
0x180003231  mov     r8, rsi; Size
0x180003234  mov     rdx, r12; Src
0x180003237  mov     rcx, rdi; void *
0x18000323a  call    memcpy_0
0x18000323f  shr     ebx, 1
0x180003241  mov     eax, ebx
0x180003243  mov     [rbp+200h+var_280], eax
0x180003246  mov     [rdi+rbx*2], r13w
0x18000324b  jmp     loc_1800032DB
0x180003250  lock inc dword ptr [r15+24h]
0x180003255  jmp     loc_1800030CE
0x18000325a  movzx   ecx, word ptr [rdx]
0x18000325d  xor     r13d, r13d
0x180003260  mov     ebx, r13d
0x180003263  test    cx, cx
0x180003266  jz      loc_180003054
0x18000326c  nop     dword ptr [rax+00h]
0x180003270  and     ecx, 0FFDFh
0x180003276  imul    ebx, 65h ; 'e'
0x180003279  lea     rdx, [rdx+2]
0x18000327d  add     ebx, ecx
0x18000327f  movzx   ecx, word ptr [rdx]
0x180003282  test    cx, cx
0x180003285  jnz     short loc_180003270
0x180003287  jmp     loc_180003054
0x18000328c  lea     rdx, [rbx+80h]; unsigned int
0x180003293  mov     eax, 0FFFFFFFFh
0x180003298  cmp     rdx, rax
0x18000329b  ja      loc_1800033E9
0x1800032a1  lea     rcx, [rsp+300h+var_2B0]; this
0x1800032a6  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800032ab  test    al, al
0x1800032ad  jnz     loc_1800033F8
0x1800032b3  call    cs:__imp_GetLastError
0x1800032ba  nop     dword ptr [rax+rax+00h]
0x1800032bf  test    eax, eax
0x1800032c1  jle     short loc_1800032CD
0x1800032c3  movzx   eax, ax
0x1800032c6  or      eax, 80070000h
0x1800032cb  test    eax, eax
0x1800032cd  js      loc_1800033E9
0x1800032d3  mov     eax, [rbp+200h+var_280]
0x1800032d6  mov     rdi, qword ptr [rsp+300h+var_290]
0x1800032db  mov     [rsp+300h+phAlgorithm], r13
0x1800032e0  xorps   xmm0, xmm0
0x1800032e3  mov     [rsp+300h+phHash], r13
0x1800032e8  movups  xmmword ptr [rbp+200h+pbOutput], xmm0
0x1800032ec  movups  [rbp+200h+var_268], xmm0
0x1800032f0  test    rdi, rdi
0x1800032f3  jz      loc_1800033E9
0x1800032f9  lea     esi, [rax+rax]
0x1800032fc  test    esi, esi
0x1800032fe  jz      loc_1800033E9
0x180003304  xor     r9d, r9d; dwFlags
0x180003307  lea     rdx, pszAlgId; "SHA256"
0x18000330e  xor     r8d, r8d; pszImplementation
0x180003311  lea     rcx, [rsp+300h+phAlgorithm]; phAlgorithm
0x180003316  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000331d  nop     dword ptr [rax+rax+00h]
0x180003322  mov     ebx, eax
0x180003324  test    eax, eax
0x180003326  js      short loc_180003399
0x180003328  mov     rcx, [rsp+300h+phAlgorithm]; hAlgorithm
0x18000332d  lea     rdx, [rsp+300h+phHash]; phHash
0x180003332  mov     [rsp+30h], r13d; dwFlags
0x180003337  xor     r9d, r9d; cbHashObject
0x18000333a  mov     [rsp+300h+cbSecret], r13d; cbSecret
0x18000333f  xor     r8d, r8d; pbHashObject
0x180003342  mov     [rsp+300h+pbSecret], r13; pbSecret
0x180003347  call    cs:__imp_BCryptCreateHash
0x18000334e  nop     dword ptr [rax+rax+00h]
0x180003353  mov     ebx, eax
0x180003355  test    eax, eax
0x180003357  js      short loc_180003399
0x180003359  mov     rcx, [rsp+300h+phHash]; hHash
0x18000335e  xor     r9d, r9d; dwFlags
0x180003361  mov     r8d, esi; cbInput
0x180003364  mov     rdx, rdi; pbInput
0x180003367  call    cs:__imp_BCryptHashData
0x18000336e  nop     dword ptr [rax+rax+00h]
0x180003373  mov     ebx, eax
0x180003375  test    eax, eax
0x180003377  js      short loc_180003399
0x180003379  mov     rcx, [rsp+300h+phHash]; hHash
0x18000337e  lea     rdx, [rbp+200h+pbOutput]; pbOutput
0x180003382  xor     r9d, r9d; dwFlags
0x180003385  mov     r8d, 20h ; ' '; cbOutput
0x18000338b  call    cs:__imp_BCryptFinishHash
0x180003392  nop     dword ptr [rax+rax+00h]
0x180003397  mov     ebx, eax
0x180003399  mov     rcx, [rsp+300h+phAlgorithm]; hAlgorithm
0x18000339e  test    rcx, rcx
0x1800033a1  jz      short loc_1800033B1
0x1800033a3  xor     edx, edx; dwFlags
0x1800033a5  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800033ac  nop     dword ptr [rax+rax+00h]
0x1800033b1  mov     rcx, [rsp+300h+phHash]; hHash
0x1800033b6  test    rcx, rcx
0x1800033b9  jz      short loc_1800033C7
0x1800033bb  call    cs:__imp_BCryptDestroyHash
0x1800033c2  nop     dword ptr [rax+rax+00h]
0x1800033c7  or      ebx, 10000000h
0x1800033cd  jl      short loc_1800033E9
0x1800033cf  lea     rcx, [rbp+200h+pbOutput]; void *
0x1800033d3  call    ?HashBlob@@YAKPEBX_KK@Z; HashBlob(void const *,unsigned __int64,ulong)
0x1800033d8  lea     rcx, [rsp+300h+var_2B0]; this
0x1800033dd  mov     ebx, eax
0x1800033df  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800033e4  jmp     loc_180003054
0x1800033e9  lea     rcx, [rsp+300h+var_2B0]; this
0x1800033ee  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800033f3  jmp     loc_180003158
0x1800033f8  mov     rdi, qword ptr [rsp+300h+var_290]
0x1800033fd  jmp     loc_180003231
```
