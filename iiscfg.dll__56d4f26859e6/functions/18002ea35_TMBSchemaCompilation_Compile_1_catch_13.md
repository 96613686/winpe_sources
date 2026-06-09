# _TMBSchemaCompilation::Compile_::_1_::catch$13

- ea: `0x18002ea35`
- end: `0x18002eb82`
- name: `_TMBSchemaCompilation::Compile_::_1_::catch$13`
- size: `333`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002bc4`
- `0x180011b38`
- `0x180012734`
- `0x18002ea35`
- `0x180030010`

## string_xrefs

- `0x18002eb18`: `inetsrv\iis\mb\config\src\core\schemagen\mbschemacompilation.cpp`

## pseudocode

```c
__int64 __fastcall TMBSchemaCompilation::Compile_::_1_::catch_13(__int64 a1, __int64 a2)
{
  unsigned int *v3; // rbx
  __int64 v5; // [rsp+20h] [rbp-A8h]
  __int64 v6; // [rsp+88h] [rbp-40h]
  __int64 v7; // [rsp+90h] [rbp-38h]

  v3 = *(unsigned int **)(a2 + 320);
  if ( v3[7] )
  {
    *(_QWORD *)(a2 + 200) = 0;
    CErrorInterceptor::Init(
      (CErrorInterceptor *)(a2 + 192),
      0,
      0,
      0x80210861,
      3u,
      v3[7],
      &word_180034198,
      &word_180034198,
      &word_180034198,
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0,
      v6,
      v7,
      -1,
      -1);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)(a2 + 192),
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\mbschemacompilation.cpp",
      172,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)(a2 + 192));
  }
  LODWORD(v5) = v3[6];
  (**(void (***)(__int64, const wchar_t *, ...))(a2 + 176))(
    a2 + 176,
    L"TException raised:\n\tHRESULT:    \t0x%08x\n\tFile:      \t%s\n\tLine Number:\t%d\n\tCode:      \t%s\n",
    *v3,
    *((_QWORD *)v3 + 1),
    v5,
    *((_QWORD *)v3 + 2));
  return 0;
}

```

## disassembly

```asm
0x18002ea35  mov     [rsp+arg_8], rdx
0x18002ea3a  push    rbx
0x18002ea3b  push    rbp
0x18002ea3c  sub     rsp, 0B8h
0x18002ea43  mov     rbp, rdx
0x18002ea46  mov     rbx, [rbp+140h]
0x18002ea4d  cmp     dword ptr [rbx+1Ch], 0
0x18002ea51  jz      loc_18002EB38
0x18002ea57  mov     qword ptr [rbp+0C8h], 0
0x18002ea62  mov     [rsp+0C8h+var_28], 0FFFFFFFFh
0x18002ea6d  mov     [rsp+0C8h+var_30], 0FFFFFFFFh
0x18002ea78  mov     [rsp+0C8h+var_48], 0
0x18002ea83  mov     [rsp+0C8h+var_50], 0
0x18002ea8c  mov     [rsp+0C8h+var_58], 0FFFFFFFFh
0x18002ea94  mov     [rsp+0C8h+var_60], 0FFFFFFFFh
0x18002ea9c  mov     [rsp+0C8h+var_68], 0
0x18002eaa4  mov     [rsp+0C8h+var_70], 0
0x18002eaad  mov     [rsp+0C8h+var_78], 0
0x18002eab5  lea     rax, word_180034198
0x18002eabc  mov     [rsp+0C8h+var_80], rax
0x18002eac1  lea     rax, word_180034198
0x18002eac8  mov     [rsp+0C8h+var_88], rax
0x18002eacd  lea     rax, word_180034198
0x18002ead4  mov     [rsp+0C8h+var_90], rax
0x18002ead9  lea     rax, word_180034198
0x18002eae0  mov     [rsp+0C8h+var_98], rax
0x18002eae5  mov     eax, [rbx+1Ch]
0x18002eae8  mov     dword ptr [rsp+0C8h+var_A0], eax
0x18002eaec  mov     dword ptr [rsp+0C8h+var_A8], 3
0x18002eaf4  mov     r9d, 80210861h
0x18002eafa  xor     r8d, r8d
0x18002eafd  xor     edx, edx
0x18002eaff  lea     rcx, [rbp+0C0h]
0x18002eb06  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18002eb0b  nop
0x18002eb0c  mov     r9d, 400000h; unsigned int
0x18002eb12  mov     r8d, 0ACh; unsigned int
0x18002eb18  lea     rdx, aInetsrvIisMbCo_9; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18002eb1f  lea     rcx, [rbp+0C0h]; this
0x18002eb26  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18002eb2b  nop
0x18002eb2c  lea     rcx, [rbp+0C0h]; this
0x18002eb33  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18002eb38  mov     rax, [rbp+0B0h]
0x18002eb3f  mov     rcx, [rbx+10h]
0x18002eb43  mov     [rsp+0C8h+var_A0], rcx
0x18002eb48  mov     ecx, [rbx+18h]
0x18002eb4b  mov     dword ptr [rsp+0C8h+var_A8], ecx
0x18002eb4f  mov     r9, [rbx+8]
0x18002eb53  mov     r8d, [rbx]
0x18002eb56  lea     rdx, aTexceptionRais; "TException raised:\n\tHRESULT:    \t0x%"...
0x18002eb5d  lea     rcx, [rbp+0B0h]
0x18002eb64  mov     rax, [rax]
0x18002eb67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb6c  nop
0x18002eb6d  mov     rax, 0
0x18002eb77  add     rsp, 0B8h
0x18002eb7e  pop     rbp
0x18002eb7f  pop     rbx
0x18002eb80  retn
```
