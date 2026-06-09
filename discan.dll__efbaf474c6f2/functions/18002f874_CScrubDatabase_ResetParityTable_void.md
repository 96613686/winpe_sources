# CScrubDatabase::ResetParityTable(void)

- ea: `0x18002f874`
- end: `0x18002f9da`
- name: `?ResetParityTable@CScrubDatabase@@QEAAJXZ`
- size: `358`
- prototype: `__int64 __fastcall(CScrubDatabase *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001e49c`

## callees

- `0x1800032f8`
- `0x180006498`
- `0x180006688`
- `0x18002eb28`
- `0x18002f874`

## import_xrefs

- `ESENT!JetCloseTable` at `0x18002f92b`
- `ESENT!JetCloseTable` at `0x18002f92b`
- `ESENT!JetDeleteTableW` at `0x18002f97b`
- `ESENT!JetDeleteTableW` at `0x18002f97b`

## pseudocode

```c
__int64 __fastcall CScrubDatabase::ResetParityTable(CScrubDatabase *this)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v3; // r8
  JET_TABLEID v4; // rdx
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // ebx
  const char *v9; // [rsp+40h] [rbp-18h] BYREF
  unsigned int ParityTable; // [rsp+48h] [rbp-10h]

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v9 = "CScrubDatabase::ResetParityTable";
  v3 = ThreadLocalStoragePointer[tls_index];
  *(_QWORD *)(v3 + 16) = "CScrubDatabase::ResetParityTable";
  ++*(_WORD *)(v3 + 8);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrubDatabase::ResetParityTable");
  }
  v4 = *((_QWORD *)this + 3);
  if ( v4 )
  {
    v5 = JetCloseTable(*((_QWORD *)this + 1), v4);
    if ( v5
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids, v5);
    }
    *((_QWORD *)this + 3) = 0;
  }
  v6 = JetDeleteTableW(*((_QWORD *)this + 1), *((_DWORD *)this + 4), ParityTable::TableName);
  if ( v6
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids, v6);
  }
  ParityTable = CScrubDatabase::CreateParityTable(this);
  v7 = ParityTable;
  CHResultImp::~CHResultImp((CHResultImp *)&v9);
  return v7;
}

```

## disassembly

```asm
0x18002f874  mov     r11, rsp
0x18002f877  mov     [r11+8], rbx
0x18002f87b  push    rsi
0x18002f87c  sub     rsp, 50h
0x18002f880  mov     edx, cs:_tls_index
0x18002f886  lea     r9, aCscrubdatabase_0; "CScrubDatabase::ResetParityTable"
0x18002f88d  mov     rax, gs:58h
0x18002f896  mov     rbx, rcx
0x18002f899  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18002f8a0  mov     [r11-18h], r9
0x18002f8a4  mov     r8, [rax+rdx*8]
0x18002f8a8  mov     eax, 10h
0x18002f8ad  mov     edx, 8
0x18002f8b2  mov     [rax+r8], r9
0x18002f8b6  movzx   eax, cx
0x18002f8b9  inc     word ptr [rdx+r8]
0x18002f8be  movzx   edx, word ptr [rdx+r8]
0x18002f8c3  cmp     dx, cx
0x18002f8c6  cmovb   ax, dx
0x18002f8ca  cmovb   cx, dx
0x18002f8ce  mov     [rsp+58h+var_28], ax
0x18002f8d3  xor     eax, eax
0x18002f8d5  mov     [rsp+58h+var_24], eax
0x18002f8d9  mov     rax, cs:off_180047060; "                                       "...
0x18002f8e0  mov     [rsp+58h+var_26], cx
0x18002f8e5  mov     [r11-20h], rax
0x18002f8e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f8f0  lea     rsi, WPP_GLOBAL_Control
0x18002f8f7  cmp     rcx, rsi
0x18002f8fa  jz      short loc_18002F91E
0x18002f8fc  test    byte ptr [rcx+1Ch], 1
0x18002f900  jz      short loc_18002F91E
0x18002f902  cmp     byte ptr [rcx+19h], 5
0x18002f906  jb      short loc_18002F91E
0x18002f908  mov     rcx, [rcx+10h]; LoggerHandle
0x18002f90c  mov     edx, 0Dh
0x18002f911  mov     [r11-38h], r9
0x18002f915  lea     r9, [r11-28h]
0x18002f919  call    WPP_SF_aZs
0x18002f91e  mov     rdx, [rbx+18h]; tableid
0x18002f922  test    rdx, rdx
0x18002f925  jz      short loc_18002F96D
0x18002f927  mov     rcx, [rbx+8]; sesid
0x18002f92b  call    cs:__imp_JetCloseTable
0x18002f931  test    eax, eax
0x18002f933  jz      short loc_18002F965
0x18002f935  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f93c  cmp     rcx, rsi
0x18002f93f  jz      short loc_18002F965
0x18002f941  test    byte ptr [rcx+1Ch], 1
0x18002f945  jz      short loc_18002F965
0x18002f947  cmp     byte ptr [rcx+19h], 2
0x18002f94b  jb      short loc_18002F965
0x18002f94d  mov     rcx, [rcx+10h]
0x18002f951  lea     r8, WPP_6045f1246e8731b6b48955e2c326822f_Traceguids
0x18002f958  mov     edx, 4Dh ; 'M'
0x18002f95d  mov     r9d, eax
0x18002f960  call    WPP_SF_d
0x18002f965  mov     qword ptr [rbx+18h], 0
0x18002f96d  mov     edx, [rbx+10h]; dbid
0x18002f970  lea     r8, ?TableName@ParityTable@@3PAGA; "ParityExtent"
0x18002f977  mov     rcx, [rbx+8]; sesid
0x18002f97b  call    cs:__imp_JetDeleteTableW
0x18002f981  test    eax, eax
0x18002f983  jz      short loc_18002F9B5
0x18002f985  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f98c  cmp     rcx, rsi
0x18002f98f  jz      short loc_18002F9B5
0x18002f991  test    byte ptr [rcx+1Ch], 1
0x18002f995  jz      short loc_18002F9B5
0x18002f997  cmp     byte ptr [rcx+19h], 2
0x18002f99b  jb      short loc_18002F9B5
0x18002f99d  mov     rcx, [rcx+10h]
0x18002f9a1  lea     r8, WPP_6045f1246e8731b6b48955e2c326822f_Traceguids
0x18002f9a8  mov     edx, 4Eh ; 'N'
0x18002f9ad  mov     r9d, eax
0x18002f9b0  call    WPP_SF_d
0x18002f9b5  mov     rcx, rbx; this
0x18002f9b8  call    ?CreateParityTable@CScrubDatabase@@AEAAJXZ; CScrubDatabase::CreateParityTable(void)
0x18002f9bd  lea     rcx, [rsp+58h+var_18]; this
0x18002f9c2  mov     [rsp+58h+var_10], eax
0x18002f9c6  mov     ebx, eax
0x18002f9c8  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18002f9cd  mov     eax, ebx
0x18002f9cf  mov     rbx, [rsp+58h+arg_0]
0x18002f9d4  add     rsp, 50h
0x18002f9d8  pop     rsi
0x18002f9d9  retn
```
