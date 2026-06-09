# CImpIRowset::GetData(unsigned __int64,unsigned __int64,void *)

- ea: `0x180017d30`
- end: `0x180018005`
- name: `?GetData@CImpIRowset@@UEAAJ_K0PEAX@Z`
- size: `725`
- prototype: `int(CImpIRowset *__hidden this, unsigned __int64, unsigned __int64, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800023c0`
- `0x180016584`
- `0x180017d30`
- `0x18001b008`
- `0x1800214e8`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180017d6e`
- `KERNEL32!GetCurrentThreadId` at `0x180017d6e`
- `KERNEL32!LeaveCriticalSection` at `0x180017dea`
- `KERNEL32!LeaveCriticalSection` at `0x180017fe5`
- `KERNEL32!LeaveCriticalSection` at `0x180017dea`
- `KERNEL32!LeaveCriticalSection` at `0x180017fe5`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180017d97`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180017d97`
- `MSDART!UMSEnterCSWraper` at `0x180017d58`
- `MSDART!UMSEnterCSWraper` at `0x180017d58`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIRowset::GetData(CImpIRowset *this, unsigned __int64 a2, unsigned __int64 a3, char *a4)
{
  __int64 v8; // rbx
  DWORD *v9; // rsi
  int DataArgs; // eax
  int v11; // ecx
  unsigned int v12; // ebp
  bool v13; // zf
  __int64 v14; // rcx
  struct tagACCESSOR *v16; // rbp
  int v17; // r15d
  unsigned int v18; // r12d
  __int64 v19; // rax
  __int64 v20; // r9
  int v21; // ecx
  char *v22; // r11
  char *v23; // r10
  __int64 v24; // r8
  char *v25; // rdx
  unsigned int BidObjectID; // eax
  unsigned int v27; // eax
  wchar_t *v28; // r8
  char *v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rcx
  int v32; // [rsp+20h] [rbp-98h]
  unsigned int v33; // [rsp+50h] [rbp-68h]
  __int64 v34; // [rsp+58h] [rbp-60h]
  struct tagACCESSOR *v35; // [rsp+C0h] [rbp+8h] BYREF

  v8 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v8);
  v9 = (DWORD *)(v8 + 8);
  if ( !*(_DWORD *)(v8 + 12) )
    *v9 = GetCurrentThreadId();
  ++*(_DWORD *)(v8 + 12);
  ++*(_DWORD *)(v8 + 16);
  v35 = 0;
  SetErrorInfo(0, 0);
  DataArgs = CRowset::ValidateGetDataArgs(*((CRowset **)this + 3), a2, a3, a4, &v35);
  if ( DataArgs < 0 )
  {
    v11 = DataArgs;
LABEL_5:
    v12 = Exit(v11, 0);
    goto LABEL_6;
  }
  if ( *(_DWORD *)((unsigned int)(*(_DWORD *)(*((_QWORD *)this + 3) + 220LL) * a2)
                 + *(_QWORD *)(*((_QWORD *)this + 3) + 224LL)
                 + 28LL) == 4 )
  {
    v11 = -2147217885;
    goto LABEL_5;
  }
  v16 = v35;
  v33 = *((_DWORD *)v35 + 2);
  v17 = 0;
  v18 = 0;
  if ( v33 )
  {
    v19 = 0;
    v34 = 0;
    do
    {
      v20 = 88 * v19;
      LODWORD(v35) = *((_DWORD *)v16 + 22 * v19 + 4);
      v21 = *((_DWORD *)v16 + 22 * v19 + 18);
      if ( (v21 & 1) != 0 )
        v22 = &a4[*(_QWORD *)((char *)v16 + v20 + 24)];
      else
        v22 = 0;
      if ( (v21 & 2) != 0 )
        v23 = &a4[*(_QWORD *)((char *)v16 + v20 + 32)];
      else
        v23 = 0;
      v24 = *(unsigned int *)((char *)v16 + v20 + 88);
      if ( v24 != *(_QWORD *)((char *)v16 + v20 + 88) )
        v24 = 0xFFFFFFFFLL;
      if ( (v21 & 4) != 0 )
        v25 = &a4[*(_QWORD *)((char *)v16 + v20 + 40)];
      else
        v25 = 0;
      LOBYTE(v32) = 0;
      LODWORD(v35) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, int, char *, char *, char *))(**((_QWORD **)this + 3) + 48LL))(
                       *((_QWORD *)this + 3),
                       (unsigned int)v35,
                       v24,
                       *(unsigned __int16 *)((char *)v16 + v20 + 100),
                       v32,
                       v25,
                       v23,
                       v22);
      if ( (_DWORD)v35 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049B18[0] )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CImpIRowset *)((char *)this + 32));
          bidTraceW(off_180049290[0], 110592, off_180049B18[0], BidObjectID, (_DWORD)v35);
        }
        ++v17;
      }
      ++v18;
      v19 = ++v34;
    }
    while ( v18 < v33 );
    if ( v17 )
    {
      if ( v33 == v17 )
      {
        v12 = -2147217887;
        if ( (bidGblFlags & 2) != 0 && off_180049B10[0] )
        {
          v27 = CBidGenericBase::GetBidObjectID((CImpIRowset *)((char *)this + 32));
          v28 = off_180049B10[0];
          v29 = off_180049288[0];
          v30 = 121856;
LABEL_35:
          bidTraceW(v29, v30, v28, v27, v12);
        }
      }
      else
      {
        v12 = 265946;
        if ( (bidGblFlags & 2) != 0 && off_180049B08[0] )
        {
          v27 = CBidGenericBase::GetBidObjectID((CImpIRowset *)((char *)this + 32));
          v28 = off_180049B08[0];
          v29 = off_180049280[0];
          v30 = 126976;
          goto LABEL_35;
        }
      }
LABEL_6:
      --*(_DWORD *)(v8 + 16);
      v13 = (*(_DWORD *)(v8 + 12))-- == 1;
      if ( v13 )
        *v9 = -1;
      v14 = *(_QWORD *)v8;
      --*(_DWORD *)(v14 + 48);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 8));
      return v12;
    }
  }
  --*(_DWORD *)(v8 + 16);
  v13 = (*(_DWORD *)(v8 + 12))-- == 1;
  if ( v13 )
    *v9 = -1;
  v31 = *(_QWORD *)v8;
  --*(_DWORD *)(v31 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v31 + 8));
  return 0;
}

```

## disassembly

```asm
0x180017d30  push    rbx
0x180017d32  push    rbp
0x180017d33  push    rsi
0x180017d34  push    rdi
0x180017d35  push    r12
0x180017d37  push    r13
0x180017d39  push    r14
0x180017d3b  push    r15
0x180017d3d  sub     rsp, 78h
0x180017d41  mov     r13, r9
0x180017d44  mov     rbp, r8
0x180017d47  mov     rdi, rdx
0x180017d4a  mov     r14, rcx
0x180017d4d  mov     rbx, [rcx+18h]
0x180017d51  sub     rbx, 0FFFFFFFFFFFFFF80h
0x180017d55  mov     rcx, rbx
0x180017d58  call    cs:__imp_UMSEnterCSWraper
0x180017d5f  nop     dword ptr [rax+rax+00h]
0x180017d64  lea     rsi, [rbx+8]
0x180017d68  cmp     dword ptr [rbx+0Ch], 0
0x180017d6c  jnz     short loc_180017D7C
0x180017d6e  call    cs:__imp_GetCurrentThreadId
0x180017d75  nop     dword ptr [rax+rax+00h]
0x180017d7a  mov     [rsi], eax
0x180017d7c  inc     dword ptr [rbx+0Ch]
0x180017d7f  inc     dword ptr [rbx+10h]
0x180017d82  mov     [rsp+0B8h+var_58], rbx
0x180017d87  mov     [rsp+0B8h+arg_0], 0
0x180017d93  xor     edx, edx; perrinfo
0x180017d95  xor     ecx, ecx; dwReserved
0x180017d97  call    cs:__imp_SetErrorInfo
0x180017d9e  nop     dword ptr [rax+rax+00h]
0x180017da3  lea     rax, [rsp+0B8h+arg_0]
0x180017dab  mov     [rsp+0B8h+var_98], rax; struct tagACCESSOR **
0x180017db0  mov     r9, r13; void *
0x180017db3  mov     r8, rbp; unsigned __int64
0x180017db6  mov     rdx, rdi; unsigned __int64
0x180017db9  mov     rcx, [r14+18h]; this
0x180017dbd  call    ?ValidateGetDataArgs@CRowset@@QEAAJ_K0PEAXPEAPEAUtagACCESSOR@@@Z; CRowset::ValidateGetDataArgs(unsigned __int64,unsigned __int64,void *,tagACCESSOR * *)
0x180017dc2  test    eax, eax
0x180017dc4  jns     short loc_180017DFD
0x180017dc6  mov     ecx, eax; int
0x180017dc8  xor     edx, edx; unsigned int
0x180017dca  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180017dcf  mov     ebp, eax
0x180017dd1  mov     edi, 0FFFFFFFFh
0x180017dd6  add     [rbx+10h], edi
0x180017dd9  add     [rbx+0Ch], edi
0x180017ddc  jnz     short loc_180017DE0
0x180017dde  mov     [rsi], edi
0x180017de0  mov     rcx, [rbx]
0x180017de3  dec     dword ptr [rcx+30h]
0x180017de6  add     rcx, 8; lpCriticalSection
0x180017dea  call    cs:__imp_LeaveCriticalSection
0x180017df1  nop     dword ptr [rax+rax+00h]
0x180017df6  mov     eax, ebp
0x180017df8  jmp     loc_180017FF3
0x180017dfd  mov     rax, [r14+18h]
0x180017e01  imul    edi, [rax+0DCh]
0x180017e08  mov     rax, [rax+0E0h]
0x180017e0f  cmp     dword ptr [rdi+rax+1Ch], 4
0x180017e14  jnz     short loc_180017E1D
0x180017e16  mov     ecx, 80040E23h
0x180017e1b  jmp     short loc_180017DC8
0x180017e1d  mov     rbp, [rsp+0B8h+arg_0]
0x180017e25  mov     edx, [rbp+8]
0x180017e28  mov     [rsp+0B8h+var_68], edx
0x180017e2c  xor     r15d, r15d
0x180017e2f  xor     r12d, r12d
0x180017e32  mov     edi, 0FFFFFFFFh
0x180017e37  test    edx, edx
0x180017e39  jz      loc_180017FD1
0x180017e3f  xor     eax, eax
0x180017e41  mov     [rsp+0B8h+var_60], rax
0x180017e46  imul    r9, rax, 58h ; 'X'
0x180017e4a  mov     eax, [r9+rbp+10h]
0x180017e4f  mov     dword ptr [rsp+0B8h+arg_0], eax
0x180017e56  mov     ecx, [r9+rbp+48h]
0x180017e5b  test    cl, 1
0x180017e5e  jz      short loc_180017E6A
0x180017e60  mov     r11, [r9+rbp+18h]
0x180017e65  add     r11, r13
0x180017e68  jmp     short loc_180017E6D
0x180017e6a  xor     r11d, r11d
0x180017e6d  test    cl, 2
0x180017e70  jz      short loc_180017E7C
0x180017e72  mov     r10, [r9+rbp+20h]
0x180017e77  add     r10, r13
0x180017e7a  jmp     short loc_180017E7F
0x180017e7c  xor     r10d, r10d
0x180017e7f  mov     r8d, [r9+rbp+58h]
0x180017e84  cmp     r8, [r9+rbp+58h]
0x180017e89  cmovnz  r8, rdi
0x180017e8d  test    cl, 4
0x180017e90  jz      short loc_180017E9C
0x180017e92  mov     rdx, [r9+rbp+28h]
0x180017e97  add     rdx, r13
0x180017e9a  jmp     short loc_180017E9E
0x180017e9c  xor     edx, edx
0x180017e9e  mov     rcx, [r14+18h]
0x180017ea2  mov     rax, [rcx]
0x180017ea5  mov     [rsp+0B8h+var_80], r11
0x180017eaa  mov     [rsp+0B8h+var_88], r10
0x180017eaf  mov     [rsp+0B8h+var_90], rdx
0x180017eb4  mov     byte ptr [rsp+0B8h+var_98], 0
0x180017eb9  movzx   r9d, word ptr [r9+rbp+64h]
0x180017ebf  mov     edx, dword ptr [rsp+0B8h+arg_0]
0x180017ec6  mov     rax, [rax+30h]
0x180017eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ecf  mov     dword ptr [rsp+0B8h+arg_0], eax
0x180017ed6  test    eax, eax
0x180017ed8  jz      short loc_180017F26
0x180017eda  test    byte ptr cs:_bidGblFlags, 2
0x180017ee1  jz      short loc_180017F23
0x180017ee3  mov     rcx, cs:off_180049B18; "<CImpIRowset::GetData|ERR|PERSIST> %u#,"...
0x180017eea  test    rcx, rcx
0x180017eed  jz      short loc_180017F23
0x180017eef  lea     rcx, [r14+20h]; this
0x180017ef3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180017ef8  mov     r8, cs:off_180049B18; "<CImpIRowset::GetData|ERR|PERSIST> %u#,"...
0x180017eff  mov     rcx, cs:off_180049290; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180017f06  mov     dword ptr [rsp+0B8h+var_90], r12d
0x180017f0b  mov     edx, dword ptr [rsp+0B8h+arg_0]
0x180017f12  mov     dword ptr [rsp+0B8h+var_98], edx
0x180017f16  mov     r9d, eax
0x180017f19  mov     edx, 1B000h
0x180017f1e  call    _bidTraceW
0x180017f23  inc     r15d
0x180017f26  inc     r12d
0x180017f29  mov     rax, [rsp+0B8h+var_60]
0x180017f2e  inc     rax
0x180017f31  mov     [rsp+0B8h+var_60], rax
0x180017f36  mov     edx, [rsp+0B8h+var_68]
0x180017f3a  cmp     r12d, edx
0x180017f3d  jb      loc_180017E46
0x180017f43  test    r15d, r15d
0x180017f46  jz      loc_180017FD1
0x180017f4c  cmp     edx, r15d
0x180017f4f  jnz     short loc_180017F99
0x180017f51  mov     ebp, 80040E21h
0x180017f56  test    byte ptr cs:_bidGblFlags, 2
0x180017f5d  jz      short loc_180017F94
0x180017f5f  mov     rax, cs:off_180049B10; "<CImpIRowset::GetData|ERR|PERSIST> %u#,"...
0x180017f66  test    rax, rax
0x180017f69  jz      short loc_180017F94
0x180017f6b  lea     rcx, [r14+20h]; this
0x180017f6f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180017f74  mov     r8, cs:off_180049B10; "<CImpIRowset::GetData|ERR|PERSIST> %u#,"...
0x180017f7b  mov     rcx, cs:off_180049288; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180017f82  mov     edx, 1DC00h
0x180017f87  mov     r9d, eax
0x180017f8a  mov     dword ptr [rsp+0B8h+var_98], ebp
0x180017f8e  call    _bidTraceW
0x180017f93  nop
0x180017f94  jmp     loc_180017DD6
0x180017f99  mov     ebp, 40EDAh
0x180017f9e  test    byte ptr cs:_bidGblFlags, 2
0x180017fa5  jz      short loc_180017F94
0x180017fa7  mov     rax, cs:off_180049B08; "<CImpIRowset::GetData|ERR|PERSIST> %u#,"...
0x180017fae  test    rax, rax
0x180017fb1  jz      short loc_180017F94
0x180017fb3  lea     rcx, [r14+20h]; this
0x180017fb7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180017fbc  mov     r8, cs:off_180049B08; "<CImpIRowset::GetData|ERR|PERSIST> %u#,"...
0x180017fc3  mov     rcx, cs:off_180049280; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180017fca  mov     edx, 1F000h
0x180017fcf  jmp     short loc_180017F87
0x180017fd1  add     [rbx+10h], edi
0x180017fd4  add     [rbx+0Ch], edi
0x180017fd7  jnz     short loc_180017FDB
0x180017fd9  mov     [rsi], edi
0x180017fdb  mov     rcx, [rbx]
0x180017fde  dec     dword ptr [rcx+30h]
0x180017fe1  add     rcx, 8; lpCriticalSection
0x180017fe5  call    cs:__imp_LeaveCriticalSection
0x180017fec  nop     dword ptr [rax+rax+00h]
0x180017ff1  xor     eax, eax
0x180017ff3  add     rsp, 78h
0x180017ff7  pop     r15
0x180017ff9  pop     r14
0x180017ffb  pop     r13
0x180017ffd  pop     r12
0x180017fff  pop     rdi
0x180018000  pop     rsi
0x180018001  pop     rbp
0x180018002  pop     rbx
0x180018003  retn
```
