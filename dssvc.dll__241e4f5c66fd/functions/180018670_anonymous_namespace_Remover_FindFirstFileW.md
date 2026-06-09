# _anonymous_namespace_::Remover::FindFirstFileW

- ea: `0x180018670`
- end: `0x18001882d`
- name: `_anonymous_namespace_::Remover::FindFirstFileW`
- size: `445`
- prototype: `ULONG __fastcall(__int64, const WCHAR *, _QWORD *, _OWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180018670`
- `0x180018860`
- `0x18001889c`
- `0x18001b30a`
- `0x18001b340`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018777`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018777`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800186f2`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800186f2`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800186be`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180018768`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800186be`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180018768`

## pseudocode

```c
ULONG __fastcall anonymous_namespace_::Remover::FindFirstFileW(__int64 a1, const WCHAR *a2, _QWORD *a3, _OWORD *a4)
{
  DWORD LastError; // ebp
  HANDLE FirstFileW; // rsi
  unsigned __int64 v10; // rdx
  NTSTATUS v11; // eax
  unsigned int v12; // r11d
  unsigned __int64 v14; // rsi
  char v15; // r14
  DWORD v16; // eax
  __int64 v17; // rcx
  _WIN32_FIND_DATAW *p_FindFileData; // rax
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  unsigned __int64 v30; // [rsp+20h] [rbp-2B8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-2A8h] BYREF

  LastError = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(a2, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
    goto LABEL_14;
  GetLastError();
  v30 = 0;
  v11 = RtlStringCchLengthW(a2, v10, &v30);
  if ( v11 < 0 )
    return RtlNtStatusToDosErrorNoTeb(v11);
  v14 = v30;
  if ( v30 > 2 && a2[v30 - 1] == 42 && a2[v30 - 2] == 92 )
  {
    v15 = 1;
    a2[v30 - 2] = 0;
  }
  else
  {
    v15 = 0;
  }
  v16 = anonymous_namespace_::Remover::Report(a1, a2, 3, v12);
  LastError = v16;
  if ( v15 )
  {
    *(_DWORD *)&a2[v14 - 2] = 2752604;
    a2[v14] = 0;
  }
  if ( !v16 )
  {
    FirstFileW = FindFirstFileW(a2, &FindFileData);
    if ( FirstFileW != (HANDLE)-1LL || (LastError = GetLastError()) == 0 )
    {
LABEL_14:
      v17 = 4;
      *a3 = FirstFileW;
      p_FindFileData = &FindFileData;
      do
      {
        v19 = *(_OWORD *)&p_FindFileData->ftLastAccessTime.dwHighDateTime;
        *a4 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
        v20 = *(_OWORD *)&p_FindFileData->nFileSizeLow;
        a4[1] = v19;
        v21 = *(_OWORD *)&p_FindFileData->cFileName[2];
        a4[2] = v20;
        v22 = *(_OWORD *)&p_FindFileData->cFileName[10];
        a4[3] = v21;
        v23 = *(_OWORD *)&p_FindFileData->cFileName[18];
        a4[4] = v22;
        v24 = *(_OWORD *)&p_FindFileData->cFileName[26];
        a4[5] = v23;
        v25 = *(_OWORD *)&p_FindFileData->cFileName[34];
        p_FindFileData = (_WIN32_FIND_DATAW *)((char *)p_FindFileData + 128);
        a4[6] = v24;
        a4[7] = v25;
        a4 += 8;
        --v17;
      }
      while ( v17 );
      v26 = *(_OWORD *)&p_FindFileData->ftLastAccessTime.dwHighDateTime;
      *a4 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
      v27 = *(_OWORD *)&p_FindFileData->nFileSizeLow;
      a4[1] = v26;
      v28 = *(_OWORD *)&p_FindFileData->cFileName[2];
      a4[2] = v27;
      v29 = *(_OWORD *)&p_FindFileData->cFileName[10];
      a4[3] = v28;
      a4[4] = v29;
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180018670  push    rbx
0x180018672  push    rbp
0x180018673  push    rsi
0x180018674  push    rdi
0x180018675  push    r12
0x180018677  push    r13
0x180018679  push    r14
0x18001867b  push    r15
0x18001867d  sub     rsp, 298h
0x180018684  mov     rax, cs:__security_cookie
0x18001868b  xor     rax, rsp
0x18001868e  mov     [rsp+2D8h+var_58], rax
0x180018696  mov     r15, r8
0x180018699  mov     rdi, rdx
0x18001869c  mov     r12, rcx
0x18001869f  xor     edx, edx; Val
0x1800186a1  mov     r8d, 250h; Size
0x1800186a7  lea     rcx, [rsp+2D8h+FindFileData]; void *
0x1800186ac  mov     rbx, r9
0x1800186af  xor     ebp, ebp
0x1800186b1  call    memset_0
0x1800186b6  lea     rdx, [rsp+2D8h+FindFileData]; lpFindFileData
0x1800186bb  mov     rcx, rdi; lpFileName
0x1800186be  call    cs:__imp_FindFirstFileW
0x1800186c4  mov     rsi, rax
0x1800186c7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800186cb  jnz     loc_180018787
0x1800186d1  call    cs:__imp_GetLastError
0x1800186d7  lea     r8, [rsp+2D8h+var_2B8]; unsigned __int64 *
0x1800186dc  mov     [rsp+2D8h+var_2B8], rbp
0x1800186e1  mov     rcx, rdi; unsigned __int16 *
0x1800186e4  mov     r11d, eax
0x1800186e7  call    ?RtlStringCchLengthW@@YAJPEBG_KPEA_K@Z; RtlStringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800186ec  test    eax, eax
0x1800186ee  jns     short loc_1800186FD
0x1800186f0  mov     ecx, eax; Status
0x1800186f2  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800186f8  jmp     loc_180018809
0x1800186fd  mov     rsi, [rsp+2D8h+var_2B8]
0x180018702  mov     eax, 5Ch ; '\'
0x180018707  lea     r13d, [rax-32h]
0x18001870b  cmp     rsi, 2
0x18001870f  jbe     short loc_18001872C
0x180018711  cmp     [rdi+rsi*2-2], r13w
0x180018717  jnz     short loc_18001872C
0x180018719  cmp     [rdi+rsi*2-4], ax
0x18001871e  jnz     short loc_18001872C
0x180018720  xor     eax, eax
0x180018722  mov     r14b, 1
0x180018725  mov     [rdi+rsi*2-4], ax
0x18001872a  jmp     short loc_18001872F
0x18001872c  xor     r14b, r14b
0x18001872f  mov     r9d, r11d
0x180018732  mov     r8d, 3
0x180018738  mov     rdx, rdi
0x18001873b  mov     rcx, r12
0x18001873e  call    _anonymous_namespace___Remover__Report
0x180018743  mov     ebp, eax
0x180018745  test    r14b, r14b
0x180018748  jz      short loc_180018758
0x18001874a  xor     edx, edx
0x18001874c  mov     dword ptr [rdi+rsi*2-4], 2A005Ch
0x180018754  mov     [rdi+rsi*2], dx
0x180018758  test    eax, eax
0x18001875a  jnz     loc_180018807
0x180018760  lea     rdx, [rsp+2D8h+FindFileData]; lpFindFileData
0x180018765  mov     rcx, rdi; lpFileName
0x180018768  call    cs:__imp_FindFirstFileW
0x18001876e  mov     rsi, rax
0x180018771  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180018775  jnz     short loc_180018787
0x180018777  call    cs:__imp_GetLastError
0x18001877d  mov     ebp, eax
0x18001877f  test    eax, eax
0x180018781  jnz     loc_180018807
0x180018787  mov     ecx, 4
0x18001878c  mov     [r15], rsi
0x18001878f  lea     rax, [rsp+2D8h+FindFileData]
0x180018794  lea     edx, [rcx+7Ch]
0x180018797  movups  xmm0, xmmword ptr [rax]
0x18001879a  movups  xmm1, xmmword ptr [rax+10h]
0x18001879e  movups  xmmword ptr [rbx], xmm0
0x1800187a1  movups  xmm0, xmmword ptr [rax+20h]
0x1800187a5  movups  xmmword ptr [rbx+10h], xmm1
0x1800187a9  movups  xmm1, xmmword ptr [rax+30h]
0x1800187ad  movups  xmmword ptr [rbx+20h], xmm0
0x1800187b1  movups  xmm0, xmmword ptr [rax+40h]
0x1800187b5  movups  xmmword ptr [rbx+30h], xmm1
0x1800187b9  movups  xmm1, xmmword ptr [rax+50h]
0x1800187bd  movups  xmmword ptr [rbx+40h], xmm0
0x1800187c1  movups  xmm0, xmmword ptr [rax+60h]
0x1800187c5  movups  xmmword ptr [rbx+50h], xmm1
0x1800187c9  movups  xmm1, xmmword ptr [rax+70h]
0x1800187cd  add     rax, rdx
0x1800187d0  movups  xmmword ptr [rbx+60h], xmm0
0x1800187d4  movups  xmmword ptr [rbx+70h], xmm1
0x1800187d8  add     rbx, rdx
0x1800187db  sub     rcx, 1
0x1800187df  jnz     short loc_180018797
0x1800187e1  movups  xmm0, xmmword ptr [rax]
0x1800187e4  movups  xmm1, xmmword ptr [rax+10h]
0x1800187e8  movups  xmmword ptr [rbx], xmm0
0x1800187eb  movups  xmm0, xmmword ptr [rax+20h]
0x1800187ef  movups  xmmword ptr [rbx+10h], xmm1
0x1800187f3  movups  xmm1, xmmword ptr [rax+30h]
0x1800187f7  movups  xmmword ptr [rbx+20h], xmm0
0x1800187fb  movups  xmm0, xmmword ptr [rax+40h]
0x1800187ff  movups  xmmword ptr [rbx+30h], xmm1
0x180018803  movups  xmmword ptr [rbx+40h], xmm0
0x180018807  mov     eax, ebp
0x180018809  mov     rcx, [rsp+2D8h+var_58]
0x180018811  xor     rcx, rsp; StackCookie
0x180018814  call    __security_check_cookie
0x180018819  add     rsp, 298h
0x180018820  pop     r15
0x180018822  pop     r14
0x180018824  pop     r13
0x180018826  pop     r12
0x180018828  pop     rdi
0x180018829  pop     rsi
0x18001882a  pop     rbp
0x18001882b  pop     rbx
0x18001882c  retn
```
