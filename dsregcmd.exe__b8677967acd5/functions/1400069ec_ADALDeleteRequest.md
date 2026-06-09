# ADALDeleteRequest

- ea: `0x1400069ec`
- end: `0x140006aca`
- name: `ADALDeleteRequest`
- size: `222`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140003458`

## callees

- `0x1400028ac`
- `0x1400069ec`
- `0x14000a17c`
- `0x14000e020`
- `0x14002c3e8`
- `0x140030010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400069fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400069fb`

## pseudocode

```c
__int64 __fastcall ADALDeleteRequest(_BYTE *Block)
{
  volatile signed __int32 *v2; // rdi
  const struct Exception **v4; // rdx
  const struct std::exception **v5; // rdx
  _BYTE v6[32]; // [rsp+0h] [rbp-58h] BYREF
  const Exception *v7; // [rsp+20h] [rbp-38h] BYREF
  const std::exception *v8; // [rsp+28h] [rbp-30h] BYREF
  _BYTE pExceptionObject[16]; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v10[24]; // [rsp+40h] [rbp-18h] BYREF

  SetLastError(0);
  if ( !Block || !(unsigned __int8)APIHandle<APIReq,HADALREQUEST__ *,-1440046422>::Validate(Block) )
  {
    InvalidHandleException::InvalidHandleException((InvalidHandleException *)v10, 0xCAA1000E);
    throw (InvalidHandleException *)v10;
  }
  if ( Block[24] )
  {
    InvalidHandleException::InvalidHandleException((InvalidHandleException *)pExceptionObject, 0xCAA1000F);
    try
    {
      throw (InvalidHandleException *)pExceptionObject;
    }
    catch ( const Exception *v7 )
    {
      v4 = (const struct Exception **)v6;
      HandleException(0, v4[4]);
      return 0;
    }
    catch ( const std::exception *v8 )
    {
      v5 = (const struct std::exception **)v6;
      HandleException(0, v5[5]);
      return 0;
    }
  }
  *(_DWORD *)Block = 0;
  v2 = (volatile signed __int32 *)*((_QWORD *)Block + 2);
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  operator delete(Block);
  return 1;
}

```

## disassembly

```asm
0x1400069ec  mov     [rsp+arg_0], rbx
0x1400069f1  push    rdi
0x1400069f2  sub     rsp, 50h
0x1400069f6  mov     rbx, rcx
0x1400069f9  xor     ecx, ecx; dwErrCode
0x1400069fb  call    cs:__imp_SetLastError
0x140006a01  nop
0x140006a02  test    rbx, rbx
0x140006a05  jz      loc_140006AA8
0x140006a0b  mov     rcx, rbx
0x140006a0e  call    ?Validate@?$APIHandle@VAPIReq@@PEAUHADALREQUEST__@@$0?FFNFFNFG@@@CA_NPEBV1@@Z; APIHandle<APIReq,HADALREQUEST__ *,-1440046422>::Validate(APIHandle<APIReq,HADALREQUEST__ *,-1440046422> const *)
0x140006a13  test    al, al
0x140006a15  jz      loc_140006AA8
0x140006a1b  cmp     byte ptr [rbx+18h], 0
0x140006a1f  jnz     short loc_140006A88
0x140006a21  mov     dword ptr [rbx], 0
0x140006a27  mov     rdi, [rbx+10h]
0x140006a2b  test    rdi, rdi
0x140006a2e  jz      short loc_140006A67
0x140006a30  or      eax, 0FFFFFFFFh
0x140006a33  lock xadd [rdi+8], eax
0x140006a38  cmp     eax, 1
0x140006a3b  jnz     short loc_140006A67
0x140006a3d  mov     rax, [rdi]
0x140006a40  mov     rcx, rdi
0x140006a43  mov     rax, [rax]
0x140006a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006a4b  or      eax, 0FFFFFFFFh
0x140006a4e  lock xadd [rdi+0Ch], eax
0x140006a53  cmp     eax, 1
0x140006a56  jnz     short loc_140006A67
0x140006a58  mov     rax, [rdi]
0x140006a5b  mov     rcx, rdi
0x140006a5e  mov     rax, [rax+8]
0x140006a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006a67  mov     edx, 20h ; ' '
0x140006a6c  mov     rcx, rbx; Block
0x140006a6f  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x140006a74  mov     eax, 1
0x140006a79  jmp     short loc_140006A7D
0x140006a7b  xor     eax, eax
0x140006a7d  mov     rbx, [rsp+58h+arg_0]
0x140006a82  add     rsp, 50h
0x140006a86  pop     rdi
0x140006a87  retn
0x140006a88  mov     edx, 0CAA1000Fh; unsigned int
0x140006a8d  lea     rcx, [rsp+58h+pExceptionObject]; this
0x140006a92  call    ??0InvalidHandleException@@QEAA@K@Z; InvalidHandleException::InvalidHandleException(ulong)
0x140006a97  lea     rdx, _TI4?AVInvalidHandleException@@; pThrowInfo
0x140006a9e  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x140006aa3  call    _CxxThrowException_0
0x140006aa8  mov     edx, 0CAA1000Eh; unsigned int
0x140006aad  lea     rcx, [rsp+58h+var_18]; this
0x140006ab2  call    ??0InvalidHandleException@@QEAA@K@Z; InvalidHandleException::InvalidHandleException(ulong)
0x140006ab7  lea     rdx, _TI4?AVInvalidHandleException@@; pThrowInfo
0x140006abe  lea     rcx, [rsp+58h+var_18]; pExceptionObject
0x140006ac3  call    _CxxThrowException_0
```
