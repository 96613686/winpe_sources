# _CLogMgr::Init_::_1_::catch$3

- ea: `0x180013566`
- end: `0x180013602`
- name: `_CLogMgr::Init_::_1_::catch$3`
- size: `156`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000d998`
- `0x180013566`
- `0x180015010`

## string_xrefs

- `0x1800135d5`: `com\complus\dtc\dtc\log\logmgr\src\logmgr.cpp`

## pseudocode

```c
__int64 __fastcall CLogMgr::Init_::_1_::catch_3(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  int v4; // ebx
  int v5; // eax

  v3 = *(_QWORD *)(a2 + 256);
  v4 = *(_DWORD *)(a2 + 80);
  if ( *(_QWORD *)(v3 + 24) )
  {
    if ( v4 == -1073737662 )
    {
      v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v3 + 24) + 24LL))(
             *(_QWORD *)(v3 + 24),
             4097,
             4);
      if ( v5 < 0 )
        TraceFile(v5, "failed in m_pIDtcTrace->Trace", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logmgr.cpp", 699);
    }
  }
  *(_DWORD *)(a2 + 288) = v4;
  return 0;
}

```

## disassembly

```asm
0x180013566  mov     [rsp+arg_8], rdx
0x18001356b  push    rbx
0x18001356c  push    rbp
0x18001356d  sub     rsp, 58h
0x180013571  mov     rbp, rdx
0x180013574  mov     rcx, [rbp+100h]
0x18001357b  mov     ebx, [rbp+50h]
0x18001357e  cmp     qword ptr [rcx+18h], 0
0x180013583  jz      short loc_1800135EA
0x180013585  cmp     ebx, 0C0001042h
0x18001358b  jnz     short loc_1800135EA
0x18001358d  mov     rax, [rcx+18h]
0x180013591  mov     rdx, [rax]
0x180013594  mov     rax, [rdx+18h]
0x180013598  mov     [rsp+68h+var_30], 0
0x1800135a1  mov     [rsp+68h+var_38], 0
0x1800135aa  mov     [rsp+68h+var_40], 0
0x1800135b2  mov     [rsp+68h+var_48], ebx
0x1800135b6  xor     r9d, r9d
0x1800135b9  mov     edx, 1001h
0x1800135be  lea     r8d, [r9+4]
0x1800135c2  mov     rcx, [rcx+18h]
0x1800135c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135cb  test    eax, eax
0x1800135cd  jns     short loc_1800135EA
0x1800135cf  mov     r9d, 2BBh; unsigned int
0x1800135d5  lea     r8, aComComplusDtcD_3; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x1800135dc  lea     rdx, aFailedInMPidtc; "failed in m_pIDtcTrace->Trace"
0x1800135e3  mov     ecx, eax; int
0x1800135e5  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x1800135ea  mov     [rbp+120h], ebx
0x1800135f0  mov     rax, 0
0x1800135fa  add     rsp, 58h
0x1800135fe  pop     rbp
0x1800135ff  pop     rbx
0x180013600  retn
```
