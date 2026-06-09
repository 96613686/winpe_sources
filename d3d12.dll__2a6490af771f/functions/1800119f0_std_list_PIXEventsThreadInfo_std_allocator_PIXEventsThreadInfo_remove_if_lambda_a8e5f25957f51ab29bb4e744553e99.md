# std::list_PIXEventsThreadInfo_std::allocator_PIXEventsThreadInfo___::remove_if__lambda_a8e5f25957f51ab29bb4e744553e99f1___

- ea: `0x1800119f0`
- end: `0x180011a8c`
- name: `std::list_PIXEventsThreadInfo_std::allocator_PIXEventsThreadInfo___::remove_if__lambda_a8e5f25957f51ab29bb4e744553e99f1___`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800050c4`

## callees

- `0x180008240`
- `0x1800119f0`

## pseudocode

```c
__int64 std::list_PIXEventsThreadInfo_std::allocator_PIXEventsThreadInfo___::remove_if__lambda_a8e5f25957f51ab29bb4e744553e99f1___()
{
  __int64 *v0; // r8
  __int64 *v1; // r9
  __int64 *v2; // rdx
  __int64 *v3; // r11
  __int64 *v4; // r10
  _QWORD *v5; // rcx
  _QWORD *v6; // rax
  __int64 *v8; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+28h] [rbp-20h] BYREF
  __int64 *v10; // [rsp+30h] [rbp-18h]

  v0 = (__int64 *)qword_18001E8A0;
  v1 = &qword_18001E8A0;
  v8 = &qword_18001E8A0;
  v9 = 0;
  v10 = &v9;
  v2 = *(__int64 **)qword_18001E8A0;
  if ( (__int64 *)*v0 != v0 )
  {
    v3 = *(__int64 **)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 24LL);
    do
    {
      v4 = (__int64 *)*v2;
      if ( v2 + 2 == v3 )
      {
        --v1[1];
        v5 = (_QWORD *)*v2;
        *v2 = 0;
        v6 = (_QWORD *)v2[1];
        *v6 = v5;
        v5[1] = v6;
        *v10 = (__int64)v2;
        v1 = v8;
        v10 = v2;
      }
      v2 = v4;
    }
    while ( v4 != v0 );
  }
  return std::list<PIXEventsThreadInfo>::_List_node_remove_op::~_List_node_remove_op(&v8);
}

```

## disassembly

```asm
0x1800119f0  mov     r11, rsp
0x1800119f3  sub     rsp, 48h
0x1800119f7  mov     r8, cs:qword_18001E8A0
0x1800119fe  lea     r9, qword_18001E8A0
0x180011a05  lea     rax, [r11-20h]
0x180011a09  mov     [r11-28h], r9
0x180011a0d  mov     qword ptr [r11-20h], 0
0x180011a15  mov     [r11-18h], rax
0x180011a19  mov     rdx, [r8]
0x180011a1c  cmp     rdx, r8
0x180011a1f  jz      short loc_180011A7D
0x180011a21  mov     ecx, cs:_tls_index
0x180011a27  mov     rax, gs:58h
0x180011a30  mov     r11d, 18h
0x180011a36  mov     rax, [rax+rcx*8]
0x180011a3a  mov     r11, [r11+rax]
0x180011a3e  mov     r10, [rdx]
0x180011a41  lea     rax, [rdx+10h]
0x180011a45  cmp     rax, r11
0x180011a48  jnz     short loc_180011A75
0x180011a4a  dec     qword ptr [r9+8]
0x180011a4e  mov     rcx, [rdx]
0x180011a51  mov     qword ptr [rdx], 0
0x180011a58  mov     rax, [rdx+8]
0x180011a5c  mov     [rax], rcx
0x180011a5f  mov     [rcx+8], rax
0x180011a63  mov     rax, [rsp+48h+var_18]
0x180011a68  mov     [rax], rdx
0x180011a6b  mov     r9, [rsp+48h+var_28]
0x180011a70  mov     [rsp+48h+var_18], rdx
0x180011a75  mov     rdx, r10
0x180011a78  cmp     r10, r8
0x180011a7b  jnz     short loc_180011A3E
0x180011a7d  lea     rcx, [rsp+48h+var_28]
0x180011a82  call    ??1_List_node_remove_op@?$list@UPIXEventsThreadInfo@@V?$allocator@UPIXEventsThreadInfo@@@std@@@std@@QEAA@XZ; std::list<PIXEventsThreadInfo>::_List_node_remove_op::~_List_node_remove_op(void)
0x180011a87  add     rsp, 48h
0x180011a8b  retn
```
