# PerflibciCloseLocalQueryHandle

- ea: `0x1800163f4`
- end: `0x18001653d`
- name: `PerflibciCloseLocalQueryHandle`
- size: `329`
- prototype: `__int64 __fastcall(struct _PERF_QUERY *)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180005680`
- `0x18000cb04`
- `0x180018960`
- `0x1800191b0`

## callees

- `0x180008050`
- `0x180015e20`
- `0x1800163f4`

## import_xrefs

- `ntdll!NtClose` at `0x180016492`
- `ntdll!NtClose` at `0x1800164ba`
- `ntdll!NtClose` at `0x180016492`
- `ntdll!NtClose` at `0x1800164ba`

## pseudocode

```c
__int64 __fastcall PerflibciCloseLocalQueryHandle(struct _PERF_QUERY *a1)
{
  __int64 *v2; // rbx
  unsigned int i; // esi
  __int64 *v4; // rbp
  __int64 j; // rax
  __int64 v6; // rdx
  void *v7; // rcx
  unsigned int k; // esi
  __int64 v9; // rcx
  __int64 v10; // rax
  _QWORD **v11; // rcx
  _QWORD *v12; // rcx
  _QWORD *v13; // rbx

  v2 = (__int64 *)*((_QWORD *)a1 + 3);
  if ( *((_QWORD *)a1 + 7) )
  {
    for ( i = 0; i < *((_DWORD *)a1 + 16); ++i )
      operator delete(*(void **)(*((_QWORD *)a1 + 7) + 16LL * i));
    operator delete(*((void **)a1 + 7));
    *((_QWORD *)a1 + 7) = 0;
    *((_DWORD *)a1 + 16) = 0;
  }
  if ( v2 )
  {
    do
    {
      v4 = (__int64 *)*v2;
      for ( j = 0; (unsigned int)j < *((_DWORD *)v2 + 7); j = (unsigned int)(*(_DWORD *)(j + v6 + 20) + j) )
      {
        v6 = v2[2];
        if ( *(_DWORD *)(j + v6 + 16) != -2 )
        {
          *(_DWORD *)(j + v6 + 16) = 1223;
          *(_DWORD *)(j + v6 + 36) = -2;
        }
      }
      if ( *(_DWORD *)(v2[1] + 32) != 1 )
      {
        PerflibciSendCounterUpdateRequest(a1, (struct PERFLIBCI_QUERY_PROVIDER_NODE *)v2, 0);
        NtClose((HANDLE)v2[6]);
      }
      operator delete((void *)v2[2]);
      operator delete(v2);
      v2 = v4;
    }
    while ( v4 );
  }
  v7 = (void *)*((_QWORD *)a1 + 9);
  if ( v7 )
    NtClose(v7);
  operator delete(*((void **)a1 + 10));
  if ( *((_QWORD *)a1 + 5) )
  {
    for ( k = 0; k < *((_DWORD *)a1 + 12); ++k )
    {
      v9 = *((_QWORD *)a1 + 5);
      v10 = 32LL * k;
      if ( (*(_BYTE *)(v10 + v9 + 24) & 8) != 0 )
      {
        v11 = *(_QWORD ***)(v10 + v9 + 8);
        if ( v11 )
        {
          v12 = *v11;
          if ( v12 )
          {
            do
            {
              v13 = (_QWORD *)v12[3];
              operator delete(v12);
              v12 = v13;
            }
            while ( v13 );
          }
        }
      }
    }
    operator delete(*((void **)a1 + 5));
    *((_QWORD *)a1 + 5) = 0;
    *((_QWORD *)a1 + 6) = 0;
  }
  *((_DWORD *)a1 + 9) = 0;
  return 0;
}

```

## disassembly

```asm
0x1800163f4  push    rbx
0x1800163f6  push    rbp
0x1800163f7  push    rsi
0x1800163f8  push    rdi
0x1800163f9  sub     rsp, 28h
0x1800163fd  cmp     qword ptr [rcx+38h], 0
0x180016402  mov     rdi, rcx
0x180016405  mov     rbx, [rcx+18h]
0x180016409  jz      short loc_180016443
0x18001640b  xor     esi, esi
0x18001640d  cmp     [rcx+40h], esi
0x180016410  jbe     short loc_18001642B
0x180016412  mov     rcx, [rdi+38h]
0x180016416  mov     eax, esi
0x180016418  add     rax, rax
0x18001641b  mov     rcx, [rcx+rax*8]; Block
0x18001641f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016424  inc     esi
0x180016426  cmp     esi, [rdi+40h]
0x180016429  jb      short loc_180016412
0x18001642b  mov     rcx, [rdi+38h]; Block
0x18001642f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016434  mov     qword ptr [rdi+38h], 0
0x18001643c  mov     dword ptr [rdi+40h], 0
0x180016443  test    rbx, rbx
0x180016446  jz      short loc_1800164B1
0x180016448  mov     rbp, [rbx]
0x18001644b  xor     eax, eax
0x18001644d  cmp     [rbx+1Ch], eax
0x180016450  jbe     short loc_180016476
0x180016452  mov     rdx, [rbx+10h]
0x180016456  cmp     dword ptr [rax+rdx+10h], 0FFFFFFFEh
0x18001645b  jz      short loc_18001646D
0x18001645d  mov     dword ptr [rax+rdx+10h], 4C7h
0x180016465  mov     dword ptr [rax+rdx+24h], 0FFFFFFFEh
0x18001646d  add     eax, [rax+rdx+14h]
0x180016471  cmp     eax, [rbx+1Ch]
0x180016474  jb      short loc_180016452
0x180016476  mov     rax, [rbx+8]
0x18001647a  cmp     dword ptr [rax+20h], 1
0x18001647e  jz      short loc_180016498
0x180016480  xor     r8d, r8d; int
0x180016483  mov     rdx, rbx; struct PERFLIBCI_QUERY_PROVIDER_NODE *
0x180016486  mov     rcx, rdi; struct _PERF_QUERY *
0x180016489  call    ?PerflibciSendCounterUpdateRequest@@YAKPEAU_PERF_QUERY@@PEAUPERFLIBCI_QUERY_PROVIDER_NODE@@H@Z; PerflibciSendCounterUpdateRequest(_PERF_QUERY *,PERFLIBCI_QUERY_PROVIDER_NODE *,int)
0x18001648e  mov     rcx, [rbx+30h]; Handle
0x180016492  call    cs:__imp_NtClose
0x180016498  mov     rcx, [rbx+10h]; Block
0x18001649c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800164a1  mov     rcx, rbx; Block
0x1800164a4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800164a9  mov     rbx, rbp
0x1800164ac  test    rbp, rbp
0x1800164af  jnz     short loc_180016448
0x1800164b1  mov     rcx, [rdi+48h]; Handle
0x1800164b5  test    rcx, rcx
0x1800164b8  jz      short loc_1800164C0
0x1800164ba  call    cs:__imp_NtClose
0x1800164c0  mov     rcx, [rdi+50h]; Block
0x1800164c4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800164c9  cmp     qword ptr [rdi+28h], 0
0x1800164ce  jz      short loc_18001652B
0x1800164d0  xor     esi, esi
0x1800164d2  cmp     [rdi+30h], esi
0x1800164d5  jbe     short loc_180016512
0x1800164d7  mov     rcx, [rdi+28h]
0x1800164db  mov     eax, esi
0x1800164dd  shl     rax, 5
0x1800164e1  test    byte ptr [rax+rcx+18h], 8
0x1800164e6  jz      short loc_18001650B
0x1800164e8  mov     rcx, [rax+rcx+8]
0x1800164ed  test    rcx, rcx
0x1800164f0  jz      short loc_18001650B
0x1800164f2  mov     rcx, [rcx]; Block
0x1800164f5  test    rcx, rcx
0x1800164f8  jz      short loc_18001650B
0x1800164fa  mov     rbx, [rcx+18h]
0x1800164fe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016503  mov     rcx, rbx
0x180016506  test    rbx, rbx
0x180016509  jnz     short loc_1800164FA
0x18001650b  inc     esi
0x18001650d  cmp     esi, [rdi+30h]
0x180016510  jb      short loc_1800164D7
0x180016512  mov     rcx, [rdi+28h]; Block
0x180016516  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001651b  mov     qword ptr [rdi+28h], 0
0x180016523  mov     qword ptr [rdi+30h], 0
0x18001652b  mov     dword ptr [rdi+24h], 0
0x180016532  xor     eax, eax
0x180016534  add     rsp, 28h
0x180016538  pop     rdi
0x180016539  pop     rsi
0x18001653a  pop     rbp
0x18001653b  pop     rbx
0x18001653c  retn
```
