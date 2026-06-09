# GrantNfsSharePermission(_MSFT_NfsServerTasks_GrantSharePermission const *,_MI_Context *)

- ea: `0x18000b72c`
- end: `0x18000b9d2`
- name: `?GrantNfsSharePermission@@YAKPEBU_MSFT_NfsServerTasks_GrantSharePermission@@PEAU_MI_Context@@@Z`
- size: `678`
- prototype: `unsigned int(const struct _MSFT_NfsServerTasks_GrantSharePermission *, struct _MI_Context *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008b70`

## callees

- `0x1800098c4`
- `0x18000b2ac`
- `0x18000b620`
- `0x18000b72c`
- `0x18000be24`
- `0x18000be78`
- `0x18000ce30`
- `0x18001d024`
- `0x18001eca0`
- `0x180031648`
- `0x1800316ec`
- `0x180031804`
- `0x180035b02`
- `0x180035b40`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000b84d`
- `msvcrt!_wcsicmp` at `0x18000b84d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GrantNfsSharePermission(
        const struct _MSFT_NfsServerTasks_GrantSharePermission *a1,
        struct _MI_Context *a2)
{
  unsigned int v4; // esi
  enum _MI_Result v5; // ebx
  unsigned int v6; // eax
  unsigned int v8; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v9; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v10; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v11[2]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v12; // [rsp+90h] [rbp-70h]
  struct _MI_Context *v13; // [rsp+98h] [rbp-68h]
  int v14; // [rsp+A0h] [rbp-60h]
  __int64 v15; // [rsp+A4h] [rbp-5Ch]
  MI_Instance instance; // [rsp+B0h] [rbp-50h] BYREF
  int ReturnValue; // [rsp+F0h] [rbp-10h]
  char v18; // [rsp+F4h] [rbp-Ch]

  v9 = 0;
  v4 = 0;
  v10 = 0;
  v8 = 0;
  v11[0] = &CWMIContext::`vftable';
  v13 = a2;
  v11[1] = 0;
  v12 = 0;
  v15 = 0;
  v14 = 0;
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x98u);
  if ( !*((_BYTE *)a1 + 80)
    || !*((_BYTE *)a1 + 96)
    || !*((_BYTE *)a1 + 112)
    || *((_BYTE *)a1 + 128) && !ValidatePermission(*((wchar_t **)a1 + 15), &v9) )
  {
    goto LABEL_18;
  }
  if ( *((_BYTE *)a1 + 112) )
  {
    if ( !ValidateClientType(*((wchar_t **)a1 + 13), &v10) )
    {
LABEL_18:
      v5 = MI_RESULT_INVALID_PARAMETER;
      goto LABEL_19;
    }
    v4 = v10;
  }
  if ( *((_BYTE *)a1 + 144) && !ValidateLanguageEncoding(*((wchar_t **)a1 + 17), &v8) )
    goto LABEL_18;
  v5 = MI_RESULT_OK;
  if ( CWMIContext::PromptUser((CWMIContext *)v11, 0x40001006u, *((_QWORD *)a1 + 11), *((_QWORD *)a1 + 9)) )
  {
    if ( _wcsicmp(*((const wchar_t **)a1 + 11), L"All Machines") || v4 != 4 )
      v6 = AddSharePermission(
             *((wchar_t **)a1 + 9),
             1u,
             0,
             *((unsigned __int16 **)a1 + 11),
             v4,
             (unsigned int *)((unsigned __int64)&v9 & -(__int64)(*((_BYTE *)a1 + 128) != 0)),
             (unsigned int *)((unsigned __int64)&v8 & -(__int64)(*((_BYTE *)a1 + 144) != 0)),
             (unsigned __int8 *)(((unsigned __int64)a1 + 152) & -(__int64)(*((_BYTE *)a1 + 153) != 0)),
             (struct CNfsTaskContext *)v11);
    else
      v6 = ModifyShare(
             *((wchar_t **)a1 + 9),
             1u,
             0,
             0,
             0,
             0,
             0,
             0,
             (unsigned __int8 *)(((unsigned __int64)a1 + 152) & -(__int64)(*((_BYTE *)a1 + 153) != 0)),
             (unsigned int *)((unsigned __int64)&v8 & -(__int64)(*((_BYTE *)a1 + 144) != 0)),
             0,
             (unsigned int *)((unsigned __int64)&v9 & -(__int64)(*((_BYTE *)a1 + 128) != 0)),
             0,
             (struct CNfsTaskContext *)v11);
    LODWORD(v15) = v6;
    v5 = MI_Context_ConstructParameters(a2, &MSFT_NfsServerTasks_GrantSharePermission_rtti, &instance);
    if ( v5 == MI_RESULT_OK )
    {
      ReturnValue = CWMIContext::GetReturnValue((CWMIContext *)v11);
      v18 = 1;
      MI_Instance_Destruct((MI_Instance *)a2);
      v5 = MI_Instance_Destruct(&instance);
    }
  }
LABEL_19:
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v11, v5);
  CWMIContext::~CWMIContext((CWMIContext *)v11);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000b72c  mov     [rsp-8+arg_10], rbx
0x18000b731  push    rbp
0x18000b732  push    rsi
0x18000b733  push    rdi
0x18000b734  push    r14
0x18000b736  push    r15
0x18000b738  lea     rbp, [rsp-60h]
0x18000b73d  sub     rsp, 160h
0x18000b744  mov     rax, cs:__security_cookie
0x18000b74b  xor     rax, rsp
0x18000b74e  mov     [rbp+80h+var_30], rax
0x18000b752  mov     r14, rdx
0x18000b755  mov     rdi, rcx
0x18000b758  xor     r15d, r15d
0x18000b75b  mov     [rsp+180h+var_10C], r15d
0x18000b760  mov     esi, r15d
0x18000b763  mov     [rsp+180h+var_108], r15d
0x18000b768  mov     [rsp+180h+var_110], r15d
0x18000b76d  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x18000b774  mov     [rbp+80h+var_100], rax
0x18000b778  mov     [rbp+80h+var_E8], rdx
0x18000b77c  mov     [rbp+80h+var_F8], r15
0x18000b780  mov     [rbp+80h+var_F0], r15w
0x18000b785  mov     [rbp+80h+var_DC], r15
0x18000b789  mov     [rbp+80h+var_E0], r15d
0x18000b78d  mov     [rbp+80h+instance.ft], r15
0x18000b791  xor     edx, edx; Val
0x18000b793  mov     r8d, 98h; Size
0x18000b799  lea     rcx, [rbp+80h+instance.classDecl]; void *
0x18000b79d  call    memset_0
0x18000b7a2  cmp     [rdi+50h], r15b
0x18000b7a6  jz      loc_18000B993
0x18000b7ac  cmp     [rdi+60h], r15b
0x18000b7b0  jz      loc_18000B993
0x18000b7b6  cmp     [rdi+70h], r15b
0x18000b7ba  jz      loc_18000B993
0x18000b7c0  cmp     [rdi+80h], r15b
0x18000b7c7  jz      short loc_18000B7DF
0x18000b7c9  lea     rdx, [rsp+180h+var_10C]; unsigned int *
0x18000b7ce  mov     rcx, [rdi+78h]; String2
0x18000b7d2  call    ?ValidatePermission@@YAEPEBGPEAK@Z; ValidatePermission(ushort const *,ulong *)
0x18000b7d7  test    al, al
0x18000b7d9  jz      loc_18000B993
0x18000b7df  cmp     [rdi+70h], r15b
0x18000b7e3  jz      short loc_18000B7FF
0x18000b7e5  lea     rdx, [rsp+180h+var_108]; unsigned int *
0x18000b7ea  mov     rcx, [rdi+68h]; String2
0x18000b7ee  call    ?ValidateClientType@@YAEPEBGPEAK@Z; ValidateClientType(ushort const *,ulong *)
0x18000b7f3  test    al, al
0x18000b7f5  jz      loc_18000B993
0x18000b7fb  mov     esi, [rsp+180h+var_108]
0x18000b7ff  cmp     [rdi+90h], r15b
0x18000b806  jz      short loc_18000B821
0x18000b808  lea     rdx, [rsp+180h+var_110]; unsigned int *
0x18000b80d  mov     rcx, [rdi+88h]; String2
0x18000b814  call    ?ValidateLanguageEncoding@@YAEPEAGPEAK@Z; ValidateLanguageEncoding(ushort *,ulong *)
0x18000b819  test    al, al
0x18000b81b  jz      loc_18000B993
0x18000b821  mov     ebx, r15d
0x18000b824  mov     r9, [rdi+48h]
0x18000b828  mov     r8, [rdi+58h]
0x18000b82c  mov     edx, 40001006h; unsigned int
0x18000b831  lea     rcx, [rbp+80h+var_100]; this
0x18000b835  call    ?PromptUser@CWMIContext@@UEAAEKZZ; CWMIContext::PromptUser(ulong,...)
0x18000b83a  test    al, al
0x18000b83c  jz      loc_18000B998
0x18000b842  lea     rdx, aAllMachines; "All Machines"
0x18000b849  mov     rcx, [rdi+58h]; String1
0x18000b84d  call    cs:__imp__wcsicmp
0x18000b853  test    eax, eax
0x18000b855  jnz     loc_18000B8E8
0x18000b85b  lea     ebx, [rax+4]
0x18000b85e  cmp     esi, ebx
0x18000b860  jnz     loc_18000B8E8
0x18000b866  lea     r8, [rdi+98h]
0x18000b86d  mov     al, [rdi+80h]
0x18000b873  neg     al
0x18000b875  sbb     r9, r9
0x18000b878  lea     rax, [rsp+180h+var_10C]
0x18000b87d  and     r9, rax
0x18000b880  mov     al, [rdi+90h]
0x18000b886  neg     al
0x18000b888  sbb     rdx, rdx
0x18000b88b  lea     rax, [rsp+180h+var_110]
0x18000b890  and     rdx, rax
0x18000b893  mov     al, [r8+1]
0x18000b897  neg     al
0x18000b899  sbb     rcx, rcx
0x18000b89c  and     rcx, r8
0x18000b89f  lea     rax, [rbp+80h+var_100]
0x18000b8a3  mov     [rsp+180h+var_118], rax; struct CNfsTaskContext *
0x18000b8a8  mov     [rsp+180h+var_120], r15; struct _LIST_ENTRY *
0x18000b8ad  mov     [rsp+180h+var_128], r9; unsigned int *
0x18000b8b2  mov     [rsp+180h+var_130], r15; unsigned int *
0x18000b8b7  mov     [rsp+180h+var_138], rdx; unsigned int *
0x18000b8bc  mov     [rsp+180h+var_140], rcx; unsigned __int8 *
0x18000b8c1  mov     [rsp+180h+var_148], r15; int *
0x18000b8c6  mov     [rsp+180h+var_150], r15; int *
0x18000b8cb  mov     [rsp+180h+var_158], r15; unsigned __int8 *
0x18000b8d0  mov     [rsp+180h+var_160], r15; unsigned __int8 *
0x18000b8d5  xor     r9d, r9d; unsigned __int16 *
0x18000b8d8  xor     r8d, r8d; unsigned __int16 *
0x18000b8db  mov     dl, 1; unsigned __int8
0x18000b8dd  mov     rcx, [rdi+48h]; String2
0x18000b8e1  call    ?ModifyShare@@YAKPEAGE00PEAE1PEAJ21PEAK33PEAU_LIST_ENTRY@@PEAVCNfsTaskContext@@@Z; ModifyShare(ushort *,uchar,ushort *,ushort *,uchar *,uchar *,long *,long *,uchar *,ulong *,ulong *,ulong *,_LIST_ENTRY *,CNfsTaskContext *)
0x18000b8e6  jmp     short loc_18000B94E
0x18000b8e8  lea     rcx, [rdi+98h]
0x18000b8ef  mov     al, [rcx+1]
0x18000b8f2  neg     al
0x18000b8f4  sbb     r8, r8
0x18000b8f7  and     r8, rcx
0x18000b8fa  mov     al, [rdi+90h]
0x18000b900  neg     al
0x18000b902  sbb     rdx, rdx
0x18000b905  lea     rax, [rsp+180h+var_110]
0x18000b90a  and     rdx, rax
0x18000b90d  mov     al, [rdi+80h]
0x18000b913  neg     al
0x18000b915  sbb     rcx, rcx
0x18000b918  lea     rax, [rsp+180h+var_10C]
0x18000b91d  and     rcx, rax
0x18000b920  lea     rax, [rbp+80h+var_100]
0x18000b924  mov     [rsp+180h+var_140], rax; struct CNfsTaskContext *
0x18000b929  mov     [rsp+180h+var_148], r8; unsigned __int8 *
0x18000b92e  mov     [rsp+180h+var_150], rdx; unsigned int *
0x18000b933  mov     [rsp+180h+var_158], rcx; unsigned int *
0x18000b938  mov     dword ptr [rsp+180h+var_160], esi; unsigned int
0x18000b93c  mov     r9, [rdi+58h]; unsigned __int16 *
0x18000b940  xor     r8d, r8d; unsigned __int16 *
0x18000b943  mov     dl, 1; unsigned __int8
0x18000b945  mov     rcx, [rdi+48h]; String2
0x18000b949  call    ?AddSharePermission@@YAKPEAGE00KPEAK1PEAEPEAVCNfsTaskContext@@@Z; AddSharePermission(ushort *,uchar,ushort *,ushort *,ulong,ulong *,ulong *,uchar *,CNfsTaskContext *)
0x18000b94e  mov     dword ptr [rbp+80h+var_DC], eax
0x18000b951  lea     r8, [rbp+80h+instance]; instance
0x18000b955  lea     rdx, MSFT_NfsServerTasks_GrantSharePermission_rtti; methodDecl
0x18000b95c  mov     rcx, r14; context
0x18000b95f  call    MI_Context_ConstructParameters
0x18000b964  mov     ebx, eax
0x18000b966  test    eax, eax
0x18000b968  jnz     short loc_18000B998
0x18000b96a  lea     rcx, [rbp+80h+var_100]; this
0x18000b96e  call    ?GetReturnValue@CWMIContext@@QEAAJXZ; CWMIContext::GetReturnValue(void)
0x18000b973  mov     [rbp+80h+var_90], eax
0x18000b976  mov     [rbp+80h+var_8C], 1
0x18000b97a  lea     rdx, [rbp+80h+instance]
0x18000b97e  mov     rcx, r14; self
0x18000b981  call    MI_Instance_Destruct
0x18000b986  lea     rcx, [rbp+80h+instance]; self
0x18000b98a  call    MI_Instance_Destruct
0x18000b98f  mov     ebx, eax
0x18000b991  jmp     short loc_18000B998
0x18000b993  mov     ebx, 4
0x18000b998  mov     edx, ebx; enum _MI_Result
0x18000b99a  lea     rcx, [rbp+80h+var_100]; this
0x18000b99e  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x18000b9a3  nop
0x18000b9a4  lea     rcx, [rbp+80h+var_100]; this
0x18000b9a8  call    ??1CWMIContext@@UEAA@XZ; CWMIContext::~CWMIContext(void)
0x18000b9ad  mov     eax, ebx
0x18000b9af  mov     rcx, [rbp+80h+var_30]
0x18000b9b3  xor     rcx, rsp; StackCookie
0x18000b9b6  call    __security_check_cookie
0x18000b9bb  mov     rbx, [rsp+180h+arg_10]
0x18000b9c3  add     rsp, 160h
0x18000b9ca  pop     r15
0x18000b9cc  pop     r14
0x18000b9ce  pop     rdi
0x18000b9cf  pop     rsi
0x18000b9d0  pop     rbp
0x18000b9d1  retn
```
