# CompletePreFetchJob(_CUCS_PRE_FETCH_JOB_ENTRY *)

- ea: `0x180003c90`
- end: `0x180003eed`
- name: `?CompletePreFetchJob@@YAXPEAU_CUCS_PRE_FETCH_JOB_ENTRY@@@Z`
- size: `605`
- prototype: `void __fastcall(struct _FILETIME *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005460`

## callees

- `0x180002478`
- `0x1800026cc`
- `0x180003a44`
- `0x180003c90`
- `0x180004c90`
- `0x1800089a0`
- `0x180008df0`
- `0x180009f28`
- `0x18000bfcc`
- `0x18000fe44`

## import_xrefs

- `CRYPT32!CryptMemFree` at `0x180003dfa`
- `CRYPT32!CryptMemFree` at `0x180003dfa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003cc4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003cc4`

## pseudocode

```c
void __fastcall CompletePreFetchJob(struct _FILETIME *a1)
{
  __int64 v2; // rdx
  struct _FILETIME v3; // rax
  DWORD dwLowDateTime; // ecx
  DWORD dwHighDateTime; // eax
  int Content; // eax
  int v7; // esi
  void *v8; // rcx
  int v9; // eax
  DWORD v10; // eax
  unsigned int v11; // edx
  __int64 v12; // rcx
  struct _FILETIME *v13; // rdx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+8h] BYREF
  __int64 v15; // [rsp+48h] [rbp+10h] BYREF

  SystemTimeAsFileTime = 0;
  if ( !*(_QWORD *)&a1[6] )
  {
    FreePreFetchJob(a1);
    return;
  }
  if ( a1[15].dwLowDateTime )
    ++a1[31].dwLowDateTime;
  else
    a1[31].dwLowDateTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v3 = SystemTimeAsFileTime;
  if ( !a1[29].dwLowDateTime && !a1[29].dwHighDateTime )
    a1[29] = SystemTimeAsFileTime;
  dwLowDateTime = a1[15].dwLowDateTime;
  if ( !dwLowDateTime )
  {
    dwHighDateTime = a1[17].dwHighDateTime;
    if ( a1[27] )
    {
      if ( dwHighDateTime != 7 && dwHighDateTime != 5 && dwHighDateTime != 6 )
      {
        if ( dwHighDateTime == 2 )
        {
          Content = ValidateCrlPreFetchContent(a1);
        }
        else if ( dwHighDateTime == 3 )
        {
          Content = ValidateOcspPreFetchContent(a1);
        }
        else
        {
          Content = ValidateAnyPreFetchContent((__int64)a1);
        }
LABEL_9:
        v7 = Content;
        if ( Content )
        {
          if ( Content != 1 )
            goto LABEL_16;
          goto LABEL_11;
        }
LABEL_12:
        v8 = (void *)a1[27];
        if ( v8 )
        {
          CryptMemFree(v8);
          a1[27] = 0;
        }
        if ( a1[22].dwLowDateTime )
        {
          UpdatePreFetchJobCacheFile((struct _CUCS_PRE_FETCH_JOB_ENTRY *)a1, v2);
          goto LABEL_16;
        }
        v10 = a1[17].dwHighDateTime;
        if ( v10 != 7 && v10 - 5 >= 2 )
        {
LABEL_16:
          v9 = 4350;
          if ( v7 )
            v9 = 13;
          a1[15].dwLowDateTime = v9;
          NextRetryPreFetchJob((struct _CUCS_PRE_FETCH_JOB_ENTRY *)a1, &SystemTimeAsFileTime, a1 + 29);
          return;
        }
LABEL_11:
        UpdatePreFetchJob((struct _CUCS_PRE_FETCH_JOB_ENTRY *)a1, v2);
        return;
      }
    }
    else if ( dwHighDateTime != 7 && dwHighDateTime - 5 >= 2 )
    {
      v7 = 0;
      goto LABEL_12;
    }
    Content = ValidateAutoUpdateCabPreFetchContent(a1);
    goto LABEL_9;
  }
  if ( dwLowDateTime == 5035 || dwLowDateTime == 50 )
    goto LABEL_20;
  v11 = a1[31].dwLowDateTime;
  v12 = 0xFFFFFFFFLL;
  if ( v11 < 3 )
    v12 = *((unsigned int *)&rglRetrySecondsForRetrievalPreFetchError + v11);
  if ( (int)v12 < 0 )
  {
LABEL_20:
    a1[31].dwLowDateTime = 0;
    NextRetryPreFetchJob((struct _CUCS_PRE_FETCH_JOB_ENTRY *)a1, &SystemTimeAsFileTime, &SystemTimeAsFileTime);
  }
  else
  {
    v15 = 0;
    v13 = 0;
    if ( (_DWORD)v12 )
    {
      v15 = *(_QWORD *)&v3 + 10000000 * v12;
      v13 = (struct _FILETIME *)&v15;
    }
    RetryPreFetchJob((struct _CUCS_PRE_FETCH_JOB_ENTRY *)a1, v13, 5u);
  }
}

```

## disassembly

```asm
0x180003c90  push    rbx
0x180003c92  push    rbp
0x180003c93  sub     rsp, 28h
0x180003c97  xor     ebp, ebp
0x180003c99  mov     rbx, rcx
0x180003c9c  mov     qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime], rbp
0x180003ca1  cmp     [rcx+30h], rbp
0x180003ca5  jz      loc_180003E3D
0x180003cab  mov     [rsp+38h+var_18], rdi
0x180003cb0  cmp     [rcx+78h], ebp
0x180003cb3  jnz     loc_180003E32
0x180003cb9  mov     [rcx+0F8h], ebp
0x180003cbf  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003cc4  call    cs:__imp_GetSystemTimeAsFileTime
0x180003cca  mov     rax, qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime]
0x180003ccf  cmp     [rbx+0E8h], ebp
0x180003cd5  jz      loc_180003DAF
0x180003cdb  mov     ecx, [rbx+78h]
0x180003cde  test    ecx, ecx
0x180003ce0  jnz     loc_180003D7F
0x180003ce6  mov     eax, [rbx+8Ch]
0x180003cec  mov     [rsp+38h+arg_10], rsi
0x180003cf1  cmp     [rbx+0D8h], rbp
0x180003cf8  jnz     loc_180003DC7
0x180003cfe  cmp     eax, 7
0x180003d01  jnz     loc_180003EC7
0x180003d07  mov     rcx, rbx
0x180003d0a  call    ValidateAutoUpdateCabPreFetchContent
0x180003d0f  mov     esi, eax
0x180003d11  test    eax, eax
0x180003d13  jz      short loc_180003D24
0x180003d15  cmp     eax, 1
0x180003d18  jnz     short loc_180003D48
0x180003d1a  mov     rcx, rbx; struct _CUCS_PRE_FETCH_JOB_ENTRY *
0x180003d1d  call    ?UpdatePreFetchJob@@YAXPEAU_CUCS_PRE_FETCH_JOB_ENTRY@@@Z; UpdatePreFetchJob(_CUCS_PRE_FETCH_JOB_ENTRY *)
0x180003d22  jmp     short loc_180003D6E
0x180003d24  mov     rcx, [rbx+0D8h]; pv
0x180003d2b  test    rcx, rcx
0x180003d2e  jnz     loc_180003DFA
0x180003d34  cmp     [rbx+0B0h], ebp
0x180003d3a  jz      loc_180003E0C
0x180003d40  mov     rcx, rbx; struct _CUCS_PRE_FETCH_JOB_ENTRY *
0x180003d43  call    ?UpdatePreFetchJobCacheFile@@YAHPEAU_CUCS_PRE_FETCH_JOB_ENTRY@@@Z; UpdatePreFetchJobCacheFile(_CUCS_PRE_FETCH_JOB_ENTRY *)
0x180003d48  test    esi, esi
0x180003d4a  lea     r8, [rbx+0E8h]; struct _FILETIME *
0x180003d51  mov     eax, 10FEh
0x180003d56  lea     rdx, [rsp+38h+SystemTimeAsFileTime]; struct _FILETIME *
0x180003d5b  mov     ecx, 0Dh
0x180003d60  cmovnz  eax, ecx
0x180003d63  mov     rcx, rbx; struct _CUCS_PRE_FETCH_JOB_ENTRY *
0x180003d66  mov     [rbx+78h], eax
0x180003d69  call    ?NextRetryPreFetchJob@@YAXPEAU_CUCS_PRE_FETCH_JOB_ENTRY@@PEAU_FILETIME@@1@Z; NextRetryPreFetchJob(_CUCS_PRE_FETCH_JOB_ENTRY *,_FILETIME *,_FILETIME *)
0x180003d6e  mov     rsi, [rsp+38h+arg_10]
0x180003d73  mov     rdi, [rsp+38h+var_18]
0x180003d78  add     rsp, 28h
0x180003d7c  pop     rbp
0x180003d7d  pop     rbx
0x180003d7e  retn
0x180003d7f  cmp     ecx, 13ABh
0x180003d85  jnz     loc_180003E49
0x180003d8b  lea     r8, [rsp+38h+SystemTimeAsFileTime]; struct _FILETIME *
0x180003d90  mov     [rbx+0F8h], ebp
0x180003d96  lea     rdx, [rsp+38h+SystemTimeAsFileTime]; struct _FILETIME *
0x180003d9b  mov     rcx, rbx; struct _CUCS_PRE_FETCH_JOB_ENTRY *
0x180003d9e  call    ?NextRetryPreFetchJob@@YAXPEAU_CUCS_PRE_FETCH_JOB_ENTRY@@PEAU_FILETIME@@1@Z; NextRetryPreFetchJob(_CUCS_PRE_FETCH_JOB_ENTRY *,_FILETIME *,_FILETIME *)
0x180003da3  mov     rdi, [rsp+38h+var_18]
0x180003da8  add     rsp, 28h
0x180003dac  pop     rbp
0x180003dad  pop     rbx
0x180003dae  retn
0x180003daf  cmp     [rbx+0ECh], ebp
0x180003db5  jnz     loc_180003CDB
0x180003dbb  mov     [rbx+0E8h], rax
0x180003dc2  jmp     loc_180003CDB
0x180003dc7  cmp     eax, 7
0x180003dca  jz      loc_180003D07
0x180003dd0  mov     ecx, eax
0x180003dd2  sub     ecx, 5
0x180003dd5  jz      loc_180003D07
0x180003ddb  cmp     ecx, 1
0x180003dde  jz      loc_180003D07
0x180003de4  cmp     eax, 2
0x180003de7  jnz     loc_180003E9A
0x180003ded  mov     rcx, rbx
0x180003df0  call    ValidateCrlPreFetchContent
0x180003df5  jmp     loc_180003D0F
0x180003dfa  call    cs:__imp_CryptMemFree
0x180003e00  mov     [rbx+0D8h], rbp
0x180003e07  jmp     loc_180003D34
0x180003e0c  mov     eax, [rbx+8Ch]
0x180003e12  cmp     eax, 7
0x180003e15  jz      loc_180003D1A
0x180003e1b  sub     eax, 5
0x180003e1e  jz      loc_180003D1A
0x180003e24  cmp     eax, 1
0x180003e27  jz      loc_180003D1A
0x180003e2d  jmp     loc_180003D48
0x180003e32  inc     dword ptr [rcx+0F8h]
0x180003e38  jmp     loc_180003CBF
0x180003e3d  call    FreePreFetchJob
0x180003e42  add     rsp, 28h
0x180003e46  pop     rbp
0x180003e47  pop     rbx
0x180003e48  retn
0x180003e49  cmp     ecx, 32h ; '2'
0x180003e4c  jz      loc_180003D8B
0x180003e52  mov     edx, [rbx+0F8h]
0x180003e58  mov     ecx, 0FFFFFFFFh
0x180003e5d  cmp     edx, 3
0x180003e60  jnb     short loc_180003E6E
0x180003e62  mov     ecx, edx
0x180003e64  lea     rdx, ?rglRetrySecondsForRetrievalPreFetchError@@3PAJA; long near * rglRetrySecondsForRetrievalPreFetchError
0x180003e6b  mov     ecx, [rdx+rcx*4]
0x180003e6e  test    ecx, ecx
0x180003e70  js      loc_180003D8B
0x180003e76  mov     [rsp+38h+arg_8], rbp
0x180003e7b  mov     rdx, rbp; struct _FILETIME *
0x180003e7e  jnz     short loc_180003EB1
0x180003e80  mov     r8d, 5; unsigned int
0x180003e86  mov     rcx, rbx; struct _CUCS_PRE_FETCH_JOB_ENTRY *
0x180003e89  call    ?RetryPreFetchJob@@YAXPEAU_CUCS_PRE_FETCH_JOB_ENTRY@@PEAU_FILETIME@@K@Z; RetryPreFetchJob(_CUCS_PRE_FETCH_JOB_ENTRY *,_FILETIME *,ulong)
0x180003e8e  mov     rdi, [rsp+38h+var_18]
0x180003e93  add     rsp, 28h
0x180003e97  pop     rbp
0x180003e98  pop     rbx
0x180003e99  retn
0x180003e9a  sub     eax, 1
0x180003e9d  jz      short loc_180003EE0
0x180003e9f  cmp     eax, 2
0x180003ea2  jnz     short loc_180003EE0
0x180003ea4  mov     rcx, rbx
0x180003ea7  call    ValidateOcspPreFetchContent
0x180003eac  jmp     loc_180003D0F
0x180003eb1  imul    rdx, rcx, 989680h
0x180003eb8  add     rdx, rax
0x180003ebb  mov     [rsp+38h+arg_8], rdx
0x180003ec0  lea     rdx, [rsp+38h+arg_8]
0x180003ec5  jmp     short loc_180003E80
0x180003ec7  sub     eax, 5
0x180003eca  jz      loc_180003D07
0x180003ed0  cmp     eax, 1
0x180003ed3  jz      loc_180003D07
0x180003ed9  mov     esi, ebp
0x180003edb  jmp     loc_180003D24
0x180003ee0  mov     rcx, rbx
0x180003ee3  call    ValidateAnyPreFetchContent
0x180003ee8  jmp     loc_180003D0F
```
