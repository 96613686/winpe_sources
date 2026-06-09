# LoadModule(void *,ushort const *,ushort const *,unsigned __int64,ulong,void *,_MODLOAD_DATA *,ulong)

- ea: `0x1800091a0`
- end: `0x180009787`
- name: `?LoadModule@@YA_KPEAXPEBG1_KK0PEAU_MODLOAD_DATA@@K@Z`
- size: `1511`
- prototype: `unsigned __int64 __fastcall(void *, LPCWSTR lpSrc, const unsigned __int16 *, unsigned __int64, unsigned int, void *, struct _MODLOAD_DATA *, unsigned int)`
- caller_count: `3`
- callee_count: `23`
- tags: `loader_planting`

## callers

- `0x18000e500`
- `0x180017ea0`
- `0x180018070`

## callees

- `0x180005a20`
- `0x180005ea4`
- `0x180008740`
- `0x180008ad0`
- `0x1800091a0`
- `0x180009790`
- `0x18000982c`
- `0x18000aeec`
- `0x18000af48`
- `0x18000ec34`
- `0x18000fb40`
- `0x18000ffd8`
- `0x1800102e4`
- `0x180012e6c`
- `0x180016a5c`
- `0x180016dec`
- `0x18001a0ec`
- `0x180023704`
- `0x1800269d4`
- `0x180027430`
- `0x180169420`
- `0x180194990`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800095be`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800095be`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180009354`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180009354`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180009370`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800095e0`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180009370`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800095e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009495`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009495`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int64 __fastcall LoadModule(
        void *a1,
        LPCWSTR lpSrc,
        const unsigned __int16 *a3,
        unsigned __int64 a4,
        unsigned int a5,
        void *a6,
        struct _MODLOAD_DATA *a7,
        unsigned int a8)
{
  unsigned int v12; // edx
  struct _PROCESS_ENTRY *ProcessEntry; // rax
  struct _PROCESS_ENTRY *v14; // rdi
  struct _MODULE_ENTRY *ModuleForDLLBase; // rax
  struct _MODULE_ENTRY *v16; // rbx
  struct _MODULE_ENTRY *ModuleForPC; // rax
  struct _MODULE_ENTRY *v19; // rbx
  struct _MODULE_ENTRY *v20; // rax
  unsigned __int64 *v21; // r13
  const wchar_t *v22; // rax
  void *v23; // rbp
  struct _MODULE_ENTRY **v24; // rax
  __int64 v25; // rcx
  unsigned __int64 v26; // rcx
  DWORD v27; // ecx
  unsigned int v28; // eax
  void *v29; // rax
  struct _IMGHLP_DEBUG_DATA *inited; // rax
  struct _IMGHLP_DEBUG_DATA *v31; // rsi
  struct _PROCESS_ENTRY *v32; // rcx
  _QWORD *v33; // rax
  _QWORD *v34; // rbx
  __int64 v35; // rcx
  _QWORD *v36; // rax
  const WCHAR *v37; // rax
  unsigned __int64 *data; // r14
  _OWORD *v39; // r15
  unsigned __int64 i; // rbp
  __int64 v41; // rax
  __int64 *v42; // rcx
  unsigned int v43; // [rsp+54h] [rbp-4C4h]
  struct _MODULE_ENTRY *v44; // [rsp+58h] [rbp-4C0h] BYREF
  void *v45[4]; // [rsp+60h] [rbp-4B8h] BYREF
  struct _IMAGEHLP_DEFERRED_SYMBOL_LOADW64 v46; // [rsp+80h] [rbp-498h] BYREF
  wchar_t Filename[256]; // [rsp+2C0h] [rbp-258h] BYREF

  v45[2] = (void *)-2LL;
  v45[0] = a1;
  memset_0(&v46, 0, sizeof(v46));
  v12 = a8 & 0xFFDFFFFF;
  if ( (a8 & 0x200000) == 0 )
    v12 = a8;
  v43 = v12;
  if ( a4 == -1 )
    return 0;
  if ( (unsigned int)extmatch(lpSrc, L".pdb") && !a4 )
    goto LABEL_29;
  ProcessEntry = FindProcessEntry(a1);
  v14 = ProcessEntry;
  if ( !ProcessEntry )
  {
    v27 = 6;
    goto LABEL_30;
  }
  if ( !*((_QWORD *)ProcessEntry + 4) )
  {
    v33 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    v34 = v33;
    v44 = (struct _MODULE_ENTRY *)v33;
    if ( v33 )
    {
      *v33 = 0;
      v33[1] = 0;
      std::_Tree<std::_Tmap_traits<unsigned __int64,_MODULE_ENTRY *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,_MODULE_ENTRY *>>,0>>::_Alloc_sentinel_and_proxy(v33);
    }
    else
    {
      v34 = 0;
    }
    *((_QWORD *)v14 + 4) = v34;
  }
  if ( !a4 )
  {
LABEL_12:
    v20 = (struct _MODULE_ENTRY *)pMemAlloc(0x5EB0u);
    v16 = v20;
    v44 = v20;
    if ( !v20 )
      return 0;
    InitModuleEntry(v20);
    v21 = (unsigned __int64 *)((char *)v16 + 24);
    *((_QWORD *)v16 + 3) = a4;
    *((_DWORD *)v16 + 8) = a5;
    *((_QWORD *)v16 + 2422) = a6;
    *((_DWORD *)v16 + 4971) = (a8 & 0x200000) != 0;
    *((_QWORD *)v16 + 2) = v14;
    if ( lpSrc )
    {
      v22 = StringDupExpand(lpSrc);
      *((_QWORD *)v16 + 38) = v22;
      _wsplitpath_s(v22, 0, 0, 0, 0, Filename, 0x100u, 0, 0);
      _o_wcsncpy_s((char *)v16 + 46, 64, Filename, -1);
      if ( a3 && (unsigned int)_o__wcsicmp(a3, (char *)v16 + 46) )
        _o_wcsncpy_s((char *)v16 + 174, 64, a3, 63);
      else
        *((_WORD *)v16 + 87) = 0;
    }
    else if ( a3 )
    {
      wcscpy_s_ex((unsigned __int16 *)v16 + 87, 0x40u, a3);
    }
    *((_QWORD *)v16 + 2430) = 0;
    *((_DWORD *)v16 + 4866) = 0;
    *((_QWORD *)v16 + 2432) = 0;
    *((_DWORD *)v16 + 4936) = v43;
    if ( !a7 )
    {
      v23 = v45[0];
LABEL_18:
      if ( (dword_1802AF9CC & 4) != 0 && a4 )
      {
        *((_DWORD *)v16 + 4842) |= 1u;
        *((_DWORD *)v16 + 599) = 5;
LABEL_21:
        v24 = (struct _MODULE_ENTRY **)*((_QWORD *)v14 + 3);
        *(_QWORD *)v16 = (char *)v14 + 16;
        *((_QWORD *)v16 + 1) = v24;
        *v24 = v16;
        *((_QWORD *)v14 + 3) = v16;
        v25 = *((_QWORD *)v14 + 4);
        if ( v25 )
        {
          std::_Tree<std::_Tmap_traits<unsigned __int64,_MODULE_ENTRY *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,_MODULE_ENTRY *>>,0>>::_Emplace<unsigned __int64 &,_MODULE_ENTRY * &>(
            v25,
            v45,
            (char *)v16 + 24,
            &v44);
          v16 = v44;
        }
        *((_QWORD *)v16 + 3022) = (char *)v16 + 24168;
        *((_QWORD *)v16 + 3021) = (char *)v16 + 24168;
        v26 = *((_QWORD *)v14 + 33);
        if ( *((_QWORD *)v16 + 3) <= v26 && *((_QWORD *)v16 + 3) + (unsigned __int64)a5 >= v26 )
          diaSetModFromIP(v14);
        return *((_QWORD *)v16 + 3);
      }
      if ( (unsigned int)modload(v23, v16) && *v21 )
        goto LABEL_21;
LABEL_66:
      FreeModuleEntry(v14, v16);
      return 0;
    }
    if ( a7->ssize == 24 )
    {
      *((struct _MODLOAD_DATA *)v16 + 823) = *a7;
      v28 = *((_DWORD *)v16 + 4942);
      if ( v28 )
      {
        v29 = (void *)pMemAlloc(v28);
        *((_QWORD *)v16 + 2472) = v29;
        if ( v29 )
        {
          *((_QWORD *)v16 + 2470) = v29;
          memcpy_0(v29, a7->data, *((unsigned int *)v16 + 4942));
          if ( a7->ssig == 4096 && a7->size >= 8 )
          {
            data = (unsigned __int64 *)a7->data;
            if ( a7->size >= 16 * *data + 8 )
            {
              v39 = data + 1;
              for ( i = 0; i < *data; ++i )
              {
                v41 = pMemAlloc(0x20u);
                if ( !v41 )
                  goto LABEL_66;
                *(_OWORD *)(v41 + 16) = *v39;
                v42 = (__int64 *)*((_QWORD *)v16 + 3026);
                *(_QWORD *)v41 = (char *)v16 + 24200;
                *(_QWORD *)(v41 + 8) = v42;
                *v42 = v41;
                *((_QWORD *)v16 + 3026) = v41;
                ++*((_DWORD *)v14 + 27431);
                ++v39;
              }
            }
          }
          v23 = v45[0];
          if ( a7->ssig == 2 )
          {
            if ( *(_DWORD *)a7->data )
            {
              inited = InitIDD(
                         v45[0],
                         (char *)0xFFFFFFFFFFFFFFFFLL,
                         0,
                         *((_DWORD *)v14 + 14),
                         0,
                         *v21,
                         *((_DWORD *)v16 + 8),
                         a7,
                         *((_DWORD *)v16 + 4936));
              v31 = inited;
              if ( inited )
              {
                if ( (unsigned int)ReadCallerData(inited) && !*((_QWORD *)v31 + 527) )
                {
                  iddcv2me(v32, v31, v16);
                  *((_DWORD *)v16 + 4958) = *((_DWORD *)v31 + 558);
                  *((_DWORD *)v16 + 4957) = *((_DWORD *)v31 + 557);
                  *(_OWORD *)((char *)v16 + 19836) = *(_OWORD *)((char *)v31 + 2244);
                }
                ReleaseDebugData(v31, 0x123u);
              }
            }
          }
          goto LABEL_18;
        }
        v27 = 8;
LABEL_30:
        SetLastError(v27);
        return 0;
      }
    }
LABEL_29:
    v27 = 87;
    goto LABEL_30;
  }
  ModuleForDLLBase = GetModuleForDLLBase(v14, a4);
  v16 = ModuleForDLLBase;
  if ( !ModuleForDLLBase )
  {
    while ( 1 )
    {
      ModuleForPC = GetModuleForPC(v14, a4, 0, 1, 0, 0);
      v19 = ModuleForPC;
      if ( !ModuleForPC )
        break;
      v35 = *(_QWORD *)ModuleForPC;
      v36 = (_QWORD *)*((_QWORD *)ModuleForPC + 1);
      *v36 = v35;
      *(_QWORD *)(v35 + 8) = v36;
      v37 = (const WCHAR *)*((_QWORD *)v19 + 39);
      if ( !v37 )
      {
        v37 = (const WCHAR *)*((_QWORD *)v19 + 38);
        if ( !v37 )
          v37 = (const WCHAR *)((char *)v19 + 46);
      }
      DoSymbolCallback(v14, 4u, v19, &v46, v37);
      FreeModuleEntry(v14, v19);
    }
    goto LABEL_12;
  }
  if ( (*((_BYTE *)ModuleForDLLBase + 19368) & 1) == 0 || !(unsigned int)modload(a1, ModuleForDLLBase) )
    return 0;
  return *((_QWORD *)v16 + 3);
}

```

## disassembly

```asm
0x1800091a0  push    rbx
0x1800091a2  push    rbp
0x1800091a3  push    rsi
0x1800091a4  push    rdi
0x1800091a5  push    r12
0x1800091a7  push    r13
0x1800091a9  push    r14
0x1800091ab  push    r15
0x1800091ad  sub     rsp, 4D8h
0x1800091b4  mov     [rsp+518h+var_4A8], 0FFFFFFFFFFFFFFFEh
0x1800091bd  mov     rax, cs:__security_cookie
0x1800091c4  xor     rax, rsp
0x1800091c7  mov     [rsp+518h+var_58], rax
0x1800091cf  mov     r12, r9
0x1800091d2  mov     r14, r8
0x1800091d5  mov     rbp, rdx
0x1800091d8  mov     r15, rcx
0x1800091db  mov     [rsp+518h+var_4B8], rcx
0x1800091e0  mov     rsi, [rsp+518h+arg_30]
0x1800091e8  xor     edx, edx; Val
0x1800091ea  mov     r8d, 238h; Size
0x1800091f0  lea     rcx, [rsp+518h+var_498]; void *
0x1800091f8  call    memset_0
0x1800091fd  mov     ecx, [rsp+518h+arg_38]
0x180009204  bt      ecx, 15h
0x180009208  mov     r13d, 0
0x18000920e  mov     edx, r13d
0x180009211  setb    dl
0x180009214  mov     [rsp+518h+var_4C8], edx
0x180009218  mov     edx, ecx
0x18000921a  btr     edx, 15h
0x18000921e  bt      ecx, 15h
0x180009222  cmovnb  edx, ecx
0x180009225  mov     [rsp+518h+var_4C4], edx
0x180009229  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18000922d  jz      short loc_18000928D
0x18000922f  lea     rdx, aPdb_3; ".pdb"
0x180009236  mov     rcx, rbp; unsigned __int16 *
0x180009239  call    ?extmatch@@YAHPEBG0@Z; extmatch(ushort const *,ushort const *)
0x18000923e  test    eax, eax
0x180009240  jnz     loc_18000971E
0x180009246  mov     rcx, r15; void *
0x180009249  call    ?FindProcessEntry@@YAPEAU_PROCESS_ENTRY@@PEAX@Z; FindProcessEntry(void *)
0x18000924e  mov     rdi, rax
0x180009251  test    rax, rax
0x180009254  jz      loc_18000972C
0x18000925a  cmp     [rax+20h], r13
0x18000925e  jz      loc_18000960A
0x180009264  test    r12, r12
0x180009267  jz      loc_180009461
0x18000926d  mov     rdx, r12; unsigned __int64
0x180009270  mov     rcx, rdi; struct _PROCESS_ENTRY *
0x180009273  call    ?GetModuleForDLLBase@@YAPEAU_MODULE_ENTRY@@PEAU_PROCESS_ENTRY@@_K@Z; GetModuleForDLLBase(_PROCESS_ENTRY *,unsigned __int64)
0x180009278  mov     rbx, rax
0x18000927b  test    rax, rax
0x18000927e  jz      short loc_180009294
0x180009280  test    byte ptr [rax+4BA8h], 1
0x180009287  jnz     loc_18000973E
0x18000928d  xor     eax, eax
0x18000928f  jmp     loc_18000943D
0x180009294  xor     r15d, r15d
0x180009297  mov     byte ptr [rsp+518h+Filename], r15b; bool
0x18000929c  mov     byte ptr [rsp+518h+DirCount], r15b; bool
0x1800092a1  mov     r9b, 1; bool
0x1800092a4  xor     r8d, r8d; bool
0x1800092a7  mov     rdx, r12; unsigned __int64
0x1800092aa  mov     rcx, rdi; struct _PROCESS_ENTRY *
0x1800092ad  call    ?GetModuleForPC@@YAPEAU_MODULE_ENTRY@@PEAU_PROCESS_ENTRY@@_K_N222@Z; GetModuleForPC(_PROCESS_ENTRY *,unsigned __int64,bool,bool,bool,bool)
0x1800092b2  mov     rbx, rax
0x1800092b5  test    rax, rax
0x1800092b8  jnz     loc_180009645
0x1800092be  mov     ecx, 5EB0h; dwBytes
0x1800092c3  call    pMemAlloc
0x1800092c8  mov     rbx, rax
0x1800092cb  mov     [rsp+518h+var_4C0], rax
0x1800092d0  test    rax, rax
0x1800092d3  jz      short loc_18000928D
0x1800092d5  mov     rcx, rax; struct _MODULE_ENTRY *
0x1800092d8  call    ?InitModuleEntry@@YAXPEAU_MODULE_ENTRY@@@Z; InitModuleEntry(_MODULE_ENTRY *)
0x1800092dd  lea     r13, [rbx+18h]
0x1800092e1  mov     [r13+0], r12
0x1800092e5  mov     eax, [rsp+518h+arg_20]
0x1800092ec  mov     [rbx+20h], eax
0x1800092ef  mov     rax, [rsp+518h+arg_28]
0x1800092f7  mov     [rbx+4BB0h], rax
0x1800092fe  mov     eax, [rsp+518h+var_4C8]
0x180009302  mov     [rbx+4DACh], eax
0x180009308  mov     [rbx+10h], rdi
0x18000930c  test    rbp, rbp
0x18000930f  jz      loc_180009469
0x180009315  mov     rcx, rbp; lpSrc
0x180009318  call    ?StringDupExpand@@YAPEAGPEBG@Z; StringDupExpand(ushort const *)
0x18000931d  mov     [rbx+130h], rax
0x180009324  mov     [rsp+518h+ExtCount], r15; ExtCount
0x180009329  mov     [rsp+518h+Ext], r15; Ext
0x18000932e  mov     [rsp+518h+FilenameCount], 100h; FilenameCount
0x180009337  lea     rcx, [rsp+518h+var_258]
0x18000933f  mov     [rsp+518h+Filename], rcx; Filename
0x180009344  mov     [rsp+518h+DirCount], r15; DirCount
0x180009349  xor     r9d, r9d; Dir
0x18000934c  xor     r8d, r8d; DriveCount
0x18000934f  xor     edx, edx; Drive
0x180009351  mov     rcx, rax; FullPath
0x180009354  call    cs:__imp__wsplitpath_s
0x18000935a  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000935e  lea     r8, [rsp+518h+var_258]
0x180009366  lea     ebp, [r9+41h]
0x18000936a  mov     edx, ebp
0x18000936c  lea     rcx, [rbx+2Eh]
0x180009370  call    cs:__imp__o_wcsncpy_s
0x180009376  test    r14, r14
0x180009379  jnz     loc_1800095B7
0x18000937f  xor     r15d, r15d
0x180009382  mov     [rbx+0AEh], r15w
0x18000938a  mov     [rbx+4BF0h], r15
0x180009391  mov     [rbx+4C08h], r15d
0x180009398  mov     [rbx+4C00h], r15
0x18000939f  mov     eax, [rsp+518h+var_4C4]
0x1800093a3  mov     [rbx+4D20h], eax
0x1800093a9  test    rsi, rsi
0x1800093ac  jnz     loc_18000948B
0x1800093b2  mov     rbp, [rsp+518h+var_4B8]
0x1800093b7  test    byte ptr cs:dword_1802AF9CC, 4
0x1800093be  jnz     loc_1800095EB
0x1800093c4  mov     rdx, rbx; struct _MODULE_ENTRY *
0x1800093c7  mov     rcx, rbp; void *
0x1800093ca  call    ?modload@@YAHPEAXPEAU_MODULE_ENTRY@@@Z; modload(void *,_MODULE_ENTRY *)
0x1800093cf  test    eax, eax
0x1800093d1  jz      loc_180009756
0x1800093d7  cmp     [r13+0], r15
0x1800093db  jz      loc_180009756
0x1800093e1  lea     rcx, [rdi+10h]
0x1800093e5  mov     rax, [rcx+8]
0x1800093e9  mov     [rbx], rcx
0x1800093ec  mov     [rbx+8], rax
0x1800093f0  mov     [rax], rbx
0x1800093f3  mov     [rcx+8], rbx
0x1800093f7  mov     rcx, [rdi+20h]
0x1800093fb  test    rcx, rcx
0x1800093fe  jz      short loc_180009417
0x180009400  lea     r9, [rsp+518h+var_4C0]
0x180009405  mov     r8, r13
0x180009408  lea     rdx, [rsp+518h+var_4B8]
0x18000940d  call    ??$_Emplace@AEA_KAEAPEAU_MODULE_ENTRY@@@?$_Tree@V?$_Tmap_traits@_KPEAU_MODULE_ENTRY@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KPEAU_MODULE_ENTRY@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KPEAU_MODULE_ENTRY@@@std@@PEAX@std@@_N@1@AEA_KAEAPEAU_MODULE_ENTRY@@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,_MODULE_ENTRY *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,_MODULE_ENTRY *>>,0>>::_Emplace<unsigned __int64 &,_MODULE_ENTRY * &>(unsigned __int64 &,_MODULE_ENTRY * &)
0x180009412  mov     rbx, [rsp+518h+var_4C0]
0x180009417  lea     rax, [rbx+5E68h]
0x18000941e  mov     [rbx+5E70h], rax
0x180009425  mov     [rax], rax
0x180009428  mov     rcx, [rdi+108h]
0x18000942f  cmp     [rbx+18h], rcx
0x180009433  jbe     loc_180009766
0x180009439  mov     rax, [rbx+18h]
0x18000943d  mov     rcx, [rsp+518h+var_58]
0x180009445  xor     rcx, rsp; StackCookie
0x180009448  call    __security_check_cookie
0x18000944d  add     rsp, 4D8h
0x180009454  pop     r15
0x180009456  pop     r14
0x180009458  pop     r13
0x18000945a  pop     r12
0x18000945c  pop     rdi
0x18000945d  pop     rsi
0x18000945e  pop     rbp
0x18000945f  pop     rbx
0x180009460  retn
0x180009461  xor     r15d, r15d
0x180009464  jmp     loc_1800092BE
0x180009469  test    r14, r14
0x18000946c  jz      loc_18000938A
0x180009472  lea     rcx, [rbx+0AEh]; unsigned __int16 *
0x180009479  mov     r8, r14; unsigned __int16 *
0x18000947c  mov     edx, 40h ; '@'; unsigned __int64
0x180009481  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x180009486  jmp     loc_18000938A
0x18000948b  cmp     dword ptr [rsi], 18h
0x18000948e  jz      short loc_1800094A0
0x180009490  mov     ecx, 57h ; 'W'; dwErrCode
0x180009495  call    cs:__imp_SetLastError
0x18000949b  jmp     loc_18000928D
0x1800094a0  movups  xmm0, xmmword ptr [rsi]
0x1800094a3  movups  xmmword ptr [rbx+4D28h], xmm0
0x1800094aa  movsd   xmm1, qword ptr [rsi+10h]
0x1800094af  movsd   qword ptr [rbx+4D38h], xmm1
0x1800094b7  mov     eax, [rbx+4D38h]
0x1800094bd  test    eax, eax
0x1800094bf  jz      short loc_180009490
0x1800094c1  mov     ecx, eax; dwBytes
0x1800094c3  call    pMemAlloc
0x1800094c8  mov     [rbx+4D40h], rax
0x1800094cf  test    rax, rax
0x1800094d2  jz      loc_18000970C
0x1800094d8  mov     [rbx+4D30h], rax
0x1800094df  mov     r8d, [rbx+4D38h]; Size
0x1800094e6  mov     rdx, [rsi+8]; Src
0x1800094ea  mov     rcx, rax; void *
0x1800094ed  call    memcpy_0
0x1800094f2  cmp     dword ptr [rsi+4], 1000h
0x1800094f9  jz      loc_18000969C
0x1800094ff  mov     rbp, [rsp+518h+var_4B8]
0x180009504  cmp     dword ptr [rsi+4], 2
0x180009508  jnz     loc_1800093B7
0x18000950e  mov     rax, [rsi+8]
0x180009512  cmp     [rax], r15d
0x180009515  jz      loc_1800093B7
0x18000951b  mov     eax, [rbx+4D20h]
0x180009521  mov     dword ptr [rsp+518h+ExtCount], eax; unsigned int
0x180009525  mov     [rsp+518h+Ext], rsi; struct _MODLOAD_DATA *
0x18000952a  mov     eax, [rbx+20h]
0x18000952d  mov     dword ptr [rsp+518h+FilenameCount], eax; unsigned int
0x180009531  mov     rax, [r13+0]
0x180009535  mov     [rsp+518h+Filename], rax; unsigned __int64
0x18000953a  mov     [rsp+518h+DirCount], r15; Source
0x18000953f  mov     r9d, [rdi+38h]; unsigned int
0x180009543  xor     r8d, r8d; unsigned __int16 *
0x180009546  or      rdx, 0FFFFFFFFFFFFFFFFh; hFile
0x18000954a  mov     rcx, rbp; void *
0x18000954d  call    ?InitIDD@@YAPEAU_IMGHLP_DEBUG_DATA@@PEAX0PEBGK1_KKPEAU_MODLOAD_DATA@@KK@Z; InitIDD(void *,void *,ushort const *,ulong,ushort const *,unsigned __int64,ulong,_MODLOAD_DATA *,ulong,ulong)
0x180009552  mov     rsi, rax
0x180009555  test    rax, rax
0x180009558  jz      loc_1800093B7
0x18000955e  mov     rcx, rax; struct _IMGHLP_DEBUG_DATA *
0x180009561  call    ?ReadCallerData@@YAHPEAU_IMGHLP_DEBUG_DATA@@@Z; ReadCallerData(_IMGHLP_DEBUG_DATA *)
0x180009566  test    eax, eax
0x180009568  jz      short loc_1800095A5
0x18000956a  cmp     [rsi+1078h], r15
0x180009571  jnz     short loc_1800095A5
0x180009573  mov     r8, rbx; struct _MODULE_ENTRY *
0x180009576  mov     rdx, rsi; struct _IMGHLP_DEBUG_DATA *
0x180009579  call    ?iddcv2me@@YAXPEAU_PROCESS_ENTRY@@PEAU_IMGHLP_DEBUG_DATA@@PEAU_MODULE_ENTRY@@@Z; iddcv2me(_PROCESS_ENTRY *,_IMGHLP_DEBUG_DATA *,_MODULE_ENTRY *)
0x18000957e  mov     eax, [rsi+8B8h]
0x180009584  mov     [rbx+4D78h], eax
0x18000958a  mov     eax, [rsi+8B4h]
0x180009590  mov     [rbx+4D74h], eax
0x180009596  movups  xmm0, xmmword ptr [rsi+8C4h]
0x18000959d  movdqu  xmmword ptr [rbx+4D7Ch], xmm0
0x1800095a5  mov     edx, 123h; unsigned int
0x1800095aa  mov     rcx, rsi; lpMem
0x1800095ad  call    ?ReleaseDebugData@@YAXPEAU_IMGHLP_DEBUG_DATA@@K@Z; ReleaseDebugData(_IMGHLP_DEBUG_DATA *,ulong)
0x1800095b2  jmp     loc_1800093B7
0x1800095b7  lea     rdx, [rbx+2Eh]
0x1800095bb  mov     rcx, r14
0x1800095be  call    cs:__imp__o__wcsicmp
0x1800095c4  xor     r15d, r15d
0x1800095c7  test    eax, eax
0x1800095c9  jz      loc_180009382
0x1800095cf  lea     rcx, [rbx+0AEh]
0x1800095d6  lea     r9d, [r15+3Fh]
0x1800095da  mov     r8, r14
0x1800095dd  mov     rdx, rbp
0x1800095e0  call    cs:__imp__o_wcsncpy_s
0x1800095e6  jmp     loc_18000938A
0x1800095eb  test    r12, r12
0x1800095ee  jz      loc_1800093C4
0x1800095f4  or      dword ptr [rbx+4BA8h], 1
0x1800095fb  mov     dword ptr [rbx+95Ch], 5
0x180009605  jmp     loc_1800093E1
0x18000960a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009611  mov     ecx, 10h; unsigned __int64
0x180009616  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000961b  mov     rbx, rax
0x18000961e  mov     [rsp+518h+var_4C0], rax
0x180009623  test    rax, rax
0x180009626  jz      loc_180009736
0x18000962c  mov     [rax], r13
0x18000962f  mov     [rax+8], r13
0x180009633  mov     rcx, rax
0x180009636  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@_KPEAU_MODULE_ENTRY@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KPEAU_MODULE_ENTRY@@@std@@@3@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<unsigned __int64,_MODULE_ENTRY *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,_MODULE_ENTRY *>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18000963b  nop
0x18000963c  mov     [rdi+20h], rbx
0x180009640  jmp     loc_180009264
0x180009645  mov     rcx, [rax]
0x180009648  mov     rax, [rax+8]
0x18000964c  mov     [rax], rcx
0x18000964f  mov     [rcx+8], rax
0x180009653  mov     rax, [rbx+138h]
0x18000965a  test    rax, rax
0x18000965d  jnz     short loc_18000966F
0x18000965f  mov     rax, [rbx+130h]
0x180009666  test    rax, rax
0x180009669  jnz     short loc_18000966F
0x18000966b  lea     rax, [rbx+2Eh]
0x18000966f  mov     [rsp+518h+DirCount], rax; lpWideCharStr
0x180009674  lea     r9, [rsp+518h+var_498]; struct _IMAGEHLP_DEFERRED_SYMBOL_LOADW64 *
0x18000967c  mov     r8, rbx; struct _MODULE_ENTRY *
0x18000967f  mov     edx, 4; unsigned int
0x180009684  mov     rcx, rdi; struct _PROCESS_ENTRY *
0x180009687  call    ?DoSymbolCallback@@YAHPEAU_PROCESS_ENTRY@@KPEAU_MODULE_ENTRY@@PEAU_IMAGEHLP_DEFERRED_SYMBOL_LOADW64@@PEBG@Z; DoSymbolCallback(_PROCESS_ENTRY *,ulong,_MODULE_ENTRY *,_IMAGEHLP_DEFERRED_SYMBOL_LOADW64 *,ushort const *)
0x18000968c  mov     rdx, rbx; struct _MODULE_ENTRY *
0x18000968f  mov     rcx, rdi; struct _PROCESS_ENTRY *
0x180009692  call    ?FreeModuleEntry@@YAXPEAU_PROCESS_ENTRY@@PEAU_MODULE_ENTRY@@@Z; FreeModuleEntry(_PROCESS_ENTRY *,_MODULE_ENTRY *)
0x180009697  jmp     loc_180009297
0x18000969c  cmp     dword ptr [rsi+10h], 8
0x1800096a0  jb      loc_1800094FF
0x1800096a6  mov     r14, [rsi+8]
0x1800096aa  mov     rcx, [r14]
0x1800096ad  shl     rcx, 4
0x1800096b1  add     rcx, 8
0x1800096b5  mov     eax, [rsi+10h]
0x1800096b8  cmp     rax, rcx
0x1800096bb  jb      loc_1800094FF
  ... truncated ...
```
