# ScopeWarden__lambda_49a6ae24957a5f2373ed175db8453749___::_ScopeWarden__lambda_49a6ae24957a5f2373ed175db8453749___

- ea: `0x1802cdb2c`
- end: `0x1802cdb99`
- name: `ScopeWarden__lambda_49a6ae24957a5f2373ed175db8453749___::_ScopeWarden__lambda_49a6ae24957a5f2373ed175db8453749___`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801657e8`
- `0x18032d09a`

## callees

- `0x1802cdb2c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cdb4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cdb54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cdb66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cdb78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cdb8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cdb4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cdb54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cdb66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cdb78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cdb8a`

## pseudocode

```c
void __fastcall ScopeWarden__lambda_49a6ae24957a5f2373ed175db8453749___::_ScopeWarden__lambda_49a6ae24957a5f2373ed175db8453749___(
        __int64 *a1)
{
  __int64 v1; // rbx
  LPVOID *v2; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    if ( !**(_DWORD **)v1 )
    {
      v2 = *(LPVOID **)(v1 + 8);
      CoTaskMemFree(v2[7]);
      CoTaskMemFree(v2[2]);
      v2[2] = 0;
      CoTaskMemFree(v2[4]);
      v2[4] = 0;
      CoTaskMemFree(v2[5]);
      v2[5] = 0;
      CoTaskMemFree(v2[13]);
    }
  }
}

```

## disassembly

```asm
0x1802cdb2c  push    rbx
0x1802cdb2e  sub     rsp, 20h
0x1802cdb32  mov     rbx, [rcx]
0x1802cdb35  test    rbx, rbx
0x1802cdb38  jz      short loc_1802CDB93
0x1802cdb3a  mov     rax, [rbx]
0x1802cdb3d  cmp     dword ptr [rax], 0
0x1802cdb40  jnz     short loc_1802CDB91
0x1802cdb42  mov     rbx, [rbx+8]
0x1802cdb46  mov     rcx, [rbx+38h]; pv
0x1802cdb4a  call    cs:__imp_CoTaskMemFree
0x1802cdb50  mov     rcx, [rbx+10h]; pv
0x1802cdb54  call    cs:__imp_CoTaskMemFree
0x1802cdb5a  mov     qword ptr [rbx+10h], 0
0x1802cdb62  mov     rcx, [rbx+20h]; pv
0x1802cdb66  call    cs:__imp_CoTaskMemFree
0x1802cdb6c  mov     qword ptr [rbx+20h], 0
0x1802cdb74  mov     rcx, [rbx+28h]; pv
0x1802cdb78  call    cs:__imp_CoTaskMemFree
0x1802cdb7e  mov     qword ptr [rbx+28h], 0
0x1802cdb86  mov     rcx, [rbx+68h]; pv
0x1802cdb8a  call    cs:__imp_CoTaskMemFree
0x1802cdb90  nop
0x1802cdb91  jmp     short $+2
0x1802cdb93  add     rsp, 20h
0x1802cdb97  pop     rbx
0x1802cdb98  retn
```
