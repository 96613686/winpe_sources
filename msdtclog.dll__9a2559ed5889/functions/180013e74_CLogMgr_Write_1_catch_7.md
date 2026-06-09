# _CLogMgr::_Write_::_1_::catch$7

- ea: `0x180013e74`
- end: `0x180013f40`
- name: `_CLogMgr::_Write_::_1_::catch$7`
- size: `204`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000d998`
- `0x18001266c`
- `0x180013e74`
- `0x180015010`

## string_xrefs

- `0x180013f17`: `com\complus\dtc\dtc\log\logmgr\src\logmgr.cpp`

## pseudocode

```c
void __fastcall __noreturn CLogMgr::_Write_::_1_::catch_7(__int64 a1, __int64 a2)
{
  int v3; // eax
  __int64 v4; // rcx
  int v5; // ebx

  v3 = -2147467259;
  v4 = *(_QWORD *)(a2 + 192);
  v5 = *(_DWORD *)(a2 + 88);
  if ( !*(_QWORD *)(v4 + 24)
    || v5 != -1073737699 && (!*(_QWORD *)(v4 + 24) || v5 != -1073737670)
    || (v3 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v4 + 24) + 24LL))(
               *(_QWORD *)(v4 + 24),
               4097,
               4),
        v3 < 0) )
  {
    TraceFile(v3, "failed in m_pIDtcTrace->Trace", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logmgr.cpp", 1356);
  }
  *(_DWORD *)(a2 + 92) = v5;
  throw (ulong *)(a2 + 92);
}

```

## disassembly

```asm
0x180013e74  mov     [rsp+arg_8], rdx
0x180013e79  push    rbx
0x180013e7a  push    rbp
0x180013e7b  sub     rsp, 58h
0x180013e7f  mov     rbp, rdx
0x180013e82  mov     eax, 80004005h
0x180013e87  mov     rcx, [rbp+0C0h]
0x180013e8e  mov     ebx, [rbp+58h]
0x180013e91  cmp     qword ptr [rcx+18h], 0
0x180013e96  jz      short loc_180013F11
0x180013e98  cmp     ebx, 0C000101Dh
0x180013e9e  jnz     short loc_180013EC0
0x180013ea0  mov     [rsp+68h+var_30], 0
0x180013ea9  mov     [rsp+68h+var_38], 0
0x180013eb2  mov     [rsp+68h+var_40], 0
0x180013eba  mov     [rsp+68h+var_48], ebx
0x180013ebe  jmp     short loc_180013EED
0x180013ec0  cmp     qword ptr [rcx+18h], 0
0x180013ec5  jz      short loc_180013F11
0x180013ec7  cmp     ebx, 0C000103Ah
0x180013ecd  jnz     short loc_180013F11
0x180013ecf  mov     [rsp+68h+var_30], 0
0x180013ed8  mov     [rsp+68h+var_38], 0
0x180013ee1  mov     [rsp+68h+var_40], 0
0x180013ee9  mov     [rsp+68h+var_48], ebx
0x180013eed  mov     rax, [rcx+18h]
0x180013ef1  mov     rdx, [rax]
0x180013ef4  mov     rax, [rdx+18h]
0x180013ef8  xor     r9d, r9d
0x180013efb  lea     r8d, [r9+4]
0x180013eff  mov     edx, 1001h
0x180013f04  mov     rcx, [rcx+18h]
0x180013f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f0d  test    eax, eax
0x180013f0f  jns     short loc_180013F2C
0x180013f11  mov     r9d, 54Ch; unsigned int
0x180013f17  lea     r8, aComComplusDtcD_3; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x180013f1e  lea     rdx, aFailedInMPidtc; "failed in m_pIDtcTrace->Trace"
0x180013f25  mov     ecx, eax; int
0x180013f27  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180013f2c  mov     [rbp+5Ch], ebx
0x180013f2f  lea     rdx, _TI1K; pThrowInfo
0x180013f36  lea     rcx, [rbp+5Ch]; pExceptionObject
0x180013f3a  call    _CxxThrowException_0
```
