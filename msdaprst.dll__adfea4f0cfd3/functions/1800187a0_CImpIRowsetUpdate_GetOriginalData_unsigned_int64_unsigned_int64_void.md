# CImpIRowsetUpdate::GetOriginalData(unsigned __int64,unsigned __int64,void *)

- ea: `0x1800187a0`
- end: `0x180018949`
- name: `?GetOriginalData@CImpIRowsetUpdate@@UEAAJ_K0PEAX@Z`
- size: `425`
- prototype: `int(CImpIRowsetUpdate *__hidden this, unsigned __int64, unsigned __int64, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180016584`
- `0x1800187a0`
- `0x1800214e8`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800187e1`
- `KERNEL32!GetCurrentThreadId` at `0x1800187e1`
- `KERNEL32!LeaveCriticalSection` at `0x180018929`
- `KERNEL32!LeaveCriticalSection` at `0x180018929`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180018806`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180018806`
- `MSDART!UMSEnterCSWraper` at `0x1800187c8`
- `MSDART!UMSEnterCSWraper` at `0x1800187c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIRowsetUpdate::GetOriginalData(
        CImpIRowsetUpdate *this,
        unsigned __int64 a2,
        unsigned __int64 a3,
        char *a4)
{
  __int64 v8; // rbx
  DWORD *v9; // rsi
  __int64 v10; // r12
  int DataArgs; // eax
  unsigned int v12; // edi
  struct tagACCESSOR *v13; // rdi
  unsigned int v14; // r13d
  int v15; // ebp
  __int64 v16; // r9
  int v17; // ecx
  char *v18; // r10
  char *v19; // r8
  char *v20; // rdx
  int v21; // eax
  int v22; // ecx
  __int64 v24; // rcx
  int v26; // [rsp+20h] [rbp-88h]
  struct tagACCESSOR *v27; // [rsp+B0h] [rbp+8h] BYREF

  v8 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v8);
  v9 = (DWORD *)(v8 + 8);
  v10 = 0;
  if ( !*(_DWORD *)(v8 + 12) )
    *v9 = GetCurrentThreadId();
  ++*(_DWORD *)(v8 + 12);
  ++*(_DWORD *)(v8 + 16);
  v27 = 0;
  SetErrorInfo(0, 0);
  DataArgs = CRowset::ValidateGetDataArgs(*((CRowset **)this + 3), a2, a3, a4, &v27);
  if ( DataArgs >= 0 )
  {
    v13 = v27;
    v14 = *((_DWORD *)v27 + 2);
    v15 = 0;
    LODWORD(v27) = 0;
    if ( v14 )
    {
      do
      {
        v16 = 88 * v10;
        v17 = *((_DWORD *)v13 + 22 * v10 + 18);
        if ( (v17 & 1) != 0 )
          v18 = &a4[*(_QWORD *)((char *)v13 + v16 + 24)];
        else
          v18 = 0;
        if ( (v17 & 2) != 0 )
          v19 = &a4[*(_QWORD *)((char *)v13 + v16 + 32)];
        else
          v19 = 0;
        if ( (v17 & 4) != 0 )
          v20 = &a4[*(_QWORD *)((char *)v13 + v16 + 40)];
        else
          v20 = 0;
        LOBYTE(v26) = 1;
        v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int, char *, char *, char *))(**((_QWORD **)this + 3) + 48LL))(
                *((_QWORD *)this + 3),
                *((unsigned int *)v13 + 22 * v10 + 4),
                *(_QWORD *)((char *)v13 + v16 + 88),
                *(unsigned __int16 *)((char *)v13 + v16 + 100),
                v26,
                v20,
                v19,
                v18);
        v22 = v15 + 1;
        if ( !v21 )
          v22 = v15;
        v15 = v22;
        LODWORD(v27) = (_DWORD)v27 + 1;
        ++v10;
      }
      while ( (unsigned int)v27 < v14 );
    }
    v12 = v15 != 0 ? 0x40EDA : 0;
  }
  else
  {
    v12 = Exit(DataArgs, 0);
  }
  --*(_DWORD *)(v8 + 16);
  if ( (*(_DWORD *)(v8 + 12))-- == 1 )
    *v9 = -1;
  v24 = *(_QWORD *)v8;
  --*(_DWORD *)(v24 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v24 + 8));
  return v12;
}

```

## disassembly

```asm
0x1800187a0  push    rbx
0x1800187a2  push    rbp
0x1800187a3  push    rsi
0x1800187a4  push    rdi
0x1800187a5  push    r12
0x1800187a7  push    r13
0x1800187a9  push    r14
0x1800187ab  push    r15
0x1800187ad  sub     rsp, 68h
0x1800187b1  mov     r14, r9
0x1800187b4  mov     rdi, r8
0x1800187b7  mov     rbp, rdx
0x1800187ba  mov     r15, rcx
0x1800187bd  mov     rbx, [rcx+18h]
0x1800187c1  sub     rbx, 0FFFFFFFFFFFFFF80h
0x1800187c5  mov     rcx, rbx
0x1800187c8  call    cs:__imp_UMSEnterCSWraper
0x1800187cf  nop     dword ptr [rax+rax+00h]
0x1800187d4  lea     rsi, [rbx+8]
0x1800187d8  xor     r12d, r12d
0x1800187db  cmp     [rbx+0Ch], r12d
0x1800187df  jnz     short loc_1800187EF
0x1800187e1  call    cs:__imp_GetCurrentThreadId
0x1800187e8  nop     dword ptr [rax+rax+00h]
0x1800187ed  mov     [rsi], eax
0x1800187ef  inc     dword ptr [rbx+0Ch]
0x1800187f2  inc     dword ptr [rbx+10h]
0x1800187f5  mov     [rsp+0A8h+var_50], rbx
0x1800187fa  mov     [rsp+0A8h+arg_0], r12
0x180018802  xor     edx, edx; perrinfo
0x180018804  xor     ecx, ecx; dwReserved
0x180018806  call    cs:__imp_SetErrorInfo
0x18001880d  nop     dword ptr [rax+rax+00h]
0x180018812  lea     rax, [rsp+0A8h+arg_0]
0x18001881a  mov     [rsp+0A8h+var_88], rax; struct tagACCESSOR **
0x18001881f  mov     r9, r14; void *
0x180018822  mov     r8, rdi; unsigned __int64
0x180018825  mov     rdx, rbp; unsigned __int64
0x180018828  mov     rcx, [r15+18h]; this
0x18001882c  call    ?ValidateGetDataArgs@CRowset@@QEAAJ_K0PEAXPEAPEAUtagACCESSOR@@@Z; CRowset::ValidateGetDataArgs(unsigned __int64,unsigned __int64,void *,tagACCESSOR * *)
0x180018831  test    eax, eax
0x180018833  jns     short loc_180018845
0x180018835  xor     edx, edx; unsigned int
0x180018837  mov     ecx, eax; int
0x180018839  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18001883e  mov     edi, eax
0x180018840  jmp     loc_180018912
0x180018845  mov     rdi, [rsp+0A8h+arg_0]
0x18001884d  mov     r13d, [rdi+8]
0x180018851  mov     ebp, r12d
0x180018854  mov     dword ptr [rsp+0A8h+arg_0], r12d
0x18001885c  test    r13d, r13d
0x18001885f  jz      loc_180018908
0x180018865  imul    r9, r12, 58h ; 'X'
0x180018869  mov     eax, [r9+rdi+10h]
0x18001886e  mov     [rsp+0A8h+var_58], eax
0x180018872  mov     ecx, [r9+rdi+48h]
0x180018877  test    cl, 1
0x18001887a  jz      short loc_180018886
0x18001887c  mov     r10, [r9+rdi+18h]
0x180018881  add     r10, r14
0x180018884  jmp     short loc_180018889
0x180018886  xor     r10d, r10d
0x180018889  test    cl, 2
0x18001888c  jz      short loc_180018898
0x18001888e  mov     r8, [r9+rdi+20h]
0x180018893  add     r8, r14
0x180018896  jmp     short loc_18001889B
0x180018898  xor     r8d, r8d
0x18001889b  mov     r11, [r9+rdi+58h]
0x1800188a0  test    cl, 4
0x1800188a3  jz      short loc_1800188AF
0x1800188a5  mov     rdx, [r9+rdi+28h]
0x1800188aa  add     rdx, r14
0x1800188ad  jmp     short loc_1800188B1
0x1800188af  xor     edx, edx
0x1800188b1  mov     rcx, [r15+18h]
0x1800188b5  mov     rax, [rcx]
0x1800188b8  mov     [rsp+0A8h+var_70], r10
0x1800188bd  mov     [rsp+0A8h+var_78], r8
0x1800188c2  mov     [rsp+0A8h+var_80], rdx
0x1800188c7  mov     byte ptr [rsp+0A8h+var_88], 1
0x1800188cc  movzx   r9d, word ptr [r9+rdi+64h]
0x1800188d2  mov     r8, r11
0x1800188d5  mov     edx, [rsp+0A8h+var_58]
0x1800188d9  mov     rax, [rax+30h]
0x1800188dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188e2  lea     ecx, [rbp+1]
0x1800188e5  test    eax, eax
0x1800188e7  cmovz   ecx, ebp
0x1800188ea  mov     ebp, ecx
0x1800188ec  mov     eax, dword ptr [rsp+0A8h+arg_0]
0x1800188f3  inc     eax
0x1800188f5  mov     dword ptr [rsp+0A8h+arg_0], eax
0x1800188fc  inc     r12
0x1800188ff  cmp     eax, r13d
0x180018902  jb      loc_180018865
0x180018908  neg     ebp
0x18001890a  sbb     edi, edi
0x18001890c  and     edi, 40EDAh
0x180018912  or      edx, 0FFFFFFFFh
0x180018915  add     [rbx+10h], edx
0x180018918  add     [rbx+0Ch], edx
0x18001891b  jnz     short loc_18001891F
0x18001891d  mov     [rsi], edx
0x18001891f  mov     rcx, [rbx]
0x180018922  dec     dword ptr [rcx+30h]
0x180018925  add     rcx, 8; lpCriticalSection
0x180018929  call    cs:__imp_LeaveCriticalSection
0x180018930  nop     dword ptr [rax+rax+00h]
0x180018935  mov     eax, edi
0x180018937  add     rsp, 68h
0x18001893b  pop     r15
0x18001893d  pop     r14
0x18001893f  pop     r13
0x180018941  pop     r12
0x180018943  pop     rdi
0x180018944  pop     rsi
0x180018945  pop     rbp
0x180018946  pop     rbx
0x180018947  retn
```
