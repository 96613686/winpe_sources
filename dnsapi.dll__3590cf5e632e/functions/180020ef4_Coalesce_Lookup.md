# Coalesce_Lookup

- ea: `0x180020ef4`
- end: `0x1800213f6`
- name: `Coalesce_Lookup`
- size: `1282`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180079dd4`

## callees

- `0x180020ef4`
- `0x1800213fc`
- `0x18002144c`
- `0x180029d80`
- `0x1800ccf00`
- `0x1800cd9b8`
- `0x1800dc9e0`
- `0x1800ddfa8`
- `0x1800de650`
- `0x1800dfdc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021020`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021333`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021020`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021333`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800210bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021360`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800210bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021360`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180021132`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180021132`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021383`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021383`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020f8a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020f8a`

## pseudocode

```c
__int64 __fastcall Coalesce_Lookup(__int64 a1, __int16 a2, int a3, int a4, __int64 *a5, __int64 *a6)
{
  char v6; // al
  int v8; // edx
  __int64 v11; // r14
  HANDLE ProcessHeap; // rax
  _QWORD *v13; // rax
  __int64 **v14; // rbx
  __int64 *v15; // r12
  unsigned int v16; // esi
  char *v17; // r15
  int v18; // eax
  signed __int32 v19; // eax
  signed __int32 v20; // ett
  const WCHAR *v21; // rcx
  unsigned int HashIndex; // eax
  __int64 v23; // rdi
  _QWORD *v24; // rcx
  __int64 *v25; // rbp
  __int64 v26; // rdi
  __int64 *v28; // rdi
  PCNZWCH *v29; // r14
  const WCHAR *lpString2; // rax
  __int64 **v31; // rax
  __int64 **v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // [rsp+58h] [rbp-40h]
  int v37; // [rsp+C0h] [rbp+28h]

  v6 = a2;
  v8 = a1;
  if ( (BYTE1(xmmword_1801119E0) & 2) != 0 )
  {
    if ( a6 )
      v33 = *a6;
    else
      v33 = -1;
    WPP_SF_SDDDqq(v33, v8, a3, v8, v6, a3, a4, (__int64)a5, v33);
  }
  if ( !a5 || !a6 || (v11 = *a6, (v34 = *a6) == 0) )
  {
    if ( (BYTE1(xmmword_1801119E0) & 2) != 0 )
      WPP_SF_(1033, 11, WPP_e7fac564e5f8353b8d950ea20f4a7fe5_Traceguids);
    v16 = 87;
    goto LABEL_23;
  }
  if ( !lpMem )
  {
    EnterCriticalSection(&stru_180112540);
    if ( !lpMem )
      lpMem = (LPVOID)Dns_Allocate(7976);
    LeaveCriticalSection(&stru_180112540);
    if ( !lpMem )
      goto LABEL_61;
  }
  ProcessHeap = g_hProcessHeap;
  if ( !g_hProcessHeap )
  {
    ProcessHeap = GetProcessHeap();
    g_hProcessHeap = ProcessHeap;
  }
  v13 = HeapAlloc(ProcessHeap, 8u, 0x58u);
  v14 = (__int64 **)v13;
  if ( !v13 )
  {
LABEL_61:
    v16 = 14;
    goto LABEL_23;
  }
  v13[1] = v13;
  v15 = v13 + 2;
  *v13 = v13;
  v16 = 0;
  v13[3] = v13 + 2;
  v13[2] = v13 + 2;
  v37 = 0;
  v17 = (char *)(v13 + 4);
  v13[4] = a1;
  *((_WORD *)v13 + 20) = a2;
  v18 = a4;
  if ( !a4 )
    v18 = a3;
  *((_DWORD *)v14 + 11) = v18;
  _m_prefetchw(&dword_18011253C);
  v19 = dword_18011253C;
  do
  {
    v20 = v19;
    v19 = _InterlockedCompareExchange(&dword_18011253C, v19, v19);
  }
  while ( v20 != v19 );
  v21 = *(const WCHAR **)v17;
  *((_DWORD *)v14 + 12) = v19;
  *((_DWORD *)v14 + 13) = a4 != 0;
  HashIndex = coalesceGetHashIndex(v21);
  v23 = HashIndex;
  *((_DWORD *)v14 + 17) = HashIndex;
  EnterCriticalSection(&stru_180112540);
  v24 = lpMem;
  v25 = (__int64 *)*((_QWORD *)lpMem + v23);
  if ( (BYTE1(xmmword_1801119E0) & 2) != 0 )
  {
    WPP_SF_qDDq(
      1033,
      12,
      (unsigned int)WPP_e7fac564e5f8353b8d950ea20f4a7fe5_Traceguids,
      (_DWORD)v14,
      *((_DWORD *)v14 + 12),
      v23,
      *((_QWORD *)lpMem + v23));
    v24 = lpMem;
  }
  if ( !v25 )
  {
    v24[v23] = v14;
    *((_DWORD *)v14 + 14) = 1;
    *((_DWORD *)v14 + 15) = 1;
    if ( (BYTE1(xmmword_1801119E0) & 2) != 0 )
      WPP_SF_(1033, 13, WPP_e7fac564e5f8353b8d950ea20f4a7fe5_Traceguids);
    goto LABEL_18;
  }
  v28 = v25;
  while ( 1 )
  {
    v29 = (PCNZWCH *)(v28 + 4);
    if ( v28 == (__int64 *)-32LL || !v17 )
      goto LABEL_33;
    lpString2 = *(const WCHAR **)v17;
    if ( *v29 )
      break;
    if ( !lpString2 )
      goto LABEL_32;
LABEL_33:
    v28 = (__int64 *)*v28;
    if ( v28 == v25 )
    {
      v31 = (__int64 **)v25[1];
      if ( *v31 != v25 )
        goto LABEL_62;
      *v14 = v25;
      v14[1] = (__int64 *)v31;
      *v31 = (__int64 *)v14;
      v25[1] = (__int64)v14;
      *((_DWORD *)v14 + 15) = 1;
      if ( (BYTE1(xmmword_1801119E0) & 2) != 0 )
        WPP_SF_(1033, 15, WPP_e7fac564e5f8353b8d950ea20f4a7fe5_Traceguids);
      goto LABEL_37;
    }
  }
  if ( !lpString2 || CompareStringW(0x409u, 1u, *v29, -1, lpString2, -1) != 2 )
    goto LABEL_33;
LABEL_32:
  if ( *((_WORD *)v28 + 20) != *((_WORD *)v17 + 4)
    || *((_DWORD *)v28 + 11) != *((_DWORD *)v17 + 3)
    || *((_DWORD *)v28 + 12) != *((_DWORD *)v17 + 4)
    || *((_DWORD *)v28 + 13) != *((_DWORD *)v17 + 5) )
  {
    goto LABEL_33;
  }
  if ( v28 )
  {
    v32 = (__int64 **)v28[3];
    if ( *v32 == v28 + 2 )
    {
      *v15 = (__int64)(v28 + 2);
      v15[1] = (__int64)v32;
      *v32 = v15;
      v28[3] = (__int64)v15;
      goto LABEL_44;
    }
LABEL_62:
    __fastfail(3u);
  }
LABEL_44:
  *((_DWORD *)v28 + 16) = 1;
  *((_DWORD *)v14 + 16) = 1;
  v37 = 1;
  if ( (BYTE1(xmmword_1801119E0) & 2) != 0 )
    WPP_SF_q(1033, 14, WPP_e7fac564e5f8353b8d950ea20f4a7fe5_Traceguids, v28);
LABEL_37:
  v11 = v34;
LABEL_18:
  v26 = 0;
  v14[9] = a5;
  if ( v37 )
  {
    v26 = v14[2][8];
    AddRefSendBlob(v26);
    v14[10] = (__int64 *)v26;
    if ( (BYTE1(xmmword_1801119E0) & 2) != 0 )
      WPP_SF_qq(1033, 16, (unsigned int)WPP_e7fac564e5f8353b8d950ea20f4a7fe5_Traceguids, (_DWORD)a5, v26);
  }
  else
  {
    AddRefSendBlob(v11);
    v14[10] = (__int64 *)v11;
    *(_QWORD *)(v11 + 8) = v14;
    *(_QWORD *)(v11 + 464) = off_1801112E0;
    if ( (BYTE1(xmmword_1801119E0) & 2) != 0 )
      WPP_SF_qq(1033, 17, (unsigned int)WPP_e7fac564e5f8353b8d950ea20f4a7fe5_Traceguids, (_DWORD)a5, v11);
  }
  LeaveCriticalSection(&stru_180112540);
  if ( v37 )
    *a6 = v26;
LABEL_23:
  if ( (BYTE1(xmmword_1801119E0) & 2) != 0 )
    WPP_SF_d(1033, 18, WPP_e7fac564e5f8353b8d950ea20f4a7fe5_Traceguids, v16);
  return v16;
}

```

## disassembly

```asm
0x180020ef4  mov     [rsp+arg_10], rbx
0x180020ef9  mov     [rsp+arg_8], dx
0x180020efe  mov     [rsp+arg_0], rcx
0x180020f03  push    rbp
0x180020f04  push    rsi
0x180020f05  push    rdi
0x180020f06  push    r12
0x180020f08  push    r13
0x180020f0a  push    r14
0x180020f0c  push    r15
0x180020f0e  sub     rsp, 60h
0x180020f12  movzx   eax, dx
0x180020f15  mov     edi, r9d
0x180020f18  mov     rdx, rcx
0x180020f1b  mov     ebp, r8d
0x180020f1e  mov     r13, [rsp+98h+arg_20]
0x180020f26  xor     r15d, r15d
0x180020f29  test    byte ptr cs:xmmword_1801119E0+1, 2
0x180020f30  mov     rbx, [rsp+98h+arg_28]
0x180020f38  jnz     loc_180021283
0x180020f3e  test    r13, r13
0x180020f41  jz      loc_180021217
0x180020f47  test    rbx, rbx
0x180020f4a  jz      loc_180021217
0x180020f50  mov     r14, [rbx]
0x180020f53  mov     [rsp+98h+var_40], r14
0x180020f58  test    r14, r14
0x180020f5b  jz      loc_180021217
0x180020f61  cmp     cs:lpMem, r15
0x180020f68  jz      loc_18002132C
0x180020f6e  mov     rax, cs:g_hProcessHeap
0x180020f75  test    rax, rax
0x180020f78  jz      loc_180021383
0x180020f7e  mov     edx, 8; dwFlags
0x180020f83  mov     rcx, rax; hHeap
0x180020f86  lea     r8d, [rdx+50h]; dwBytes
0x180020f8a  call    cs:__imp_HeapAlloc
0x180020f91  nop     dword ptr [rax+rax+00h]
0x180020f96  mov     rbx, rax
0x180020f99  test    rax, rax
0x180020f9c  jz      loc_180021379
0x180020fa2  mov     [rax+8], rax
0x180020fa6  lea     r12, [rax+10h]
0x180020faa  mov     [rax], rax
0x180020fad  mov     esi, r15d
0x180020fb0  mov     [r12+8], r12
0x180020fb5  test    edi, edi
0x180020fb7  mov     [r12], r12
0x180020fbb  mov     dword ptr [rsp+98h+arg_20], r15d
0x180020fc3  lea     r15, [rax+20h]
0x180020fc7  mov     rax, [rsp+98h+arg_0]
0x180020fcf  mov     [r15], rax
0x180020fd2  movzx   eax, [rsp+98h+arg_8]
0x180020fda  mov     [rbx+28h], ax
0x180020fde  mov     eax, edi
0x180020fe0  cmovz   eax, ebp
0x180020fe3  mov     [rbx+2Ch], eax
0x180020fe6  prefetchw byte ptr cs:dword_18011253C
0x180020fed  mov     eax, cs:dword_18011253C
0x180020ff3  mov     ecx, eax
0x180020ff5  lock cmpxchg cs:dword_18011253C, ecx
0x180020ffd  jnz     short loc_180020FF3
0x180020fff  mov     rcx, [r15]
0x180021002  mov     [rbx+30h], eax
0x180021005  xor     eax, eax
0x180021007  test    edi, edi
0x180021009  setnz   al
0x18002100c  mov     [rbx+34h], eax
0x18002100f  call    coalesceGetHashIndex
0x180021014  mov     edi, eax
0x180021016  lea     rcx, stru_180112540; lpCriticalSection
0x18002101d  mov     [rbx+44h], edi
0x180021020  call    cs:__imp_EnterCriticalSection
0x180021027  nop     dword ptr [rax+rax+00h]
0x18002102c  mov     rcx, cs:lpMem
0x180021033  mov     edx, 1; dwCmpFlags
0x180021038  mov     rbp, [rcx+rdi*8]
0x18002103c  test    byte ptr cs:xmmword_1801119E0+1, 2
0x180021043  jnz     loc_1800212B4
0x180021049  test    rbp, rbp
0x18002104c  jnz     loc_1800210F7
0x180021052  mov     [rcx+rdi*8], rbx
0x180021056  mov     [rbx+38h], edx
0x180021059  mov     [rbx+3Ch], edx
0x18002105c  test    byte ptr cs:xmmword_1801119E0+1, 2
0x180021063  jnz     loc_18002139B
0x180021069  mov     r15d, 1
0x18002106f  mov     ebp, dword ptr [rsp+98h+arg_20]
0x180021076  xor     edi, edi
0x180021078  mov     [rbx+48h], r13
0x18002107c  test    ebp, ebp
0x18002107e  jnz     loc_18002124C
0x180021084  mov     rcx, r14
0x180021087  call    AddRefSendBlob
0x18002108c  mov     [rbx+50h], r14
0x180021090  mov     [r14+8], rbx
0x180021094  mov     rax, cs:off_1801112E0
0x18002109b  mov     [r14+1D0h], rax
0x1800210a2  test    byte ptr cs:xmmword_1801119E0+1, 2
0x1800210a9  jnz     loc_1800212EE
0x1800210af  test    r15d, r15d
0x1800210b2  jz      short loc_1800210C7
0x1800210b4  lea     rcx, stru_180112540; lpCriticalSection
0x1800210bb  call    cs:__imp_LeaveCriticalSection
0x1800210c2  nop     dword ptr [rax+rax+00h]
0x1800210c7  test    ebp, ebp
0x1800210c9  jnz     loc_18002123C
0x1800210cf  test    byte ptr cs:xmmword_1801119E0+1, 2
0x1800210d6  jnz     loc_1800213D8
0x1800210dc  mov     rbx, [rsp+98h+arg_10]
0x1800210e4  mov     eax, esi
0x1800210e6  add     rsp, 60h
0x1800210ea  pop     r15
0x1800210ec  pop     r14
0x1800210ee  pop     r13
0x1800210f0  pop     r12
0x1800210f2  pop     rdi
0x1800210f3  pop     rsi
0x1800210f4  pop     rbp
0x1800210f5  retn
0x1800210f7  mov     rdi, rbp
0x1800210fa  lea     r14, [rdi+20h]
0x1800210fe  test    r14, r14
0x180021101  jz      short loc_18002114F
0x180021103  test    r15, r15
0x180021106  jz      short loc_18002114F
0x180021108  mov     r8, [r14]; lpString1
0x18002110b  mov     rax, [r15]
0x18002110e  test    r8, r8
0x180021111  jz      loc_18002122E
0x180021117  test    rax, rax
0x18002111a  jz      short loc_18002114F
0x18002111c  mov     [rsp+98h+cchCount2], 0FFFFFFFFh; cchCount2
0x180021124  or      r9d, 0FFFFFFFFh; cchCount1
0x180021128  mov     ecx, 409h; Locale
0x18002112d  mov     [rsp+98h+lpString2], rax; lpString2
0x180021132  call    cs:__imp_CompareStringW
0x180021139  nop     dword ptr [rax+rax+00h]
0x18002113e  cmp     eax, 2
0x180021141  jnz     short loc_18002114F
0x180021143  movzx   eax, word ptr [r15+8]
0x180021148  cmp     [r14+8], ax
0x18002114d  jz      short loc_180021197
0x18002114f  mov     rdi, [rdi]
0x180021152  cmp     rdi, rbp
0x180021155  jnz     loc_180021279
0x18002115b  mov     rax, [rbp+8]
0x18002115f  cmp     [rax], rbp
0x180021162  jnz     loc_1800213B6
0x180021168  mov     [rbx], rbp
0x18002116b  mov     [rbx+8], rax
0x18002116f  mov     [rax], rbx
0x180021172  mov     [rbp+8], rbx
0x180021176  mov     r15d, 1
0x18002117c  mov     [rbx+3Ch], r15d
0x180021180  test    byte ptr cs:xmmword_1801119E0+1, 2
0x180021187  jnz     loc_180021311
0x18002118d  mov     r14, [rsp+98h+var_40]
0x180021192  jmp     loc_18002106F
0x180021197  mov     eax, [r15+0Ch]
0x18002119b  cmp     [r14+0Ch], eax
0x18002119f  jnz     short loc_18002114F
0x1800211a1  mov     eax, [r15+10h]
0x1800211a5  cmp     [r14+10h], eax
0x1800211a9  jnz     short loc_18002114F
0x1800211ab  mov     eax, [r15+14h]
0x1800211af  cmp     [r14+14h], eax
0x1800211b3  jnz     short loc_18002114F
0x1800211b5  test    rdi, rdi
0x1800211b8  jz      short loc_1800211DB
0x1800211ba  lea     rax, [rdi+10h]
0x1800211be  mov     rcx, [rax+8]
0x1800211c2  cmp     [rcx], rax
0x1800211c5  jnz     loc_1800213B6
0x1800211cb  mov     [r12], rax
0x1800211cf  mov     [r12+8], rcx
0x1800211d4  mov     [rcx], r12
0x1800211d7  mov     [rax+8], r12
0x1800211db  mov     r15d, 1
0x1800211e1  mov     [rdi+40h], r15d
0x1800211e5  mov     [rbx+40h], r15d
0x1800211e9  mov     dword ptr [rsp+98h+arg_20], r15d
0x1800211f1  test    byte ptr cs:xmmword_1801119E0+1, 2
0x1800211f8  jz      short loc_18002118D
0x1800211fa  lea     edx, [r15+0Dh]
0x1800211fe  mov     ecx, 409h
0x180021203  mov     r9, rdi
0x180021206  lea     r8, WPP_e7fac564e5f8353b8d950ea20f4a7fe5_Traceguids
0x18002120d  call    WPP_SF_q
0x180021212  jmp     loc_18002118D
0x180021217  test    byte ptr cs:xmmword_1801119E0+1, 2
0x18002121e  jnz     loc_1800213BD
0x180021224  mov     esi, 57h ; 'W'
0x180021229  jmp     loc_1800210CF
0x18002122e  test    rax, rax
0x180021231  jz      loc_180021143
0x180021237  jmp     loc_18002114F
0x18002123c  mov     rax, [rsp+98h+arg_28]
0x180021244  mov     [rax], rdi
0x180021247  jmp     loc_1800210CF
0x18002124c  mov     rax, [rbx+10h]
0x180021250  mov     rdi, [rax+40h]
0x180021254  mov     rcx, rdi
0x180021257  call    AddRefSendBlob
0x18002125c  mov     [rbx+50h], rdi
0x180021260  test    byte ptr cs:xmmword_1801119E0+1, 2
0x180021267  jz      loc_1800210AF
0x18002126d  mov     edx, 10h
0x180021272  mov     [rsp+98h+lpString2], rdi
0x180021277  jmp     short loc_1800212F8
0x180021279  mov     edx, 1
0x18002127e  jmp     loc_1800210FA
0x180021283  test    rbx, rbx
0x180021286  jz      short loc_1800212AE
0x180021288  mov     rcx, [rbx]
0x18002128b  mov     [rsp+98h+var_58], rcx
0x180021290  mov     r9, rdx
0x180021293  mov     [rsp+98h+var_60], r13
0x180021298  mov     dword ptr [rsp+98h+var_68], edi
0x18002129c  mov     [rsp+98h+cchCount2], ebp
0x1800212a0  mov     dword ptr [rsp+98h+lpString2], eax
0x1800212a4  call    WPP_SF_SDDDqq
0x1800212a9  jmp     loc_180020F3E
0x1800212ae  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800212b2  jmp     short loc_18002128B
0x1800212b4  mov     eax, [rbx+30h]
0x1800212b7  lea     r8, WPP_e7fac564e5f8353b8d950ea20f4a7fe5_Traceguids
0x1800212be  mov     [rsp+98h+var_68], rbp
0x1800212c3  mov     edx, 0Ch
0x1800212c8  mov     [rsp+98h+cchCount2], edi
0x1800212cc  mov     ecx, 409h
0x1800212d1  mov     r9, rbx
0x1800212d4  mov     dword ptr [rsp+98h+lpString2], eax
0x1800212d8  call    WPP_SF_qDDq
0x1800212dd  mov     rcx, cs:lpMem
0x1800212e4  mov     edx, 1
0x1800212e9  jmp     loc_180021049
0x1800212ee  mov     edx, 11h
0x1800212f3  mov     [rsp+98h+lpString2], r14
0x1800212f8  mov     r9, r13
0x1800212fb  lea     r8, WPP_e7fac564e5f8353b8d950ea20f4a7fe5_Traceguids
0x180021302  mov     ecx, 409h
0x180021307  call    WPP_SF_qq
0x18002130c  jmp     loc_1800210AF
0x180021311  mov     edx, 0Fh
0x180021316  lea     r8, WPP_e7fac564e5f8353b8d950ea20f4a7fe5_Traceguids
0x18002131d  mov     ecx, 409h
0x180021322  call    WPP_SF_
0x180021327  jmp     loc_18002118D
0x18002132c  lea     rcx, stru_180112540; lpCriticalSection
0x180021333  call    cs:__imp_EnterCriticalSection
0x18002133a  nop     dword ptr [rax+rax+00h]
0x18002133f  cmp     cs:lpMem, r15
0x180021346  jnz     short loc_180021359
0x180021348  mov     ecx, 1F28h
0x18002134d  call    Dns_Allocate
0x180021352  mov     cs:lpMem, rax
0x180021359  lea     rcx, stru_180112540; lpCriticalSection
0x180021360  call    cs:__imp_LeaveCriticalSection
0x180021367  nop     dword ptr [rax+rax+00h]
0x18002136c  cmp     cs:lpMem, r15
0x180021373  jnz     loc_180020F6E
0x180021379  mov     esi, 0Eh
0x18002137e  jmp     loc_1800210CF
0x180021383  call    cs:__imp_GetProcessHeap
0x18002138a  nop     dword ptr [rax+rax+00h]
0x18002138f  mov     cs:g_hProcessHeap, rax
0x180021396  jmp     loc_180020F7E
0x18002139b  mov     edx, 0Dh
0x1800213a0  lea     r8, WPP_e7fac564e5f8353b8d950ea20f4a7fe5_Traceguids
0x1800213a7  mov     ecx, 409h
0x1800213ac  call    WPP_SF_
0x1800213b1  jmp     loc_180021069
0x1800213b6  mov     ecx, 3
0x1800213bb  int     29h; Win8: RtlFailFast(ecx)
0x1800213bd  mov     edx, 0Bh
0x1800213c2  lea     r8, WPP_e7fac564e5f8353b8d950ea20f4a7fe5_Traceguids
0x1800213c9  mov     ecx, 409h
0x1800213ce  call    WPP_SF_
0x1800213d3  jmp     loc_180021224
0x1800213d8  mov     edx, 12h
0x1800213dd  lea     r8, WPP_e7fac564e5f8353b8d950ea20f4a7fe5_Traceguids
0x1800213e4  mov     ecx, 409h
0x1800213e9  mov     r9d, esi
0x1800213ec  call    WPP_SF_d
0x1800213f1  jmp     loc_1800210DC
```
