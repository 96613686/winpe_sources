# ATL::CRowset<ATL::CDynamicAccessor>::MoveNext(void)

- ea: `0x1800094a8`
- end: `0x1800095fd`
- name: `?MoveNext@?$CRowset@VCDynamicAccessor@ATL@@@ATL@@QEAAJXZ`
- size: `341`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800099e4`

## callees

- `0x18000278c`
- `0x180008db4`
- `0x1800094a8`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CRowset<ATL::CDynamicAccessor>::MoveNext(_QWORD *a1)
{
  _QWORD *v2; // rsi
  int v3; // edi
  unsigned int v4; // r14d
  unsigned int i; // ebp
  __int64 *v6; // r9
  __int64 v7; // rdx
  _QWORD *v9; // [rsp+70h] [rbp+8h] BYREF
  __int64 v10; // [rsp+78h] [rbp+10h] BYREF

  v10 = 0;
  ATL::CDynamicAccessor::FreeRecordMemory((ATL::CDynamicAccessor *)a1[2], (struct IRowset *)*a1);
  v2 = a1 + 3;
  if ( a1[3] )
  {
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*a1 + 48LL))(
      *a1,
      1,
      a1 + 3,
      0,
      0,
      0);
    *v2 = 0;
  }
  v9 = a1 + 3;
  v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int64 *, _QWORD **))(*(_QWORD *)*a1 + 40LL))(
         *a1,
         0,
         0,
         1,
         &v10,
         &v9);
  if ( !v3 )
  {
    v4 = *(_DWORD *)(a1[2] + 8LL);
    for ( i = 0; i < v4; ++i )
    {
      v6 = (__int64 *)a1[2];
      v7 = *v6;
      if ( !*v6 )
        ATL::AtlThrowImpl(-2147467259);
      if ( *(_BYTE *)(v7 + 16LL * i + 8) )
      {
        v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)*a1 + 32LL))(
               *a1,
               *v2,
               *(_QWORD *)(v7 + 16LL * i),
               v6[2]);
        if ( v3 < 0 )
          break;
      }
    }
    if ( v3 < 0 && *v2 )
    {
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*a1 + 48LL))(
        *a1,
        1,
        a1 + 3,
        0,
        0,
        0);
      *v2 = 0;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800094a8  mov     [rsp+arg_10], rbx
0x1800094ad  push    rbp
0x1800094ae  push    rsi
0x1800094af  push    rdi
0x1800094b0  push    r12
0x1800094b2  push    r14
0x1800094b4  sub     rsp, 40h
0x1800094b8  mov     rbx, rcx
0x1800094bb  mov     [rsp+68h+arg_8], 0
0x1800094c4  mov     rdx, [rcx]; struct IRowset *
0x1800094c7  mov     rcx, [rcx+10h]; this
0x1800094cb  call    ?FreeRecordMemory@CDynamicAccessor@ATL@@QEAAXPEAUIRowset@@@Z; ATL::CDynamicAccessor::FreeRecordMemory(IRowset *)
0x1800094d0  nop
0x1800094d1  lea     rsi, [rbx+18h]
0x1800094d5  mov     r12d, 1
0x1800094db  cmp     qword ptr [rsi], 0
0x1800094df  jz      short loc_180009512
0x1800094e1  mov     rcx, [rbx]
0x1800094e4  mov     rax, [rcx]
0x1800094e7  mov     [rsp+68h+var_40], 0
0x1800094f0  mov     [rsp+68h+var_48], 0
0x1800094f9  xor     r9d, r9d
0x1800094fc  mov     r8, rsi
0x1800094ff  mov     edx, r12d
0x180009502  mov     rax, [rax+30h]
0x180009506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000950b  mov     qword ptr [rsi], 0
0x180009512  mov     [rsp+68h+arg_0], rsi
0x180009517  mov     rcx, [rbx]
0x18000951a  mov     rax, [rcx]
0x18000951d  lea     rdx, [rsp+68h+arg_0]
0x180009522  mov     [rsp+68h+var_40], rdx
0x180009527  lea     rdx, [rsp+68h+arg_8]
0x18000952c  mov     [rsp+68h+var_48], rdx
0x180009531  mov     r9, r12
0x180009534  xor     r8d, r8d
0x180009537  xor     edx, edx
0x180009539  mov     rax, [rax+28h]
0x18000953d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009542  mov     edi, eax
0x180009544  test    eax, eax
0x180009546  jnz     loc_1800095DC
0x18000954c  mov     rax, [rbx+10h]
0x180009550  mov     r14d, [rax+8]
0x180009554  xor     ebp, ebp
0x180009556  test    r14d, r14d
0x180009559  jz      short loc_1800095A1
0x18000955b  mov     r9, [rbx+10h]
0x18000955f  mov     rdx, [r9]
0x180009562  test    rdx, rdx
0x180009565  jz      loc_1800095F2
0x18000956b  mov     r8d, ebp
0x18000956e  add     r8, r8
0x180009571  cmp     byte ptr [rdx+r8*8+8], 0
0x180009577  jz      short loc_180009599
0x180009579  mov     rcx, [rbx]
0x18000957c  mov     rax, [rcx]
0x18000957f  mov     r9, [r9+10h]
0x180009583  mov     r8, [rdx+r8*8]
0x180009587  mov     rdx, [rsi]
0x18000958a  mov     rax, [rax+20h]
0x18000958e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009593  mov     edi, eax
0x180009595  test    eax, eax
0x180009597  js      short loc_1800095A1
0x180009599  add     ebp, r12d
0x18000959c  cmp     ebp, r14d
0x18000959f  jb      short loc_18000955B
0x1800095a1  test    edi, edi
0x1800095a3  jns     short loc_1800095DC
0x1800095a5  cmp     qword ptr [rsi], 0
0x1800095a9  jz      short loc_1800095DC
0x1800095ab  mov     rcx, [rbx]
0x1800095ae  mov     rax, [rcx]
0x1800095b1  mov     [rsp+68h+var_40], 0
0x1800095ba  mov     [rsp+68h+var_48], 0
0x1800095c3  xor     r9d, r9d
0x1800095c6  mov     r8, rsi
0x1800095c9  mov     rdx, r12
0x1800095cc  mov     rax, [rax+30h]
0x1800095d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095d5  mov     qword ptr [rsi], 0
0x1800095dc  mov     eax, edi
0x1800095de  mov     rbx, [rsp+68h+arg_10]
0x1800095e6  add     rsp, 40h
0x1800095ea  pop     r14
0x1800095ec  pop     r12
0x1800095ee  pop     rdi
0x1800095ef  pop     rsi
0x1800095f0  pop     rbp
0x1800095f1  retn
0x1800095f2  mov     ecx, 80004005h; int
0x1800095f7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
