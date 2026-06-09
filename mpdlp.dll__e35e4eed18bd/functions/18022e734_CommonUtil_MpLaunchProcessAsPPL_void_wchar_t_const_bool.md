# CommonUtil::MpLaunchProcessAsPPL(void * *,wchar_t const *,bool)

- ea: `0x18022e734`
- end: `0x18022e9b3`
- name: `?MpLaunchProcessAsPPL@CommonUtil@@YAJPEAPEAXPEB_W_N@Z`
- size: `639`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, void **, const wchar_t *, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18022e194`

## callees

- `0x1800809d0`
- `0x1800af840`
- `0x1800ccf98`
- `0x180105f50`
- `0x18010cb40`
- `0x18010ce3c`
- `0x18022e018`
- `0x18022e734`
- `0x18023a310`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18022e791`
- `KERNEL32!GetLastError` at `0x18022e791`
- `KERNEL32!UpdateProcThreadAttribute` at `0x18022e8b2`
- `KERNEL32!UpdateProcThreadAttribute` at `0x18022e8b2`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x18022e787`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x18022e81d`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x18022e787`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x18022e81d`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpLaunchProcessAsPPL(CommonUtil *this, void **a2, const wchar_t *a3)
{
  unsigned int LastFailure; // eax
  int v6; // ebx
  const struct std::nothrow_t *v8; // rdx
  LPPROC_THREAD_ATTRIBUTE_LIST v9; // rbx
  unsigned int v10; // eax
  const struct std::nothrow_t *v11; // rdx
  int Process; // edi
  _QWORD *v13; // r10
  __int64 v14; // rdx
  const struct std::nothrow_t *v15; // rdx
  struct _SECURITY_ATTRIBUTES *v16; // [rsp+38h] [rbp-81h]
  LPPROC_THREAD_ATTRIBUTE_LIST v17; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v18[26]; // [rsp+60h] [rbp-59h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST v19; // [rsp+C8h] [rbp+Fh]
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList[2]; // [rsp+D0h] [rbp+17h] BYREF
  int Value; // [rsp+E0h] [rbp+27h] BYREF
  ULONG_PTR Size; // [rsp+E8h] [rbp+2Fh] BYREF

  memset(&v18[1], 0, 0x64u);
  v18[0] = 112;
  Size = 0;
  if ( !InitializeProcThreadAttributeList(0, 1u, 0, &Size) && GetLastError() != 122 )
  {
    LastFailure = HrGetLastFailure();
    v6 = LastFailure;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_df4475de42c930d043888ffd5b211355_Traceguids, LastFailure);
    return (unsigned int)v6;
  }
  lpAttributeList[0] = 0;
  v6 = CommonUtil::MpNewBuffer<unsigned char>(lpAttributeList, Size);
  if ( v6 < 0 )
  {
    if ( lpAttributeList[0] )
      operator delete(lpAttributeList[0], v8);
    return (unsigned int)v6;
  }
  v9 = lpAttributeList[0];
  v17 = lpAttributeList[0];
  if ( !InitializeProcThreadAttributeList(lpAttributeList[0], 1u, 0, &Size) )
  {
    v10 = HrGetLastFailure();
    Process = v10;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_df4475de42c930d043888ffd5b211355_Traceguids, v10);
    goto LABEL_14;
  }
  lpAttributeList[1] = (LPPROC_THREAD_ATTRIBUTE_LIST)&v17;
  LOBYTE(lpAttributeList[0]) = 0;
  Value = -1;
  if ( !UpdateProcThreadAttribute(v17, 0, 0x2000Bu, &Value, 4u, 0, 0) )
  {
    Process = HrGetLastFailure();
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_22;
    v14 = 12;
LABEL_21:
    WPP_SF_d(v13[2], v14, &WPP_df4475de42c930d043888ffd5b211355_Traceguids, (unsigned int)Process);
LABEL_22:
    CommonUtil::ScopeGuardImpl__lambda_684ff7778f6737aba85595ac0c0ae798___::_ScopeGuardImpl__lambda_684ff7778f6737aba85595ac0c0ae798___(lpAttributeList);
LABEL_14:
    if ( v9 )
      operator delete(v9, v11);
    return (unsigned int)Process;
  }
  LOBYTE(v16) = 1;
  v19 = v17;
  Process = CommonUtil::UtilCreateProcess(
              this,
              a2,
              (const wchar_t *)0xC0000,
              (unsigned int)v18,
              0,
              0,
              0,
              v16,
              0,
              0,
              (const wchar_t *)v17);
  if ( Process < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_22;
    v14 = 13;
    goto LABEL_21;
  }
  CommonUtil::ScopeGuardImpl__lambda_684ff7778f6737aba85595ac0c0ae798___::_ScopeGuardImpl__lambda_684ff7778f6737aba85595ac0c0ae798___(lpAttributeList);
  if ( v9 )
    operator delete(v9, v15);
  return 0;
}

```

## disassembly

```asm
0x18022e734  mov     [rsp-8+arg_10], rbx
0x18022e739  push    rbp
0x18022e73a  push    rsi
0x18022e73b  push    rdi
0x18022e73c  lea     rbp, [rsp-47h]
0x18022e741  sub     rsp, 100h
0x18022e748  mov     rax, cs:__security_cookie
0x18022e74f  xor     rax, rsp
0x18022e752  mov     [rbp+57h+var_20], rax
0x18022e756  mov     rsi, rdx
0x18022e759  mov     rdi, rcx
0x18022e75c  xor     edx, edx; Val
0x18022e75e  lea     rcx, [rbp+57h+var_AC]; void *
0x18022e762  lea     r8d, [rdx+64h]; Size
0x18022e766  call    memset
0x18022e76b  xor     r8d, r8d; dwFlags
0x18022e76e  mov     [rbp+57h+var_B0], 70h ; 'p'
0x18022e775  lea     r9, [rbp+57h+Size]; lpSize
0x18022e779  mov     [rbp+57h+Size], 0
0x18022e781  xor     ecx, ecx; lpAttributeList
0x18022e783  lea     edx, [r8+1]; dwAttributeCount
0x18022e787  call    cs:__imp_InitializeProcThreadAttributeList
0x18022e78d  test    eax, eax
0x18022e78f  jnz     short loc_18022E7DC
0x18022e791  call    cs:__imp_GetLastError
0x18022e797  cmp     eax, 7Ah ; 'z'
0x18022e79a  jz      short loc_18022E7DC
0x18022e79c  call    HrGetLastFailure
0x18022e7a1  mov     ebx, eax
0x18022e7a3  mov     r10, cs:WPP_GLOBAL_Control
0x18022e7aa  lea     rcx, WPP_GLOBAL_Control
0x18022e7b1  cmp     r10, rcx
0x18022e7b4  jz      short loc_18022E7D5
0x18022e7b6  test    byte ptr [r10+1Ch], 1
0x18022e7bb  jz      short loc_18022E7D5
0x18022e7bd  mov     rcx, [r10+10h]
0x18022e7c1  lea     r8, WPP_df4475de42c930d043888ffd5b211355_Traceguids
0x18022e7c8  mov     edx, 0Ah
0x18022e7cd  mov     r9d, eax
0x18022e7d0  call    WPP_SF_d
0x18022e7d5  mov     eax, ebx
0x18022e7d7  jmp     loc_18022E994
0x18022e7dc  mov     rdx, [rbp+57h+Size]
0x18022e7e0  lea     rcx, [rbp+57h+lpAttributeList]
0x18022e7e4  mov     [rbp+57h+lpAttributeList], 0
0x18022e7ec  call    ??$MpNewBuffer@E@CommonUtil@@YAJPEAPEAE_K@Z; CommonUtil::MpNewBuffer<uchar>(uchar * *,unsigned __int64)
0x18022e7f1  mov     ebx, eax
0x18022e7f3  test    eax, eax
0x18022e7f5  jns     short loc_18022E807
0x18022e7f7  mov     rcx, [rbp+57h+lpAttributeList]; void *
0x18022e7fb  test    rcx, rcx
0x18022e7fe  jz      short loc_18022E7D5
0x18022e800  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18022e805  jmp     short loc_18022E7D5
0x18022e807  mov     rbx, [rbp+57h+lpAttributeList]
0x18022e80b  lea     r9, [rbp+57h+Size]; lpSize
0x18022e80f  xor     r8d, r8d; dwFlags
0x18022e812  mov     [rbp+57h+var_C0], rbx
0x18022e816  mov     rcx, rbx; lpAttributeList
0x18022e819  lea     edx, [r8+1]; dwAttributeCount
0x18022e81d  call    cs:__imp_InitializeProcThreadAttributeList
0x18022e823  test    eax, eax
0x18022e825  jnz     short loc_18022E874
0x18022e827  call    HrGetLastFailure
0x18022e82c  mov     edi, eax
0x18022e82e  mov     r10, cs:WPP_GLOBAL_Control
0x18022e835  lea     rcx, WPP_GLOBAL_Control
0x18022e83c  cmp     r10, rcx
0x18022e83f  jz      short loc_18022E860
0x18022e841  test    byte ptr [r10+1Ch], 1
0x18022e846  jz      short loc_18022E860
0x18022e848  mov     rcx, [r10+10h]
0x18022e84c  lea     r8, WPP_df4475de42c930d043888ffd5b211355_Traceguids
0x18022e853  mov     edx, 0Bh
0x18022e858  mov     r9d, eax
0x18022e85b  call    WPP_SF_d
0x18022e860  test    rbx, rbx
0x18022e863  jz      short loc_18022E86D
0x18022e865  mov     rcx, rbx; void *
0x18022e868  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18022e86d  mov     eax, edi
0x18022e86f  jmp     loc_18022E994
0x18022e874  mov     rcx, [rbp+57h+var_C0]; lpAttributeList
0x18022e878  lea     rax, [rbp+57h+var_C0]
0x18022e87c  mov     [rsp+110h+lpReturnSize], 0; lpReturnSize
0x18022e885  lea     r9, [rbp+57h+Value]; lpValue
0x18022e889  mov     [rsp+110h+lpPreviousValue], 0; lpPreviousValue
0x18022e892  xor     edx, edx; dwFlags
0x18022e894  mov     r8d, 2000Bh; Attribute
0x18022e89a  mov     [rbp+57h+var_38], rax
0x18022e89e  mov     [rsp+110h+cbSize], 4; cbSize
0x18022e8a7  mov     byte ptr [rbp+57h+lpAttributeList], 0
0x18022e8ab  mov     [rbp+57h+Value], 0FFFFFFFFh
0x18022e8b2  call    cs:__imp_UpdateProcThreadAttribute
0x18022e8b8  test    eax, eax
0x18022e8ba  jnz     short loc_18022E903
0x18022e8bc  call    HrGetLastFailure
0x18022e8c1  mov     edi, eax
0x18022e8c3  mov     r10, cs:WPP_GLOBAL_Control
0x18022e8ca  lea     rcx, WPP_GLOBAL_Control
0x18022e8d1  cmp     r10, rcx
0x18022e8d4  jz      short loc_18022E8F5
0x18022e8d6  test    byte ptr [r10+1Ch], 1
0x18022e8db  jz      short loc_18022E8F5
0x18022e8dd  mov     edx, 0Ch
0x18022e8e2  mov     rcx, [r10+10h]
0x18022e8e6  lea     r8, WPP_df4475de42c930d043888ffd5b211355_Traceguids
0x18022e8ed  mov     r9d, edi
0x18022e8f0  call    WPP_SF_d
0x18022e8f5  lea     rcx, [rbp+57h+lpAttributeList]
0x18022e8f9  call    CommonUtil__ScopeGuardImpl__lambda_684ff7778f6737aba85595ac0c0ae798______ScopeGuardImpl__lambda_684ff7778f6737aba85595ac0c0ae798___
0x18022e8fe  jmp     loc_18022E860
0x18022e903  mov     rax, [rbp+57h+var_C0]
0x18022e907  lea     r9, [rbp+57h+var_B0]; unsigned int
0x18022e90b  mov     [rsp+110h+var_C8], 0; void *
0x18022e914  mov     r8d, 0C0000h; wchar_t *
0x18022e91a  mov     qword ptr [rsp+110h+var_D0], 0; bool
0x18022e923  mov     rdx, rsi; void **
0x18022e926  mov     byte ptr [rsp+110h+var_D8], 1; struct _SECURITY_ATTRIBUTES *
0x18022e92b  mov     rcx, rdi; this
0x18022e92e  mov     [rsp+110h+lpReturnSize], 0; struct _SECURITY_ATTRIBUTES *
0x18022e937  mov     [rsp+110h+lpPreviousValue], 0; wchar_t *
0x18022e940  mov     [rsp+110h+cbSize], 0; struct _STARTUPINFOW *
0x18022e949  mov     [rbp+57h+var_48], rax
0x18022e94d  call    ?UtilCreateProcess@CommonUtil@@YAJPEAPEAXPEB_WKPEAU_STARTUPINFOW@@1PEAU_SECURITY_ATTRIBUTES@@3_NPEAX1@Z; CommonUtil::UtilCreateProcess(void * *,wchar_t const *,ulong,_STARTUPINFOW *,wchar_t const *,_SECURITY_ATTRIBUTES *,_SECURITY_ATTRIBUTES *,bool,void *,wchar_t const *)
0x18022e952  mov     edi, eax
0x18022e954  test    eax, eax
0x18022e956  jns     short loc_18022E97C
0x18022e958  mov     r10, cs:WPP_GLOBAL_Control
0x18022e95f  lea     rcx, WPP_GLOBAL_Control
0x18022e966  cmp     r10, rcx
0x18022e969  jz      short loc_18022E8F5
0x18022e96b  test    byte ptr [r10+1Ch], 1
0x18022e970  jz      short loc_18022E8F5
0x18022e972  mov     edx, 0Dh
0x18022e977  jmp     loc_18022E8E2
0x18022e97c  lea     rcx, [rbp+57h+lpAttributeList]
0x18022e980  call    CommonUtil__ScopeGuardImpl__lambda_684ff7778f6737aba85595ac0c0ae798______ScopeGuardImpl__lambda_684ff7778f6737aba85595ac0c0ae798___
0x18022e985  test    rbx, rbx
0x18022e988  jz      short loc_18022E992
0x18022e98a  mov     rcx, rbx; void *
0x18022e98d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18022e992  xor     eax, eax
0x18022e994  mov     rcx, [rbp+57h+var_20]
0x18022e998  xor     rcx, rsp; StackCookie
0x18022e99b  call    __security_check_cookie
0x18022e9a0  mov     rbx, [rsp+110h+arg_10]
0x18022e9a8  add     rsp, 100h
0x18022e9af  pop     rdi
0x18022e9b0  pop     rsi
0x18022e9b1  pop     rbp
0x18022e9b2  retn
```
