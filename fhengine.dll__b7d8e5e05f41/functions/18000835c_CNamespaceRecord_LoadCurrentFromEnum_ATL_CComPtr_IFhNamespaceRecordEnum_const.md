# CNamespaceRecord::LoadCurrentFromEnum(ATL::CComPtr<IFhNamespaceRecordEnum> const &)

- ea: `0x18000835c`
- end: `0x18000847d`
- name: `?LoadCurrentFromEnum@CNamespaceRecord@@QEAAJAEBV?$CComPtr@UIFhNamespaceRecordEnum@@@ATL@@@Z`
- size: `289`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `10`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a4ac`
- `0x18000a818`
- `0x18000d4f4`
- `0x180010b18`
- `0x180010de8`
- `0x180013e14`
- `0x18001789c`
- `0x180017c68`
- `0x18001afe4`
- `0x18001f92c`

## callees

- `0x180007818`
- `0x18000835c`
- `0x180034010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180008397`
- `OLEAUT32!__imp_SysFreeString` at `0x180008397`

## pseudocode

```c
__int64 __fastcall CNamespaceRecord::LoadCurrentFromEnum(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // r13
  int v5; // ebx
  __int64 v7; // [rsp+C0h] [rbp+8h]
  __int64 v8; // [rsp+C8h] [rbp+10h] BYREF

  v8 = 0;
  v7 = a1 + 16;
  v4 = (_QWORD *)(a1 + 24);
  SysFreeString(*(BSTR *)(a1 + 24));
  *v4 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64 *, __int64))(*(_QWORD *)*a2 + 48LL))(
         *a2,
         v7,
         v4,
         v7 + 16,
         a1 + 36,
         a1 + 40,
         a1 + 56,
         a1 + 60,
         a1 + 68,
         a1 + 48,
         a1 + 76,
         a1 + 80,
         &v8,
         a1 + 84);
  if ( v5 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_d0c10813b8dd33525641bcb4dab89869_Traceguids, (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000835c  mov     rax, rsp
0x18000835f  mov     [rax+18h], rbx
0x180008363  push    rbp
0x180008364  push    rsi
0x180008365  push    rdi
0x180008366  push    r12
0x180008368  push    r13
0x18000836a  push    r14
0x18000836c  push    r15
0x18000836e  sub     rsp, 80h
0x180008375  mov     rbx, rdx
0x180008378  mov     r12, rcx
0x18000837b  mov     qword ptr [rax+10h], 0
0x180008383  lea     rax, [rcx+10h]
0x180008387  mov     [rsp+0B8h+arg_0], rax
0x18000838f  lea     r13, [rax+8]
0x180008393  mov     rcx, [r13+0]; bstrString
0x180008397  call    cs:__imp_SysFreeString
0x18000839d  mov     qword ptr [r13+0], 0
0x1800083a5  mov     rcx, [rbx]
0x1800083a8  mov     rax, [rcx]
0x1800083ab  lea     r10, [r12+54h]
0x1800083b0  lea     r11, [r12+50h]
0x1800083b5  lea     rbx, [r12+4Ch]
0x1800083ba  lea     rdi, [r12+30h]
0x1800083bf  lea     rsi, [r12+44h]
0x1800083c4  lea     rbp, [r12+3Ch]
0x1800083c9  lea     r14, [r12+38h]
0x1800083ce  lea     r15, [r12+28h]
0x1800083d3  add     r12, 24h ; '$'
0x1800083d7  mov     rdx, [rsp+0B8h+arg_0]
0x1800083df  lea     r9, [rdx+10h]
0x1800083e3  mov     [rsp+0B8h+var_50], r10
0x1800083e8  lea     r8, [rsp+0B8h+arg_8]
0x1800083f0  mov     [rsp+0B8h+var_58], r8
0x1800083f5  mov     [rsp+0B8h+var_60], r11
0x1800083fa  mov     [rsp+0B8h+var_68], rbx
0x1800083ff  mov     [rsp+0B8h+var_70], rdi
0x180008404  mov     [rsp+0B8h+var_78], rsi
0x180008409  mov     [rsp+0B8h+var_80], rbp
0x18000840e  mov     [rsp+0B8h+var_88], r14
0x180008413  mov     [rsp+0B8h+var_90], r15
0x180008418  mov     [rsp+0B8h+var_98], r12
0x18000841d  mov     r8, r13
0x180008420  mov     rax, [rax+30h]
0x180008424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008429  mov     ebx, eax
0x18000842b  test    eax, eax
0x18000842d  jns     short loc_180008460
0x18000842f  lea     rax, WPP_GLOBAL_Control
0x180008436  mov     rcx, cs:WPP_GLOBAL_Control
0x18000843d  cmp     rcx, rax
0x180008440  jz      short loc_180008460
0x180008442  test    byte ptr [rcx+1Ch], 1
0x180008446  jz      short loc_180008460
0x180008448  mov     edx, 15h
0x18000844d  mov     r9d, ebx
0x180008450  lea     r8, WPP_d0c10813b8dd33525641bcb4dab89869_Traceguids
0x180008457  mov     rcx, [rcx+10h]
0x18000845b  call    WPP_SF_d
0x180008460  mov     eax, ebx
0x180008462  mov     rbx, [rsp+0B8h+arg_10]
0x18000846a  add     rsp, 80h
0x180008471  pop     r15
0x180008473  pop     r14
0x180008475  pop     r13
0x180008477  pop     r12
0x180008479  pop     rdi
0x18000847a  pop     rsi
0x18000847b  pop     rbp
0x18000847c  retn
```
