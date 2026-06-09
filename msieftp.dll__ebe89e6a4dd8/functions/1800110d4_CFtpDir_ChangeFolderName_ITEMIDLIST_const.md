# CFtpDir::ChangeFolderName(_ITEMIDLIST const *)

- ea: `0x1800110d4`
- end: `0x180011212`
- name: `?ChangeFolderName@CFtpDir@@QEAAJPEFBU_ITEMIDLIST@@@Z`
- size: `318`
- prototype: `__int64 __fastcall(CFtpDir *__hidden this, const struct _ITEMIDLIST *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024378`

## callees

- `0x1800110d4`
- `0x18001187c`
- `0x18001bd14`
- `0x18001bda4`
- `0x18001c46c`
- `0x180026884`
- `0x1800269f4`
- `0x180026ff0`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILCombine` at `0x1800111bb`
- `SHELL32!__imp_ILCombine` at `0x1800111bb`
- `SHELL32!__imp_ILFree` at `0x1800111c7`
- `SHELL32!__imp_ILFree` at `0x1800111fa`
- `SHELL32!__imp_ILFree` at `0x1800111c7`
- `SHELL32!__imp_ILFree` at `0x1800111fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011107`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011107`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011172`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011172`

## pseudocode

```c
__int64 __fastcall CFtpDir::ChangeFolderName(CFtpDir *this, const struct _ITEMIDLIST *a2)
{
  __int64 v2; // rsi
  unsigned int v5; // r14d
  const struct _ITEMIDLIST *v6; // r12
  unsigned int v7; // ebx
  PVOID Ptr; // rax
  __int64 *v9; // r15
  __int64 v10; // rax
  signed int v11; // ebx
  ITEMIDLIST *v12; // rsi
  struct CFtpSite *v13; // rdx
  CFtpDir *v14; // rcx
  struct _ITEMIDLIST *v15; // r15
  const ITEMIDLIST *v16; // rdx

  v2 = *((_QWORD *)this + 2);
  v5 = -2147467259;
  if ( v2 )
  {
    v6 = (const struct _ITEMIDLIST *)*((_QWORD *)this + 5);
    EnterCriticalSection(&g_csDll);
    v7 = **(_DWORD **)(*(_QWORD *)(v2 + 40) + 16LL);
    while ( (--v7 & 0x80000000) == 0 )
    {
      Ptr = DPA_GetPtr(*(HDPA *)(*(_QWORD *)(v2 + 40) + 16LL), v7);
      v9 = (__int64 *)Ptr;
      if ( Ptr && (unsigned int)FtpItemID_IsParent(v6, *((const struct _ITEMIDLIST **)Ptr + 5)) )
      {
        DPA_DeletePtr(*(HDPA *)(*(_QWORD *)(v2 + 40) + 16LL), v7);
        v10 = *v9;
        v9[2] = 0;
        (*(void (__fastcall **)(__int64 *))(v10 + 16))(v9);
      }
    }
    LeaveCriticalSection(&g_csDll);
    v11 = -2147024809;
    v12 = 0;
    if ( (unsigned int)FtpID_IsServerItemID(*((const struct _ITEMIDLIST **)this + 6)) )
    {
      v15 = FtpCloneServerID(*((LPCITEMIDLIST *)this + 6));
      if ( v15 )
      {
        if ( (unsigned int)FtpID_IsServerItemID(a2) )
          v16 = (const struct _ITEMIDLIST *)((char *)a2 + a2->mkid.cb);
        else
          v16 = a2;
        v12 = ILCombine(v15, v16);
        ILFree(v15);
        v11 = v12 == 0 ? 0x80004005 : 0;
      }
    }
    v5 = v11;
    CFtpDir::_SetFtpDir(v14, v13, this, a2);
    if ( v11 >= 0 )
    {
      Pidl_Set((char *)this + 48, v12);
      ILFree(v12);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800110d4  push    rbx
0x1800110d6  push    rbp
0x1800110d7  push    rsi
0x1800110d8  push    rdi
0x1800110d9  push    r12
0x1800110db  push    r14
0x1800110dd  push    r15
0x1800110df  sub     rsp, 20h
0x1800110e3  mov     rsi, [rcx+10h]
0x1800110e7  mov     rdi, rdx
0x1800110ea  mov     rbp, rcx
0x1800110ed  mov     r14d, 80004005h
0x1800110f3  test    rsi, rsi
0x1800110f6  jz      loc_180011200
0x1800110fc  mov     r12, [rcx+28h]
0x180011100  lea     rcx, g_csDll; lpCriticalSection
0x180011107  call    cs:__imp_EnterCriticalSection
0x18001110d  mov     rax, [rsi+28h]
0x180011111  mov     rcx, [rax+10h]
0x180011115  mov     ebx, [rcx]
0x180011117  jmp     short loc_180011166
0x180011119  mov     rcx, [rsi+28h]
0x18001111d  mov     edx, ebx; i
0x18001111f  mov     rcx, [rcx+10h]; hdpa
0x180011123  call    DPA_GetPtr
0x180011128  mov     r15, rax
0x18001112b  test    rax, rax
0x18001112e  jz      short loc_180011166
0x180011130  mov     rdx, [rax+28h]; struct _ITEMIDLIST *
0x180011134  mov     rcx, r12; struct _ITEMIDLIST *
0x180011137  call    ?FtpItemID_IsParent@@YAHPEFBU_ITEMIDLIST@@0@Z; FtpItemID_IsParent(_ITEMIDLIST const *,_ITEMIDLIST const *)
0x18001113c  test    eax, eax
0x18001113e  jz      short loc_180011166
0x180011140  mov     rcx, [rsi+28h]
0x180011144  mov     edx, ebx; i
0x180011146  mov     rcx, [rcx+10h]; hdpa
0x18001114a  call    DPA_DeletePtr
0x18001114f  mov     rax, [r15]
0x180011152  mov     rcx, r15
0x180011155  mov     qword ptr [r15+10h], 0
0x18001115d  mov     rax, [rax+10h]
0x180011161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011166  sub     ebx, 1
0x180011169  jns     short loc_180011119
0x18001116b  lea     rcx, g_csDll; lpCriticalSection
0x180011172  call    cs:__imp_LeaveCriticalSection
0x180011178  lea     r12, [rbp+30h]
0x18001117c  mov     ebx, 80070057h
0x180011181  mov     rcx, [r12]; struct _ITEMIDLIST *
0x180011185  xor     esi, esi
0x180011187  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x18001118c  test    eax, eax
0x18001118e  jz      short loc_1800111DA
0x180011190  mov     rcx, [r12]; pidl
0x180011194  call    ?FtpCloneServerID@@YAPEFAU_ITEMIDLIST@@PEFBU1@@Z; FtpCloneServerID(_ITEMIDLIST const *)
0x180011199  mov     r15, rax
0x18001119c  test    rax, rax
0x18001119f  jz      short loc_1800111DA
0x1800111a1  mov     rcx, rdi; struct _ITEMIDLIST *
0x1800111a4  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x1800111a9  test    eax, eax
0x1800111ab  jz      short loc_1800111B5
0x1800111ad  movzx   edx, word ptr [rdi]
0x1800111b0  add     rdx, rdi
0x1800111b3  jmp     short loc_1800111B8
0x1800111b5  mov     rdx, rdi; pidl2
0x1800111b8  mov     rcx, r15; pidl1
0x1800111bb  call    cs:__imp_ILCombine
0x1800111c1  mov     rcx, r15; pidl
0x1800111c4  mov     rsi, rax
0x1800111c7  call    cs:__imp_ILFree
0x1800111cd  mov     rax, rsi
0x1800111d0  neg     rax
0x1800111d3  sbb     ebx, ebx
0x1800111d5  not     ebx
0x1800111d7  and     ebx, r14d
0x1800111da  mov     r9, rdi; struct _ITEMIDLIST *
0x1800111dd  mov     r8, rbp; struct CFtpDir *
0x1800111e0  mov     r14d, ebx
0x1800111e3  call    ?_SetFtpDir@CFtpDir@@IEAAJPEAVCFtpSite@@PEAV1@PEFBU_ITEMIDLIST@@@Z; CFtpDir::_SetFtpDir(CFtpSite *,CFtpDir *,_ITEMIDLIST const *)
0x1800111e8  test    ebx, ebx
0x1800111ea  js      short loc_180011200
0x1800111ec  mov     rdx, rsi
0x1800111ef  mov     rcx, r12
0x1800111f2  call    Pidl_Set
0x1800111f7  mov     rcx, rsi; pidl
0x1800111fa  call    cs:__imp_ILFree
0x180011200  mov     eax, r14d
0x180011203  add     rsp, 20h
0x180011207  pop     r15
0x180011209  pop     r14
0x18001120b  pop     r12
0x18001120d  pop     rdi
0x18001120e  pop     rsi
0x18001120f  pop     rbp
0x180011210  pop     rbx
0x180011211  retn
```
