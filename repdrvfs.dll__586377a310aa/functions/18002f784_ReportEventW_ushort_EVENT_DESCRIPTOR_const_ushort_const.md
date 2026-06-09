# ReportEventW(ushort,_EVENT_DESCRIPTOR const &,ushort const *)

- ea: `0x18002f784`
- end: `0x18002f9a6`
- name: `?ReportEventW@@YAXGAEBU_EVENT_DESCRIPTOR@@PEBG@Z`
- size: `546`
- prototype: `void __fastcall(unsigned __int16, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800262cc`
- `0x18002fd70`
- `0x1800397a8`
- `0x18003c714`
- `0x18003c8a0`

## callees

- `0x18002f784`

## import_xrefs

- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002f7ec`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002f801`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002f816`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002f82b`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002f840`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002f859`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002f870`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002f887`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002f89d`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002f8cb`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002f7ec`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002f801`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002f816`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002f82b`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002f840`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002f859`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002f870`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002f887`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002f89d`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002f8cb`
- `wbemcomn!??0CInsertionString@@QEAA@PEBG@Z` at `0x18002f8b6`
- `wbemcomn!??0CInsertionString@@QEAA@PEBG@Z` at `0x18002f8b6`
- `wbemcomn!??1CInsertionString@@QEAA@XZ` at `0x18002f957`
- `wbemcomn!??1CInsertionString@@QEAA@XZ` at `0x18002f96a`
- `wbemcomn!??1CInsertionString@@QEAA@XZ` at `0x18002f957`
- `wbemcomn!??1CInsertionString@@QEAA@XZ` at `0x18002f96a`
- `wbemcomn!??0CInsertionString@@QEAA@$$QEAV0@@Z` at `0x18002f8e4`
- `wbemcomn!??0CInsertionString@@QEAA@$$QEAV0@@Z` at `0x18002f8e4`
- `wbemcomn!??0CEventLog@@QEAA@PEBGAEBU_GUID@@K@Z` at `0x18002f7cc`
- `wbemcomn!??0CEventLog@@QEAA@PEBGAEBU_GUID@@K@Z` at `0x18002f7cc`
- `wbemcomn!??1CEventLog@@QEAA@XZ` at `0x18002f985`
- `wbemcomn!??1CEventLog@@QEAA@XZ` at `0x18002f985`
- `wbemcomn!?Close@CEventLog@@QEAAHXZ` at `0x18002f977`
- `wbemcomn!?Close@CEventLog@@QEAAHXZ` at `0x18002f977`
- `wbemcomn!?Open@CEventLog@@QEAAHXZ` at `0x18002f7da`
- `wbemcomn!?Open@CEventLog@@QEAAHXZ` at `0x18002f7da`
- `wbemcomn!?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z` at `0x18002f941`
- `wbemcomn!?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z` at `0x18002f941`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall ReportEventW(unsigned __int16 a1, const struct _EVENT_DESCRIPTOR *a2, const unsigned __int16 *a3)
{
  CInsertionString *v6; // r14
  CInsertionString *v7; // r15
  CInsertionString *v8; // r12
  CInsertionString *v9; // r13
  CInsertionString *v10; // rax
  char v11; // bl
  __int64 v12; // rax
  CInsertionString *v13; // [rsp+70h] [rbp-90h]
  CInsertionString *v14; // [rsp+78h] [rbp-88h]
  CInsertionString *v15; // [rsp+80h] [rbp-80h]
  CInsertionString *v16; // [rsp+88h] [rbp-78h]
  _BYTE v17[16]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v18[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v19[16]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v20[16]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v21[16]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v22[16]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v23[16]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v24[16]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v25[16]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v26[16]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v27[16]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v28[16]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v29[144]; // [rsp+1A0h] [rbp+A0h] BYREF
  CInsertionString *v30; // [rsp+258h] [rbp+158h]

  CEventLog::CEventLog((CEventLog *)v29, 0, (const struct _GUID *)S_WinMgmtR, 0xAu);
  CEventLog::Open((CEventLog *)v29);
  v6 = CInsertionString::CInsertionString((CInsertionString *)v17);
  v7 = CInsertionString::CInsertionString((CInsertionString *)v18);
  v8 = CInsertionString::CInsertionString((CInsertionString *)v19);
  v9 = CInsertionString::CInsertionString((CInsertionString *)v20);
  v30 = CInsertionString::CInsertionString((CInsertionString *)v21);
  v13 = CInsertionString::CInsertionString((CInsertionString *)v22);
  v14 = CInsertionString::CInsertionString((CInsertionString *)v23);
  v15 = CInsertionString::CInsertionString((CInsertionString *)v24);
  v16 = CInsertionString::CInsertionString((CInsertionString *)v25);
  if ( a3 )
  {
    v10 = CInsertionString::CInsertionString((CInsertionString *)v28, a3);
    v11 = 1;
  }
  else
  {
    v10 = CInsertionString::CInsertionString((CInsertionString *)v27);
    v11 = 2;
  }
  v12 = CInsertionString::CInsertionString(v26, v10);
  CEventLog::Report(v29, a1, a2, v12, v16, v15, v14, v13, v30, v9, v8, v7, v6);
  if ( (v11 & 2) != 0 )
  {
    v11 &= ~2u;
    CInsertionString::~CInsertionString((CInsertionString *)v27);
  }
  if ( (v11 & 1) != 0 )
    CInsertionString::~CInsertionString((CInsertionString *)v28);
  CEventLog::Close((CEventLog *)v29);
  CEventLog::~CEventLog((CEventLog *)v29);
}

```

## disassembly

```asm
0x18002f784  mov     [rsp-8+arg_0], rbx
0x18002f789  push    rbp
0x18002f78a  push    rsi
0x18002f78b  push    rdi
0x18002f78c  push    r12
0x18002f78e  push    r13
0x18002f790  push    r14
0x18002f792  push    r15
0x18002f794  lea     rbp, [rsp-100h]
0x18002f79c  sub     rsp, 200h
0x18002f7a3  mov     rbx, r8
0x18002f7a6  mov     rdi, rdx
0x18002f7a9  movzx   esi, cx
0x18002f7ac  mov     [rbp+130h+arg_10], 0
0x18002f7b6  mov     r9d, 0Ah
0x18002f7bc  lea     r8, S_WinMgmtR
0x18002f7c3  xor     edx, edx
0x18002f7c5  lea     rcx, [rbp+130h+var_90]
0x18002f7cc  call    cs:__imp_??0CEventLog@@QEAA@PEBGAEBU_GUID@@K@Z; CEventLog::CEventLog(ushort const *,_GUID const &,ulong)
0x18002f7d2  nop
0x18002f7d3  lea     rcx, [rbp+130h+var_90]
0x18002f7da  call    cs:__imp_?Open@CEventLog@@QEAAHXZ; CEventLog::Open(void)
0x18002f7e0  lea     rax, [rbp+130h+var_150]
0x18002f7e4  mov     [rbp+130h+var_1A0], rax
0x18002f7e8  lea     rcx, [rbp+130h+var_150]
0x18002f7ec  call    cs:__imp_??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x18002f7f2  mov     r14, rax
0x18002f7f5  lea     rax, [rbp+130h+var_140]
0x18002f7f9  mov     [rbp+130h+var_198], rax
0x18002f7fd  lea     rcx, [rbp+130h+var_140]
0x18002f801  call    cs:__imp_??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x18002f807  mov     r15, rax
0x18002f80a  lea     rax, [rbp+130h+var_130]
0x18002f80e  mov     [rbp+130h+var_190], rax
0x18002f812  lea     rcx, [rbp+130h+var_130]
0x18002f816  call    cs:__imp_??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x18002f81c  mov     r12, rax
0x18002f81f  lea     rax, [rbp+130h+var_120]
0x18002f823  mov     [rbp+130h+var_188], rax
0x18002f827  lea     rcx, [rbp+130h+var_120]
0x18002f82b  call    cs:__imp_??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x18002f831  mov     r13, rax
0x18002f834  lea     rax, [rbp+130h+var_110]
0x18002f838  mov     [rbp+130h+var_180], rax
0x18002f83c  lea     rcx, [rbp+130h+var_110]
0x18002f840  call    cs:__imp_??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x18002f846  mov     [rbp+130h+arg_18], rax
0x18002f84d  lea     rax, [rbp+130h+var_100]
0x18002f851  mov     [rbp+130h+var_178], rax
0x18002f855  lea     rcx, [rbp+130h+var_100]
0x18002f859  call    cs:__imp_??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x18002f85f  mov     [rsp+230h+var_1C0], rax
0x18002f864  lea     rax, [rbp+130h+var_F0]
0x18002f868  mov     [rbp+130h+var_170], rax
0x18002f86c  lea     rcx, [rbp+130h+var_F0]
0x18002f870  call    cs:__imp_??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x18002f876  mov     [rsp+230h+var_1B8], rax
0x18002f87b  lea     rax, [rbp+130h+var_E0]
0x18002f87f  mov     [rbp+130h+var_168], rax
0x18002f883  lea     rcx, [rbp+130h+var_E0]
0x18002f887  call    cs:__imp_??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x18002f88d  mov     [rbp+130h+var_1B0], rax
0x18002f891  lea     rax, [rbp+130h+var_D0]
0x18002f895  mov     [rbp+130h+var_160], rax
0x18002f899  lea     rcx, [rbp+130h+var_D0]
0x18002f89d  call    cs:__imp_??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x18002f8a3  mov     [rbp+130h+var_1A8], rax
0x18002f8a7  test    rbx, rbx
0x18002f8aa  jz      short loc_18002F8C4
0x18002f8ac  mov     rdx, rbx
0x18002f8af  lea     rcx, [rbp+130h+var_A0]
0x18002f8b6  call    cs:__imp_??0CInsertionString@@QEAA@PEBG@Z; CInsertionString::CInsertionString(ushort const *)
0x18002f8bc  nop
0x18002f8bd  mov     ebx, 1
0x18002f8c2  jmp     short loc_18002F8D7
0x18002f8c4  lea     rcx, [rbp+130h+var_B0]
0x18002f8cb  call    cs:__imp_??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x18002f8d1  nop
0x18002f8d2  mov     ebx, 2
0x18002f8d7  mov     [rbp+130h+arg_10], ebx
0x18002f8dd  mov     rdx, rax
0x18002f8e0  lea     rcx, [rbp+130h+var_C0]
0x18002f8e4  call    cs:__imp_??0CInsertionString@@QEAA@$$QEAV0@@Z; CInsertionString::CInsertionString(CInsertionString &&)
0x18002f8ea  nop
0x18002f8eb  mov     [rsp+230h+var_1D0], r14
0x18002f8f0  mov     [rsp+230h+var_1D8], r15
0x18002f8f5  mov     [rsp+230h+var_1E0], r12
0x18002f8fa  mov     [rsp+230h+var_1E8], r13
0x18002f8ff  mov     rcx, [rbp+130h+arg_18]
0x18002f906  mov     [rsp+230h+var_1F0], rcx
0x18002f90b  mov     rcx, [rsp+230h+var_1C0]
0x18002f910  mov     [rsp+230h+var_1F8], rcx
0x18002f915  mov     rcx, [rsp+230h+var_1B8]
0x18002f91a  mov     [rsp+230h+var_200], rcx
0x18002f91f  mov     rcx, [rbp+130h+var_1B0]
0x18002f923  mov     [rsp+230h+var_208], rcx
0x18002f928  mov     rcx, [rbp+130h+var_1A8]
0x18002f92c  mov     [rsp+230h+var_210], rcx
0x18002f931  mov     r9, rax
0x18002f934  mov     r8, rdi
0x18002f937  movzx   edx, si
0x18002f93a  lea     rcx, [rbp+130h+var_90]
0x18002f941  call    cs:__imp_?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z; CEventLog::Report(ushort,_EVENT_DESCRIPTOR const &,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString)
0x18002f947  nop
0x18002f948  test    bl, 2
0x18002f94b  jz      short loc_18002F95E
0x18002f94d  and     ebx, 0FFFFFFFDh
0x18002f950  lea     rcx, [rbp+130h+var_B0]
0x18002f957  call    cs:__imp_??1CInsertionString@@QEAA@XZ; CInsertionString::~CInsertionString(void)
0x18002f95d  nop
0x18002f95e  test    bl, 1
0x18002f961  jz      short loc_18002F970
0x18002f963  lea     rcx, [rbp+130h+var_A0]
0x18002f96a  call    cs:__imp_??1CInsertionString@@QEAA@XZ; CInsertionString::~CInsertionString(void)
0x18002f970  lea     rcx, [rbp+130h+var_90]
0x18002f977  call    cs:__imp_?Close@CEventLog@@QEAAHXZ; CEventLog::Close(void)
0x18002f97d  nop
0x18002f97e  lea     rcx, [rbp+130h+var_90]
0x18002f985  call    cs:__imp_??1CEventLog@@QEAA@XZ; CEventLog::~CEventLog(void)
0x18002f98b  mov     rbx, [rsp+230h+arg_0]
0x18002f993  add     rsp, 200h
0x18002f99a  pop     r15
0x18002f99c  pop     r14
0x18002f99e  pop     r13
0x18002f9a0  pop     r12
0x18002f9a2  pop     rdi
0x18002f9a3  pop     rsi
0x18002f9a4  pop     rbp
0x18002f9a5  retn
```
