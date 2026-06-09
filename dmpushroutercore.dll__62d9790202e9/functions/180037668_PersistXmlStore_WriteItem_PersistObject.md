# PersistXmlStore::WriteItem(PersistObject *)

- ea: `0x180037668`
- end: `0x180037c20`
- name: `?WriteItem@PersistXmlStore@@AEAAJPEAVPersistObject@@@Z`
- size: `1464`
- prototype: `__int64 __fastcall(PersistXmlStore *__hidden this, struct PersistObject *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180036f3c`

## callees

- `0x1800039f0`
- `0x180003a14`
- `0x1800043a8`
- `0x1800060b4`
- `0x1800064a2`
- `0x180037668`
- `0x18003b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ltow_s` at `0x18003780d`
- `api-ms-win-crt-private-l1-1-0!_o__ltow_s` at `0x1800378e6`
- `api-ms-win-crt-private-l1-1-0!_o__ltow_s` at `0x18003792d`
- `api-ms-win-crt-private-l1-1-0!_o__ltow_s` at `0x18003780d`
- `api-ms-win-crt-private-l1-1-0!_o__ltow_s` at `0x1800378e6`
- `api-ms-win-crt-private-l1-1-0!_o__ltow_s` at `0x18003792d`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1800379e5`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1800379e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037702`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037761`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800377ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003789d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800379c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037a9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037b60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037702`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037761`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800377ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003789d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800379c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037a9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037b60`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800376f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037734`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800377a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037865`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037988`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037a20`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037b16`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800376f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037734`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800377a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037865`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037988`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037a20`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037b16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037aeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037af6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037b91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037bea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037aeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037af6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037b91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037bea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037a65`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037a65`
- `DMCmnUtils!CopyString` at `0x180037b55`
- `DMCmnUtils!CopyString` at `0x180037b55`
- `DMCmnUtils!EncodeBase64W` at `0x180037ab6`
- `DMCmnUtils!EncodeBase64W` at `0x180037ab6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PersistXmlStore::WriteItem(PersistXmlStore *this, struct PersistObject *a2)
{
  PersistXmlStore *v3; // r13
  _DWORD *v4; // r12
  const struct std::nothrow_t *v5; // rdx
  int v6; // ebx
  __int64 *v7; // rsi
  __int64 v8; // rdi
  __int64 v9; // rbx
  unsigned int v10; // edi
  unsigned int v11; // edx
  unsigned int v12; // ecx
  unsigned __int64 v13; // rax
  unsigned int v14; // r8d
  unsigned int v15; // r9d
  unsigned int i; // edx
  unsigned int v17; // eax
  __int64 v18; // rsi
  __int64 v19; // rbx
  int *v20; // rdx
  __int64 v21; // rbx
  unsigned int v22; // esi
  _DWORD *v23; // rdx
  __int64 v24; // rbx
  unsigned __int8 *v25; // rsi
  __int64 v26; // r13
  unsigned __int8 *v27; // rax
  __int64 v28; // rbx
  __int64 v29; // rcx
  unsigned int v31; // [rsp+30h] [rbp-A9h]
  int Value; // [rsp+34h] [rbp-A5h]
  int v33; // [rsp+38h] [rbp-A1h]
  unsigned int v34; // [rsp+3Ch] [rbp-9Dh]
  HLOCAL hMem; // [rsp+40h] [rbp-99h] BYREF
  PersistXmlStore *v36; // [rsp+48h] [rbp-91h]
  HLOCAL v37[2]; // [rsp+50h] [rbp-89h] BYREF
  char v38; // [rsp+60h] [rbp-79h]
  wchar_t Buffer[2]; // [rsp+70h] [rbp-69h] BYREF
  char v40[124]; // [rsp+74h] [rbp-65h] BYREF

  v3 = this;
  v36 = this;
  *(_DWORD *)Buffer = 0;
  memset_0(v40, 0, sizeof(v40));
  hMem = 0;
  v37[0] = 0;
  v4 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, _QWORD))(**((_QWORD **)v3 + 9) + 216LL))(
         *((_QWORD *)v3 + 9),
         0,
         L"item",
         0);
  if ( v6 >= 0 )
  {
    v7 = (__int64 *)*((_QWORD *)v3 + 9);
    v8 = *v7;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
    v9 = *((_QWORD *)a2 + 3);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
    v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, const unsigned __int16 *, _QWORD, __int64))(v8 + 56))(
           v7,
           0,
           L"id",
           0,
           v9);
    if ( v6 >= 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
      v10 = 0;
      if ( *((_DWORD *)a2 + 4) )
      {
        v11 = 0;
        do
        {
          v12 = v10 + 1;
          if ( !*(_QWORD *)(*((_QWORD *)a2 + 1) + 8LL * v11) )
            v12 = v10;
          v10 = v12;
          ++v11;
        }
        while ( v11 < *((_DWORD *)a2 + 4) );
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
      v13 = 4LL * v10;
      if ( !is_mul_ok(v10, 4u) )
        v13 = -1;
      v4 = operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v4 )
      {
        v6 = -2147024882;
        goto LABEL_72;
      }
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
      v14 = 0;
      v15 = 0;
      for ( i = 0; i < *((_DWORD *)a2 + 4); ++i )
      {
        if ( *(_QWORD *)(*((_QWORD *)a2 + 1) + 8LL * i) )
        {
          if ( v10 < ++v14 || v15 >= v10 )
          {
            v6 = -2147024774;
            goto LABEL_19;
          }
          v4[v15++] = i;
        }
      }
      v6 = 0;
      v10 = v14;
LABEL_19:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
      if ( v6 >= 0 )
      {
        _ltow_s(v10, Buffer, 0x40u, 10);
        v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, _QWORD, wchar_t *))(**((_QWORD **)v3 + 9) + 56LL))(
               *((_QWORD *)v3 + 9),
               0,
               L"count",
               0,
               Buffer);
        if ( v6 >= 0 )
        {
          v33 = 0;
          v31 = 0;
          Value = 0;
          v17 = 0;
          v34 = 0;
          if ( !v10 )
          {
LABEL_71:
            v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 9) + 136LL))(*((_QWORD *)v3 + 9));
            goto LABEL_72;
          }
          while ( 1 )
          {
            v18 = v17;
            v19 = (unsigned int)v4[v17];
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
            if ( (unsigned int)v19 < *((_DWORD *)a2 + 4)
              && (_mm_lfence(), (v20 = *(int **)(*((_QWORD *)a2 + 1) + 8 * v19)) != 0) )
            {
              v6 = 0;
              Value = *v20;
            }
            else
            {
              v6 = -2147023728;
            }
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
            if ( v6 < 0 )
              goto LABEL_72;
            v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, _QWORD))(**((_QWORD **)v3 + 9) + 216LL))(
                   *((_QWORD *)v3 + 9),
                   0,
                   L"prop",
                   0);
            if ( v6 < 0 )
              goto LABEL_72;
            _ltow_s(v4[v18], Buffer, 0x40u, 10);
            v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, _QWORD, wchar_t *))(**((_QWORD **)v3 + 9) + 56LL))(
                   *((_QWORD *)v3 + 9),
                   0,
                   L"id",
                   0,
                   Buffer);
            if ( v6 < 0 )
              goto LABEL_72;
            _ltow_s(Value, Buffer, 0x40u, 10);
            v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, _QWORD, wchar_t *))(**((_QWORD **)v3 + 9) + 56LL))(
                   *((_QWORD *)v3 + 9),
                   0,
                   L"regtype",
                   0,
                   Buffer);
            if ( v6 < 0 )
              goto LABEL_72;
            if ( Value == 1 )
            {
              v28 = (unsigned int)v4[v18];
              v37[1] = (char *)a2 + 32;
              EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
              v38 = 1;
              if ( (unsigned int)v28 < *((_DWORD *)a2 + 4)
                && (_mm_lfence(), (v29 = *(_QWORD *)(*((_QWORD *)a2 + 1) + 8 * v28)) != 0) )
              {
                if ( *(_DWORD *)v29 == 1 )
                  v6 = CopyString(*(const unsigned __int16 **)(v29 + 16), 0xFFFFFFFF, (unsigned __int16 **)v37);
                else
                  v6 = -2147024883;
              }
              else
              {
                v6 = -2147023728;
              }
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
              v38 = 0;
              if ( v6 < 0 )
                goto LABEL_72;
              v6 = (*(__int64 (__fastcall **)(_QWORD, HLOCAL))(**((_QWORD **)v3 + 9) + 224LL))(
                     *((_QWORD *)v3 + 9),
                     v37[0]);
              if ( v6 < 0 )
                goto LABEL_72;
              LocalFree(v37[0]);
              v37[0] = 0;
              goto LABEL_69;
            }
            if ( Value == 3 )
            {
              v24 = (unsigned int)v4[v18];
              EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
              if ( (unsigned int)v24 >= *((_DWORD *)a2 + 4) )
              {
                v6 = -2147023728;
                v25 = 0;
                goto LABEL_56;
              }
              _mm_lfence();
              v26 = *(_QWORD *)(*((_QWORD *)a2 + 1) + 8 * v24);
              if ( !v26 )
              {
                v6 = -2147023728;
                goto LABEL_49;
              }
              if ( *(_DWORD *)v26 == 3 )
              {
                v27 = (unsigned __int8 *)LocalAlloc(0x40u, *(unsigned int *)(v26 + 8));
                v25 = v27;
                if ( v27 )
                {
                  v6 = 0;
                  memcpy_0(v27, *(const void **)(v26 + 24), *(unsigned int *)(v26 + 8));
                  v33 = *(_DWORD *)(v26 + 8);
                }
                else
                {
                  v6 = -2147024882;
                }
              }
              else
              {
                v6 = -2147024883;
LABEL_49:
                v25 = 0;
              }
              v3 = v36;
LABEL_56:
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
              if ( v6 < 0 )
                goto LABEL_72;
              v6 = EncodeBase64W(v25, v33, (unsigned __int16 **)&hMem);
              if ( v6 < 0 )
                goto LABEL_72;
              v6 = (*(__int64 (__fastcall **)(_QWORD, HLOCAL))(**((_QWORD **)v3 + 9) + 224LL))(
                     *((_QWORD *)v3 + 9),
                     hMem);
              if ( v6 < 0 )
                goto LABEL_72;
              LocalFree(v25);
              LocalFree(hMem);
              hMem = 0;
              goto LABEL_69;
            }
            if ( Value == 4 )
              break;
LABEL_69:
            v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 9) + 120LL))(*((_QWORD *)v3 + 9));
            if ( v6 < 0 )
              goto LABEL_72;
            v17 = v34 + 1;
            v34 = v17;
            if ( v17 >= v10 )
              goto LABEL_71;
          }
          v21 = (unsigned int)v4[v18];
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
          if ( (unsigned int)v21 < *((_DWORD *)a2 + 4)
            && (_mm_lfence(), (v23 = *(_DWORD **)(*((_QWORD *)a2 + 1) + 8 * v21)) != 0) )
          {
            if ( *v23 == 4 )
            {
              v6 = 0;
              v22 = v23[1];
              v31 = v22;
              goto LABEL_41;
            }
            v6 = -2147024883;
          }
          else
          {
            v6 = -2147023728;
          }
          v22 = v31;
LABEL_41:
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
          if ( v6 < 0 )
            goto LABEL_72;
          if ( (unsigned int)_o__ultow_s(v22, Buffer, 64) )
          {
            v6 = -2147467259;
            goto LABEL_72;
          }
          v6 = (*(__int64 (__fastcall **)(_QWORD, wchar_t *))(**((_QWORD **)v3 + 9) + 224LL))(
                 *((_QWORD *)v3 + 9),
                 Buffer);
          if ( v6 < 0 )
            goto LABEL_72;
          goto LABEL_69;
        }
      }
    }
  }
LABEL_72:
  operator delete(v4, v5);
  LocalFree(hMem);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180037668  mov     [rsp-8+arg_10], rbx
0x18003766d  push    rbp
0x18003766e  push    rsi
0x18003766f  push    rdi
0x180037670  push    r12
0x180037672  push    r13
0x180037674  push    r14
0x180037676  push    r15
0x180037678  lea     rbp, [rsp-27h]
0x18003767d  sub     rsp, 100h
0x180037684  mov     rax, cs:__security_cookie
0x18003768b  xor     rax, rsp
0x18003768e  mov     [rbp+57h+var_40], rax
0x180037692  mov     r14, rdx
0x180037695  mov     r13, rcx
0x180037698  mov     [rsp+130h+var_E8], rcx
0x18003769d  xor     edi, edi
0x18003769f  mov     dword ptr [rbp+57h+Buffer], edi
0x1800376a2  xor     edx, edx; Val
0x1800376a4  lea     r8d, [rdi+7Ch]; Size
0x1800376a8  lea     rcx, [rbp+57h+var_BC]; void *
0x1800376ac  call    memset_0
0x1800376b1  mov     [rsp+130h+hMem], rdi
0x1800376b6  mov     [rsp+130h+var_E0], rdi
0x1800376bb  mov     r12d, edi
0x1800376be  mov     rcx, [r13+48h]
0x1800376c2  mov     rax, [rcx]
0x1800376c5  xor     r9d, r9d
0x1800376c8  lea     r8, aItem; "item"
0x1800376cf  xor     edx, edx
0x1800376d1  mov     rax, [rax+0D8h]
0x1800376d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376dd  mov     ebx, eax
0x1800376df  test    eax, eax
0x1800376e1  js      loc_180037BDD
0x1800376e7  mov     rsi, [r13+48h]
0x1800376eb  mov     rdi, [rsi]
0x1800376ee  lea     r15, [r14+20h]
0x1800376f2  mov     rcx, r15; lpCriticalSection
0x1800376f5  call    cs:__imp_EnterCriticalSection
0x1800376fb  mov     rbx, [r14+18h]
0x1800376ff  mov     rcx, r15; lpCriticalSection
0x180037702  call    cs:__imp_LeaveCriticalSection
0x180037708  mov     [rsp+130h+var_110], rbx
0x18003770d  xor     r9d, r9d
0x180037710  lea     r8, aId; "id"
0x180037717  xor     edx, edx
0x180037719  mov     rcx, rsi
0x18003771c  mov     rax, [rdi+38h]
0x180037720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037725  mov     ebx, eax
0x180037727  xor     esi, esi
0x180037729  test    eax, eax
0x18003772b  js      loc_180037BDD
0x180037731  mov     rcx, r15; lpCriticalSection
0x180037734  call    cs:__imp_EnterCriticalSection
0x18003773a  mov     edi, esi
0x18003773c  cmp     [r14+10h], esi
0x180037740  jbe     short loc_18003775E
0x180037742  mov     edx, esi
0x180037744  mov     r8, [r14+8]
0x180037748  mov     eax, edx
0x18003774a  lea     ecx, [rdi+1]
0x18003774d  cmp     [r8+rax*8], rsi
0x180037751  cmovz   ecx, edi
0x180037754  mov     edi, ecx
0x180037756  inc     edx
0x180037758  cmp     edx, [r14+10h]
0x18003775c  jb      short loc_180037748
0x18003775e  mov     rcx, r15; lpCriticalSection
0x180037761  call    cs:__imp_LeaveCriticalSection
0x180037767  mov     ecx, edi
0x180037769  mov     eax, 4
0x18003776e  mul     rcx
0x180037771  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180037778  cmovb   rax, rcx
0x18003777c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180037783  mov     rcx, rax; unsigned __int64
0x180037786  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003778b  mov     r12, rax
0x18003778e  test    rax, rax
0x180037791  jnz     short loc_18003779D
0x180037793  mov     ebx, 8007000Eh
0x180037798  jmp     loc_180037BDD
0x18003779d  mov     rcx, r15; lpCriticalSection
0x1800377a0  call    cs:__imp_EnterCriticalSection
0x1800377a6  mov     r8d, esi
0x1800377a9  mov     r9d, esi
0x1800377ac  mov     edx, esi
0x1800377ae  cmp     [r14+10h], esi
0x1800377b2  jbe     short loc_1800377E7
0x1800377b4  mov     ecx, edx
0x1800377b6  mov     rax, [r14+8]
0x1800377ba  cmp     [rax+rcx*8], rsi
0x1800377be  jz      short loc_1800377DF
0x1800377c0  inc     r8d
0x1800377c3  cmp     edi, r8d
0x1800377c6  jb      loc_180037878
0x1800377cc  cmp     r9d, edi
0x1800377cf  jnb     loc_180037878
0x1800377d5  mov     eax, r9d
0x1800377d8  mov     [r12+rax*4], edx
0x1800377dc  inc     r9d
0x1800377df  inc     edx
0x1800377e1  cmp     edx, [r14+10h]
0x1800377e5  jb      short loc_1800377B4
0x1800377e7  mov     ebx, esi
0x1800377e9  mov     edi, r8d
0x1800377ec  mov     rcx, r15; lpCriticalSection
0x1800377ef  call    cs:__imp_LeaveCriticalSection
0x1800377f5  test    ebx, ebx
0x1800377f7  js      loc_180037BDD
0x1800377fd  mov     r9d, 0Ah; Radix
0x180037803  lea     r8d, [r9+36h]; BufferCount
0x180037807  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18003780b  mov     ecx, edi; Value
0x18003780d  call    cs:__imp__ltow_s
0x180037813  mov     rcx, [r13+48h]
0x180037817  mov     rax, [rcx]
0x18003781a  lea     rdx, [rbp+57h+Buffer]
0x18003781e  mov     [rsp+130h+var_110], rdx
0x180037823  xor     r9d, r9d
0x180037826  lea     r8, aCount; "count"
0x18003782d  xor     edx, edx
0x18003782f  mov     rax, [rax+38h]
0x180037833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037838  mov     ebx, eax
0x18003783a  test    eax, eax
0x18003783c  js      loc_180037BDD
0x180037842  mov     [rsp+130h+var_F8], esi
0x180037846  mov     [rsp+130h+var_100], esi
0x18003784a  mov     [rsp+130h+Value], esi
0x18003784e  mov     eax, esi
0x180037850  mov     [rsp+130h+var_F4], eax
0x180037854  test    edi, edi
0x180037856  jz      loc_180037BC8
0x18003785c  mov     esi, eax
0x18003785e  mov     ebx, [r12+rsi*4]
0x180037862  mov     rcx, r15; lpCriticalSection
0x180037865  call    cs:__imp_EnterCriticalSection
0x18003786b  cmp     ebx, [r14+10h]
0x18003786f  jb      short loc_180037882
0x180037871  mov     ebx, 80070490h
0x180037876  jmp     short loc_18003789A
0x180037878  mov     ebx, 8007007Ah
0x18003787d  jmp     loc_1800377EC
0x180037882  lfence
0x180037885  mov     rax, [r14+8]
0x180037889  mov     rdx, [rax+rbx*8]
0x18003788d  test    rdx, rdx
0x180037890  jz      short loc_180037871
0x180037892  xor     ebx, ebx
0x180037894  mov     eax, [rdx]
0x180037896  mov     [rsp+130h+Value], eax
0x18003789a  mov     rcx, r15; lpCriticalSection
0x18003789d  call    cs:__imp_LeaveCriticalSection
0x1800378a3  test    ebx, ebx
0x1800378a5  js      loc_180037BDD
0x1800378ab  mov     rcx, [r13+48h]
0x1800378af  mov     rax, [rcx]
0x1800378b2  xor     r9d, r9d
0x1800378b5  lea     r8, aProp; "prop"
0x1800378bc  xor     edx, edx
0x1800378be  mov     rax, [rax+0D8h]
0x1800378c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800378ca  mov     ebx, eax
0x1800378cc  test    eax, eax
0x1800378ce  js      loc_180037BDD
0x1800378d4  mov     r9d, 0Ah; Radix
0x1800378da  lea     r8d, [r9+36h]; BufferCount
0x1800378de  lea     rdx, [rbp+57h+Buffer]; Buffer
0x1800378e2  mov     ecx, [r12+rsi*4]; Value
0x1800378e6  call    cs:__imp__ltow_s
0x1800378ec  mov     rcx, [r13+48h]
0x1800378f0  mov     rax, [rcx]
0x1800378f3  lea     rdx, [rbp+57h+Buffer]
0x1800378f7  mov     [rsp+130h+var_110], rdx
0x1800378fc  xor     r9d, r9d
0x1800378ff  lea     r8, aId; "id"
0x180037906  xor     edx, edx
0x180037908  mov     rax, [rax+38h]
0x18003790c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037911  mov     ebx, eax
0x180037913  test    eax, eax
0x180037915  js      loc_180037BDD
0x18003791b  mov     r9d, 0Ah; Radix
0x180037921  lea     r8d, [r9+36h]; BufferCount
0x180037925  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180037929  mov     ecx, [rsp+130h+Value]; Value
0x18003792d  call    cs:__imp__ltow_s
0x180037933  mov     rcx, [r13+48h]
0x180037937  mov     rax, [rcx]
0x18003793a  lea     rdx, [rbp+57h+Buffer]
0x18003793e  mov     [rsp+130h+var_110], rdx
0x180037943  xor     r9d, r9d
0x180037946  lea     r8, aRegtype; "regtype"
0x18003794d  xor     edx, edx
0x18003794f  mov     rax, [rax+38h]
0x180037953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037958  mov     ebx, eax
0x18003795a  test    eax, eax
0x18003795c  js      loc_180037BDD
0x180037962  mov     eax, [rsp+130h+Value]
0x180037966  sub     eax, 1
0x180037969  jz      loc_180037B0A
0x18003796f  sub     eax, 2
0x180037972  jz      loc_180037A19
0x180037978  cmp     eax, 1
0x18003797b  jnz     loc_180037BA0
0x180037981  mov     ebx, [r12+rsi*4]
0x180037985  mov     rcx, r15; lpCriticalSection
0x180037988  call    cs:__imp_EnterCriticalSection
0x18003798e  cmp     ebx, [r14+10h]
0x180037992  jb      short loc_18003799F
0x180037994  mov     ebx, 80070490h
0x180037999  mov     esi, [rsp+130h+var_100]
0x18003799d  jmp     short loc_1800379C4
0x18003799f  lfence
0x1800379a2  mov     rax, [r14+8]
0x1800379a6  mov     rdx, [rax+rbx*8]
0x1800379aa  test    rdx, rdx
0x1800379ad  jz      short loc_180037994
0x1800379af  cmp     dword ptr [rdx], 4
0x1800379b2  jz      short loc_1800379BB
0x1800379b4  mov     ebx, 8007000Dh
0x1800379b9  jmp     short loc_180037999
0x1800379bb  xor     ebx, ebx
0x1800379bd  mov     esi, [rdx+4]
0x1800379c0  mov     [rsp+130h+var_100], esi
0x1800379c4  mov     rcx, r15; lpCriticalSection
0x1800379c7  call    cs:__imp_LeaveCriticalSection
0x1800379cd  test    ebx, ebx
0x1800379cf  js      loc_180037BDD
0x1800379d5  mov     r9d, 0Ah
0x1800379db  lea     r8d, [r9+36h]
0x1800379df  lea     rdx, [rbp+57h+Buffer]
0x1800379e3  mov     ecx, esi
0x1800379e5  call    cs:__imp__o__ultow_s
0x1800379eb  test    eax, eax
0x1800379ed  jnz     loc_180037C19
0x1800379f3  mov     rcx, [r13+48h]
0x1800379f7  mov     rax, [rcx]
0x1800379fa  lea     rdx, [rbp+57h+Buffer]
0x1800379fe  mov     rax, [rax+0E0h]
0x180037a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a0a  mov     ebx, eax
0x180037a0c  test    eax, eax
0x180037a0e  js      loc_180037BDD
0x180037a14  jmp     loc_180037BA0
0x180037a19  mov     ebx, [r12+rsi*4]
0x180037a1d  mov     rcx, r15; lpCriticalSection
0x180037a20  call    cs:__imp_EnterCriticalSection
0x180037a26  cmp     ebx, [r14+10h]
0x180037a2a  jb      short loc_180037A35
0x180037a2c  mov     ebx, 80070490h
0x180037a31  xor     esi, esi
0x180037a33  jmp     short loc_180037A99
0x180037a35  lfence
0x180037a38  mov     rax, [r14+8]
0x180037a3c  mov     r13, [rax+rbx*8]
0x180037a40  test    r13, r13
0x180037a43  jnz     short loc_180037A4E
0x180037a45  mov     ebx, 80070490h
0x180037a4a  xor     esi, esi
0x180037a4c  jmp     short loc_180037A94
0x180037a4e  cmp     dword ptr [r13+0], 3
0x180037a53  jz      short loc_180037A5C
0x180037a55  mov     ebx, 8007000Dh
0x180037a5a  jmp     short loc_180037A4A
0x180037a5c  mov     edx, [r13+8]; uBytes
0x180037a60  mov     ecx, 40h ; '@'; uFlags
0x180037a65  call    cs:__imp_LocalAlloc
0x180037a6b  mov     rsi, rax
0x180037a6e  test    rax, rax
0x180037a71  jnz     short loc_180037A7A
0x180037a73  mov     ebx, 8007000Eh
0x180037a78  jmp     short loc_180037A94
0x180037a7a  xor     ebx, ebx
0x180037a7c  mov     r8d, [r13+8]; Size
0x180037a80  mov     rdx, [r13+18h]; Src
0x180037a84  mov     rcx, rax; void *
0x180037a87  call    memcpy_0
0x180037a8c  mov     eax, [r13+8]
0x180037a90  mov     [rsp+130h+var_F8], eax
0x180037a94  mov     r13, [rsp+130h+var_E8]
0x180037a99  mov     rcx, r15; lpCriticalSection
0x180037a9c  call    cs:__imp_LeaveCriticalSection
0x180037aa2  test    ebx, ebx
0x180037aa4  js      loc_180037BDD
0x180037aaa  lea     r8, [rsp+130h+hMem]
0x180037aaf  mov     edx, [rsp+130h+var_F8]
0x180037ab3  mov     rcx, rsi
0x180037ab6  call    cs:__imp_?EncodeBase64W@@YAJPEBEHPEAPEAG@Z; EncodeBase64W(uchar const *,int,ushort * *)
0x180037abc  mov     ebx, eax
0x180037abe  test    eax, eax
0x180037ac0  js      loc_180037BDD
0x180037ac6  mov     rcx, [r13+48h]
0x180037aca  mov     rax, [rcx]
0x180037acd  mov     rdx, [rsp+130h+hMem]
0x180037ad2  mov     rax, [rax+0E0h]
  ... truncated ...
```
