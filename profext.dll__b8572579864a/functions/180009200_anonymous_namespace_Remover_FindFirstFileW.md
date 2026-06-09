# _anonymous_namespace_::Remover::FindFirstFileW

- ea: `0x180009200`
- end: `0x18000943a`
- name: `_anonymous_namespace_::Remover::FindFirstFileW`
- size: `570`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180009200`
- `0x180011e6e`
- `0x1800227f2`
- `0x180022830`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180009252`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800093ec`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180009252`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800093ec`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180009429`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180009429`

## pseudocode

```c
ULONG __fastcall anonymous_namespace_::Remover::FindFirstFileW(__int64 a1, const WCHAR *a2, _QWORD *a3, _OWORD *a4)
{
  DWORD LastError_0; // ebp
  HANDLE FirstFileW; // rdi
  _WIN32_FIND_DATAW *p_FindFileData; // rcx
  __int64 v10; // rax
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  char v23; // r12
  __int64 v24; // rdx
  const WCHAR *v25; // rax
  NTSTATUS v26; // ecx
  unsigned __int64 v27; // rdi
  __int64 v28; // r14
  __int64 (__fastcall *v29)(const WCHAR *, __int64, _QWORD, _QWORD); // rax
  _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-2A8h] BYREF

  LastError_0 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(a2, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
LABEL_2:
    p_FindFileData = &FindFileData;
    *a3 = FirstFileW;
    v10 = 4;
    do
    {
      v11 = *(_OWORD *)&p_FindFileData->ftLastAccessTime.dwHighDateTime;
      *a4 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
      v12 = *(_OWORD *)&p_FindFileData->nFileSizeLow;
      a4[1] = v11;
      v13 = *(_OWORD *)&p_FindFileData->cFileName[2];
      a4[2] = v12;
      v14 = *(_OWORD *)&p_FindFileData->cFileName[10];
      a4[3] = v13;
      v15 = *(_OWORD *)&p_FindFileData->cFileName[18];
      a4[4] = v14;
      v16 = *(_OWORD *)&p_FindFileData->cFileName[26];
      a4[5] = v15;
      v17 = *(_OWORD *)&p_FindFileData->cFileName[34];
      p_FindFileData = (_WIN32_FIND_DATAW *)((char *)p_FindFileData + 128);
      a4[6] = v16;
      a4[7] = v17;
      a4 += 8;
      --v10;
    }
    while ( v10 );
    v18 = *(_OWORD *)&p_FindFileData->ftLastAccessTime.dwHighDateTime;
    *a4 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
    v19 = *(_OWORD *)&p_FindFileData->nFileSizeLow;
    a4[1] = v18;
    v20 = *(_OWORD *)&p_FindFileData->cFileName[2];
    a4[2] = v19;
    v21 = *(_OWORD *)&p_FindFileData->cFileName[10];
    a4[3] = v20;
    a4[4] = v21;
    return LastError_0;
  }
  LastError_0 = GetLastError_0();
  if ( a2 )
  {
    v23 = 1;
    v24 = 0x8000;
    v25 = a2;
    do
    {
      if ( !*v25 )
        break;
      ++v25;
      --v24;
    }
    while ( v24 );
    v26 = v24 == 0 ? 0xC000000D : 0;
    v27 = (0x8000 - v24) & -(__int64)(v24 != 0);
    if ( v24 )
    {
      if ( v27 > 2 && (v28 = v27, a2[v27 - 1] == 42) && a2[v27 - 2] == 92 )
      {
        a2[v27 - 2] = 0;
      }
      else
      {
        v23 = 0;
        v28 = v27;
      }
      v29 = *(__int64 (__fastcall **)(const WCHAR *, __int64, _QWORD, _QWORD))(a1 + 8);
      if ( v29 )
        LastError_0 = v29(a2, 3, LastError_0, *(_QWORD *)(a1 + 16));
      if ( v23 )
      {
        a2[v27 - 2] = 92;
        *(_DWORD *)&a2[v28 - 1] = 42;
      }
      if ( LastError_0 )
        return LastError_0;
      FirstFileW = FindFirstFileW(a2, &FindFileData);
      if ( FirstFileW == (HANDLE)-1LL )
      {
        LastError_0 = GetLastError_0();
        if ( LastError_0 )
          return LastError_0;
      }
      goto LABEL_2;
    }
  }
  else
  {
    v26 = -1073741811;
  }
  return RtlNtStatusToDosErrorNoTeb(v26);
}

```

## disassembly

```asm
0x180009200  push    rbx
0x180009202  push    rbp
0x180009203  push    rsi
0x180009204  push    rdi
0x180009205  push    r12
0x180009207  push    r13
0x180009209  push    r14
0x18000920b  push    r15
0x18000920d  sub     rsp, 2A8h
0x180009214  mov     rax, cs:__security_cookie
0x18000921b  xor     rax, rsp
0x18000921e  mov     [rsp+2E8h+var_58], rax
0x180009226  mov     [rsp+2E8h+var_2B8], r8
0x18000922b  mov     rsi, rdx
0x18000922e  mov     r13, rcx
0x180009231  xor     eax, eax
0x180009233  xor     edx, edx; Val
0x180009235  lea     rcx, [rsp+2E8h+FindFileData]; void *
0x18000923a  mov     r8d, 250h; Size
0x180009240  mov     ebp, eax
0x180009242  mov     rbx, r9
0x180009245  call    memset_0
0x18000924a  lea     rdx, [rsp+2E8h+FindFileData]; lpFindFileData
0x18000924f  mov     rcx, rsi; lpFileName
0x180009252  call    cs:__imp_FindFirstFileW
0x180009259  nop     dword ptr [rax+rax+00h]
0x18000925e  mov     rdi, rax
0x180009261  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009265  jz      loc_180009317
0x18000926b  mov     rax, [rsp+2E8h+var_2B8]
0x180009270  lea     rcx, [rsp+2E8h+FindFileData]
0x180009275  mov     [rax], rdi
0x180009278  mov     eax, 4
0x18000927d  lea     edx, [rax+7Ch]
0x180009280  movups  xmm0, xmmword ptr [rcx]
0x180009283  movups  xmm1, xmmword ptr [rcx+10h]
0x180009287  movups  xmmword ptr [rbx], xmm0
0x18000928a  movups  xmm0, xmmword ptr [rcx+20h]
0x18000928e  movups  xmmword ptr [rbx+10h], xmm1
0x180009292  movups  xmm1, xmmword ptr [rcx+30h]
0x180009296  movups  xmmword ptr [rbx+20h], xmm0
0x18000929a  movups  xmm0, xmmword ptr [rcx+40h]
0x18000929e  movups  xmmword ptr [rbx+30h], xmm1
0x1800092a2  movups  xmm1, xmmword ptr [rcx+50h]
0x1800092a6  movups  xmmword ptr [rbx+40h], xmm0
0x1800092aa  movups  xmm0, xmmword ptr [rcx+60h]
0x1800092ae  movups  xmmword ptr [rbx+50h], xmm1
0x1800092b2  movups  xmm1, xmmword ptr [rcx+70h]
0x1800092b6  add     rcx, rdx
0x1800092b9  movups  xmmword ptr [rbx+60h], xmm0
0x1800092bd  movups  xmmword ptr [rbx+70h], xmm1
0x1800092c1  add     rbx, rdx
0x1800092c4  sub     rax, 1
0x1800092c8  jnz     short loc_180009280
0x1800092ca  movups  xmm0, xmmword ptr [rcx]
0x1800092cd  movups  xmm1, xmmword ptr [rcx+10h]
0x1800092d1  movups  xmmword ptr [rbx], xmm0
0x1800092d4  movups  xmm0, xmmword ptr [rcx+20h]
0x1800092d8  movups  xmmword ptr [rbx+10h], xmm1
0x1800092dc  movups  xmm1, xmmword ptr [rcx+30h]
0x1800092e0  movups  xmmword ptr [rbx+20h], xmm0
0x1800092e4  movups  xmm0, xmmword ptr [rcx+40h]
0x1800092e8  movups  xmmword ptr [rbx+30h], xmm1
0x1800092ec  movups  xmmword ptr [rbx+40h], xmm0
0x1800092f0  mov     eax, ebp
0x1800092f2  mov     rcx, [rsp+2E8h+var_58]
0x1800092fa  xor     rcx, rsp; StackCookie
0x1800092fd  call    __security_check_cookie
0x180009302  add     rsp, 2A8h
0x180009309  pop     r15
0x18000930b  pop     r14
0x18000930d  pop     r13
0x18000930f  pop     r12
0x180009311  pop     rdi
0x180009312  pop     rsi
0x180009313  pop     rbp
0x180009314  pop     rbx
0x180009315  retn
0x180009317  call    GetLastError_0
0x18000931c  xor     r9d, r9d
0x18000931f  mov     ebp, eax
0x180009321  test    rsi, rsi
0x180009324  jz      loc_180009424
0x18000932a  mov     r8d, 8000h
0x180009330  lea     r12d, [r9+1]
0x180009334  mov     edx, r8d
0x180009337  mov     rax, rsi
0x18000933a  cmp     [rax], r9w
0x18000933e  jz      short loc_180009349
0x180009340  add     rax, 2
0x180009344  sub     rdx, r12
0x180009347  jnz     short loc_18000933A
0x180009349  mov     rax, rdx
0x18000934c  neg     rax
0x18000934f  mov     rax, rdx
0x180009352  sbb     ecx, ecx
0x180009354  sub     r8, rdx
0x180009357  not     ecx
0x180009359  and     ecx, 0C000000Dh
0x18000935f  neg     rax
0x180009362  sbb     rdi, rdi
0x180009365  and     rdi, r8
0x180009368  test    rdx, rdx
0x18000936b  jz      loc_180009429
0x180009371  mov     ecx, 2Ah ; '*'
0x180009376  lea     edx, [rcx+32h]
0x180009379  cmp     rdi, 2
0x18000937d  jbe     short loc_180009396
0x18000937f  lea     r14, [rdi+rdi]
0x180009383  cmp     [r14+rsi-2], cx
0x180009389  jnz     short loc_180009396
0x18000938b  cmp     [rsi+rdi*2-4], dx
0x180009390  jz      loc_180009419
0x180009396  mov     r12b, r9b
0x180009399  lea     r14, [rdi+rdi]
0x18000939d  mov     rax, [r13+8]
0x1800093a1  mov     r15, 0FFFFFFFFFFFFFFFEh
0x1800093a8  test    rax, rax
0x1800093ab  jz      short loc_1800093C6
0x1800093ad  mov     r9, [r13+10h]
0x1800093b1  lea     edx, [r15+5]
0x1800093b5  mov     r8d, ebp
0x1800093b8  mov     rcx, rsi
0x1800093bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093c0  mov     ebp, eax
0x1800093c2  lea     edx, [r15+5Eh]
0x1800093c6  test    r12b, r12b
0x1800093c9  jz      short loc_1800093DC
0x1800093cb  lea     rax, [r15+rdi]
0x1800093cf  mov     [rsi+rax*2], dx
0x1800093d3  mov     dword ptr [r14+rsi-2], 2Ah ; '*'
0x1800093dc  test    ebp, ebp
0x1800093de  jnz     loc_1800092F0
0x1800093e4  lea     rdx, [rsp+2E8h+FindFileData]; lpFindFileData
0x1800093e9  mov     rcx, rsi; lpFileName
0x1800093ec  call    cs:__imp_FindFirstFileW
0x1800093f3  nop     dword ptr [rax+rax+00h]
0x1800093f8  mov     rdi, rax
0x1800093fb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800093ff  jnz     loc_18000926B
0x180009405  call    GetLastError_0
0x18000940a  mov     ebp, eax
0x18000940c  test    eax, eax
0x18000940e  jz      loc_18000926B
0x180009414  jmp     loc_1800092F0
0x180009419  mov     [rsi+rdi*2-4], r9w
0x18000941f  jmp     loc_18000939D
0x180009424  mov     ecx, 0C000000Dh; Status
0x180009429  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180009430  nop     dword ptr [rax+rax+00h]
0x180009435  jmp     loc_1800092F2
```
