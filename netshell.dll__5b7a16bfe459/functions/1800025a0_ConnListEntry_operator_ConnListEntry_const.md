# ConnListEntry::operator=(ConnListEntry const &)

- ea: `0x1800025a0`
- end: `0x180002892`
- name: `??4ConnListEntry@@QEAAAEAV0@AEBV0@@Z`
- size: `754`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `6`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800022f0`
- `0x180015400`
- `0x180016eb4`
- `0x18001d27c`
- `0x1800416ac`
- `0x180042294`

## callees

- `0x1800025a0`
- `0x180002930`
- `0x180004920`
- `0x180062124`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800027fa`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000284c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800027fa`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000284c`
- `SHELL32!__imp_SHFree` at `0x1800026b7`
- `SHELL32!__imp_SHFree` at `0x1800026ca`
- `SHELL32!__imp_SHFree` at `0x1800026dd`
- `SHELL32!__imp_SHFree` at `0x1800026f0`
- `SHELL32!__imp_SHFree` at `0x180002703`
- `SHELL32!__imp_SHFree` at `0x1800026b7`
- `SHELL32!__imp_SHFree` at `0x1800026ca`
- `SHELL32!__imp_SHFree` at `0x1800026dd`
- `SHELL32!__imp_SHFree` at `0x1800026f0`
- `SHELL32!__imp_SHFree` at `0x180002703`
- `ole32!CoTaskMemFree` at `0x18000274a`
- `ole32!CoTaskMemFree` at `0x18000275b`
- `ole32!CoTaskMemFree` at `0x180002768`
- `ole32!CoTaskMemFree` at `0x180002807`
- `ole32!CoTaskMemFree` at `0x18000285a`
- `ole32!CoTaskMemFree` at `0x18000274a`
- `ole32!CoTaskMemFree` at `0x18000275b`
- `ole32!CoTaskMemFree` at `0x180002768`
- `ole32!CoTaskMemFree` at `0x180002807`
- `ole32!CoTaskMemFree` at `0x18000285a`
- `ole32!CoTaskMemAlloc` at `0x180002792`
- `ole32!CoTaskMemAlloc` at `0x1800027e3`
- `ole32!CoTaskMemAlloc` at `0x180002833`
- `ole32!CoTaskMemAlloc` at `0x180002792`
- `ole32!CoTaskMemAlloc` at `0x1800027e3`
- `ole32!CoTaskMemAlloc` at `0x180002833`

## pseudocode

```c
__int64 __fastcall ConnListEntry::operator=(__int64 a1, __int64 a2)
{
  __int128 v4; // xmm1
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  LPVOID *v10; // rcx
  _QWORD *v11; // rbx
  LPVOID *v12; // rax
  LPVOID *v13; // rsi
  __int64 v14; // rbp
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned int v17; // r14d
  LPVOID v18; // rax
  __int64 v19; // rax
  __int64 v20; // rbp
  LPVOID v21; // rax
  __int128 v23; // [rsp+80h] [rbp-38h] BYREF
  __int128 v24; // [rsp+90h] [rbp-28h] BYREF

  *(_DWORD *)(a1 + 160) = *(_DWORD *)(a2 + 160);
  *(_DWORD *)a1 = *(_DWORD *)a2;
  *(_DWORD *)(a1 + 120) = 1;
  v23 = *(_OWORD *)(a2 + 32);
  if ( !memcmp_0(&v23, &GUID_NULL, 0x10u) )
  {
    v5 = *(void **)(a1 + 72);
    if ( v5 )
    {
      SHFree(v5);
      *(_QWORD *)(a1 + 72) = 0;
    }
    v6 = *(void **)(a1 + 80);
    if ( v6 )
    {
      SHFree(v6);
      *(_QWORD *)(a1 + 80) = 0;
    }
    v7 = *(void **)(a1 + 112);
    if ( v7 )
    {
      SHFree(v7);
      *(_QWORD *)(a1 + 112) = 0;
    }
    v8 = *(void **)(a1 + 88);
    if ( v8 )
    {
      SHFree(v8);
      *(_QWORD *)(a1 + 88) = 0;
    }
    v9 = *(void **)(a1 + 96);
    if ( v9 )
    {
      SHFree(v9);
      *(_QWORD *)(a1 + 96) = 0;
      *(_DWORD *)(a1 + 104) = 0;
    }
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = 0;
    *(_DWORD *)(a1 + 64) = 0;
    *(GUID *)(a1 + 32) = GUID_NULL;
    *(_QWORD *)(a1 + 20) = 0;
    *(_DWORD *)(a1 + 28) = 0;
    *(GUID *)(a1 + 48) = GUID_NULL;
  }
  else
  {
    v4 = *(_OWORD *)(a2 + 48);
    v24 = *(_OWORD *)(a2 + 32);
    v23 = v4;
    CConFoldEntry::clear((CConFoldEntry *)(a1 + 8));
    if ( (int)CConFoldEntry::HrInitData(
                a1 + 8,
                *(unsigned int *)(a2 + 8),
                *(unsigned int *)(a2 + 12),
                *(unsigned int *)(a2 + 16),
                &v24,
                &v23,
                *(_DWORD *)(a2 + 64),
                *(_QWORD *)(a2 + 96),
                *(_DWORD *)(a2 + 104),
                *(_QWORD *)(a2 + 72),
                *(_QWORD *)(a2 + 80),
                *(_QWORD *)(a2 + 112),
                *(_QWORD *)(a2 + 88),
                *(_DWORD *)(a2 + 20),
                *(_DWORD *)(a2 + 24),
                *(_DWORD *)(a2 + 28)) < 0 )
      CConFoldEntry::clear((CConFoldEntry *)(a1 + 8));
  }
  v10 = *(LPVOID **)(a1 + 152);
  if ( v10 )
  {
    CoTaskMemFree(*v10);
    CoTaskMemFree(*(LPVOID *)(*(_QWORD *)(a1 + 152) + 8LL));
    CoTaskMemFree(*(LPVOID *)(a1 + 152));
    *(_QWORD *)(a1 + 152) = 0;
  }
  v11 = *(_QWORD **)(a2 + 152);
  if ( v11 )
  {
    v12 = (LPVOID *)CoTaskMemAlloc(0x10u);
    v13 = v12;
    if ( v12 )
    {
      v14 = -1;
      *v12 = 0;
      v12[1] = 0;
      if ( *v11 )
      {
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)(*v11 + 2 * v15) );
        v16 = (unsigned int)(v15 + 1);
        if ( (_DWORD)v16 )
        {
          v17 = v16;
          v18 = CoTaskMemAlloc(2 * v16);
          *v13 = v18;
          if ( v18 )
          {
            if ( (unsigned int)_o_wcscpy_s(v18, v17, *v11) )
            {
              CoTaskMemFree(*v13);
              *v13 = 0;
            }
          }
        }
      }
      v19 = v11[1];
      if ( v19 )
      {
        do
          ++v14;
        while ( *(_WORD *)(v19 + 2 * v14) );
        v20 = (unsigned int)(v14 + 1);
        if ( (_DWORD)v20 )
        {
          v21 = CoTaskMemAlloc(2 * v20);
          v13[1] = v21;
          if ( v21 )
          {
            if ( (unsigned int)_o_wcscpy_s(v21, (unsigned int)v20, v11[1]) )
            {
              CoTaskMemFree(v13[1]);
              v13[1] = 0;
            }
          }
        }
      }
    }
    *(_QWORD *)(a1 + 152) = v13;
  }
  else
  {
    *(_QWORD *)(a1 + 152) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x1800025a0  mov     r11, rsp
0x1800025a3  mov     [r11+18h], rbx
0x1800025a7  push    rsi
0x1800025a8  push    rdi
0x1800025a9  push    r15
0x1800025ab  sub     rsp, 0A0h
0x1800025b2  mov     eax, [rdx+0A0h]
0x1800025b8  mov     rsi, rdx
0x1800025bb  mov     [rcx+0A0h], eax
0x1800025c1  mov     rdi, rcx
0x1800025c4  mov     eax, [rdx]
0x1800025c6  mov     r8d, 10h; Size
0x1800025cc  mov     [rcx], eax
0x1800025ce  mov     dword ptr [rcx+78h], 1
0x1800025d5  lea     rcx, [r11-38h]; Buf1
0x1800025d9  movups  xmm0, xmmword ptr [rdx+20h]
0x1800025dd  lea     rdx, GUID_NULL; Buf2
0x1800025e4  movups  xmmword ptr [r11-38h], xmm0
0x1800025e9  call    memcmp_0
0x1800025ee  xor     r15d, r15d
0x1800025f1  test    eax, eax
0x1800025f3  jz      loc_1800026AE
0x1800025f9  movups  xmm0, xmmword ptr [rsi+20h]
0x1800025fd  lea     rcx, [rdi+8]; this
0x180002601  movups  xmm1, xmmword ptr [rsi+30h]
0x180002605  movups  [rsp+0B8h+var_28], xmm0
0x18000260d  movups  [rsp+0B8h+var_38], xmm1
0x180002615  call    ?clear@CConFoldEntry@@QEAAXXZ; CConFoldEntry::clear(void)
0x18000261a  mov     eax, [rsi+1Ch]
0x18000261d  lea     rcx, [rdi+8]
0x180002621  mov     r9d, [rsi+10h]
0x180002625  mov     r8d, [rsi+0Ch]
0x180002629  mov     edx, [rsi+8]
0x18000262c  mov     [rsp+0B8h+var_40], eax
0x180002630  mov     eax, [rsi+18h]
0x180002633  mov     [rsp+0B8h+var_48], eax
0x180002637  mov     eax, [rsi+14h]
0x18000263a  mov     [rsp+0B8h+var_50], eax
0x18000263e  mov     rax, [rsi+58h]
0x180002642  mov     [rsp+0B8h+var_58], rax
0x180002647  mov     rax, [rsi+70h]
0x18000264b  mov     [rsp+0B8h+var_60], rax
0x180002650  mov     rax, [rsi+50h]
0x180002654  mov     [rsp+0B8h+var_68], rax
0x180002659  mov     rax, [rsi+48h]
0x18000265d  mov     [rsp+0B8h+var_70], rax
0x180002662  mov     eax, [rsi+68h]
0x180002665  mov     [rsp+0B8h+var_78], eax
0x180002669  mov     rax, [rsi+60h]
0x18000266d  mov     [rsp+0B8h+var_80], rax
0x180002672  mov     eax, [rsi+40h]
0x180002675  mov     [rsp+0B8h+var_88], eax
0x180002679  lea     rax, [rsp+0B8h+var_38]
0x180002681  mov     [rsp+0B8h+var_90], rax
0x180002686  lea     rax, [rsp+0B8h+var_28]
0x18000268e  mov     [rsp+0B8h+var_98], rax
0x180002693  call    ?HrInitData@CConFoldEntry@@QEAAJW4tagNETCON_MEDIATYPE@@W4tagNETCON_SUBMEDIATYPE@@W4tagNETCON_STATUS@@PEBU_GUID@@3KPEBEKPEBG555KHK@Z; CConFoldEntry::HrInitData(tagNETCON_MEDIATYPE,tagNETCON_SUBMEDIATYPE,tagNETCON_STATUS,_GUID const *,_GUID const *,ulong,uchar const *,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,int,ulong)
0x180002698  test    eax, eax
0x18000269a  jns     loc_18000273B
0x1800026a0  lea     rcx, [rdi+8]; this
0x1800026a4  call    ?clear@CConFoldEntry@@QEAAXXZ; CConFoldEntry::clear(void)
0x1800026a9  jmp     loc_18000273B
0x1800026ae  mov     rcx, [rdi+48h]; pv
0x1800026b2  test    rcx, rcx
0x1800026b5  jz      short loc_1800026C1
0x1800026b7  call    cs:__imp_SHFree
0x1800026bd  mov     [rdi+48h], r15
0x1800026c1  mov     rcx, [rdi+50h]; pv
0x1800026c5  test    rcx, rcx
0x1800026c8  jz      short loc_1800026D4
0x1800026ca  call    cs:__imp_SHFree
0x1800026d0  mov     [rdi+50h], r15
0x1800026d4  mov     rcx, [rdi+70h]; pv
0x1800026d8  test    rcx, rcx
0x1800026db  jz      short loc_1800026E7
0x1800026dd  call    cs:__imp_SHFree
0x1800026e3  mov     [rdi+70h], r15
0x1800026e7  mov     rcx, [rdi+58h]; pv
0x1800026eb  test    rcx, rcx
0x1800026ee  jz      short loc_1800026FA
0x1800026f0  call    cs:__imp_SHFree
0x1800026f6  mov     [rdi+58h], r15
0x1800026fa  mov     rcx, [rdi+60h]; pv
0x1800026fe  test    rcx, rcx
0x180002701  jz      short loc_180002711
0x180002703  call    cs:__imp_SHFree
0x180002709  mov     [rdi+60h], r15
0x18000270d  mov     [rdi+68h], r15d
0x180002711  mov     [rdi+8], r15
0x180002715  mov     [rdi+10h], r15d
0x180002719  mov     [rdi+40h], r15d
0x18000271d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180002724  movups  xmmword ptr [rdi+20h], xmm0
0x180002728  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18000272f  mov     [rdi+14h], r15
0x180002733  mov     [rdi+1Ch], r15d
0x180002737  movups  xmmword ptr [rdi+30h], xmm1
0x18000273b  mov     rcx, [rdi+98h]
0x180002742  test    rcx, rcx
0x180002745  jz      short loc_180002775
0x180002747  mov     rcx, [rcx]; pv
0x18000274a  call    cs:__imp_CoTaskMemFree
0x180002750  mov     rcx, [rdi+98h]
0x180002757  mov     rcx, [rcx+8]; pv
0x18000275b  call    cs:__imp_CoTaskMemFree
0x180002761  mov     rcx, [rdi+98h]; pv
0x180002768  call    cs:__imp_CoTaskMemFree
0x18000276e  mov     [rdi+98h], r15
0x180002775  mov     rbx, [rsi+98h]
0x18000277c  test    rbx, rbx
0x18000277f  jnz     short loc_18000278D
0x180002781  mov     [rdi+98h], r15
0x180002788  jmp     loc_18000287B
0x18000278d  mov     ecx, 10h; cb
0x180002792  call    cs:__imp_CoTaskMemAlloc
0x180002798  mov     rsi, rax
0x18000279b  test    rax, rax
0x18000279e  jz      loc_180002874
0x1800027a4  mov     [rsp+0B8h+arg_0], rbp
0x1800027ac  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x1800027b3  mov     [rax], r15
0x1800027b6  mov     [rax+8], r15
0x1800027ba  mov     rcx, [rbx]
0x1800027bd  mov     [rsp+0B8h+arg_8], r14
0x1800027c5  test    rcx, rcx
0x1800027c8  jz      short loc_180002810
0x1800027ca  mov     rax, rbp
0x1800027cd  inc     rax
0x1800027d0  cmp     [rcx+rax*2], r15w
0x1800027d5  jnz     short loc_1800027CD
0x1800027d7  add     eax, 1
0x1800027da  jz      short loc_180002810
0x1800027dc  lea     rcx, [rax+rax]; cb
0x1800027e0  mov     r14d, eax
0x1800027e3  call    cs:__imp_CoTaskMemAlloc
0x1800027e9  mov     [rsi], rax
0x1800027ec  test    rax, rax
0x1800027ef  jz      short loc_180002810
0x1800027f1  mov     r8, [rbx]
0x1800027f4  mov     edx, r14d
0x1800027f7  mov     rcx, rax
0x1800027fa  call    cs:__imp__o_wcscpy_s
0x180002800  test    eax, eax
0x180002802  jz      short loc_180002810
0x180002804  mov     rcx, [rsi]; pv
0x180002807  call    cs:__imp_CoTaskMemFree
0x18000280d  mov     [rsi], r15
0x180002810  mov     rax, [rbx+8]
0x180002814  test    rax, rax
0x180002817  jz      short loc_180002864
0x180002819  inc     rbp
0x18000281c  cmp     [rax+rbp*2], r15w
0x180002821  jnz     short loc_180002819
0x180002823  add     ebp, 1
0x180002826  jz      short loc_180002864
0x180002828  lea     rcx, ds:0[rbp*2]; cb
0x180002830  mov     r14d, ebp
0x180002833  call    cs:__imp_CoTaskMemAlloc
0x180002839  mov     [rsi+8], rax
0x18000283d  test    rax, rax
0x180002840  jz      short loc_180002864
0x180002842  mov     r8, [rbx+8]
0x180002846  mov     edx, r14d
0x180002849  mov     rcx, rax
0x18000284c  call    cs:__imp__o_wcscpy_s
0x180002852  test    eax, eax
0x180002854  jz      short loc_180002864
0x180002856  mov     rcx, [rsi+8]; pv
0x18000285a  call    cs:__imp_CoTaskMemFree
0x180002860  mov     [rsi+8], r15
0x180002864  mov     r14, [rsp+0B8h+arg_8]
0x18000286c  mov     rbp, [rsp+0B8h+arg_0]
0x180002874  mov     [rdi+98h], rsi
0x18000287b  mov     rbx, [rsp+0B8h+arg_10]
0x180002883  mov     rax, rdi
0x180002886  add     rsp, 0A0h
0x18000288d  pop     r15
0x18000288f  pop     rdi
0x180002890  pop     rsi
0x180002891  retn
```
