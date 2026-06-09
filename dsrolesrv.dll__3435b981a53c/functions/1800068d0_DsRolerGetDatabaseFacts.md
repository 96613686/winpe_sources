# DsRolerGetDatabaseFacts

- ea: `0x1800068d0`
- end: `0x180006a0e`
- name: `DsRolerGetDatabaseFacts`
- size: `318`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800068d0`
- `0x180008fd4`
- `0x1800150cc`
- `0x180016e94`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006993`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006993`

## string_xrefs

- `0x1800069de`: `Couldn't get the IFM Handle lock during GetDbFacts().\n`

## pseudocode

```c
__int64 __fastcall DsRolerGetDatabaseFacts(__int64 a1, __int64 a2, char a3, wchar_t **a4, _DWORD *a5, _QWORD *a6)
{
  __int64 result; // rax
  signed __int32 v10; // ebx
  unsigned int DatabaseFacts; // ebx
  __int64 v12; // rcx
  SIZE_T v13; // rdi
  wchar_t *v14; // rax

  result = DsRolepCheckClientAccess(DsRolepPromoteSD, a2, 0);
  if ( !(_DWORD)result )
  {
    if ( a4 && a5 && a6 )
    {
      v10 = _InterlockedCompareExchange(&DsRolepCurrentIfmOperationHandle, 1, 0);
      if ( !v10 && !dword_18004DBD4 )
      {
        DatabaseFacts = DsRolepGetDatabaseFacts(a2, a3);
        if ( !DatabaseFacts )
        {
          dword_18004DBD4 = 1;
          if ( qword_18004DBF8 )
          {
            v12 = -1;
            do
              ++v12;
            while ( qword_18004DBF8[v12] );
            v13 = 2 * v12 + 2;
            v14 = (wchar_t *)LocalAlloc(0x40u, v13);
            *a4 = v14;
            if ( !v14 )
            {
              DatabaseFacts = 8;
              goto LABEL_16;
            }
            StringCchCopyW(v14, v13 >> 1, qword_18004DBF8);
          }
          else
          {
            *a4 = 0;
          }
          *a5 = dword_18004DBF0;
          *a6 = &DsRolepCurrentIfmOperationHandle;
        }
LABEL_16:
        DsRolepCurrentIfmOperationHandle = 0;
        return DatabaseFacts;
      }
      DsRolepLogPrintRoutine(1, "Couldn't get the IFM Handle lock during GetDbFacts().\n");
      if ( !v10 )
        DsRolepCurrentIfmOperationHandle = 0;
    }
    return 87;
  }
  return result;
}

```

## disassembly

```asm
0x1800068d0  push    rbx
0x1800068d2  push    rbp
0x1800068d3  push    rsi
0x1800068d4  push    rdi
0x1800068d5  push    r12
0x1800068d7  push    r13
0x1800068d9  push    r14
0x1800068db  push    r15
0x1800068dd  sub     rsp, 28h
0x1800068e1  mov     edi, r8d
0x1800068e4  lea     rcx, DsRolepPromoteSD; pSecurityDescriptor
0x1800068eb  xor     r8d, r8d
0x1800068ee  mov     rsi, r9
0x1800068f1  mov     rbp, rdx
0x1800068f4  call    DsRolepCheckClientAccess
0x1800068f9  xor     r12d, r12d
0x1800068fc  test    eax, eax
0x1800068fe  jnz     loc_1800069FD
0x180006904  test    rsi, rsi
0x180006907  jz      loc_1800069F8
0x18000690d  mov     r14, [rsp+68h+arg_20]
0x180006915  test    r14, r14
0x180006918  jz      loc_1800069F8
0x18000691e  mov     r15, [rsp+68h+arg_28]
0x180006926  test    r15, r15
0x180006929  jz      loc_1800069F8
0x18000692f  lea     r13d, [r12+1]
0x180006934  lock cmpxchg cs:DsRolepCurrentIfmOperationHandle, r13d
0x18000693d  mov     ebx, eax
0x18000693f  jnz     loc_1800069DE
0x180006945  cmp     cs:dword_18004DBD4, r12d
0x18000694c  jnz     loc_1800069DE
0x180006952  mov     edx, edi
0x180006954  mov     rcx, rbp
0x180006957  call    DsRolepGetDatabaseFacts
0x18000695c  mov     ebx, eax
0x18000695e  test    eax, eax
0x180006960  jnz     short loc_1800069D3
0x180006962  mov     rax, cs:qword_18004DBF8
0x180006969  mov     cs:dword_18004DBD4, r13d
0x180006970  test    rax, rax
0x180006973  jz      short loc_1800069BD
0x180006975  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180006979  inc     rcx
0x18000697c  cmp     [rax+rcx*2], r12w
0x180006981  jnz     short loc_180006979
0x180006983  lea     rdi, ds:2[rcx*2]
0x18000698b  mov     ecx, 40h ; '@'; uFlags
0x180006990  mov     rdx, rdi; uBytes
0x180006993  call    cs:__imp_LocalAlloc
0x180006999  mov     [rsi], rax
0x18000699c  test    rax, rax
0x18000699f  jnz     short loc_1800069A6
0x1800069a1  lea     ebx, [rax+8]
0x1800069a4  jmp     short loc_1800069D3
0x1800069a6  mov     r8, cs:qword_18004DBF8; pszSrc
0x1800069ad  mov     rcx, rax; pszDest
0x1800069b0  shr     rdi, 1
0x1800069b3  mov     rdx, rdi; cchDest
0x1800069b6  call    StringCchCopyW
0x1800069bb  jmp     short loc_1800069C0
0x1800069bd  mov     [rsi], r12
0x1800069c0  mov     eax, cs:dword_18004DBF0
0x1800069c6  mov     [r14], eax
0x1800069c9  lea     rax, DsRolepCurrentIfmOperationHandle
0x1800069d0  mov     [r15], rax
0x1800069d3  mov     cs:DsRolepCurrentIfmOperationHandle, r12d
0x1800069da  mov     eax, ebx
0x1800069dc  jmp     short loc_1800069FD
0x1800069de  lea     rdx, aCouldnTGetTheI; "Couldn't get the IFM Handle lock during"...
0x1800069e5  mov     ecx, r13d
0x1800069e8  call    DsRolepLogPrintRoutine
0x1800069ed  test    ebx, ebx
0x1800069ef  jnz     short loc_1800069F8
0x1800069f1  mov     cs:DsRolepCurrentIfmOperationHandle, r12d
0x1800069f8  mov     eax, 57h ; 'W'
0x1800069fd  add     rsp, 28h
0x180006a01  pop     r15
0x180006a03  pop     r14
0x180006a05  pop     r13
0x180006a07  pop     r12
0x180006a09  pop     rdi
0x180006a0a  pop     rsi
0x180006a0b  pop     rbp
0x180006a0c  pop     rbx
0x180006a0d  retn
```
