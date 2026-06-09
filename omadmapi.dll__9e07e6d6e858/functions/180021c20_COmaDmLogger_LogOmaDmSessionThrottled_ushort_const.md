# COmaDmLogger::LogOmaDmSessionThrottled(ushort const *)

- ea: `0x180021c20`
- end: `0x180021cb2`
- name: `?LogOmaDmSessionThrottled@COmaDmLogger@@QEAAXPEBG@Z`
- size: `146`
- prototype: `void __fastcall(COmaDmLogger *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001fa38`

## callees

- `0x18000171c`
- `0x1800031b0`
- `0x180021c20`

## pseudocode

```c
void __fastcall COmaDmLogger::LogOmaDmSessionThrottled(COmaDmLogger *this, const unsigned __int16 *a2)
{
  __int64 v2; // rax
  int v3; // eax
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-48h] BYREF
  const unsigned __int16 *v5; // [rsp+50h] [rbp-28h]
  int v6; // [rsp+58h] [rbp-20h]
  int v7; // [rsp+5Ch] [rbp-1Ch]

  if ( (unsigned int)dword_180032108 > 5 )
  {
    if ( a2 )
    {
      v2 = -1;
      do
        ++v2;
      while ( a2[v2] );
      v3 = 2 * v2 + 2;
    }
    else
    {
      a2 = (const unsigned __int16 *)&qword_1800289F0;
      v3 = 2;
    }
    v6 = v3;
    v5 = a2;
    v7 = 0;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180032108, (unsigned __int8 *)&word_18002B346, 0, 0, 3u, &v4);
  }
}

```

## disassembly

```asm
0x180021c20  sub     rsp, 78h
0x180021c24  mov     rax, cs:__security_cookie
0x180021c2b  xor     rax, rsp
0x180021c2e  mov     [rsp+78h+var_18], rax
0x180021c33  mov     eax, cs:dword_180032108
0x180021c39  cmp     eax, 5
0x180021c3c  jbe     short loc_180021C9F
0x180021c3e  xor     ecx, ecx
0x180021c40  test    rdx, rdx
0x180021c43  jz      short loc_180021C5B
0x180021c45  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021c49  inc     rax
0x180021c4c  cmp     [rdx+rax*2], cx
0x180021c50  jnz     short loc_180021C49
0x180021c52  lea     eax, ds:2[rax*2]
0x180021c59  jmp     short loc_180021C67
0x180021c5b  lea     rdx, qword_1800289F0
0x180021c62  mov     eax, 2
0x180021c67  mov     [rsp+78h+var_20], eax
0x180021c6b  xor     r9d, r9d
0x180021c6e  lea     rax, [rsp+78h+var_48]
0x180021c73  mov     [rsp+78h+var_28], rdx
0x180021c78  mov     [rsp+78h+var_1C], ecx
0x180021c7c  lea     rdx, word_18002B346
0x180021c83  mov     [rsp+78h+var_50], rax
0x180021c88  lea     rcx, dword_180032108
0x180021c8f  xor     r8d, r8d
0x180021c92  mov     [rsp+78h+var_58], 3
0x180021c9a  call    _tlgWriteTransfer_EventWriteTransfer
0x180021c9f  mov     rcx, [rsp+78h+var_18]
0x180021ca4  xor     rcx, rsp; StackCookie
0x180021ca7  call    __security_check_cookie
0x180021cac  add     rsp, 78h
0x180021cb0  retn
```
