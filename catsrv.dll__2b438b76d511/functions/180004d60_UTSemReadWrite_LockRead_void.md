# UTSemReadWrite::LockRead(void)

- ea: `0x180004d60`
- end: `0x180004f41`
- name: `?LockRead@UTSemReadWrite@@QEAAXXZ`
- size: `481`
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

- `0x180004d60`
- `0x180009098`
- `0x18000b1e8`
- `0x1800319f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004e2d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004e2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e3c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180004dcb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180004de6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180004dcb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180004de6`

## string_xrefs

- `0x180004e5f`: `com\complus\src\shared\util\utsem.cpp`
- `0x180004e9d`: `com\complus\src\shared\util\utsem.cpp`
- `0x180004efc`: `com\complus\src\shared\util\utsem.cpp`
- `0x180004e49`: `WaitForSingleObject failed in UTSemReadWrite:LockRead`
- `0x180004e83`: `Problem with Reader info in UTSemReadWrite::LockRead`
- `0x180004ee2`: `Problem with Writer info in UTSemReadWrite::LockRead`

## pseudocode

```c
void __fastcall UTSemReadWrite::LockRead(UTSemReadWrite *this)
{
  unsigned int v1; // ebx
  int v2; // ecx
  unsigned int v3; // eax
  void *WaiterSemaphore; // rax
  DWORD LastError; // eax
  unsigned __int16 v6; // r8
  unsigned int v7; // r9d
  const void *v8; // [rsp+28h] [rbp-60h]
  unsigned int v9; // [rsp+30h] [rbp-58h]
  int v10; // [rsp+38h] [rbp-50h]
  int v11; // [rsp+40h] [rbp-48h]
  int v12; // [rsp+50h] [rbp-38h] BYREF
  __int16 v13; // [rsp+54h] [rbp-34h]
  int v14; // [rsp+58h] [rbp-30h]
  unsigned __int16 *v15; // [rsp+60h] [rbp-28h]
  __int64 v16; // [rsp+68h] [rbp-20h]
  __int64 v17; // [rsp+70h] [rbp-18h]
  int v18; // [rsp+78h] [rbp-10h]
  int v19; // [rsp+7Ch] [rbp-Ch]

  v1 = 0;
  do
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v2 = dword_180072D84;
        if ( (unsigned int)dword_180072D84 >= 0x3FF )
          break;
        if ( v2 == _InterlockedCompareExchange(&dword_180072D84, dword_180072D84 + 1, dword_180072D84) )
          goto LABEL_4;
      }
      if ( (dword_180072D84 & 0x3FF) != 0x3FF && (dword_180072D84 & 0x3FF000) != 0x3FF000 )
        break;
      Sleep(0x3E8u);
    }
    v3 = v1++;
  }
  while ( v3 < g_semRW || v2 != _InterlockedCompareExchange(&dword_180072D84, dword_180072D84 + 4096, dword_180072D84) );
  WaiterSemaphore = UTSemReadWrite::GetReadWaiterSemaphore((UTSemReadWrite *)&g_semRW);
  if ( WaitForSingleObject(WaiterSemaphore, 0xFFFFFFFF) == -1 )
  {
    LastError = GetLastError();
    CErrorWin32::CErrorWin32(
      (CErrorWin32 *)&v12,
      LastError,
      v6,
      v7,
      L"WaitForSingleObject failed in UTSemReadWrite:LockRead",
      v8,
      v9,
      v10,
      v11);
    v18 = 1;
    CError::WriteToLog((CError *)&v12, L"com\\complus\\src\\shared\\util\\utsem.cpp", 0x165u, v15);
  }
LABEL_4:
  if ( (dword_180072D84 & 0x3FF) == 0 )
  {
    v12 = 0;
    v15 = L"Problem with Reader info in UTSemReadWrite::LockRead";
    v13 = 21;
    v14 = -1073606063;
    v16 = 0;
    v17 = 0;
    v19 = 1;
    v18 = 1;
    CError::WriteToLog(
      (CError *)&v12,
      L"com\\complus\\src\\shared\\util\\utsem.cpp",
      0x16Fu,
      L"Problem with Reader info in UTSemReadWrite::LockRead");
  }
  if ( (dword_180072D84 & 0xC00) != 0 )
  {
    v12 = 0;
    v15 = L"Problem with Writer info in UTSemReadWrite::LockRead";
    v13 = 21;
    v14 = -1073606063;
    v16 = 0;
    v17 = 0;
    v19 = 1;
    v18 = 1;
    CError::WriteToLog(
      (CError *)&v12,
      L"com\\complus\\src\\shared\\util\\utsem.cpp",
      0x171u,
      L"Problem with Writer info in UTSemReadWrite::LockRead");
  }
}

```

## disassembly

```asm
0x180004d60  push    rbx
0x180004d62  sub     rsp, 80h
0x180004d69  xor     ebx, ebx
0x180004d6b  mov     ecx, cs:dword_180072D84
0x180004d71  mov     eax, ecx
0x180004d73  cmp     ecx, 3FFh
0x180004d79  jnb     short loc_180004DBA
0x180004d7b  lea     edx, [rcx+1]
0x180004d7e  lock cmpxchg cs:dword_180072D84, edx
0x180004d86  cmp     ecx, eax
0x180004d88  jnz     short loc_180004D6B
0x180004d8a  mov     eax, cs:dword_180072D84
0x180004d90  mov     ebx, 15h
0x180004d95  test    eax, 3FFh
0x180004d9a  jz      loc_180004E83
0x180004da0  mov     eax, cs:dword_180072D84
0x180004da6  test    eax, 0C00h
0x180004dab  jnz     loc_180004EE2
0x180004db1  add     rsp, 80h
0x180004db8  pop     rbx
0x180004db9  retn
0x180004dba  and     eax, 3FFh
0x180004dbf  cmp     eax, 3FFh
0x180004dc4  jnz     short loc_180004DD3
0x180004dc6  mov     ecx, 3E8h; dwMilliseconds
0x180004dcb  call    cs:__imp_Sleep
0x180004dd1  jmp     short loc_180004D6B
0x180004dd3  mov     eax, ecx
0x180004dd5  and     eax, 3FF000h
0x180004dda  cmp     eax, 3FF000h
0x180004ddf  jnz     short loc_180004DF1
0x180004de1  mov     ecx, 3E8h; dwMilliseconds
0x180004de6  call    cs:__imp_Sleep
0x180004dec  jmp     loc_180004D6B
0x180004df1  mov     eax, ebx
0x180004df3  inc     ebx
0x180004df5  cmp     eax, cs:?g_semRW@@3VUTSemReadWrite@@A; UTSemReadWrite g_semRW
0x180004dfb  jb      loc_180004D6B
0x180004e01  lea     edx, [rcx+1000h]
0x180004e07  mov     eax, ecx
0x180004e09  lock cmpxchg cs:dword_180072D84, edx
0x180004e11  cmp     ecx, eax
0x180004e13  jnz     loc_180004D6B
0x180004e19  lea     rcx, ?g_semRW@@3VUTSemReadWrite@@A; this
0x180004e20  call    ?GetReadWaiterSemaphore@UTSemReadWrite@@AEAAPEAXXZ; UTSemReadWrite::GetReadWaiterSemaphore(void)
0x180004e25  mov     rcx, rax; hHandle
0x180004e28  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180004e2d  call    cs:__imp_WaitForSingleObject
0x180004e33  cmp     eax, 0FFFFFFFFh
0x180004e36  jnz     loc_180004D8A
0x180004e3c  call    cs:__imp_GetLastError
0x180004e42  mov     edx, eax; unsigned int
0x180004e44  lea     rcx, [rsp+88h+var_38]; this
0x180004e49  lea     rax, aWaitforsingleo_0; "WaitForSingleObject failed in UTSemRead"...
0x180004e50  mov     [rsp+88h+var_68], rax; unsigned __int16 *
0x180004e55  call    ??0CErrorWin32@@QEAA@KGKPEBGPEBXIHH@Z; CErrorWin32::CErrorWin32(ulong,ushort,ulong,ushort const *,void const *,uint,int,int)
0x180004e5a  mov     r9, [rsp+88h+var_28]; unsigned __int16 *
0x180004e5f  lea     rdx, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x180004e66  mov     r8d, 165h; unsigned int
0x180004e6c  mov     [rsp+88h+var_10], 1
0x180004e74  lea     rcx, [rsp+88h+var_38]; this
0x180004e79  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180004e7e  jmp     loc_180004D8A
0x180004e83  lea     r9, aProblemWithRea_1; "Problem with Reader info in UTSemReadWr"...
0x180004e8a  mov     [rsp+88h+var_38], 0
0x180004e92  mov     r8d, 16Fh; unsigned int
0x180004e98  mov     [rsp+88h+var_28], r9
0x180004e9d  lea     rdx, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x180004ea4  mov     [rsp+88h+var_34], bx
0x180004ea9  lea     rcx, [rsp+88h+var_38]; this
0x180004eae  mov     [rsp+88h+var_30], 0C0021251h
0x180004eb6  mov     [rsp+88h+var_20], 0
0x180004ebf  mov     [rsp+88h+var_18], 0
0x180004ec8  mov     [rsp+88h+var_C], 1
0x180004ed0  mov     [rsp+88h+var_10], 1
0x180004ed8  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180004edd  jmp     loc_180004DA0
0x180004ee2  lea     r9, aProblemWithWri_3; "Problem with Writer info in UTSemReadWr"...
0x180004ee9  mov     [rsp+88h+var_38], 0
0x180004ef1  mov     r8d, 171h; unsigned int
0x180004ef7  mov     [rsp+88h+var_28], r9
0x180004efc  lea     rdx, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x180004f03  mov     [rsp+88h+var_34], bx
0x180004f08  lea     rcx, [rsp+88h+var_38]; this
0x180004f0d  mov     [rsp+88h+var_30], 0C0021251h
0x180004f15  mov     [rsp+88h+var_20], 0
0x180004f1e  mov     [rsp+88h+var_18], 0
0x180004f27  mov     [rsp+88h+var_C], 1
0x180004f2f  mov     [rsp+88h+var_10], 1
0x180004f37  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180004f3c  jmp     loc_180004DB1
```
