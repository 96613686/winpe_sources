# _CLogMgr::_Write_::_1_::catch$8

- ea: `0x180013f46`
- end: `0x180014011`
- name: `_CLogMgr::_Write_::_1_::catch$8`
- size: `203`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000d998`
- `0x18001266c`
- `0x180013f46`
- `0x180015010`

## string_xrefs

- `0x180013fe8`: `com\complus\dtc\dtc\log\logmgr\src\logmgr.cpp`

## pseudocode

```c
void __fastcall __noreturn CLogMgr::_Write_::_1_::catch_8(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  int v4; // ebx
  int v5; // eax

  v3 = *(_QWORD *)(a2 + 192);
  v4 = *(_DWORD *)(a2 + 96);
  if ( *(_QWORD *)(v3 + 24) && (v4 == -1073737699 || *(_QWORD *)(v3 + 24) && v4 == -1073737670) )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v3 + 24) + 24LL))(
           *(_QWORD *)(v3 + 24),
           4097,
           4);
    if ( v5 < 0 )
      TraceFile(v5, "failed in m_pIDtcTrace->Trace", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logmgr.cpp", 1386);
  }
  *(_DWORD *)(a2 + 100) = v4;
  throw (ulong *)(a2 + 100);
}

```

## disassembly

```asm
0x180013f46  mov     [rsp+arg_8], rdx
0x180013f4b  push    rbx
0x180013f4c  push    rbp
0x180013f4d  sub     rsp, 58h
0x180013f51  mov     rbp, rdx
0x180013f54  mov     rcx, [rbp+0C0h]
0x180013f5b  mov     ebx, [rbp+60h]
0x180013f5e  cmp     qword ptr [rcx+18h], 0
0x180013f63  jz      loc_180013FFD
0x180013f69  cmp     ebx, 0C000101Dh
0x180013f6f  jnz     short loc_180013F91
0x180013f71  mov     [rsp+68h+var_30], 0
0x180013f7a  mov     [rsp+68h+var_38], 0
0x180013f83  mov     [rsp+68h+var_40], 0
0x180013f8b  mov     [rsp+68h+var_48], ebx
0x180013f8f  jmp     short loc_180013FBE
0x180013f91  cmp     qword ptr [rcx+18h], 0
0x180013f96  jz      short loc_180013FFD
0x180013f98  cmp     ebx, 0C000103Ah
0x180013f9e  jnz     short loc_180013FFD
0x180013fa0  mov     [rsp+68h+var_30], 0
0x180013fa9  mov     [rsp+68h+var_38], 0
0x180013fb2  mov     [rsp+68h+var_40], 0
0x180013fba  mov     [rsp+68h+var_48], ebx
0x180013fbe  mov     rax, [rcx+18h]
0x180013fc2  mov     rdx, [rax]
0x180013fc5  mov     rax, [rdx+18h]
0x180013fc9  xor     r9d, r9d
0x180013fcc  lea     r8d, [r9+4]
0x180013fd0  mov     edx, 1001h
0x180013fd5  mov     rcx, [rcx+18h]
0x180013fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fde  test    eax, eax
0x180013fe0  jns     short loc_180013FFD
0x180013fe2  mov     r9d, 56Ah; unsigned int
0x180013fe8  lea     r8, aComComplusDtcD_3; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x180013fef  lea     rdx, aFailedInMPidtc; "failed in m_pIDtcTrace->Trace"
0x180013ff6  mov     ecx, eax; int
0x180013ff8  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180013ffd  mov     [rbp+64h], ebx
0x180014000  lea     rdx, _TI1K; pThrowInfo
0x180014007  lea     rcx, [rbp+64h]; pExceptionObject
0x18001400b  call    _CxxThrowException_0
```
