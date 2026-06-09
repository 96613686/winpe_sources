# RtlpFcUpdateLocalConfiguration

- ea: `0x1800845f8`
- end: `0x180084828`
- name: `RtlpFcUpdateLocalConfiguration`
- size: `560`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180083f80`
- `0x1800840a0`

## callees

- `0x180017e90`
- `0x1800183a0`
- `0x1800845f8`
- `0x180084830`
- `0x1800848fc`
- `0x1800849a0`
- `0x180084a30`
- `0x180084ef0`
- `0x18015e4b0`
- `0x18015e810`
- `0x180161080`
- `0x180162000`
- `0x18016e774`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall RtlpFcUpdateLocalConfiguration(__int64 a1, unsigned __int64 a2, char a3)
{
  __int64 *v6; // rdi
  unsigned __int64 v7; // rdx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rsi
  int v11; // eax
  __int64 j; // rdi
  __int64 k; // rdi
  HANDLE v14; // rcx
  __int64 v16; // rtt
  __int64 *v17; // rdx
  unsigned int i; // r8d
  unsigned int v19; // eax
  __int64 v20; // r8
  _DWORD v21[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v22; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v23; // [rsp+50h] [rbp-B0h]
  HANDLE v24[14]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v25[96]; // [rsp+D0h] [rbp-30h] BYREF

  v22 = 0;
  v23 = 0;
  memset_thunk_772440563353939046(v24, 0, 0x68u);
  memset_thunk_772440563353939046(v25, 0, 0x60u);
  if ( byte_1801CA908 )
  {
    v8 = -1073741058;
    goto LABEL_17;
  }
  if ( a3 )
  {
    RtlAcquireSRWLockExclusive(a1);
  }
  else if ( !(unsigned __int8)RtlTryAcquireSRWLockExclusive(a1) )
  {
    v8 = -1073741608;
    goto LABEL_17;
  }
  v6 = (__int64 *)(a1 + 8);
  if ( *(_QWORD *)(a1 + 8 + 8 * (*(_QWORD *)(a1 + 8) & 1LL) + 216) >= a2 )
  {
    v8 = 0;
  }
  else
  {
    v21[0] = 0;
    while ( 1 )
    {
      _m_prefetchw(v6);
      v7 = *v6 & 1 | ((*v6 & 0xFFFFFFFFFFFFFFFEuLL) + 2);
      if ( v7 < 2 )
        __fastfail(0xEu);
      v16 = *v6;
      if ( v16 == _InterlockedCompareExchange64(v6, v7, *v6) )
        break;
      RtlBackoff(v21);
    }
    v22 = 0;
    v23 = 0;
    v17 = &v6[12 * (v7 & 1) + 3];
    for ( i = 0; i < 4; i = v20 + 1 )
    {
      v19 = RtlpFcSectionTypeToBufferType(i, v17);
      *((_QWORD *)&v22 + v20) = v17[3 * v19];
    }
    RtlpFcBufferManagerDereferenceBuffers(a1 + 8);
    v8 = NtQuerySystemInformationEx(211, &v22, 32, v24, 104, 0);
    if ( v8 >= 0 )
    {
      v10 = 0;
      while ( 1 )
      {
        v11 = RtlpFcSectionTypeToBufferType((unsigned int)v10, v9);
        v8 = RtlpFcMapSingleBuffer(&v24[3 * v10 + 1], &v25[24 * v11]);
        if ( v8 < 0 )
          break;
        v10 = (unsigned int)(v10 + 1);
        if ( (unsigned int)v10 >= 4 )
        {
          RtlpFcBufferManagerUpdateBuffers(a1 + 8, v24[0], v25);
          break;
        }
      }
    }
  }
  RtlReleaseSRWLockExclusive(a1);
LABEL_17:
  for ( j = 0; j != 4; ++j )
  {
    if ( *(_QWORD *)&v25[24 * j + 8] )
      NtUnmapViewOfSection(-1);
  }
  for ( k = 0; k != 4; ++k )
  {
    v14 = v24[3 * k + 2];
    if ( v14 )
      NtClose(v14);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800845f8  push    rbp
0x1800845fa  push    rbx
0x1800845fb  push    rsi
0x1800845fc  push    rdi
0x1800845fd  push    r14
0x1800845ff  push    r15
0x180084601  lea     rbp, [rsp-48h]
0x180084606  sub     rsp, 148h
0x18008460d  mov     rax, cs:__security_cookie
0x180084614  xor     rax, rsp
0x180084617  mov     [rbp+70h+var_40], rax
0x18008461b  xorps   xmm0, xmm0
0x18008461e  mov     rsi, rdx
0x180084621  xor     edx, edx; Val
0x180084623  mov     bl, r8b
0x180084626  mov     r14, rcx
0x180084629  lea     rcx, [rsp+170h+var_110]; void *
0x18008462e  movups  [rsp+170h+var_130], xmm0
0x180084633  lea     r8d, [rdx+68h]; Size
0x180084637  movups  [rsp+170h+var_120], xmm0
0x18008463c  call    memset$thunk$772440563353939046
0x180084641  xor     edx, edx; Val
0x180084643  lea     rcx, [rbp+70h+var_A0]; void *
0x180084647  lea     r8d, [rdx+60h]; Size
0x18008464b  call    memset$thunk$772440563353939046
0x180084650  cmp     cs:byte_1801CA908, 0
0x180084657  jnz     short loc_1800846C9
0x180084659  mov     rcx, r14
0x18008465c  test    bl, bl
0x18008465e  jz      short loc_1800846B3
0x180084660  call    RtlAcquireSRWLockExclusive
0x180084665  mov     r15b, 1
0x180084668  lea     rdi, [r14+8]
0x18008466c  mov     rax, [rdi]
0x18008466f  and     eax, 1
0x180084672  cmp     [rdi+rax*8+0D8h], rsi
0x18008467a  jnb     loc_1800847C5
0x180084680  mov     [rsp+170h+var_140], 0
0x180084688  prefetchw byte ptr [rdi]
0x18008468b  mov     rax, [rdi]
0x18008468e  mov     rcx, rax
0x180084691  mov     rdx, rax
0x180084694  and     rdx, 0FFFFFFFFFFFFFFFEh
0x180084698  and     ecx, 1
0x18008469b  add     rdx, 2
0x18008469f  or      rdx, rcx
0x1800846a2  cmp     rdx, 2
0x1800846a6  jnb     loc_1800847C9
0x1800846ac  mov     ecx, 0Eh
0x1800846b1  int     29h; Win8: RtlFailFast(ecx)
0x1800846b3  call    RtlTryAcquireSRWLockExclusive
0x1800846b8  mov     r15b, al
0x1800846bb  test    al, al
0x1800846bd  jnz     short loc_180084668
0x1800846bf  mov     ebx, 0C00000D8h
0x1800846c4  jmp     loc_180084764
0x1800846c9  mov     ebx, 0C00002FEh
0x1800846ce  jmp     loc_180084764
0x1800846d3  mov     rcx, rdi
0x1800846d6  call    RtlpFcBufferManagerDereferenceBuffers
0x1800846db  lea     r9, [rsp+170h+var_110]
0x1800846e0  mov     [rsp+170h+var_148], 0
0x1800846e9  mov     r8d, 20h ; ' '
0x1800846ef  mov     [rsp+170h+var_150], 68h ; 'h'
0x1800846f7  lea     rdx, [rsp+170h+var_130]
0x1800846fc  mov     ecx, 0D3h
0x180084701  call    NtQuerySystemInformationEx
0x180084706  mov     ebx, eax
0x180084708  test    eax, eax
0x18008470a  js      short loc_180084757
0x18008470c  xor     esi, esi
0x18008470e  mov     ecx, esi
0x180084710  call    RtlpFcSectionTypeToBufferType
0x180084715  mov     ecx, eax
0x180084717  lea     rdx, [rbp+70h+var_A0]
0x18008471b  lea     rax, [rcx+rcx*2]
0x18008471f  lea     rdx, [rdx+rax*8]
0x180084723  lea     rax, [rsp+170h+var_108]
0x180084728  lea     rcx, [rsi+rsi*2]
0x18008472c  lea     rcx, [rax+rcx*8]
0x180084730  call    RtlpFcMapSingleBuffer
0x180084735  mov     ebx, eax
0x180084737  test    eax, eax
0x180084739  js      short loc_180084757
0x18008473b  inc     esi
0x18008473d  cmp     esi, 4
0x180084740  jb      short loc_18008470E
0x180084742  test    eax, eax
0x180084744  js      short loc_180084757
0x180084746  mov     rdx, [rsp+170h+var_110]
0x18008474b  lea     r8, [rbp+70h+var_A0]
0x18008474f  mov     rcx, rdi
0x180084752  call    RtlpFcBufferManagerUpdateBuffers
0x180084757  test    r15b, r15b
0x18008475a  jz      short loc_180084764
0x18008475c  mov     rcx, r14
0x18008475f  call    RtlReleaseSRWLockExclusive
0x180084764  xor     edi, edi
0x180084766  lea     rax, [rdi+rdi*2]
0x18008476a  mov     rdx, [rbp+rax*8+70h+var_98]
0x18008476f  test    rdx, rdx
0x180084772  jnz     short loc_1800847BA
0x180084774  inc     rdi
0x180084777  cmp     rdi, 4
0x18008477b  jnz     short loc_180084766
0x18008477d  xor     edi, edi
0x18008477f  lea     rax, [rdi+rdi*2]
0x180084783  mov     rcx, [rsp+rax*8+170h+Handle]; Handle
0x180084788  test    rcx, rcx
0x18008478b  jz      short loc_180084792
0x18008478d  call    NtClose
0x180084792  inc     rdi
0x180084795  cmp     rdi, 4
0x180084799  jnz     short loc_18008477F
0x18008479b  mov     eax, ebx
0x18008479d  mov     rcx, [rbp+70h+var_40]
0x1800847a1  xor     rcx, rsp; StackCookie
0x1800847a4  call    __security_check_cookie
0x1800847a9  add     rsp, 148h
0x1800847b0  pop     r15
0x1800847b2  pop     r14
0x1800847b4  pop     rdi
0x1800847b5  pop     rsi
0x1800847b6  pop     rbx
0x1800847b7  pop     rbp
0x1800847b8  retn
0x1800847ba  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800847be  call    NtUnmapViewOfSection
0x1800847c3  jmp     short loc_180084774
0x1800847c5  xor     ebx, ebx
0x1800847c7  jmp     short loc_180084757
0x1800847c9  mov     ecx, edx
0x1800847cb  lock cmpxchg [rdi], rdx
0x1800847d0  jnz     short loc_180084819
0x1800847d2  and     ecx, 1
0x1800847d5  xorps   xmm0, xmm0
0x1800847d8  movups  [rsp+170h+var_130], xmm0
0x1800847dd  movups  [rsp+170h+var_120], xmm0
0x1800847e2  lea     rdx, [rcx+rcx*2]
0x1800847e6  shl     rdx, 5
0x1800847ea  add     rdx, 18h
0x1800847ee  add     rdx, rdi
0x1800847f1  xor     r8d, r8d
0x1800847f4  mov     ecx, r8d
0x1800847f7  call    RtlpFcSectionTypeToBufferType
0x1800847fc  mov     ecx, eax
0x1800847fe  lea     rax, [rcx+rcx*2]
0x180084802  mov     rax, [rdx+rax*8]
0x180084806  mov     qword ptr [rsp+r8*8+170h+var_130], rax
0x18008480b  inc     r8d
0x18008480e  cmp     r8d, 4
0x180084812  jb      short loc_1800847F4
0x180084814  jmp     loc_1800846D3
0x180084819  lea     rcx, [rsp+170h+var_140]
0x18008481e  call    RtlBackoff
0x180084823  jmp     loc_180084688
```
