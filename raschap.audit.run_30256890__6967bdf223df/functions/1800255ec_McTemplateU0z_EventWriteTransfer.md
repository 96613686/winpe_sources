# McTemplateU0z_EventWriteTransfer

- ea: `0x1800255ec`
- end: `0x180025666`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `122`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e548`
- `0x180010218`
- `0x18001029c`

## callees

- `0x180013b20`
- `0x180016ab0`
- `0x1800255ec`

## pseudocode

```c
ULONG __fastcall McTemplateU0z_EventWriteTransfer(REGHANDLE *a1, const EVENT_DESCRIPTOR *a2, const wchar_t *a3)
{
  __int64 v3; // rax
  int v4; // eax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-38h] BYREF
  const wchar_t *v7; // [rsp+40h] [rbp-28h]
  int v8; // [rsp+48h] [rbp-20h]
  int v9; // [rsp+4Ch] [rbp-1Ch]

  if ( a3 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a3[v3] );
    v4 = 2 * v3 + 2;
  }
  else
  {
    v4 = 10;
  }
  v8 = v4;
  v9 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v7 = a3;
  return McGenEventWrite_EventWriteTransfer(a1, a2, (__int64)a3, 2u, &v6);
}

```

## disassembly

```asm
0x1800255ec  sub     rsp, 68h
0x1800255f0  mov     rax, cs:__security_cookie
0x1800255f7  xor     rax, rsp
0x1800255fa  mov     [rsp+68h+var_18], rax
0x1800255ff  xor     r10d, r10d
0x180025602  test    r8, r8
0x180025605  jz      short loc_18002561E
0x180025607  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002560b  inc     rax
0x18002560e  cmp     [r8+rax*2], r10w
0x180025613  jnz     short loc_18002560B
0x180025615  lea     eax, ds:2[rax*2]
0x18002561c  jmp     short loc_180025623
0x18002561e  mov     eax, 0Ah
0x180025623  lea     r9, aNull_0; "NULL"
0x18002562a  mov     [rsp+68h+var_20], eax
0x18002562e  test    r8, r8
0x180025631  mov     [rsp+68h+var_1C], r10d
0x180025636  lea     rax, [rsp+68h+var_38]
0x18002563b  cmovz   r8, r9
0x18002563f  mov     [rsp+68h+var_48], rax
0x180025644  mov     r9d, 2
0x18002564a  mov     [rsp+68h+var_28], r8
0x18002564f  call    McGenEventWrite_EventWriteTransfer
0x180025654  mov     rcx, [rsp+68h+var_18]
0x180025659  xor     rcx, rsp; StackCookie
0x18002565c  call    __security_check_cookie
0x180025661  add     rsp, 68h
0x180025665  retn
```
