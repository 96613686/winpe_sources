# UrlCacheSvcProcessExitCallback(void *,uchar)

- ea: `0x18000b420`
- end: `0x18000b49b`
- name: `?UrlCacheSvcProcessExitCallback@@YAXPEAXE@Z`
- size: `123`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800068f0`
- `0x18000b420`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b449`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b430`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b430`

## pseudocode

```c
void __fastcall UrlCacheSvcProcessExitCallback(_DWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rcx

  EnterCriticalSection(&JobsCriticalSection);
  if ( !a1[16] )
  {
    a1[16] = 1;
    v2 = *(_QWORD **)a1;
    v3 = (_QWORD *)*((_QWORD *)a1 + 1);
    if ( *(_QWORD *)a1 )
    {
      v2[1] = v3;
      *(_QWORD *)a1 = 0;
    }
    if ( v3 )
    {
      *v3 = v2;
      *((_QWORD *)a1 + 1) = 0;
    }
    else
    {
      pPendingLogoffExitJobHead = v2;
    }
    AddToBeRunJobEx((FILETIME)a1, 4, 0, 0);
  }
  LeaveCriticalSection(&JobsCriticalSection);
}

```

## disassembly

```asm
0x18000b420  push    rbx
0x18000b422  sub     rsp, 20h
0x18000b426  mov     rbx, rcx
0x18000b429  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b430  call    cs:__imp_EnterCriticalSection
0x18000b436  mov     eax, [rbx+40h]
0x18000b439  test    eax, eax
0x18000b43b  jz      short loc_18000B450
0x18000b43d  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION JobsCriticalSection
0x18000b444  add     rsp, 20h
0x18000b448  pop     rbx
0x18000b449  jmp     cs:__imp_LeaveCriticalSection
0x18000b450  mov     dword ptr [rbx+40h], 1
0x18000b457  mov     rax, [rbx]
0x18000b45a  mov     rcx, [rbx+8]
0x18000b45e  test    rax, rax
0x18000b461  jz      short loc_18000B46E
0x18000b463  mov     [rax+8], rcx
0x18000b467  mov     qword ptr [rbx], 0
0x18000b46e  test    rcx, rcx
0x18000b471  jz      short loc_18000B492
0x18000b473  mov     [rcx], rax
0x18000b476  mov     qword ptr [rbx+8], 0
0x18000b47e  xor     r9d, r9d
0x18000b481  xor     r8d, r8d
0x18000b484  mov     rcx, rbx
0x18000b487  lea     edx, [r9+4]
0x18000b48b  call    AddToBeRunJobEx
0x18000b490  jmp     short loc_18000B43D
0x18000b492  mov     cs:?pPendingLogoffExitJobHead@@3PEAU_CUCS_LOGOFF_EXIT_JOB_ENTRY@@EA, rax; _CUCS_LOGOFF_EXIT_JOB_ENTRY * pPendingLogoffExitJobHead
0x18000b499  jmp     short loc_18000B47E
```
