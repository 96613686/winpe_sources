# IASAttributeFromBerVal(berval const &,IASTYPEENUM)

- ea: `0x18002752c`
- end: `0x1800276a7`
- name: `?IASAttributeFromBerVal@@YAPEAU_IASATTRIBUTE@@AEBUberval@@W4IASTYPEENUM@@@Z`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024dcc`

## callees

- `0x180001f26`
- `0x18000b680`
- `0x18000b81c`
- `0x18000bea8`
- `0x18000c108`
- `0x18000c808`
- `0x18000d55c`
- `0x18002752c`

## import_xrefs

- `msvcrt!strtoul` at `0x180027634`
- `msvcrt!strtoul` at `0x180027666`
- `msvcrt!strtoul` at `0x180027634`
- `msvcrt!strtoul` at `0x180027666`
- `msvcrt!_strnicmp` at `0x18002767f`
- `msvcrt!_strnicmp` at `0x18002767f`
- `WS2_32!__imp_htonl` at `0x18002763c`
- `WS2_32!__imp_htonl` at `0x18002763c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800275e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800275e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IASAttributeFromBerVal(const char **a1, int a2)
{
  __int64 v4; // rdi
  unsigned __int16 v5; // dx
  unsigned __int8 *v6; // r8
  const char *v7; // rbp
  void *v8; // rsi
  __int64 v9; // rax
  size_t v10; // r15
  void *v11; // rax
  int v12; // edx
  u_long v13; // eax
  u_long v15; // [rsp+58h] [rbp+10h] BYREF
  __int64 v16; // [rsp+60h] [rbp+18h] BYREF

  IASTL::IASAttribute::IASAttribute((IASTL::IASAttribute *)&v16, a2);
  v4 = v16;
  switch ( a2 )
  {
    case 1:
      *(_DWORD *)(v4 + 24) = _strnicmp(a1[1], "TRUE", *(unsigned int *)a1) == 0;
      break;
    case 2:
    case 3:
      *(_DWORD *)(v4 + 24) = strtoul(a1[1], 0, 10);
      break;
    case 4:
      v13 = strtoul(a1[1], 0, 10);
      v15 = htonl(v13);
      v5 = 2;
      v6 = (unsigned __int8 *)&v15;
      goto LABEL_21;
    case 5:
      v7 = a1[1];
      v8 = 0;
      if ( v7 )
      {
        v9 = -1;
        do
          ++v9;
        while ( v7[v9] );
        v10 = v9 + 1;
        v11 = CoTaskMemAlloc(v9 + 1);
        v8 = v11;
        if ( !v11 )
          IASTL::issue_error((IASTL *)0x8007000ELL, v12);
        memcpy_0(v11, v7, v10);
      }
      IASTL::IASAttribute::clearValue((IASTL::IASAttribute *)&v16);
      *(_QWORD *)(v4 + 24) = v8;
      *(_QWORD *)(v4 + 32) = 0;
      *(_DWORD *)(v4 + 16) = 5;
      break;
    default:
      if ( a2 != 6 )
      {
        if ( a2 == 7 )
          goto LABEL_11;
        if ( a2 != 8 )
        {
          if ( a2 == 10 )
          {
            v5 = 23;
            v6 = (unsigned __int8 *)a1[1];
LABEL_21:
            IASTL::IASAttribute::setSockAddress((IASTL::IASAttribute *)&v16, v5, v6);
            break;
          }
LABEL_11:
          _com_issue_error(-2147024809);
        }
      }
      IASTL::IASAttribute::setOctetString(
        (IASTL::IASAttribute *)&v16,
        *(unsigned int *)a1,
        (const unsigned __int8 *)a1[1]);
      break;
  }
  *(_DWORD *)(v4 + 16) = a2;
  return v4;
}

```

## disassembly

```asm
0x18002752c  mov     [rsp+arg_0], rbx
0x180027531  push    rbp
0x180027532  push    rsi
0x180027533  push    rdi
0x180027534  push    r14
0x180027536  push    r15
0x180027538  sub     rsp, 20h
0x18002753c  mov     r14d, edx
0x18002753f  mov     rbx, rcx
0x180027542  lea     rcx, [rsp+48h+arg_10]; this
0x180027547  call    ??0IASAttribute@IASTL@@QEAA@_N@Z; IASTL::IASAttribute::IASAttribute(bool)
0x18002754c  nop
0x18002754d  mov     r8d, r14d
0x180027550  mov     rdi, [rsp+48h+arg_10]
0x180027555  sub     r8d, 1
0x180027559  jz      loc_180027671
0x18002755f  sub     r8d, 1
0x180027563  jz      loc_18002765C
0x180027569  sub     r8d, 1
0x18002756d  jz      loc_18002765C
0x180027573  sub     r8d, 1
0x180027577  jz      loc_18002762A
0x18002757d  sub     r8d, 1
0x180027581  jz      short loc_1800275C8
0x180027583  sub     r8d, 1
0x180027587  jz      short loc_1800275B3
0x180027589  sub     r8d, 1
0x18002758d  jz      short loc_1800275A8
0x18002758f  sub     r8d, 1
0x180027593  jz      short loc_1800275B3
0x180027595  cmp     r8d, 2
0x180027599  jnz     short loc_1800275A8
0x18002759b  lea     edx, [r8+15h]
0x18002759f  mov     r8, [rbx+8]
0x1800275a3  jmp     loc_180027650
0x1800275a8  mov     ecx, 80070057h; int
0x1800275ad  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800275b3  mov     r8, [rbx+8]; Src
0x1800275b7  mov     edx, [rbx]; Size
0x1800275b9  lea     rcx, [rsp+48h+arg_10]; this
0x1800275be  call    ?setOctetString@IASAttribute@IASTL@@QEAAXKPEBE@Z; IASTL::IASAttribute::setOctetString(ulong,uchar const *)
0x1800275c3  jmp     loc_18002768F
0x1800275c8  mov     rbp, [rbx+8]
0x1800275cc  xor     ebx, ebx
0x1800275ce  mov     esi, ebx
0x1800275d0  test    rbp, rbp
0x1800275d3  jz      short loc_18002760F
0x1800275d5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800275d9  inc     rax
0x1800275dc  cmp     [rax+rbp], bl
0x1800275df  jnz     short loc_1800275D9
0x1800275e1  lea     r15, [rax+1]
0x1800275e5  mov     rcx, r15; cb
0x1800275e8  call    cs:__imp_CoTaskMemAlloc
0x1800275ee  mov     rsi, rax
0x1800275f1  test    rax, rax
0x1800275f4  jnz     short loc_180027601
0x1800275f6  mov     ecx, 8007000Eh; this
0x1800275fb  call    ?issue_error@IASTL@@YAXJ@Z; IASTL::issue_error(long)
0x180027601  mov     r8, r15; Size
0x180027604  mov     rdx, rbp; Src
0x180027607  mov     rcx, rax; void *
0x18002760a  call    memcpy_0
0x18002760f  lea     rcx, [rsp+48h+arg_10]; this
0x180027614  call    ?clearValue@IASAttribute@IASTL@@IEAAXXZ; IASTL::IASAttribute::clearValue(void)
0x180027619  mov     [rdi+18h], rsi
0x18002761d  mov     [rdi+20h], rbx
0x180027621  mov     dword ptr [rdi+10h], 5
0x180027628  jmp     short loc_18002768F
0x18002762a  xor     edx, edx; EndPtr
0x18002762c  lea     r8d, [rdx+0Ah]; Radix
0x180027630  mov     rcx, [rbx+8]; String
0x180027634  call    cs:__imp_strtoul
0x18002763a  mov     ecx, eax; hostlong
0x18002763c  call    cs:__imp_htonl
0x180027642  mov     [rsp+48h+arg_8], eax
0x180027646  mov     edx, 2; unsigned __int16
0x18002764b  lea     r8, [rsp+48h+arg_8]; unsigned __int8 *
0x180027650  lea     rcx, [rsp+48h+arg_10]; this
0x180027655  call    ?setSockAddress@IASAttribute@IASTL@@QEAAXGQEAE@Z; IASTL::IASAttribute::setSockAddress(ushort,uchar * const)
0x18002765a  jmp     short loc_18002768F
0x18002765c  xor     edx, edx; EndPtr
0x18002765e  lea     r8d, [rdx+0Ah]; Radix
0x180027662  mov     rcx, [rbx+8]; String
0x180027666  call    cs:__imp_strtoul
0x18002766c  mov     [rdi+18h], eax
0x18002766f  jmp     short loc_18002768F
0x180027671  mov     r8d, [rbx]; MaxCount
0x180027674  lea     rdx, aTrue_0; "TRUE"
0x18002767b  mov     rcx, [rbx+8]; String1
0x18002767f  call    cs:__imp__strnicmp
0x180027685  xor     ebx, ebx
0x180027687  test    eax, eax
0x180027689  setz    bl
0x18002768c  mov     [rdi+18h], ebx
0x18002768f  mov     [rdi+10h], r14d
0x180027693  mov     rax, rdi
0x180027696  mov     rbx, [rsp+48h+arg_0]
0x18002769b  add     rsp, 20h
0x18002769f  pop     r15
0x1800276a1  pop     r14
0x1800276a3  pop     rdi
0x1800276a4  pop     rsi
0x1800276a5  pop     rbp
0x1800276a6  retn
```
