# CTimeRunList::AddSorted(_FILETIME,_FILETIME,_FILETIME,ushort *,ulong,ulong,ushort,ushort *,ushort)

- ea: `0x180019678`
- end: `0x180019842`
- name: `?AddSorted@CTimeRunList@@QEAAJU_FILETIME@@00PEAGKKG1G@Z`
- size: `458`
- prototype: `int(CTimeRunList *__hidden this, struct _FILETIME, struct _FILETIME, struct _FILETIME, unsigned __int16 *, unsigned int, unsigned int, unsigned __int16, unsigned __int16 *, unsigned __int16)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800018c0`

## callees

- `0x180009ef8`
- `0x180019678`
- `0x180019848`
- `0x18001987c`
- `0x180019914`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800196c4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800196dc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180019717`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800196c4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800196dc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180019717`

## pseudocode

```c
__int64 __fastcall CTimeRunList::AddSorted(
        CTimeRunList *this,
        FILETIME a2,
        struct _FILETIME a3,
        struct _FILETIME a4,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned int a7,
        unsigned __int16 a8,
        unsigned __int16 *a9,
        unsigned __int16 a10)
{
  __int64 v10; // r14
  unsigned __int16 v14; // ax
  unsigned __int16 *v16; // r15
  CDLink *v17; // rcx
  void (__fastcall ***v18)(_QWORD, __int64); // rcx
  _QWORD *v19; // rax
  const unsigned __int16 *v20; // rdx
  _QWORD *v21; // rsi
  FILETIME v22; // rcx
  unsigned __int16 v23; // ax
  int v24; // ebx
  __int64 v25; // rax
  FILETIME FileTime1; // [rsp+60h] [rbp+40h] BYREF
  FILETIME FileTime2; // [rsp+68h] [rbp+48h] BYREF

  FileTime2 = a2;
  v10 = *((_QWORD *)this + 2);
  FileTime1 = 0;
  while ( 1 )
  {
    FileTime1 = *(FILETIME *)(v10 + 24);
    if ( !*(_QWORD *)&FileTime1 )
      break;
    if ( !CompareFileTime(&FileTime1, &FileTime2) && !*(_QWORD *)(v10 + 48) )
    {
      v14 = a8;
      if ( *(_WORD *)(v10 + 104) < a8 )
        v14 = *(_WORD *)(v10 + 104);
      *(_WORD *)(v10 + 104) = v14;
      CRun::AdvanceKillTime((CRun *)v10, a4);
      a5 = (unsigned __int16 *)a3;
      if ( CompareFileTime((const FILETIME *)&a5, (const FILETIME *)(v10 + 32)) > 0 )
        *(_QWORD *)(v10 + 32) = a5;
      return 0;
    }
    if ( CompareFileTime(&FileTime1, &FileTime2) < 0 )
      break;
    v10 = *(_QWORD *)(v10 + 16);
  }
  v16 = a9;
  if ( *a9 >= a10 )
  {
    v17 = (CDLink *)*((_QWORD *)this + 2);
    if ( v17 == (CDLink *)v10 )
      return 1;
    CDLink::UnLink(v17);
    if ( v18 )
      (**v18)(v18, 1);
    --*v16;
  }
  v19 = operator new(0x78u);
  v21 = v19;
  if ( !v19 )
    return 2147942414LL;
  v19[1] = 0;
  v19[2] = 0;
  *v19 = &CRun::`vftable';
  v22 = FileTime2;
  *((_DWORD *)v19 + 24) = a6;
  *((_DWORD *)v19 + 25) = a7;
  v23 = a8;
  v21[3] = v22;
  *((_WORD *)v21 + 52) = v23;
  v21[4] = a3;
  v21[5] = a4;
  v21[6] = 0;
  v21[7] = 0;
  *((_DWORD *)v21 + 16) = 0;
  v21[9] = 0;
  v21[10] = 0;
  v21[11] = 0;
  *(_QWORD *)((char *)v21 + 108) = 0;
  *((_DWORD *)v21 + 29) = 0;
  v24 = CRun::SetName((CRun *)v21, v20);
  if ( v24 >= 0 )
  {
    v25 = *(_QWORD *)(v10 + 8);
    v21[1] = v25;
    *(_QWORD *)(v25 + 16) = v21;
    *(_QWORD *)(v10 + 8) = v21;
    v21[2] = v10;
    ++*v16;
    return 0;
  }
  (*(void (__fastcall **)(_QWORD *, __int64))*v21)(v21, 1);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x180019678  mov     [rsp-38h+arg_10], rbx
0x18001967d  mov     qword ptr [rsp-38h+FileTime2.dwLowDateTime], rdx
0x180019682  push    rbp
0x180019683  push    rsi
0x180019684  push    rdi
0x180019685  push    r12
0x180019687  push    r13
0x180019689  push    r14
0x18001968b  push    r15
0x18001968d  mov     rbp, rsp
0x180019690  sub     rsp, 20h
0x180019694  mov     r14, [rcx+10h]
0x180019698  xor     r12d, r12d
0x18001969b  mov     qword ptr [rbp+FileTime1.dwLowDateTime], r12
0x18001969f  mov     rbx, r9
0x1800196a2  mov     rdi, r8
0x1800196a5  mov     rsi, rcx
0x1800196a8  mov     rax, [r14+18h]
0x1800196ac  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rax
0x1800196b0  test    eax, eax
0x1800196b2  jnz     short loc_1800196BC
0x1800196b4  shr     rax, 20h
0x1800196b8  test    eax, eax
0x1800196ba  jz      short loc_180019730
0x1800196bc  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x1800196c0  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x1800196c4  call    cs:__imp_CompareFileTime
0x1800196ca  test    eax, eax
0x1800196cc  jnz     short loc_1800196D4
0x1800196ce  cmp     [r14+30h], r12
0x1800196d2  jz      short loc_1800196EC
0x1800196d4  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x1800196d8  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x1800196dc  call    cs:__imp_CompareFileTime
0x1800196e2  test    eax, eax
0x1800196e4  js      short loc_180019730
0x1800196e6  mov     r14, [r14+10h]
0x1800196ea  jmp     short loc_1800196A8
0x1800196ec  movzx   eax, [rbp+arg_38]
0x1800196f0  mov     rdx, rbx; struct _FILETIME
0x1800196f3  cmp     [r14+68h], ax
0x1800196f8  mov     rcx, r14; this
0x1800196fb  cmovb   ax, [r14+68h]
0x180019701  mov     [r14+68h], ax
0x180019706  call    ?AdvanceKillTime@CRun@@QEAAXU_FILETIME@@@Z; CRun::AdvanceKillTime(_FILETIME)
0x18001970b  lea     rdx, [r14+20h]; lpFileTime2
0x18001970f  mov     qword ptr [rbp+arg_20.dwLowDateTime], rdi
0x180019713  lea     rcx, [rbp+arg_20]; lpFileTime1
0x180019717  call    cs:__imp_CompareFileTime
0x18001971d  test    eax, eax
0x18001971f  jle     short loc_180019729
0x180019721  mov     rax, qword ptr [rbp+arg_20.dwLowDateTime]
0x180019725  mov     [r14+20h], rax
0x180019729  xor     eax, eax
0x18001972b  jmp     loc_18001982D
0x180019730  mov     r15, [rbp+arg_40]
0x180019737  mov     r13d, 1
0x18001973d  movzx   ecx, [rbp+arg_48]
0x180019744  cmp     [r15], cx
0x180019748  jb      short loc_18001977C
0x18001974a  mov     rcx, [rsi+10h]; this
0x18001974e  cmp     rcx, r14
0x180019751  jnz     short loc_18001975B
0x180019753  mov     eax, r13d
0x180019756  jmp     loc_18001982D
0x18001975b  call    ?UnLink@CDLink@@QEAAXXZ; CDLink::UnLink(void)
0x180019760  test    rcx, rcx
0x180019763  jz      short loc_180019773
0x180019765  mov     rax, [rcx]
0x180019768  mov     edx, r13d
0x18001976b  mov     rax, [rax]
0x18001976e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019773  mov     eax, 0FFFFh
0x180019778  add     [r15], ax
0x18001977c  mov     ecx, 78h ; 'x'; Size
0x180019781  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019786  mov     rsi, rax
0x180019789  test    rax, rax
0x18001978c  jz      loc_180019828
0x180019792  mov     [rax+8], r12
0x180019796  mov     [rax+10h], r12
0x18001979a  lea     rax, ??_7CRun@@6B@; const CRun::`vftable'
0x1800197a1  mov     [rsi], rax
0x1800197a4  mov     rcx, qword ptr [rbp+FileTime2.dwLowDateTime]
0x1800197a8  mov     eax, [rbp+arg_28]
0x1800197ab  mov     [rsi+60h], eax
0x1800197ae  mov     eax, [rbp+arg_30]
0x1800197b1  mov     [rsi+64h], eax
0x1800197b4  movzx   eax, [rbp+arg_38]
0x1800197b8  mov     [rsi+18h], rcx
0x1800197bc  mov     rcx, rsi; this
0x1800197bf  mov     [rsi+68h], ax
0x1800197c3  mov     [rsi+20h], rdi
0x1800197c7  mov     [rsi+28h], rbx
0x1800197cb  mov     [rsi+30h], r12
0x1800197cf  mov     [rsi+38h], r12
0x1800197d3  mov     [rsi+40h], r12d
0x1800197d7  mov     [rsi+48h], r12
0x1800197db  mov     [rsi+50h], r12
0x1800197df  mov     [rsi+58h], r12
0x1800197e3  mov     [rsi+6Ch], r12
0x1800197e7  mov     [rsi+74h], r12d
0x1800197eb  call    ?SetName@CRun@@QEAAJPEBG@Z; CRun::SetName(ushort const *)
0x1800197f0  mov     ebx, eax
0x1800197f2  test    eax, eax
0x1800197f4  jns     short loc_18001980B
0x1800197f6  mov     rcx, [rsi]
0x1800197f9  mov     edx, r13d
0x1800197fc  mov     rax, [rcx]
0x1800197ff  mov     rcx, rsi
0x180019802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019807  mov     eax, ebx
0x180019809  jmp     short loc_18001982D
0x18001980b  mov     rax, [r14+8]
0x18001980f  mov     [rsi+8], rax
0x180019813  mov     [rax+10h], rsi
0x180019817  mov     [r14+8], rsi
0x18001981b  mov     [rsi+10h], r14
0x18001981f  add     [r15], r13w
0x180019823  jmp     loc_180019729
0x180019828  mov     eax, 8007000Eh
0x18001982d  mov     rbx, [rsp+20h+arg_10]
0x180019832  add     rsp, 20h
0x180019836  pop     r15
0x180019838  pop     r14
0x18001983a  pop     r13
0x18001983c  pop     r12
0x18001983e  pop     rdi
0x18001983f  pop     rsi
0x180019840  pop     rbp
0x180019841  retn
```
