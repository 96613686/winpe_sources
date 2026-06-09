# AddTimeOrderedJob

- ea: `0x180002630`
- end: `0x1800026c6`
- name: `AddTimeOrderedJob`
- size: `150`
- prototype: `void __fastcall(FILETIME **, FILETIME)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002478`
- `0x1800026cc`

## callees

- `0x180002630`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000265a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000265a`

## pseudocode

```c
void __fastcall AddTimeOrderedJob(FILETIME **a1, FILETIME a2)
{
  FILETIME *v2; // rbx
  FILETIME *v5; // rax

  v2 = *a1;
  if ( *a1 )
  {
    while ( CompareFileTime((const FILETIME *)(*(_QWORD *)&a2 + 16LL), v2 + 2) >= 0 )
    {
      if ( !*(_QWORD *)v2 )
      {
        *(_QWORD *)(*(_QWORD *)&a2 + 8LL) = v2;
        *v2 = a2;
        return;
      }
      v2 = (FILETIME *)*v2;
    }
    **(_QWORD **)&a2 = v2;
    *(FILETIME *)(*(_QWORD *)&a2 + 8LL) = v2[1];
    v5 = (FILETIME *)v2[1];
    if ( v5 )
      *v5 = a2;
    else
      *a1 = (FILETIME *)a2;
    v2[1] = a2;
  }
  else
  {
    *a1 = (FILETIME *)a2;
  }
}

```

## disassembly

```asm
0x180002630  mov     [rsp+arg_8], rbx
0x180002635  mov     [rsp+arg_10], rsi
0x18000263a  push    rdi
0x18000263b  sub     rsp, 20h
0x18000263f  mov     rbx, [rcx]
0x180002642  mov     rdi, rdx
0x180002645  mov     rsi, rcx
0x180002648  test    rbx, rbx
0x18000264b  jz      short loc_180002688
0x18000264d  mov     [rsp+28h+arg_0], rbp
0x180002652  lea     rdx, [rbx+10h]; lpFileTime2
0x180002656  lea     rcx, [rdi+10h]; lpFileTime1
0x18000265a  call    cs:__imp_CompareFileTime
0x180002660  test    eax, eax
0x180002662  js      short loc_1800026A0
0x180002664  mov     rax, [rbx]
0x180002667  test    rax, rax
0x18000266a  jnz     short loc_18000269B
0x18000266c  mov     [rdi+8], rbx
0x180002670  mov     [rbx], rdi
0x180002673  mov     rbp, [rsp+28h+arg_0]
0x180002678  mov     rbx, [rsp+28h+arg_8]
0x18000267d  mov     rsi, [rsp+28h+arg_10]
0x180002682  add     rsp, 20h
0x180002686  pop     rdi
0x180002687  retn
0x180002688  mov     rbx, [rsp+28h+arg_8]
0x18000268d  mov     rsi, [rsp+28h+arg_10]
0x180002692  mov     [rcx], rdi
0x180002695  add     rsp, 20h
0x180002699  pop     rdi
0x18000269a  retn
0x18000269b  mov     rbx, rax
0x18000269e  jmp     short loc_180002652
0x1800026a0  mov     [rdi], rbx
0x1800026a3  mov     rax, [rbx+8]
0x1800026a7  mov     [rdi+8], rax
0x1800026ab  mov     rax, [rbx+8]
0x1800026af  test    rax, rax
0x1800026b2  jnz     short loc_1800026BD
0x1800026b4  mov     [rsi], rdi
0x1800026b7  mov     [rbx+8], rdi
0x1800026bb  jmp     short loc_180002673
0x1800026bd  mov     [rax], rdi
0x1800026c0  mov     [rbx+8], rdi
0x1800026c4  jmp     short loc_180002673
```
