# FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)

- ea: `0x18000bda4`
- end: `0x18000be46`
- name: `?FreeHelperAttributes@@YAXPEAUtagHELPER_ATTRIBUTE@@KH@Z`
- size: `162`
- prototype: `void __fastcall(struct tagHELPER_ATTRIBUTE *pv, unsigned int, int)`
- caller_count: `9`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008ca8`
- `0x18001171c`
- `0x180011e30`
- `0x1800184d4`
- `0x180018ae4`
- `0x18001a4b4`
- `0x18001a5b4`
- `0x18001dfa4`
- `0x180028254`

## callees

- `0x18000bda4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bdd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bdf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bdd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bdf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be33`

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
0x18000bda4  test    rcx, rcx
0x18000bda7  jz      locret_18000BE45
0x18000bdad  push    rbx
0x18000bdae  push    rbp
0x18000bdaf  push    rsi
0x18000bdb0  push    rdi
0x18000bdb1  push    r14
0x18000bdb3  push    r15
0x18000bdb5  sub     rsp, 28h
0x18000bdb9  mov     r15d, r8d
0x18000bdbc  mov     r14d, edx
0x18000bdbf  mov     rbx, rcx
0x18000bdc2  test    edx, edx
0x18000bdc4  jz      short loc_18000BE39
0x18000bdc6  xor     ebp, ebp
0x18000bdc8  xor     esi, esi
0x18000bdca  lea     rdi, [rsi+rsi*8]
0x18000bdce  add     rdi, rdi
0x18000bdd1  mov     rcx, [rbx+rdi*8]; pv
0x18000bdd5  call    cs:__imp_CoTaskMemFree
0x18000bddb  mov     qword ptr [rbx], 0
0x18000bde2  cmp     dword ptr [rbx+rdi*8+8], 0Ah
0x18000bde7  jz      short loc_18000BE06
0x18000bde9  cmp     dword ptr [rbx+rdi*8+8], 0Eh
0x18000bdee  jnz     short loc_18000BE19
0x18000bdf0  mov     rcx, [rbx+rdi*8+18h]; pv
0x18000bdf5  call    cs:__imp_CoTaskMemFree
0x18000bdfb  mov     qword ptr [rbx+rdi*8+18h], 0
0x18000be04  jmp     short loc_18000BE19
0x18000be06  mov     rcx, [rbx+rdi*8+10h]; pv
0x18000be0b  call    cs:__imp_CoTaskMemFree
0x18000be11  mov     qword ptr [rbx+10h], 0
0x18000be19  inc     ebp
0x18000be1b  mov     dword ptr [rbx+rdi*8+8], 0
0x18000be23  inc     rsi
0x18000be26  cmp     ebp, r14d
0x18000be29  jb      short loc_18000BDCA
0x18000be2b  test    r15d, r15d
0x18000be2e  jz      short loc_18000BE39
0x18000be30  mov     rcx, rbx; pv
0x18000be33  call    cs:__imp_CoTaskMemFree
0x18000be39  add     rsp, 28h
0x18000be3d  pop     r15
0x18000be3f  pop     r14
0x18000be41  pop     rdi
0x18000be42  pop     rsi
0x18000be43  pop     rbp
0x18000be44  pop     rbx
0x18000be45  retn
```
