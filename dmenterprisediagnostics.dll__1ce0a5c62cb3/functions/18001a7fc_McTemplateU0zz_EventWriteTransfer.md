# McTemplateU0zz_EventWriteTransfer

- ea: `0x18001a7fc`
- end: `0x18001a8ad`
- name: `McTemplateU0zz_EventWriteTransfer`
- size: `177`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180019194`

## callees

- `0x1800017e0`
- `0x18001a62c`
- `0x18001a7fc`

## pseudocode

```c
ULONG __fastcall McTemplateU0zz_EventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, const wchar_t *a4)
{
  __int64 v4; // rax
  int v5; // edx
  __int64 v6; // rcx
  __int64 v7; // rcx
  bool v8; // zf
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v11; // [rsp+40h] [rbp-38h]
  int v12; // [rsp+48h] [rbp-30h]
  int v13; // [rsp+4Ch] [rbp-2Ch]
  const wchar_t *v14; // [rsp+50h] [rbp-28h]
  int v15; // [rsp+58h] [rbp-20h]
  int v16; // [rsp+5Ch] [rbp-1Ch]

  v4 = -1;
  v5 = 10;
  if ( a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
    v7 = (unsigned int)(2 * v6 + 2);
  }
  else
  {
    v7 = 10;
  }
  v12 = v7;
  v13 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v11 = a3;
  v8 = a4 == 0;
  if ( a4 )
  {
    do
      ++v4;
    while ( a4[v4] );
    v5 = 2 * v4 + 2;
    v8 = a4 == 0;
  }
  if ( v8 )
    a4 = L"NULL";
  v15 = v5;
  v14 = a4;
  v16 = 0;
  return McGenEventWrite_EventWriteTransfer(
           v7,
           (const EVENT_DESCRIPTOR *)TraceMerge_NGEN_CopyingPDB_Start,
           (__int64)a3,
           3u,
           &v10);
}

```

## disassembly

```asm
0x18001a7fc  sub     rsp, 78h
0x18001a800  mov     rax, cs:__security_cookie
0x18001a807  xor     rax, rsp
0x18001a80a  mov     [rsp+78h+var_18], rax
0x18001a80f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a813  xor     r10d, r10d
0x18001a816  mov     edx, 0Ah
0x18001a81b  test    r8, r8
0x18001a81e  jz      short loc_18001A836
0x18001a820  mov     rcx, rax
0x18001a823  inc     rcx
0x18001a826  cmp     [r8+rcx*2], r10w
0x18001a82b  jnz     short loc_18001A823
0x18001a82d  lea     ecx, ds:2[rcx*2]
0x18001a834  jmp     short loc_18001A838
0x18001a836  mov     ecx, edx
0x18001a838  test    r8, r8
0x18001a83b  mov     [rsp+78h+var_30], ecx
0x18001a83f  lea     r11, aNull; "NULL"
0x18001a846  mov     [rsp+78h+var_2C], r10d
0x18001a84b  cmovz   r8, r11
0x18001a84f  mov     [rsp+78h+var_38], r8
0x18001a854  test    r9, r9
0x18001a857  jz      short loc_18001A86D
0x18001a859  inc     rax
0x18001a85c  cmp     [r9+rax*2], r10w
0x18001a861  jnz     short loc_18001A859
0x18001a863  lea     edx, ds:2[rax*2]
0x18001a86a  test    r9, r9
0x18001a86d  cmovz   r9, r11
0x18001a871  mov     [rsp+78h+var_20], edx
0x18001a875  mov     [rsp+78h+var_28], r9
0x18001a87a  lea     rax, [rsp+78h+var_48]
0x18001a87f  mov     r9d, 3
0x18001a885  mov     [rsp+78h+var_1C], r10d
0x18001a88a  lea     rdx, TraceMerge_NGEN_CopyingPDB_Start
0x18001a891  mov     [rsp+78h+var_58], rax
0x18001a896  call    McGenEventWrite_EventWriteTransfer
0x18001a89b  mov     rcx, [rsp+78h+var_18]
0x18001a8a0  xor     rcx, rsp; StackCookie
0x18001a8a3  call    __security_check_cookie
0x18001a8a8  add     rsp, 78h
0x18001a8ac  retn
```
