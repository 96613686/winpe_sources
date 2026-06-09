# NcaUserStoreCreateHelper(_TOKEN_USER *,void *,int,NCA_USER_ * *,int *)

- ea: `0x180017c78`
- end: `0x180017e5f`
- name: `?NcaUserStoreCreateHelper@@YAKPEAU_TOKEN_USER@@PEAXHPEAPEAUNCA_USER_@@PEAH@Z`
- size: `487`
- prototype: `__int64 __fastcall(struct _TOKEN_USER *, void *, int, struct NCA_USER_ **, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017708`

## callees

- `0x180003770`
- `0x180004f34`
- `0x180017c78`
- `0x18001abd4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180017da4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180017da4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017db9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017db9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180017ce8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180017ce8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180017d55`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180017d55`

## pseudocode

```c
__int64 __fastcall NcaUserStoreCreateHelper(struct _TOKEN_USER *a1, void *a2, int a3, struct NCA_USER_ **a4, int *a5)
{
  __int64 v9; // rbx
  DWORD LastError; // edi
  DWORD v11; // ebp
  void *v12; // rax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  PTP_WORK ThreadpoolWork; // rax
  int v16; // edx
  signed __int32 v17; // eax

  v9 = NcaAlloc(80);
  if ( v9 )
  {
    v11 = 10 * GetLengthSid(a1->User.Sid);
    v12 = (void *)NcaAlloc(v11);
    *(_QWORD *)(v9 + 24) = v12;
    if ( !v12 )
    {
      LastError = 14;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_f6fba97516d23319eaec26e747470e80_Traceguids, 14);
      goto LABEL_20;
    }
    if ( CopySid(v11, v12, a1->User.Sid) )
    {
      ThreadpoolWork = CreateThreadpoolWork(NcaUserStoreCloseCallback, (PVOID)v9, 0);
      *(_QWORD *)(v9 + 40) = ThreadpoolWork;
      if ( ThreadpoolWork )
      {
        LastError = 0;
        v16 = 1;
        v17 = _InterlockedIncrement(&dword_180029580);
        *(_QWORD *)(v9 + 32) = a2;
        *(_DWORD *)(v9 + 16) = v17;
        *(_DWORD *)(v9 + 20) = v17;
        *(_DWORD *)(v9 + 72) = 1;
        *(_DWORD *)(v9 + 56) = a3;
        if ( !dword_180029598 || !a3 )
          v16 = 0;
        *a5 = v16;
        goto LABEL_25;
      }
      LastError = GetLastError();
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 19;
        goto LABEL_17;
      }
    }
    else
    {
      LastError = GetLastError();
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 18;
LABEL_17:
        WPP_SF_d(v13[2], v14, WPP_f6fba97516d23319eaec26e747470e80_Traceguids, LastError);
      }
    }
    if ( LastError )
    {
      NcaFree(*(LPVOID *)(v9 + 24));
LABEL_20:
      NcaFree((LPVOID)v9);
      return LastError;
    }
LABEL_25:
    *a4 = (struct NCA_USER_ *)v9;
    return LastError;
  }
  LastError = 14;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_f6fba97516d23319eaec26e747470e80_Traceguids, 14);
  return LastError;
}

```

## disassembly

```asm
0x180017c78  push    rbx
0x180017c7a  push    rbp
0x180017c7b  push    rsi
0x180017c7c  push    rdi
0x180017c7d  push    r14
0x180017c7f  push    r15
0x180017c81  sub     rsp, 28h
0x180017c85  mov     rdi, rcx
0x180017c88  mov     r15, r9
0x180017c8b  mov     ecx, 50h ; 'P'
0x180017c90  mov     esi, r8d
0x180017c93  mov     r14, rdx
0x180017c96  call    NcaAlloc
0x180017c9b  mov     rbx, rax
0x180017c9e  test    rax, rax
0x180017ca1  jnz     short loc_180017CE5
0x180017ca3  lea     r9d, [rax+0Eh]
0x180017ca7  mov     edi, r9d
0x180017caa  mov     rcx, cs:WPP_GLOBAL_Control
0x180017cb1  lea     rax, WPP_GLOBAL_Control
0x180017cb8  cmp     rcx, rax
0x180017cbb  jz      loc_180017E4F
0x180017cc1  lea     edx, [rbx+1]
0x180017cc4  test    [rcx+1Ch], dl
0x180017cc7  jz      loc_180017E4F
0x180017ccd  mov     rcx, [rcx+10h]
0x180017cd1  lea     edx, [rbx+10h]
0x180017cd4  lea     r8, WPP_f6fba97516d23319eaec26e747470e80_Traceguids
0x180017cdb  call    WPP_SF_d
0x180017ce0  jmp     loc_180017E4F
0x180017ce5  mov     rcx, [rdi]; pSid
0x180017ce8  call    cs:__imp_GetLengthSid
0x180017cef  nop     dword ptr [rax+rax+00h]
0x180017cf4  lea     ecx, [rax+rax*4]
0x180017cf7  add     ecx, ecx
0x180017cf9  mov     ebp, ecx
0x180017cfb  call    NcaAlloc
0x180017d00  mov     [rbx+18h], rax
0x180017d04  test    rax, rax
0x180017d07  jnz     short loc_180017D4D
0x180017d09  lea     r9d, [rax+0Eh]
0x180017d0d  mov     edi, r9d
0x180017d10  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d17  lea     rax, WPP_GLOBAL_Control
0x180017d1e  cmp     rcx, rax
0x180017d21  jz      loc_180017E09
0x180017d27  lea     edx, [r9-0Dh]
0x180017d2b  test    [rcx+1Ch], dl
0x180017d2e  jz      loc_180017E09
0x180017d34  mov     rcx, [rcx+10h]
0x180017d38  lea     edx, [r9+3]
0x180017d3c  lea     r8, WPP_f6fba97516d23319eaec26e747470e80_Traceguids
0x180017d43  call    WPP_SF_d
0x180017d48  jmp     loc_180017E09
0x180017d4d  mov     r8, [rdi]; pSourceSid
0x180017d50  mov     rdx, rax; pDestinationSid
0x180017d53  mov     ecx, ebp; nDestinationSidLength
0x180017d55  call    cs:__imp_CopySid
0x180017d5c  nop     dword ptr [rax+rax+00h]
0x180017d61  test    eax, eax
0x180017d63  jnz     short loc_180017D97
0x180017d65  call    cs:__imp_GetLastError
0x180017d6c  nop     dword ptr [rax+rax+00h]
0x180017d71  mov     edi, eax
0x180017d73  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d7a  lea     rax, WPP_GLOBAL_Control
0x180017d81  cmp     rcx, rax
0x180017d84  jz      short loc_180017DFC
0x180017d86  mov     edx, 1
0x180017d8b  test    [rcx+1Ch], dl
0x180017d8e  jz      short loc_180017DFC
0x180017d90  mov     edx, 12h
0x180017d95  jmp     short loc_180017DE9
0x180017d97  xor     r8d, r8d; pcbe
0x180017d9a  lea     rcx, ?NcaUserStoreCloseCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180017da1  mov     rdx, rbx; pv
0x180017da4  call    cs:__imp_CreateThreadpoolWork
0x180017dab  nop     dword ptr [rax+rax+00h]
0x180017db0  mov     [rbx+28h], rax
0x180017db4  test    rax, rax
0x180017db7  jnz     short loc_180017E13
0x180017db9  call    cs:__imp_GetLastError
0x180017dc0  nop     dword ptr [rax+rax+00h]
0x180017dc5  mov     edi, eax
0x180017dc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180017dce  lea     rax, WPP_GLOBAL_Control
0x180017dd5  cmp     rcx, rax
0x180017dd8  jz      short loc_180017DFC
0x180017dda  mov     edx, 1
0x180017ddf  test    [rcx+1Ch], dl
0x180017de2  jz      short loc_180017DFC
0x180017de4  mov     edx, 13h
0x180017de9  mov     rcx, [rcx+10h]
0x180017ded  lea     r8, WPP_f6fba97516d23319eaec26e747470e80_Traceguids
0x180017df4  mov     r9d, edi
0x180017df7  call    WPP_SF_d
0x180017dfc  test    edi, edi
0x180017dfe  jz      short loc_180017E4C
0x180017e00  mov     rcx, [rbx+18h]; lpMem
0x180017e04  call    NcaFree
0x180017e09  mov     rcx, rbx; lpMem
0x180017e0c  call    NcaFree
0x180017e11  jmp     short loc_180017E4F
0x180017e13  xor     edi, edi
0x180017e15  lea     edx, [rdi+1]
0x180017e18  mov     eax, edx
0x180017e1a  lock xadd cs:dword_180029580, eax
0x180017e22  add     eax, edx
0x180017e24  mov     [rbx+20h], r14
0x180017e28  mov     [rbx+10h], eax
0x180017e2b  mov     [rbx+14h], eax
0x180017e2e  mov     [rbx+48h], edx
0x180017e31  mov     [rbx+38h], esi
0x180017e34  cmp     cs:dword_180029598, edi
0x180017e3a  jz      short loc_180017E40
0x180017e3c  test    esi, esi
0x180017e3e  jnz     short loc_180017E42
0x180017e40  xor     edx, edx
0x180017e42  mov     rax, [rsp+58h+arg_20]
0x180017e4a  mov     [rax], edx
0x180017e4c  mov     [r15], rbx
0x180017e4f  mov     eax, edi
0x180017e51  add     rsp, 28h
0x180017e55  pop     r15
0x180017e57  pop     r14
0x180017e59  pop     rdi
0x180017e5a  pop     rsi
0x180017e5b  pop     rbp
0x180017e5c  pop     rbx
0x180017e5d  retn
```
