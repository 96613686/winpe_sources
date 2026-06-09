# RemovePreFetchJobFromDir

- ea: `0x180003b60`
- end: `0x180003c89`
- name: `RemovePreFetchJobFromDir`
- size: `297`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180003a44`
- `0x180003aa0`
- `0x180004998`

## callees

- `0x180003b60`
- `0x1800089a0`
- `0x18000b720`
- `0x18000d4c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003bd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003c5b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003c7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003bd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003c5b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003c7e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003b77`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c66`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003b77`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c66`
- `CRYPT32!I_CryptRemoveLruEntry` at `0x180003c42`
- `CRYPT32!I_CryptRemoveLruEntry` at `0x180003c42`

## pseudocode

```c
void __fastcall RemovePreFetchJobFromDir(_QWORD *hMem)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rdx
  _QWORD *v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx

  EnterCriticalSection(&JobsCriticalSection);
  v2 = hMem[4];
  v3 = hMem[6];
  v4 = hMem[5];
  if ( v2 )
  {
    *(_QWORD *)(v2 + 40) = v4;
    hMem[4] = 0;
  }
  if ( v4 )
  {
    *(_QWORD *)(v4 + 32) = v2;
    hMem[5] = 0;
  }
  else
  {
    *(_QWORD *)(v3 + 40) = v2;
  }
  if ( *((_DWORD *)hMem + 29) == 1 )
  {
    v5 = *hMem;
    v6 = hMem[6];
    v7 = (_QWORD *)hMem[1];
    if ( *hMem )
    {
      *(_QWORD *)(v5 + 8) = v7;
      *hMem = 0;
    }
    if ( v7 )
    {
      *v7 = v5;
      hMem[1] = 0;
    }
    else
    {
      *(_QWORD *)(v6 + 48) = v5;
    }
    goto LABEL_10;
  }
  if ( *((_DWORD *)hMem + 29) == 2 )
  {
    EnterCriticalSection(&JobsCriticalSection);
    RemoveFromLinkList2(v10, v9, hMem);
    *((_DWORD *)hMem + 29) = 0;
    LeaveCriticalSection(&JobsCriticalSection);
LABEL_10:
    hMem[6] = 0;
    LeaveCriticalSection(&JobsCriticalSection);
    FreePreFetchJob(hMem);
    return;
  }
  if ( *((_DWORD *)hMem + 29) != 3 )
  {
    if ( (unsigned int)(*((_DWORD *)hMem + 29) - 4) < 2 )
      RemoveToBeRunJob(hMem);
    goto LABEL_10;
  }
  v8 = hMem[13];
  if ( v8 )
  {
    I_CryptRemoveLruEntry(v8, 4);
    hMem[13] = 0;
  }
  hMem[6] = 0;
  LeaveCriticalSection(&JobsCriticalSection);
}

```

## disassembly

```asm
0x180003b60  mov     [rsp+arg_0], rbx
0x180003b65  push    rsi
0x180003b66  sub     rsp, 20h
0x180003b6a  mov     rbx, rcx
0x180003b6d  lea     rsi, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION JobsCriticalSection
0x180003b74  mov     rcx, rsi; lpCriticalSection
0x180003b77  call    cs:__imp_EnterCriticalSection
0x180003b7d  mov     rax, [rbx+20h]
0x180003b81  mov     rdx, [rbx+30h]
0x180003b85  mov     rcx, [rbx+28h]
0x180003b89  test    rax, rax
0x180003b8c  jz      short loc_180003B9A
0x180003b8e  mov     [rax+28h], rcx
0x180003b92  mov     qword ptr [rbx+20h], 0
0x180003b9a  test    rcx, rcx
0x180003b9d  jz      short loc_180003BEF
0x180003b9f  mov     [rcx+20h], rax
0x180003ba3  mov     qword ptr [rbx+28h], 0
0x180003bab  mov     ecx, [rbx+74h]
0x180003bae  sub     ecx, 1
0x180003bb1  jz      short loc_180003BF5
0x180003bb3  sub     ecx, 1
0x180003bb6  jz      loc_180003C63
0x180003bbc  sub     ecx, 1
0x180003bbf  jz      short loc_180003C32
0x180003bc1  sub     ecx, 1
0x180003bc4  jz      short loc_180003C28
0x180003bc6  cmp     ecx, 1
0x180003bc9  jz      short loc_180003C28
0x180003bcb  mov     rcx, rsi; lpCriticalSection
0x180003bce  mov     qword ptr [rbx+30h], 0
0x180003bd6  call    cs:__imp_LeaveCriticalSection
0x180003bdc  mov     rcx, rbx; hMem
0x180003bdf  call    FreePreFetchJob
0x180003be4  mov     rbx, [rsp+28h+arg_0]
0x180003be9  add     rsp, 20h
0x180003bed  pop     rsi
0x180003bee  retn
0x180003bef  mov     [rdx+28h], rax
0x180003bf3  jmp     short loc_180003BAB
0x180003bf5  mov     rax, [rbx]
0x180003bf8  mov     rdx, [rbx+30h]
0x180003bfc  mov     rcx, [rbx+8]
0x180003c00  test    rax, rax
0x180003c03  jz      short loc_180003C10
0x180003c05  mov     [rax+8], rcx
0x180003c09  mov     qword ptr [rbx], 0
0x180003c10  test    rcx, rcx
0x180003c13  jz      short loc_180003C22
0x180003c15  mov     [rcx], rax
0x180003c18  mov     qword ptr [rbx+8], 0
0x180003c20  jmp     short loc_180003BCB
0x180003c22  mov     [rdx+30h], rax
0x180003c26  jmp     short loc_180003BCB
0x180003c28  mov     rcx, rbx
0x180003c2b  call    RemoveToBeRunJob
0x180003c30  jmp     short loc_180003BCB
0x180003c32  mov     rcx, [rbx+68h]
0x180003c36  test    rcx, rcx
0x180003c39  jz      short loc_180003C50
0x180003c3b  xor     r8d, r8d
0x180003c3e  lea     edx, [r8+4]
0x180003c42  call    cs:__imp_I_CryptRemoveLruEntry
0x180003c48  mov     qword ptr [rbx+68h], 0
0x180003c50  mov     rcx, rsi; lpCriticalSection
0x180003c53  mov     qword ptr [rbx+30h], 0
0x180003c5b  call    cs:__imp_LeaveCriticalSection
0x180003c61  jmp     short loc_180003BE4
0x180003c63  mov     rcx, rsi; lpCriticalSection
0x180003c66  call    cs:__imp_EnterCriticalSection
0x180003c6c  mov     r8, rbx
0x180003c6f  call    RemoveFromLinkList2
0x180003c74  mov     rcx, rsi; lpCriticalSection
0x180003c77  mov     dword ptr [rbx+74h], 0
0x180003c7e  call    cs:__imp_LeaveCriticalSection
0x180003c84  jmp     loc_180003BCB
```
