# CSimpleTable4ui::~CSimpleTable4ui(void)

- ea: `0x180007210`
- end: `0x1800073d6`
- name: `??1CSimpleTable4ui@@QEAA@XZ`
- size: `454`
- prototype: `void __fastcall(CSimpleTable4ui *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800071e0`

## callees

- `0x180007210`
- `0x18000824c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000728b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800072a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800072ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800072d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800072e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007302`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000731b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000734d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007369`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800073bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000728b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800072a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800072ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800072d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800072e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007302`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000731b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000734d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007369`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800073bc`

## pseudocode

```c
void __fastcall CSimpleTable4ui::~CSimpleTable4ui(CSimpleTable4ui *this)
{
  bool v2; // zf
  __int64 v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  unsigned int i; // edi
  void *v12; // rcx
  void *v13; // rcx
  __int64 v14; // rcx
  void *v15; // rdi

  *(_QWORD *)this = &CSimpleTable4ui::`vftable'{for `ISimpleTableWrite'};
  *((_QWORD *)this + 1) = &CSimpleTable4ui::`vftable'{for `ISimpleTableMarshall'};
  *((_QWORD *)this + 2) = &CSimpleTable4ui::`vftable'{for `ISimpleTableControl'};
  v2 = *((_DWORD *)this + 25) == 1;
  v3 = *((_QWORD *)this + 33);
  if ( v2 )
  {
    if ( v3 && dword_180072FE8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
      *((_QWORD *)this + 33) = 0;
    }
  }
  else
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  v4 = (void *)*((_QWORD *)this + 29);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 29) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 30);
  if ( v5 )
  {
    CoTaskMemFree(v5);
    *((_QWORD *)this + 30) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 13);
  if ( v6 )
  {
    CoTaskMemFree(v6);
    *((_QWORD *)this + 13) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 23);
  if ( v7 )
  {
    CoTaskMemFree(v7);
    *((_QWORD *)this + 23) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 26);
  if ( v8 )
  {
    CoTaskMemFree(v8);
    *((_QWORD *)this + 26) = 0;
  }
  v9 = (void *)*((_QWORD *)this + 27);
  if ( v9 )
  {
    CoTaskMemFree(v9);
    *((_QWORD *)this + 27) = 0;
  }
  v10 = (void *)*((_QWORD *)this + 24);
  if ( v10 )
  {
    CoTaskMemFree(v10);
    *((_QWORD *)this + 24) = 0;
  }
  if ( *((_QWORD *)this + 25) )
  {
    for ( i = 0; i < *((_DWORD *)this + 44); ++i )
    {
      v12 = *(void **)(*((_QWORD *)this + 25) + 8LL * i);
      if ( v12 )
        CoTaskMemFree(v12);
    }
  }
  v13 = (void *)*((_QWORD *)this + 25);
  if ( v13 )
  {
    CoTaskMemFree(v13);
    *((_QWORD *)this + 25) = 0;
  }
  *((_BYTE *)this + 32) = 17;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 12) = -1;
  *((_DWORD *)this + 16) = -1;
  v14 = *((_QWORD *)this + 3);
  if ( v14 && _InterlockedExchangeAdd((volatile signed __int32 *)(v14 + 44), 0xFFFFFFFF) == 1 )
  {
    v15 = (void *)*((_QWORD *)this + 3);
    if ( v15 )
    {
      CSimpleDataTableCache::~CSimpleDataTableCache(*((CSimpleDataTableCache **)this + 3));
      CoTaskMemFree(v15);
      *((_QWORD *)this + 3) = 0;
    }
  }
}

```

## disassembly

```asm
0x180007210  mov     [rsp+arg_8], rbx
0x180007215  mov     [rsp+arg_10], rsi
0x18000721a  push    rdi
0x18000721b  sub     rsp, 20h
0x18000721f  mov     rbx, rcx
0x180007222  lea     rax, ??_7CSimpleTable4ui@@6BISimpleTableWrite@@@; const CSimpleTable4ui::`vftable'{for `ISimpleTableWrite'}
0x180007229  mov     [rcx], rax
0x18000722c  lea     rax, ??_7CSimpleTable4ui@@6BISimpleTableMarshall@@@; const CSimpleTable4ui::`vftable'{for `ISimpleTableMarshall'}
0x180007233  mov     [rcx+8], rax
0x180007237  lea     rax, ??_7CSimpleTable4ui@@6BISimpleTableControl@@@; const CSimpleTable4ui::`vftable'{for `ISimpleTableControl'}
0x18000723e  mov     [rcx+10h], rax
0x180007242  xor     esi, esi
0x180007244  cmp     dword ptr [rcx+64h], 1
0x180007248  mov     rcx, [rcx+108h]
0x18000724f  jnz     short loc_180007273
0x180007251  test    rcx, rcx
0x180007254  jz      short loc_18000727F
0x180007256  cmp     cs:dword_180072FE8, esi
0x18000725c  jz      short loc_18000727F
0x18000725e  mov     rax, [rcx]
0x180007261  mov     rax, [rax+10h]
0x180007265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000726a  mov     [rbx+108h], rsi
0x180007271  jmp     short loc_18000727F
0x180007273  mov     rax, [rcx]
0x180007276  mov     rax, [rax+10h]
0x18000727a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000727f  mov     rcx, [rbx+0E8h]; pv
0x180007286  test    rcx, rcx
0x180007289  jz      short loc_180007298
0x18000728b  call    cs:__imp_CoTaskMemFree
0x180007291  mov     [rbx+0E8h], rsi
0x180007298  mov     rcx, [rbx+0F0h]; pv
0x18000729f  test    rcx, rcx
0x1800072a2  jz      short loc_1800072B1
0x1800072a4  call    cs:__imp_CoTaskMemFree
0x1800072aa  mov     [rbx+0F0h], rsi
0x1800072b1  mov     rcx, [rbx+68h]; pv
0x1800072b5  test    rcx, rcx
0x1800072b8  jz      short loc_1800072C4
0x1800072ba  call    cs:__imp_CoTaskMemFree
0x1800072c0  mov     [rbx+68h], rsi
0x1800072c4  mov     rcx, [rbx+0B8h]; pv
0x1800072cb  test    rcx, rcx
0x1800072ce  jz      short loc_1800072DD
0x1800072d0  call    cs:__imp_CoTaskMemFree
0x1800072d6  mov     [rbx+0B8h], rsi
0x1800072dd  mov     rcx, [rbx+0D0h]; pv
0x1800072e4  test    rcx, rcx
0x1800072e7  jz      short loc_1800072F6
0x1800072e9  call    cs:__imp_CoTaskMemFree
0x1800072ef  mov     [rbx+0D0h], rsi
0x1800072f6  mov     rcx, [rbx+0D8h]; pv
0x1800072fd  test    rcx, rcx
0x180007300  jz      short loc_18000730F
0x180007302  call    cs:__imp_CoTaskMemFree
0x180007308  mov     [rbx+0D8h], rsi
0x18000730f  mov     rcx, [rbx+0C0h]; pv
0x180007316  test    rcx, rcx
0x180007319  jz      short loc_180007328
0x18000731b  call    cs:__imp_CoTaskMemFree
0x180007321  mov     [rbx+0C0h], rsi
0x180007328  cmp     [rbx+0C8h], rsi
0x18000732f  jz      short loc_18000735D
0x180007331  mov     edi, esi
0x180007333  cmp     [rbx+0B0h], esi
0x180007339  jbe     short loc_18000735D
0x18000733b  mov     ecx, edi
0x18000733d  mov     rax, [rbx+0C8h]
0x180007344  mov     rcx, [rax+rcx*8]; pv
0x180007348  test    rcx, rcx
0x18000734b  jz      short loc_180007353
0x18000734d  call    cs:__imp_CoTaskMemFree
0x180007353  inc     edi
0x180007355  cmp     edi, [rbx+0B0h]
0x18000735b  jb      short loc_18000733B
0x18000735d  mov     rcx, [rbx+0C8h]; pv
0x180007364  test    rcx, rcx
0x180007367  jz      short loc_180007376
0x180007369  call    cs:__imp_CoTaskMemFree
0x18000736f  mov     [rbx+0C8h], rsi
0x180007376  mov     byte ptr [rbx+20h], 11h
0x18000737a  mov     [rbx+28h], rsi
0x18000737e  mov     [rbx+38h], rsi
0x180007382  mov     dword ptr [rbx+30h], 0FFFFFFFFh
0x180007389  mov     dword ptr [rbx+40h], 0FFFFFFFFh
0x180007390  mov     rcx, [rbx+18h]
0x180007394  test    rcx, rcx
0x180007397  jz      short loc_1800073C6
0x180007399  mov     eax, 0FFFFFFFFh
0x18000739e  lock xadd [rcx+2Ch], eax
0x1800073a3  cmp     eax, 1
0x1800073a6  jnz     short loc_1800073C6
0x1800073a8  mov     rdi, [rbx+18h]
0x1800073ac  test    rdi, rdi
0x1800073af  jz      short loc_1800073C6
0x1800073b1  mov     rcx, rdi; this
0x1800073b4  call    ??1CSimpleDataTableCache@@QEAA@XZ; CSimpleDataTableCache::~CSimpleDataTableCache(void)
0x1800073b9  mov     rcx, rdi; pv
0x1800073bc  call    cs:__imp_CoTaskMemFree
0x1800073c2  mov     [rbx+18h], rsi
0x1800073c6  mov     rbx, [rsp+28h+arg_8]
0x1800073cb  mov     rsi, [rsp+28h+arg_10]
0x1800073d0  add     rsp, 20h
0x1800073d4  pop     rdi
0x1800073d5  retn
```
