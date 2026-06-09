# RemoveActiveAssociations(int,ushort const *,ushort const *)

- ea: `0x18006237c`
- end: `0x18006250b`
- name: `?RemoveActiveAssociations@@YAJHPEBG0@Z`
- size: `399`
- prototype: `int(int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002eee0`
- `0x180030960`
- `0x180046174`
- `0x1800464a0`

## callees

- `0x18006237c`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006239f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006239f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800624d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800624d6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800624e9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800624e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180062469`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180062486`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006249a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180062469`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180062486`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006249a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180062477`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180062494`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800624a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180062477`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180062494`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800624a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800624ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800624ba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800623d3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800623f3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800623d3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800623f3`

## pseudocode

```c
__int64 __fastcall RemoveActiveAssociations(BOOL a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  unsigned int v6; // ebx
  LPCWCH *i; // rdi
  int v8; // eax
  int v9; // ecx
  BOOL v10; // eax
  LPCWCH v11; // rbp
  LPCWCH v12; // rcx
  void **v13; // rax
  WCHAR *v14; // r14
  HANDLE ProcessHeap; // rax
  WCHAR *v16; // r14
  HANDLE v17; // rax
  HANDLE v18; // rax
  signed int LastError; // eax

  v6 = 1;
  EnterCriticalSection(&ActiveAssociationsList);
  for ( i = (LPCWCH *)qword_1800A46A0; i != (LPCWCH *)&qword_1800A46A0; i = (LPCWCH *)v11 )
  {
    if ( a1 )
    {
      v10 = a1;
LABEL_12:
      v11 = *i;
      if ( !v10 )
        continue;
      goto LABEL_13;
    }
    v8 = CompareStringOrdinal(a2, -1, i[3], -1, 1);
    if ( v8 == 2 )
    {
      if ( *((_DWORD *)i + 10) )
      {
        v9 = CompareStringOrdinal(a3, -1, i[4], -1, 1);
        if ( !v9 )
          goto LABEL_21;
        v10 = v9 == 2;
        goto LABEL_12;
      }
      v11 = *i;
LABEL_13:
      (*(void (__fastcall **)(LPCWCH))(*(_QWORD *)i[2] + 16LL))(i[2]);
      v12 = *i;
      if ( *((LPCWCH **)*i + 1) != i || (v13 = (void **)i[1], *v13 != i) )
        __fastfail(3u);
      *v13 = (void *)v12;
      *((_QWORD *)v12 + 1) = v13;
      v14 = (WCHAR *)i[3];
      if ( v14 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v14);
      }
      v16 = (WCHAR *)i[4];
      if ( v16 )
      {
        v17 = GetProcessHeap();
        HeapFree(v17, 0, v16);
      }
      v18 = GetProcessHeap();
      HeapFree(v18, 0, i);
      if ( !a1 )
      {
        v6 = 0;
        break;
      }
      continue;
    }
    if ( !v8 )
    {
LABEL_21:
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      break;
    }
    v11 = *i;
  }
  LeaveCriticalSection(&ActiveAssociationsList);
  if ( a1 )
  {
    v6 = 0;
    DeleteCriticalSection(&ActiveAssociationsList);
  }
  return v6;
}

```

## disassembly

```asm
0x18006237c  push    rbx
0x18006237e  push    rbp
0x18006237f  push    rsi
0x180062380  push    rdi
0x180062381  push    r12
0x180062383  push    r14
0x180062385  push    r15
0x180062387  sub     rsp, 30h
0x18006238b  mov     esi, ecx
0x18006238d  mov     r12, r8
0x180062390  lea     rcx, ?ActiveAssociationsList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x180062397  mov     r15, rdx
0x18006239a  mov     ebx, 1
0x18006239f  call    cs:__imp_EnterCriticalSection
0x1800623a5  mov     rdi, cs:qword_1800A46A0
0x1800623ac  or      ebp, 0FFFFFFFFh
0x1800623af  lea     rax, qword_1800A46A0
0x1800623b6  cmp     rdi, rax
0x1800623b9  jz      loc_1800624CF
0x1800623bf  test    esi, esi
0x1800623c1  jnz     short loc_180062422
0x1800623c3  mov     r8, [rdi+18h]; lpString2
0x1800623c7  mov     r9d, ebp; cchCount2
0x1800623ca  mov     edx, ebp; cchCount1
0x1800623cc  mov     [rsp+68h+bIgnoreCase], ebx; bIgnoreCase
0x1800623d0  mov     rcx, r15; lpString1
0x1800623d3  call    cs:__imp_CompareStringOrdinal
0x1800623d9  cmp     eax, 2
0x1800623dc  jnz     short loc_180062412
0x1800623de  cmp     [rdi+28h], esi
0x1800623e1  jz      short loc_18006240D
0x1800623e3  mov     r8, [rdi+20h]; lpString2
0x1800623e7  mov     r9d, ebp; cchCount2
0x1800623ea  mov     edx, ebp; cchCount1
0x1800623ec  mov     [rsp+68h+bIgnoreCase], ebx; bIgnoreCase
0x1800623f0  mov     rcx, r12; lpString1
0x1800623f3  call    cs:__imp_CompareStringOrdinal
0x1800623f9  mov     ecx, eax
0x1800623fb  test    eax, eax
0x1800623fd  jz      loc_1800624BA
0x180062403  cmp     ecx, 2
0x180062406  mov     eax, ebx
0x180062408  cmovnz  eax, esi
0x18006240b  jmp     short loc_180062424
0x18006240d  mov     rbp, [rdi]
0x180062410  jmp     short loc_18006242F
0x180062412  test    eax, eax
0x180062414  jz      loc_1800624BA
0x18006241a  mov     rbp, [rdi]
0x18006241d  jmp     loc_1800624B2
0x180062422  mov     eax, esi
0x180062424  mov     rbp, [rdi]
0x180062427  test    eax, eax
0x180062429  jz      loc_1800624B2
0x18006242f  mov     rcx, [rdi+10h]
0x180062433  mov     rax, [rcx]
0x180062436  mov     rax, [rax+10h]
0x18006243a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006243f  mov     rcx, [rdi]
0x180062442  cmp     [rcx+8], rdi
0x180062446  jnz     loc_180062504
0x18006244c  mov     rax, [rdi+8]
0x180062450  cmp     [rax], rdi
0x180062453  jnz     loc_180062504
0x180062459  mov     [rax], rcx
0x18006245c  mov     [rcx+8], rax
0x180062460  mov     r14, [rdi+18h]
0x180062464  test    r14, r14
0x180062467  jz      short loc_18006247D
0x180062469  call    cs:__imp_GetProcessHeap
0x18006246f  mov     r8, r14; lpMem
0x180062472  xor     edx, edx; dwFlags
0x180062474  mov     rcx, rax; hHeap
0x180062477  call    cs:__imp_HeapFree
0x18006247d  mov     r14, [rdi+20h]
0x180062481  test    r14, r14
0x180062484  jz      short loc_18006249A
0x180062486  call    cs:__imp_GetProcessHeap
0x18006248c  mov     r8, r14; lpMem
0x18006248f  xor     edx, edx; dwFlags
0x180062491  mov     rcx, rax; hHeap
0x180062494  call    cs:__imp_HeapFree
0x18006249a  call    cs:__imp_GetProcessHeap
0x1800624a0  mov     r8, rdi; lpMem
0x1800624a3  xor     edx, edx; dwFlags
0x1800624a5  mov     rcx, rax; hHeap
0x1800624a8  call    cs:__imp_HeapFree
0x1800624ae  test    esi, esi
0x1800624b0  jz      short loc_180062500
0x1800624b2  mov     rdi, rbp
0x1800624b5  jmp     loc_1800623AC
0x1800624ba  call    cs:__imp_GetLastError
0x1800624c0  mov     ebx, eax
0x1800624c2  test    eax, eax
0x1800624c4  jle     short loc_1800624CF
0x1800624c6  movzx   ebx, ax
0x1800624c9  or      ebx, 80070000h
0x1800624cf  lea     rcx, ?ActiveAssociationsList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x1800624d6  call    cs:__imp_LeaveCriticalSection
0x1800624dc  test    esi, esi
0x1800624de  jz      short loc_1800624EF
0x1800624e0  xor     ebx, ebx
0x1800624e2  lea     rcx, ?ActiveAssociationsList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x1800624e9  call    cs:__imp_DeleteCriticalSection
0x1800624ef  mov     eax, ebx
0x1800624f1  add     rsp, 30h
0x1800624f5  pop     r15
0x1800624f7  pop     r14
0x1800624f9  pop     r12
0x1800624fb  pop     rdi
0x1800624fc  pop     rsi
0x1800624fd  pop     rbp
0x1800624fe  pop     rbx
0x1800624ff  retn
0x180062500  xor     ebx, ebx
0x180062502  jmp     short loc_1800624CF
0x180062504  mov     ecx, 3
0x180062509  int     29h; Win8: RtlFailFast(ecx)
```
