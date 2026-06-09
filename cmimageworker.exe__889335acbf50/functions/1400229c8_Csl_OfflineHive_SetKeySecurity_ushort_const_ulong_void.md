# Csl::OfflineHive::SetKeySecurity(ushort const *,ulong,void *)

- ea: `0x1400229c8`
- end: `0x140022aa1`
- name: `?SetKeySecurity@OfflineHive@Csl@@QEAAJPEBGKPEAX@Z`
- size: `217`
- prototype: `__int64 __fastcall(Csl::OfflineHive *this, const unsigned __int16 *, __int64, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140019e40`

## callees

- `0x14000d7bc`
- `0x1400229c8`
- `0x140023c20`
- `0x140024760`
- `0x1400253e0`

## string_xrefs

- `0x140022a11`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x140022a62`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::OfflineHive::SetKeySecurity(
        Csl::OfflineHive *this,
        const unsigned __int16 *a2,
        __int64 a3,
        void *a4)
{
  __int64 v6; // rbx
  __int64 v7; // rax
  unsigned int v8; // eax
  unsigned int v9; // ebx
  __int64 v11; // rcx
  unsigned int v12; // eax
  unsigned int v13; // edi
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF

  v6 = 0;
  v15 = 0;
  if ( !a2 )
    goto LABEL_10;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  if ( !v7 )
    goto LABEL_10;
  v8 = OROpenKey(*((_QWORD *)this + 1), a2, &v15);
  if ( v8 )
  {
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x3CC,
           (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
           (const char *)v8);
    if ( v15 )
      ORCloseKey(v15);
    return v9;
  }
  v6 = v15;
  v11 = v15;
  if ( !v15 )
LABEL_10:
    v11 = *((_QWORD *)this + 1);
  v12 = ORSetKeySecurity(v11, 4, a4);
  if ( v12 )
  {
    v13 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x3D2,
            (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
            (const char *)v12);
    if ( v6 )
      ORCloseKey(v6);
    return v13;
  }
  else
  {
    if ( v6 )
      ORCloseKey(v6);
    return 0;
  }
}

```

## disassembly

```asm
0x1400229c8  push    rbx
0x1400229ca  push    rbp
0x1400229cb  push    rsi
0x1400229cc  push    rdi
0x1400229cd  sub     rsp, 28h
0x1400229d1  mov     rsi, r9
0x1400229d4  mov     rdi, rcx
0x1400229d7  xor     ebp, ebp
0x1400229d9  mov     ebx, ebp
0x1400229db  mov     [rsp+48h+arg_8], rbx
0x1400229e0  test    rdx, rdx
0x1400229e3  jz      short loc_140022A45
0x1400229e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400229e9  inc     rax
0x1400229ec  cmp     [rdx+rax*2], bp
0x1400229f0  jnz     short loc_1400229E9
0x1400229f2  test    rax, rax
0x1400229f5  jz      short loc_140022A45
0x1400229f7  lea     r8, [rsp+48h+arg_8]
0x1400229fc  mov     rcx, [rcx+8]
0x140022a00  call    OROpenKey
0x140022a05  test    eax, eax
0x140022a07  jz      short loc_140022A38
0x140022a09  mov     rcx, [rsp+48h]; this
0x140022a0e  mov     r9d, eax; char *
0x140022a11  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140022a18  mov     edx, 3CCh; void *
0x140022a1d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140022a22  mov     ebx, eax
0x140022a24  mov     rcx, [rsp+48h+arg_8]
0x140022a29  test    rcx, rcx
0x140022a2c  jz      short loc_140022A34
0x140022a2e  call    ORCloseKey
0x140022a33  nop
0x140022a34  mov     eax, ebx
0x140022a36  jmp     short loc_140022A97
0x140022a38  mov     rbx, [rsp+48h+arg_8]
0x140022a3d  test    rbx, rbx
0x140022a40  mov     rcx, rbx
0x140022a43  jnz     short loc_140022A49
0x140022a45  mov     rcx, [rdi+8]
0x140022a49  mov     r8, rsi
0x140022a4c  mov     edx, 4
0x140022a51  call    ORSetKeySecurity
0x140022a56  test    eax, eax
0x140022a58  jz      short loc_140022A87
0x140022a5a  mov     rcx, [rsp+48h]; this
0x140022a5f  mov     r9d, eax; char *
0x140022a62  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140022a69  mov     edx, 3D2h; void *
0x140022a6e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140022a73  mov     edi, eax
0x140022a75  test    rbx, rbx
0x140022a78  jz      short loc_140022A83
0x140022a7a  mov     rcx, rbx
0x140022a7d  call    ORCloseKey
0x140022a82  nop
0x140022a83  mov     eax, edi
0x140022a85  jmp     short loc_140022A97
0x140022a87  test    rbx, rbx
0x140022a8a  jz      short loc_140022A95
0x140022a8c  mov     rcx, rbx
0x140022a8f  call    ORCloseKey
0x140022a94  nop
0x140022a95  xor     eax, eax
0x140022a97  add     rsp, 28h
0x140022a9b  pop     rdi
0x140022a9c  pop     rsi
0x140022a9d  pop     rbp
0x140022a9e  pop     rbx
0x140022a9f  retn
```
