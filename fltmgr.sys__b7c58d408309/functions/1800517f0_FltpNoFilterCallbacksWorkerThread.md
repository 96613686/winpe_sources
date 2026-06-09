# FltpNoFilterCallbacksWorkerThread

- ea: `0x1800517f0`
- end: `0x180051a0c`
- name: `FltpNoFilterCallbacksWorkerThread`
- size: `540`
- prototype: `void __fastcall(PVOID IoObject, _QWORD *Context, PIO_WORKITEM IoWorkItem)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180009f20`
- `0x180016f40`
- `0x180016f80`
- `0x180017fc0`
- `0x1800247a0`
- `0x1800517f0`
- `0x180060930`

## import_xrefs

- `ntoskrnl!IoPropagateActivityIdToThread` at `0x180051869`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x180051869`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18005183f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18005183f`
- `ntoskrnl!IoClearActivityIdThread` at `0x1800519e7`
- `ntoskrnl!IoClearActivityIdThread` at `0x1800519e7`
- `ntoskrnl!IoUninitializeWorkItem` at `0x180051829`
- `ntoskrnl!IoUninitializeWorkItem` at `0x180051829`

## pseudocode

```c
void __fastcall FltpNoFilterCallbacksWorkerThread(PVOID IoObject, _QWORD *Context, PIO_WORKITEM IoWorkItem)
{
  char *v3; // rsi
  _DWORD *v7; // rbp
  unsigned int v8; // ebx
  __int64 v9; // r9
  int v10; // edx
  _BYTE *v11; // rax
  bool v12; // zf
  _DWORD *v13; // rax
  char v14; // al
  int v15; // eax
  int v16; // eax
  __int64 v17; // rax
  unsigned __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // [rsp+30h] [rbp-48h] BYREF
  __int128 v21; // [rsp+38h] [rbp-40h] BYREF

  v3 = (char *)Context[23];
  v7 = *(_DWORD **)(*(_QWORD *)(*((_QWORD *)v3 + 5) + 64LL) + 80LL);
  IoUninitializeWorkItem(IoWorkItem);
  ExFreeToNPagedLookasideList(&stru_18003ED40, IoWorkItem);
  v20 = 0;
  v21 = 0;
  v8 = IoPropagateActivityIdToThread(Context, &v21, &v20);
  if ( (v7[14] & 0x100) == 0 )
    goto LABEL_32;
  if ( *v3 == 6 )
  {
    v10 = *((_DWORD *)v3 + 4);
    if ( (unsigned int)(v10 - 19) <= 1 || v10 == 39 )
      goto LABEL_31;
    if ( v10 == 13 )
    {
      v11 = (_BYTE *)Context[3];
      if ( !v11 )
        goto LABEL_18;
      v12 = *v11 == 0;
    }
    else
    {
      if ( v10 != 64 )
        goto LABEL_18;
      v13 = (_DWORD *)Context[3];
      if ( !v13 )
        goto LABEL_18;
      v12 = (*v13 & 1) == 0;
    }
    if ( !v12 )
      goto LABEL_31;
  }
  else if ( *v3 == 4 && ((Context[2] & 1) != 0 || (v7[14] & 1) != 0 || v7[15] == 27) && (Context[2] & 0x42) == 0 )
  {
    goto LABEL_31;
  }
LABEL_18:
  v14 = *v3;
  if ( *v3 )
  {
    if ( v14 == 13 )
    {
      v15 = *((_DWORD *)v3 + 6);
      if ( v15 != 622792 && v15 != 623208 && v15 != 1327346 && v15 != 1343730 && v15 != 590047 )
        goto LABEL_32;
    }
    else
    {
      if ( v14 != 14 )
        goto LABEL_32;
      v16 = *((_DWORD *)v3 + 6);
      if ( v16 != 1328152 && v16 != 1344540 )
        goto LABEL_32;
    }
LABEL_31:
    LOBYTE(v9) = 1;
    if ( (unsigned int)FltpDataScanConflictProcessing(Context, IoObject, 0, v9) == -1073741802 )
      goto LABEL_39;
    goto LABEL_32;
  }
  if ( *((_DWORD *)v3 + 4) < 0x1000000u )
    goto LABEL_31;
LABEL_32:
  FltpPurgeAndReinstateNameCacheForPosixDelete(v7);
  v17 = Context[23];
  if ( *(_BYTE *)v17 == 6 )
  {
    v18 = (unsigned int)(*(_DWORD *)(v17 + 16) - 10);
    if ( (unsigned int)v18 <= 0x3E )
    {
      v19 = 0x4080000040000003LL;
      if ( _bittest64(&v19, v18) )
        FltpReinstateNameCachingAllFrames(v7, 0);
    }
  }
  if ( *((_BYTE *)Context + 65) )
    *(_BYTE *)(Context[23] + 3LL) |= 1u;
  FltpCompleteRequest(Context, *((unsigned int *)Context + 12));
LABEL_39:
  if ( (int)FltpDbgStatus(v8, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 4753, 0) >= 0 )
    IoClearActivityIdThread(v20);
}

```

## disassembly

```asm
0x1800517f0  push    rbx
0x1800517f2  push    rbp
0x1800517f3  push    rsi
0x1800517f4  push    rdi
0x1800517f5  push    r14
0x1800517f7  sub     rsp, 50h
0x1800517fb  mov     rax, cs:__security_cookie
0x180051802  xor     rax, rsp
0x180051805  mov     [rsp+78h+var_30], rax
0x18005180a  mov     rsi, [rdx+0B8h]
0x180051811  mov     r14, rcx
0x180051814  mov     rbx, r8
0x180051817  mov     rdi, rdx
0x18005181a  mov     rax, [rsi+28h]
0x18005181e  mov     rcx, [rax+40h]
0x180051822  mov     rbp, [rcx+50h]
0x180051826  mov     rcx, r8; IoWorkItem
0x180051829  call    cs:__imp_IoUninitializeWorkItem
0x180051830  nop     dword ptr [rax+rax+00h]
0x180051835  mov     rdx, rbx; Entry
0x180051838  lea     rcx, stru_18003ED40; Lookaside
0x18005183f  call    cs:__imp_ExFreeToNPagedLookasideList
0x180051846  nop     dword ptr [rax+rax+00h]
0x18005184b  xorps   xmm0, xmm0
0x18005184e  mov     [rsp+78h+var_48], 0
0x180051857  lea     r8, [rsp+78h+var_48]
0x18005185c  mov     rcx, rdi
0x18005185f  lea     rdx, [rsp+78h+var_40]
0x180051864  movups  [rsp+78h+var_40], xmm0
0x180051869  call    cs:__imp_IoPropagateActivityIdToThread
0x180051870  nop     dword ptr [rax+rax+00h]
0x180051875  mov     ecx, [rbp+38h]
0x180051878  mov     ebx, eax
0x18005187a  bt      ecx, 8
0x18005187e  jnb     loc_180051956
0x180051884  mov     cl, [rsi]
0x180051886  cmp     cl, 6
0x180051889  jnz     short loc_1800518CC
0x18005188b  mov     edx, [rsi+10h]
0x18005188e  lea     ecx, [rdx-13h]
0x180051891  cmp     ecx, 1
0x180051894  jbe     loc_18005193E
0x18005189a  cmp     edx, 27h ; '''
0x18005189d  jz      loc_18005193E
0x1800518a3  cmp     edx, 0Dh
0x1800518a6  jnz     short loc_1800518B6
0x1800518a8  mov     rax, [rdi+18h]
0x1800518ac  test    rax, rax
0x1800518af  jz      short loc_1800518EC
0x1800518b1  cmp     byte ptr [rax], 0
0x1800518b4  jmp     short loc_1800518C8
0x1800518b6  cmp     edx, 40h ; '@'
0x1800518b9  jnz     short loc_1800518EC
0x1800518bb  mov     rax, [rdi+18h]
0x1800518bf  test    rax, rax
0x1800518c2  jz      short loc_1800518EC
0x1800518c4  mov     eax, [rax]
0x1800518c6  test    al, 1
0x1800518c8  jnz     short loc_18005193E
0x1800518ca  jmp     short loc_1800518EC
0x1800518cc  cmp     cl, 4
0x1800518cf  jnz     short loc_1800518EC
0x1800518d1  mov     eax, [rdi+10h]
0x1800518d4  test    al, 1
0x1800518d6  jnz     short loc_1800518E5
0x1800518d8  mov     eax, [rbp+38h]
0x1800518db  test    al, 1
0x1800518dd  jnz     short loc_1800518E5
0x1800518df  cmp     dword ptr [rbp+3Ch], 1Bh
0x1800518e3  jnz     short loc_1800518EC
0x1800518e5  mov     eax, [rdi+10h]
0x1800518e8  test    al, 42h
0x1800518ea  jz      short loc_18005193E
0x1800518ec  mov     al, [rsi]
0x1800518ee  test    al, al
0x1800518f0  jnz     short loc_1800518FD
0x1800518f2  cmp     dword ptr [rsi+10h], 1000000h
0x1800518f9  jnb     short loc_180051956
0x1800518fb  jmp     short loc_18005193E
0x1800518fd  cmp     al, 0Dh
0x1800518ff  jnz     short loc_180051929
0x180051901  mov     eax, [rsi+18h]
0x180051904  cmp     eax, 980C8h
0x180051909  jz      short loc_18005193E
0x18005190b  cmp     eax, 98268h
0x180051910  jz      short loc_18005193E
0x180051912  cmp     eax, 1440F2h
0x180051917  jz      short loc_18005193E
0x180051919  cmp     eax, 1480F2h
0x18005191e  jz      short loc_18005193E
0x180051920  cmp     eax, 900DFh
0x180051925  jz      short loc_18005193E
0x180051927  jmp     short loc_180051956
0x180051929  cmp     al, 0Eh
0x18005192b  jnz     short loc_180051956
0x18005192d  mov     eax, [rsi+18h]
0x180051930  cmp     eax, 144418h
0x180051935  jz      short loc_18005193E
0x180051937  cmp     eax, 14841Ch
0x18005193c  jnz     short loc_180051956
0x18005193e  mov     r9b, 1
0x180051941  xor     r8d, r8d
0x180051944  mov     rdx, r14
0x180051947  mov     rcx, rdi
0x18005194a  call    FltpDataScanConflictProcessing
0x18005194f  cmp     eax, 0C0000016h
0x180051954  jz      short loc_1800519C7
0x180051956  mov     rdx, [rsi+30h]
0x18005195a  xor     r9d, r9d
0x18005195d  mov     r8, rdi
0x180051960  mov     rcx, rbp; OwnerId
0x180051963  call    FltpPurgeAndReinstateNameCacheForPosixDelete
0x180051968  mov     rax, [rdi+0B8h]
0x18005196f  cmp     byte ptr [rax], 6
0x180051972  jnz     short loc_1800519AB
0x180051974  mov     eax, [rax+10h]
0x180051977  add     eax, 0FFFFFFF6h
0x18005197a  cmp     eax, 3Eh ; '>'
0x18005197d  ja      short loc_1800519AB
0x18005197f  mov     rcx, 4080000040000003h
0x180051989  bt      rcx, rax
0x18005198d  jnb     short loc_1800519AB
0x18005198f  mov     r8d, [rdi+30h]
0x180051993  mov     r9, rdi
0x180051996  mov     rdx, [rsi+30h]
0x18005199a  mov     rcx, rbp; OwnerId
0x18005199d  mov     [rsp+78h+var_58], 0; __int64
0x1800519a6  call    FltpReinstateNameCachingAllFrames
0x1800519ab  cmp     byte ptr [rdi+41h], 0
0x1800519af  jz      short loc_1800519BC
0x1800519b1  mov     rax, [rdi+0B8h]
0x1800519b8  or      byte ptr [rax+3], 1
0x1800519bc  mov     edx, [rdi+30h]
0x1800519bf  mov     rcx, rdi
0x1800519c2  call    FltpCompleteRequest
0x1800519c7  mov     r8d, 1291h
0x1800519cd  lea     rdx, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x1800519d4  xor     r9d, r9d
0x1800519d7  mov     ecx, ebx
0x1800519d9  call    FltpDbgStatus
0x1800519de  test    eax, eax
0x1800519e0  js      short loc_1800519F3
0x1800519e2  mov     rcx, [rsp+78h+var_48]
0x1800519e7  call    cs:__imp_IoClearActivityIdThread
0x1800519ee  nop     dword ptr [rax+rax+00h]
0x1800519f3  mov     rcx, [rsp+78h+var_30]
0x1800519f8  xor     rcx, rsp; StackCookie
0x1800519fb  call    __security_check_cookie
0x180051a00  add     rsp, 50h
0x180051a04  pop     r14
0x180051a06  pop     rdi
0x180051a07  pop     rsi
0x180051a08  pop     rbp
0x180051a09  pop     rbx
0x180051a0a  retn
```
