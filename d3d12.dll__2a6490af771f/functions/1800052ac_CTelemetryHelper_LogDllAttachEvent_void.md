# CTelemetryHelper::LogDllAttachEvent(void)

- ea: `0x1800052ac`
- end: `0x18000535f`
- name: `?LogDllAttachEvent@CTelemetryHelper@@QEAAXXZ`
- size: `179`
- prototype: `void __fastcall(CTelemetryHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180004ba8`

## callees

- `0x1800052ac`
- `0x180008988`
- `0x18000b410`

## pseudocode

```c
void __fastcall CTelemetryHelper::LogDllAttachEvent(CTelemetryHelper *this)
{
  char v1; // [rsp+30h] [rbp-68h] BYREF
  int v2; // [rsp+34h] [rbp-64h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v3; // [rsp+40h] [rbp-58h] BYREF
  int *v4; // [rsp+60h] [rbp-38h]
  __int64 v5; // [rsp+68h] [rbp-30h]
  char *v6; // [rsp+70h] [rbp-28h]
  __int64 v7; // [rsp+78h] [rbp-20h]

  if ( byte_18001C108
    && (unsigned int)*off_18001C110 > 5
    && (*((_QWORD *)off_18001C110 + 2) & 0x200000000000LL) != 0
    && (*((_QWORD *)off_18001C110 + 3) & 0x200000000000LL) == *((_QWORD *)off_18001C110 + 3) )
  {
    v1 = 1;
    v6 = &v1;
    v2 = 1;
    v7 = 1;
    v4 = &v2;
    v5 = 4;
    tlgWriteTransfer_EventWriteTransfer((__int64)off_18001C110, (unsigned __int8 *)byte_180018341, 0, 0, 4u, &v3);
  }
}

```

## disassembly

```asm
0x1800052ac  mov     r11, rsp
0x1800052af  sub     rsp, 98h
0x1800052b6  mov     rax, cs:__security_cookie
0x1800052bd  xor     rax, rsp
0x1800052c0  mov     [rsp+98h+var_18], rax
0x1800052c8  xor     r8d, r8d
0x1800052cb  cmp     cs:byte_18001C108, r8b
0x1800052d2  jz      short loc_180005347
0x1800052d4  mov     rcx, cs:off_18001C110
0x1800052db  mov     eax, [rcx]
0x1800052dd  cmp     eax, 5
0x1800052e0  jbe     short loc_180005347
0x1800052e2  mov     rdx, [rcx+18h]
0x1800052e6  mov     r9, 200000000000h
0x1800052f0  mov     rax, [rcx+10h]
0x1800052f4  test    r9, rax
0x1800052f7  jz      short loc_180005347
0x1800052f9  mov     rax, rdx
0x1800052fc  and     rax, r9
0x1800052ff  cmp     rax, rdx
0x180005302  jnz     short loc_180005347
0x180005304  lea     edx, [r8+1]
0x180005308  xor     r9d, r9d
0x18000530b  lea     rax, [r11-68h]
0x18000530f  mov     [rsp+98h+var_68], dl
0x180005313  mov     [r11-28h], rax
0x180005317  lea     rax, [r11-64h]
0x18000531b  mov     [rsp+98h+var_64], edx
0x18000531f  mov     [r11-20h], rdx
0x180005323  lea     edx, [r8+4]
0x180005327  mov     [r11-38h], rax
0x18000532b  lea     rax, [r11-58h]
0x18000532f  mov     [r11-70h], rax
0x180005333  mov     [rsp+98h+var_78], edx
0x180005337  mov     [r11-30h], rdx
0x18000533b  lea     rdx, byte_180018341
0x180005342  call    _tlgWriteTransfer_EventWriteTransfer
0x180005347  mov     rcx, [rsp+98h+var_18]
0x18000534f  xor     rcx, rsp; StackCookie
0x180005352  call    __security_check_cookie
0x180005357  add     rsp, 98h
0x18000535e  retn
```
