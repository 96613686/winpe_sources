# FreeHypothesesEmbeddedMemory(ulong,tagHYPOTHESIS *)

- ea: `0x18002b550`
- end: `0x18002b616`
- name: `?FreeHypothesesEmbeddedMemory@@YAXKPEAUtagHYPOTHESIS@@@Z`
- size: `198`
- prototype: `void __fastcall(unsigned int, struct tagHYPOTHESIS *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000be4c`
- `0x18000be90`

## callees

- `0x18002b550`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b577`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b588`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b5b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b5d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b5ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b577`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b588`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b5b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b5d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b5ed`

## pseudocode

```c
void __fastcall FreeHypothesesEmbeddedMemory(unsigned int a1, struct tagHYPOTHESIS *a2)
{
  unsigned int v2; // esi
  struct tagHYPOTHESIS *i; // rbx
  LPWSTR pwszDescription; // rcx
  PHELPER_ATTRIBUTE rgAttributes; // rdi
  ULONG celt; // r15d
  ULONG v8; // r14d
  void *lpValue; // rcx

  if ( a2 )
  {
    v2 = 0;
    for ( i = a2; v2 < a1; ++v2 )
    {
      CoTaskMemFree(i->pwszClassName);
      pwszDescription = i->pwszDescription;
      i->pwszClassName = 0;
      CoTaskMemFree(pwszDescription);
      rgAttributes = i->rgAttributes;
      i->pwszDescription = 0;
      if ( rgAttributes )
      {
        celt = i->celt;
        v8 = 0;
        if ( celt )
        {
          while ( 1 )
          {
            if ( rgAttributes->pwszName )
              CoTaskMemFree(rgAttributes->pwszName);
            if ( rgAttributes->type == AT_STRING )
              break;
            if ( rgAttributes->type == AT_OCTET_STRING )
            {
              lpValue = rgAttributes->OctetString.lpValue;
              goto LABEL_11;
            }
LABEL_13:
            ++v8;
            ++rgAttributes;
            if ( v8 >= celt )
              goto LABEL_14;
          }
          lpValue = rgAttributes->PWStr;
LABEL_11:
          if ( lpValue )
            CoTaskMemFree(lpValue);
          goto LABEL_13;
        }
LABEL_14:
        CoTaskMemFree(i->rgAttributes);
        i->rgAttributes = 0;
      }
      ++i;
    }
  }
}

```

## disassembly

```asm
0x18002b550  test    rdx, rdx
0x18002b553  jz      locret_18002B615
0x18002b559  push    rbx
0x18002b55a  push    rbp
0x18002b55b  push    rsi
0x18002b55c  push    rdi
0x18002b55d  push    r14
0x18002b55f  push    r15
0x18002b561  sub     rsp, 28h
0x18002b565  xor     esi, esi
0x18002b567  mov     rbx, rdx
0x18002b56a  mov     ebp, ecx
0x18002b56c  test    ecx, ecx
0x18002b56e  jz      loc_18002B609
0x18002b574  mov     rcx, [rbx]; pv
0x18002b577  call    cs:__imp_CoTaskMemFree
0x18002b57d  mov     rcx, [rbx+8]; pv
0x18002b581  mov     qword ptr [rbx], 0
0x18002b588  call    cs:__imp_CoTaskMemFree
0x18002b58e  mov     rdi, [rbx+18h]
0x18002b592  mov     qword ptr [rbx+8], 0
0x18002b59a  test    rdi, rdi
0x18002b59d  jz      short loc_18002B5FB
0x18002b59f  mov     r15d, [rbx+10h]
0x18002b5a3  xor     r14d, r14d
0x18002b5a6  test    r15d, r15d
0x18002b5a9  jz      short loc_18002B5E9
0x18002b5ab  mov     rcx, [rdi]; pv
0x18002b5ae  test    rcx, rcx
0x18002b5b1  jz      short loc_18002B5B9
0x18002b5b3  call    cs:__imp_CoTaskMemFree
0x18002b5b9  cmp     dword ptr [rdi+8], 0Ah
0x18002b5bd  jz      short loc_18002B5CB
0x18002b5bf  cmp     dword ptr [rdi+8], 0Eh
0x18002b5c3  jnz     short loc_18002B5DA
0x18002b5c5  mov     rcx, [rdi+18h]
0x18002b5c9  jmp     short loc_18002B5CF
0x18002b5cb  mov     rcx, [rdi+10h]; pv
0x18002b5cf  test    rcx, rcx
0x18002b5d2  jz      short loc_18002B5DA
0x18002b5d4  call    cs:__imp_CoTaskMemFree
0x18002b5da  inc     r14d
0x18002b5dd  add     rdi, 90h
0x18002b5e4  cmp     r14d, r15d
0x18002b5e7  jb      short loc_18002B5AB
0x18002b5e9  mov     rcx, [rbx+18h]; pv
0x18002b5ed  call    cs:__imp_CoTaskMemFree
0x18002b5f3  mov     qword ptr [rbx+18h], 0
0x18002b5fb  add     rbx, 20h ; ' '
0x18002b5ff  inc     esi
0x18002b601  cmp     esi, ebp
0x18002b603  jb      loc_18002B574
0x18002b609  add     rsp, 28h
0x18002b60d  pop     r15
0x18002b60f  pop     r14
0x18002b611  pop     rdi
0x18002b612  pop     rsi
0x18002b613  pop     rbp
0x18002b614  pop     rbx
0x18002b615  retn
```
