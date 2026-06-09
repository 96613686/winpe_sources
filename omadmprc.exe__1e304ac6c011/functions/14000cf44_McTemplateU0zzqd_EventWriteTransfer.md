# McTemplateU0zzqd_EventWriteTransfer

- ea: `0x14000cf44`
- end: `0x14000d01b`
- name: `McTemplateU0zzqd_EventWriteTransfer`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000bbbc`

## callees

- `0x14000cd7c`
- `0x14000cf44`
- `0x140015690`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzqd_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        char a5,
        char a6)
{
  __int64 v6; // rax
  int v7; // edx
  __int64 v8; // rcx
  __int64 v9; // rcx
  bool v10; // zf
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-19h] BYREF
  const wchar_t *v13; // [rsp+40h] [rbp-9h]
  int v14; // [rsp+48h] [rbp-1h]
  int v15; // [rsp+4Ch] [rbp+3h]
  const wchar_t *v16; // [rsp+50h] [rbp+7h]
  int v17; // [rsp+58h] [rbp+Fh]
  int v18; // [rsp+5Ch] [rbp+13h]
  char *v19; // [rsp+60h] [rbp+17h]
  __int64 v20; // [rsp+68h] [rbp+1Fh]
  char *v21; // [rsp+70h] [rbp+27h]
  __int64 v22; // [rsp+78h] [rbp+2Fh]

  v6 = -1;
  v7 = 10;
  if ( a3 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a3[v8] );
    v9 = (unsigned int)(2 * v8 + 2);
  }
  else
  {
    v9 = 10;
  }
  v14 = v9;
  v15 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v13 = a3;
  v10 = a4 == 0;
  if ( a4 )
  {
    do
      ++v6;
    while ( a4[v6] );
    v7 = 2 * v6 + 2;
    v10 = a4 == 0;
  }
  if ( v10 )
    a4 = L"NULL";
  v17 = v7;
  v16 = a4;
  v19 = &a5;
  v18 = 0;
  v21 = &a6;
  v20 = 4;
  v22 = 4;
  return McGenEventWrite_EventWriteTransfer(
           v9,
           (const EVENT_DESCRIPTOR *)EnterpriseDiagnosticsOmaDmSessionRetryScheduledWithInitiationID,
           (__int64)a3,
           5u,
           &v12);
}

```

## disassembly

```asm
0x14000cf44  push    rbp
0x14000cf46  lea     rbp, [rsp-47h]
0x14000cf4b  sub     rsp, 90h
0x14000cf52  mov     rax, cs:__security_cookie
0x14000cf59  xor     rax, rsp
0x14000cf5c  mov     [rbp+47h+var_10], rax
0x14000cf60  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000cf64  xor     r10d, r10d
0x14000cf67  mov     edx, 0Ah
0x14000cf6c  test    r8, r8
0x14000cf6f  jz      short loc_14000CF87
0x14000cf71  mov     rcx, rax
0x14000cf74  inc     rcx
0x14000cf77  cmp     [r8+rcx*2], r10w
0x14000cf7c  jnz     short loc_14000CF74
0x14000cf7e  lea     ecx, ds:2[rcx*2]
0x14000cf85  jmp     short loc_14000CF89
0x14000cf87  mov     ecx, edx
0x14000cf89  test    r8, r8
0x14000cf8c  mov     [rbp+47h+var_48], ecx
0x14000cf8f  lea     r11, aNull; "NULL"
0x14000cf96  mov     [rbp+47h+var_44], r10d
0x14000cf9a  cmovz   r8, r11
0x14000cf9e  mov     [rbp+47h+var_50], r8
0x14000cfa2  test    r9, r9
0x14000cfa5  jz      short loc_14000CFBB
0x14000cfa7  inc     rax
0x14000cfaa  cmp     [r9+rax*2], r10w
0x14000cfaf  jnz     short loc_14000CFA7
0x14000cfb1  lea     edx, ds:2[rax*2]
0x14000cfb8  test    r9, r9
0x14000cfbb  cmovz   r9, r11
0x14000cfbf  mov     [rbp+47h+var_38], edx
0x14000cfc2  lea     rax, [rbp+47h+arg_20]
0x14000cfc6  mov     [rbp+47h+var_40], r9
0x14000cfca  mov     [rbp+47h+var_30], rax
0x14000cfce  lea     rdx, EnterpriseDiagnosticsOmaDmSessionRetryScheduledWithInitiationID
0x14000cfd5  lea     rax, [rbp+47h+arg_28]
0x14000cfd9  mov     [rbp+47h+var_34], r10d
0x14000cfdd  mov     [rbp+47h+var_20], rax
0x14000cfe1  mov     r9d, 5
0x14000cfe7  lea     rax, [rbp+47h+var_60]
0x14000cfeb  mov     [rbp+47h+var_28], 4
0x14000cff3  mov     [rsp+90h+var_70], rax
0x14000cff8  mov     [rbp+47h+var_18], 4
0x14000d000  call    McGenEventWrite_EventWriteTransfer
0x14000d005  mov     rcx, [rbp+47h+var_10]
0x14000d009  xor     rcx, rsp; StackCookie
0x14000d00c  call    __security_check_cookie
0x14000d011  add     rsp, 90h
0x14000d018  pop     rbp
0x14000d019  retn
```
