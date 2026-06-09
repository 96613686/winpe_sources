# _lambda_08caf8ab2051d287a2afafff80b82ba2_::operator()

- ea: `0x18007db90`
- end: `0x18007dcbf`
- name: `_lambda_08caf8ab2051d287a2afafff80b82ba2_::operator()`
- size: `303`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007da9c`
- `0x18008031c`

## callees

- `0x18007db90`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18007dbc4`
- `OLEAUT32!__imp_SysFreeString` at `0x18007dc28`
- `OLEAUT32!__imp_SysFreeString` at `0x18007dc88`
- `OLEAUT32!__imp_SysFreeString` at `0x18007dbc4`
- `OLEAUT32!__imp_SysFreeString` at `0x18007dc28`
- `OLEAUT32!__imp_SysFreeString` at `0x18007dc88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007dbee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007dc54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007dbee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007dc54`

## pseudocode

```c
__int64 *__fastcall lambda_08caf8ab2051d287a2afafff80b82ba2_::operator()(__int64 a1)
{
  __int64 i; // rdi
  OLECHAR *v3; // rcx
  __int64 j; // rdi
  OLECHAR *v5; // rcx
  __int64 *result; // rax
  unsigned __int64 v7; // rdi
  __int64 k; // r8

  if ( **(_QWORD **)a1 )
  {
    for ( i = 0; (unsigned int)i < **(_DWORD **)(a1 + 8); i = (unsigned int)(i + 1) )
    {
      v3 = *(OLECHAR **)(**(_QWORD **)a1 + 8 * i);
      if ( v3 )
      {
        SysFreeString(v3);
        *(_QWORD *)(**(_QWORD **)a1 + 8 * i) = 0;
      }
    }
    CoTaskMemFree(**(LPVOID **)a1);
    **(_QWORD **)a1 = 0;
  }
  if ( **(_QWORD **)(a1 + 16) )
  {
    for ( j = 0; (unsigned int)j < **(_DWORD **)(a1 + 24); j = (unsigned int)(j + 1) )
    {
      v5 = *(OLECHAR **)(**(_QWORD **)(a1 + 16) + 8 * j);
      if ( v5 )
      {
        SysFreeString(v5);
        *(_QWORD *)(**(_QWORD **)(a1 + 16) + 8 * j) = 0;
      }
    }
    CoTaskMemFree(**(LPVOID **)(a1 + 16));
    **(_QWORD **)(a1 + 16) = 0;
  }
  result = *(__int64 **)(a1 + 32);
  v7 = 0;
  for ( k = *result; v7 < (result[1] - *result) >> 3; k = *result )
  {
    SysFreeString(*(BSTR *)(k + 8 * v7));
    result = *(__int64 **)(a1 + 32);
    ++v7;
  }
  return result;
}

```

## disassembly

```asm
0x18007db90  mov     [rsp+arg_0], rbx
0x18007db95  mov     [rsp+arg_8], rsi
0x18007db9a  push    rdi
0x18007db9b  sub     rsp, 20h
0x18007db9f  mov     rax, [rcx]
0x18007dba2  mov     rbx, rcx
0x18007dba5  cmp     qword ptr [rax], 0
0x18007dba9  jz      short loc_18007DC04
0x18007dbab  mov     rax, [rcx+8]
0x18007dbaf  xor     edi, edi
0x18007dbb1  cmp     [rax], edi
0x18007dbb3  jbe     short loc_18007DBE8
0x18007dbb5  mov     rax, [rbx]
0x18007dbb8  mov     rcx, [rax]
0x18007dbbb  mov     rcx, [rcx+rdi*8]; bstrString
0x18007dbbf  test    rcx, rcx
0x18007dbc2  jz      short loc_18007DBDE
0x18007dbc4  call    cs:__imp_SysFreeString
0x18007dbcb  nop     dword ptr [rax+rax+00h]
0x18007dbd0  mov     rax, [rbx]
0x18007dbd3  mov     rcx, [rax]
0x18007dbd6  mov     qword ptr [rcx+rdi*8], 0
0x18007dbde  mov     rax, [rbx+8]
0x18007dbe2  inc     edi
0x18007dbe4  cmp     edi, [rax]
0x18007dbe6  jb      short loc_18007DBB5
0x18007dbe8  mov     rcx, [rbx]
0x18007dbeb  mov     rcx, [rcx]; pv
0x18007dbee  call    cs:__imp_CoTaskMemFree
0x18007dbf5  nop     dword ptr [rax+rax+00h]
0x18007dbfa  mov     rax, [rbx]
0x18007dbfd  mov     qword ptr [rax], 0
0x18007dc04  mov     rax, [rbx+10h]
0x18007dc08  cmp     qword ptr [rax], 0
0x18007dc0c  jz      short loc_18007DC6B
0x18007dc0e  mov     rax, [rbx+18h]
0x18007dc12  xor     edi, edi
0x18007dc14  cmp     [rax], edi
0x18007dc16  jbe     short loc_18007DC4D
0x18007dc18  mov     rax, [rbx+10h]
0x18007dc1c  mov     rcx, [rax]
0x18007dc1f  mov     rcx, [rcx+rdi*8]; bstrString
0x18007dc23  test    rcx, rcx
0x18007dc26  jz      short loc_18007DC43
0x18007dc28  call    cs:__imp_SysFreeString
0x18007dc2f  nop     dword ptr [rax+rax+00h]
0x18007dc34  mov     rax, [rbx+10h]
0x18007dc38  mov     rcx, [rax]
0x18007dc3b  mov     qword ptr [rcx+rdi*8], 0
0x18007dc43  mov     rax, [rbx+18h]
0x18007dc47  inc     edi
0x18007dc49  cmp     edi, [rax]
0x18007dc4b  jb      short loc_18007DC18
0x18007dc4d  mov     rcx, [rbx+10h]
0x18007dc51  mov     rcx, [rcx]; pv
0x18007dc54  call    cs:__imp_CoTaskMemFree
0x18007dc5b  nop     dword ptr [rax+rax+00h]
0x18007dc60  mov     rax, [rbx+10h]
0x18007dc64  mov     qword ptr [rax], 0
0x18007dc6b  mov     rax, [rbx+20h]
0x18007dc6f  xor     edi, edi
0x18007dc71  mov     r8, [rax]
0x18007dc74  mov     rdx, [rax+8]
0x18007dc78  sub     rdx, r8
0x18007dc7b  sar     rdx, 3
0x18007dc7f  test    rdx, rdx
0x18007dc82  jz      short loc_18007DCAE
0x18007dc84  mov     rcx, [r8+rdi*8]; bstrString
0x18007dc88  call    cs:__imp_SysFreeString
0x18007dc8f  nop     dword ptr [rax+rax+00h]
0x18007dc94  mov     rax, [rbx+20h]
0x18007dc98  inc     rdi
0x18007dc9b  mov     r8, [rax]
0x18007dc9e  mov     rcx, [rax+8]
0x18007dca2  sub     rcx, r8
0x18007dca5  sar     rcx, 3
0x18007dca9  cmp     rdi, rcx
0x18007dcac  jb      short loc_18007DC84
0x18007dcae  mov     rbx, [rsp+28h+arg_0]
0x18007dcb3  mov     rsi, [rsp+28h+arg_8]
0x18007dcb8  add     rsp, 20h
0x18007dcbc  pop     rdi
0x18007dcbd  retn
```
