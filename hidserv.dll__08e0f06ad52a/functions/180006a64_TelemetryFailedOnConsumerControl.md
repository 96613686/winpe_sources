# TelemetryFailedOnConsumerControl

- ea: `0x180006a64`
- end: `0x180006b95`
- name: `TelemetryFailedOnConsumerControl`
- size: `305`
- prototype: `ULONG __fastcall(const int *, char *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005708`

## callees

- `0x180006a64`
- `0x1800081d4`
- `0x180008450`

## pseudocode

```c
ULONG __fastcall TelemetryFailedOnConsumerControl(const int *a1, char *a2, int a3)
{
  ULONG result; // eax
  __int64 v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // r9
  int v9; // [rsp+30h] [rbp-49h] BYREF
  __int64 v10; // [rsp+38h] [rbp-41h] BYREF
  __int64 v11; // [rsp+40h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+50h] [rbp-29h] BYREF
  __int64 *v13; // [rsp+70h] [rbp-9h]
  __int64 v14; // [rsp+78h] [rbp-1h]
  const int *v15; // [rsp+80h] [rbp+7h]
  int v16; // [rsp+88h] [rbp+Fh]
  int v17; // [rsp+8Ch] [rbp+13h]
  char *v18; // [rsp+90h] [rbp+17h]
  int v19; // [rsp+98h] [rbp+1Fh]
  int v20; // [rsp+9Ch] [rbp+23h]
  int *v21; // [rsp+A0h] [rbp+27h]
  __int64 v22; // [rsp+A8h] [rbp+2Fh]
  __int64 *v23; // [rsp+B0h] [rbp+37h]
  __int64 v24; // [rsp+B8h] [rbp+3Fh]

  result = dword_18000D000;
  if ( (unsigned int)dword_18000D000 > 5 )
  {
    result = qword_18000D010;
    if ( (qword_18000D010 & 0x400000000000LL) != 0 )
    {
      result = 0;
      if ( (qword_18000D018 & 0x400000000000LL) == qword_18000D018 )
      {
        v14 = 8;
        v13 = &v10;
        v5 = -1;
        v6 = 1;
        v10 = 1;
        if ( a1 )
        {
          v7 = -1;
          do
            ++v7;
          while ( *((_WORD *)a1 + v7) );
          v8 = (unsigned int)(2 * v7 + 2);
        }
        else
        {
          a1 = &dword_18000A75C;
          v8 = 2;
        }
        v15 = a1;
        v16 = v8;
        v17 = 0;
        if ( a2 )
        {
          do
            ++v5;
          while ( a2[v5] );
          v6 = (unsigned int)(v5 + 1);
        }
        else
        {
          a2 = byte_18000A758;
        }
        v18 = a2;
        v21 = &v9;
        v19 = v6;
        v23 = &v11;
        v20 = 0;
        v9 = a3;
        v22 = 4;
        v11 = 0x1000000;
        v24 = 8;
        return tlgWriteAgg((__int64)a1, (unsigned __int8 *)&dword_18000AE04, v6, v8, &v12);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006a64  push    rbp
0x180006a66  lea     rbp, [rsp-57h]
0x180006a6b  sub     rsp, 0D0h
0x180006a72  mov     rax, cs:__security_cookie
0x180006a79  xor     rax, rsp
0x180006a7c  mov     [rbp+57h+var_10], rax
0x180006a80  mov     eax, cs:dword_18000D000
0x180006a86  mov     r10d, r8d
0x180006a89  cmp     eax, 5
0x180006a8c  jbe     loc_180006B80
0x180006a92  mov     r9, cs:qword_18000D018
0x180006a99  mov     r8, 400000000000h
0x180006aa3  mov     rax, cs:qword_18000D010
0x180006aaa  test    r8, rax
0x180006aad  jz      loc_180006B80
0x180006ab3  mov     rax, r9
0x180006ab6  and     rax, r8
0x180006ab9  cmp     rax, r9
0x180006abc  jnz     loc_180006B80
0x180006ac2  lea     rax, [rbp+57h+var_98]
0x180006ac6  mov     [rbp+57h+var_58], 8
0x180006ace  mov     [rbp+57h+var_60], rax
0x180006ad2  xor     r11d, r11d
0x180006ad5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006ad9  mov     r8d, 1; int
0x180006adf  mov     [rbp+57h+var_98], r8
0x180006ae3  test    rcx, rcx
0x180006ae6  jz      short loc_180006AFF
0x180006ae8  mov     r9, rax
0x180006aeb  inc     r9
0x180006aee  cmp     [rcx+r9*2], r11w
0x180006af3  jnz     short loc_180006AEB
0x180006af5  lea     r9d, ds:2[r9*2]
0x180006afd  jmp     short loc_180006B0C
0x180006aff  lea     rcx, dword_18000A75C; int
0x180006b06  mov     r9d, 2; int
0x180006b0c  mov     [rbp+57h+var_50], rcx
0x180006b10  mov     [rbp+57h+var_48], r9d
0x180006b14  mov     [rbp+57h+var_44], r11d
0x180006b18  test    rdx, rdx
0x180006b1b  jz      short loc_180006B2C
0x180006b1d  inc     rax
0x180006b20  cmp     [rdx+rax], r11b
0x180006b24  jnz     short loc_180006B1D
0x180006b26  lea     r8d, [rax+1]
0x180006b2a  jmp     short loc_180006B33
0x180006b2c  lea     rdx, byte_18000A758
0x180006b33  lea     rax, [rbp+57h+var_A0]
0x180006b37  mov     [rbp+57h+var_40], rdx
0x180006b3b  mov     [rbp+57h+var_30], rax
0x180006b3f  lea     rdx, dword_18000AE04; int
0x180006b46  lea     rax, [rbp+57h+var_90]
0x180006b4a  mov     [rbp+57h+var_38], r8d
0x180006b4e  mov     [rbp+57h+var_20], rax
0x180006b52  lea     rax, [rbp+57h+var_80]
0x180006b56  mov     [rsp+0D0h+var_B0], rax; PEVENT_DATA_DESCRIPTOR
0x180006b5b  mov     [rbp+57h+var_34], r11d
0x180006b5f  mov     [rbp+57h+var_A0], r10d
0x180006b63  mov     [rbp+57h+var_28], 4
0x180006b6b  mov     [rbp+57h+var_90], 1000000h
0x180006b73  mov     [rbp+57h+var_18], 8
0x180006b7b  call    _tlgWriteAgg
0x180006b80  mov     rcx, [rbp+57h+var_10]
0x180006b84  xor     rcx, rsp; StackCookie
0x180006b87  call    __security_check_cookie
0x180006b8c  add     rsp, 0D0h
0x180006b93  pop     rbp
0x180006b94  retn
```
