# PortMgrDeletePort

- ea: `0x180016e80`
- end: `0x1800170b3`
- name: `PortMgrDeletePort`
- size: `563`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180018700`

## callees

- `0x180004f40`
- `0x180005440`
- `0x180016e80`
- `0x18001e824`
- `0x1800214f0`
- `0x180023b14`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180016fc9`
- `MobileNetworking!ReleaseWriteLock` at `0x180016ff3`
- `MobileNetworking!ReleaseWriteLock` at `0x180016fc9`
- `MobileNetworking!ReleaseWriteLock` at `0x180016ff3`
- `MobileNetworking!AcquireWriteLock` at `0x180016f46`
- `MobileNetworking!AcquireWriteLock` at `0x180016f46`

## string_xrefs

- `0x180016f31`: `PortMgrFindInGlobalListAndRemove`
- `0x180016fb5`: `PortMgrFindInGlobalListAndRemove`
- `0x180016fde`: `PortMgrFindInGlobalListAndRemove`

## pseudocode

```c
__int64 __fastcall PortMgrDeletePort(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v4; // rcx
  unsigned int v5; // edi
  __int64 *i; // rax
  __int64 v7; // rcx
  __int64 *v8; // rdx
  __int64 **v9; // r8

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 51, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x800) != 0 )
    {
      WPP_SF_(v4[7], 36, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
  }
  if ( a1 )
  {
    AcquireWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrFindInGlobalListAndRemove", 310);
    for ( i = (__int64 *)qword_18003DD68; ; i = (__int64 *)*i )
    {
      if ( i == &qword_18003DD68 )
      {
        ReleaseWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrFindInGlobalListAndRemove", 339);
        v5 = 6;
        goto LABEL_21;
      }
      v7 = *i;
      if ( (__int64 *)a1 == i )
        break;
    }
    if ( *(__int64 **)(v7 + 8) != i
      || (v8 = (__int64 *)i[1], (__int64 *)*v8 != i)
      || (*v8 = v7,
          *(_QWORD *)(v7 + 8) = v8,
          v9 = (__int64 **)qword_18003DD80,
          *(__int64 **)qword_18003DD80 != &qword_18003DD78) )
    {
      __fastfail(3u);
    }
    *i = (__int64)&qword_18003DD78;
    i[1] = (__int64)v9;
    *v9 = i;
    v5 = 0;
    qword_18003DD80 = (__int64)i;
    ReleaseWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrFindInGlobalListAndRemove", 339);
    goto LABEL_21;
  }
  v5 = 6;
  if ( v4 == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)v4 + 68) & 1) != 0 )
  {
    WPP_SF_(v4[7], 37, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
LABEL_21:
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v4[7], 38, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v5);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v5 )
  {
    if ( v4 == &WPP_GLOBAL_Control )
      return v5;
    if ( (*((_BYTE *)v4 + 68) & 1) == 0 )
      goto LABEL_33;
    WPP_SF_qd(v4[7], a2, a3, a1, v5);
  }
  else
  {
    if ( (Microsoft_Windows_OneXEnableBits & 1) != 0 )
      McTemplateU0q_EtwEventWriteTransfer(v4, SupplicantPortDestroyed, *(unsigned int *)(a1 + 20));
    PortMgrDeletePortHelper(a1);
  }
  v4 = WPP_GLOBAL_Control;
LABEL_33:
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x800) != 0 )
    WPP_SF_D(v4[7], 53, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180016e80  mov     [rsp+arg_8], rbx
0x180016e85  push    rsi
0x180016e86  sub     rsp, 30h
0x180016e8a  mov     rbx, rcx
0x180016e8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e94  lea     rsi, WPP_GLOBAL_Control
0x180016e9b  cmp     rcx, rsi
0x180016e9e  jz      short loc_180016EEF
0x180016ea0  test    dword ptr [rcx+44h], 800h
0x180016ea7  jz      short loc_180016EC5
0x180016ea9  mov     rcx, [rcx+38h]
0x180016ead  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180016eb4  mov     edx, 33h ; '3'
0x180016eb9  call    WPP_SF_
0x180016ebe  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ec5  cmp     rcx, rsi
0x180016ec8  jz      short loc_180016EEF
0x180016eca  test    dword ptr [rcx+44h], 800h
0x180016ed1  jz      short loc_180016EEF
0x180016ed3  mov     rcx, [rcx+38h]
0x180016ed7  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180016ede  mov     edx, 24h ; '$'
0x180016ee3  call    WPP_SF_
0x180016ee8  mov     rcx, cs:WPP_GLOBAL_Control
0x180016eef  mov     [rsp+38h+arg_0], rdi
0x180016ef4  test    rbx, rbx
0x180016ef7  jnz     short loc_180016F2B
0x180016ef9  mov     edi, 6
0x180016efe  cmp     rcx, rsi
0x180016f01  jz      loc_1800170A1
0x180016f07  test    byte ptr [rcx+44h], 1
0x180016f0b  jz      loc_180017005
0x180016f11  mov     rcx, [rcx+38h]
0x180016f15  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180016f1c  mov     edx, 25h ; '%'
0x180016f21  call    WPP_SF_
0x180016f26  jmp     loc_180016FFE
0x180016f2b  mov     r9d, 136h
0x180016f31  lea     r8, aPortmgrfinding; "PortMgrFindInGlobalListAndRemove"
0x180016f38  lea     rdx, qword_18003DD98
0x180016f3f  lea     rcx, g_OneXInfo
0x180016f46  call    cs:__imp_AcquireWriteLock
0x180016f4c  mov     rax, cs:qword_18003DD68
0x180016f53  lea     rdx, qword_18003DD68
0x180016f5a  nop     word ptr [rax+rax+00h]
0x180016f60  cmp     rax, rdx
0x180016f63  jz      short loc_180016FD8
0x180016f65  mov     rcx, [rax]
0x180016f68  cmp     rbx, rax
0x180016f6b  jz      short loc_180016F72
0x180016f6d  mov     rax, rcx
0x180016f70  jmp     short loc_180016F60
0x180016f72  cmp     [rcx+8], rax
0x180016f76  jnz     short loc_180016FD1
0x180016f78  mov     rdx, [rax+8]
0x180016f7c  cmp     [rdx], rax
0x180016f7f  jnz     short loc_180016FD1
0x180016f81  mov     [rdx], rcx
0x180016f84  lea     r9, qword_18003DD78
0x180016f8b  mov     [rcx+8], rdx
0x180016f8f  mov     r8, cs:qword_18003DD80
0x180016f96  cmp     [r8], r9
0x180016f99  jnz     short loc_180016FD1
0x180016f9b  mov     [rax], r9
0x180016f9e  lea     rdx, qword_18003DD98
0x180016fa5  mov     [rax+8], r8
0x180016fa9  lea     rcx, g_OneXInfo
0x180016fb0  mov     [r8], rax
0x180016fb3  xor     edi, edi
0x180016fb5  lea     r8, aPortmgrfinding; "PortMgrFindInGlobalListAndRemove"
0x180016fbc  mov     cs:qword_18003DD80, rax
0x180016fc3  mov     r9d, 153h
0x180016fc9  call    cs:__imp_ReleaseWriteLock
0x180016fcf  jmp     short loc_180016FFE
0x180016fd1  mov     ecx, 3
0x180016fd6  int     29h; Win8: RtlFailFast(ecx)
0x180016fd8  mov     r9d, 153h
0x180016fde  lea     r8, aPortmgrfinding; "PortMgrFindInGlobalListAndRemove"
0x180016fe5  lea     rdx, qword_18003DD98
0x180016fec  lea     rcx, g_OneXInfo
0x180016ff3  call    cs:__imp_ReleaseWriteLock
0x180016ff9  mov     edi, 6
0x180016ffe  mov     rcx, cs:WPP_GLOBAL_Control
0x180017005  cmp     rcx, rsi
0x180017008  jz      short loc_180017032
0x18001700a  test    dword ptr [rcx+44h], 800h
0x180017011  jz      short loc_180017032
0x180017013  mov     rcx, [rcx+38h]
0x180017017  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18001701e  mov     edx, 26h ; '&'
0x180017023  mov     r9d, edi
0x180017026  call    WPP_SF_D
0x18001702b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017032  test    edi, edi
0x180017034  jz      short loc_180017053
0x180017036  cmp     rcx, rsi
0x180017039  jz      short loc_1800170A1
0x18001703b  test    byte ptr [rcx+44h], 1
0x18001703f  jz      short loc_18001707B
0x180017041  mov     rcx, [rcx+38h]
0x180017045  mov     r9, rbx
0x180017048  mov     [rsp+38h+var_18], edi
0x18001704c  call    WPP_SF_qd
0x180017051  jmp     short loc_180017074
0x180017053  test    cs:Microsoft_Windows_OneXEnableBits, 1
0x18001705a  jz      short loc_18001706C
0x18001705c  mov     r8d, [rbx+14h]
0x180017060  lea     rdx, SupplicantPortDestroyed
0x180017067  call    McTemplateU0q_EtwEventWriteTransfer
0x18001706c  mov     rcx, rbx
0x18001706f  call    PortMgrDeletePortHelper
0x180017074  mov     rcx, cs:WPP_GLOBAL_Control
0x18001707b  cmp     rcx, rsi
0x18001707e  jz      short loc_1800170A1
0x180017080  test    dword ptr [rcx+44h], 800h
0x180017087  jz      short loc_1800170A1
0x180017089  mov     rcx, [rcx+38h]
0x18001708d  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180017094  mov     edx, 35h ; '5'
0x180017099  mov     r9d, edi
0x18001709c  call    WPP_SF_D
0x1800170a1  mov     rbx, [rsp+38h+arg_8]
0x1800170a6  mov     eax, edi
0x1800170a8  mov     rdi, [rsp+38h+arg_0]
0x1800170ad  add     rsp, 30h
0x1800170b1  pop     rsi
0x1800170b2  retn
```
