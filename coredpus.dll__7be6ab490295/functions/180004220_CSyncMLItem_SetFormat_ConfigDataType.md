# CSyncMLItem::SetFormat(ConfigDataType)

- ea: `0x180004220`
- end: `0x180004397`
- name: `?SetFormat@CSyncMLItem@@QEAAJW4ConfigDataType@@@Z`
- size: `375`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000a760`
- `0x18000e940`
- `0x18001ef60`

## callees

- `0x180002550`
- `0x180004220`
- `0x180011034`
- `0x1800145f0`
- `0x180015174`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800042f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800042f3`
- `DMCmnUtils!CopyString` at `0x180004311`
- `DMCmnUtils!CopyString` at `0x18000434e`
- `DMCmnUtils!CopyString` at `0x180004311`
- `DMCmnUtils!CopyString` at `0x18000434e`

## pseudocode

```c
__int64 __fastcall CSyncMLItem::SetFormat(__int64 a1, int a2)
{
  _QWORD *v2; // r14
  unsigned __int16 *v4; // rdi
  _QWORD *v5; // rax
  __int64 i; // rbx
  void **v8; // rsi
  void *v9; // rcx
  int v10; // edx
  unsigned __int64 v11; // [rsp+30h] [rbp+8h] BYREF

  v2 = *(_QWORD **)(a1 + 16);
  v4 = (unsigned __int16 *)a2;
  if ( !v2 )
  {
    v5 = operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
    v11 = (unsigned __int64)v5;
    v2 = v5;
    if ( !v5 )
    {
      *(_QWORD *)(a1 + 16) = 0;
      return 2147942414LL;
    }
    v5[16] = 0;
    memset_0(v5, 0, 0x80u);
    *(_QWORD *)(a1 + 16) = v2;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 0x10 )
      return (unsigned int)-2147024809;
    if ( !*((_DWORD *)&CSyncMLMeta::rgSupportedProps + i) )
      break;
  }
  if ( !(unsigned int)CSyncMLMeta::IsImplementedProp(i) )
    return 2147500033LL;
  v8 = (void **)&v2[i];
  if ( (unsigned int)i > 4 )
  {
    v10 = 0;
    *v8 = v4;
LABEL_18:
    *((_DWORD *)v2 + 32) |= 1 << i;
    return (unsigned int)v10;
  }
  v9 = *v8;
  v11 = 0;
  LocalFree(v9);
  *v8 = 0;
  v10 = CopyString(v4, 0xFFFFFFFF, (unsigned __int16 **)&v2[i]);
  if ( v4 )
  {
    v10 = StringCchLengthW(v4, 0x7FFFFFFFu, &v11);
    if ( v10 >= 0 )
    {
      if ( v11 )
      {
        v10 = CopyString(v4, v11, (unsigned __int16 **)&v2[i]);
        if ( v10 >= 0 )
          goto LABEL_18;
      }
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180004220  mov     [rsp+arg_10], rbx
0x180004225  mov     [rsp+arg_18], rdi
0x18000422a  push    r14
0x18000422c  sub     rsp, 20h
0x180004230  mov     r14, [rcx+10h]
0x180004234  mov     rbx, rcx
0x180004237  movsxd  rdi, edx
0x18000423a  test    r14, r14
0x18000423d  jnz     short loc_180004281
0x18000423f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004246  mov     ecx, 88h; unsigned __int64
0x18000424b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004250  mov     [rsp+28h+arg_0], rax
0x180004255  mov     r14, rax
0x180004258  test    rax, rax
0x18000425b  jz      short loc_1800042A3
0x18000425d  xor     edx, edx; Val
0x18000425f  mov     qword ptr [rax+80h], 0
0x18000426a  mov     r8d, 80h; Size
0x180004270  mov     rcx, rax; void *
0x180004273  call    memset_0
0x180004278  mov     [rbx+10h], r14
0x18000427c  test    r14, r14
0x18000427f  jz      short loc_1800042AB
0x180004281  xor     ebx, ebx
0x180004283  lea     rax, ?rgSupportedProps@CSyncMLMeta@@0QBW4SyncMLProp@@B; SyncMLProp const near * const CSyncMLMeta::rgSupportedProps
0x18000428a  nop     word ptr [rax+rax+00h]
0x180004290  cmp     ebx, 10h
0x180004293  jnb     loc_18000437E
0x180004299  cmp     dword ptr [rax+rbx*4], 0
0x18000429d  jz      short loc_1800042B5
0x18000429f  inc     ebx
0x1800042a1  jmp     short loc_180004290
0x1800042a3  mov     qword ptr [rbx+10h], 0
0x1800042ab  mov     eax, 8007000Eh
0x1800042b0  jmp     loc_180004385
0x1800042b5  mov     ecx, ebx; unsigned int
0x1800042b7  call    ?IsImplementedProp@CSyncMLMeta@@CAHK@Z; CSyncMLMeta::IsImplementedProp(ulong)
0x1800042bc  test    eax, eax
0x1800042be  jnz     short loc_1800042D9
0x1800042c0  mov     edx, 80004001h
0x1800042c5  mov     eax, edx
0x1800042c7  mov     rbx, [rsp+28h+arg_10]
0x1800042cc  mov     rdi, [rsp+28h+arg_18]
0x1800042d1  add     rsp, 20h
0x1800042d5  pop     r14
0x1800042d7  retn
0x1800042d9  mov     [rsp+28h+arg_8], rsi
0x1800042de  lea     rsi, [r14+rbx*8]
0x1800042e2  cmp     ebx, 4
0x1800042e5  ja      short loc_180004362
0x1800042e7  mov     rcx, [rsi]; hMem
0x1800042ea  mov     [rsp+28h+arg_0], 0
0x1800042f3  call    cs:__imp_LocalFree
0x1800042fa  nop     dword ptr [rax+rax+00h]
0x1800042ff  mov     r8, rsi
0x180004302  mov     qword ptr [rsi], 0
0x180004309  mov     edx, 0FFFFFFFFh
0x18000430e  mov     rcx, rdi
0x180004311  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180004318  nop     dword ptr [rax+rax+00h]
0x18000431d  mov     edx, eax
0x18000431f  test    rdi, rdi
0x180004322  jz      short loc_180004377
0x180004324  lea     r8, [rsp+28h+arg_0]; unsigned __int64 *
0x180004329  mov     edx, 7FFFFFFFh; unsigned __int64
0x18000432e  mov     rcx, rdi; unsigned __int16 *
0x180004331  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180004336  mov     edx, eax
0x180004338  test    eax, eax
0x18000433a  js      short loc_180004377
0x18000433c  mov     rax, [rsp+28h+arg_0]
0x180004341  test    rax, rax
0x180004344  jz      short loc_180004377
0x180004346  mov     r8, rsi
0x180004349  mov     edx, eax
0x18000434b  mov     rcx, rdi
0x18000434e  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180004355  nop     dword ptr [rax+rax+00h]
0x18000435a  mov     edx, eax
0x18000435c  test    eax, eax
0x18000435e  jns     short loc_180004367
0x180004360  jmp     short loc_180004377
0x180004362  xor     edx, edx
0x180004364  mov     [rsi], rdi
0x180004367  mov     ecx, ebx
0x180004369  mov     eax, 1
0x18000436e  shl     eax, cl
0x180004370  or      [r14+80h], eax
0x180004377  mov     rsi, [rsp+28h+arg_8]
0x18000437c  jmp     short loc_180004383
0x18000437e  mov     edx, 80070057h
0x180004383  mov     eax, edx
0x180004385  mov     rbx, [rsp+28h+arg_10]
0x18000438a  mov     rdi, [rsp+28h+arg_18]
0x18000438f  add     rsp, 20h
0x180004393  pop     r14
0x180004395  retn
```
