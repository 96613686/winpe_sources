# CTray::_UpdateHotkey(HWND__ *,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x1400ab150`
- end: `0x1400ab2da`
- name: `?_UpdateHotkey@CTray@@IEAA_JPEAUHWND__@@PEBU_ITEMIDLIST_ABSOLUTE@@1@Z`
- size: `394`
- prototype: `__int64(CTray *__hidden this, HWND, const struct _ITEMIDLIST_ABSOLUTE *, const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001d860`

## callees

- `0x140023fe0`
- `0x1400ab150`
- `0x1400aca34`
- `0x140123110`
- `0x140126448`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400ab2bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400ab2bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400ab196`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400ab196`
- `api-ms-win-shell-namespace-l1-1-0!ILRemoveLastID` at `0x1400ab25b`
- `api-ms-win-shell-namespace-l1-1-0!ILRemoveLastID` at `0x1400ab25b`
- `api-ms-win-shell-namespace-l1-1-0!ILIsEqual` at `0x1400ab1fc`
- `api-ms-win-shell-namespace-l1-1-0!ILIsEqual` at `0x1400ab1fc`
- `api-ms-win-shell-namespace-l1-1-0!ILCombine` at `0x1400ab1e4`
- `api-ms-win-shell-namespace-l1-1-0!ILCombine` at `0x1400ab1e4`
- `api-ms-win-shell-namespace-l1-1-0!ILCloneFirst` at `0x1400ab23e`
- `api-ms-win-shell-namespace-l1-1-0!ILCloneFirst` at `0x1400ab23e`
- `api-ms-win-shell-namespace-l1-1-0!ILClone` at `0x1400ab24a`
- `api-ms-win-shell-namespace-l1-1-0!ILClone` at `0x1400ab24a`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1400ab218`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1400ab227`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1400ab2a6`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1400ab218`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1400ab227`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1400ab2a6`
- `api-ms-win-shell-namespace-l1-1-0!ILFindLastID` at `0x1400ab235`
- `api-ms-win-shell-namespace-l1-1-0!ILFindLastID` at `0x1400ab235`

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
0x1400ab150  mov     [rsp+arg_18], rbx
0x1400ab155  mov     [rsp+arg_10], r8
0x1400ab15a  mov     [rsp+arg_8], rdx
0x1400ab15f  push    rbp
0x1400ab160  push    rsi
0x1400ab161  push    rdi
0x1400ab162  push    r12
0x1400ab164  push    r13
0x1400ab166  push    r14
0x1400ab168  push    r15
0x1400ab16a  sub     rsp, 20h
0x1400ab16e  cmp     qword ptr [rcx+108h], 0
0x1400ab176  mov     r13, r9
0x1400ab179  mov     r15, r8
0x1400ab17c  mov     rsi, rcx
0x1400ab17f  jz      loc_1400AB2C1
0x1400ab185  lea     r12, [rcx+158h]
0x1400ab18c  xor     ebp, ebp
0x1400ab18e  mov     rcx, r12; lpCriticalSection
0x1400ab191  mov     [rsp+58h+lpCriticalSection], r12
0x1400ab196  call    cs:__imp_EnterCriticalSection
0x1400ab19c  mov     rax, [rsi+108h]
0x1400ab1a3  xor     edi, edi
0x1400ab1a5  mov     r12d, [rax]
0x1400ab1a8  cmp     edi, r12d
0x1400ab1ab  jge     loc_1400AB2B6
0x1400ab1b1  mov     rcx, [rsi+108h]; hdsa
0x1400ab1b8  mov     edx, edi; i
0x1400ab1ba  call    DSA_GetItemPtr
0x1400ab1bf  mov     rbx, rax
0x1400ab1c2  test    rax, rax
0x1400ab1c5  jz      loc_1400AB2AC
0x1400ab1cb  mov     rcx, [rax]; pidl1
0x1400ab1ce  test    rcx, rcx
0x1400ab1d1  jz      loc_1400AB2AC
0x1400ab1d7  mov     rdx, [rax+8]; pidl2
0x1400ab1db  test    rdx, rdx
0x1400ab1de  jz      loc_1400AB2AC
0x1400ab1e4  call    cs:__imp_ILCombine
0x1400ab1ea  mov     r14, rax
0x1400ab1ed  test    rax, rax
0x1400ab1f0  jz      loc_1400AB2AC
0x1400ab1f6  mov     rdx, r15; pidl2
0x1400ab1f9  mov     rcx, rax; pidl1
0x1400ab1fc  call    cs:__imp_ILIsEqual
0x1400ab202  test    eax, eax
0x1400ab204  jz      loc_1400AB2A3
0x1400ab20a  test    byte ptr [rbx+12h], 2
0x1400ab20e  jz      short loc_1400AB22D
0x1400ab210  mov     rcx, [rbx]; pidl
0x1400ab213  test    rcx, rcx
0x1400ab216  jz      short loc_1400AB21E
0x1400ab218  call    cs:__imp_ILFree
0x1400ab21e  mov     rcx, [rbx+8]; pidl
0x1400ab222  test    rcx, rcx
0x1400ab225  jz      short loc_1400AB22D
0x1400ab227  call    cs:__imp_ILFree
0x1400ab22d  test    r13, r13
0x1400ab230  jz      short loc_1400AB274
0x1400ab232  mov     rcx, r13; pidl
0x1400ab235  call    cs:__imp_ILFindLastID
0x1400ab23b  mov     rcx, rax; pidl
0x1400ab23e  call    cs:__imp_ILCloneFirst
0x1400ab244  mov     rcx, r13; pidl
0x1400ab247  mov     r15, rax
0x1400ab24a  call    cs:__imp_ILClone
0x1400ab250  mov     rbp, rax
0x1400ab253  test    rax, rax
0x1400ab256  jz      short loc_1400AB261
0x1400ab258  mov     rcx, rax; pidl
0x1400ab25b  call    cs:__imp_ILRemoveLastID
0x1400ab261  or      word ptr [rbx+12h], 3
0x1400ab266  mov     [rbx+8], r15
0x1400ab26a  mov     r15, [rsp+58h+arg_10]
0x1400ab26f  mov     [rbx], rbp
0x1400ab272  jmp     short loc_1400AB29E
0x1400ab274  mov     rdx, [rsp+58h+arg_8]; HWND
0x1400ab279  mov     r8d, edi; int
0x1400ab27c  call    ?_UnregisterHotkey@CTray@@IEAA_JPEAUHWND__@@H@Z; CTray::_UnregisterHotkey(HWND__ *,int)
0x1400ab281  movzx   ecx, word ptr [rbx+10h]; unsigned __int16
0x1400ab285  call    ?_MapGlobalHotkeyToHotkey@@YAGG@Z; _MapGlobalHotkeyToHotkey(ushort)
0x1400ab28a  movzx   edx, ax; unsigned __int16
0x1400ab28d  call    ?_DeleteHotkeyFromAllWindows@CTray@@IEAAXG@Z; CTray::_DeleteHotkeyFromAllWindows(ushort)
0x1400ab292  xorps   xmm0, xmm0
0x1400ab295  xor     eax, eax
0x1400ab297  movups  xmmword ptr [rbx], xmm0
0x1400ab29a  mov     [rbx+10h], rax
0x1400ab29e  mov     ebp, 1
0x1400ab2a3  mov     rcx, r14; pidl
0x1400ab2a6  call    cs:__imp_ILFree
0x1400ab2ac  inc     edi
0x1400ab2ae  test    ebp, ebp
0x1400ab2b0  jz      loc_1400AB1A8
0x1400ab2b6  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1400ab2bb  call    cs:__imp_LeaveCriticalSection
0x1400ab2c1  mov     rbx, [rsp+58h+arg_18]
0x1400ab2c6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400ab2ca  add     rsp, 20h
0x1400ab2ce  pop     r15
0x1400ab2d0  pop     r14
0x1400ab2d2  pop     r13
0x1400ab2d4  pop     r12
0x1400ab2d6  pop     rdi
0x1400ab2d7  pop     rsi
0x1400ab2d8  pop     rbp
0x1400ab2d9  retn
```
