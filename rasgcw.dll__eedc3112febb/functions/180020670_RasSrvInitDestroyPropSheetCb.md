# RasSrvInitDestroyPropSheetCb

- ea: `0x180020670`
- end: `0x180020808`
- name: `RasSrvInitDestroyPropSheetCb`
- size: `408`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180020670`
- `0x180020c48`
- `0x180021470`
- `0x180026710`
- `0x180026f44`
- `0x180027168`
- `0x180027e84`
- `0x1800283bc`
- `0x180028ebc`

## import_xrefs

- `MPRAPI!MprAdminUserServerDisconnect` at `0x18002071f`
- `MPRAPI!MprAdminUserServerDisconnect` at `0x18002071f`
- `USER32!SetPropW` at `0x1800207dd`
- `USER32!SetPropW` at `0x1800207dd`

## string_xrefs

- `0x1800206c7`: `RasSrvCleanPropSht commit dbs.`

## pseudocode

```c
__int64 __fastcall RasSrvInitDestroyPropSheetCb(HWND hWnd, int a2, __int64 a3)
{
  _DWORD *v3; // rsi
  __int64 result; // rax
  __int64 v6; // rbx
  int v7; // eax
  bool v8; // zf
  _DWORD *v9; // rdi
  _DWORD *v10; // rdi
  __int64 i; // rbp
  void **v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  _DWORD *v15; // rdi
  void *v16; // rcx

  v3 = *(_DWORD **)(a3 + 48);
  if ( !v3 )
    return 1003;
  v6 = *((_QWORD *)v3 + 1);
  if ( a2 == 1 )
  {
    if ( v6 )
    {
      v7 = ~*v3;
      v8 = (v7 & *(_DWORD *)(v6 + 48)) == 0;
      *(_DWORD *)(v6 + 48) &= v7;
      if ( v8 )
      {
        if ( *(_DWORD *)(v6 + 56) )
        {
          DbgOutputTrace("RasSrvCleanPropSht commit dbs.");
          RassrvCommitSettings(v6, v3[1]);
        }
        DbgOutputTrace("RasSrvCleanPropSht closing dbs.");
        v9 = *(_DWORD **)(v6 + 24);
        if ( v9 && v9[2] )
        {
          if ( v9[8] )
            usrFlushLocalDatabase(*(_QWORD *)(v6 + 24));
          usrFreeUserArray(*((_QWORD *)v9 + 5), (unsigned int)v9[2]);
          RassrvFree(*((LPVOID *)v9 + 5));
          MprAdminUserServerDisconnect(*(_QWORD *)v9);
          RassrvFree(v9);
        }
        v10 = *(_DWORD **)(v6 + 16);
        if ( v10 )
        {
          if ( v10[4] )
            devFlushDatabase(*(_QWORD *)(v6 + 16));
          for ( i = 0; (unsigned int)i < *v10; i = (unsigned int)(i + 1) )
          {
            v12 = *(void ***)(*((_QWORD *)v10 + 1) + 8 * i);
            if ( v12 )
            {
              v13 = *v12;
              if ( v13 )
                RassrvFree(v13);
              RassrvFree(*(LPVOID *)(*((_QWORD *)v10 + 1) + 8 * i));
            }
          }
          v14 = (void *)*((_QWORD *)v10 + 1);
          if ( v14 )
            RassrvFree(v14);
          RassrvFree(v10);
        }
        v15 = *(_DWORD **)(v6 + 40);
        if ( v15 )
        {
          if ( v15[1] )
            miscFlushDatabase(*(int **)(v6 + 40));
          RassrvFree(v15);
        }
        v16 = *(void **)(v6 + 32);
        if ( v16 )
          netDbClose(v16);
        DbgOutputTrace("RasSrvCleanPropSht %d freeing pageset data.", *v3);
        RassrvFree((LPVOID)v6);
      }
    }
    SetPropW(hWnd, lpString, 0);
    DbgOutputTrace("RasSrvCleanPropSht %d freeing page data.", *v3);
    RassrvFree(v3);
    return 0;
  }
  else
  {
    result = 1;
    *(_DWORD *)(v6 + 48) |= *v3;
  }
  return result;
}

```

## disassembly

```asm
0x180020670  push    rbx
0x180020672  push    rbp
0x180020673  push    rsi
0x180020674  push    rdi
0x180020675  push    r14
0x180020677  push    r15
0x180020679  sub     rsp, 28h
0x18002067d  mov     rsi, [r8+30h]
0x180020681  mov     r15, rcx
0x180020684  test    rsi, rsi
0x180020687  jnz     short loc_180020693
0x180020689  mov     eax, 3EBh
0x18002068e  jmp     loc_1800207FB
0x180020693  mov     rbx, [rsi+8]
0x180020697  cmp     edx, 1
0x18002069a  jz      short loc_1800206AB
0x18002069c  mov     ecx, [rsi]
0x18002069e  mov     eax, 1
0x1800206a3  or      [rbx+30h], ecx
0x1800206a6  jmp     loc_1800207FB
0x1800206ab  test    rbx, rbx
0x1800206ae  jz      loc_1800207D0
0x1800206b4  mov     eax, [rsi]
0x1800206b6  not     eax
0x1800206b8  and     [rbx+30h], eax
0x1800206bb  jnz     loc_1800207D0
0x1800206c1  cmp     dword ptr [rbx+38h], 0
0x1800206c5  jz      short loc_1800206DE
0x1800206c7  lea     rcx, aRassrvcleanpro; "RasSrvCleanPropSht commit dbs."
0x1800206ce  call    DbgOutputTrace
0x1800206d3  mov     edx, [rsi+4]
0x1800206d6  mov     rcx, rbx
0x1800206d9  call    RassrvCommitSettings
0x1800206de  lea     rcx, aRassrvcleanpro_0; "RasSrvCleanPropSht closing dbs."
0x1800206e5  call    DbgOutputTrace
0x1800206ea  mov     rdi, [rbx+18h]
0x1800206ee  test    rdi, rdi
0x1800206f1  jz      short loc_18002072D
0x1800206f3  cmp     dword ptr [rdi+8], 0
0x1800206f7  jz      short loc_18002072D
0x1800206f9  cmp     dword ptr [rdi+20h], 0
0x1800206fd  jz      short loc_180020707
0x1800206ff  mov     rcx, rdi
0x180020702  call    usrFlushLocalDatabase
0x180020707  mov     edx, [rdi+8]
0x18002070a  mov     rcx, [rdi+28h]
0x18002070e  call    usrFreeUserArray
0x180020713  mov     rcx, [rdi+28h]; lpMem
0x180020717  call    RassrvFree
0x18002071c  mov     rcx, [rdi]
0x18002071f  call    cs:__imp_MprAdminUserServerDisconnect
0x180020725  mov     rcx, rdi; lpMem
0x180020728  call    RassrvFree
0x18002072d  mov     rdi, [rbx+10h]
0x180020731  test    rdi, rdi
0x180020734  jz      short loc_18002078D
0x180020736  cmp     dword ptr [rdi+10h], 0
0x18002073a  jz      short loc_180020744
0x18002073c  mov     rcx, rdi
0x18002073f  call    devFlushDatabase
0x180020744  xor     ebp, ebp
0x180020746  cmp     [rdi], ebp
0x180020748  jbe     short loc_180020777
0x18002074a  mov     rax, [rdi+8]
0x18002074e  mov     rcx, [rax+rbp*8]
0x180020752  test    rcx, rcx
0x180020755  jz      short loc_180020771
0x180020757  mov     rcx, [rcx]; lpMem
0x18002075a  test    rcx, rcx
0x18002075d  jz      short loc_180020764
0x18002075f  call    RassrvFree
0x180020764  mov     rcx, [rdi+8]
0x180020768  mov     rcx, [rcx+rbp*8]; lpMem
0x18002076c  call    RassrvFree
0x180020771  inc     ebp
0x180020773  cmp     ebp, [rdi]
0x180020775  jb      short loc_18002074A
0x180020777  mov     rcx, [rdi+8]; lpMem
0x18002077b  test    rcx, rcx
0x18002077e  jz      short loc_180020785
0x180020780  call    RassrvFree
0x180020785  mov     rcx, rdi; lpMem
0x180020788  call    RassrvFree
0x18002078d  mov     rdi, [rbx+28h]
0x180020791  test    rdi, rdi
0x180020794  jz      short loc_1800207AC
0x180020796  cmp     dword ptr [rdi+4], 0
0x18002079a  jz      short loc_1800207A4
0x18002079c  mov     rcx, rdi
0x18002079f  call    miscFlushDatabase
0x1800207a4  mov     rcx, rdi; lpMem
0x1800207a7  call    RassrvFree
0x1800207ac  mov     rcx, [rbx+20h]; lpMem
0x1800207b0  test    rcx, rcx
0x1800207b3  jz      short loc_1800207BA
0x1800207b5  call    netDbClose
0x1800207ba  mov     edx, [rsi]
0x1800207bc  lea     rcx, aRassrvcleanpro_1; "RasSrvCleanPropSht %d freeing pageset d"...
0x1800207c3  call    DbgOutputTrace
0x1800207c8  mov     rcx, rbx; lpMem
0x1800207cb  call    RassrvFree
0x1800207d0  mov     rdx, cs:lpString; lpString
0x1800207d7  xor     r8d, r8d; hData
0x1800207da  mov     rcx, r15; hWnd
0x1800207dd  call    cs:__imp_SetPropW
0x1800207e3  mov     edx, [rsi]
0x1800207e5  lea     rcx, aRassrvcleanpro_2; "RasSrvCleanPropSht %d freeing page data"...
0x1800207ec  call    DbgOutputTrace
0x1800207f1  mov     rcx, rsi; lpMem
0x1800207f4  call    RassrvFree
0x1800207f9  xor     eax, eax
0x1800207fb  add     rsp, 28h
0x1800207ff  pop     r15
0x180020801  pop     r14
0x180020803  pop     rdi
0x180020804  pop     rsi
0x180020805  pop     rbp
0x180020806  pop     rbx
0x180020807  retn
```
