# RevokeNfsSharePermission(_MSFT_NfsServerTasks_RevokeSharePermission const *,_MI_Context *)

- ea: `0x18000cfec`
- end: `0x18000d183`
- name: `?RevokeNfsSharePermission@@YAKPEBU_MSFT_NfsServerTasks_RevokeSharePermission@@PEAU_MI_Context@@@Z`
- size: `407`
- prototype: `unsigned int(const struct _MSFT_NfsServerTasks_RevokeSharePermission *, struct _MI_Context *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008c00`

## callees

- `0x1800098c4`
- `0x18000b2ac`
- `0x18000b620`
- `0x18000be24`
- `0x18000be78`
- `0x18000ce30`
- `0x18000cfec`
- `0x18000e350`
- `0x180020920`
- `0x180031648`
- `0x180035b02`
- `0x180035b40`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000d09e`
- `msvcrt!_wcsicmp` at `0x18000d09e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RevokeNfsSharePermission(
        const struct _MSFT_NfsServerTasks_RevokeSharePermission *a1,
        struct _MI_Context *a2)
{
  unsigned int v4; // esi
  _BYTE *v5; // rax
  enum _MI_Result v6; // ebx
  unsigned int v8; // [rsp+30h] [rbp-99h] BYREF
  _QWORD v9[2]; // [rsp+38h] [rbp-91h] BYREF
  __int16 v10; // [rsp+48h] [rbp-81h]
  struct _MI_Context *v11; // [rsp+50h] [rbp-79h]
  int v12; // [rsp+58h] [rbp-71h]
  __int64 v13; // [rsp+5Ch] [rbp-6Dh]
  MI_Instance instance; // [rsp+70h] [rbp-59h] BYREF
  int ReturnValue; // [rsp+B0h] [rbp-19h]
  char v16; // [rsp+B4h] [rbp-15h]

  v4 = 0;
  v8 = 0;
  v9[0] = &CWMIContext::`vftable';
  v11 = a2;
  v9[1] = 0;
  v10 = 0;
  v13 = 0;
  v12 = 0;
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x70u);
  if ( *((_BYTE *)a1 + 80) && *((_BYTE *)a1 + 96) && (v5 = (char *)a1 + 112, *((_BYTE *)a1 + 112)) )
  {
    v6 = MI_RESULT_OK;
  }
  else
  {
    v6 = MI_RESULT_INVALID_PARAMETER;
    v5 = (char *)a1 + 112;
  }
  if ( *v5 )
  {
    if ( !ValidateClientType(*((wchar_t **)a1 + 13), &v8) )
      v6 = MI_RESULT_INVALID_PARAMETER;
    v4 = v8;
  }
  if ( _wcsicmp(*((const wchar_t **)a1 + 11), L"All Machines") || v4 != 4 )
  {
    if ( v6 == MI_RESULT_OK )
    {
      if ( CWMIContext::PromptUser((CWMIContext *)v9, 0x40001005u, *((_QWORD *)a1 + 11), *((_QWORD *)a1 + 9)) )
      {
        LODWORD(v13) = RemoveSharePermission(
                         *((wchar_t **)a1 + 9),
                         1u,
                         0,
                         *((unsigned __int16 **)a1 + 11),
                         v4,
                         (struct CNfsTaskContext *)v9);
        v6 = MI_Context_ConstructParameters(a2, &MSFT_NfsServerTasks_RevokeSharePermission_rtti, &instance);
        if ( v6 == MI_RESULT_OK )
        {
          ReturnValue = CWMIContext::GetReturnValue((CWMIContext *)v9);
          v16 = 1;
          MI_Instance_Destruct((MI_Instance *)a2);
          v6 = MI_Instance_Destruct(&instance);
        }
      }
    }
  }
  else
  {
    CWMIContext::WriteWarning((CWMIContext *)v9, 0x80001008);
    v6 = MI_RESULT_INVALID_PARAMETER;
  }
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v9, v6);
  CWMIContext::~CWMIContext((CWMIContext *)v9);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000cfec  mov     [rsp-8+arg_10], rbx
0x18000cff1  push    rbp
0x18000cff2  push    rsi
0x18000cff3  push    rdi
0x18000cff4  push    r12
0x18000cff6  push    r14
0x18000cff8  lea     rbp, [rsp-37h]
0x18000cffd  sub     rsp, 100h
0x18000d004  mov     rax, cs:__security_cookie
0x18000d00b  xor     rax, rsp
0x18000d00e  mov     [rbp+57h+var_30], rax
0x18000d012  mov     r14, rdx
0x18000d015  mov     rdi, rcx
0x18000d018  xor     esi, esi
0x18000d01a  mov     [rsp+120h+var_F0], esi
0x18000d01e  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x18000d025  mov     [rsp+120h+var_E8], rax
0x18000d02a  mov     [rbp+57h+var_D0], rdx
0x18000d02e  mov     [rsp+120h+var_E0], rsi
0x18000d033  mov     [rsp+120h+var_D8], si
0x18000d038  mov     [rbp+57h+var_C4], rsi
0x18000d03c  mov     [rbp+57h+var_C8], esi
0x18000d03f  mov     [rbp+57h+instance.ft], rsi
0x18000d043  xor     edx, edx; Val
0x18000d045  lea     r8d, [rsi+70h]; Size
0x18000d049  lea     rcx, [rbp+57h+instance.classDecl]; void *
0x18000d04d  call    memset_0
0x18000d052  lea     r12d, [rsi+4]
0x18000d056  cmp     [rdi+50h], sil
0x18000d05a  jz      short loc_18000D06F
0x18000d05c  cmp     [rdi+60h], sil
0x18000d060  jz      short loc_18000D06F
0x18000d062  lea     rax, [rdi+70h]
0x18000d066  cmp     [rax], sil
0x18000d069  jz      short loc_18000D06F
0x18000d06b  xor     ebx, ebx
0x18000d06d  jmp     short loc_18000D076
0x18000d06f  mov     ebx, r12d
0x18000d072  lea     rax, [rdi+70h]
0x18000d076  cmp     byte ptr [rax], 0
0x18000d079  jz      short loc_18000D093
0x18000d07b  lea     rdx, [rsp+120h+var_F0]; unsigned int *
0x18000d080  mov     rcx, [rdi+68h]; String2
0x18000d084  call    ?ValidateClientType@@YAEPEBGPEAK@Z; ValidateClientType(ushort const *,ulong *)
0x18000d089  test    al, al
0x18000d08b  cmovz   ebx, r12d
0x18000d08f  mov     esi, [rsp+120h+var_F0]
0x18000d093  lea     rdx, aAllMachines; "All Machines"
0x18000d09a  mov     rcx, [rdi+58h]; String1
0x18000d09e  call    cs:__imp__wcsicmp
0x18000d0a4  test    eax, eax
0x18000d0a6  jnz     short loc_18000D0C4
0x18000d0a8  cmp     esi, r12d
0x18000d0ab  jnz     short loc_18000D0C4
0x18000d0ad  mov     edx, 80001008h; unsigned int
0x18000d0b2  lea     rcx, [rsp+120h+var_E8]; this
0x18000d0b7  call    ?WriteWarning@CWMIContext@@UEAAXKZZ; CWMIContext::WriteWarning(ulong,...)
0x18000d0bc  mov     ebx, r12d
0x18000d0bf  jmp     loc_18000D147
0x18000d0c4  test    ebx, ebx
0x18000d0c6  jnz     short loc_18000D147
0x18000d0c8  mov     r9, [rdi+48h]
0x18000d0cc  mov     r8, [rdi+58h]
0x18000d0d0  mov     edx, 40001005h; unsigned int
0x18000d0d5  lea     rcx, [rsp+120h+var_E8]; this
0x18000d0da  call    ?PromptUser@CWMIContext@@UEAAEKZZ; CWMIContext::PromptUser(ulong,...)
0x18000d0df  test    al, al
0x18000d0e1  jz      short loc_18000D147
0x18000d0e3  lea     rax, [rsp+120h+var_E8]
0x18000d0e8  mov     [rsp+120h+var_F8], rax; struct CNfsTaskContext *
0x18000d0ed  mov     [rsp+120h+var_100], esi; unsigned int
0x18000d0f1  mov     r9, [rdi+58h]; unsigned __int16 *
0x18000d0f5  xor     r8d, r8d; unsigned __int16 *
0x18000d0f8  mov     dl, 1; unsigned __int8
0x18000d0fa  mov     rcx, [rdi+48h]; String2
0x18000d0fe  call    ?RemoveSharePermission@@YAKPEAGE00KPEAVCNfsTaskContext@@@Z; RemoveSharePermission(ushort *,uchar,ushort *,ushort *,ulong,CNfsTaskContext *)
0x18000d103  mov     dword ptr [rbp+57h+var_C4], eax
0x18000d106  lea     r8, [rbp+57h+instance]; instance
0x18000d10a  lea     rdx, MSFT_NfsServerTasks_RevokeSharePermission_rtti; methodDecl
0x18000d111  mov     rcx, r14; context
0x18000d114  call    MI_Context_ConstructParameters
0x18000d119  mov     ebx, eax
0x18000d11b  test    eax, eax
0x18000d11d  jnz     short loc_18000D147
0x18000d11f  lea     rcx, [rsp+120h+var_E8]; this
0x18000d124  call    ?GetReturnValue@CWMIContext@@QEAAJXZ; CWMIContext::GetReturnValue(void)
0x18000d129  mov     [rbp+57h+var_70], eax
0x18000d12c  mov     [rbp+57h+var_6C], 1
0x18000d130  lea     rdx, [rbp+57h+instance]
0x18000d134  mov     rcx, r14; self
0x18000d137  call    MI_Instance_Destruct
0x18000d13c  lea     rcx, [rbp+57h+instance]; self
0x18000d140  call    MI_Instance_Destruct
0x18000d145  mov     ebx, eax
0x18000d147  mov     edx, ebx; enum _MI_Result
0x18000d149  lea     rcx, [rsp+120h+var_E8]; this
0x18000d14e  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x18000d153  nop
0x18000d154  lea     rcx, [rsp+120h+var_E8]; this
0x18000d159  call    ??1CWMIContext@@UEAA@XZ; CWMIContext::~CWMIContext(void)
0x18000d15e  mov     eax, ebx
0x18000d160  mov     rcx, [rbp+57h+var_30]
0x18000d164  xor     rcx, rsp; StackCookie
0x18000d167  call    __security_check_cookie
0x18000d16c  mov     rbx, [rsp+120h+arg_10]
0x18000d174  add     rsp, 100h
0x18000d17b  pop     r14
0x18000d17d  pop     r12
0x18000d17f  pop     rdi
0x18000d180  pop     rsi
0x18000d181  pop     rbp
0x18000d182  retn
```
