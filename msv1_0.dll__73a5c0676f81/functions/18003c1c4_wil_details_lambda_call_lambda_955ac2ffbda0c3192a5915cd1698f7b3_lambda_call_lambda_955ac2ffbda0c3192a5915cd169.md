# wil::details::lambda_call__lambda_955ac2ffbda0c3192a5915cd1698f7b3___::_lambda_call__lambda_955ac2ffbda0c3192a5915cd1698f7b3___

- ea: `0x18003c1c4`
- end: `0x18003c210`
- name: `wil::details::lambda_call__lambda_955ac2ffbda0c3192a5915cd1698f7b3___::_lambda_call__lambda_955ac2ffbda0c3192a5915cd1698f7b3___`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18006c102`

## callees

- `0x18003c1c4`

## import_xrefs

- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18003c1f3`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18003c1f3`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18003c1e2`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18003c1e2`
- `SAMSRV!SamrCloseHandle` at `0x18003c203`
- `SAMSRV!SamrCloseHandle` at `0x18003c203`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall wil::details::lambda_call__lambda_955ac2ffbda0c3192a5915cd1698f7b3___::_lambda_call__lambda_955ac2ffbda0c3192a5915cd1698f7b3___(
        __int64 **a1,
        __int64 a2)
{
  __int64 *result; // rax
  __int64 v4; // rcx
  __int64 *v5; // rcx
  __int64 *v6; // rcx

  if ( *((_BYTE *)a1 + 24) )
  {
    *((_BYTE *)a1 + 24) = 0;
    result = *a1;
    v4 = **a1;
    if ( v4 )
      result = (__int64 *)SamIFree_UserInternal6Information(v4);
    v5 = a1[1];
    if ( v5[1] )
      result = (__int64 *)SamIFreeSidAndAttributesList(v5, a2);
    v6 = a1[2];
    if ( *v6 )
      return (__int64 *)SamrCloseHandle(v6);
  }
  return result;
}

```

## disassembly

```asm
0x18003c1c4  push    rbx
0x18003c1c6  sub     rsp, 20h
0x18003c1ca  mov     rbx, rcx
0x18003c1cd  cmp     byte ptr [rcx+18h], 0
0x18003c1d1  jz      short loc_18003C20A
0x18003c1d3  mov     byte ptr [rcx+18h], 0
0x18003c1d7  mov     rax, [rcx]
0x18003c1da  mov     rcx, [rax]
0x18003c1dd  test    rcx, rcx
0x18003c1e0  jz      short loc_18003C1E8
0x18003c1e2  call    cs:__imp_SamIFree_UserInternal6Information
0x18003c1e8  mov     rcx, [rbx+8]
0x18003c1ec  cmp     qword ptr [rcx+8], 0
0x18003c1f1  jz      short loc_18003C1F9
0x18003c1f3  call    cs:__imp_SamIFreeSidAndAttributesList
0x18003c1f9  mov     rcx, [rbx+10h]
0x18003c1fd  cmp     qword ptr [rcx], 0
0x18003c201  jz      short loc_18003C20A
0x18003c203  call    cs:__imp_SamrCloseHandle
0x18003c209  nop
0x18003c20a  add     rsp, 20h
0x18003c20e  pop     rbx
0x18003c20f  retn
```
