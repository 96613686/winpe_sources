# McTemplateU0s_EtwEventWriteTransfer

- ea: `0x18000c1a8`
- end: `0x18000c217`
- name: `McTemplateU0s_EtwEventWriteTransfer`
- size: `111`
- prototype: `__int64 __fastcall(_QWORD *, __int64, const char *)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f2c8`
- `0x18000f77c`
- `0x18001064c`
- `0x180011cb0`
- `0x1800122b8`
- `0x180012968`
- `0x180012b30`
- `0x180012cf8`
- `0x1800133a8`
- `0x180013578`
- `0x1800142dc`
- `0x1800148c4`

## callees

- `0x180001f60`
- `0x18000c150`
- `0x18000c1a8`

## pseudocode

```c
__int64 __fastcall McTemplateU0s_EtwEventWriteTransfer(_QWORD *a1, __int64 a2, const char *a3)
{
  __int64 v3; // rax
  int v4; // eax
  _BYTE v6[16]; // [rsp+30h] [rbp-38h] BYREF
  const char *v7; // [rsp+40h] [rbp-28h]
  int v8; // [rsp+48h] [rbp-20h]
  int v9; // [rsp+4Ch] [rbp-1Ch]

  if ( a3 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a3[v3] );
    v4 = v3 + 1;
  }
  else
  {
    v4 = 5;
  }
  v8 = v4;
  v9 = 0;
  if ( !a3 )
    a3 = "NULL";
  v7 = a3;
  return McGenEventWrite_EtwEventWriteTransfer(a1, a2, (__int64)a3, (__int64)"NULL", (__int64)v6);
}

```

## disassembly

```asm
0x18000c1a8  sub     rsp, 68h
0x18000c1ac  mov     rax, cs:__security_cookie
0x18000c1b3  xor     rax, rsp
0x18000c1b6  mov     [rsp+68h+var_18], rax
0x18000c1bb  test    r8, r8
0x18000c1be  jz      short loc_18000C1D2
0x18000c1c0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c1c4  inc     rax
0x18000c1c7  cmp     byte ptr [r8+rax], 0
0x18000c1cc  jnz     short loc_18000C1C4
0x18000c1ce  inc     eax
0x18000c1d0  jmp     short loc_18000C1D7
0x18000c1d2  mov     eax, 5
0x18000c1d7  test    r8, r8
0x18000c1da  mov     [rsp+68h+var_20], eax
0x18000c1de  lea     r9, aNull; "NULL"
0x18000c1e5  mov     [rsp+68h+var_1C], 0
0x18000c1ed  cmovz   r8, r9
0x18000c1f1  lea     rax, [rsp+68h+var_38]
0x18000c1f6  mov     [rsp+68h+var_28], r8
0x18000c1fb  mov     [rsp+68h+var_48], rax
0x18000c200  call    McGenEventWrite_EtwEventWriteTransfer
0x18000c205  mov     rcx, [rsp+68h+var_18]
0x18000c20a  xor     rcx, rsp; StackCookie
0x18000c20d  call    __security_check_cookie
0x18000c212  add     rsp, 68h
0x18000c216  retn
```
