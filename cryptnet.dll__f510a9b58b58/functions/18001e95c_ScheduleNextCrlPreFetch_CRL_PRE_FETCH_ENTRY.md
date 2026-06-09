# ScheduleNextCrlPreFetch(_CRL_PRE_FETCH_ENTRY *)

- ea: `0x18001e95c`
- end: `0x18001ea3f`
- name: `?ScheduleNextCrlPreFetch@@YAXPEAU_CRL_PRE_FETCH_ENTRY@@@Z`
- size: `227`
- prototype: `void __fastcall(struct _CRL_PRE_FETCH_ENTRY *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008f80`
- `0x18001e834`

## callees

- `0x180017d34`
- `0x18001e95c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001e987`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001e987`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ea2e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ea2e`

## pseudocode

```c
void __fastcall ScheduleNextCrlPreFetch(struct _CRL_PRE_FETCH_ENTRY *a1)
{
  __int64 v1; // rax
  __int64 v3; // rdi
  unsigned int v4; // eax
  unsigned int v5; // r8d
  unsigned int v6; // ecx
  unsigned int v7; // edx
  unsigned int v8; // eax
  struct _FILETIME v9; // rax
  unsigned int v10; // eax
  __int64 v11; // rcx
  struct _TP_TIMER *v12; // rcx
  struct _FILETIME v13; // [rsp+30h] [rbp+8h] BYREF
  struct _FILETIME pftDueTime; // [rsp+38h] [rbp+10h] BYREF

  v1 = *((_QWORD *)a1 + 8);
  v13 = 0;
  pftDueTime = 0;
  v3 = *(_QWORD *)(v1 + 24);
  GetSystemTimeAsFileTime(&v13);
  v4 = I_CryptSubtractFileTimes(v3 + 56, &v13);
  v5 = *((_DWORD *)a1 + 32);
  if ( v4 < v5 )
  {
    v10 = I_CryptSubtractFileTimes(&v13, v3 + 56);
    v11 = *((unsigned int *)a1 + 33);
    if ( v10 > (unsigned int)v11 )
      v9 = (struct _FILETIME)(*(_QWORD *)&v13 + 10000000LL * *((unsigned int *)a1 + 31));
    else
      v9 = (struct _FILETIME)(*(_QWORD *)(v3 + 56) + 10000000 * v11);
  }
  else
  {
    v6 = *((_DWORD *)a1 + 34);
    if ( v4 >= v6 )
    {
      if ( v4 < *((_DWORD *)a1 + 31) )
      {
        v7 = *((_DWORD *)a1 + 34);
      }
      else
      {
        v8 = v4 - *((_DWORD *)a1 + 31);
        v7 = *((_DWORD *)a1 + 34);
        if ( v8 >= v6 )
          v7 = v8;
      }
    }
    else
    {
      v7 = v4 >> 1;
    }
    if ( v7 >= v5 )
      v5 = v7;
    v9 = (struct _FILETIME)(*(_QWORD *)(v3 + 56) - 10000000LL * v5);
  }
  v12 = (struct _TP_TIMER *)*((_QWORD *)a1 + 3);
  pftDueTime = v9;
  SetThreadpoolTimer(v12, &pftDueTime, 0, 0);
}

```

## disassembly

```asm
0x18001e95c  mov     r11, rsp
0x18001e95f  mov     [r11+18h], rbx
0x18001e963  push    rdi
0x18001e964  sub     rsp, 20h
0x18001e968  mov     rax, [rcx+40h]
0x18001e96c  mov     rbx, rcx
0x18001e96f  mov     qword ptr [r11+8], 0
0x18001e977  lea     rcx, [r11+8]; lpSystemTimeAsFileTime
0x18001e97b  mov     qword ptr [r11+10h], 0
0x18001e983  mov     rdi, [rax+18h]
0x18001e987  call    cs:__imp_GetSystemTimeAsFileTime
0x18001e98d  lea     rdx, [rsp+28h+arg_0]
0x18001e992  lea     rcx, [rdi+38h]
0x18001e996  call    I_CryptSubtractFileTimes
0x18001e99b  mov     r8d, [rbx+80h]
0x18001e9a2  mov     edx, eax
0x18001e9a4  cmp     eax, r8d
0x18001e9a7  jb      short loc_18001E9E6
0x18001e9a9  mov     ecx, [rbx+88h]
0x18001e9af  cmp     eax, ecx
0x18001e9b1  jnb     short loc_18001E9B7
0x18001e9b3  shr     edx, 1
0x18001e9b5  jmp     short loc_18001E9CC
0x18001e9b7  cmp     edx, [rbx+7Ch]
0x18001e9ba  jb      short loc_18001E9CA
0x18001e9bc  sub     edx, [rbx+7Ch]
0x18001e9bf  mov     eax, edx
0x18001e9c1  mov     edx, ecx
0x18001e9c3  cmp     eax, ecx
0x18001e9c5  cmovnb  edx, eax
0x18001e9c8  jmp     short loc_18001E9CC
0x18001e9ca  mov     edx, ecx
0x18001e9cc  cmp     edx, r8d
0x18001e9cf  cmovnb  r8d, edx
0x18001e9d3  mov     eax, r8d
0x18001e9d6  imul    rcx, rax, 989680h
0x18001e9dd  mov     rax, [rdi+38h]
0x18001e9e1  sub     rax, rcx
0x18001e9e4  jmp     short loc_18001EA1A
0x18001e9e6  lea     rdx, [rdi+38h]
0x18001e9ea  lea     rcx, [rsp+28h+arg_0]
0x18001e9ef  call    I_CryptSubtractFileTimes
0x18001e9f4  mov     ecx, [rbx+84h]
0x18001e9fa  cmp     eax, ecx
0x18001e9fc  ja      short loc_18001EA0B
0x18001e9fe  imul    rax, rcx, 989680h
0x18001ea05  add     rax, [rdi+38h]
0x18001ea09  jmp     short loc_18001EA1A
0x18001ea0b  mov     eax, [rbx+7Ch]
0x18001ea0e  imul    rax, 989680h
0x18001ea15  add     rax, [rsp+28h+arg_0]
0x18001ea1a  mov     rcx, [rbx+18h]; pti
0x18001ea1e  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18001ea23  xor     r9d, r9d; msWindowLength
0x18001ea26  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18001ea2b  xor     r8d, r8d; msPeriod
0x18001ea2e  call    cs:__imp_SetThreadpoolTimer
0x18001ea34  mov     rbx, [rsp+28h+arg_10]
0x18001ea39  add     rsp, 20h
0x18001ea3d  pop     rdi
0x18001ea3e  retn
```
