# CWrappedDocFile::FindGreaterEntry(CDfName const *,SIterBuffer *,tagSTATSTG *)

- ea: `0x180022338`
- end: `0x180022686`
- name: `?FindGreaterEntry@CWrappedDocFile@@QEAAJPEBVCDfName@@PEAUSIterBuffer@@PEAUtagSTATSTG@@@Z`
- size: `846`
- prototype: `int(CWrappedDocFile *__hidden this, const struct CDfName *, struct SIterBuffer *, struct tagSTATSTG *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002200c`

## callees

- `0x18000e940`
- `0x180021fb0`
- `0x18002200c`
- `0x1800222fc`
- `0x180022338`
- `0x180022d8c`
- `0x180022e30`
- `0x18003fa80`
- `0x18003fc30`
- `0x180042800`
- `0x18006141c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002254a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002261f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002264a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002254a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002261f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002264a`

## pseudocode

```c
__int64 __fastcall CWrappedDocFile::FindGreaterEntry(
        CWrappedDocFile *this,
        const struct CDfName *a2,
        struct SIterBuffer *a3,
        struct tagSTATSTG *a4)
{
  char *v4; // r12
  __int64 v6; // rsi
  __int64 i; // rdx
  _QWORD *ReservedForOle; // rcx
  __int64 v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rcx
  unsigned __int16 v15; // bx
  __int64 v16; // rdx
  PDocFile *v17; // rcx
  int GreaterEntry; // eax
  unsigned int v19; // ebx
  unsigned __int16 v20; // bp
  __int64 v22; // rdx
  __int64 v23; // rcx
  PTSetMember *Name; // rax
  void *v25; // rsi
  int v26; // eax
  __int64 v27; // rdx
  PTSetMember *v28; // rcx
  _BYTE v29[64]; // [rsp+20h] [rbp-A8h] BYREF
  unsigned __int16 v30; // [rsp+60h] [rbp-68h]

  v4 = (char *)this + 128;
  v6 = 0;
  for ( i = *((_QWORD *)this + 16); i; i = *(_QWORD *)(v12 + 152) )
  {
    ReservedForOle = NtCurrentTeb()->ReservedForOle;
    v12 = i + *ReservedForOle;
    if ( !v12 )
      break;
    if ( (!*(_WORD *)(v12 + 130) || *(_WORD *)(v12 + 64))
      && !(unsigned int)CUpdateList::IsEntry(v4, i + *ReservedForOle, 0)
      && (int)CDirectory::NameCompare((const struct CDfName *)v12, a2) > 0
      && (!v6 || (int)CDirectory::NameCompare((const struct CDfName *)v12, (const struct CDfName *)v6) <= 0) )
    {
      v6 = v12;
    }
  }
  v13 = *((_QWORD *)this + 15);
  if ( v13 )
    v14 = v13 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
  else
    v14 = 0;
  if ( v14 )
  {
    v15 = *((_WORD *)a2 + 32);
    if ( v15 > 0x40u )
      v15 = 64;
    memcpy_0(v29, a2, v15);
    v30 = v15;
    while ( 1 )
    {
      v16 = *((_QWORD *)this + 15);
      if ( v16 )
        v17 = (PDocFile *)(v16 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
      else
        v17 = 0;
      GreaterEntry = PDocFile::FindGreaterEntry(v17, (const struct CDfName *)v29, a3, a4);
      v19 = GreaterEntry;
      if ( GreaterEntry < 0 )
      {
        if ( GreaterEntry != -2147287022 )
          return v19;
        goto LABEL_22;
      }
      if ( a3 )
      {
        v20 = *((_WORD *)a3 + 32);
        if ( v20 > 0x40u )
          v20 = 64;
        memcpy_0(v29, a3, v20);
        v30 = v20;
      }
      else
      {
        CDfName::Set((CDfName *)v29, *(const unsigned __int16 **)a4);
      }
      if ( (unsigned int)CUpdateList::IsEntry(v4, v29, 0) != 1 )
        break;
      if ( a4 )
      {
        CoTaskMemFree(*(LPVOID *)a4);
        *(_QWORD *)a4 = 0;
      }
    }
    if ( !v6 || (int)CDirectory::NameCompare((const struct CDfName *)v29, (const struct CDfName *)v6) < 0 )
    {
      if ( a4 )
      {
        v22 = *((_QWORD *)this + 26);
        v23 = v22 ? v22 + *(_QWORD *)NtCurrentTeb()->ReservedForOle : 0LL;
        Name = CTSSet::FindName((CTSSet *)(v23 + 104), (const struct CDfName *)v29, *((_DWORD *)this + 9));
        if ( Name )
        {
          v25 = *(void **)a4;
          v19 = PTSetMember::Stat(Name, a4, 1u);
          if ( (v19 & 0x80000000) == 0 )
            *(_QWORD *)a4 = v25;
          else
            CoTaskMemFree(v25);
        }
      }
      return v19;
    }
    if ( !a4 )
      goto LABEL_56;
    CoTaskMemFree(*(LPVOID *)a4);
  }
  else
  {
LABEL_22:
    if ( !v6 )
      return (unsigned int)-2147287022;
    if ( !a4 )
    {
LABEL_56:
      CDfName::Set(a3, (const struct CDfName *)v6);
      *((_DWORD *)a3 + 17) = *(_DWORD *)(v6 + 136) & 3;
      return 0;
    }
  }
  if ( *(_WORD *)(v6 + 130) )
  {
    v26 = CWrappedDocFile::StatEntry(this, (const struct CDfName *)v6, a3, a4);
  }
  else
  {
    v27 = *(_QWORD *)(v6 + 144);
    if ( v27 )
      v28 = (PTSetMember *)(v27 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
    else
      v28 = 0;
    v26 = PTSetMember::Stat(v28, a4, 0);
  }
  v19 = v26;
  if ( v26 >= 0 )
    return 0;
  return v19;
}

```

## disassembly

```asm
0x180022338  push    rbx
0x18002233a  push    rbp
0x18002233b  push    rsi
0x18002233c  push    rdi
0x18002233d  push    r12
0x18002233f  push    r13
0x180022341  push    r14
0x180022343  push    r15
0x180022345  sub     rsp, 88h
0x18002234c  mov     rax, cs:__security_cookie
0x180022353  xor     rax, rsp
0x180022356  mov     [rsp+0C8h+var_58], rax
0x18002235b  xor     r13d, r13d
0x18002235e  lea     r12, [rcx+80h]
0x180022365  mov     rbp, rdx
0x180022368  mov     esi, r13d
0x18002236b  mov     rdx, [r12]
0x18002236f  mov     rdi, r9
0x180022372  mov     r14, r8
0x180022375  mov     r15, rcx
0x180022378  test    rdx, rdx
0x18002237b  jz      short loc_180022399
0x18002237d  mov     rax, gs:30h
0x180022386  mov     rcx, [rax+1758h]
0x18002238d  mov     rbx, [rcx]
0x180022390  add     rbx, rdx
0x180022393  jnz     loc_1800224B7
0x180022399  mov     rdx, [r15+78h]
0x18002239d  test    rdx, rdx
0x1800223a0  jz      loc_1800224E4
0x1800223a6  mov     rax, gs:30h
0x1800223af  mov     rcx, [rax+1758h]
0x1800223b6  mov     rcx, [rcx]
0x1800223b9  add     rcx, rdx
0x1800223bc  test    rcx, rcx
0x1800223bf  jz      loc_1800224A7
0x1800223c5  movzx   ebx, word ptr [rbp+40h]
0x1800223c9  mov     eax, 40h ; '@'
0x1800223ce  cmp     bx, ax
0x1800223d1  jbe     short loc_1800223D6
0x1800223d3  movzx   ebx, ax
0x1800223d6  movzx   r8d, bx; Size
0x1800223da  lea     rcx, [rsp+0C8h+var_A8]; void *
0x1800223df  mov     rdx, rbp; Src
0x1800223e2  call    memcpy_0
0x1800223e7  mov     [rsp+0C8h+var_68], bx
0x1800223ec  mov     rdx, [r15+78h]
0x1800223f0  test    rdx, rdx
0x1800223f3  jz      loc_1800224DC
0x1800223f9  mov     rax, gs:30h
0x180022402  mov     rcx, [rax+1758h]
0x180022409  mov     rcx, [rcx]
0x18002240c  add     rcx, rdx; this
0x18002240f  mov     r9, rdi; struct tagSTATSTG *
0x180022412  lea     rdx, [rsp+0C8h+var_A8]; struct CDfName *
0x180022417  mov     r8, r14; struct SIterBuffer *
0x18002241a  call    ?FindGreaterEntry@PDocFile@@QEAAJPEBVCDfName@@PEAUSIterBuffer@@PEAUtagSTATSTG@@@Z; PDocFile::FindGreaterEntry(CDfName const *,SIterBuffer *,tagSTATSTG *)
0x18002241f  mov     ebx, eax
0x180022421  test    eax, eax
0x180022423  js      short loc_1800224A0
0x180022425  test    r14, r14
0x180022428  jz      loc_180022601
0x18002242e  movzx   ebp, word ptr [r14+40h]
0x180022433  mov     eax, 40h ; '@'
0x180022438  cmp     bp, ax
0x18002243b  jbe     short loc_180022440
0x18002243d  movzx   ebp, ax
0x180022440  movzx   r8d, bp; Size
0x180022444  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180022449  mov     rdx, r14; Src
0x18002244c  call    memcpy_0
0x180022451  mov     [rsp+0C8h+var_68], bp
0x180022456  xor     r8d, r8d
0x180022459  lea     rdx, [rsp+0C8h+var_A8]
0x18002245e  mov     rcx, r12
0x180022461  call    ?IsEntry@CUpdateList@@QEAA?AW4UlIsEntry@@PEBVCDfName@@PEAPEAVCUpdate@@@Z; CUpdateList::IsEntry(CDfName const *,CUpdate * *)
0x180022466  cmp     eax, 1
0x180022469  jz      loc_180022613
0x18002246f  test    rsi, rsi
0x180022472  jnz     loc_18002262D
0x180022478  test    rdi, rdi
0x18002247b  jnz     short loc_1800224EC
0x18002247d  mov     eax, ebx
0x18002247f  mov     rcx, [rsp+0C8h+var_58]
0x180022484  xor     rcx, rsp; StackCookie
0x180022487  call    __security_check_cookie
0x18002248c  add     rsp, 88h
0x180022493  pop     r15
0x180022495  pop     r14
0x180022497  pop     r13
0x180022499  pop     r12
0x18002249b  pop     rdi
0x18002249c  pop     rsi
0x18002249d  pop     rbp
0x18002249e  pop     rbx
0x18002249f  retn
0x1800224a0  cmp     eax, 80030012h
0x1800224a5  jnz     short loc_18002247D
0x1800224a7  test    rsi, rsi
0x1800224aa  jnz     loc_18002265D
0x1800224b0  mov     ebx, 80030012h
0x1800224b5  jmp     short loc_18002247D
0x1800224b7  cmp     [rbx+82h], r13w
0x1800224bf  jz      loc_1800225B8
0x1800224c5  cmp     [rbx+40h], r13w
0x1800224ca  jnz     loc_1800225B8
0x1800224d0  mov     rdx, [rbx+98h]
0x1800224d7  jmp     loc_180022378
0x1800224dc  mov     rcx, r13
0x1800224df  jmp     loc_18002240F
0x1800224e4  mov     rcx, r13
0x1800224e7  jmp     loc_1800223BC
0x1800224ec  mov     rdx, [r15+0D0h]
0x1800224f3  test    rdx, rdx
0x1800224f6  jz      short loc_180022555
0x1800224f8  mov     rax, gs:30h
0x180022501  mov     rcx, [rax+1758h]
0x180022508  mov     rcx, [rcx]
0x18002250b  add     rcx, rdx
0x18002250e  mov     r8d, [r15+24h]; unsigned int
0x180022512  lea     rdx, [rsp+0C8h+var_A8]; struct CDfName *
0x180022517  add     rcx, 68h ; 'h'; this
0x18002251b  call    ?FindName@CTSSet@@QEAAPEAVPTSetMember@@PEBVCDfName@@K@Z; CTSSet::FindName(CDfName const *,ulong)
0x180022520  test    rax, rax
0x180022523  jz      loc_18002247D
0x180022529  mov     rsi, [rdi]
0x18002252c  mov     r8d, 1; unsigned int
0x180022532  mov     rdx, rdi; struct tagSTATSTG *
0x180022535  mov     rcx, rax; this
0x180022538  call    ?Stat@PTSetMember@@QEAAJPEAUtagSTATSTG@@K@Z; PTSetMember::Stat(tagSTATSTG *,ulong)
0x18002253d  mov     ebx, eax
0x18002253f  test    eax, eax
0x180022541  jns     loc_180022655
0x180022547  mov     rcx, rsi; pv
0x18002254a  call    cs:__imp_CoTaskMemFree
0x180022550  jmp     loc_18002247D
0x180022555  mov     rcx, r13
0x180022558  jmp     short loc_18002250E
0x18002255a  cmp     [rsi+82h], r13w
0x180022562  jz      short loc_180022584
0x180022564  mov     r9, rdi; struct tagSTATSTG *
0x180022567  mov     r8, r14; struct SIterBuffer *
0x18002256a  mov     rdx, rsi; struct CDfName *
0x18002256d  mov     rcx, r15; this
0x180022570  call    ?StatEntry@CWrappedDocFile@@QEAAJPEBVCDfName@@PEAUSIterBuffer@@PEAUtagSTATSTG@@@Z; CWrappedDocFile::StatEntry(CDfName const *,SIterBuffer *,tagSTATSTG *)
0x180022575  mov     ebx, eax
0x180022577  test    eax, eax
0x180022579  js      loc_18002247D
0x18002257f  jmp     loc_18002267E
0x180022584  mov     rdx, [rsi+90h]
0x18002258b  test    rdx, rdx
0x18002258e  jz      short loc_1800225B3
0x180022590  mov     rax, gs:30h
0x180022599  mov     rcx, [rax+1758h]
0x1800225a0  mov     rcx, [rcx]
0x1800225a3  add     rcx, rdx; this
0x1800225a6  xor     r8d, r8d; unsigned int
0x1800225a9  mov     rdx, rdi; struct tagSTATSTG *
0x1800225ac  call    ?Stat@PTSetMember@@QEAAJPEAUtagSTATSTG@@K@Z; PTSetMember::Stat(tagSTATSTG *,ulong)
0x1800225b1  jmp     short loc_180022575
0x1800225b3  mov     rcx, r13
0x1800225b6  jmp     short loc_1800225A6
0x1800225b8  xor     r8d, r8d
0x1800225bb  mov     rdx, rbx
0x1800225be  mov     rcx, r12
0x1800225c1  call    ?IsEntry@CUpdateList@@QEAA?AW4UlIsEntry@@PEBVCDfName@@PEAPEAVCUpdate@@@Z; CUpdateList::IsEntry(CDfName const *,CUpdate * *)
0x1800225c6  test    eax, eax
0x1800225c8  jnz     loc_1800224D0
0x1800225ce  mov     rdx, rbp; struct CDfName *
0x1800225d1  mov     rcx, rbx; struct CDfName *
0x1800225d4  call    ?NameCompare@CDirectory@@SAHPEBVCDfName@@0@Z; CDirectory::NameCompare(CDfName const *,CDfName const *)
0x1800225d9  test    eax, eax
0x1800225db  jle     loc_1800224D0
0x1800225e1  test    rsi, rsi
0x1800225e4  jz      short loc_1800225F9
0x1800225e6  mov     rdx, rsi; struct CDfName *
0x1800225e9  mov     rcx, rbx; struct CDfName *
0x1800225ec  call    ?NameCompare@CDirectory@@SAHPEBVCDfName@@0@Z; CDirectory::NameCompare(CDfName const *,CDfName const *)
0x1800225f1  test    eax, eax
0x1800225f3  jg      loc_1800224D0
0x1800225f9  mov     rsi, rbx
0x1800225fc  jmp     loc_1800224D0
0x180022601  mov     rdx, [rdi]; unsigned __int16 *
0x180022604  lea     rcx, [rsp+0C8h+var_A8]; this
0x180022609  call    ?Set@CDfName@@QEAAXPEBG@Z; CDfName::Set(ushort const *)
0x18002260e  jmp     loc_180022456
0x180022613  test    rdi, rdi
0x180022616  jz      loc_1800223EC
0x18002261c  mov     rcx, [rdi]; pv
0x18002261f  call    cs:__imp_CoTaskMemFree
0x180022625  mov     [rdi], r13
0x180022628  jmp     loc_1800223EC
0x18002262d  mov     rdx, rsi; struct CDfName *
0x180022630  lea     rcx, [rsp+0C8h+var_A8]; struct CDfName *
0x180022635  call    ?NameCompare@CDirectory@@SAHPEBVCDfName@@0@Z; CDirectory::NameCompare(CDfName const *,CDfName const *)
0x18002263a  test    eax, eax
0x18002263c  js      loc_180022478
0x180022642  test    rdi, rdi
0x180022645  jz      short loc_180022666
0x180022647  mov     rcx, [rdi]; pv
0x18002264a  call    cs:__imp_CoTaskMemFree
0x180022650  jmp     loc_18002255A
0x180022655  mov     [rdi], rsi
0x180022658  jmp     loc_18002247D
0x18002265d  test    rdi, rdi
0x180022660  jnz     loc_18002255A
0x180022666  mov     rdx, rsi; struct CDfName *
0x180022669  mov     rcx, r14; this
0x18002266c  call    ?Set@CDfName@@QEAAXPEBV1@@Z; CDfName::Set(CDfName const *)
0x180022671  mov     eax, [rsi+88h]
0x180022677  and     eax, 3
0x18002267a  mov     [r14+44h], eax
0x18002267e  mov     ebx, r13d
0x180022681  jmp     loc_18002247D
```
