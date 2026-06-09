# CManagerThread::SetBackupMoratorium(ulong)

- ea: `0x1800096c0`
- end: `0x180009771`
- name: `?SetBackupMoratorium@CManagerThread@@QEAAXK@Z`
- size: `177`
- prototype: `void __fastcall(CManagerThread *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008180`

## callees

- `0x1800062b0`
- `0x1800092b0`
- `0x1800096c0`
- `0x18000ca14`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000976a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800096ef`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800096ef`

## pseudocode

```c
void __fastcall CManagerThread::SetBackupMoratorium(CManagerThread *this, unsigned int a2)
{
  __int64 v2; // rbx
  _QWORD *v3; // rax
  __int64 v4; // rcx
  int v5; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+8h] BYREF

  SystemTimeAsFileTime = (struct _FILETIME)this;
  v2 = a2;
  if ( a2 == -1 )
  {
    _InterlockedExchange64(&qword_1800199B0, -1);
  }
  else
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    _InterlockedExchange64(&qword_1800199B0, *(_QWORD *)&SystemTimeAsFileTime + 10000 * v2);
  }
  if ( (dword_180019A78 & 1) == 0 )
  {
    v3 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&SystemTimeAsFileTime);
    v5 = CManagerThread::StopConfig(v4, v3, 0);
    if ( v5 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        90,
        &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
        (unsigned int)v5);
  }
  SetEvent(hEvent);
}

```

## disassembly

```asm
0x1800096c0  mov     qword ptr [rsp+SystemTimeAsFileTime.dwLowDateTime], rcx
0x1800096c5  push    rbx
0x1800096c6  sub     rsp, 30h
0x1800096ca  mov     ebx, edx
0x1800096cc  cmp     ebx, 0FFFFFFFFh
0x1800096cf  jnz     short loc_1800096E1
0x1800096d1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800096d8  xchg    rax, cs:qword_1800199B0
0x1800096df  jmp     short loc_180009708
0x1800096e1  mov     qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800096ea  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800096ef  call    cs:__imp_GetSystemTimeAsFileTime
0x1800096f5  imul    rcx, rbx, 2710h
0x1800096fc  add     rcx, qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime]
0x180009701  xchg    rcx, cs:qword_1800199B0
0x180009708  test    byte ptr cs:dword_180019A78, 1
0x18000970f  jnz     short loc_18000975C
0x180009711  lea     rcx, [rsp+38h+SystemTimeAsFileTime]
0x180009716  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000971b  xor     r8d, r8d
0x18000971e  mov     rdx, rax
0x180009721  call    ?StopConfig@CManagerThread@@QEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; CManagerThread::StopConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int)
0x180009726  test    eax, eax
0x180009728  jns     short loc_18000975C
0x18000972a  lea     rdx, WPP_GLOBAL_Control
0x180009731  mov     rcx, cs:WPP_GLOBAL_Control
0x180009738  cmp     rcx, rdx
0x18000973b  jz      short loc_18000975C
0x18000973d  test    byte ptr [rcx+1Ch], 1
0x180009741  jz      short loc_18000975C
0x180009743  mov     edx, 5Ah ; 'Z'
0x180009748  mov     r9d, eax
0x18000974b  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180009752  mov     rcx, [rcx+10h]
0x180009756  call    WPP_SF_d
0x18000975b  nop
0x18000975c  jmp     short $+2
0x18000975e  mov     rcx, cs:hEvent
0x180009765  add     rsp, 30h
0x180009769  pop     rbx
0x18000976a  jmp     cs:__imp_SetEvent
```
