# WcmCommon::ThreadPoolProcessLatestWorkItem<1>::WorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180022460`
- end: `0x18002274f`
- name: `?WorkCallback@?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `751`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18000d208`
- `0x180022460`
- `0x180022758`
- `0x180022788`
- `0x18002d1c4`
- `0x180047240`
- `0x180047f78`
- `0x18004f44c`
- `0x18005587c`
- `0x18007c010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180022683`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180022683`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180022638`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18002265b`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180022638`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18002265b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800224bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022614`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800224bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022614`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002249a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002249a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WcmCommon::ThreadPoolProcessLatestWorkItem<1>::WorkCallback(
        __int64 a1,
        struct _RTL_CRITICAL_SECTION *a2)
{
  HANDLE *i; // rbx
  __int64 v4; // rax
  _BYTE *v5; // rdx
  __int64 result; // rax
  _OWORD *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  _OWORD *v10; // rcx
  void ***v11; // rcx
  __int64 (__fastcall ***v12)(_QWORD, _BYTE *); // rcx
  std::_Ref_count_base *v13; // rbx
  _OWORD v14[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v15; // [rsp+40h] [rbp-C0h]
  _OWORD *v16; // [rsp+48h] [rbp-B8h]
  void (__fastcall **v17)(_OWORD *); // [rsp+50h] [rbp-B0h]
  __int64 v18; // [rsp+58h] [rbp-A8h]
  _BYTE v19[64]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v20[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+C0h] [rbp-40h]
  __int64 v22; // [rsp+C8h] [rbp-38h]
  __int64 v23; // [rsp+D0h] [rbp-30h]
  __int64 v24; // [rsp+D8h] [rbp-28h]
  _BYTE v25[56]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE *v26; // [rsp+118h] [rbp+18h]

  memset_0(v20, 0, 0x40u);
  EnterCriticalSection(a2);
  for ( i = (HANDLE *)&a2[3].SpinCount; ; i += 8 )
  {
    if ( i == &a2[5].OwningThread )
    {
      if ( a2 )
        LeaveCriticalSection(a2);
      goto LABEL_9;
    }
    if ( i[7] )
      break;
  }
  memset_0(v14, 0, 0x40u);
  v18 = v24;
  switch ( v24 & 3 )
  {
    case 0LL:
      goto LABEL_18;
    case 1LL:
      v17 = (void (__fastcall **)(_OWORD *))v23;
      v16 = (_OWORD *)v22;
      v24 = 0;
      break;
    case 2LL:
      v17 = (void (__fastcall **)(_OWORD *))v23;
      (*(void (__fastcall **)(_OWORD *, _OWORD *))(v23 + 16))(v14, v20);
      break;
    default:
LABEL_18:
      v14[0] = v20[0];
      v14[1] = v20[1];
      v15 = v21;
      v16 = (_OWORD *)v22;
      v17 = (void (__fastcall **)(_OWORD *))v23;
      break;
  }
  v8 = std::any::any((std::any *)v19, (struct std::any *)i);
  std::any::_Assign(v20, v8);
  std::any::operator=(i, v14);
  v9 = (v18 & 3) - 1;
  if ( (v18 & 3) != 1 )
    goto LABEL_32;
  v10 = v16;
LABEL_21:
  (*v17)(v10);
  while ( 1 )
  {
    if ( a2 )
      LeaveCriticalSection(a2);
    v11 = &void `RTTI Type Descriptor';
    if ( (v24 & 0xFFFFFFFFFFFFFFFCuLL) != 0 )
      v11 = (void ***)(v24 & 0xFFFFFFFFFFFFFFFCuLL);
    if ( (unsigned int)__std_type_info_compare(v11 + 1, &qword_18009A530) )
      break;
    if ( (v24 & 0xFFFFFFFFFFFFFFFCuLL) == 0
      || (unsigned int)__std_type_info_compare((v24 & 0xFFFFFFFFFFFFFFFCuLL) + 8, &qword_18009A530)
      || !v22 )
    {
      std::_Throw_bad_any_cast();
    }
    v26 = 0;
    v12 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(v22 + 56);
    if ( v12 )
    {
      v4 = (**v12)(v12, v25);
      v26 = (_BYTE *)v4;
      if ( v4 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        if ( v26 )
        {
          v5 = v25;
          LOBYTE(v5) = v26 != v25;
          (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v26 + 32LL))(v26, v5);
        }
        goto LABEL_9;
      }
    }
    std::_Xbad_function_call();
LABEL_32:
    if ( v9 == 1 )
    {
      v10 = v14;
      goto LABEL_21;
    }
  }
  if ( (v24 & 0xFFFFFFFFFFFFFFFCuLL) == 0
    || !(unsigned __int8)type_info::operator==(
                           v24 & 0xFFFFFFFFFFFFFFFCuLL,
                           &std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> `RTTI Type Descriptor') )
  {
    std::_Throw_bad_any_cast();
  }
  if ( *((_QWORD *)&v20[0] + 1) )
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v20[0] + 1) + 8LL));
  v13 = (std::_Ref_count_base *)*((_QWORD *)&v20[0] + 1);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v20[0] + 8LL))(*(_QWORD *)&v20[0]);
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
LABEL_9:
  result = (v24 & 3) - 1;
  if ( (v24 & 3) == 1 )
  {
    v7 = (_OWORD *)v22;
    return (*(__int64 (__fastcall **)(_OWORD *))v23)(v7);
  }
  if ( (v24 & 3) == 2 )
  {
    v7 = v20;
    return (*(__int64 (__fastcall **)(_OWORD *))v23)(v7);
  }
  return result;
}

```

## disassembly

```asm
0x180022460  mov     [rsp-8+arg_0], rbx
0x180022465  mov     [rsp-8+arg_10], rdi
0x18002246a  push    rbp
0x18002246b  lea     rbp, [rsp-30h]
0x180022470  sub     rsp, 130h
0x180022477  mov     rax, cs:__security_cookie
0x18002247e  xor     rax, rsp
0x180022481  mov     [rbp+30h+var_10], rax
0x180022485  mov     rdi, rdx
0x180022488  xor     edx, edx; Val
0x18002248a  lea     r8d, [rdx+40h]; Size
0x18002248e  lea     rcx, [rbp+30h+var_90]; void *
0x180022492  call    memset_0
0x180022497  mov     rcx, rdi; lpCriticalSection
0x18002249a  call    cs:__imp_EnterCriticalSection
0x1800224a0  lea     rbx, [rdi+98h]
0x1800224a7  lea     rax, [rbx+40h]
0x1800224ab  cmp     rbx, rax
0x1800224ae  jnz     loc_1800226FA
0x1800224b4  test    rdi, rdi
0x1800224b7  jz      short loc_1800224C3
0x1800224b9  mov     rcx, rdi; lpCriticalSection
0x1800224bc  call    cs:__imp_LeaveCriticalSection
0x1800224c2  nop
0x1800224c3  jmp     short loc_180022513
0x1800224c5  mov     rax, [rcx]
0x1800224c8  lea     rdx, [rbp+30h+var_50]
0x1800224cc  mov     rax, [rax]
0x1800224cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224d4  mov     rdx, rax
0x1800224d7  mov     [rbp+30h+var_18], rax
0x1800224db  test    rax, rax
0x1800224de  jz      loc_180022683
0x1800224e4  mov     rcx, [rax]
0x1800224e7  mov     rax, [rcx+10h]
0x1800224eb  mov     rcx, rdx
0x1800224ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224f3  mov     rcx, [rbp+30h+var_18]
0x1800224f7  test    rcx, rcx
0x1800224fa  jz      short loc_180022513
0x1800224fc  mov     rax, [rcx]
0x1800224ff  lea     rdx, [rbp+30h+var_50]
0x180022503  cmp     rcx, rdx
0x180022506  setnz   dl
0x180022509  mov     rax, [rax+20h]
0x18002250d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022512  nop
0x180022513  mov     rax, [rbp+30h+var_58]
0x180022517  and     eax, 3
0x18002251a  sub     rax, 1
0x18002251e  jnz     short loc_180022552
0x180022520  mov     rcx, [rbp+30h+var_68]
0x180022524  mov     rax, [rbp+30h+var_60]
0x180022528  mov     rax, [rax]
0x18002252b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022530  nop
0x180022531  mov     rcx, [rbp+30h+var_10]
0x180022535  xor     rcx, rsp; StackCookie
0x180022538  call    __security_check_cookie
0x18002253d  lea     r11, [rsp+130h+var_s0]
0x180022545  mov     rbx, [r11+10h]
0x180022549  mov     rdi, [r11+20h]
0x18002254d  mov     rsp, r11
0x180022550  pop     rbp
0x180022551  retn
0x180022552  cmp     rax, 1
0x180022556  jnz     short loc_180022531
0x180022558  lea     rcx, [rbp+30h+var_90]
0x18002255c  jmp     short loc_180022524
0x18002255e  xor     edx, edx; Val
0x180022560  lea     r8d, [rdx+40h]; Size
0x180022564  lea     rcx, [rsp+130h+var_110]; void *
0x180022569  call    memset_0
0x18002256e  nop
0x18002256f  mov     rax, [rbp+30h+var_58]
0x180022573  mov     [rsp+130h+var_D8], rax
0x180022578  and     eax, 3
0x18002257b  jz      short loc_180022591
0x18002257d  sub     rax, 1
0x180022581  jz      loc_18002270E
0x180022587  cmp     rax, 1
0x18002258b  jz      loc_1800226A4
0x180022591  movaps  xmm0, [rbp+30h+var_90]
0x180022595  movups  [rsp+130h+var_110], xmm0
0x18002259a  movaps  xmm1, [rbp+30h+var_80]
0x18002259e  movups  [rsp+130h+var_100], xmm1
0x1800225a3  movsd   xmm0, [rbp+30h+var_70]
0x1800225a8  movsd   [rsp+130h+var_F0], xmm0
0x1800225ae  mov     rax, [rbp+30h+var_68]
0x1800225b2  mov     [rsp+130h+var_E8], rax
0x1800225b7  mov     rax, [rbp+30h+var_60]
0x1800225bb  mov     [rsp+130h+var_E0], rax
0x1800225c0  mov     rdx, rbx; struct std::any *
0x1800225c3  lea     rcx, [rsp+130h+var_D0]; this
0x1800225c8  call    ??0any@std@@QEAA@$$QEAV01@@Z; std::any::any(std::any &&)
0x1800225cd  mov     rdx, rax
0x1800225d0  lea     rcx, [rbp+30h+var_90]
0x1800225d4  call    ?_Assign@any@std@@AEAAXV12@@Z; std::any::_Assign(std::any)
0x1800225d9  lea     rdx, [rsp+130h+var_110]
0x1800225de  mov     rcx, rbx
0x1800225e1  call    ??4any@std@@QEAAAEAV01@$$QEAV01@@Z; std::any::operator=(std::any &&)
0x1800225e6  nop
0x1800225e7  mov     rax, [rsp+130h+var_D8]
0x1800225ec  and     eax, 3
0x1800225ef  sub     rax, 1
0x1800225f3  jnz     loc_18002268A
0x1800225f9  mov     rcx, [rsp+130h+var_E8]
0x1800225fe  mov     rax, [rsp+130h+var_E0]
0x180022603  mov     rax, [rax]
0x180022606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002260b  nop
0x18002260c  test    rdi, rdi
0x18002260f  jz      short loc_18002261A
0x180022611  mov     rcx, rdi; lpCriticalSection
0x180022614  call    cs:__imp_LeaveCriticalSection
0x18002261a  mov     rax, [rbp+30h+var_58]
0x18002261e  and     rax, 0FFFFFFFFFFFFFFFCh
0x180022622  lea     rcx, ??_R0X@8; void `RTTI Type Descriptor'
0x180022629  cmovnz  rcx, rax
0x18002262d  add     rcx, 8
0x180022631  lea     rdx, qword_18009A530
0x180022638  call    cs:__imp___std_type_info_compare
0x18002263e  mov     rcx, [rbp+30h+var_58]
0x180022642  test    eax, eax
0x180022644  jnz     loc_18002272D
0x18002264a  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18002264e  jz      short loc_18002269E
0x180022650  add     rcx, 8
0x180022654  lea     rdx, qword_18009A530
0x18002265b  call    cs:__imp___std_type_info_compare
0x180022661  test    eax, eax
0x180022663  jnz     short loc_18002269E
0x180022665  mov     rax, [rbp+30h+var_68]
0x180022669  test    rax, rax
0x18002266c  jz      short loc_18002269E
0x18002266e  mov     [rbp+30h+var_18], 0
0x180022676  mov     rcx, [rax+38h]
0x18002267a  test    rcx, rcx
0x18002267d  jnz     loc_1800224C5
0x180022683  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180022689  nop
0x18002268a  cmp     rax, 1
0x18002268e  jnz     loc_18002260C
0x180022694  lea     rcx, [rsp+130h+var_110]
0x180022699  jmp     loc_1800225FE
0x18002269e  call    ?_Throw_bad_any_cast@std@@YAXXZ; std::_Throw_bad_any_cast(void)
0x1800226a4  mov     rax, [rbp+30h+var_60]
0x1800226a8  mov     [rsp+130h+var_E0], rax
0x1800226ad  lea     rdx, [rbp+30h+var_90]
0x1800226b1  lea     rcx, [rsp+130h+var_110]
0x1800226b6  mov     rax, [rax+10h]
0x1800226ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226bf  jmp     loc_1800225C0
0x1800226c4  lea     rbx, [rbp+30h+var_90]
0x1800226c8  mov     rax, [rbx+8]
0x1800226cc  test    rax, rax
0x1800226cf  jnz     short loc_180022749
0x1800226d1  mov     rcx, [rbx]
0x1800226d4  mov     rbx, [rbx+8]
0x1800226d8  mov     rax, [rcx]
0x1800226db  mov     rax, [rax+8]
0x1800226df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226e4  test    rbx, rbx
0x1800226e7  jz      loc_180022513
0x1800226ed  mov     rcx, rbx; this
0x1800226f0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800226f5  jmp     loc_180022513
0x1800226fa  cmp     qword ptr [rbx+38h], 0
0x1800226ff  jnz     loc_18002255E
0x180022705  add     rbx, 40h ; '@'
0x180022709  jmp     loc_1800224AB
0x18002270e  mov     rax, [rbp+30h+var_60]
0x180022712  mov     [rsp+130h+var_E0], rax
0x180022717  mov     rax, [rbp+30h+var_68]
0x18002271b  mov     [rsp+130h+var_E8], rax
0x180022720  mov     [rbp+30h+var_58], 0
0x180022728  jmp     loc_1800225C0
0x18002272d  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180022731  jz      short loc_180022743
0x180022733  lea     rdx, ??_R0?AV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@8; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> `RTTI Type Descriptor'
0x18002273a  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x18002273f  test    al, al
0x180022741  jnz     short loc_1800226C4
0x180022743  call    ?_Throw_bad_any_cast@std@@YAXXZ; std::_Throw_bad_any_cast(void)
0x180022749  lock inc dword ptr [rax+8]
0x18002274d  jmp     short loc_1800226D1
```
