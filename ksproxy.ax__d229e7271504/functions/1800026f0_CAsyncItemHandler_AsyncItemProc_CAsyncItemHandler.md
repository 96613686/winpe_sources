# CAsyncItemHandler::AsyncItemProc(CAsyncItemHandler *)

- ea: `0x1800026f0`
- end: `0x180002b51`
- name: `?AsyncItemProc@CAsyncItemHandler@@KAKPEAV1@@Z`
- size: `1121`
- prototype: `__int64 __fastcall(char *Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800026f0`
- `0x180002b58`
- `0x18001c488`
- `0x18001cb40`
- `0x18003b50c`
- `0x18004485c`
- `0x180045010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800028e5`
- `KERNEL32!GetLastError` at `0x1800028e5`
- `KERNEL32!SetEvent` at `0x1800028c7`
- `KERNEL32!SetEvent` at `0x1800028c7`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800027a9`
- `KERNEL32!WaitForSingleObjectEx` at `0x180002937`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800027a9`
- `KERNEL32!WaitForSingleObjectEx` at `0x180002937`
- `KERNEL32!ReleaseMutex` at `0x180002790`
- `KERNEL32!ReleaseMutex` at `0x180002824`
- `KERNEL32!ReleaseMutex` at `0x180002a2f`
- `KERNEL32!ReleaseMutex` at `0x180002790`
- `KERNEL32!ReleaseMutex` at `0x180002824`
- `KERNEL32!ReleaseMutex` at `0x180002a2f`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180002743`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180002743`
- `KERNEL32!ReleaseSemaphore` at `0x180002840`
- `KERNEL32!ReleaseSemaphore` at `0x180002a4f`
- `KERNEL32!ReleaseSemaphore` at `0x180002840`
- `KERNEL32!ReleaseSemaphore` at `0x180002a4f`
- `KERNEL32!GetHandleInformation` at `0x180002a9f`
- `KERNEL32!GetHandleInformation` at `0x180002a9f`

## pseudocode

```c
__int64 __fastcall CAsyncItemHandler::AsyncItemProc(char *Parameter)
{
  DWORD v2; // edi
  DWORD v3; // eax
  __int64 v4; // r8
  __int64 v5; // rsi
  char *v6; // r14
  __int64 v7; // rdx
  char v8; // di
  void *v9; // rcx
  unsigned int v10; // eax
  char *v11; // rdi
  struct _ITEM_LIST_HEAD *v12; // rcx
  _ITEM_LIST_ITEM *fLink; // rdi
  LONG v14; // edi
  unsigned int v15; // esi
  unsigned int j; // edi
  bool v17; // zf
  _DWORD *v18; // rax
  __int64 v19; // rdx
  __int64 v21; // r9
  DWORD LastError; // eax
  unsigned int v23; // ecx
  LONG v24; // esi
  unsigned int i; // edi
  __int64 v26; // rbp
  void *v27; // rcx
  __int64 v28; // rax
  DWORD dwFlags; // [rsp+60h] [rbp+8h] BYREF

  while ( 1 )
  {
    v2 = 64;
    if ( *((_DWORD *)Parameter + 256) < 0x40u )
      v2 = *((_DWORD *)Parameter + 256);
    v3 = WaitForMultipleObjectsEx(v2, (const HANDLE *)Parameter, 0, 0xFFFFFFFF, 0);
    v5 = v3;
    if ( v3 == -1 )
      break;
    if ( v3 >= v2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        LastError = GetLastError();
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          208,
          &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids,
          (unsigned int)v5,
          LastError);
      }
      goto LABEL_15;
    }
    if ( v3 )
    {
      v6 = &Parameter[8 * v3];
      v7 = *((_QWORD *)v6 + 64);
      v8 = *(_BYTE *)(v7 + 16);
      (*(void (__fastcall **)(_QWORD))(v7 + 32))(0);
      v9 = (void *)*((_QWORD *)Parameter + 139);
      if ( v8 )
      {
        WaitForSingleObjectEx(v9, 0xFFFFFFFF, 0);
        v10 = --*((_DWORD *)Parameter + 256);
        if ( (unsigned int)v5 < v10 )
        {
          v11 = &Parameter[8 * v5];
          memmove_0(v11, v11 + 8, 8LL * (v10 - (unsigned int)v5));
          memmove_0(v6 + 512, v11 + 520, 8LL * (unsigned int)(*((_DWORD *)Parameter + 256) - v5));
        }
        v12 = (struct _ITEM_LIST_HEAD *)(Parameter + 1048);
        if ( *((_DWORD *)Parameter + 270) && (fLink = v12->head.fLink) != 0 )
        {
          ItemListRemoveItem(v12, v12->head.fLink);
          *(_QWORD *)&Parameter[8 * *((unsigned int *)Parameter + 256)] = fLink[1].bLink;
          *(_QWORD *)&Parameter[8 * *((unsigned int *)Parameter + 256) + 512] = fLink;
          v14 = 0;
          ++*((_DWORD *)Parameter + 256);
        }
        else
        {
          v14 = 1;
        }
        ReleaseMutex(*((HANDLE *)Parameter + 139));
        if ( v14 )
          ReleaseSemaphore(*((HANDLE *)Parameter + 138), v14, 0);
      }
      else
      {
        ReleaseMutex(v9);
      }
    }
    else
    {
      v21 = *((unsigned int *)Parameter + 257);
      if ( (unsigned int)v21 > 1 )
      {
        if ( (_DWORD)v21 != 2 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 209, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, v21);
          goto LABEL_15;
        }
        WaitForSingleObjectEx(*((HANDLE *)Parameter + 139), 0xFFFFFFFF, 0);
        v23 = *((_DWORD *)Parameter + 256);
        v24 = 0;
        if ( v23 > 1 )
        {
          for ( i = 1; i < v23; ++i )
          {
            if ( *(_QWORD *)&Parameter[8 * i] == *((_QWORD *)Parameter + 129) )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)&Parameter[8 * i + 512] + 32LL))(1);
              v23 = --*((_DWORD *)Parameter + 256);
              if ( i < v23 )
              {
                memmove_0(Parameter, Parameter + 8, 8LL * v23);
                memmove_0(Parameter + 512, Parameter + 520, 8LL * *((unsigned int *)Parameter + 256));
                v23 = *((_DWORD *)Parameter + 256);
              }
              if ( *((_DWORD *)Parameter + 270) && (v26 = *((_QWORD *)Parameter + 131)) != 0 )
              {
                ItemListRemoveItem(
                  (struct _ITEM_LIST_HEAD *)(Parameter + 1048),
                  *((struct _ITEM_LIST_ITEM **)Parameter + 131));
                *(_QWORD *)&Parameter[8 * *((unsigned int *)Parameter + 256)] = *(_QWORD *)(v26 + 24);
                *(_QWORD *)&Parameter[8 * (*((_DWORD *)Parameter + 256))++ + 512] = v26;
                v23 = *((_DWORD *)Parameter + 256);
              }
              else
              {
                ++v24;
              }
            }
          }
        }
        ReleaseMutex(*((HANDLE *)Parameter + 139));
        if ( v24 )
          ReleaseSemaphore(*((HANDLE *)Parameter + 138), v24, 0);
      }
      SetEvent(*((HANDLE *)Parameter + 130));
    }
LABEL_15:
    if ( !*((_DWORD *)Parameter + 257) )
      goto LABEL_16;
  }
  v27 = *(void **)Parameter;
  dwFlags = 0;
  if ( GetHandleInformation(v27, &dwFlags) )
    goto LABEL_15;
LABEL_16:
  v15 = *((_DWORD *)Parameter + 256);
  for ( j = 1; j < v15; ++j )
  {
    v28 = *(_QWORD *)&Parameter[8 * j + 512];
    if ( v28 && !*(_BYTE *)(v28 + 16) )
    {
      (*(void (__fastcall **)(__int64, _QWORD))(v28 + 32))(1, *(_QWORD *)&Parameter[8 * j + 512]);
      --*((_DWORD *)Parameter + 256);
    }
  }
  v17 = (*((_DWORD *)Parameter + 256))-- == 1;
  v18 = Parameter + 1080;
  v19 = *((unsigned int *)Parameter + 256);
  if ( v17 && !*v18 || WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return (unsigned int)v19;
  WPP_SF_qdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v4, Parameter, v19, *v18);
  return *((unsigned int *)Parameter + 256);
}

```

## disassembly

```asm
0x1800026f0  push    rbx
0x1800026f2  push    r12
0x1800026f4  sub     rsp, 48h
0x1800026f8  mov     [rsp+58h+arg_8], rbp
0x1800026fd  lea     r12, WPP_GLOBAL_Control
0x180002704  mov     [rsp+58h+arg_10], rsi
0x180002709  mov     rbx, rcx
0x18000270c  mov     [rsp+58h+var_18], rdi
0x180002711  mov     [rsp+58h+var_28], r15
0x180002716  xor     r15d, r15d
0x180002719  mov     [rsp+58h+var_20], r14
0x18000271e  xchg    ax, ax
0x180002720  mov     eax, [rbx+400h]
0x180002726  mov     edi, 40h ; '@'
0x18000272b  cmp     eax, edi
0x18000272d  mov     [rsp+58h+bAlertable], r15d; bAlertable
0x180002732  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x180002738  mov     rdx, rbx; lpHandles
0x18000273b  cmovb   edi, eax
0x18000273e  xor     r8d, r8d; bWaitAll
0x180002741  mov     ecx, edi; nCount
0x180002743  call    cs:__imp_WaitForMultipleObjectsEx
0x18000274a  nop     dword ptr [rax+rax+00h]
0x18000274f  mov     esi, eax
0x180002751  cmp     eax, 0FFFFFFFFh
0x180002754  jz      loc_180002A92
0x18000275a  cmp     esi, edi
0x18000275c  jnb     loc_1800028D8
0x180002762  test    eax, eax
0x180002764  jz      loc_1800028B3
0x18000276a  lea     r14, [rbx+rsi*8]
0x18000276e  xor     ecx, ecx
0x180002770  mov     rdx, [r14+200h]
0x180002777  mov     rax, [rdx+20h]
0x18000277b  movzx   edi, byte ptr [rdx+10h]
0x18000277f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002784  mov     rcx, [rbx+458h]; hHandle
0x18000278b  test    dil, dil
0x18000278e  jnz     short loc_1800027A1
0x180002790  call    cs:__imp_ReleaseMutex
0x180002797  nop     dword ptr [rax+rax+00h]
0x18000279c  jmp     loc_18000284C
0x1800027a1  xor     r8d, r8d; bAlertable
0x1800027a4  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800027a9  call    cs:__imp_WaitForSingleObjectEx
0x1800027b0  nop     dword ptr [rax+rax+00h]
0x1800027b5  dec     dword ptr [rbx+400h]
0x1800027bb  mov     eax, [rbx+400h]
0x1800027c1  cmp     esi, eax
0x1800027c3  jnb     short loc_1800027FF
0x1800027c5  sub     eax, esi
0x1800027c7  lea     rdi, [rbx+rsi*8]
0x1800027cb  mov     r8d, eax
0x1800027ce  lea     rdx, [rdi+8]; Src
0x1800027d2  shl     r8, 3; Size
0x1800027d6  mov     rcx, rdi; void *
0x1800027d9  call    memmove_0
0x1800027de  mov     r8d, [rbx+400h]
0x1800027e5  lea     rdx, [rdi+208h]; Src
0x1800027ec  sub     r8d, esi
0x1800027ef  lea     rcx, [r14+200h]; void *
0x1800027f6  shl     r8, 3; Size
0x1800027fa  call    memmove_0
0x1800027ff  lea     rcx, [rbx+418h]; struct _ITEM_LIST_HEAD *
0x180002806  cmp     [rcx+20h], r15d
0x18000280a  jbe     short loc_180002818
0x18000280c  mov     rdi, [rcx]
0x18000280f  test    rdi, rdi
0x180002812  jnz     loc_180002A60
0x180002818  mov     edi, 1
0x18000281d  mov     rcx, [rbx+458h]; hMutex
0x180002824  call    cs:__imp_ReleaseMutex
0x18000282b  nop     dword ptr [rax+rax+00h]
0x180002830  test    edi, edi
0x180002832  jz      short loc_18000284C
0x180002834  mov     rcx, [rbx+450h]; hSemaphore
0x18000283b  xor     r8d, r8d; lpPreviousCount
0x18000283e  mov     edx, edi; lReleaseCount
0x180002840  call    cs:__imp_ReleaseSemaphore
0x180002847  nop     dword ptr [rax+rax+00h]
0x18000284c  cmp     [rbx+404h], r15d
0x180002853  jnz     loc_180002720
0x180002859  mov     esi, [rbx+400h]
0x18000285f  mov     edi, 1
0x180002864  mov     r15, [rsp+58h+var_28]
0x180002869  mov     r14, [rsp+58h+var_20]
0x18000286e  mov     rbp, [rsp+58h+arg_8]
0x180002873  cmp     esi, edi
0x180002875  ja      loc_180002AE9
0x18000287b  add     dword ptr [rbx+400h], 0FFFFFFFFh
0x180002882  lea     rax, [rbx+438h]
0x180002889  mov     edx, [rbx+400h]
0x18000288f  mov     rdi, [rsp+58h+var_18]
0x180002894  mov     rsi, [rsp+58h+arg_10]
0x180002899  jnz     loc_180002B20
0x18000289f  cmp     dword ptr [rax], 0
0x1800028a2  ja      loc_180002B20
0x1800028a8  mov     eax, edx
0x1800028aa  add     rsp, 48h
0x1800028ae  pop     r12
0x1800028b0  pop     rbx
0x1800028b1  retn
0x1800028b3  mov     r9d, [rbx+404h]
0x1800028ba  cmp     r9d, 1
0x1800028be  jnz     short loc_180002919
0x1800028c0  mov     rcx, [rbx+410h]; hEvent
0x1800028c7  call    cs:__imp_SetEvent
0x1800028ce  nop     dword ptr [rax+rax+00h]
0x1800028d3  jmp     loc_18000284C
0x1800028d8  cmp     cs:WPP_GLOBAL_Control, r12
0x1800028df  jz      loc_18000284C
0x1800028e5  call    cs:__imp_GetLastError
0x1800028ec  nop     dword ptr [rax+rax+00h]
0x1800028f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028f8  lea     r8, WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x1800028ff  mov     edx, 0D0h
0x180002904  mov     [rsp+58h+bAlertable], eax
0x180002908  mov     r9d, esi
0x18000290b  mov     rcx, [rcx+10h]
0x18000290f  call    WPP_SF_DD
0x180002914  jmp     loc_18000284C
0x180002919  test    r9d, r9d
0x18000291c  jz      short loc_1800028C0
0x18000291e  cmp     r9d, 2
0x180002922  jnz     loc_180002AB8
0x180002928  mov     rcx, [rbx+458h]; hHandle
0x18000292f  xor     r8d, r8d; bAlertable
0x180002932  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180002937  call    cs:__imp_WaitForSingleObjectEx
0x18000293e  nop     dword ptr [rax+rax+00h]
0x180002943  mov     ecx, [rbx+400h]
0x180002949  mov     esi, r15d
0x18000294c  cmp     ecx, 1
0x18000294f  jbe     loc_180002A28
0x180002955  mov     edi, 1
0x18000295a  mov     rax, [rbx+408h]
0x180002961  mov     edx, edi
0x180002963  cmp     [rbx+rdx*8], rax
0x180002967  jnz     loc_180002A1E
0x18000296d  mov     rdx, [rbx+rdx*8+200h]
0x180002975  mov     ecx, 1
0x18000297a  mov     rax, [rdx+20h]
0x18000297e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002983  dec     dword ptr [rbx+400h]
0x180002989  mov     ecx, [rbx+400h]
0x18000298f  cmp     edi, ecx
0x180002991  jnb     short loc_1800029CA
0x180002993  mov     r8d, ecx
0x180002996  lea     rdx, [rbx+8]; Src
0x18000299a  shl     r8, 3; Size
0x18000299e  mov     rcx, rbx; void *
0x1800029a1  call    memmove_0
0x1800029a6  mov     r8d, [rbx+400h]
0x1800029ad  lea     rdx, [rbx+208h]; Src
0x1800029b4  shl     r8, 3; Size
0x1800029b8  lea     rcx, [rbx+200h]; void *
0x1800029bf  call    memmove_0
0x1800029c4  mov     ecx, [rbx+400h]
0x1800029ca  cmp     [rbx+438h], r15d
0x1800029d1  jbe     loc_180002AE2
0x1800029d7  mov     rbp, [rbx+418h]
0x1800029de  test    rbp, rbp
0x1800029e1  jz      loc_180002AE2
0x1800029e7  mov     rdx, rbp; struct _ITEM_LIST_ITEM *
0x1800029ea  lea     rcx, [rbx+418h]; struct _ITEM_LIST_HEAD *
0x1800029f1  call    ?ItemListRemoveItem@@YAPEAU_ITEM_LIST_ITEM@@PEAU_ITEM_LIST_HEAD@@PEAU1@@Z; ItemListRemoveItem(_ITEM_LIST_HEAD *,_ITEM_LIST_ITEM *)
0x1800029f6  mov     ecx, [rbx+400h]
0x1800029fc  mov     rax, [rbp+18h]
0x180002a00  mov     [rbx+rcx*8], rax
0x180002a04  mov     eax, [rbx+400h]
0x180002a0a  mov     [rbx+rax*8+200h], rbp
0x180002a12  inc     dword ptr [rbx+400h]
0x180002a18  mov     ecx, [rbx+400h]
0x180002a1e  inc     edi
0x180002a20  cmp     edi, ecx
0x180002a22  jb      loc_18000295A
0x180002a28  mov     rcx, [rbx+458h]; hMutex
0x180002a2f  call    cs:__imp_ReleaseMutex
0x180002a36  nop     dword ptr [rax+rax+00h]
0x180002a3b  test    esi, esi
0x180002a3d  jz      loc_1800028C0
0x180002a43  mov     rcx, [rbx+450h]; hSemaphore
0x180002a4a  xor     r8d, r8d; lpPreviousCount
0x180002a4d  mov     edx, esi; lReleaseCount
0x180002a4f  call    cs:__imp_ReleaseSemaphore
0x180002a56  nop     dword ptr [rax+rax+00h]
0x180002a5b  jmp     loc_1800028C0
0x180002a60  mov     rdx, rdi; struct _ITEM_LIST_ITEM *
0x180002a63  call    ?ItemListRemoveItem@@YAPEAU_ITEM_LIST_ITEM@@PEAU_ITEM_LIST_HEAD@@PEAU1@@Z; ItemListRemoveItem(_ITEM_LIST_HEAD *,_ITEM_LIST_ITEM *)
0x180002a68  mov     rax, [rdi+18h]
0x180002a6c  mov     ecx, [rbx+400h]
0x180002a72  mov     [rbx+rcx*8], rax
0x180002a76  mov     eax, [rbx+400h]
0x180002a7c  mov     [rbx+rax*8+200h], rdi
0x180002a84  mov     edi, r15d
0x180002a87  inc     dword ptr [rbx+400h]
0x180002a8d  jmp     loc_18000281D
0x180002a92  mov     rcx, [rbx]; hObject
0x180002a95  lea     rdx, [rsp+58h+dwFlags]; lpdwFlags
0x180002a9a  mov     [rsp+58h+dwFlags], r15d
0x180002a9f  call    cs:__imp_GetHandleInformation
0x180002aa6  nop     dword ptr [rax+rax+00h]
0x180002aab  test    eax, eax
0x180002aad  jnz     loc_18000284C
0x180002ab3  jmp     loc_180002859
0x180002ab8  mov     rcx, cs:WPP_GLOBAL_Control
0x180002abf  cmp     rcx, r12
0x180002ac2  jz      loc_18000284C
0x180002ac8  mov     rcx, [rcx+10h]
0x180002acc  lea     r8, WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x180002ad3  mov     edx, 0D1h
0x180002ad8  call    WPP_SF_d
0x180002add  jmp     loc_18000284C
0x180002ae2  inc     esi
0x180002ae4  jmp     loc_180002A1E
0x180002ae9  mov     eax, edi
0x180002aeb  mov     rax, [rbx+rax*8+200h]
0x180002af3  test    rax, rax
0x180002af6  jz      short loc_180002B15
0x180002af8  cmp     byte ptr [rax+10h], 0
0x180002afc  jnz     short loc_180002B15
0x180002afe  mov     rdx, rax
0x180002b01  mov     ecx, 1
0x180002b06  mov     rax, [rax+20h]
0x180002b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b0f  dec     dword ptr [rbx+400h]
0x180002b15  inc     edi
0x180002b17  cmp     edi, esi
0x180002b19  jb      short loc_180002AE9
0x180002b1b  jmp     loc_18000287B
0x180002b20  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b27  cmp     rcx, r12
0x180002b2a  jz      loc_1800028A8
0x180002b30  mov     eax, [rax]
0x180002b32  mov     r9, rbx
0x180002b35  mov     rcx, [rcx+10h]
0x180002b39  mov     [rsp+58h+var_30], eax
0x180002b3d  mov     [rsp+58h+bAlertable], edx
0x180002b41  call    WPP_SF_qdd
0x180002b46  mov     eax, [rbx+400h]
0x180002b4c  jmp     loc_1800028AA
```
