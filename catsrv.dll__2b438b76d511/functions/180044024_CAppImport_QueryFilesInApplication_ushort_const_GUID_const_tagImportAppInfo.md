# CAppImport::QueryFilesInApplication(ushort const *,_GUID const &,tagImportAppInfo *)

- ea: `0x180044024`
- end: `0x18004438a`
- name: `?QueryFilesInApplication@CAppImport@@AEAAJPEBGAEBU_GUID@@PEAUtagImportAppInfo@@@Z`
- size: `870`
- prototype: `int(CAppImport *__hidden this, const unsigned __int16 *, const struct _GUID *, struct tagImportAppInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180043b4c`

## callees

- `0x18000a01c`
- `0x18001a6c8`
- `0x180044024`
- `0x180055502`
- `0x18005551a`
- `0x180058010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800442bd`
- `msvcrt!wcsrchr` at `0x1800442bd`
- `CLBCatQ!GetSimpleTableDispenser` at `0x1800440b6`
- `CLBCatQ!GetSimpleTableDispenser` at `0x1800440b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044351`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044362`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044351`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044362`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800441df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180044279`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800442e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800441df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180044279`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800442e5`

## pseudocode

```c
__int64 __fastcall CAppImport::QueryFilesInApplication(
        CAppImport *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        struct tagImportAppInfo *a4)
{
  int v7; // eax
  __int64 v8; // r8
  int SimpleTableDispenser; // eax
  bool v10; // zf
  int v11; // eax
  int v12; // ebx
  __int64 v13; // rax
  unsigned __int64 v14; // rax
  size_t v15; // rbx
  void *v16; // rax
  __int64 v17; // rsi
  unsigned int i; // r14d
  __int64 v19; // rax
  unsigned __int64 v20; // rbx
  unsigned __int16 *v21; // rcx
  wchar_t *v22; // rax
  const unsigned __int16 *v23; // rbx
  unsigned __int64 v24; // rsi
  unsigned __int16 *v25; // rcx
  unsigned int v26; // esi
  int v28; // [rsp+50h] [rbp-19h] BYREF
  __int64 v29; // [rsp+58h] [rbp-11h] BYREF
  signed __int64 v30; // [rsp+60h] [rbp-9h] BYREF
  unsigned __int16 *v31; // [rsp+68h] [rbp-1h] BYREF
  const unsigned __int16 *v32; // [rsp+70h] [rbp+7h] BYREF
  int v33; // [rsp+78h] [rbp+Fh]
  int v34; // [rsp+7Ch] [rbp+13h]
  int v35; // [rsp+80h] [rbp+17h]
  int v36; // [rsp+84h] [rbp+1Bh]
  __int64 v37; // [rsp+88h] [rbp+1Fh]
  __int64 v38; // [rsp+90h] [rbp+27h]
  int v39; // [rsp+98h] [rbp+2Fh]
  int v40; // [rsp+9Ch] [rbp+33h]
  unsigned int v41; // [rsp+D8h] [rbp+6Fh] BYREF
  int v42; // [rsp+E0h] [rbp+77h] BYREF

  v32 = a2;
  v41 = 0;
  v28 = 0;
  v42 = 0;
  v31 = 0;
  v33 = 0;
  v34 = -268435455;
  v35 = 130;
  v7 = safe_lstrlenW(a2);
  v37 = v8;
  v38 = 0;
  v39 = 72;
  v40 = 16;
  v36 = 2 * v7 + 2;
  v29 = 0;
  if ( !*((_QWORD *)this + 9) )
  {
    v30 = 0;
    SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v30);
    v10 = SimpleTableDispenser == 0;
    if ( SimpleTableDispenser < 0 )
      goto LABEL_6;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 9, v30, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  v11 = memcmp_0(tidCOMSERVICES_DLLNAMES_EXPORT, &TID_APPLICATION, 0x10u);
  v10 = (*(unsigned int (__fastcall **)(_QWORD, __int64 *, __int64 *, const unsigned __int16 **, __int64, int, int, __int64 *))(**((_QWORD **)this + 9) + 24LL))(
          *((_QWORD *)this + 9),
          didCOMSERVICES,
          tidCOMSERVICES_DLLNAMES_EXPORT,
          &v32,
          2,
          1,
          v11 != 0 ? 7 : 5,
          &v29) == 0;
LABEL_6:
  if ( !v10 )
  {
    v12 = -2146368504;
    goto LABEL_33;
  }
  if ( !v29 )
  {
    v12 = -2147024882;
LABEL_36:
    if ( *((_QWORD *)a4 + 4) )
    {
      v26 = 0;
      do
        CoTaskMemFree(*(LPVOID *)(*((_QWORD *)a4 + 4) + 8LL * v26++));
      while ( v26 <= v41 );
      CoTaskMemFree(*((LPVOID *)a4 + 4));
      *((_QWORD *)a4 + 4) = 0;
    }
    return (unsigned int)v12;
  }
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 24LL))(v29);
  if ( v12 >= 0 )
  {
    v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *, _QWORD))(*(_QWORD *)v29 + 72LL))(
            v29,
            0,
            0,
            0,
            0,
            0,
            0,
            &v41,
            0);
    if ( v12 >= 0 )
    {
      v13 = v41 + 1;
      if ( v41 == -1 )
      {
        *((_DWORD *)a4 + 7) = -1;
      }
      else
      {
        *((_DWORD *)a4 + 7) = v13;
        v14 = 8 * v13;
        if ( v14 <= 0xFFFFFFFF )
        {
          v15 = (unsigned int)v14;
          v16 = CoTaskMemAlloc((unsigned int)v14);
          *((_QWORD *)a4 + 4) = v16;
          if ( !v16 )
            goto LABEL_15;
          memset_0(v16, 0, v15);
          v17 = -1;
          for ( i = 0; i < v41; ++i )
          {
            v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 40LL))(v29);
            if ( v12 < 0 )
              goto LABEL_33;
            v12 = (*(__int64 (__fastcall **)(__int64, __int64, int *, int *, unsigned __int16 **))(*(_QWORD *)v29 + 64LL))(
                    v29,
                    1,
                    &v28,
                    &v42,
                    &v31);
            if ( v12 < 0 )
              goto LABEL_33;
            v19 = -1;
            do
              ++v19;
            while ( v31[v19] );
            v20 = v19 + 1;
            *(_QWORD *)(*((_QWORD *)a4 + 4) + 8LL * i) = CoTaskMemAlloc(2 * (v19 + 1));
            v21 = *(unsigned __int16 **)(*((_QWORD *)a4 + 4) + 8LL * i);
            if ( !v21 )
              goto LABEL_15;
            v12 = StringCchCopyW(v21, v20, v31);
            if ( v12 < 0 )
              goto LABEL_33;
          }
          v22 = wcsrchr(a2, 0x5Cu);
          v23 = v22 ? v22 + 1 : a2;
          do
            ++v17;
          while ( v23[v17] );
          v24 = v17 + 1;
          *(_QWORD *)(*((_QWORD *)a4 + 4) + 8LL * v41) = CoTaskMemAlloc(2 * v24);
          v25 = *(unsigned __int16 **)(*((_QWORD *)a4 + 4) + 8LL * v41);
          if ( v25 )
            v12 = StringCchCopyW(v25, v24, v23);
          else
LABEL_15:
            v12 = -2147024882;
          goto LABEL_33;
        }
      }
      v12 = -2147024362;
    }
  }
LABEL_33:
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  if ( v12 < 0 )
    goto LABEL_36;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180044024  mov     [rsp-8+arg_0], rbx
0x180044029  mov     [rsp-8+arg_18], rsi
0x18004402e  push    rbp
0x18004402f  push    rdi
0x180044030  push    r12
0x180044032  push    r14
0x180044034  push    r15
0x180044036  lea     rbp, [rsp-37h]
0x18004403b  sub     rsp, 0A0h
0x180044042  xor     r12d, r12d
0x180044045  mov     [rbp+57h+var_50], rdx
0x180044049  mov     rbx, rcx
0x18004404c  mov     [rbp+57h+arg_8], r12d
0x180044050  mov     rcx, rdx; unsigned __int16 *
0x180044053  mov     [rbp+57h+var_70], r12d
0x180044057  mov     [rbp+57h+arg_10], r12d
0x18004405b  mov     rdi, r9
0x18004405e  mov     [rbp+57h+var_58], r12
0x180044062  mov     r15, rdx
0x180044065  mov     [rbp+57h+var_48], r12d
0x180044069  mov     [rbp+57h+var_44], 0F0000001h
0x180044070  mov     [rbp+57h+var_40], 82h
0x180044077  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004407c  lea     esi, [r12+10h]
0x180044081  mov     [rbp+57h+var_38], r8
0x180044085  mov     [rbp+57h+var_30], r12
0x180044089  mov     [rbp+57h+var_28], 48h ; 'H'
0x180044090  lea     eax, ds:2[rax*2]
0x180044097  mov     [rbp+57h+var_24], esi
0x18004409a  mov     [rbp+57h+var_3C], eax
0x18004409d  mov     [rbp+57h+var_68], r12
0x1800440a1  cmp     [rbx+48h], r12
0x1800440a5  jnz     short loc_1800440E2
0x1800440a7  lea     rdx, [rbp+57h+var_60]
0x1800440ab  mov     [rbp+57h+var_60], r12
0x1800440af  lea     rcx, IID_ISimpleTableDispenser
0x1800440b6  call    cs:__imp_GetSimpleTableDispenser
0x1800440bc  test    eax, eax
0x1800440be  js      loc_180044144
0x1800440c4  mov     rcx, [rbp+57h+var_60]
0x1800440c8  xor     eax, eax
0x1800440ca  lock cmpxchg [rbx+48h], rcx
0x1800440d0  jz      short loc_1800440E2
0x1800440d2  mov     rcx, [rbp+57h+var_60]
0x1800440d6  mov     rax, [rcx]
0x1800440d9  mov     rax, [rax+10h]
0x1800440dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800440e2  mov     r8, rsi; Size
0x1800440e5  lea     rdx, TID_APPLICATION; Buf2
0x1800440ec  lea     rcx, tidCOMSERVICES_DLLNAMES_EXPORT; Buf1
0x1800440f3  call    memcmp_0
0x1800440f8  mov     rcx, [rbx+48h]
0x1800440fc  lea     r9, [rbp+57h+var_68]
0x180044100  mov     [rsp+0C0h+var_88], r9
0x180044105  lea     r8, tidCOMSERVICES_DLLNAMES_EXPORT
0x18004410c  neg     eax
0x18004410e  lea     r9, [rbp+57h+var_50]
0x180044112  mov     rax, [rcx]
0x180044115  sbb     edx, edx
0x180044117  and     edx, 2
0x18004411a  add     edx, 5
0x18004411d  mov     dword ptr [rsp+0C0h+var_90], edx
0x180044121  lea     rdx, didCOMSERVICES
0x180044128  mov     rax, [rax+18h]
0x18004412c  mov     dword ptr [rsp+0C0h+var_98], 1
0x180044134  mov     [rsp+0C0h+var_A0], 2
0x18004413d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044142  test    eax, eax
0x180044144  jz      short loc_180044150
0x180044146  mov     ebx, 80110408h
0x18004414b  jmp     loc_180044325
0x180044150  mov     rcx, [rbp+57h+var_68]
0x180044154  test    rcx, rcx
0x180044157  jnz     short loc_180044163
0x180044159  mov     ebx, 8007000Eh
0x18004415e  jmp     loc_18004433E
0x180044163  mov     rax, [rcx]
0x180044166  mov     rax, [rax+18h]
0x18004416a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004416f  mov     ebx, eax
0x180044171  test    eax, eax
0x180044173  js      loc_180044325
0x180044179  mov     rcx, [rbp+57h+var_68]
0x18004417d  lea     rdx, [rbp+57h+arg_8]
0x180044181  mov     [rsp+0C0h+var_80], r12
0x180044186  xor     r9d, r9d
0x180044189  mov     [rsp+0C0h+var_88], rdx
0x18004418e  xor     r8d, r8d
0x180044191  mov     [rsp+0C0h+var_90], r12
0x180044196  xor     edx, edx
0x180044198  mov     rax, [rcx]
0x18004419b  mov     [rsp+0C0h+var_98], r12
0x1800441a0  mov     [rsp+0C0h+var_A0], r12
0x1800441a5  mov     rax, [rax+48h]
0x1800441a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800441ae  mov     ebx, eax
0x1800441b0  test    eax, eax
0x1800441b2  js      loc_180044325
0x1800441b8  mov     eax, [rbp+57h+arg_8]
0x1800441bb  inc     eax
0x1800441bd  cmp     eax, 1
0x1800441c0  jb      loc_180044319
0x1800441c6  mov     [rdi+1Ch], eax
0x1800441c9  mov     ecx, 0FFFFFFFFh
0x1800441ce  shl     rax, 3
0x1800441d2  cmp     rax, rcx
0x1800441d5  ja      loc_180044320
0x1800441db  mov     ecx, eax; cb
0x1800441dd  mov     ebx, eax
0x1800441df  call    cs:__imp_CoTaskMemAlloc
0x1800441e5  mov     [rdi+20h], rax
0x1800441e9  test    rax, rax
0x1800441ec  jnz     short loc_1800441F8
0x1800441ee  mov     ebx, 8007000Eh
0x1800441f3  jmp     loc_180044325
0x1800441f8  mov     r8, rbx; Size
0x1800441fb  xor     edx, edx; Val
0x1800441fd  mov     rcx, rax; void *
0x180044200  call    memset_0
0x180044205  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180044209  mov     r14d, r12d
0x18004420c  cmp     r14d, [rbp+57h+arg_8]
0x180044210  jnb     loc_1800442B5
0x180044216  mov     rcx, [rbp+57h+var_68]
0x18004421a  mov     rax, [rcx]
0x18004421d  mov     rax, [rax+28h]
0x180044221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044226  mov     ebx, eax
0x180044228  test    eax, eax
0x18004422a  js      loc_180044325
0x180044230  mov     rcx, [rbp+57h+var_68]
0x180044234  lea     rdx, [rbp+57h+var_58]
0x180044238  mov     [rsp+0C0h+var_A0], rdx
0x18004423d  lea     r9, [rbp+57h+arg_10]
0x180044241  lea     r8, [rbp+57h+var_70]
0x180044245  mov     edx, 1
0x18004424a  mov     rax, [rcx]
0x18004424d  mov     rax, [rax+40h]
0x180044251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044256  mov     ebx, eax
0x180044258  test    eax, eax
0x18004425a  js      loc_180044325
0x180044260  mov     rcx, [rbp+57h+var_58]
0x180044264  mov     rax, rsi
0x180044267  inc     rax
0x18004426a  cmp     [rcx+rax*2], r12w
0x18004426f  jnz     short loc_180044267
0x180044271  lea     rbx, [rax+1]
0x180044275  lea     rcx, [rbx+rbx]; cb
0x180044279  call    cs:__imp_CoTaskMemAlloc
0x18004427f  mov     rcx, [rdi+20h]
0x180044283  mov     r8d, r14d
0x180044286  mov     [rcx+r8*8], rax
0x18004428a  mov     rax, [rdi+20h]
0x18004428e  mov     rcx, [rax+r8*8]; unsigned __int16 *
0x180044292  test    rcx, rcx
0x180044295  jz      loc_1800441EE
0x18004429b  mov     r8, [rbp+57h+var_58]; unsigned __int16 *
0x18004429f  mov     rdx, rbx; unsigned __int64
0x1800442a2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800442a7  mov     ebx, eax
0x1800442a9  test    eax, eax
0x1800442ab  js      short loc_180044325
0x1800442ad  inc     r14d
0x1800442b0  jmp     loc_18004420C
0x1800442b5  mov     edx, 5Ch ; '\'; Ch
0x1800442ba  mov     rcx, r15; Str
0x1800442bd  call    cs:__imp_wcsrchr
0x1800442c3  mov     rbx, rax
0x1800442c6  test    rax, rax
0x1800442c9  jnz     short loc_1800442D0
0x1800442cb  mov     rbx, r15
0x1800442ce  jmp     short loc_1800442D4
0x1800442d0  add     rbx, 2
0x1800442d4  inc     rsi
0x1800442d7  cmp     [rbx+rsi*2], r12w
0x1800442dc  jnz     short loc_1800442D4
0x1800442de  inc     rsi
0x1800442e1  lea     rcx, [rsi+rsi]; cb
0x1800442e5  call    cs:__imp_CoTaskMemAlloc
0x1800442eb  mov     rcx, [rdi+20h]
0x1800442ef  mov     edx, [rbp+57h+arg_8]
0x1800442f2  mov     [rcx+rdx*8], rax
0x1800442f6  mov     ecx, [rbp+57h+arg_8]
0x1800442f9  mov     rax, [rdi+20h]
0x1800442fd  mov     rcx, [rax+rcx*8]; unsigned __int16 *
0x180044301  test    rcx, rcx
0x180044304  jz      loc_1800441EE
0x18004430a  mov     r8, rbx; unsigned __int16 *
0x18004430d  mov     rdx, rsi; unsigned __int64
0x180044310  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180044315  mov     ebx, eax
0x180044317  jmp     short loc_180044325
0x180044319  mov     dword ptr [rdi+1Ch], 0FFFFFFFFh
0x180044320  mov     ebx, 80070216h
0x180044325  mov     rcx, [rbp+57h+var_68]
0x180044329  test    rcx, rcx
0x18004432c  jz      short loc_18004433A
0x18004432e  mov     rax, [rcx]
0x180044331  mov     rax, [rax+10h]
0x180044335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004433a  test    ebx, ebx
0x18004433c  jns     short loc_18004436C
0x18004433e  cmp     [rdi+20h], r12
0x180044342  jz      short loc_18004436C
0x180044344  mov     esi, r12d
0x180044347  mov     rcx, [rdi+20h]
0x18004434b  mov     eax, esi
0x18004434d  mov     rcx, [rcx+rax*8]; pv
0x180044351  call    cs:__imp_CoTaskMemFree
0x180044357  inc     esi
0x180044359  cmp     esi, [rbp+57h+arg_8]
0x18004435c  jbe     short loc_180044347
0x18004435e  mov     rcx, [rdi+20h]; pv
0x180044362  call    cs:__imp_CoTaskMemFree
0x180044368  mov     [rdi+20h], r12
0x18004436c  lea     r11, [rsp+0C0h+var_20]
0x180044374  mov     eax, ebx
0x180044376  mov     rbx, [r11+30h]
0x18004437a  mov     rsi, [r11+48h]
0x18004437e  mov     rsp, r11
0x180044381  pop     r15
0x180044383  pop     r14
0x180044385  pop     r12
0x180044387  pop     rdi
0x180044388  pop     rbp
0x180044389  retn
```
