# CMapperCache::RegEnumFilterInfo(Cursor &,bool,ulong,int,_GUID const *,ulong,REGPINMEDIUM const *,_GUID const *,int,int,_GUID const *,ulong,REGPINMEDIUM const *,_GUID const *,IMoniker * *,_GUID *,ushort *)

- ea: `0x180015350`
- end: `0x18001575a`
- name: `?RegEnumFilterInfo@CMapperCache@@QEAAJAEAUCursor@@_NKHPEBU_GUID@@KPEBUREGPINMEDIUM@@2HH2K32PEAPEAUIMoniker@@PEAU3@PEAG@Z`
- size: `1034`
- prototype: `__int64 __usercall@<rax>(CMapperCache *__hidden this@<rcx>, struct Cursor *@<rdx>, bool@<r8b>, unsigned int@<r9d>, int, const struct _GUID *, unsigned int, const struct REGPINMEDIUM *, const struct _GUID *, int, int, const struct _GUID *, unsigned int, const struct REGPINMEDIUM *, const struct _GUID *, struct IMoniker **, struct _GUID *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800150a0`
- `0x180066dc0`

## callees

- `0x1800078b0`
- `0x180015350`
- `0x180015760`
- `0x180015810`
- `0x180020d1c`
- `0x180020e20`
- `0x180067024`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800153a4`
- `KERNEL32!LeaveCriticalSection` at `0x1800156e0`
- `KERNEL32!LeaveCriticalSection` at `0x180015714`
- `KERNEL32!LeaveCriticalSection` at `0x180015727`
- `KERNEL32!LeaveCriticalSection` at `0x18001573d`
- `KERNEL32!LeaveCriticalSection` at `0x1800153a4`
- `KERNEL32!LeaveCriticalSection` at `0x1800156e0`
- `KERNEL32!LeaveCriticalSection` at `0x180015714`
- `KERNEL32!LeaveCriticalSection` at `0x180015727`
- `KERNEL32!LeaveCriticalSection` at `0x18001573d`
- `KERNEL32!EnterCriticalSection` at `0x18001536d`
- `KERNEL32!EnterCriticalSection` at `0x18001536d`
- `ole32!CoTaskMemFree` at `0x1800156cd`
- `ole32!CoTaskMemFree` at `0x1800156cd`

## pseudocode

```c
__int64 __fastcall CMapperCache::RegEnumFilterInfo(
        CMapperCache *this,
        struct Cursor *a2,
        bool a3,
        unsigned int a4,
        int a5,
        const struct _GUID *a6,
        unsigned int a7,
        const struct REGPINMEDIUM *a8,
        const struct _GUID *a9,
        int a10,
        int a11,
        const struct _GUID *a12,
        unsigned int a13,
        const struct REGPINMEDIUM *a14,
        const struct _GUID *a15,
        struct IMoniker **a16,
        struct _GUID *a17,
        unsigned __int16 *a18)
{
  unsigned int v18; // ebp
  int v21; // r13d
  int v23; // r11d
  __int64 v24; // rax
  CMapperCache *v25; // rcx
  __int64 v26; // r12
  unsigned int i; // r9d
  int v28; // edx
  __int64 v29; // rcx
  __int64 v30; // rax
  CMapperCache **v31; // rax
  __int64 v32; // rsi
  BOOL v33; // r14d
  BOOL v34; // ebx
  unsigned int v35; // ebp
  __int64 v36; // r13
  const struct REGFILTERPINS2 *v37; // rdx
  const OLECHAR *v38; // rcx
  int v39; // eax
  int MonikerClsid; // eax
  struct IMoniker *v41; // rcx
  const unsigned __int16 *Name; // rax
  int v43; // ebx
  LPVOID v44; // r11
  int v45; // [rsp+90h] [rbp+8h]

  v18 = a4;
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  if ( v18 < *((_DWORD *)this + 13) )
  {
    *((_DWORD *)this + 10) = 1;
    *((_DWORD *)this + 13) = v18;
  }
  v45 = CMapperCache::Refresh(this);
  v21 = v45;
  if ( v45 < 0 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)this);
    return (unsigned int)v45;
  }
  if ( *(_QWORD *)a2 )
  {
    if ( v45 == 1 || *((_DWORD *)a2 + 2) != *((_DWORD *)this + 11) )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)this);
      return 2147746307LL;
    }
  }
  else
  {
    *(_QWORD *)a2 = **((_QWORD **)this + 7);
    *((_DWORD *)a2 + 2) = *((_DWORD *)this + 11);
    *((_BYTE *)a2 + 12) = 0;
  }
  v23 = a11;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        do
        {
          v24 = *(_QWORD *)a2;
          if ( !*(_QWORD *)a2 )
          {
            LeaveCriticalSection((LPCRITICAL_SECTION)this);
            return 1;
          }
          v25 = *(CMapperCache **)(v24 + 8);
          *(_QWORD *)a2 = v25;
          v26 = *(_QWORD *)(v24 + 16);
          if ( !v25 && !*((_BYTE *)a2 + 12) )
          {
            for ( i = 1; i < a7; ++i )
            {
              v28 = 2 * i;
              v29 = *(_QWORD *)&a6[2 * i].Data1 - *(_QWORD *)&GUID_NULL.Data1;
              if ( !v29 )
                v29 = *(_QWORD *)a6[2 * i].Data4 - *(_QWORD *)GUID_NULL.Data4;
              if ( !v29 )
                goto LABEL_22;
              v25 = (CMapperCache *)(2LL * (unsigned int)(v28 + 1));
              v30 = *(_QWORD *)&a6[v28 + 1].Data1 - *(_QWORD *)&GUID_NULL.Data1;
              if ( !v30 )
                v30 = *(_QWORD *)a6[v28 + 1].Data4 - *(_QWORD *)GUID_NULL.Data4;
              if ( !v30 )
              {
LABEL_22:
                *((_BYTE *)a2 + 12) = 1;
                v31 = (CMapperCache **)*((_QWORD *)this + 7);
                v25 = *v31;
                *(_QWORD *)a2 = *v31;
                break;
              }
            }
          }
          v32 = *(_QWORD *)(v26 + 8);
          v33 = v23 == 0;
          v34 = a5 == 0;
        }
        while ( *(_DWORD *)(v32 + 4) < v18 );
        v35 = *(_DWORD *)(v32 + 8);
        if ( v35 )
          break;
LABEL_40:
        v18 = a4;
        if ( v34 && v33 )
          goto LABEL_44;
      }
      v36 = 0;
      while ( !v33 || !v34 )
      {
        v37 = (const struct REGFILTERPINS2 *)(*(_QWORD *)(v32 + 16) + 48 * v36);
        if ( (v37->dwFlags & 8) != 0 )
        {
          if ( v33 || (unsigned int)CMapperCache::FindType(v25, v37, a12, a13, a14, a15, a3, 0, 0) )
            v33 = 1;
        }
        else
        {
          v34 = v34
             || (!a10 || (v37->dwFlags & 2) != 0)
             && (unsigned int)CMapperCache::FindType(v25, v37, a6, a7, a8, a9, a3, 1, *((unsigned __int8 *)a2 + 12));
        }
        v36 = (unsigned int)(v36 + 1);
        if ( (unsigned int)v36 >= v35 )
        {
          v21 = v45;
          v23 = a11;
          goto LABEL_40;
        }
      }
      v21 = v45;
      v23 = a11;
LABEL_44:
      if ( *(_QWORD *)v26 )
        break;
      v38 = *(const OLECHAR **)(v26 + 16);
      v18 = a4;
      if ( v38 )
      {
        v39 = ParseDisplayNameHelper(v38, *((struct IClassFactory **)this + 10), (struct IMoniker **)v26);
        v23 = a11;
        v21 = v39;
        v45 = v39;
        break;
      }
    }
    v18 = a4;
    if ( v21 >= 0 )
    {
      if ( !a17 )
        break;
      MonikerClsid = GetMonikerClsid(*(struct IMoniker **)v26, a17);
      v23 = a11;
      if ( MonikerClsid >= 0 )
        break;
    }
  }
  if ( a16 )
  {
    v41 = *(struct IMoniker **)v26;
    *a16 = *(struct IMoniker **)v26;
    ((void (__fastcall *)(struct IMoniker *))v41->lpVtbl->AddRef)(v41);
  }
  if ( a18
    && (Name = MonGetName(*(struct IMoniker **)v26)) != 0
    && (v43 = StringCchCopyW(a18, 0x104u, Name), CoTaskMemFree(v44), v43 < 0) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)this);
    return (unsigned int)v43;
  }
  else
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)this);
    return 0;
  }
}

```

## disassembly

```asm
0x180015350  mov     [rsp+arg_18], r9d
0x180015355  mov     [rsp+arg_10], r8b
0x18001535a  push    rbp
0x18001535b  push    rdi
0x18001535c  push    r13
0x18001535e  push    r15
0x180015360  sub     rsp, 68h
0x180015364  mov     ebp, r9d
0x180015367  mov     rdi, rdx
0x18001536a  mov     r15, rcx
0x18001536d  call    cs:__imp_EnterCriticalSection
0x180015374  nop     dword ptr [rax+rax+00h]
0x180015379  cmp     ebp, [r15+34h]
0x18001537d  jnb     short loc_18001538B
0x18001537f  mov     dword ptr [r15+28h], 1
0x180015387  mov     [r15+34h], ebp
0x18001538b  mov     rcx, r15; this
0x18001538e  call    ?Refresh@CMapperCache@@AEAAJXZ; CMapperCache::Refresh(void)
0x180015393  mov     [rsp+88h+arg_0], eax
0x18001539a  mov     r13d, eax
0x18001539d  test    eax, eax
0x18001539f  jns     short loc_1800153BF
0x1800153a1  mov     rcx, r15; lpCriticalSection
0x1800153a4  call    cs:__imp_LeaveCriticalSection
0x1800153ab  nop     dword ptr [rax+rax+00h]
0x1800153b0  mov     eax, r13d
0x1800153b3  add     rsp, 68h
0x1800153b7  pop     r15
0x1800153b9  pop     r13
0x1800153bb  pop     rdi
0x1800153bc  pop     rbp
0x1800153bd  retn
0x1800153bf  cmp     qword ptr [rdi], 0
0x1800153c3  jnz     short loc_1800153DC
0x1800153c5  mov     rax, [r15+38h]
0x1800153c9  mov     rcx, [rax]
0x1800153cc  mov     [rdi], rcx
0x1800153cf  mov     eax, [r15+2Ch]
0x1800153d3  mov     [rdi+8], eax
0x1800153d6  mov     byte ptr [rdi+0Ch], 0
0x1800153da  jmp     short loc_1800153F3
0x1800153dc  cmp     r13d, 1
0x1800153e0  jz      loc_18001573A
0x1800153e6  mov     eax, [r15+2Ch]
0x1800153ea  cmp     [rdi+8], eax
0x1800153ed  jnz     loc_18001573A
0x1800153f3  mov     r11d, [rsp+88h+arg_50]
0x1800153fb  mov     [rsp+88h+arg_8], rbx
0x180015403  mov     [rsp+88h+var_28], rsi
0x180015408  mov     [rsp+88h+var_38], r14
0x18001540d  mov     [rsp+88h+var_30], r12
0x180015412  mov     rax, [rdi]
0x180015415  test    rax, rax
0x180015418  jz      loc_180015724
0x18001541e  mov     rcx, [rax+8]
0x180015422  mov     [rdi], rcx
0x180015425  mov     r12, [rax+10h]
0x180015429  test    rcx, rcx
0x18001542c  jnz     short loc_1800154A7
0x18001542e  cmp     [rdi+0Ch], cl
0x180015431  jnz     short loc_1800154A7
0x180015433  mov     r10, qword ptr cs:GUID_NULL.Data4
0x18001543a  mov     r9d, 1
0x180015440  mov     r8, qword ptr cs:GUID_NULL.Data1
0x180015447  mov     rbx, [rsp+88h+arg_28]
0x18001544f  cmp     r9d, [rsp+88h+arg_30]
0x180015457  jnb     short loc_1800154A7
0x180015459  lea     edx, [r9+r9]
0x18001545d  mov     eax, edx
0x18001545f  add     rax, rax
0x180015462  mov     rcx, [rbx+rax*8]
0x180015466  sub     rcx, r8
0x180015469  jnz     short loc_180015473
0x18001546b  mov     rcx, [rbx+rax*8+8]
0x180015470  sub     rcx, r10
0x180015473  test    rcx, rcx
0x180015476  jz      short loc_180015499
0x180015478  lea     ecx, [rdx+1]
0x18001547b  add     rcx, rcx
0x18001547e  mov     rax, [rbx+rcx*8]
0x180015482  sub     rax, r8
0x180015485  jnz     short loc_18001548F
0x180015487  mov     rax, [rbx+rcx*8+8]
0x18001548c  sub     rax, r10
0x18001548f  test    rax, rax
0x180015492  jz      short loc_180015499
0x180015494  inc     r9d
0x180015497  jmp     short loc_18001544F
0x180015499  mov     byte ptr [rdi+0Ch], 1
0x18001549d  mov     rax, [r15+38h]
0x1800154a1  mov     rcx, [rax]; this
0x1800154a4  mov     [rdi], rcx
0x1800154a7  mov     rsi, [r12+8]
0x1800154ac  xor     r14d, r14d
0x1800154af  test    r11d, r11d
0x1800154b2  setz    r14b
0x1800154b6  xor     ebx, ebx
0x1800154b8  cmp     [rsp+88h+arg_20], ebx
0x1800154bf  setz    bl
0x1800154c2  cmp     [rsi+4], ebp
0x1800154c5  jb      loc_180015412
0x1800154cb  mov     ebp, [rsi+8]
0x1800154ce  test    ebp, ebp
0x1800154d0  jz      loc_1800155DA
0x1800154d6  xor     r13d, r13d
0x1800154d9  test    r14d, r14d
0x1800154dc  jz      short loc_1800154E6
0x1800154de  test    ebx, ebx
0x1800154e0  jnz     loc_1800155F4
0x1800154e6  lea     rdx, ds:0[r13*2]
0x1800154ee  add     rdx, r13
0x1800154f1  shl     rdx, 4
0x1800154f5  add     rdx, [rsi+10h]; struct REGFILTERPINS2 *
0x1800154f9  mov     eax, [rdx]
0x1800154fb  test    al, 8
0x1800154fd  jnz     short loc_18001556A
0x1800154ff  test    ebx, ebx
0x180015501  jnz     short loc_180015563
0x180015503  cmp     [rsp+88h+arg_48], ebx
0x18001550a  jz      short loc_180015510
0x18001550c  test    al, 2
0x18001550e  jz      short loc_18001555F
0x180015510  movzx   eax, byte ptr [rdi+0Ch]
0x180015514  mov     r8, [rsp+88h+arg_28]; struct _GUID *
0x18001551c  mov     r9d, [rsp+88h+arg_30]; unsigned int
0x180015524  mov     [rsp+88h+var_48], eax; int
0x180015528  movzx   eax, [rsp+88h+arg_10]
0x180015530  mov     [rsp+88h+var_50], 1; int
0x180015538  mov     [rsp+88h+var_58], al; bool
0x18001553c  mov     rax, [rsp+88h+arg_40]
0x180015544  mov     [rsp+88h+var_60], rax; struct _GUID *
0x180015549  mov     rax, [rsp+88h+arg_38]
0x180015551  mov     [rsp+88h+var_68], rax; struct REGPINMEDIUM *
0x180015556  call    ?FindType@CMapperCache@@AEAAHPEBUREGFILTERPINS2@@PEBU_GUID@@KPEBUREGPINMEDIUM@@1_NHH@Z; CMapperCache::FindType(REGFILTERPINS2 const *,_GUID const *,ulong,REGPINMEDIUM const *,_GUID const *,bool,int,int)
0x18001555b  test    eax, eax
0x18001555d  jnz     short loc_180015563
0x18001555f  xor     ebx, ebx
0x180015561  jmp     short loc_1800155BE
0x180015563  mov     ebx, 1
0x180015568  jmp     short loc_1800155BE
0x18001556a  test    r14d, r14d
0x18001556d  jnz     short loc_1800155B8
0x18001556f  movzx   eax, [rsp+88h+arg_10]
0x180015577  mov     r8, [rsp+88h+arg_58]; struct _GUID *
0x18001557f  mov     r9d, [rsp+88h+arg_60]; unsigned int
0x180015587  mov     [rsp+88h+var_48], r14d; int
0x18001558c  mov     [rsp+88h+var_50], r14d; int
0x180015591  mov     [rsp+88h+var_58], al; bool
0x180015595  mov     rax, [rsp+88h+arg_70]
0x18001559d  mov     [rsp+88h+var_60], rax; struct _GUID *
0x1800155a2  mov     rax, [rsp+88h+arg_68]
0x1800155aa  mov     [rsp+88h+var_68], rax; struct REGPINMEDIUM *
0x1800155af  call    ?FindType@CMapperCache@@AEAAHPEBUREGFILTERPINS2@@PEBU_GUID@@KPEBUREGPINMEDIUM@@1_NHH@Z; CMapperCache::FindType(REGFILTERPINS2 const *,_GUID const *,ulong,REGPINMEDIUM const *,_GUID const *,bool,int,int)
0x1800155b4  test    eax, eax
0x1800155b6  jz      short loc_1800155BE
0x1800155b8  mov     r14d, 1
0x1800155be  inc     r13d
0x1800155c1  cmp     r13d, ebp
0x1800155c4  jb      loc_1800154D9
0x1800155ca  mov     r13d, [rsp+88h+arg_0]
0x1800155d2  mov     r11d, [rsp+88h+arg_50]
0x1800155da  mov     ebp, [rsp+88h+arg_18]
0x1800155e1  test    ebx, ebx
0x1800155e3  jz      loc_180015412
0x1800155e9  test    r14d, r14d
0x1800155ec  jz      loc_180015412
0x1800155f2  jmp     short loc_180015604
0x1800155f4  mov     r13d, [rsp+88h+arg_0]
0x1800155fc  mov     r11d, [rsp+88h+arg_50]
0x180015604  cmp     qword ptr [r12], 0
0x180015609  jnz     short loc_18001563E
0x18001560b  mov     rcx, [r12+10h]; szUserName
0x180015610  mov     ebp, [rsp+88h+arg_18]
0x180015617  test    rcx, rcx
0x18001561a  jz      loc_180015412
0x180015620  mov     rdx, [r15+50h]; struct IClassFactory *
0x180015624  mov     r8, r12; struct IMoniker **
0x180015627  call    ?ParseDisplayNameHelper@@YAJPEAGPEAUIClassFactory@@PEAPEAUIMoniker@@@Z; ParseDisplayNameHelper(ushort *,IClassFactory *,IMoniker * *)
0x18001562c  mov     r11d, [rsp+88h+arg_50]
0x180015634  mov     r13d, eax
0x180015637  mov     [rsp+88h+arg_0], eax
0x18001563e  mov     ebp, [rsp+88h+arg_18]
0x180015645  test    r13d, r13d
0x180015648  js      loc_180015412
0x18001564e  cmp     [rsp+88h+arg_80], 0
0x180015657  jz      short loc_18001567A
0x180015659  mov     rdx, [rsp+88h+arg_80]; struct _GUID *
0x180015661  mov     rcx, [r12]; struct IMoniker *
0x180015665  call    ?GetMonikerClsid@@YAJPEAUIMoniker@@PEAU_GUID@@@Z; GetMonikerClsid(IMoniker *,_GUID *)
0x18001566a  mov     r11d, [rsp+88h+arg_50]
0x180015672  test    eax, eax
0x180015674  js      loc_180015412
0x18001567a  mov     rax, [rsp+88h+arg_78]
0x180015682  test    rax, rax
0x180015685  jz      short loc_18001569A
0x180015687  mov     rcx, [r12]
0x18001568b  mov     [rax], rcx
0x18001568e  mov     rax, [rcx]
0x180015691  mov     rax, [rax+8]
0x180015695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001569a  mov     rbx, [rsp+88h+arg_88]
0x1800156a2  test    rbx, rbx
0x1800156a5  jz      short loc_180015711
0x1800156a7  mov     rcx, [r12]; struct IMoniker *
0x1800156ab  call    ?MonGetName@@YAPEAGPEAUIMoniker@@@Z; MonGetName(IMoniker *)
0x1800156b0  mov     r11, rax
0x1800156b3  test    rax, rax
0x1800156b6  jz      short loc_180015711
0x1800156b8  mov     r8, rax; unsigned __int16 *
0x1800156bb  mov     edx, 104h; unsigned __int64
0x1800156c0  mov     rcx, rbx; unsigned __int16 *
0x1800156c3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800156c8  mov     rcx, r11; pv
0x1800156cb  mov     ebx, eax
0x1800156cd  call    cs:__imp_CoTaskMemFree
0x1800156d4  nop     dword ptr [rax+rax+00h]
0x1800156d9  test    ebx, ebx
0x1800156db  jns     short loc_180015711
0x1800156dd  mov     rcx, r15; lpCriticalSection
0x1800156e0  call    cs:__imp_LeaveCriticalSection
0x1800156e7  nop     dword ptr [rax+rax+00h]
0x1800156ec  mov     eax, ebx
0x1800156ee  mov     r12, [rsp+88h+var_30]
0x1800156f3  mov     rsi, [rsp+88h+var_28]
0x1800156f8  mov     rbx, [rsp+88h+arg_8]
0x180015700  mov     r14, [rsp+88h+var_38]
0x180015705  add     rsp, 68h
0x180015709  pop     r15
0x18001570b  pop     r13
0x18001570d  pop     rdi
0x18001570e  pop     rbp
0x18001570f  retn
0x180015711  mov     rcx, r15; lpCriticalSection
0x180015714  call    cs:__imp_LeaveCriticalSection
0x18001571b  nop     dword ptr [rax+rax+00h]
0x180015720  xor     eax, eax
0x180015722  jmp     short loc_1800156EE
0x180015724  mov     rcx, r15; lpCriticalSection
0x180015727  call    cs:__imp_LeaveCriticalSection
0x18001572e  nop     dword ptr [rax+rax+00h]
0x180015733  mov     eax, 1
0x180015738  jmp     short loc_1800156EE
0x18001573a  mov     rcx, r15; lpCriticalSection
0x18001573d  call    cs:__imp_LeaveCriticalSection
0x180015744  nop     dword ptr [rax+rax+00h]
0x180015749  mov     eax, 80040203h
0x18001574e  add     rsp, 68h
0x180015752  pop     r15
0x180015754  pop     r13
0x180015756  pop     rdi
0x180015757  pop     rbp
0x180015758  retn
```
