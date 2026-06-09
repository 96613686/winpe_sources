# FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)

- ea: `0x180008a60`
- end: `0x180008b02`
- name: `?FreeHelperAttributes@@YAXPEAUtagHELPER_ATTRIBUTE@@KH@Z`
- size: `162`
- prototype: `void __fastcall(struct tagHELPER_ATTRIBUTE *pv, unsigned int, int)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180008120`
- `0x180008580`
- `0x1800087f8`
- `0x18000a9e0`
- `0x18000e0c4`
- `0x180011c20`

## callees

- `0x180008a60`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180008a91`
- `ole32!CoTaskMemFree` at `0x180008ab1`
- `ole32!CoTaskMemFree` at `0x180008ac7`
- `ole32!CoTaskMemFree` at `0x180008aef`
- `ole32!CoTaskMemFree` at `0x180008a91`
- `ole32!CoTaskMemFree` at `0x180008ab1`
- `ole32!CoTaskMemFree` at `0x180008ac7`
- `ole32!CoTaskMemFree` at `0x180008aef`

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
0x180008a60  test    rcx, rcx
0x180008a63  jz      locret_180008B01
0x180008a69  push    rbx
0x180008a6a  push    rbp
0x180008a6b  push    rsi
0x180008a6c  push    rdi
0x180008a6d  push    r14
0x180008a6f  push    r15
0x180008a71  sub     rsp, 28h
0x180008a75  mov     r15d, r8d
0x180008a78  mov     r14d, edx
0x180008a7b  mov     rbx, rcx
0x180008a7e  test    edx, edx
0x180008a80  jz      short loc_180008AF5
0x180008a82  xor     ebp, ebp
0x180008a84  xor     esi, esi
0x180008a86  lea     rdi, [rsi+rsi*8]
0x180008a8a  add     rdi, rdi
0x180008a8d  mov     rcx, [rbx+rdi*8]; pv
0x180008a91  call    cs:__imp_CoTaskMemFree
0x180008a97  mov     qword ptr [rbx], 0
0x180008a9e  cmp     dword ptr [rbx+rdi*8+8], 0Ah
0x180008aa3  jz      short loc_180008AC2
0x180008aa5  cmp     dword ptr [rbx+rdi*8+8], 0Eh
0x180008aaa  jnz     short loc_180008AD5
0x180008aac  mov     rcx, [rbx+rdi*8+18h]; pv
0x180008ab1  call    cs:__imp_CoTaskMemFree
0x180008ab7  mov     qword ptr [rbx+rdi*8+18h], 0
0x180008ac0  jmp     short loc_180008AD5
0x180008ac2  mov     rcx, [rbx+rdi*8+10h]; pv
0x180008ac7  call    cs:__imp_CoTaskMemFree
0x180008acd  mov     qword ptr [rbx+10h], 0
0x180008ad5  inc     ebp
0x180008ad7  mov     dword ptr [rbx+rdi*8+8], 0
0x180008adf  inc     rsi
0x180008ae2  cmp     ebp, r14d
0x180008ae5  jb      short loc_180008A86
0x180008ae7  test    r15d, r15d
0x180008aea  jz      short loc_180008AF5
0x180008aec  mov     rcx, rbx; pv
0x180008aef  call    cs:__imp_CoTaskMemFree
0x180008af5  add     rsp, 28h
0x180008af9  pop     r15
0x180008afb  pop     r14
0x180008afd  pop     rdi
0x180008afe  pop     rsi
0x180008aff  pop     rbp
0x180008b00  pop     rbx
0x180008b01  retn
```
