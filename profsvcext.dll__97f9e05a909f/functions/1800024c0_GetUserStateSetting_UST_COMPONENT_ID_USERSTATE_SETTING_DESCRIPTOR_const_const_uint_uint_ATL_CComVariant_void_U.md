# GetUserStateSetting(UST_COMPONENT_ID,USERSTATE_SETTING_DESCRIPTOR const * const,uint,uint,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES,ushort const *)

- ea: `0x1800024c0`
- end: `0x1800025a4`
- name: `?GetUserStateSetting@@YAJW4UST_COMPONENT_ID@@QEBUUSERSTATE_SETTING_DESCRIPTOR@@IIAEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@PEBG@Z`
- size: `228`
- prototype: `__int64 __fastcall(unsigned int, __int64, unsigned int, __int64, VARIANTARG *, void *, int)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001898`
- `0x1800019b0`
- `0x180002320`
- `0x1800079f0`
- `0x1800101f4`

## callees

- `0x1800019b0`
- `0x1800024c0`
- `0x18001afa0`

## pseudocode

```c
__int64 __fastcall GetUserStateSetting(
        unsigned int a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        VARIANTARG *a5,
        void *a6,
        int a7)
{
  unsigned int v7; // r14d
  __int64 i; // rax
  _DWORD *v9; // rbx
  int v10; // edi
  __int64 result; // rax

  v7 = a1;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= a3 )
      return 2147942487LL;
    v9 = (_DWORD *)(a2 + 72 * i);
    if ( *v9 == (_DWORD)a4 )
      break;
  }
  v10 = a7;
  if ( !a7 )
    v10 = v9[2];
  if ( (v10 & 3) != 3 )
    return GetUserStateSettingPriv(a1, (__int64)v9, a5, a6, v10, 0);
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_313c576492293c0704086ae70e07ed75_Traceguids, a4);
  }
  result = GetUserStateSettingPriv(v7, (__int64)v9, a5, a6, v10 & 0xFFFFFFFE, 0);
  if ( (int)result < 0 || (_DWORD)result == 1 )
  {
    v10 &= ~2u;
    a1 = v7;
    return GetUserStateSettingPriv(a1, (__int64)v9, a5, a6, v10, 0);
  }
  return result;
}

```

## disassembly

```asm
0x1800024c0  push    r14
0x1800024c2  sub     rsp, 30h
0x1800024c6  mov     r14d, ecx
0x1800024c9  mov     [rsp+38h+arg_0], rbx
0x1800024ce  xor     eax, eax
0x1800024d0  cmp     eax, r8d
0x1800024d3  jnb     loc_18000259D
0x1800024d9  lea     r11, [rax+rax*8]
0x1800024dd  cmp     [rdx+r11*8], r9d
0x1800024e1  lea     rbx, [rdx+r11*8]
0x1800024e5  jz      short loc_1800024EB
0x1800024e7  inc     eax
0x1800024e9  jmp     short loc_1800024D0
0x1800024eb  mov     [rsp+38h+arg_8], rdi
0x1800024f0  mov     edi, [rsp+38h+arg_30]
0x1800024f4  test    edi, edi
0x1800024f6  jnz     short loc_1800024FB
0x1800024f8  mov     edi, [rbx+8]
0x1800024fb  mov     eax, edi
0x1800024fd  and     eax, 3
0x180002500  cmp     al, 3
0x180002502  jz      short loc_180002534
0x180002504  mov     r9, [rsp+38h+arg_28]
0x180002509  mov     rdx, rbx
0x18000250c  mov     r8, [rsp+38h+arg_20]
0x180002511  mov     [rsp+38h+var_10], 0
0x18000251a  mov     [rsp+38h+var_18], edi
0x18000251e  call    ?GetUserStateSettingPriv@@YAJW4UST_COMPONENT_ID@@PEBUUSERSTATE_SETTING_DESCRIPTOR@@AEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@PEBG@Z; GetUserStateSettingPriv(UST_COMPONENT_ID,USERSTATE_SETTING_DESCRIPTOR const *,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES,ushort const *)
0x180002523  mov     rdi, [rsp+38h+arg_8]
0x180002528  mov     rbx, [rsp+38h+arg_0]
0x18000252d  add     rsp, 30h
0x180002531  pop     r14
0x180002533  retn
0x180002534  mov     rcx, cs:WPP_GLOBAL_Control
0x18000253b  lea     rax, WPP_GLOBAL_Control
0x180002542  cmp     rcx, rax
0x180002545  jz      short loc_180002562
0x180002547  test    byte ptr [rcx+1Ch], 2
0x18000254b  jz      short loc_180002562
0x18000254d  mov     rcx, [rcx+10h]
0x180002551  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x180002558  mov     edx, 21h ; '!'
0x18000255d  call    WPP_SF_
0x180002562  mov     r9, [rsp+38h+arg_28]
0x180002567  mov     eax, edi
0x180002569  mov     r8, [rsp+38h+arg_20]
0x18000256e  and     eax, 0FFFFFFFEh
0x180002571  mov     [rsp+38h+var_10], 0
0x18000257a  mov     rdx, rbx
0x18000257d  mov     ecx, r14d
0x180002580  mov     [rsp+38h+var_18], eax
0x180002584  call    ?GetUserStateSettingPriv@@YAJW4UST_COMPONENT_ID@@PEBUUSERSTATE_SETTING_DESCRIPTOR@@AEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@PEBG@Z; GetUserStateSettingPriv(UST_COMPONENT_ID,USERSTATE_SETTING_DESCRIPTOR const *,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES,ushort const *)
0x180002589  test    eax, eax
0x18000258b  js      short loc_180002592
0x18000258d  cmp     eax, 1
0x180002590  jnz     short loc_180002523
0x180002592  and     edi, 0FFFFFFFDh
0x180002595  mov     ecx, r14d
0x180002598  jmp     loc_180002504
0x18000259d  mov     eax, 80070057h
0x1800025a2  jmp     short loc_180002528
```
