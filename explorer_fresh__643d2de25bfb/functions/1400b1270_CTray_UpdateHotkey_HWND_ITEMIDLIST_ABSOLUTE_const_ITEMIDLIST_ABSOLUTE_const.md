# CTray::_UpdateHotkey(HWND__ *,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x1400b1270`
- end: `0x1400b143d`
- name: `?_UpdateHotkey@CTray@@IEAA_JPEAUHWND__@@PEBU_ITEMIDLIST_ABSOLUTE@@1@Z`
- size: `461`
- prototype: `__int64(CTray *__hidden this, HWND, const struct _ITEMIDLIST_ABSOLUTE *, const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140019eb0`

## callees

- `0x140021430`
- `0x1400b1270`
- `0x1400b2a9c`
- `0x14012e75c`
- `0x140131b28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400b12b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400b12b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400b1417`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400b1417`
- `api-ms-win-shell-namespace-l1-1-0!ILRemoveLastID` at `0x1400b13ab`
- `api-ms-win-shell-namespace-l1-1-0!ILRemoveLastID` at `0x1400b13ab`
- `api-ms-win-shell-namespace-l1-1-0!ILIsEqual` at `0x1400b1328`
- `api-ms-win-shell-namespace-l1-1-0!ILIsEqual` at `0x1400b1328`
- `api-ms-win-shell-namespace-l1-1-0!ILCombine` at `0x1400b130a`
- `api-ms-win-shell-namespace-l1-1-0!ILCombine` at `0x1400b130a`
- `api-ms-win-shell-namespace-l1-1-0!ILClone` at `0x1400b1394`
- `api-ms-win-shell-namespace-l1-1-0!ILClone` at `0x1400b1394`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1400b134a`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1400b135f`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1400b13fc`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1400b134a`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1400b135f`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1400b13fc`
- `api-ms-win-shell-namespace-l1-1-0!ILFindLastID` at `0x1400b1373`
- `api-ms-win-shell-namespace-l1-1-0!ILFindLastID` at `0x1400b1373`
- `api-ms-win-shell-namespace-l1-1-0!ILCloneFirst` at `0x1400b1382`
- `api-ms-win-shell-namespace-l1-1-0!ILCloneFirst` at `0x1400b1382`

## pseudocode

```c
__int64 __fastcall CTray::_UpdateHotkey(CTray *this, HWND a2, const ITEMIDLIST *a3, const ITEMIDLIST *a4)
{
  const ITEMIDLIST *v5; // r15
  int v7; // ebp
  int v8; // edi
  int v9; // r12d
  LPCITEMIDLIST *ItemPtr; // rax
  LPCITEMIDLIST *v11; // rbx
  const ITEMIDLIST *v12; // rdx
  const ITEMIDLIST *v13; // rax
  ITEMIDLIST *v14; // r14
  ITEMIDLIST *v15; // rcx
  const ITEMIDLIST *ID; // rax
  LPITEMIDLIST v17; // r15
  ITEMIDLIST *v18; // rax
  ITEMIDLIST *v19; // rbp
  unsigned __int16 v20; // ax
  CTray *v21; // rcx
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+60h] [rbp+8h]

  v5 = a3;
  if ( *((_QWORD *)this + 33) )
  {
    v7 = 0;
    lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)((char *)this + 344);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 344));
    v8 = 0;
    v9 = **((_DWORD **)this + 33);
    do
    {
      if ( v8 >= v9 )
        break;
      ItemPtr = (LPCITEMIDLIST *)DSA_GetItemPtr(*((HDSA *)this + 33), v8);
      v11 = ItemPtr;
      if ( ItemPtr )
      {
        if ( *ItemPtr )
        {
          v12 = ItemPtr[1];
          if ( v12 )
          {
            v13 = ILCombine(*ItemPtr, v12);
            v14 = (ITEMIDLIST *)v13;
            if ( v13 )
            {
              if ( ILIsEqual(v13, v5) )
              {
                if ( (*((_BYTE *)v11 + 18) & 2) != 0 )
                {
                  if ( *v11 )
                    ILFree((LPITEMIDLIST)*v11);
                  v15 = (ITEMIDLIST *)v11[1];
                  if ( v15 )
                    ILFree(v15);
                }
                if ( a4 )
                {
                  ID = ILFindLastID(a4);
                  v17 = ILCloneFirst(ID);
                  v18 = ILClone(a4);
                  v19 = v18;
                  if ( v18 )
                    ILRemoveLastID(v18);
                  *((_WORD *)v11 + 9) |= 3u;
                  v11[1] = v17;
                  v5 = a3;
                  *v11 = v19;
                }
                else
                {
                  CTray::_UnregisterHotkey((CTray *)v15, a2, v8);
                  v20 = _MapGlobalHotkeyToHotkey(*((_WORD *)v11 + 8));
                  CTray::_DeleteHotkeyFromAllWindows(v21, v20);
                  *(_OWORD *)v11 = 0;
                  v11[2] = 0;
                }
                v7 = 1;
              }
              ILFree(v14);
            }
          }
        }
      }
      ++v8;
    }
    while ( !v7 );
    LeaveCriticalSection(lpCriticalSection);
  }
  return -1;
}

```

## disassembly

```asm
0x1400b1270  mov     [rsp+arg_18], rbx
0x1400b1275  mov     [rsp+arg_10], r8
0x1400b127a  mov     [rsp+arg_8], rdx
0x1400b127f  push    rbp
0x1400b1280  push    rsi
0x1400b1281  push    rdi
0x1400b1282  push    r12
0x1400b1284  push    r13
0x1400b1286  push    r14
0x1400b1288  push    r15
0x1400b128a  sub     rsp, 20h
0x1400b128e  cmp     qword ptr [rcx+108h], 0
0x1400b1296  mov     r13, r9
0x1400b1299  mov     r15, r8
0x1400b129c  mov     rsi, rcx
0x1400b129f  jz      loc_1400B1423
0x1400b12a5  lea     r12, [rcx+158h]
0x1400b12ac  xor     ebp, ebp
0x1400b12ae  mov     rcx, r12; lpCriticalSection
0x1400b12b1  mov     [rsp+58h+lpCriticalSection], r12
0x1400b12b6  call    cs:__imp_EnterCriticalSection
0x1400b12bd  nop     dword ptr [rax+rax+00h]
0x1400b12c2  mov     rax, [rsi+108h]
0x1400b12c9  xor     edi, edi
0x1400b12cb  mov     r12d, [rax]
0x1400b12ce  cmp     edi, r12d
0x1400b12d1  jge     loc_1400B1412
0x1400b12d7  mov     rcx, [rsi+108h]; hdsa
0x1400b12de  mov     edx, edi; i
0x1400b12e0  call    DSA_GetItemPtr
0x1400b12e5  mov     rbx, rax
0x1400b12e8  test    rax, rax
0x1400b12eb  jz      loc_1400B1408
0x1400b12f1  mov     rcx, [rax]; pidl1
0x1400b12f4  test    rcx, rcx
0x1400b12f7  jz      loc_1400B1408
0x1400b12fd  mov     rdx, [rax+8]; pidl2
0x1400b1301  test    rdx, rdx
0x1400b1304  jz      loc_1400B1408
0x1400b130a  call    cs:__imp_ILCombine
0x1400b1311  nop     dword ptr [rax+rax+00h]
0x1400b1316  mov     r14, rax
0x1400b1319  test    rax, rax
0x1400b131c  jz      loc_1400B1408
0x1400b1322  mov     rdx, r15; pidl2
0x1400b1325  mov     rcx, rax; pidl1
0x1400b1328  call    cs:__imp_ILIsEqual
0x1400b132f  nop     dword ptr [rax+rax+00h]
0x1400b1334  test    eax, eax
0x1400b1336  jz      loc_1400B13F9
0x1400b133c  test    byte ptr [rbx+12h], 2
0x1400b1340  jz      short loc_1400B136B
0x1400b1342  mov     rcx, [rbx]; pidl
0x1400b1345  test    rcx, rcx
0x1400b1348  jz      short loc_1400B1356
0x1400b134a  call    cs:__imp_ILFree
0x1400b1351  nop     dword ptr [rax+rax+00h]
0x1400b1356  mov     rcx, [rbx+8]; pidl
0x1400b135a  test    rcx, rcx
0x1400b135d  jz      short loc_1400B136B
0x1400b135f  call    cs:__imp_ILFree
0x1400b1366  nop     dword ptr [rax+rax+00h]
0x1400b136b  test    r13, r13
0x1400b136e  jz      short loc_1400B13CA
0x1400b1370  mov     rcx, r13; pidl
0x1400b1373  call    cs:__imp_ILFindLastID
0x1400b137a  nop     dword ptr [rax+rax+00h]
0x1400b137f  mov     rcx, rax; pidl
0x1400b1382  call    cs:__imp_ILCloneFirst
0x1400b1389  nop     dword ptr [rax+rax+00h]
0x1400b138e  mov     rcx, r13; pidl
0x1400b1391  mov     r15, rax
0x1400b1394  call    cs:__imp_ILClone
0x1400b139b  nop     dword ptr [rax+rax+00h]
0x1400b13a0  mov     rbp, rax
0x1400b13a3  test    rax, rax
0x1400b13a6  jz      short loc_1400B13B7
0x1400b13a8  mov     rcx, rax; pidl
0x1400b13ab  call    cs:__imp_ILRemoveLastID
0x1400b13b2  nop     dword ptr [rax+rax+00h]
0x1400b13b7  or      word ptr [rbx+12h], 3
0x1400b13bc  mov     [rbx+8], r15
0x1400b13c0  mov     r15, [rsp+58h+arg_10]
0x1400b13c5  mov     [rbx], rbp
0x1400b13c8  jmp     short loc_1400B13F4
0x1400b13ca  mov     rdx, [rsp+58h+arg_8]; HWND
0x1400b13cf  mov     r8d, edi; int
0x1400b13d2  call    ?_UnregisterHotkey@CTray@@IEAA_JPEAUHWND__@@H@Z; CTray::_UnregisterHotkey(HWND__ *,int)
0x1400b13d7  movzx   ecx, word ptr [rbx+10h]; unsigned __int16
0x1400b13db  call    ?_MapGlobalHotkeyToHotkey@@YAGG@Z; _MapGlobalHotkeyToHotkey(ushort)
0x1400b13e0  movzx   edx, ax; unsigned __int16
0x1400b13e3  call    ?_DeleteHotkeyFromAllWindows@CTray@@IEAAXG@Z; CTray::_DeleteHotkeyFromAllWindows(ushort)
0x1400b13e8  xorps   xmm0, xmm0
0x1400b13eb  xor     eax, eax
0x1400b13ed  movups  xmmword ptr [rbx], xmm0
0x1400b13f0  mov     [rbx+10h], rax
0x1400b13f4  mov     ebp, 1
0x1400b13f9  mov     rcx, r14; pidl
0x1400b13fc  call    cs:__imp_ILFree
0x1400b1403  nop     dword ptr [rax+rax+00h]
0x1400b1408  inc     edi
0x1400b140a  test    ebp, ebp
0x1400b140c  jz      loc_1400B12CE
0x1400b1412  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1400b1417  call    cs:__imp_LeaveCriticalSection
0x1400b141e  nop     dword ptr [rax+rax+00h]
0x1400b1423  mov     rbx, [rsp+58h+arg_18]
0x1400b1428  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400b142c  add     rsp, 20h
0x1400b1430  pop     r15
0x1400b1432  pop     r14
0x1400b1434  pop     r13
0x1400b1436  pop     r12
0x1400b1438  pop     rdi
0x1400b1439  pop     rsi
0x1400b143a  pop     rbp
0x1400b143b  retn
```
