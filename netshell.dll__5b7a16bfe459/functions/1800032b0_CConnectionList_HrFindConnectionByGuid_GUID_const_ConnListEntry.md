# CConnectionList::HrFindConnectionByGuid(_GUID const *,ConnListEntry &)

- ea: `0x1800032b0`
- end: `0x1800036ed`
- name: `?HrFindConnectionByGuid@CConnectionList@@QEAAJPEFBU_GUID@@AEAVConnListEntry@@@Z`
- size: `1085`
- prototype: `__int64 __fastcall(CConnectionList *__hidden this, const struct _GUID *, struct ConnListEntry *)`
- caller_count: `19`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800030e0`
- `0x180003770`
- `0x180004f10`
- `0x180008060`
- `0x180009388`
- `0x180015864`
- `0x180016bfc`
- `0x180018f74`
- `0x18001d0bc`
- `0x18001d188`
- `0x180041fb4`
- `0x18004205c`
- `0x1800421c0`
- `0x180042294`
- `0x1800426a4`
- `0x180048470`
- `0x18004abf0`
- `0x18004ae40`
- `0x18004b060`

## callees

- `0x180002930`
- `0x1800032b0`
- `0x180004920`
- `0x180062124`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000366e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800036cc`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000366e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800036cc`
- `SHELL32!__imp_SHFree` at `0x18000341a`
- `SHELL32!__imp_SHFree` at `0x18000342d`
- `SHELL32!__imp_SHFree` at `0x18000359f`
- `SHELL32!__imp_SHFree` at `0x1800035b8`
- `SHELL32!__imp_SHFree` at `0x1800035c7`
- `SHELL32!__imp_SHFree` at `0x18000341a`
- `SHELL32!__imp_SHFree` at `0x18000342d`
- `SHELL32!__imp_SHFree` at `0x18000359f`
- `SHELL32!__imp_SHFree` at `0x1800035b8`
- `SHELL32!__imp_SHFree` at `0x1800035c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000336e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000336e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800032e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800032e4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800034c6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800034c6`
- `ole32!CoTaskMemFree` at `0x1800035d9`
- `ole32!CoTaskMemFree` at `0x1800035ea`
- `ole32!CoTaskMemFree` at `0x1800035f7`
- `ole32!CoTaskMemFree` at `0x18000367b`
- `ole32!CoTaskMemFree` at `0x1800036de`
- `ole32!CoTaskMemFree` at `0x1800035d9`
- `ole32!CoTaskMemFree` at `0x1800035ea`
- `ole32!CoTaskMemFree` at `0x1800035f7`
- `ole32!CoTaskMemFree` at `0x18000367b`
- `ole32!CoTaskMemFree` at `0x1800036de`
- `ole32!CoTaskMemAlloc` at `0x18000360e`
- `ole32!CoTaskMemAlloc` at `0x180003657`
- `ole32!CoTaskMemAlloc` at `0x1800036b0`
- `ole32!CoTaskMemAlloc` at `0x18000360e`
- `ole32!CoTaskMemAlloc` at `0x180003657`
- `ole32!CoTaskMemAlloc` at `0x1800036b0`

## pseudocode

```c
__int64 __fastcall CConnectionList::HrFindConnectionByGuid(
        __int64 **this,
        const struct _GUID *a2,
        struct ConnListEntry *a3)
{
  bool v3; // zf
  struct _RTL_CRITICAL_SECTION *v6; // rbp
  __int64 *v7; // rsi
  __int64 *v8; // rdi
  __int64 *v9; // rbx
  char v10; // cl
  __int64 *v11; // rax
  unsigned int v12; // esi
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx
  LPVOID *v19; // rcx
  _QWORD *v20; // rbx
  LPVOID *v21; // rdi
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  LPVOID *v24; // rax
  __int64 v25; // rsi
  __int64 v26; // rax
  __int64 v27; // rax
  unsigned int v28; // r15d
  LPVOID v29; // rax
  __int64 v30; // rax
  __int64 v31; // rsi
  LPVOID v32; // rax
  __int128 Buf2; // [rsp+80h] [rbp-48h] BYREF
  _OWORD Buf1[3]; // [rsp+90h] [rbp-38h] BYREF

  v3 = *this == 0;
  Buf2 = (__int128)*a2;
  if ( v3 )
    return 1;
  v6 = (struct _RTL_CRITICAL_SECTION *)(this + 2);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 2));
  v7 = (__int64 *)**this;
  HIDWORD(Buf1[0]) = 0;
  v8 = v7;
  v9 = (__int64 *)v7[1];
  if ( !*((_BYTE *)v9 + 25) )
  {
    do
    {
      if ( memcmp_0(v9 + 4, &Buf2, 0x10u) < 0 )
      {
        v10 = 1;
      }
      else
      {
        v10 = 0;
        v8 = v9;
      }
      v11 = v9 + 2;
      if ( !v10 )
        v11 = v9;
      v9 = (__int64 *)*v11;
    }
    while ( !*(_BYTE *)(*v11 + 25) );
  }
  if ( *((_BYTE *)v8 + 25) || memcmp_0(&Buf2, v8 + 4, 0x10u) < 0 || v8 == v7 )
  {
    v12 = 1;
  }
  else
  {
    *((_DWORD *)a3 + 40) = *((_DWORD *)v8 + 52);
    *(_DWORD *)a3 = *((_DWORD *)v8 + 12);
    *((_DWORD *)a3 + 30) = 1;
    Buf2 = *((_OWORD *)v8 + 5);
    if ( !memcmp_0(&Buf2, &GUID_NULL, 0x10u) )
    {
      v14 = (void *)*((_QWORD *)a3 + 9);
      if ( v14 )
      {
        SHFree(v14);
        *((_QWORD *)a3 + 9) = 0;
      }
      v15 = (void *)*((_QWORD *)a3 + 10);
      if ( v15 )
      {
        SHFree(v15);
        *((_QWORD *)a3 + 10) = 0;
      }
      v16 = (void *)*((_QWORD *)a3 + 14);
      if ( v16 )
      {
        SHFree(v16);
        *((_QWORD *)a3 + 14) = 0;
      }
      v17 = (void *)*((_QWORD *)a3 + 11);
      if ( v17 )
      {
        SHFree(v17);
        *((_QWORD *)a3 + 11) = 0;
      }
      v18 = (void *)*((_QWORD *)a3 + 12);
      if ( v18 )
      {
        SHFree(v18);
        *((_QWORD *)a3 + 12) = 0;
        *((_DWORD *)a3 + 26) = 0;
      }
      *((_QWORD *)a3 + 1) = 0;
      *((_DWORD *)a3 + 4) = 0;
      *((_DWORD *)a3 + 16) = 0;
      *((GUID *)a3 + 2) = GUID_NULL;
      *(_QWORD *)((char *)a3 + 20) = 0;
      *((_DWORD *)a3 + 7) = 0;
      *((GUID *)a3 + 3) = GUID_NULL;
    }
    else
    {
      v23 = *((_OWORD *)v8 + 6);
      Buf1[0] = *((_OWORD *)v8 + 5);
      Buf2 = v23;
      CConFoldEntry::clear((struct ConnListEntry *)((char *)a3 + 8));
      if ( (int)CConFoldEntry::HrInitData(
                  (char *)a3 + 8,
                  *((unsigned int *)v8 + 14),
                  *((unsigned int *)v8 + 15),
                  *((unsigned int *)v8 + 16),
                  Buf1,
                  &Buf2,
                  *((_DWORD *)v8 + 28),
                  v8[18],
                  *((_DWORD *)v8 + 38),
                  v8[15],
                  v8[16],
                  v8[20],
                  v8[17],
                  *((_DWORD *)v8 + 17),
                  *((_DWORD *)v8 + 18),
                  *((_DWORD *)v8 + 19)) < 0 )
        CConFoldEntry::clear((struct ConnListEntry *)((char *)a3 + 8));
    }
    v19 = (LPVOID *)*((_QWORD *)a3 + 19);
    if ( v19 )
    {
      CoTaskMemFree(*v19);
      CoTaskMemFree(*(LPVOID *)(*((_QWORD *)a3 + 19) + 8LL));
      CoTaskMemFree(*((LPVOID *)a3 + 19));
      *((_QWORD *)a3 + 19) = 0;
    }
    v20 = (_QWORD *)v8[25];
    if ( v20 )
    {
      v24 = (LPVOID *)CoTaskMemAlloc(0x10u);
      v21 = v24;
      if ( v24 )
      {
        *v24 = 0;
        v25 = -1;
        v24[1] = 0;
        if ( *v20 )
        {
          v26 = -1;
          do
            ++v26;
          while ( *(_WORD *)(*v20 + 2 * v26) );
          v27 = (unsigned int)(v26 + 1);
          if ( (_DWORD)v27 )
          {
            v28 = v27;
            v29 = CoTaskMemAlloc(2 * v27);
            *v21 = v29;
            if ( v29 )
            {
              if ( (unsigned int)_o_wcscpy_s(v29, v28, *v20) )
              {
                CoTaskMemFree(*v21);
                *v21 = 0;
              }
            }
          }
        }
        v30 = v20[1];
        if ( v30 )
        {
          do
            ++v25;
          while ( *(_WORD *)(v30 + 2 * v25) );
          v31 = (unsigned int)(v25 + 1);
          if ( (_DWORD)v31 )
          {
            v32 = CoTaskMemAlloc(2 * v31);
            v21[1] = v32;
            if ( v32 )
            {
              if ( (unsigned int)_o_wcscpy_s(v32, (unsigned int)v31, v20[1]) )
              {
                CoTaskMemFree(v21[1]);
                v21[1] = 0;
              }
            }
          }
        }
      }
    }
    else
    {
      v21 = 0;
    }
    v22 = *((_OWORD *)a3 + 2);
    *((_QWORD *)a3 + 19) = v21;
    Buf1[0] = v22;
    if ( !memcmp_0(Buf1, &GUID_NULL, 0x10u) )
    {
      v12 = -2147024882;
    }
    else
    {
      *((_DWORD *)a3 + 40) = GetTickCount();
      v12 = 0;
    }
  }
  LeaveCriticalSection(v6);
  return v12;
}

```

## disassembly

```asm
0x1800032b0  mov     rax, rsp
0x1800032b3  push    rbx
0x1800032b4  push    rsi
0x1800032b5  push    r14
0x1800032b7  sub     rsp, 0B0h
0x1800032be  cmp     qword ptr [rcx], 0
0x1800032c2  mov     r14, r8
0x1800032c5  movups  xmm0, xmmword ptr [rdx]
0x1800032c8  mov     rbx, rcx
0x1800032cb  movups  xmmword ptr [rax-48h], xmm0
0x1800032cf  jz      loc_1800035AE
0x1800032d5  mov     [rax+8], rbp
0x1800032d9  lea     rbp, [rcx+10h]
0x1800032dd  mov     rcx, rbp; lpCriticalSection
0x1800032e0  mov     [rax+10h], rdi
0x1800032e4  call    cs:__imp_EnterCriticalSection
0x1800032ea  mov     rax, [rbx]
0x1800032ed  mov     rsi, [rax]
0x1800032f0  xor     eax, eax
0x1800032f2  mov     dword ptr [rsp+0C8h+Buf1+0Ch], eax
0x1800032f9  mov     rdi, rsi
0x1800032fc  mov     rbx, [rsi+8]
0x180003300  cmp     [rbx+19h], al
0x180003303  jnz     short loc_180003338
0x180003305  lea     rcx, [rbx+20h]; Buf1
0x180003309  mov     r8d, 10h; Size
0x18000330f  lea     rdx, [rsp+0C8h+Buf2]; Buf2
0x180003317  call    memcmp_0
0x18000331c  test    eax, eax
0x18000331e  js      short loc_18000339A
0x180003320  xor     cl, cl
0x180003322  mov     rdi, rbx
0x180003325  test    cl, cl
0x180003327  lea     rax, [rbx+10h]
0x18000332b  cmovz   rax, rbx
0x18000332f  mov     rbx, [rax]
0x180003332  cmp     byte ptr [rbx+19h], 0
0x180003336  jz      short loc_180003305
0x180003338  cmp     byte ptr [rdi+19h], 0
0x18000333c  mov     [rsp+0C8h+arg_10], r12
0x180003344  jnz     short loc_180003366
0x180003346  lea     rdx, [rdi+20h]; Buf2
0x18000334a  mov     r8d, 10h; Size
0x180003350  lea     rcx, [rsp+0C8h+Buf2]; Buf1
0x180003358  call    memcmp_0
0x18000335d  test    eax, eax
0x18000335f  js      short loc_180003366
0x180003361  cmp     rdi, rsi
0x180003364  jnz     short loc_18000339E
0x180003366  mov     esi, 1
0x18000336b  mov     rcx, rbp; lpCriticalSection
0x18000336e  call    cs:__imp_LeaveCriticalSection
0x180003374  mov     r12, [rsp+0C8h+arg_10]
0x18000337c  mov     eax, esi
0x18000337e  mov     rdi, [rsp+0C8h+arg_8]
0x180003386  mov     rbp, [rsp+0C8h+arg_0]
0x18000338e  add     rsp, 0B0h
0x180003395  pop     r14
0x180003397  pop     rsi
0x180003398  pop     rbx
0x180003399  retn
0x18000339a  mov     cl, 1
0x18000339c  jmp     short loc_180003325
0x18000339e  mov     eax, [rdi+0D0h]
0x1800033a4  lea     rdx, GUID_NULL; Buf2
0x1800033ab  mov     [r14+0A0h], eax
0x1800033b2  lea     rcx, [rsp+0C8h+Buf2]; Buf1
0x1800033ba  mov     eax, [rdi+30h]
0x1800033bd  mov     r8d, 10h; Size
0x1800033c3  mov     [r14], eax
0x1800033c6  mov     dword ptr [r14+78h], 1
0x1800033ce  movups  xmm0, xmmword ptr [rdi+50h]
0x1800033d2  movups  [rsp+0C8h+Buf2], xmm0
0x1800033da  call    memcmp_0
0x1800033df  xor     r12d, r12d
0x1800033e2  test    eax, eax
0x1800033e4  jnz     loc_1800034DB
0x1800033ea  mov     rcx, [r14+48h]; pv
0x1800033ee  test    rcx, rcx
0x1800033f1  jnz     loc_18000359F
0x1800033f7  mov     rcx, [r14+50h]; pv
0x1800033fb  test    rcx, rcx
0x1800033fe  jnz     loc_1800035B8
0x180003404  mov     rcx, [r14+70h]; pv
0x180003408  test    rcx, rcx
0x18000340b  jnz     loc_1800035C7
0x180003411  mov     rcx, [r14+58h]; pv
0x180003415  test    rcx, rcx
0x180003418  jz      short loc_180003424
0x18000341a  call    cs:__imp_SHFree
0x180003420  mov     [r14+58h], r12
0x180003424  mov     rcx, [r14+60h]; pv
0x180003428  test    rcx, rcx
0x18000342b  jz      short loc_18000343B
0x18000342d  call    cs:__imp_SHFree
0x180003433  mov     [r14+60h], r12
0x180003437  mov     [r14+68h], r12d
0x18000343b  mov     [r14+8], r12
0x18000343f  mov     [r14+10h], r12d
0x180003443  mov     [r14+40h], r12d
0x180003447  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000344e  movups  xmmword ptr [r14+20h], xmm0
0x180003453  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18000345a  mov     [r14+14h], r12
0x18000345e  mov     [r14+1Ch], r12d
0x180003462  movups  xmmword ptr [r14+30h], xmm1
0x180003467  mov     rcx, [r14+98h]
0x18000346e  test    rcx, rcx
0x180003471  jnz     loc_1800035D6
0x180003477  mov     rbx, [rdi+0C8h]
0x18000347e  test    rbx, rbx
0x180003481  jnz     loc_180003609
0x180003487  mov     rdi, r12
0x18000348a  movups  xmm0, xmmword ptr [r14+20h]
0x18000348f  mov     r8d, 10h; Size
0x180003495  mov     [r14+98h], rdi
0x18000349c  lea     rdx, GUID_NULL; Buf2
0x1800034a3  lea     rcx, [rsp+0C8h+Buf1]; Buf1
0x1800034ab  movups  [rsp+0C8h+Buf1], xmm0
0x1800034b3  call    memcmp_0
0x1800034b8  test    eax, eax
0x1800034ba  jnz     short loc_1800034C6
0x1800034bc  mov     esi, 8007000Eh
0x1800034c1  jmp     loc_18000336B
0x1800034c6  call    cs:__imp_GetTickCount
0x1800034cc  mov     [r14+0A0h], eax
0x1800034d3  mov     esi, r12d
0x1800034d6  jmp     loc_18000336B
0x1800034db  movups  xmm0, xmmword ptr [rdi+50h]
0x1800034df  lea     rcx, [r14+8]; this
0x1800034e3  movups  xmm1, xmmword ptr [rdi+60h]
0x1800034e7  movups  [rsp+0C8h+Buf1], xmm0
0x1800034ef  movups  [rsp+0C8h+Buf2], xmm1
0x1800034f7  call    ?clear@CConFoldEntry@@QEAAXXZ; CConFoldEntry::clear(void)
0x1800034fc  mov     eax, [rdi+4Ch]
0x1800034ff  lea     rcx, [r14+8]
0x180003503  mov     r9d, [rdi+40h]
0x180003507  mov     r8d, [rdi+3Ch]
0x18000350b  mov     edx, [rdi+38h]
0x18000350e  mov     [rsp+0C8h+var_50], eax
0x180003512  mov     eax, [rdi+48h]
0x180003515  mov     [rsp+0C8h+var_58], eax
0x180003519  mov     eax, [rdi+44h]
0x18000351c  mov     [rsp+0C8h+var_60], eax
0x180003520  mov     rax, [rdi+88h]
0x180003527  mov     [rsp+0C8h+var_68], rax
0x18000352c  mov     rax, [rdi+0A0h]
0x180003533  mov     [rsp+0C8h+var_70], rax
0x180003538  mov     rax, [rdi+80h]
0x18000353f  mov     [rsp+0C8h+var_78], rax
0x180003544  mov     rax, [rdi+78h]
0x180003548  mov     [rsp+0C8h+var_80], rax
0x18000354d  mov     eax, [rdi+98h]
0x180003553  mov     [rsp+0C8h+var_88], eax
0x180003557  mov     rax, [rdi+90h]
0x18000355e  mov     [rsp+0C8h+var_90], rax
0x180003563  mov     eax, [rdi+70h]
0x180003566  mov     [rsp+0C8h+var_98], eax
0x18000356a  lea     rax, [rsp+0C8h+Buf2]
0x180003572  mov     [rsp+0C8h+var_A0], rax
0x180003577  lea     rax, [rsp+0C8h+Buf1]
0x18000357f  mov     [rsp+0C8h+var_A8], rax
0x180003584  call    ?HrInitData@CConFoldEntry@@QEAAJW4tagNETCON_MEDIATYPE@@W4tagNETCON_SUBMEDIATYPE@@W4tagNETCON_STATUS@@PEBU_GUID@@3KPEBEKPEBG555KHK@Z; CConFoldEntry::HrInitData(tagNETCON_MEDIATYPE,tagNETCON_SUBMEDIATYPE,tagNETCON_STATUS,_GUID const *,_GUID const *,ulong,uchar const *,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,int,ulong)
0x180003589  test    eax, eax
0x18000358b  jns     loc_180003467
0x180003591  lea     rcx, [r14+8]; this
0x180003595  call    ?clear@CConFoldEntry@@QEAAXXZ; CConFoldEntry::clear(void)
0x18000359a  jmp     loc_180003467
0x18000359f  call    cs:__imp_SHFree
0x1800035a5  mov     [r14+48h], r12
0x1800035a9  jmp     loc_1800033F7
0x1800035ae  mov     eax, 1
0x1800035b3  jmp     loc_18000338E
0x1800035b8  call    cs:__imp_SHFree
0x1800035be  mov     [r14+50h], r12
0x1800035c2  jmp     loc_180003404
0x1800035c7  call    cs:__imp_SHFree
0x1800035cd  mov     [r14+70h], r12
0x1800035d1  jmp     loc_180003411
0x1800035d6  mov     rcx, [rcx]; pv
0x1800035d9  call    cs:__imp_CoTaskMemFree
0x1800035df  mov     rcx, [r14+98h]
0x1800035e6  mov     rcx, [rcx+8]; pv
0x1800035ea  call    cs:__imp_CoTaskMemFree
0x1800035f0  mov     rcx, [r14+98h]; pv
0x1800035f7  call    cs:__imp_CoTaskMemFree
0x1800035fd  mov     [r14+98h], r12
0x180003604  jmp     loc_180003477
0x180003609  mov     ecx, 10h; cb
0x18000360e  call    cs:__imp_CoTaskMemAlloc
0x180003614  mov     rdi, rax
0x180003617  test    rax, rax
0x18000361a  jz      loc_18000348A
0x180003620  mov     [rax], r12
0x180003623  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000362a  mov     [rax+8], r12
0x18000362e  mov     rcx, [rbx]
0x180003631  test    rcx, rcx
0x180003634  jz      short loc_18000368C
0x180003636  mov     rax, rsi
0x180003639  inc     rax
0x18000363c  cmp     [rcx+rax*2], r12w
0x180003641  jnz     short loc_180003639
0x180003643  add     eax, 1
0x180003646  jz      short loc_18000368C
0x180003648  mov     [rsp+0C8h+arg_18], r15
0x180003650  lea     rcx, [rax+rax]; cb
0x180003654  mov     r15d, eax
0x180003657  call    cs:__imp_CoTaskMemAlloc
0x18000365d  mov     [rdi], rax
0x180003660  test    rax, rax
0x180003663  jz      short loc_180003684
0x180003665  mov     r8, [rbx]
0x180003668  mov     edx, r15d
0x18000366b  mov     rcx, rax
0x18000366e  call    cs:__imp__o_wcscpy_s
0x180003674  test    eax, eax
0x180003676  jz      short loc_180003684
0x180003678  mov     rcx, [rdi]; pv
0x18000367b  call    cs:__imp_CoTaskMemFree
0x180003681  mov     [rdi], r12
0x180003684  mov     r15, [rsp+0C8h+arg_18]
0x18000368c  mov     rax, [rbx+8]
0x180003690  test    rax, rax
0x180003693  jz      loc_18000348A
0x180003699  inc     rsi
0x18000369c  cmp     [rax+rsi*2], r12w
0x1800036a1  jnz     short loc_180003699
0x1800036a3  add     esi, 1
0x1800036a6  jz      loc_18000348A
0x1800036ac  lea     rcx, [rsi+rsi]; cb
0x1800036b0  call    cs:__imp_CoTaskMemAlloc
0x1800036b6  mov     [rdi+8], rax
0x1800036ba  test    rax, rax
0x1800036bd  jz      loc_18000348A
0x1800036c3  mov     r8, [rbx+8]
0x1800036c7  mov     edx, esi
0x1800036c9  mov     rcx, rax
0x1800036cc  call    cs:__imp__o_wcscpy_s
0x1800036d2  test    eax, eax
0x1800036d4  jz      loc_18000348A
0x1800036da  mov     rcx, [rdi+8]; pv
0x1800036de  call    cs:__imp_CoTaskMemFree
0x1800036e4  mov     [rdi+8], r12
0x1800036e8  jmp     loc_18000348A
```
