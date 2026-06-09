# SetNfsSharePermissionByString(_MSFT_NfsServerTasks_SetSharePermissionByString const *,_MI_Context *)

- ea: `0x18000d66c`
- end: `0x18000d872`
- name: `?SetNfsSharePermissionByString@@YAKPEBU_MSFT_NfsServerTasks_SetSharePermissionByString@@PEAU_MI_Context@@@Z`
- size: `518`
- prototype: `unsigned int(const struct _MSFT_NfsServerTasks_SetSharePermissionByString *, struct _MI_Context *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008c40`

## callees

- `0x1800098c4`
- `0x18000b2ac`
- `0x18000b328`
- `0x18000b620`
- `0x18000be24`
- `0x18000be78`
- `0x18000ce30`
- `0x18000d66c`
- `0x18000eae4`
- `0x180020b64`
- `0x180035b02`
- `0x180035b40`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000d778`
- `msvcrt!memcpy_s` at `0x18000d778`
- `KERNEL32!HeapFree` at `0x18000d828`
- `KERNEL32!HeapFree` at `0x18000d828`
- `KERNEL32!HeapAlloc` at `0x18000d744`
- `KERNEL32!HeapAlloc` at `0x18000d744`
- `KERNEL32!GetProcessHeap` at `0x18000d735`
- `KERNEL32!GetProcessHeap` at `0x18000d81a`
- `KERNEL32!GetProcessHeap` at `0x18000d735`
- `KERNEL32!GetProcessHeap` at `0x18000d81a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SetNfsSharePermissionByString(wchar_t **a1, struct _MI_Context *a2)
{
  unsigned __int16 *v4; // rbx
  __int64 v5; // rdx
  enum _MI_Result v6; // edi
  SIZE_T v7; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v9; // rax
  __int64 v10; // rcx
  void **v11; // r8
  bool v12; // dl
  unsigned __int16 *v13; // r8
  HANDLE v14; // rax
  _QWORD v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v17; // [rsp+40h] [rbp-C0h]
  struct _MI_Context *v18; // [rsp+48h] [rbp-B8h]
  int v19; // [rsp+50h] [rbp-B0h]
  __int64 v20; // [rsp+54h] [rbp-ACh]
  MI_Instance instance; // [rsp+70h] [rbp-90h] BYREF
  int ReturnValue; // [rsp+B0h] [rbp-50h]
  char v23; // [rsp+B4h] [rbp-4Ch]
  void *Source[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v25; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v26; // [rsp+F8h] [rbp-8h]

  v16[0] = &CWMIContext::`vftable';
  v18 = a2;
  v16[1] = 0;
  v17 = 0;
  v20 = 0;
  v19 = 0;
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x60u);
  if ( *((_BYTE *)a1 + 80) && *((_BYTE *)a1 + 96) )
  {
    v4 = 0;
    v26 = 7;
    v25 = 0;
    LOWORD(Source[0]) = 0;
    v6 = (unsigned int)CWMIContext::FormatMessageW((CWMIContext *)v16, 0x40001032u);
    if ( v6 == MI_RESULT_OK )
    {
      v7 = 2 * v25 + 2;
      ProcessHeap = GetProcessHeap();
      v9 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v7);
      v4 = v9;
      if ( v9 )
      {
        v10 = v25;
        v11 = Source;
        if ( v26 >= 8 )
          v11 = (void **)Source[0];
        if ( v25 )
        {
          memcpy_s(v9, 2 * v25, v11, 2 * v25);
          v10 = v25;
        }
        v4[v10] = 0;
      }
      else
      {
        v6 = MI_RESULT_FAILED;
      }
    }
    LOBYTE(v5) = 1;
    std::wstring::_Tidy(Source, v5, 0);
    if ( v6 == MI_RESULT_OK )
    {
      if ( CWMIContext::PromptUser((CWMIContext *)v16, 0x40001007u, a1[9]) )
      {
        LODWORD(v20) = SetSharePermission(a1[9], v12, v13, a1[11], v4, (struct CNfsTaskContext *)v16);
        v6 = MI_Context_ConstructParameters(a2, &MSFT_NfsServerTasks_SetSharePermissionByString_rtti, &instance);
        if ( v6 == MI_RESULT_OK )
        {
          ReturnValue = CWMIContext::GetReturnValue((CWMIContext *)v16);
          v23 = 1;
          MI_Instance_Destruct((MI_Instance *)a2);
          v6 = MI_Instance_Destruct(&instance);
        }
      }
    }
    if ( v4 )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v4);
    }
  }
  else
  {
    v6 = MI_RESULT_INVALID_PARAMETER;
  }
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v16, v6);
  CWMIContext::~CWMIContext((CWMIContext *)v16);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000d66c  mov     [rsp-8+arg_10], rbx
0x18000d671  mov     [rsp-8+arg_18], rsi
0x18000d676  push    rbp
0x18000d677  push    rdi
0x18000d678  push    r14
0x18000d67a  lea     rbp, [rsp-10h]
0x18000d67f  sub     rsp, 110h
0x18000d686  mov     rax, cs:__security_cookie
0x18000d68d  xor     rax, rsp
0x18000d690  mov     [rbp+20h+var_20], rax
0x18000d694  mov     r14, rdx
0x18000d697  mov     rsi, rcx
0x18000d69a  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x18000d6a1  mov     [rsp+120h+var_F0], rax
0x18000d6a6  mov     [rsp+120h+var_D8], rdx
0x18000d6ab  mov     [rsp+120h+var_E8], 0
0x18000d6b4  mov     [rsp+120h+var_E0], 0
0x18000d6bb  mov     [rsp+120h+var_CC], 0
0x18000d6c4  mov     [rsp+120h+var_D0], 0
0x18000d6cc  mov     [rsp+120h+instance.ft], 0
0x18000d6d5  xor     edx, edx; Val
0x18000d6d7  lea     r8d, [rdx+60h]; Size
0x18000d6db  lea     rcx, [rsp+120h+instance.classDecl]; void *
0x18000d6e0  call    memset_0
0x18000d6e5  cmp     byte ptr [rsi+50h], 0
0x18000d6e9  jz      loc_18000D830
0x18000d6ef  cmp     byte ptr [rsi+60h], 0
0x18000d6f3  jz      loc_18000D830
0x18000d6f9  xor     ebx, ebx
0x18000d6fb  mov     [rbp+20h+var_28], 7
0x18000d703  mov     [rbp+20h+var_30], rbx
0x18000d707  xor     eax, eax
0x18000d709  mov     word ptr [rbp+20h+Source], ax
0x18000d70d  xor     r9d, r9d
0x18000d710  lea     r8, [rbp+20h+Source]
0x18000d714  mov     edx, 40001032h; dwMessageId
0x18000d719  lea     rcx, [rsp+120h+var_F0]; this
0x18000d71e  call    ?FormatMessageW@CWMIContext@@QEAA?AW4_MI_Result@@KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAD@Z; CWMIContext::FormatMessageW(ulong,std::wstring &,char * *)
0x18000d723  mov     edi, eax
0x18000d725  test    eax, eax
0x18000d727  jnz     short loc_18000D788
0x18000d729  mov     rax, [rbp+20h+var_30]
0x18000d72d  lea     rbx, ds:2[rax*2]
0x18000d735  call    cs:__imp_GetProcessHeap
0x18000d73b  mov     rcx, rax; hHeap
0x18000d73e  mov     r8, rbx; dwBytes
0x18000d741  lea     edx, [rdi+8]; dwFlags
0x18000d744  call    cs:__imp_HeapAlloc
0x18000d74a  mov     rbx, rax
0x18000d74d  test    rax, rax
0x18000d750  jnz     short loc_18000D757
0x18000d752  lea     edi, [rax+1]
0x18000d755  jmp     short loc_18000D788
0x18000d757  mov     rcx, [rbp+20h+var_30]
0x18000d75b  lea     r8, [rbp+20h+Source]
0x18000d75f  cmp     [rbp+20h+var_28], 8
0x18000d764  cmovnb  r8, [rbp+20h+Source]; Source
0x18000d769  test    rcx, rcx
0x18000d76c  jz      short loc_18000D782
0x18000d76e  lea     rdx, [rcx+rcx]; DestinationSize
0x18000d772  mov     r9, rdx; SourceSize
0x18000d775  mov     rcx, rbx; Destination
0x18000d778  call    cs:__imp_memcpy_s
0x18000d77e  mov     rcx, [rbp+20h+var_30]
0x18000d782  xor     eax, eax
0x18000d784  mov     [rbx+rcx*2], ax
0x18000d788  xor     r8d, r8d
0x18000d78b  mov     dl, 1
0x18000d78d  lea     rcx, [rbp+20h+Source]
0x18000d791  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000d796  test    edi, edi
0x18000d798  jnz     short loc_18000D815
0x18000d79a  mov     r8, [rsi+48h]
0x18000d79e  mov     edx, 40001007h; unsigned int
0x18000d7a3  lea     rcx, [rsp+120h+var_F0]; this
0x18000d7a8  call    ?PromptUser@CWMIContext@@UEAAEKZZ; CWMIContext::PromptUser(ulong,...)
0x18000d7ad  test    al, al
0x18000d7af  jz      short loc_18000D815
0x18000d7b1  lea     rax, [rsp+120h+var_F0]
0x18000d7b6  mov     [rsp+120h+var_F8], rax; struct CNfsTaskContext *
0x18000d7bb  mov     [rsp+120h+var_100], rbx; unsigned __int16 *
0x18000d7c0  mov     r9, [rsi+58h]; unsigned __int16 *
0x18000d7c4  mov     rcx, [rsi+48h]; String2
0x18000d7c8  call    ?SetSharePermission@@YAKPEAGE000PEAVCNfsTaskContext@@@Z; SetSharePermission(ushort *,uchar,ushort *,ushort *,ushort *,CNfsTaskContext *)
0x18000d7cd  mov     dword ptr [rsp+120h+var_CC], eax
0x18000d7d1  lea     r8, [rsp+120h+instance]; instance
0x18000d7d6  lea     rdx, MSFT_NfsServerTasks_SetSharePermissionByString_rtti; methodDecl
0x18000d7dd  mov     rcx, r14; context
0x18000d7e0  call    MI_Context_ConstructParameters
0x18000d7e5  mov     edi, eax
0x18000d7e7  test    eax, eax
0x18000d7e9  jnz     short loc_18000D815
0x18000d7eb  lea     rcx, [rsp+120h+var_F0]; this
0x18000d7f0  call    ?GetReturnValue@CWMIContext@@QEAAJXZ; CWMIContext::GetReturnValue(void)
0x18000d7f5  mov     [rbp+20h+var_70], eax
0x18000d7f8  mov     [rbp+20h+var_6C], 1
0x18000d7fc  lea     rdx, [rsp+120h+instance]
0x18000d801  mov     rcx, r14; self
0x18000d804  call    MI_Instance_Destruct
0x18000d809  lea     rcx, [rsp+120h+instance]; self
0x18000d80e  call    MI_Instance_Destruct
0x18000d813  mov     edi, eax
0x18000d815  test    rbx, rbx
0x18000d818  jz      short loc_18000D835
0x18000d81a  call    cs:__imp_GetProcessHeap
0x18000d820  mov     rcx, rax; hHeap
0x18000d823  mov     r8, rbx; lpMem
0x18000d826  xor     edx, edx; dwFlags
0x18000d828  call    cs:__imp_HeapFree
0x18000d82e  jmp     short loc_18000D835
0x18000d830  mov     edi, 4
0x18000d835  mov     edx, edi; enum _MI_Result
0x18000d837  lea     rcx, [rsp+120h+var_F0]; this
0x18000d83c  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x18000d841  nop
0x18000d842  lea     rcx, [rsp+120h+var_F0]; this
0x18000d847  call    ??1CWMIContext@@UEAA@XZ; CWMIContext::~CWMIContext(void)
0x18000d84c  mov     eax, edi
0x18000d84e  mov     rcx, [rbp+20h+var_20]
0x18000d852  xor     rcx, rsp; StackCookie
0x18000d855  call    __security_check_cookie
0x18000d85a  lea     r11, [rsp+120h+var_10]
0x18000d862  mov     rbx, [r11+30h]
0x18000d866  mov     rsi, [r11+38h]
0x18000d86a  mov     rsp, r11
0x18000d86d  pop     r14
0x18000d86f  pop     rdi
0x18000d870  pop     rbp
0x18000d871  retn
```
