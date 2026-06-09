# CImpIUpdateInfo::GetPendingColumns(unsigned __int64,unsigned __int64 *,unsigned __int64 * *)

- ea: `0x180023540`
- end: `0x1800236da`
- name: `?GetPendingColumns@CImpIUpdateInfo@@UEAAJ_KPEA_KPEAPEA_K@Z`
- size: `410`
- prototype: `__int64 __fastcall(CImpIUpdateInfo *__hidden this, unsigned __int64, unsigned __int64 *, unsigned __int64 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x1800041ec`
- `0x180016584`
- `0x180023540`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180023580`
- `KERNEL32!GetCurrentThreadId` at `0x180023580`
- `KERNEL32!LeaveCriticalSection` at `0x18002367f`
- `KERNEL32!LeaveCriticalSection` at `0x1800236b4`
- `KERNEL32!LeaveCriticalSection` at `0x18002367f`
- `KERNEL32!LeaveCriticalSection` at `0x1800236b4`
- `ole32!CoTaskMemFree` at `0x180023655`
- `ole32!CoTaskMemFree` at `0x180023655`
- `ole32!CoTaskMemAlloc` at `0x1800235d3`
- `ole32!CoTaskMemAlloc` at `0x1800235d3`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800235a8`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800235a8`
- `MSDART!UMSEnterCSWraper` at `0x18002356a`
- `MSDART!UMSEnterCSWraper` at `0x18002356a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIUpdateInfo::GetPendingColumns(
        CImpIUpdateInfo *this,
        __int64 a2,
        unsigned __int64 *a3,
        LPVOID *a4)
{
  __int64 v7; // rbx
  DWORD *v8; // rdi
  __int64 v9; // r15
  unsigned int v10; // ebp
  unsigned __int64 *v11; // rax
  int v12; // ecx
  __int64 v13; // r11
  unsigned int i; // r10d
  unsigned int v15; // ecx
  bool v16; // zf
  __int64 v17; // rcx
  unsigned int v19; // esi
  __int64 v20; // rcx

  v7 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v7);
  v8 = (DWORD *)(v7 + 8);
  if ( !*(_DWORD *)(v7 + 12) )
    *v8 = GetCurrentThreadId();
  ++*(_DWORD *)(v7 + 12);
  ++*(_DWORD *)(v7 + 16);
  v9 = *((_QWORD *)this + 3);
  v10 = *(_DWORD *)(v9 + 152);
  SetErrorInfo(0, 0);
  if ( !a3 || !a4 )
  {
    v12 = -2147024809;
    goto LABEL_18;
  }
  *a3 = 0;
  v11 = (unsigned __int64 *)CoTaskMemAlloc(8LL * v10);
  *a4 = v11;
  if ( !v11 )
  {
    v12 = -2147024882;
LABEL_18:
    v19 = Exit(v12, 0);
    --*(_DWORD *)(v7 + 16);
    v16 = (*(_DWORD *)(v7 + 12))-- == 1;
    if ( v16 )
      *v8 = -1;
    v20 = *(_QWORD *)v7;
    --*(_DWORD *)(v20 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v20 + 8));
    return v19;
  }
  LODWORD(v13) = 1;
  for ( i = 1; i <= v10; i += v13 )
  {
    v15 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 280LL) + 8LL * i) + 4LL) & 0xFEFFFFFF;
    if ( !v15 || v15 == 3 )
    {
      *((_QWORD *)*a4 + *a3) = CMetaData::mdGetOrdinal((CMetaData *)(v9 + 304), i - v13);
      *a3 += v13;
    }
  }
  if ( !*a3 )
  {
    CoTaskMemFree(*a4);
    *a4 = 0;
  }
  --*(_DWORD *)(v7 + 16);
  v16 = (*(_DWORD *)(v7 + 12))-- == 1;
  if ( v16 )
    *v8 = -1;
  v17 = *(_QWORD *)v7;
  --*(_DWORD *)(v17 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v17 + 8));
  return 0;
}

```

## disassembly

```asm
0x180023540  mov     [rsp+arg_8], rbx
0x180023545  mov     [rsp+arg_10], rbp
0x18002354a  push    rsi
0x18002354b  push    rdi
0x18002354c  push    r13
0x18002354e  push    r14
0x180023550  push    r15
0x180023552  sub     rsp, 20h
0x180023556  mov     rsi, r9
0x180023559  mov     r14, r8
0x18002355c  mov     r13, rcx
0x18002355f  mov     rbx, [rcx+18h]
0x180023563  sub     rbx, 0FFFFFFFFFFFFFF80h
0x180023567  mov     rcx, rbx
0x18002356a  call    cs:__imp_UMSEnterCSWraper
0x180023571  nop     dword ptr [rax+rax+00h]
0x180023576  lea     rdi, [rbx+8]
0x18002357a  cmp     dword ptr [rbx+0Ch], 0
0x18002357e  jnz     short loc_18002358E
0x180023580  call    cs:__imp_GetCurrentThreadId
0x180023587  nop     dword ptr [rax+rax+00h]
0x18002358c  mov     [rdi], eax
0x18002358e  inc     dword ptr [rbx+0Ch]
0x180023591  inc     dword ptr [rbx+10h]
0x180023594  mov     [rsp+48h+arg_0], rbx
0x180023599  mov     r15, [r13+18h]
0x18002359d  mov     ebp, [r15+98h]
0x1800235a4  xor     edx, edx; perrinfo
0x1800235a6  xor     ecx, ecx; dwReserved
0x1800235a8  call    cs:__imp_SetErrorInfo
0x1800235af  nop     dword ptr [rax+rax+00h]
0x1800235b4  test    r14, r14
0x1800235b7  jz      loc_18002368F
0x1800235bd  test    rsi, rsi
0x1800235c0  jz      loc_18002368F
0x1800235c6  mov     qword ptr [r14], 0
0x1800235cd  mov     ecx, ebp
0x1800235cf  shl     rcx, 3; cb
0x1800235d3  call    cs:__imp_CoTaskMemAlloc
0x1800235da  nop     dword ptr [rax+rax+00h]
0x1800235df  mov     [rsi], rax
0x1800235e2  test    rax, rax
0x1800235e5  jnz     short loc_1800235F1
0x1800235e7  mov     ecx, 8007000Eh
0x1800235ec  jmp     loc_180023694
0x1800235f1  mov     r11d, 1
0x1800235f7  mov     r10d, r11d
0x1800235fa  cmp     ebp, r11d
0x1800235fd  jb      short loc_18002364C
0x1800235ff  mov     edx, r10d
0x180023602  mov     rax, [r13+18h]
0x180023606  mov     rcx, [rax+118h]
0x18002360d  mov     rax, [rcx+rdx*8]
0x180023611  mov     ecx, [rax+4]
0x180023614  and     ecx, 0FEFFFFFFh
0x18002361a  jz      short loc_180023621
0x18002361c  cmp     ecx, 3
0x18002361f  jnz     short loc_180023644
0x180023621  movzx   edx, r10w
0x180023625  sub     dx, r11w; unsigned __int16
0x180023629  lea     rcx, [r15+130h]; this
0x180023630  call    ?mdGetOrdinal@CMetaData@@QEAAKG@Z; CMetaData::mdGetOrdinal(ushort)
0x180023635  mov     edx, eax
0x180023637  mov     rcx, [r14]
0x18002363a  mov     rax, [rsi]
0x18002363d  mov     [rax+rcx*8], rdx
0x180023641  add     [r14], r11
0x180023644  add     r10d, r11d
0x180023647  cmp     r10d, ebp
0x18002364a  jbe     short loc_1800235FF
0x18002364c  cmp     qword ptr [r14], 0
0x180023650  jnz     short loc_180023668
0x180023652  mov     rcx, [rsi]; pv
0x180023655  call    cs:__imp_CoTaskMemFree
0x18002365c  nop     dword ptr [rax+rax+00h]
0x180023661  mov     qword ptr [rsi], 0
0x180023668  or      edx, 0FFFFFFFFh
0x18002366b  add     [rbx+10h], edx
0x18002366e  add     [rbx+0Ch], edx
0x180023671  jnz     short loc_180023675
0x180023673  mov     [rdi], edx
0x180023675  mov     rcx, [rbx]
0x180023678  dec     dword ptr [rcx+30h]
0x18002367b  add     rcx, 8; lpCriticalSection
0x18002367f  call    cs:__imp_LeaveCriticalSection
0x180023686  nop     dword ptr [rax+rax+00h]
0x18002368b  xor     eax, eax
0x18002368d  jmp     short loc_1800236C2
0x18002368f  mov     ecx, 80070057h; int
0x180023694  xor     edx, edx; unsigned int
0x180023696  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18002369b  mov     esi, eax
0x18002369d  or      edx, 0FFFFFFFFh
0x1800236a0  add     [rbx+10h], edx
0x1800236a3  add     [rbx+0Ch], edx
0x1800236a6  jnz     short loc_1800236AA
0x1800236a8  mov     [rdi], edx
0x1800236aa  mov     rcx, [rbx]
0x1800236ad  dec     dword ptr [rcx+30h]
0x1800236b0  add     rcx, 8; lpCriticalSection
0x1800236b4  call    cs:__imp_LeaveCriticalSection
0x1800236bb  nop     dword ptr [rax+rax+00h]
0x1800236c0  mov     eax, esi
0x1800236c2  mov     rbx, [rsp+48h+arg_8]
0x1800236c7  mov     rbp, [rsp+48h+arg_10]
0x1800236cc  add     rsp, 20h
0x1800236d0  pop     r15
0x1800236d2  pop     r14
0x1800236d4  pop     r13
0x1800236d6  pop     rdi
0x1800236d7  pop     rsi
0x1800236d8  retn
```
