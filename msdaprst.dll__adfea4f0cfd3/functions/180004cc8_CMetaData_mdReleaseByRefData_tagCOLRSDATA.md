# CMetaData::mdReleaseByRefData(tagCOLRSDATA *)

- ea: `0x180004cc8`
- end: `0x180004d27`
- name: `?mdReleaseByRefData@CMetaData@@AEAAXPEAUtagCOLRSDATA@@@Z`
- size: `95`
- prototype: `void __fastcall(CMetaData *__hidden this, struct tagCOLRSDATA *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800027b0`
- `0x1800043c8`

## callees

- `0x180004cc8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180004cf9`
- `ole32!CoTaskMemFree` at `0x180004cf9`

## pseudocode

```c
void __fastcall CMetaData::mdReleaseByRefData(CMetaData *this, struct tagCOLRSDATA *a2)
{
  __int64 v2; // rdi
  __int64 v3; // rbx

  v2 = 0;
  v3 = 0;
  do
  {
    if ( *(_DWORD *)((char *)a2 + *(unsigned int *)((char *)&g_rgDesiredColumn + v3 + 36)) != 3
      && !*(const struct tagDESIREDCOLUMNS near *const *)((char *)&g_rgDesiredColumn + v3 + 48) )
    {
      CoTaskMemFree(*(LPVOID *)((char *)a2 + *(unsigned int *)((char *)&g_rgDesiredColumn + v3 + 32)));
      *(_DWORD *)((char *)a2 + *(unsigned int *)((char *)&g_rgDesiredColumn + v3 + 36)) = 3;
    }
    ++v2;
    v3 += 80;
  }
  while ( v2 != 31 );
}

```

## disassembly

```asm
0x180004cc8  push    rbx
0x180004cca  push    rbp
0x180004ccb  push    rsi
0x180004ccc  push    rdi
0x180004ccd  sub     rsp, 28h
0x180004cd1  xor     edi, edi
0x180004cd3  lea     rbp, ?g_rgDesiredColumn@@3QBUtagDESIREDCOLUMNS@@B; tagDESIREDCOLUMNS const near * const g_rgDesiredColumn
0x180004cda  xor     ebx, ebx
0x180004cdc  mov     rsi, rdx
0x180004cdf  mov     eax, [rbx+rbp+24h]
0x180004ce3  cmp     dword ptr [rax+rsi], 3
0x180004ce7  jz      short loc_180004D10
0x180004ce9  cmp     qword ptr [rbx+rbp+30h], 0
0x180004cef  jnz     short loc_180004D10
0x180004cf1  mov     ecx, [rbx+rbp+20h]
0x180004cf5  mov     rcx, [rcx+rsi]; pv
0x180004cf9  call    cs:__imp_CoTaskMemFree
0x180004d00  nop     dword ptr [rax+rax+00h]
0x180004d05  mov     eax, [rbx+rbp+24h]
0x180004d09  mov     dword ptr [rax+rsi], 3
0x180004d10  inc     rdi
0x180004d13  add     rbx, 50h ; 'P'
0x180004d17  cmp     rdi, 1Fh
0x180004d1b  jnz     short loc_180004CDF
0x180004d1d  add     rsp, 28h
0x180004d21  pop     rdi
0x180004d22  pop     rsi
0x180004d23  pop     rbp
0x180004d24  pop     rbx
0x180004d25  retn
```
