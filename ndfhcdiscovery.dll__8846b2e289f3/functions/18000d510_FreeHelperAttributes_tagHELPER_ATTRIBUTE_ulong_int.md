# FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)

- ea: `0x18000d510`
- end: `0x18000d5cf`
- name: `?FreeHelperAttributes@@YAXPEAUtagHELPER_ATTRIBUTE@@KH@Z`
- size: `191`
- prototype: `void __fastcall(struct tagHELPER_ATTRIBUTE *pv, unsigned int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bca0`
- `0x18000c9f8`

## callees

- `0x18000d510`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d545`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d56b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d587`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d5b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d545`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d56b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d587`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d5b5`

## pseudocode

```c
void __fastcall FreeHelperAttributes(struct tagHELPER_ATTRIBUTE *pv, unsigned int a2, int a3)
{
  unsigned int v6; // ebp
  __int64 v7; // rsi

  if ( pv && a2 )
  {
    v6 = 0;
    v7 = 0;
    do
    {
      CoTaskMemFree(pv[v7].pwszName);
      pv->pwszName = 0;
      if ( pv[v7].type == AT_STRING )
      {
        CoTaskMemFree(pv[v7].PWStr);
        pv->Int64 = 0;
      }
      else if ( pv[v7].type == AT_OCTET_STRING )
      {
        CoTaskMemFree(pv[v7].OctetString.lpValue);
        pv[v7].OctetString.lpValue = 0;
      }
      ++v6;
      pv[v7++].type = AT_INVALID;
    }
    while ( v6 < a2 );
    if ( a3 )
      CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x18000d510  test    rcx, rcx
0x18000d513  jz      locret_18000D5CD
0x18000d519  push    rbx
0x18000d51a  push    rbp
0x18000d51b  push    rsi
0x18000d51c  push    rdi
0x18000d51d  push    r14
0x18000d51f  push    r15
0x18000d521  sub     rsp, 28h
0x18000d525  mov     r15d, r8d
0x18000d528  mov     r14d, edx
0x18000d52b  mov     rbx, rcx
0x18000d52e  test    edx, edx
0x18000d530  jz      loc_18000D5C1
0x18000d536  xor     ebp, ebp
0x18000d538  xor     esi, esi
0x18000d53a  lea     rdi, [rsi+rsi*8]
0x18000d53e  add     rdi, rdi
0x18000d541  mov     rcx, [rbx+rdi*8]; pv
0x18000d545  call    cs:__imp_CoTaskMemFree
0x18000d54c  nop     dword ptr [rax+rax+00h]
0x18000d551  mov     qword ptr [rbx], 0
0x18000d558  cmp     dword ptr [rbx+rdi*8+8], 0Ah
0x18000d55d  jz      short loc_18000D582
0x18000d55f  cmp     dword ptr [rbx+rdi*8+8], 0Eh
0x18000d564  jnz     short loc_18000D59B
0x18000d566  mov     rcx, [rbx+rdi*8+18h]; pv
0x18000d56b  call    cs:__imp_CoTaskMemFree
0x18000d572  nop     dword ptr [rax+rax+00h]
0x18000d577  mov     qword ptr [rbx+rdi*8+18h], 0
0x18000d580  jmp     short loc_18000D59B
0x18000d582  mov     rcx, [rbx+rdi*8+10h]; pv
0x18000d587  call    cs:__imp_CoTaskMemFree
0x18000d58e  nop     dword ptr [rax+rax+00h]
0x18000d593  mov     qword ptr [rbx+10h], 0
0x18000d59b  inc     ebp
0x18000d59d  mov     dword ptr [rbx+rdi*8+8], 0
0x18000d5a5  inc     rsi
0x18000d5a8  cmp     ebp, r14d
0x18000d5ab  jb      short loc_18000D53A
0x18000d5ad  test    r15d, r15d
0x18000d5b0  jz      short loc_18000D5C1
0x18000d5b2  mov     rcx, rbx; pv
0x18000d5b5  call    cs:__imp_CoTaskMemFree
0x18000d5bc  nop     dword ptr [rax+rax+00h]
0x18000d5c1  add     rsp, 28h
0x18000d5c5  pop     r15
0x18000d5c7  pop     r14
0x18000d5c9  pop     rdi
0x18000d5ca  pop     rsi
0x18000d5cb  pop     rbp
0x18000d5cc  pop     rbx
0x18000d5cd  retn
```
