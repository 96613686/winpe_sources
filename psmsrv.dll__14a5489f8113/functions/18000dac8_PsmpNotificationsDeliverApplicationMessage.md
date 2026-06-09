# PsmpNotificationsDeliverApplicationMessage

- ea: `0x18000dac8`
- end: `0x18000db80`
- name: `PsmpNotificationsDeliverApplicationMessage`
- size: `184`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180009b40`
- `0x18000b4d8`

## callees

- `0x18000dac8`
- `0x18000dbd0`
- `0x18001c10c`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18000db14`
- `ntdll!RtlCopySid` at `0x18000db14`

## pseudocode

```c
__int64 __fastcall PsmpNotificationsDeliverApplicationMessage(__int64 a1, int a2)
{
  __int64 v4; // r8
  _WORD *v5; // rbx
  __int64 v6; // rcx
  char *v7; // rax
  __int64 v8; // rdx
  char *v9; // rcx
  _BYTE v11[24]; // [rsp+20h] [rbp-268h] BYREF
  int v12; // [rsp+38h] [rbp-250h]
  _BYTE DestinationSid[68]; // [rsp+3Ch] [rbp-24Ch] BYREF
  int v14; // [rsp+80h] [rbp-208h]
  char v15; // [rsp+84h] [rbp-204h] BYREF

  memset_0(v11, 0, 0x260u);
  v4 = *(_QWORD *)(a1 + 312);
  v12 = a2;
  v5 = *(_WORD **)(a1 + 8);
  v14 = *(_DWORD *)(v4 + 4);
  RtlCopySid(0x44u, DestinationSid, *(PSID *)(v4 + 40));
  v6 = 2147483646;
  v7 = &v15;
  v8 = 232;
  do
  {
    if ( !v6 )
      break;
    if ( !*v5 )
      break;
    *(_WORD *)v7 = *v5++;
    v7 += 2;
    --v6;
    --v8;
  }
  while ( v8 );
  v9 = v7 - 2;
  if ( v8 )
    v9 = v7;
  *(_WORD *)v9 = 0;
  return PsmpNotificationsDeliverMessage(a1, v11);
}

```

## disassembly

```asm
0x18000dac8  mov     [rsp+arg_0], rbx
0x18000dacd  push    rdi
0x18000dace  sub     rsp, 280h
0x18000dad5  mov     ebx, edx
0x18000dad7  mov     rdi, rcx
0x18000dada  xor     edx, edx; Val
0x18000dadc  lea     rcx, [rsp+288h+var_268]; void *
0x18000dae1  mov     r8d, 260h; Size
0x18000dae7  call    memset_0
0x18000daec  mov     r8, [rdi+138h]
0x18000daf3  lea     rdx, [rsp+288h+DestinationSid]; DestinationSid
0x18000daf8  mov     [rsp+288h+var_250], ebx
0x18000dafc  mov     ecx, 44h ; 'D'; DestinationSidLength
0x18000db01  mov     rbx, [rdi+8]
0x18000db05  mov     eax, [r8+4]
0x18000db09  mov     [rsp+288h+var_208], eax
0x18000db10  mov     r8, [r8+28h]; SourceSid
0x18000db14  call    cs:__imp_RtlCopySid
0x18000db1a  mov     ecx, 7FFFFFFEh
0x18000db1f  lea     rax, [rsp+288h+var_204]
0x18000db27  mov     edx, 0E8h
0x18000db2c  xor     r9d, r9d
0x18000db2f  test    rcx, rcx
0x18000db32  jz      short loc_18000DB53
0x18000db34  movzx   r8d, word ptr [rbx]
0x18000db38  test    r8w, r8w
0x18000db3c  jz      short loc_18000DB53
0x18000db3e  mov     [rax], r8w
0x18000db42  add     rbx, 2
0x18000db46  add     rax, 2
0x18000db4a  dec     rcx
0x18000db4d  sub     rdx, 1
0x18000db51  jnz     short loc_18000DB2F
0x18000db53  test    rdx, rdx
0x18000db56  lea     rcx, [rax-2]
0x18000db5a  lea     rdx, [rsp+288h+var_268]
0x18000db5f  cmovnz  rcx, rax
0x18000db63  mov     [rcx], r9w
0x18000db67  mov     rcx, rdi
0x18000db6a  call    PsmpNotificationsDeliverMessage
0x18000db6f  mov     rbx, [rsp+288h+arg_0]
0x18000db77  add     rsp, 280h
0x18000db7e  pop     rdi
0x18000db7f  retn
```
