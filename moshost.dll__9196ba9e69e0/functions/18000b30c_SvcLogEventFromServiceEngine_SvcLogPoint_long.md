# SvcLogEventFromServiceEngine(SvcLogPoint,long)

- ea: `0x18000b30c`
- end: `0x18000b385`
- name: `?SvcLogEventFromServiceEngine@@YAXW4SvcLogPoint@@J@Z`
- size: `121`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b8e0`
- `0x18000bcc0`

## callees

- `0x180001d00`
- `0x180007298`
- `0x18000b30c`

## pseudocode

```c
__int64 __fastcall SvcLogEventFromServiceEngine(__int64 a1, int a2)
{
  __int64 result; // rax
  int v3; // [rsp+30h] [rbp-58h] BYREF
  int v4; // [rsp+38h] [rbp-50h] BYREF
  int *v5; // [rsp+50h] [rbp-38h]
  __int64 v6; // [rsp+58h] [rbp-30h]
  int *v7; // [rsp+60h] [rbp-28h]
  __int64 v8; // [rsp+68h] [rbp-20h]

  if ( (Microsoft_Windows_MosHostEnableBits & 1) != 0 )
  {
    v3 = a2;
    v5 = &v3;
    v4 = a1;
    v7 = &v4;
    v6 = 4;
    v8 = 4;
    return McGenEventWrite_EventWriteTransfer(a1, EngineState);
  }
  return result;
}

```

## disassembly

```asm
0x18000b30c  mov     r11, rsp
0x18000b30f  sub     rsp, 88h
0x18000b316  mov     rax, cs:__security_cookie
0x18000b31d  xor     rax, rsp
0x18000b320  mov     [rsp+88h+var_18], rax
0x18000b325  test    cs:Microsoft_Windows_MosHostEnableBits, 1
0x18000b32c  jz      short loc_18000B370
0x18000b32e  lea     rax, [r11-58h]
0x18000b332  mov     [rsp+88h+var_58], edx
0x18000b336  mov     [r11-38h], rax
0x18000b33a  lea     rdx, EngineState
0x18000b341  lea     rax, [r11-50h]
0x18000b345  mov     [rsp+88h+var_50], ecx
0x18000b349  mov     [r11-28h], rax
0x18000b34d  mov     r9d, 3
0x18000b353  lea     rax, [r11-48h]
0x18000b357  mov     qword ptr [r11-30h], 4
0x18000b35f  mov     [r11-68h], rax
0x18000b363  mov     qword ptr [r11-20h], 4
0x18000b36b  call    McGenEventWrite_EventWriteTransfer
0x18000b370  mov     rcx, [rsp+88h+var_18]
0x18000b375  xor     rcx, rsp; StackCookie
0x18000b378  call    __security_check_cookie
0x18000b37d  add     rsp, 88h
0x18000b384  retn
```
