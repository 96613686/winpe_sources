# CXaRm1PipeConn_State_WaitForMessage::MsgOpenXaRmConn(CXaRm1PipeConn *,IXaTmUser_OpenXaResource_Message *)

- ea: `0x1800a7010`
- end: `0x1800a71a0`
- name: `?MsgOpenXaRmConn@CXaRm1PipeConn_State_WaitForMessage@@UEAAXPEAVCXaRm1PipeConn@@PEAVIXaTmUser_OpenXaResource_Message@@@Z`
- size: `400`
- prototype: `void __fastcall(CXaRm1PipeConn_State_WaitForMessage *__hidden this, struct CXaRm1PipeConn *, struct IXaTmUser_OpenXaResource_Message *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800063b0`
- `0x18001b4f0`
- `0x18001b8f0`
- `0x18001bc70`
- `0x1800240f0`
- `0x1800240fc`
- `0x1800a7010`
- `0x1800b83ee`
- `0x1800bd010`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800a70fb`
- `RPCRT4!UuidCreate` at `0x1800a70fb`
- `msvcrt!rand_s` at `0x1800a7114`
- `msvcrt!rand_s` at `0x1800a7114`

## string_xrefs

- `0x1800a7122`: `com\complus\dtc\dtc\xatm\src\xarmconn.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CXaRm1PipeConn_State_WaitForMessage::MsgOpenXaRmConn(
        CXaRm1PipeConn_State_WaitForMessage *this,
        struct CXaRm1PipeConn *a2,
        struct IXaTmUser_OpenXaResource_Message *a3)
{
  unsigned __int64 v3; // rbp
  const char *v7; // r15
  void *v8; // rcx
  char *v9; // rax
  char *v10; // rsi
  int v11; // eax
  int v12; // [rsp+38h] [rbp-30h]
  int v13; // [rsp+80h] [rbp+18h] BYREF

  v3 = 3072;
  if ( *(_DWORD *)a3 >= 0xC00u || *((_DWORD *)a3 + 1) >= 0x100u )
    goto LABEL_7;
  v7 = (char *)a3 + 12;
  TracedStringCbCopyNA((char *)a2 + 524, 0x100u, (const char *)a3 + *(unsigned int *)a3 + 12, *((unsigned int *)a3 + 1));
  *((_DWORD *)a2 + 342) = *(_DWORD *)a3;
  if ( *(_DWORD *)a3 < 0x100u )
  {
    v10 = (char *)a2 + 268;
    memset_0((char *)a2 + 268, 0, 0x100u);
    v3 = 256;
  }
  else
  {
    v8 = (void *)*((_QWORD *)a2 + 172);
    if ( v8 )
    {
      operator delete(v8);
      *((_QWORD *)a2 + 172) = 0;
    }
    v9 = (char *)operator new[](*(unsigned int *)a3 + 1LL);
    *((_QWORD *)a2 + 172) = v9;
    v10 = v9;
    if ( !v9 )
      goto LABEL_7;
  }
  TracedStringCbCopyNA(v10, v3, v7, *(unsigned int *)a3);
  if ( UuidCreate((UUID *)((char *)a2 + 252)) )
  {
LABEL_7:
    CXaRm1PipeConn_State::Change_State_RespondAndWaitForDown(this, a2, 0xA0000003);
    return;
  }
  v13 = 0;
  v11 = rand_s(&v13);
  if ( v11 )
  {
    v12 = v11;
    TraceStringInline(
      11,
      1,
      L"com\\complus\\dtc\\dtc\\xatm\\src\\xarmconn.cpp",
      1799,
      L"CXaRm1PipeConn::GenRmId",
      0,
      L"Generated RmId failed with error: 0x%x",
      v12);
    goto LABEL_7;
  }
  *((_DWORD *)a2 + 62) = v13 & 0x7FFFFFFF;
  (*(void (__fastcall **)(CXaRm1PipeConn_State_WaitForMessage *, struct CXaRm1PipeConn *))(*(_QWORD *)this + 88LL))(
    this,
    a2);
  *((_QWORD *)a2 + 26) = g_CXaRm1PipeConn_State_Validating;
  CXaRm1PipeConn_State_Validating::Enter_State((CXaRm1PipeConn_State_Validating *)g_CXaRm1PipeConn_State_Validating, a2);
}

```

## disassembly

```asm
0x1800a7010  mov     [rsp+arg_0], rbx
0x1800a7015  mov     [rsp+arg_8], rbp
0x1800a701a  push    rsi
0x1800a701b  push    rdi
0x1800a701c  push    r13
0x1800a701e  push    r14
0x1800a7020  push    r15
0x1800a7022  sub     rsp, 40h
0x1800a7026  mov     ebp, 0C00h
0x1800a702b  mov     rdi, r8
0x1800a702e  mov     rbx, rdx
0x1800a7031  mov     r14, rcx
0x1800a7034  cmp     [r8], ebp
0x1800a7037  jnb     short loc_1800A70A4
0x1800a7039  mov     r13d, 100h
0x1800a703f  cmp     [r8+4], r13d
0x1800a7043  jnb     short loc_1800A70A4
0x1800a7045  mov     r9d, [r8+4]; unsigned __int64
0x1800a7049  lea     r15, [r8+0Ch]
0x1800a704d  mov     r8d, [r8]
0x1800a7050  lea     rcx, [rdx+20Ch]; char *
0x1800a7057  add     r8, r15; char *
0x1800a705a  mov     edx, r13d; unsigned __int64
0x1800a705d  call    ?TracedStringCbCopyNA@@YAXPEAD_KPEBD1@Z; TracedStringCbCopyNA(char *,unsigned __int64,char const *,unsigned __int64)
0x1800a7062  mov     eax, [rdi]
0x1800a7064  mov     [rbx+558h], eax
0x1800a706a  cmp     [rdi], r13d
0x1800a706d  jb      short loc_1800A70CC
0x1800a706f  mov     rcx, [rbx+560h]; Block
0x1800a7076  test    rcx, rcx
0x1800a7079  jz      short loc_1800A708B
0x1800a707b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a7080  mov     qword ptr [rbx+560h], 0
0x1800a708b  mov     ecx, [rdi]
0x1800a708d  inc     rcx; unsigned __int64
0x1800a7090  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800a7095  mov     [rbx+560h], rax
0x1800a709c  mov     rsi, rax
0x1800a709f  test    rax, rax
0x1800a70a2  jnz     short loc_1800A70E3
0x1800a70a4  mov     r8d, 0A0000003h; unsigned int
0x1800a70aa  mov     rdx, rbx; struct CXaRm1PipeConn *
0x1800a70ad  mov     rcx, r14; this
0x1800a70b0  call    ?Change_State_RespondAndWaitForDown@CXaRm1PipeConn_State@@QEAAXPEAVCXaRm1PipeConn@@K@Z; CXaRm1PipeConn_State::Change_State_RespondAndWaitForDown(CXaRm1PipeConn *,ulong)
0x1800a70b5  mov     rbx, [rsp+68h+arg_0]
0x1800a70ba  mov     rbp, [rsp+68h+arg_8]
0x1800a70bf  add     rsp, 40h
0x1800a70c3  pop     r15
0x1800a70c5  pop     r14
0x1800a70c7  pop     r13
0x1800a70c9  pop     rdi
0x1800a70ca  pop     rsi
0x1800a70cb  retn
0x1800a70cc  lea     rsi, [rbx+10Ch]
0x1800a70d3  mov     r8, r13; Size
0x1800a70d6  mov     rcx, rsi; void *
0x1800a70d9  xor     edx, edx; Val
0x1800a70db  call    memset_0
0x1800a70e0  mov     rbp, r13
0x1800a70e3  mov     r9d, [rdi]; unsigned __int64
0x1800a70e6  mov     r8, r15; char *
0x1800a70e9  mov     rdx, rbp; unsigned __int64
0x1800a70ec  mov     rcx, rsi; char *
0x1800a70ef  call    ?TracedStringCbCopyNA@@YAXPEAD_KPEBD1@Z; TracedStringCbCopyNA(char *,unsigned __int64,char const *,unsigned __int64)
0x1800a70f4  lea     rcx, [rbx+0FCh]; Uuid
0x1800a70fb  call    cs:__imp_UuidCreate
0x1800a7101  test    eax, eax
0x1800a7103  jnz     short loc_1800A70A4
0x1800a7105  lea     rcx, [rsp+68h+arg_10]
0x1800a710d  mov     [rsp+68h+arg_10], eax
0x1800a7114  call    cs:__imp_rand_s
0x1800a711a  test    eax, eax
0x1800a711c  jz      short loc_1800A7162
0x1800a711e  mov     [rsp+68h+var_30], eax
0x1800a7122  lea     r8, aComComplusDtcD_21; "com\\complus\\dtc\\dtc\\xatm\\src\\xarm"...
0x1800a7129  mov     edx, 1
0x1800a712e  lea     rax, aGeneratedRmidF; "Generated RmId failed with error: 0x%x"
0x1800a7135  mov     [rsp+68h+var_38], rax
0x1800a713a  mov     r9d, 707h
0x1800a7140  lea     rax, aCxarm1pipeconn_5; "CXaRm1PipeConn::GenRmId"
0x1800a7147  mov     [rsp+68h+var_40], 0
0x1800a7150  mov     [rsp+68h+var_48], rax
0x1800a7155  lea     ecx, [rdx+0Ah]
0x1800a7158  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800a715d  jmp     loc_1800A70A4
0x1800a7162  mov     eax, [rsp+68h+arg_10]
0x1800a7169  mov     rdx, rbx
0x1800a716c  btr     eax, 1Fh
0x1800a7170  mov     rcx, r14
0x1800a7173  mov     [rbx+0F8h], eax
0x1800a7179  mov     rax, [r14]
0x1800a717c  mov     rax, [rax+58h]
0x1800a7180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7185  lea     rcx, ?g_CXaRm1PipeConn_State_Validating@@3VCXaRm1PipeConn_State_Validating@@A; this
0x1800a718c  mov     rdx, rbx; struct CXaRm1PipeConn *
0x1800a718f  mov     [rbx+0D0h], rcx
0x1800a7196  call    ?Enter_State@CXaRm1PipeConn_State_Validating@@UEAAXPEAVCXaRm1PipeConn@@@Z; CXaRm1PipeConn_State_Validating::Enter_State(CXaRm1PipeConn *)
0x1800a719b  jmp     loc_1800A70B5
```
