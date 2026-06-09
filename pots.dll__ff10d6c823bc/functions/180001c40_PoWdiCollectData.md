# PoWdiCollectData

- ea: `0x180001c40`
- end: `0x180001d07`
- name: `PoWdiCollectData`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800032c0`

## callees

- `0x180001c40`
- `0x180004520`

## pseudocode

```c
__int64 __fastcall PoWdiCollectData(WCHAR *a1, __int64 a2, _DWORD *a3)
{
  _DWORD *v3; // rsi
  unsigned int v5; // edi
  _QWORD v8[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 (__fastcall *v9)(); // [rsp+30h] [rbp-18h]
  _DWORD *v10; // [rsp+38h] [rbp-10h]

  v3 = a3 + 35;
  v8[1] = *(_QWORD *)(a2 + 16);
  v5 = 0;
  v10 = a3 + 35;
  a3[35] = 0;
  v8[0] = 0;
  v9 = 0;
  if ( PoWdiProcessEvents(a1, (void (__stdcall *)(PEVENT_TRACE))PoWdiFindStartTime, v8) )
  {
    *v3 = 1;
    if ( v8[0] )
    {
      a3[34] |= 8u;
      a3[1] |= 0x10000000u;
      v9 = PoWdiPass0Callback;
      v10 = a3;
      if ( PoWdiProcessEvents(a1, (void (__stdcall *)(PEVENT_TRACE))PoWdiCallback, v8) )
      {
        v10 = a3;
        v9 = PoWdiPass1Callback;
        return PoWdiProcessEvents(a1, (void (__stdcall *)(PEVENT_TRACE))PoWdiCallback, v8);
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180001c40  push    rbp
0x180001c42  push    rbx
0x180001c43  push    rsi
0x180001c44  push    rdi
0x180001c45  push    r12
0x180001c47  push    r14
0x180001c49  mov     rbp, rsp
0x180001c4c  sub     rsp, 48h
0x180001c50  mov     rax, [rdx+10h]
0x180001c54  lea     rsi, [r8+8Ch]
0x180001c5b  mov     rbx, r8
0x180001c5e  mov     [rbp+var_20], rax
0x180001c62  xor     edi, edi
0x180001c64  mov     [rbp+var_10], rsi
0x180001c68  lea     r8, [rbp+var_28]
0x180001c6c  mov     [rsi], edi
0x180001c6e  lea     rdx, PoWdiFindStartTime
0x180001c75  mov     [rbp+var_28], 0
0x180001c7d  mov     r14, rcx
0x180001c80  mov     [rbp+var_18], 0
0x180001c88  call    PoWdiProcessEvents
0x180001c8d  test    eax, eax
0x180001c8f  jz      short loc_180001CF8
0x180001c91  lea     r12d, [rdi+1]
0x180001c95  mov     [rsi], r12d
0x180001c98  cmp     [rbp+var_28], rdi
0x180001c9c  jz      short loc_180001CF8
0x180001c9e  or      dword ptr [rbx+88h], 8
0x180001ca5  lea     rax, PoWdiPass0Callback
0x180001cac  bts     dword ptr [rbx+4], 1Ch
0x180001cb1  lea     r8, [rbp+var_28]
0x180001cb5  lea     rdx, PoWdiCallback
0x180001cbc  mov     [rbp+var_18], rax
0x180001cc0  mov     rcx, r14
0x180001cc3  mov     [rbp+var_10], rbx
0x180001cc7  call    PoWdiProcessEvents
0x180001ccc  test    eax, eax
0x180001cce  jz      short loc_180001CF8
0x180001cd0  lea     rax, PoWdiPass1Callback
0x180001cd7  mov     [rbp+var_10], rbx
0x180001cdb  lea     r8, [rbp+var_28]
0x180001cdf  mov     [rbp+var_18], rax
0x180001ce3  lea     rdx, PoWdiCallback
0x180001cea  mov     rcx, r14
0x180001ced  call    PoWdiProcessEvents
0x180001cf2  test    eax, eax
0x180001cf4  cmovnz  edi, r12d
0x180001cf8  mov     eax, edi
0x180001cfa  add     rsp, 48h
0x180001cfe  pop     r14
0x180001d00  pop     r12
0x180001d02  pop     rdi
0x180001d03  pop     rsi
0x180001d04  pop     rbx
0x180001d05  pop     rbp
0x180001d06  retn
```
