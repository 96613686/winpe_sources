# CIEAdminBrokerObject::QueryInterface(_GUID const &,void * *)

- ea: `0x140008030`
- end: `0x140008171`
- name: `?QueryInterface@CIEAdminBrokerObject@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `321`
- prototype: `__int64 __fastcall(CIEAdminBrokerObject *__hidden this, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140008180`
- `0x140008190`

## callees

- `0x140008030`
- `0x14000ba88`
- `0x140011010`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerObject::QueryInterface(CIEAdminBrokerObject *this, const struct _GUID *a2, void **a3)
{
  unsigned int v3; // edi
  CIEAdminBrokerObject *v5; // rbx
  __int64 v6; // rax

  v3 = 0;
  v5 = this;
  if ( *(_OWORD *)a2 != *(_OWORD *)&IID_IUnknown
    && (*(_QWORD *)&a2->Data1 != *(_QWORD *)&IID_IeAxiInstaller.Data1
     || *(_QWORD *)a2->Data4 != *(_QWORD *)IID_IeAxiInstaller.Data4)
    && (*(_QWORD *)&a2->Data1 != *(_QWORD *)&IID_IeAxiInstaller2.Data1
     || *(_QWORD *)a2->Data4 != *(_QWORD *)IID_IeAxiInstaller2.Data4) )
  {
    if ( *(_QWORD *)&a2->Data1 != *(_QWORD *)&IID_IeAxiAdminInstaller.Data1
      || *(_QWORD *)a2->Data4 != *(_QWORD *)IID_IeAxiAdminInstaller.Data4 )
    {
      if ( *(_QWORD *)&a2->Data1 != *(_QWORD *)&IID_IeAxiSystemInstaller.Data1
        || *(_QWORD *)a2->Data4 != *(_QWORD *)IID_IeAxiSystemInstaller.Data4 )
      {
        *a3 = 0;
        return (unsigned int)-2147467262;
      }
      if ( !(unsigned int)VerifyCallerIsSystemOrAdminWithHighIL()
        && (g_fRunningAsSystem || g_fRunningAsAdminWithHighIL)
        && (!*((_DWORD *)v5 + 10) || *((_DWORD *)v5 + 11)) )
      {
        *a3 = (void *)(((unsigned __int64)v5 + 8) & -(__int64)(v5 != 0));
        goto LABEL_7;
      }
      *a3 = 0;
      return (unsigned int)-2147467259;
    }
    if ( g_fRunningAsSystem )
    {
      if ( !*((_DWORD *)this + 10) )
      {
LABEL_17:
        *a3 = 0;
        return (unsigned int)-2147467259;
      }
    }
    else if ( !*((_DWORD *)this + 10) )
    {
LABEL_16:
      *a3 = this;
      v6 = *(_QWORD *)this;
      goto LABEL_8;
    }
    if ( !*((_DWORD *)this + 11) )
      goto LABEL_16;
    goto LABEL_17;
  }
  *a3 = (void *)(((unsigned __int64)this + 16) & -(__int64)(this != 0));
LABEL_7:
  v6 = *(_QWORD *)v5;
  this = v5;
LABEL_8:
  (*(void (__fastcall **)(CIEAdminBrokerObject *))(v6 + 8))(this);
  return v3;
}

```

## disassembly

```asm
0x140008030  mov     [rsp+arg_0], rbx
0x140008035  mov     [rsp+arg_8], rsi
0x14000803a  push    rdi
0x14000803b  sub     rsp, 20h
0x14000803f  mov     rax, [rdx]
0x140008042  xor     edi, edi
0x140008044  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x14000804b  mov     rsi, r8
0x14000804e  mov     rbx, rcx
0x140008051  jnz     short loc_140008060
0x140008053  mov     rax, [rdx+8]
0x140008057  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x14000805e  jz      short loc_140008092
0x140008060  mov     rax, [rdx]
0x140008063  cmp     rax, qword ptr cs:IID_IeAxiInstaller.Data1
0x14000806a  jnz     short loc_140008079
0x14000806c  mov     rax, [rdx+8]
0x140008070  cmp     rax, qword ptr cs:IID_IeAxiInstaller.Data4
0x140008077  jz      short loc_140008092
0x140008079  mov     rax, [rdx]
0x14000807c  cmp     rax, qword ptr cs:IID_IeAxiInstaller2.Data1
0x140008083  jnz     short loc_1400080B9
0x140008085  mov     rax, [rdx+8]
0x140008089  cmp     rax, qword ptr cs:IID_IeAxiInstaller2.Data4
0x140008090  jnz     short loc_1400080B9
0x140008092  lea     rdx, [rcx+10h]
0x140008096  mov     rax, rbx
0x140008099  neg     rax
0x14000809c  sbb     rcx, rcx
0x14000809f  and     rcx, rdx
0x1400080a2  mov     [r8], rcx
0x1400080a5  mov     rax, [rbx]
0x1400080a8  mov     rcx, rbx
0x1400080ab  mov     rax, [rax+8]
0x1400080af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080b4  jmp     loc_14000815E
0x1400080b9  mov     rax, [rdx]
0x1400080bc  cmp     rax, qword ptr cs:IID_IeAxiAdminInstaller.Data1
0x1400080c3  jnz     short loc_1400080F8
0x1400080c5  mov     rax, [rdx+8]
0x1400080c9  cmp     rax, qword ptr cs:IID_IeAxiAdminInstaller.Data4
0x1400080d0  jnz     short loc_1400080F8
0x1400080d2  cmp     cs:?g_fRunningAsSystem@@3HA, edi; int g_fRunningAsSystem
0x1400080d8  jnz     short loc_1400080E1
0x1400080da  cmp     [rcx+28h], edi
0x1400080dd  jz      short loc_1400080EB
0x1400080df  jmp     short loc_1400080E6
0x1400080e1  cmp     [rcx+28h], edi
0x1400080e4  jz      short loc_1400080F3
0x1400080e6  cmp     [rcx+2Ch], edi
0x1400080e9  jnz     short loc_1400080F3
0x1400080eb  mov     [r8], rbx
0x1400080ee  mov     rax, [rcx]
0x1400080f1  jmp     short loc_1400080AB
0x1400080f3  mov     [r8], rdi
0x1400080f6  jmp     short loc_14000814F
0x1400080f8  mov     rax, [rdx]
0x1400080fb  cmp     rax, qword ptr cs:IID_IeAxiSystemInstaller.Data1
0x140008102  jnz     short loc_140008156
0x140008104  mov     rax, [rdx+8]
0x140008108  cmp     rax, qword ptr cs:IID_IeAxiSystemInstaller.Data4
0x14000810f  jnz     short loc_140008156
0x140008111  call    ?VerifyCallerIsSystemOrAdminWithHighIL@@YAJXZ; VerifyCallerIsSystemOrAdminWithHighIL(void)
0x140008116  test    eax, eax
0x140008118  jnz     short loc_14000814C
0x14000811a  cmp     cs:?g_fRunningAsSystem@@3HA, edi; int g_fRunningAsSystem
0x140008120  jnz     short loc_14000812A
0x140008122  cmp     cs:?g_fRunningAsAdminWithHighIL@@3HA, edi; int g_fRunningAsAdminWithHighIL
0x140008128  jz      short loc_14000814C
0x14000812a  cmp     [rbx+28h], edi
0x14000812d  jz      short loc_140008134
0x14000812f  cmp     [rbx+2Ch], edi
0x140008132  jz      short loc_14000814C
0x140008134  mov     rax, rbx
0x140008137  lea     rdx, [rbx+8]
0x14000813b  neg     rax
0x14000813e  sbb     rcx, rcx
0x140008141  and     rcx, rdx
0x140008144  mov     [rsi], rcx
0x140008147  jmp     loc_1400080A5
0x14000814c  mov     [rsi], rdi
0x14000814f  mov     edi, 80004005h
0x140008154  jmp     short loc_14000815E
0x140008156  mov     [r8], rdi
0x140008159  mov     edi, 80004002h
0x14000815e  mov     rbx, [rsp+28h+arg_0]
0x140008163  mov     eax, edi
0x140008165  mov     rsi, [rsp+28h+arg_8]
0x14000816a  add     rsp, 20h
0x14000816e  pop     rdi
0x14000816f  retn
```
