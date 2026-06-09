# UTSemReadWrite::UnlockRead(void)

- ea: `0x180004f48`
- end: `0x18000513c`
- name: `?UnlockRead@UTSemReadWrite@@QEAAXXZ`
- size: `500`
- prototype: `void __fastcall(UTSemReadWrite *__hidden this)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004c10`
- `0x1800204e0`
- `0x180020690`
- `0x180021760`
- `0x1800218b0`
- `0x180022040`

## callees

- `0x180004f48`
- `0x180009098`
- `0x18000b1e8`
- `0x180031aa8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800050ea`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800050ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050f4`

## string_xrefs

- `0x180004f63`: `Problem with Reader info in UTSemReadWrite::UnlockRead`
- `0x180004f6c`: `com\complus\src\shared\util\utsem.cpp`
- `0x180004ffe`: `Problem with WriteWatier info in UTSemReadWrite::UnlockRead`
- `0x180005077`: `Problem with WriteWatier info in UTSemReadWrite::UnlockRead`
- `0x1800050cc`: `Problem with WriteWatier info in UTSemReadWrite::UnlockRead`
- `0x180004fc4`: `Problem with Writer info in UTSemReadWrite::UnlockRead`
- `0x180005100`: `SetEvent failed in UTSemReadWrite:UnlockRead`

## pseudocode

```c
void __fastcall UTSemReadWrite::UnlockRead(UTSemReadWrite *this)
{
  signed __int32 v1; // ebx
  bool v2; // zf
  unsigned int v3; // eax
  void *v4; // rax
  DWORD LastError; // eax
  unsigned __int16 v6; // r8
  unsigned int v7; // r9d
  const void *v8; // [rsp+28h] [rbp-58h]
  unsigned int v9; // [rsp+30h] [rbp-50h]
  int v10; // [rsp+38h] [rbp-48h]
  int v11; // [rsp+40h] [rbp-40h]
  int v12; // [rsp+50h] [rbp-30h] BYREF
  __int16 v13; // [rsp+54h] [rbp-2Ch]
  int v14; // [rsp+58h] [rbp-28h]
  unsigned __int16 *v15; // [rsp+60h] [rbp-20h]
  __int64 v16; // [rsp+68h] [rbp-18h]
  __int64 v17; // [rsp+70h] [rbp-10h]
  int v18; // [rsp+78h] [rbp-8h]
  int v19; // [rsp+7Ch] [rbp-4h]

  if ( (dword_180072D84 & 0x3FF) == 0 )
  {
    v12 = 0;
    v13 = 21;
    v14 = -1073606063;
    v15 = L"Problem with Reader info in UTSemReadWrite::UnlockRead";
    v16 = 0;
    v17 = 0;
    v19 = 1;
    v18 = 1;
    CError::WriteToLog(
      (CError *)&v12,
      L"com\\complus\\src\\shared\\util\\utsem.cpp",
      0x1E2u,
      L"Problem with Reader info in UTSemReadWrite::UnlockRead");
  }
  if ( (dword_180072D84 & 0xC00) != 0 )
  {
    v12 = 0;
    v15 = L"Problem with Writer info in UTSemReadWrite::UnlockRead";
    v13 = 21;
    v14 = -1073606063;
    v16 = 0;
    v17 = 0;
    v19 = 1;
    v18 = 1;
    CError::WriteToLog(
      (CError *)&v12,
      L"com\\complus\\src\\shared\\util\\utsem.cpp",
      0x1E4u,
      L"Problem with Writer info in UTSemReadWrite::UnlockRead");
  }
  do
  {
    while ( 1 )
    {
      v1 = dword_180072D84;
      if ( dword_180072D84 != 1 )
        break;
      v2 = _InterlockedCompareExchange(&dword_180072D84, 0, 1) == 1;
LABEL_9:
      if ( v2 )
        return;
    }
    v3 = dword_180072D84 & 0x3FF;
    if ( v3 > 1 )
    {
      v2 = v1 == _InterlockedCompareExchange(&dword_180072D84, dword_180072D84 - 1, dword_180072D84);
      goto LABEL_9;
    }
    if ( v3 != 1 )
    {
      v12 = 0;
      v13 = 21;
      v14 = -1073606063;
      v15 = L"Problem with Reader info in UTSemReadWrite::UnlockRead";
      v16 = 0;
      v17 = 0;
      v19 = 1;
      v18 = 1;
      CError::WriteToLog(
        (CError *)&v12,
        L"com\\complus\\src\\shared\\util\\utsem.cpp",
        0x1F9u,
        L"Problem with Reader info in UTSemReadWrite::UnlockRead");
    }
    if ( (v1 & 0xFFC00000) == 0 )
    {
      v15 = L"Problem with WriteWatier info in UTSemReadWrite::UnlockRead";
      v12 = 0;
      v13 = 21;
      v14 = -1073606063;
      v16 = 0;
      v17 = 0;
      v19 = 1;
      v18 = 1;
      CError::WriteToLog(
        (CError *)&v12,
        L"com\\complus\\src\\shared\\util\\utsem.cpp",
        0x1FBu,
        L"Problem with WriteWatier info in UTSemReadWrite::UnlockRead");
    }
  }
  while ( v1 != _InterlockedCompareExchange(&dword_180072D84, v1 - 4193281, v1) );
  v4 = UTSemReadWrite::GetWriteWaiterEvent((UTSemReadWrite *)&g_semRW);
  if ( !SetEvent(v4) )
  {
    LastError = GetLastError();
    CErrorWin32::CErrorWin32(
      (CErrorWin32 *)&v12,
      LastError,
      v6,
      v7,
      L"SetEvent failed in UTSemReadWrite:UnlockRead",
      v8,
      v9,
      v10,
      v11);
    v18 = 1;
    CError::WriteToLog((CError *)&v12, L"com\\complus\\src\\shared\\util\\utsem.cpp", 0x204u, v15);
  }
}

```

## disassembly

```asm
0x180004f48  push    rbp
0x180004f4a  push    rbx
0x180004f4b  push    rsi
0x180004f4c  push    rdi
0x180004f4d  push    r12
0x180004f4f  push    r13
0x180004f51  push    r14
0x180004f53  mov     rbp, rsp
0x180004f56  sub     rsp, 80h
0x180004f5d  mov     eax, cs:dword_180072D84
0x180004f63  lea     r13, aProblemWithRea; "Problem with Reader info in UTSemReadWr"...
0x180004f6a  xor     esi, esi
0x180004f6c  lea     r14, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x180004f73  lea     r12d, [rsi+15h]
0x180004f77  lea     edi, [rsi+1]
0x180004f7a  test    eax, 3FFh
0x180004f7f  jnz     short loc_180004FB7
0x180004f81  mov     r9, r13; unsigned __int16 *
0x180004f84  mov     [rbp+var_30], esi
0x180004f87  mov     r8d, 1E2h; unsigned int
0x180004f8d  mov     [rbp+var_2C], r12w
0x180004f92  mov     rdx, r14; unsigned __int16 *
0x180004f95  mov     [rbp+var_28], 0C0021251h
0x180004f9c  lea     rcx, [rbp+var_30]; this
0x180004fa0  mov     [rbp+var_20], r13
0x180004fa4  mov     [rbp+var_18], rsi
0x180004fa8  mov     [rbp+var_10], rsi
0x180004fac  mov     [rbp+var_4], edi
0x180004faf  mov     [rbp+var_8], edi
0x180004fb2  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180004fb7  mov     eax, cs:dword_180072D84
0x180004fbd  test    eax, 0C00h
0x180004fc2  jz      short loc_180004FFE
0x180004fc4  lea     r9, aProblemWithWri; "Problem with Writer info in UTSemReadWr"...
0x180004fcb  mov     [rbp+var_30], esi
0x180004fce  mov     r8d, 1E4h; unsigned int
0x180004fd4  mov     [rbp+var_20], r9
0x180004fd8  mov     rdx, r14; unsigned __int16 *
0x180004fdb  mov     [rbp+var_2C], r12w
0x180004fe0  lea     rcx, [rbp+var_30]; this
0x180004fe4  mov     [rbp+var_28], 0C0021251h
0x180004feb  mov     [rbp+var_18], rsi
0x180004fef  mov     [rbp+var_10], rsi
0x180004ff3  mov     [rbp+var_4], edi
0x180004ff6  mov     [rbp+var_8], edi
0x180004ff9  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180004ffe  lea     rcx, aProblemWithWri_1; "Problem with WriteWatier info in UTSemR"...
0x180005005  mov     ebx, cs:dword_180072D84
0x18000500b  cmp     ebx, edi
0x18000500d  jnz     short loc_18000501D
0x18000500f  mov     ecx, esi
0x180005011  mov     eax, edi
0x180005013  lock cmpxchg cs:dword_180072D84, ecx
0x18000501b  jmp     short loc_180005037
0x18000501d  mov     eax, ebx
0x18000501f  and     eax, 3FFh
0x180005024  cmp     eax, edi
0x180005026  jbe     short loc_18000503F
0x180005028  lea     ecx, [rbx-1]
0x18000502b  mov     eax, ebx
0x18000502d  lock cmpxchg cs:dword_180072D84, ecx
0x180005035  cmp     ebx, eax
0x180005037  jz      loc_18000512A
0x18000503d  jmp     short loc_180004FFE
0x18000503f  jz      short loc_18000507E
0x180005041  mov     r9, r13; unsigned __int16 *
0x180005044  mov     [rbp+var_30], esi
0x180005047  mov     r8d, 1F9h; unsigned int
0x18000504d  mov     [rbp+var_2C], r12w
0x180005052  mov     rdx, r14; unsigned __int16 *
0x180005055  mov     [rbp+var_28], 0C0021251h
0x18000505c  lea     rcx, [rbp+var_30]; this
0x180005060  mov     [rbp+var_20], r13
0x180005064  mov     [rbp+var_18], rsi
0x180005068  mov     [rbp+var_10], rsi
0x18000506c  mov     [rbp+var_4], edi
0x18000506f  mov     [rbp+var_8], edi
0x180005072  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180005077  lea     rcx, aProblemWithWri_1; "Problem with WriteWatier info in UTSemR"...
0x18000507e  test    ebx, 0FFC00000h
0x180005084  jnz     short loc_1800050BC
0x180005086  mov     [rbp+var_20], rcx
0x18000508a  mov     r9, rcx; unsigned __int16 *
0x18000508d  lea     rcx, [rbp+var_30]; this
0x180005091  mov     [rbp+var_30], esi
0x180005094  mov     r8d, 1FBh; unsigned int
0x18000509a  mov     [rbp+var_2C], r12w
0x18000509f  mov     rdx, r14; unsigned __int16 *
0x1800050a2  mov     [rbp+var_28], 0C0021251h
0x1800050a9  mov     [rbp+var_18], rsi
0x1800050ad  mov     [rbp+var_10], rsi
0x1800050b1  mov     [rbp+var_4], edi
0x1800050b4  mov     [rbp+var_8], edi
0x1800050b7  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x1800050bc  lea     ecx, [rbx-3FFC01h]
0x1800050c2  mov     eax, ebx
0x1800050c4  lock cmpxchg cs:dword_180072D84, ecx
0x1800050cc  lea     rcx, aProblemWithWri_1; "Problem with WriteWatier info in UTSemR"...
0x1800050d3  cmp     ebx, eax
0x1800050d5  jnz     loc_180005005
0x1800050db  lea     rcx, ?g_semRW@@3VUTSemReadWrite@@A; this
0x1800050e2  call    ?GetWriteWaiterEvent@UTSemReadWrite@@AEAAPEAXXZ; UTSemReadWrite::GetWriteWaiterEvent(void)
0x1800050e7  mov     rcx, rax; hEvent
0x1800050ea  call    cs:__imp_SetEvent
0x1800050f0  test    eax, eax
0x1800050f2  jnz     short loc_18000512A
0x1800050f4  call    cs:__imp_GetLastError
0x1800050fa  mov     edx, eax; unsigned int
0x1800050fc  lea     rcx, [rbp+var_30]; this
0x180005100  lea     rax, aSeteventFailed; "SetEvent failed in UTSemReadWrite:Unloc"...
0x180005107  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x18000510c  call    ??0CErrorWin32@@QEAA@KGKPEBGPEBXIHH@Z; CErrorWin32::CErrorWin32(ulong,ushort,ulong,ushort const *,void const *,uint,int,int)
0x180005111  mov     r9, [rbp+var_20]; unsigned __int16 *
0x180005115  lea     rcx, [rbp+var_30]; this
0x180005119  mov     r8d, 204h; unsigned int
0x18000511f  mov     [rbp+var_8], edi
0x180005122  mov     rdx, r14; unsigned __int16 *
0x180005125  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000512a  add     rsp, 80h
0x180005131  pop     r14
0x180005133  pop     r13
0x180005135  pop     r12
0x180005137  pop     rdi
0x180005138  pop     rsi
0x180005139  pop     rbx
0x18000513a  pop     rbp
0x18000513b  retn
```
