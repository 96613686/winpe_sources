# RevokeNfsSharePermissionByName(_MSFT_NfsServerTasks_RevokeSharePermissionByName const *,_MI_Context *)

- ea: `0x18000d18c`
- end: `0x18000d357`
- name: `?RevokeNfsSharePermissionByName@@YAKPEBU_MSFT_NfsServerTasks_RevokeSharePermissionByName@@PEAU_MI_Context@@@Z`
- size: `459`
- prototype: `unsigned int(const struct _MSFT_NfsServerTasks_RevokeSharePermissionByName *, struct _MI_Context *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008c10`

## callees

- `0x1800098c4`
- `0x18000b2ac`
- `0x18000b620`
- `0x18000be24`
- `0x18000be78`
- `0x18000ce30`
- `0x18000d18c`
- `0x18000e350`
- `0x180020920`
- `0x180031648`
- `0x180035b02`
- `0x180035b40`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000d259`
- `msvcrt!_wcsicmp` at `0x18000d259`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RevokeNfsSharePermissionByName(
        const struct _MSFT_NfsServerTasks_RevokeSharePermissionByName *a1,
        struct _MI_Context *a2)
{
  unsigned int v4; // esi
  _BYTE *v5; // rax
  enum _MI_Result v6; // ebx
  unsigned __int16 *v7; // r8
  unsigned int v9; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v10[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v11; // [rsp+48h] [rbp-B8h]
  struct _MI_Context *v12; // [rsp+50h] [rbp-B0h]
  int v13; // [rsp+58h] [rbp-A8h]
  __int64 v14; // [rsp+5Ch] [rbp-A4h]
  MI_Instance instance; // [rsp+70h] [rbp-90h] BYREF
  int ReturnValue; // [rsp+B0h] [rbp-50h]
  char v17; // [rsp+B4h] [rbp-4Ch]

  v4 = 0;
  v9 = 0;
  v10[0] = &CWMIContext::`vftable';
  v12 = a2;
  v10[1] = 0;
  v11 = 0;
  v14 = 0;
  v13 = 0;
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x80u);
  if ( *((_BYTE *)a1 + 80) && *((_BYTE *)a1 + 112) && (v5 = (char *)a1 + 128, *((_BYTE *)a1 + 128)) )
  {
    v6 = MI_RESULT_OK;
  }
  else
  {
    v6 = MI_RESULT_INVALID_PARAMETER;
    v5 = (char *)a1 + 128;
  }
  if ( *v5 )
  {
    if ( !ValidateClientType(*((wchar_t **)a1 + 15), &v9) )
      v6 = MI_RESULT_INVALID_PARAMETER;
    v4 = v9;
  }
  if ( _wcsicmp(*((const wchar_t **)a1 + 13), L"All Machines") || v4 != 4 )
  {
    if ( v6 == MI_RESULT_OK
      && CWMIContext::PromptUser((CWMIContext *)v10, 0x40001005u, *((_QWORD *)a1 + 13), *((_QWORD *)a1 + 9)) )
    {
      if ( *((_BYTE *)a1 + 96) )
        v7 = (unsigned __int16 *)*((_QWORD *)a1 + 11);
      else
        v7 = 0;
      LODWORD(v14) = RemoveSharePermission(
                       *((wchar_t **)a1 + 9),
                       0,
                       v7,
                       *((unsigned __int16 **)a1 + 13),
                       v4,
                       (struct CNfsTaskContext *)v10);
      v6 = MI_Context_ConstructParameters(a2, &MSFT_NfsServerTasks_RevokeSharePermissionByName_rtti, &instance);
      if ( v6 == MI_RESULT_OK )
      {
        ReturnValue = CWMIContext::GetReturnValue((CWMIContext *)v10);
        v17 = 1;
        MI_Instance_Destruct((MI_Instance *)a2);
        v6 = MI_Instance_Destruct(&instance);
      }
    }
  }
  else
  {
    CWMIContext::WriteWarning((CWMIContext *)v10, 0x80001008);
    v6 = MI_RESULT_INVALID_PARAMETER;
  }
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v10, v6);
  CWMIContext::~CWMIContext((CWMIContext *)v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000d18c  mov     [rsp-8+arg_10], rbx
0x18000d191  mov     [rsp-8+arg_18], rsi
0x18000d196  push    rbp
0x18000d197  push    rdi
0x18000d198  push    r12
0x18000d19a  push    r14
0x18000d19c  push    r15
0x18000d19e  lea     rbp, [rsp-10h]
0x18000d1a3  sub     rsp, 110h
0x18000d1aa  mov     rax, cs:__security_cookie
0x18000d1b1  xor     rax, rsp
0x18000d1b4  mov     [rbp+30h+var_30], rax
0x18000d1b8  mov     r14, rdx
0x18000d1bb  mov     rdi, rcx
0x18000d1be  xor     r15d, r15d
0x18000d1c1  mov     esi, r15d
0x18000d1c4  mov     [rsp+130h+var_100], r15d
0x18000d1c9  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x18000d1d0  mov     [rsp+130h+var_F8], rax
0x18000d1d5  mov     [rsp+130h+var_E0], rdx
0x18000d1da  mov     [rsp+130h+var_F0], r15
0x18000d1df  mov     [rsp+130h+var_E8], r15w
0x18000d1e5  mov     [rsp+130h+var_D4], r15
0x18000d1ea  mov     [rsp+130h+var_D8], r15d
0x18000d1ef  mov     [rsp+130h+instance.ft], r15
0x18000d1f4  xor     edx, edx; Val
0x18000d1f6  mov     r8d, 80h; Size
0x18000d1fc  lea     rcx, [rsp+130h+instance.classDecl]; void *
0x18000d201  call    memset_0
0x18000d206  lea     r12d, [r15+4]
0x18000d20a  cmp     [rdi+50h], r15b
0x18000d20e  jz      short loc_18000D227
0x18000d210  cmp     [rdi+70h], r15b
0x18000d214  jz      short loc_18000D227
0x18000d216  lea     rax, [rdi+80h]
0x18000d21d  cmp     [rax], r15b
0x18000d220  jz      short loc_18000D227
0x18000d222  mov     ebx, r15d
0x18000d225  jmp     short loc_18000D231
0x18000d227  mov     ebx, r12d
0x18000d22a  lea     rax, [rdi+80h]
0x18000d231  cmp     [rax], r15b
0x18000d234  jz      short loc_18000D24E
0x18000d236  lea     rdx, [rsp+130h+var_100]; unsigned int *
0x18000d23b  mov     rcx, [rdi+78h]; String2
0x18000d23f  call    ?ValidateClientType@@YAEPEBGPEAK@Z; ValidateClientType(ushort const *,ulong *)
0x18000d244  test    al, al
0x18000d246  cmovz   ebx, r12d
0x18000d24a  mov     esi, [rsp+130h+var_100]
0x18000d24e  lea     rdx, aAllMachines; "All Machines"
0x18000d255  mov     rcx, [rdi+68h]; String1
0x18000d259  call    cs:__imp__wcsicmp
0x18000d25f  test    eax, eax
0x18000d261  jnz     short loc_18000D27F
0x18000d263  cmp     esi, r12d
0x18000d266  jnz     short loc_18000D27F
0x18000d268  mov     edx, 80001008h; unsigned int
0x18000d26d  lea     rcx, [rsp+130h+var_F8]; this
0x18000d272  call    ?WriteWarning@CWMIContext@@UEAAXKZZ; CWMIContext::WriteWarning(ulong,...)
0x18000d277  mov     ebx, r12d
0x18000d27a  jmp     loc_18000D316
0x18000d27f  test    ebx, ebx
0x18000d281  jnz     loc_18000D316
0x18000d287  mov     r9, [rdi+48h]
0x18000d28b  mov     r8, [rdi+68h]
0x18000d28f  mov     edx, 40001005h; unsigned int
0x18000d294  lea     rcx, [rsp+130h+var_F8]; this
0x18000d299  call    ?PromptUser@CWMIContext@@UEAAEKZZ; CWMIContext::PromptUser(ulong,...)
0x18000d29e  test    al, al
0x18000d2a0  jz      short loc_18000D316
0x18000d2a2  cmp     [rdi+60h], r15b
0x18000d2a6  jz      short loc_18000D2AE
0x18000d2a8  mov     r8, [rdi+58h]
0x18000d2ac  jmp     short loc_18000D2B1
0x18000d2ae  mov     r8, r15; unsigned __int16 *
0x18000d2b1  lea     rax, [rsp+130h+var_F8]
0x18000d2b6  mov     [rsp+130h+var_108], rax; struct CNfsTaskContext *
0x18000d2bb  mov     [rsp+130h+var_110], esi; unsigned int
0x18000d2bf  mov     r9, [rdi+68h]; unsigned __int16 *
0x18000d2c3  xor     edx, edx; unsigned __int8
0x18000d2c5  mov     rcx, [rdi+48h]; String2
0x18000d2c9  call    ?RemoveSharePermission@@YAKPEAGE00KPEAVCNfsTaskContext@@@Z; RemoveSharePermission(ushort *,uchar,ushort *,ushort *,ulong,CNfsTaskContext *)
0x18000d2ce  mov     dword ptr [rsp+130h+var_D4], eax
0x18000d2d2  lea     r8, [rsp+130h+instance]; instance
0x18000d2d7  lea     rdx, MSFT_NfsServerTasks_RevokeSharePermissionByName_rtti; methodDecl
0x18000d2de  mov     rcx, r14; context
0x18000d2e1  call    MI_Context_ConstructParameters
0x18000d2e6  mov     ebx, eax
0x18000d2e8  test    eax, eax
0x18000d2ea  jnz     short loc_18000D316
0x18000d2ec  lea     rcx, [rsp+130h+var_F8]; this
0x18000d2f1  call    ?GetReturnValue@CWMIContext@@QEAAJXZ; CWMIContext::GetReturnValue(void)
0x18000d2f6  mov     [rbp+30h+var_80], eax
0x18000d2f9  mov     [rbp+30h+var_7C], 1
0x18000d2fd  lea     rdx, [rsp+130h+instance]
0x18000d302  mov     rcx, r14; self
0x18000d305  call    MI_Instance_Destruct
0x18000d30a  lea     rcx, [rsp+130h+instance]; self
0x18000d30f  call    MI_Instance_Destruct
0x18000d314  mov     ebx, eax
0x18000d316  mov     edx, ebx; enum _MI_Result
0x18000d318  lea     rcx, [rsp+130h+var_F8]; this
0x18000d31d  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x18000d322  nop
0x18000d323  lea     rcx, [rsp+130h+var_F8]; this
0x18000d328  call    ??1CWMIContext@@UEAA@XZ; CWMIContext::~CWMIContext(void)
0x18000d32d  mov     eax, ebx
0x18000d32f  mov     rcx, [rbp+30h+var_30]
0x18000d333  xor     rcx, rsp; StackCookie
0x18000d336  call    __security_check_cookie
0x18000d33b  lea     r11, [rsp+130h+var_20]
0x18000d343  mov     rbx, [r11+40h]
0x18000d347  mov     rsi, [r11+48h]
0x18000d34b  mov     rsp, r11
0x18000d34e  pop     r15
0x18000d350  pop     r14
0x18000d352  pop     r12
0x18000d354  pop     rdi
0x18000d355  pop     rbp
0x18000d356  retn
```
