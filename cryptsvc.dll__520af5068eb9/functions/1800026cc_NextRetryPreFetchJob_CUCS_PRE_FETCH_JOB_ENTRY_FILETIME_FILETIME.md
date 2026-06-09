# NextRetryPreFetchJob(_CUCS_PRE_FETCH_JOB_ENTRY *,_FILETIME *,_FILETIME *)

- ea: `0x1800026cc`
- end: `0x180002813`
- name: `?NextRetryPreFetchJob@@YAXPEAU_CUCS_PRE_FETCH_JOB_ENTRY@@PEAU_FILETIME@@1@Z`
- size: `327`
- prototype: `void __fastcall(struct _CUCS_PRE_FETCH_JOB_ENTRY *, struct _FILETIME *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003c90`

## callees

- `0x180002630`
- `0x1800026cc`
- `0x180003a44`
- `0x180007a80`

## import_xrefs

- `CRYPT32!CryptMemFree` at `0x1800027fd`
- `CRYPT32!CryptMemFree` at `0x1800027fd`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000270b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000272c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002744`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000270b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000272c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002744`

## pseudocode

```c
void __fastcall NextRetryPreFetchJob(struct _CUCS_PRE_FETCH_JOB_ENTRY *a1, struct _FILETIME *a2, struct _FILETIME *a3)
{
  FILETIME *v5; // rdi
  BOOL v6; // ecx
  void *v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx

  if ( !*((_DWORD *)a1 + 44) )
    goto LABEL_12;
  v5 = (FILETIME *)((char *)a1 + 184);
  *((_QWORD *)a1 + 23) = *(_QWORD *)a3 + 10000000LL * *((unsigned int *)a1 + 45);
  if ( CompareFileTime((const FILETIME *)a1 + 23, a2) < 0 )
    *v5 = *a2;
  v6 = (!*((_DWORD *)a1 + 42) && !*((_DWORD *)a1 + 43) || CompareFileTime(v5, (const FILETIME *)a1 + 21) < 0)
    && CompareFileTime(v5, (const FILETIME *)a1 + 20) < 0;
  *((_DWORD *)a1 + 44) = v6;
  if ( !v6 )
  {
LABEL_12:
    v9 = *((unsigned int *)a1 + 53);
    if ( (unsigned int)v9 >= *((_DWORD *)a1 + 52) )
      goto LABEL_13;
    v5 = (FILETIME *)((char *)a1 + 8 * v9 + 192);
    *((_DWORD *)a1 + 53) = v9 + 1;
  }
  if ( !v5 )
  {
LABEL_13:
    UpdatePreFetchJob(a1, (__int64)a2);
    return;
  }
  v7 = (void *)*((_QWORD *)a1 + 27);
  if ( v7 )
  {
    CryptMemFree(v7);
    *((_QWORD *)a1 + 27) = 0;
  }
  *(_QWORD *)((char *)a1 + 116) = 1;
  ReleaseTokenEntry((char *)a1 + 128);
  v8 = *((_QWORD *)a1 + 6) + 48LL;
  *((FILETIME *)a1 + 2) = *v5;
  AddTimeOrderedJob(v8, a1);
}

```

## disassembly

```asm
0x1800026cc  mov     [rsp+arg_0], rbx
0x1800026d1  mov     [rsp+arg_8], rsi
0x1800026d6  push    rdi
0x1800026d7  sub     rsp, 20h
0x1800026db  cmp     dword ptr [rcx+0B0h], 0
0x1800026e2  mov     rsi, rdx
0x1800026e5  mov     rbx, rcx
0x1800026e8  jz      loc_1800027AB
0x1800026ee  mov     eax, [rcx+0B4h]
0x1800026f4  lea     rdi, [rcx+0B8h]
0x1800026fb  imul    r9, rax, 989680h
0x180002702  mov     rcx, rdi; lpFileTime1
0x180002705  add     r9, [r8]
0x180002708  mov     [rdi], r9
0x18000270b  call    cs:__imp_CompareFileTime
0x180002711  test    eax, eax
0x180002713  js      loc_1800027C3
0x180002719  lea     rdx, [rbx+0A8h]; lpFileTime2
0x180002720  cmp     dword ptr [rdx], 0
0x180002723  jz      loc_1800027CE
0x180002729  mov     rcx, rdi; lpFileTime1
0x18000272c  call    cs:__imp_CompareFileTime
0x180002732  test    eax, eax
0x180002734  jns     loc_1800027DD
0x18000273a  lea     rdx, [rbx+0A0h]; lpFileTime2
0x180002741  mov     rcx, rdi; lpFileTime1
0x180002744  call    cs:__imp_CompareFileTime
0x18000274a  xor     ecx, ecx
0x18000274c  test    eax, eax
0x18000274e  sets    cl
0x180002751  mov     [rbx+0B0h], ecx
0x180002757  test    ecx, ecx
0x180002759  jz      short loc_1800027AB
0x18000275b  test    rdi, rdi
0x18000275e  jz      short loc_1800027B9
0x180002760  mov     rcx, [rbx+0D8h]; pv
0x180002767  test    rcx, rcx
0x18000276a  jnz     loc_1800027FD
0x180002770  lea     rcx, [rbx+80h]
0x180002777  mov     qword ptr [rbx+74h], 1
0x18000277f  call    ReleaseTokenEntry
0x180002784  mov     rcx, [rbx+30h]
0x180002788  mov     rdx, rbx
0x18000278b  mov     rax, [rdi]
0x18000278e  add     rcx, 30h ; '0'
0x180002792  mov     [rbx+10h], rax
0x180002796  call    AddTimeOrderedJob
0x18000279b  mov     rbx, [rsp+28h+arg_0]
0x1800027a0  mov     rsi, [rsp+28h+arg_8]
0x1800027a5  add     rsp, 20h
0x1800027a9  pop     rdi
0x1800027aa  retn
0x1800027ab  mov     ecx, [rbx+0D4h]
0x1800027b1  cmp     ecx, [rbx+0D0h]
0x1800027b7  jb      short loc_1800027E4
0x1800027b9  mov     rcx, rbx; struct _CUCS_PRE_FETCH_JOB_ENTRY *
0x1800027bc  call    ?UpdatePreFetchJob@@YAXPEAU_CUCS_PRE_FETCH_JOB_ENTRY@@@Z; UpdatePreFetchJob(_CUCS_PRE_FETCH_JOB_ENTRY *)
0x1800027c1  jmp     short loc_18000279B
0x1800027c3  mov     rax, [rsi]
0x1800027c6  mov     [rdi], rax
0x1800027c9  jmp     loc_180002719
0x1800027ce  cmp     dword ptr [rdx+4], 0
0x1800027d2  jz      loc_18000273A
0x1800027d8  jmp     loc_180002729
0x1800027dd  xor     ecx, ecx
0x1800027df  jmp     loc_180002751
0x1800027e4  lea     rdi, [rbx+0C0h]
0x1800027eb  lea     eax, [rcx+1]
0x1800027ee  lea     rdi, [rdi+rcx*8]
0x1800027f2  mov     [rbx+0D4h], eax
0x1800027f8  jmp     loc_18000275B
0x1800027fd  call    cs:__imp_CryptMemFree
0x180002803  mov     qword ptr [rbx+0D8h], 0
0x18000280e  jmp     loc_180002770
```
