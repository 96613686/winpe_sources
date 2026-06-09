# CPackage::Next(ulong,tagOLEVERB *,ulong *)

- ea: `0x1800096e0`
- end: `0x1800098a3`
- name: `?Next@CPackage@@UEAAJKPEAUtagOLEVERB@@PEAK@Z`
- size: `451`
- prototype: `__int64 __fastcall(CPackage *this, unsigned int, struct tagOLEVERB *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800041d4`
- `0x1800096e0`
- `0x18000cbb2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009767`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009830`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009767`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009830`
- `KERNEL32!lstrlenW` at `0x180009759`
- `KERNEL32!lstrlenW` at `0x180009821`
- `KERNEL32!lstrlenW` at `0x180009759`
- `KERNEL32!lstrlenW` at `0x180009821`

## pseudocode

```c
__int64 __fastcall CPackage::Next(CPackage *this, unsigned int a2, struct tagOLEVERB *a3, unsigned int *a4)
{
  __int64 v8; // rax
  const WCHAR *v9; // rcx
  __int64 v10; // rdi
  OLECHAR *v11; // rax
  unsigned int v12; // ecx
  __int64 v13; // rcx
  int v14; // edi
  __int64 v15; // rbp
  const WCHAR *v16; // rcx
  __int64 v17; // r12
  OLECHAR *v18; // rax

  if ( !a3 )
    return (unsigned int)-2147024809;
  if ( a2 == 1 )
  {
    v8 = *((unsigned int *)this + 55);
    if ( (unsigned int)v8 >= *((_DWORD *)this + 54) )
    {
      v12 = 1;
    }
    else
    {
      *a3 = *(struct tagOLEVERB *)(*((_QWORD *)this + 28) + 24 * v8);
      v9 = *(const WCHAR **)(*((_QWORD *)this + 28) + 24LL * *((unsigned int *)this + 55) + 8);
      if ( v9 )
      {
        v10 = (unsigned int)(lstrlenW(v9) + 1);
        v11 = (OLECHAR *)CoTaskMemAlloc(2 * v10);
        a3->lpszVerbName = v11;
        if ( v11 )
          StringCchCopyW(
            v11,
            (unsigned int)v10,
            *(const unsigned __int16 **)(*((_QWORD *)this + 28) + 24LL * *((unsigned int *)this + 55) + 8));
      }
      ++*((_DWORD *)this + 55);
      v12 = 0;
    }
    if ( a4 )
      *a4 = v12 ^ 1;
    return v12;
  }
  if ( !a4 )
    return (unsigned int)-2147024809;
  v13 = *((unsigned int *)this + 55);
  v14 = *((_DWORD *)this + 54) - v13;
  if ( a2 < v14 )
    v14 = a2;
  if ( v14 > 0 )
  {
    memcpy_0(a3, (const void *)(*((_QWORD *)this + 28) + 24 * v13), 24LL * v14);
    v15 = 0;
    while ( 1 )
    {
      v16 = *(const WCHAR **)(*((_QWORD *)this + 28) + 24LL * (unsigned int)(v15 + *((_DWORD *)this + 55)) + 8);
      if ( v16 )
      {
        v17 = (unsigned int)(lstrlenW(v16) + 1);
        v18 = (OLECHAR *)CoTaskMemAlloc(2 * v17);
        a3[v15].lpszVerbName = v18;
        if ( !v18 )
          return (unsigned int)-2147024882;
        StringCchCopyW(
          v18,
          (unsigned int)v17,
          *(const unsigned __int16 **)(*((_QWORD *)this + 28) + 24LL * (unsigned int)(v15 + *((_DWORD *)this + 55)) + 8));
      }
      v15 = (unsigned int)(v15 + 1);
      if ( (int)v15 >= v14 )
      {
        *((_DWORD *)this + 55) += v14;
        break;
      }
    }
  }
  *a4 = v14;
  return a2 != v14;
}

```

## disassembly

```asm
0x1800096e0  push    rbx
0x1800096e2  push    rbp
0x1800096e3  push    rsi
0x1800096e4  push    rdi
0x1800096e5  push    r12
0x1800096e7  push    r14
0x1800096e9  push    r15
0x1800096eb  sub     rsp, 20h
0x1800096ef  mov     rsi, r9
0x1800096f2  mov     r15, r8
0x1800096f5  mov     r14d, edx
0x1800096f8  mov     rbx, rcx
0x1800096fb  test    r8, r8
0x1800096fe  jz      loc_18000988D
0x180009704  cmp     edx, 1
0x180009707  jnz     loc_1800097BA
0x18000970d  mov     eax, [rcx+0DCh]
0x180009713  cmp     eax, [rcx+0D8h]
0x180009719  jnb     loc_1800097A0
0x18000971f  lea     rcx, [rax+rax*2]
0x180009723  mov     rax, [rbx+0E0h]
0x18000972a  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18000972e  movups  xmmword ptr [r8], xmm0
0x180009732  movsd   xmm1, qword ptr [rax+rcx*8+10h]
0x180009738  movsd   qword ptr [r8+10h], xmm1
0x18000973e  mov     eax, [rbx+0DCh]
0x180009744  lea     rcx, [rax+rax*2]
0x180009748  mov     rax, [rbx+0E0h]
0x18000974f  mov     rcx, [rax+rcx*8+8]; lpString
0x180009754  test    rcx, rcx
0x180009757  jz      short loc_180009796
0x180009759  call    cs:__imp_lstrlenW
0x18000975f  inc     eax
0x180009761  mov     edi, eax
0x180009763  lea     rcx, [rax+rax]; cb
0x180009767  call    cs:__imp_CoTaskMemAlloc
0x18000976d  mov     [r15+8], rax
0x180009771  test    rax, rax
0x180009774  jz      short loc_180009796
0x180009776  mov     ecx, [rbx+0DCh]
0x18000977c  mov     edx, edi; unsigned __int64
0x18000977e  mov     r8, [rbx+0E0h]
0x180009785  lea     r9, [rcx+rcx*2]
0x180009789  mov     rcx, rax; unsigned __int16 *
0x18000978c  mov     r8, [r8+r9*8+8]; unsigned __int16 *
0x180009791  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009796  inc     dword ptr [rbx+0DCh]
0x18000979c  xor     ecx, ecx
0x18000979e  jmp     short loc_1800097A5
0x1800097a0  mov     ecx, 1
0x1800097a5  test    rsi, rsi
0x1800097a8  jz      loc_180009892
0x1800097ae  mov     eax, ecx
0x1800097b0  xor     eax, 1
0x1800097b3  mov     [rsi], eax
0x1800097b5  jmp     loc_180009892
0x1800097ba  test    rsi, rsi
0x1800097bd  jz      loc_18000988D
0x1800097c3  mov     ecx, [rcx+0DCh]
0x1800097c9  mov     edi, [rbx+0D8h]
0x1800097cf  sub     edi, ecx
0x1800097d1  cmp     r14d, edi
0x1800097d4  cmovb   edi, r14d
0x1800097d8  test    edi, edi
0x1800097da  jle     loc_18000987A
0x1800097e0  lea     rcx, [rcx+rcx*2]
0x1800097e4  movsxd  rax, edi
0x1800097e7  lea     r8, [rax+rax*2]
0x1800097eb  mov     rax, [rbx+0E0h]
0x1800097f2  shl     r8, 3; Size
0x1800097f6  lea     rdx, [rax+rcx*8]; Src
0x1800097fa  mov     rcx, r15; void *
0x1800097fd  call    memcpy_0
0x180009802  xor     ebp, ebp
0x180009804  mov     eax, [rbx+0DCh]
0x18000980a  add     eax, ebp
0x18000980c  lea     rcx, [rax+rax*2]
0x180009810  mov     rax, [rbx+0E0h]
0x180009817  mov     rcx, [rax+rcx*8+8]; lpString
0x18000981c  test    rcx, rcx
0x18000981f  jz      short loc_18000986E
0x180009821  call    cs:__imp_lstrlenW
0x180009827  inc     eax
0x180009829  mov     r12d, eax
0x18000982c  lea     rcx, [rax+rax]; cb
0x180009830  call    cs:__imp_CoTaskMemAlloc
0x180009836  lea     r8, ds:0[rbp*2]
0x18000983e  add     r8, rbp
0x180009841  mov     [r15+r8*8+8], rax
0x180009846  test    rax, rax
0x180009849  jz      short loc_180009886
0x18000984b  mov     ecx, [rbx+0DCh]
0x180009851  mov     edx, r12d; unsigned __int64
0x180009854  mov     r8, [rbx+0E0h]
0x18000985b  add     ecx, ebp
0x18000985d  lea     r9, [rcx+rcx*2]
0x180009861  mov     rcx, rax; unsigned __int16 *
0x180009864  mov     r8, [r8+r9*8+8]; unsigned __int16 *
0x180009869  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000986e  inc     ebp
0x180009870  cmp     ebp, edi
0x180009872  jl      short loc_180009804
0x180009874  add     [rbx+0DCh], edi
0x18000987a  xor     ecx, ecx
0x18000987c  mov     [rsi], edi
0x18000987e  cmp     r14d, edi
0x180009881  setnz   cl
0x180009884  jmp     short loc_180009892
0x180009886  mov     ecx, 8007000Eh
0x18000988b  jmp     short loc_180009892
0x18000988d  mov     ecx, 80070057h
0x180009892  mov     eax, ecx
0x180009894  add     rsp, 20h
0x180009898  pop     r15
0x18000989a  pop     r14
0x18000989c  pop     r12
0x18000989e  pop     rdi
0x18000989f  pop     rsi
0x1800098a0  pop     rbp
0x1800098a1  pop     rbx
0x1800098a2  retn
```
