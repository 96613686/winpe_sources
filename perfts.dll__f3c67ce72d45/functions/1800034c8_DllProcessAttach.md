# DllProcessAttach

- ea: `0x1800034c8`
- end: `0x1800035fc`
- name: `DllProcessAttach`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180003450`

## callees

- `0x1800034c8`
- `0x180003604`
- `0x180003a40`
- `0x1800098f6`
- `0x180009930`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x18000357a`
- `ntdll!NtQuerySystemInformation` at `0x18000357a`
- `KERNEL32!GetProcessHeap` at `0x1800034de`
- `KERNEL32!GetProcessHeap` at `0x1800034de`
- `ADVAPI32!DeregisterEventSource` at `0x18000352b`
- `ADVAPI32!DeregisterEventSource` at `0x18000352b`

## pseudocode

```c
__int64 DllProcessAttach()
{
  bool v1; // sf
  int v2; // eax
  __int64 v3; // r8
  __int64 v4; // rdx
  _QWORD *v5; // rcx
  ULONG ReturnLength[4]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE SystemInformation[64]; // [rsp+30h] [rbp-58h] BYREF

  hLibHeap = GetProcessHeap();
  if ( !hLibHeap )
    return 0;
  if ( !hEventLog )
    hEventLog = MonOpenEventLog();
  if ( (int)GetDescriptionOffset() < 0 )
  {
    if ( hEventLog )
    {
      if ( !--dwLogUsers )
        DeregisterEventSource(hEventLog);
      hEventLog = 0;
    }
    return 0;
  }
  dword_18001222C += dword_180012AB0;
  dword_180012234 += dword_180012AB0;
  ReturnLength[0] = 0;
  memset_0(SystemInformation, 0, sizeof(SystemInformation));
  v1 = NtQuerySystemInformation(SystemBasicInformation, SystemInformation, 0x40u, ReturnLength) < 0;
  v2 = SystemInformation[56];
  if ( v1 )
    v2 = 1;
  dword_180012AB4 = v2;
  v3 = 0;
  v4 = 0;
  *((_QWORD *)&UsedList + 1) = &UsedList;
  *(_QWORD *)&UsedList = &UsedList;
  *((_QWORD *)&UnusedList + 1) = &UnusedList;
  *(_QWORD *)&UnusedList = &UnusedList;
  do
  {
    v5 = (_QWORD *)((char *)&DefaultWinStationHashBuckets + v4);
    ++v3;
    *(_QWORD *)((char *)&DefaultWinStationHashBuckets + v4 + 8) = (char *)&DefaultWinStationHashBuckets + v4;
    v4 += 16;
    *v5 = v5;
  }
  while ( v3 != 4 );
  return 1;
}

```

## disassembly

```asm
0x1800034c8  sub     rsp, 88h
0x1800034cf  mov     rax, cs:__security_cookie
0x1800034d6  xor     rax, rsp
0x1800034d9  mov     [rsp+88h+var_18], rax
0x1800034de  call    cs:__imp_GetProcessHeap
0x1800034e4  mov     cs:hLibHeap, rax
0x1800034eb  test    rax, rax
0x1800034ee  jnz     short loc_1800034F7
0x1800034f0  xor     eax, eax
0x1800034f2  jmp     loc_1800035E7
0x1800034f7  cmp     cs:hEventLog, 0
0x1800034ff  jnz     short loc_18000350D
0x180003501  call    MonOpenEventLog
0x180003506  mov     cs:hEventLog, rax
0x18000350d  call    GetDescriptionOffset
0x180003512  test    eax, eax
0x180003514  jns     short loc_18000353E
0x180003516  mov     rcx, cs:hEventLog; hEventLog
0x18000351d  test    rcx, rcx
0x180003520  jz      short loc_1800034F0
0x180003522  add     cs:dwLogUsers, 0FFFFFFFFh
0x180003529  jnz     short loc_180003531
0x18000352b  call    cs:__imp_DeregisterEventSource
0x180003531  mov     cs:hEventLog, 0
0x18000353c  jmp     short loc_1800034F0
0x18000353e  mov     eax, cs:dword_180012AB0
0x180003544  lea     rcx, [rsp+88h+SystemInformation]; void *
0x180003549  add     cs:dword_18001222C, eax
0x18000354f  xor     edx, edx; Val
0x180003551  add     cs:dword_180012234, eax
0x180003557  mov     [rsp+88h+ReturnLength], 0
0x18000355f  lea     r8d, [rdx+40h]; Size
0x180003563  call    memset_0
0x180003568  lea     r9, [rsp+88h+ReturnLength]; ReturnLength
0x18000356d  mov     r8d, 40h ; '@'; SystemInformationLength
0x180003573  lea     rdx, [rsp+88h+SystemInformation]; SystemInformation
0x180003578  xor     ecx, ecx; SystemInformationClass
0x18000357a  call    cs:__imp_NtQuerySystemInformation
0x180003580  test    eax, eax
0x180003582  movsx   eax, [rsp+88h+var_20]
0x180003587  jns     short loc_18000358E
0x180003589  mov     eax, 1
0x18000358e  mov     cs:dword_180012AB4, eax
0x180003594  xor     r8d, r8d
0x180003597  lea     rax, UsedList
0x18000359e  xor     edx, edx
0x1800035a0  mov     qword ptr cs:UsedList+8, rax
0x1800035a7  mov     qword ptr cs:UsedList, rax
0x1800035ae  lea     rax, UnusedList
0x1800035b5  mov     qword ptr cs:UnusedList+8, rax
0x1800035bc  mov     qword ptr cs:UnusedList, rax
0x1800035c3  lea     rax, DefaultWinStationHashBuckets
0x1800035ca  lea     rcx, [rdx+rax]
0x1800035ce  inc     r8
0x1800035d1  mov     [rdx+rax+8], rcx
0x1800035d6  lea     rdx, [rdx+10h]
0x1800035da  mov     [rcx], rcx
0x1800035dd  cmp     r8, 4
0x1800035e1  jnz     short loc_1800035CA
0x1800035e3  lea     eax, [r8-3]
0x1800035e7  mov     rcx, [rsp+88h+var_18]
0x1800035ec  xor     rcx, rsp; StackCookie
0x1800035ef  call    __security_check_cookie
0x1800035f4  add     rsp, 88h
0x1800035fb  retn
```
