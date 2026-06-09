# RtlpImageNtHeader

- ea: `0x1400035fc`
- end: `0x14000364d`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140003654`

## callees

- `0x1400035fc`

## pseudocode

```c
__int64 __fastcall RtlpImageNtHeader(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v2; // rax

  v1 = 0;
  if ( (unsigned __int64)(a1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && *(_WORD *)a1 == 23117 )
  {
    v2 = *(int *)(a1 + 60);
    if ( (unsigned int)v2 < 0x10000000 )
    {
      v1 = a1 + v2;
      if ( *(_DWORD *)(a1 + v2) != 17744 )
        return 0;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1400035fc  sub     rsp, 18h
0x140003600  xor     edx, edx
0x140003602  lea     rax, [rcx-1]
0x140003606  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000360a  ja      short loc_140003645
0x14000360c  mov     eax, 5A4Dh
0x140003611  cmp     [rcx], ax
0x140003614  jnz     short loc_14000363D
0x140003616  movsxd  rax, dword ptr [rcx+3Ch]
0x14000361a  test    eax, eax
0x14000361c  js      short loc_14000363D
0x14000361e  cmp     eax, 10000000h
0x140003623  jnb     short loc_14000363D
0x140003625  lea     rdx, [rcx+rax]
0x140003629  mov     [rsp+18h+var_18], rdx
0x14000362d  xor     eax, eax
0x14000362f  cmp     dword ptr [rdx], 4550h
0x140003635  cmovnz  rdx, rax
0x140003639  mov     [rsp+18h+var_18], rdx
0x14000363d  jmp     short loc_140003645
0x14000363f  xor     edx, edx
0x140003641  mov     [rsp+18h+var_18], rdx
0x140003645  mov     rax, rdx
0x140003648  add     rsp, 18h
0x14000364c  retn
```
