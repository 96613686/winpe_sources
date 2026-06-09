# McTemplateK0zz_EtwWriteTransfer

- ea: `0x1400015f0`
- end: `0x1400016ad`
- name: `McTemplateK0zz_EtwWriteTransfer`
- size: `189`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140008010`
- `0x140008ed0`
- `0x140009fa0`

## callees

- `0x1400015f0`
- `0x140001800`
- `0x140001b40`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0zz_EtwWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        __int64 a4,
        const char *a5)
{
  __int64 v6; // rcx
  __int64 v7; // rax
  bool v8; // zf
  const char *v9; // rax
  int v10; // ecx
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v13; // [rsp+40h] [rbp-38h]
  int v14; // [rsp+48h] [rbp-30h]
  int v15; // [rsp+4Ch] [rbp-2Ch]
  const char *v16; // [rsp+50h] [rbp-28h]
  int v17; // [rsp+58h] [rbp-20h]
  int v18; // [rsp+5Ch] [rbp-1Ch]

  v6 = -1;
  v7 = -1;
  do
    v8 = a1f81d1313fac45[++v7] == 0;
  while ( !v8 );
  v13 = L"1f81d131-3fac-4537-9e0c-7e7b0c2f4b55";
  v14 = 2 * v7 + 2;
  v9 = a5;
  v15 = 0;
  if ( a5 )
  {
    do
      v8 = *(_WORD *)&a5[2 * v6++ + 2] == 0;
    while ( !v8 );
    v10 = 2 * v6 + 2;
  }
  else
  {
    v10 = 10;
  }
  v17 = v10;
  v18 = 0;
  if ( !a5 )
    v9 = L"NULL";
  v16 = v9;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, (__int64)a1, (__int64)L"NULL", &v12);
}

```

## disassembly

```asm
0x1400015f0  sub     rsp, 78h
0x1400015f4  mov     rax, cs:__security_cookie
0x1400015fb  xor     rax, rsp
0x1400015fe  mov     [rsp+78h+var_18], rax
0x140001603  mov     r8, rcx; int
0x140001606  lea     r9, a1f81d1313fac45; "1f81d131-3fac-4537-9e0c-7e7b0c2f4b55"
0x14000160d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140001614  mov     rax, rcx
0x140001617  nop     word ptr [rax+rax+00000000h]
0x140001620  cmp     word ptr [r9+rax*2+2], 0
0x140001627  lea     rax, [rax+1]
0x14000162b  jnz     short loc_140001620
0x14000162d  lea     eax, ds:2[rax*2]
0x140001634  mov     [rsp+78h+var_38], r9
0x140001639  xor     r10d, r10d
0x14000163c  mov     [rsp+78h+var_30], eax
0x140001640  mov     rax, [rsp+78h+arg_20]
0x140001648  mov     [rsp+78h+var_2C], r10d
0x14000164d  test    rax, rax
0x140001650  jz      short loc_140001667
0x140001652  cmp     [rax+rcx*2+2], r10w
0x140001658  lea     rcx, [rcx+1]
0x14000165c  jnz     short loc_140001652
0x14000165e  lea     ecx, ds:2[rcx*2]
0x140001665  jmp     short loc_14000166C
0x140001667  mov     ecx, 0Ah
0x14000166c  test    rax, rax
0x14000166f  mov     [rsp+78h+var_20], ecx
0x140001673  lea     r9, aNull; "NULL"
0x14000167a  mov     [rsp+78h+var_1C], r10d
0x14000167f  cmovz   rax, r9
0x140001683  mov     rcx, r8; int
0x140001686  mov     [rsp+78h+var_28], rax
0x14000168b  lea     rax, [rsp+78h+var_48]
0x140001690  mov     [rsp+78h+var_58], rax; PEVENT_DATA_DESCRIPTOR
0x140001695  call    McGenEventWrite_EtwWriteTransfer
0x14000169a  mov     rcx, [rsp+78h+var_18]
0x14000169f  xor     rcx, rsp; StackCookie
0x1400016a2  call    __security_check_cookie
0x1400016a7  add     rsp, 78h
0x1400016ab  retn
```
