# IP_RESTRICTION_LIST::ReverseDNSLookup(sockaddr const *,int,STRU *,long *)

- ea: `0x180023d10`
- end: `0x180023e26`
- name: `?ReverseDNSLookup@IP_RESTRICTION_LIST@@SAJPEBUsockaddr@@HPEAVSTRU@@PEAJ@Z`
- size: `278`
- prototype: `__int64 __fastcall(const struct sockaddr *, int, struct STRU *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800235b0`

## callees

- `0x180001210`
- `0x180001250`
- `0x180023964`
- `0x180023d10`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x180023d57`
- `KERNEL32!GetTickCount64` at `0x180023d75`
- `KERNEL32!GetTickCount64` at `0x180023d57`
- `KERNEL32!GetTickCount64` at `0x180023d75`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180023d90`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180023d90`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180023d3c`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180023d3c`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180023de1`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180023de1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180023e0b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180023e0b`

## pseudocode

```c
__int64 __fastcall IP_RESTRICTION_LIST::ReverseDNSLookup(
        const struct sockaddr *a1,
        __int64 a2,
        struct STRU *a3,
        int *a4)
{
  int Key; // eax
  char *v8; // rbx
  __int64 v9; // rdi
  int v10; // edi
  _QWORD *v11; // rax
  void *v12; // rdi
  void *Block; // [rsp+20h] [rbp-38h] BYREF

  Block = 0;
  Key = CLKRHashTable::FindKey(IP_RESTRICTION_LIST::sm_pFastDNSLookupTable, a1, &Block);
  v8 = (char *)Block;
  if ( Key )
    goto LABEL_7;
  v9 = *((_QWORD *)Block + 28);
  if ( *((int *)Block + 1) >= 0 )
  {
    if ( GetTickCount64() - v9 <= 0x493E0 )
    {
      v10 = STRU::Copy(a3, *((const unsigned __int16 **)v8 + 5), *((_DWORD *)v8 + 14));
      if ( v10 < 0 )
        goto LABEL_12;
LABEL_10:
      v10 = 0;
      goto LABEL_12;
    }
    goto LABEL_6;
  }
  if ( GetTickCount64() - v9 > 0x2BF20 )
  {
LABEL_6:
    CLKRHashTable::DeleteRecord(IP_RESTRICTION_LIST::sm_pFastDNSLookupTable, v8);
LABEL_7:
    v11 = operator new(0x20u);
    Block = v11;
    v12 = v11;
    if ( !v11 )
    {
      v10 = -2147024882;
      goto LABEL_12;
    }
    *v11 = a1;
    v11[1] = a3;
    *((_DWORD *)v11 + 4) = 1;
    v11[3] = a4;
    IP_RESTRICTION_LIST::PrivateReverseDNSLookup((STRU **)v11);
    operator delete(v12);
    goto LABEL_10;
  }
  v10 = 0;
  *a4 = -2147023728;
LABEL_12:
  if ( v8 && _InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF) == 1 )
  {
    STRU::~STRU(v8 + 8);
    operator delete(v8);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180023d10  push    rbx
0x180023d12  push    rbp
0x180023d13  push    rsi
0x180023d14  push    rdi
0x180023d15  push    r14
0x180023d17  sub     rsp, 30h
0x180023d1b  mov     rbp, r8
0x180023d1e  mov     [rsp+58h+Block], 0
0x180023d27  mov     r14, rcx
0x180023d2a  lea     r8, [rsp+58h+Block]
0x180023d2f  mov     rdx, rcx
0x180023d32  mov     rsi, r9
0x180023d35  mov     rcx, cs:?sm_pFastDNSLookupTable@IP_RESTRICTION_LIST@@0PEAVFAST_DNS_LOOKUP_HASH@@EA; FAST_DNS_LOOKUP_HASH * IP_RESTRICTION_LIST::sm_pFastDNSLookupTable
0x180023d3c  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180023d42  mov     rbx, [rsp+58h+Block]
0x180023d47  test    eax, eax
0x180023d49  jnz     short loc_180023D96
0x180023d4b  mov     rdi, [rbx+0E0h]
0x180023d52  cmp     [rbx+4], eax
0x180023d55  jge     short loc_180023D75
0x180023d57  call    cs:__imp_GetTickCount64
0x180023d5d  sub     rax, rdi
0x180023d60  cmp     rax, 2BF20h
0x180023d66  ja      short loc_180023D86
0x180023d68  xor     edi, edi
0x180023d6a  mov     dword ptr [rsi], 80070490h
0x180023d70  jmp     loc_180023DF6
0x180023d75  call    cs:__imp_GetTickCount64
0x180023d7b  sub     rax, rdi
0x180023d7e  cmp     rax, 493E0h
0x180023d84  jbe     short loc_180023DD6
0x180023d86  mov     rcx, cs:?sm_pFastDNSLookupTable@IP_RESTRICTION_LIST@@0PEAVFAST_DNS_LOOKUP_HASH@@EA; FAST_DNS_LOOKUP_HASH * IP_RESTRICTION_LIST::sm_pFastDNSLookupTable
0x180023d8d  mov     rdx, rbx
0x180023d90  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x180023d96  mov     ecx, 20h ; ' '; Size
0x180023d9b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023da0  mov     [rsp+58h+Block], rax
0x180023da5  mov     rdi, rax
0x180023da8  test    rax, rax
0x180023dab  jz      short loc_180023DF1
0x180023dad  mov     [rax], r14
0x180023db0  mov     [rax+8], rbp
0x180023db4  mov     dword ptr [rax+10h], 1
0x180023dbb  mov     [rax+18h], rsi
0x180023dbf  test    rax, rax
0x180023dc2  jz      short loc_180023DF1
0x180023dc4  mov     rcx, rax; struct DNS_LOOKUP_WORK_ITEM *
0x180023dc7  call    ?PrivateReverseDNSLookup@IP_RESTRICTION_LIST@@CAXPEAVDNS_LOOKUP_WORK_ITEM@@@Z; IP_RESTRICTION_LIST::PrivateReverseDNSLookup(DNS_LOOKUP_WORK_ITEM *)
0x180023dcc  mov     rcx, rdi; Block
0x180023dcf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023dd4  jmp     short loc_180023DED
0x180023dd6  mov     r8d, [rbx+38h]
0x180023dda  mov     rcx, rbp
0x180023ddd  mov     rdx, [rbx+28h]
0x180023de1  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180023de7  mov     edi, eax
0x180023de9  test    eax, eax
0x180023deb  js      short loc_180023DF6
0x180023ded  xor     edi, edi
0x180023def  jmp     short loc_180023DF6
0x180023df1  mov     edi, 8007000Eh
0x180023df6  test    rbx, rbx
0x180023df9  jz      short loc_180023E19
0x180023dfb  or      eax, 0FFFFFFFFh
0x180023dfe  lock xadd [rbx], eax
0x180023e02  cmp     eax, 1
0x180023e05  jnz     short loc_180023E19
0x180023e07  lea     rcx, [rbx+8]
0x180023e0b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180023e11  mov     rcx, rbx; Block
0x180023e14  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023e19  mov     eax, edi
0x180023e1b  add     rsp, 30h
0x180023e1f  pop     r14
0x180023e21  pop     rdi
0x180023e22  pop     rsi
0x180023e23  pop     rbp
0x180023e24  pop     rbx
0x180023e25  retn
```
